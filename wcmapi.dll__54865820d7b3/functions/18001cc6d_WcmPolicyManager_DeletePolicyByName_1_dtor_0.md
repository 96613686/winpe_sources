# _WcmPolicyManager::DeletePolicyByName_::_1_::dtor$0

- ea: `0x18001cc6d`
- end: `0x18001cc79`
- name: `_WcmPolicyManager::DeletePolicyByName_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800172e0`

## pseudocode

```c
void __fastcall WcmPolicyManager::DeletePolicyByName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 56));
}

```

## disassembly

```asm
0x18001cc6d  lea     rcx, [rdx+38h]; this
0x18001cc74  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
