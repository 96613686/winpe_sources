# __scrt_dllmain_uninitialize_c

- ea: `0x1800020dc`
- end: `0x18000210c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c98`

## callees

- `0x1800020dc`
- `0x1800028c0`
- `0x1800029da`
- `0x1800029fe`
- `0x180026980`

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
0x1800020dc  sub     rsp, 28h
0x1800020e0  call    __scrt_is_ucrt_dll_in_use
0x1800020e5  test    eax, eax
0x1800020e7  jz      short loc_1800020F9
0x1800020e9  lea     rcx, Table; Table
0x1800020f0  add     rsp, 28h
0x1800020f4  jmp     _execute_onexit_table
0x1800020f9  call    __scrt_stub_for_is_c_termination_complete
0x1800020fe  test    eax, eax
0x180002100  jnz     short loc_180002107
0x180002102  call    _o__cexit_0
0x180002107  add     rsp, 28h
0x18000210b  retn
```
