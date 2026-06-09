# _OpenOrCreatePolicySourceRegKey_::_1_::dtor$0

- ea: `0x18001cb2e`
- end: `0x18001cb3a`
- name: `_OpenOrCreatePolicySourceRegKey_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800172e0`

## pseudocode

```c
void __fastcall OpenOrCreatePolicySourceRegKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)(a2 + 64));
}

```

## disassembly

```asm
0x18001cb2e  lea     rcx, [rdx+40h]; this
0x18001cb35  jmp     ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
```
