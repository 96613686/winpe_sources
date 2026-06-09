# [thunk]:ATL::CComObject<CWinInetHelperClass>::Release`adjustor{8}' (void)

- ea: `0x18000bfd0`
- end: `0x18000bfd9`
- name: `?Release@?$CComObject@VCWinInetHelperClass@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CWinInetHelperClass>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x18000bfd0  sub     rcx, 8
0x18000bfd4  jmp     ?Release@?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAKXZ; ATL::CComObject<CWinInetHelperClass>::Release(void)
```
