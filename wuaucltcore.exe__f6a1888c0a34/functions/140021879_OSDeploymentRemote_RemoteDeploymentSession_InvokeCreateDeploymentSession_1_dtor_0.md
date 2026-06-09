# _OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSession_::_1_::dtor$0

- ea: `0x140021879`
- end: `0x140021885`
- name: `_OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSession_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400135e8`

## pseudocode

```c
__int64 __fastcall OSDeploymentRemote::RemoteDeploymentSession::InvokeCreateDeploymentSession_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::~XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>(a2 + 48);
}

```

## disassembly

```asm
0x140021879  lea     rcx, [rdx+30h]
0x140021880  jmp     ??1?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::~XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>(void)
```
