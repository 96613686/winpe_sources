# UserManagerTokenAndShellHandler::QueryDefaultAccountUser(unsigned __int64,Windows::System::IUser * *)

- ea: `0x1800b6ac4`
- end: `0x1800b6c2e`
- name: `?QueryDefaultAccountUser@UserManagerTokenAndShellHandler@@QEAAJ_KPEAPEAUIUser@System@Windows@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(UserManagerTokenAndShellHandler *__hidden this, unsigned __int64, struct Windows::System::IUser **)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027e60`
- `0x180035c50`
- `0x1800b2614`

## callees

- `0x180006130`
- `0x180007920`
- `0x1800088e8`
- `0x180024828`
- `0x1800b6ac4`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b6b43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b6b43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b6bb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b6be6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b6c0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b6bb3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b6be6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b6c0a`

## string_xrefs

- `0x1800b6b17`: `onecore\ds\security\umstartup\usermgr\lib\usermgrtokenandshellhandler.cpp`
- `0x1800b6b96`: `onecore\ds\security\umstartup\usermgr\lib\usermgrtokenandshellhandler.cpp`
- `0x1800b6bcc`: `onecore\ds\security\umstartup\usermgr\lib\usermgrtokenandshellhandler.cpp`

## pseudocode

```c

```
