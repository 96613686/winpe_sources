# VmxpRaid5ParallelReconstructStripeCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140014950`
- end: `0x140014d57`
- name: `?VmxpRaid5ParallelReconstructStripeCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `1031`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140007828`
- `0x14000d0dc`
- `0x140012560`
- `0x140014950`
- `0x140018fcc`
- `0x14001b9a0`
- `0x14001bb80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014980`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a04`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a5f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014cea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014980`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a04`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a5f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014cea`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014be8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014be8`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140014bac`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140014d0f`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140014bac`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140014d0f`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140014bd6`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140014bd6`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400149a9`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400149a9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014b0f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014b5b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014c6f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014cbb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014b0f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014b5b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014c6f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140014cbb`

## pseudocode

```c
void __fastcall VmxpRaid5ParallelReconstructStripeCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbp
  NTSTATUS v3; // ebx
  __int64 v4; // r13
  KSPIN_LOCK *v5; // rdi
  KIRQL v6; // r14
  __int64 v7; // r8
  KIRQL v8; // al
  __int64 v9; // rdx
  KIRQL v10; // r11
  int v11; // ebx
  _QWORD *v12; // r14
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // r15
  __int64 v16; // r10
  __int64 v17; // rcx
  const void *v18; // r12
  PVOID v19; // rax
  PVOID v20; // rax
  KSPIN_LOCK *v21; // rsi
  KIRQL v22; // di
  PVOID v23; // rbx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r10
  __int64 v27; // rcx
  void *v28; // r12
  PVOID v29; // rax
  PVOID v30; // rax

  v1 = *((_QWORD *)a1 + 17);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 + 232);
  if ( v3 < 0 )
  {
    if ( FsRtlIsTotalDeviceFailure(v3) && v3 != -2147483626 )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 29, v7, v4, v3);
      }
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v9 = *((unsigned int *)a1 + 36);
      v10 = v8;
      if ( *(_DWORD *)(*(_QWORD *)(v4 + 112) + 24 * v9 + 16) != 4
        && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v4, v9, 1) )
      {
        ++*(_DWORD *)(*(_QWORD *)(v1 + 256) + 168LL);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v10);
    }
    v5 = (KSPIN_LOCK *)(v1 + 88);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 88));
    if ( VmxpIsWorseStatus(v3, *(_DWORD *)(v1 + 96)) )
    {
      *(_DWORD *)(v1 + 96) = v3;
      *(_QWORD *)(v1 + 104) = 0;
    }
  }
  else
  {
    v5 = (KSPIN_LOCK *)(v1 + 88);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 88));
    if ( *(int *)(v1 + 96) >= 0 )
      *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
  }
  v11 = --*(_DWORD *)(v1 + 128);
  KeReleaseSpinLock(v5, v6);
  if ( !v11 )
  {
    v12 = (_QWORD *)(v1 + 112);
    v13 = *(_QWORD **)(v1 + 112);
    if ( v13[1] != v1 + 112 || (v14 = *v13, *(_QWORD **)(*v13 + 8LL) != v13) )
LABEL_47:
      __fastfail(3u);
    *v12 = v14;
    v15 = v13 - 19;
    *(_QWORD *)(v14 + 8) = v12;
    v16 = *(_QWORD *)(v1 + 24);
    if ( v16 )
    {
      v17 = v15[3];
      if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
      {
        v18 = *(const void **)(v17 + 24);
      }
      else
      {
        v19 = MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000010u);
        v16 = *(_QWORD *)(v1 + 24);
        v18 = v19;
      }
      if ( (*(_BYTE *)(v16 + 10) & 5) != 0 )
        v20 = *(PVOID *)(v16 + 24);
      else
        v20 = MmMapLockedPagesSpecifyCache(
                (PMDL)v16,
                0,
                MmCached,
                0,
                0,
                ((*(_DWORD *)(v1 + 64) & 2) != 0 ? 32 : 16) | 0x40000000u);
      if ( !v20 )
      {
        v21 = (KSPIN_LOCK *)(v4 + 352);
        v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 352));
        v23 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 344), 0x6D526D56u, *(PMDL *)(v1 + 24), MmCached);
        memmove(v23, v18, *(unsigned int *)(v1 + 8));
        goto LABEL_29;
      }
      memmove(v20, v18, *(unsigned int *)(v1 + 8));
    }
    while ( 1 )
    {
      if ( v15 )
        (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
      v24 = (_QWORD *)*v12;
      if ( (_QWORD *)*v12 == v12 )
        break;
      if ( (_QWORD *)v24[1] != v12 )
        goto LABEL_47;
      v25 = *v24;
      if ( *(_QWORD **)(*v24 + 8LL) != v24 )
        goto LABEL_47;
      *v12 = v25;
      v15 = v24 - 19;
      *(_QWORD *)(v25 + 8) = v12;
      v26 = *(_QWORD *)(v1 + 24);
      if ( v26 )
      {
        v27 = v15[3];
        if ( (*(_BYTE *)(v27 + 10) & 5) != 0 )
        {
          v28 = *(void **)(v27 + 24);
        }
        else
        {
          v29 = MmMapLockedPagesSpecifyCache((PMDL)v27, 0, MmCached, 0, 0, 0x40000010u);
          v26 = *(_QWORD *)(v1 + 24);
          v28 = v29;
        }
        if ( (*(_BYTE *)(v26 + 10) & 5) != 0 )
          v30 = *(PVOID *)(v26 + 24);
        else
          v30 = MmMapLockedPagesSpecifyCache(
                  (PMDL)v26,
                  0,
                  MmCached,
                  0,
                  0,
                  ((*(_DWORD *)(v1 + 64) & 2) != 0 ? 32 : 16) | 0x40000000u);
        if ( v30 )
        {
          VmxpComputeParity(v30, v28, *(_DWORD *)(v1 + 8));
        }
        else
        {
          v21 = (KSPIN_LOCK *)(v4 + 352);
          v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 352));
          v23 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 344), 0x6D526D56u, *(PMDL *)(v1 + 24), MmCached);
          VmxpComputeParity(v23, v28, *(_DWORD *)(v1 + 8));
LABEL_29:
          MmUnmapReservedMapping(v23, 0x6D526D56u, *(PMDL *)(v1 + 24));
          KeReleaseSpinLock(v21, v22);
        }
      }
    }
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
  }
}

```

## disassembly

```asm
0x140014950  push    rbx
0x140014952  push    rbp
0x140014953  push    rsi
0x140014954  push    rdi
0x140014955  push    r12
0x140014957  push    r13
0x140014959  push    r14
0x14001495b  push    r15
0x14001495d  sub     rsp, 38h
0x140014961  mov     rbp, [rcx+88h]
0x140014968  mov     rsi, rcx
0x14001496b  mov     ebx, [rcx+60h]
0x14001496e  mov     r13, [rbp+0E8h]
0x140014975  test    ebx, ebx
0x140014977  js      short loc_1400149A7
0x140014979  lea     rdi, [rbp+58h]
0x14001497d  mov     rcx, rdi; SpinLock
0x140014980  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014987  nop     dword ptr [rax+rax+00h]
0x14001498c  cmp     dword ptr [rbp+60h], 0
0x140014990  mov     r14b, al
0x140014993  jl      loc_140014A87
0x140014999  movups  xmm0, xmmword ptr [rsi+60h]
0x14001499d  movdqu  xmmword ptr [rbp+60h], xmm0
0x1400149a2  jmp     loc_140014A87
0x1400149a7  mov     ecx, ebx; Status
0x1400149a9  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x1400149b0  nop     dword ptr [rax+rax+00h]
0x1400149b5  test    al, al
0x1400149b7  jz      loc_140014A58
0x1400149bd  cmp     ebx, 80000016h
0x1400149c3  jz      loc_140014A58
0x1400149c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400149d0  lea     rax, WPP_GLOBAL_Control
0x1400149d7  cmp     rcx, rax
0x1400149da  jz      short loc_140014A00
0x1400149dc  test    dword ptr [rcx+2Ch], 1000h
0x1400149e3  jz      short loc_140014A00
0x1400149e5  cmp     byte ptr [rcx+29h], 3
0x1400149e9  jb      short loc_140014A00
0x1400149eb  mov     rcx, [rcx+18h]
0x1400149ef  mov     edx, 1Dh
0x1400149f4  mov     r9, r13
0x1400149f7  mov     [rsp+78h+BugCheckOnFailure], ebx
0x1400149fb  call    WPP_SF_qd
0x140014a00  lea     rcx, [r13+18h]; SpinLock
0x140014a04  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014a0b  nop     dword ptr [rax+rax+00h]
0x140014a10  mov     edx, [rsi+90h]; unsigned int
0x140014a16  mov     r11b, al
0x140014a19  mov     rcx, [r13+70h]
0x140014a1d  lea     r8, [rdx+rdx*2]
0x140014a21  cmp     dword ptr [rcx+r8*8+10h], 4
0x140014a27  jz      short loc_140014A45
0x140014a29  mov     r8b, 1; unsigned __int8
0x140014a2c  mov     rcx, r13; this
0x140014a2f  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x140014a34  test    al, al
0x140014a36  jz      short loc_140014A45
0x140014a38  mov     rax, [rbp+100h]
0x140014a3f  inc     dword ptr [rax+0A8h]
0x140014a45  mov     dl, r11b; NewIrql
0x140014a48  lea     rcx, [r13+18h]; SpinLock
0x140014a4c  call    cs:__imp_KeReleaseSpinLock
0x140014a53  nop     dword ptr [rax+rax+00h]
0x140014a58  lea     rdi, [rbp+58h]
0x140014a5c  mov     rcx, rdi; SpinLock
0x140014a5f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014a66  nop     dword ptr [rax+rax+00h]
0x140014a6b  mov     edx, [rbp+60h]; NTSTATUS
0x140014a6e  mov     ecx, ebx; Status
0x140014a70  mov     r14b, al
0x140014a73  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x140014a78  test    al, al
0x140014a7a  jz      short loc_140014A87
0x140014a7c  mov     [rbp+60h], ebx
0x140014a7f  mov     qword ptr [rbp+68h], 0
0x140014a87  dec     dword ptr [rbp+80h]
0x140014a8d  mov     dl, r14b; NewIrql
0x140014a90  mov     ebx, [rbp+80h]
0x140014a96  mov     rcx, rdi; SpinLock
0x140014a99  call    cs:__imp_KeReleaseSpinLock
0x140014aa0  nop     dword ptr [rax+rax+00h]
0x140014aa5  test    ebx, ebx
0x140014aa7  jnz     loc_140014D3E
0x140014aad  lea     r14, [rbp+70h]
0x140014ab1  mov     rax, [r14]
0x140014ab4  cmp     [rax+8], r14
0x140014ab8  jnz     loc_140014D50
0x140014abe  mov     rcx, [rax]
0x140014ac1  cmp     [rcx+8], rax
0x140014ac5  jnz     loc_140014D50
0x140014acb  mov     [r14], rcx
0x140014ace  lea     r15, [rax-98h]
0x140014ad5  mov     [rcx+8], r14
0x140014ad9  mov     r10, [rbp+18h]
0x140014add  test    r10, r10
0x140014ae0  jz      loc_140014BF4
0x140014ae6  mov     rcx, [r15+18h]; MemoryDescriptorList
0x140014aea  test    byte ptr [rcx+0Ah], 5
0x140014aee  jz      short loc_140014AF6
0x140014af0  mov     r12, [rcx+18h]
0x140014af4  jmp     short loc_140014B22
0x140014af6  xor     r9d, r9d; RequestedAddress
0x140014af9  mov     [rsp+78h+Priority], 40000010h; Priority
0x140014b01  xor     edx, edx; AccessMode
0x140014b03  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140014b0b  lea     r8d, [r9+1]; CacheType
0x140014b0f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140014b16  nop     dword ptr [rax+rax+00h]
0x140014b1b  mov     r10, [rbp+18h]
0x140014b1f  mov     r12, rax
0x140014b22  mov     ecx, [rbp+40h]
0x140014b25  and     cl, 2
0x140014b28  neg     cl
0x140014b2a  sbb     edx, edx
0x140014b2c  and     edx, 10h
0x140014b2f  add     edx, 10h
0x140014b32  test    byte ptr [r10+0Ah], 5
0x140014b37  jz      short loc_140014B3F
0x140014b39  mov     rax, [r10+18h]
0x140014b3d  jmp     short loc_140014B67
0x140014b3f  bts     edx, 1Eh
0x140014b43  xor     r9d, r9d; RequestedAddress
0x140014b46  mov     [rsp+78h+Priority], edx; Priority
0x140014b4a  mov     rcx, r10; MemoryDescriptorList
0x140014b4d  xor     edx, edx; AccessMode
0x140014b4f  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140014b57  lea     r8d, [r9+1]; CacheType
0x140014b5b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140014b62  nop     dword ptr [rax+rax+00h]
0x140014b67  test    rax, rax
0x140014b6a  jz      short loc_140014B7D
0x140014b6c  mov     r8d, [rbp+8]; Size
0x140014b70  mov     rdx, r12; Src
0x140014b73  mov     rcx, rax; void *
0x140014b76  call    memmove
0x140014b7b  jmp     short loc_140014BF4
0x140014b7d  lea     rsi, [r13+160h]
0x140014b84  mov     rcx, rsi; SpinLock
0x140014b87  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014b8e  nop     dword ptr [rax+rax+00h]
0x140014b93  mov     r8, [rbp+18h]; MemoryDescriptorList
0x140014b97  mov     r9d, 1; CacheType
0x140014b9d  mov     rcx, [r13+158h]; MappingAddress
0x140014ba4  mov     edx, 6D526D56h; PoolTag
0x140014ba9  mov     dil, al
0x140014bac  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140014bb3  nop     dword ptr [rax+rax+00h]
0x140014bb8  mov     r8d, [rbp+8]; Size
0x140014bbc  mov     rdx, r12; Src
0x140014bbf  mov     rcx, rax; void *
0x140014bc2  mov     rbx, rax
0x140014bc5  call    memmove
0x140014bca  mov     r8, [rbp+18h]; MemoryDescriptorList
0x140014bce  mov     edx, 6D526D56h; PoolTag
0x140014bd3  mov     rcx, rbx; BaseAddress
0x140014bd6  call    cs:__imp_MmUnmapReservedMapping
0x140014bdd  nop     dword ptr [rax+rax+00h]
0x140014be2  mov     dl, dil; NewIrql
0x140014be5  mov     rcx, rsi; SpinLock
0x140014be8  call    cs:__imp_KeReleaseSpinLock
0x140014bef  nop     dword ptr [rax+rax+00h]
0x140014bf4  test    r15, r15
0x140014bf7  jz      short loc_140014C0C
0x140014bf9  mov     rax, [r15]
0x140014bfc  mov     edx, 1
0x140014c01  mov     rcx, r15
0x140014c04  mov     rax, [rax]
0x140014c07  call    _guard_dispatch_icall
0x140014c0c  mov     rax, [r14]
0x140014c0f  cmp     rax, r14
0x140014c12  jz      loc_140014D32
0x140014c18  cmp     [rax+8], r14
0x140014c1c  jnz     loc_140014D50
0x140014c22  mov     rcx, [rax]
0x140014c25  cmp     [rcx+8], rax
0x140014c29  jnz     loc_140014D50
0x140014c2f  mov     [r14], rcx
0x140014c32  lea     r15, [rax-98h]
0x140014c39  mov     [rcx+8], r14
0x140014c3d  mov     r10, [rbp+18h]
0x140014c41  test    r10, r10
0x140014c44  jz      short loc_140014BF4
0x140014c46  mov     rcx, [r15+18h]; MemoryDescriptorList
0x140014c4a  test    byte ptr [rcx+0Ah], 5
0x140014c4e  jz      short loc_140014C56
0x140014c50  mov     r12, [rcx+18h]
0x140014c54  jmp     short loc_140014C82
0x140014c56  xor     r9d, r9d; RequestedAddress
0x140014c59  mov     [rsp+78h+Priority], 40000010h; Priority
0x140014c61  xor     edx, edx; AccessMode
0x140014c63  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140014c6b  lea     r8d, [r9+1]; CacheType
0x140014c6f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140014c76  nop     dword ptr [rax+rax+00h]
0x140014c7b  mov     r10, [rbp+18h]
0x140014c7f  mov     r12, rax
0x140014c82  mov     ecx, [rbp+40h]
0x140014c85  and     cl, 2
0x140014c88  neg     cl
0x140014c8a  sbb     edx, edx
0x140014c8c  and     edx, 10h
0x140014c8f  add     edx, 10h
0x140014c92  test    byte ptr [r10+0Ah], 5
0x140014c97  jz      short loc_140014C9F
0x140014c99  mov     rax, [r10+18h]
0x140014c9d  jmp     short loc_140014CC7
0x140014c9f  bts     edx, 1Eh
0x140014ca3  xor     r9d, r9d; RequestedAddress
0x140014ca6  mov     [rsp+78h+Priority], edx; Priority
0x140014caa  mov     rcx, r10; MemoryDescriptorList
0x140014cad  xor     edx, edx; AccessMode
0x140014caf  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140014cb7  lea     r8d, [r9+1]; CacheType
0x140014cbb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140014cc2  nop     dword ptr [rax+rax+00h]
0x140014cc7  test    rax, rax
0x140014cca  jz      short loc_140014CE0
0x140014ccc  mov     r8d, [rbp+8]; unsigned int
0x140014cd0  mov     rdx, r12; void *
0x140014cd3  mov     rcx, rax; void *
0x140014cd6  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x140014cdb  jmp     loc_140014BF4
0x140014ce0  lea     rsi, [r13+160h]
0x140014ce7  mov     rcx, rsi; SpinLock
0x140014cea  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014cf1  nop     dword ptr [rax+rax+00h]
0x140014cf6  mov     r8, [rbp+18h]; MemoryDescriptorList
0x140014cfa  mov     r9d, 1; CacheType
0x140014d00  mov     rcx, [r13+158h]; MappingAddress
0x140014d07  mov     edx, 6D526D56h; PoolTag
0x140014d0c  mov     dil, al
0x140014d0f  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140014d16  nop     dword ptr [rax+rax+00h]
0x140014d1b  mov     r8d, [rbp+8]; unsigned int
0x140014d1f  mov     rdx, r12; void *
0x140014d22  mov     rcx, rax; void *
0x140014d25  mov     rbx, rax
0x140014d28  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x140014d2d  jmp     loc_140014BCA
0x140014d32  mov     rax, [rbp+28h]
0x140014d36  mov     rcx, rbp
0x140014d39  call    _guard_dispatch_icall
0x140014d3e  add     rsp, 38h
0x140014d42  pop     r15
0x140014d44  pop     r14
0x140014d46  pop     r13
0x140014d48  pop     r12
0x140014d4a  pop     rdi
0x140014d4b  pop     rsi
0x140014d4c  pop     rbp
0x140014d4d  pop     rbx
0x140014d4e  retn
0x140014d50  mov     ecx, 3
0x140014d55  int     29h; Win8: RtlFailFast(ecx)
```
