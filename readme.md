# Mongodb to Amazon s3 Backup Script

#### this is an improvement of the [original](https://github.com/RGBboy/mongodb-s3-backup) RGBoy script.

## Requirements

* Running mongod process
* mongodump
* mongo (**Lower then 3.0** - this script uses `eval`)
* openssl
* tar
* rm
* curl (using port 443 for https)

###Access Control

If authorization is enabled, you must have access to all actions on all resources in order to run eval. Providing such access is not recommended, but if your organization requires a user to run eval, create a role that grants anyAction on anyResource. Do not assign this role to any other user.


## Usage

`bash /path/to/backup.sh -u MONGODB_USER -p MONGODB_PASSWORD -k AWS_ACCESS_KEY -s AWS_SECRET_KEY -r S3_REGION -b S3_BUCKET [-P MONGODB_PORT]`

Where `S3_REGION` is in the format `ap-southeast-1`

And port is optional while the default value is 27017.

<!--## Cron

### Daily

Add the following line to `/etc/cron.d/db-backup` to run the script every day at midnight (UTC time) 

    0 0 * * * root /bin/bash /path/to/backup.sh -u MONGODB_USER -p MONGODB_PASSWORD -k AWS_ACCESS_KEY -s AWS_SECRET_KEY -b S3_BUCKET [-P MONGODB_PORT]-->

# License 

(The MIT License)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
