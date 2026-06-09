# SIO_RAID1::OnPacketCompletion(SC_PACKET *)

- ea: `0x140011e70`
- end: `0x14001226d`
- name: `?OnPacketCompletion@SIO_RAID1@@UEAAJPEAVSC_PACKET@@@Z`
- size: `1021`
- prototype: `__int64 __fastcall(SIO_RAID1 *__hidden this, struct SC_PACKET *)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400061a0`
- `0x140011e70`
- `0x140012280`
- `0x140012600`
- `0x140012880`
- `0x1400129d0`
- `0x140012c60`
- `0x14001fc10`
- `0x14004bbc0`
- `0x14004bd88`
- `0x14004c820`
- `0x14004cc58`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001218a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001218a`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012167`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012167`

## pseudocode

```c
int __fastcall SIO_RAID1::OnPacketCompletion(volatile LONG *this, struct SC_PACKET *a2)
{
  int result; // eax
  int v4; // edx
  int v6; // edx
  int v7; // edx
  int v8; // esi
  int v9; // eax
  char v10; // al
  int v11; // esi
  __int64 v12; // rbp
  char v13; // cl
  __int64 v14; // rax
  __int64 v15; // rax
  _WORD *v16; // r14
  int v17; // ecx
  KIRQL v18; // al

  result = *((_DWORD *)a2 + 45);
  v4 = *((unsigned __int8 *)a2 + 169);
  if ( v4 != 14 )
  {
    v6 = v4 - 7;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 4 )
        {
          return SIO_RAID1::OnPacketCompletionRegenerate((SIO_RAID1 *)this, a2);
        }
        else
        {
          v8 = *((_DWORD *)a2 + 45);
          v9 = *((unsigned __int8 *)a2 + 169);
          if ( v9 == 16 )
            return v8;
          if ( v9 != 9 )
          {
            switch ( *((_BYTE *)a2 + 169) )
            {
              case 7:
                return SIO_RAID::OnPacketCompletionRead((SIO_RAID *)this, a2);
              case 8:
                return SIO_RAID::OnPacketCompletionReadUnit(this, a2);
              case 0xA:
                v11 = *((_DWORD *)a2 + 45);
                v12 = *((_QWORD *)a2 + 2);
                if ( v11 == -1058602981 || v11 == -2147483626 )
                  goto LABEL_45;
                v13 = *(_BYTE *)(*((_QWORD *)a2 + 1) + 169LL);
                if ( v13 == 13 || v13 == 15 )
                  _InterlockedAdd64(
                    (volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)this + 1) + 176LL) + 520LL),
                    *((unsigned int *)a2 + 36));
                v14 = *((_QWORD *)this + 4);
                if ( v14 )
                  v15 = v14 + 88;
                else
                  v15 = *((_QWORD *)this + 1) + 80LL;
                v16 = (_WORD *)(*((_QWORD *)this + 6)
                              + 32LL
                              * (unsigned int)(*((_DWORD *)a2 + 37) + *((_DWORD *)a2 + 38) * *(_DWORD *)(v15 + 16)));
                if ( v11 < 0 )
                {
                  if ( *((_BYTE *)a2 + 170) == 6 )
                    return v11;
                  if ( (*v16 & 0x40) != 0 )
                    SIO_RAID::SetStripeState(
                      (SIO_RAID *)this,
                      *((_DWORD *)a2 + 37),
                      *((_DWORD *)a2 + 38),
                      *((_QWORD *)a2 + 17),
                      *((unsigned int *)a2 + 36),
                      1u);
                  v11 = SIO_RAID::TransitionColumnState(
                          (SIO_RAID *)this,
                          *((_DWORD *)a2 + 37),
                          *((_DWORD *)a2 + 38),
                          0,
                          v11);
LABEL_45:
                  if ( v11 < 0 )
                    return v11;
                }
                else if ( (*v16 & 1) != 0 )
                {
                  v18 = ExAcquireSpinLockExclusive(this + 6);
                  *v16 &= ~1u;
                  ExReleaseSpinLockExclusive(this + 6, v18);
                }
                if ( (*((_DWORD *)a2 + 19) & 2) != 0 )
                  *(_QWORD *)(v12 + 192) = (unsigned int)(*((_DWORD *)a2 + 38) + 1);
                return v11;
              case 0xB:
                v8 = *((_DWORD *)a2 + 45);
                if ( v8 != -1058602981 && v8 != -2147483626 && v8 < 0 )
                  return SIO_RAID::TransitionColumnState(
                           (SIO_RAID *)this,
                           *((_DWORD *)a2 + 37),
                           *((_DWORD *)a2 + 38),
                           0,
                           *((_DWORD *)a2 + 45));
                return v8;
              case 0x11:
                v8 = *((_DWORD *)a2 + 45);
                if ( *((_BYTE *)a2 + 170) == 1 )
                {
                  SIO_RAID::ReleaseRegion((SIO_RAID *)this, a2);
                  return v8;
                }
                if ( *((_BYTE *)a2 + 170) != 4 )
                  return v8;
                goto LABEL_54;
              case 0x13:
                v8 = *((_DWORD *)a2 + 45);
                if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 128LL) + 24LL) + 4LL) == -2147483631 )
                  return SIO_RAID::OnPacketCompletionDsmAddresses((SIO_RAID *)this, a2);
                return v8;
              default:
                return v8;
            }
          }
          v8 = *((_DWORD *)a2 + 45);
          v10 = *((_BYTE *)a2 + 170);
          if ( v10 == 1 )
          {
            v8 = *((_DWORD *)a2 + 45);
            if ( (*((_DWORD *)a2 + 19) & 0x10000000) == 0 )
              SIO_RAID::ReleaseRegion((SIO_RAID *)this, a2);
            if ( v8 < 0 )
              return v8;
            *((_DWORD *)a2 + 36) = *((_DWORD *)a2 + 67);
            if ( *((_QWORD *)this + 8) )
              SIO_LOG::UpdateCountersIoComplete(*(SIO_LOG **)(*((_QWORD *)this + 1) + 376LL), a2);
            goto LABEL_14;
          }
          if ( v10 != 4 )
          {
            if ( v10 == 8 )
              v8 = SIO_RAID::OnPacketCompletionWriteLog((SIO_RAID *)this, a2);
LABEL_14:
            if ( v8 >= 0 && (*((_DWORD *)a2 + 19) & 2) != 0 )
              *(_QWORD *)(*((_QWORD *)a2 + 2) + 192LL) += *((unsigned int *)a2 + 36);
            return v8;
          }
LABEL_54:
          *((_BYTE *)a2 + 170) = 1;
          return -1073741267;
        }
      }
      else
      {
        v17 = *((_DWORD *)a2 + 45);
        if ( *(_BYTE *)(*((_QWORD *)a2 + 2) + 170LL) != 24 )
          return SIO_RAID::OnPacketCompletion((SIO_RAID *)this, a2);
        return v17;
      }
    }
    else
    {
      return SIO_RAID1::OnPacketCompletionRead((SIO_RAID1 *)this, a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011e70  mov     [rsp+arg_18], rbx
0x140011e75  push    rdi
0x140011e76  sub     rsp, 30h
0x140011e7a  mov     eax, [rdx+0B4h]
0x140011e80  mov     rbx, rdx
0x140011e83  movzx   edx, byte ptr [rdx+0A9h]
0x140011e8a  mov     rdi, rcx
0x140011e8d  cmp     edx, 0Eh
0x140011e90  jnz     short loc_140011E9E
0x140011e92  mov     rbx, [rsp+38h+arg_18]
0x140011e97  add     rsp, 30h
0x140011e9b  pop     rdi
0x140011e9c  retn
0x140011e9e  sub     edx, 7
0x140011ea1  jz      loc_1400120D7
0x140011ea7  sub     edx, 1
0x140011eaa  jz      loc_1400120B2
0x140011eb0  cmp     edx, 4
0x140011eb3  jz      loc_14001224E
0x140011eb9  mov     [rsp+38h+arg_8], rsi
0x140011ebe  mov     esi, [rbx+0B4h]
0x140011ec4  movzx   eax, byte ptr [rbx+0A9h]
0x140011ecb  cmp     eax, 10h
0x140011ece  jnz     short loc_140011EE3
0x140011ed0  mov     eax, esi; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x140011ed2  mov     rsi, [rsp+38h+arg_8]
0x140011ed7  mov     rbx, [rsp+38h+arg_18]
0x140011edc  add     rsp, 30h
0x140011ee0  pop     rdi
0x140011ee1  retn
0x140011ee3  cmp     eax, 9
0x140011ee6  jnz     short loc_140011F4D
0x140011ee8  mov     esi, [rbx+0B4h]
0x140011eee  movzx   eax, byte ptr [rbx+0AAh]
0x140011ef5  cmp     al, 1
0x140011ef7  jnz     loc_140012027
0x140011efd  mov     esi, [rbx+0B4h]
0x140011f03  test    dword ptr [rbx+4Ch], 10000000h
0x140011f0a  jnz     short loc_140011F14
0x140011f0c  mov     rdx, rbx; struct SC_PACKET *
0x140011f0f  call    ?ReleaseRegion@SIO_RAID@@QEAAXPEAVSC_PACKET@@@Z; SIO_RAID::ReleaseRegion(SC_PACKET *)
0x140011f14  test    esi, esi
0x140011f16  js      short def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x140011f18  mov     eax, [rbx+10Ch]
0x140011f1e  mov     [rbx+90h], eax
0x140011f24  cmp     qword ptr [rdi+40h], 0
0x140011f29  jnz     loc_140012236
0x140011f2f  test    esi, esi
0x140011f31  js      short def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x140011f33  mov     eax, [rbx+4Ch]
0x140011f36  test    al, 2
0x140011f38  jz      short def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x140011f3a  mov     rdx, [rbx+10h]
0x140011f3e  mov     ecx, [rbx+90h]
0x140011f44  add     [rdx+0C0h], rcx
0x140011f4b  jmp     short def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x140011f4d  add     eax, 0FFFFFFF9h; switch 14 cases
0x140011f50  cmp     eax, 0Dh
0x140011f53  ja      def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x140011f59  lea     rdx, cs:140000000h
0x140011f60  cdqe
0x140011f62  mov     ecx, ds:(jpt_140011F6C - 140000000h)[rdx+rax*4]
0x140011f69  add     rcx, rdx
0x140011f6c  jmp     rcx; switch jump
0x140011f72  mov     esi, [rbx+0B4h]; jumptable 0000000140011F6C case 10
0x140011f78  mov     [rsp+38h+arg_0], rbp
0x140011f7d  mov     rbp, [rbx+10h]
0x140011f81  mov     [rsp+38h+arg_10], r14
0x140011f86  cmp     esi, 0C0E7001Bh
0x140011f8c  jz      loc_140012138
0x140011f92  cmp     esi, 80000016h
0x140011f98  jz      loc_140012138
0x140011f9e  mov     rax, [rbx+8]
0x140011fa2  movzx   ecx, byte ptr [rax+0A9h]; this
0x140011fa9  cmp     cl, 0Dh
0x140011fac  jz      loc_140012145
0x140011fb2  cmp     cl, 0Fh
0x140011fb5  jz      loc_140012145
0x140011fbb  mov     rax, [rdi+20h]
0x140011fbf  test    rax, rax
0x140011fc2  jnz     loc_1400120E4
0x140011fc8  mov     rax, [rdi+8]
0x140011fcc  add     rax, 50h ; 'P'
0x140011fd0  mov     r14d, [rax+10h]
0x140011fd4  imul    r14d, [rbx+98h]
0x140011fdc  add     r14d, [rbx+94h]
0x140011fe3  shl     r14, 5
0x140011fe7  add     r14, [rdi+30h]
0x140011feb  test    esi, esi
0x140011fed  js      loc_1400120ED
0x140011ff3  movzx   eax, word ptr [r14]
0x140011ff7  test    al, 1
0x140011ff9  jnz     loc_140012163
0x140011fff  mov     eax, [rbx+4Ch]
0x140012002  test    al, 2
0x140012004  jnz     loc_14001219B
0x14001200a  mov     r14, [rsp+38h+arg_10]
0x14001200f  mov     eax, esi
0x140012011  mov     rsi, [rsp+38h+arg_8]
0x140012016  mov     rbp, [rsp+38h+arg_0]
0x14001201b  mov     rbx, [rsp+38h+arg_18]
0x140012020  add     rsp, 30h
0x140012024  pop     rdi
0x140012025  retn
0x140012027  cmp     al, 4
0x140012029  jz      loc_140012217
0x14001202f  cmp     al, 8
0x140012031  jnz     loc_140011F2F
0x140012037  mov     rdx, rbx; struct SC_PACKET *
0x14001203a  call    ?OnPacketCompletionWriteLog@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionWriteLog(SC_PACKET *)
0x14001203f  mov     esi, eax
0x140012041  jmp     loc_140011F2F
0x140012046  mov     rdx, rbx; jumptable 0000000140011F6C case 7
0x140012049  mov     rcx, rdi; this
0x14001204c  call    ?OnPacketCompletionRead@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionRead(SC_PACKET *)
0x140012051  mov     rsi, [rsp+38h+arg_8]
0x140012056  mov     rbx, [rsp+38h+arg_18]
0x14001205b  add     rsp, 30h
0x14001205f  pop     rdi
0x140012060  retn
0x140012062  mov     rdx, rbx; jumptable 0000000140011F6C case 8
0x140012065  mov     rcx, rdi; this
0x140012068  call    ?OnPacketCompletionReadUnit@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionReadUnit(SC_PACKET *)
0x14001206d  mov     rsi, [rsp+38h+arg_8]
0x140012072  mov     rbx, [rsp+38h+arg_18]
0x140012077  add     rsp, 30h
0x14001207b  pop     rdi
0x14001207c  retn
0x14001207e  mov     esi, [rbx+0B4h]; jumptable 0000000140011F6C case 19
0x140012084  mov     rax, [rbx+10h]
0x140012088  mov     rax, [rax+80h]
0x14001208f  mov     rax, [rax+18h]
0x140012093  cmp     dword ptr [rax+4], 80000011h
0x14001209a  jnz     def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x1400120a0  mov     rdx, rbx; struct SC_PACKET *
0x1400120a3  mov     rcx, rdi; this
0x1400120a6  call    ?OnPacketCompletionDsmAddresses@SIO_RAID@@AEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletionDsmAddresses(SC_PACKET *)
0x1400120ab  mov     esi, eax
0x1400120ad  jmp     def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x1400120b2  mov     ecx, [rbx+0B4h]; this
0x1400120b8  mov     rax, [rbx+10h]
0x1400120bc  cmp     byte ptr [rax+0AAh], 18h
0x1400120c3  jnz     loc_14001225B
0x1400120c9  mov     eax, ecx
0x1400120cb  mov     rbx, [rsp+38h+arg_18]
0x1400120d0  add     rsp, 30h
0x1400120d4  pop     rdi
0x1400120d5  retn
0x1400120d7  mov     rdx, rbx; struct SC_PACKET *
0x1400120da  call    ?OnPacketCompletionRead@SIO_RAID1@@QEAAJPEAVSC_PACKET@@@Z; SIO_RAID1::OnPacketCompletionRead(SC_PACKET *)
0x1400120df  jmp     loc_140011E92
0x1400120e4  add     rax, 58h ; 'X'
0x1400120e8  jmp     loc_140011FD0
0x1400120ed  cmp     byte ptr [rbx+0AAh], 6
0x1400120f4  jz      loc_14001200A
0x1400120fa  movzx   eax, word ptr [r14]
0x1400120fe  test    al, 40h
0x140012100  jz      loc_1400699DE
0x140012106  mov     eax, [rbx+90h]
0x14001210c  mov     rcx, rdi; this
0x14001210f  mov     r9, [rbx+88h]; unsigned __int64
0x140012116  mov     r8d, [rbx+98h]; unsigned int
0x14001211d  mov     edx, [rbx+94h]; unsigned int
0x140012123  mov     [rsp+38h+var_10], 1; unsigned __int8
0x140012128  mov     [rsp+38h+var_18], rax; unsigned __int64
0x14001212d  call    ?SetStripeState@SIO_RAID@@IEAAXKK_K0E@Z; SIO_RAID::SetStripeState(ulong,ulong,unsigned __int64,unsigned __int64,uchar)
0x140012132  nop
0x140012133  jmp     loc_1400699DE
0x140012138  test    esi, esi
0x14001213a  jns     loc_140011FFF
0x140012140  jmp     loc_14001200A
0x140012145  mov     rax, [rdi+8]
0x140012149  mov     edx, [rbx+90h]
0x14001214f  mov     rcx, [rax+0B0h]
0x140012156  lock add [rcx+208h], rdx
0x14001215e  jmp     loc_140011FBB
0x140012163  lea     rcx, [rdi+18h]; SpinLock
0x140012167  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001216e  nop     dword ptr [rax+rax+00h]
0x140012173  movzx   edx, word ptr [r14]
0x140012177  mov     ecx, 0FFFEh
0x14001217c  and     dx, cx
0x14001217f  lea     rcx, [rdi+18h]; SpinLock
0x140012183  mov     [r14], dx
0x140012187  movzx   edx, al; OldIrql
0x14001218a  call    cs:__imp_ExReleaseSpinLockExclusive
0x140012191  nop     dword ptr [rax+rax+00h]
0x140012196  jmp     loc_140011FFF
0x14001219b  mov     eax, [rbx+98h]
0x1400121a1  inc     eax
0x1400121a3  mov     [rbp+0C0h], rax
0x1400121aa  jmp     loc_14001200A
0x1400121af  mov     esi, [rbx+0B4h]; jumptable 0000000140011F6C case 11
0x1400121b5  cmp     esi, 0C0E7001Bh
0x1400121bb  jz      def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x1400121c1  cmp     esi, 80000016h
0x1400121c7  jz      def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x1400121cd  test    esi, esi
0x1400121cf  jns     def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x1400121d5  mov     r8d, [rbx+98h]; unsigned int
0x1400121dc  xor     r9d, r9d; unsigned __int8
0x1400121df  mov     edx, [rbx+94h]; unsigned int
0x1400121e5  mov     rcx, rdi; this
0x1400121e8  mov     dword ptr [rsp+38h+var_18], esi; int
0x1400121ec  call    ?TransitionColumnState@SIO_RAID@@IEAAJKKEJ@Z; SIO_RAID::TransitionColumnState(ulong,ulong,uchar,long)
0x1400121f1  mov     esi, eax
0x1400121f3  jmp     def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x1400121f8  mov     esi, [rbx+0B4h]; jumptable 0000000140011F6C case 17
0x1400121fe  movzx   ecx, byte ptr [rbx+0AAh]
0x140012205  sub     ecx, 1
0x140012208  jz      loc_140069A01
0x14001220e  cmp     ecx, 3
0x140012211  jnz     def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
0x140012217  mov     esi, 0C000022Dh
0x14001221c  mov     byte ptr [rbx+0AAh], 1
0x140012223  mov     rbx, [rsp+38h+arg_18]
0x140012228  mov     eax, esi
0x14001222a  mov     rsi, [rsp+38h+arg_8]
0x14001222f  add     rsp, 30h
0x140012233  pop     rdi
0x140012234  retn
0x140012236  mov     rcx, [rdi+8]
0x14001223a  mov     rdx, rbx; struct SIO_LOG_PACKET *
0x14001223d  mov     rcx, [rcx+178h]; this
0x140012244  call    ?UpdateCountersIoComplete@SIO_LOG@@QEAAXPEAVSIO_LOG_PACKET@@@Z; SIO_LOG::UpdateCountersIoComplete(SIO_LOG_PACKET *)
0x140012249  jmp     loc_140011F2F
0x14001224e  mov     rdx, rbx; struct SC_PACKET *
0x140012251  call    ?OnPacketCompletionRegenerate@SIO_RAID1@@QEAAJPEAVSC_PACKET@@@Z; SIO_RAID1::OnPacketCompletionRegenerate(SC_PACKET *)
0x140012256  jmp     loc_140011E92
0x14001225b  mov     rdx, rbx; struct SC_PACKET *
0x14001225e  mov     rcx, rdi; this
0x140012261  call    ?OnPacketCompletion@SIO_RAID@@UEAAJPEAVSC_PACKET@@@Z; SIO_RAID::OnPacketCompletion(SC_PACKET *)
0x140012266  mov     ecx, eax
0x140012268  jmp     loc_1400120C9
0x1400699de  mov     r8d, [rbx+98h]; unsigned int
0x1400699e5  xor     r9d, r9d; unsigned __int8
0x1400699e8  mov     edx, [rbx+94h]; unsigned int
0x1400699ee  mov     rcx, rdi; this
0x1400699f1  mov     dword ptr [rsp+38h+var_18], esi; int
0x1400699f5  call    ?TransitionColumnState@SIO_RAID@@IEAAJKKEJ@Z; SIO_RAID::TransitionColumnState(ulong,ulong,uchar,long)
0x1400699fa  mov     esi, eax
0x1400699fc  jmp     loc_140012138
0x140069a01  mov     rdx, rbx; struct SC_PACKET *
0x140069a04  mov     rcx, rdi; this
0x140069a07  call    ?ReleaseRegion@SIO_RAID@@QEAAXPEAVSC_PACKET@@@Z; SIO_RAID::ReleaseRegion(SC_PACKET *)
0x140069a0c  nop
0x140069a0d  jmp     def_140011F6C; jumptable 0000000140011F6C default case, cases 9,12-16,18,20
```
