# filetime

- ea: `0x1800a8d00`
- end: `0x1800a8fe3`
- name: `filetime`
- size: `739`
- prototype: `__int64 __fastcall(STRSAFE_LPCSTR pszSrc)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800a06a0`
- `0x1800a0c30`
- `0x1800a3410`
- `0x1800a3a5c`
- `0x1800a5c24`
- `0x1800a72b0`
- `0x1800a90a0`

## callees

- `0x180001f88`
- `0x18009fa48`
- `0x1800a17ac`
- `0x1800a84d0`
- `0x1800a8d00`
- `0x1800afc80`
- `0x1800b1ad8`
- `0x1800b1b28`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!time` at `0x1800a8f62`
- `msvcrt!time` at `0x1800a8f62`
- `msvcrt!gmtime` at `0x1800a8f73`
- `msvcrt!gmtime` at `0x1800a8f73`
- `msvcrt!localtime` at `0x1800a8f84`
- `msvcrt!localtime` at `0x1800a8f84`
- `KERNEL32!lstrlenA` at `0x1800a8d79`
- `KERNEL32!lstrlenA` at `0x1800a8d79`
- `KERNEL32!CloseHandle` at `0x1800a8eb2`
- `KERNEL32!CloseHandle` at `0x1800a8eb2`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800a8e3d`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800a8e3d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExA` at `0x1800a8e11`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExA` at `0x1800a8e11`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a8e8f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a8e8f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800a8e58`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800a8e58`

## pseudocode

```c

```
