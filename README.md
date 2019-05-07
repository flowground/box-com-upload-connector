# ![LOGO](logo.png) Box 2.0 Uploads **flow**ground Connector

## Description

A generated **flow**ground connector for the Box 2.0 Uploads API (version 2.0).

Generated from: https://api.apis.guru/v2/specs/box.com/upload/2.0/swagger.json<br/>
Generated at: 2019-05-07T17:39:48+03:00

## API Description

The Box Uploads API allows users to add a new file or add a new file version in the same way as uploading file.

## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Upload File

> Use the Uploads API to allow users to add a new file.

*Tags:* `FileUpload`

### Create File Upload Session

> Use the Uploads API to create a new session to upload a new file.

*Tags:* `ChunkedUpload`

### Abort Upload Session

> Abort the upload session and discard all data uploaded. This cannot be reversed.

*Tags:* `ChunkedUpload`

#### Input Parameters
* `SESSION_ID` - _required_

### Upload Session Details

> Return the information about this session.

*Tags:* `ChunkedUpload`

#### Input Parameters
* `SESSION_ID` - _required_

### Upload Part

> Upload a part of the file to this session.

*Tags:* `ChunkedUpload`

#### Input Parameters
* `SESSION_ID` - _required_
* `Digest` - _required_ - The message digest of the partbody, formatted as specified by RFC 3230. The usage is sha=BASE64_ENCODED_DIGEST. Currently only SHA-1 is supported.As per RFC 3230, the output from SHA-1 algorithm must be Base64 encoded.
* `Content-Range` - _required_ - Byte range of part within overall file. E.g: bytes 8388608-16777215/445856194. It must not overlap with the range of a part already uploaded to this session.

### Commit Upload

> Create a Box file comprised of the uploaded parts.

*Tags:* `ChunkedUpload`

#### Input Parameters
* `SESSION_ID` - _required_
* `Digest` - _required_ - The message digest of the file, formatted as specified by RFC 3230. The usage is sha=BASE64_ENCODED_DIGEST. Currently only SHA-1 is supported.As per RFC 3230, the output from SHA-1 algorithm must be Base64 encoded.
* `If-Match` - _optional_ - This is in the 'etag' field of the file object. See https://developer.box.com/v2.0/reference#if-match
* `If-Non-Match` - _optional_ - This is in the 'etag' field of the file object. See https://developer.box.com/v2.0/reference#if-match

### List Parts

> Return the list of parts uploaded so far for this session.

*Tags:* `ChunkedUpload`

#### Input Parameters
* `SESSION_ID` - _required_
* `offset` - _optional_ - Zero-based index of first part to return. Defaults to zero, if not specified.
* `limit` - _optional_ - How many parts to return. Defaults to 1000 if not specified, which is also the maximum value allowed.

### Upload File Version

> This method is used to upload a new version of an existing file in a user's account.

*Tags:* `FileUpload`

#### Input Parameters
* `FILE_ID` - _required_
* `If-Match` - _optional_ - This is in the 'etag' field of the file object

### Create File Upload Session

> Use the Uploads API to create a new session to upload a new version of existing file.

*Tags:* `ChunkedUpload`

#### Input Parameters
* `FILE_ID` - _required_

## License

**flow**ground :- Telekom iPaaS / box-com-upload-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
