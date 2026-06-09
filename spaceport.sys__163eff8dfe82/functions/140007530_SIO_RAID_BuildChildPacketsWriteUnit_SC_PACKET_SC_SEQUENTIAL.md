# SIO_RAID::BuildChildPacketsWriteUnit(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x140007530`
- end: `0x1400079fa`
- name: `?BuildChildPacketsWriteUnit@SIO_RAID@@AEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `1226`
- prototype: `__int64 __fastcall(SIO_RAID *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x140006980`
- `0x140006b40`
- `0x140009770`

## callees

- `0x1400057f0`
- `0x140005940`
- `0x140007530`
- `0x140009f80`
- `0x14000b170`
- `0x14000e2e0`
- `0x14004b708`
- `0x140068150`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007745`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007745`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400076b1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400076b1`

## pseudocode

```c
__int64 __fastcall SIO_RAID::BuildChildPacketsWriteUnit(SIO_RAID *this, struct SC_PACKET *a2, struct SC_SEQUENTIAL *a3)
{
  unsigned int v3; // r12d
  char v4; // r8
  unsigned int v5; // r15d
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  char v14; // dl
  __int64 v15; // rcx
  unsigned __int64 v16; // r13
  __int64 v17; // rcx
  __int64 v18; // rbx
  SIO_SPACE_DRIVE *DriveContext; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  KIRQL v22; // al
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rbx
  char v27; // al
  unsigned int v28; // ecx
  __int16 v29; // ax
  unsigned int v30; // ebp
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  char v35; // dl
  struct SC_SEQUENTIAL *v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rax
  SC_PACKET *v39; // rcx
  SC_PACKET *v40; // rax
  unsigned __int8 v41; // r8
  SC_PACKET *v42; // rbx
  int v43; // eax
  char *v44; // rax
  char *v45; // rbx
  __int64 v46; // rcx
  char **v47; // rcx
  char v49; // [rsp+70h] [rbp+8h]
  __int64 v50; // [rsp+78h] [rbp+10h]
  KIRQL v51; // [rsp+78h] [rbp+10h]

  v3 = *((_DWORD *)a2 + 37);
  v4 = 0;
  v5 = *((_DWORD *)a2 + 48);
  v6 = 0;
  v7 = 0;
  v49 = 0;
  if ( !*((_BYTE *)this + 43) )
  {
    v29 = *((_WORD *)this + 20);
    goto LABEL_69;
  }
  do
  {
    if ( _bittest((const signed __int32 *)a2 + 39, v7) )
    {
      v10 = *((_QWORD *)this + 4);
      v11 = v10 + 88;
      if ( v10 )
        v12 = v10 + 88;
      else
        v12 = *((_QWORD *)this + 1) + 80LL;
      v13 = *((_QWORD *)this + 6);
      v14 = *(_BYTE *)(32LL * (v3 + *(_DWORD *)(v12 + 16) * v7) + v13 + 2) & 0xF;
      if ( ((v14 - 1) & 0xFA) != 0 || v14 == 2 )
      {
        if ( !v10 )
          v11 = *((_QWORD *)this + 1) + 80LL;
        if ( (*(_WORD *)(32LL * (v3 + *(_DWORD *)(v11 + 16) * v7) + v13) & 0x40) != 0 )
        {
          v15 = *((_QWORD *)this + 4);
          v16 = *((unsigned int *)a2 + 36);
          v50 = *((_QWORD *)a2 + 17);
          v17 = v15 ? v15 + 88 : *((_QWORD *)this + 1) + 80LL;
          v18 = *((_QWORD *)this + 6) + 32LL * (v3 + *(_DWORD *)(v17 + 16) * v7);
          DriveContext = SIO_SPACE::GetDriveContext(*((SIO_SPACE **)this + 1), *(_DWORD *)(v18 + 4));
          if ( (int)SIO_SPACE_DRIVE::SetStripeState(DriveContext, *(_QWORD *)(v18 + 8) + v50, v16, 1u) < 0 )
            SIO_RAID::InvalidateStripeState(this, v3, v7);
        }
        v20 = *((_QWORD *)this + 4);
        if ( v20 )
          v21 = v20 + 88;
        else
          v21 = *((_QWORD *)this + 1) + 80LL;
        if ( (*(_BYTE *)(32LL * (v3 + *(_DWORD *)(v21 + 16) * v7) + *((_QWORD *)this + 6) + 2) & 0xF) == 2 )
        {
          v22 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)this + 6);
          v24 = *((_QWORD *)this + 4);
          v6 = -1058602989;
          v51 = v22;
          if ( v24 )
            v25 = v24 + 88;
          else
            v25 = *((_QWORD *)this + 1) + 80LL;
          v26 = *((_QWORD *)this + 6) + 32LL * (v3 + *(_DWORD *)(v25 + 16) * v7);
          if ( (*(_WORD *)v26 & 2) == 0 && (*(_BYTE *)(v26 + 3) & 0xFu) <= 1 )
          {
            v27 = *(_BYTE *)(v26 + 2) & 0xF;
            if ( v27 == 1 || (LOBYTE(v23) = 0, v27 == 2) )
              LOBYTE(v23) = 1;
            if ( (*(unsigned __int8 (__fastcall **)(SIO_RAID *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 168LL))(
                   this,
                   v3,
                   v7,
                   v23) )
            {
              v6 = -1058602997;
            }
            else
            {
              *(_BYTE *)(v26 + 3) = 19;
            }
          }
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)this + 6, v51);
        }
        v4 = v49;
      }
      else
      {
        v4 = ++v49;
      }
    }
    v28 = *((unsigned __int8 *)this + 43);
    ++v7;
  }
  while ( v7 < v28 );
  if ( (v6 & 0x80000000) != 0 )
    return v6;
  v29 = *((_WORD *)this + 20);
  if ( !v4 )
  {
LABEL_69:
    if ( (v29 & 4) == 0 )
      return (unsigned int)-1073741810;
    return v6;
  }
  v30 = -1;
  if ( (v29 & 0x200) != 0 )
  {
    v31 = (*(__int64 (__fastcall **)(SIO_RAID *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 144LL))(
            this,
            v3,
            (unsigned int)((1 << v28) - 1),
            *((_QWORD *)a2 + 17));
    v4 = v49;
    v30 = v31;
  }
  while ( 1 )
  {
    v32 = *((unsigned __int8 *)this + 43);
    if ( v5 >= v32 )
      return v6;
    if ( v4 == (_BYTE)v32
      || _bittest((const signed __int32 *)a2 + 39, v5)
      && ((v33 = *((_QWORD *)this + 4)) == 0 ? (v34 = *((_QWORD *)this + 1) + 80LL) : (v34 = v33 + 88),
          (v35 = *(_BYTE *)(32LL * (v3 + *(_DWORD *)(v34 + 16) * v5) + *((_QWORD *)this + 6) + 2) & 0xF,
           ((v35 - 1) & 0xFA) == 0)
       && v35 != 2) )
    {
      v36 = a3;
      if ( a3 )
      {
        v42 = *(SC_PACKET **)a3;
        *((_DWORD *)v42 + 19) |= *((_DWORD *)a2 + 19) & 4;
        *((_DWORD *)v42 + 28) = 1;
        *((_QWORD *)v42 + 15) = *((_QWORD *)a2 + 15);
        v43 = *((_DWORD *)a2 + 41);
        if ( v43 != -1 )
          *((_DWORD *)v42 + 41) = v43;
      }
      else
      {
        v37 = *((_QWORD *)a2 + 1);
        if ( v37 && (v38 = *(unsigned __int8 *)(v37 + 173), (unsigned __int8)v38 < *(_BYTE *)(v37 + 172)) )
        {
          v39 = (SC_PACKET *)(v37 + 248 * v38);
          *((_BYTE *)v39 + 172) = 0;
          *((_BYTE *)v39 + 173) = *(_BYTE *)(v37 + 173);
          *((_BYTE *)v39 + 171) = -1;
          ++*(_BYTE *)(v37 + 173);
        }
        else
        {
          v39 = (SC_PACKET *)SC_PACKET::operator new(0xF8u);
        }
        if ( !v39 )
          return (unsigned int)-1073741670;
        v40 = SC_PACKET::SC_PACKET(v39);
        v42 = v40;
        if ( !v40 )
          return (unsigned int)-1073741670;
        v6 = SC_PACKET::Split(v40, a2, 0, *((_DWORD *)a2 + 36), v41 > 1u);
        if ( (v6 & 0x80000000) != 0 )
        {
          (**(void (__fastcall ***)(SC_PACKET *, __int64))v42)(v42, 1);
          return v6;
        }
        v4 = v49;
        v36 = 0;
      }
      *((_QWORD *)v42 + 16) = v30;
      *((_QWORD *)v42 + 17) = *((_QWORD *)a2 + 17);
      *((_DWORD *)v42 + 36) = *((_DWORD *)a2 + 36);
      *((_DWORD *)v42 + 37) = v3;
      *((_DWORD *)v42 + 38) = v5;
      *((_BYTE *)v42 + 168) = 4;
      *((_BYTE *)v42 + 170) = *((_BYTE *)a2 + 170);
      *((_QWORD *)v42 + 30) = this;
      *((_QWORD *)v42 + 1) = *((_QWORD *)a2 + 1);
      v44 = (char *)a2 + 40;
      *((_QWORD *)v42 + 2) = a2;
      v45 = (char *)v42 + 56;
      if ( v30 == v5 )
      {
        v47 = (char **)*((_QWORD *)a2 + 6);
        if ( *v47 != v44 )
LABEL_67:
          __fastfail(3u);
        *(_QWORD *)v45 = v44;
        *((_QWORD *)v45 + 1) = v47;
        *v47 = v45;
        *((_QWORD *)a2 + 6) = v45;
      }
      else
      {
        v46 = *(_QWORD *)v44;
        if ( *(char **)(*(_QWORD *)v44 + 8LL) != v44 )
          goto LABEL_67;
        *(_QWORD *)v45 = v46;
        *((_QWORD *)v45 + 1) = v44;
        *(_QWORD *)(v46 + 8) = v45;
        *(_QWORD *)v44 = v45;
      }
      ++*((_DWORD *)a2 + 18);
      if ( v36 )
        return v6;
    }
    ++v5;
  }
}

```

## disassembly

```asm
0x140007530  mov     [rsp+arg_10], r8
0x140007535  push    rbx
0x140007536  push    rbp
0x140007537  push    rsi
0x140007538  push    rdi
0x140007539  push    r12
0x14000753b  push    r14
0x14000753d  push    r15
0x14000753f  sub     rsp, 30h
0x140007543  mov     r12d, [rdx+94h]
0x14000754a  xor     r8b, r8b
0x14000754d  mov     r15d, [rdx+0C0h]
0x140007554  xor     r14d, r14d
0x140007557  xor     ebp, ebp
0x140007559  mov     [rsp+68h+arg_0], r8b
0x14000755e  mov     rsi, rdx
0x140007561  mov     rdi, rcx
0x140007564  cmp     [rcx+2Bh], bpl
0x140007568  jbe     loc_1400079D8
0x14000756e  mov     [rsp+68h+arg_18], r13
0x140007576  nop     word ptr [rax+rax+00000000h]
0x140007580  bt      [rsi+9Ch], ebp
0x140007587  jnb     loc_140007757
0x14000758d  mov     r8, [rdi+20h]
0x140007591  lea     rcx, [r8+58h]
0x140007595  test    r8, r8
0x140007598  jz      short loc_14000759F
0x14000759a  mov     rdx, rcx
0x14000759d  jmp     short loc_1400075A7
0x14000759f  mov     rdx, [rdi+8]
0x1400075a3  add     rdx, 50h ; 'P'
0x1400075a7  mov     r9, [rdi+30h]
0x1400075ab  mov     eax, ebp
0x1400075ad  imul    eax, [rdx+10h]
0x1400075b1  add     eax, r12d
0x1400075b4  shl     rax, 5
0x1400075b8  movzx   edx, byte ptr [rax+r9+2]
0x1400075be  and     dl, 0Fh
0x1400075c1  lea     eax, [rdx-1]
0x1400075c4  test    al, 0FAh
0x1400075c6  jnz     short loc_1400075E0
0x1400075c8  cmp     dl, 2
0x1400075cb  jz      short loc_1400075E0
0x1400075cd  movzx   r8d, [rsp+68h+arg_0]
0x1400075d3  inc     r8b
0x1400075d6  mov     [rsp+68h+arg_0], r8b
0x1400075db  jmp     loc_140007757
0x1400075e0  test    r8, r8
0x1400075e3  jnz     short loc_1400075ED
0x1400075e5  mov     rcx, [rdi+8]
0x1400075e9  add     rcx, 50h ; 'P'
0x1400075ed  mov     eax, ebp
0x1400075ef  imul    eax, [rcx+10h]
0x1400075f3  add     eax, r12d
0x1400075f6  shl     rax, 5
0x1400075fa  movzx   eax, word ptr [rax+r9]
0x1400075ff  test    al, 40h
0x140007601  jz      short loc_140007673
0x140007603  mov     rcx, [rdi+20h]
0x140007607  mov     rax, [rsi+88h]
0x14000760e  mov     r13d, [rsi+90h]
0x140007615  mov     [rsp+68h+arg_8], rax
0x14000761a  test    rcx, rcx
0x14000761d  jz      short loc_140007625
0x14000761f  add     rcx, 58h ; 'X'
0x140007623  jmp     short loc_14000762D
0x140007625  mov     rcx, [rdi+8]
0x140007629  add     rcx, 50h ; 'P'
0x14000762d  mov     ebx, ebp
0x14000762f  imul    ebx, [rcx+10h]
0x140007633  mov     rcx, [rdi+8]; this
0x140007637  add     ebx, r12d
0x14000763a  shl     rbx, 5
0x14000763e  add     rbx, [rdi+30h]
0x140007642  mov     edx, [rbx+4]; unsigned int
0x140007645  call    ?GetDriveContext@SIO_SPACE@@QEAAPEAVSIO_SPACE_DRIVE@@K@Z; SIO_SPACE::GetDriveContext(ulong)
0x14000764a  mov     rdx, [rsp+68h+arg_8]
0x14000764f  mov     rcx, rax; this
0x140007652  add     rdx, [rbx+8]; unsigned __int64
0x140007656  mov     r9b, 1; unsigned __int8
0x140007659  mov     r8, r13; unsigned __int64
0x14000765c  call    ?SetStripeState@SIO_SPACE_DRIVE@@QEAAJ_K0E@Z; SIO_SPACE_DRIVE::SetStripeState(unsigned __int64,unsigned __int64,uchar)
0x140007661  test    eax, eax
0x140007663  jns     short loc_140007673
0x140007665  mov     r8d, ebp; unsigned int
0x140007668  mov     edx, r12d; unsigned int
0x14000766b  mov     rcx, rdi; this
0x14000766e  call    ?InvalidateStripeState@SIO_RAID@@IEAAXKK@Z; SIO_RAID::InvalidateStripeState(ulong,ulong)
0x140007673  mov     rcx, [rdi+20h]
0x140007677  test    rcx, rcx
0x14000767a  jz      short loc_140007682
0x14000767c  add     rcx, 58h ; 'X'
0x140007680  jmp     short loc_14000768A
0x140007682  mov     rcx, [rdi+8]
0x140007686  add     rcx, 50h ; 'P'
0x14000768a  mov     eax, ebp
0x14000768c  imul    eax, [rcx+10h]
0x140007690  lea     ecx, [r12+rax]
0x140007694  mov     rax, [rdi+30h]
0x140007698  shl     rcx, 5
0x14000769c  movzx   ecx, byte ptr [rcx+rax+2]
0x1400076a1  and     cl, 0Fh
0x1400076a4  cmp     cl, 2
0x1400076a7  jnz     loc_140007751
0x1400076ad  lea     rcx, [rdi+18h]; SpinLock
0x1400076b1  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400076b8  nop     dword ptr [rax+rax+00h]
0x1400076bd  mov     rcx, [rdi+20h]
0x1400076c1  mov     r14d, 0C0E70013h
0x1400076c7  mov     byte ptr [rsp+68h+arg_8], al
0x1400076cb  test    rcx, rcx
0x1400076ce  jz      short loc_1400076D6
0x1400076d0  add     rcx, 58h ; 'X'
0x1400076d4  jmp     short loc_1400076DE
0x1400076d6  mov     rcx, [rdi+8]
0x1400076da  add     rcx, 50h ; 'P'
0x1400076de  mov     ebx, ebp
0x1400076e0  imul    ebx, [rcx+10h]
0x1400076e4  add     ebx, r12d
0x1400076e7  shl     rbx, 5
0x1400076eb  add     rbx, [rdi+30h]
0x1400076ef  movzx   eax, word ptr [rbx]
0x1400076f2  test    al, 2
0x1400076f4  jnz     short loc_14000773C
0x1400076f6  movzx   eax, byte ptr [rbx+3]
0x1400076fa  and     al, 0Fh
0x1400076fc  cmp     al, 1
0x1400076fe  ja      short loc_14000773C
0x140007700  movzx   eax, byte ptr [rbx+2]
0x140007704  and     al, 0Fh
0x140007706  cmp     al, 1
0x140007708  jz      short loc_140007711
0x14000770a  xor     r9b, r9b
0x14000770d  cmp     al, 2
0x14000770f  jnz     short loc_140007714
0x140007711  mov     r9b, 1
0x140007714  mov     rax, [rdi]
0x140007717  mov     r8d, ebp
0x14000771a  mov     edx, r12d
0x14000771d  mov     rcx, rdi
0x140007720  mov     rax, [rax+0A8h]
0x140007727  call    _guard_dispatch_icall
0x14000772c  test    al, al
0x14000772e  jz      short loc_140007738
0x140007730  mov     r14d, 0C0E7000Bh
0x140007736  jmp     short loc_14000773C
0x140007738  mov     byte ptr [rbx+3], 13h
0x14000773c  movzx   edx, byte ptr [rsp+68h+arg_8]; OldIrql
0x140007741  lea     rcx, [rdi+18h]; SpinLock
0x140007745  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000774c  nop     dword ptr [rax+rax+00h]
0x140007751  movzx   r8d, [rsp+68h+arg_0]
0x140007757  movzx   ecx, byte ptr [rdi+2Bh]
0x14000775b  inc     ebp
0x14000775d  cmp     ebp, ecx
0x14000775f  jb      loc_140007580
0x140007765  mov     r13, [rsp+68h+arg_18]
0x14000776d  test    r14d, r14d
0x140007770  js      loc_1400079E7
0x140007776  movzx   eax, word ptr [rdi+28h]
0x14000777a  test    r8b, r8b
0x14000777d  jz      loc_1400079DC
0x140007783  bt      ax, 9
0x140007788  mov     ebp, 0FFFFFFFFh
0x14000778d  jnb     short loc_1400077BF
0x14000778f  mov     rax, [rdi]
0x140007792  mov     r8d, 1
0x140007798  mov     r9, [rsi+88h]
0x14000779f  mov     edx, r12d
0x1400077a2  shl     r8d, cl
0x1400077a5  mov     rcx, rdi
0x1400077a8  dec     r8d
0x1400077ab  mov     rax, [rax+90h]
0x1400077b2  call    _guard_dispatch_icall
0x1400077b7  movzx   r8d, [rsp+68h+arg_0]
0x1400077bd  mov     ebp, eax
0x1400077bf  movzx   eax, byte ptr [rdi+2Bh]
0x1400077c3  cmp     r15d, eax
0x1400077c6  jnb     loc_1400079E7
0x1400077cc  cmp     r8b, al
0x1400077cf  jz      short loc_140007825
0x1400077d1  bt      [rsi+9Ch], r15d
0x1400077d9  jnb     loc_1400079AC
0x1400077df  mov     rcx, [rdi+20h]
0x1400077e3  test    rcx, rcx
0x1400077e6  jz      short loc_1400077EE
0x1400077e8  add     rcx, 58h ; 'X'
0x1400077ec  jmp     short loc_1400077F6
0x1400077ee  mov     rcx, [rdi+8]
0x1400077f2  add     rcx, 50h ; 'P'
0x1400077f6  mov     eax, r15d
0x1400077f9  imul    eax, [rcx+10h]
0x1400077fd  lea     ecx, [r12+rax]
0x140007801  mov     rax, [rdi+30h]
0x140007805  shl     rcx, 5
0x140007809  movzx   edx, byte ptr [rcx+rax+2]
0x14000780e  and     dl, 0Fh
0x140007811  lea     eax, [rdx-1]
0x140007814  test    al, 0FAh
0x140007816  jnz     loc_1400079AC
0x14000781c  cmp     dl, 2
0x14000781f  jz      loc_1400079AC
0x140007825  mov     rdx, [rsp+68h+arg_10]
0x14000782d  test    rdx, rdx
0x140007830  jnz     loc_1400078E3
0x140007836  mov     rdx, [rsi+8]
0x14000783a  test    rdx, rdx
0x14000783d  jz      short loc_14000787B
0x14000783f  movzx   eax, byte ptr [rdx+0ADh]
0x140007846  cmp     al, [rdx+0ACh]
0x14000784c  jnb     short loc_14000787B
0x14000784e  imul    rcx, rax, 0F8h
0x140007855  add     rcx, rdx
0x140007858  mov     byte ptr [rcx+0ACh], 0
0x14000785f  movzx   eax, byte ptr [rdx+0ADh]
0x140007866  mov     [rcx+0ADh], al
0x14000786c  mov     byte ptr [rcx+0ABh], 0FFh
0x140007873  inc     byte ptr [rdx+0ADh]
0x140007879  jmp     short loc_14000788E
0x14000787b  mov     ecx, 0F8h; NumberOfBytes
0x140007880  call    ??2SC_PACKET@@SAPEAX_K@Z; SC_PACKET::operator new(unsigned __int64)
0x140007885  movzx   r8d, [rsp+68h+arg_0]
0x14000788b  mov     rcx, rax; this
0x14000788e  test    rcx, rcx
0x140007891  jz      loc_1400079C9
0x140007897  call    ??0SC_PACKET@@QEAA@XZ; SC_PACKET::SC_PACKET(void)
0x14000789c  mov     rbx, rax
0x14000789f  test    rax, rax
0x1400078a2  jz      loc_1400079C9
0x1400078a8  mov     r9d, [rsi+90h]; unsigned int
0x1400078af  cmp     r8b, 1
0x1400078b3  mov     rdx, rsi; struct SC_PACKET *
0x1400078b6  mov     rcx, rbx; this
0x1400078b9  setnbe  al
0x1400078bc  xor     r8d, r8d; unsigned int
0x1400078bf  mov     [rsp+68h+var_48], al; unsigned __int8
0x1400078c3  call    ?Split@SC_PACKET@@QEAAJPEAV1@KKE@Z; SC_PACKET::Split(SC_PACKET *,ulong,ulong,uchar)
0x1400078c8  mov     r14d, eax
0x1400078cb  test    eax, eax
0x1400078cd  js      loc_1400079B4
0x1400078d3  movzx   r8d, [rsp+68h+arg_0]
0x1400078d9  mov     rdx, [rsp+68h+arg_10]
0x1400078e1  jmp     short loc_14000790F
0x1400078e3  mov     eax, [rsi+4Ch]
0x1400078e6  mov     rbx, [rdx]
0x1400078e9  and     eax, 4
0x1400078ec  or      [rbx+4Ch], eax
0x1400078ef  mov     dword ptr [rbx+70h], 1
0x1400078f6  mov     rax, [rsi+78h]
0x1400078fa  mov     [rbx+78h], rax
0x1400078fe  mov     eax, [rsi+0A4h]
0x140007904  cmp     eax, 0FFFFFFFFh
0x140007907  jz      short loc_14000790F
0x140007909  mov     [rbx+0A4h], eax
0x14000790f  mov     eax, ebp
0x140007911  mov     [rbx+80h], rax
0x140007918  mov     rax, [rsi+88h]
0x14000791f  mov     [rbx+88h], rax
0x140007926  mov     eax, [rsi+90h]
0x14000792c  mov     [rbx+90h], eax
0x140007932  mov     [rbx+94h], r12d
0x140007939  mov     [rbx+98h], r15d
0x140007940  mov     byte ptr [rbx+0A8h], 4
0x140007947  movzx   eax, byte ptr [rsi+0AAh]
0x14000794e  mov     [rbx+0AAh], al
0x140007954  mov     [rbx+0F0h], rdi
0x14000795b  mov     rax, [rsi+8]
0x14000795f  mov     [rbx+8], rax
0x140007963  lea     rax, [rsi+28h]
0x140007967  mov     [rbx+10h], rsi
0x14000796b  add     rbx, 38h ; '8'
0x14000796f  cmp     ebp, r15d
0x140007972  jz      short loc_14000798D
0x140007974  mov     rcx, [rax]
0x140007977  cmp     [rcx+8], rax
0x14000797b  jnz     short loc_1400079D1
0x14000797d  mov     [rbx], rcx
0x140007980  mov     [rbx+8], rax
0x140007984  mov     [rcx+8], rbx
0x140007988  mov     [rax], rbx
0x14000798b  jmp     short loc_1400079A4
0x14000798d  mov     rcx, [rax+8]
0x140007991  cmp     [rcx], rax
0x140007994  jnz     short loc_1400079D1
0x140007996  mov     [rbx], rax
0x140007999  mov     [rbx+8], rcx
0x14000799d  mov     [rcx], rbx
0x1400079a0  mov     [rax+8], rbx
0x1400079a4  inc     dword ptr [rsi+48h]
0x1400079a7  test    rdx, rdx
0x1400079aa  jnz     short loc_1400079E7
0x1400079ac  inc     r15d
0x1400079af  jmp     loc_1400077BF
0x1400079b4  mov     rax, [rbx]
0x1400079b7  mov     edx, 1
0x1400079bc  mov     rcx, rbx
0x1400079bf  mov     rax, [rax]
0x1400079c2  call    _guard_dispatch_icall
0x1400079c7  jmp     short loc_1400079E7
0x1400079c9  mov     r14d, 0C000009Ah
  ... truncated ...
```
