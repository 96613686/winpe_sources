# __scrt_dllmain_uninitialize_c

- ea: `0x18000e7c4`
- end: `0x18000e7f4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e428`

## callees

- `0x18000e7c4`
- `0x18000eeb4`
- `0x18000ef52`
- `0x18000ef76`
- `0x18000fafc`

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
0x18000e7c4  sub     rsp, 28h
0x18000e7c8  call    __scrt_is_ucrt_dll_in_use
0x18000e7cd  test    eax, eax
0x18000e7cf  jz      short loc_18000E7E1
0x18000e7d1  lea     rcx, Table; Table
0x18000e7d8  add     rsp, 28h
0x18000e7dc  jmp     _execute_onexit_table
0x18000e7e1  call    __scrt_stub_for_is_c_termination_complete
0x18000e7e6  test    eax, eax
0x18000e7e8  jnz     short loc_18000E7EF
0x18000e7ea  call    _o__cexit_0
0x18000e7ef  add     rsp, 28h
0x18000e7f3  retn
```
