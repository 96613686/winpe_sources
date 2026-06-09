# _SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance_::_1_::dtor$0

- ea: `0x140021add`
- end: `0x140021ae9`
- name: `_SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400138f4`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfoWrapper::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfoWrapper>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfoWrapper>>(a2 + 64);
}

```

## disassembly

```asm
0x140021add  lea     rcx, [rdx+40h]
0x140021ae4  jmp     ??1?$XPtrBase@VWUOptionalSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfoWrapper>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfoWrapper>>(void)
```
