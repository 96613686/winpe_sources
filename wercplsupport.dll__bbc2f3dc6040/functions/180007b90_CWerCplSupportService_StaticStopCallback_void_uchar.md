# CWerCplSupportService::StaticStopCallback(void *,uchar)

- ea: `0x180007b90`
- end: `0x180007b95`
- name: `?StaticStopCallback@CWerCplSupportService@@CAXPEAXE@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180007b9c`

## pseudocode

```c
// attributes: thunk
void __fastcall CWerCplSupportService::StaticStopCallback(struct _RTL_CRITICAL_SECTION *this)
{
  CWerCplSupportService::Stop(this);
}

```

## disassembly

```asm
0x180007b90  jmp     ?Stop@CWerCplSupportService@@AEAAXXZ; CWerCplSupportService::Stop(void)
```
