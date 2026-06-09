# _CRegistryTreeEventRequest::_scalar_deleting_destructor__::_1_::dtor$0

- ea: `0x18001650a`
- end: `0x180016516`
- name: `_CRegistryTreeEventRequest::_scalar_deleting_destructor__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b5ac`

## pseudocode

```c
void __fastcall CRegistryTreeEventRequest::_scalar_deleting_destructor__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CRegistryEventRequest::~CRegistryEventRequest(*(CRegistryEventRequest **)(a2 + 48));
}

```

## disassembly

```asm
0x18001650a  mov     rcx, [rdx+30h]; this
0x180016511  jmp     ??1CRegistryEventRequest@@UEAA@XZ; CRegistryEventRequest::~CRegistryEventRequest(void)
```
