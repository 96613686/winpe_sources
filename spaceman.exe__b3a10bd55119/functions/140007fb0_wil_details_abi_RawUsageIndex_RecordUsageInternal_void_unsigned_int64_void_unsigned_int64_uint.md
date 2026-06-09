# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140007fb0`
- end: `0x140008330`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007e00`

## callees

- `0x14000625c`
- `0x14000797c`
- `0x140007fb0`
- `0x140009f2c`
- `0x14000d1a6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400080bb`
- `msvcrt!memcpy_s` at `0x140008154`
- `msvcrt!memcpy_s` at `0x1400082fa`
- `msvcrt!memcpy_s` at `0x1400080bb`
- `msvcrt!memcpy_s` at `0x140008154`
- `msvcrt!memcpy_s` at `0x1400082fa`
- `msvcrt!memmove_s` at `0x14000828f`
- `msvcrt!memmove_s` at `0x14000828f`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rbx
  unsigned __int8 *v11; // r8
  unsigned __int8 *v12; // rbx
  char v13; // al
  bool v14; // al
  unsigned __int64 v15; // r12
  int v16; // ecx
  unsigned __int8 *v17; // rsi
  unsigned __int64 v18; // rax
  unsigned int v19; // edx
  rsize_t v20; // r9
  unsigned int *p_Source; // r8
  unsigned int v22; // esi
  unsigned int v23; // eax
  bool v24; // zf
  rsize_t v25; // r9
  unsigned int *v26; // r8
  rsize_t v27; // rdx
  unsigned __int8 *v28; // r8
  bool v29; // si
  __int64 v30; // rcx
  __int64 v32; // rax
  char v33; // dl
  unsigned __int64 v34; // rdx
  __int64 v35; // rsi
  unsigned __int64 v36; // r9
  __int16 v37; // r8
  rsize_t v38; // r9
  rsize_t v39; // rdx
  unsigned int *v40; // r8
  __int16 v41; // [rsp+30h] [rbp-69h] BYREF
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 v43; // [rsp+40h] [rbp-59h] BYREF
  char v44; // [rsp+42h] [rbp-57h]
  unsigned int Source; // [rsp+44h] [rbp-55h] BYREF
  unsigned __int16 v46; // [rsp+48h] [rbp-51h]
  void *Buf2[2]; // [rsp+50h] [rbp-49h]
  __int16 v48; // [rsp+60h] [rbp-39h] BYREF
  char v49; // [rsp+62h] [rbp-37h]
  unsigned int v50; // [rsp+64h] [rbp-35h]
  __int16 v51; // [rsp+68h] [rbp-31h]
  __int64 v52; // [rsp+70h] [rbp-29h]
  void *v53; // [rsp+78h] [rbp-21h]
  __int16 v54; // [rsp+80h] [rbp-19h] BYREF
  char v55; // [rsp+82h] [rbp-17h]
  int v56; // [rsp+84h] [rbp-15h]
  __int16 v57; // [rsp+88h] [rbp-11h]
  __int128 v58; // [rsp+90h] [rbp-9h]
  __int16 v59; // [rsp+F0h] [rbp+57h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( !v6 )
    return 0;
  v11 = (unsigned __int8 *)*((_QWORD *)this + 4);
  v12 = (unsigned __int8 *)(v6 + 10);
  v43 = *((_WORD *)this + 1);
  v13 = *((_BYTE *)this + 4);
  Source = 0;
  v46 = 0;
  LOBYTE(v59) = 0;
  v44 = v13;
  InsertionPointOrIncrement = v12;
  *(_OWORD *)Buf2 = 0;
  v14 = wil::details_abi::UsageIndexProperty::Read(
          (wil::details_abi::UsageIndexProperty *)&v43,
          &InsertionPointOrIncrement,
          v11);
  v15 = a5;
  while ( 1 )
  {
    v29 = v14;
    if ( !v14 )
    {
      v12 = InsertionPointOrIncrement;
      goto LABEL_30;
    }
    v16 = Size == v46 ? memcmp_0(Buf1, Buf2[1], Size) : Size - v46;
    if ( v16 < 0 )
      break;
    if ( !v16 )
    {
      InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                    this,
                                    (struct wil::details_abi::UsageIndexProperty *)&v43,
                                    InsertionPointOrIncrement,
                                    a4,
                                    v15,
                                    a6);
      v12 = InsertionPointOrIncrement;
      if ( InsertionPointOrIncrement )
      {
        LOBYTE(v59) = 1;
        goto LABEL_38;
      }
      return 1;
    }
    v12 = InsertionPointOrIncrement;
    if ( *((_QWORD *)this + 2) )
    {
      v17 = InsertionPointOrIncrement;
      v18 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
      v19 = Source;
      if ( Source > v18 && Source != (_DWORD)v18 )
      {
        v19 = (*((_QWORD *)this + 4) - *((_QWORD *)this + 3)) / *((_QWORD *)this + 2);
        Source = v19;
        if ( v44 == 1 )
        {
          v41 = v18;
          v20 = 2;
          p_Source = (unsigned int *)&v41;
          goto LABEL_15;
        }
        if ( v44 == 2 )
        {
          v20 = 4;
          p_Source = &Source;
LABEL_15:
          memcpy_s(Buf2[0], v20, p_Source, v20);
          v19 = Source;
        }
      }
      v12 = &v17[*((_QWORD *)this + 2) * v19];
      goto LABEL_27;
    }
    v54 = *((_WORD *)this + 3);
    v22 = 0;
    v55 = *((_BYTE *)this + 8);
    v23 = Source;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    if ( Source )
    {
      do
      {
        v24 = !wil::details_abi::UsageIndexProperty::Read(
                 (wil::details_abi::UsageIndexProperty *)&v54,
                 &InsertionPointOrIncrement,
                 *((unsigned __int8 **)this + 4));
        v23 = Source;
        if ( v24 )
          break;
        ++v22;
      }
      while ( v22 < Source );
      v12 = InsertionPointOrIncrement;
    }
    if ( v23 != v22 )
    {
      Source = v22;
      if ( v44 == 1 )
      {
        v41 = v22;
        v25 = 2;
        v26 = (unsigned int *)&v41;
        v27 = 2;
      }
      else
      {
        if ( v44 != 2 )
          goto LABEL_27;
        v27 = 4;
        v26 = &Source;
        v25 = 4;
      }
      memcpy_s(Buf2[0], v27, v26, v25);
    }
LABEL_27:
    v28 = (unsigned __int8 *)*((_QWORD *)this + 4);
    InsertionPointOrIncrement = v12;
    v14 = wil::details_abi::UsageIndexProperty::Read(
            (wil::details_abi::UsageIndexProperty *)&v43,
            &InsertionPointOrIncrement,
            v28);
  }
  InsertionPointOrIncrement = v12;
LABEL_38:
  if ( !v29 )
LABEL_30:
    *((_QWORD *)this + 4) = v12;
  v30 = 0;
  if ( !(_BYTE)v59 )
  {
    Source = 1;
    v46 = Size;
    Buf2[0] = 0;
    Buf2[1] = Buf1;
    if ( v43 )
      v30 = v43;
    else
      v30 = (unsigned __int16)Size + 2LL;
    if ( v44 == 1 )
    {
      v30 += 2;
    }
    else if ( v44 == 2 )
    {
      v30 += 4;
    }
  }
  v32 = *((unsigned __int16 *)this + 3);
  v33 = *((_BYTE *)this + 8);
  v48 = v32;
  v49 = v33;
  v50 = a6;
  v51 = v15;
  v52 = 0;
  v53 = a4;
  if ( !(_WORD)v32 )
    v32 = (unsigned __int16)v15 + 2LL;
  if ( v33 == 1 )
  {
    v32 += 2;
  }
  else if ( v33 == 2 )
  {
    v32 += 4;
  }
  v34 = *((_QWORD *)this + 5);
  v35 = v32 + v30;
  v36 = *((_QWORD *)this + 4);
  if ( ((v34 - v36) & -(__int64)(v36 < v34)) >= v32 + v30 )
  {
    memmove_s(&v12[v35], v34 - v35 - (_QWORD)v12, v12, v36 - (_QWORD)v12);
    *((_QWORD *)this + 4) += v35;
    if ( !(_BYTE)v59 )
    {
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v43,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
LABEL_61:
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v48,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
    if ( !v44 )
      goto LABEL_61;
    v37 = Source + 1;
    if ( Source == Source + 1 )
      goto LABEL_61;
    ++Source;
    if ( v44 == 1 )
    {
      v38 = 2;
      v59 = v37;
      v39 = 2;
      v40 = (unsigned int *)&v59;
    }
    else
    {
      if ( v44 != 2 )
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
0x140007fb0  push    rbp
0x140007fb2  push    rbx
0x140007fb3  push    rsi
0x140007fb4  push    rdi
0x140007fb5  push    r12
0x140007fb7  push    r13
0x140007fb9  push    r14
0x140007fbb  push    r15
0x140007fbd  lea     rbp, [rsp-0Fh]
0x140007fc2  sub     rsp, 0A8h
0x140007fc9  mov     rbx, [rcx+18h]
0x140007fcd  mov     rdi, rcx
0x140007fd0  xor     ecx, ecx
0x140007fd2  mov     r13, r9
0x140007fd5  mov     r14, r8
0x140007fd8  mov     r15, rdx
0x140007fdb  test    rbx, rbx
0x140007fde  jz      loc_14000831A
0x140007fe4  movzx   eax, word ptr [rdi+2]
0x140007fe8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140007fec  mov     r8, [rdi+20h]; unsigned __int8 *
0x140007ff0  add     rbx, 0Ah
0x140007ff4  mov     [rbp+47h+var_A0], ax
0x140007ff8  xorps   xmm0, xmm0
0x140007ffb  mov     al, [rdi+4]
0x140007ffe  mov     [rbp+47h+Source], ecx
0x140008001  mov     [rbp+47h+var_98], cx
0x140008005  mov     byte ptr [rbp+47h+arg_0], cl
0x140008008  lea     rcx, [rbp+47h+var_A0]; this
0x14000800c  mov     [rbp+47h+var_9E], al
0x14000800f  mov     [rbp+47h+var_A8], rbx
0x140008013  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x140008018  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000801d  mov     r12, [rbp+47h+arg_20]
0x140008021  jmp     loc_14000816F
0x140008026  movzx   eax, [rbp+47h+var_98]
0x14000802a  cmp     r14, rax
0x14000802d  jnz     short loc_140008045
0x14000802f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x140008033  mov     r8, r14; Size
0x140008036  mov     rcx, r15; Buf1
0x140008039  call    memcmp_0
0x14000803e  mov     ecx, eax
0x140008040  xor     r9d, r9d
0x140008043  jmp     short loc_14000804E
0x140008045  movzx   eax, [rbp+47h+var_98]
0x140008049  mov     ecx, r14d
0x14000804c  sub     ecx, eax
0x14000804e  test    ecx, ecx
0x140008050  js      loc_1400081F4
0x140008056  jz      loc_1400081B9
0x14000805c  mov     rbx, [rbp+47h+var_A8]
0x140008060  mov     [rbp+47h+var_A8], rbx
0x140008064  cmp     [rdi+10h], r9
0x140008068  jbe     short loc_1400080D3
0x14000806a  mov     rax, [rdi+20h]
0x14000806e  xor     edx, edx
0x140008070  sub     rax, [rdi+18h]
0x140008074  mov     rsi, rbx
0x140008077  div     qword ptr [rdi+10h]
0x14000807b  mov     edx, [rbp+47h+Source]
0x14000807e  cmp     rdx, rax
0x140008081  jbe     short loc_1400080C4
0x140008083  cmp     edx, eax
0x140008085  jz      short loc_1400080C4
0x140008087  mov     edx, eax
0x140008089  mov     [rbp+47h+Source], eax
0x14000808c  mov     al, [rbp+47h+var_9E]
0x14000808f  cmp     al, 1
0x140008091  jnz     short loc_1400080A6
0x140008093  movzx   eax, dx
0x140008096  mov     [rbp+47h+var_B0], dx
0x14000809a  mov     r9d, 2
0x1400080a0  lea     r8, [rbp+47h+var_B0]
0x1400080a4  jmp     short loc_1400080B4
0x1400080a6  cmp     al, 2
0x1400080a8  jnz     short loc_1400080C4
0x1400080aa  mov     r9d, 4; SourceSize
0x1400080b0  lea     r8, [rbp+47h+Source]; Source
0x1400080b4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1400080b8  mov     rdx, r9; DestinationSize
0x1400080bb  call    cs:__imp_memcpy_s
0x1400080c1  mov     edx, [rbp+47h+Source]
0x1400080c4  mov     ebx, edx
0x1400080c6  imul    rbx, [rdi+10h]
0x1400080cb  add     rbx, rsi
0x1400080ce  jmp     loc_14000815A
0x1400080d3  movzx   eax, word ptr [rdi+6]
0x1400080d7  xorps   xmm0, xmm0
0x1400080da  mov     [rbp+47h+var_60], ax
0x1400080de  mov     esi, r9d
0x1400080e1  mov     al, [rdi+8]
0x1400080e4  mov     [rbp+47h+var_5E], al
0x1400080e7  mov     eax, [rbp+47h+Source]
0x1400080ea  mov     [rbp+47h+var_5C], r9d
0x1400080ee  mov     [rbp+47h+var_58], r9w
0x1400080f3  movdqu  [rbp+47h+var_50], xmm0
0x1400080f8  test    eax, eax
0x1400080fa  jz      short loc_14000811E
0x1400080fc  mov     r8, [rdi+20h]; unsigned __int8 *
0x140008100  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140008104  lea     rcx, [rbp+47h+var_60]; this
0x140008108  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000810d  test    al, al
0x14000810f  mov     eax, [rbp+47h+Source]
0x140008112  jz      short loc_14000811A
0x140008114  inc     esi
0x140008116  cmp     esi, eax
0x140008118  jb      short loc_1400080FC
0x14000811a  mov     rbx, [rbp+47h+var_A8]
0x14000811e  cmp     eax, esi
0x140008120  jz      short loc_14000815A
0x140008122  mov     al, [rbp+47h+var_9E]
0x140008125  mov     [rbp+47h+Source], esi
0x140008128  cmp     al, 1
0x14000812a  jnz     short loc_140008140
0x14000812c  mov     eax, 2
0x140008131  mov     [rbp+47h+var_B0], si
0x140008135  mov     r9d, eax
0x140008138  lea     r8, [rbp+47h+var_B0]
0x14000813c  mov     edx, eax
0x14000813e  jmp     short loc_140008150
0x140008140  cmp     al, 2
0x140008142  jnz     short loc_14000815A
0x140008144  mov     edx, 4; DestinationSize
0x140008149  lea     r8, [rbp+47h+Source]; Source
0x14000814d  mov     r9d, edx; SourceSize
0x140008150  mov     rcx, [rbp+47h+Buf2]; Destination
0x140008154  call    cs:__imp_memcpy_s
0x14000815a  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000815e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140008162  lea     rcx, [rbp+47h+var_A0]; this
0x140008166  mov     [rbp+47h+var_A8], rbx
0x14000816a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000816f  xor     r9d, r9d
0x140008172  mov     sil, al
0x140008175  test    al, al
0x140008177  jnz     loc_140008026
0x14000817d  mov     rbx, [rbp+47h+var_A8]
0x140008181  mov     [rdi+20h], rbx
0x140008185  mov     rcx, r9
0x140008188  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14000818c  jnz     loc_140008217
0x140008192  movzx   eax, [rbp+47h+var_A0]
0x140008196  mov     [rbp+47h+Source], 1
0x14000819d  mov     [rbp+47h+var_98], r14w
0x1400081a2  mov     [rbp+47h+Buf2], r9
0x1400081a6  mov     [rbp+47h+Buf2+8], r15
0x1400081aa  test    ax, ax
0x1400081ad  jnz     short loc_1400081FF
0x1400081af  movzx   ecx, r14w
0x1400081b3  add     rcx, 2
0x1400081b7  jmp     short loc_140008202
0x1400081b9  mov     eax, [rbp+47h+arg_28]
0x1400081bc  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1400081c0  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1400081c4  mov     r9, r13; void *
0x1400081c7  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1400081cb  mov     rcx, rdi; this
0x1400081ce  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1400081d3  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1400081d8  xor     r9d, r9d
0x1400081db  mov     [rbp+47h+var_A8], rax
0x1400081df  mov     rbx, rax
0x1400081e2  test    rax, rax
0x1400081e5  jnz     short loc_1400081EE
0x1400081e7  mov     al, 1
0x1400081e9  jmp     loc_14000831C
0x1400081ee  mov     byte ptr [rbp+47h+arg_0], 1
0x1400081f2  jmp     short loc_1400081F8
0x1400081f4  mov     [rbp+47h+var_A8], rbx
0x1400081f8  test    sil, sil
0x1400081fb  jnz     short loc_140008185
0x1400081fd  jmp     short loc_140008181
0x1400081ff  mov     rcx, rax
0x140008202  mov     al, [rbp+47h+var_9E]
0x140008205  cmp     al, 1
0x140008207  jnz     short loc_14000820F
0x140008209  add     rcx, 2
0x14000820d  jmp     short loc_140008217
0x14000820f  cmp     al, 2
0x140008211  jnz     short loc_140008217
0x140008213  add     rcx, 4
0x140008217  movzx   eax, word ptr [rdi+6]
0x14000821b  mov     dl, [rdi+8]
0x14000821e  mov     r8d, [rbp+47h+arg_28]
0x140008222  mov     [rbp+47h+var_80], ax
0x140008226  mov     [rbp+47h+var_7E], dl
0x140008229  mov     [rbp+47h+var_7C], r8d
0x14000822d  mov     [rbp+47h+var_78], r12w
0x140008232  mov     [rbp+47h+var_70], r9
0x140008236  mov     [rbp+47h+var_68], r13
0x14000823a  test    ax, ax
0x14000823d  jnz     short loc_140008247
0x14000823f  movzx   eax, r12w
0x140008243  add     rax, 2
0x140008247  cmp     dl, 1
0x14000824a  jnz     short loc_140008252
0x14000824c  add     rax, 2
0x140008250  jmp     short loc_14000825B
0x140008252  cmp     dl, 2
0x140008255  jnz     short loc_14000825B
0x140008257  add     rax, 4
0x14000825b  mov     rdx, [rdi+28h]
0x14000825f  lea     rsi, [rax+rcx]
0x140008263  mov     r9, [rdi+20h]
0x140008267  mov     rcx, rdx
0x14000826a  sub     rcx, r9
0x14000826d  cmp     r9, rdx
0x140008270  sbb     rax, rax
0x140008273  and     rax, rcx
0x140008276  cmp     rax, rsi
0x140008279  jb      loc_14000831A
0x14000827f  sub     rdx, rsi
0x140008282  lea     rcx, [rsi+rbx]; Destination
0x140008286  sub     rdx, rbx; DestinationSize
0x140008289  sub     r9, rbx; SourceSize
0x14000828c  mov     r8, rbx; Source
0x14000828f  call    cs:__imp_memmove_s
0x140008295  add     [rdi+20h], rsi
0x140008299  xor     ebx, ebx
0x14000829b  cmp     byte ptr [rbp+47h+arg_0], bl
0x14000829e  jnz     short loc_1400082B3
0x1400082a0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400082a4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1400082a8  lea     rcx, [rbp+47h+var_A0]; this
0x1400082ac  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400082b1  jmp     short loc_140008300
0x1400082b3  mov     cl, [rbp+47h+var_9E]
0x1400082b6  test    cl, cl
0x1400082b8  jz      short loc_140008300
0x1400082ba  mov     eax, [rbp+47h+Source]
0x1400082bd  lea     r8d, [rax+1]
0x1400082c1  cmp     eax, r8d
0x1400082c4  jz      short loc_140008300
0x1400082c6  mov     [rbp+47h+Source], r8d
0x1400082ca  cmp     cl, 1
0x1400082cd  jnz     short loc_1400082E3
0x1400082cf  mov     r9d, 2
0x1400082d5  mov     [rbp+47h+arg_0], r8w
0x1400082da  mov     edx, r9d
0x1400082dd  lea     r8, [rbp+47h+arg_0]
0x1400082e1  jmp     short loc_1400082F6
0x1400082e3  cmp     cl, 2
0x1400082e6  jnz     short loc_140008300
0x1400082e8  mov     eax, 4
0x1400082ed  lea     r8, [rbp+47h+Source]; Source
0x1400082f1  mov     r9d, eax; SourceSize
0x1400082f4  mov     edx, eax; DestinationSize
0x1400082f6  mov     rcx, [rbp+47h+Buf2]; Destination
0x1400082fa  call    cs:__imp_memcpy_s
0x140008300  mov     r8, [rdi+20h]; unsigned __int8 *
0x140008304  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140008308  lea     rcx, [rbp+47h+var_80]; this
0x14000830c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140008311  mov     byte ptr [rdi+38h], 1
0x140008315  jmp     loc_1400081E7
0x14000831a  xor     al, al
0x14000831c  add     rsp, 0A8h
0x140008323  pop     r15
0x140008325  pop     r14
0x140008327  pop     r13
0x140008329  pop     r12
0x14000832b  pop     rdi
0x14000832c  pop     rsi
0x14000832d  pop     rbx
0x14000832e  pop     rbp
0x14000832f  retn
```
