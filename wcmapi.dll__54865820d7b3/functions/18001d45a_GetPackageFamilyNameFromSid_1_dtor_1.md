# _GetPackageFamilyNameFromSid_::_1_::dtor$1

- ea: `0x18001d45a`
- end: `0x18001d466`
- name: `_GetPackageFamilyNameFromSid_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1800172d4`

## pseudocode

```c
__int64 __fastcall GetPackageFamilyNameFromSid_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 72);
}

```

## disassembly

```asm
0x18001d45a  lea     rcx, [rdx+48h]
0x18001d461  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
