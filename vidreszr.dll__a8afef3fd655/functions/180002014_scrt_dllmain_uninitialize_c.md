# __scrt_dllmain_uninitialize_c

- ea: `0x180002014`
- end: `0x180002044`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001ba8`

## callees

- `0x180002014`
- `0x180002598`
- `0x1800025f2`
- `0x18000260a`
- `0x180002fd0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  unsigned int v0; // edx
  CWMResizeDMO *v1; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CWMResizeDMO::SetWorkQueue(v1, v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002014  sub     rsp, 28h
0x180002018  call    __scrt_is_ucrt_dll_in_use
0x18000201d  test    eax, eax
0x18000201f  jz      short loc_180002031
0x180002021  lea     rcx, Table; Table
0x180002028  add     rsp, 28h
0x18000202c  jmp     _execute_onexit_table
0x180002031  call    ?SetWorkQueue@CWMResizeDMO@@UEAAJK@Z; CWMResizeDMO::SetWorkQueue(ulong)
0x180002036  test    eax, eax
0x180002038  jnz     short loc_18000203F
0x18000203a  call    _o__cexit_0
0x18000203f  add     rsp, 28h
0x180002043  retn
```
