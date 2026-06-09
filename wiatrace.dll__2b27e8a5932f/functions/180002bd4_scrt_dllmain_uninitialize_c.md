# __scrt_dllmain_uninitialize_c

- ea: `0x180002bd4`
- end: `0x180002c04`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002768`

## callees

- `0x180002bd4`
- `0x180003158`
- `0x1800031a6`
- `0x1800031be`
- `0x180003268`

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
0x180002bd4  sub     rsp, 28h
0x180002bd8  call    __scrt_is_ucrt_dll_in_use
0x180002bdd  test    eax, eax
0x180002bdf  jz      short loc_180002BF1
0x180002be1  lea     rcx, Table; Table
0x180002be8  add     rsp, 28h
0x180002bec  jmp     _execute_onexit_table
0x180002bf1  call    __scrt_stub_for_is_c_termination_complete
0x180002bf6  test    eax, eax
0x180002bf8  jnz     short loc_180002BFF
0x180002bfa  call    _o__cexit_0
0x180002bff  add     rsp, 28h
0x180002c03  retn
```
