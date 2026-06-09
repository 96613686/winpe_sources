# _JsonUtil::GetStringPropertyWithDefault_::_1_::dtor$0

- ea: `0x140021b13`
- end: `0x140021b1f`
- name: `_JsonUtil::GetStringPropertyWithDefault_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140018368`

## pseudocode

```c
void __fastcall JsonUtil::GetStringPropertyWithDefault_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 72));
}

```

## disassembly

```asm
0x140021b13  lea     rcx, [rdx+48h]; this
0x140021b1a  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
