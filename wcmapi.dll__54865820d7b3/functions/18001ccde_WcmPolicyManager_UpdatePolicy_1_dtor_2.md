# _WcmPolicyManager::UpdatePolicy_::_1_::dtor$2

- ea: `0x18001ccde`
- end: `0x18001ccea`
- name: `_WcmPolicyManager::UpdatePolicy_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x1800172d4`

## pseudocode

```c
__int64 __fastcall WcmPolicyManager::UpdatePolicy_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 144);
}

```

## disassembly

```asm
0x18001ccde  lea     rcx, [rdx+90h]
0x18001cce5  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
