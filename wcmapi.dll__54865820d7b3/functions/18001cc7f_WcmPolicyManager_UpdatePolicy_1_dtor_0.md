# _WcmPolicyManager::UpdatePolicy_::_1_::dtor$0

- ea: `0x18001cc7f`
- end: `0x18001cc8b`
- name: `_WcmPolicyManager::UpdatePolicy_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800172e0`

## pseudocode

```c
void __fastcall WcmPolicyManager::UpdatePolicy_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 80));
}

```

## disassembly

```asm
0x18001cc7f  lea     rcx, [rdx+50h]; this
0x18001cc86  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
