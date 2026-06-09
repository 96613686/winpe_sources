# [thunk]:ATL::CComObject<CWinInetHelperClass>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000af70`
- end: `0x18000af79`
- name: `?QueryInterface@?$CComObject@VCWinInetHelperClass@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000af50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWinInetHelperClass>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CWinInetHelperClass>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x18000af70  sub     rcx, 8
0x18000af74  jmp     ?QueryInterface@?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CWinInetHelperClass>::QueryInterface(_GUID const &,void * *)
```
