# VMX_IO_RAID5::ReadStripe(VMX_RAID5_TRANSFER_PACKET *)

- ea: `0x140010a30`
- end: `0x140010abd`
- name: `?ReadStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@@Z`
- size: `141`
- prototype: `void __fastcall(VMX_IO_RAID5 *__hidden this, struct VMX_RAID5_TRANSFER_PACKET *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ea38`
- `0x14000f068`
- `0x1400174d0`

## callees

- `0x140010a30`
- `0x140010ac4`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a56`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a56`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a7c`

## pseudocode

```c
void __fastcall VMX_IO_RAID5::ReadStripe(VMX_IO_RAID5 *this, struct VMX_RAID5_TRANSFER_PACKET *a2)
{
  KIRQL v4; // al
  int v5; // ebx
  __int64 v6; // rcx

  *((_QWORD *)a2 + 6) = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * *((unsigned int *)a2 + 60));
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 3);
  v5 = *(_DWORD *)(*((_QWORD *)this + 14) + 24LL * *((unsigned int *)a2 + 60) + 16);
  KeReleaseSpinLock((PKSPIN_LOCK)this + 3, v4);
  if ( v5 )
  {
    VMX_IO_RAID5::ReconstructStripe((KSPIN_LOCK *)this, a2, 1);
  }
  else
  {
    v6 = *((_QWORD *)a2 + 6);
    *((_DWORD *)a2 + 3) = 33619969;
    (*(void (__fastcall **)(__int64, struct VMX_RAID5_TRANSFER_PACKET *))(*(_QWORD *)v6 + 8LL))(v6, a2);
  }
}

```

## disassembly

```asm
0x140010a30  push    rbx
0x140010a32  push    rbp
0x140010a33  push    rsi
0x140010a34  push    rdi
0x140010a35  sub     rsp, 28h
0x140010a39  mov     rax, [rcx+30h]
0x140010a3d  mov     rbp, rcx
0x140010a40  mov     r8d, [rdx+0F0h]
0x140010a47  add     rcx, 18h; SpinLock
0x140010a4b  mov     rsi, rdx
0x140010a4e  mov     r8, [rax+r8*8]
0x140010a52  mov     [rdx+30h], r8
0x140010a56  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010a5d  nop     dword ptr [rax+rax+00h]
0x140010a62  mov     rdx, [rbp+70h]
0x140010a66  lea     rcx, [rbp+18h]; SpinLock
0x140010a6a  mov     r8d, [rsi+0F0h]
0x140010a71  lea     r9, [r8+r8*2]
0x140010a75  mov     ebx, [rdx+r9*8+10h]
0x140010a7a  mov     dl, al; NewIrql
0x140010a7c  call    cs:__imp_KeReleaseSpinLock
0x140010a83  nop     dword ptr [rax+rax+00h]
0x140010a88  mov     rdx, rsi; struct VMX_RAID5_TRANSFER_PACKET *
0x140010a8b  test    ebx, ebx
0x140010a8d  jnz     short loc_140010AA8
0x140010a8f  mov     rcx, [rsi+30h]
0x140010a93  mov     dword ptr [rsi+0Ch], 2010001h
0x140010a9a  mov     rax, [rcx]
0x140010a9d  mov     rax, [rax+8]
0x140010aa1  call    _guard_dispatch_icall
0x140010aa6  jmp     short loc_140010AB3
0x140010aa8  mov     r8b, 1; unsigned __int8
0x140010aab  mov     rcx, rbp; this
0x140010aae  call    ?ReconstructStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@E@Z; VMX_IO_RAID5::ReconstructStripe(VMX_RAID5_TRANSFER_PACKET *,uchar)
0x140010ab3  add     rsp, 28h
0x140010ab7  pop     rdi
0x140010ab8  pop     rsi
0x140010ab9  pop     rbp
0x140010aba  pop     rbx
0x140010abb  retn
```
