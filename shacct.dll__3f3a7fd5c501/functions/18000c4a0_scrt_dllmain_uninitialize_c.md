# __scrt_dllmain_uninitialize_c

- ea: `0x18000c4a0`
- end: `0x18000c4d0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c028`

## callees

- `0x18000c4a0`
- `0x18000ca78`
- `0x18000cae2`
- `0x18000cb06`
- `0x18000d800`

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
0x18000c4a0  sub     rsp, 28h
0x18000c4a4  call    __scrt_is_ucrt_dll_in_use
0x18000c4a9  test    eax, eax
0x18000c4ab  jz      short loc_18000C4BD
0x18000c4ad  lea     rcx, Table; Table
0x18000c4b4  add     rsp, 28h
0x18000c4b8  jmp     _execute_onexit_table
0x18000c4bd  call    __scrt_stub_for_is_c_termination_complete
0x18000c4c2  test    eax, eax
0x18000c4c4  jnz     short loc_18000C4CB
0x18000c4c6  call    _o__cexit_0
0x18000c4cb  add     rsp, 28h
0x18000c4cf  retn
```
