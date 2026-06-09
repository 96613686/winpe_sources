# __scrt_dllmain_uninitialize_c

- ea: `0x18000cbc8`
- end: `0x18000cbf8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c778`

## callees

- `0x18000cbc8`
- `0x18000d344`
- `0x18000d3b6`
- `0x18000d3da`
- `0x18000dd90`

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
0x18000cbc8  sub     rsp, 28h
0x18000cbcc  call    __scrt_is_ucrt_dll_in_use
0x18000cbd1  test    eax, eax
0x18000cbd3  jz      short loc_18000CBE5
0x18000cbd5  lea     rcx, Table; Table
0x18000cbdc  add     rsp, 28h
0x18000cbe0  jmp     _execute_onexit_table
0x18000cbe5  call    __scrt_stub_for_is_c_termination_complete
0x18000cbea  test    eax, eax
0x18000cbec  jnz     short loc_18000CBF3
0x18000cbee  call    _o__cexit_0
0x18000cbf3  add     rsp, 28h
0x18000cbf7  retn
```
