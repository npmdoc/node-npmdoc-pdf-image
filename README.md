# api documentation for  [pdf-image (v1.1.0)](https://github.com/mooz/node-pdf-image#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-pdf-image.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-pdf-image) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-pdf-image.svg)](https://travis-ci.org/npmdoc/node-npmdoc-pdf-image)
#### Provides an interface to convert PDF's pages to png files in Node.js by using ImageMagick.

[![NPM](https://nodei.co/npm/pdf-image.png?downloads=true)](https://www.npmjs.com/package/pdf-image)

[![apidoc](https://npmdoc.github.io/node-npmdoc-pdf-image/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-pdf-image_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-pdf-image/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-pdf-image/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-pdf-image/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/mooz/node-pdf-image/issues"
    },
    "dependencies": {
        "chai": "~1.9.2",
        "es6-promise": "~2.0.0"
    },
    "description": "Provides an interface to convert PDF's pages to png files in Node.js by using ImageMagick.",
    "devDependencies": {
        "mocha": "~2.3.4"
    },
    "directories": {},
    "dist": {
        "shasum": "2ddc0397dcf0f2007e40519cdddd7ba64fa4d367",
        "tarball": "https://registry.npmjs.org/pdf-image/-/pdf-image-1.1.0.tgz"
    },
    "gitHead": "a2f393949ab969c5cc6272e6757b435aae40d065",
    "homepage": "https://github.com/mooz/node-pdf-image#readme",
    "main": "index.js",
    "maintainers": [
        {
            "name": "mooz",
            "email": "stillpedant@gmail.com"
        }
    ],
    "name": "pdf-image",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/mooz/node-pdf-image.git"
    },
    "scripts": {
        "test": "mocha tests/*"
    },
    "version": "1.1.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module pdf-image](#apidoc.module.pdf-image)
1.  [function <span class="apidocSignatureSpan">pdf-image.</span>PDFImage (pdfFilePath, options)](#apidoc.element.pdf-image.PDFImage)
1.  object <span class="apidocSignatureSpan">pdf-image.</span>PDFImage.prototype

#### [module pdf-image.PDFImage](#apidoc.module.pdf-image.PDFImage)
1.  [function <span class="apidocSignatureSpan">pdf-image.</span>PDFImage (pdfFilePath, options)](#apidoc.element.pdf-image.PDFImage.PDFImage)

#### [module pdf-image.PDFImage.prototype](#apidoc.module.pdf-image.PDFImage.prototype)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>constructConvertCommandForPage (pageNumber)](#apidoc.element.pdf-image.PDFImage.prototype.constructConvertCommandForPage)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>constructConvertOptions ()](#apidoc.element.pdf-image.PDFImage.prototype.constructConvertOptions)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>constructGetInfoCommand ()](#apidoc.element.pdf-image.PDFImage.prototype.constructGetInfoCommand)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>convertPage (pageNumber)](#apidoc.element.pdf-image.PDFImage.prototype.convertPage)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>getInfo ()](#apidoc.element.pdf-image.PDFImage.prototype.getInfo)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>getOutputImagePathForPage (pageNumber)](#apidoc.element.pdf-image.PDFImage.prototype.getOutputImagePathForPage)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>numberOfPages ()](#apidoc.element.pdf-image.PDFImage.prototype.numberOfPages)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>parseGetInfoCommandOutput (output)](#apidoc.element.pdf-image.PDFImage.prototype.parseGetInfoCommandOutput)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>setConvertExtension (convertExtension)](#apidoc.element.pdf-image.PDFImage.prototype.setConvertExtension)
1.  [function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>setConvertOptions (convertOptions)](#apidoc.element.pdf-image.PDFImage.prototype.setConvertOptions)



# <a name="apidoc.module.pdf-image"></a>[module pdf-image](#apidoc.module.pdf-image)

#### <a name="apidoc.element.pdf-image.PDFImage"></a>[function <span class="apidocSignatureSpan">pdf-image.</span>PDFImage (pdfFilePath, options)](#apidoc.element.pdf-image.PDFImage)
- description and source-code
```javascript
function PDFImage(pdfFilePath, options) {
  if (!options) options = {};

  this.pdfFilePath = pdfFilePath;
  this.pdfFileBaseName = path.basename(pdfFilePath, ".pdf");

  this.setConvertOptions(options.convertOptions);
  this.setConvertExtension(options.convertExtension);
  this.useGM = options.graphicsMagick || false;

  this.outputDirectory = options.outputDirectory || path.dirname(pdfFilePath);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.pdf-image.PDFImage"></a>[module pdf-image.PDFImage](#apidoc.module.pdf-image.PDFImage)

#### <a name="apidoc.element.pdf-image.PDFImage.PDFImage"></a>[function <span class="apidocSignatureSpan">pdf-image.</span>PDFImage (pdfFilePath, options)](#apidoc.element.pdf-image.PDFImage.PDFImage)
- description and source-code
```javascript
function PDFImage(pdfFilePath, options) {
  if (!options) options = {};

  this.pdfFilePath = pdfFilePath;
  this.pdfFileBaseName = path.basename(pdfFilePath, ".pdf");

  this.setConvertOptions(options.convertOptions);
  this.setConvertExtension(options.convertExtension);
  this.useGM = options.graphicsMagick || false;

  this.outputDirectory = options.outputDirectory || path.dirname(pdfFilePath);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.pdf-image.PDFImage.prototype"></a>[module pdf-image.PDFImage.prototype](#apidoc.module.pdf-image.PDFImage.prototype)

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.constructConvertCommandForPage"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>constructConvertCommandForPage (pageNumber)](#apidoc.element.pdf-image.PDFImage.prototype.constructConvertCommandForPage)
- description and source-code
```javascript
constructConvertCommandForPage = function (pageNumber) {
  var pdfFilePath = this.pdfFilePath;
  var outputImagePath = this.getOutputImagePathForPage(pageNumber);
  var convertOptionsString = this.constructConvertOptions();
  return util.format(
    "%s %s'%s[%d]' '%s'",
    this.useGM ? "gm convert" : "convert",
    convertOptionsString ? convertOptionsString + " " : "",
    pdfFilePath, pageNumber, outputImagePath
  );
}
```
- example usage
```shell
...
    return optionName;
  }
}, this).join(" ");
  },
  convertPage: function (pageNumber) {
var pdfFilePath     = this.pdfFilePath;
var outputImagePath = this.getOutputImagePathForPage(pageNumber);
var convertCommand  = this.constructConvertCommandForPage(pageNumber);

var promise = new Promise(function (resolve, reject) {
  function convertPageToImage() {
    exec(convertCommand, function (err, stdout, stderr) {
      if (err) {
        return reject({
          message: "Failed to convert page to image",
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.constructConvertOptions"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>constructConvertOptions ()](#apidoc.element.pdf-image.PDFImage.prototype.constructConvertOptions)
- description and source-code
```javascript
constructConvertOptions = function () {
  return Object.keys(this.convertOptions).sort().map(function (optionName) {
    if (this.convertOptions[optionName] !== null) {
      return optionName + " " + this.convertOptions[optionName];
    } else {
      return optionName;
    }
  }, this).join(" ");
}
```
- example usage
```shell
...
},
setConvertExtension: function (convertExtension) {
  this.convertExtension = convertExtension || "png";
},
constructConvertCommandForPage: function (pageNumber) {
  var pdfFilePath = this.pdfFilePath;
  var outputImagePath = this.getOutputImagePathForPage(pageNumber);
  var convertOptionsString = this.constructConvertOptions();
  return util.format(
    "%s %s'%s[%d]' '%s'",
    this.useGM ? "gm convert" : "convert",
    convertOptionsString ? convertOptionsString + " " : "",
    pdfFilePath, pageNumber, outputImagePath
  );
},
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.constructGetInfoCommand"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>constructGetInfoCommand ()](#apidoc.element.pdf-image.PDFImage.prototype.constructGetInfoCommand)
- description and source-code
```javascript
constructGetInfoCommand = function () {
  return util.format(
    "pdfinfo '%s'",
    this.pdfFilePath
  );
}
```
- example usage
```shell
...
      info[RegExp.$1] = RegExp.$2;
    }
  });
  return info;
},
getInfo: function () {
  var self = this;
  var getInfoCommand = this.constructGetInfoCommand();
  var promise = new Promise(function (resolve, reject) {
    exec(getInfoCommand, function (err, stdout, stderr) {
      if (err) {
        return reject({
          message: "Failed to get PDF'S information",
          error: err,
          stdout: stdout,
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.convertPage"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>convertPage (pageNumber)](#apidoc.element.pdf-image.PDFImage.prototype.convertPage)
- description and source-code
```javascript
convertPage = function (pageNumber) {
  var pdfFilePath     = this.pdfFilePath;
  var outputImagePath = this.getOutputImagePathForPage(pageNumber);
  var convertCommand  = this.constructConvertCommandForPage(pageNumber);

  var promise = new Promise(function (resolve, reject) {
    function convertPageToImage() {
      exec(convertCommand, function (err, stdout, stderr) {
        if (err) {
          return reject({
            message: "Failed to convert page to image",
            error: err,
            stdout: stdout,
            stderr: stderr
          });
        }
        return resolve(outputImagePath);
      });
    }

    fs.stat(outputImagePath, function (err, imageFileStat) {
      var imageNotExists = err && err.code === "ENOENT";
      if (!imageNotExists && err) {
        return reject({
          message: "Failed to stat image file",
          error: err
        });
      }

      // convert when (1) image doesn't exits or (2) image exists
      // but its timestamp is older than pdf's one

      if (imageNotExists) {
        // (1)
        convertPageToImage();
        return;
      }

      // image exist. check timestamp.
      fs.stat(pdfFilePath, function (err, pdfFileStat) {
        if (err) {
          return reject({
            message: "Failed to stat PDF file",
            error: err
          });
        }

        if (imageFileStat.mtime < pdfFileStat.mtime) {
          // (2)
          convertPageToImage();
          return;
        }

        return resolve(outputImagePath);
      });
    });
  });
  return promise;
}
```
- example usage
```shell
...

## Usage

'''javascript
var PDFImage = require("pdf-image").PDFImage;

var pdfImage = new PDFImage("/tmp/slide.pdf");
pdfImage.convertPage(0).then(function (imagePath) {
  // 0-th page (first page) of the slide.pdf is available as slide-0.png
  fs.existsSync("/tmp/slide-0.png") // => true
});
'''

## Express
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.getInfo"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>getInfo ()](#apidoc.element.pdf-image.PDFImage.prototype.getInfo)
- description and source-code
```javascript
getInfo = function () {
  var self = this;
  var getInfoCommand = this.constructGetInfoCommand();
  var promise = new Promise(function (resolve, reject) {
    exec(getInfoCommand, function (err, stdout, stderr) {
      if (err) {
        return reject({
          message: "Failed to get PDF'S information",
          error: err,
          stdout: stdout,
          stderr: stderr
        });
      }
      return resolve(self.parseGetInfoCommandOutput(stdout));
    });
  });
  return promise;
}
```
- example usage
```shell
...
      }
      return resolve(self.parseGetInfoCommandOutput(stdout));
    });
  });
  return promise;
},
numberOfPages: function () {
  return this.getInfo().then(function (info) {
    return info["Pages"];
  });
},
getOutputImagePathForPage: function (pageNumber) {
  return path.join(
    this.outputDirectory,
    this.pdfFileBaseName + "-" + pageNumber + "." + this.convertExtension
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.getOutputImagePathForPage"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>getOutputImagePathForPage (pageNumber)](#apidoc.element.pdf-image.PDFImage.prototype.getOutputImagePathForPage)
- description and source-code
```javascript
getOutputImagePathForPage = function (pageNumber) {
  return path.join(
    this.outputDirectory,
    this.pdfFileBaseName + "-" + pageNumber + "." + this.convertExtension
  );
}
```
- example usage
```shell
...
  this.convertOptions = convertOptions || {};
},
setConvertExtension: function (convertExtension) {
  this.convertExtension = convertExtension || "png";
},
constructConvertCommandForPage: function (pageNumber) {
  var pdfFilePath = this.pdfFilePath;
  var outputImagePath = this.getOutputImagePathForPage(pageNumber);
  var convertOptionsString = this.constructConvertOptions();
  return util.format(
    "%s %s'%s[%d]' '%s'",
    this.useGM ? "gm convert" : "convert",
    convertOptionsString ? convertOptionsString + " " : "",
    pdfFilePath, pageNumber, outputImagePath
  );
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.numberOfPages"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>numberOfPages ()](#apidoc.element.pdf-image.PDFImage.prototype.numberOfPages)
- description and source-code
```javascript
numberOfPages = function () {
  return this.getInfo().then(function (info) {
    return info["Pages"];
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.parseGetInfoCommandOutput"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>parseGetInfoCommandOutput (output)](#apidoc.element.pdf-image.PDFImage.prototype.parseGetInfoCommandOutput)
- description and source-code
```javascript
parseGetInfoCommandOutput = function (output) {
  var info = {};
  output.split("\n").forEach(function (line) {
    if (line.match(/^(.*?):[ \t]*(.*)$/)) {
      info[RegExp.$1] = RegExp.$2;
    }
  });
  return info;
}
```
- example usage
```shell
...
        return reject({
          message: "Failed to get PDF'S information",
          error: err,
          stdout: stdout,
          stderr: stderr
        });
      }
      return resolve(self.parseGetInfoCommandOutput(stdout));
    });
  });
  return promise;
},
numberOfPages: function () {
  return this.getInfo().then(function (info) {
    return info["Pages"];
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.setConvertExtension"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>setConvertExtension (convertExtension)](#apidoc.element.pdf-image.PDFImage.prototype.setConvertExtension)
- description and source-code
```javascript
setConvertExtension = function (convertExtension) {
  this.convertExtension = convertExtension || "png";
}
```
- example usage
```shell
...
function PDFImage(pdfFilePath, options) {
if (!options) options = {};

this.pdfFilePath = pdfFilePath;
this.pdfFileBaseName = path.basename(pdfFilePath, ".pdf");

this.setConvertOptions(options.convertOptions);
this.setConvertExtension(options.convertExtension);
this.useGM = options.graphicsMagick || false;

this.outputDirectory = options.outputDirectory || path.dirname(pdfFilePath);
}

PDFImage.prototype = {
constructGetInfoCommand: function () {
...
```

#### <a name="apidoc.element.pdf-image.PDFImage.prototype.setConvertOptions"></a>[function <span class="apidocSignatureSpan">pdf-image.PDFImage.prototype.</span>setConvertOptions (convertOptions)](#apidoc.element.pdf-image.PDFImage.prototype.setConvertOptions)
- description and source-code
```javascript
setConvertOptions = function (convertOptions) {
  this.convertOptions = convertOptions || {};
}
```
- example usage
```shell
...

function PDFImage(pdfFilePath, options) {
  if (!options) options = {};

  this.pdfFilePath = pdfFilePath;
  this.pdfFileBaseName = path.basename(pdfFilePath, ".pdf");

  this.setConvertOptions(options.convertOptions);
  this.setConvertExtension(options.convertExtension);
  this.useGM = options.graphicsMagick || false;

  this.outputDirectory = options.outputDirectory || path.dirname(pdfFilePath);
}

PDFImage.prototype = {
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
