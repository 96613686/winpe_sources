# [thunk]:ATL::CComContainedObject<CFciPropertiesShellExt>::Release`adjustor{8}' (void)

- ea: `0x180015420`
- end: `0x180015429`
- name: `?Release@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015400`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFciPropertiesShellExt>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CFciPropertiesShellExt>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180015420  sub     rcx, 8
0x180015424  jmp     ?Release@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CFciPropertiesShellExt>::Release(void)
```
