# VMX_PARITY_IO_MANAGER::UpdateParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)

- ea: `0x1400087d0`
- end: `0x140008a81`
- name: `?UpdateParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z`
- size: `689`
- prototype: `void __fastcall(VMX_PARITY_IO_MANAGER *__hidden this, struct VMX_RAID5_PARITY_TRANSFER_PACKET *)`
- caller_count: `6`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007f70`
- `0x140008150`
- `0x140008300`
- `0x14000c6ec`
- `0x140018410`
- `0x140018840`

## callees

- `0x140002470`
- `0x1400087d0`
- `0x14000b420`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008827`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008827`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000890a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000891c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000896c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008994`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008a4f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000890a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000891c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000896c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008994`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008a4f`

## pseudocode

```c
void __fastcall VMX_PARITY_IO_MANAGER::UpdateParity(
        VMX_PARITY_IO_MANAGER *this,
        struct VMX_RAID5_PARITY_TRANSFER_PACKET *a2)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rdx
  __int64 v6; // rdi
  KSPIN_LOCK *v7; // r14
  KIRQL v8; // al
  __int64 v9; // rcx
  KIRQL v10; // r15
  __int64 v11; // rbx
  _BYTE *v12; // rax
  _BYTE *v13; // rbx
  KSPIN_LOCK *v14; // rbx
  KIRQL v15; // al
  char **v16; // r8
  char *v17; // rbp
  char v18; // bp
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rcx

  *((_QWORD *)a2 + 22) = this;
  *((_BYTE *)a2 + 82) = 0;
  *((_BYTE *)a2 + 136) = 0;
  v4 = *((_QWORD *)a2 + 2) / (unsigned __int64)*((unsigned int *)this + 1);
  *((_QWORD *)a2 + 23) = v4;
  v5 = v4 % *(unsigned int *)this;
  v6 = *((_QWORD *)this + 3) + 16LL * (unsigned int)v5;
  v7 = (KSPIN_LOCK *)(*((_QWORD *)this + 2) + 8LL * (unsigned int)v5);
  v8 = KeAcquireSpinLockRaiseToDpc(v7);
  v9 = *(_QWORD *)(v6 + 8);
  v10 = v8;
  if ( v9 == v6 )
  {
LABEL_4:
    v12 = VMX_TRANSFER_PACKET::operator new(0xC8u);
    v13 = v12;
    if ( v12 )
    {
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 3) = 0;
      v12[83] = 0;
      *((_WORD *)v12 + 66) = 0;
      *(_QWORD *)v12 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
      if ( (int)VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v12, *((_DWORD *)this + 1)) >= 0 )
        goto LABEL_15;
      (**(void (__fastcall ***)(_BYTE *, __int64))v13)(v13, 1);
    }
    v14 = (KSPIN_LOCK *)((char *)this + 64);
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 8);
    if ( *((_BYTE *)this + 40) )
    {
      v16 = (char **)*((_QWORD *)this + 7);
      v17 = (char *)this + 48;
      if ( *v16 == v17 )
      {
        *((_QWORD *)a2 + 18) = v17;
        *((_QWORD *)a2 + 19) = v16;
        *v16 = (char *)a2 + 144;
        *((_QWORD *)v17 + 1) = (char *)a2 + 144;
        KeReleaseSpinLock(v14, v15);
        KeReleaseSpinLock(v7, v10);
        return;
      }
LABEL_18:
      __fastfail(3u);
    }
    *((_BYTE *)this + 40) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)this + 8, v15);
    v13 = (_BYTE *)*((_QWORD *)this + 4);
LABEL_15:
    *((_DWORD *)v13 + 2) = *((_DWORD *)a2 + 2);
    *((_QWORD *)v13 + 2) = *((_QWORD *)a2 + 2);
    *((_QWORD *)v13 + 5) = VmxpRaid5UpdateParityCompletionRoutine;
    *((_QWORD *)v13 + 6) = *((_QWORD *)a2 + 6);
    *((_QWORD *)v13 + 7) = *((_QWORD *)a2 + 7);
    *((_DWORD *)v13 + 16) = *((_DWORD *)a2 + 16);
    *((_QWORD *)v13 + 9) = *((_QWORD *)a2 + 9);
    v13[81] = *((_BYTE *)a2 + 81);
    v13[82] = 1;
    *((_WORD *)v13 + 68) = 0;
    *((_QWORD *)v13 + 21) = v13 + 160;
    *((_QWORD *)v13 + 20) = v13 + 160;
    *((_QWORD *)v13 + 22) = this;
    *((_QWORD *)v13 + 23) = *((_QWORD *)a2 + 23);
    v20 = *(_QWORD **)(v6 + 8);
    if ( *v20 == v6 )
    {
      v21 = v13 + 144;
      *((_QWORD *)v13 + 18) = v6;
      *((_QWORD *)v13 + 19) = v20;
      *v20 = v13 + 144;
      *(_QWORD *)(v6 + 8) = v13 + 144;
      if ( *((_QWORD *)v13 + 18) == v6 )
      {
        *((_QWORD *)a2 + 19) = v21;
        *((_QWORD *)a2 + 18) = v6;
        *v21 = (char *)a2 + 144;
        *(_QWORD *)(v6 + 8) = (char *)a2 + 144;
        KeReleaseSpinLock(v7, v10);
        v22 = *((_QWORD *)v13 + 6);
        *((_DWORD *)v13 + 3) = 33685506;
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v22 + 8LL))(v22, v13);
        return;
      }
    }
    goto LABEL_18;
  }
  while ( 1 )
  {
    v11 = v9 - 144;
    if ( *(_QWORD *)(v9 - 144 + 184) == *((_QWORD *)a2 + 23) )
      break;
    v9 = *(_QWORD *)(v9 + 8);
    if ( v9 == v6 )
      goto LABEL_4;
  }
  v18 = *(_BYTE *)(v11 + 136);
  *(_BYTE *)(v11 + 136) = 0;
  v19 = *(_QWORD **)(v6 + 8);
  if ( *v19 != v6 )
    goto LABEL_18;
  *((_QWORD *)a2 + 19) = v19;
  *((_QWORD *)a2 + 18) = v6;
  *v19 = (char *)a2 + 144;
  *(_QWORD *)(v6 + 8) = (char *)a2 + 144;
  KeReleaseSpinLock(v7, v8);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(v11 + 40))(v11);
}

```

## disassembly

```asm
0x1400087d0  push    rbx
0x1400087d2  push    rbp
0x1400087d3  push    rsi
0x1400087d4  push    rdi
0x1400087d5  push    r14
0x1400087d7  push    r15
0x1400087d9  sub     rsp, 28h
0x1400087dd  mov     [rdx+0B0h], rcx
0x1400087e4  mov     rsi, rdx
0x1400087e7  mov     byte ptr [rdx+52h], 0
0x1400087eb  mov     rbp, rcx
0x1400087ee  mov     byte ptr [rdx+88h], 0
0x1400087f5  xor     edx, edx
0x1400087f7  mov     r8d, [rcx+4]
0x1400087fb  mov     rax, [rsi+10h]
0x1400087ff  div     r8
0x140008802  xor     edx, edx
0x140008804  mov     [rsi+0B8h], rax
0x14000880b  mov     ecx, [rcx]
0x14000880d  div     rcx
0x140008810  mov     rax, [rbp+10h]
0x140008814  mov     ecx, edx
0x140008816  mov     edi, edx
0x140008818  shl     rdi, 4
0x14000881c  add     rdi, [rbp+18h]
0x140008820  lea     r14, [rax+rcx*8]
0x140008824  mov     rcx, r14; SpinLock
0x140008827  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000882e  nop     dword ptr [rax+rax+00h]
0x140008833  mov     rcx, [rdi+8]
0x140008837  mov     r15b, al
0x14000883a  cmp     rcx, rdi
0x14000883d  jz      short loc_140008863
0x14000883f  mov     rdx, [rsi+0B8h]
0x140008846  lea     rbx, [rcx-90h]
0x14000884d  cmp     [rbx+0B8h], rdx
0x140008854  jz      loc_140008936
0x14000885a  mov     rcx, [rcx+8]
0x14000885e  cmp     rcx, rdi
0x140008861  jnz     short loc_140008846
0x140008863  mov     ecx, 0C8h; unsigned __int64
0x140008868  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x14000886d  mov     rbx, rax
0x140008870  test    rax, rax
0x140008873  jz      short loc_1400088C2
0x140008875  mov     qword ptr [rax+20h], 0
0x14000887d  mov     rcx, rbx; this
0x140008880  mov     qword ptr [rax+18h], 0
0x140008888  mov     byte ptr [rax+53h], 0
0x14000888c  mov     word ptr [rax+84h], 0
0x140008895  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x14000889c  mov     [rbx], rax
0x14000889f  mov     edx, [rbp+4]; unsigned int
0x1400088a2  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJK@Z; VMX_TRANSFER_PACKET::AllocateMdl(ulong)
0x1400088a7  test    eax, eax
0x1400088a9  jns     loc_1400089A4
0x1400088af  mov     rax, [rbx]
0x1400088b2  mov     edx, 1
0x1400088b7  mov     rcx, rbx
0x1400088ba  mov     rax, [rax]
0x1400088bd  call    _guard_dispatch_icall
0x1400088c2  lea     rbx, [rbp+40h]
0x1400088c6  mov     rcx, rbx; SpinLock
0x1400088c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400088d0  nop     dword ptr [rax+rax+00h]
0x1400088d5  cmp     byte ptr [rbp+28h], 0
0x1400088d9  jz      loc_14000898B
0x1400088df  mov     r8, [rbp+38h]
0x1400088e3  add     rbp, 30h ; '0'
0x1400088e7  cmp     [r8], rbp
0x1400088ea  jnz     loc_140008A7A
0x1400088f0  lea     rdx, [rsi+90h]
0x1400088f7  mov     rcx, rbx; SpinLock
0x1400088fa  mov     [rdx], rbp
0x1400088fd  mov     [rdx+8], r8
0x140008901  mov     [r8], rdx
0x140008904  mov     [rbp+8], rdx
0x140008908  mov     dl, al; NewIrql
0x14000890a  call    cs:__imp_KeReleaseSpinLock
0x140008911  nop     dword ptr [rax+rax+00h]
0x140008916  mov     dl, r15b; NewIrql
0x140008919  mov     rcx, r14; SpinLock
0x14000891c  call    cs:__imp_KeReleaseSpinLock
0x140008923  nop     dword ptr [rax+rax+00h]
0x140008928  add     rsp, 28h
0x14000892c  pop     r15
0x14000892e  pop     r14
0x140008930  pop     rdi
0x140008931  pop     rsi
0x140008932  pop     rbp
0x140008933  pop     rbx
0x140008934  retn
0x140008936  mov     bpl, [rbx+88h]
0x14000893d  mov     byte ptr [rbx+88h], 0
0x140008944  mov     rdx, [rdi+8]
0x140008948  cmp     [rdx], rdi
0x14000894b  jnz     loc_140008A7A
0x140008951  lea     rax, [rsi+90h]
0x140008958  mov     rcx, r14; SpinLock
0x14000895b  mov     [rax+8], rdx
0x14000895f  mov     [rax], rdi
0x140008962  mov     [rdx], rax
0x140008965  mov     dl, r15b; NewIrql
0x140008968  mov     [rdi+8], rax
0x14000896c  call    cs:__imp_KeReleaseSpinLock
0x140008973  nop     dword ptr [rax+rax+00h]
0x140008978  test    bpl, bpl
0x14000897b  jz      short loc_140008928
0x14000897d  mov     rax, [rbx+28h]
0x140008981  mov     rcx, rbx
0x140008984  call    _guard_dispatch_icall
0x140008989  jmp     short loc_140008928
0x14000898b  mov     dl, al; NewIrql
0x14000898d  mov     byte ptr [rbp+28h], 1
0x140008991  mov     rcx, rbx; SpinLock
0x140008994  call    cs:__imp_KeReleaseSpinLock
0x14000899b  nop     dword ptr [rax+rax+00h]
0x1400089a0  mov     rbx, [rbp+20h]
0x1400089a4  mov     eax, [rsi+8]
0x1400089a7  mov     [rbx+8], eax
0x1400089aa  mov     rax, [rsi+10h]
0x1400089ae  mov     [rbx+10h], rax
0x1400089b2  lea     rax, ?VmxpRaid5UpdateParityCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z; VmxpRaid5UpdateParityCompletionRoutine(VMX_TRANSFER_PACKET *)
0x1400089b9  mov     [rbx+28h], rax
0x1400089bd  mov     rax, [rsi+30h]
0x1400089c1  mov     [rbx+30h], rax
0x1400089c5  mov     rax, [rsi+38h]
0x1400089c9  mov     [rbx+38h], rax
0x1400089cd  mov     eax, [rsi+40h]
0x1400089d0  mov     [rbx+40h], eax
0x1400089d3  mov     rax, [rsi+48h]
0x1400089d7  mov     [rbx+48h], rax
0x1400089db  mov     al, [rsi+51h]
0x1400089de  mov     [rbx+51h], al
0x1400089e1  lea     rax, [rbx+0A0h]
0x1400089e8  mov     byte ptr [rbx+52h], 1
0x1400089ec  mov     word ptr [rbx+88h], 0
0x1400089f5  mov     [rax+8], rax
0x1400089f9  mov     [rax], rax
0x1400089fc  mov     [rbx+0B0h], rbp
0x140008a03  mov     rax, [rsi+0B8h]
0x140008a0a  mov     [rbx+0B8h], rax
0x140008a11  mov     rax, [rdi+8]
0x140008a15  cmp     [rax], rdi
0x140008a18  jnz     short loc_140008A7A
0x140008a1a  lea     rcx, [rbx+90h]
0x140008a21  mov     [rcx], rdi
0x140008a24  mov     [rcx+8], rax
0x140008a28  mov     [rax], rcx
0x140008a2b  mov     [rdi+8], rcx
0x140008a2f  cmp     [rcx], rdi
0x140008a32  jnz     short loc_140008A7A
0x140008a34  lea     rax, [rsi+90h]
0x140008a3b  mov     dl, r15b; NewIrql
0x140008a3e  mov     [rax+8], rcx
0x140008a42  mov     [rax], rdi
0x140008a45  mov     [rcx], rax
0x140008a48  mov     rcx, r14; SpinLock
0x140008a4b  mov     [rdi+8], rax
0x140008a4f  call    cs:__imp_KeReleaseSpinLock
0x140008a56  nop     dword ptr [rax+rax+00h]
0x140008a5b  mov     rcx, [rbx+30h]
0x140008a5f  mov     rdx, rbx
0x140008a62  mov     dword ptr [rbx+0Ch], 2020002h
0x140008a69  mov     rax, [rcx]
0x140008a6c  mov     rax, [rax+8]
0x140008a70  call    _guard_dispatch_icall
0x140008a75  jmp     loc_140008928
0x140008a7a  mov     ecx, 3
0x140008a7f  int     29h; Win8: RtlFailFast(ecx)
```
