# _CRegistryValueEventRequest::_CRegistryValueEventRequest_::_1_::dtor$1

- ea: `0x180016d75`
- end: `0x180016d88`
- name: `_CRegistryValueEventRequest::_CRegistryValueEventRequest_::_1_::dtor$1`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000bb70`

## pseudocode

```c
void __fastcall CRegistryValueEventRequest::_CRegistryValueEventRequest_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  WString::~WString((WString *)(*(_QWORD *)(a2 + 48) + 224LL));
}

```

## disassembly

```asm
0x180016d75  mov     rcx, [rdx+30h]
0x180016d7c  add     rcx, 0E0h; this
0x180016d83  jmp     ??1WString@@QEAA@XZ; WString::~WString(void)
```
