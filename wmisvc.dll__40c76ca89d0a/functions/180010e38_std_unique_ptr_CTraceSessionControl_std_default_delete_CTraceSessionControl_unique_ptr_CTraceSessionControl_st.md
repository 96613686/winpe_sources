# std::unique_ptr<CTraceSessionControl,std::default_delete<CTraceSessionControl>>::~unique_ptr<CTraceSessionControl,std::default_delete<CTraceSessionControl>>(void)

- ea: `0x180010e38`
- end: `0x180010e50`
- name: `??1?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@XZ`
- size: `24`
- prototype: `int __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000574c`
- `0x18001da05`
- `0x18001da29`

## callees

- `0x180010e38`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180010e44`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180010e44`

## pseudocode

```c
int __fastcall std::unique_ptr<CTraceSessionControl>::~unique_ptr<CTraceSessionControl>(void **a1)
{
  void *v1; // rcx
  int result; // eax

  v1 = *a1;
  if ( v1 )
    return CWin32DefaultArena::WbemMemFree(v1);
  return result;
}

```

## disassembly

```asm
0x180010e38  sub     rsp, 28h
0x180010e3c  mov     rcx, [rcx]
0x180010e3f  test    rcx, rcx
0x180010e42  jz      short loc_180010E4B
0x180010e44  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180010e4a  nop
0x180010e4b  add     rsp, 28h
0x180010e4f  retn
```
