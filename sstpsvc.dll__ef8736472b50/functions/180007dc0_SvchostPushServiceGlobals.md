# SvchostPushServiceGlobals

- ea: `0x180007dc0`
- end: `0x180007dc8`
- name: `SvchostPushServiceGlobals`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(__int64 a1)
{
  SstpSvchostGlobal = a1;
}

```

## disassembly

```asm
0x180007dc0  mov     cs:SstpSvchostGlobal, rcx
0x180007dc7  retn
```
