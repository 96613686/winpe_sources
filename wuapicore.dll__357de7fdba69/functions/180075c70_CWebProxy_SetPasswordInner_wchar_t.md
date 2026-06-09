# CWebProxy::SetPasswordInner(wchar_t *)

- ea: `0x180075c70`
- end: `0x180075df0`
- name: `?SetPasswordInner@CWebProxy@@UEAAJPEA_W@Z`
- size: `384`
- prototype: `int(CWebProxy *__hidden this, wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x180075c70`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075da1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075da1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075d50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075d50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075dbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180075dbd`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180075cd8`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180075cd8`
- `CRYPT32!CryptProtectData` at `0x180075d14`
- `CRYPT32!CryptProtectData` at `0x180075d14`

## string_xrefs

- `0x180075cb3`: `C:\__w\1\s\src\Client\comapi\WebProxy.cpp`
- `0x180075d22`: `C:\__w\1\s\src\Client\comapi\WebProxy.cpp`

## pseudocode

```c

```
