# VmxpRaid5SequentialReconstructStripeCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140017110`
- end: `0x14001741a`
- name: `?VmxpRaid5SequentialReconstructStripeCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `778`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140007828`
- `0x14000d0dc`
- `0x140012560`
- `0x140017110`
- `0x140018fcc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400171af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400172cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400173a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400171af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400172cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400173a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400171f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001732d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400173f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400171f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001732d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400173f1`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400172f1`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400172f1`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14001731b`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14001731b`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140017154`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140017154`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017258`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400172a0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017258`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400172a0`

## pseudocode

```c
void __fastcall VmxpRaid5SequentialReconstructStripeCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbp
  NTSTATUS v2; // ebx
  __int64 v4; // r15
  __int64 v5; // r8
  KIRQL v6; // al
  __int64 v7; // rdx
  KIRQL v8; // r11
  __int64 v9; // r10
  int v10; // r13d
  __int64 v11; // rcx
  void *v12; // r12
  PVOID v13; // rax
  PVOID v14; // rax
  KIRQL v15; // di
  PVOID v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // rcx
  KIRQL v19; // al
  _QWORD *v20; // rdx
  KIRQL v21; // r8
  _QWORD *v22; // rcx
  _QWORD *v23; // rbx
  __int64 v24; // rax

  v1 = *((_QWORD *)a1 + 17);
  v2 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 + 232);
  if ( v2 < 0 )
  {
    if ( FsRtlIsTotalDeviceFailure(v2) && v2 != -2147483626 )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 3), 28, v5, v4, v2);
      }
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v7 = *((unsigned int *)a1 + 36);
      v8 = v6;
      if ( *(_DWORD *)(*(_QWORD *)(v4 + 112) + 24 * v7 + 16) != 4
        && VMX_IO_RAID5::DetachFaultTolerantMember((VMX_IO_RAID5 *)v4, v7, 1) )
      {
        ++*(_DWORD *)(*(_QWORD *)(v1 + 256) + 168LL);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v8);
    }
    if ( VmxpIsWorseStatus(v2, *(_DWORD *)(v1 + 96)) )
    {
      *(_DWORD *)(v1 + 96) = v2;
      *(_QWORD *)(v1 + 104) = 0;
    }
  }
  else if ( *(int *)(v1 + 96) >= 0 )
  {
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
  }
  --*(_DWORD *)(v1 + 128);
  v9 = *(_QWORD *)(v1 + 24);
  v10 = *(_DWORD *)(v1 + 128);
  if ( v9 )
  {
    v11 = *((_QWORD *)a1 + 3);
    if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
    {
      v12 = *(void **)(v11 + 24);
    }
    else
    {
      v13 = MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000010u);
      v9 = *(_QWORD *)(v1 + 24);
      v12 = v13;
    }
    if ( (*(_BYTE *)(v9 + 10) & 5) != 0 )
      v14 = *(PVOID *)(v9 + 24);
    else
      v14 = MmMapLockedPagesSpecifyCache(
              (PMDL)v9,
              0,
              MmCached,
              0,
              0,
              ((*(_DWORD *)(v1 + 64) & 2) != 0 ? 32 : 16) | 0x40000000u);
    if ( v14 )
    {
      VmxpComputeParity(v14, v12, *(_DWORD *)(v1 + 8));
    }
    else
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 352));
      v16 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 344), 0x6D526D56u, *(PMDL *)(v1 + 24), MmCached);
      VmxpComputeParity(v16, v12, *(_DWORD *)(v1 + 8));
      MmUnmapReservedMapping(v16, 0x6D526D56u, *(PMDL *)(v1 + 24));
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 352), v15);
    }
  }
  if ( v10 )
  {
    v17 = ++*((_DWORD *)a1 + 36);
    if ( v17 == *(_DWORD *)(v1 + 240) )
      *((_DWORD *)a1 + 36) = ++v17;
    v18 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8LL * v17);
    *((_QWORD *)a1 + 6) = v18;
    *((_DWORD *)a1 + 3) = 33619970;
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v18 + 8LL))(v18, a1);
  }
  else
  {
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
    v20 = (_QWORD *)(v4 + 304);
    v21 = v19;
    v22 = *(_QWORD **)(v4 + 304);
    if ( v22 == (_QWORD *)(v4 + 304) )
    {
      *(_BYTE *)(v4 + 266) = 0;
      v23 = 0;
    }
    else
    {
      if ( (_QWORD *)v22[1] != v20 || (v24 = *v22, *(_QWORD **)(*v22 + 8LL) != v22) )
        __fastfail(3u);
      *v20 = v24;
      v23 = v22 - 14;
      *(_QWORD *)(v24 + 8) = v20;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v21);
    if ( v23 )
      ((void (__fastcall *)(_QWORD *))v23[5])(v23);
  }
}

```

## disassembly

```asm
0x140017110  push    rbx
0x140017112  push    rbp
0x140017113  push    rsi
0x140017114  push    rdi
0x140017115  push    r12
0x140017117  push    r13
0x140017119  push    r14
0x14001711b  push    r15
0x14001711d  sub     rsp, 38h
0x140017121  mov     rbp, [rcx+88h]
0x140017128  xor     esi, esi
0x14001712a  mov     ebx, [rcx+60h]
0x14001712d  mov     r14, rcx
0x140017130  mov     r15, [rbp+0E8h]
0x140017137  test    ebx, ebx
0x140017139  js      short loc_140017152
0x14001713b  cmp     [rbp+60h], esi
0x14001713e  jl      loc_140017219
0x140017144  movups  xmm0, xmmword ptr [rcx+60h]
0x140017148  movdqu  xmmword ptr [rbp+60h], xmm0
0x14001714d  jmp     loc_140017219
0x140017152  mov     ecx, ebx; Status
0x140017154  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x14001715b  nop     dword ptr [rax+rax+00h]
0x140017160  test    al, al
0x140017162  jz      loc_140017204
0x140017168  cmp     ebx, 80000016h
0x14001716e  jz      loc_140017204
0x140017174  mov     rcx, cs:WPP_GLOBAL_Control
0x14001717b  lea     rax, WPP_GLOBAL_Control
0x140017182  cmp     rcx, rax
0x140017185  jz      short loc_1400171AB
0x140017187  test    dword ptr [rcx+2Ch], 1000h
0x14001718e  jz      short loc_1400171AB
0x140017190  cmp     byte ptr [rcx+29h], 3
0x140017194  jb      short loc_1400171AB
0x140017196  mov     rcx, [rcx+18h]
0x14001719a  mov     edx, 1Ch
0x14001719f  mov     r9, r15
0x1400171a2  mov     [rsp+78h+BugCheckOnFailure], ebx
0x1400171a6  call    WPP_SF_qd
0x1400171ab  lea     rcx, [r15+18h]; SpinLock
0x1400171af  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400171b6  nop     dword ptr [rax+rax+00h]
0x1400171bb  mov     edx, [r14+90h]; unsigned int
0x1400171c2  mov     r11b, al
0x1400171c5  mov     rcx, [r15+70h]
0x1400171c9  lea     r8, [rdx+rdx*2]
0x1400171cd  cmp     dword ptr [rcx+r8*8+10h], 4
0x1400171d3  jz      short loc_1400171F1
0x1400171d5  mov     r8b, 1; unsigned __int8
0x1400171d8  mov     rcx, r15; this
0x1400171db  call    ?DetachFaultTolerantMember@VMX_IO_RAID5@@QEAAEKE@Z; VMX_IO_RAID5::DetachFaultTolerantMember(ulong,uchar)
0x1400171e0  test    al, al
0x1400171e2  jz      short loc_1400171F1
0x1400171e4  mov     rax, [rbp+100h]
0x1400171eb  inc     dword ptr [rax+0A8h]
0x1400171f1  mov     dl, r11b; NewIrql
0x1400171f4  lea     rcx, [r15+18h]; SpinLock
0x1400171f8  call    cs:__imp_KeReleaseSpinLock
0x1400171ff  nop     dword ptr [rax+rax+00h]
0x140017204  mov     edx, [rbp+60h]; NTSTATUS
0x140017207  mov     ecx, ebx; Status
0x140017209  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x14001720e  test    al, al
0x140017210  jz      short loc_140017219
0x140017212  mov     [rbp+60h], ebx
0x140017215  mov     [rbp+68h], rsi
0x140017219  dec     dword ptr [rbp+80h]
0x14001721f  mov     r10, [rbp+18h]
0x140017223  mov     r13d, [rbp+80h]
0x14001722a  test    r10, r10
0x14001722d  jz      loc_14001733B
0x140017233  mov     rcx, [r14+18h]; MemoryDescriptorList
0x140017237  test    byte ptr [rcx+0Ah], 5
0x14001723b  jz      short loc_140017243
0x14001723d  mov     r12, [rcx+18h]
0x140017241  jmp     short loc_14001726B
0x140017243  xor     r9d, r9d; RequestedAddress
0x140017246  mov     [rsp+78h+Priority], 40000010h; Priority
0x14001724e  xor     edx, edx; AccessMode
0x140017250  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x140017254  lea     r8d, [r9+1]; CacheType
0x140017258  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001725f  nop     dword ptr [rax+rax+00h]
0x140017264  mov     r10, [rbp+18h]
0x140017268  mov     r12, rax
0x14001726b  mov     ecx, [rbp+40h]
0x14001726e  and     cl, 2
0x140017271  neg     cl
0x140017273  sbb     edx, edx
0x140017275  and     edx, 10h
0x140017278  add     edx, 10h
0x14001727b  test    byte ptr [r10+0Ah], 5
0x140017280  jz      short loc_140017288
0x140017282  mov     rax, [r10+18h]
0x140017286  jmp     short loc_1400172AC
0x140017288  bts     edx, 1Eh
0x14001728c  xor     r9d, r9d; RequestedAddress
0x14001728f  mov     [rsp+78h+Priority], edx; Priority
0x140017293  mov     rcx, r10; MemoryDescriptorList
0x140017296  xor     edx, edx; AccessMode
0x140017298  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14001729c  lea     r8d, [r9+1]; CacheType
0x1400172a0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400172a7  nop     dword ptr [rax+rax+00h]
0x1400172ac  test    rax, rax
0x1400172af  jz      short loc_1400172C2
0x1400172b1  mov     r8d, [rbp+8]; unsigned int
0x1400172b5  mov     rdx, r12; void *
0x1400172b8  mov     rcx, rax; void *
0x1400172bb  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x1400172c0  jmp     short loc_14001733B
0x1400172c2  lea     rsi, [r15+160h]
0x1400172c9  mov     rcx, rsi; SpinLock
0x1400172cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400172d3  nop     dword ptr [rax+rax+00h]
0x1400172d8  mov     r8, [rbp+18h]; MemoryDescriptorList
0x1400172dc  mov     r9d, 1; CacheType
0x1400172e2  mov     rcx, [r15+158h]; MappingAddress
0x1400172e9  mov     edx, 6D526D56h; PoolTag
0x1400172ee  mov     dil, al
0x1400172f1  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400172f8  nop     dword ptr [rax+rax+00h]
0x1400172fd  mov     r8d, [rbp+8]; unsigned int
0x140017301  mov     rdx, r12; void *
0x140017304  mov     rcx, rax; void *
0x140017307  mov     rbx, rax
0x14001730a  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x14001730f  mov     r8, [rbp+18h]; MemoryDescriptorList
0x140017313  mov     edx, 6D526D56h; PoolTag
0x140017318  mov     rcx, rbx; BaseAddress
0x14001731b  call    cs:__imp_MmUnmapReservedMapping
0x140017322  nop     dword ptr [rax+rax+00h]
0x140017327  mov     dl, dil; NewIrql
0x14001732a  mov     rcx, rsi; SpinLock
0x14001732d  call    cs:__imp_KeReleaseSpinLock
0x140017334  nop     dword ptr [rax+rax+00h]
0x140017339  xor     esi, esi
0x14001733b  test    r13d, r13d
0x14001733e  jz      short loc_140017396
0x140017340  inc     dword ptr [r14+90h]
0x140017347  mov     eax, [r14+90h]
0x14001734e  cmp     eax, [rbp+0F0h]
0x140017354  jnz     short loc_14001735F
0x140017356  inc     eax
0x140017358  mov     [r14+90h], eax
0x14001735f  mov     ecx, eax
0x140017361  mov     rdx, r14
0x140017364  mov     rax, [r15+30h]
0x140017368  mov     rcx, [rax+rcx*8]
0x14001736c  mov     [r14+30h], rcx
0x140017370  mov     dword ptr [r14+0Ch], 2010002h
0x140017378  mov     rax, [rcx]
0x14001737b  mov     rax, [rax+8]
0x14001737f  call    _guard_dispatch_icall
0x140017384  add     rsp, 38h
0x140017388  pop     r15
0x14001738a  pop     r14
0x14001738c  pop     r13
0x14001738e  pop     r12
0x140017390  pop     rdi
0x140017391  pop     rsi
0x140017392  pop     rbp
0x140017393  pop     rbx
0x140017394  retn
0x140017396  mov     rax, [rbp+28h]
0x14001739a  mov     rcx, rbp
0x14001739d  call    _guard_dispatch_icall
0x1400173a2  lea     rcx, [r15+18h]; SpinLock
0x1400173a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400173ad  nop     dword ptr [rax+rax+00h]
0x1400173b2  lea     rdx, [r15+130h]
0x1400173b9  mov     r8b, al
0x1400173bc  mov     rcx, [rdx]
0x1400173bf  cmp     rcx, rdx
0x1400173c2  jnz     short loc_1400173D0
0x1400173c4  mov     [r15+10Ah], sil
0x1400173cb  mov     rbx, rsi
0x1400173ce  jmp     short loc_1400173EA
0x1400173d0  cmp     [rcx+8], rdx
0x1400173d4  jnz     short loc_140017413
0x1400173d6  mov     rax, [rcx]
0x1400173d9  cmp     [rax+8], rcx
0x1400173dd  jnz     short loc_140017413
0x1400173df  mov     [rdx], rax
0x1400173e2  lea     rbx, [rcx-70h]
0x1400173e6  mov     [rax+8], rdx
0x1400173ea  mov     dl, r8b; NewIrql
0x1400173ed  lea     rcx, [r15+18h]; SpinLock
0x1400173f1  call    cs:__imp_KeReleaseSpinLock
0x1400173f8  nop     dword ptr [rax+rax+00h]
0x1400173fd  test    rbx, rbx
0x140017400  jz      short loc_140017384
0x140017402  mov     rax, [rbx+28h]
0x140017406  mov     rcx, rbx
0x140017409  call    _guard_dispatch_icall
0x14001740e  jmp     loc_140017384
0x140017413  mov     ecx, 3
0x140017418  int     29h; Win8: RtlFailFast(ecx)
```
