# CCDLAgent::GetErrorMessage(long)

- ea: `0x180003d20`
- end: `0x180003e34`
- name: `?GetErrorMessage@CCDLAgent@@QEAAPEAGJ@Z`
- size: `276`
- prototype: `unsigned __int16 *(CCDLAgent *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003e40`

## callees

- `0x180003d20`
- `0x18001ba40`
- `0x180029280`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180003d7d`
- `KERNEL32!FormatMessageW` at `0x180003d7d`
- `KERNEL32!MultiByteToWideChar` at `0x180003de5`
- `KERNEL32!MultiByteToWideChar` at `0x180003de5`
- `USER32!LoadStringW` at `0x180003dac`
- `USER32!LoadStringW` at `0x180003dac`
- `OLEAUT32!__imp_SysAllocString` at `0x180003dbb`
- `OLEAUT32!__imp_SysAllocString` at `0x180003df4`
- `OLEAUT32!__imp_SysAllocString` at `0x180003dbb`
- `OLEAUT32!__imp_SysAllocString` at `0x180003df4`

## pseudocode

```c

```
