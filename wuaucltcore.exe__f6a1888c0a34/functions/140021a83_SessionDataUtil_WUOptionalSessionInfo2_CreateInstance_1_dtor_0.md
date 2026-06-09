# _SessionDataUtil::WUOptionalSessionInfo2::CreateInstance_::_1_::dtor$0

- ea: `0x140021a83`
- end: `0x140021a8f`
- name: `_SessionDataUtil::WUOptionalSessionInfo2::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013c68`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo2::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo2,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo2>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo2,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo2>>(a2 + 48);
}

```

## disassembly

```asm
0x140021a83  lea     rcx, [rdx+30h]
0x140021a8a  jmp     ??1?$XPtrBase@VWUOptionalSessionInfo2@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo2@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo2,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo2>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo2,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo2>>(void)
```
