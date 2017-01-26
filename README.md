# BraindeadDB

BraindeadDB is a simple key-value store based on the file system.
It supports versioning, arbitrary data, and data-race-free updates.

Initial implementations are provided in Python and Go. JavaScript might follow.

## Design

* BraindeadDB keys are SHA1 hashes of the values.
* To list all available documents, send a `GET` to `/`.
* To set a new document, send a `PUT` to `/`. It will return the hash.
* To retrieve the values under a key, send a `GET` to `/<hash>`. This may result in a HTTP 404.
* To make an update, send a `POST` to `/<hash>`. It will return a new hash.
* To delete a document, send a `DELETE` to `/<hash`.

## FAQ

**Q**: Are you serious?

**A**: No.

**Q**: How fast is it?

**A**: How fast is your filesystem cache?

**Q**: Where in the CAP space is BraindeadDB?

**A**: Somewhere in the "lolnope" space.
