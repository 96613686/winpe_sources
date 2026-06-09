# DloadReleaseSectionWriteAccess

- ea: `0x180015a6c`
- end: `0x180015ac6`
- name: `DloadReleaseSectionWriteAccess`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015ba0`

## callees

- `0x1800159c8`
- `0x180015a6c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015ab4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015ab4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180015a88`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180015a88`

## pseudocode

```c
void DloadReleaseSectionWriteAccess()
{
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  flOldProtect = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
  ReleaseSRWLockExclusive(&DloadSrwLock);
}

```

## disassembly

```asm
0x180015a6c  sub     rsp, 28h
0x180015a70  and     [rsp+28h+flOldProtect], 0
0x180015a75  test    cs:dword_180018B30, 1000h
0x180015a7f  jz      short loc_180015AC0
0x180015a81  lea     rcx, DloadSrwLock; SRWLock
0x180015a88  call    cs:__imp_AcquireSRWLockExclusive
0x180015a8f  nop     dword ptr [rax+rax+00h]
0x180015a94  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180015a9b  jnz     short loc_180015AAD
0x180015a9d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180015aa3  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x180015aa8  call    DloadProtectSection
0x180015aad  lea     rcx, DloadSrwLock; SRWLock
0x180015ab4  call    cs:__imp_ReleaseSRWLockExclusive
0x180015abb  nop     dword ptr [rax+rax+00h]
0x180015ac0  add     rsp, 28h
0x180015ac4  retn
```
