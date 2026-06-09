# [thunk]:ATL::CComObject<CWinInetHelperClass>::Release`adjustor{56}' (void)

- ea: `0x18000bfe0`
- end: `0x18000bfe9`
- name: `?Release@?$CComObject@VCWinInetHelperClass@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bf40`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWinInetHelperClass>::Release(__int64 a1)
{
  return ATL::CComObject<CWinInetHelperClass>::Release((volatile signed __int32 *)(a1 - 56));
}

```

## disassembly

```asm
0x18000bfe0  sub     rcx, 38h ; '8'
0x18000bfe4  jmp     ?Release@?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWinInetHelperClass>::Release(void)
```
