# VmxpRaid5RecoverUpdateParityPhase7(VMX_TRANSFER_PACKET *)

- ea: `0x140008150`
- end: `0x1400082f2`
- name: `?VmxpRaid5RecoverUpdateParityPhase7@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `418`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140008150`
- `0x1400087d0`
- `0x1400110f8`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140008231`
- `ntoskrnl!RtlCompareMemory` at `0x140008231`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400082a0`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400082a0`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140008171`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140008171`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000826f`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000826f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400081d2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008211`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400081d2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140008211`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverUpdateParityPhase7(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rsi
  NTSTATUS v3; // ebx
  __int64 v4; // r14
  __int64 v5; // rcx
  PVOID v6; // rbp
  __int64 v7; // r10
  PVOID v8; // rax
  SIZE_T v9; // rbx
  __int64 v10; // rcx
  int v11; // r8d
  struct _MDL *v12; // rdx
  ULONG v13; // r9d
  __int64 v14; // rcx

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *(_QWORD *)(v1 - 336);
  if ( FsRtlIsTotalDeviceFailure(v3) )
  {
    *(_OWORD *)(v1 + 96) = *((_OWORD *)a1 + 6);
    VMX_IO_RAID5::RecycleRecoverPacket((VMX_IO_RAID5 *)v4, a1);
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
  }
  else
  {
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
      v14 = *((_QWORD *)a1 + 6);
      *((_QWORD *)a1 + 3) = *((_QWORD *)a1 + 36);
      *((_QWORD *)a1 + 5) = VmxpRaid5RecoverUpdateParityPhase8;
      (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v14 + 16LL))(v14, a1);
    }
  }
}

```

## disassembly

```asm
0x140008150  push    rbx
0x140008152  push    rbp
0x140008153  push    rsi
0x140008154  push    rdi
0x140008155  push    r14
0x140008157  sub     rsp, 30h
0x14000815b  mov     rsi, [rcx+0E0h]
0x140008162  mov     rdi, rcx
0x140008165  mov     ebx, [rcx+60h]
0x140008168  mov     ecx, ebx; Status
0x14000816a  mov     r14, [rsi-150h]
0x140008171  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140008178  nop     dword ptr [rax+rax+00h]
0x14000817d  test    al, al
0x14000817f  jz      short loc_1400081A6
0x140008181  movups  xmm0, xmmword ptr [rdi+60h]
0x140008185  mov     rdx, rdi; struct VMX_RAID5_RECOVER_TRANSFER_PACKET *
0x140008188  mov     rcx, r14; this
0x14000818b  movdqu  xmmword ptr [rsi+60h], xmm0
0x140008190  call    ?RecycleRecoverPacket@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_RECOVER_TRANSFER_PACKET@@@Z; VMX_IO_RAID5::RecycleRecoverPacket(VMX_RAID5_RECOVER_TRANSFER_PACKET *)
0x140008195  mov     rax, [rsi+28h]
0x140008199  mov     rcx, rsi
0x14000819c  call    _guard_dispatch_icall
0x1400081a1  jmp     loc_1400082E6
0x1400081a6  mov     rcx, [rdi+120h]; MemoryDescriptorList
0x1400081ad  test    byte ptr [rcx+0Ah], 5
0x1400081b1  jz      short loc_1400081B9
0x1400081b3  mov     rbp, [rcx+18h]
0x1400081b7  jmp     short loc_1400081E1
0x1400081b9  xor     r9d, r9d; RequestedAddress
0x1400081bc  mov     [rsp+58h+Priority], 40000010h; Priority
0x1400081c4  xor     edx, edx; AccessMode
0x1400081c6  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400081ce  lea     r8d, [r9+1]; CacheType
0x1400081d2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400081d9  nop     dword ptr [rax+rax+00h]
0x1400081de  mov     rbp, rax
0x1400081e1  mov     r10, [rdi+118h]
0x1400081e8  test    byte ptr [r10+0Ah], 5
0x1400081ed  jz      short loc_1400081F5
0x1400081ef  mov     rax, [r10+18h]
0x1400081f3  jmp     short loc_14000821D
0x1400081f5  xor     r9d, r9d; RequestedAddress
0x1400081f8  mov     [rsp+58h+Priority], 40000010h; Priority
0x140008200  xor     edx, edx; AccessMode
0x140008202  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000820a  mov     rcx, r10; MemoryDescriptorList
0x14000820d  lea     r8d, [r9+1]; CacheType
0x140008211  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140008218  nop     dword ptr [rax+rax+00h]
0x14000821d  test    ebx, ebx
0x14000821f  js      loc_1400082BD
0x140008225  mov     ebx, [rdi+8]
0x140008228  mov     rdx, rax; Source2
0x14000822b  mov     r8d, ebx; Length
0x14000822e  mov     rcx, rbp; Source1
0x140008231  call    cs:__imp_RtlCompareMemory
0x140008238  nop     dword ptr [rax+rax+00h]
0x14000823d  cmp     rax, rbx
0x140008240  jnz     short loc_1400082BD
0x140008242  mov     eax, [rdi+8]
0x140008245  lea     rbx, [rdi+128h]
0x14000824c  mov     [rbx+8], eax
0x14000824f  mov     rax, [rdi+10h]
0x140008253  mov     [rbx+10h], rax
0x140008257  mov     byte ptr [rbx+52h], 0
0x14000825b  mov     rcx, [rdi+110h]
0x140008262  test    byte ptr [rcx+0Ah], 20h
0x140008266  jz      short loc_14000827B
0x140008268  mov     rdx, rcx; MemoryDescriptorList
0x14000826b  mov     rcx, [rcx+18h]; BaseAddress
0x14000826f  call    cs:__imp_MmUnmapLockedPages
0x140008276  nop     dword ptr [rax+rax+00h]
0x14000827b  mov     r8d, [rbx+10h]
0x14000827f  mov     rdx, [rdi+110h]; TargetMdl
0x140008286  mov     r9d, [rbx+8]; Length
0x14000828a  mov     [rbx+18h], rdx
0x14000828e  mov     rcx, [rsi+18h]; SourceMdl
0x140008292  sub     r8d, [rsi+10h]
0x140008296  mov     eax, [rcx+2Ch]
0x140008299  add     r8, rax
0x14000829c  add     r8, [rcx+20h]; VirtualAddress
0x1400082a0  call    cs:__imp_IoBuildPartialMdl
0x1400082a7  nop     dword ptr [rax+rax+00h]
0x1400082ac  lea     rcx, [r14+0A0h]; this
0x1400082b3  mov     rdx, rbx; struct VMX_RAID5_PARITY_TRANSFER_PACKET *
0x1400082b6  call    ?UpdateParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z; VMX_PARITY_IO_MANAGER::UpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)
0x1400082bb  jmp     short loc_1400082E6
0x1400082bd  mov     rax, [rdi+120h]
0x1400082c4  mov     rdx, rdi
0x1400082c7  mov     rcx, [rdi+30h]
0x1400082cb  mov     [rdi+18h], rax
0x1400082cf  lea     rax, ?VmxpRaid5RecoverUpdateParityPhase8@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase8(VMX_TRANSFER_PACKET *)
0x1400082d6  mov     [rdi+28h], rax
0x1400082da  mov     rax, [rcx]
0x1400082dd  mov     rax, [rax+10h]
0x1400082e1  call    _guard_dispatch_icall
0x1400082e6  add     rsp, 30h
0x1400082ea  pop     r14
0x1400082ec  pop     rdi
0x1400082ed  pop     rsi
0x1400082ee  pop     rbp
0x1400082ef  pop     rbx
0x1400082f0  retn
```
