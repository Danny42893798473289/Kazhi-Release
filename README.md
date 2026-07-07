# Romlet Client (public release)

Pre-built **Romlet Client** injector for **Minecraft 1.21.8 NeoForge** (official Mojang launcher or NetEase PC).  
This repo contains **binaries only** — no source code.

## Download

Use the latest [GitHub Release](https://github.com/Danny42893798473289/Kazhi-Release/releases) or the files in `app/`.

## Required files

Keep all payload JARs in the same folder (`app/` when using the launcher bundle):

| File | Role |
|------|------|
| `kazhi-agent-*.jar` | Java attach agent (loads into the game JVM) |
| `kazhi-client-*.jar` | Obfuscated payload |
| `kazhi-client-*-unobf.jar` | Runtime payload (required at inject time) |

The injector validates agent + payload jars before attach. Do not delete or rename `-unobf.jar` files.

## Quick start (launcher bundle)

1. Download `RomletClient.zip` from Releases and extract the whole folder.
2. Install **JDK 21+** if you do not already have it.
3. Install **NeoForge 1.21.8** for the official launcher if needed.
4. **Double-click `kazhi-injector-*.jar` in `app/`** (opens the launcher GUI), or run **`RomletClient.bat`** / **`RomletClient.sh`**.
5. Unlock with your passkey, start Minecraft, and click **INJECT**.

Keep all jars in `app/` together. The injector JAR is the main launcher — no `.exe` required.

## Quick start (JARs only)

Put all JARs in one folder (`app/`):

- `kazhi-injector-*.jar`
- `kazhi-agent-*.jar`
- `kazhi-client-*.jar` and `kazhi-client-*-unobf.jar`

Then run (JDK 21+):

```bash
java --add-modules jdk.attach -jar kazhi-injector-1.2.0.jar gui
```

Unlock with your passkey in the launcher before injecting.

## Logs

See `~/.kazhi/kazhi-debug.log` (or `%USERPROFILE%\.kazhi\kazhi-debug.log` on Windows), or use **Open log** in the launcher.

## Requirements

**Minecraft 1.21.8 + NeoForge** only. Fabric, vanilla, and other MC versions are not supported.
