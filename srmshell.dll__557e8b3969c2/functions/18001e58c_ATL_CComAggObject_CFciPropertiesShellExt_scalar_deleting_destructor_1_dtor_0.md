# _ATL::CComAggObject_CFciPropertiesShellExt_::_scalar_deleting_destructor__::_1_::dtor$0

- ea: `0x18001e58c`
- end: `0x18001e59c`
- name: `_ATL::CComAggObject_CFciPropertiesShellExt_::_scalar_deleting_destructor__::_1_::dtor$0`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011dec`

## pseudocode

```c
void __fastcall ATL::CComAggObject_CFciPropertiesShellExt_::_scalar_deleting_destructor__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  ATL::CComContainedObject<CFciPropertiesShellExt>::~CComContainedObject<CFciPropertiesShellExt>((CFciPropertiesShellExt *)(*(_QWORD *)(a2 + 48) + 16LL));
}

```

## disassembly

```asm
0x18001e58c  mov     rcx, [rdx+30h]
0x18001e593  add     rcx, 10h
0x18001e597  jmp     ??1?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@QEAA@XZ; ATL::CComContainedObject<CFciPropertiesShellExt>::~CComContainedObject<CFciPropertiesShellExt>(void)
```
