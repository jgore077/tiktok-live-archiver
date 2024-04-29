<div align="center">


<h1> TikTok Live Archiver🎥</h1> (With Internet Archive Uploads)

<em>TikTok Live Recorder is a tool for recording live streaming tiktok.</em>

[![Licence](https://img.shields.io/github/license/Ileriayo/markdown-badges?style=for-the-badge)](./LICENSE) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

The TikTok Live Archiver is designed to monitor a TikTok users livestreams. It will check every minute whether they are live or not and if they are it will start recording. Once the recording is finished it will upload it to your Internet Archive account. The script is ran through a bash file that creates an infinite loop so errors will cause the program to restart.
</div>

# Original Repo
This repo is a detached fork of https://github.com/Michele0303/tiktok-live-recorder. The original maintainers have a github that features more functionality + instructions.

# Setup
Firstly install the python depedencies

```
pip install -r requirements.txt
```
<b><h1>YOU WILL ALSO NEED FFMPEG INSTALLED!</h1></b>
### Configure .env
To allow the archiver to upload to the Internet Archive you will need to provide 3 pieces of information; The identifier of the collection you wish to upload to, the email of your account, and your password. You will set these in the repos `.env` file. 

```env
IA_USERNAME= example@gmail.com
IA_PASSWORD= thisismyinternetarchivepassword
IDENTIFIER= uniqueidentiferforinternetarchive
```

### Configure metadata.json
When you first clone the repository a basic metadata template will be contained in `metadata.json`. You will need to change many of the keys in order for your files to be uploading correctly especially the title and date. You can also add additional keys so long as it follows the [metadata schema](https://archive.org/developers/metadata-schema/index.html).
```json
{
    "title": "my title",
    "mediatype": "video",
    "collection": "opensource_movies",
    "date": "date of your choice in the YYYY-MM-DD format",
    "description": "Your description",
    "subject": [ "subject 1", "subject 2"],
    "creator": "the creator",
    "language": "English",
    "licenseurl": "http://creativecommons.org/publicdomain/zero/1.0/"
}
```
# Usage
To run the archiver use
```
sh run.bash <username>
```
The script will run continously looking for livestreams and restarting on fatal errors.


