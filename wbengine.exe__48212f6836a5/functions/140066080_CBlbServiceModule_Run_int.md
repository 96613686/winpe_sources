# CBlbServiceModule::Run(int)

- ea: `0x140066080`
- end: `0x1400661cd`
- name: `?Run@CBlbServiceModule@@QEAAJH@Z`
- size: `333`
- prototype: `__int64 __fastcall(CBlbServiceModule *this, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x1400673b8`
- `0x1400687cc`

## callees

- `0x14000bb24`
- `0x140062ce8`
- `0x1400648a8`
- `0x140066080`
- `0x1400d7934`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x140066124`
- `ADVAPI32!SetServiceStatus` at `0x140066124`
- `KERNEL32!GetCurrentThreadId` at `0x14006609b`
- `KERNEL32!GetCurrentThreadId` at `0x14006609b`
- `KERNEL32!Sleep` at `0x1400661b5`
- `KERNEL32!Sleep` at `0x1400661b5`
- `USER32!DispatchMessageW` at `0x14006614e`
- `USER32!DispatchMessageW` at `0x14006614e`
- `USER32!TranslateMessage` at `0x140066143`
- `USER32!TranslateMessage` at `0x140066143`
- `USER32!GetMessageW` at `0x140066161`
- `USER32!GetMessageW` at `0x140066161`
- `ole32!CoRevokeClassObject` at `0x140066194`
- `ole32!CoRevokeClassObject` at `0x140066194`

## pseudocode

```c

```
