# _OSDeploymentInformationFactory::RemoveDeploymentProgress_::_1_::dtor$0

- ea: `0x140021a4d`
- end: `0x140021a59`
- name: `_OSDeploymentInformationFactory::RemoveDeploymentProgress_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140007a70`

## pseudocode

```c
__int64 __fastcall OSDeploymentInformationFactory::RemoveDeploymentProgress_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::SusPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::SusPolicy<wchar_t>>(a2 + 32);
}

```

## disassembly

```asm
0x140021a4d  lea     rcx, [rdx+20h]
0x140021a54  jmp     ??1?$XPtrBaseWithArrayAllocation@_WU?$SusPolicy@_W@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::SusPolicy<wchar_t>>::~XPtrBaseWithArrayAllocation<wchar_t,WuSmartPtr::Policies::SusPolicy<wchar_t>>(void)
```
