# _WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::dtor$2

- ea: `0x18001cc1b`
- end: `0x18001cc27`
- name: `_WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800172e0`

## pseudocode

```c
void __fastcall WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 160));
}

```

## disassembly

```asm
0x18001cc1b  lea     rcx, [rdx+0A0h]; this
0x18001cc22  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
