# VmxpRaid5UpdateParityCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140017cd0`
- end: `0x140018330`
- name: `?VmxpRaid5UpdateParityCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `1632`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002470`
- `0x14000b420`
- `0x140010e0c`
- `0x140012560`
- `0x140017cd0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017dd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018060`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400180d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018219`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017dd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018060`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400180d4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018219`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017ec1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fe3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400180a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018288`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001829b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400182f9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017ec1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fe3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400180a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018288`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001829b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400182f9`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140017d11`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140017d11`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f03`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f49`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f03`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140017f49`

## pseudocode

```c
void __fastcall VmxpRaid5UpdateParityCompletionRoutine(struct VMX_TRANSFER_PACKET *a1)
{
  unsigned int *v1; // rbp
  NTSTATUS v3; // r15d
  _QWORD **v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rax
  char v9; // r13
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // rsi
  KSPIN_LOCK *v13; // r12
  KIRQL v14; // al
  char *v15; // r8
  KIRQL v16; // r10
  _QWORD *i; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  struct VMX_TRANSFER_PACKET **v20; // r9
  unsigned __int64 v21; // r9
  unsigned int v22; // r11d
  int v23; // ecx
  _QWORD **v24; // rsi
  __int64 v25; // rcx
  char *v26; // r15
  _QWORD *j; // rdi
  __int64 v28; // rcx
  unsigned int v29; // ebp
  PVOID v30; // rax
  __int64 v31; // rcx
  KIRQL v32; // dl
  __int64 v33; // rcx
  char **v34; // rax
  _QWORD *v35; // rcx
  _QWORD *v36; // rax
  _QWORD *v37; // rcx
  void (*v38)(void); // rax
  __int64 **v39; // r13
  KIRQL v40; // al
  __int64 *v41; // rdi
  __int64 *v42; // rcx
  __int64 v43; // rdx
  unsigned __int64 v44; // rdx
  __int64 v45; // rsi
  KSPIN_LOCK *v46; // r15
  KIRQL v47; // al
  __int64 **v48; // rdx
  __int64 **v49; // rcx
  __int64 **v50; // r15
  _BYTE *v51; // rax
  _BYTE *v52; // rbx
  _QWORD *v53; // rcx
  __int64 **v54; // rax
  KIRQL v55; // r10
  __int64 *v56; // rdx
  __int64 v57; // r8
  __int64 **v58; // rax
  __int64 **v59; // rax
  __int64 v60; // rcx
  char v61; // bl
  KIRQL NewIrql; // [rsp+60h] [rbp+8h]
  KSPIN_LOCK *SpinLock; // [rsp+68h] [rbp+10h]

  v1 = (unsigned int *)*((_QWORD *)a1 + 22);
  v3 = *((_DWORD *)a1 + 24);
  if ( *((_BYTE *)a1 + 82) )
  {
    v4 = (_QWORD **)((char *)a1 + 160);
  }
  else
  {
    if ( v3 < 0 && !*((_BYTE *)a1 + 137) && !FsRtlIsTotalDeviceFailure(v3) )
    {
      *((_BYTE *)a1 + 137) = 1;
      VMX_PARITY_IO_MANAGER::RecoverWriteParity((VMX_PARITY_IO_MANAGER *)v1, a1);
      return;
    }
    v4 = (_QWORD **)((char *)a1 + 160);
    while ( 1 )
    {
      v5 = *v4;
      if ( *v4 == v4 )
        break;
      if ( (_QWORD **)v5[1] != v4 )
        goto LABEL_79;
      v6 = (_QWORD *)*v5;
      if ( *(_QWORD **)(*v5 + 8LL) != v5 )
        goto LABEL_79;
      v7 = v5 - 20;
      *v4 = v6;
      v6[1] = v4;
      *((_DWORD *)v7 + 24) = v3;
      if ( v3 < 0 )
      {
        *((_BYTE *)v7 + 82) = 0;
        v8 = 0;
      }
      else
      {
        v8 = *((unsigned int *)v7 + 2);
      }
      v7[13] = v8;
      ((void (*)(void))v7[5])();
    }
  }
  v9 = *((_BYTE *)a1 + 82);
  v10 = *((_QWORD *)a1 + 23);
  *((_BYTE *)a1 + 82) = 0;
  v11 = v10 % *v1;
  v12 = *((_QWORD *)v1 + 3) + 16LL * (unsigned int)v11;
  v13 = (KSPIN_LOCK *)(*((_QWORD *)v1 + 2) + 8LL * (unsigned int)v11);
  v14 = KeAcquireSpinLockRaiseToDpc(v13);
  v15 = (char *)a1 + 144;
  v16 = v14;
  for ( i = (_QWORD *)*((_QWORD *)a1 + 18); i != (_QWORD *)v12; i = (_QWORD *)*i )
  {
    if ( i[5] == *((_QWORD *)a1 + 23) )
    {
      v18 = (_QWORD *)*i;
      if ( *(_QWORD **)(*i + 8LL) != i )
        goto LABEL_79;
      v19 = (_QWORD *)i[1];
      if ( (_QWORD *)*v19 != i )
        goto LABEL_79;
      *v19 = v18;
      v18[1] = v19;
      v20 = (struct VMX_TRANSFER_PACKET **)*((_QWORD *)a1 + 21);
      if ( *v20 != (struct VMX_TRANSFER_PACKET *)((char *)a1 + 160) )
        goto LABEL_79;
      i[2] = (char *)a1 + 160;
      i[3] = v20;
      *v20 = (struct VMX_TRANSFER_PACKET *)(i + 2);
      *((_QWORD *)a1 + 21) = i + 2;
      v21 = *((_QWORD *)a1 + 2);
      if ( *(i - 16) < v21 )
      {
        *((_DWORD *)a1 + 2) += v21 - *((_DWORD *)i - 32);
        v21 = *(i - 16);
        *((_QWORD *)a1 + 2) = v21;
        *((_BYTE *)a1 + 82) = 1;
      }
      v22 = *((_DWORD *)i - 34);
      if ( *(i - 16) + (unsigned __int64)v22 > v21 + *((unsigned int *)a1 + 2) )
      {
        v23 = *((_DWORD *)i - 32) - *((_DWORD *)a1 + 4);
        *((_BYTE *)a1 + 82) = 1;
        *((_DWORD *)a1 + 2) = v22 + v23;
      }
    }
  }
  if ( v3 >= 0 )
  {
    v24 = (_QWORD **)((char *)a1 + 160);
    if ( *v24 != v24 )
    {
      KeReleaseSpinLock(v13, v16);
      if ( !*((_BYTE *)a1 + 82) )
      {
        v25 = *((_QWORD *)a1 + 3);
        if ( (*(_BYTE *)(v25 + 10) & 5) != 0 )
          v26 = *(char **)(v25 + 24);
        else
          v26 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v25, 0, MmCached, 0, 0, 0x40000010u);
        for ( j = *v24; j != v24; j = (_QWORD *)*j )
        {
          v28 = *(j - 17);
          v29 = *((_DWORD *)j - 36) - *((_DWORD *)a1 + 4);
          if ( (*(_BYTE *)(v28 + 10) & 5) != 0 )
            v30 = *(PVOID *)(v28 + 24);
          else
            v30 = MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000010u);
          VmxpComputeParity(&v26[v29], v30, *((_DWORD *)j - 38));
        }
      }
      v31 = *((_QWORD *)a1 + 6);
      *((_DWORD *)a1 + 3) = 33685507;
      (*(void (__fastcall **)(__int64, struct VMX_TRANSFER_PACKET *))(*(_QWORD *)v31 + 8LL))(v31, a1);
      return;
    }
  }
  if ( v9 && *v4 == v4 )
  {
    *((_BYTE *)a1 + 82) = 1;
    v32 = v16;
    *((_BYTE *)a1 + 136) = 1;
LABEL_42:
    KeReleaseSpinLock(v13, v32);
    return;
  }
  v33 = *(_QWORD *)v15;
  if ( *(char **)(*(_QWORD *)v15 + 8LL) != v15 || (v34 = (char **)*((_QWORD *)a1 + 19), *v34 != v15) )
LABEL_79:
    __fastfail(3u);
  *v34 = (char *)v33;
  *(_QWORD *)(v33 + 8) = v34;
  KeReleaseSpinLock(v13, v16);
  while ( 1 )
  {
    v35 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v35[1] != v4 )
      goto LABEL_79;
    v36 = (_QWORD *)*v35;
    if ( *(_QWORD **)(*v35 + 8LL) != v35 )
      goto LABEL_79;
    *v4 = v36;
    v37 = v35 - 20;
    v36[1] = v4;
    v38 = (void (*)(void))v37[5];
    *((_DWORD *)v37 + 24) = v3;
    v37[13] = 0;
    *((_BYTE *)v37 + 82) = v9;
    v38();
  }
  if ( a1 != *((struct VMX_TRANSFER_PACKET **)v1 + 4) )
  {
    (**(void (__fastcall ***)(struct VMX_TRANSFER_PACKET *, __int64))a1)(a1, 1);
    return;
  }
  v13 = (KSPIN_LOCK *)(v1 + 16);
  v39 = (__int64 **)(v1 + 12);
  do
  {
LABEL_53:
    v40 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v1 + 8);
    v41 = *v39;
    if ( *v39 == (__int64 *)v39 )
    {
      *((_BYTE *)v1 + 40) = 0;
      v32 = v40;
      goto LABEL_42;
    }
    v42 = (__int64 *)(v1 + 12);
    if ( (unsigned int *)v41[1] != v1 + 12 )
      goto LABEL_79;
    v43 = *v41;
    if ( *(__int64 **)(*v41 + 8) != v41 )
      goto LABEL_79;
    *v42 = v43;
    *(_QWORD *)(v43 + 8) = v42;
    KeReleaseSpinLock((PKSPIN_LOCK)v1 + 8, v40);
    v44 = v41[5] % (unsigned __int64)*v1;
    v45 = *((_QWORD *)v1 + 3) + 16LL * (unsigned int)v44;
    v46 = (KSPIN_LOCK *)(*((_QWORD *)v1 + 2) + 8LL * (unsigned int)v44);
    SpinLock = v46;
    v47 = KeAcquireSpinLockRaiseToDpc(v46);
    v48 = *(__int64 ***)(v45 + 8);
    NewIrql = v47;
    v49 = v48;
    if ( v48 == (__int64 **)v45 )
      goto LABEL_60;
    do
    {
      v50 = v49 - 18;
      if ( v49[5] == (__int64 *)v41[5] )
      {
        if ( *v48 != (__int64 *)v45 )
          goto LABEL_79;
        v41[1] = (__int64)v48;
        *v41 = v45;
        *v48 = v41;
        *(_QWORD *)(v45 + 8) = v41;
        v61 = *((_BYTE *)v50 + 136);
        *((_BYTE *)v50 + 136) = 0;
        KeReleaseSpinLock(SpinLock, v47);
        if ( v61 )
          ((void (__fastcall *)(__int64 **))v50[5])(v50);
        goto LABEL_53;
      }
      v49 = (__int64 **)v49[1];
    }
    while ( v49 != (__int64 **)v45 );
    v46 = SpinLock;
LABEL_60:
    v51 = VMX_TRANSFER_PACKET::operator new(0xC8u);
    v52 = v51;
    if ( v51 )
    {
      *((_QWORD *)v51 + 4) = 0;
      *((_QWORD *)v51 + 3) = 0;
      v51[83] = 0;
      *((_WORD *)v51 + 66) = 0;
      *(_QWORD *)v51 = &VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable';
      if ( (int)VMX_TRANSFER_PACKET::AllocateMdl((VMX_TRANSFER_PACKET *)v51, v1[1]) < 0 )
      {
        (**(void (__fastcall ***)(_BYTE *, __int64))v52)(v52, 1);
        goto LABEL_63;
      }
    }
    else
    {
LABEL_63:
      v52 = (_BYTE *)*((_QWORD *)v1 + 4);
    }
    *((_DWORD *)v52 + 2) = v1[1];
    *((_QWORD *)v52 + 2) = v41[5] * v1[1];
    *((_QWORD *)v52 + 5) = VmxpRaid5UpdateParityCompletionRoutine;
    *((_QWORD *)v52 + 6) = *(v41 - 12);
    *((_QWORD *)v52 + 7) = *(v41 - 11);
    *((_DWORD *)v52 + 16) = *((_DWORD *)v41 - 20);
    *((_QWORD *)v52 + 9) = *(v41 - 9);
    v52[81] = *((_BYTE *)v41 - 63);
    v52[82] = 1;
    *((_WORD *)v52 + 68) = 0;
    *((_QWORD *)v52 + 21) = v52 + 160;
    *((_QWORD *)v52 + 20) = v52 + 160;
    *((_QWORD *)v52 + 22) = v1;
    *((_QWORD *)v52 + 23) = v41[5];
    v53 = *(_QWORD **)(v45 + 8);
    if ( *v53 != v45 )
      goto LABEL_79;
    v54 = (__int64 **)(v52 + 144);
    *((_QWORD *)v52 + 18) = v45;
    *((_QWORD *)v52 + 19) = v53;
    *v53 = v52 + 144;
    *(_QWORD *)(v45 + 8) = v52 + 144;
    if ( *((_QWORD *)v52 + 18) != v45 )
      goto LABEL_79;
    *v41 = v45;
    v41[1] = (__int64)v54;
    *v54 = v41;
    *(_QWORD *)(v45 + 8) = v41;
    v55 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v1 + 8);
    v56 = (__int64 *)*((_QWORD *)v1 + 6);
    if ( v56 != (__int64 *)(v1 + 12) )
    {
      do
      {
        v57 = *v56;
        if ( v56[5] == v41[5] )
        {
          if ( *(__int64 **)(v57 + 8) != v56 )
            goto LABEL_79;
          v58 = (__int64 **)v56[1];
          if ( *v58 != v56 )
            goto LABEL_79;
          *v58 = (__int64 *)v57;
          *(_QWORD *)(v57 + 8) = v58;
          v59 = *(__int64 ***)(v45 + 8);
          if ( *v59 != (__int64 *)v45 )
            goto LABEL_79;
          *v56 = v45;
          v56[1] = (__int64)v59;
          *v59 = v56;
          *(_QWORD *)(v45 + 8) = v56;
        }
        v56 = (__int64 *)v57;
      }
      while ( (unsigned int *)v57 != v1 + 12 );
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v1 + 8, v55);
    KeReleaseSpinLock(v46, NewIrql);
    v60 = *((_QWORD *)v52 + 6);
    *((_DWORD *)v52 + 3) = 33685506;
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v60 + 8LL))(v60, v52);
  }
  while ( v52 != *((_BYTE **)v1 + 4) );
}

```

## disassembly

```asm
0x140017cd0  mov     [rsp+arg_10], rbx
0x140017cd5  mov     [rsp+arg_18], rbp
0x140017cda  push    rsi
0x140017cdb  push    rdi
0x140017cdc  push    r12
0x140017cde  push    r13
0x140017ce0  push    r15
0x140017ce2  sub     rsp, 30h
0x140017ce6  mov     rbp, [rcx+0B0h]
0x140017ced  xor     esi, esi
0x140017cef  mov     rbx, rcx
0x140017cf2  mov     r15d, [rcx+60h]
0x140017cf6  cmp     [rcx+52h], sil
0x140017cfa  jnz     loc_140017DA3
0x140017d00  test    r15d, r15d
0x140017d03  jns     short loc_140017D4B
0x140017d05  cmp     [rcx+89h], sil
0x140017d0c  jnz     short loc_140017D4B
0x140017d0e  mov     ecx, r15d; Status
0x140017d11  call    cs:__imp_FsRtlIsTotalDeviceFailure
0x140017d18  nop     dword ptr [rax+rax+00h]
0x140017d1d  test    al, al
0x140017d1f  jnz     short loc_140017D4B
0x140017d21  mov     rdx, rbx; struct VMX_RAID5_PARITY_TRANSFER_PACKET *
0x140017d24  mov     byte ptr [rbx+89h], 1
0x140017d2b  mov     rcx, rbp; this
0x140017d2e  call    ?RecoverWriteParity@VMX_PARITY_IO_MANAGER@@QEAAXPEAVVMX_RAID5_PARITY_TRANSFER_PACKET@@@Z; VMX_PARITY_IO_MANAGER::RecoverWriteParity(VMX_RAID5_PARITY_TRANSFER_PACKET *)
0x140017d33  mov     rbx, [rsp+58h+arg_10]
0x140017d38  mov     rbp, [rsp+58h+arg_18]
0x140017d3d  add     rsp, 30h
0x140017d41  pop     r15
0x140017d43  pop     r13
0x140017d45  pop     r12
0x140017d47  pop     rdi
0x140017d48  pop     rsi
0x140017d49  retn
0x140017d4b  lea     rdi, [rbx+0A0h]
0x140017d52  mov     rcx, [rdi]
0x140017d55  cmp     rcx, rdi
0x140017d58  jz      short loc_140017DAA
0x140017d5a  cmp     [rcx+8], rdi
0x140017d5e  jnz     loc_140018329
0x140017d64  mov     rax, [rcx]
0x140017d67  cmp     [rax+8], rcx
0x140017d6b  jnz     loc_140018329
0x140017d71  add     rcx, 0FFFFFFFFFFFFFF60h
0x140017d78  mov     [rdi], rax
0x140017d7b  mov     [rax+8], rdi
0x140017d7f  mov     [rcx+60h], r15d
0x140017d83  test    r15d, r15d
0x140017d86  js      short loc_140017D8D
0x140017d88  mov     eax, [rcx+8]
0x140017d8b  jmp     short loc_140017D94
0x140017d8d  mov     [rcx+52h], sil
0x140017d91  mov     rax, rsi
0x140017d94  mov     [rcx+68h], rax
0x140017d98  mov     rax, [rcx+28h]
0x140017d9c  call    _guard_dispatch_icall
0x140017da1  jmp     short loc_140017D52
0x140017da3  lea     rdi, [rcx+0A0h]
0x140017daa  mov     r13b, [rbx+52h]
0x140017dae  xor     edx, edx
0x140017db0  mov     rax, [rbx+0B8h]
0x140017db7  mov     [rbx+52h], sil
0x140017dbb  mov     ecx, [rbp+0]
0x140017dbe  div     rcx
0x140017dc1  mov     rax, [rbp+10h]
0x140017dc5  mov     ecx, edx
0x140017dc7  mov     esi, edx
0x140017dc9  shl     rsi, 4
0x140017dcd  add     rsi, [rbp+18h]
0x140017dd1  lea     r12, [rax+rcx*8]
0x140017dd5  mov     rcx, r12; SpinLock
0x140017dd8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017ddf  nop     dword ptr [rax+rax+00h]
0x140017de4  lea     r8, [rbx+90h]
0x140017deb  mov     r10b, al
0x140017dee  mov     rdx, [r8]
0x140017df1  jmp     loc_140017E99
0x140017df6  mov     rax, [rbx+0B8h]
0x140017dfd  cmp     [rdx+28h], rax
0x140017e01  jnz     loc_140017E96
0x140017e07  mov     rcx, [rdx]
0x140017e0a  cmp     [rcx+8], rdx
0x140017e0e  jnz     loc_140018329
0x140017e14  mov     rax, [rdx+8]
0x140017e18  cmp     [rax], rdx
0x140017e1b  jnz     loc_140018329
0x140017e21  mov     [rax], rcx
0x140017e24  mov     [rcx+8], rax
0x140017e28  lea     rcx, [rbx+0A0h]
0x140017e2f  mov     r9, [rcx+8]
0x140017e33  cmp     [r9], rcx
0x140017e36  jnz     loc_140018329
0x140017e3c  lea     rax, [rdx+10h]
0x140017e40  mov     [rax], rcx
0x140017e43  mov     [rax+8], r9
0x140017e47  mov     [r9], rax
0x140017e4a  mov     [rcx+8], rax
0x140017e4e  mov     r9, [rbx+10h]
0x140017e52  cmp     [rdx-80h], r9
0x140017e56  jnb     short loc_140017E6D
0x140017e58  mov     ecx, r9d
0x140017e5b  sub     ecx, [rdx-80h]
0x140017e5e  add     [rbx+8], ecx
0x140017e61  mov     r9, [rdx-80h]
0x140017e65  mov     [rbx+10h], r9
0x140017e69  mov     byte ptr [rbx+52h], 1
0x140017e6d  mov     r11d, [rdx-88h]
0x140017e74  mov     eax, [rbx+8]
0x140017e77  mov     ecx, r11d
0x140017e7a  add     rcx, [rdx-80h]
0x140017e7e  add     rax, r9
0x140017e81  cmp     rcx, rax
0x140017e84  jbe     short loc_140017E96
0x140017e86  mov     ecx, [rdx-80h]
0x140017e89  sub     ecx, [rbx+10h]
0x140017e8c  add     ecx, r11d
0x140017e8f  mov     byte ptr [rbx+52h], 1
0x140017e93  mov     [rbx+8], ecx
0x140017e96  mov     rdx, [rdx]
0x140017e99  cmp     rdx, rsi
0x140017e9c  jnz     loc_140017DF6
0x140017ea2  test    r15d, r15d
0x140017ea5  js      loc_140017F90
0x140017eab  lea     rsi, [rbx+0A0h]
0x140017eb2  cmp     [rsi], rsi
0x140017eb5  jz      loc_140017F90
0x140017ebb  mov     dl, r10b; NewIrql
0x140017ebe  mov     rcx, r12; SpinLock
0x140017ec1  call    cs:__imp_KeReleaseSpinLock
0x140017ec8  nop     dword ptr [rax+rax+00h]
0x140017ecd  cmp     byte ptr [rbx+52h], 0
0x140017ed1  jnz     loc_140017F71
0x140017ed7  mov     rcx, [rbx+18h]; MemoryDescriptorList
0x140017edb  mov     r12d, 40000010h
0x140017ee1  test    byte ptr [rcx+0Ah], 5
0x140017ee5  jz      short loc_140017EED
0x140017ee7  mov     r15, [rcx+18h]
0x140017eeb  jmp     short loc_140017F12
0x140017eed  xor     r9d, r9d; RequestedAddress
0x140017ef0  mov     [rsp+58h+Priority], r12d; Priority
0x140017ef5  xor     edx, edx; AccessMode
0x140017ef7  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140017eff  lea     r8d, [r9+1]; CacheType
0x140017f03  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140017f0a  nop     dword ptr [rax+rax+00h]
0x140017f0f  mov     r15, rax
0x140017f12  mov     rdi, [rsi]
0x140017f15  jmp     short loc_140017F6C
0x140017f17  mov     rcx, [rdi-88h]; MemoryDescriptorList
0x140017f1e  mov     ebp, [rdi-90h]
0x140017f24  sub     ebp, [rbx+10h]
0x140017f27  test    byte ptr [rcx+0Ah], 5
0x140017f2b  jz      short loc_140017F33
0x140017f2d  mov     rax, [rcx+18h]
0x140017f31  jmp     short loc_140017F55
0x140017f33  xor     r9d, r9d; RequestedAddress
0x140017f36  mov     [rsp+58h+Priority], r12d; Priority
0x140017f3b  xor     edx, edx; AccessMode
0x140017f3d  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140017f45  lea     r8d, [r9+1]; CacheType
0x140017f49  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140017f50  nop     dword ptr [rax+rax+00h]
0x140017f55  mov     r8d, [rdi-98h]; unsigned int
0x140017f5c  mov     rdx, rax; void *
0x140017f5f  mov     ecx, ebp
0x140017f61  add     rcx, r15; void *
0x140017f64  call    ?VmxpComputeParity@@YAXPEAX0K@Z; VmxpComputeParity(void *,void *,ulong)
0x140017f69  mov     rdi, [rdi]
0x140017f6c  cmp     rdi, rsi
0x140017f6f  jnz     short loc_140017F17
0x140017f71  mov     rcx, [rbx+30h]
0x140017f75  mov     rdx, rbx
0x140017f78  mov     dword ptr [rbx+0Ch], 2020003h
0x140017f7f  mov     rax, [rcx]
0x140017f82  mov     rax, [rax+8]
0x140017f86  call    _guard_dispatch_icall
0x140017f8b  jmp     loc_140017D33
0x140017f90  test    r13b, r13b
0x140017f93  jz      short loc_140017FBC
0x140017f95  cmp     [rdi], rdi
0x140017f98  jnz     short loc_140017FBC
0x140017f9a  mov     byte ptr [rbx+52h], 1
0x140017f9e  mov     dl, r10b; NewIrql
0x140017fa1  mov     byte ptr [rbx+88h], 1
0x140017fa8  mov     rcx, r12; SpinLock
0x140017fab  call    cs:__imp_KeReleaseSpinLock
0x140017fb2  nop     dword ptr [rax+rax+00h]
0x140017fb7  jmp     loc_140017D33
0x140017fbc  mov     rcx, [r8]
0x140017fbf  cmp     [rcx+8], r8
0x140017fc3  jnz     loc_140018329
0x140017fc9  mov     rax, [r8+8]
0x140017fcd  cmp     [rax], r8
0x140017fd0  jnz     loc_140018329
0x140017fd6  mov     [rax], rcx
0x140017fd9  mov     dl, r10b; NewIrql
0x140017fdc  mov     [rcx+8], rax
0x140017fe0  mov     rcx, r12; SpinLock
0x140017fe3  call    cs:__imp_KeReleaseSpinLock
0x140017fea  nop     dword ptr [rax+rax+00h]
0x140017fef  mov     rcx, [rdi]
0x140017ff2  cmp     rcx, rdi
0x140017ff5  jz      short loc_140018037
0x140017ff7  cmp     [rcx+8], rdi
0x140017ffb  jnz     loc_140018329
0x140018001  mov     rax, [rcx]
0x140018004  cmp     [rax+8], rcx
0x140018008  jnz     loc_140018329
0x14001800e  mov     [rdi], rax
0x140018011  add     rcx, 0FFFFFFFFFFFFFF60h
0x140018018  mov     [rax+8], rdi
0x14001801c  mov     rax, [rcx+28h]
0x140018020  mov     [rcx+60h], r15d
0x140018024  mov     qword ptr [rcx+68h], 0
0x14001802c  mov     [rcx+52h], r13b
0x140018030  call    _guard_dispatch_icall
0x140018035  jmp     short loc_140017FEF
0x140018037  cmp     rbx, [rbp+20h]
0x14001803b  jz      short loc_140018055
0x14001803d  mov     rax, [rbx]
0x140018040  mov     edx, 1
0x140018045  mov     rcx, rbx
0x140018048  mov     rax, [rax]
0x14001804b  call    _guard_dispatch_icall
0x140018050  jmp     loc_140017D33
0x140018055  lea     r12, [rbp+40h]
0x140018059  lea     r13, [rbp+30h]
0x14001805d  mov     rcx, r12; SpinLock
0x140018060  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018067  nop     dword ptr [rax+rax+00h]
0x14001806c  mov     rdi, [r13+0]
0x140018070  cmp     rdi, r13
0x140018073  jz      loc_14001831E
0x140018079  lea     rcx, [rbp+30h]
0x14001807d  cmp     [rdi+8], rcx
0x140018081  jnz     loc_140018329
0x140018087  mov     rdx, [rdi]
0x14001808a  cmp     [rdx+8], rdi
0x14001808e  jnz     loc_140018329
0x140018094  mov     [rcx], rdx
0x140018097  mov     [rdx+8], rcx
0x14001809b  mov     dl, al; NewIrql
0x14001809d  mov     rcx, r12; SpinLock
0x1400180a0  call    cs:__imp_KeReleaseSpinLock
0x1400180a7  nop     dword ptr [rax+rax+00h]
0x1400180ac  mov     ecx, [rbp+0]
0x1400180af  xor     edx, edx
0x1400180b1  mov     rax, [rdi+28h]
0x1400180b5  div     rcx
0x1400180b8  mov     rax, [rbp+10h]
0x1400180bc  mov     ecx, edx
0x1400180be  mov     esi, edx
0x1400180c0  shl     rsi, 4
0x1400180c4  add     rsi, [rbp+18h]
0x1400180c8  lea     r15, [rax+rcx*8]
0x1400180cc  mov     rcx, r15; SpinLock
0x1400180cf  mov     [rsp+58h+SpinLock], r15
0x1400180d4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400180db  nop     dword ptr [rax+rax+00h]
0x1400180e0  mov     rdx, [rsi+8]
0x1400180e4  mov     [rsp+58h+NewIrql], al
0x1400180e8  mov     rcx, rdx
0x1400180eb  cmp     rdx, rsi
0x1400180ee  jz      short loc_140018116
0x1400180f0  mov     r8, [rdi+28h]
0x1400180f4  lea     r15, [rcx-90h]
0x1400180fb  cmp     [r15+0B8h], r8
0x140018102  jz      loc_1400182D0
0x140018108  mov     rcx, [rcx+8]
0x14001810c  cmp     rcx, rsi
0x14001810f  jnz     short loc_1400180F4
0x140018111  mov     r15, [rsp+58h+SpinLock]
0x140018116  mov     ecx, 0C8h; unsigned __int64
0x14001811b  call    ??2VMX_TRANSFER_PACKET@@SAPEAX_K@Z; VMX_TRANSFER_PACKET::operator new(unsigned __int64)
0x140018120  xor     ecx, ecx
0x140018122  mov     rbx, rax
0x140018125  test    rax, rax
0x140018128  jz      short loc_140018168
0x14001812a  mov     [rax+20h], rcx
0x14001812e  mov     [rax+18h], rcx
0x140018132  mov     [rax+53h], cl
0x140018135  mov     [rax+84h], cx
0x14001813c  lea     rax, ??_7VMX_RAID5_PARITY_TRANSFER_PACKET@@6B@; const VMX_RAID5_PARITY_TRANSFER_PACKET::`vftable'
0x140018143  mov     [rbx], rax
0x140018146  mov     rcx, rbx; this
0x140018149  mov     edx, [rbp+4]; unsigned int
0x14001814c  call    ?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJK@Z; VMX_TRANSFER_PACKET::AllocateMdl(ulong)
0x140018151  test    eax, eax
0x140018153  jns     short loc_14001816C
0x140018155  mov     rax, [rbx]
0x140018158  mov     edx, 1
0x14001815d  mov     rcx, rbx
0x140018160  mov     rax, [rax]
0x140018163  call    _guard_dispatch_icall
0x140018168  mov     rbx, [rbp+20h]
0x14001816c  mov     eax, [rbp+4]
0x14001816f  mov     [rbx+8], eax
0x140018172  mov     eax, [rbp+4]
  ... truncated ...
```
