# __scrt_dllmain_uninitialize_c

- ea: `0x1800026e0`
- end: `0x180002710`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800021e8`

## callees

- `0x1800026e0`
- `0x180002d30`
- `0x180002dd2`
- `0x180002df6`
- `0x180002fe0`

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
0x1800026e0  sub     rsp, 28h
0x1800026e4  call    __scrt_is_ucrt_dll_in_use
0x1800026e9  test    eax, eax
0x1800026eb  jz      short loc_1800026FD
0x1800026ed  lea     rcx, Table; Table
0x1800026f4  add     rsp, 28h
0x1800026f8  jmp     _execute_onexit_table
0x1800026fd  call    __scrt_stub_for_is_c_termination_complete
0x180002702  test    eax, eax
0x180002704  jnz     short loc_18000270B
0x180002706  call    _o__cexit_0
0x18000270b  add     rsp, 28h
0x18000270f  retn
```
