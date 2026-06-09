# _CRegistryEventRequest::_CRegistryEventRequest_::_1_::dtor$1

- ea: `0x1800163d8`
- end: `0x1800163eb`
- name: `_CRegistryEventRequest::_CRegistryEventRequest_::_1_::dtor$1`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000bb70`

## pseudocode

```c
void __fastcall CRegistryEventRequest::_CRegistryEventRequest_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  WString::~WString((WString *)(*(_QWORD *)(a2 + 48) + 128LL));
}

```

## disassembly

```asm
0x1800163d8  mov     rcx, [rdx+30h]
0x1800163df  add     rcx, 80h; this
0x1800163e6  jmp     ??1WString@@QEAA@XZ; WString::~WString(void)
```
