# CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)

- ea: `0x180007a00`
- end: `0x180007a2b`
- name: `??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
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
- `0x180012dd4`
- `0x180012e1e`
- `0x180012e30`
- `0x180012e42`
- `0x180012e54`

## callees

- `0x180007a00`
- `0x180007a5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a12`

## pseudocode

```c
LSTATUS __fastcall CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(
        __int64 a1,
        unsigned int a2)
{
  HKEY v3; // rcx
  LSTATUS result; // eax

  v3 = *(HKEY *)(a1 + 8);
  if ( v3 )
    result = RegCloseKey(v3);
  if ( *(_QWORD *)a1 )
    return (unsigned int)CRegistryLockedTransaction::`scalar deleting destructor'(
                           *(CRegistryLockedTransaction **)a1,
                           a2);
  return result;
}

```

## disassembly

```asm
0x180007a00  push    rbx
0x180007a02  sub     rsp, 20h
0x180007a06  mov     rbx, rcx
0x180007a09  mov     rcx, [rcx+8]; hKey
0x180007a0d  test    rcx, rcx
0x180007a10  jz      short loc_180007A18
0x180007a12  call    cs:__imp_RegCloseKey
0x180007a18  mov     rcx, [rbx]; this
0x180007a1b  test    rcx, rcx
0x180007a1e  jz      short loc_180007A25
0x180007a20  call    ??_GCRegistryLockedTransaction@@QEAAPEAXI@Z; CRegistryLockedTransaction::`scalar deleting destructor'(uint)
0x180007a25  add     rsp, 20h
0x180007a29  pop     rbx
0x180007a2a  retn
```
