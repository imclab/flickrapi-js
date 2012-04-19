flickrapi-js
--

A Javascript library for talking to the Flickr API. It is currently incomplete
and only works for uploading files, and only then does it work in Firefox and
Opera.

Uploads in Webkit related browsers should be possible but I've not gotten around
to working out the details yet.

Here's an example of how you might upload the contents of a <canvas> element to
Flickr:

	var api_key = 'FLICKR_API_KEY';
	var api_secret = 'FLICKR_API_SECRET';
	var auth_token = 'FLICKR_AUTH_TOKEN';

	var canvas = document.getElementById("some-canvas-thing");

	var data = canvas.toDataURL();
	var enc = data.replace("data:image/png;base64,", "");
	var bytes = base64_decode(enc);
	
	var fl = flickr.api(api_key, api_secret);
	fl.upload(bytes, {'auth_token': auth_token});

IMPORTANT: This is still plain old Javascript and if you fill in all those
FLICKR API key and auth token variables with real data and then put them on the
public Internet **any one will be able to see them, steal them and start
uploading stuff to that account**.

This is not a magic pony so be careful how you use it and where.
