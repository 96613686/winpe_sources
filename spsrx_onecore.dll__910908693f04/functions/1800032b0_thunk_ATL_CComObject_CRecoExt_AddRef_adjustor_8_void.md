# [thunk]:ATL::CComObject<CRecoExt>::AddRef`adjustor{8}' (void)

- ea: `0x1800032b0`
- end: `0x1800032b9`
- name: `?AddRef@?$CComObject@VCRecoExt@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CRecoExt>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1800032b0  sub     rcx, 8
0x1800032b4  jmp     ?AddRef@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComObject<CRecoExt>::AddRef(void)
```
