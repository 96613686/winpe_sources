# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008e44`
- end: `0x1800091f5`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `945`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008ccc`

## callees

- `0x180005d30`
- `0x1800087e4`
- `0x180008e44`
- `0x18000b708`
- `0x18000d6c6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008f56`
- `msvcrt!memcpy_s` at `0x180008ff5`
- `msvcrt!memcpy_s` at `0x1800091ab`
- `msvcrt!memcpy_s` at `0x180008f56`
- `msvcrt!memcpy_s` at `0x180008ff5`
- `msvcrt!memcpy_s` at `0x1800091ab`
- `msvcrt!memmove_s` at `0x180009136`
- `msvcrt!memmove_s` at `0x180009136`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        size_t a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v11; // r8
  unsigned __int8 *v12; // rdi
  char v13; // al
  bool v14; // al
  size_t v15; // r12
  int v16; // ecx
  unsigned __int64 v17; // rax
  unsigned int v18; // edx
  rsize_t v19; // r9
  unsigned int *p_Source; // r8
  unsigned int v21; // esi
  unsigned int v22; // eax
  bool v23; // zf
  rsize_t v24; // r9
  unsigned int *v25; // r8
  rsize_t v26; // rdx
  unsigned __int8 *v27; // r8
  bool v28; // si
  __int64 v29; // rcx
  __int64 v31; // rax
  char v32; // dl
  unsigned __int64 v33; // rdx
  __int64 v34; // rsi
  unsigned __int64 v35; // r9
  unsigned __int8 *v36; // r8
  __int16 v37; // r8
  rsize_t v38; // r9
  rsize_t v39; // rdx
  unsigned int *v40; // r8
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 v42; // [rsp+40h] [rbp-41h] BYREF
  char v43; // [rsp+42h] [rbp-3Fh]
  unsigned int Source; // [rsp+44h] [rbp-3Dh] BYREF
  unsigned __int16 v45; // [rsp+48h] [rbp-39h]
  void *Buf2[2]; // [rsp+50h] [rbp-31h]
  __int16 v47; // [rsp+60h] [rbp-21h] BYREF
  __int16 v48; // [rsp+64h] [rbp-1Dh] BYREF
  __int16 v49; // [rsp+68h] [rbp-19h] BYREF
  char v50; // [rsp+6Ah] [rbp-17h]
  unsigned int v51; // [rsp+6Ch] [rbp-15h]
  __int16 v52; // [rsp+70h] [rbp-11h]
  __int64 v53; // [rsp+78h] [rbp-9h]
  void *v54; // [rsp+80h] [rbp-1h]
  __int16 v55; // [rsp+88h] [rbp+7h] BYREF
  char v56; // [rsp+8Ah] [rbp+9h]
  int v57; // [rsp+8Ch] [rbp+Bh]
  __int16 v58; // [rsp+90h] [rbp+Fh]
  __int128 v59; // [rsp+98h] [rbp+17h]
  __int16 v60; // [rsp+D8h] [rbp+57h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v11 = (unsigned __int8 *)*((_QWORD *)this + 4);
  v12 = (unsigned __int8 *)(v6 + 10);
  v42 = *((_WORD *)this + 1);
  v13 = *((_BYTE *)this + 4);
  Source = 0;
  v45 = 0;
  LOBYTE(v60) = 0;
  v43 = v13;
  InsertionPointOrIncrement = v12;
  *(_OWORD *)Buf2 = 0;
  v14 = wil::details_abi::UsageIndexProperty::Read(
          (wil::details_abi::UsageIndexProperty *)&v42,
          &InsertionPointOrIncrement,
          v11);
  v15 = a5;
  while ( 1 )
  {
    v28 = v14;
    if ( !v14 )
    {
      v12 = InsertionPointOrIncrement;
      goto LABEL_30;
    }
    v16 = Size == v45 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v45;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v42,
                                    InsertionPointOrIncrement,
                                    a4,
                                    v15,
                                    a6);
      v12 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        LOBYTE(v60) = 1;
        goto LABEL_38;
      }
      return 1;
    }
    v12 = InsertionPointOrIncrement;
    if ( *((_QWORD *)this + 2) )
    {
      v17 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v18 = Source;
      if ( Source > v17 && Source != (_DWORD)v17 )
      {
        v18 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v18;
        if ( v43 == 1 )
        {
          v47 = v17;
          v19 = 2;
          p_Source = (unsigned int *)&v47;
          goto LABEL_15;
        }
        if ( v43 == 2 )
        {
          v19 = 4;
          p_Source = &Source;
LABEL_15:
          memcpy_s(Buf2[0], v19, p_Source, v19);
          v18 = Source;
        }
      }
      v12 += *((_QWORD *)this + 2) * v18;
      goto LABEL_27;
    }
    v55 = *((_WORD *)this + 3);
    v21 = 0;
    v56 = *((_BYTE *)this + 8);
    v22 = Source;
    v57 = 0;
    v58 = 0;
    v59 = 0;
    if ( Source )
    {
      do
      {
        v23 = !wil::details_abi::UsageIndexProperty::Read(
                 (wil::details_abi::UsageIndexProperty *)&v55,
                 &InsertionPointOrIncrement,
                 *((unsigned __int8 **)this + 4));
        v22 = Source;
        if ( v23 )
          break;
        ++v21;
      }
      while ( v21 < Source );
      v12 = InsertionPointOrIncrement;
    }
    if ( v22 != v21 )
    {
      Source = v21;
      if ( v43 == 1 )
      {
        v48 = v21;
        v24 = 2;
        v25 = (unsigned int *)&v48;
        v26 = 2;
      }
      else
      {
        if ( v43 != 2 )
          goto LABEL_27;
        v26 = 4;
        v25 = &Source;
        v24 = 4;
      }
      memcpy_s(Buf2[0], v26, v25, v24);
    }
LABEL_27:
    v27 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v12;
    v14 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v42,
            &InsertionPointOrIncrement,
            v27);
  }
  InsertionPointOrIncrement = v12;
LABEL_38:
  if ( !v28 )
LABEL_30:
    *((_QWORD *)this + 4) = v12;
  v29 = 0;
  if ( !(_BYTE)v60 )
  {
    Source = 1;
    v45 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v42 )
      v29 = v42;
    else
      v29 = (unsigned __int16)Size + 2LL;
    if ( v43 == 1 )
    {
      v29 += 2;
    }
    else if ( v43 == 2 )
    {
      v29 += 4;
    }
  }
  v31 = *((unsigned __int16 *)this + 3);
  v32 = *((_BYTE *)this + 8);
  v49 = v31;
  v50 = v32;
  v51 = a6;
  v52 = v15;
  v53 = 0;
  v54 = a4;
  if ( !(_WORD)v31 )
    v31 = (unsigned __int16)v15 + 2LL;
  if ( v32 == 1 )
  {
    v31 += 2;
  }
  else if ( v32 == 2 )
  {
    v31 += 4;
  }
  v33 = *((_QWORD *)this + 5);
  v34 = v31 + v29;
  v35 = *((_QWORD *)this + 4);
  if ( ((v33 - v35) & -(__int64)(v35 < v33)) >= v31 + v29 )
  {
    memmove_s(&v12[v34], v33 - v34 - (_QWORD)v12, v12, v35 - (_QWORD)v12);
    v36 = (unsigned __int8 *)(v34 + *((_QWORD *)this + 4));
    *((_QWORD *)this + 4) = v36;
    if ( !(_BYTE)v60 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v42,
        &InsertionPointOrIncrement,
        v36);
LABEL_61:
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v49,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
    if ( !v43 )
      goto LABEL_61;
    v37 = Source + 1;
    if ( Source == Source + 1 )
      goto LABEL_61;
    ++Source;
    if ( v43 == 1 )
    {
      v38 = 2;
      v60 = v37;
      v39 = 2;
      v40 = (unsigned int *)&v60;
    }
    else
    {
      if ( v43 != 2 )
        goto LABEL_61;
      v40 = &Source;
      v38 = 4;
      v39 = 4;
    }
    memcpy_s(Buf2[0], v39, v40, v38);
    goto LABEL_61;
  }
  return 0;
}

```

## disassembly

```asm
0x180008e44  mov     rax, rsp
0x180008e47  mov     [rax+10h], rbx
0x180008e4b  mov     [rax+18h], rsi
0x180008e4f  mov     [rax+20h], rdi
0x180008e53  push    rbp
0x180008e54  push    r12
0x180008e56  push    r13
0x180008e58  push    r14
0x180008e5a  push    r15
0x180008e5c  lea     rbp, [rax-4Fh]
0x180008e60  sub     rsp, 0A0h
0x180008e67  mov     rdi, [rcx+18h]
0x180008e6b  mov     rbx, rcx
0x180008e6e  xor     ecx, ecx
0x180008e70  mov     r13, r9
0x180008e73  mov     r14, r8
0x180008e76  mov     r15, rdx
0x180008e79  test    rdi, rdi
0x180008e7c  jz      loc_1800091D1
0x180008e82  movzx   eax, word ptr [rbx+2]
0x180008e86  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180008e8a  mov     r8, [rbx+20h]; unsigned __int8 *
0x180008e8e  add     rdi, 0Ah
0x180008e92  mov     [rbp+47h+var_88], ax
0x180008e96  xorps   xmm0, xmm0
0x180008e99  mov     al, [rbx+4]
0x180008e9c  mov     [rbp+47h+Source], ecx
0x180008e9f  mov     [rbp+47h+var_80], cx
0x180008ea3  mov     byte ptr [rbp+47h+arg_0], cl
0x180008ea6  lea     rcx, [rbp+47h+var_88]; this
0x180008eaa  mov     [rbp+47h+var_86], al
0x180008ead  mov     [rbp+47h+var_90], rdi
0x180008eb1  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180008eb6  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008ebb  mov     r12, [rbp+47h+arg_20]
0x180008ebf  jmp     loc_180009016
0x180008ec4  movzx   ecx, [rbp+47h+var_80]
0x180008ec8  cmp     r14, rcx
0x180008ecb  jnz     short loc_180008EE3
0x180008ecd  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180008ed1  mov     r8, r14; Size
0x180008ed4  mov     rcx, r15; Buf1
0x180008ed7  call    memcmp_0
0x180008edc  mov     ecx, eax
0x180008ede  xor     r9d, r9d
0x180008ee1  jmp     short loc_180008EEC
0x180008ee3  movzx   eax, [rbp+47h+var_80]
0x180008ee7  mov     ecx, r14d
0x180008eea  sub     ecx, eax
0x180008eec  test    ecx, ecx
0x180008eee  js      loc_18000909B
0x180008ef4  jz      loc_180009060
0x180008efa  mov     rdi, [rbp+47h+var_90]
0x180008efe  mov     [rbp+47h+var_90], rdi
0x180008f02  cmp     [rbx+10h], r9
0x180008f06  jbe     short loc_180008F74
0x180008f08  mov     rax, [rbx+20h]
0x180008f0c  xor     edx, edx
0x180008f0e  sub     rax, [rbx+18h]
0x180008f12  div     qword ptr [rbx+10h]
0x180008f16  mov     edx, [rbp+47h+Source]
0x180008f19  cmp     rdx, rax
0x180008f1c  jbe     short loc_180008F65
0x180008f1e  cmp     edx, eax
0x180008f20  jz      short loc_180008F65
0x180008f22  mov     edx, eax
0x180008f24  mov     [rbp+47h+Source], eax
0x180008f27  mov     al, [rbp+47h+var_86]
0x180008f2a  cmp     al, 1
0x180008f2c  jnz     short loc_180008F41
0x180008f2e  movzx   eax, dx
0x180008f31  mov     [rbp+47h+var_68], dx
0x180008f35  mov     r9d, 2
0x180008f3b  lea     r8, [rbp+47h+var_68]
0x180008f3f  jmp     short loc_180008F4F
0x180008f41  cmp     al, 2
0x180008f43  jnz     short loc_180008F65
0x180008f45  mov     r9d, 4; SourceSize
0x180008f4b  lea     r8, [rbp+47h+Source]; Source
0x180008f4f  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008f53  mov     rdx, r9; DestinationSize
0x180008f56  call    cs:__imp_memcpy_s
0x180008f5d  nop     dword ptr [rax+rax+00h]
0x180008f62  mov     edx, [rbp+47h+Source]
0x180008f65  mov     eax, edx
0x180008f67  imul    rax, [rbx+10h]
0x180008f6c  add     rdi, rax
0x180008f6f  jmp     loc_180009001
0x180008f74  movzx   eax, word ptr [rbx+6]
0x180008f78  xorps   xmm0, xmm0
0x180008f7b  mov     [rbp+47h+var_40], ax
0x180008f7f  mov     esi, r9d
0x180008f82  mov     al, [rbx+8]
0x180008f85  mov     [rbp+47h+var_3E], al
0x180008f88  mov     eax, [rbp+47h+Source]
0x180008f8b  mov     [rbp+47h+var_3C], r9d
0x180008f8f  mov     [rbp+47h+var_38], r9w
0x180008f94  movdqu  [rbp+47h+var_30], xmm0
0x180008f99  test    eax, eax
0x180008f9b  jz      short loc_180008FBF
0x180008f9d  mov     r8, [rbx+20h]; unsigned __int8 *
0x180008fa1  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180008fa5  lea     rcx, [rbp+47h+var_40]; this
0x180008fa9  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008fae  test    al, al
0x180008fb0  mov     eax, [rbp+47h+Source]
0x180008fb3  jz      short loc_180008FBB
0x180008fb5  inc     esi
0x180008fb7  cmp     esi, eax
0x180008fb9  jb      short loc_180008F9D
0x180008fbb  mov     rdi, [rbp+47h+var_90]
0x180008fbf  cmp     eax, esi
0x180008fc1  jz      short loc_180009001
0x180008fc3  mov     al, [rbp+47h+var_86]
0x180008fc6  mov     [rbp+47h+Source], esi
0x180008fc9  cmp     al, 1
0x180008fcb  jnz     short loc_180008FE1
0x180008fcd  mov     eax, 2
0x180008fd2  mov     [rbp+47h+var_64], si
0x180008fd6  mov     r9d, eax
0x180008fd9  lea     r8, [rbp+47h+var_64]
0x180008fdd  mov     edx, eax
0x180008fdf  jmp     short loc_180008FF1
0x180008fe1  cmp     al, 2
0x180008fe3  jnz     short loc_180009001
0x180008fe5  mov     edx, 4; DestinationSize
0x180008fea  lea     r8, [rbp+47h+Source]; Source
0x180008fee  mov     r9d, edx; SourceSize
0x180008ff1  mov     rcx, [rbp+47h+Buf2]; Destination
0x180008ff5  call    cs:__imp_memcpy_s
0x180008ffc  nop     dword ptr [rax+rax+00h]
0x180009001  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009005  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180009009  lea     rcx, [rbp+47h+var_88]; this
0x18000900d  mov     [rbp+47h+var_90], rdi
0x180009011  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009016  xor     r9d, r9d
0x180009019  mov     sil, al
0x18000901c  test    al, al
0x18000901e  jnz     loc_180008EC4
0x180009024  mov     rdi, [rbp+47h+var_90]
0x180009028  mov     [rbx+20h], rdi
0x18000902c  mov     rcx, r9
0x18000902f  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180009033  jnz     loc_1800090BE
0x180009039  movzx   eax, [rbp+47h+var_88]
0x18000903d  mov     [rbp+47h+Source], 1
0x180009044  mov     [rbp+47h+var_80], r14w
0x180009049  mov     [rbp+47h+Buf2], r9
0x18000904d  mov     [rbp+47h+Buf2+8], r15
0x180009051  test    ax, ax
0x180009054  jnz     short loc_1800090A6
0x180009056  movzx   ecx, r14w
0x18000905a  add     rcx, 2
0x18000905e  jmp     short loc_1800090A9
0x180009060  mov     eax, [rbp+47h+arg_28]
0x180009063  lea     rdx, [rbp+47h+var_88]; struct wil::details_abi::UsageIndexProperty *
0x180009067  mov     r8, [rbp+47h+var_90]; unsigned __int8 *
0x18000906b  mov     r9, r13; void *
0x18000906e  mov     [rsp+0C0h+var_98], eax; unsigned int
0x180009072  mov     rcx, rbx; this
0x180009075  mov     [rsp+0C0h+Size], r12; Size
0x18000907a  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000907f  xor     r9d, r9d
0x180009082  mov     [rbp+47h+var_90], rax
0x180009086  mov     rdi, rax
0x180009089  test    rax, rax
0x18000908c  jnz     short loc_180009095
0x18000908e  mov     al, 1
0x180009090  jmp     loc_1800091D3
0x180009095  mov     byte ptr [rbp+47h+arg_0], 1
0x180009099  jmp     short loc_18000909F
0x18000909b  mov     [rbp+47h+var_90], rdi
0x18000909f  test    sil, sil
0x1800090a2  jnz     short loc_18000902C
0x1800090a4  jmp     short loc_180009028
0x1800090a6  mov     rcx, rax
0x1800090a9  mov     al, [rbp+47h+var_86]
0x1800090ac  cmp     al, 1
0x1800090ae  jnz     short loc_1800090B6
0x1800090b0  add     rcx, 2
0x1800090b4  jmp     short loc_1800090BE
0x1800090b6  cmp     al, 2
0x1800090b8  jnz     short loc_1800090BE
0x1800090ba  add     rcx, 4
0x1800090be  movzx   eax, word ptr [rbx+6]
0x1800090c2  mov     dl, [rbx+8]
0x1800090c5  mov     r8d, [rbp+47h+arg_28]
0x1800090c9  mov     [rbp+47h+var_60], ax
0x1800090cd  mov     [rbp+47h+var_5E], dl
0x1800090d0  mov     [rbp+47h+var_5C], r8d
0x1800090d4  mov     [rbp+47h+var_58], r12w
0x1800090d9  mov     [rbp+47h+var_50], r9
0x1800090dd  mov     [rbp+47h+var_48], r13
0x1800090e1  test    ax, ax
0x1800090e4  jnz     short loc_1800090EE
0x1800090e6  movzx   eax, r12w
0x1800090ea  add     rax, 2
0x1800090ee  cmp     dl, 1
0x1800090f1  jnz     short loc_1800090F9
0x1800090f3  add     rax, 2
0x1800090f7  jmp     short loc_180009102
0x1800090f9  cmp     dl, 2
0x1800090fc  jnz     short loc_180009102
0x1800090fe  add     rax, 4
0x180009102  mov     rdx, [rbx+28h]
0x180009106  lea     rsi, [rax+rcx]
0x18000910a  mov     r9, [rbx+20h]
0x18000910e  mov     rcx, rdx
0x180009111  sub     rcx, r9
0x180009114  cmp     r9, rdx
0x180009117  sbb     rax, rax
0x18000911a  and     rax, rcx
0x18000911d  cmp     rax, rsi
0x180009120  jb      loc_1800091D1
0x180009126  sub     rdx, rsi
0x180009129  lea     rcx, [rsi+rdi]; Destination
0x18000912d  sub     rdx, rdi; DestinationSize
0x180009130  sub     r9, rdi; SourceSize
0x180009133  mov     r8, rdi; Source
0x180009136  call    cs:__imp_memmove_s
0x18000913d  nop     dword ptr [rax+rax+00h]
0x180009142  mov     r8, [rbx+20h]
0x180009146  xor     edi, edi
0x180009148  add     r8, rsi; unsigned __int8 *
0x18000914b  mov     [rbx+20h], r8
0x18000914f  cmp     byte ptr [rbp+47h+arg_0], dil
0x180009153  jnz     short loc_180009164
0x180009155  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x180009159  lea     rcx, [rbp+47h+var_88]; this
0x18000915d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180009162  jmp     short loc_1800091B7
0x180009164  mov     cl, [rbp+47h+var_86]
0x180009167  test    cl, cl
0x180009169  jz      short loc_1800091B7
0x18000916b  mov     eax, [rbp+47h+Source]
0x18000916e  lea     r8d, [rax+1]
0x180009172  cmp     eax, r8d
0x180009175  jz      short loc_1800091B7
0x180009177  mov     [rbp+47h+Source], r8d
0x18000917b  cmp     cl, 1
0x18000917e  jnz     short loc_180009194
0x180009180  mov     r9d, 2
0x180009186  mov     [rbp+47h+arg_0], r8w
0x18000918b  mov     edx, r9d
0x18000918e  lea     r8, [rbp+47h+arg_0]
0x180009192  jmp     short loc_1800091A7
0x180009194  cmp     cl, 2
0x180009197  jnz     short loc_1800091B7
0x180009199  mov     eax, 4
0x18000919e  lea     r8, [rbp+47h+Source]; Source
0x1800091a2  mov     r9d, eax; SourceSize
0x1800091a5  mov     edx, eax; DestinationSize
0x1800091a7  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800091ab  call    cs:__imp_memcpy_s
0x1800091b2  nop     dword ptr [rax+rax+00h]
0x1800091b7  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800091bb  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x1800091bf  lea     rcx, [rbp+47h+var_60]; this
0x1800091c3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800091c8  mov     byte ptr [rbx+38h], 1
0x1800091cc  jmp     loc_18000908E
0x1800091d1  xor     al, al
0x1800091d3  lea     r11, [rsp+0C0h+var_20]
0x1800091db  mov     rbx, [r11+38h]
0x1800091df  mov     rsi, [r11+40h]
0x1800091e3  mov     rdi, [r11+48h]
0x1800091e7  mov     rsp, r11
0x1800091ea  pop     r15
0x1800091ec  pop     r14
0x1800091ee  pop     r13
0x1800091f0  pop     r12
0x1800091f2  pop     rbp
0x1800091f3  retn
```
