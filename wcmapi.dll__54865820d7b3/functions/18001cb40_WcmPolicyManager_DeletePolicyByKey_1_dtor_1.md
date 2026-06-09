# _WcmPolicyManager::DeletePolicyByKey_::_1_::dtor$1

- ea: `0x18001cb40`
- end: `0x18001cb4c`
- name: `_WcmPolicyManager::DeletePolicyByKey_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800172e0`

## pseudocode

```c
void __fastcall WcmPolicyManager::DeletePolicyByKey_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 88));
}

```

## disassembly

```asm
0x18001cb40  lea     rcx, [rdx+58h]; this
0x18001cb47  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
