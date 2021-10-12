A very easy to use library to download videos from reddit with sound without installing external installation of ffmpeg. The library can also be used to download pictures all just with a reddit post link
note that this package does only download media from posts with images/video directly uploaded to reddit and not from sources like imgur or youtube / vimeo.

Usage:
To Install the package:

```
pip install RedDownloader
```

To Import package just do:

```python
from RedDownloader import RedDownloader
```

RedDownloader is auth less you don't need to have a praw bot to use this package.

After importing, Downloading is just a single line of code

```python
RedDownloader.Download(url)
```

This will automatically download media from the passed url it would automatically detect if it's a picture/video with default options. to pass in an output filename just pass in the output parameter as:

```python
RedDownloader.Download(url , output="MyAwesomeRedditMedia")
```

To set a custom path for downloaded file use ```destination``` as an argument like

```python
RedDownloader.Download(url , output="MyAwesomeRedditMedia" , destination="D:/Pictures/")
```

default file name is "downloaded".
you don't have to pass in extensions to the output parameter.

default download location for file is current working directory.

Another argument is the ```quality``` argument which defines the resolution to download if the filetype is a video the avaliable options to choose from are 360 , 720 , 1080 please note that higher resolution would result in bigger file size. An example:

```python
RedDownloader.Download(url , output="MyAwesomeRedditMedia" , quality = 1080)
```
You at times might need to know the media type of the file being downloaded for that you can use the ```GetMediaType()``` method

```python
file = RedDownloader.Download(url)
print(file.GetMediaType())
```

for images it returns a ```i``` while for videos it returns a ```v```

The package has been tested for videos with no sound as well. It doesn't support gallery posts yet