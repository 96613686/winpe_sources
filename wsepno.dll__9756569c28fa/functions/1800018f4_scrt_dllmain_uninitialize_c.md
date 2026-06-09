# __scrt_dllmain_uninitialize_c

- ea: `0x1800018f4`
- end: `0x180001924`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001548`

## callees

- `0x1800018f4`
- `0x180002068`
- `0x180002142`
- `0x180002166`
- `0x1800022a8`

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
0x1800018f4  sub     rsp, 28h
0x1800018f8  call    __scrt_is_ucrt_dll_in_use
0x1800018fd  test    eax, eax
0x1800018ff  jz      short loc_180001911
0x180001901  lea     rcx, Table; Table
0x180001908  add     rsp, 28h
0x18000190c  jmp     _execute_onexit_table
0x180001911  call    __scrt_stub_for_is_c_termination_complete
0x180001916  test    eax, eax
0x180001918  jnz     short loc_18000191F
0x18000191a  call    _o__cexit_0
0x18000191f  add     rsp, 28h
0x180001923  retn
```
