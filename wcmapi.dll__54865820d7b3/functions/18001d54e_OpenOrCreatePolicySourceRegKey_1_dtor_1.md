# _OpenOrCreatePolicySourceRegKey_::_1_::dtor$1

- ea: `0x18001d54e`
- end: `0x18001d55a`
- name: `_OpenOrCreatePolicySourceRegKey_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800172d4`

## pseudocode

```c
__int64 __fastcall OpenOrCreatePolicySourceRegKey_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 128);
}

```

## disassembly

```asm
0x18001d54e  lea     rcx, [rdx+80h]
0x18001d555  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
