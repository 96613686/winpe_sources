# _WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::dtor$1

- ea: `0x18001cbcc`
- end: `0x18001cbd8`
- name: `_WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800172e0`

## pseudocode

```c
void __fastcall WcmConnectionMappingPolicyData::WriteToRegistry_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 72));
}

```

## disassembly

```asm
0x18001cbcc  lea     rcx, [rdx+48h]; this
0x18001cbd3  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
