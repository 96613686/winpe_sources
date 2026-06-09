# __scrt_dllmain_uninitialize_c

- ea: `0x1800365b0`
- end: `0x1800365e0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180036208`

## callees

- `0x1800365b0`
- `0x180037010`
- `0x1800370ca`
- `0x1800370ee`
- `0x180037408`

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
0x1800365b0  sub     rsp, 28h
0x1800365b4  call    __scrt_is_ucrt_dll_in_use
0x1800365b9  test    eax, eax
0x1800365bb  jz      short loc_1800365CD
0x1800365bd  lea     rcx, Table; Table
0x1800365c4  add     rsp, 28h
0x1800365c8  jmp     _execute_onexit_table
0x1800365cd  call    __scrt_stub_for_is_c_termination_complete
0x1800365d2  test    eax, eax
0x1800365d4  jnz     short loc_1800365DB
0x1800365d6  call    _o__cexit_0
0x1800365db  add     rsp, 28h
0x1800365df  retn
```
