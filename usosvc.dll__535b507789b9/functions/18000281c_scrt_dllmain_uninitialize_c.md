# __scrt_dllmain_uninitialize_c

- ea: `0x18000281c`
- end: `0x18000284c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800024b8`

## callees

- `0x18000281c`
- `0x180003018`
- `0x1800030f2`
- `0x180003116`
- `0x180009b30`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  DWORD v0; // edx
  DWORD v1; // ecx
  void *v2; // r8
  void *v3; // r9
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete(v1, v0, v2, v3);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000281c  sub     rsp, 28h
0x180002820  call    __scrt_is_ucrt_dll_in_use
0x180002825  test    eax, eax
0x180002827  jz      short loc_180002839
0x180002829  lea     rcx, Table; Table
0x180002830  add     rsp, 28h
0x180002834  jmp     _execute_onexit_table
0x180002839  call    __scrt_stub_for_is_c_termination_complete
0x18000283e  test    eax, eax
0x180002840  jnz     short loc_180002847
0x180002842  call    _o__cexit_0
0x180002847  add     rsp, 28h
0x18000284b  retn
```
