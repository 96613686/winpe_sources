# _CRegistryEventRequest::_CRegistryEventRequest_::_1_::dtor$2

- ea: `0x1800163f1`
- end: `0x180016404`
- name: `_CRegistryEventRequest::_CRegistryEventRequest_::_1_::dtor$2`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000bb70`

## pseudocode

```c
void __fastcall CRegistryEventRequest::_CRegistryEventRequest_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  WString::~WString((WString *)(*(_QWORD *)(a2 + 48) + 136LL));
}

```

## disassembly

```asm
0x1800163f1  mov     rcx, [rdx+30h]
0x1800163f8  add     rcx, 88h; this
0x1800163ff  jmp     ??1WString@@QEAA@XZ; WString::~WString(void)
```
