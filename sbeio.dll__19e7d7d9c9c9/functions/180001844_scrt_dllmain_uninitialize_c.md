# __scrt_dllmain_uninitialize_c

- ea: `0x180001844`
- end: `0x180001874`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800013d8`

## callees

- `0x180001844`
- `0x180001e1c`
- `0x180001e7e`
- `0x180001ea2`
- `0x1800043d0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  CASFMutualExclusionObjectEx *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CASFMutualExclusionObjectEx::IsBackwardsCompatible(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001844  sub     rsp, 28h
0x180001848  call    __scrt_is_ucrt_dll_in_use
0x18000184d  test    eax, eax
0x18000184f  jz      short loc_180001861
0x180001851  lea     rcx, Table; Table
0x180001858  add     rsp, 28h
0x18000185c  jmp     _execute_onexit_table
0x180001861  call    ?IsBackwardsCompatible@CASFMutualExclusionObjectEx@@UEAAHXZ; CASFMutualExclusionObjectEx::IsBackwardsCompatible(void)
0x180001866  test    eax, eax
0x180001868  jnz     short loc_18000186F
0x18000186a  call    _o__cexit_0
0x18000186f  add     rsp, 28h
0x180001873  retn
```
