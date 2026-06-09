# __scrt_dllmain_uninitialize_c

- ea: `0x180001f0c`
- end: `0x180001f3c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ba8`

## callees

- `0x180001f0c`
- `0x180002928`
- `0x180002a02`
- `0x180002a26`
- `0x180002b5c`

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
0x180001f0c  sub     rsp, 28h
0x180001f10  call    __scrt_is_ucrt_dll_in_use
0x180001f15  test    eax, eax
0x180001f17  jz      short loc_180001F29
0x180001f19  lea     rcx, Table; Table
0x180001f20  add     rsp, 28h
0x180001f24  jmp     _execute_onexit_table
0x180001f29  call    __scrt_stub_for_is_c_termination_complete
0x180001f2e  test    eax, eax
0x180001f30  jnz     short loc_180001F37
0x180001f32  call    _o__cexit_0
0x180001f37  add     rsp, 28h
0x180001f3b  retn
```
