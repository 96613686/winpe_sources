# _SessionDataUtil::WUOptionalSessionInfo::CreateInstance_::_1_::dtor$0

- ea: `0x140021a71`
- end: `0x140021a7d`
- name: `_SessionDataUtil::WUOptionalSessionInfo::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013cac`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo>>(a2 + 48);
}

```

## disassembly

```asm
0x140021a71  lea     rcx, [rdx+30h]
0x140021a78  jmp     ??1?$XPtrBase@VWUOptionalSessionInfo@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo>>(void)
```
