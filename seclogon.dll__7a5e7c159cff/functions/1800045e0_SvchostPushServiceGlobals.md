# SvchostPushServiceGlobals

- ea: `0x1800045e0`
- end: `0x1800045e8`
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
  GlobalData = a1;
}

```

## disassembly

```asm
0x1800045e0  mov     cs:GlobalData, rcx
0x1800045e7  retn
```
