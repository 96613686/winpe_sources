# __scrt_dllmain_uninitialize_c

- ea: `0x1800022b4`
- end: `0x1800022e4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001eb8`

## callees

- `0x1800022b4`
- `0x1800029fc`
- `0x180002a9a`
- `0x180002abe`
- `0x18000ec50`

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
0x1800022b4  sub     rsp, 28h
0x1800022b8  call    __scrt_is_ucrt_dll_in_use
0x1800022bd  test    eax, eax
0x1800022bf  jz      short loc_1800022D1
0x1800022c1  lea     rcx, Table; Table
0x1800022c8  add     rsp, 28h
0x1800022cc  jmp     _execute_onexit_table
0x1800022d1  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800022d6  test    eax, eax
0x1800022d8  jnz     short loc_1800022DF
0x1800022da  call    _o__cexit_0
0x1800022df  add     rsp, 28h
0x1800022e3  retn
```
