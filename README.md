storage-file-transfer-json-python
================================

Uploads and downloads files between Google Cloud Storage and the local filesystem using the Google Python Client Library. Uploads and downloads files between Google Cloud Storage and the local
filesystem using the Google APIs Python Client Library.

api: storage
keywords: cmdline, media, oauth2

chunked_transfer.py
SETUP:
  1. Download chunked_transfer.py and client_secrets.json to the same directory.
  2. As of August 2012, the Google APIs interface to Google Cloud Storage
  (a.k.a. the GCS JSON API) is in Limited Preview, so users must request access
  from the API Console Services tab:
      <https://code.google.com/apis/console/#:services>
  3. Visit the API Console Access tab to create a client ID and secret for an
  installed application:
    <https://code.google.com/apis/console/#:access>
  4. Add your client ID and secret to your client_secrets.json file.
  5. The first time the script runs, it will open a browser window asking for
  permission to access Google Cloud Storage on your behalf. After you've
  granted permission, the script creates a credentials.json file, which stores
  the access and refresh tokens acquired from the OAuth flow.

**USAGE**:
  This script uploads and downloads files in chunks between Google Cloud
  Storage and your local filesystem. It accepts two arguments: a file path and
  a Cloud Storage resource name in "gs://<bucket>/<object>" format. The order
  of these arguments dictates whether to upload or download (source first,
  destination second).

  For example, this command uploads filename to bucket 'foo' with object name
  'bar':

    $ python chunked_transfer.py Desktop/file_1 gs://foo/bar

  and this command downloads that object back to a file on the desktop:

    $ python chunked_transfer.py gs://foo/bar Desktop/file_2

  When an upload concludes, the script prints the new object's JSON
  representation.

