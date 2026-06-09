# __scrt_dllmain_uninitialize_c

- ea: `0x180006874`
- end: `0x1800068a4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006408`

## callees

- `0x180006874`
- `0x180006df8`
- `0x180006e6e`
- `0x180006e86`
- `0x1800075c8`

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
0x180006874  sub     rsp, 28h
0x180006878  call    __scrt_is_ucrt_dll_in_use
0x18000687d  test    eax, eax
0x18000687f  jz      short loc_180006891
0x180006881  lea     rcx, Table; Table
0x180006888  add     rsp, 28h
0x18000688c  jmp     _execute_onexit_table
0x180006891  call    __scrt_stub_for_is_c_termination_complete
0x180006896  test    eax, eax
0x180006898  jnz     short loc_18000689F
0x18000689a  call    _o__cexit_0
0x18000689f  add     rsp, 28h
0x1800068a3  retn
```
