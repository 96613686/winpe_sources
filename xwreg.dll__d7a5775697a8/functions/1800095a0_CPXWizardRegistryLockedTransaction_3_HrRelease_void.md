# CPXWizardRegistryLockedTransaction<3>::HrRelease(void)

- ea: `0x1800095a0`
- end: `0x1800095b8`
- name: `?HrRelease@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ`
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

- `0x1800095a0`
- `0x18000d548`

## pseudocode

```c
__int64 __fastcall CPXWizardRegistryLockedTransaction<3>::HrRelease(__int64 a1)
{
  __int64 result; // rax

  result = *(unsigned int *)(a1 + 16);
  if ( (int)result >= 0 )
    return CRegistryLockedTransaction::HrReleaseKey(*(CRegistryLockedTransaction **)a1);
  return result;
}

```

## disassembly

```asm
0x1800095a0  sub     rsp, 28h
0x1800095a4  mov     eax, [rcx+10h]
0x1800095a7  test    eax, eax
0x1800095a9  js      short loc_1800095B3
0x1800095ab  mov     rcx, [rcx]; this
0x1800095ae  call    ?HrReleaseKey@CRegistryLockedTransaction@@QEAAJXZ; CRegistryLockedTransaction::HrReleaseKey(void)
0x1800095b3  add     rsp, 28h
0x1800095b7  retn
```
