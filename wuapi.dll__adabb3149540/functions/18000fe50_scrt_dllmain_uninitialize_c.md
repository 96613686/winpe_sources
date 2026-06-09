# __scrt_dllmain_uninitialize_c

- ea: `0x18000fe50`
- end: `0x18000fe80`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800102f0`

## callees

- `0x18000fbee`
- `0x18000fc1e`
- `0x18000fe50`
- `0x18001094c`
- `0x1800158ec`

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
0x18000fe50  sub     rsp, 28h
0x18000fe54  call    __scrt_is_ucrt_dll_in_use
0x18000fe59  test    eax, eax
0x18000fe5b  jz      short loc_18000FE6D
0x18000fe5d  lea     rcx, Table; Table
0x18000fe64  add     rsp, 28h
0x18000fe68  jmp     _execute_onexit_table
0x18000fe6d  call    __scrt_stub_for_is_c_termination_complete
0x18000fe72  test    eax, eax
0x18000fe74  jnz     short loc_18000FE7B
0x18000fe76  call    _o__cexit_0
0x18000fe7b  add     rsp, 28h
0x18000fe7f  retn
```
