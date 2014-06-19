wkhtml2pdf
==========
Version 1.0 - Laravel 4 - Html to PDF Composer Package
19-06-2014 #vodun add param to download or get url to file
	example:  PDF::url('http://google.com','jj','F');  get url google.com with filename jj and return href to file pdf

#Usage#

	return PDF::html('hello'); // hello is naw of blade template
	
	return PDF::html('hello',array('name' => 'Nithin')); // pass variables for the view as second option
	
	return PDF::html('hello',array('name' => 'Nithin'), 'New File'); // thrid option is for the name of the pdf file thats generated

	PDF::url('http://google.com'); // Pdf from url
	
	#vodun add param to download or get url to file
	example:  PDF::url('http://google.com','jj','F');  get url google.com with filename jj and return href to file pdf

## Quick start

### Required setup

In the `require` key of `composer.json` file add the following

    "nitmedia/wkhtml2pdf": "dev-master"

Run the Composer update comand

    $ composer update

In your `config/app.php` add `'Nitmedia\Wkhtml2pdf\Wkhtml2pdfServiceProvider'` to the end of the `$providers` array

    'providers' => array(

        'Illuminate\Foundation\Providers\ArtisanServiceProvider',
        'Illuminate\Auth\AuthServiceProvider',
        ...
        'Nitmedia\Wkhtml2pdf\Wkhtml2pdfServiceProvider',

    ),

At the end of `config/app.php` add `'PDF'    => 'Nitmedia\Wkhtml2pdf\Facades\Wkhtml2pdf'` to the `$aliases` array

    'aliases' => array(

        'App'        => 'Illuminate\Support\Facades\App',
        'Artisan'    => 'Illuminate\Support\Facades\Artisan',
        ...
        'PDF'    => 'Nitmedia\Wkhtml2pdf\Facades\Wkhtml2pdf',

    ),

## Configuration
Please set the driver file accoridng to the current OS, Supported drivers include: mac osx, linux 32, linux 64

    php artisan config:publish nitmedia/wkhtml2pdf

### Driver
[wkhtml2pdf][1]

Version: [0.12.1-rc][2]


### Driver types

- wkhtmltopdf-0.12.1-OS-X.i386  - `Mac OS X 10.8+ (Carbon), 32-bit`
- wkhtmltopdf-amd64 - `Linux (Debian Wheezy), 64-bit, for recent distributions (i.e. glibc 2.13 or later)`
- wkhtmltopdf-i386 -  `Linux (Debian Wheezy), 32-bit, for recent distributions (i.e. glibc 2.13 or later)`

## Troubleshooting
	**There is a debug flag in config where you can test the output of the drivers.**

	1. Some users have noted a strange permissions issue executing the drivers. Try chmod'ing the driver files to solve the issue.
	2. All asset urls must be absolute, relative urls wont work.


The MIT License (MIT)

Copyright (c) <2013> <Nithin Meppurathu>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.


  [1]: http://wkhtmltopdf.org/
  [2]: https://github.com/wkhtmltopdf/wkhtmltopdf/tree/c22928d
