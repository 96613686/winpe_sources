# __scrt_dllmain_uninitialize_c

- ea: `0x18000b69c`
- end: `0x18000b6cc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b338`

## callees

- `0x18000b69c`
- `0x18000bdd0`
- `0x18000c0c8`
- `0x18000c0ec`
- `0x18000c8e4`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&stru_180025420);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000b69c  sub     rsp, 28h
0x18000b6a0  call    __scrt_is_ucrt_dll_in_use
0x18000b6a5  test    eax, eax
0x18000b6a7  jz      short loc_18000B6B9
0x18000b6a9  lea     rcx, stru_180025420; Table
0x18000b6b0  add     rsp, 28h
0x18000b6b4  jmp     _execute_onexit_table
0x18000b6b9  call    __scrt_stub_for_is_c_termination_complete
0x18000b6be  test    eax, eax
0x18000b6c0  jnz     short loc_18000B6C7
0x18000b6c2  call    _o__cexit_0
0x18000b6c7  add     rsp, 28h
0x18000b6cb  retn
```
