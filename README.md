# htmx-ext-ably

An extension to make [Ably](https://ably.com/) elements work seamlessly (as possible) with htmx.

## Usage

1. Import htmx and the extension

```
<script src="htmx.js"></script>
<script src="htmx.ext.ably.js"></script>
```

2. Add "ably" to the `hx-ext` parameter. on a `div` tag. 

```
<div hx-ext="ably">
```

3. Adding the `ably-connect` attribute to a `div` tag triggers opening a connection to Ably.  The extension includes `ably-authUrl` and `ably-authMthod` attributes to authenticate the Ably JS client:

```
<div hx-ext="ably">
  <div ably-connect ably-authUrl="/api/ably/token">
  </div>
</div>
```

3. To publish a message to an Ably channel, add the `ably-publish` attribute to a `form` element.  Specify the channel to publish to using the `ably-channel` attribute:

```
<form ably-publish ably-channel="chatroom">
  <input id="inp" type="text" name="chat_message" />
  <button id="btn" value="Send">Send</button>
</form>
```

4. To subscribe to channel messages, add the `ably-subscribe` attribute to a `div` element. Specify the channel to publish to using the `ably-channel` attribute:

```
<div ably-subscribe ably-channel="chatroom">
  <div id="chatWindow" hx-swap-oob="beforeend">
</div>
```

# Events

- ablyBeforeSend
- ablyAfterSend
- ablyAfterChannelSubscribe
- ablyBeforeChannelSubscribe
- ablyConfigureSend
- ablyConnecting
- ablyConnected
- ablyFailed
- ablyClosed
- ablySuspended
- ablyDisconnected
- ablyAfterMessage
- ablyBeforeMessage
