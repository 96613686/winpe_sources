# [thunk]:ATL::CComObject<CFciPropertiesShellExt>::AddRef`adjustor{8}' (void)

- ea: `0x180005cd0`
- end: `0x180005cd9`
- name: `?AddRef@?$CComObject@VCFciPropertiesShellExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005cb0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFciPropertiesShellExt>::AddRef(__int64 a1)
{
  return ATL::CComObject<CFciPropertiesShellExt>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180005cd0  sub     rcx, 8
0x180005cd4  jmp     ?AddRef@?$CComObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ; ATL::CComObject<CFciPropertiesShellExt>::AddRef(void)
```
