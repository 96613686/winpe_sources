# VmxpRaid5RecoverReadStripePhase5(VMX_TRANSFER_PACKET *)

- ea: `0x1400157f0`
- end: `0x140015a51`
- name: `?VmxpRaid5RecoverReadStripePhase5@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `609`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400110f8`
- `0x1400157f0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001592d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001592d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001599b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001599b`
- `ntoskrnl!RtlCompareMemory` at `0x14001590f`
- `ntoskrnl!RtlCompareMemory` at `0x14001596b`
- `ntoskrnl!RtlCompareMemory` at `0x14001590f`
- `ntoskrnl!RtlCompareMemory` at `0x14001596b`
- `ntoskrnl!IoBuildPartialMdl` at `0x140015a1b`
- `ntoskrnl!IoBuildPartialMdl` at `0x140015a1b`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140015952`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140015952`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140015989`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140015989`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140015815`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140015815`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400159f1`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400159f1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400158aa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400158f4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400158aa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400158f4`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverReadStripePhase5(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // r14
  NTSTATUS v3; // ebx
  __int64 v4; // r13
  __int64 v5; // rcx
  __int64 v6; // rcx
  PVOID v7; // r15
  __int64 v8; // r10
  PVOID v9; // rax
  int v10; // r15d
  KIRQL v11; // di
  PVOID v12; // rbx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 + 232);
  if ( FsRtlIsTotalDeviceFailure(v3) )
  {
    *(_BYTE *)(v1 + 264) = 0;
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
LABEL_3:
    VMX_IO_RAID5::RecycleRecoverPacket((VMX_IO_RAID5 *)v4, a1);
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    return;
  }
  if ( v3 < 0 )
    goto LABEL_5;
  v6 = *((_QWORD *)a1 + 35);
  v7 = (*(_BYTE *)(v6 + 10) & 5) != 0
     ? *(PVOID *)(v6 + 24)
     : MmMapLockedPagesSpecifyCache((PMDL)v6, 0, MmCached, 0, 0, 0x40000010u);
  v8 = *((_QWORD *)a1 + 34);
  v9 = (*(_BYTE *)(v8 + 10) & 5) != 0
     ? *(PVOID *)(v8 + 24)
     : MmMapLockedPagesSpecifyCache(
         (PMDL)v8,
         0,
         MmCached,
         0,
         0,
         ((*((_DWORD *)a1 + 16) & 2) != 0 ? 32 : 16) | 0x40000000u);
  if ( v9 )
  {
    v10 = RtlCompareMemory(v9, v7, *((unsigned int *)a1 + 2));
  }
  else
  {
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 352));
    v12 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 344), 0x6D526D56u, *((PMDL *)a1 + 34), MmCached);
    v10 = RtlCompareMemory(v12, v7, *((unsigned int *)a1 + 2));
    MmUnmapReservedMapping(v12, 0x6D526D56u, *((PMDL *)a1 + 34));
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 352), v11);
  }
  v13 = *((_DWORD *)a1 + 2);
  if ( v10 == v13 )
  {
    v14 = *((_QWORD *)a1 + 2) + v13;
    if ( v14 == *(_QWORD *)(v1 + 16) + *(unsigned int *)(v1 + 8) )
      goto LABEL_3;
    v15 = *((_QWORD *)a1 + 34);
    *((_QWORD *)a1 + 3) = v15;
    *((_QWORD *)a1 + 2) = v14;
    *((_QWORD *)a1 + 5) = VmxpRaid5RecoverReadStripePhase2;
    if ( (*(_BYTE *)(v15 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v15 + 24), (PMDL)v15);
    IoBuildPartialMdl(
      *(PMDL *)(v1 + 24),
      *((PMDL *)a1 + 3),
      (PVOID)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 32LL)
            + *(unsigned int *)(*(_QWORD *)(v1 + 24) + 44LL)
            + (unsigned __int64)(unsigned int)(*((_DWORD *)a1 + 4) - *(_DWORD *)(v1 + 16))),
      *((_DWORD *)a1 + 2));
    v16 = *((_QWORD *)a1 + 6);
    *((_DWORD *)a1 + 3) = 33619971;
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v16 + 8LL))(v16, a1);
  }
  else
  {
LABEL_5:
    v5 = *((_QWORD *)a1 + 6);
    *((_QWORD *)a1 + 3) = *((_QWORD *)a1 + 34);
    *((_QWORD *)a1 + 5) = VmxpRaid5RecoverReadStripePhase6;
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v5 + 16LL))(v5, a1);
  }
}

```

## disassembly

```asm
0x1400157f0  push    rbx
0x1400157f2  push    rbp
0x1400157f3  push    rsi
0x1400157f4  push    rdi
0x1400157f5  push    r13
0x1400157f7  push    r14
0x1400157f9  push    r15
0x1400157fb  sub     rsp, 30h
0x1400157ff  mov     r14, [rcx+0E0h]
0x140015806  mov     rbp, rcx
0x140015809  mov     ebx, [rcx+60h]
0x14001580c  mov     ecx, ebx; Status
0x14001580e  mov     r13, [r14+0E8h]
0x140015815  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x14001581c  nop     dword ptr [rax+rax+00h]
0x140015821  xor     edi, edi
0x140015823  test    al, al
0x140015825  jz      short loc_140015854
0x140015827  mov     [r14+108h], dil
0x14001582e  movups  xmm0, xmmword ptr [rbp+60h]
0x140015832  movdqu  xmmword ptr [r14+60h], xmm0
0x140015838  mov     rdx, rbp; struct VMX_RAID5_RECOVER_TRANSFER_PACKET *
0x14001583b  mov     rcx, r13; this
0x14001583e  call    ?RecycleRecoverPacket@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_RECOVER_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::RecycleRecoverPacket(VMX_RAID5_RECOVER_TRANSFER_PACKET *)
0x140015843  mov     rax, [r14+28h]
0x140015847  mov     rcx, r14
0x14001584a  call    _guard_dispatch_icall
0x14001584f  jmp     loc_140015A41
0x140015854  test    ebx, ebx
0x140015856  jns     short loc_14001587E
0x140015858  mov     rax, [rbp+110h]
0x14001585f  mov     rcx, [rbp+30h]
0x140015863  mov     [rbp+18h], rax
0x140015867  lea     rax, ?VmxpRaid5RecoverReadStripePhase6@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverReadStripePhase6(VMX_TRANSFER_PACKET *)
0x14001586e  mov     [rbp+28h], rax
0x140015872  mov     rax, [rcx]
0x140015875  mov     rax, [rax+10h]
0x140015879  jmp     loc_140015A39
0x14001587e  mov     rcx, [rbp+118h]; MemoryDescriptorList
0x140015885  mov     ebx, 1
0x14001588a  test    byte ptr [rcx+0Ah], 5
0x14001588e  jz      short loc_140015896
0x140015890  mov     r15, [rcx+18h]
0x140015894  jmp     short loc_1400158B9
0x140015896  mov     [rsp+68h+Priority], 40000010h; Priority
0x14001589e  xor     r9d, r9d; RequestedAddress
0x1400158a1  mov     r8d, ebx; CacheType
0x1400158a4  mov     [rsp+68h+BugCheckOnFailure], edi; BugCheckOnFailure
0x1400158a8  xor     edx, edx; AccessMode
0x1400158aa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400158b1  nop     dword ptr [rax+rax+00h]
0x1400158b6  mov     r15, rax
0x1400158b9  mov     ecx, [rbp+40h]
0x1400158bc  mov     r10, [rbp+110h]
0x1400158c3  and     cl, 2
0x1400158c6  neg     cl
0x1400158c8  sbb     edx, edx
0x1400158ca  and     edx, 10h
0x1400158cd  add     edx, 10h
0x1400158d0  test    byte ptr [r10+0Ah], 5
0x1400158d5  jz      short loc_1400158DD
0x1400158d7  mov     rax, [r10+18h]
0x1400158db  jmp     short loc_140015900
0x1400158dd  bts     edx, 1Eh
0x1400158e1  xor     r9d, r9d; RequestedAddress
0x1400158e4  mov     [rsp+68h+Priority], edx; Priority
0x1400158e8  mov     r8d, ebx; CacheType
0x1400158eb  xor     edx, edx; AccessMode
0x1400158ed  mov     [rsp+68h+BugCheckOnFailure], edi; BugCheckOnFailure
0x1400158f1  mov     rcx, r10; MemoryDescriptorList
0x1400158f4  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400158fb  nop     dword ptr [rax+rax+00h]
0x140015900  test    rax, rax
0x140015903  jz      short loc_140015923
0x140015905  mov     r8d, [rbp+8]; Length
0x140015909  mov     rdx, r15; Source2
0x14001590c  mov     rcx, rax; Source1
0x14001590f  call    cs:__imp_RtlCompareMemory
0x140015916  nop     dword ptr [rax+rax+00h]
0x14001591b  mov     r15, rax
0x14001591e  jmp     loc_1400159A7
0x140015923  lea     rsi, [r13+160h]
0x14001592a  mov     rcx, rsi; SpinLock
0x14001592d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015934  nop     dword ptr [rax+rax+00h]
0x140015939  mov     r8, [rbp+110h]; MemoryDescriptorList
0x140015940  mov     r9d, ebx; CacheType
0x140015943  mov     rcx, [r13+158h]; MappingAddress
0x14001594a  mov     edx, 6D526D56h; PoolTag
0x14001594f  mov     dil, al
0x140015952  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140015959  nop     dword ptr [rax+rax+00h]
0x14001595e  mov     r8d, [rbp+8]; Length
0x140015962  mov     rdx, r15; Source2
0x140015965  mov     rcx, rax; Source1
0x140015968  mov     rbx, rax
0x14001596b  call    cs:__imp_RtlCompareMemory
0x140015972  nop     dword ptr [rax+rax+00h]
0x140015977  mov     r8, [rbp+110h]; MemoryDescriptorList
0x14001597e  mov     edx, 6D526D56h; PoolTag
0x140015983  mov     rcx, rbx; BaseAddress
0x140015986  mov     r15, rax
0x140015989  call    cs:__imp_MmUnmapReservedMapping
0x140015990  nop     dword ptr [rax+rax+00h]
0x140015995  mov     dl, dil; NewIrql
0x140015998  mov     rcx, rsi; SpinLock
0x14001599b  call    cs:__imp_KeReleaseSpinLock
0x1400159a2  nop     dword ptr [rax+rax+00h]
0x1400159a7  mov     eax, [rbp+8]
0x1400159aa  cmp     r15d, eax
0x1400159ad  jnz     loc_140015858
0x1400159b3  mov     edx, eax
0x1400159b5  mov     eax, [r14+8]
0x1400159b9  add     rax, [r14+10h]
0x1400159bd  add     rdx, [rbp+10h]
0x1400159c1  cmp     rdx, rax
0x1400159c4  jz      loc_140015838
0x1400159ca  mov     rcx, [rbp+110h]
0x1400159d1  lea     rax, ?VmxpRaid5RecoverReadStripePhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverReadStripePhase2(VMX_TRANSFER_PACKET *)
0x1400159d8  mov     [rbp+18h], rcx
0x1400159dc  mov     [rbp+10h], rdx
0x1400159e0  mov     [rbp+28h], rax
0x1400159e4  test    byte ptr [rcx+0Ah], 20h
0x1400159e8  jz      short loc_1400159FD
0x1400159ea  mov     rdx, rcx; MemoryDescriptorList
0x1400159ed  mov     rcx, [rcx+18h]; BaseAddress
0x1400159f1  call    cs:__imp_MmUnmapLockedPages
0x1400159f8  nop     dword ptr [rax+rax+00h]
0x1400159fd  mov     rcx, [r14+18h]; SourceMdl
0x140015a01  mov     r8d, [rbp+10h]
0x140015a05  sub     r8d, [r14+10h]
0x140015a09  mov     r9d, [rbp+8]; Length
0x140015a0d  mov     eax, [rcx+2Ch]
0x140015a10  mov     rdx, [rbp+18h]; TargetMdl
0x140015a14  add     r8, rax
0x140015a17  add     r8, [rcx+20h]; VirtualAddress
0x140015a1b  call    cs:__imp_IoBuildPartialMdl
0x140015a22  nop     dword ptr [rax+rax+00h]
0x140015a27  mov     rcx, [rbp+30h]
0x140015a2b  mov     dword ptr [rbp+0Ch], 2010003h
0x140015a32  mov     rax, [rcx]
0x140015a35  mov     rax, [rax+8]
0x140015a39  mov     rdx, rbp
0x140015a3c  call    _guard_dispatch_icall
0x140015a41  add     rsp, 30h
0x140015a45  pop     r15
0x140015a47  pop     r14
0x140015a49  pop     r13
0x140015a4b  pop     rdi
0x140015a4c  pop     rsi
0x140015a4d  pop     rbp
0x140015a4e  pop     rbx
0x140015a4f  retn
```
