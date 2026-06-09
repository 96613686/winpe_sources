# _CreateTenantGatewayEntryStruct_::_1_::dtor$1

- ea: `0x18001d920`
- end: `0x18001d92c`
- name: `_CreateTenantGatewayEntryStruct_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010914`

## pseudocode

```c
__int64 __fastcall CreateTenantGatewayEntryStruct_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18001d920  mov     rcx, [rdx+30h]
0x18001d927  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
