# DloadAcquireSectionWriteAccess

- ea: `0x1800157f8`
- end: `0x180015856`
- name: `DloadAcquireSectionWriteAccess`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015ba0`

## callees

- `0x1800157f8`
- `0x1800159c8`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015844`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015844`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001580f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001580f`

## pseudocode

```c
void DloadAcquireSectionWriteAccess()
{
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
}

```

## disassembly

```asm
0x1800157f8  sub     rsp, 28h
0x1800157fc  test    cs:dword_180018B30, 1000h
0x180015806  jz      short loc_180015850
0x180015808  lea     rcx, DloadSrwLock; SRWLock
0x18001580f  call    cs:__imp_AcquireSRWLockExclusive
0x180015816  nop     dword ptr [rax+rax+00h]
0x18001581b  mov     eax, cs:DloadSectionLockCount
0x180015821  inc     eax
0x180015823  mov     cs:DloadSectionLockCount, eax
0x180015829  cmp     eax, 1
0x18001582c  jnz     short loc_18001583D
0x18001582e  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180015835  lea     ecx, [rax+3]; flNewProtect
0x180015838  call    DloadProtectSection
0x18001583d  lea     rcx, DloadSrwLock; SRWLock
0x180015844  call    cs:__imp_ReleaseSRWLockExclusive
0x18001584b  nop     dword ptr [rax+rax+00h]
0x180015850  add     rsp, 28h
0x180015854  retn
```
