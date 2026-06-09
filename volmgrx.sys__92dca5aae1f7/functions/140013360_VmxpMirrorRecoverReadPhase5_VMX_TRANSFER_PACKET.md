# VmxpMirrorRecoverReadPhase5(VMX_TRANSFER_PACKET *)

- ea: `0x140013360`
- end: `0x14001355a`
- name: `?VmxpMirrorRecoverReadPhase5@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `506`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003774`
- `0x140003cf0`
- `0x140013360`
- `0x140013898`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400134c0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400134c0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001352e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001352e`
- `ntoskrnl!RtlCompareMemory` at `0x1400134a2`
- `ntoskrnl!RtlCompareMemory` at `0x1400134fe`
- `ntoskrnl!RtlCompareMemory` at `0x1400134a2`
- `ntoskrnl!RtlCompareMemory` at `0x1400134fe`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400134e5`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x1400134e5`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14001351c`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14001351c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140013383`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140013383`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001343d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013487`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001343d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013487`

## pseudocode

```c
void __fastcall VmxpMirrorRecoverReadPhase5(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbx
  NTSTATUS v3; // edi
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rcx
  PVOID v7; // r15
  __int64 v8; // r10
  PVOID v9; // rax
  int v10; // r14d
  KSPIN_LOCK *v11; // rsi
  KIRQL v12; // di
  PVOID v13; // rbx

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 + 232);
  if ( FsRtlIsTotalDeviceFailure(v3) )
  {
    *(_BYTE *)(v1 + 272) = 0;
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
    if ( !*(_BYTE *)(v1 + 273) && !*(_BYTE *)(v1 + 274) )
      VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(
        (VMX_OVERLAPPED_IO_MANAGER *)(v4 + 104),
        (struct VMX_OVERLAP_TRANSFER_PACKET *)v1);
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    VMX_IO_MIRROR::RecyclePacket((VMX_IO_MIRROR *)v4, a1);
  }
  else
  {
    if ( v3 < 0 )
      goto LABEL_7;
    v6 = *((_QWORD *)a1 + 38);
    v7 = (*(_BYTE *)(v6 + 10) & 5) != 0
       ? *(PVOID *)(v6 + 24)
       : MmMapLockedPagesSpecifyCache((PMDL)v6, 0, MmCached, 0, 0, 0x40000010u);
    v8 = *((_QWORD *)a1 + 37);
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
      v11 = (KSPIN_LOCK *)(v4 + 224);
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 224));
      v13 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 216), 0x6D4D6D56u, *((PMDL *)a1 + 37), MmCached);
      v10 = RtlCompareMemory(v13, v7, *((unsigned int *)a1 + 2));
      MmUnmapReservedMapping(v13, 0x6D4D6D56u, *((PMDL *)a1 + 37));
      KeReleaseSpinLock(v11, v12);
    }
    if ( v10 == *((_DWORD *)a1 + 2) )
    {
      VmxpMirrorRecoverReadPhase9(a1);
    }
    else
    {
LABEL_7:
      v5 = *((_QWORD *)a1 + 6);
      *((_QWORD *)a1 + 3) = *((_QWORD *)a1 + 37);
      *((_QWORD *)a1 + 5) = VmxpMirrorRecoverReadPhase6;
      (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v5 + 16LL))(v5, a1);
    }
  }
}

```

## disassembly

```asm
0x140013360  push    rbx
0x140013362  push    rbp
0x140013363  push    rsi
0x140013364  push    rdi
0x140013365  push    r14
0x140013367  push    r15
0x140013369  sub     rsp, 38h
0x14001336d  mov     rbx, [rcx+0E0h]
0x140013374  mov     rbp, rcx
0x140013377  mov     edi, [rcx+60h]
0x14001337a  mov     ecx, edi; Status
0x14001337c  mov     r14, [rbx+0E8h]
0x140013383  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x14001338a  nop     dword ptr [rax+rax+00h]
0x14001338f  xor     esi, esi
0x140013391  test    al, al
0x140013393  jz      short loc_1400133DF
0x140013395  mov     [rbx+110h], sil
0x14001339c  movups  xmm0, xmmword ptr [rbp+60h]
0x1400133a0  movdqu  xmmword ptr [rbx+60h], xmm0
0x1400133a5  cmp     [rbx+111h], sil
0x1400133ac  jnz     short loc_1400133C3
0x1400133ae  cmp     [rbx+112h], sil
0x1400133b5  jnz     short loc_1400133C3
0x1400133b7  lea     rcx, [r14+68h]; this
0x1400133bb  mov     rdx, rbx; struct VMX_OVERLAP_TRANSFER_PACKET *
0x1400133be  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x1400133c3  mov     rax, [rbx+28h]
0x1400133c7  mov     rcx, rbx
0x1400133ca  call    _guard_dispatch_icall
0x1400133cf  mov     rdx, rbp; struct VMX_MIRROR_TRANSFER_PACKET *
0x1400133d2  mov     rcx, r14; this
0x1400133d5  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x1400133da  jmp     loc_14001354C
0x1400133df  test    edi, edi
0x1400133e1  jns     short loc_140013411
0x1400133e3  mov     rax, [rbp+128h]
0x1400133ea  mov     rdx, rbp
0x1400133ed  mov     rcx, [rbp+30h]
0x1400133f1  mov     [rbp+18h], rax
0x1400133f5  lea     rax, ?VmxpMirrorRecoverReadPhase6@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase6(VMX_TRANSFER_PACKET *)
0x1400133fc  mov     [rbp+28h], rax
0x140013400  mov     rax, [rcx]
0x140013403  mov     rax, [rax+10h]
0x140013407  call    _guard_dispatch_icall
0x14001340c  jmp     loc_14001354C
0x140013411  mov     rcx, [rbp+130h]; MemoryDescriptorList
0x140013418  mov     ebx, 1
0x14001341d  test    byte ptr [rcx+0Ah], 5
0x140013421  jz      short loc_140013429
0x140013423  mov     r15, [rcx+18h]
0x140013427  jmp     short loc_14001344C
0x140013429  mov     [rsp+68h+Priority], 40000010h; Priority
0x140013431  xor     r9d, r9d; RequestedAddress
0x140013434  mov     r8d, ebx; CacheType
0x140013437  mov     [rsp+68h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14001343b  xor     edx, edx; AccessMode
0x14001343d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140013444  nop     dword ptr [rax+rax+00h]
0x140013449  mov     r15, rax
0x14001344c  mov     ecx, [rbp+40h]
0x14001344f  mov     r10, [rbp+128h]
0x140013456  and     cl, 2
0x140013459  neg     cl
0x14001345b  sbb     edx, edx
0x14001345d  and     edx, 10h
0x140013460  add     edx, 10h
0x140013463  test    byte ptr [r10+0Ah], 5
0x140013468  jz      short loc_140013470
0x14001346a  mov     rax, [r10+18h]
0x14001346e  jmp     short loc_140013493
0x140013470  bts     edx, 1Eh
0x140013474  xor     r9d, r9d; RequestedAddress
0x140013477  mov     [rsp+68h+Priority], edx; Priority
0x14001347b  mov     r8d, ebx; CacheType
0x14001347e  xor     edx, edx; AccessMode
0x140013480  mov     [rsp+68h+BugCheckOnFailure], esi; BugCheckOnFailure
0x140013484  mov     rcx, r10; MemoryDescriptorList
0x140013487  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001348e  nop     dword ptr [rax+rax+00h]
0x140013493  test    rax, rax
0x140013496  jz      short loc_1400134B6
0x140013498  mov     r8d, [rbp+8]; Length
0x14001349c  mov     rdx, r15; Source2
0x14001349f  mov     rcx, rax; Source1
0x1400134a2  call    cs:__imp_RtlCompareMemory
0x1400134a9  nop     dword ptr [rax+rax+00h]
0x1400134ae  mov     r14, rax
0x1400134b1  jmp     loc_14001353A
0x1400134b6  lea     rsi, [r14+0E0h]
0x1400134bd  mov     rcx, rsi; SpinLock
0x1400134c0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400134c7  nop     dword ptr [rax+rax+00h]
0x1400134cc  mov     r8, [rbp+128h]; MemoryDescriptorList
0x1400134d3  mov     r9d, ebx; CacheType
0x1400134d6  mov     rcx, [r14+0D8h]; MappingAddress
0x1400134dd  mov     edx, 6D4D6D56h; PoolTag
0x1400134e2  mov     dil, al
0x1400134e5  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x1400134ec  nop     dword ptr [rax+rax+00h]
0x1400134f1  mov     r8d, [rbp+8]; Length
0x1400134f5  mov     rdx, r15; Source2
0x1400134f8  mov     rcx, rax; Source1
0x1400134fb  mov     rbx, rax
0x1400134fe  call    cs:__imp_RtlCompareMemory
0x140013505  nop     dword ptr [rax+rax+00h]
0x14001350a  mov     r8, [rbp+128h]; MemoryDescriptorList
0x140013511  mov     edx, 6D4D6D56h; PoolTag
0x140013516  mov     rcx, rbx; BaseAddress
0x140013519  mov     r14, rax
0x14001351c  call    cs:__imp_MmUnmapReservedMapping
0x140013523  nop     dword ptr [rax+rax+00h]
0x140013528  mov     dl, dil; NewIrql
0x14001352b  mov     rcx, rsi; SpinLock
0x14001352e  call    cs:__imp_KeReleaseSpinLock
0x140013535  nop     dword ptr [rax+rax+00h]
0x14001353a  cmp     r14d, [rbp+8]
0x14001353e  jnz     loc_1400133E3
0x140013544  mov     rcx, rbp; struct VMX_TRANSFER_PACKET *
0x140013547  call    ?VmxpMirrorRecoverReadPhase9@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase9(VMX_TRANSFER_PACKET *)
0x14001354c  add     rsp, 38h
0x140013550  pop     r15
0x140013552  pop     r14
0x140013554  pop     rdi
0x140013555  pop     rsi
0x140013556  pop     rbp
0x140013557  pop     rbx
0x140013558  retn
```
