# [thunk]:ATL::CComObject<CUWFCspCurrentSessionNode>::Release`adjustor{8}' (void)

- ea: `0x18000ad40`
- end: `0x18000ad49`
- name: `?Release@?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000acb0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspCurrentSessionNode>::Release(__int64 a1)
{
  return ATL::CComObject<CUWFCspNextSessionNode>::Release(a1 - 8);
}

```

## disassembly

```asm
0x18000ad40  sub     rcx, 8
0x18000ad44  jmp     ?Release@?$CComObject@VCUWFCspNextSessionNode@@@ATL@@UEAAKXZ; ATL::CComObject<CUWFCspNextSessionNode>::Release(void)
```
