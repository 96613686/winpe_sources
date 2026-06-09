# _WcmPolicyManager::UpdatePolicy_::_1_::dtor$1

- ea: `0x18001cccc`
- end: `0x18001ccd8`
- name: `_WcmPolicyManager::UpdatePolicy_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800172e0`

## pseudocode

```c
void __fastcall WcmPolicyManager::UpdatePolicy_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 104));
}

```

## disassembly

```asm
0x18001cccc  lea     rcx, [rdx+68h]; this
0x18001ccd3  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
