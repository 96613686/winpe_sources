# __scrt_dllmain_uninitialize_c

- ea: `0x1800026dc`
- end: `0x18000270c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002368`

## callees

- `0x1800026dc`
- `0x180002ea8`
- `0x180002fa6`
- `0x180002fd6`
- `0x1800299d0`

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
0x1800026dc  sub     rsp, 28h
0x1800026e0  call    __scrt_is_ucrt_dll_in_use
0x1800026e5  test    eax, eax
0x1800026e7  jz      short loc_1800026F9
0x1800026e9  lea     rcx, Table; Table
0x1800026f0  add     rsp, 28h
0x1800026f4  jmp     _execute_onexit_table
0x1800026f9  call    __scrt_stub_for_is_c_termination_complete
0x1800026fe  test    eax, eax
0x180002700  jnz     short loc_180002707
0x180002702  call    _o__cexit_0
0x180002707  add     rsp, 28h
0x18000270b  retn
```
