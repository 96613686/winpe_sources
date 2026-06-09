# _SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance_::_1_::dtor$0

- ea: `0x140021867`
- end: `0x140021873`
- name: `_SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400135e8`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::~XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>(a2 + 64);
}

```

## disassembly

```asm
0x140021867  lea     rcx, [rdx+40h]
0x14002186e  jmp     ??1?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::~XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>(void)
```
