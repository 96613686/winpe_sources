# _WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::dtor$0

- ea: `0x18001cbba`
- end: `0x18001cbc6`
- name: `_WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800172d4`

## pseudocode

```c
__int64 __fastcall WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 96);
}

```

## disassembly

```asm
0x18001cbba  lea     rcx, [rdx+60h]
0x18001cbc1  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
