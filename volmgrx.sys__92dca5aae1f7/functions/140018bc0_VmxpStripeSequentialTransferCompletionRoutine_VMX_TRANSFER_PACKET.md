# VmxpStripeSequentialTransferCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140018bc0`
- end: `0x140018d9b`
- name: `?VmxpStripeSequentialTransferCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `475`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004670`
- `0x140007828`
- `0x14000f488`
- `0x140018bc0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018c7c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018c7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018cab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ce8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018cab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018ce8`
- `ntoskrnl!IoBuildPartialMdl` at `0x140018d72`
- `ntoskrnl!IoBuildPartialMdl` at `0x140018d72`
- `ntoskrnl!MmUnmapLockedPages` at `0x140018c19`
- `ntoskrnl!MmUnmapLockedPages` at `0x140018c19`

## pseudocode

```c
void __fastcall VmxpStripeSequentialTransferCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rdi
  NTSTATUS v3; // ebp
  __int64 v4; // rsi
  NTSTATUS v5; // edx
  __int64 v6; // rcx
  __int64 v7; // r11
  unsigned __int64 v8; // rtt
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r10
  _QWORD **v11; // rdi
  KIRQL v12; // al
  _QWORD *v13; // rbx
  _QWORD *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  struct _MDL *v17; // rdx

  v1 = *((_QWORD *)a1 + 22);
  v3 = *((_DWORD *)a1 + 24);
  v4 = *((_QWORD *)a1 + 23);
  v5 = *(_DWORD *)(v1 + 96);
  if ( v3 < 0 )
  {
    if ( VmxpIsWorseStatus(v3, v5) )
    {
      *(_DWORD *)(v1 + 96) = v3;
      *(_QWORD *)(v1 + 104) = 0;
    }
  }
  else if ( v5 >= 0 )
  {
    *(_QWORD *)(v1 + 104) += *((_QWORD *)a1 + 13);
  }
  v6 = *((_QWORD *)a1 + 3);
  if ( (*(_BYTE *)(v6 + 10) & 0x20) != 0 )
    MmUnmapLockedPages(*(PVOID *)(v6 + 24), *((PMDL *)a1 + 3));
  v7 = *((unsigned int *)a1 + 48);
  v8 = *((_QWORD *)a1 + 2);
  v9 = v8 / *(unsigned int *)(v4 + 64);
  v10 = *(unsigned int *)(v4 + 64) * (v7 + v9 * *(unsigned int *)(v4 + 56))
      + v8 % *(unsigned int *)(v4 + 64)
      + *((unsigned int *)a1 + 2);
  if ( v10 == *(_QWORD *)(v1 + 16) + *(unsigned int *)(v1 + 8) )
  {
    (*(void (__fastcall **)(__int64))(v1 + 40))(v1);
    v11 = (_QWORD **)(v4 + 96);
    while ( 1 )
    {
      v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 24));
      v13 = *v11;
      if ( *v11 == v11 )
        break;
      if ( (_QWORD **)v13[1] != v11 || (v14 = (_QWORD *)*v13, *(_QWORD **)(*v13 + 8LL) != v13) )
        __fastfail(3u);
      *v11 = v14;
      v14[1] = v11;
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v12);
      if ( !VMX_IO_STRIPE::LaunchParallel((VMX_IO_STRIPE *)v4, (struct VMX_TRANSFER_PACKET *)(v13 - 14)) )
      {
        VMX_IO_STRIPE::LaunchSequential((VMX_IO_STRIPE *)v4, (struct VMX_TRANSFER_PACKET *)(v13 - 14));
        return;
      }
    }
    *(_BYTE *)(v4 + 88) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 24), v12);
  }
  else
  {
    v15 = (unsigned int)(v7 + 1);
    *((_DWORD *)a1 + 48) = v15;
    if ( (_DWORD)v15 == *(_DWORD *)(v4 + 56) )
    {
      ++v9;
      *((_DWORD *)a1 + 48) = 0;
      v15 = 0;
    }
    *((_QWORD *)a1 + 2) = v9 * *(unsigned int *)(v4 + 64);
    v16 = *(unsigned int *)(v4 + 64);
    *((_DWORD *)a1 + 2) = v16;
    if ( v10 + v16 > *(_QWORD *)(v1 + 16) + (unsigned __int64)*(unsigned int *)(v1 + 8) )
    {
      LODWORD(v16) = *(_DWORD *)(v1 + 8) - v10 + *(_DWORD *)(v1 + 16);
      *((_DWORD *)a1 + 2) = v16;
    }
    v17 = (struct _MDL *)*((_QWORD *)a1 + 3);
    *((_QWORD *)a1 + 6) = *(_QWORD *)(*(_QWORD *)(v4 + 48) + 8 * v15);
    IoBuildPartialMdl(
      *(PMDL *)(v1 + 24),
      v17,
      (PVOID)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 32LL)
            + *(unsigned int *)(*(_QWORD *)(v1 + 24) + 44LL)
            + (unsigned __int64)(unsigned int)(v10 - *(_DWORD *)(v1 + 16))),
      v16);
    (*(void (__fastcall **)(_QWORD, struct VMX_TRANSFER_PACKET *))(**((_QWORD **)a1 + 6) + 8LL))(
      *((_QWORD *)a1 + 6),
      a1);
  }
}

```

## disassembly

```asm
0x140018bc0  push    rbx
0x140018bc2  push    rbp
0x140018bc3  push    rsi
0x140018bc4  push    rdi
0x140018bc5  sub     rsp, 28h
0x140018bc9  mov     rdi, [rcx+0B0h]
0x140018bd0  mov     rbx, rcx
0x140018bd3  mov     ebp, [rcx+60h]
0x140018bd6  mov     rsi, [rcx+0B8h]
0x140018bdd  mov     edx, [rdi+60h]; NTSTATUS
0x140018be0  test    ebp, ebp
0x140018be2  js      short loc_140018BF2
0x140018be4  test    edx, edx
0x140018be6  js      short loc_140018C08
0x140018be8  mov     rax, [rcx+68h]
0x140018bec  add     [rdi+68h], rax
0x140018bf0  jmp     short loc_140018C08
0x140018bf2  mov     ecx, ebp; Status
0x140018bf4  call    ?VmxpIsWorseStatus@@YAEJJ@Z; VmxpIsWorseStatus(long,long)
0x140018bf9  test    al, al
0x140018bfb  jz      short loc_140018C08
0x140018bfd  mov     [rdi+60h], ebp
0x140018c00  mov     qword ptr [rdi+68h], 0
0x140018c08  mov     rcx, [rbx+18h]
0x140018c0c  test    byte ptr [rcx+0Ah], 20h
0x140018c10  jz      short loc_140018C25
0x140018c12  mov     rdx, rcx; MemoryDescriptorList
0x140018c15  mov     rcx, [rcx+18h]; BaseAddress
0x140018c19  call    cs:__imp_MmUnmapLockedPages
0x140018c20  nop     dword ptr [rax+rax+00h]
0x140018c25  mov     r8d, [rsi+40h]
0x140018c29  xor     edx, edx
0x140018c2b  mov     rax, [rbx+10h]
0x140018c2f  mov     r9d, [rsi+38h]
0x140018c33  mov     r11d, [rbx+0C0h]
0x140018c3a  mov     r10d, [rbx+8]
0x140018c3e  div     r8
0x140018c41  imul    r9, rax
0x140018c45  mov     rcx, rax
0x140018c48  mov     eax, [rdi+8]
0x140018c4b  add     rax, [rdi+10h]
0x140018c4f  add     r9, r11
0x140018c52  imul    r9, r8
0x140018c56  add     rdx, r9
0x140018c59  add     r10, rdx
0x140018c5c  cmp     r10, rax
0x140018c5f  jnz     loc_140018CF9
0x140018c65  mov     rax, [rdi+28h]
0x140018c69  mov     rcx, rdi
0x140018c6c  call    _guard_dispatch_icall
0x140018c71  lea     rbp, [rsi+18h]
0x140018c75  lea     rdi, [rsi+60h]
0x140018c79  mov     rcx, rbp; SpinLock
0x140018c7c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018c83  nop     dword ptr [rax+rax+00h]
0x140018c88  mov     rbx, [rdi]
0x140018c8b  cmp     rbx, rdi
0x140018c8e  jz      short loc_140018CDF
0x140018c90  cmp     [rbx+8], rdi
0x140018c94  jnz     short loc_140018CD8
0x140018c96  mov     rcx, [rbx]
0x140018c99  cmp     [rcx+8], rbx
0x140018c9d  jnz     short loc_140018CD8
0x140018c9f  mov     [rdi], rcx
0x140018ca2  mov     dl, al; NewIrql
0x140018ca4  mov     [rcx+8], rdi
0x140018ca8  mov     rcx, rbp; SpinLock
0x140018cab  call    cs:__imp_KeReleaseSpinLock
0x140018cb2  nop     dword ptr [rax+rax+00h]
0x140018cb7  lea     rdx, [rbx-70h]; struct VMX_TRANSFER_PACKET *
0x140018cbb  mov     rcx, rsi; this
0x140018cbe  call    ?LaunchParallel@VMX_IO_STRIPE@@QEAAEPEAVVMX_TRANSFER_PACKET@@@Z; VMX_IO_STRIPE::LaunchParallel(VMX_TRANSFER_PACKET *)
0x140018cc3  test    al, al
0x140018cc5  jnz     short loc_140018C79
0x140018cc7  lea     rdx, [rbx-70h]; struct VMX_TRANSFER_PACKET *
0x140018ccb  mov     rcx, rsi; this
0x140018cce  call    ?LaunchSequential@VMX_IO_STRIPE@@QEAAXPEAVVMX_TRANSFER_PACKET@@@Z; VMX_IO_STRIPE::LaunchSequential(VMX_TRANSFER_PACKET *)
0x140018cd3  jmp     loc_140018D91
0x140018cd8  mov     ecx, 3
0x140018cdd  int     29h; Win8: RtlFailFast(ecx)
0x140018cdf  mov     dl, al; NewIrql
0x140018ce1  mov     byte ptr [rsi+58h], 0
0x140018ce5  mov     rcx, rbp; SpinLock
0x140018ce8  call    cs:__imp_KeReleaseSpinLock
0x140018cef  nop     dword ptr [rax+rax+00h]
0x140018cf4  jmp     loc_140018D91
0x140018cf9  lea     r8d, [r11+1]
0x140018cfd  mov     [rbx+0C0h], r8d
0x140018d04  cmp     r8d, [rsi+38h]
0x140018d08  jnz     short loc_140018D1A
0x140018d0a  inc     rcx
0x140018d0d  mov     dword ptr [rbx+0C0h], 0
0x140018d17  xor     r8d, r8d
0x140018d1a  mov     eax, [rsi+40h]
0x140018d1d  imul    rax, rcx
0x140018d21  mov     [rbx+10h], rax
0x140018d25  mov     r9d, [rsi+40h]
0x140018d29  mov     [rbx+8], r9d
0x140018d2d  mov     edx, [rdi+8]
0x140018d30  mov     eax, edx
0x140018d32  add     rax, [rdi+10h]
0x140018d36  lea     rcx, [r10+r9]
0x140018d3a  cmp     rcx, rax
0x140018d3d  jbe     short loc_140018D4D
0x140018d3f  mov     r9d, [rdi+10h]
0x140018d43  sub     edx, r10d
0x140018d46  add     r9d, edx; Length
0x140018d49  mov     [rbx+8], r9d
0x140018d4d  mov     rax, [rsi+30h]
0x140018d51  mov     rdx, [rbx+18h]; TargetMdl
0x140018d55  mov     rcx, [rax+r8*8]
0x140018d59  mov     [rbx+30h], rcx
0x140018d5d  mov     rcx, [rdi+18h]; SourceMdl
0x140018d61  sub     r10d, [rdi+10h]
0x140018d65  mov     r8d, r10d
0x140018d68  mov     eax, [rcx+2Ch]
0x140018d6b  add     r8, rax
0x140018d6e  add     r8, [rcx+20h]; VirtualAddress
0x140018d72  call    cs:__imp_IoBuildPartialMdl
0x140018d79  nop     dword ptr [rax+rax+00h]
0x140018d7e  mov     rcx, [rbx+30h]
0x140018d82  mov     rdx, rbx
0x140018d85  mov     rax, [rcx]
0x140018d88  mov     rax, [rax+8]
0x140018d8c  call    _guard_dispatch_icall
0x140018d91  add     rsp, 28h
0x140018d95  pop     rdi
0x140018d96  pop     rsi
0x140018d97  pop     rbp
0x140018d98  pop     rbx
0x140018d99  retn
```
