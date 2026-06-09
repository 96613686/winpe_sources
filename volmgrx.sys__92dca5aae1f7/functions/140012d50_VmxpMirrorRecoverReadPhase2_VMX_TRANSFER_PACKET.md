# VmxpMirrorRecoverReadPhase2(VMX_TRANSFER_PACKET *)

- ea: `0x140012d50`
- end: `0x140012f74`
- name: `?VmxpMirrorRecoverReadPhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `548`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003774`
- `0x140003cf0`
- `0x140012d50`
- `0x140013898`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012de1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012eb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012de1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012eb5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012f1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012e1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012f1b`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140012edd`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140012edd`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140012f09`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140012f09`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140012d71`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140012d71`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012e8a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140012e8a`

## pseudocode

```c
void __fastcall VmxpMirrorRecoverReadPhase2(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rbp
  NTSTATUS v3; // edi
  __int64 v4; // rbx
  bool v5; // zf
  KIRQL v6; // al
  unsigned int v7; // r8d
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r10
  PVOID v11; // rax
  KSPIN_LOCK *v12; // rsi
  KIRQL v13; // di
  PVOID v14; // rbx
  __int64 v15; // rcx

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 + 232);
  if ( FsRtlIsTotalDeviceFailure(v3) )
  {
    v5 = *(_BYTE *)(v1 + 273) == 0;
    *(_BYTE *)(v1 + 272) = 0;
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
    if ( !v5 )
    {
LABEL_5:
      (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
      VMX_IO_MIRROR::RecyclePacket((VMX_IO_MIRROR *)v4, a1);
      return;
    }
LABEL_3:
    if ( !*(_BYTE *)(v1 + 274) )
      VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(
        (VMX_OVERLAPPED_IO_MANAGER *)(v4 + 104),
        (struct VMX_OVERLAP_TRANSFER_PACKET *)v1);
    goto LABEL_5;
  }
  if ( v3 >= 0 )
    goto LABEL_7;
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
  v7 = *(_DWORD *)(v4 + 56);
  v8 = 0;
  if ( v7 )
  {
    v9 = *(_QWORD *)(v4 + 96);
    do
    {
      if ( (_DWORD)v8 != *(_DWORD *)(v1 + 240) && !*(_DWORD *)(v9 + 16) )
        break;
      v8 = (unsigned int)(v8 + 1);
      v9 += 40;
    }
    while ( (unsigned int)v8 < v7 );
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v6);
  if ( (_DWORD)v8 == *(_DWORD *)(v4 + 56) )
  {
    if ( !*(_BYTE *)(v1 + 273) )
    {
      *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
      goto LABEL_3;
    }
    v10 = *((_QWORD *)a1 + 37);
    if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
      v11 = *(PVOID *)(v10 + 24);
    else
      v11 = MmMapLockedPagesSpecifyCache(
              (PMDL)v10,
              0,
              MmCached,
              0,
              0,
              ((*((_DWORD *)a1 + 16) & 2) != 0 ? 32 : 16) | 0x40000000u);
    if ( v11 )
    {
      memset(v11, 0, *((unsigned int *)a1 + 2));
    }
    else
    {
      v12 = (KSPIN_LOCK *)(v4 + 224);
      v13 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 224));
      v14 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v4 + 216), 0x6D4D6D56u, *((PMDL *)a1 + 37), MmCached);
      memset(v14, 0, *((unsigned int *)a1 + 2));
      MmUnmapReservedMapping(v14, 0x6D4D6D56u, *((PMDL *)a1 + 37));
      KeReleaseSpinLock(v12, v13);
    }
    *(_DWORD *)(v1 + 96) = -2143813631;
LABEL_7:
    VmxpMirrorRecoverReadPhase9(a1);
    return;
  }
  *((_DWORD *)a1 + 60) = v8;
  v15 = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8 * v8);
  *((_QWORD *)a1 + 5) = VmxpMirrorRecoverReadPhase3;
  *((_QWORD *)a1 + 6) = v15;
  *((_DWORD *)a1 + 3) = 16842757;
  (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v15 + 8LL))(v15, a1);
}

```

## disassembly

```asm
0x140012d50  push    rbx
0x140012d52  push    rbp
0x140012d53  push    rsi
0x140012d54  push    rdi
0x140012d55  push    r14
0x140012d57  sub     rsp, 30h
0x140012d5b  mov     rbp, [rcx+0E0h]
0x140012d62  mov     r14, rcx
0x140012d65  mov     edi, [rcx+60h]
0x140012d68  mov     ecx, edi; Status
0x140012d6a  mov     rbx, [rbp+0E8h]
0x140012d71  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140012d78  nop     dword ptr [rax+rax+00h]
0x140012d7d  test    al, al
0x140012d7f  jz      short loc_140012DCC
0x140012d81  cmp     byte ptr [rbp+111h], 0
0x140012d88  mov     byte ptr [rbp+110h], 0
0x140012d8f  movups  xmm0, xmmword ptr [r14+60h]
0x140012d94  movdqu  xmmword ptr [rbp+60h], xmm0
0x140012d99  jnz     short loc_140012DB0
0x140012d9b  cmp     byte ptr [rbp+112h], 0
0x140012da2  jnz     short loc_140012DB0
0x140012da4  lea     rcx, [rbx+68h]; this
0x140012da8  mov     rdx, rbp; struct VMX_OVERLAP_TRANSFER_PACKET *
0x140012dab  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x140012db0  mov     rax, [rbp+28h]
0x140012db4  mov     rcx, rbp
0x140012db7  call    _guard_dispatch_icall
0x140012dbc  mov     rdx, r14; struct VMX_MIRROR_TRANSFER_PACKET *
0x140012dbf  mov     rcx, rbx; this
0x140012dc2  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x140012dc7  jmp     loc_140012F68
0x140012dcc  test    edi, edi
0x140012dce  js      short loc_140012DDD
0x140012dd0  mov     rcx, r14; struct VMX_TRANSFER_PACKET *
0x140012dd3  call    ?VmxpMirrorRecoverReadPhase9@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase9(VMX_TRANSFER_PACKET *)
0x140012dd8  jmp     loc_140012F68
0x140012ddd  lea     rcx, [rbx+18h]; SpinLock
0x140012de1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012de8  nop     dword ptr [rax+rax+00h]
0x140012ded  mov     r8d, [rbx+38h]
0x140012df1  xor     edi, edi
0x140012df3  test    r8d, r8d
0x140012df6  jz      short loc_140012E17
0x140012df8  mov     rdx, [rbx+60h]
0x140012dfc  mov     ecx, [rbp+0F0h]
0x140012e02  cmp     edi, ecx
0x140012e04  jz      short loc_140012E0C
0x140012e06  cmp     dword ptr [rdx+10h], 0
0x140012e0a  jz      short loc_140012E17
0x140012e0c  inc     edi
0x140012e0e  add     rdx, 28h ; '('
0x140012e12  cmp     edi, r8d
0x140012e15  jb      short loc_140012E02
0x140012e17  mov     dl, al; NewIrql
0x140012e19  lea     rcx, [rbx+18h]; SpinLock
0x140012e1d  call    cs:__imp_KeReleaseSpinLock
0x140012e24  nop     dword ptr [rax+rax+00h]
0x140012e29  cmp     edi, [rbx+38h]
0x140012e2c  jnz     loc_140012F33
0x140012e32  cmp     byte ptr [rbp+111h], 0
0x140012e39  jnz     short loc_140012E4A
0x140012e3b  movups  xmm0, xmmword ptr [r14+60h]
0x140012e40  movdqu  xmmword ptr [rbp+60h], xmm0
0x140012e45  jmp     loc_140012D9B
0x140012e4a  mov     eax, [r14+40h]
0x140012e4e  mov     r10, [r14+128h]
0x140012e55  and     al, 2
0x140012e57  neg     al
0x140012e59  sbb     ecx, ecx
0x140012e5b  and     ecx, 10h
0x140012e5e  add     ecx, 10h
0x140012e61  test    byte ptr [r10+0Ah], 5
0x140012e66  jz      short loc_140012E6E
0x140012e68  mov     rax, [r10+18h]
0x140012e6c  jmp     short loc_140012E96
0x140012e6e  bts     ecx, 1Eh
0x140012e72  xor     r9d, r9d; RequestedAddress
0x140012e75  mov     [rsp+58h+Priority], ecx; Priority
0x140012e79  xor     edx, edx; AccessMode
0x140012e7b  mov     rcx, r10; MemoryDescriptorList
0x140012e7e  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140012e86  lea     r8d, [r9+1]; CacheType
0x140012e8a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140012e91  nop     dword ptr [rax+rax+00h]
0x140012e96  test    rax, rax
0x140012e99  jz      short loc_140012EAB
0x140012e9b  mov     r8d, [r14+8]; Size
0x140012e9f  xor     edx, edx; Val
0x140012ea1  mov     rcx, rax; void *
0x140012ea4  call    memset
0x140012ea9  jmp     short loc_140012F27
0x140012eab  lea     rsi, [rbx+0E0h]
0x140012eb2  mov     rcx, rsi; SpinLock
0x140012eb5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012ebc  nop     dword ptr [rax+rax+00h]
0x140012ec1  mov     r8, [r14+128h]; MemoryDescriptorList
0x140012ec8  mov     r9d, 1; CacheType
0x140012ece  mov     rcx, [rbx+0D8h]; MappingAddress
0x140012ed5  mov     edx, 6D4D6D56h; PoolTag
0x140012eda  mov     dil, al
0x140012edd  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x140012ee4  nop     dword ptr [rax+rax+00h]
0x140012ee9  mov     r8d, [r14+8]; Size
0x140012eed  xor     edx, edx; Val
0x140012eef  mov     rcx, rax; void *
0x140012ef2  mov     rbx, rax
0x140012ef5  call    memset
0x140012efa  mov     r8, [r14+128h]; MemoryDescriptorList
0x140012f01  mov     edx, 6D4D6D56h; PoolTag
0x140012f06  mov     rcx, rbx; BaseAddress
0x140012f09  call    cs:__imp_MmUnmapReservedMapping
0x140012f10  nop     dword ptr [rax+rax+00h]
0x140012f15  mov     dl, dil; NewIrql
0x140012f18  mov     rcx, rsi; SpinLock
0x140012f1b  call    cs:__imp_KeReleaseSpinLock
0x140012f22  nop     dword ptr [rax+rax+00h]
0x140012f27  mov     dword ptr [rbp+60h], 80380001h
0x140012f2e  jmp     loc_140012DD0
0x140012f33  mov     [r14+0F0h], edi
0x140012f3a  mov     rdx, r14
0x140012f3d  mov     rax, [rbx+30h]
0x140012f41  mov     rcx, [rax+rdi*8]
0x140012f45  lea     rax, ?VmxpMirrorRecoverReadPhase3@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase3(VMX_TRANSFER_PACKET *)
0x140012f4c  mov     [r14+28h], rax
0x140012f50  mov     [r14+30h], rcx
0x140012f54  mov     dword ptr [r14+0Ch], 1010005h
0x140012f5c  mov     rax, [rcx]
0x140012f5f  mov     rax, [rax+8]
0x140012f63  call    _guard_dispatch_icall
0x140012f68  add     rsp, 30h
0x140012f6c  pop     r14
0x140012f6e  pop     rdi
0x140012f6f  pop     rsi
0x140012f70  pop     rbp
0x140012f71  pop     rbx
0x140012f72  retn
```
