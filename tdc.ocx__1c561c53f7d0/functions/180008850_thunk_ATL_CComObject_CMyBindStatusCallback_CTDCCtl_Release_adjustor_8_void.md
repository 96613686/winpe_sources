# [thunk]:ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release`adjustor{8}' (void)

- ea: `0x180008850`
- end: `0x180008859`
- name: `?Release@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800087d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release(__int64 a1)
{
  return ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x180008850  sub     rcx, 8
0x180008854  jmp     ?Release@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAKXZ; ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release(void)
```
