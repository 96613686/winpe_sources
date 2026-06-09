# _HrUnregisterWizardComponent_::_1_::dtor$2

- ea: `0x180012e1e`
- end: `0x180012e2a`
- name: `_HrUnregisterWizardComponent_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007a00`

## pseudocode

```c
LSTATUS __fastcall HrUnregisterWizardComponent_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(a2 + 72, a2);
}

```

## disassembly

```asm
0x180012e1e  lea     rcx, [rdx+48h]
0x180012e25  jmp     ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
```
