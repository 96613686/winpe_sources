# UdfMapUserBuffer

- ea: `0x1400543e0`
- end: `0x14005444e`
- name: `UdfMapUserBuffer`
- size: `110`
- prototype: `PVOID __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010f0`
- `0x14000c728`
- `0x14000feb4`
- `0x140010f38`
- `0x14003f4c8`
- `0x140044f90`

## callees

- `0x1400543e0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005443b`
- `ntoskrnl!ExRaiseStatus` at `0x14005443b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005441e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14005441e`

## pseudocode

```c
PVOID __fastcall UdfMapUserBuffer(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  PVOID result; // rax

  v3 = *(_QWORD *)(a2 + 8);
  if ( !v3 )
    return *(PVOID *)(a2 + 112);
  if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    result = *(PVOID *)(v3 + 24);
  else
    result = MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000010u);
  if ( !result )
  {
    *(_DWORD *)(a1 + 24) = -1073741670;
    ExRaiseStatus(-1073741670);
  }
  return result;
}

```

## disassembly

```asm
0x1400543e0  push    rbx
0x1400543e2  sub     rsp, 30h
0x1400543e6  mov     rbx, rcx
0x1400543e9  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400543ed  test    rcx, rcx
0x1400543f0  jnz     short loc_1400543FD
0x1400543f2  mov     rax, [rdx+70h]
0x1400543f6  add     rsp, 30h
0x1400543fa  pop     rbx
0x1400543fb  retn
0x1400543fd  test    byte ptr [rcx+0Ah], 5
0x140054401  jnz     short loc_140054448
0x140054403  mov     [rsp+38h+Priority], 40000010h; Priority
0x14005440b  xor     r9d, r9d; RequestedAddress
0x14005440e  xor     edx, edx; AccessMode
0x140054410  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140054418  mov     r8d, 1; CacheType
0x14005441e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140054425  nop     dword ptr [rax+rax+00h]
0x14005442a  test    rax, rax
0x14005442d  jnz     short loc_1400543F6
0x14005442f  mov     ecx, 0C000009Ah; Status
0x140054434  mov     dword ptr [rbx+18h], 0C000009Ah
0x14005443b  call    cs:__imp_ExRaiseStatus
0x140054448  mov     rax, [rcx+18h]
0x14005444c  jmp     short loc_14005442A
```
