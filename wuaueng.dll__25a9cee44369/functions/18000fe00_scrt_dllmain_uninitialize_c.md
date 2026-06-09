# __scrt_dllmain_uninitialize_c

- ea: `0x18000fe00`
- end: `0x18000fe30`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800102a0`

## callees

- `0x18000fb9e`
- `0x18000fbce`
- `0x18000fe00`
- `0x1800108fc`
- `0x18001589c`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000fe00  sub     rsp, 28h
0x18000fe04  call    __scrt_is_ucrt_dll_in_use
0x18000fe09  test    eax, eax
0x18000fe0b  jz      short loc_18000FE1D
0x18000fe0d  lea     rcx, Table; Table
0x18000fe14  add     rsp, 28h
0x18000fe18  jmp     _execute_onexit_table
0x18000fe1d  call    __scrt_stub_for_is_c_termination_complete
0x18000fe22  test    eax, eax
0x18000fe24  jnz     short loc_18000FE2B
0x18000fe26  call    _o__cexit_0
0x18000fe2b  add     rsp, 28h
0x18000fe2f  retn
```
