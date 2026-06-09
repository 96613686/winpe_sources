# [thunk]:ATL::CComObject<CFciPropertiesShellExt>::Release`adjustor{8}' (void)

- ea: `0x18000ccd0`
- end: `0x18000ccd9`
- name: `?Release@?$CComObject@VCFciPropertiesShellExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cc50`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFciPropertiesShellExt>::Release(__int64 a1)
{
  return ATL::CComObject<CFciPropertiesShellExt>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x18000ccd0  sub     rcx, 8
0x18000ccd4  jmp     ?Release@?$CComObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ; ATL::CComObject<CFciPropertiesShellExt>::Release(void)
```
