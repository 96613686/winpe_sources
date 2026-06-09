# VmxpRaid5ReconstructStripePhase1(VMX_TRANSFER_PACKET *)

- ea: `0x140014fc0`
- end: `0x1400152f5`
- name: `?VmxpRaid5ReconstructStripePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `821`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010ac4`

## callees

- `0x140002470`
- `0x14000b420`
- `0x140014fc0`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015247`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015247`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015234`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015287`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400152a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015234`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015287`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400152a2`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400151f9`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400151f9`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015133`
- `ntoskrnl!KeInitializeSpinLock` at `0x140015133`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140015222`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140015222`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400151a9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400151a9`

## pseudocode

```c
void __fastcall VmxpRaid5ReconstructStripePhase1(struct VMX_TRANSFER_PACKET *a1)
{
  char *v1; // r14
  __int64 v2; // r15
  __int64 v4; // rdi
  _BYTE *v5; // rax
  _BYTE *v6; // rbx
  char **v7; // rcx
  char *v8; // rax
  __int64 v9; // rcx
  char v10; // bl
  __int64 v11; // r10
  PVOID v12; // rax
  KIRQL v13; // di
  PVOID v14; // rbx
  KSPIN_LOCK *v15; // rbx
  KIRQL v16; // al
  __int64 v17; // r15
  char **v18; // rcx
  char *v19; // rbx
  char *v20; // rdx
  __int64 v21; // rcx

  v1 = (char *)a1 + 112;
  v2 = *((_QWORD *)a1 + 29);
  *((_QWORD *)a1 + 5) = *((_QWORD *)a1 + 31);
  v4 = 0;
  *((_QWORD *)a1 + 15) = (char *)a1 + 112;
  *((_QWORD *)a1 + 14) = (char *)a1 + 112;
  while ( 1 )
  {
    if ( (unsigned int)v4 >= *(_DWORD *)(v2 + 56) )
      goto LABEL_17;
    if ( (_DWORD)v4 != *((_DWORD *)a1 + 60) )
      break;
LABEL_8:
    v4 = (unsigned int)(v4 + 1);
  }
  v5 = VMX_TRANSFER_PACKET::operator new(0xA8u);
  v6 = v5;
  if ( !v5 )
    goto LABEL_10;
  *((_QWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 3) = 0;
  v5[83] = 0;
  *((_WORD *)v5 + 66) = 0;
  *(_QWORD *)v5 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
  if ( (int)VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v5, *((_DWORD *)a1 + 2)) >= 0 )
  {
    *((_DWORD *)v6 + 2) = *((_DWORD *)a1 + 2);
    *((_QWORD *)v6 + 2) = *((_QWORD *)a1 + 2);
    *((_QWORD *)v6 + 5) = VmxpRaid5ParallelReconstructStripeCompletionRoutine;
    *((_QWORD *)v6 + 6) = *(_QWORD *)(*(_QWORD *)(v2 + 48) + 8 * v4);
    *((_QWORD *)v6 + 7) = *((_QWORD *)a1 + 7);
    *((_DWORD *)v6 + 16) = *((_DWORD *)a1 + 16);
    *((_QWORD *)v6 + 9) = *((_QWORD *)a1 + 9);
    v6[81] = *((_BYTE *)a1 + 81);
    v6[82] = 1;
    *((_QWORD *)v6 + 17) = a1;
    *((_DWORD *)v6 + 36) = v4;
    v7 = (char **)*((_QWORD *)v1 + 1);
    if ( *v7 != v1 )
      goto LABEL_27;
    *((_QWORD *)v6 + 19) = v1;
    *((_QWORD *)v6 + 20) = v7;
    *v7 = v6 + 152;
    *((_QWORD *)v1 + 1) = v6 + 152;
    goto LABEL_8;
  }
  (**(void (__fastcall ***)(_BYTE *, __int64))v6)(v6, 1);
LABEL_10:
  if ( (unsigned int)v4 >= *(_DWORD *)(v2 + 56) )
  {
LABEL_17:
    v10 = 0;
    goto LABEL_18;
  }
  while ( 1 )
  {
    v8 = *(char **)v1;
    if ( *(char **)v1 == v1 )
      break;
    if ( *((char **)v8 + 1) != v1 )
      goto LABEL_27;
    v9 = *(_QWORD *)v8;
    if ( *(char **)(*(_QWORD *)v8 + 8LL) != v8 )
      goto LABEL_27;
    *(_QWORD *)v1 = v9;
    *(_QWORD *)(v9 + 8) = v1;
    if ( v8 != (char *)152 )
      (**((void (__fastcall ***)(_QWORD *, __int64))v8 - 19))((_QWORD *)v8 - 19, 1);
  }
  v10 = 1;
LABEL_18:
  KeInitializeSpinLock((PKSPIN_LOCK)a1 + 11);
  *((_DWORD *)a1 + 24) = 0;
  *((_QWORD *)a1 + 13) = 0;
  *((_DWORD *)a1 + 32) = *(_DWORD *)(v2 + 56) - 1;
  if ( v10 )
  {
    v11 = *((_QWORD *)a1 + 3);
    *((_QWORD *)a1 + 5) = VmxpRaid5SequentialReconstructStripeEmergencyCompletionRoutine;
    if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
      v12 = *(PVOID *)(v11 + 24);
    else
      v12 = MmMapLockedPagesSpecifyCache(
              (PMDL)v11,
              0,
              MmCached,
              0,
              0,
              ((*((_DWORD *)a1 + 16) & 2) != 0 ? 32 : 16) | 0x40000000u);
    if ( v12 )
    {
      memset(v12, 0, *((unsigned int *)a1 + 2));
    }
    else
    {
      v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 352));
      v14 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v2 + 344), 0x6D526D56u, *((PMDL *)a1 + 3), MmCached);
      memset(v14, 0, *((unsigned int *)a1 + 2));
      MmUnmapReservedMapping(v14, 0x6D526D56u, *((PMDL *)a1 + 3));
      KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 352), v13);
    }
    v15 = (KSPIN_LOCK *)(v2 + 24);
    v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 24));
    if ( *(_BYTE *)(v2 + 266) )
    {
      v17 = v2 + 304;
      v18 = *(char ***)(v17 + 8);
      if ( *v18 != (char *)v17 )
LABEL_27:
        __fastfail(3u);
      *((_QWORD *)v1 + 1) = v18;
      *(_QWORD *)v1 = v17;
      *v18 = v1;
      *(_QWORD *)(v17 + 8) = v1;
      KeReleaseSpinLock(v15, v16);
    }
    else
    {
      *(_BYTE *)(v2 + 266) = 1;
      KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v16);
      (*((void (__fastcall **)(struct VMX_TRANSFER_PACKET *))a1 + 5))(a1);
    }
  }
  else
  {
    v19 = *(char **)v1;
    while ( v19 != v1 )
    {
      v20 = v19 - 152;
      v19 = *(char **)v19;
      v21 = *((_QWORD *)v20 + 6);
      *((_DWORD *)v20 + 3) = 33619970;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
}

```

## disassembly

```asm
0x140014fc0  push    rbx
0x140014fc2  push    rbp
0x140014fc3  push    rsi
0x140014fc4  push    rdi
0x140014fc5  push    r14
0x140014fc7  push    r15
0x140014fc9  sub     rsp, 38h
0x140014fcd  mov     rax, [rcx+0F8h]
0x140014fd4  lea     r14, [rcx+70h]
0x140014fd8  mov     r15, [rcx+0E8h]
0x140014fdf  mov     rbp, rcx
0x140014fe2  mov     [rcx+28h], rax
0x140014fe6  xor     edi, edi
0x140014fe8  mov     [r14+8], r14
0x140014fec  mov     [r14], r14
0x140014fef  cmp     edi, [r15+38h]
0x140014ff3  jnb     loc_14001512D
0x140014ff9  cmp     edi, [rbp+0F0h]
0x140014fff  jz      loc_1400150C5
0x140015005  mov     ecx, 0A8h; unsigned __int64
0x14001500a  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x14001500f  mov     rbx, rax
0x140015012  test    rax, rax
0x140015015  jz      loc_1400150DF
0x14001501b  mov     qword ptr [rax+20h], 0
0x140015023  mov     rcx, rbx; this
0x140015026  mov     qword ptr [rax+18h], 0
0x14001502e  mov     byte ptr [rax+53h], 0
0x140015032  mov     word ptr [rax+84h], 0
0x14001503b  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x140015042  mov     [rbx], rax
0x140015045  mov     edx, [rbp+8]; unsigned int
0x140015048  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJK@Z; VMX_TRANSFER_PACKET::AllocateMdl(ulong)
0x14001504d  test    eax, eax
0x14001504f  js      short loc_1400150CC
0x140015051  mov     eax, [rbp+8]
0x140015054  mov     [rbx+8], eax
0x140015057  mov     rax, [rbp+10h]
0x14001505b  mov     [rbx+10h], rax
0x14001505f  lea     rax, ?VmxpRaid5ParallelReconstructStripeCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5ParallelReconstructStripeCompletionRoutine(VMX_TRANSFER_PACKET *)
0x140015066  mov     [rbx+28h], rax
0x14001506a  mov     rax, [r15+30h]
0x14001506e  mov     rcx, [rax+rdi*8]
0x140015072  mov     [rbx+30h], rcx
0x140015076  mov     rax, [rbp+38h]
0x14001507a  mov     [rbx+38h], rax
0x14001507e  mov     eax, [rbp+40h]
0x140015081  mov     [rbx+40h], eax
0x140015084  mov     rax, [rbp+48h]
0x140015088  mov     [rbx+48h], rax
0x14001508c  mov     al, [rbp+51h]
0x14001508f  mov     [rbx+51h], al
0x140015092  mov     byte ptr [rbx+52h], 1
0x140015096  mov     [rbx+88h], rbp
0x14001509d  mov     [rbx+90h], edi
0x1400150a3  mov     rcx, [r14+8]
0x1400150a7  cmp     [rcx], r14
0x1400150aa  jnz     loc_14001526D
0x1400150b0  lea     rax, [rbx+98h]
0x1400150b7  mov     [rax], r14
0x1400150ba  mov     [rax+8], rcx
0x1400150be  mov     [rcx], rax
0x1400150c1  mov     [r14+8], rax
0x1400150c5  inc     edi
0x1400150c7  jmp     loc_140014FEF
0x1400150cc  mov     rax, [rbx]
0x1400150cf  mov     edx, 1
0x1400150d4  mov     rcx, rbx
0x1400150d7  mov     rax, [rax]
0x1400150da  call    _guard_dispatch_icall
0x1400150df  cmp     edi, [r15+38h]
0x1400150e3  jnb     short loc_14001512D
0x1400150e5  mov     rax, [r14]
0x1400150e8  cmp     rax, r14
0x1400150eb  jz      short loc_140015129
0x1400150ed  cmp     [rax+8], r14
0x1400150f1  jnz     loc_14001526D
0x1400150f7  mov     rcx, [rax]
0x1400150fa  cmp     [rcx+8], rax
0x1400150fe  jnz     loc_14001526D
0x140015104  mov     [r14], rcx
0x140015107  mov     [rcx+8], r14
0x14001510b  lea     rcx, [rax-98h]
0x140015112  test    rcx, rcx
0x140015115  jz      short loc_1400150E5
0x140015117  mov     rax, [rcx]
0x14001511a  mov     edx, 1
0x14001511f  mov     rax, [rax]
0x140015122  call    _guard_dispatch_icall
0x140015127  jmp     short loc_1400150E5
0x140015129  mov     bl, 1
0x14001512b  jmp     short loc_14001512F
0x14001512d  xor     bl, bl
0x14001512f  lea     rcx, [rbp+58h]; SpinLock
0x140015133  call    cs:__imp_KeInitializeSpinLock
0x14001513a  nop     dword ptr [rax+rax+00h]
0x14001513f  mov     dword ptr [rbp+60h], 0
0x140015146  mov     qword ptr [rbp+68h], 0
0x14001514e  mov     eax, [r15+38h]
0x140015152  dec     eax
0x140015154  mov     [rbp+80h], eax
0x14001515a  test    bl, bl
0x14001515c  jz      loc_1400152BC
0x140015162  mov     r10, [rbp+18h]
0x140015166  lea     rax, ?VmxpRaid5SequentialReconstructStripeEmergencyCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5SequentialReconstructStripeEmergencyCompletionRoutine(VMX_TRANSFER_PACKET *)
0x14001516d  mov     [rbp+28h], rax
0x140015171  mov     eax, [rbp+40h]
0x140015174  and     al, 2
0x140015176  neg     al
0x140015178  sbb     ecx, ecx
0x14001517a  and     ecx, 10h
0x14001517d  add     ecx, 10h
0x140015180  test    byte ptr [r10+0Ah], 5
0x140015185  jz      short loc_14001518D
0x140015187  mov     rax, [r10+18h]
0x14001518b  jmp     short loc_1400151B5
0x14001518d  bts     ecx, 1Eh
0x140015191  xor     r9d, r9d; RequestedAddress
0x140015194  mov     [rsp+68h+Priority], ecx; Priority
0x140015198  xor     edx, edx; AccessMode
0x14001519a  mov     rcx, r10; MemoryDescriptorList
0x14001519d  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400151a5  lea     r8d, [r9+1]; CacheType
0x1400151a9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400151b0  nop     dword ptr [rax+rax+00h]
0x1400151b5  test    rax, rax
0x1400151b8  jz      short loc_1400151CA
0x1400151ba  mov     r8d, [rbp+8]; Size
0x1400151be  xor     edx, edx; Val
0x1400151c0  mov     rcx, rax; void *
0x1400151c3  call    memset
0x1400151c8  jmp     short loc_140015240
0x1400151ca  lea     rsi, [r15+160h]
0x1400151d1  mov     rcx, rsi; SpinLock
0x1400151d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400151db  nop     dword ptr [rax+rax+00h]
0x1400151e0  mov     r8, [rbp+18h]; MemoryDescriptorList
0x1400151e4  mov     r9d, 1; CacheType
0x1400151ea  mov     rcx, [r15+158h]; MappingAddress
0x1400151f1  mov     edx, 6D526D56h; PoolTag
0x1400151f6  mov     dil, al
0x1400151f9  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140015200  nop     dword ptr [rax+rax+00h]
0x140015205  mov     r8d, [rbp+8]; Size
0x140015209  xor     edx, edx; Val
0x14001520b  mov     rcx, rax; void *
0x14001520e  mov     rbx, rax
0x140015211  call    memset
0x140015216  mov     r8, [rbp+18h]; MemoryDescriptorList
0x14001521a  mov     edx, 6D526D56h; PoolTag
0x14001521f  mov     rcx, rbx; BaseAddress
0x140015222  call    cs:__imp_MmUnmapReservedMapping
0x140015229  nop     dword ptr [rax+rax+00h]
0x14001522e  mov     dl, dil; NewIrql
0x140015231  mov     rcx, rsi; SpinLock
0x140015234  call    cs:__imp_KeReleaseSpinLock
0x14001523b  nop     dword ptr [rax+rax+00h]
0x140015240  lea     rbx, [r15+18h]
0x140015244  mov     rcx, rbx; SpinLock
0x140015247  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001524e  nop     dword ptr [rax+rax+00h]
0x140015253  cmp     byte ptr [r15+10Ah], 0
0x14001525b  jz      short loc_140015295
0x14001525d  add     r15, 130h
0x140015264  mov     rcx, [r15+8]
0x140015268  cmp     [rcx], r15
0x14001526b  jz      short loc_140015274
0x14001526d  mov     ecx, 3
0x140015272  int     29h; Win8: RtlFailFast(ecx)
0x140015274  mov     [r14+8], rcx
0x140015278  mov     dl, al; NewIrql
0x14001527a  mov     [r14], r15
0x14001527d  mov     [rcx], r14
0x140015280  mov     rcx, rbx; SpinLock
0x140015283  mov     [r15+8], r14
0x140015287  call    cs:__imp_KeReleaseSpinLock
0x14001528e  nop     dword ptr [rax+rax+00h]
0x140015293  jmp     short loc_1400152E7
0x140015295  mov     dl, al; NewIrql
0x140015297  mov     byte ptr [r15+10Ah], 1
0x14001529f  mov     rcx, rbx; SpinLock
0x1400152a2  call    cs:__imp_KeReleaseSpinLock
0x1400152a9  nop     dword ptr [rax+rax+00h]
0x1400152ae  mov     rax, [rbp+28h]
0x1400152b2  mov     rcx, rbp
0x1400152b5  call    _guard_dispatch_icall
0x1400152ba  jmp     short loc_1400152E7
0x1400152bc  mov     rbx, [r14]
0x1400152bf  jmp     short loc_1400152E2
0x1400152c1  lea     rdx, [rbx-98h]
0x1400152c8  mov     rbx, [rbx]
0x1400152cb  mov     rcx, [rdx+30h]
0x1400152cf  mov     dword ptr [rdx+0Ch], 2010002h
0x1400152d6  mov     rax, [rcx]
0x1400152d9  mov     rax, [rax+8]
0x1400152dd  call    _guard_dispatch_icall
0x1400152e2  cmp     rbx, r14
0x1400152e5  jnz     short loc_1400152C1
0x1400152e7  add     rsp, 38h
0x1400152eb  pop     r15
0x1400152ed  pop     r14
0x1400152ef  pop     rdi
0x1400152f0  pop     rsi
0x1400152f1  pop     rbp
0x1400152f2  pop     rbx
0x1400152f3  retn
```
