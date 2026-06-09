# VMX_IO_MIRROR::RecoverWrite(VMX_MIRROR_TRANSFER_PACKET *)

- ea: `0x140003f3c`
- end: `0x1400040df`
- name: `?RecoverWrite@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z`
- size: `419`
- prototype: `void __fastcall(VMX_IO_MIRROR *__hidden this, struct VMX_MIRROR_TRANSFER_PACKET *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002be0`
- `0x1400141d0`

## callees

- `0x140002470`
- `0x140003f3c`
- `0x14000a2a4`
- `0x14000b4dc`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003fb3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003fb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000400c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004027`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000400c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004027`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004054`
- `ntoskrnl!IoBuildPartialMdl` at `0x140004054`

## pseudocode

```c
void __fastcall VMX_IO_MIRROR::RecoverWrite(KSPIN_LOCK *this, struct VMX_MIRROR_TRANSFER_PACKET *a2)
{
  ULONG v4; // eax
  ULONG v5; // ebp
  VMX_MIRROR_RECOVER_TRANSFER_PACKET *v6; // rax
  VMX_MIRROR_RECOVER_TRANSFER_PACKET *v7; // rax
  VMX_MIRROR_RECOVER_TRANSFER_PACKET *v8; // rbx
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
  v6 = (VMX_MIRROR_RECOVER_TRANSFER_PACKET *)VMX_TRANSFER_PACKET::operator new(0x138u);
  if ( v6 )
  {
    v7 = VMX_MIRROR_RECOVER_TRANSFER_PACKET::VMX_MIRROR_RECOVER_TRANSFER_PACKET(v6);
    v8 = v7;
    if ( v7 )
    {
      if ( (int)VMX_MIRROR_RECOVER_TRANSFER_PACKET::AllocateMdls(v7, v5) >= 0 )
      {
LABEL_10:
        v13 = (struct _MDL *)*((_QWORD *)v8 + 37);
        *((_QWORD *)v8 + 3) = v13;
        IoBuildPartialMdl(
          *((PMDL *)a2 + 3),
          v13,
          (PVOID)(*(_QWORD *)(*((_QWORD *)a2 + 3) + 32LL) + *(unsigned int *)(*((_QWORD *)a2 + 3) + 44LL)),
          v5);
        *((_DWORD *)v8 + 2) = v5;
        *((_QWORD *)v8 + 2) = *((_QWORD *)a2 + 2);
        *((_QWORD *)v8 + 5) = VmxpMirrorRecoverWritePhase1;
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
        *((_BYTE *)v8 + 272) = 0;
        *((_DWORD *)v8 + 3) = 16908290;
        (*(void (__fastcall **)(__int64, VMX_MIRROR_RECOVER_TRANSFER_PACKET *))(*(_QWORD *)v14 + 8LL))(v14, v8);
        return;
      }
      (**(void (__fastcall ***)(VMX_MIRROR_RECOVER_TRANSFER_PACKET *, __int64))v8)(v8, 1);
    }
  }
  v9 = this + 3;
  v10 = KeAcquireSpinLockRaiseToDpc(this + 3);
  if ( !*((_BYTE *)this + 161) )
  {
    *((_BYTE *)this + 161) = 1;
    KeReleaseSpinLock(this + 3, v10);
    v8 = (VMX_MIRROR_RECOVER_TRANSFER_PACKET *)this[24];
    goto LABEL_10;
  }
  v11 = (char *)(this + 25);
  *((_QWORD *)a2 + 33) = *((_QWORD *)a2 + 5);
  *((_QWORD *)a2 + 5) = VmxpMirrorRecoverWriteEmergencyCompletion;
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
0x140003f3c  push    rbx
0x140003f3e  push    rbp
0x140003f3f  push    rsi
0x140003f40  push    rdi
0x140003f41  sub     rsp, 28h
0x140003f45  mov     rax, [rcx]
0x140003f48  mov     rdi, rdx
0x140003f4b  mov     rsi, rcx
0x140003f4e  mov     rax, [rax+28h]
0x140003f52  call    _guard_dispatch_icall
0x140003f57  mov     r8d, [rdi+8]
0x140003f5b  mov     ecx, 138h; unsigned __int64
0x140003f60  mov     [rdi+68h], r8
0x140003f64  mov     ebp, eax
0x140003f66  mov     dword ptr [rdi+60h], 0
0x140003f6d  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140003f72  test    rax, rax
0x140003f75  jz      short loc_140003FAC
0x140003f77  mov     rcx, rax; this
0x140003f7a  call    ??0VMX_MIRROR_RECOVER_TRANSFER_PACKET@@QEAA@XZ; VMX_MIRROR_RECOVER_TRANSFER_PACKET::VMX_MIRROR_RECOVER_TRANSFER_PACKET(void)
0x140003f7f  mov     rbx, rax
0x140003f82  test    rax, rax
0x140003f85  jz      short loc_140003FAC
0x140003f87  mov     edx, ebp; Length
0x140003f89  mov     rcx, rax; this
0x140003f8c  call    ?AllocateMdls@VMX_MIRROR_RECOVER_TRANSFER_PACKET@@QEAAJK@Z; VMX_MIRROR_RECOVER_TRANSFER_PACKET::AllocateMdls(ulong)
0x140003f91  test    eax, eax
0x140003f93  jns     loc_14000403A
0x140003f99  mov     rax, [rbx]
0x140003f9c  mov     edx, 1
0x140003fa1  mov     rcx, rbx
0x140003fa4  mov     rax, [rax]
0x140003fa7  call    _guard_dispatch_icall
0x140003fac  lea     rbx, [rsi+18h]
0x140003fb0  mov     rcx, rbx; SpinLock
0x140003fb3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003fba  nop     dword ptr [rax+rax+00h]
0x140003fbf  cmp     byte ptr [rsi+0A1h], 0
0x140003fc6  mov     dl, al; NewIrql
0x140003fc8  jz      short loc_14000401D
0x140003fca  mov     rcx, [rdi+28h]
0x140003fce  lea     rax, ?VmxpMirrorRecoverWriteEmergencyCompletion@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverWriteEmergencyCompletion(VMX_TRANSFER_PACKET *)
0x140003fd5  add     rsi, 0C8h
0x140003fdc  mov     [rdi+108h], rcx
0x140003fe3  mov     [rdi+28h], rax
0x140003fe7  mov     rcx, [rsi+8]
0x140003feb  cmp     [rcx], rsi
0x140003fee  jz      short loc_140003FF7
0x140003ff0  mov     ecx, 3
0x140003ff5  int     29h; Win8: RtlFailFast(ecx)
0x140003ff7  lea     rax, [rdi+70h]
0x140003ffb  mov     [rax+8], rcx
0x140003fff  mov     [rax], rsi
0x140004002  mov     [rcx], rax
0x140004005  mov     rcx, rbx; SpinLock
0x140004008  mov     [rsi+8], rax
0x14000400c  call    cs:__imp_KeReleaseSpinLock
0x140004013  nop     dword ptr [rax+rax+00h]
0x140004018  jmp     loc_1400040D5
0x14000401d  mov     rcx, rbx; SpinLock
0x140004020  mov     byte ptr [rsi+0A1h], 1
0x140004027  call    cs:__imp_KeReleaseSpinLock
0x14000402e  nop     dword ptr [rax+rax+00h]
0x140004033  mov     rbx, [rsi+0C0h]
0x14000403a  mov     rdx, [rbx+128h]; TargetMdl
0x140004041  mov     r9d, ebp; Length
0x140004044  mov     [rbx+18h], rdx
0x140004048  mov     rcx, [rdi+18h]; SourceMdl
0x14000404c  mov     r8d, [rcx+2Ch]
0x140004050  add     r8, [rcx+20h]; VirtualAddress
0x140004054  call    cs:__imp_IoBuildPartialMdl
0x14000405b  nop     dword ptr [rax+rax+00h]
0x140004060  mov     [rbx+8], ebp
0x140004063  mov     rdx, rbx
0x140004066  mov     rax, [rdi+10h]
0x14000406a  mov     [rbx+10h], rax
0x14000406e  lea     rax, ?VmxpMirrorRecoverWritePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverWritePhase1(VMX_TRANSFER_PACKET *)
0x140004075  mov     [rbx+28h], rax
0x140004079  mov     rcx, [rdi+30h]
0x14000407d  mov     [rbx+30h], rcx
0x140004081  mov     rax, [rdi+38h]
0x140004085  mov     [rbx+38h], rax
0x140004089  mov     eax, [rdi+40h]
0x14000408c  mov     [rbx+40h], eax
0x14000408f  mov     rax, [rdi+48h]
0x140004093  mov     [rbx+48h], rax
0x140004097  mov     al, [rdi+51h]
0x14000409a  mov     [rbx+51h], al
0x14000409d  mov     byte ptr [rbx+52h], 0
0x1400040a1  mov     [rbx+0E0h], rdi
0x1400040a8  mov     [rbx+0E8h], rsi
0x1400040af  mov     eax, [rdi+0F0h]
0x1400040b5  mov     [rbx+0F0h], eax
0x1400040bb  mov     byte ptr [rbx+110h], 0
0x1400040c2  mov     dword ptr [rbx+0Ch], 1020002h
0x1400040c9  mov     rax, [rcx]
0x1400040cc  mov     rax, [rax+8]
0x1400040d0  call    _guard_dispatch_icall
0x1400040d5  add     rsp, 28h
0x1400040d9  pop     rdi
0x1400040da  pop     rsi
0x1400040db  pop     rbp
0x1400040dc  pop     rbx
0x1400040dd  retn
```
