# _GetRegKeyPath_::_1_::dtor$0

- ea: `0x180016bc8`
- end: `0x180016bd4`
- name: `_GetRegKeyPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000ab6c`

## pseudocode

```c
void __fastcall GetRegKeyPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>((void **)(a2 + 56));
}

```

## disassembly

```asm
0x180016bc8  lea     rcx, [rdx+38h]
0x180016bcf  jmp     ??1?$XPtrBaseWithArrayAllocation@_WU?$CoPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(void)
```
