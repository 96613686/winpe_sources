# __scrt_dllmain_uninitialize_c

- ea: `0x180001750`
- end: `0x180001780`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012c8`

## callees

- `0x180001750`
- `0x180001d04`
- `0x180001d6a`
- `0x180001d8e`
- `0x180012d70`

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
0x180001750  sub     rsp, 28h
0x180001754  call    __scrt_is_ucrt_dll_in_use
0x180001759  test    eax, eax
0x18000175b  jz      short loc_18000176D
0x18000175d  lea     rcx, Table; Table
0x180001764  add     rsp, 28h
0x180001768  jmp     _execute_onexit_table
0x18000176d  call    __scrt_stub_for_is_c_termination_complete
0x180001772  test    eax, eax
0x180001774  jnz     short loc_18000177B
0x180001776  call    _o__cexit_0
0x18000177b  add     rsp, 28h
0x18000177f  retn
```
