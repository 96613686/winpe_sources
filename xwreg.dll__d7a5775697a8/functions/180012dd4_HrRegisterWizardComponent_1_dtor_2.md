# _HrRegisterWizardComponent_::_1_::dtor$2

- ea: `0x180012dd4`
- end: `0x180012de0`
- name: `_HrRegisterWizardComponent_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007a00`

## pseudocode

```c
LSTATUS __fastcall HrRegisterWizardComponent_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(a2 + 176, a2);
}

```

## disassembly

```asm
0x180012dd4  lea     rcx, [rdx+0B0h]
0x180012ddb  jmp     ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
```
