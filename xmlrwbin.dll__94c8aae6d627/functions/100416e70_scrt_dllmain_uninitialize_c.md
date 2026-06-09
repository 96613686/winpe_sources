# __scrt_dllmain_uninitialize_c

- ea: `0x100416e70`
- end: `0x100416ea0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100416734`

## callees

- `0x100416e70`
- `0x10041730c`
- `0x10041a40c`
- `0x10041a434`
- `0x10041adf4`

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
0x100416e70  sub     rsp, 28h
0x100416e74  call    __scrt_is_ucrt_dll_in_use
0x100416e79  test    eax, eax
0x100416e7b  jz      short loc_100416E8D
0x100416e7d  lea     rcx, Table
0x100416e84  add     rsp, 28h
0x100416e88  jmp     _execute_onexit_table
0x100416e8d  call    _is_c_termination_complete
0x100416e92  test    eax, eax
0x100416e94  jnz     short loc_100416E9B
0x100416e96  call    _cexit
0x100416e9b  add     rsp, 28h
0x100416e9f  retn
```
