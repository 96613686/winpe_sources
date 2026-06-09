# [thunk]:ATL::CComContainedObject<CRecoExt>::AddRef`adjustor{24}' (void)

- ea: `0x180003260`
- end: `0x180003269`
- name: `?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x180003260  sub     rcx, 18h
0x180003264  jmp     ?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::AddRef(void)
```
