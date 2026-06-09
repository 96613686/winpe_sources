# __scrt_dllmain_uninitialize_c

- ea: `0x18001031c`
- end: `0x18001034c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fe58`

## callees

- `0x18001031c`
- `0x180010880`
- `0x1800108f2`
- `0x18001090a`
- `0x180010e2c`

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
0x18001031c  sub     rsp, 28h
0x180010320  call    __scrt_is_ucrt_dll_in_use
0x180010325  test    eax, eax
0x180010327  jz      short loc_180010339
0x180010329  lea     rcx, Table; Table
0x180010330  add     rsp, 28h
0x180010334  jmp     _execute_onexit_table
0x180010339  call    __scrt_stub_for_is_c_termination_complete
0x18001033e  test    eax, eax
0x180010340  jnz     short loc_180010347
0x180010342  call    _o__cexit_0
0x180010347  add     rsp, 28h
0x18001034b  retn
```
