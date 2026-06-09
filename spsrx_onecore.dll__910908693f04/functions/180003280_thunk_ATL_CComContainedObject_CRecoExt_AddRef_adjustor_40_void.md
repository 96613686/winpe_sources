# [thunk]:ATL::CComContainedObject<CRecoExt>::AddRef`adjustor{40}' (void)

- ea: `0x180003280`
- end: `0x180003289`
- name: `?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@WCI@EAAKXZ`
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
  return ATL::CComContainedObject<CRecoExt>::AddRef(a1 - 40);
}

```

## disassembly

```asm
0x180003280  sub     rcx, 28h ; '('
0x180003284  jmp     ?AddRef@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CRecoExt>::AddRef(void)
```
