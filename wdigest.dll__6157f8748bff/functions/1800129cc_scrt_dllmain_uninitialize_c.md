# __scrt_dllmain_uninitialize_c

- ea: `0x1800129cc`
- end: `0x1800129fc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012668`

## callees

- `0x1800129cc`
- `0x180013120`
- `0x18001324e`
- `0x180013272`
- `0x180013c2c`

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
0x1800129cc  sub     rsp, 28h
0x1800129d0  call    __scrt_is_ucrt_dll_in_use
0x1800129d5  test    eax, eax
0x1800129d7  jz      short loc_1800129E9
0x1800129d9  lea     rcx, Table; Table
0x1800129e0  add     rsp, 28h
0x1800129e4  jmp     _execute_onexit_table
0x1800129e9  call    __scrt_stub_for_is_c_termination_complete
0x1800129ee  test    eax, eax
0x1800129f0  jnz     short loc_1800129F7
0x1800129f2  call    _o__cexit_0
0x1800129f7  add     rsp, 28h
0x1800129fb  retn
```
