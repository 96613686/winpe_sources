# __scrt_dllmain_uninitialize_c

- ea: `0x180002718`
- end: `0x180002748`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002358`

## callees

- `0x180001ed0`
- `0x180002718`
- `0x180002dd4`
- `0x180002e2e`
- `0x180002e52`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  ATL::CRegObject *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CRegObject::Release(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002718  sub     rsp, 28h
0x18000271c  call    __scrt_is_ucrt_dll_in_use
0x180002721  test    eax, eax
0x180002723  jz      short loc_180002735
0x180002725  lea     rcx, Table; Table
0x18000272c  add     rsp, 28h
0x180002730  jmp     _execute_onexit_table
0x180002735  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x18000273a  test    eax, eax
0x18000273c  jnz     short loc_180002743
0x18000273e  call    _o__cexit_0
0x180002743  add     rsp, 28h
0x180002747  retn
```
