# __scrt_dllmain_uninitialize_c

- ea: `0x180001ed8`
- end: `0x180001f08`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b48`

## callees

- `0x180001ed8`
- `0x180002834`
- `0x18000288e`
- `0x1800028b2`
- `0x18000e5a0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  CShareWithListItemBase *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CShareWithListItemBase::_UpdatePowerManagementLabel(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001ed8  sub     rsp, 28h
0x180001edc  call    __scrt_is_ucrt_dll_in_use
0x180001ee1  test    eax, eax
0x180001ee3  jz      short loc_180001EF5
0x180001ee5  lea     rcx, Table; Table
0x180001eec  add     rsp, 28h
0x180001ef0  jmp     _execute_onexit_table
0x180001ef5  call    ?_UpdatePowerManagementLabel@CShareWithListItemBase@@MEAAJXZ; CShareWithListItemBase::_UpdatePowerManagementLabel(void)
0x180001efa  test    eax, eax
0x180001efc  jnz     short loc_180001F03
0x180001efe  call    _o__cexit_0
0x180001f03  add     rsp, 28h
0x180001f07  retn
```
