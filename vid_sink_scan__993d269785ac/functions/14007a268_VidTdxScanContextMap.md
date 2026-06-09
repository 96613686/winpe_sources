# VidTdxScanContextMap

- ea: `0x14007a268`
- end: `0x14007a4a5`
- name: `VidTdxScanContextMap`
- size: `573`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14007fc98`

## callees

- `0x140021650`
- `0x140024c78`
- `0x14007a268`
- `0x140099e84`
- `0x1400ed530`
- `0x1400ed9b4`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14007a476`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007a476`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007a3b9`
- `ntoskrnl!PsGetCurrentProcess` at `0x14007a3b9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a35e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007a35e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a45e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a45e`
- `ntoskrnl!ExAllocatePool2` at `0x14007a2f4`
- `ntoskrnl!ExAllocatePool2` at `0x14007a2f4`

## pseudocode

```c
__int64 __fastcall VidTdxScanContextMap(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *v4; // r14
  unsigned __int64 v7; // rdi
  int v8; // eax
  _QWORD *Pool2; // rsi
  unsigned int v10; // edi
  int v11; // r8d
  __int64 i; // rdx
  void *CurrentProcess; // rax
  __int64 v16; // [rsp+48h] [rbp-41h]
  struct _MDL MemoryDescriptorList; // [rsp+58h] [rbp-31h] BYREF
  __int64 v19; // [rsp+88h] [rbp-1h]

  v19 = 0;
  v4 = 0;
  v16 = *(unsigned int *)(a2 + 16);
  memset(&MemoryDescriptorList, 0, sizeof(MemoryDescriptorList));
  v7 = (unsigned __int64)(v16 + 511) >> 9;
  if ( (unsigned int)v7 > 0x200 )
  {
    v8 = -1073741670;
    Pool2 = 0;
    v10 = -1073741670;
    v11 = 338;
    goto LABEL_13;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(256, 8LL * (unsigned int)v7, 1917084758);
  if ( !Pool2 )
  {
    v8 = -1073741670;
    v11 = 351;
    v10 = -1073741670;
    goto LABEL_13;
  }
  v19 = *(_QWORD *)(a2 + 24);
  MemoryDescriptorList.Next = 0;
  memset(&MemoryDescriptorList.MdlFlags + 1, 0, 28);
  *(_DWORD *)&MemoryDescriptorList.Size = 131128;
  *(_QWORD *)&MemoryDescriptorList.ByteCount = 4096;
  v4 = MmMapLockedPagesSpecifyCache(&MemoryDescriptorList, 0, MmNonCached, 0, 0, 0x40000010u);
  if ( !v4 )
  {
    v8 = -1073741670;
    v11 = 373;
    v10 = -1073741670;
    goto LABEL_13;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
    Pool2[i] = v4[i];
  v8 = VidClientBufferPrepareFromOverlayPages(a2 + 32, Pool2, v7);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 393;
    goto LABEL_13;
  }
  CurrentProcess = (void *)PsGetCurrentProcess();
  v8 = VidClientBufferShare(a2 + 32, 0, (_QWORD *)(a2 + 32), 1, CurrentProcess, (_QWORD *)(a2 + 104));
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 407;
LABEL_13:
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidTdxScanContextMap",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdx.c",
      v11,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      v8);
    VidClientBufferUnShare(a2 + 32, 0, a2 + 32);
    *(_QWORD *)(a2 + 104) = 0;
    if ( !Pool2 )
      goto LABEL_17;
    goto LABEL_16;
  }
  v10 = 0;
  *a3 = *(_QWORD *)(a2 + 104);
  *a4 = v16;
LABEL_16:
  ExFreePoolWithTag(Pool2, 0x72446456u);
LABEL_17:
  if ( v4 )
    MmUnmapLockedPages(v4, &MemoryDescriptorList);
  return v10;
}

```

## disassembly

```asm
0x14007a268  push    rbp
0x14007a26a  push    rbx
0x14007a26b  push    rsi
0x14007a26c  push    rdi
0x14007a26d  push    r12
0x14007a26f  push    r13
0x14007a271  push    r14
0x14007a273  push    r15
0x14007a275  lea     rbp, [rsp-1Fh]
0x14007a27a  sub     rsp, 0A8h
0x14007a281  mov     rax, cs:__security_cookie
0x14007a288  xor     rax, rsp
0x14007a28b  mov     [rbp+57h+var_50], rax
0x14007a28f  xor     eax, eax
0x14007a291  mov     [rbp+57h+var_90], r9
0x14007a295  xorps   xmm0, xmm0
0x14007a298  mov     [rbp+57h+var_58], rax
0x14007a29c  mov     eax, [rdx+10h]
0x14007a29f  xor     r14d, r14d
0x14007a2a2  mov     [rbp+57h+var_A0], r8
0x14007a2a6  mov     r13, rdx
0x14007a2a9  mov     rbx, rcx
0x14007a2ac  mov     [rbp+57h+var_98], rax
0x14007a2b0  movups  xmmword ptr [rbp+57h+MemoryDescriptorList.Next], xmm0
0x14007a2b4  lea     rdi, [rax+1FFh]
0x14007a2bb  shr     rdi, 9
0x14007a2bf  movups  xmmword ptr [rbp+57h+MemoryDescriptorList.Process], xmm0
0x14007a2c3  movups  xmmword ptr [rbp+57h+MemoryDescriptorList.StartVa], xmm0
0x14007a2c7  cmp     edi, 200h
0x14007a2cd  jbe     short loc_14007A2E3
0x14007a2cf  mov     eax, 0C000009Ah
0x14007a2d4  xor     esi, esi
0x14007a2d6  mov     edi, eax
0x14007a2d8  mov     r8d, 152h
0x14007a2de  jmp     loc_14007A3EE
0x14007a2e3  mov     edx, edi
0x14007a2e5  mov     ecx, 100h
0x14007a2ea  shl     rdx, 3
0x14007a2ee  mov     r8d, 72446456h
0x14007a2f4  call    cs:__imp_ExAllocatePool2
0x14007a2fb  nop     dword ptr [rax+rax+00h]
0x14007a300  mov     rsi, rax
0x14007a303  test    rax, rax
0x14007a306  jnz     short loc_14007A31A
0x14007a308  mov     eax, 0C000009Ah
0x14007a30d  mov     r8d, 15Fh
0x14007a313  mov     edi, eax
0x14007a315  jmp     loc_14007A3EE
0x14007a31a  mov     rax, [r13+18h]
0x14007a31e  lea     rcx, [rbp+57h+MemoryDescriptorList]; MemoryDescriptorList
0x14007a322  xorps   xmm0, xmm0
0x14007a325  mov     [rsp+0E0h+Priority], 40000010h; Priority
0x14007a32d  xor     r9d, r9d; RequestedAddress
0x14007a330  mov     [rbp+57h+var_58], rax
0x14007a334  xor     r8d, r8d; CacheType
0x14007a337  mov     dword ptr [rbp+57h+MemoryDescriptorList.MappedSystemVa+4], r14d
0x14007a33b  xor     edx, edx; AccessMode
0x14007a33d  mov     [rbp+57h+MemoryDescriptorList.Next], r14
0x14007a341  movdqu  xmmword ptr [rbp+57h+MemoryDescriptorList+0Ch], xmm0
0x14007a346  mov     dword ptr [rbp+57h+MemoryDescriptorList.Size], 20038h
0x14007a34d  mov     [rbp+57h+MemoryDescriptorList.StartVa], r14
0x14007a351  mov     qword ptr [rbp+57h+MemoryDescriptorList.ByteCount], 1000h
0x14007a359  mov     [rsp+0E0h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x14007a35e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007a365  nop     dword ptr [rax+rax+00h]
0x14007a36a  mov     r14, rax
0x14007a36d  test    rax, rax
0x14007a370  jnz     short loc_14007A381
0x14007a372  mov     eax, 0C000009Ah
0x14007a377  mov     r8d, 175h
0x14007a37d  mov     edi, eax
0x14007a37f  jmp     short loc_14007A3EE
0x14007a381  xor     edx, edx
0x14007a383  test    edi, edi
0x14007a385  jz      short loc_14007A395
0x14007a387  mov     rax, [r14+rdx*8]
0x14007a38b  mov     [rsi+rdx*8], rax
0x14007a38f  inc     edx
0x14007a391  cmp     edx, edi
0x14007a393  jb      short loc_14007A387
0x14007a395  lea     r15, [r13+20h]
0x14007a399  mov     r8d, edi
0x14007a39c  mov     rcx, r15
0x14007a39f  mov     rdx, rsi
0x14007a3a2  call    VidClientBufferPrepareFromOverlayPages
0x14007a3a7  mov     edi, eax
0x14007a3a9  test    eax, eax
0x14007a3ab  jns     short loc_14007A3B5
0x14007a3ad  mov     r8d, 189h
0x14007a3b3  jmp     short loc_14007A3EE
0x14007a3b5  lea     r12, [r13+68h]
0x14007a3b9  call    cs:__imp_PsGetCurrentProcess
0x14007a3c0  nop     dword ptr [rax+rax+00h]
0x14007a3c5  mov     r9d, 1; int
0x14007a3cb  mov     qword ptr [rsp+0E0h+Priority], r12; __int64
0x14007a3d0  mov     r8, r15; int
0x14007a3d3  mov     qword ptr [rsp+0E0h+BugCheckOnFailure], rax; Object
0x14007a3d8  xor     edx, edx; int
0x14007a3da  mov     rcx, r15; int
0x14007a3dd  call    VidClientBufferShare
0x14007a3e2  mov     edi, eax
0x14007a3e4  test    eax, eax
0x14007a3e6  jns     short loc_14007A43E
0x14007a3e8  mov     r8d, 197h
0x14007a3ee  mov     r11, [rbx+288h]
0x14007a3f5  lea     rdx, aOnecoreVmVidSy_49; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007a3fc  lea     r9, [rbx+290h]
0x14007a403  lea     r10, [rbx+78h]
0x14007a407  mov     [rsp+0E0h+var_B0], eax
0x14007a40b  lea     rcx, aVidtdxscancont_0; "VidTdxScanContextMap"
0x14007a412  mov     qword ptr [rsp+0E0h+Priority], r11
0x14007a417  mov     qword ptr [rsp+0E0h+BugCheckOnFailure], r10
0x14007a41c  call    VidTracePartitionErrorInternal0
0x14007a421  lea     rcx, [r13+20h]
0x14007a425  xor     edx, edx
0x14007a427  mov     r8, rcx
0x14007a42a  call    VidClientBufferUnShare
0x14007a42f  mov     qword ptr [r13+68h], 0
0x14007a437  test    rsi, rsi
0x14007a43a  jz      short loc_14007A46A
0x14007a43c  jmp     short loc_14007A456
0x14007a43e  mov     rax, [r12]
0x14007a442  xor     edi, edi
0x14007a444  mov     rcx, [rbp+57h+var_A0]
0x14007a448  mov     [rcx], rax
0x14007a44b  mov     rcx, [rbp+57h+var_90]
0x14007a44f  mov     rax, [rbp+57h+var_98]
0x14007a453  mov     [rcx], rax
0x14007a456  mov     edx, 72446456h; Tag
0x14007a45b  mov     rcx, rsi; P
0x14007a45e  call    cs:__imp_ExFreePoolWithTag
0x14007a465  nop     dword ptr [rax+rax+00h]
0x14007a46a  test    r14, r14
0x14007a46d  jz      short loc_14007A482
0x14007a46f  lea     rdx, [rbp+57h+MemoryDescriptorList]; MemoryDescriptorList
0x14007a473  mov     rcx, r14; BaseAddress
0x14007a476  call    cs:__imp_MmUnmapLockedPages
0x14007a47d  nop     dword ptr [rax+rax+00h]
0x14007a482  mov     eax, edi
0x14007a484  mov     rcx, [rbp+57h+var_50]
0x14007a488  xor     rcx, rsp; StackCookie
0x14007a48b  call    __security_check_cookie
0x14007a490  add     rsp, 0A8h
0x14007a497  pop     r15
0x14007a499  pop     r14
0x14007a49b  pop     r13
0x14007a49d  pop     r12
0x14007a49f  pop     rdi
0x14007a4a0  pop     rsi
0x14007a4a1  pop     rbx
0x14007a4a2  pop     rbp
0x14007a4a3  retn
```
