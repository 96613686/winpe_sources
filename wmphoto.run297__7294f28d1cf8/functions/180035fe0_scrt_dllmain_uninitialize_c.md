# __scrt_dllmain_uninitialize_c

- ea: `0x180035fe0`
- end: `0x180036010`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035c38`

## callees

- `0x180035fe0`
- `0x180036a40`
- `0x180036afa`
- `0x180036b1e`
- `0x180037d00`

## pseudocode

```c
HRESULT _scrt_dllmain_uninitialize_c()
{
  HRESULT result; // eax

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
0x180035fe0  sub     rsp, 28h
0x180035fe4  call    __scrt_is_ucrt_dll_in_use
0x180035fe9  test    eax, eax
0x180035feb  jz      short loc_180035FFD
0x180035fed  lea     rcx, Table; Table
0x180035ff4  add     rsp, 28h
0x180035ff8  jmp     _execute_onexit_table
0x180035ffd  call    __scrt_stub_for_is_c_termination_complete
0x180036002  test    eax, eax
0x180036004  jnz     short loc_18003600B
0x180036006  call    _o__cexit_0
0x18003600b  add     rsp, 28h
0x18003600f  retn
```
