# Windows::System::Internal::UserPackageRegistration::HasRegisterPackageIfNeededSucceededForUser(Windows::System::IUser *,bool *,uint *)

- ea: `0x1800076f0`
- end: `0x180007915`
- name: `?HasRegisterPackageIfNeededSucceededForUser@UserPackageRegistration@Internal@System@Windows@@QEAAJPEAUIUser@34@PEA_NPEAI@Z`
- size: `549`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserPackageRegistration *__hidden this, struct Windows::System::IUser *, bool *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006260`
- `0x18000707c`
- `0x1800bb6d0`

## callees

- `0x1800076f0`
- `0x180007920`
- `0x1800088e8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007725`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007725`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800077fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000789b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800077fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000789b`

## string_xrefs

- `0x18000784c`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x1800078aa`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`
- `0x1800078f8`: `onecore\ds\security\umstartup\usermgr\lib\userpackageregistration.cpp`

## pseudocode

```c

```
