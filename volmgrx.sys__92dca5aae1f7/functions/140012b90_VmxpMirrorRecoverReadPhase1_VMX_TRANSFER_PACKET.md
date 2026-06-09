# VmxpMirrorRecoverReadPhase1(VMX_TRANSFER_PACKET *)

- ea: `0x140012b90`
- end: `0x140012d3d`
- name: `?VmxpMirrorRecoverReadPhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `429`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010bb0`

## callees

- `0x140002470`
- `0x14000a2a4`
- `0x14000b4dc`
- `0x140012b90`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012c18`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012c18`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c8c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012c8c`
- `ntoskrnl!IoBuildPartialMdl` at `0x140012cb9`
- `ntoskrnl!IoBuildPartialMdl` at `0x140012cb9`

## pseudocode

```c
void __fastcall VmxpMirrorRecoverReadPhase1(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rsi
  ULONG v3; // ebp
  __int64 v4; // rdx
  VMX_MIRROR_RECOVER_TRANSFER_PACKET *v5; // rax
  VMX_MIRROR_RECOVER_TRANSFER_PACKET *v6; // rax
  VMX_MIRROR_RECOVER_TRANSFER_PACKET *v7; // rdi
  KSPIN_LOCK *v8; // rdi
  KIRQL v9; // dl
  __int64 v10; // rsi
  _QWORD *v11; // rcx
  struct _MDL *v12; // rdx
  __int64 v13; // rcx

  v1 = *((_QWORD *)a1 + 29);
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 40LL))(v1);
  v4 = *((_QWORD *)a1 + 33);
  *((_QWORD *)a1 + 13) = *((unsigned int *)a1 + 2);
  *((_QWORD *)a1 + 5) = v4;
  *((_DWORD *)a1 + 24) = 0;
  v5 = (VMX_MIRROR_RECOVER_TRANSFER_PACKET *)VMX_TRANSFER_PACKET::operator new(0x138u);
  if ( v5 )
  {
    v6 = VMX_MIRROR_RECOVER_TRANSFER_PACKET::VMX_MIRROR_RECOVER_TRANSFER_PACKET(v5);
    v7 = v6;
    if ( v6 )
    {
      if ( (int)VMX_MIRROR_RECOVER_TRANSFER_PACKET::AllocateMdls(v6, v3) >= 0 )
      {
LABEL_10:
        v12 = (struct _MDL *)*((_QWORD *)v7 + 37);
        *((_QWORD *)v7 + 3) = v12;
        IoBuildPartialMdl(
          *((PMDL *)a1 + 3),
          v12,
          (PVOID)(*(_QWORD *)(*((_QWORD *)a1 + 3) + 32LL) + *(unsigned int *)(*((_QWORD *)a1 + 3) + 44LL)),
          v3);
        *((_DWORD *)v7 + 2) = v3;
        *((_QWORD *)v7 + 2) = *((_QWORD *)a1 + 2);
        *((_QWORD *)v7 + 5) = VmxpMirrorRecoverReadPhase2;
        v13 = *((_QWORD *)a1 + 6);
        *((_QWORD *)v7 + 6) = v13;
        *((_QWORD *)v7 + 7) = *((_QWORD *)a1 + 7);
        *((_DWORD *)v7 + 16) = *((_DWORD *)a1 + 16);
        *((_QWORD *)v7 + 9) = *((_QWORD *)a1 + 9);
        *((_BYTE *)v7 + 81) = *((_BYTE *)a1 + 81);
        *((_BYTE *)v7 + 82) = 1;
        *((_QWORD *)v7 + 28) = a1;
        *((_QWORD *)v7 + 29) = v1;
        *((_DWORD *)v7 + 60) = *((_DWORD *)a1 + 60);
        *((_DWORD *)v7 + 3) = 16842756;
        (*(void (__fastcall **)(__int64, VMX_MIRROR_RECOVER_TRANSFER_PACKET *))(*(_QWORD *)v13 + 8LL))(v13, v7);
        return;
      }
      (**(void (__fastcall ***)(VMX_MIRROR_RECOVER_TRANSFER_PACKET *, __int64))v7)(v7, 1);
    }
  }
  v8 = (KSPIN_LOCK *)(v1 + 24);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
  if ( !*(_BYTE *)(v1 + 161) )
  {
    *(_BYTE *)(v1 + 161) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), v9);
    v7 = *(VMX_MIRROR_RECOVER_TRANSFER_PACKET **)(v1 + 192);
    goto LABEL_10;
  }
  v10 = v1 + 200;
  *((_QWORD *)a1 + 33) = *((_QWORD *)a1 + 5);
  *((_QWORD *)a1 + 5) = VmxpMirrorRecoverReadEmergencyCompletion;
  v11 = *(_QWORD **)(v10 + 8);
  if ( *v11 != v10 )
    __fastfail(3u);
  *((_QWORD *)a1 + 15) = v11;
  *((_QWORD *)a1 + 14) = v10;
  *v11 = (char *)a1 + 112;
  *(_QWORD *)(v10 + 8) = (char *)a1 + 112;
  KeReleaseSpinLock(v8, v9);
}

```

## disassembly

```asm
0x140012b90  push    rbx
0x140012b92  push    rbp
0x140012b93  push    rsi
0x140012b94  push    rdi
0x140012b95  sub     rsp, 28h
0x140012b99  mov     rsi, [rcx+0E8h]
0x140012ba0  mov     rbx, rcx
0x140012ba3  mov     rcx, rsi
0x140012ba6  mov     rax, [rsi]
0x140012ba9  mov     rax, [rax+28h]
0x140012bad  call    _guard_dispatch_icall
0x140012bb2  mov     ecx, [rbx+8]
0x140012bb5  mov     ebp, eax
0x140012bb7  mov     rdx, [rbx+108h]
0x140012bbe  mov     [rbx+68h], rcx
0x140012bc2  mov     ecx, 138h; unsigned __int64
0x140012bc7  mov     [rbx+28h], rdx
0x140012bcb  mov     dword ptr [rbx+60h], 0
0x140012bd2  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140012bd7  test    rax, rax
0x140012bda  jz      short loc_140012C11
0x140012bdc  mov     rcx, rax; this
0x140012bdf  call    ??0VMX_MIRROR_RECOVER_TRANSFER_PACKET@@QEAA@XZ; VMX_MIRROR_RECOVER_TRANSFER_PACKET::VMX_MIRROR_RECOVER_TRANSFER_PACKET(void)
0x140012be4  mov     rdi, rax
0x140012be7  test    rax, rax
0x140012bea  jz      short loc_140012C11
0x140012bec  mov     edx, ebp; Length
0x140012bee  mov     rcx, rax; this
0x140012bf1  call    ?AllocateMdls@VMX_MIRROR_RECOVER_TRANSFER_PACKET@@QEAAJK@Z; VMX_MIRROR_RECOVER_TRANSFER_PACKET::AllocateMdls(ulong)
0x140012bf6  test    eax, eax
0x140012bf8  jns     loc_140012C9F
0x140012bfe  mov     rax, [rdi]
0x140012c01  mov     edx, 1
0x140012c06  mov     rcx, rdi
0x140012c09  mov     rax, [rax]
0x140012c0c  call    _guard_dispatch_icall
0x140012c11  lea     rdi, [rsi+18h]
0x140012c15  mov     rcx, rdi; SpinLock
0x140012c18  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012c1f  nop     dword ptr [rax+rax+00h]
0x140012c24  cmp     byte ptr [rsi+0A1h], 0
0x140012c2b  mov     dl, al; NewIrql
0x140012c2d  jz      short loc_140012C82
0x140012c2f  mov     rcx, [rbx+28h]
0x140012c33  lea     rax, ?VmxpMirrorRecoverReadEmergencyCompletion@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadEmergencyCompletion(VMX_TRANSFER_PACKET *)
0x140012c3a  add     rsi, 0C8h
0x140012c41  mov     [rbx+108h], rcx
0x140012c48  mov     [rbx+28h], rax
0x140012c4c  mov     rcx, [rsi+8]
0x140012c50  cmp     [rcx], rsi
0x140012c53  jz      short loc_140012C5C
0x140012c55  mov     ecx, 3
0x140012c5a  int     29h; Win8: RtlFailFast(ecx)
0x140012c5c  lea     rax, [rbx+70h]
0x140012c60  mov     [rax+8], rcx
0x140012c64  mov     [rax], rsi
0x140012c67  mov     [rcx], rax
0x140012c6a  mov     rcx, rdi; SpinLock
0x140012c6d  mov     [rsi+8], rax
0x140012c71  call    cs:__imp_KeReleaseSpinLock
0x140012c78  nop     dword ptr [rax+rax+00h]
0x140012c7d  jmp     loc_140012D33
0x140012c82  mov     rcx, rdi; SpinLock
0x140012c85  mov     byte ptr [rsi+0A1h], 1
0x140012c8c  call    cs:__imp_KeReleaseSpinLock
0x140012c93  nop     dword ptr [rax+rax+00h]
0x140012c98  mov     rdi, [rsi+0C0h]
0x140012c9f  mov     rdx, [rdi+128h]; TargetMdl
0x140012ca6  mov     r9d, ebp; Length
0x140012ca9  mov     [rdi+18h], rdx
0x140012cad  mov     rcx, [rbx+18h]; SourceMdl
0x140012cb1  mov     r8d, [rcx+2Ch]
0x140012cb5  add     r8, [rcx+20h]; VirtualAddress
0x140012cb9  call    cs:__imp_IoBuildPartialMdl
0x140012cc0  nop     dword ptr [rax+rax+00h]
0x140012cc5  mov     [rdi+8], ebp
0x140012cc8  mov     rdx, rdi
0x140012ccb  mov     rax, [rbx+10h]
0x140012ccf  mov     [rdi+10h], rax
0x140012cd3  lea     rax, ?VmxpMirrorRecoverReadPhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpMirrorRecoverReadPhase2(VMX_TRANSFER_PACKET *)
0x140012cda  mov     [rdi+28h], rax
0x140012cde  mov     rcx, [rbx+30h]
0x140012ce2  mov     [rdi+30h], rcx
0x140012ce6  mov     rax, [rbx+38h]
0x140012cea  mov     [rdi+38h], rax
0x140012cee  mov     eax, [rbx+40h]
0x140012cf1  mov     [rdi+40h], eax
0x140012cf4  mov     rax, [rbx+48h]
0x140012cf8  mov     [rdi+48h], rax
0x140012cfc  mov     al, [rbx+51h]
0x140012cff  mov     [rdi+51h], al
0x140012d02  mov     byte ptr [rdi+52h], 1
0x140012d06  mov     [rdi+0E0h], rbx
0x140012d0d  mov     [rdi+0E8h], rsi
0x140012d14  mov     eax, [rbx+0F0h]
0x140012d1a  mov     [rdi+0F0h], eax
0x140012d20  mov     dword ptr [rdi+0Ch], 1010004h
0x140012d27  mov     rax, [rcx]
0x140012d2a  mov     rax, [rax+8]
0x140012d2e  call    _guard_dispatch_icall
0x140012d33  add     rsp, 28h
0x140012d37  pop     rdi
0x140012d38  pop     rsi
0x140012d39  pop     rbp
0x140012d3a  pop     rbx
0x140012d3b  retn
```
