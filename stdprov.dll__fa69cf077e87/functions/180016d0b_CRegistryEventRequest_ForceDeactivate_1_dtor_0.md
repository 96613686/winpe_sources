# _CRegistryEventRequest::ForceDeactivate_::_1_::dtor$0

- ea: `0x180016d0b`
- end: `0x180016d17`
- name: `_CRegistryEventRequest::ForceDeactivate_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b2d4`

## pseudocode

```c
void __fastcall CRegistryEventRequest::ForceDeactivate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CInCritSec::~CInCritSec((LPCRITICAL_SECTION *)(a2 + 48));
}

```

## disassembly

```asm
0x180016d0b  lea     rcx, [rdx+30h]; this
0x180016d12  jmp     ??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
```
