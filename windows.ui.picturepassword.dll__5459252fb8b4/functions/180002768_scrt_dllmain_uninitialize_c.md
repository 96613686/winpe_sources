# __scrt_dllmain_uninitialize_c

- ea: `0x180002768`
- end: `0x180002798`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800023f8`

## callees

- `0x180002768`
- `0x180002e54`
- `0x180002eba`
- `0x180002ede`
- `0x180004398`

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
0x180002768  sub     rsp, 28h
0x18000276c  call    __scrt_is_ucrt_dll_in_use
0x180002771  test    eax, eax
0x180002773  jz      short loc_180002785
0x180002775  lea     rcx, Table; Table
0x18000277c  add     rsp, 28h
0x180002780  jmp     _execute_onexit_table
0x180002785  call    __scrt_stub_for_is_c_termination_complete
0x18000278a  test    eax, eax
0x18000278c  jnz     short loc_180002793
0x18000278e  call    _o__cexit_0
0x180002793  add     rsp, 28h
0x180002797  retn
```
