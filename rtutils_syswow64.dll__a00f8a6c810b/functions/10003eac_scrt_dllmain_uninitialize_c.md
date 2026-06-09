# ___scrt_dllmain_uninitialize_c

- ea: `0x10003eac`
- end: `0x10003ecf`
- name: `___scrt_dllmain_uninitialize_c`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100039eb`

## callees

- `0x10003eac`
- `0x100044c5`
- `0x10004513`
- `0x1000452b`
- `0x10004716`

## pseudocode

```c
void __scrt_dllmain_uninitialize_c()
{
  if ( __scrt_is_ucrt_dll_in_use() )
  {
    _o__execute_onexit_table(&Table);
  }
  else if ( !_is_c_termination_complete() )
  {
    _cexit();
  }
}

```

## disassembly

```asm
0x10003eac  call    ___scrt_is_ucrt_dll_in_use
0x10003eb1  test    eax, eax
0x10003eb3  jz      short loc_10003EC1
0x10003eb5  push    offset Table; Table
0x10003eba  call    __o__execute_onexit_table
0x10003ebf  pop     ecx
0x10003ec0  retn
0x10003ec1  call    __is_c_termination_complete
0x10003ec6  test    eax, eax
0x10003ec8  jz      __cexit
0x10003ece  retn
```
