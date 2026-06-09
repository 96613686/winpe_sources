# [thunk]:ATL::CComContainedObject<CRecoExt>::AddRef`adjustor{56}' (void)

- ea: `0x1800032a0`
- end: `0x1800032a9`
- name: `?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001c90`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CRecoExt>::AddRef(a1 - 56);
}

```

## disassembly

```asm
0x1800032a0  sub     rcx, 38h ; '8'
0x1800032a4  jmp     ?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::AddRef(void)
```
