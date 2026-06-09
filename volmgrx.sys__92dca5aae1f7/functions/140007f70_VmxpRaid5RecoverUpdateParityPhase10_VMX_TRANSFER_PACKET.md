# VmxpRaid5RecoverUpdateParityPhase10(VMX_TRANSFER_PACKET *)

- ea: `0x140007f70`
- end: `0x140008147`
- name: `?VmxpRaid5RecoverUpdateParityPhase10@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `471`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140007f70`
- `0x1400087d0`
- `0x1400110f8`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140008051`
- `ntoskrnl!RtlCompareMemory` at `0x140008051`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400080c0`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400080c0`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140007f91`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140007f91`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000808f`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000808f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007ff2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008031`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140007ff2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008031`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverUpdateParityPhase10(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rsi
  NTSTATUS v3; // ebx
  __int64 v4; // rbp
  __int64 v5; // rcx
  PVOID v6; // r14
  __int64 v7; // r10
  PVOID v8; // rax
  SIZE_T v9; // rbx
  __int64 v10; // rcx
  int v11; // r8d
  struct _MDL *v12; // rdx
  ULONG v13; // r9d
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 - 336);
  if ( FsRtlIsTotalDeviceFailure(v3) )
  {
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
LABEL_3:
    VMX_IO_RAID5::RecycleRecoverPacket((VMX_IO_RAID5 *)v4, a1);
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    return;
  }
  v5 = *((_QWORD *)a1 + 36);
  if ( (*(_BYTE *)(v5 + 10) & 5) != 0 )
    v6 = *(PVOID *)(v5 + 24);
  else
    v6 = MmMapLockedPagesSpecifyCache((PMDL)v5, 0, MmCached, 0, 0, 0x40000010u);
  v7 = *((_QWORD *)a1 + 35);
  if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
    v8 = *(PVOID *)(v7 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u);
  if ( v3 >= 0 && (v9 = *((unsigned int *)a1 + 2), RtlCompareMemory(v6, v8, v9) == v9) )
  {
    *((_DWORD *)a1 + 76) = *((_DWORD *)a1 + 2);
    *((_QWORD *)a1 + 39) = *((_QWORD *)a1 + 2);
    *((_BYTE *)a1 + 378) = 0;
    v10 = *((_QWORD *)a1 + 34);
    if ( (*(_BYTE *)(v10 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v10 + 24), *((PMDL *)a1 + 34));
    v11 = *((_DWORD *)a1 + 78);
    v12 = (struct _MDL *)*((_QWORD *)a1 + 34);
    v13 = *((_DWORD *)a1 + 76);
    *((_QWORD *)a1 + 40) = v12;
    IoBuildPartialMdl(
      *(PMDL *)(v1 + 24),
      v12,
      (PVOID)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 32LL)
            + *(unsigned int *)(*(_QWORD *)(v1 + 24) + 44LL)
            + (unsigned __int64)(unsigned int)(v11 - *(_DWORD *)(v1 + 16))),
      v13);
    VMX_PARITY_IO_MANAGER::UpdateParity(
      (VMX_PARITY_IO_MANAGER *)(v4 + 160),
      (struct VMX_TRANSFER_PACKET *)((char *)a1 + 296));
  }
  else
  {
    v14 = *(_QWORD *)(v1 + 16) + *(unsigned int *)(v1 + 8);
    *(_DWORD *)(v1 + 96) = -1073741668;
    *(_QWORD *)(v1 + 104) = 0;
    v15 = *((_QWORD *)a1 + 2) + *((unsigned int *)a1 + 2);
    if ( v15 == v14 )
      goto LABEL_3;
    v16 = *((_QWORD *)a1 + 6);
    *((_QWORD *)a1 + 3) = *((_QWORD *)a1 + 36);
    *((_QWORD *)a1 + 5) = VmxpRaid5RecoverUpdateParityPhase1;
    *((_QWORD *)a1 + 2) = v15;
    *((_BYTE *)a1 + 82) = 1;
    *((_DWORD *)a1 + 3) = 33685511;
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v16 + 8LL))(v16, a1);
  }
}

```

## disassembly

```asm
0x140007f70  push    rbx
0x140007f72  push    rbp
0x140007f73  push    rsi
0x140007f74  push    rdi
0x140007f75  push    r14
0x140007f77  sub     rsp, 30h
0x140007f7b  mov     rsi, [rcx+0E0h]
0x140007f82  mov     rdi, rcx
0x140007f85  mov     ebx, [rcx+60h]
0x140007f88  mov     ecx, ebx; Status
0x140007f8a  mov     rbp, [rsi-150h]
0x140007f91  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140007f98  nop     dword ptr [rax+rax+00h]
0x140007f9d  test    al, al
0x140007f9f  jz      short loc_140007FC6
0x140007fa1  movups  xmm0, xmmword ptr [rdi+60h]
0x140007fa5  movdqu  xmmword ptr [rsi+60h], xmm0
0x140007faa  mov     rdx, rdi; struct VMX_RAID5_RECOVER_TRANSFER_PACKET *
0x140007fad  mov     rcx, rbp; this
0x140007fb0  call    ?RecycleRecoverPacket@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_RECOVER_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::RecycleRecoverPacket(VMX_RAID5_RECOVER_TRANSFER_PACKET *)
0x140007fb5  mov     rax, [rsi+28h]
0x140007fb9  mov     rcx, rsi
0x140007fbc  call    _guard_dispatch_icall
0x140007fc1  jmp     loc_14000813B
0x140007fc6  mov     rcx, [rdi+120h]; MemoryDescriptorList
0x140007fcd  test    byte ptr [rcx+0Ah], 5
0x140007fd1  jz      short loc_140007FD9
0x140007fd3  mov     r14, [rcx+18h]
0x140007fd7  jmp     short loc_140008001
0x140007fd9  xor     r9d, r9d; RequestedAddress
0x140007fdc  mov     [rsp+58h+Priority], 40000010h; Priority
0x140007fe4  xor     edx, edx; AccessMode
0x140007fe6  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140007fee  lea     r8d, [r9+1]; CacheType
0x140007ff2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140007ff9  nop     dword ptr [rax+rax+00h]
0x140007ffe  mov     r14, rax
0x140008001  mov     r10, [rdi+118h]
0x140008008  test    byte ptr [r10+0Ah], 5
0x14000800d  jz      short loc_140008015
0x14000800f  mov     rax, [r10+18h]
0x140008013  jmp     short loc_14000803D
0x140008015  xor     r9d, r9d; RequestedAddress
0x140008018  mov     [rsp+58h+Priority], 40000010h; Priority
0x140008020  xor     edx, edx; AccessMode
0x140008022  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000802a  mov     rcx, r10; MemoryDescriptorList
0x14000802d  lea     r8d, [r9+1]; CacheType
0x140008031  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140008038  nop     dword ptr [rax+rax+00h]
0x14000803d  test    ebx, ebx
0x14000803f  js      loc_1400080DD
0x140008045  mov     ebx, [rdi+8]
0x140008048  mov     rdx, rax; Source2
0x14000804b  mov     r8d, ebx; Length
0x14000804e  mov     rcx, r14; Source1
0x140008051  call    cs:__imp_RtlCompareMemory
0x140008058  nop     dword ptr [rax+rax+00h]
0x14000805d  cmp     rax, rbx
0x140008060  jnz     short loc_1400080DD
0x140008062  mov     eax, [rdi+8]
0x140008065  lea     rbx, [rdi+128h]
0x14000806c  mov     [rbx+8], eax
0x14000806f  mov     rax, [rdi+10h]
0x140008073  mov     [rbx+10h], rax
0x140008077  mov     byte ptr [rbx+52h], 0
0x14000807b  mov     rcx, [rdi+110h]
0x140008082  test    byte ptr [rcx+0Ah], 20h
0x140008086  jz      short loc_14000809B
0x140008088  mov     rdx, rcx; MemoryDescriptorList
0x14000808b  mov     rcx, [rcx+18h]; BaseAddress
0x14000808f  call    cs:__imp_MmUnmapLockedPages
0x140008096  nop     dword ptr [rax+rax+00h]
0x14000809b  mov     r8d, [rbx+10h]
0x14000809f  mov     rdx, [rdi+110h]; TargetMdl
0x1400080a6  mov     r9d, [rbx+8]; Length
0x1400080aa  mov     [rbx+18h], rdx
0x1400080ae  mov     rcx, [rsi+18h]; SourceMdl
0x1400080b2  sub     r8d, [rsi+10h]
0x1400080b6  mov     eax, [rcx+2Ch]
0x1400080b9  add     r8, rax
0x1400080bc  add     r8, [rcx+20h]; VirtualAddress
0x1400080c0  call    cs:__imp_IoBuildPartialMdl
0x1400080c7  nop     dword ptr [rax+rax+00h]
0x1400080cc  lea     rcx, [rbp+0A0h]; this
0x1400080d3  mov     rdx, rbx; struct VMX_RAID5_PARITY_TRANSFER_PACKET *
0x1400080d6  call    ?UpdateParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z; VMX_PARITY_IO_MANAGER::UpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)
0x1400080db  jmp     short loc_14000813B
0x1400080dd  mov     eax, [rsi+8]
0x1400080e0  add     rax, [rsi+10h]
0x1400080e4  mov     dword ptr [rsi+60h], 0C000009Ch
0x1400080eb  mov     qword ptr [rsi+68h], 0
0x1400080f3  mov     edx, [rdi+8]
0x1400080f6  add     rdx, [rdi+10h]
0x1400080fa  cmp     rdx, rax
0x1400080fd  jz      loc_140007FAA
0x140008103  mov     rax, [rdi+120h]
0x14000810a  mov     rcx, [rdi+30h]
0x14000810e  mov     [rdi+18h], rax
0x140008112  lea     rax, ?VmxpRaid5RecoverUpdateParityPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase1(VMX_TRANSFER_PACKET *)
0x140008119  mov     [rdi+28h], rax
0x14000811d  mov     [rdi+10h], rdx
0x140008121  mov     rdx, rdi
0x140008124  mov     byte ptr [rdi+52h], 1
0x140008128  mov     dword ptr [rdi+0Ch], 2020007h
0x14000812f  mov     rax, [rcx]
0x140008132  mov     rax, [rax+8]
0x140008136  call    _guard_dispatch_icall
0x14000813b  add     rsp, 30h
0x14000813f  pop     r14
0x140008141  pop     rdi
0x140008142  pop     rsi
0x140008143  pop     rbp
0x140008144  pop     rbx
0x140008145  retn
```
