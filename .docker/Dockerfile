# Usa a imagem oficial do FrankenPHP como base
FROM dunglas/frankenphp:1-php8.4

# Instala Node.js 20.x
RUN apt-get update && apt-get install -y \
    curl \
    && curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

# Instala extensões PHP necessárias para o Laravel
RUN install-php-extensions \
    pdo_mysql \
    mbstring \
    xml \
    bcmath \
    curl \
    gd \
    intl \
    zip \
    redis

# Instala o Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Define o diretório de trabalho
WORKDIR /app

# Copia os arquivos da aplicação
COPY ./src /app

# Instala as dependências do Laravel via Composer
# O --no-dev remove dependências de desenvolvimento para produção
# Para desenvolvimento, remova a flag --no-dev
RUN composer install --no-scripts --no-autoloader --prefer-dist

# Define permissões corretas para Laravel
RUN chown -R www-data:www-data /app/storage /app/bootstrap/cache \
    && chmod -R 775 /app/storage /app/bootstrap/cache
