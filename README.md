# fast / local web development using chrome in insecure mode (on OS X)

The file [ChromeInsecure.zip](ChromeInsecure.zip?raw=true) can be unzipped anywhere e.g. on your desktop.
It contains a Mac OS X application that runs Chrome with the following parameters.
BTW this is Applescript:

    set chrome to "\"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome\""
    set userdatadir to "\"$HOME/Library/Application Support/Google/ChromeInsecure\""
    do shell script chrome & " --allow-file-access-from-files --disable-web-security --user-data-dir=" & userdatadir

- Such a setup allows opening local files in the browser using the file: protocol and still allows calling remote JSON or other services.
- No local backend server is needed.
- No local HTTP server and/or proxy is needed.
- The remote backend does not need to understand / enable CORS.
- But you might need to disable the CSRF check at the backend.

It has been tested with an AngularJs 1.6 based UI and a Spring Boot 1.5 backend.

**Beware:** this browser instance is really insecure!
It should be used for development purposes with trusted backends only.

Adaptations for other operating systems are welcome.
Feel free to open a pull request.
