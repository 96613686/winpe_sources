# VmxpMirrorRecoverReadPhase9(VMX_TRANSFER_PACKET *)

- ea: `0x140013898`
- end: `0x14001398f`
- name: `?VmxpMirrorRecoverReadPhase9@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `247`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140012d50`
- `0x140012f80`
- `0x140013360`
- `0x140013560`
- `0x1400135d0`
- `0x1400136b0`

## callees

- `0x140003774`
- `0x140003cf0`
- `0x140013898`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x140013958`
- `ntoskrnl!IoBuildPartialMdl` at `0x140013958`
- `ntoskrnl!MmUnmapLockedPages` at `0x14001392e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14001392e`

## pseudocode

```c
void __fastcall VmxpMirrorRecoverReadPhase9(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rdi
  __int64 v3; // r8
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rcx

  v1 = *((_QWORD *)a1 + 28);
  v3 = *((_QWORD *)a1 + 2) + *((unsigned int *)a1 + 2);
  if ( v3 == *(_QWORD *)(v1 + 16) + *(unsigned int *)(v1 + 8) )
  {
    v4 = *(_QWORD *)(v1 + 232);
    if ( !*(_BYTE *)(v1 + 273) && !*(_BYTE *)(v1 + 274) )
      VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(
        (VMX_OVERLAPPED_IO_MANAGER *)(v4 + 104),
        (struct VMX_OVERLAP_TRANSFER_PACKET *)v1);
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    VMX_IO_MIRROR::RecyclePacket((VMX_IO_MIRROR *)v4, a1);
  }
  else
  {
    v5 = *((_QWORD *)a1 + 37);
    *((_QWORD *)a1 + 3) = v5;
    *((_QWORD *)a1 + 2) = v3;
    *((_QWORD *)a1 + 5) = VmxpMirrorRecoverReadPhase2;
    *((_BYTE *)a1 + 82) = 1;
    if ( (*(_BYTE *)(v5 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v5 + 24), (PMDL)v5);
    IoBuildPartialMdl(
      *(PMDL *)(v1 + 24),
      *((PMDL *)a1 + 3),
      (PVOID)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 32LL)
            + *(unsigned int *)(*(_QWORD *)(v1 + 24) + 44LL)
            + (unsigned __int64)(unsigned int)(*((_DWORD *)a1 + 4) - *(_DWORD *)(v1 + 16))),
      *((_DWORD *)a1 + 2));
    v6 = *((_QWORD *)a1 + 6);
    *((_DWORD *)a1 + 3) = 16842756;
    (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v6 + 8LL))(v6, a1);
  }
}

```

## disassembly

```asm
0x140013898  mov     [rsp+arg_0], rbx
0x14001389d  mov     [rsp+arg_8], rsi
0x1400138a2  push    rdi
0x1400138a3  sub     rsp, 20h
0x1400138a7  mov     rdi, [rcx+0E0h]
0x1400138ae  mov     rbx, rcx
0x1400138b1  mov     r8d, [rcx+8]
0x1400138b5  add     r8, [rcx+10h]
0x1400138b9  mov     eax, [rdi+8]
0x1400138bc  add     rax, [rdi+10h]
0x1400138c0  cmp     r8, rax
0x1400138c3  jnz     short loc_140013903
0x1400138c5  cmp     byte ptr [rdi+111h], 0
0x1400138cc  mov     rsi, [rdi+0E8h]
0x1400138d3  jnz     short loc_1400138EA
0x1400138d5  cmp     byte ptr [rdi+112h], 0
0x1400138dc  jnz     short loc_1400138EA
0x1400138de  lea     rcx, [rsi+68h]; this
0x1400138e2  mov     rdx, rdi; struct VMX_OVERLAP_TRANSFER_PACKET *
0x1400138e5  call    ?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z; VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)
0x1400138ea  mov     rax, [rdi+28h]
0x1400138ee  mov     rcx, rdi
0x1400138f1  call    _guard_dispatch_icall
0x1400138f6  mov     rdx, rbx; struct VMX_MIRROR_TRANSFER_PACKET *
0x1400138f9  mov     rcx, rsi; this
0x1400138fc  call    ?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z; VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)
0x140013901  jmp     short loc_14001397E
0x140013903  mov     rcx, [rcx+128h]
0x14001390a  lea     rax, ?VmxpMirrorRecoverReadPhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase2(VMX_TRANSFER_PACKET *)
0x140013911  mov     [rbx+18h], rcx
0x140013915  mov     [rbx+10h], r8
0x140013919  mov     [rbx+28h], rax
0x14001391d  mov     byte ptr [rbx+52h], 1
0x140013921  test    byte ptr [rcx+0Ah], 20h
0x140013925  jz      short loc_14001393A
0x140013927  mov     rdx, rcx; MemoryDescriptorList
0x14001392a  mov     rcx, [rcx+18h]; BaseAddress
0x14001392e  call    cs:__imp_MmUnmapLockedPages
0x140013935  nop     dword ptr [rax+rax+00h]
0x14001393a  mov     rcx, [rdi+18h]; SourceMdl
0x14001393e  mov     r8d, [rbx+10h]
0x140013942  sub     r8d, [rdi+10h]
0x140013946  mov     r9d, [rbx+8]; Length
0x14001394a  mov     eax, [rcx+2Ch]
0x14001394d  mov     rdx, [rbx+18h]; TargetMdl
0x140013951  add     r8, rax
0x140013954  add     r8, [rcx+20h]; VirtualAddress
0x140013958  call    cs:__imp_IoBuildPartialMdl
0x14001395f  nop     dword ptr [rax+rax+00h]
0x140013964  mov     rcx, [rbx+30h]
0x140013968  mov     rdx, rbx
0x14001396b  mov     dword ptr [rbx+0Ch], 1010004h
0x140013972  mov     rax, [rcx]
0x140013975  mov     rax, [rax+8]
0x140013979  call    _guard_dispatch_icall
0x14001397e  mov     rbx, [rsp+28h+arg_0]
0x140013983  mov     rsi, [rsp+28h+arg_8]
0x140013988  add     rsp, 20h
0x14001398c  pop     rdi
0x14001398d  retn
```
