# __scrt_dllmain_uninitialize_c

- ea: `0x18000991c`
- end: `0x18000994c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800095b8`

## callees

- `0x18000991c`
- `0x18000a050`
- `0x18000a0ea`
- `0x18000a10e`
- `0x18000b03c`

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
0x18000991c  sub     rsp, 28h
0x180009920  call    __scrt_is_ucrt_dll_in_use
0x180009925  test    eax, eax
0x180009927  jz      short loc_180009939
0x180009929  lea     rcx, Table; Table
0x180009930  add     rsp, 28h
0x180009934  jmp     _execute_onexit_table
0x180009939  call    __scrt_stub_for_is_c_termination_complete
0x18000993e  test    eax, eax
0x180009940  jnz     short loc_180009947
0x180009942  call    _o__cexit_0
0x180009947  add     rsp, 28h
0x18000994b  retn
```
