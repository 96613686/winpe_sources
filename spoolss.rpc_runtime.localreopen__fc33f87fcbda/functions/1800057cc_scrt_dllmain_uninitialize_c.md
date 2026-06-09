# __scrt_dllmain_uninitialize_c

- ea: `0x1800057cc`
- end: `0x1800057fc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005468`

## callees

- `0x1800057cc`
- `0x180005ed8`
- `0x180005f7e`
- `0x180005fa2`
- `0x180006810`

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
0x1800057cc  sub     rsp, 28h
0x1800057d0  call    __scrt_is_ucrt_dll_in_use
0x1800057d5  test    eax, eax
0x1800057d7  jz      short loc_1800057E9
0x1800057d9  lea     rcx, Table; Table
0x1800057e0  add     rsp, 28h
0x1800057e4  jmp     _execute_onexit_table
0x1800057e9  call    __scrt_stub_for_is_c_termination_complete
0x1800057ee  test    eax, eax
0x1800057f0  jnz     short loc_1800057F7
0x1800057f2  call    _o__cexit_0
0x1800057f7  add     rsp, 28h
0x1800057fb  retn
```
