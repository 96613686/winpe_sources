# SIO_RAID::OnPacketCompletion(SC_PACKET *)

- ea: `0x140012280`
- end: `0x1400125fa`
- name: `?OnPacketCompletion@SIO_RAID@@UEAAJPEAVSC_PACKET@@@Z`
- size: `890`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011dc0`
- `0x140011e70`
- `0x140012bf0`
- `0x140012c60`

## callees

- `0x1400061a0`
- `0x140012280`
- `0x140012600`
- `0x140012880`
- `0x1400129d0`
- `0x14004bc80`
- `0x14004be48`
- `0x14004c8e0`
- `0x14004cd18`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012544`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012544`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012521`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012521`

## pseudocode

```c
int __fastcall SIO_RAID::OnPacketCompletion(volatile LONG *this, struct SC_PACKET *a2)
{
  int v2; // esi
  int v4; // eax
  char v7; // al
  int v8; // esi
  __int64 v9; // rbp
  char v10; // cl
  __int64 v11; // rax
  __int64 v12; // rax
  _WORD *v13; // r14
  KIRQL v14; // al

  v2 = *((_DWORD *)a2 + 45);
  v4 = *((unsigned __int8 *)a2 + 169);
  if ( v4 == 16 )
    return v2;
  if ( v4 != 9 )
  {
    switch ( *((_BYTE *)a2 + 169) )
    {
      case 7:
        return SIO_RAID::OnPacketCompletionRead((SIO_RAID *)this, a2);
      case 8:
        return SIO_RAID::OnPacketCompletionReadUnit(this, a2);
      case 0xA:
        v8 = *((_DWORD *)a2 + 45);
        v9 = *((_QWORD *)a2 + 2);
        if ( v8 == -1058602981 || v8 == -2147483626 )
          goto LABEL_38;
        v10 = *(_BYTE *)(*((_QWORD *)a2 + 1) + 169LL);
        if ( v10 == 13 || v10 == 15 )
          _InterlockedAdd64(
            (volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)this + 1) + 176LL) + 520LL),
            *((unsigned int *)a2 + 36));
        v11 = *((_QWORD *)this + 4);
        if ( v11 )
          v12 = v11 + 88;
        else
          v12 = *((_QWORD *)this + 1) + 80LL;
        v13 = (_WORD *)(*((_QWORD *)this + 6)
                      + 32LL * (unsigned int)(*((_DWORD *)a2 + 37) + *((_DWORD *)a2 + 38) * *(_DWORD *)(v12 + 16)));
        if ( v8 < 0 )
        {
          if ( *((_BYTE *)a2 + 170) == 6 )
            return v8;
          if ( (*v13 & 0x40) != 0 )
            SIO_RAID::SetStripeState(
              (SIO_RAID *)this,
              *((_DWORD *)a2 + 37),
              *((_DWORD *)a2 + 38),
              *((_QWORD *)a2 + 17),
              *((unsigned int *)a2 + 36),
              1u);
          v8 = SIO_RAID::TransitionColumnState((SIO_RAID *)this, *((_DWORD *)a2 + 37), *((_DWORD *)a2 + 38), 0, v8);
LABEL_38:
          if ( v8 < 0 )
            return v8;
        }
        else if ( (*v13 & 1) != 0 )
        {
          v14 = ExAcquireSpinLockExclusive(this + 6);
          *v13 &= ~1u;
          ExReleaseSpinLockExclusive(this + 6, v14);
        }
        if ( (*((_DWORD *)a2 + 19) & 2) != 0 )
          *(_QWORD *)(v9 + 192) = (unsigned int)(*((_DWORD *)a2 + 38) + 1);
        return v8;
      case 0xB:
        v2 = *((_DWORD *)a2 + 45);
        if ( v2 != -1058602981 && v2 != -2147483626 && v2 < 0 )
          return SIO_RAID::TransitionColumnState(
                   (SIO_RAID *)this,
                   *((_DWORD *)a2 + 37),
                   *((_DWORD *)a2 + 38),
                   0,
                   *((_DWORD *)a2 + 45));
        return v2;
      case 0x11:
        v2 = *((_DWORD *)a2 + 45);
        if ( *((_BYTE *)a2 + 170) == 1 )
        {
          SIO_RAID::ReleaseRegion((SIO_RAID *)this, a2);
        }
        else if ( *((_BYTE *)a2 + 170) == 4 )
        {
          *((_BYTE *)a2 + 170) = 1;
          return -1073741267;
        }
        return v2;
      case 0x13:
        v2 = *((_DWORD *)a2 + 45);
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 128LL) + 24LL) + 4LL) == -2147483631 )
          return SIO_RAID::OnPacketCompletionDsmAddresses((SIO_RAID *)this, a2);
        return v2;
      default:
        return v2;
    }
  }
  v2 = *((_DWORD *)a2 + 45);
  v7 = *((_BYTE *)a2 + 170);
  if ( v7 == 1 )
  {
    v2 = *((_DWORD *)a2 + 45);
    if ( (*((_DWORD *)a2 + 19) & 0x10000000) == 0 )
      SIO_RAID::ReleaseRegion((SIO_RAID *)this, a2);
    if ( v2 < 0 )
      return v2;
    *((_DWORD *)a2 + 36) = *((_DWORD *)a2 + 67);
    if ( *((_QWORD *)this + 8) )
      SIO_LOG::UpdateCountersIoComplete(*(SIO_LOG **)(*((_QWORD *)this + 1) + 376LL), a2);
    goto LABEL_10;
  }
  if ( v7 != 4 )
  {
    if ( v7 == 8 )
      v2 = SIO_RAID::OnPacketCompletionWriteLog((SIO_RAID *)this, a2);
LABEL_10:
    if ( v2 >= 0 && (*((_DWORD *)a2 + 19) & 2) != 0 )
      *(_QWORD *)(*((_QWORD *)a2 + 2) + 192LL) += *((unsigned int *)a2 + 36);
    return v2;
  }
  *((_BYTE *)a2 + 170) = 1;
  return -1073741267;
}

```

## disassembly

```asm
0x140012280  mov     [rsp+arg_10], rbx
0x140012285  mov     [rsp+arg_18], rsi
0x14001228a  push    rdi
0x14001228b  sub     rsp, 30h
0x14001228f  mov     esi, [rdx+0B4h]
0x140012295  mov     rbx, rdx
0x140012298  movzx   eax, byte ptr [rdx+0A9h]
0x14001229f  mov     rdi, rcx
0x1400122a2  cmp     eax, 10h
0x1400122a5  jnz     short loc_1400122BA
0x1400122a7  mov     eax, esi; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x1400122a9  mov     rbx, [rsp+38h+arg_10]
0x1400122ae  mov     rsi, [rsp+38h+arg_18]
0x1400122b3  add     rsp, 30h
0x1400122b7  pop     rdi
0x1400122b8  retn
0x1400122ba  cmp     eax, 9
0x1400122bd  jnz     short loc_140012321
0x1400122bf  mov     esi, [rdx+0B4h]
0x1400122c5  movzx   eax, byte ptr [rdx+0AAh]
0x1400122cc  cmp     al, 1
0x1400122ce  jnz     loc_1400123FB
0x1400122d4  mov     esi, [rdx+0B4h]
0x1400122da  test    dword ptr [rdx+4Ch], 10000000h
0x1400122e1  jnz     short loc_1400122E8
0x1400122e3  call    ?ReleaseRegion@SIO_RAID@@QEAAXPEAVSC_PACKET@@@Z; SIO_RAID::ReleaseRegion(SC_PACKET *)
0x1400122e8  test    esi, esi
0x1400122ea  js      short def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x1400122ec  mov     eax, [rbx+10Ch]
0x1400122f2  mov     [rbx+90h], eax
0x1400122f8  cmp     qword ptr [rdi+40h], 0
0x1400122fd  jnz     loc_1400125E2
0x140012303  test    esi, esi
0x140012305  js      short def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x140012307  mov     eax, [rbx+4Ch]
0x14001230a  test    al, 2
0x14001230c  jz      short def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x14001230e  mov     rcx, [rbx+10h]
0x140012312  mov     eax, [rbx+90h]
0x140012318  add     [rcx+0C0h], rax
0x14001231f  jmp     short def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x140012321  add     eax, 0FFFFFFF9h; switch 14 cases
0x140012324  cmp     eax, 0Dh
0x140012327  ja      def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x14001232d  lea     rdx, cs:140000000h; struct SC_PACKET *
0x140012334  cdqe
0x140012336  mov     ecx, ds:(jpt_140012340 - 140000000h)[rdx+rax*4]
0x14001233d  add     rcx, rdx
0x140012340  jmp     rcx; switch jump
0x140012346  mov     esi, [rbx+0B4h]; jumptable 0000000140012340 case 10
0x14001234c  mov     [rsp+38h+arg_0], rbp
0x140012351  mov     rbp, [rbx+10h]
0x140012355  mov     [rsp+38h+arg_8], r14
0x14001235a  cmp     esi, 0C0E7001Bh
0x140012360  jz      loc_1400124F2
0x140012366  cmp     esi, 80000016h
0x14001236c  jz      loc_1400124F2
0x140012372  mov     rax, [rbx+8]
0x140012376  movzx   ecx, byte ptr [rax+0A9h]; this
0x14001237d  cmp     cl, 0Dh
0x140012380  jz      loc_1400124FF
0x140012386  cmp     cl, 0Fh
0x140012389  jz      loc_1400124FF
0x14001238f  mov     rax, [rdi+20h]
0x140012393  test    rax, rax
0x140012396  jnz     loc_14001249E
0x14001239c  mov     rax, [rdi+8]
0x1400123a0  add     rax, 50h ; 'P'
0x1400123a4  mov     r14d, [rax+10h]
0x1400123a8  imul    r14d, [rbx+98h]
0x1400123b0  add     r14d, [rbx+94h]
0x1400123b7  shl     r14, 5
0x1400123bb  add     r14, [rdi+30h]
0x1400123bf  test    esi, esi
0x1400123c1  js      loc_1400124A7
0x1400123c7  movzx   eax, word ptr [r14]
0x1400123cb  test    al, 1
0x1400123cd  jnz     loc_14001251D
0x1400123d3  mov     eax, [rbx+4Ch]
0x1400123d6  test    al, 2
0x1400123d8  jnz     loc_140012555
0x1400123de  mov     r14, [rsp+38h+arg_8]
0x1400123e3  mov     eax, esi
0x1400123e5  mov     rbp, [rsp+38h+arg_0]
0x1400123ea  mov     rbx, [rsp+38h+arg_10]
0x1400123ef  mov     rsi, [rsp+38h+arg_18]
0x1400123f4  add     rsp, 30h
0x1400123f8  pop     rdi
0x1400123f9  retn
0x1400123fb  cmp     al, 4
0x1400123fd  jz      short loc_140012413
0x1400123ff  cmp     al, 8
0x140012401  jnz     loc_140012303
0x140012407  call    ?OnPacketCompletionWriteLog@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionWriteLog(SC_PACKET *)
0x14001240c  mov     esi, eax
0x14001240e  jmp     loc_140012303
0x140012413  mov     esi, 0C000022Dh
0x140012418  mov     byte ptr [rdx+0AAh], 1
0x14001241f  mov     eax, esi
0x140012421  mov     rbx, [rsp+38h+arg_10]
0x140012426  mov     rsi, [rsp+38h+arg_18]
0x14001242b  add     rsp, 30h
0x14001242f  pop     rdi
0x140012430  retn
0x140012432  mov     rdx, rbx; jumptable 0000000140012340 case 7
0x140012435  mov     rcx, rdi; this
0x140012438  call    ?OnPacketCompletionRead@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionRead(SC_PACKET *)
0x14001243d  mov     rbx, [rsp+38h+arg_10]
0x140012442  mov     rsi, [rsp+38h+arg_18]
0x140012447  add     rsp, 30h
0x14001244b  pop     rdi
0x14001244c  retn
0x14001244e  mov     rdx, rbx; jumptable 0000000140012340 case 8
0x140012451  mov     rcx, rdi; this
0x140012454  call    ?OnPacketCompletionReadUnit@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionReadUnit(SC_PACKET *)
0x140012459  mov     rbx, [rsp+38h+arg_10]
0x14001245e  mov     rsi, [rsp+38h+arg_18]
0x140012463  add     rsp, 30h
0x140012467  pop     rdi
0x140012468  retn
0x14001246a  mov     esi, [rbx+0B4h]; jumptable 0000000140012340 case 19
0x140012470  mov     rax, [rbx+10h]
0x140012474  mov     rax, [rax+80h]
0x14001247b  mov     rax, [rax+18h]
0x14001247f  cmp     dword ptr [rax+4], 80000011h
0x140012486  jnz     def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x14001248c  mov     rdx, rbx; struct SC_PACKET *
0x14001248f  mov     rcx, rdi; this
0x140012492  call    ?OnPacketCompletionDsmAddresses@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionDsmAddresses(SC_PACKET *)
0x140012497  mov     esi, eax
0x140012499  jmp     def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x14001249e  add     rax, 58h ; 'X'
0x1400124a2  jmp     loc_1400123A4
0x1400124a7  cmp     byte ptr [rbx+0AAh], 6
0x1400124ae  jz      loc_1400123DE
0x1400124b4  movzx   eax, word ptr [r14]
0x1400124b8  test    al, 40h
0x1400124ba  jz      loc_140069B52
0x1400124c0  mov     eax, [rbx+90h]
0x1400124c6  mov     rcx, rdi; this
0x1400124c9  mov     r9, [rbx+88h]; unsigned __int64
0x1400124d0  mov     r8d, [rbx+98h]; unsigned int
0x1400124d7  mov     edx, [rbx+94h]; unsigned int
0x1400124dd  mov     [rsp+38h+var_10], 1; unsigned __int8
0x1400124e2  mov     [rsp+38h+var_18], rax; unsigned __int64
0x1400124e7  call    ?SetStripeState@SIO_RAID@@IEAAXKK_K0E@Z; SIO_RAID::SetStripeState(ulong,ulong,unsigned __int64,unsigned __int64,uchar)
0x1400124ec  nop
0x1400124ed  jmp     loc_140069B52
0x1400124f2  test    esi, esi
0x1400124f4  jns     loc_1400123D3
0x1400124fa  jmp     loc_1400123DE
0x1400124ff  mov     rax, [rdi+8]
0x140012503  mov     edx, [rbx+90h]
0x140012509  mov     rcx, [rax+0B0h]
0x140012510  lock add [rcx+208h], rdx
0x140012518  jmp     loc_14001238F
0x14001251d  lea     rcx, [rdi+18h]; SpinLock
0x140012521  call    cs:__imp_ExAcquireSpinLockExclusive
0x140012528  nop     dword ptr [rax+rax+00h]
0x14001252d  movzx   edx, word ptr [r14]
0x140012531  mov     ecx, 0FFFEh
0x140012536  and     dx, cx
0x140012539  lea     rcx, [rdi+18h]; SpinLock
0x14001253d  mov     [r14], dx
0x140012541  movzx   edx, al; OldIrql
0x140012544  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001254b  nop     dword ptr [rax+rax+00h]
0x140012550  jmp     loc_1400123D3
0x140012555  mov     eax, [rbx+98h]
0x14001255b  inc     eax
0x14001255d  mov     [rbp+0C0h], rax
0x140012564  jmp     loc_1400123DE
0x140012569  mov     esi, [rbx+0B4h]; jumptable 0000000140012340 case 11
0x14001256f  cmp     esi, 0C0E7001Bh
0x140012575  jz      def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x14001257b  cmp     esi, 80000016h
0x140012581  jz      def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x140012587  test    esi, esi
0x140012589  jns     def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x14001258f  mov     r8d, [rbx+98h]; unsigned int
0x140012596  xor     r9d, r9d; unsigned __int8
0x140012599  mov     edx, [rbx+94h]; unsigned int
0x14001259f  mov     rcx, rdi; this
0x1400125a2  mov     dword ptr [rsp+38h+var_18], esi; int
0x1400125a6  call    ?TransitionColumnState@SIO_RAID@@IEAAJKKEJ@Z; SIO_RAID::TransitionColumnState(ulong,ulong,uchar,long)
0x1400125ab  mov     esi, eax
0x1400125ad  jmp     def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x1400125b2  mov     esi, [rbx+0B4h]; jumptable 0000000140012340 case 17
0x1400125b8  movzx   ecx, byte ptr [rbx+0AAh]
0x1400125bf  sub     ecx, 1
0x1400125c2  jz      loc_140069B75
0x1400125c8  cmp     ecx, 3
0x1400125cb  jnz     def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x1400125d1  mov     byte ptr [rbx+0AAh], 1
0x1400125d8  mov     esi, 0C000022Dh
0x1400125dd  jmp     def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
0x1400125e2  mov     rcx, [rdi+8]
0x1400125e6  mov     rdx, rbx; struct SIO_LOG_PACKET *
0x1400125e9  mov     rcx, [rcx+178h]; this
0x1400125f0  call    ?UpdateCountersIoComplete@SIO_LOG@@QEAAXPEAVSIO_LOG_PACKET@@@Z; SIO_LOG::UpdateCountersIoComplete(SIO_LOG_PACKET *)
0x1400125f5  jmp     loc_140012303
0x140069b52  mov     r8d, [rbx+98h]; unsigned int
0x140069b59  xor     r9d, r9d; unsigned __int8
0x140069b5c  mov     edx, [rbx+94h]; unsigned int
0x140069b62  mov     rcx, rdi; this
0x140069b65  mov     dword ptr [rsp+38h+var_18], esi; int
0x140069b69  call    ?TransitionColumnState@SIO_RAID@@IEAAJKKEJ@Z; SIO_RAID::TransitionColumnState(ulong,ulong,uchar,long)
0x140069b6e  mov     esi, eax
0x140069b70  jmp     loc_1400124F2
0x140069b75  mov     rdx, rbx; struct SC_PACKET *
0x140069b78  mov     rcx, rdi; this
0x140069b7b  call    ?ReleaseRegion@SIO_RAID@@QEAAXPEAVSC_PACKET@@@Z; SIO_RAID::ReleaseRegion(SC_PACKET *)
0x140069b80  nop
0x140069b81  jmp     def_140012340; jumptable 0000000140012340 default case, cases 9,12-16,18,20
```
