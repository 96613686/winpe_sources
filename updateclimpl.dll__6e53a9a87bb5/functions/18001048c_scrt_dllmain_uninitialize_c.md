# __scrt_dllmain_uninitialize_c

- ea: `0x18001048c`
- end: `0x1800104bc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800108b0`

## callees

- `0x18000ef80`
- `0x180010168`
- `0x180010198`
- `0x18001048c`
- `0x180010f18`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = std::wstreambuf::showmanyc();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18001048c  sub     rsp, 28h
0x180010490  call    __scrt_is_ucrt_dll_in_use
0x180010495  test    eax, eax
0x180010497  jz      short loc_1800104A9
0x180010499  lea     rcx, Table; Table
0x1800104a0  add     rsp, 28h
0x1800104a4  jmp     _execute_onexit_table
0x1800104a9  call    ?showmanyc@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@MEAA_JXZ; std::wstreambuf::showmanyc(void)
0x1800104ae  test    eax, eax
0x1800104b0  jnz     short loc_1800104B7
0x1800104b2  call    _o__cexit_0
0x1800104b7  add     rsp, 28h
0x1800104bb  retn
```
