# VmxpRaid5RecoverReadStripePhase8(VMX_TRANSFER_PACKET *)

- ea: `0x140015ca0`
- end: `0x140015f09`
- name: `?VmxpRaid5RecoverReadStripePhase8@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `617`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400110f8`
- `0x140015ca0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015dd5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015dd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e47`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015e47`
- `ntoskrnl!RtlCompareMemory` at `0x140015db7`
- `ntoskrnl!RtlCompareMemory` at `0x140015e1a`
- `ntoskrnl!RtlCompareMemory` at `0x140015db7`
- `ntoskrnl!RtlCompareMemory` at `0x140015e1a`
- `ntoskrnl!IoBuildPartialMdl` at `0x140015ed1`
- `ntoskrnl!IoBuildPartialMdl` at `0x140015ed1`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140015e02`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140015e02`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140015e35`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140015e35`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140015ccf`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140015ccf`
- `ntoskrnl!MmUnmapLockedPages` at `0x140015ea8`
- `ntoskrnl!MmUnmapLockedPages` at `0x140015ea8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015d4a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015d99`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015d4a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015d99`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverReadStripePhase8(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // r14
  NTSTATUS v3; // ebx
  KSPIN_LOCK *v4; // rdi
  ULONG *v5; // r15
  PMDL *v6; // r12
  __int64 v7; // rcx
  PVOID v8; // r13
  __int64 v9; // r10
  PVOID v10; // rax
  int v11; // r13d
  KSPIN_LOCK *v12; // rsi
  KIRQL v13; // di
  PVOID v14; // rbx
  __int64 v15; // rdx
  PMDL v16; // rcx
  __int64 v17; // rcx
  KSPIN_LOCK *v18; // [rsp+80h] [rbp+8h]

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(KSPIN_LOCK **)(v1 + 232);
  v18 = v4;
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
  {
    v5 = (ULONG *)((char *)a1 + 8);
    v6 = (PMDL *)((char *)a1 + 272);
LABEL_16:
    *(_DWORD *)(v1 + 96) = 1073741834;
    goto LABEL_17;
  }
  v7 = *((_QWORD *)a1 + 35);
  if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
    v8 = *(PVOID *)(v7 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u);
  v6 = (PMDL *)((char *)a1 + 272);
  v9 = *((_QWORD *)a1 + 34);
  if ( (*(_BYTE *)(v9 + 10) & 5) != 0 )
    v10 = *(PVOID *)(v9 + 24);
  else
    v10 = MmMapLockedPagesSpecifyCache(
            (PMDL)v9,
            0,
            MmCached,
            0,
            0,
            ((*((_DWORD *)a1 + 16) & 2) != 0 ? 32 : 16) | 0x40000000u);
  v5 = (ULONG *)((char *)a1 + 8);
  if ( v10 )
  {
    v11 = RtlCompareMemory(v10, v8, *v5);
  }
  else
  {
    v12 = v4 + 44;
    v13 = KeAcquireSpinLockRaiseToDpc(v4 + 44);
    v14 = MmMapLockedPagesWithReservedMapping((PVOID)v18[43], 0x6D526D56u, *v6, MmCached);
    v11 = RtlCompareMemory(v14, v8, *v5);
    MmUnmapReservedMapping(v14, 0x6D526D56u, *v6);
    KeReleaseSpinLock(v12, v13);
    v4 = v18;
  }
  if ( v11 != *v5 )
    goto LABEL_16;
LABEL_17:
  v15 = *((_QWORD *)a1 + 2) + *v5;
  if ( v15 == *(_QWORD *)(v1 + 16) + *(unsigned int *)(v1 + 8) )
    goto LABEL_3;
  v16 = *v6;
  *((_QWORD *)a1 + 3) = *v6;
  *((_QWORD *)a1 + 2) = v15;
  *((_QWORD *)a1 + 5) = VmxpRaid5RecoverReadStripePhase2;
  *((_BYTE *)a1 + 82) = 1;
  if ( (v16->MdlFlags & 0x20) != 0 )
    MmUnmapLockedPages(v16->MappedSystemVa, v16);
  IoBuildPartialMdl(
    *(PMDL *)(v1 + 24),
    *((PMDL *)a1 + 3),
    (PVOID)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 32LL)
          + *(unsigned int *)(*(_QWORD *)(v1 + 24) + 44LL)
          + (unsigned __int64)(unsigned int)(*((_DWORD *)a1 + 4) - *(_DWORD *)(v1 + 16))),
    *v5);
  v17 = *((_QWORD *)a1 + 6);
  *((_DWORD *)a1 + 3) = 33619971;
  (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v17 + 8LL))(v17, a1);
}

```

## disassembly

```asm
0x140015ca0  push    rbx
0x140015ca2  push    rbp
0x140015ca3  push    rsi
0x140015ca4  push    rdi
0x140015ca5  push    r12
0x140015ca7  push    r13
0x140015ca9  push    r14
0x140015cab  push    r15
0x140015cad  sub     rsp, 38h
0x140015cb1  mov     r14, [rcx+0E0h]
0x140015cb8  mov     rbp, rcx
0x140015cbb  mov     ebx, [rcx+60h]
0x140015cbe  mov     ecx, ebx; Status
0x140015cc0  mov     rdi, [r14+0E8h]
0x140015cc7  mov     [rsp+78h+arg_0], rdi
0x140015ccf  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140015cd6  nop     dword ptr [rax+rax+00h]
0x140015cdb  xor     esi, esi
0x140015cdd  test    al, al
0x140015cdf  jz      short loc_140015D0E
0x140015ce1  mov     [r14+108h], sil
0x140015ce8  movups  xmm0, xmmword ptr [rbp+60h]
0x140015cec  movdqu  xmmword ptr [r14+60h], xmm0
0x140015cf2  mov     rdx, rbp; struct VMX_RAID5_RECOVER_TRANSFER_PACKET *
0x140015cf5  mov     rcx, rdi; this
0x140015cf8  call    ?RecycleRecoverPacket@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_RECOVER_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::RecycleRecoverPacket(VMX_RAID5_RECOVER_TRANSFER_PACKET *)
0x140015cfd  mov     rax, [r14+28h]
0x140015d01  mov     rcx, r14
0x140015d04  call    _guard_dispatch_icall
0x140015d09  jmp     loc_140015EF7
0x140015d0e  test    ebx, ebx
0x140015d10  jns     short loc_140015D22
0x140015d12  lea     r15, [rbp+8]
0x140015d16  lea     r12, [rbp+110h]
0x140015d1d  jmp     loc_140015E60
0x140015d22  mov     rcx, [rbp+118h]; MemoryDescriptorList
0x140015d29  test    byte ptr [rcx+0Ah], 5
0x140015d2d  jz      short loc_140015D35
0x140015d2f  mov     r13, [rcx+18h]
0x140015d33  jmp     short loc_140015D59
0x140015d35  xor     r9d, r9d; RequestedAddress
0x140015d38  mov     [rsp+78h+Priority], 40000010h; Priority
0x140015d40  xor     edx, edx; AccessMode
0x140015d42  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x140015d46  lea     r8d, [r9+1]; CacheType
0x140015d4a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140015d51  nop     dword ptr [rax+rax+00h]
0x140015d56  mov     r13, rax
0x140015d59  mov     ecx, [rbp+40h]
0x140015d5c  lea     r12, [rbp+110h]
0x140015d63  mov     r10, [r12]
0x140015d67  and     cl, 2
0x140015d6a  neg     cl
0x140015d6c  sbb     edx, edx
0x140015d6e  and     edx, 10h
0x140015d71  add     edx, 10h
0x140015d74  test    byte ptr [r10+0Ah], 5
0x140015d79  jz      short loc_140015D81
0x140015d7b  mov     rax, [r10+18h]
0x140015d7f  jmp     short loc_140015DA5
0x140015d81  bts     edx, 1Eh
0x140015d85  xor     r9d, r9d; RequestedAddress
0x140015d88  mov     [rsp+78h+Priority], edx; Priority
0x140015d8c  mov     rcx, r10; MemoryDescriptorList
0x140015d8f  xor     edx, edx; AccessMode
0x140015d91  mov     [rsp+78h+BugCheckOnFailure], esi; BugCheckOnFailure
0x140015d95  lea     r8d, [r9+1]; CacheType
0x140015d99  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140015da0  nop     dword ptr [rax+rax+00h]
0x140015da5  lea     r15, [rbp+8]
0x140015da9  test    rax, rax
0x140015dac  jz      short loc_140015DCB
0x140015dae  mov     r8d, [r15]; Length
0x140015db1  mov     rdx, r13; Source2
0x140015db4  mov     rcx, rax; Source1
0x140015db7  call    cs:__imp_RtlCompareMemory
0x140015dbe  nop     dword ptr [rax+rax+00h]
0x140015dc3  mov     r13, rax
0x140015dc6  jmp     loc_140015E5B
0x140015dcb  lea     rsi, [rdi+160h]
0x140015dd2  mov     rcx, rsi; SpinLock
0x140015dd5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015ddc  nop     dword ptr [rax+rax+00h]
0x140015de1  mov     rcx, [rsp+78h+arg_0]
0x140015de9  mov     r9d, 1; CacheType
0x140015def  mov     r8, [r12]; MemoryDescriptorList
0x140015df3  mov     edx, 6D526D56h; PoolTag
0x140015df8  mov     dil, al
0x140015dfb  mov     rcx, [rcx+158h]; MappingAddress
0x140015e02  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140015e09  nop     dword ptr [rax+rax+00h]
0x140015e0e  mov     r8d, [r15]; Length
0x140015e11  mov     rdx, r13; Source2
0x140015e14  mov     rcx, rax; Source1
0x140015e17  mov     rbx, rax
0x140015e1a  call    cs:__imp_RtlCompareMemory
0x140015e21  nop     dword ptr [rax+rax+00h]
0x140015e26  mov     r8, [r12]; MemoryDescriptorList
0x140015e2a  mov     edx, 6D526D56h; PoolTag
0x140015e2f  mov     rcx, rbx; BaseAddress
0x140015e32  mov     r13, rax
0x140015e35  call    cs:__imp_MmUnmapReservedMapping
0x140015e3c  nop     dword ptr [rax+rax+00h]
0x140015e41  mov     dl, dil; NewIrql
0x140015e44  mov     rcx, rsi; SpinLock
0x140015e47  call    cs:__imp_KeReleaseSpinLock
0x140015e4e  nop     dword ptr [rax+rax+00h]
0x140015e53  mov     rdi, [rsp+78h+arg_0]
0x140015e5b  cmp     r13d, [r15]
0x140015e5e  jz      short loc_140015E68
0x140015e60  mov     dword ptr [r14+60h], 4000000Ah
0x140015e68  mov     edx, [r15]
0x140015e6b  mov     eax, [r14+8]
0x140015e6f  add     rdx, [rbp+10h]
0x140015e73  add     rax, [r14+10h]
0x140015e77  cmp     rdx, rax
0x140015e7a  jz      loc_140015CF2
0x140015e80  mov     rcx, [r12]
0x140015e84  lea     rax, ?VmxpRaid5RecoverReadStripePhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverReadStripePhase2(VMX_TRANSFER_PACKET *)
0x140015e8b  mov     [rbp+18h], rcx
0x140015e8f  mov     [rbp+10h], rdx
0x140015e93  mov     [rbp+28h], rax
0x140015e97  mov     byte ptr [rbp+52h], 1
0x140015e9b  test    byte ptr [rcx+0Ah], 20h
0x140015e9f  jz      short loc_140015EB4
0x140015ea1  mov     rdx, rcx; MemoryDescriptorList
0x140015ea4  mov     rcx, [rcx+18h]; BaseAddress
0x140015ea8  call    cs:__imp_MmUnmapLockedPages
0x140015eaf  nop     dword ptr [rax+rax+00h]
0x140015eb4  mov     rcx, [r14+18h]; SourceMdl
0x140015eb8  mov     r8d, [rbp+10h]
0x140015ebc  sub     r8d, [r14+10h]
0x140015ec0  mov     r9d, [r15]; Length
0x140015ec3  mov     eax, [rcx+2Ch]
0x140015ec6  mov     rdx, [rbp+18h]; TargetMdl
0x140015eca  add     r8, rax
0x140015ecd  add     r8, [rcx+20h]; VirtualAddress
0x140015ed1  call    cs:__imp_IoBuildPartialMdl
0x140015ed8  nop     dword ptr [rax+rax+00h]
0x140015edd  mov     rcx, [rbp+30h]
0x140015ee1  mov     rdx, rbp
0x140015ee4  mov     dword ptr [rbp+0Ch], 2010003h
0x140015eeb  mov     rax, [rcx]
0x140015eee  mov     rax, [rax+8]
0x140015ef2  call    _guard_dispatch_icall
0x140015ef7  add     rsp, 38h
0x140015efb  pop     r15
0x140015efd  pop     r14
0x140015eff  pop     r13
0x140015f01  pop     r12
0x140015f03  pop     rdi
0x140015f04  pop     rsi
0x140015f05  pop     rbp
0x140015f06  pop     rbx
0x140015f07  retn
```
