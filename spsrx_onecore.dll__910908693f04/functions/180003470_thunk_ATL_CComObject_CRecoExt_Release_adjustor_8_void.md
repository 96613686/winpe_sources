# [thunk]:ATL::CComObject<CRecoExt>::Release`adjustor{8}' (void)

- ea: `0x180003470`
- end: `0x180003479`
- name: `?Release@?$CComObject@VCRecoExt@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CRecoExt>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180003470  sub     rcx, 8
0x180003474  jmp     ?Release@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ; ATL::CComObject<CRecoExt>::Release(void)
```
