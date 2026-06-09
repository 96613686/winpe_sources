# _SessionDataUtil::WUOptionalSessionInfo6::CreateInstance_::_1_::dtor$0

- ea: `0x140021acb`
- end: `0x140021ad7`
- name: `_SessionDataUtil::WUOptionalSessionInfo6::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013b78`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo6::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo6,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo6>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo6,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo6>>(a2 + 48);
}

```

## disassembly

```asm
0x140021acb  lea     rcx, [rdx+30h]
0x140021ad2  jmp     ??1?$XPtrBase@VWUOptionalSessionInfo6@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo6@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo6,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo6>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo6,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo6>>(void)
```
