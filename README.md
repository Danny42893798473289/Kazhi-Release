# Romlet Client (public release)

Pre-built **Romlet Client** injector for **Minecraft 1.21.x NeoForge (NetEase PC)**.  
This repo contains **binaries only** — no source code.

Supported MC patches: **1.21.8**, **1.21.4** (launcher detects version and loads the matching payload).

## Download

Use the latest [GitHub Release](https://github.com/Danny42893798473289/Kazhi-Release/releases) or the files in `app/`.

## Required files

Keep all payload JARs in the same folder (`app/` when using the launcher bundle):

| File | Role |
|------|------|
| `kazhi-agent-*.jar` | Java attach agent (loads into the game JVM) |
| `kazhi-client-*-mc1.21.8.jar` | Obfuscated payload for MC 1.21.8 |
| `kazhi-client-*-mc1.21.8-unobf.jar` | Runtime payload for MC 1.21.8 |
| `kazhi-client-*-mc1.21.4.jar` | Obfuscated payload for MC 1.21.4 |
| `kazhi-client-*-mc1.21.4-unobf.jar` | Runtime payload for MC 1.21.4 |

Legacy unprefixed `kazhi-client-*.jar` names (without `-mc`) still work for **1.21.8** only.

The injector validates agent + payload jars before attach. Do not delete or rename `-unobf.jar` files.

## Quick start (launcher bundle)

1. Download `RomletClient.zip` from Releases and extract the whole folder.
2. Install **JDK 21+** if you do not already have it.
3. **Double-click `kazhi-injector-*.jar` in `app/`** (opens the launcher GUI), or run **`RomletClient.bat`** / **`RomletClient.sh`**.
4. Unlock with your passkey, start Minecraft (NetEase), and click **INJECT**.

Keep all jars in `app/` together. The injector JAR is the main launcher — no `.exe` required.

## Quick start (JARs only)

Put all JARs in one folder (`app/`):

- `kazhi-injector-*.jar`
- `kazhi-agent-*.jar`
- both MC variant client pairs (`-mc1.21.8` and `-mc1.21.4`, obf + unobf each)

Then run (JDK 21+):

```bash
java --add-modules jdk.attach -jar kazhi-injector-1.2.0.jar gui
```

Unlock with your passkey in the launcher before injecting.

## Logs

See `~/.kazhi/kazhi-debug.log` (or `%USERPROFILE%\.kazhi\kazhi-debug.log` on Windows), or use **Open log** in the launcher.

## Unsupported versions

If your NetEase launcher ships an MC patch not listed above, injection is blocked with a clear message — do not force-load the wrong payload jar.
