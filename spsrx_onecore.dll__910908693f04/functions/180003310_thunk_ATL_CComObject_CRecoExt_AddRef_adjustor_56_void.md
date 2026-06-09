# [thunk]:ATL::CComObject<CRecoExt>::AddRef`adjustor{56}' (void)

- ea: `0x180003310`
- end: `0x180003319`
- name: `?AddRef@?$CComObject@VCRecoExt@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005d90`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CRecoExt>::AddRef(__int64 a1)
{
  return ATL::CComObject<CRecoExt>::AddRef(a1 - 56);
}

```

## disassembly

```asm
0x180003310  sub     rcx, 38h ; '8'
0x180003314  jmp     ?AddRef@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComObject<CRecoExt>::AddRef(void)
```
