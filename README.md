# chrome-dev-workflow: fast / local web development using chrome in insecure mode

The file ChromeInsecure.zip can be unzipped anywhere e.g. on your desktop.
It contains a Mac OS X application that runs Chrome with the following parameters:

    set chrome to "\"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome\""
    set userdatadir to "\"$HOME/Library/Application Support/Google/ChromeInsecure\""
    do shell script chrome & " --allow-file-access-from-files --disable-web-security --user-data-dir=" & userdatadir

Such a setup allows opening local files in the browser including local Javascript + CSS and still calling remote Json services.
No local backend server is needed.
No local Http proxy to the remote backend is needed.
The remote backend does not need to understand / enable CORS.
You might need to disable the CSRF check at the backend.
