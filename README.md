# strophe-rebind

Rebind plugin for strophe-js

## Usage

Just load this script after main strophe.js file:

```
<head>
<!-- ... -->
<script type="text/javascript" src="strophe.js"></script>
<script type="text/javascript" src="strophe.rebind.js"></script>
<!-- ... -->
</head>
```

doing this will offer two new method accessible from connection object `con`:

* `con.rebind.rebind(jid, sid, callback)` - This will try to restore previous server session using
  `jid` and `sid` values from previous session (`jid` is available as `con.jid`, `sid` as
  `con.rebind.sid`). If session restoration fails, connection status will be changed to `CONNFAIL`
* `con.rebind.rebindOrConnect(jid, pass, sid, callback)` - Works as above function, but when session
  couldn't be restored, this version would create new session using `jid` and `pass`.

and two new fields:

* `con.rebind.active` - Boolean value that tells if that session could be restored in future
* `con.rebind.hasRebindFeature` - Boolean value that tells if server offers rebind feature
