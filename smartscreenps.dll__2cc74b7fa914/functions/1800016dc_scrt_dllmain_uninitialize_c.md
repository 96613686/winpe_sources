# __scrt_dllmain_uninitialize_c

- ea: `0x1800016dc`
- end: `0x18000170c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001378`

## callees

- `0x1800016dc`
- `0x180001e78`
- `0x1800068f6`
- `0x18000690e`
- `0x180006bf8`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table_0(&Table);
  }
  else if ( !(unsigned int)_scrt_stub_for_is_c_termination_complete() )
  {
    cexit_0();
  }
}

```

## disassembly

```asm
0x1800016dc  sub     rsp, 28h
0x1800016e0  call    __scrt_is_ucrt_dll_in_use
0x1800016e5  test    eax, eax
0x1800016e7  jz      short loc_1800016F9
0x1800016e9  lea     rcx, Table; Table
0x1800016f0  add     rsp, 28h
0x1800016f4  jmp     _execute_onexit_table_0
0x1800016f9  call    __scrt_stub_for_is_c_termination_complete
0x1800016fe  test    eax, eax
0x180001700  jnz     short loc_180001707
0x180001702  call    _cexit_0
0x180001707  add     rsp, 28h
0x18000170b  retn
```
