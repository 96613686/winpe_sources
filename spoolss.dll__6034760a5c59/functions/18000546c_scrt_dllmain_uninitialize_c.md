# __scrt_dllmain_uninitialize_c

- ea: `0x18000546c`
- end: `0x18000549c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005108`

## callees

- `0x18000546c`
- `0x180005b78`
- `0x180005c0e`
- `0x180005c32`
- `0x1800064a0`

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
0x18000546c  sub     rsp, 28h
0x180005470  call    __scrt_is_ucrt_dll_in_use
0x180005475  test    eax, eax
0x180005477  jz      short loc_180005489
0x180005479  lea     rcx, Table; Table
0x180005480  add     rsp, 28h
0x180005484  jmp     _execute_onexit_table
0x180005489  call    __scrt_stub_for_is_c_termination_complete
0x18000548e  test    eax, eax
0x180005490  jnz     short loc_180005497
0x180005492  call    _o__cexit_0
0x180005497  add     rsp, 28h
0x18000549b  retn
```
