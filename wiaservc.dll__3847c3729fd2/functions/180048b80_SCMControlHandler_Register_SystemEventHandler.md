# SCMControlHandler::Register(SystemEventHandler *)

- ea: `0x180048b80`
- end: `0x180048ca7`
- name: `?Register@SCMControlHandler@@UEAAJPEAVSystemEventHandler@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(SCMControlHandler *__hidden this, struct SystemEventHandler *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180048b80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180048c21`
- `KERNEL32!GetLastError` at `0x180048c55`
- `KERNEL32!GetLastError` at `0x180048c21`
- `KERNEL32!GetLastError` at `0x180048c55`
- `USER32!RegisterPowerSettingNotification` at `0x180048c0f`
- `USER32!RegisterPowerSettingNotification` at `0x180048c0f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180048be2`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180048be2`

## pseudocode

```c

```
