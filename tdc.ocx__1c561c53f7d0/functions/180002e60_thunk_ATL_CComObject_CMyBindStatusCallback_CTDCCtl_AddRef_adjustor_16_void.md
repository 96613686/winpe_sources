# [thunk]:ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::AddRef`adjustor{16}' (void)

- ea: `0x180002e60`
- end: `0x180002e69`
- name: `?AddRef@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002e30`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::AddRef(__int64 a1)
{
  return ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180002e60  sub     rcx, 10h
0x180002e64  jmp     ?AddRef@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAKXZ; ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::AddRef(void)
```
