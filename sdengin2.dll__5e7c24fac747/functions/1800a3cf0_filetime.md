# filetime

- ea: `0x1800a3cf0`
- end: `0x1800a3f9c`
- name: `filetime`
- size: `684`
- prototype: `__int64 __fastcall(STRSAFE_LPCSTR pszSrc)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18009beac`
- `0x18009c3e4`
- `0x18009e974`
- `0x18009ef7c`
- `0x1800a0f48`
- `0x1800a24ac`
- `0x1800a404c`

## callees

- `0x180001f18`
- `0x18009b2f0`
- `0x18009cee8`
- `0x1800a359c`
- `0x1800a3cf0`
- `0x1800aa668`
- `0x1800ac3ac`
- `0x1800ac3fc`
- `0x1800c9830`

## import_xrefs

- `msvcrt!time` at `0x1800a3f2e`
- `msvcrt!time` at `0x1800a3f2e`
- `msvcrt!gmtime` at `0x1800a3f39`
- `msvcrt!gmtime` at `0x1800a3f39`
- `msvcrt!localtime` at `0x1800a3f44`
- `msvcrt!localtime` at `0x1800a3f44`
- `KERNEL32!lstrlenA` at `0x1800a3d69`
- `KERNEL32!lstrlenA` at `0x1800a3d69`
- `KERNEL32!CloseHandle` at `0x1800a3e84`
- `KERNEL32!CloseHandle` at `0x1800a3e84`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800a3e21`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800a3e21`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExA` at `0x1800a3dfb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExA` at `0x1800a3dfb`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a3e67`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a3e67`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800a3e36`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800a3e36`

## pseudocode

```c

```
