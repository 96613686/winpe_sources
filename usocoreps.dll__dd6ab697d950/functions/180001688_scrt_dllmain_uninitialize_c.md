# __scrt_dllmain_uninitialize_c

- ea: `0x180001688`
- end: `0x1800016b8`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e8`

## callees

- `0x180001688`
- `0x180001db4`
- `0x180002082`
- `0x1800020a6`
- `0x180004300`

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
0x180001688  sub     rsp, 28h
0x18000168c  call    __scrt_is_ucrt_dll_in_use
0x180001691  test    eax, eax
0x180001693  jz      short loc_1800016A5
0x180001695  lea     rcx, Table; Table
0x18000169c  add     rsp, 28h
0x1800016a0  jmp     _execute_onexit_table
0x1800016a5  call    ?Release@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::Release(void)
0x1800016aa  test    eax, eax
0x1800016ac  jnz     short loc_1800016B3
0x1800016ae  call    _o__cexit_0
0x1800016b3  add     rsp, 28h
0x1800016b7  retn
```
