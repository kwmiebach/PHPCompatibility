# phpcs docker image with PHP Compatiblity Ruleset

[Docker_Hub](https://hub.docker.com/r/domw/phpcompatibility)

## Compilation

    docker login

    docker build -t domw/phpcompatibility:latest ./

    docker push domw/phpcompatibility:latest

    docker build -t domw/phpcompatibility:7.1-cli ./

    docker push domw/phpcompatibility:7.1-cli 

## Test

    docker-compose run --rm phpcompatibility
    
    docker-compose run --rm phpcompatibility -i
    
## Usage
    
    docker pull domw/phpcompatibility
    
    docker run --rm -v $PWD:/code:ro domw/phpcompatibility phpcs --version
    
    docker run --rm -v $PWD:/code:ro domw/phpcompatibility phpcs -i
       
    docker run --rm -v $PWD:/code:ro domw/phpcompatibility phpcs --standard=PHPCompatibility --runtime-set testVersion 5.6 /path/to/code
    
    docker run --rm -v $PWD:/code:ro domw/phpcompatibility phpcs --standard=PHPCompatibility --runtime-set testVersion 5.5-5.6 --report=full,summary,gitblame /path/to/code
    
    docker run --rm -v $PWD:/code:ro domw/phpcompatibility phpcs --standard=PHPCompatibility --runtime-set testVersion 7.0 --colors --warning-severity=0  --report=full,summary,gitblame /path/to/code
    
    docker run --rm -v $PWD:/code:ro domw/phpcompatibility phpcs --standard=PHPCompatibility --runtime-set testVersion 7.0 --colors --warning-severity=0 --report=full,summary --extensions=php,phtml /path/to/code
