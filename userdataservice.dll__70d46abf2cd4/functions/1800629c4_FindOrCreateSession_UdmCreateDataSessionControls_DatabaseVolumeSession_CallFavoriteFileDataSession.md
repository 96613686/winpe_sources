# FindOrCreateSession(UdmCreateDataSessionControls,DatabaseVolumeSession * *,CallFavoriteFileDataSession *)

- ea: `0x1800629c4`
- end: `0x180062c3e`
- name: `?FindOrCreateSession@@YAJUUdmCreateDataSessionControls@@PEAPEAVDatabaseVolumeSession@@PEAVCallFavoriteFileDataSession@@@Z`
- size: `634`
- prototype: `__int64 __fastcall(__int64, DatabaseVolumeSession **, CallFavoriteFileDataSession *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x1800627bc`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180035040`
- `0x1800357bc`
- `0x180035c40`
- `0x18003e698`
- `0x1800629c4`
- `0x180062c44`
- `0x18007cabc`
- `0x18007de00`
- `0x18007ee4c`
- `0x1800977ac`
- `0x1800977c4`
- `0x18009e558`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180062ac0`
- `msvcrt!_wcsicmp` at `0x180062ac0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800629e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800629e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062bf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062bf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062c29`

## string_xrefs

- `0x180062b28`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180062b84`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180062bc4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180062c0d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c

```
