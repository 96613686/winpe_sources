# [thunk]:ATL::CComObject<CRecoExt>::Release`adjustor{32}' (void)

- ea: `0x1800034a0`
- end: `0x1800034a9`
- name: `?Release@?$CComObject@VCRecoExt@@@ATL@@WCA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007ec0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRecoExt>::Release(__int64 a1)
{
  return ATL::CComObject<CRecoExt>::Release(a1 - 32);
}

```

## disassembly

```asm
0x1800034a0  sub     rcx, 20h ; ' '
0x1800034a4  jmp     ?Release@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComObject<CRecoExt>::Release(void)
```
