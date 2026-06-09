# _dynamic_atexit_destructor_for__s_EventLog2__

- ea: `0x180002640`
- end: `0x18000266a`
- name: `_dynamic_atexit_destructor_for__s_EventLog2__`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002640`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x180002650`
- `ADVAPI32!EventUnregister` at `0x180002650`

## pseudocode

```c
ULONG dynamic_atexit_destructor_for__s_EventLog2__()
{
  ULONG result; // eax

  if ( RegHandle )
  {
    result = EventUnregister(RegHandle);
    RegHandle = 0;
  }
  dword_180005668 = 0;
  return result;
}

```

## disassembly

```asm
0x180002640  sub     rsp, 28h
0x180002644  mov     rcx, cs:RegHandle; RegHandle
0x18000264b  test    rcx, rcx
0x18000264e  jz      short loc_18000265E
0x180002650  call    cs:__imp_EventUnregister
0x180002656  and     cs:RegHandle, 0
0x18000265e  and     cs:dword_180005668, 0
0x180002665  add     rsp, 28h
0x180002669  retn
```
