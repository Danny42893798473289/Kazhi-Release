# Romlet Client (public release)

Pre-built **Romlet Client** injector for **Minecraft 1.21.8 NeoForge (NetEase PC)**.  
This repo contains **binaries only** — no source code.

## Download

Use the latest [GitHub Release](https://github.com/Danny42893798473289/Kazhi-Release/releases) or the files in `app/`.

## Required files

All three JARs must stay in the same folder (`app/` when using the EXE):

| File | Role |
|------|------|
| `kazhi-agent-*.jar` | Java attach agent (loads into the game JVM) |
| `kazhi-client-*.jar` | Obfuscated client payload |
| `kazhi-client-*-unobf.jar` | Runtime payload used at inject time |

The injector validates all three before attach. Do not delete or rename `-unobf.jar`.

## Quick start (EXE)

1. Download `RomletClient.zip` from Releases and extract the whole folder.
2. Run **`RomletClient.exe`** and unlock with your passkey.
3. Start Minecraft (NetEase) and wait at the **main menu**.
4. Select the game process (or enable **Auto-inject when Minecraft starts**) and click **INJECT**.
5. Switch to the game and press **INSERT** (default menu key).

Keep `RomletClient.exe`, `app/`, and `runtime/` together.

## Quick start (JARs only)

Put all four JARs in one folder (`app/`):

- `kazhi-injector-*.jar`
- `kazhi-agent-*.jar`
- `kazhi-client-*.jar`
- `kazhi-client-*-unobf.jar`

Then run (JDK 21+):

```bat
java --add-modules jdk.attach -jar kazhi-injector-1.2.0.jar
```

Unlock with your passkey in the launcher before injecting.

## Logs

- Romlet / agent debug: `%USERPROFILE%\.kazhi\kazhi-debug.log` (use **Open log** in the launcher)
- Minecraft: `<gameDir>\logs\latest.log`

## Disclaimer

Singleplayer / educational use only. Using utility clients on multiplayer may violate server rules or terms of service.
