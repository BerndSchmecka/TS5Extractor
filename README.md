# TS5Extractor
Extract your user data from Matrix from the TeamSpeak database to be able to use it in Elements, for example.

Download current Build -> [Download Here](https://space.byte-store.de/external/bytestore/download/software/extractor/TeamSpeakExtraction.zip)

![image](https://user-images.githubusercontent.com/31771657/163729102-b670fb86-ace7-4c72-b8e6-1f6016b049c6.png)

## Select your Settings Database:

Windows: %appdata%/TeamSpeak/settings.db

![aaa](https://user-images.githubusercontent.com/31771657/163729183-81134b23-9cbc-4a5d-85bb-b5be9b65a493.png)

## Use the Credentials in Elements.io

To use your Credentials you need to change your User Agent to ``Go-http-client/2.0``.

When you like to use a Mobile App or the Elements Desktop App, you can create a Reverse Proxy with NGINX to do that automatically.

```
location ^~ / {
	proxy_ssl_server_name on;
	#proxy_ssl_name "sni.cloudflaressl.com";
	proxy_pass https://chat.teamspeak.com;
	proxy_set_header Host chat.teamspeak.com;
	#proxy_pass_request_headers on;
	proxy_intercept_errors on;
	proxy_set_header User-Agent "Go-http-client/2.0";
}```

The current Version is fully functional, but it's missing some Messaging and Logging Options.
