# [thunk]:ATL::CComContainedObject<CFciPropertiesShellExt>::AddRef`adjustor{8}' (void)

- ea: `0x1800125f0`
- end: `0x1800125f9`
- name: `?AddRef@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800125d0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFciPropertiesShellExt>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CFciPropertiesShellExt>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1800125f0  sub     rcx, 8
0x1800125f4  jmp     ?AddRef@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CFciPropertiesShellExt>::AddRef(void)
```
