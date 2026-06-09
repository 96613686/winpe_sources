# GetTaskSchedulerTask(ITaskService *,ushort const *,IRegisteredTask * *)

- ea: `0x18001d82c`
- end: `0x18001d949`
- name: `?GetTaskSchedulerTask@@YAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct ITaskService *, const unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d588`

## callees

- `0x18001d82c`
- `0x18002f8c0`
- `0x1800338f4`
- `0x180033aec`
- `0x18006d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d854`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d854`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d8df`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d8df`

## string_xrefs

- `0x18001d86c`: `shell\lib\comtaskserverutil.cpp`
- `0x18001d8b2`: `shell\lib\comtaskserverutil.cpp`
- `0x18001d90b`: `shell\lib\comtaskserverutil.cpp`
- `0x18001d84a`: `\Microsoft\Windows\Shell\CreateObjectTask`

## pseudocode

```c

```
