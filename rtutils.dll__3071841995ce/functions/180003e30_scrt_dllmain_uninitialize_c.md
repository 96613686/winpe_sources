# __scrt_dllmain_uninitialize_c

- ea: `0x180003e30`
- end: `0x180003e60`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003998`

## callees

- `0x180003e30`
- `0x180004390`
- `0x18000440e`
- `0x180004426`
- `0x1800045ec`

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
0x180003e30  sub     rsp, 28h
0x180003e34  call    __scrt_is_ucrt_dll_in_use
0x180003e39  test    eax, eax
0x180003e3b  jz      short loc_180003E4D
0x180003e3d  lea     rcx, Table; Table
0x180003e44  add     rsp, 28h
0x180003e48  jmp     _execute_onexit_table
0x180003e4d  call    __scrt_stub_for_is_c_termination_complete
0x180003e52  test    eax, eax
0x180003e54  jnz     short loc_180003E5B
0x180003e56  call    _o__cexit_0
0x180003e5b  add     rsp, 28h
0x180003e5f  retn
```
