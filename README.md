# stylesheets

This repository contains asciidoc presentation stylesheets

### Requirements

* asciidoc
* make
* web browser

### Run

* Clone the stylesheet repo into your presentation directory
```
$ mkdir presentation && cd presentation
$ git clone https://github.com/vengatlnx/stylesheets.git

```

* Create a presentation document in asciidoc `(slide.asciidoc)`
```
== HelloWorld
=== HelloWorld
This is my first html presentation using asciidoc
```

* Create a Makefile to generate an asciidoc presentation slide
```
TOPDIR = ../

EXPORT_WIDTH  = 1024

images_dia = $(wildcard figures/*.dia)
images_png = $(images_dia:.dia=.png)

all: slides.html

slides.html: $(images_png) 

clean:
	rm -f $(images_png)
	rm -f slides.html
	rm -fr code/simple

include $(TOPDIR)/stylesheets/Makefile.rules
```

* Open the html presentation on your web browser
```
$ make && firefox slide.html
```
*Note*: Refer [slide2pdf](https://github.com/vengatlnx/slide2pdf) to convert your html slide to pdf