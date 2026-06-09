# _SessionDataUtil::WUOptionalSessionInfo4::CreateInstance_::_1_::dtor$0

- ea: `0x140021aa7`
- end: `0x140021ab3`
- name: `_SessionDataUtil::WUOptionalSessionInfo4::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140013c18`

## pseudocode

```c
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo4::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>(a2 + 48);
}

```

## disassembly

```asm
0x140021aa7  lea     rcx, [rdx+30h]
0x140021aae  jmp     ??1?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAA@XZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::~XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>(void)
```
