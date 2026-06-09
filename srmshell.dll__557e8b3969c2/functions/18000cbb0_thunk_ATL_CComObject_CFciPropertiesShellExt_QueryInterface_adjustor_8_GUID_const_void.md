# [thunk]:ATL::CComObject<CFciPropertiesShellExt>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000cbb0`
- end: `0x18000cbb9`
- name: `?QueryInterface@?$CComObject@VCFciPropertiesShellExt@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cb90`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFciPropertiesShellExt>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CFciPropertiesShellExt>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x18000cbb0  sub     rcx, 8
0x18000cbb4  jmp     ?QueryInterface@?$CComObject@VCFciPropertiesShellExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CFciPropertiesShellExt>::QueryInterface(_GUID const &,void * *)
```
