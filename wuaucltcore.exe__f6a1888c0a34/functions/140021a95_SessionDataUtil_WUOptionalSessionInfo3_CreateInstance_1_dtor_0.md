# _SessionDataUtil::WUOptionalSessionInfo3::CreateInstance_::_1_::dtor$0

- ea: `0x140021a95`
- end: `0x140021aa1`
- name: `_SessionDataUtil::WUOptionalSessionInfo3::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013c24`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo3::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo3,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo3>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo3,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo3>>(a2 + 48);
}

```

## disassembly

```asm
0x140021a95  lea     rcx, [rdx+30h]
0x140021a9c  jmp     ??1?$XPtrBase@VWUOptionalSessionInfo3@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo3@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo3,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo3>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo3,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo3>>(void)
```
