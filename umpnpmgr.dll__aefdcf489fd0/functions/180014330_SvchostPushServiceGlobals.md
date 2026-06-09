# SvchostPushServiceGlobals

- ea: `0x180014330`
- end: `0x180014338`
- name: `SvchostPushServiceGlobals`
- size: `8`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(__int64 a1)
{
  PnpSvchostGlobalData = a1;
}

```

## disassembly

```asm
0x180014330  mov     cs:PnpSvchostGlobalData, rcx
0x180014337  retn
```
