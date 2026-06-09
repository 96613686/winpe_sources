# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180003458`
- end: `0x180003476`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000344c`
- `0x1800035b0`
- `0x180004fc8`
- `0x18000530c`
- `0x180007b3c`
- `0x1800081a4`
- `0x18000d158`
- `0x18000d180`
- `0x18000f448`
- `0x18000fdf0`
- `0x1800105cc`
- `0x1800138d0`
- `0x1800139a0`
- `0x180014230`
- `0x180020a10`
- `0x180022488`
- `0x180023550`
- `0x180023e18`
- `0x180023f10`
- `0x180026024`
- `0x180029cc8`
- `0x180029cf4`
- `0x18002a410`
- `0x18002b1d4`
- `0x18002c1d0`
- `0x18002c8a8`
- `0x18002d3f0`
- `0x18002d458`
- `0x18002d520`

## callees

- `0x180003458`
- `0x180030010`

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
0x180003458  sub     rsp, 28h
0x18000345c  mov     rcx, [rcx]
0x18000345f  test    rcx, rcx
0x180003462  jz      short loc_180003471
0x180003464  mov     rax, [rcx]
0x180003467  mov     rax, [rax+10h]
0x18000346b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003470  nop
0x180003471  add     rsp, 28h
0x180003475  retn
```
