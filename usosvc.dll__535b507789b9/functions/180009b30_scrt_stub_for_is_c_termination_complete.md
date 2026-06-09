# __scrt_stub_for_is_c_termination_complete

- ea: `0x180009b30`
- end: `0x180009b33`
- name: `__scrt_stub_for_is_c_termination_complete`
- size: `3`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000281c`

## pseudocode

```c
__int64 __fastcall _scrt_stub_for_is_c_termination_complete(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  return 0;
}

```

## disassembly

```asm
0x180009b30  xor     eax, eax
0x180009b32  retn
```
