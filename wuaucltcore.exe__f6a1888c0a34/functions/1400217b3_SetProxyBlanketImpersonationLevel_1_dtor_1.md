# _SetProxyBlanketImpersonationLevel_::_1_::dtor$1

- ea: `0x1400217b3`
- end: `0x1400217bf`
- name: `_SetProxyBlanketImpersonationLevel_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000bd78`

## pseudocode

```c
void __fastcall SetProxyBlanketImpersonationLevel_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>((void **)(a2 + 96));
}

```

## disassembly

```asm
0x1400217b3  lea     rcx, [rdx+60h]
0x1400217ba  jmp     ??1?$XPtrBaseWithArrayAllocation@_WU?$CoPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::CoPolicy<wchar_t>>(void)
```
