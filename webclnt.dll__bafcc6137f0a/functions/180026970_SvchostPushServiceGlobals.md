# SvchostPushServiceGlobals

- ea: `0x180026970`
- end: `0x180026978`
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
  DavSvcsGlobalData = a1;
}

```

## disassembly

```asm
0x180026970  mov     cs:DavSvcsGlobalData, rcx
0x180026977  retn
```
