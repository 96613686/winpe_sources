# [thunk]:ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release`adjustor{16}' (void)

- ea: `0x180008860`
- end: `0x180008869`
- name: `?Release@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release((_DWORD *)(a1 - 16));
}

```

## disassembly

```asm
0x180008860  sub     rcx, 10h
0x180008864  jmp     ?Release@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAKXZ; ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::Release(void)
```
