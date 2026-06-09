# VmxpMirrorRecoverReadPhase3(VMX_TRANSFER_PACKET *)

- ea: `0x140012f80`
- end: `0x140013273`
- name: `?VmxpMirrorRecoverReadPhase3@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `755`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140003774`
- `0x140003cf0`
- `0x14000d078`
- `0x140012f80`
- `0x140013898`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012fea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001305d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013163`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012fea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001305d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013163`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001303f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400131c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001303f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400130a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400131c9`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14001318b`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14001318b`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400131b7`
- `ntoskrnl!MmUnmapReservedMapping` at `0x1400131b7`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140012fba`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140012fba`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013138`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013138`

## pseudocode

```c
void __fastcall VmxpMirrorRecoverReadPhase3(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // r14
  NTSTATUS v2; // ebx
  __int64 v4; // r15
  KSPIN_LOCK *v5; // rdi
  KIRQL v6; // al
  __int64 v7; // rdx
  KIRQL v8; // bl
  __int64 v9; // rax
  __int128 v10; // xmm6
  KIRQL v11; // al
  unsigned int v12; // r9d
  __int64 v13; // rbx
  __int64 v14; // r8
  __int64 v15; // r10
  PVOID v16; // rax
  KIRQL v17; // di
  PVOID v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // rcx
  void (__fastcall *v21)(struct VMX_TRANSFER_PACKET *); // rax
  unsigned int v22; // eax
  __int128 v23; // [rsp+30h] [rbp-58h]

  v1 = *((_QWORD *)a1 + 28);
  v2 = *((_DWORD *)a1 + 24);
  DWORD1(v23) = 0;
  v4 = *(_QWORD *)(v1 + 232);
  if ( v2 >= 0 )
  {
    v22 = *(_DWORD *)(v1 + 240);
    *((_DWORD *)a1 + 60) = v22;
    v20 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8LL * v22);
    v21 = VmxpMirrorRecoverReadPhase4;
    *((_BYTE *)a1 + 82) = 0;
    *((_DWORD *)a1 + 3) = 16842758;
    goto LABEL_30;
  }
  if ( !FsRtlIsTotalDeviceFailure(v2) || v2 == -2147483626 )
  {
    v10 = *((_OWORD *)a1 + 6);
    v5 = (KSPIN_LOCK *)(v4 + 24);
  }
  else
  {
    v5 = (KSPIN_LOCK *)(v4 + 24);
    LODWORD(v23) = -1073741668;
    *((_QWORD *)&v23 + 1) = 0;
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
    v7 = *((unsigned int *)a1 + 60);
    v8 = v6;
    if ( *(_DWORD *)(*(_QWORD *)(v4 + 96) + 40 * v7 + 16) != 4
      && VMX_IO_MIRROR::DetachFaultTolerantMember((VMX_IO_MIRROR *)v4, v7, 1) )
    {
      v9 = *(_QWORD *)(v1 + 224);
      if ( *(_BYTE *)(v1 + 273) )
        v9 = *(_QWORD *)(v9 + 128);
      ++*(_DWORD *)(v9 + 168);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v8);
    v10 = v23;
  }
  v11 = KeAcquireSpinLockRaiseToDpc(v5);
  v12 = *(_DWORD *)(v4 + 56);
  v13 = (unsigned int)(*((_DWORD *)a1 + 60) + 1);
  if ( (unsigned int)v13 < v12 )
  {
    v14 = *(_QWORD *)(v4 + 96) + 40 * v13;
    do
    {
      if ( (_DWORD)v13 != *(_DWORD *)(v1 + 240) && !*(_DWORD *)(v14 + 16) )
        break;
      v13 = (unsigned int)(v13 + 1);
      v14 += 40;
    }
    while ( (unsigned int)v13 < v12 );
  }
  KeReleaseSpinLock(v5, v11);
  if ( (_DWORD)v13 != *(_DWORD *)(v4 + 56) )
  {
    *((_DWORD *)a1 + 60) = v13;
    v20 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8 * v13);
    v21 = VmxpMirrorRecoverReadPhase3;
    *((_DWORD *)a1 + 3) = 16842757;
LABEL_30:
    *((_QWORD *)a1 + 5) = v21;
    *((_QWORD *)a1 + 6) = v20;
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v20 + 8LL))(v20, a1);
    return;
  }
  if ( *(_BYTE *)(v1 + 273) )
  {
    v15 = *((_QWORD *)a1 + 37);
    if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
      v16 = *(PVOID *)(v15 + 24);
    else
      v16 = MmMapLockedPagesSpecifyCache(
              (PMDL)v15,
              0,
              MmCached,
              0,
              0,
              ((*((_DWORD *)a1 + 16) & 2) != 0 ? 32 : 16) | 0x40000000u);
    if ( v16 )
    {
      memset(v16, 0, *((unsigned int *)a1 + 2));
    }
    else
    {
      v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 224));
      v18 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 216), 0x6D4D6D56u, *((PMDL *)a1 + 37), MmCached);
      memset(v18, 0, *((unsigned int *)a1 + 2));
      MmUnmapReservedMapping(v18, 0x6D4D6D56u, *((PMDL *)a1 + 37));
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 224), v17);
    }
    v19 = *(_DWORD *)(v1 + 240);
    *(_DWORD *)(v1 + 96) = -2143813631;
    *((_DWORD *)a1 + 60) = v19;
    *((_QWORD *)a1 + 6) = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8LL * v19);
    VmxpMirrorRecoverReadPhase9(a1);
  }
  else
  {
    *(_OWORD *)(v1 + 96) = v10;
    if ( !*(_BYTE *)(v1 + 274) )
      VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(
        (VMX_OVERLAPPED_IO_MANAGER *)(v4 + 104),
        (struct VMX_OVERLAP_TRANSFER_PACKET *)v1);
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    VMX_IO_MIRROR::RecyclePacket((VMX_IO_MIRROR *)v4, a1);
  }
}

```

## disassembly

```asm
0x140012f80  push    rbx
0x140012f82  push    rbp
0x140012f83  push    rsi
0x140012f84  push    rdi
0x140012f85  push    r14
0x140012f87  push    r15
0x140012f89  sub     rsp, 58h
0x140012f8d  mov     r14, [rcx+0E0h]
0x140012f94  xor     esi, esi
0x140012f96  mov     ebx, [rcx+60h]
0x140012f99  xorps   xmm0, xmm0
0x140012f9c  movaps  [rsp+88h+var_48], xmm6
0x140012fa1  mov     rbp, rcx
0x140012fa4  movups  [rsp+88h+var_58], xmm0
0x140012fa9  mov     r15, [r14+0E8h]
0x140012fb0  test    ebx, ebx
0x140012fb2  jns     loc_140013220
0x140012fb8  mov     ecx, ebx; Status
0x140012fba  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140012fc1  nop     dword ptr [rax+rax+00h]
0x140012fc6  test    al, al
0x140012fc8  jz      loc_140013052
0x140012fce  cmp     ebx, 80000016h
0x140012fd4  jz      short loc_140013052
0x140012fd6  lea     rdi, [r15+18h]
0x140012fda  mov     dword ptr [rsp+88h+var_58], 0C000009Ch
0x140012fe2  mov     rcx, rdi; SpinLock
0x140012fe5  mov     qword ptr [rsp+88h+var_58+8], rsi
0x140012fea  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012ff1  nop     dword ptr [rax+rax+00h]
0x140012ff6  mov     edx, [rbp+0F0h]; unsigned int
0x140012ffc  mov     bl, al
0x140012ffe  mov     rcx, [r15+60h]
0x140013002  lea     r8, [rdx+rdx*4]
0x140013006  cmp     dword ptr [rcx+r8*8+10h], 4
0x14001300c  jz      short loc_14001303A
0x14001300e  mov     r8b, 1; unsigned __int8
0x140013011  mov     rcx, r15; this
0x140013014  call    ?DetachFaultTolerantMember@VMX_IO_MIRROR@@QEAAEKE@Z; VMX_IO_MIRROR::DetachFaultTolerantMember(ulong,uchar)
0x140013019  test    al, al
0x14001301b  jz      short loc_14001303A
0x14001301d  mov     rax, [r14+0E0h]
0x140013024  cmp     [r14+111h], sil
0x14001302b  jz      short loc_140013034
0x14001302d  mov     rax, [rax+80h]
0x140013034  inc     dword ptr [rax+0A8h]
0x14001303a  mov     dl, bl; NewIrql
0x14001303c  mov     rcx, rdi; SpinLock
0x14001303f  call    cs:__imp_KeReleaseSpinLock
0x140013046  nop     dword ptr [rax+rax+00h]
0x14001304b  movups  xmm6, [rsp+88h+var_58]
0x140013050  jmp     short loc_14001305A
0x140013052  movups  xmm6, xmmword ptr [rbp+60h]
0x140013056  lea     rdi, [r15+18h]
0x14001305a  mov     rcx, rdi; SpinLock
0x14001305d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013064  nop     dword ptr [rax+rax+00h]
0x140013069  mov     ebx, [rbp+0F0h]
0x14001306f  mov     r9d, [r15+38h]
0x140013073  inc     ebx
0x140013075  cmp     ebx, r9d
0x140013078  jnb     short loc_1400130A2
0x14001307a  mov     rcx, [r15+60h]
0x14001307e  lea     rdx, [rbx+rbx*4]
0x140013082  lea     r8, [rcx+rdx*8]
0x140013086  mov     ecx, [r14+0F0h]
0x14001308d  cmp     ebx, ecx
0x14001308f  jz      short loc_140013097
0x140013091  cmp     [r8+10h], esi
0x140013095  jz      short loc_1400130A2
0x140013097  inc     ebx
0x140013099  add     r8, 28h ; '('
0x14001309d  cmp     ebx, r9d
0x1400130a0  jb      short loc_14001308D
0x1400130a2  mov     dl, al; NewIrql
0x1400130a4  mov     rcx, rdi; SpinLock
0x1400130a7  call    cs:__imp_KeReleaseSpinLock
0x1400130ae  nop     dword ptr [rax+rax+00h]
0x1400130b3  cmp     ebx, [r15+38h]
0x1400130b7  jnz     loc_140013202
0x1400130bd  cmp     [r14+111h], sil
0x1400130c4  jnz     short loc_1400130FD
0x1400130c6  movdqu  xmmword ptr [r14+60h], xmm6
0x1400130cc  cmp     [r14+112h], sil
0x1400130d3  jnz     short loc_1400130E1
0x1400130d5  lea     rcx, [r15+68h]; this
0x1400130d9  mov     rdx, r14; struct VMX_OVERLAP_TRANSFER_PACKET *
0x1400130dc  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x1400130e1  mov     rax, [r14+28h]
0x1400130e5  mov     rcx, r14
0x1400130e8  call    _guard_dispatch_icall
0x1400130ed  mov     rdx, rbp; struct VMX_MIRROR_TRANSFER_PACKET *
0x1400130f0  mov     rcx, r15; this
0x1400130f3  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x1400130f8  jmp     loc_140013260
0x1400130fd  mov     eax, [rbp+40h]
0x140013100  mov     r10, [rbp+128h]
0x140013107  and     al, 2
0x140013109  neg     al
0x14001310b  sbb     ecx, ecx
0x14001310d  and     ecx, 10h
0x140013110  add     ecx, 10h
0x140013113  test    byte ptr [r10+0Ah], 5
0x140013118  jz      short loc_140013120
0x14001311a  mov     rax, [r10+18h]
0x14001311e  jmp     short loc_140013144
0x140013120  bts     ecx, 1Eh
0x140013124  xor     r9d, r9d; RequestedAddress
0x140013127  mov     [rsp+88h+Priority], ecx; Priority
0x14001312b  xor     edx, edx; AccessMode
0x14001312d  mov     rcx, r10; MemoryDescriptorList
0x140013130  mov     [rsp+88h+BugCheckOnFailure], esi; BugCheckOnFailure
0x140013134  lea     r8d, [r9+1]; CacheType
0x140013138  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001313f  nop     dword ptr [rax+rax+00h]
0x140013144  test    rax, rax
0x140013147  jz      short loc_140013159
0x140013149  mov     r8d, [rbp+8]; Size
0x14001314d  xor     edx, edx; Val
0x14001314f  mov     rcx, rax; void *
0x140013152  call    memset
0x140013157  jmp     short loc_1400131D5
0x140013159  lea     rsi, [r15+0E0h]
0x140013160  mov     rcx, rsi; SpinLock
0x140013163  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001316a  nop     dword ptr [rax+rax+00h]
0x14001316f  mov     r8, [rbp+128h]; MemoryDescriptorList
0x140013176  mov     r9d, 1; CacheType
0x14001317c  mov     rcx, [r15+0D8h]; MappingAddress
0x140013183  mov     edx, 6D4D6D56h; PoolTag
0x140013188  mov     dil, al
0x14001318b  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140013192  nop     dword ptr [rax+rax+00h]
0x140013197  mov     r8d, [rbp+8]; Size
0x14001319b  xor     edx, edx; Val
0x14001319d  mov     rcx, rax; void *
0x1400131a0  mov     rbx, rax
0x1400131a3  call    memset
0x1400131a8  mov     r8, [rbp+128h]; MemoryDescriptorList
0x1400131af  mov     edx, 6D4D6D56h; PoolTag
0x1400131b4  mov     rcx, rbx; BaseAddress
0x1400131b7  call    cs:__imp_MmUnmapReservedMapping
0x1400131be  nop     dword ptr [rax+rax+00h]
0x1400131c3  mov     dl, dil; NewIrql
0x1400131c6  mov     rcx, rsi; SpinLock
0x1400131c9  call    cs:__imp_KeReleaseSpinLock
0x1400131d0  nop     dword ptr [rax+rax+00h]
0x1400131d5  mov     eax, [r14+0F0h]
0x1400131dc  mov     dword ptr [r14+60h], 80380001h
0x1400131e4  mov     ecx, eax
0x1400131e6  mov     [rbp+0F0h], eax
0x1400131ec  mov     rax, [r15+30h]
0x1400131f0  mov     rcx, [rax+rcx*8]
0x1400131f4  mov     [rbp+30h], rcx
0x1400131f8  mov     rcx, rbp; struct VMX_TRANSFER_PACKET *
0x1400131fb  call    ?VmxpMirrorRecoverReadPhase9@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase9(VMX_TRANSFER_PACKET *)
0x140013200  jmp     short loc_140013260
0x140013202  mov     [rbp+0F0h], ebx
0x140013208  mov     rax, [r15+30h]
0x14001320c  mov     rcx, [rax+rbx*8]
0x140013210  lea     rax, ?VmxpMirrorRecoverReadPhase3@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase3(VMX_TRANSFER_PACKET *)
0x140013217  mov     dword ptr [rbp+0Ch], 1010005h
0x14001321e  jmp     short loc_140013249
0x140013220  mov     eax, [r14+0F0h]
0x140013227  mov     [rcx+0F0h], eax
0x14001322d  mov     ecx, eax
0x14001322f  mov     rax, [r15+30h]
0x140013233  mov     rcx, [rax+rcx*8]
0x140013237  lea     rax, ?VmxpMirrorRecoverReadPhase4@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase4(VMX_TRANSFER_PACKET *)
0x14001323e  mov     [rbp+52h], sil
0x140013242  mov     dword ptr [rbp+0Ch], 1010006h
0x140013249  mov     [rbp+28h], rax
0x14001324d  mov     rdx, rbp
0x140013250  mov     [rbp+30h], rcx
0x140013254  mov     rax, [rcx]
0x140013257  mov     rax, [rax+8]
0x14001325b  call    _guard_dispatch_icall
0x140013260  movaps  xmm6, [rsp+88h+var_48]
0x140013265  add     rsp, 58h
0x140013269  pop     r15
0x14001326b  pop     r14
0x14001326d  pop     rdi
0x14001326e  pop     rsi
0x14001326f  pop     rbp
0x140013270  pop     rbx
0x140013271  retn
```
