# _SessionDataUtil::WUOptionalSessionInfo5::CreateInstance_::_1_::dtor$0

- ea: `0x140021ab9`
- end: `0x140021ac5`
- name: `_SessionDataUtil::WUOptionalSessionInfo5::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013bbc`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo5::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo5,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo5>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo5,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo5>>(a2 + 48);
}

```

## disassembly

```asm
0x140021ab9  lea     rcx, [rdx+30h]
0x140021ac0  jmp     ??1?$XPtrBase@VWUOptionalSessionInfo5@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo5@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo5,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo5>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo5,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo5>>(void)
```
