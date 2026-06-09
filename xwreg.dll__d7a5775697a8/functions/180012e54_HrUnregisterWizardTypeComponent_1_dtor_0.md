# _HrUnregisterWizardTypeComponent_::_1_::dtor$0

- ea: `0x180012e54`
- end: `0x180012e60`
- name: `_HrUnregisterWizardTypeComponent_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007a00`

## pseudocode

```c
LSTATUS __fastcall HrUnregisterWizardTypeComponent_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(a2 + 64, a2);
}

```

## disassembly

```asm
0x180012e54  lea     rcx, [rdx+40h]
0x180012e5b  jmp     ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
```
