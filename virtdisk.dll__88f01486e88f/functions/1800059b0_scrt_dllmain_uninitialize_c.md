# __scrt_dllmain_uninitialize_c

- ea: `0x1800059b0`
- end: `0x1800059e0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005518`

## callees

- `0x1800059b0`
- `0x180005f10`
- `0x180005f82`
- `0x180005f9a`
- `0x1800061c0`

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
0x1800059b0  sub     rsp, 28h
0x1800059b4  call    __scrt_is_ucrt_dll_in_use
0x1800059b9  test    eax, eax
0x1800059bb  jz      short loc_1800059CD
0x1800059bd  lea     rcx, Table; Table
0x1800059c4  add     rsp, 28h
0x1800059c8  jmp     _execute_onexit_table
0x1800059cd  call    __scrt_stub_for_is_c_termination_complete
0x1800059d2  test    eax, eax
0x1800059d4  jnz     short loc_1800059DB
0x1800059d6  call    _o__cexit_0
0x1800059db  add     rsp, 28h
0x1800059df  retn
```
