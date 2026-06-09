# __scrt_dllmain_uninitialize_c

- ea: `0x180004ed4`
- end: `0x180004f04`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004a68`

## callees

- `0x180004ed4`
- `0x18000544c`
- `0x1800054b2`
- `0x1800054ca`
- `0x1800055f4`

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
0x180004ed4  sub     rsp, 28h
0x180004ed8  call    __scrt_is_ucrt_dll_in_use
0x180004edd  test    eax, eax
0x180004edf  jz      short loc_180004EF1
0x180004ee1  lea     rcx, Table; Table
0x180004ee8  add     rsp, 28h
0x180004eec  jmp     _execute_onexit_table
0x180004ef1  call    __scrt_stub_for_is_c_termination_complete
0x180004ef6  test    eax, eax
0x180004ef8  jnz     short loc_180004EFF
0x180004efa  call    _o__cexit_0
0x180004eff  add     rsp, 28h
0x180004f03  retn
```
