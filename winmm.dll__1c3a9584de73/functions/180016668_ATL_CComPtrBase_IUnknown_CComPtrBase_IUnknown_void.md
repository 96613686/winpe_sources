# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180016668`
- end: `0x180016686`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001665c`
- `0x18001795c`
- `0x180017f04`

## callees

- `0x180016668`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180016668  sub     rsp, 28h
0x18001666c  mov     rcx, [rcx]
0x18001666f  test    rcx, rcx
0x180016672  jz      short loc_180016681
0x180016674  mov     rax, [rcx]
0x180016677  mov     rax, [rax+10h]
0x18001667b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016680  nop
0x180016681  add     rsp, 28h
0x180016685  retn
```
