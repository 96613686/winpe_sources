# [thunk]:ATL::CComContainedObject<CRecoExt>::AddRef`adjustor{48}' (void)

- ea: `0x180003290`
- end: `0x180003299`
- name: `?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@WDA@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::AddRef(a1 - 48);
}

```

## disassembly

```asm
0x180003290  sub     rcx, 30h ; '0'
0x180003294  jmp     ?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::AddRef(void)
```
