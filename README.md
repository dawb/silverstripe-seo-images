# Optimised images for SilverStripe


This Module is a combination of Ralph Slooten's [axllent/silverstripe-image-optimiser](https://github.com/axllent/silverstripe-image-optimiser) and Bastian Fritsch's [nomidi/silverstripe-webp-image](https://github.com/nomidi/silverstripe-webp-image)

This module automatically optimise, compress and generates WebP images from both uploaded as well as any resampled
(cropped, scaled etc) images in SilverStripe.

Images (JPG, PNG & GIF) are automatically
optimised, provided you have the correct binaries installed (see "Installation" below) and it also generates WebP images for all optimized and compressed (JPG & PNG) images. More Information about webp images [https://developers.google.com/speed/webp/](https://developers.google.com/speed/webp/)

The module overrides the default `FlysystemAssetStore` to first optimise the image
before adding the image to the store, then if the image is a JPG or PNG it will create a WebP image. It works transparently.


## Requirements

- `silverstripe/assets` ^4.2
- [spatie/image-optimizer](https://github.com/spatie/image-optimizer) - automatically installed
- JpegOptim, Optipng, Pngquant 2 & Gifsicle binaries (see below)
- GDLib with webp Extension


## Optimisation tools

The module uses [spatie/image-optimizer](https://github.com/spatie/image-optimizer) and will use the
following optimisers if they are both present and in your default path on your system:

- [JpegOptim](https://github.com/tjko/jpegoptim)
- [Optipng](http://optipng.sourceforge.net/)
- [Pngquant 2](https://pngquant.org/)
- [Gifsicle](http://www.lcdf.org/gifsicle/)


## Installation

```shell
composer require axllent/silverstripe-image-optimiser
```

### Installing the utilities on Ubuntu:

```bash
sudo apt-get install jpegoptim optipng pngquant gifsicle
```


### Installing the utilities on Alpine Linux:

```bash
apk add jpegoptim optipng pngquant gifsicle
```


## Usage

Assuming you have the necessary binaries installed, it should "just work" with the default settings
once you have flushed your SilverStripe installation.


For custom optimisation settings, please refer to the
[Configuration documentation](docs/en/Configuration.md).
