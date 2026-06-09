# __scrt_dllmain_uninitialize_c

- ea: `0x180008c38`
- end: `0x180008c68`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008868`

## callees

- `0x180008c38`
- `0x18000935c`
- `0x18000946e`
- `0x180009492`
- `0x180009724`

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
0x180008c38  sub     rsp, 28h
0x180008c3c  call    __scrt_is_ucrt_dll_in_use
0x180008c41  test    eax, eax
0x180008c43  jz      short loc_180008C55
0x180008c45  lea     rcx, Table; Table
0x180008c4c  add     rsp, 28h
0x180008c50  jmp     _execute_onexit_table
0x180008c55  call    __scrt_stub_for_is_c_termination_complete
0x180008c5a  test    eax, eax
0x180008c5c  jnz     short loc_180008C63
0x180008c5e  call    _o__cexit_0
0x180008c63  add     rsp, 28h
0x180008c67  retn
```
