# _CRegistryLockedTransaction::CRegistryLockedTransaction_::_1_::dtor$0

- ea: `0x180012e66`
- end: `0x180012e76`
- name: `_CRegistryLockedTransaction::CRegistryLockedTransaction_::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000d258`

## pseudocode

```c
void __fastcall CRegistryLockedTransaction::CRegistryLockedTransaction_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CRegistryTransaction::~CRegistryTransaction((const WCHAR *)(*(_QWORD *)(a2 + 64) + 8LL));
}

```

## disassembly

```asm
0x180012e66  mov     rcx, [rdx+40h]
0x180012e6d  add     rcx, 8; this
0x180012e71  jmp     ??1CRegistryTransaction@@QEAA@XZ; CRegistryTransaction::~CRegistryTransaction(void)
```
