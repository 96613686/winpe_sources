# CSusClientGlobal::Uninit(void)

- ea: `0x1800142a0`
- end: `0x180014685`
- name: `?Uninit@CSusClientGlobal@@AEAAXXZ`
- size: `997`
- prototype: `void __fastcall(CSusClientGlobal *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010f84`

## callees

- `0x1800142a0`
- `0x1800170cc`
- `0x180019778`
- `0x18001a69c`
- `0x180054d78`
- `0x1800563d0`
- `0x1800566a4`
- `0x180058f28`
- `0x18005b9f8`
- `0x180113ae8`
- `0x180116c80`
- `0x18012b618`
- `0x18013e97c`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014382`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014382`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001432c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001432c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014367`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014518`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014367`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014518`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001438f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001438f`

## string_xrefs

- `0x1800142c0`: `CSusClientGlobal::DoServicePreShutdown`
- `0x1800143a4`: `Agent uninit`
- `0x18001445d`: `ServiceManager uninit`
- `0x180014551`: `setting cache uninit`
- `0x1800145d0`: `security checker uninit`
- `0x180014303`: `Idle timer told to prepare for service shutdown without first being initialized`
- `0x180014332`: `Idle timer disabled in preparation for service shutdown`

## pseudocode

```c

```
