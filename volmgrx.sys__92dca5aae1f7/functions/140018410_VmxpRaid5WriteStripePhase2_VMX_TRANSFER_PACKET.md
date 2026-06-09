# VmxpRaid5WriteStripePhase2(VMX_TRANSFER_PACKET *)

- ea: `0x140018410`
- end: `0x1400187f0`
- name: `?VmxpRaid5WriteStripePhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `992`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400087d0`
- `0x14000d0dc`
- `0x14000f898`
- `0x140012560`
- `0x140018410`
- `0x140018fcc`
- `0x14001b9a0`
- `0x14001bb80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400184ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018661`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400184ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018661`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400184f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400186c4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400184f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400186c4`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140018686`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140018686`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001859b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001859b`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400186b2`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400186b2`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14001845f`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14001845f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400185e9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140018632`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140018710`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400185e9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140018632`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140018710`

## pseudocode

```c
void __fastcall VmxpRaid5WriteStripePhase2(struct VMX_TRANSFER_PACKET *a1)
{
  NTSTATUS v1; // edi
  __int64 v2; // r15
  __int64 v4; // rbp
  __int64 v5; // r8
  KIRQL v6; // al
  __int64 v7; // r9
  KIRQL v8; // r11
  void (__fastcall *v9)(struct VMX_TRANSFER_PACKET *); // rax
  __int64 v10; // rcx
  PVOID v11; // rbx
  __int64 v12; // rcx
  PVOID v13; // rax
  KIRQL v14; // di
  PVOID v15; // rbx
  __int64 v16; // rcx
  PVOID v17; // rax
  __int64 v18; // rax
  bool v19; // zf
  __int64 v20; // rcx
  void *v21; // [rsp+60h] [rbp+8h]

  v1 = *((_DWORD *)a1 + 24);
  v2 = *((_QWORD *)a1 + 29);
  v4 = *((_QWORD *)a1 + 28);
  if ( v1 < 0 )
  {
    if ( !*((_BYTE *)a1 + 264) && v1 != -2147483626 )
    {
      if ( FsRtlIsTotalDeviceFailure(v1) )
      {
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 26, v5, v2, v1);
        }
        v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 24));
        v7 = *((unsigned int *)a1 + 60);
        v8 = v6;
        if ( *(_DWORD *)(*(_QWORD *)(v2 + 112) + 24 * v7 + 16) != 4 )
        {
          if ( VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v2, v7, 1) )
            ++*(_DWORD *)(*((_QWORD *)a1 + 32) + 168LL);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), v8);
        v9 = VmxpRaid5WriteStripePhase1;
        *((_BYTE *)a1 + 264) = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 27, v5, v2, v1);
        }
        *((_BYTE *)a1 + 264) = 1;
        *(_QWORD *)(v4 + 248) = *(_QWORD *)(v4 + 40);
        v9 = VmxpRaid5WriteStripePhase3;
      }
      *(_QWORD *)(v4 + 40) = v9;
      VMX_OVERLAPPED_IO_MANAGER::PromoteToAllMembers(
        (VMX_OVERLAPPED_IO_MANAGER *)(v2 + 136),
        (struct VMX_OVERLAP_TRANSFER_PACKET *)v4);
      return;
    }
    *(_OWORD *)(v4 + 96) = *((_OWORD *)a1 + 6);
LABEL_41:
    (*(void (__fastcall **)(__int64))(v4 + 40))(v4);
    return;
  }
  KeInitializeSpinLock((PKSPIN_LOCK)(v4 + 88));
  v10 = *(_QWORD *)(v4 + 280);
  *(_DWORD *)(v4 + 96) = 0;
  *(_QWORD *)(v4 + 104) = 0;
  *(_QWORD *)(v4 + 320) = v10;
  *(_QWORD *)(v4 + 336) = VmxpRaid5WriteStripePhase4;
  *(_BYTE *)(v4 + 378) = 0;
  if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
    v11 = *(PVOID *)(v10 + 24);
  else
    v11 = MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
  v21 = v11;
  v12 = *(_QWORD *)(v4 + 24);
  if ( (*(_BYTE *)(v12 + 10) & 5) != 0 )
    v13 = *(PVOID *)(v12 + 24);
  else
    v13 = MmMapLockedPagesSpecifyCache(
            (PMDL)v12,
            0,
            MmCached,
            0,
            0,
            ((*(_DWORD *)(v4 + 64) & 2) != 0 ? 32 : 16) | 0x40000000u);
  if ( v13 )
  {
    memmove(v11, v13, *(unsigned int *)(v4 + 304));
  }
  else
  {
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 352));
    v15 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v2 + 344), 0x6D526D56u, *(PMDL *)(v4 + 24), MmCached);
    memmove(v21, v15, *(unsigned int *)(v4 + 304));
    MmUnmapReservedMapping(v15, 0x6D526D56u, *(PMDL *)(v4 + 24));
    KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 352), v14);
    v11 = v21;
  }
  v16 = *(_QWORD *)(v4 + 272);
  *(_QWORD *)(v4 + 592) = v16;
  *(_QWORD *)(v4 + 608) = VmxpRaid5WriteStripePhase5;
  if ( (*(_BYTE *)(v16 + 10) & 5) != 0 )
    v17 = *(PVOID *)(v16 + 24);
  else
    v17 = MmMapLockedPagesSpecifyCache((PMDL)v16, 0, MmCached, 0, 0, 0x40000010u);
  VmxpComputeParity(v17, v11, *(_DWORD *)(v4 + 576));
  v18 = *(_QWORD *)(v4 + 616);
  if ( *(_DWORD *)(v4 + 288) == 4 )
  {
    if ( v18 )
    {
      *(_DWORD *)(v4 + 128) = 1;
      *(_DWORD *)(v4 + 392) = -1073741810;
      *(_QWORD *)(v4 + 400) = 0;
      VMX_PARITY_IO_MANAGER::UpdateParity(
        (VMX_PARITY_IO_MANAGER *)(v2 + 160),
        (struct VMX_RAID5_PARITY_TRANSFER_PACKET *)(v4 + 568));
      return;
    }
    *(_DWORD *)(v4 + 96) = -1073741810;
    *(_QWORD *)(v4 + 104) = 0;
    goto LABEL_41;
  }
  if ( v18 )
  {
    v19 = (*(_BYTE *)(v4 + 81) & 8) == 0;
    *(_DWORD *)(v4 + 128) = 2;
    if ( v19 )
      VMX_PARITY_IO_MANAGER::UpdateParity(
        (VMX_PARITY_IO_MANAGER *)(v2 + 160),
        (struct VMX_RAID5_PARITY_TRANSFER_PACKET *)(v4 + 568));
  }
  else
  {
    *(_DWORD *)(v4 + 128) = 1;
    *(_DWORD *)(v4 + 664) = -1073741810;
    *(_QWORD *)(v4 + 672) = 0;
  }
  v20 = *(_QWORD *)(v4 + 344);
  *(_DWORD *)(v4 + 308) = 33685508;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, v4 + 296);
}

```

## disassembly

```asm
0x140018410  mov     [rsp+arg_8], rbx
0x140018415  mov     [rsp+arg_10], rbp
0x14001841a  push    rsi
0x14001841b  push    rdi
0x14001841c  push    r12
0x14001841e  push    r13
0x140018420  push    r15
0x140018422  sub     rsp, 30h
0x140018426  mov     edi, [rcx+60h]
0x140018429  xor     esi, esi
0x14001842b  mov     r15, [rcx+0E8h]
0x140018432  mov     rbx, rcx
0x140018435  mov     rbp, [rcx+0E0h]
0x14001843c  test    edi, edi
0x14001843e  jns     loc_140018589
0x140018444  cmp     [rcx+108h], sil
0x14001844b  jnz     loc_14001857B
0x140018451  cmp     edi, 80000016h
0x140018457  jz      loc_14001857B
0x14001845d  mov     ecx, edi; Status
0x14001845f  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140018466  nop     dword ptr [rax+rax+00h]
0x14001846b  test    al, al
0x14001846d  jz      loc_140018529
0x140018473  mov     rcx, cs:WPP_GLOBAL_Control
0x14001847a  lea     rax, WPP_GLOBAL_Control
0x140018481  cmp     rcx, rax
0x140018484  jz      short loc_1400184A8
0x140018486  test    dword ptr [rcx+2Ch], 1000h
0x14001848d  jz      short loc_1400184A8
0x14001848f  cmp     byte ptr [rcx+29h], 3
0x140018493  jb      short loc_1400184A8
0x140018495  mov     rcx, [rcx+18h]
0x140018499  lea     edx, [rsi+1Ah]
0x14001849c  mov     r9, r15
0x14001849f  mov     [rsp+58h+BugCheckOnFailure], edi
0x1400184a3  call    WPP_SF_qd
0x1400184a8  lea     rcx, [r15+18h]; SpinLock
0x1400184ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400184b3  nop     dword ptr [rax+rax+00h]
0x1400184b8  mov     r9d, [rbx+0F0h]
0x1400184bf  mov     r11b, al
0x1400184c2  mov     rcx, [r15+70h]
0x1400184c6  lea     rdx, [r9+r9*2]
0x1400184ca  cmp     dword ptr [rcx+rdx*8+10h], 4
0x1400184cf  jz      short loc_1400184F0
0x1400184d1  mov     r8b, 1; unsigned __int8
0x1400184d4  mov     edx, r9d; unsigned int
0x1400184d7  mov     rcx, r15; this
0x1400184da  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x1400184df  test    al, al
0x1400184e1  jz      short loc_1400184F0
0x1400184e3  mov     rax, [rbx+100h]
0x1400184ea  inc     dword ptr [rax+0A8h]
0x1400184f0  mov     dl, r11b; NewIrql
0x1400184f3  lea     rcx, [r15+18h]; SpinLock
0x1400184f7  call    cs:__imp_KeReleaseSpinLock
0x1400184fe  nop     dword ptr [rax+rax+00h]
0x140018503  lea     rax, ?VmxpRaid5WriteStripePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5WriteStripePhase1(VMX_TRANSFER_PACKET *)
0x14001850a  mov     byte ptr [rbx+108h], 1
0x140018511  lea     rcx, [r15+88h]; this
0x140018518  mov     [rbp+28h], rax
0x14001851c  mov     rdx, rbp; struct VMX_OVERLAP_TRANSFER_PACKET *
0x14001851f  call    ?PromoteToAllMembers@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::PromoteToAllMembers(VMX_OVERLAP_TRANSFER_PACKET *)
0x140018524  jmp     loc_1400187D8
0x140018529  mov     rcx, cs:WPP_GLOBAL_Control
0x140018530  lea     rax, WPP_GLOBAL_Control
0x140018537  cmp     rcx, rax
0x14001853a  jz      short loc_140018560
0x14001853c  test    dword ptr [rcx+2Ch], 1000h
0x140018543  jz      short loc_140018560
0x140018545  cmp     byte ptr [rcx+29h], 3
0x140018549  jb      short loc_140018560
0x14001854b  mov     rcx, [rcx+18h]
0x14001854f  mov     edx, 1Bh
0x140018554  mov     r9, r15
0x140018557  mov     [rsp+58h+BugCheckOnFailure], edi
0x14001855b  call    WPP_SF_qd
0x140018560  mov     byte ptr [rbx+108h], 1
0x140018567  mov     rax, [rbp+28h]
0x14001856b  mov     [rbp+0F8h], rax
0x140018572  lea     rax, ?VmxpRaid5WriteStripePhase3@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5WriteStripePhase3(VMX_TRANSFER_PACKET *)
0x140018579  jmp     short loc_140018511
0x14001857b  movups  xmm0, xmmword ptr [rcx+60h]
0x14001857f  movdqu  xmmword ptr [rbp+60h], xmm0
0x140018584  jmp     loc_1400187CC
0x140018589  lea     rcx, [rbp+58h]; SpinLock
0x14001858d  lea     r12, [rbp+238h]
0x140018594  lea     r13, [rbp+128h]
0x14001859b  call    cs:__imp_KeInitializeSpinLock
0x1400185a2  nop     dword ptr [rax+rax+00h]
0x1400185a7  mov     rcx, [rbp+118h]; MemoryDescriptorList
0x1400185ae  lea     rax, ?VmxpRaid5WriteStripePhase4@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5WriteStripePhase4(VMX_TRANSFER_PACKET *)
0x1400185b5  mov     [rbp+60h], esi
0x1400185b8  mov     [rbp+68h], rsi
0x1400185bc  mov     [r13+18h], rcx
0x1400185c0  mov     [r13+28h], rax
0x1400185c4  mov     [r13+52h], sil
0x1400185c8  test    byte ptr [rcx+0Ah], 5
0x1400185cc  jz      short loc_1400185D4
0x1400185ce  mov     rbx, [rcx+18h]
0x1400185d2  jmp     short loc_1400185F8
0x1400185d4  xor     r9d, r9d; RequestedAddress
0x1400185d7  mov     [rsp+58h+Priority], 40000010h; Priority
0x1400185df  xor     edx, edx; AccessMode
0x1400185e1  mov     [rsp+58h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1400185e5  lea     r8d, [r9+1]; CacheType
0x1400185e9  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400185f0  nop     dword ptr [rax+rax+00h]
0x1400185f5  mov     rbx, rax
0x1400185f8  mov     ecx, [rbp+40h]
0x1400185fb  and     cl, 2
0x1400185fe  mov     [rsp+58h+arg_0], rbx
0x140018603  neg     cl
0x140018605  mov     rcx, [rbp+18h]; MemoryDescriptorList
0x140018609  sbb     edx, edx
0x14001860b  and     edx, 10h
0x14001860e  add     edx, 10h
0x140018611  test    byte ptr [rcx+0Ah], 5
0x140018615  jz      short loc_14001861D
0x140018617  mov     rax, [rcx+18h]
0x14001861b  jmp     short loc_14001863E
0x14001861d  bts     edx, 1Eh
0x140018621  xor     r9d, r9d; RequestedAddress
0x140018624  mov     [rsp+58h+Priority], edx; Priority
0x140018628  xor     edx, edx; AccessMode
0x14001862a  mov     [rsp+58h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14001862e  lea     r8d, [r9+1]; CacheType
0x140018632  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140018639  nop     dword ptr [rax+rax+00h]
0x14001863e  test    rax, rax
0x140018641  jz      short loc_140018657
0x140018643  mov     r8d, [r13+8]; Size
0x140018647  mov     rdx, rax; Src
0x14001864a  mov     rcx, rbx; void *
0x14001864d  call    memmove
0x140018652  jmp     loc_1400186D7
0x140018657  lea     rsi, [r15+160h]
0x14001865e  mov     rcx, rsi; SpinLock
0x140018661  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018668  nop     dword ptr [rax+rax+00h]
0x14001866d  mov     r8, [rbp+18h]; MemoryDescriptorList
0x140018671  mov     r9d, 1; CacheType
0x140018677  mov     rcx, [r15+158h]; MappingAddress
0x14001867e  mov     edx, 6D526D56h; PoolTag
0x140018683  mov     dil, al
0x140018686  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x14001868d  nop     dword ptr [rax+rax+00h]
0x140018692  mov     r8d, [r13+8]; Size
0x140018696  mov     rdx, rax; Src
0x140018699  mov     rcx, [rsp+58h+arg_0]; void *
0x14001869e  mov     rbx, rax
0x1400186a1  call    memmove
0x1400186a6  mov     r8, [rbp+18h]; MemoryDescriptorList
0x1400186aa  mov     edx, 6D526D56h; PoolTag
0x1400186af  mov     rcx, rbx; BaseAddress
0x1400186b2  call    cs:__imp_MmUnmapReservedMapping
0x1400186b9  nop     dword ptr [rax+rax+00h]
0x1400186be  mov     dl, dil; NewIrql
0x1400186c1  mov     rcx, rsi; SpinLock
0x1400186c4  call    cs:__imp_KeReleaseSpinLock
0x1400186cb  nop     dword ptr [rax+rax+00h]
0x1400186d0  mov     rbx, [rsp+58h+arg_0]
0x1400186d5  xor     esi, esi
0x1400186d7  mov     rcx, [rbp+110h]; MemoryDescriptorList
0x1400186de  lea     rax, ?VmxpRaid5WriteStripePhase5@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5WriteStripePhase5(VMX_TRANSFER_PACKET *)
0x1400186e5  mov     [r12+18h], rcx
0x1400186ea  mov     [r12+28h], rax
0x1400186ef  test    byte ptr [rcx+0Ah], 5
0x1400186f3  jz      short loc_1400186FB
0x1400186f5  mov     rax, [rcx+18h]
0x1400186f9  jmp     short loc_14001871C
0x1400186fb  xor     r9d, r9d; RequestedAddress
0x1400186fe  mov     [rsp+58h+Priority], 40000010h; Priority
0x140018706  xor     edx, edx; AccessMode
0x140018708  mov     [rsp+58h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14001870c  lea     r8d, [r9+1]; CacheType
0x140018710  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140018717  nop     dword ptr [rax+rax+00h]
0x14001871c  mov     r8d, [r12+8]; unsigned int
0x140018721  mov     rdx, rbx; void *
0x140018724  mov     rcx, rax; void *
0x140018727  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x14001872c  cmp     dword ptr [rbp+120h], 4
0x140018733  mov     rax, [r12+30h]
0x140018738  jz      short loc_140018795
0x14001873a  test    rax, rax
0x14001873d  jz      short loc_140018760
0x14001873f  test    byte ptr [rbp+51h], 8
0x140018743  mov     dword ptr [rbp+80h], 2
0x14001874d  jnz     short loc_140018778
0x14001874f  lea     rcx, [r15+0A0h]; this
0x140018756  mov     rdx, r12; struct VMX_RAID5_PARITY_TRANSFER_PACKET *
0x140018759  call    ?UpdateParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z; VMX_PARITY_IO_MANAGER::UpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)
0x14001875e  jmp     short loc_140018778
0x140018760  mov     dword ptr [rbp+80h], 1
0x14001876a  mov     dword ptr [r12+60h], 0C000000Eh
0x140018773  mov     [r12+68h], rsi
0x140018778  mov     rcx, [r13+30h]
0x14001877c  mov     rdx, r13
0x14001877f  mov     dword ptr [r13+0Ch], 2020004h
0x140018787  mov     rax, [rcx]
0x14001878a  mov     rax, [rax+8]
0x14001878e  call    _guard_dispatch_icall
0x140018793  jmp     short loc_1400187D8
0x140018795  test    rax, rax
0x140018798  jz      short loc_1400187C1
0x14001879a  mov     dword ptr [rbp+80h], 1
0x1400187a4  lea     rcx, [r15+0A0h]; this
0x1400187ab  mov     rdx, r12; struct VMX_RAID5_PARITY_TRANSFER_PACKET *
0x1400187ae  mov     dword ptr [r13+60h], 0C000000Eh
0x1400187b6  mov     [r13+68h], rsi
0x1400187ba  call    ?UpdateParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z; VMX_PARITY_IO_MANAGER::UpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)
0x1400187bf  jmp     short loc_1400187D8
0x1400187c1  mov     dword ptr [rbp+60h], 0C000000Eh
0x1400187c8  mov     [rbp+68h], rsi
0x1400187cc  mov     rax, [rbp+28h]
0x1400187d0  mov     rcx, rbp
0x1400187d3  call    _guard_dispatch_icall
0x1400187d8  mov     rbx, [rsp+58h+arg_8]
0x1400187dd  mov     rbp, [rsp+58h+arg_10]
0x1400187e2  add     rsp, 30h
0x1400187e6  pop     r15
0x1400187e8  pop     r13
0x1400187ea  pop     r12
0x1400187ec  pop     rdi
0x1400187ed  pop     rsi
0x1400187ee  retn
```
