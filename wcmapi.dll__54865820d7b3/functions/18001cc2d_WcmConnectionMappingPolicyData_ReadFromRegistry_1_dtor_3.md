# _WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::dtor$3

- ea: `0x18001cc2d`
- end: `0x18001cc39`
- name: `_WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001980c`

## pseudocode

```c
__int64 __fastcall WcmConnectionMappingPolicyData::ReadFromRegistry_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::shared_ptr<WcmConnectionSelectionByDeviceType>::~shared_ptr<WcmConnectionSelectionByDeviceType>(a2 + 48);
}

```

## disassembly

```asm
0x18001cc2d  lea     rcx, [rdx+30h]
0x18001cc34  jmp     ??1?$shared_ptr@VWcmConnectionSelectionByDeviceType@@@std@@QEAA@XZ; std::shared_ptr<WcmConnectionSelectionByDeviceType>::~shared_ptr<WcmConnectionSelectionByDeviceType>(void)
```
