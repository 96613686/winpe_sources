# Windows::System::Internal::UserManagerStatics::IsConnectedToXboxLive(void)

- ea: `0x18004e77c`
- end: `0x18004e94c`
- name: `?IsConnectedToXboxLive@UserManagerStatics@Internal@System@Windows@@AEAA_NXZ`
- size: `464`
- prototype: `bool __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180095e88`
- `0x18009ac9c`
- `0x18009e47c`
- `0x1800a5a70`
- `0x1800a5dc0`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x1800179c0`
- `0x18004e4e8`
- `0x18004e77c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e7fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e7fc`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18004e845`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18004e845`
- `ntdll!RtlQueryWnfStateData` at `0x18004e7cf`
- `ntdll!RtlQueryWnfStateData` at `0x18004e7cf`

## string_xrefs

- `0x18004e7e1`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18004e857`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18004e8cc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18004e90a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c

```
