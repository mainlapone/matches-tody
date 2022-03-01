# Flask Demo


This is a small Flask app that replies with a header dump to any request. 


You can deploy this application as is on Clever Cloud:

```bash
git remote add clevercloud {your-clever-cloud-endpoint}
git push clevercloud master
```

And it will do the trick.

We demonstrate several Clever Cloud possibilities in here:

## Choose python version

We have a python_version file in the clevercloud repository that
contains "3". This will select the latest python 3 version installed (at the time of
this writing, 3.4). Doc here:
[https://www.clever-cloud.com/doc/python/python_apps/#use-python-3](https://www.clever-cloud.com/doc/python/python_apps/#use-python-3)

## Build app in a subfolder

In the `clevercloud/python.json` file, we have the
"build"."folder" field that points to the "app" folder. We will build & run the app
from this "app" folder.

## Static files

We set up in `clevercloud/python.json` a "static" folder: everything in
that folder will be served statically. Note that the static folder will be the root of
static files requests. In this example, to get to Cat.svg which is in the "s" folder in
the clevercloud/static folder, you need to request "http://{yourdomain}/s/Cat.svg".

You can also see that "s" is a link to the static folder at the root of the app. It's just
to show that you can do symlinks.

## Run the app

As explained in
[https://www.clever-cloud.com/doc/python/python_apps/#select-your-module](https://www.clever-cloud.com/doc/python/python_apps/#select-your-module) 
we ask Clever Cloud to run the "app" Flask application defined in the "hello.py" file. So
the "module" field is "hello:app".
