# __scrt_dllmain_uninitialize_c

- ea: `0x18000237c`
- end: `0x1800023ac`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002018`

## callees

- `0x18000237c`
- `0x180002a8c`
- `0x180002af2`
- `0x180002b16`
- `0x180003198`

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
0x18000237c  sub     rsp, 28h
0x180002380  call    __scrt_is_ucrt_dll_in_use
0x180002385  test    eax, eax
0x180002387  jz      short loc_180002399
0x180002389  lea     rcx, Table; Table
0x180002390  add     rsp, 28h
0x180002394  jmp     _execute_onexit_table
0x180002399  call    __scrt_stub_for_is_c_termination_complete
0x18000239e  test    eax, eax
0x1800023a0  jnz     short loc_1800023A7
0x1800023a2  call    _o__cexit_0
0x1800023a7  add     rsp, 28h
0x1800023ab  retn
```
