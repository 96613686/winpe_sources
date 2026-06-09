# VmxpMirrorRecoverReadPhase8(VMX_TRANSFER_PACKET *)

- ea: `0x1400136b0`
- end: `0x140013892`
- name: `?VmxpMirrorRecoverReadPhase8@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `482`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003774`
- `0x140003cf0`
- `0x1400136b0`
- `0x140013898`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400137ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400137ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013858`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013858`
- `ntoskrnl!RtlCompareMemory` at `0x1400137cc`
- `ntoskrnl!RtlCompareMemory` at `0x140013828`
- `ntoskrnl!RtlCompareMemory` at `0x1400137cc`
- `ntoskrnl!RtlCompareMemory` at `0x140013828`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14001380f`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14001380f`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140013846`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140013846`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400136d5`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400136d5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013766`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400137b1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013766`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400137b1`

## pseudocode

```c
void __fastcall VmxpMirrorRecoverReadPhase8(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbp
  NTSTATUS v3; // ebx
  __int64 v4; // r15
  __int64 v5; // rcx
  PVOID v6; // r12
  __int64 v7; // r10
  PVOID v8; // rax
  int v9; // r15d
  KSPIN_LOCK *v10; // rsi
  KIRQL v11; // di
  PVOID v12; // rbx

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
      goto LABEL_17;
    v5 = *((_QWORD *)a1 + 38);
    v6 = (*(_BYTE *)(v5 + 10) & 5) != 0
       ? *(PVOID *)(v5 + 24)
       : MmMapLockedPagesSpecifyCache((PMDL)v5, 0, MmCached, 0, 0, 0x40000010u);
    v7 = *((_QWORD *)a1 + 37);
    v8 = (*(_BYTE *)(v7 + 10) & 5) != 0
       ? *(PVOID *)(v7 + 24)
       : MmMapLockedPagesSpecifyCache(
           (PMDL)v7,
           0,
           MmCached,
           0,
           0,
           ((*((_DWORD *)a1 + 16) & 2) != 0 ? 32 : 16) | 0x40000000u);
    if ( v8 )
    {
      v9 = RtlCompareMemory(v8, v6, *((unsigned int *)a1 + 2));
    }
    else
    {
      v10 = (KSPIN_LOCK *)(v4 + 224);
      v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 224));
      v12 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 216), 0x6D4D6D56u, *((PMDL *)a1 + 37), MmCached);
      v9 = RtlCompareMemory(v12, v6, *((unsigned int *)a1 + 2));
      MmUnmapReservedMapping(v12, 0x6D4D6D56u, *((PMDL *)a1 + 37));
      KeReleaseSpinLock(v10, v11);
    }
    if ( v9 != *((_DWORD *)a1 + 2) )
    {
LABEL_17:
      if ( *(_DWORD *)(v1 + 96) != -2143813631 )
        *(_DWORD *)(v1 + 96) = 1073741834;
    }
    VmxpMirrorRecoverReadPhase9(a1);
  }
}

```

## disassembly

```asm
0x1400136b0  push    rbx
0x1400136b2  push    rbp
0x1400136b3  push    rsi
0x1400136b4  push    rdi
0x1400136b5  push    r12
0x1400136b7  push    r14
0x1400136b9  push    r15
0x1400136bb  sub     rsp, 30h
0x1400136bf  mov     rbp, [rcx+0E0h]
0x1400136c6  mov     r14, rcx
0x1400136c9  mov     ebx, [rcx+60h]
0x1400136cc  mov     ecx, ebx; Status
0x1400136ce  mov     r15, [rbp+0E8h]
0x1400136d5  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x1400136dc  nop     dword ptr [rax+rax+00h]
0x1400136e1  xor     edi, edi
0x1400136e3  test    al, al
0x1400136e5  jz      short loc_140013732
0x1400136e7  mov     [rbp+110h], dil
0x1400136ee  movups  xmm0, xmmword ptr [r14+60h]
0x1400136f3  movdqu  xmmword ptr [rbp+60h], xmm0
0x1400136f8  cmp     [rbp+111h], dil
0x1400136ff  jnz     short loc_140013716
0x140013701  cmp     [rbp+112h], dil
0x140013708  jnz     short loc_140013716
0x14001370a  lea     rcx, [r15+68h]; this
0x14001370e  mov     rdx, rbp; struct VMX_OVERLAP_TRANSFER_PACKET *
0x140013711  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x140013716  mov     rax, [rbp+28h]
0x14001371a  mov     rcx, rbp
0x14001371d  call    _guard_dispatch_icall
0x140013722  mov     rdx, r14; struct VMX_MIRROR_TRANSFER_PACKET *
0x140013725  mov     rcx, r15; this
0x140013728  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x14001372d  jmp     loc_140013882
0x140013732  test    ebx, ebx
0x140013734  js      loc_14001386A
0x14001373a  mov     rcx, [r14+130h]; MemoryDescriptorList
0x140013741  mov     ebx, 1
0x140013746  test    byte ptr [rcx+0Ah], 5
0x14001374a  jz      short loc_140013752
0x14001374c  mov     r12, [rcx+18h]
0x140013750  jmp     short loc_140013775
0x140013752  mov     [rsp+68h+Priority], 40000010h; Priority
0x14001375a  xor     r9d, r9d; RequestedAddress
0x14001375d  mov     r8d, ebx; CacheType
0x140013760  mov     [rsp+68h+BugCheckOnFailure], edi; BugCheckOnFailure
0x140013764  xor     edx, edx; AccessMode
0x140013766  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001376d  nop     dword ptr [rax+rax+00h]
0x140013772  mov     r12, rax
0x140013775  mov     ecx, [r14+40h]
0x140013779  mov     r10, [r14+128h]
0x140013780  and     cl, 2
0x140013783  neg     cl
0x140013785  sbb     edx, edx
0x140013787  and     edx, 10h
0x14001378a  add     edx, 10h
0x14001378d  test    byte ptr [r10+0Ah], 5
0x140013792  jz      short loc_14001379A
0x140013794  mov     rax, [r10+18h]
0x140013798  jmp     short loc_1400137BD
0x14001379a  bts     edx, 1Eh
0x14001379e  xor     r9d, r9d; RequestedAddress
0x1400137a1  mov     [rsp+68h+Priority], edx; Priority
0x1400137a5  mov     r8d, ebx; CacheType
0x1400137a8  xor     edx, edx; AccessMode
0x1400137aa  mov     [rsp+68h+BugCheckOnFailure], edi; BugCheckOnFailure
0x1400137ae  mov     rcx, r10; MemoryDescriptorList
0x1400137b1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400137b8  nop     dword ptr [rax+rax+00h]
0x1400137bd  test    rax, rax
0x1400137c0  jz      short loc_1400137E0
0x1400137c2  mov     r8d, [r14+8]; Length
0x1400137c6  mov     rdx, r12; Source2
0x1400137c9  mov     rcx, rax; Source1
0x1400137cc  call    cs:__imp_RtlCompareMemory
0x1400137d3  nop     dword ptr [rax+rax+00h]
0x1400137d8  mov     r15, rax
0x1400137db  jmp     loc_140013864
0x1400137e0  lea     rsi, [r15+0E0h]
0x1400137e7  mov     rcx, rsi; SpinLock
0x1400137ea  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400137f1  nop     dword ptr [rax+rax+00h]
0x1400137f6  mov     r8, [r14+128h]; MemoryDescriptorList
0x1400137fd  mov     r9d, ebx; CacheType
0x140013800  mov     rcx, [r15+0D8h]; MappingAddress
0x140013807  mov     edx, 6D4D6D56h; PoolTag
0x14001380c  mov     dil, al
0x14001380f  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140013816  nop     dword ptr [rax+rax+00h]
0x14001381b  mov     r8d, [r14+8]; Length
0x14001381f  mov     rdx, r12; Source2
0x140013822  mov     rcx, rax; Source1
0x140013825  mov     rbx, rax
0x140013828  call    cs:__imp_RtlCompareMemory
0x14001382f  nop     dword ptr [rax+rax+00h]
0x140013834  mov     r8, [r14+128h]; MemoryDescriptorList
0x14001383b  mov     edx, 6D4D6D56h; PoolTag
0x140013840  mov     rcx, rbx; BaseAddress
0x140013843  mov     r15, rax
0x140013846  call    cs:__imp_MmUnmapReservedMapping
0x14001384d  nop     dword ptr [rax+rax+00h]
0x140013852  mov     dl, dil; NewIrql
0x140013855  mov     rcx, rsi; SpinLock
0x140013858  call    cs:__imp_KeReleaseSpinLock
0x14001385f  nop     dword ptr [rax+rax+00h]
0x140013864  cmp     r15d, [r14+8]
0x140013868  jz      short loc_14001387A
0x14001386a  cmp     dword ptr [rbp+60h], 80380001h
0x140013871  jz      short loc_14001387A
0x140013873  mov     dword ptr [rbp+60h], 4000000Ah
0x14001387a  mov     rcx, r14; struct VMX_TRANSFER_PACKET *
0x14001387d  call    ?VmxpMirrorRecoverReadPhase9@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase9(VMX_TRANSFER_PACKET *)
0x140013882  add     rsp, 30h
0x140013886  pop     r15
0x140013888  pop     r14
0x14001388a  pop     r12
0x14001388c  pop     rdi
0x14001388d  pop     rsi
0x14001388e  pop     rbp
0x14001388f  pop     rbx
0x140013890  retn
```
