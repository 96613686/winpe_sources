# [thunk]:ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x180008700`
- end: `0x180008709`
- name: `?QueryInterface@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface((char *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x180008700  sub     rcx, 18h
0x180008704  jmp     ?QueryInterface@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface(_GUID const &,void * *)
```
