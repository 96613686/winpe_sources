# __scrt_dllmain_uninitialize_c

- ea: `0x18000db34`
- end: `0x18000db64`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d798`

## callees

- `0x18000db34`
- `0x18000e224`
- `0x18000e2a2`
- `0x18000e2c6`
- `0x18000ee4c`

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
0x18000db34  sub     rsp, 28h
0x18000db38  call    __scrt_is_ucrt_dll_in_use
0x18000db3d  test    eax, eax
0x18000db3f  jz      short loc_18000DB51
0x18000db41  lea     rcx, Table; Table
0x18000db48  add     rsp, 28h
0x18000db4c  jmp     _execute_onexit_table
0x18000db51  call    __scrt_stub_for_is_c_termination_complete
0x18000db56  test    eax, eax
0x18000db58  jnz     short loc_18000DB5F
0x18000db5a  call    _o__cexit_0
0x18000db5f  add     rsp, 28h
0x18000db63  retn
```
