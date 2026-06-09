# ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(void)

- ea: `0x180004c74`
- end: `0x180004c92`
- name: `??1?$CComPtrBase@UIFsrmPropertyDefinition2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c089`
- `0x18001c748`
- `0x18001c75a`
- `0x18001c896`
- `0x18001d1e2`
- `0x18001d264`
- `0x18001d276`
- `0x18001d6c1`
- `0x18001df42`
- `0x18001e12e`
- `0x18001e140`

## callees

- `0x180004c74`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IFsrmPropertyDefinition2>::~CComPtrBase<IFsrmPropertyDefinition2>(__int64 *a1)
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
0x180004c74  sub     rsp, 28h
0x180004c78  mov     rcx, [rcx]
0x180004c7b  test    rcx, rcx
0x180004c7e  jz      short loc_180004C8D
0x180004c80  mov     rax, [rcx]
0x180004c83  mov     rax, [rax+10h]
0x180004c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c8c  nop
0x180004c8d  add     rsp, 28h
0x180004c91  retn
```
