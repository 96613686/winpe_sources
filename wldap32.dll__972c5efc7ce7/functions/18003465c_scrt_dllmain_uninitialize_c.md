# __scrt_dllmain_uninitialize_c

- ea: `0x18003465c`
- end: `0x18003468c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800342f8`

## callees

- `0x18003465c`
- `0x180034d48`
- `0x180034dda`
- `0x180034dfe`
- `0x180035670`

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
0x18003465c  sub     rsp, 28h
0x180034660  call    __scrt_is_ucrt_dll_in_use
0x180034665  test    eax, eax
0x180034667  jz      short loc_180034679
0x180034669  lea     rcx, Table; Table
0x180034670  add     rsp, 28h
0x180034674  jmp     _execute_onexit_table
0x180034679  call    __scrt_stub_for_is_c_termination_complete
0x18003467e  test    eax, eax
0x180034680  jnz     short loc_180034687
0x180034682  call    _o__cexit_0
0x180034687  add     rsp, 28h
0x18003468b  retn
```
