# __scrt_dllmain_uninitialize_c

- ea: `0x180003464`
- end: `0x180003494`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800030c8`

## callees

- `0x180003464`
- `0x180003bc4`
- `0x180003cc2`
- `0x180003ce6`
- `0x1800086d0`

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
0x180003464  sub     rsp, 28h
0x180003468  call    __scrt_is_ucrt_dll_in_use
0x18000346d  test    eax, eax
0x18000346f  jz      short loc_180003481
0x180003471  lea     rcx, Table; Table
0x180003478  add     rsp, 28h
0x18000347c  jmp     _execute_onexit_table
0x180003481  call    __scrt_stub_for_is_c_termination_complete
0x180003486  test    eax, eax
0x180003488  jnz     short loc_18000348F
0x18000348a  call    _o__cexit_0
0x18000348f  add     rsp, 28h
0x180003493  retn
```
