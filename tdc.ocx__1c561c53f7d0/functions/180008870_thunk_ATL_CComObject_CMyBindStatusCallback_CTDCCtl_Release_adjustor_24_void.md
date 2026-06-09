# [thunk]:ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release`adjustor{24}' (void)

- ea: `0x180008870`
- end: `0x180008879`
- name: `?Release@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release((_DWORD *)(a1 - 24));
}

```

## disassembly

```asm
0x180008870  sub     rcx, 18h
0x180008874  jmp     ?Release@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAKXZ; ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release(void)
```
