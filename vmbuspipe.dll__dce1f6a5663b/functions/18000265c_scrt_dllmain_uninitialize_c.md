# __scrt_dllmain_uninitialize_c

- ea: `0x18000265c`
- end: `0x18000268c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022c8`

## callees

- `0x18000265c`
- `0x180002de8`
- `0x180003012`
- `0x180003036`
- `0x180003128`

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
0x18000265c  sub     rsp, 28h
0x180002660  call    __scrt_is_ucrt_dll_in_use
0x180002665  test    eax, eax
0x180002667  jz      short loc_180002679
0x180002669  lea     rcx, Table; Table
0x180002670  add     rsp, 28h
0x180002674  jmp     _execute_onexit_table
0x180002679  call    __scrt_stub_for_is_c_termination_complete
0x18000267e  test    eax, eax
0x180002680  jnz     short loc_180002687
0x180002682  call    _o__cexit_0
0x180002687  add     rsp, 28h
0x18000268b  retn
```
