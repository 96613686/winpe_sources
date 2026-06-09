# VMX_IO_RAID5::RecoverWriteStripe(VMX_RAID5_TRANSFER_PACKET *)

- ea: `0x140010f4c`
- end: `0x1400110ef`
- name: `?RecoverWriteStripe@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_TRANSFER_PACKET@@@Z`
- size: `419`
- prototype: `void __fastcall(VMX_IO_RAID5 *__hidden this, struct VMX_RAID5_TRANSFER_PACKET *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140014380`
- `0x140016f10`
- `0x140017ad0`

## callees

- `0x140002470`
- `0x14000a2f8`
- `0x14000b5b8`
- `0x140010f4c`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010fc3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010fc3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001101c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011037`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001101c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011037`
- `ntoskrnl!IoBuildPartialMdl` at `0x140011064`
- `ntoskrnl!IoBuildPartialMdl` at `0x140011064`

## pseudocode

```c
void __fastcall VMX_IO_RAID5::RecoverWriteStripe(KSPIN_LOCK *this, struct VMX_RAID5_TRANSFER_PACKET *a2)
{
  ULONG v4; // eax
  ULONG v5; // ebp
  VMX_RAID5_RECOVER_TRANSFER_PACKET *v6; // rax
  VMX_RAID5_RECOVER_TRANSFER_PACKET *v7; // rax
  VMX_RAID5_RECOVER_TRANSFER_PACKET *v8; // rbx
  KSPIN_LOCK *v9; // rbx
  KIRQL v10; // dl
  char *v11; // rsi
  char **v12; // rcx
  struct _MDL *v13; // rdx
  __int64 v14; // rcx

  v4 = (*(__int64 (__fastcall **)(KSPIN_LOCK *))(*this + 40))(this);
  *((_QWORD *)a2 + 13) = *((unsigned int *)a2 + 2);
  v5 = v4;
  *((_DWORD *)a2 + 24) = 0;
  v6 = (VMX_RAID5_RECOVER_TRANSFER_PACKET *)VMX_TRANSFER_PACKET::operator new(0x1F0u);
  if ( v6 )
  {
    v7 = VMX_RAID5_RECOVER_TRANSFER_PACKET::VMX_RAID5_RECOVER_TRANSFER_PACKET(v6);
    v8 = v7;
    if ( v7 )
    {
      if ( (int)VMX_RAID5_RECOVER_TRANSFER_PACKET::AllocateMdls(v7, v5) >= 0 )
      {
LABEL_10:
        v13 = (struct _MDL *)*((_QWORD *)v8 + 34);
        *((_QWORD *)v8 + 3) = v13;
        IoBuildPartialMdl(
          *((PMDL *)a2 + 3),
          v13,
          (PVOID)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 32LL) + *(unsigned int *)(*((_QWORD *)a2 + 3) + 44LL)),
          v5);
        *((_DWORD *)v8 + 2) = v5;
        *((_QWORD *)v8 + 2) = *((_QWORD *)a2 + 2);
        *((_QWORD *)v8 + 5) = VmxpRaid5RecoverWriteStripePhase1;
        v14 = *((_QWORD *)a2 + 6);
        *((_QWORD *)v8 + 6) = v14;
        *((_QWORD *)v8 + 7) = *((_QWORD *)a2 + 7);
        *((_DWORD *)v8 + 16) = *((_DWORD *)a2 + 16);
        *((_QWORD *)v8 + 9) = *((_QWORD *)a2 + 9);
        *((_BYTE *)v8 + 81) = *((_BYTE *)a2 + 81);
        *((_BYTE *)v8 + 82) = 0;
        *((_QWORD *)v8 + 28) = a2;
        *((_QWORD *)v8 + 29) = this;
        *((_DWORD *)v8 + 60) = *((_DWORD *)a2 + 60);
        *((_BYTE *)v8 + 264) = 0;
        *((_DWORD *)v8 + 3) = 33685509;
        (*(void (__fastcall **)(__int64, VMX_RAID5_RECOVER_TRANSFER_PACKET *))(*(_QWORD *)v14 + 8LL))(v14, v8);
        return;
      }
      (**(void (__fastcall ***)(VMX_RAID5_RECOVER_TRANSFER_PACKET *, __int64))v8)(v8, 1);
    }
  }
  v9 = this + 3;
  v10 = KeAcquireSpinLockRaiseToDpc(this + 3);
  if ( !*((_BYTE *)this + 267) )
  {
    *((_BYTE *)this + 267) = 1;
    KeReleaseSpinLock(this + 3, v10);
    v8 = (VMX_RAID5_RECOVER_TRANSFER_PACKET *)this[40];
    goto LABEL_10;
  }
  v11 = (char *)(this + 41);
  *((_QWORD *)a2 + 31) = *((_QWORD *)a2 + 5);
  *((_QWORD *)a2 + 5) = VmxpRaid5RecoverWriteStripeEmergencyCompletion;
  v12 = (char **)*((_QWORD *)v11 + 1);
  if ( *v12 != v11 )
    __fastfail(3u);
  *((_QWORD *)a2 + 15) = v12;
  *((_QWORD *)a2 + 14) = v11;
  *v12 = (char *)a2 + 112;
  *((_QWORD *)v11 + 1) = (char *)a2 + 112;
  KeReleaseSpinLock(v9, v10);
}

```

## disassembly

```asm
0x140010f4c  push    rbx
0x140010f4e  push    rbp
0x140010f4f  push    rsi
0x140010f50  push    rdi
0x140010f51  sub     rsp, 28h
0x140010f55  mov     rax, [rcx]
0x140010f58  mov     rdi, rdx
0x140010f5b  mov     rsi, rcx
0x140010f5e  mov     rax, [rax+28h]
0x140010f62  call    _guard_dispatch_icall
0x140010f67  mov     r8d, [rdi+8]
0x140010f6b  mov     ecx, 1F0h; unsigned __int64
0x140010f70  mov     [rdi+68h], r8
0x140010f74  mov     ebp, eax
0x140010f76  mov     dword ptr [rdi+60h], 0
0x140010f7d  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140010f82  test    rax, rax
0x140010f85  jz      short loc_140010FBC
0x140010f87  mov     rcx, rax; this
0x140010f8a  call    ??0VMX_RAID5_RECOVER_TRANSFER_PACKET@@QEAA@XZ; VMX_RAID5_RECOVER_TRANSFER_PACKET::VMX_RAID5_RECOVER_TRANSFER_PACKET(void)
0x140010f8f  mov     rbx, rax
0x140010f92  test    rax, rax
0x140010f95  jz      short loc_140010FBC
0x140010f97  mov     edx, ebp; Length
0x140010f99  mov     rcx, rax; this
0x140010f9c  call    ?AllocateMdls@VMX_RAID5_RECOVER_TRANSFER_PACKET@@QEAAJK@Z; VMX_RAID5_RECOVER_TRANSFER_PACKET::AllocateMdls(ulong)
0x140010fa1  test    eax, eax
0x140010fa3  jns     loc_14001104A
0x140010fa9  mov     rax, [rbx]
0x140010fac  mov     edx, 1
0x140010fb1  mov     rcx, rbx
0x140010fb4  mov     rax, [rax]
0x140010fb7  call    _guard_dispatch_icall
0x140010fbc  lea     rbx, [rsi+18h]
0x140010fc0  mov     rcx, rbx; SpinLock
0x140010fc3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010fca  nop     dword ptr [rax+rax+00h]
0x140010fcf  cmp     byte ptr [rsi+10Bh], 0
0x140010fd6  mov     dl, al; NewIrql
0x140010fd8  jz      short loc_14001102D
0x140010fda  mov     rcx, [rdi+28h]
0x140010fde  lea     rax, ?VmxpRaid5RecoverWriteStripeEmergencyCompletion@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverWriteStripeEmergencyCompletion(VMX_TRANSFER_PACKET *)
0x140010fe5  add     rsi, 148h
0x140010fec  mov     [rdi+0F8h], rcx
0x140010ff3  mov     [rdi+28h], rax
0x140010ff7  mov     rcx, [rsi+8]
0x140010ffb  cmp     [rcx], rsi
0x140010ffe  jz      short loc_140011007
0x140011000  mov     ecx, 3
0x140011005  int     29h; Win8: RtlFailFast(ecx)
0x140011007  lea     rax, [rdi+70h]
0x14001100b  mov     [rax+8], rcx
0x14001100f  mov     [rax], rsi
0x140011012  mov     [rcx], rax
0x140011015  mov     rcx, rbx; SpinLock
0x140011018  mov     [rsi+8], rax
0x14001101c  call    cs:__imp_KeReleaseSpinLock
0x140011023  nop     dword ptr [rax+rax+00h]
0x140011028  jmp     loc_1400110E5
0x14001102d  mov     rcx, rbx; SpinLock
0x140011030  mov     byte ptr [rsi+10Bh], 1
0x140011037  call    cs:__imp_KeReleaseSpinLock
0x14001103e  nop     dword ptr [rax+rax+00h]
0x140011043  mov     rbx, [rsi+140h]
0x14001104a  mov     rdx, [rbx+110h]; TargetMdl
0x140011051  mov     r9d, ebp; Length
0x140011054  mov     [rbx+18h], rdx
0x140011058  mov     rcx, [rdi+18h]; SourceMdl
0x14001105c  mov     r8d, [rcx+2Ch]
0x140011060  add     r8, [rcx+20h]; VirtualAddress
0x140011064  call    cs:__imp_IoBuildPartialMdl
0x14001106b  nop     dword ptr [rax+rax+00h]
0x140011070  mov     [rbx+8], ebp
0x140011073  mov     rdx, rbx
0x140011076  mov     rax, [rdi+10h]
0x14001107a  mov     [rbx+10h], rax
0x14001107e  lea     rax, ?VmxpRaid5RecoverWriteStripePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverWriteStripePhase1(VMX_TRANSFER_PACKET *)
0x140011085  mov     [rbx+28h], rax
0x140011089  mov     rcx, [rdi+30h]
0x14001108d  mov     [rbx+30h], rcx
0x140011091  mov     rax, [rdi+38h]
0x140011095  mov     [rbx+38h], rax
0x140011099  mov     eax, [rdi+40h]
0x14001109c  mov     [rbx+40h], eax
0x14001109f  mov     rax, [rdi+48h]
0x1400110a3  mov     [rbx+48h], rax
0x1400110a7  mov     al, [rdi+51h]
0x1400110aa  mov     [rbx+51h], al
0x1400110ad  mov     byte ptr [rbx+52h], 0
0x1400110b1  mov     [rbx+0E0h], rdi
0x1400110b8  mov     [rbx+0E8h], rsi
0x1400110bf  mov     eax, [rdi+0F0h]
0x1400110c5  mov     [rbx+0F0h], eax
0x1400110cb  mov     byte ptr [rbx+108h], 0
0x1400110d2  mov     dword ptr [rbx+0Ch], 2020005h
0x1400110d9  mov     rax, [rcx]
0x1400110dc  mov     rax, [rax+8]
0x1400110e0  call    _guard_dispatch_icall
0x1400110e5  add     rsp, 28h
0x1400110e9  pop     rdi
0x1400110ea  pop     rsi
0x1400110eb  pop     rbp
0x1400110ec  pop     rbx
0x1400110ed  retn
```
