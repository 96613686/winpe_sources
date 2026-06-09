# CPXWizardRegistryLockedTransaction<3>::HrRestore(void)

- ea: `0x180009994`
- end: `0x1800099ac`
- name: `?HrRestore@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800085ac`
- `0x180009ca0`
- `0x18000b114`
- `0x18000bac8`
- `0x18000c240`
- `0x18000c5c8`
- `0x18000ca6c`

## callees

- `0x180009994`
- `0x18000d68c`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistryLockedTransaction<3>::HrRestore(__int64 a1)
{
  __int64 result; // rax

  result = *(unsigned int *)(a1 + 16);
  if ( (int)result >= 0 )
    return CRegistryLockedTransaction::HrRestoreKey(*(CRegistryLockedTransaction **)a1);
  return result;
}

```

## disassembly

```asm
0x180009994  sub     rsp, 28h
0x180009998  mov     eax, [rcx+10h]
0x18000999b  test    eax, eax
0x18000999d  js      short loc_1800099A7
0x18000999f  mov     rcx, [rcx]; this
0x1800099a2  call    ?HrRestoreKey@CRegistryLockedTransaction@@QEAAJXZ; CRegistryLockedTransaction::HrRestoreKey(void)
0x1800099a7  add     rsp, 28h
0x1800099ab  retn
```
