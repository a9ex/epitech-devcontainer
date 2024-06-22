# How to have audio in your DevContainer :

1. Install `pulseaudio` (or `pulseaudio-alsa`) in your computer. (`pulseaudio` is already installed in the devcontainer)
2. Add the following `runArgs` to your `devcontainer.json` file:

```json
"-v/run/user/<UID>/pulse/native:/run/user/<UID>/pulse/native"
```

Your container must run with the same UID as your host user for the application to connect to the pulse socket.

3. Add the following environment variable to your `devcontainer.json` file:

```json
"PULSE_SERVER": "unix:/run/user/<UID>/pulse/native"
```
