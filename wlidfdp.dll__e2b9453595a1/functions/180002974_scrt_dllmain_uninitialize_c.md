# __scrt_dllmain_uninitialize_c

- ea: `0x180002974`
- end: `0x1800029a4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800025c8`

## callees

- `0x180002974`
- `0x1800030e0`
- `0x1800032fe`
- `0x180003322`
- `0x180006650`

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
0x180002974  sub     rsp, 28h
0x180002978  call    __scrt_is_ucrt_dll_in_use
0x18000297d  test    eax, eax
0x18000297f  jz      short loc_180002991
0x180002981  lea     rcx, Table; Table
0x180002988  add     rsp, 28h
0x18000298c  jmp     _execute_onexit_table
0x180002991  call    __scrt_stub_for_is_c_termination_complete
0x180002996  test    eax, eax
0x180002998  jnz     short loc_18000299F
0x18000299a  call    _o__cexit_0
0x18000299f  add     rsp, 28h
0x1800029a3  retn
```
