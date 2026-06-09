# CPXWizardRegistryLockedTransaction<3>::HrBackup(ulong)

- ea: `0x180007a84`
- end: `0x180007aa0`
- name: `?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z`
- size: `28`
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

- `0x180007a84`
- `0x18000d294`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistryLockedTransaction<3>::HrBackup(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax

  result = *(unsigned int *)(a1 + 16);
  if ( (int)result >= 0 )
    return CRegistryLockedTransaction::HrBackupKey(*(CRegistryLockedTransaction **)a1, *(HKEY *)(a1 + 8), a3);
  return result;
}

```

## disassembly

```asm
0x180007a84  sub     rsp, 28h
0x180007a88  mov     eax, [rcx+10h]
0x180007a8b  test    eax, eax
0x180007a8d  js      short loc_180007A9B
0x180007a8f  mov     rdx, [rcx+8]; HKEY
0x180007a93  mov     rcx, [rcx]; this
0x180007a96  call    ?HrBackupKey@CRegistryLockedTransaction@@QEAAJQEAUHKEY__@@K@Z; CRegistryLockedTransaction::HrBackupKey(HKEY__ * const,ulong)
0x180007a9b  add     rsp, 28h
0x180007a9f  retn
```
