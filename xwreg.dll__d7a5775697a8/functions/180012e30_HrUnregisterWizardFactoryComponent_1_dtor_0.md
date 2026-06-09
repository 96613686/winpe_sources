# _HrUnregisterWizardFactoryComponent_::_1_::dtor$0

- ea: `0x180012e30`
- end: `0x180012e3c`
- name: `_HrUnregisterWizardFactoryComponent_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007a00`

## pseudocode

```c
LSTATUS __fastcall HrUnregisterWizardFactoryComponent_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(a2 + 56, a2);
}

```

## disassembly

```asm
0x180012e30  lea     rcx, [rdx+38h]
0x180012e37  jmp     ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
```
