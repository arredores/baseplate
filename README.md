# Baseplate

<div class="meta subtitle">
Beautiful documents, no pain
</div>

Baseplate is a dead-simple way to turn
[markdown](http://daringfireball.net/projects/markdown/) files into
beautifully-styled webpages without any external programs. Just drop files in a
web-accessible directory and go. It uses
[showdown.js](https://github.com/coreyti/showdown) to render markdown on the
fly in the browser.

Features:

* Updating the output is simple: just edit the markdown source files. Whenever
  you reload the Baseplate index page, AJAX fetches the markdown file and
  re-renders the output using showdown.js.
* No special server is required. Publish documents on any website.
* `Last-Modified` headers are parsed and included in the page footer to
  indicate when the content was last changed.
* Page titles are automatically updated with the content of the first H1 header.

Non-features:

* Baseplate is not as flexible as alternatives like
  [jekyll](http://jekyllrb.com/); it cannot run other programs like
  [Sass](http://sass-lang.com/) to post-process or minimize CSS or JavaScript
  files.
* All markdown source files must be web-accessible. Otherwise, Baseplate would
  not be able to read them.

## Demo

See this document rendered by Baseplate.  
[http://quadpoint.org/projects/baseplate/#!/README](http://quadpoint.org/projects/baseplate/#!/README)

Baseplate uses `README.md` as the source.  
[http://quadpoint.org/projects/baseplate/README.md](http://quadpoint.org/projects/baseplate/README.md)

## Installation and usage

Three simple commands get you a full Baseplate installation.

    % git clone git://github.com/msparks/baseplate.git
    % cd baseplate
    % python -m SimpleHTTPServer 8001

The last command starts a Python webserver that serves files from the
*baseplate* directory at [http://localhost:8001](http://localhost:8001). If
everything worked, you should see this document at that URL.

Adding new documents is easy. Just create new markdown files (with the
extension *.md*) in the *baseplate* directory (the same one that contains
*index.html*). To see these documents using Baseplate, add `#!/pagename` to the
URL, where `pagename` is the name of the corresponding file without the *.md*
extension. For example, the content for this page is in `README.md`, so the
rendered page can be accessed at
[http://localhost:8001/#!/README](http://localhost:8001/#!/README).

If no page is specified in the URL, Baseplate will attempt to load `index.md`
first. If that fails, it will try to load `README.md` (this file).

### Hosting Baseplate elsewhere

The quick-start example above shows how host Baseplate-rendered documents on
your own computer, but you can easily use Baseplate anywhere you have
public webspace. Just copy the files created by the `git clone` command to a
web-accessible directory on your webhost of choice. After that, you need only
add and update your markdown files.

### Using Baseplate on Dropbox

[Dropbox](http://db.tt/hcdgDWe) is a free service for putting your files in the
cloud. All Dropbox accounts include a
[Public directory](http://www.dropbox.com/help/16) that you can drop files in
to instantly publish on the web. This feature works great with Baseplate; just
install Baseplate in your Public directory and copy the public link to the
`index.html` file in your Baseplate installation.
