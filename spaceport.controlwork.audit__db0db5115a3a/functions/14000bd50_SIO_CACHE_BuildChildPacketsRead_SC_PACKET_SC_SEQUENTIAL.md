# SIO_CACHE::BuildChildPacketsRead(SC_PACKET *,SC_SEQUENTIAL *)

- ea: `0x14000bd50`
- end: `0x14000bf95`
- name: `?BuildChildPacketsRead@SIO_CACHE@@IEAAJPEAVSC_PACKET@@PEAVSC_SEQUENTIAL@@@Z`
- size: `581`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, struct SC_PACKET *, struct SC_SEQUENTIAL *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14000dc60`

## callees

- `0x14000b170`
- `0x14000bd00`
- `0x14000bd50`
- `0x14000bfa0`
- `0x14000bff0`
- `0x14000c410`
- `0x1400154c0`
- `0x1400190f0`
- `0x14001b5a0`
- `0x140026b40`
- `0x14002f7e8`
- `0x140044f64`
- `0x140045d80`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000be6a`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000bf37`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000be6a`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14000bf37`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000bde9`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14000bde9`

## pseudocode

```c
__int64 __fastcall SIO_CACHE::BuildChildPacketsRead(
        volatile LONG *this,
        struct SC_PACKET *a2,
        struct SC_SEQUENTIAL *a3)
{
  __int64 v3; // r13
  __int64 v5; // rdx
  unsigned int v7; // esi
  unsigned __int64 v8; // r14
  int Space; // r12d
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  KIRQL v13; // r9
  unsigned __int64 v14; // rax
  __int64 v15; // r9
  int i; // r8d
  __int64 v17; // r9
  SIO_VDT *v18; // rcx
  char *v20; // r9
  char *j; // r15
  unsigned __int64 v22; // r8
  unsigned int v23; // ecx
  unsigned int v24; // edi
  SIO_CACHE_PACKET *v25; // rax
  SC_PACKET *v26; // rax
  SC_PACKET *v27; // rbx
  _QWORD v28[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v29; // [rsp+40h] [rbp-58h]
  __int64 v30; // [rsp+48h] [rbp-50h]
  __int64 v31; // [rsp+50h] [rbp-48h]
  unsigned __int64 v32; // [rsp+A8h] [rbp+10h]
  KIRQL v33; // [rsp+B0h] [rbp+18h]
  unsigned int SetRun; // [rsp+B0h] [rbp+18h]
  unsigned int v35; // [rsp+B8h] [rbp+20h]

  v3 = 0;
  v5 = *((_QWORD *)a2 + 17);
  v28[0] = 0;
  v7 = 0;
  v28[1] = 0;
  v8 = 0;
  Space = 0;
  v10 = v5 + *((unsigned int *)a2 + 36);
  v11 = v5 + *((_QWORD *)a2 + 24);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  while ( v11 < v10 )
  {
    v12 = *((unsigned int *)this + 118) - v11 % *((unsigned int *)this + 118);
    v32 = v11 % *((unsigned int *)this + 118);
    if ( v10 - v11 < v12 )
      LODWORD(v12) = v10 - v11;
    v35 = v12;
    v13 = ExAcquireSpinLockShared(this + 84);
    v33 = v13;
    v14 = v11 / *((unsigned int *)this + 118);
    if ( v14 < *((_QWORD *)this + 30) )
    {
      v15 = *((_QWORD *)this + 22);
      for ( i = *((_DWORD *)this + 62);
            ;
            v15 = *(_QWORD *)(v15 + 8 * ((unsigned int)(*((_DWORD *)this + 57) - 1) & (v14 >> i)) + 24) )
      {
        i -= *((_DWORD *)this + 58);
        if ( i <= 0 )
          break;
        if ( !v15 )
          goto LABEL_10;
      }
      if ( v15 )
        v3 = *(_QWORD *)(v15 + 8LL * ((unsigned int)v14 & (*((_DWORD *)this + 57) - 1)) + 24);
LABEL_10:
      v13 = v33;
    }
    if ( v3 && (*(_DWORD *)(v3 + 52) == 1 || !SIO_CACHE_STATE::AddRef((SIO_CACHE_STATE *)(v3 + 48), 0)) )
    {
      ExReleaseSpinLockShared(this + 84, v13);
    }
    else
    {
      ExReleaseSpinLockShared(this + 84, v13);
      if ( v3 )
      {
        SC_ITERATOR_BITMAP::Initialize(
          (SC_ITERATOR_BITMAP *)v28,
          (struct _RTL_BITMAP *)(v3 + 72),
          v32,
          v35,
          *((unsigned int *)this + 26));
        while ( 1 )
        {
          if ( SC_ITERATOR_BITMAP::IsComplete((SC_ITERATOR_BITMAP *)v28) )
          {
            SIO_CACHE_STATE::DecRef((SIO_CACHE_STATE *)(v3 + 48));
            v17 = v35;
            goto LABEL_16;
          }
          SetRun = SC_ITERATOR_BITMAP::GetSetRun((SC_ITERATOR_BITMAP *)v28);
          if ( SetRun )
          {
            if ( v7 )
            {
              Space = SIO_CACHE::BuildChildPacketsReadSpace((SIO_CACHE *)this, a2, v8, v7);
              if ( Space < 0 )
                goto LABEL_44;
              v8 = 0;
              v7 = 0;
            }
            Space = SIO_CACHE::BuildChildPacketsReadCache(
                      (SIO_CACHE *)this,
                      a2,
                      v32 + *(_QWORD *)(v3 + 32),
                      (struct SIO_CACHE_LINE *)v3,
                      v32,
                      SetRun);
            if ( Space < 0 )
            {
LABEL_44:
              SIO_CACHE_STATE::DecRef((SIO_CACHE_STATE *)(v3 + 48));
              goto LABEL_28;
            }
            SIO_CACHE_STATE::AddRef((SIO_CACHE_STATE *)(v3 + 48), 0);
            v22 = SetRun + v32;
            v32 = v22;
          }
          else
          {
            v22 = v32;
          }
          v23 = HIDWORD(v29) * v31;
          if ( HIDWORD(v29) * (_DWORD)v31 )
          {
            if ( !v7 )
              v8 = v22 + *(_QWORD *)(v3 + 32);
            v7 += v23;
            v32 = v23 + v22;
          }
          LODWORD(v30) = HIDWORD(v29) + HIDWORD(v30) + v30;
        }
      }
    }
    v17 = v35;
    if ( !v7 )
      v8 = v11;
    v7 += v35;
LABEL_16:
    v11 += v17;
    v3 = 0;
  }
  if ( v7 )
  {
    v18 = *(SIO_VDT **)(*((_QWORD *)this + 1) + 128LL);
    if ( v18 )
    {
      Space = SIO_VDT::BuildChildPacketsRead(v18, a2, v8, v7);
    }
    else
    {
      v24 = v8 - *((_DWORD *)a2 + 34);
      v25 = (SIO_CACHE_PACKET *)SC_PACKET::operator new(0x128u, *((struct SC_PACKET **)a2 + 1));
      if ( v25 && (v26 = SIO_CACHE_PACKET::SIO_CACHE_PACKET(v25), (v27 = v26) != 0) )
      {
        Space = SC_PACKET::Split(v26, a2, v24, v7, 0);
        if ( Space < 0 )
        {
          (**(void (__fastcall ***)(SC_PACKET *, __int64))v27)(v27, 1);
        }
        else
        {
          *((_QWORD *)v27 + 17) = v8;
          *((_DWORD *)v27 + 36) = v7;
          *((_DWORD *)v27 + 38) = *((_DWORD *)a2 + 38);
          *((_BYTE *)v27 + 168) = 3;
          *((_BYTE *)v27 + 170) = 1;
          *((_QWORD *)v27 + 30) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 80LL))(*((_QWORD *)this + 1));
          SC_PACKET::Attach(a2, v27, 0);
        }
      }
      else
      {
        Space = -1073741670;
      }
    }
  }
  if ( Space < 0 )
  {
LABEL_28:
    v20 = (char *)*((_QWORD *)a2 + 5);
    for ( j = (char *)a2 + 40; v20 != j; v20 = *(char **)v20 )
    {
      if ( v20[114] == 22 )
        SIO_CACHE_STATE::DecRef((SIO_CACHE_STATE *)(*((_QWORD *)v20 + 9) + 48LL));
    }
  }
  return (unsigned int)Space;
}

```

## disassembly

```asm
0x14000bd50  mov     rax, rsp
0x14000bd53  mov     [rax+8], rbx
0x14000bd57  mov     [rax+18h], r8
0x14000bd5b  push    rbp
0x14000bd5c  push    rsi
0x14000bd5d  push    rdi
0x14000bd5e  push    r12
0x14000bd60  push    r13
0x14000bd62  push    r14
0x14000bd64  push    r15
0x14000bd66  sub     rsp, 60h
0x14000bd6a  xor     r13d, r13d
0x14000bd6d  mov     r15, rdx
0x14000bd70  mov     rdx, [rdx+88h]
0x14000bd77  mov     rbp, rcx
0x14000bd7a  mov     [rax-68h], r13
0x14000bd7e  mov     esi, r13d
0x14000bd81  mov     [rax-60h], r13
0x14000bd85  mov     r14d, r13d
0x14000bd88  mov     edi, [r15+90h]
0x14000bd8f  mov     r12d, r13d
0x14000bd92  mov     rbx, [r15+0C0h]
0x14000bd99  add     rdi, rdx
0x14000bd9c  add     rbx, rdx
0x14000bd9f  mov     [rax-58h], r13
0x14000bda3  mov     [rax-50h], r13
0x14000bda7  mov     [rax-48h], r13
0x14000bdab  cmp     rbx, rdi
0x14000bdae  jnb     loc_14000BE9D
0x14000bdb4  mov     ecx, [rbp+1D8h]
0x14000bdba  xor     edx, edx
0x14000bdbc  mov     rax, rbx
0x14000bdbf  div     rcx
0x14000bdc2  mov     rax, rdi
0x14000bdc5  sub     rcx, rdx
0x14000bdc8  mov     [rsp+98h+arg_8], rdx
0x14000bdd0  sub     rax, rbx
0x14000bdd3  cmp     rax, rcx
0x14000bdd6  cmovb   rcx, rax
0x14000bdda  mov     [rsp+98h+arg_18], rcx
0x14000bde2  lea     rcx, [rbp+150h]; SpinLock
0x14000bde9  call    cs:__imp_ExAcquireSpinLockShared
0x14000bdf0  nop     dword ptr [rax+rax+00h]
0x14000bdf5  mov     ecx, [rbp+1D8h]
0x14000bdfb  xor     edx, edx
0x14000bdfd  movzx   r9d, al
0x14000be01  mov     byte ptr [rsp+98h+arg_10], al
0x14000be08  mov     rax, rbx
0x14000be0b  div     rcx
0x14000be0e  cmp     rax, [rbp+0F0h]
0x14000be15  jnb     short loc_14000BE56
0x14000be17  mov     r9, [rbp+0B0h]
0x14000be1e  mov     r10d, [rbp+0E8h]
0x14000be25  mov     r8d, [rbp+0F8h]
0x14000be2c  sub     r8d, r10d
0x14000be2f  test    r8d, r8d
0x14000be32  jg      loc_14000BEEB
0x14000be38  test    r9, r9
0x14000be3b  jz      short loc_14000BE4D
0x14000be3d  mov     ecx, [rbp+0E4h]
0x14000be43  dec     ecx
0x14000be45  and     rcx, rax
0x14000be48  mov     r13, [r9+rcx*8+18h]
0x14000be4d  movzx   r9d, byte ptr [rsp+98h+arg_10]
0x14000be56  test    r13, r13
0x14000be59  jnz     loc_14000BF12
0x14000be5f  movzx   edx, r9b; OldIrql
0x14000be63  lea     rcx, [rbp+150h]; SpinLock
0x14000be6a  call    cs:__imp_ExReleaseSpinLockShared
0x14000be71  nop     dword ptr [rax+rax+00h]
0x14000be76  test    r13, r13
0x14000be79  jnz     loc_14000BF48
0x14000be7f  mov     rax, [rsp+98h+arg_18]
0x14000be87  test    esi, esi
0x14000be89  mov     r9d, eax
0x14000be8c  cmovz   r14, rbx
0x14000be90  add     esi, eax
0x14000be92  add     rbx, r9
0x14000be95  xor     r13d, r13d
0x14000be98  jmp     loc_14000BDAB
0x14000be9d  test    esi, esi
0x14000be9f  jz      short loc_14000BEC6
0x14000bea1  mov     rax, [rbp+8]
0x14000bea5  mov     rcx, [rax+80h]; this
0x14000beac  test    rcx, rcx
0x14000beaf  jz      loc_1400690B2
0x14000beb5  mov     r9d, esi; unsigned int
0x14000beb8  mov     r8, r14; unsigned __int64
0x14000bebb  mov     rdx, r15; struct SC_PACKET *
0x14000bebe  call    ?BuildChildPacketsRead@SIO_VDT@@QEAAJPEAVSC_PACKET@@_KK@Z; SIO_VDT::BuildChildPacketsRead(SC_PACKET *,unsigned __int64,ulong)
0x14000bec3  mov     r12d, eax
0x14000bec6  test    r12d, r12d
0x14000bec9  js      loc_14000BF7F
0x14000becf  mov     rbx, [rsp+98h+arg_0]
0x14000bed7  mov     eax, r12d
0x14000beda  add     rsp, 60h
0x14000bede  pop     r15
0x14000bee0  pop     r14
0x14000bee2  pop     r13
0x14000bee4  pop     r12
0x14000bee6  pop     rdi
0x14000bee7  pop     rsi
0x14000bee8  pop     rbp
0x14000bee9  retn
0x14000beeb  test    r9, r9
0x14000beee  jz      loc_14000BE4D
0x14000bef4  mov     ecx, r8d
0x14000bef7  mov     rdx, rax
0x14000befa  shr     rdx, cl
0x14000befd  mov     ecx, [rbp+0E4h]
0x14000bf03  dec     ecx
0x14000bf05  and     rdx, rcx
0x14000bf08  mov     r9, [r9+rdx*8+18h]
0x14000bf0d  jmp     loc_14000BE2C
0x14000bf12  cmp     dword ptr [r13+34h], 1
0x14000bf17  jz      short loc_14000BF2C
0x14000bf19  lea     rcx, [r13+30h]; this
0x14000bf1d  xor     edx, edx; unsigned __int8
0x14000bf1f  call    ?AddRef@SIO_CACHE_STATE@@QEAAEE@Z; SIO_CACHE_STATE::AddRef(uchar)
0x14000bf24  test    al, al
0x14000bf26  jnz     loc_14000BE5F
0x14000bf2c  movzx   edx, r9b; OldIrql
0x14000bf30  lea     rcx, [rbp+150h]; SpinLock
0x14000bf37  call    cs:__imp_ExReleaseSpinLockShared
0x14000bf3e  nop     dword ptr [rax+rax+00h]
0x14000bf43  jmp     loc_14000BE7F
0x14000bf48  mov     r9, [rsp+98h+arg_18]
0x14000bf50  lea     rdx, [r13+48h]; struct _RTL_BITMAP *
0x14000bf54  mov     eax, [rbp+68h]
0x14000bf57  lea     rcx, [rsp+98h+var_68]; this
0x14000bf5c  mov     r8, [rsp+98h+arg_8]; unsigned __int64
0x14000bf64  mov     r9d, r9d; unsigned __int64
0x14000bf67  mov     [rsp+98h+arg_18], r9
0x14000bf6f  mov     qword ptr [rsp+98h+var_78], rax; unsigned __int64
0x14000bf74  call    ?Initialize@SC_ITERATOR_BITMAP@@QEAAXPEAU_RTL_BITMAP@@_K11@Z; SC_ITERATOR_BITMAP::Initialize(_RTL_BITMAP *,unsigned __int64,unsigned __int64,unsigned __int64)
0x14000bf79  nop
0x14000bf7a  jmp     loc_140068FA0
0x14000bf7f  mov     r9, [r15+28h]
0x14000bf83  add     r15, 28h ; '('
0x14000bf87  cmp     r9, r15
0x14000bf8a  jz      loc_14000BECF
0x14000bf90  jmp     loc_14006917B
0x140068fa0  lea     rcx, [rsp+98h+var_68]; this
0x140068fa5  call    ?IsComplete@SC_ITERATOR_BITMAP@@QEAAEXZ; SC_ITERATOR_BITMAP::IsComplete(void)
0x140068faa  test    al, al
0x140068fac  jnz     loc_14006908D
0x140068fb2  lea     rcx, [rsp+98h+var_68]; this
0x140068fb7  call    ?GetSetRun@SC_ITERATOR_BITMAP@@QEAA_KXZ; SC_ITERATOR_BITMAP::GetSetRun(void)
0x140068fbc  mov     qword ptr [rsp+98h+arg_10], rax
0x140068fc4  test    eax, eax
0x140068fc6  jz      loc_14006904D
0x140068fcc  test    esi, esi
0x140068fce  jz      short loc_140068FF1
0x140068fd0  mov     r9d, esi; unsigned int
0x140068fd3  mov     r8, r14; unsigned __int64
0x140068fd6  mov     rdx, r15; struct SC_PACKET *
0x140068fd9  mov     rcx, rbp; this
0x140068fdc  call    ?BuildChildPacketsReadSpace@SIO_CACHE@@IEAAJPEAVSC_PACKET@@_KK@Z; SIO_CACHE::BuildChildPacketsReadSpace(SC_PACKET *,unsigned __int64,ulong)
0x140068fe1  mov     r12d, eax
0x140068fe4  test    eax, eax
0x140068fe6  js      loc_1400690A3
0x140068fec  xor     r14d, r14d
0x140068fef  xor     esi, esi
0x140068ff1  mov     rcx, [rsp+98h+arg_8]
0x140068ff9  mov     r9, r13; struct SIO_CACHE_LINE *
0x140068ffc  mov     rax, qword ptr [rsp+98h+arg_10]
0x140069004  mov     rdx, r15; struct SC_PACKET *
0x140069007  mov     r8, [r13+20h]
0x14006900b  mov     [rsp+98h+var_70], eax; unsigned int
0x14006900f  add     r8, rcx; unsigned __int64
0x140069012  mov     qword ptr [rsp+98h+var_78], rcx; unsigned __int64
0x140069017  mov     rcx, rbp; this
0x14006901a  call    ?BuildChildPacketsReadCache@SIO_CACHE@@IEAAJPEAVSC_PACKET@@_KPEAVSIO_CACHE_LINE@@1K@Z; SIO_CACHE::BuildChildPacketsReadCache(SC_PACKET *,unsigned __int64,SIO_CACHE_LINE *,unsigned __int64,ulong)
0x14006901f  mov     r12d, eax
0x140069022  test    eax, eax
0x140069024  js      short loc_1400690A3
0x140069026  lea     rcx, [r13+30h]; this
0x14006902a  xor     edx, edx; unsigned __int8
0x14006902c  call    ?AddRef@SIO_CACHE_STATE@@QEAAEE@Z; SIO_CACHE_STATE::AddRef(uchar)
0x140069031  mov     r8, [rsp+98h+arg_8]
0x140069039  mov     ecx, [rsp+98h+arg_10]
0x140069040  add     r8, rcx
0x140069043  mov     [rsp+98h+arg_8], r8
0x14006904b  jmp     short loc_140069055
0x14006904d  mov     r8, [rsp+98h+arg_8]
0x140069055  mov     ecx, dword ptr [rsp+98h+var_48]
0x140069059  mov     edx, [rsp+98h+var_54]
0x14006905d  imul    ecx, edx
0x140069060  test    ecx, ecx
0x140069062  jz      short loc_14006907E
0x140069064  test    esi, esi
0x140069066  jnz     short loc_14006906F
0x140069068  mov     r14, [r13+20h]
0x14006906c  add     r14, r8
0x14006906f  add     esi, ecx
0x140069071  mov     eax, ecx
0x140069073  add     r8, rax
0x140069076  mov     [rsp+98h+arg_8], r8
0x14006907e  mov     ecx, [rsp+98h+var_4C]
0x140069082  add     ecx, edx
0x140069084  add     [rsp+98h+var_50], ecx
0x140069088  jmp     loc_140068FA0
0x14006908d  lea     rcx, [r13+30h]; this
0x140069091  call    ?DecRef@SIO_CACHE_STATE@@QEAAXXZ; SIO_CACHE_STATE::DecRef(void)
0x140069096  mov     r9, [rsp+98h+arg_18]
0x14006909e  jmp     loc_14000BE92
0x1400690a3  lea     rcx, [r13+30h]; this
0x1400690a7  call    ?DecRef@SIO_CACHE_STATE@@QEAAXXZ; SIO_CACHE_STATE::DecRef(void)
0x1400690ac  nop
0x1400690ad  jmp     loc_14000BF7F
0x1400690b2  mov     rdx, [r15+8]; struct SC_PACKET *
0x1400690b6  mov     edi, r14d
0x1400690b9  sub     edi, [r15+88h]
0x1400690c0  mov     ecx, 128h; unsigned __int64
0x1400690c5  call    ??2SC_PACKET@@SAPEAX_KPEAV0@@Z; SC_PACKET::operator new(unsigned __int64,SC_PACKET *)
0x1400690ca  test    rax, rax
0x1400690cd  jz      loc_140069170
0x1400690d3  mov     rcx, rax; this
0x1400690d6  call    ??0SIO_CACHE_PACKET@@QEAA@XZ; SIO_CACHE_PACKET::SIO_CACHE_PACKET(void)
0x1400690db  mov     rbx, rax
0x1400690de  test    rax, rax
0x1400690e1  jz      loc_140069170
0x1400690e7  mov     r9d, esi; unsigned int
0x1400690ea  mov     [rsp+98h+var_78], 0; unsigned __int8
0x1400690ef  mov     r8d, edi; unsigned int
0x1400690f2  mov     rdx, r15; struct SC_PACKET *
0x1400690f5  mov     rcx, rax; this
0x1400690f8  call    ?Split@SC_PACKET@@QEAAJPEAV1@KKE@Z; SC_PACKET::Split(SC_PACKET *,ulong,ulong,uchar)
0x1400690fd  mov     r12d, eax
0x140069100  test    eax, eax
0x140069102  js      short loc_140069157
0x140069104  mov     [rbx+88h], r14
0x14006910b  mov     [rbx+90h], esi
0x140069111  mov     eax, [r15+98h]
0x140069118  mov     [rbx+98h], eax
0x14006911e  mov     byte ptr [rbx+0A8h], 3
0x140069125  mov     byte ptr [rbx+0AAh], 1
0x14006912c  mov     rcx, [rbp+8]
0x140069130  mov     rax, [rcx]
0x140069133  mov     rax, [rax+50h]
0x140069137  call    _guard_dispatch_icall
0x14006913c  xor     r8d, r8d; unsigned __int8
0x14006913f  mov     [rbx+0F0h], rax
0x140069146  mov     rdx, rbx; struct SC_PACKET *
0x140069149  mov     rcx, r15; this
0x14006914c  call    ?Attach@SC_PACKET@@QEAAXPEAV1@E@Z; SC_PACKET::Attach(SC_PACKET *,uchar)
0x140069151  nop
0x140069152  jmp     loc_14000BEC6
0x140069157  mov     rax, [rbx]
0x14006915a  mov     edx, 1
0x14006915f  mov     rcx, rbx
0x140069162  mov     rax, [rax]
0x140069165  call    _guard_dispatch_icall
0x14006916a  nop
0x14006916b  jmp     loc_14000BEC6
0x140069170  mov     r12d, 0C000009Ah
0x140069176  jmp     loc_14000BEC6
0x14006917b  cmp     byte ptr [r9+72h], 16h
0x140069180  jnz     short loc_14006918F
0x140069182  mov     rcx, [r9+48h]
0x140069186  add     rcx, 30h ; '0'; this
0x14006918a  call    ?DecRef@SIO_CACHE_STATE@@QEAAXXZ; SIO_CACHE_STATE::DecRef(void)
0x14006918f  mov     r9, [r9]
0x140069192  cmp     r9, r15
0x140069195  jnz     short loc_14006917B
0x140069197  jmp     loc_14000BECF
```
