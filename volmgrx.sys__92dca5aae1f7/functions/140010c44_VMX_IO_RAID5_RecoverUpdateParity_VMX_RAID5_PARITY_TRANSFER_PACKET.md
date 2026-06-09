# VMX_IO_RAID5::RecoverUpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)

- ea: `0x140010c44`
- end: `0x140010e06`
- name: `?RecoverUpdateParity@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z`
- size: `450`
- prototype: `void __fastcall(VMX_IO_RAID5 *__hidden this, struct VMX_RAID5_PARITY_TRANSFER_PACKET *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140014380`
- `0x140014410`

## callees

- `0x140002470`
- `0x14000a2f8`
- `0x14000b5b8`
- `0x140010c44`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d14`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010d2f`

## pseudocode

```c
void __fastcall VMX_IO_RAID5::RecoverUpdateParity(KSPIN_LOCK *this, struct VMX_RAID5_PARITY_TRANSFER_PACKET *a2)
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
  __int64 v13; // rcx

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
        *((_QWORD *)v8 + 42) = VmxpRaid5RecoverUpdateParityPhase11;
        *((_QWORD *)v8 + 43) = *((_QWORD *)a2 + 6);
        *((_QWORD *)v8 + 44) = *((_QWORD *)a2 + 7);
        *((_DWORD *)v8 + 90) = *((_DWORD *)a2 + 16);
        *((_QWORD *)v8 + 46) = *((_QWORD *)a2 + 9);
        *((_BYTE *)v8 + 377) = *((_BYTE *)a2 + 81);
        *((_QWORD *)v8 + 3) = *((_QWORD *)v8 + 36);
        *((_DWORD *)v8 + 2) = v5;
        *((_QWORD *)v8 + 2) = *((_QWORD *)a2 + 2);
        *((_QWORD *)v8 + 5) = VmxpRaid5RecoverUpdateParityPhase1;
        v13 = *((_QWORD *)a2 + 6);
        *((_QWORD *)v8 + 6) = v13;
        *((_QWORD *)v8 + 7) = *((_QWORD *)a2 + 7);
        *((_DWORD *)v8 + 16) = *((_DWORD *)a2 + 16);
        *((_QWORD *)v8 + 9) = *((_QWORD *)a2 + 9);
        *((_BYTE *)v8 + 81) = *((_BYTE *)a2 + 81);
        *((_BYTE *)v8 + 82) = 1;
        *((_QWORD *)v8 + 28) = a2;
        *((_QWORD *)v8 + 29) = this;
        *((_DWORD *)v8 + 60) = *((_DWORD *)a2 + 50);
        *((_DWORD *)v8 + 3) = 33685511;
        (*(void (__fastcall **)(__int64, VMX_RAID5_RECOVER_TRANSFER_PACKET *))(*(_QWORD *)v13 + 8LL))(v13, v8);
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
  *((_QWORD *)a2 + 24) = *((_QWORD *)a2 + 5);
  *((_QWORD *)a2 + 5) = VmxpRaid5RecoverUpdateParityEmergencyCompletion;
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
0x140010c44  push    rbx
0x140010c46  push    rbp
0x140010c47  push    rsi
0x140010c48  push    rdi
0x140010c49  sub     rsp, 28h
0x140010c4d  mov     rax, [rcx]
0x140010c50  mov     rdi, rdx
0x140010c53  mov     rsi, rcx
0x140010c56  mov     rax, [rax+28h]
0x140010c5a  call    _guard_dispatch_icall
0x140010c5f  mov     r8d, [rdi+8]
0x140010c63  mov     ecx, 1F0h; unsigned __int64
0x140010c68  mov     [rdi+68h], r8
0x140010c6c  mov     ebp, eax
0x140010c6e  mov     dword ptr [rdi+60h], 0
0x140010c75  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140010c7a  test    rax, rax
0x140010c7d  jz      short loc_140010CB4
0x140010c7f  mov     rcx, rax; this
0x140010c82  call    ??0VMX_RAID5_RECOVER_TRANSFER_PACKET@@QEAA@XZ; VMX_RAID5_RECOVER_TRANSFER_PACKET::VMX_RAID5_RECOVER_TRANSFER_PACKET(void)
0x140010c87  mov     rbx, rax
0x140010c8a  test    rax, rax
0x140010c8d  jz      short loc_140010CB4
0x140010c8f  mov     edx, ebp; Length
0x140010c91  mov     rcx, rax; this
0x140010c94  call    ?AllocateMdls@VMX_RAID5_RECOVER_TRANSFER_PACKET@@QEAAJK@Z; VMX_RAID5_RECOVER_TRANSFER_PACKET::AllocateMdls(ulong)
0x140010c99  test    eax, eax
0x140010c9b  jns     loc_140010D42
0x140010ca1  mov     rax, [rbx]
0x140010ca4  mov     edx, 1
0x140010ca9  mov     rcx, rbx
0x140010cac  mov     rax, [rax]
0x140010caf  call    _guard_dispatch_icall
0x140010cb4  lea     rbx, [rsi+18h]
0x140010cb8  mov     rcx, rbx; SpinLock
0x140010cbb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010cc2  nop     dword ptr [rax+rax+00h]
0x140010cc7  cmp     byte ptr [rsi+10Bh], 0
0x140010cce  mov     dl, al; NewIrql
0x140010cd0  jz      short loc_140010D25
0x140010cd2  mov     rcx, [rdi+28h]
0x140010cd6  lea     rax, ?VmxpRaid5RecoverUpdateParityEmergencyCompletion@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityEmergencyCompletion(VMX_TRANSFER_PACKET *)
0x140010cdd  add     rsi, 148h
0x140010ce4  mov     [rdi+0C0h], rcx
0x140010ceb  mov     [rdi+28h], rax
0x140010cef  mov     rcx, [rsi+8]
0x140010cf3  cmp     [rcx], rsi
0x140010cf6  jz      short loc_140010CFF
0x140010cf8  mov     ecx, 3
0x140010cfd  int     29h; Win8: RtlFailFast(ecx)
0x140010cff  lea     rax, [rdi+70h]
0x140010d03  mov     [rax+8], rcx
0x140010d07  mov     [rax], rsi
0x140010d0a  mov     [rcx], rax
0x140010d0d  mov     rcx, rbx; SpinLock
0x140010d10  mov     [rsi+8], rax
0x140010d14  call    cs:__imp_KeReleaseSpinLock
0x140010d1b  nop     dword ptr [rax+rax+00h]
0x140010d20  jmp     loc_140010DFC
0x140010d25  mov     rcx, rbx; SpinLock
0x140010d28  mov     byte ptr [rsi+10Bh], 1
0x140010d2f  call    cs:__imp_KeReleaseSpinLock
0x140010d36  nop     dword ptr [rax+rax+00h]
0x140010d3b  mov     rbx, [rsi+140h]
0x140010d42  lea     rax, ?VmxpRaid5RecoverUpdateParityPhase11@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase11(VMX_TRANSFER_PACKET *)
0x140010d49  mov     rdx, rbx
0x140010d4c  mov     [rbx+150h], rax
0x140010d53  mov     rax, [rdi+30h]
0x140010d57  mov     [rbx+158h], rax
0x140010d5e  mov     rax, [rdi+38h]
0x140010d62  mov     [rbx+160h], rax
0x140010d69  mov     eax, [rdi+40h]
0x140010d6c  mov     [rbx+168h], eax
0x140010d72  mov     rax, [rdi+48h]
0x140010d76  mov     [rbx+170h], rax
0x140010d7d  mov     al, [rdi+51h]
0x140010d80  mov     [rbx+179h], al
0x140010d86  mov     rax, [rbx+120h]
0x140010d8d  mov     [rbx+18h], rax
0x140010d91  mov     [rbx+8], ebp
0x140010d94  mov     rax, [rdi+10h]
0x140010d98  mov     [rbx+10h], rax
0x140010d9c  lea     rax, ?VmxpRaid5RecoverUpdateParityPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverUpdateParityPhase1(VMX_TRANSFER_PACKET *)
0x140010da3  mov     [rbx+28h], rax
0x140010da7  mov     rcx, [rdi+30h]
0x140010dab  mov     [rbx+30h], rcx
0x140010daf  mov     rax, [rdi+38h]
0x140010db3  mov     [rbx+38h], rax
0x140010db7  mov     eax, [rdi+40h]
0x140010dba  mov     [rbx+40h], eax
0x140010dbd  mov     rax, [rdi+48h]
0x140010dc1  mov     [rbx+48h], rax
0x140010dc5  mov     al, [rdi+51h]
0x140010dc8  mov     [rbx+51h], al
0x140010dcb  mov     byte ptr [rbx+52h], 1
0x140010dcf  mov     [rbx+0E0h], rdi
0x140010dd6  mov     [rbx+0E8h], rsi
0x140010ddd  mov     eax, [rdi+0C8h]
0x140010de3  mov     [rbx+0F0h], eax
0x140010de9  mov     dword ptr [rbx+0Ch], 2020007h
0x140010df0  mov     rax, [rcx]
0x140010df3  mov     rax, [rax+8]
0x140010df7  call    _guard_dispatch_icall
0x140010dfc  add     rsp, 28h
0x140010e00  pop     rdi
0x140010e01  pop     rsi
0x140010e02  pop     rbp
0x140010e03  pop     rbx
0x140010e04  retn
```
