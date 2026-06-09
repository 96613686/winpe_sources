# [thunk]:ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x1800086f0`
- end: `0x1800086f9`
- name: `?QueryInterface@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086c0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x1800086f0  sub     rcx, 10h
0x1800086f4  jmp     ?QueryInterface@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface(_GUID const &,void * *)
```
