# _ATL::CComCreator_ATL::CComAggObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor$1

- ea: `0x18001e77c`
- end: `0x18001e78c`
- name: `_ATL::CComCreator_ATL::CComAggObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor$1`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011dec`

## pseudocode

```c
void __fastcall ATL::CComCreator_ATL::CComAggObject_CFciPropertiesShellExt___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  ATL::CComContainedObject<CFciPropertiesShellExt>::~CComContainedObject<CFciPropertiesShellExt>((CFciPropertiesShellExt *)(*(_QWORD *)(a2 + 40) + 16LL));
}

```

## disassembly

```asm
0x18001e77c  mov     rcx, [rdx+28h]
0x18001e783  add     rcx, 10h
0x18001e787  jmp     ??1?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@QEAA@XZ; ATL::CComContainedObject<CFciPropertiesShellExt>::~CComContainedObject<CFciPropertiesShellExt>(void)
```
