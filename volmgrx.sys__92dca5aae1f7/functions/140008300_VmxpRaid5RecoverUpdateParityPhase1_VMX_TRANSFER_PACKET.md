# VmxpRaid5RecoverUpdateParityPhase1(VMX_TRANSFER_PACKET *)

- ea: `0x140008300`
- end: `0x1400087c7`
- name: `?VmxpRaid5RecoverUpdateParityPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `1223`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002470`
- `0x140008300`
- `0x1400087d0`
- `0x14000b420`
- `0x1400110f8`
- `0x140012560`
- `0x14001b9a0`
- `0x14001bb80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008717`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083e3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008717`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000842a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008756`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008770`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000842a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008756`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008770`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400083bc`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400083bc`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400086ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400086ce`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140008327`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140008327`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000838b`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000838b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400084bf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400084fa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008532`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400084bf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400084fa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008532`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverUpdateParityPhase1(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rdi
  NTSTATUS v3; // esi
  __int64 v4; // rbp
  __int64 v5; // rcx
  int v6; // r8d
  struct _MDL *v7; // rdx
  ULONG v8; // r9d
  KSPIN_LOCK *v9; // r12
  KIRQL v10; // al
  unsigned int v11; // edx
  unsigned int v12; // esi
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  PVOID v18; // rsi
  __int64 v19; // r10
  char *v20; // r14
  __int64 v21; // r10
  char *v22; // rax
  _QWORD **v23; // rsi
  unsigned int v24; // r15d
  _BYTE *v25; // rax
  _BYTE *v26; // r14
  _QWORD *v27; // rcx
  _QWORD *v28; // rax
  _QWORD *v29; // rcx
  char v30; // di
  KIRQL v31; // al
  _QWORD *v32; // rbp
  _QWORD *v33; // rcx
  _QWORD *v34; // rbx
  _QWORD *v35; // rdx
  __int64 v36; // rcx

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 - 336);
  if ( FsRtlIsTotalDeviceFailure(v3) )
  {
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
    goto LABEL_3;
  }
  if ( v3 >= 0 )
  {
    *((_DWORD *)a1 + 76) = *((_DWORD *)a1 + 2);
    *((_QWORD *)a1 + 39) = *((_QWORD *)a1 + 2);
    *((_BYTE *)a1 + 378) = 0;
    v5 = *((_QWORD *)a1 + 34);
    if ( (*(_BYTE *)(v5 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v5 + 24), *((PMDL *)a1 + 34));
    v6 = *((_DWORD *)a1 + 78);
    v7 = (struct _MDL *)*((_QWORD *)a1 + 34);
    v8 = *((_DWORD *)a1 + 76);
    *((_QWORD *)a1 + 40) = v7;
    IoBuildPartialMdl(
      *(PMDL *)(v1 + 24),
      v7,
      (PVOID)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 32LL)
            + *(unsigned int *)(*(_QWORD *)(v1 + 24) + 44LL)
            + (unsigned __int64)(unsigned int)(v6 - *(_DWORD *)(v1 + 16))),
      v8);
    VMX_PARITY_IO_MANAGER::UpdateParity(
      (VMX_PARITY_IO_MANAGER *)(v4 + 160),
      (struct VMX_TRANSFER_PACKET *)((char *)a1 + 296));
    return;
  }
  v9 = (KSPIN_LOCK *)(v4 + 24);
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
  v11 = *(_DWORD *)(v4 + 56);
  v12 = 0;
  if ( v11 )
  {
    v13 = *(_QWORD *)(v4 + 112);
    do
    {
      if ( v12 != *(_DWORD *)(v1 - 32) && v12 != *((_DWORD *)a1 + 60) && *(_DWORD *)(v13 + 16) )
        break;
      ++v12;
      v13 += 24;
    }
    while ( v12 < v11 );
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v10);
  if ( v12 < *(_DWORD *)(v4 + 56) )
  {
    v14 = *(_QWORD *)(v1 + 16) + *(unsigned int *)(v1 + 8);
    *(_DWORD *)(v1 + 96) = -1073741668;
    *(_QWORD *)(v1 + 104) = 0;
    v15 = *((_QWORD *)a1 + 2) + *((unsigned int *)a1 + 2);
    if ( v15 != v14 )
    {
      v16 = *((_QWORD *)a1 + 6);
      *((_QWORD *)a1 + 3) = *((_QWORD *)a1 + 36);
      *((_QWORD *)a1 + 5) = VmxpRaid5RecoverUpdateParityPhase1;
      *((_QWORD *)a1 + 2) = v15;
      *((_BYTE *)a1 + 82) = 1;
      *((_DWORD *)a1 + 3) = 33685511;
      (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v16 + 8LL))(v16, a1);
      return;
    }
LABEL_3:
    VMX_IO_RAID5::RecycleRecoverPacket((VMX_IO_RAID5 *)v4, a1);
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    return;
  }
  v17 = *((_QWORD *)a1 + 3);
  if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
    v18 = *(PVOID *)(v17 + 24);
  else
    v18 = MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000010u);
  v19 = *(_QWORD *)(v1 - 248);
  if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
    v20 = *(char **)(v19 + 24);
  else
    v20 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000010u);
  v21 = *(_QWORD *)(v1 + 24);
  if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
    v22 = *(char **)(v21 + 24);
  else
    v22 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000010u);
  memmove(v18, &v22[*((_DWORD *)a1 + 4) - *(_DWORD *)(v1 + 16)], *((unsigned int *)a1 + 2));
  VmxpComputeParity(v18, &v20[*((_DWORD *)a1 + 4) - *(_DWORD *)(v1 - 256)], *((_DWORD *)a1 + 2));
  v23 = (_QWORD **)((char *)a1 + 112);
  v24 = 0;
  *((_QWORD *)a1 + 15) = (char *)a1 + 112;
  *((_QWORD *)a1 + 14) = (char *)a1 + 112;
  while ( 1 )
  {
    if ( v24 >= *(_DWORD *)(v4 + 56) )
      goto LABEL_43;
    if ( v24 != *(_DWORD *)(v1 - 32) && v24 != *((_DWORD *)a1 + 60) )
      break;
LABEL_34:
    ++v24;
  }
  v25 = VMX_TRANSFER_PACKET::operator new(0xA8u);
  v26 = v25;
  if ( !v25 )
    goto LABEL_36;
  *((_QWORD *)v25 + 4) = 0;
  *((_QWORD *)v25 + 3) = 0;
  v25[83] = 0;
  *((_WORD *)v25 + 66) = 0;
  *(_QWORD *)v25 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
  if ( (int)VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v25, *((_DWORD *)a1 + 2)) >= 0 )
  {
    *((_DWORD *)v26 + 2) = *((_DWORD *)a1 + 2);
    *((_QWORD *)v26 + 2) = *((_QWORD *)a1 + 2);
    *((_QWORD *)v26 + 5) = VmxpRaid5RecoverUpdateParityPhase2;
    *((_QWORD *)v26 + 6) = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8LL * v24);
    *((_QWORD *)v26 + 7) = *((_QWORD *)a1 + 7);
    *((_DWORD *)v26 + 16) = *((_DWORD *)a1 + 16);
    *((_QWORD *)v26 + 9) = *((_QWORD *)a1 + 9);
    v26[81] = *((_BYTE *)a1 + 81);
    v26[82] = 1;
    *((_QWORD *)v26 + 17) = a1;
    *((_DWORD *)v26 + 36) = v24;
    v27 = (_QWORD *)*((_QWORD *)a1 + 15);
    if ( (_QWORD **)*v27 != v23 )
      goto LABEL_47;
    *((_QWORD *)v26 + 19) = v23;
    *((_QWORD *)v26 + 20) = v27;
    *v27 = v26 + 152;
    *((_QWORD *)a1 + 15) = v26 + 152;
    goto LABEL_34;
  }
  (**(void (__fastcall ***)(_BYTE *, __int64))v26)(v26, 1);
LABEL_36:
  if ( v24 >= *(_DWORD *)(v4 + 56) )
  {
LABEL_43:
    v30 = 0;
    goto LABEL_44;
  }
  while ( 1 )
  {
    v28 = *v23;
    if ( *v23 == v23 )
      break;
    if ( (_QWORD **)v28[1] != v23 )
      goto LABEL_47;
    v29 = (_QWORD *)*v28;
    if ( *(_QWORD **)(*v28 + 8LL) != v28 )
      goto LABEL_47;
    *v23 = v29;
    v29[1] = v23;
    if ( v28 != (_QWORD *)152 )
      (*(void (__fastcall **)(_QWORD *, __int64))*(v28 - 19))(v28 - 19, 1);
  }
  v30 = 1;
LABEL_44:
  KeInitializeSpinLock((PKSPIN_LOCK)a1 + 11);
  *((_DWORD *)a1 + 24) = 0;
  *((_QWORD *)a1 + 5) = VmxpRaid5RecoverUpdateParityPhase5;
  *((_QWORD *)a1 + 13) = 0;
  *((_DWORD *)a1 + 32) = *(_DWORD *)(v4 + 56) - 2;
  if ( v30 )
  {
    *((_QWORD *)a1 + 31) = VmxpRaid5RecoverUpdateParityPhase5;
    *((_QWORD *)a1 + 5) = VmxpRaid5RecoverUpdateParityPhase3;
    v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
    if ( *(_BYTE *)(v4 + 266) )
    {
      v32 = (_QWORD *)(v4 + 304);
      v33 = (_QWORD *)v32[1];
      if ( (_QWORD *)*v33 != v32 )
LABEL_47:
        __fastfail(3u);
      *((_QWORD *)a1 + 15) = v33;
      *v23 = v32;
      *v33 = v23;
      v32[1] = v23;
      KeReleaseSpinLock(v9, v31);
    }
    else
    {
      *(_BYTE *)(v4 + 266) = 1;
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v31);
      (*((void (__fastcall **)(struct VMX_TRANSFER_PACKET *))a1 + 5))(a1);
    }
  }
  else
  {
    v34 = *v23;
    while ( v34 != v23 )
    {
      v35 = v34 - 19;
      v34 = (_QWORD *)*v34;
      v36 = v35[6];
      *((_DWORD *)v35 + 3) = 33685512;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
}

```

## disassembly

```asm
0x140008300  push    rbx
0x140008302  push    rbp
0x140008303  push    rsi
0x140008304  push    rdi
0x140008305  push    r12
0x140008307  push    r13
0x140008309  push    r14
0x14000830b  push    r15
0x14000830d  sub     rsp, 38h
0x140008311  mov     rdi, [rcx+0E0h]
0x140008318  mov     rbx, rcx
0x14000831b  mov     esi, [rcx+60h]
0x14000831e  mov     ecx, esi; Status
0x140008320  mov     rbp, [rdi-150h]
0x140008327  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x14000832e  nop     dword ptr [rax+rax+00h]
0x140008333  xor     r13d, r13d
0x140008336  test    al, al
0x140008338  jz      short loc_14000835A
0x14000833a  movups  xmm0, xmmword ptr [rbx+60h]
0x14000833e  movdqu  xmmword ptr [rdi+60h], xmm0
0x140008343  mov     rdx, rbx; struct VMX_RAID5_RECOVER_TRANSFER_PACKET *
0x140008346  mov     rcx, rbp; this
0x140008349  call    ?RecycleRecoverPacket@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_RECOVER_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::RecycleRecoverPacket(VMX_RAID5_RECOVER_TRANSFER_PACKET *)
0x14000834e  mov     rax, [rdi+28h]
0x140008352  mov     rcx, rdi
0x140008355  jmp     loc_140008783
0x14000835a  test    esi, esi
0x14000835c  js      short loc_1400083DC
0x14000835e  mov     eax, [rbx+8]
0x140008361  lea     rsi, [rbx+128h]
0x140008368  mov     [rsi+8], eax
0x14000836b  mov     rax, [rbx+10h]
0x14000836f  mov     [rsi+10h], rax
0x140008373  mov     [rsi+52h], r13b
0x140008377  mov     rcx, [rbx+110h]
0x14000837e  test    byte ptr [rcx+0Ah], 20h
0x140008382  jz      short loc_140008397
0x140008384  mov     rdx, rcx; MemoryDescriptorList
0x140008387  mov     rcx, [rcx+18h]; BaseAddress
0x14000838b  call    cs:__imp_MmUnmapLockedPages
0x140008392  nop     dword ptr [rax+rax+00h]
0x140008397  mov     r8d, [rsi+10h]
0x14000839b  mov     rdx, [rbx+110h]; TargetMdl
0x1400083a2  mov     r9d, [rsi+8]; Length
0x1400083a6  mov     [rsi+18h], rdx
0x1400083aa  mov     rcx, [rdi+18h]; SourceMdl
0x1400083ae  sub     r8d, [rdi+10h]
0x1400083b2  mov     eax, [rcx+2Ch]
0x1400083b5  add     r8, rax
0x1400083b8  add     r8, [rcx+20h]; VirtualAddress
0x1400083bc  call    cs:__imp_IoBuildPartialMdl
0x1400083c3  nop     dword ptr [rax+rax+00h]
0x1400083c8  lea     rcx, [rbp+0A0h]; this
0x1400083cf  mov     rdx, rsi; struct VMX_RAID5_PARITY_TRANSFER_PACKET *
0x1400083d2  call    ?UpdateParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z; VMX_PARITY_IO_MANAGER::UpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)
0x1400083d7  jmp     loc_1400087B5
0x1400083dc  lea     r12, [rbp+18h]
0x1400083e0  mov     rcx, r12; SpinLock
0x1400083e3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400083ea  nop     dword ptr [rax+rax+00h]
0x1400083ef  mov     edx, [rbp+38h]
0x1400083f2  mov     esi, r13d
0x1400083f5  mov     r15d, 1
0x1400083fb  test    edx, edx
0x1400083fd  jz      short loc_140008425
0x1400083ff  mov     rcx, [rbp+70h]
0x140008403  mov     r8d, [rdi-20h]
0x140008407  cmp     esi, r8d
0x14000840a  jz      short loc_14000841A
0x14000840c  cmp     esi, [rbx+0F0h]
0x140008412  jz      short loc_14000841A
0x140008414  cmp     [rcx+10h], r13d
0x140008418  jnz     short loc_140008425
0x14000841a  add     esi, r15d
0x14000841d  add     rcx, 18h
0x140008421  cmp     esi, edx
0x140008423  jb      short loc_140008407
0x140008425  mov     dl, al; NewIrql
0x140008427  mov     rcx, r12; SpinLock
0x14000842a  call    cs:__imp_KeReleaseSpinLock
0x140008431  nop     dword ptr [rax+rax+00h]
0x140008436  cmp     esi, [rbp+38h]
0x140008439  jnb     short loc_14000849A
0x14000843b  mov     eax, [rdi+8]
0x14000843e  add     rax, [rdi+10h]
0x140008442  mov     dword ptr [rdi+60h], 0C000009Ch
0x140008449  mov     [rdi+68h], r13
0x14000844d  mov     edx, [rbx+8]
0x140008450  add     rdx, [rbx+10h]
0x140008454  cmp     rdx, rax
0x140008457  jz      loc_140008343
0x14000845d  mov     rax, [rbx+120h]
0x140008464  mov     rcx, [rbx+30h]
0x140008468  mov     [rbx+18h], rax
0x14000846c  lea     rax, ?VmxpRaid5RecoverUpdateParityPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase1(VMX_TRANSFER_PACKET *)
0x140008473  mov     [rbx+28h], rax
0x140008477  mov     [rbx+10h], rdx
0x14000847b  mov     rdx, rbx
0x14000847e  mov     [rbx+52h], r15b
0x140008482  mov     dword ptr [rbx+0Ch], 2020007h
0x140008489  mov     rax, [rcx]
0x14000848c  mov     rax, [rax+8]
0x140008490  call    _guard_dispatch_icall
0x140008495  jmp     loc_1400087B5
0x14000849a  mov     rcx, [rbx+18h]; MemoryDescriptorList
0x14000849e  test    byte ptr [rcx+0Ah], 5
0x1400084a2  jz      short loc_1400084AA
0x1400084a4  mov     rsi, [rcx+18h]
0x1400084a8  jmp     short loc_1400084CE
0x1400084aa  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400084b2  xor     r9d, r9d; RequestedAddress
0x1400084b5  mov     r8d, r15d; CacheType
0x1400084b8  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400084bd  xor     edx, edx; AccessMode
0x1400084bf  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400084c6  nop     dword ptr [rax+rax+00h]
0x1400084cb  mov     rsi, rax
0x1400084ce  mov     r10, [rdi-0F8h]
0x1400084d5  test    byte ptr [r10+0Ah], 5
0x1400084da  jz      short loc_1400084E2
0x1400084dc  mov     r14, [r10+18h]
0x1400084e0  jmp     short loc_140008509
0x1400084e2  mov     [rsp+78h+Priority], 40000010h; Priority
0x1400084ea  xor     r9d, r9d; RequestedAddress
0x1400084ed  mov     r8d, r15d; CacheType
0x1400084f0  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400084f5  xor     edx, edx; AccessMode
0x1400084f7  mov     rcx, r10; MemoryDescriptorList
0x1400084fa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140008501  nop     dword ptr [rax+rax+00h]
0x140008506  mov     r14, rax
0x140008509  mov     r10, [rdi+18h]
0x14000850d  test    byte ptr [r10+0Ah], 5
0x140008512  jz      short loc_14000851A
0x140008514  mov     rax, [r10+18h]
0x140008518  jmp     short loc_14000853E
0x14000851a  mov     [rsp+78h+Priority], 40000010h; Priority
0x140008522  xor     r9d, r9d; RequestedAddress
0x140008525  mov     r8d, r15d; CacheType
0x140008528  mov     [rsp+78h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14000852d  xor     edx, edx; AccessMode
0x14000852f  mov     rcx, r10; MemoryDescriptorList
0x140008532  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140008539  nop     dword ptr [rax+rax+00h]
0x14000853e  mov     edx, [rbx+10h]
0x140008541  mov     rcx, rsi; void *
0x140008544  sub     edx, [rdi+10h]
0x140008547  mov     r8d, [rbx+8]; Size
0x14000854b  add     rdx, rax; Src
0x14000854e  call    memmove
0x140008553  mov     edx, [rbx+10h]
0x140008556  mov     rcx, rsi; void *
0x140008559  sub     edx, [rdi-100h]
0x14000855f  mov     r8d, [rbx+8]; unsigned int
0x140008563  add     rdx, r14; void *
0x140008566  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x14000856b  lea     rsi, [rbx+70h]
0x14000856f  mov     r15d, r13d
0x140008572  mov     [rsi+8], rsi
0x140008576  mov     [rsi], rsi
0x140008579  cmp     r15d, [rbp+38h]
0x14000857d  jnb     loc_1400086C7
0x140008583  cmp     r15d, [rdi-20h]
0x140008587  jz      loc_14000865D
0x14000858d  cmp     r15d, [rbx+0F0h]
0x140008594  jz      loc_14000865D
0x14000859a  mov     ecx, 0A8h; unsigned __int64
0x14000859f  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x1400085a4  mov     r14, rax
0x1400085a7  test    rax, rax
0x1400085aa  jz      loc_140008678
0x1400085b0  mov     [rax+20h], r13
0x1400085b4  mov     rcx, r14; this
0x1400085b7  mov     [rax+18h], r13
0x1400085bb  mov     [rax+53h], r13b
0x1400085bf  mov     [rax+84h], r13w
0x1400085c7  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x1400085ce  mov     [r14], rax
0x1400085d1  mov     edx, [rbx+8]; unsigned int
0x1400085d4  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJK@Z; VMX_TRANSFER_PACKET::AllocateMdl(ulong)
0x1400085d9  test    eax, eax
0x1400085db  js      loc_140008665
0x1400085e1  mov     eax, [rbx+8]
0x1400085e4  mov     [r14+8], eax
0x1400085e8  mov     rax, [rbx+10h]
0x1400085ec  mov     [r14+10h], rax
0x1400085f0  lea     rax, ?VmxpRaid5RecoverUpdateParityPhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase2(VMX_TRANSFER_PACKET *)
0x1400085f7  mov     [r14+28h], rax
0x1400085fb  mov     rax, [rbp+30h]
0x1400085ff  mov     ecx, r15d
0x140008602  mov     rcx, [rax+rcx*8]
0x140008606  mov     [r14+30h], rcx
0x14000860a  mov     rax, [rbx+38h]
0x14000860e  mov     [r14+38h], rax
0x140008612  mov     eax, [rbx+40h]
0x140008615  mov     [r14+40h], eax
0x140008619  mov     rax, [rbx+48h]
0x14000861d  mov     [r14+48h], rax
0x140008621  mov     al, [rbx+51h]
0x140008624  mov     [r14+51h], al
0x140008628  mov     byte ptr [r14+52h], 1
0x14000862d  mov     [r14+88h], rbx
0x140008634  mov     [r14+90h], r15d
0x14000863b  mov     rcx, [rsi+8]
0x14000863f  cmp     [rcx], rsi
0x140008642  jnz     loc_14000873C
0x140008648  lea     rax, [r14+98h]
0x14000864f  mov     [rax], rsi
0x140008652  mov     [rax+8], rcx
0x140008656  mov     [rcx], rax
0x140008659  mov     [rsi+8], rax
0x14000865d  inc     r15d
0x140008660  jmp     loc_140008579
0x140008665  mov     rax, [r14]
0x140008668  mov     edx, 1
0x14000866d  mov     rcx, r14
0x140008670  mov     rax, [rax]
0x140008673  call    _guard_dispatch_icall
0x140008678  cmp     r15d, [rbp+38h]
0x14000867c  jnb     short loc_1400086C7
0x14000867e  mov     rax, [rsi]
0x140008681  cmp     rax, rsi
0x140008684  jz      short loc_1400086C2
0x140008686  cmp     [rax+8], rsi
0x14000868a  jnz     loc_14000873C
0x140008690  mov     rcx, [rax]
0x140008693  cmp     [rcx+8], rax
0x140008697  jnz     loc_14000873C
0x14000869d  mov     [rsi], rcx
0x1400086a0  mov     [rcx+8], rsi
0x1400086a4  lea     rcx, [rax-98h]
0x1400086ab  test    rcx, rcx
0x1400086ae  jz      short loc_14000867E
0x1400086b0  mov     rax, [rcx]
0x1400086b3  mov     edx, 1
0x1400086b8  mov     rax, [rax]
0x1400086bb  call    _guard_dispatch_icall
0x1400086c0  jmp     short loc_14000867E
0x1400086c2  mov     dil, 1
0x1400086c5  jmp     short loc_1400086CA
0x1400086c7  mov     dil, r13b
0x1400086ca  lea     rcx, [rbx+58h]; SpinLock
0x1400086ce  call    cs:__imp_KeInitializeSpinLock
0x1400086d5  nop     dword ptr [rax+rax+00h]
0x1400086da  lea     rcx, ?VmxpRaid5RecoverUpdateParityPhase5@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase5(VMX_TRANSFER_PACKET *)
0x1400086e1  mov     [rbx+60h], r13d
0x1400086e5  mov     [rbx+28h], rcx
0x1400086e9  mov     [rbx+68h], r13
0x1400086ed  mov     eax, [rbp+38h]
0x1400086f0  sub     eax, 2
0x1400086f3  mov     [rbx+80h], eax
0x1400086f9  test    dil, dil
0x1400086fc  jz      loc_14000878A
0x140008702  mov     [rbx+0F8h], rcx
0x140008709  lea     rax, ?VmxpRaid5RecoverUpdateParityPhase3@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase3(VMX_TRANSFER_PACKET *)
0x140008710  mov     rcx, r12; SpinLock
0x140008713  mov     [rbx+28h], rax
0x140008717  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000871e  nop     dword ptr [rax+rax+00h]
0x140008723  cmp     [rbp+10Ah], r13b
0x14000872a  jz      short loc_140008764
0x14000872c  add     rbp, 130h
0x140008733  mov     rcx, [rbp+8]
0x140008737  cmp     [rcx], rbp
0x14000873a  jz      short loc_140008743
0x14000873c  mov     ecx, 3
0x140008741  int     29h; Win8: RtlFailFast(ecx)
0x140008743  mov     [rsi+8], rcx
0x140008747  mov     dl, al; NewIrql
0x140008749  mov     [rsi], rbp
0x14000874c  mov     [rcx], rsi
0x14000874f  mov     rcx, r12; SpinLock
0x140008752  mov     [rbp+8], rsi
0x140008756  call    cs:__imp_KeReleaseSpinLock
0x14000875d  nop     dword ptr [rax+rax+00h]
0x140008762  jmp     short loc_1400087B5
0x140008764  mov     dl, al; NewIrql
0x140008766  mov     byte ptr [rbp+10Ah], 1
0x14000876d  mov     rcx, r12; SpinLock
0x140008770  call    cs:__imp_KeReleaseSpinLock
0x140008777  nop     dword ptr [rax+rax+00h]
0x14000877c  mov     rax, [rbx+28h]
0x140008780  mov     rcx, rbx
0x140008783  call    _guard_dispatch_icall
0x140008788  jmp     short loc_1400087B5
0x14000878a  mov     rbx, [rsi]
0x14000878d  jmp     short loc_1400087B0
0x14000878f  lea     rdx, [rbx-98h]
0x140008796  mov     rbx, [rbx]
0x140008799  mov     rcx, [rdx+30h]
0x14000879d  mov     dword ptr [rdx+0Ch], 2020008h
0x1400087a4  mov     rax, [rcx]
0x1400087a7  mov     rax, [rax+8]
0x1400087ab  call    _guard_dispatch_icall
0x1400087b0  cmp     rbx, rsi
0x1400087b3  jnz     short loc_14000878F
0x1400087b5  add     rsp, 38h
0x1400087b9  pop     r15
0x1400087bb  pop     r14
  ... truncated ...
```
