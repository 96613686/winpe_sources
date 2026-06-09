# [thunk]:ATL::CComObject<CWinInetHelperClass>::AddRef`adjustor{8}' (void)

- ea: `0x180003a40`
- end: `0x180003a49`
- name: `?AddRef@?$CComObject@VCWinInetHelperClass@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003a10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWinInetHelperClass>::AddRef(__int64 a1)
{
  return ATL::CComObject<CWinInetHelperClass>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180003a40  sub     rcx, 8
0x180003a44  jmp     ?AddRef@?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWinInetHelperClass>::AddRef(void)
```
