# [thunk]:ATL::CComObject<CRecoExt>::AddRef`adjustor{48}' (void)

- ea: `0x180003300`
- end: `0x180003309`
- name: `?AddRef@?$CComObject@VCRecoExt@@@ATL@@WDA@EAAKXZ`
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
  return ATL::CComObject<CRecoExt>::AddRef(a1 - 48);
}

```

## disassembly

```asm
0x180003300  sub     rcx, 30h ; '0'
0x180003304  jmp     ?AddRef@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComObject<CRecoExt>::AddRef(void)
```
