## m3u-gen-acestream

> M3U playlist generator for AceStream.

## How to use?
* Install [Python 3.7.0](https://www.python.org/downloads/release/python-370/)
  or higher.
* Run `./src/m3u_gen_acestream.py` to start a program.
  When playlist(s) is generated, you can close the program
  if you do not need automatic updates.
* Run AceStream if it is not running yet.
  In default configuration, assuming that AceStream Engine
  is listening at `127.0.0.1:6878`.
  
  If you use HTTPAceProxy, you can use it instead.
  In default configuration, assuming that HTTPAceProxy
  is listening at `127.0.0.1:8000`.
* Open generated playlist with your favorite IPTV player.
* Done.

## Notes:
Default output folder: `./out/`.

See `./src/config/config.py` to configure program behavior.

See `./src/filter/filter.json` to configure filter.
See formatting in the config file.

See `./src/channel/injection.json` to configure channel injections.
See formatting in the config file.

---
If you use player with built-in AceStream support,
you can add new 'DataSet' to the config file
with URL format like 'acestream://{CONTENT_ID}'.

---
If you want to serve generated files over http, you can use
python built-in http server module, for example:

```sh
cd out
python -m http.server 7999
```

The command above will serve output directory on port `7999`.

So generated files can be accessed via local network and you can
open links like `<your-local-ip>:7999/<playlist-file-name>` in
IPTV player directly.
