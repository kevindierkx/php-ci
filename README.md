# PHP-CI - Docker images

This is a collection of very specific docker images we're using for CI/CD.

The 'base' images contain a collection of programs for working with [Composer](https://getcomposer.org) and creating RPM or DEB packages. The `-ioncube` images add the PHP ionCube Loader to the base images and can be used to test and build ionCube encoded applications.

**We do not recommend using these images in your project.** We're not actively maintaining these images and only use them for some very basic CI/CD work on legacy projects.

## Security

If you discover a security vulnerability within this package, please send an e-mail to Kevin Dierkx via kevin@distortedfusion.com. All security vulnerabilities will be promptly addressed.

## Contributing

Contributions are welcome and will be [fully credited](https://github.com/kevindierkx/php-ci/graphs/contributors).

## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.
