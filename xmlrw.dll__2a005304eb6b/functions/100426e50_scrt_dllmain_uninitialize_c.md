# __scrt_dllmain_uninitialize_c

- ea: `0x100426e50`
- end: `0x100426e80`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100426724`

## callees

- `0x100426e50`
- `0x1004272e0`
- `0x10042a39c`
- `0x10042a3c4`
- `0x10042ad84`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table(&Table);
  }
  else if ( !is_c_termination_complete() )
  {
    cexit();
  }
}

```

## disassembly

```asm
0x100426e50  sub     rsp, 28h
0x100426e54  call    __scrt_is_ucrt_dll_in_use
0x100426e59  test    eax, eax
0x100426e5b  jz      short loc_100426E6D
0x100426e5d  lea     rcx, Table
0x100426e64  add     rsp, 28h
0x100426e68  jmp     _execute_onexit_table
0x100426e6d  call    _is_c_termination_complete
0x100426e72  test    eax, eax
0x100426e74  jnz     short loc_100426E7B
0x100426e76  call    _cexit
0x100426e7b  add     rsp, 28h
0x100426e7f  retn
```
