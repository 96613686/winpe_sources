# LSA_SSPI_HANDLE_rundown

- ea: `0x180001be0`
- end: `0x180001c06`
- name: `LSA_SSPI_HANDLE_rundown`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001bb0`
- `0x180002350`

## callees

- `0x180001be0`
- `0x180004010`

## pseudocode

```c
__int64 (*LSA_SSPI_HANDLE_rundown())(void)
{
  __int64 (*result)(void); // rax

  result = (__int64 (*)(void))gLsapSspiExtension;
  if ( gLsapSspiExtension )
  {
    result = *(__int64 (**)(void))(gLsapSspiExtension + 16);
    if ( result )
      return (__int64 (*)(void))result();
  }
  return result;
}

```

## disassembly

```asm
0x180001be0  sub     rsp, 28h
0x180001be4  mov     rax, cs:gLsapSspiExtension
0x180001beb  test    rax, rax
0x180001bee  jz      short loc_180001BF9
0x180001bf0  mov     rax, [rax+10h]
0x180001bf4  test    rax, rax
0x180001bf7  jnz     short loc_180001BFF
0x180001bf9  add     rsp, 28h
0x180001bfd  retn
0x180001bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c04  jmp     short loc_180001BF9
```
