# VmxpRaid5RecoverReadStripePhase1(VMX_TRANSFER_PACKET *)

- ea: `0x1400153e0`
- end: `0x14001558d`
- name: `?VmxpRaid5RecoverReadStripePhase1@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `429`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140010c00`

## callees

- `0x140002470`
- `0x14000a2f8`
- `0x14000b5b8`
- `0x1400153e0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015468`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015468`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400154c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400154dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400154c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400154dc`
- `ntoskrnl!IoBuildPartialMdl` at `0x140015509`
- `ntoskrnl!IoBuildPartialMdl` at `0x140015509`

## pseudocode

```c
void __fastcall VmxpRaid5RecoverReadStripePhase1(struct VMX_TRANSFER_PACKET *a1)
{
  __int64 v1; // rsi
  ULONG v3; // ebp
  __int64 v4; // rdx
  VMX_RAID5_RECOVER_TRANSFER_PACKET *v5; // rax
  VMX_RAID5_RECOVER_TRANSFER_PACKET *v6; // rax
  VMX_RAID5_RECOVER_TRANSFER_PACKET *v7; // rdi
  KSPIN_LOCK *v8; // rdi
  KIRQL v9; // dl
  __int64 v10; // rsi
  _QWORD *v11; // rcx
  struct _MDL *v12; // rdx
  __int64 v13; // rcx

  v1 = *((_QWORD *)a1 + 29);
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 40LL))(v1);
  v4 = *((_QWORD *)a1 + 31);
  *((_QWORD *)a1 + 13) = *((unsigned int *)a1 + 2);
  *((_QWORD *)a1 + 5) = v4;
  *((_DWORD *)a1 + 24) = 0;
  v5 = (VMX_RAID5_RECOVER_TRANSFER_PACKET *)VMX_TRANSFER_PACKET::operator new(0x1F0u);
  if ( v5 )
  {
    v6 = VMX_RAID5_RECOVER_TRANSFER_PACKET::VMX_RAID5_RECOVER_TRANSFER_PACKET(v5);
    v7 = v6;
    if ( v6 )
    {
      if ( (int)VMX_RAID5_RECOVER_TRANSFER_PACKET::AllocateMdls(v6, v3) >= 0 )
      {
LABEL_10:
        v12 = (struct _MDL *)*((_QWORD *)v7 + 34);
        *((_QWORD *)v7 + 3) = v12;
        IoBuildPartialMdl(
          *((PMDL *)a1 + 3),
          v12,
          (PVOID)(*(_QWORD *)(*((_QWORD *)a1 + 3) + 32LL) + *(unsigned int *)(*((_QWORD *)a1 + 3) + 44LL)),
          v3);
        *((_DWORD *)v7 + 2) = v3;
        *((_QWORD *)v7 + 2) = *((_QWORD *)a1 + 2);
        *((_QWORD *)v7 + 5) = VmxpRaid5RecoverReadStripePhase2;
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
        *((_DWORD *)v7 + 3) = 33619971;
        (*(void (__fastcall **)(__int64, VMX_RAID5_RECOVER_TRANSFER_PACKET *))(*(_QWORD *)v13 + 8LL))(v13, v7);
        return;
      }
      (**(void (__fastcall ***)(VMX_RAID5_RECOVER_TRANSFER_PACKET *, __int64))v7)(v7, 1);
    }
  }
  v8 = (KSPIN_LOCK *)(v1 + 24);
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
  if ( !*(_BYTE *)(v1 + 267) )
  {
    *(_BYTE *)(v1 + 267) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), v9);
    v7 = *(VMX_RAID5_RECOVER_TRANSFER_PACKET **)(v1 + 320);
    goto LABEL_10;
  }
  v10 = v1 + 328;
  *((_QWORD *)a1 + 31) = *((_QWORD *)a1 + 5);
  *((_QWORD *)a1 + 5) = VmxpRaid5RecoverReadStripeEmergencyCompletion;
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
0x1400153e0  push    rbx
0x1400153e2  push    rbp
0x1400153e3  push    rsi
0x1400153e4  push    rdi
0x1400153e5  sub     rsp, 28h
0x1400153e9  mov     rsi, [rcx+0E8h]
0x1400153f0  mov     rbx, rcx
0x1400153f3  mov     rcx, rsi
0x1400153f6  mov     rax, [rsi]
0x1400153f9  mov     rax, [rax+28h]
0x1400153fd  call    _guard_dispatch_icall
0x140015402  mov     ecx, [rbx+8]
0x140015405  mov     ebp, eax
0x140015407  mov     rdx, [rbx+0F8h]
0x14001540e  mov     [rbx+68h], rcx
0x140015412  mov     ecx, 1F0h; unsigned __int64
0x140015417  mov     [rbx+28h], rdx
0x14001541b  mov     dword ptr [rbx+60h], 0
0x140015422  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140015427  test    rax, rax
0x14001542a  jz      short loc_140015461
0x14001542c  mov     rcx, rax; this
0x14001542f  call    ??0VMX_RAID5_RECOVER_TRANSFER_PACKET@@QEAA@XZ; VMX_RAID5_RECOVER_TRANSFER_PACKET::VMX_RAID5_RECOVER_TRANSFER_PACKET(void)
0x140015434  mov     rdi, rax
0x140015437  test    rax, rax
0x14001543a  jz      short loc_140015461
0x14001543c  mov     edx, ebp; Length
0x14001543e  mov     rcx, rax; this
0x140015441  call    ?AllocateMdls@VMX_RAID5_RECOVER_TRANSFER_PACKET@@QEAAJK@Z; VMX_RAID5_RECOVER_TRANSFER_PACKET::AllocateMdls(ulong)
0x140015446  test    eax, eax
0x140015448  jns     loc_1400154EF
0x14001544e  mov     rax, [rdi]
0x140015451  mov     edx, 1
0x140015456  mov     rcx, rdi
0x140015459  mov     rax, [rax]
0x14001545c  call    _guard_dispatch_icall
0x140015461  lea     rdi, [rsi+18h]
0x140015465  mov     rcx, rdi; SpinLock
0x140015468  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001546f  nop     dword ptr [rax+rax+00h]
0x140015474  cmp     byte ptr [rsi+10Bh], 0
0x14001547b  mov     dl, al; NewIrql
0x14001547d  jz      short loc_1400154D2
0x14001547f  mov     rcx, [rbx+28h]
0x140015483  lea     rax, ?VmxpRaid5RecoverReadStripeEmergencyCompletion@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverReadStripeEmergencyCompletion(VMX_TRANSFER_PACKET *)
0x14001548a  add     rsi, 148h
0x140015491  mov     [rbx+0F8h], rcx
0x140015498  mov     [rbx+28h], rax
0x14001549c  mov     rcx, [rsi+8]
0x1400154a0  cmp     [rcx], rsi
0x1400154a3  jz      short loc_1400154AC
0x1400154a5  mov     ecx, 3
0x1400154aa  int     29h; Win8: RtlFailFast(ecx)
0x1400154ac  lea     rax, [rbx+70h]
0x1400154b0  mov     [rax+8], rcx
0x1400154b4  mov     [rax], rsi
0x1400154b7  mov     [rcx], rax
0x1400154ba  mov     rcx, rdi; SpinLock
0x1400154bd  mov     [rsi+8], rax
0x1400154c1  call    cs:__imp_KeReleaseSpinLock
0x1400154c8  nop     dword ptr [rax+rax+00h]
0x1400154cd  jmp     loc_140015583
0x1400154d2  mov     rcx, rdi; SpinLock
0x1400154d5  mov     byte ptr [rsi+10Bh], 1
0x1400154dc  call    cs:__imp_KeReleaseSpinLock
0x1400154e3  nop     dword ptr [rax+rax+00h]
0x1400154e8  mov     rdi, [rsi+140h]
0x1400154ef  mov     rdx, [rdi+110h]; TargetMdl
0x1400154f6  mov     r9d, ebp; Length
0x1400154f9  mov     [rdi+18h], rdx
0x1400154fd  mov     rcx, [rbx+18h]; SourceMdl
0x140015501  mov     r8d, [rcx+2Ch]
0x140015505  add     r8, [rcx+20h]; VirtualAddress
0x140015509  call    cs:__imp_IoBuildPartialMdl
0x140015510  nop     dword ptr [rax+rax+00h]
0x140015515  mov     [rdi+8], ebp
0x140015518  mov     rdx, rdi
0x14001551b  mov     rax, [rbx+10h]
0x14001551f  mov     [rdi+10h], rax
0x140015523  lea     rax, ?VmxpRaid5RecoverReadStripePhase2@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5RecoverReadStripePhase2(VMX_TRANSFER_PACKET *)
0x14001552a  mov     [rdi+28h], rax
0x14001552e  mov     rcx, [rbx+30h]
0x140015532  mov     [rdi+30h], rcx
0x140015536  mov     rax, [rbx+38h]
0x14001553a  mov     [rdi+38h], rax
0x14001553e  mov     eax, [rbx+40h]
0x140015541  mov     [rdi+40h], eax
0x140015544  mov     rax, [rbx+48h]
0x140015548  mov     [rdi+48h], rax
0x14001554c  mov     al, [rbx+51h]
0x14001554f  mov     [rdi+51h], al
0x140015552  mov     byte ptr [rdi+52h], 1
0x140015556  mov     [rdi+0E0h], rbx
0x14001555d  mov     [rdi+0E8h], rsi
0x140015564  mov     eax, [rbx+0F0h]
0x14001556a  mov     [rdi+0F0h], eax
0x140015570  mov     dword ptr [rdi+0Ch], 2010003h
0x140015577  mov     rax, [rcx]
0x14001557a  mov     rax, [rax+8]
0x14001557e  call    _guard_dispatch_icall
0x140015583  add     rsp, 28h
0x140015587  pop     rdi
0x140015588  pop     rsi
0x140015589  pop     rbp
0x14001558a  pop     rbx
0x14001558b  retn
```
