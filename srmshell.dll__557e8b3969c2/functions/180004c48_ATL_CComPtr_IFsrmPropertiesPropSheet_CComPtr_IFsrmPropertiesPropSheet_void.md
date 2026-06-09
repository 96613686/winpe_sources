# ATL::CComPtr<IFsrmPropertiesPropSheet>::~CComPtr<IFsrmPropertiesPropSheet>(void)

- ea: `0x180004c48`
- end: `0x180004c6b`
- name: `??1?$CComPtr@UIFsrmPropertiesPropSheet@@@ATL@@QEAA@XZ`
- size: `35`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c724`
- `0x18001c736`
- `0x18001c872`
- `0x18001d11c`
- `0x18001d188`
- `0x18001d1ac`
- `0x18001d68b`
- `0x18001df0c`
- `0x18001e10a`
- `0x18001e11c`

## callees

- `0x180004c48`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IFsrmPropertiesPropSheet>::~CComPtr<IFsrmPropertiesPropSheet>(__int64 *a1)
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
0x180004c48  mov     [rsp+arg_0], rcx
0x180004c4d  sub     rsp, 28h
0x180004c51  mov     rcx, [rcx]
0x180004c54  test    rcx, rcx
0x180004c57  jz      short loc_180004C66
0x180004c59  mov     rax, [rcx]
0x180004c5c  mov     rax, [rax+10h]
0x180004c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c65  nop
0x180004c66  add     rsp, 28h
0x180004c6a  retn
```
