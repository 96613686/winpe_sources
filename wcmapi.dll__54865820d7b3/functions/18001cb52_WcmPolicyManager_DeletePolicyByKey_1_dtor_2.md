# _WcmPolicyManager::DeletePolicyByKey_::_1_::dtor$2

- ea: `0x18001cb52`
- end: `0x18001cb5e`
- name: `_WcmPolicyManager::DeletePolicyByKey_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180006b0c`

## pseudocode

```c
void __fastcall WcmPolicyManager::DeletePolicyByKey_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  WcmConnectionMappingPolicyKey::~WcmConnectionMappingPolicyKey((WcmConnectionMappingPolicyKey *)(a2 + 128));
}

```

## disassembly

```asm
0x18001cb52  lea     rcx, [rdx+80h]; this
0x18001cb59  jmp     ??1WcmConnectionMappingPolicyKey@@UEAA@XZ; WcmConnectionMappingPolicyKey::~WcmConnectionMappingPolicyKey(void)
```
