# __scrt_dllmain_uninitialize_c

- ea: `0x180001aa4`
- end: `0x180001ad4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001390`

## callees

- `0x180001aa4`
- `0x1800024f0`
- `0x1800025b6`
- `0x1800025da`
- `0x18000270c`

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
0x180001aa4  sub     rsp, 28h
0x180001aa8  call    __scrt_is_ucrt_dll_in_use
0x180001aad  test    eax, eax
0x180001aaf  jz      short loc_180001AC1
0x180001ab1  lea     rcx, Table; Table
0x180001ab8  add     rsp, 28h
0x180001abc  jmp     _execute_onexit_table
0x180001ac1  call    __scrt_stub_for_is_c_termination_complete
0x180001ac6  test    eax, eax
0x180001ac8  jnz     short loc_180001ACF
0x180001aca  call    _o__cexit_0
0x180001acf  add     rsp, 28h
0x180001ad3  retn
```
