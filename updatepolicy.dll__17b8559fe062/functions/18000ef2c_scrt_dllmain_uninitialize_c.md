# __scrt_dllmain_uninitialize_c

- ea: `0x18000ef2c`
- end: `0x18000ef5c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f350`

## callees

- `0x18000ec55`
- `0x18000ec85`
- `0x18000ef2c`
- `0x18000f9e0`
- `0x180015320`

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
0x18000ef2c  sub     rsp, 28h
0x18000ef30  call    __scrt_is_ucrt_dll_in_use
0x18000ef35  test    eax, eax
0x18000ef37  jz      short loc_18000EF49
0x18000ef39  lea     rcx, Table; Table
0x18000ef40  add     rsp, 28h
0x18000ef44  jmp     _execute_onexit_table
0x18000ef49  call    __scrt_stub_for_is_c_termination_complete
0x18000ef4e  test    eax, eax
0x18000ef50  jnz     short loc_18000EF57
0x18000ef52  call    _o__cexit_0
0x18000ef57  add     rsp, 28h
0x18000ef5b  retn
```
