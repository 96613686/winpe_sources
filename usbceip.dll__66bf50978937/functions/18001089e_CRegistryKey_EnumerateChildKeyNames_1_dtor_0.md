# _CRegistryKey::EnumerateChildKeyNames_::_1_::dtor$0

- ea: `0x18001089e`
- end: `0x1800108aa`
- name: `_CRegistryKey::EnumerateChildKeyNames_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003cb8`

## pseudocode

```c
void __fastcall CRegistryKey::EnumerateChildKeyNames_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t((_bstr_t *)(a2 + 80));
}

```

## disassembly

```asm
0x18001089e  lea     rcx, [rdx+50h]; this
0x1800108a5  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
