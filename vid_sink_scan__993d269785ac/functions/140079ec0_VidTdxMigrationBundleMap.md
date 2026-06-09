# VidTdxMigrationBundleMap

- ea: `0x140079ec0`
- end: `0x14007a149`
- name: `VidTdxMigrationBundleMap`
- size: `649`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14007f888`

## callees

- `0x140021650`
- `0x140021800`
- `0x140021d40`
- `0x140024c78`
- `0x140079ec0`
- `0x140099e84`
- `0x1400ed530`
- `0x1400ed9b4`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14007a117`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007a117`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007a04e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007a04e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140079fe5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140079fe5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a0fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a0fe`
- `ntoskrnl!ExAllocatePool2` at `0x140079f50`
- `ntoskrnl!ExAllocatePool2` at `0x140079f50`

## pseudocode

```c
__int64 __fastcall VidTdxMigrationBundleMap(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v6; // r14
  _QWORD *v7; // r15
  unsigned __int64 v8; // rdi
  int v9; // eax
  int v10; // r8d
  unsigned int v11; // edi
  _QWORD *Pool2; // rsi
  unsigned int i; // edx
  __int64 v14; // rcx
  void *CurrentProcess; // rax
  _BYTE MemoryDescriptorList[304]; // [rsp+50h] [rbp-B0h] BYREF

  memset(MemoryDescriptorList, 0, sizeof(MemoryDescriptorList));
  v6 = *(unsigned int *)(a2 + 16);
  v7 = 0;
  v8 = (unsigned __int64)(v6 + 511) >> 9;
  if ( (unsigned int)v8 > 0x20 )
  {
    v9 = -1073741670;
    v10 = 85;
    v11 = -1073741670;
    Pool2 = 0;
    goto LABEL_15;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(256, 8 * v6, 1917084758);
  if ( !Pool2 )
  {
    v9 = -1073741670;
    v10 = 98;
    v11 = -1073741670;
    goto LABEL_15;
  }
  memset(&MemoryDescriptorList[12], 0, 28);
  *(_QWORD *)MemoryDescriptorList = 0;
  *(_WORD *)&MemoryDescriptorList[8] = 8 * (v8 + 6);
  *(_DWORD *)&MemoryDescriptorList[40] = (_DWORD)v8 << 12;
  *(_WORD *)&MemoryDescriptorList[10] = 2;
  *(_DWORD *)&MemoryDescriptorList[44] = 0;
  if ( (_DWORD)v8 )
    memmove(&MemoryDescriptorList[48], (const void *)(a2 + 24), 8LL * (unsigned int)v8);
  v7 = MmMapLockedPagesSpecifyCache((PMDL)MemoryDescriptorList, 0, MmNonCached, 0, 0, 0x40000010u);
  if ( !v7 )
  {
    v9 = -1073741670;
    v10 = 124;
    v11 = -1073741670;
    goto LABEL_15;
  }
  for ( i = 0; i < *(_DWORD *)(a2 + 16); Pool2[v14] = v7[v14] )
    v14 = i++;
  v9 = VidClientBufferPrepareFromOverlayPages(a2 + 280, Pool2, v6);
  v11 = v9;
  if ( v9 < 0 )
  {
    v10 = 144;
    goto LABEL_15;
  }
  CurrentProcess = (void *)PsGetCurrentProcess();
  v9 = VidClientBufferShare(a2 + 280, 0, (_QWORD *)(a2 + 280), 0, CurrentProcess, (_QWORD *)(a2 + 368));
  v11 = v9;
  if ( v9 < 0 )
  {
    v10 = 158;
LABEL_15:
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxMigrationBundleMap",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdx.c",
      v10,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      v9);
    VidClientBufferUnShare(a2 + 280, 0, a2 + 280);
    *(_QWORD *)(a2 + 368) = 0;
    if ( !Pool2 )
      goto LABEL_19;
    goto LABEL_18;
  }
  v11 = 0;
  *a3 = *(_QWORD *)(a2 + 368);
  *a4 = (unsigned int)((_DWORD)v6 << 12);
LABEL_18:
  ExFreePoolWithTag(Pool2, 0x72446456u);
LABEL_19:
  if ( v7 )
    MmUnmapLockedPages(v7, (PMDL)MemoryDescriptorList);
  return v11;
}

```

## disassembly

```asm
0x140079ec0  push    rbp
0x140079ec2  push    rbx
0x140079ec3  push    rsi
0x140079ec4  push    rdi
0x140079ec5  push    r12
0x140079ec7  push    r13
0x140079ec9  push    r14
0x140079ecb  push    r15
0x140079ecd  lea     rbp, [rsp-98h]
0x140079ed5  sub     rsp, 198h
0x140079edc  mov     rax, cs:__security_cookie
0x140079ee3  xor     rax, rsp
0x140079ee6  mov     [rbp+0D0h+var_50], rax
0x140079eed  mov     [rsp+1D0h+var_190], r8
0x140079ef2  mov     r13, rdx
0x140079ef5  mov     rbx, rcx
0x140079ef8  mov     [rsp+1D0h+var_188], r9
0x140079efd  xor     edx, edx; Val
0x140079eff  lea     rcx, [rsp+1D0h+MemoryDescriptorList]; void *
0x140079f04  mov     r8d, 130h; Size
0x140079f0a  call    memset
0x140079f0f  mov     r14d, [r13+10h]
0x140079f13  xor     r12d, r12d
0x140079f16  mov     r15d, r12d
0x140079f19  lea     rdi, [r14+1FFh]
0x140079f20  shr     rdi, 9
0x140079f24  cmp     edi, 20h ; ' '
0x140079f27  jbe     short loc_140079F3D
0x140079f29  mov     eax, 0C000009Ah
0x140079f2e  lea     r8d, [r12+55h]
0x140079f33  mov     edi, eax
0x140079f35  mov     esi, r12d
0x140079f38  jmp     loc_14007A083
0x140079f3d  lea     rdx, ds:0[r14*8]
0x140079f45  mov     ecx, 100h
0x140079f4a  mov     r8d, 72446456h
0x140079f50  call    cs:__imp_ExAllocatePool2
0x140079f57  nop     dword ptr [rax+rax+00h]
0x140079f5c  mov     rsi, rax
0x140079f5f  test    rax, rax
0x140079f62  jnz     short loc_140079F74
0x140079f64  mov     eax, 0C000009Ah
0x140079f69  lea     r8d, [rsi+62h]
0x140079f6d  mov     edi, eax
0x140079f6f  jmp     loc_14007A083
0x140079f74  mov     r8d, edi
0x140079f77  mov     qword ptr [rsp+1D0h+MemoryDescriptorList+0Ch], r12
0x140079f7c  mov     [rsp+1D0h+MemoryDescriptorList.Process+4], r12
0x140079f81  mov     dword ptr [rsp+1D0h+MemoryDescriptorList.MappedSystemVa+4], r12d
0x140079f86  lea     eax, [r8+6]
0x140079f8a  mov     [rsp+1D0h+MemoryDescriptorList.Next], r12
0x140079f8f  shl     ax, 3
0x140079f93  mov     [rsp+1D0h+MemoryDescriptorList.Size], ax
0x140079f98  mov     eax, edi
0x140079f9a  shl     rax, 0Ch
0x140079f9e  mov     [rsp+1D0h+MemoryDescriptorList.ByteCount], eax
0x140079fa2  mov     eax, 2
0x140079fa7  mov     [rsp+1D0h+MemoryDescriptorList.MdlFlags], ax
0x140079fac  mov     [rsp+1D0h+MemoryDescriptorList.StartVa], r12
0x140079fb1  mov     [rsp+1D0h+MemoryDescriptorList.ByteOffset], r12d
0x140079fb6  test    edi, edi
0x140079fb8  jz      short loc_140079FCB
0x140079fba  shl     r8, 3; Size
0x140079fbe  lea     rdx, [r13+18h]; Src
0x140079fc2  lea     rcx, [rbp+0D0h+var_150]; void *
0x140079fc6  call    memmove
0x140079fcb  mov     [rsp+1D0h+Priority], 40000010h; Priority
0x140079fd3  lea     rcx, [rsp+1D0h+MemoryDescriptorList]; MemoryDescriptorList
0x140079fd8  xor     r9d, r9d; RequestedAddress
0x140079fdb  mov     [rsp+1D0h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140079fe0  xor     r8d, r8d; CacheType
0x140079fe3  xor     edx, edx; AccessMode
0x140079fe5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140079fec  nop     dword ptr [rax+rax+00h]
0x140079ff1  mov     r15, rax
0x140079ff4  test    rax, rax
0x140079ff7  jnz     short loc_14007A006
0x140079ff9  mov     eax, 0C000009Ah
0x140079ffe  lea     r8d, [r15+7Ch]
0x14007a002  mov     edi, eax
0x14007a004  jmp     short loc_14007A083
0x14007a006  mov     edx, r12d
0x14007a009  cmp     [r13+10h], r12d
0x14007a00d  jbe     short loc_14007A021
0x14007a00f  mov     ecx, edx
0x14007a011  inc     edx
0x14007a013  mov     rax, [r15+rcx*8]
0x14007a017  mov     [rsi+rcx*8], rax
0x14007a01b  cmp     edx, [r13+10h]
0x14007a01f  jb      short loc_14007A00F
0x14007a021  lea     r12, [r13+118h]
0x14007a028  mov     r8d, r14d
0x14007a02b  mov     rcx, r12
0x14007a02e  mov     rdx, rsi
0x14007a031  call    VidClientBufferPrepareFromOverlayPages
0x14007a036  mov     edi, eax
0x14007a038  test    eax, eax
0x14007a03a  jns     short loc_14007A047
0x14007a03c  mov     r8d, 90h
0x14007a042  xor     r12d, r12d
0x14007a045  jmp     short loc_14007A083
0x14007a047  lea     rdi, [r13+170h]
0x14007a04e  call    cs:__imp_PsGetCurrentProcess
0x14007a055  nop     dword ptr [rax+rax+00h]
0x14007a05a  xor     r9d, r9d; int
0x14007a05d  mov     qword ptr [rsp+1D0h+Priority], rdi; __int64
0x14007a062  mov     r8, r12; int
0x14007a065  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], rax; Object
0x14007a06a  xor     edx, edx; int
0x14007a06c  mov     rcx, r12; int
0x14007a06f  call    VidClientBufferShare
0x14007a074  xor     r12d, r12d
0x14007a077  mov     edi, eax
0x14007a079  test    eax, eax
0x14007a07b  jns     short loc_14007A0D5
0x14007a07d  mov     r8d, 9Eh
0x14007a083  mov     r11, [rbx+288h]
0x14007a08a  lea     rdx, aOnecoreVmVidSy_49; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007a091  lea     r9, [rbx+290h]
0x14007a098  lea     r10, [rbx+78h]
0x14007a09c  mov     [rsp+1D0h+var_1A0], eax
0x14007a0a0  lea     rcx, aVidtdxmigratio_0; "VidTdxMigrationBundleMap"
0x14007a0a7  mov     qword ptr [rsp+1D0h+Priority], r11
0x14007a0ac  mov     qword ptr [rsp+1D0h+BugCheckOnFailure], r10
0x14007a0b1  call    VidTracePartitionErrorInternal0
0x14007a0b6  lea     rcx, [r13+118h]
0x14007a0bd  xor     edx, edx
0x14007a0bf  mov     r8, rcx
0x14007a0c2  call    VidClientBufferUnShare
0x14007a0c7  mov     [r13+170h], r12
0x14007a0ce  test    rsi, rsi
0x14007a0d1  jz      short loc_14007A10A
0x14007a0d3  jmp     short loc_14007A0F6
0x14007a0d5  mov     rax, [r13+170h]
0x14007a0dc  mov     edi, r12d
0x14007a0df  mov     rcx, [rsp+1D0h+var_190]
0x14007a0e4  shl     r14d, 0Ch
0x14007a0e8  mov     [rcx], rax
0x14007a0eb  mov     rcx, [rsp+1D0h+var_188]
0x14007a0f0  mov     eax, r14d
0x14007a0f3  mov     [rcx], rax
0x14007a0f6  mov     edx, 72446456h; Tag
0x14007a0fb  mov     rcx, rsi; P
0x14007a0fe  call    cs:__imp_ExFreePoolWithTag
0x14007a105  nop     dword ptr [rax+rax+00h]
0x14007a10a  test    r15, r15
0x14007a10d  jz      short loc_14007A123
0x14007a10f  lea     rdx, [rsp+1D0h+MemoryDescriptorList]; MemoryDescriptorList
0x14007a114  mov     rcx, r15; BaseAddress
0x14007a117  call    cs:__imp_MmUnmapLockedPages
0x14007a11e  nop     dword ptr [rax+rax+00h]
0x14007a123  mov     eax, edi
0x14007a125  mov     rcx, [rbp+0D0h+var_50]
0x14007a12c  xor     rcx, rsp; StackCookie
0x14007a12f  call    __security_check_cookie
0x14007a134  add     rsp, 198h
0x14007a13b  pop     r15
0x14007a13d  pop     r14
0x14007a13f  pop     r13
0x14007a141  pop     r12
0x14007a143  pop     rdi
0x14007a144  pop     rsi
0x14007a145  pop     rbx
0x14007a146  pop     rbp
0x14007a147  retn
```
