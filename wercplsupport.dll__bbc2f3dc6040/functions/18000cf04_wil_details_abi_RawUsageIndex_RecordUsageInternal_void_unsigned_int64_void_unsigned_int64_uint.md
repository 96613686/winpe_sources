# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000cf04`
- end: `0x18000d284`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cd54`

## callees

- `0x18000ab20`
- `0x18000c8f0`
- `0x18000cf04`
- `0x18000eea0`
- `0x180012166`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000d1e3`
- `msvcrt!memmove_s` at `0x18000d1e3`
- `msvcrt!memcpy_s` at `0x18000d00f`
- `msvcrt!memcpy_s` at `0x18000d0a8`
- `msvcrt!memcpy_s` at `0x18000d24e`
- `msvcrt!memcpy_s` at `0x18000d00f`
- `msvcrt!memcpy_s` at `0x18000d0a8`
- `msvcrt!memcpy_s` at `0x18000d24e`

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
0x18000cf04  push    rbp
0x18000cf06  push    rbx
0x18000cf07  push    rsi
0x18000cf08  push    rdi
0x18000cf09  push    r12
0x18000cf0b  push    r13
0x18000cf0d  push    r14
0x18000cf0f  push    r15
0x18000cf11  lea     rbp, [rsp-0Fh]
0x18000cf16  sub     rsp, 0A8h
0x18000cf1d  mov     rbx, [rcx+18h]
0x18000cf21  mov     rdi, rcx
0x18000cf24  xor     ecx, ecx
0x18000cf26  mov     r13, r9
0x18000cf29  mov     r14, r8
0x18000cf2c  mov     r15, rdx
0x18000cf2f  test    rbx, rbx
0x18000cf32  jz      loc_18000D26E
0x18000cf38  movzx   eax, word ptr [rdi+2]
0x18000cf3c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000cf40  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000cf44  add     rbx, 0Ah
0x18000cf48  mov     [rbp+47h+var_A0], ax
0x18000cf4c  xorps   xmm0, xmm0
0x18000cf4f  mov     al, [rdi+4]
0x18000cf52  mov     [rbp+47h+Source], ecx
0x18000cf55  mov     [rbp+47h+var_98], cx
0x18000cf59  mov     byte ptr [rbp+47h+arg_0], cl
0x18000cf5c  lea     rcx, [rbp+47h+var_A0]; this
0x18000cf60  mov     [rbp+47h+var_9E], al
0x18000cf63  mov     [rbp+47h+var_A8], rbx
0x18000cf67  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000cf6c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000cf71  mov     r12, [rbp+47h+arg_20]
0x18000cf75  jmp     loc_18000D0C3
0x18000cf7a  movzx   eax, [rbp+47h+var_98]
0x18000cf7e  cmp     r14, rax
0x18000cf81  jnz     short loc_18000CF99
0x18000cf83  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000cf87  mov     r8, r14; Size
0x18000cf8a  mov     rcx, r15; Buf1
0x18000cf8d  call    memcmp_0
0x18000cf92  mov     ecx, eax
0x18000cf94  xor     r9d, r9d
0x18000cf97  jmp     short loc_18000CFA2
0x18000cf99  movzx   eax, [rbp+47h+var_98]
0x18000cf9d  mov     ecx, r14d
0x18000cfa0  sub     ecx, eax
0x18000cfa2  test    ecx, ecx
0x18000cfa4  js      loc_18000D148
0x18000cfaa  jz      loc_18000D10D
0x18000cfb0  mov     rbx, [rbp+47h+var_A8]
0x18000cfb4  mov     [rbp+47h+var_A8], rbx
0x18000cfb8  cmp     [rdi+10h], r9
0x18000cfbc  jbe     short loc_18000D027
0x18000cfbe  mov     rax, [rdi+20h]
0x18000cfc2  xor     edx, edx
0x18000cfc4  sub     rax, [rdi+18h]
0x18000cfc8  mov     rsi, rbx
0x18000cfcb  div     qword ptr [rdi+10h]
0x18000cfcf  mov     edx, [rbp+47h+Source]
0x18000cfd2  cmp     rdx, rax
0x18000cfd5  jbe     short loc_18000D018
0x18000cfd7  cmp     edx, eax
0x18000cfd9  jz      short loc_18000D018
0x18000cfdb  mov     edx, eax
0x18000cfdd  mov     [rbp+47h+Source], eax
0x18000cfe0  mov     al, [rbp+47h+var_9E]
0x18000cfe3  cmp     al, 1
0x18000cfe5  jnz     short loc_18000CFFA
0x18000cfe7  movzx   eax, dx
0x18000cfea  mov     [rbp+47h+var_B0], dx
0x18000cfee  mov     r9d, 2
0x18000cff4  lea     r8, [rbp+47h+var_B0]
0x18000cff8  jmp     short loc_18000D008
0x18000cffa  cmp     al, 2
0x18000cffc  jnz     short loc_18000D018
0x18000cffe  mov     r9d, 4; SourceSize
0x18000d004  lea     r8, [rbp+47h+Source]; Source
0x18000d008  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d00c  mov     rdx, r9; DestinationSize
0x18000d00f  call    cs:__imp_memcpy_s
0x18000d015  mov     edx, [rbp+47h+Source]
0x18000d018  mov     ebx, edx
0x18000d01a  imul    rbx, [rdi+10h]
0x18000d01f  add     rbx, rsi
0x18000d022  jmp     loc_18000D0AE
0x18000d027  movzx   eax, word ptr [rdi+6]
0x18000d02b  xorps   xmm0, xmm0
0x18000d02e  mov     [rbp+47h+var_60], ax
0x18000d032  mov     esi, r9d
0x18000d035  mov     al, [rdi+8]
0x18000d038  mov     [rbp+47h+var_5E], al
0x18000d03b  mov     eax, [rbp+47h+Source]
0x18000d03e  mov     [rbp+47h+var_5C], r9d
0x18000d042  mov     [rbp+47h+var_58], r9w
0x18000d047  movdqu  [rbp+47h+var_50], xmm0
0x18000d04c  test    eax, eax
0x18000d04e  jz      short loc_18000D072
0x18000d050  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d054  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d058  lea     rcx, [rbp+47h+var_60]; this
0x18000d05c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d061  test    al, al
0x18000d063  mov     eax, [rbp+47h+Source]
0x18000d066  jz      short loc_18000D06E
0x18000d068  inc     esi
0x18000d06a  cmp     esi, eax
0x18000d06c  jb      short loc_18000D050
0x18000d06e  mov     rbx, [rbp+47h+var_A8]
0x18000d072  cmp     eax, esi
0x18000d074  jz      short loc_18000D0AE
0x18000d076  mov     al, [rbp+47h+var_9E]
0x18000d079  mov     [rbp+47h+Source], esi
0x18000d07c  cmp     al, 1
0x18000d07e  jnz     short loc_18000D094
0x18000d080  mov     eax, 2
0x18000d085  mov     [rbp+47h+var_B0], si
0x18000d089  mov     r9d, eax
0x18000d08c  lea     r8, [rbp+47h+var_B0]
0x18000d090  mov     edx, eax
0x18000d092  jmp     short loc_18000D0A4
0x18000d094  cmp     al, 2
0x18000d096  jnz     short loc_18000D0AE
0x18000d098  mov     edx, 4; DestinationSize
0x18000d09d  lea     r8, [rbp+47h+Source]; Source
0x18000d0a1  mov     r9d, edx; SourceSize
0x18000d0a4  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d0a8  call    cs:__imp_memcpy_s
0x18000d0ae  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d0b2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d0b6  lea     rcx, [rbp+47h+var_A0]; this
0x18000d0ba  mov     [rbp+47h+var_A8], rbx
0x18000d0be  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d0c3  xor     r9d, r9d
0x18000d0c6  mov     sil, al
0x18000d0c9  test    al, al
0x18000d0cb  jnz     loc_18000CF7A
0x18000d0d1  mov     rbx, [rbp+47h+var_A8]
0x18000d0d5  mov     [rdi+20h], rbx
0x18000d0d9  mov     rcx, r9
0x18000d0dc  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000d0e0  jnz     loc_18000D16B
0x18000d0e6  movzx   eax, [rbp+47h+var_A0]
0x18000d0ea  mov     [rbp+47h+Source], 1
0x18000d0f1  mov     [rbp+47h+var_98], r14w
0x18000d0f6  mov     [rbp+47h+Buf2], r9
0x18000d0fa  mov     [rbp+47h+Buf2+8], r15
0x18000d0fe  test    ax, ax
0x18000d101  jnz     short loc_18000D153
0x18000d103  movzx   ecx, r14w
0x18000d107  add     rcx, 2
0x18000d10b  jmp     short loc_18000D156
0x18000d10d  mov     eax, [rbp+47h+arg_28]
0x18000d110  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000d114  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000d118  mov     r9, r13; void *
0x18000d11b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000d11f  mov     rcx, rdi; this
0x18000d122  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000d127  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000d12c  xor     r9d, r9d
0x18000d12f  mov     [rbp+47h+var_A8], rax
0x18000d133  mov     rbx, rax
0x18000d136  test    rax, rax
0x18000d139  jnz     short loc_18000D142
0x18000d13b  mov     al, 1
0x18000d13d  jmp     loc_18000D270
0x18000d142  mov     byte ptr [rbp+47h+arg_0], 1
0x18000d146  jmp     short loc_18000D14C
0x18000d148  mov     [rbp+47h+var_A8], rbx
0x18000d14c  test    sil, sil
0x18000d14f  jnz     short loc_18000D0D9
0x18000d151  jmp     short loc_18000D0D5
0x18000d153  mov     rcx, rax
0x18000d156  mov     al, [rbp+47h+var_9E]
0x18000d159  cmp     al, 1
0x18000d15b  jnz     short loc_18000D163
0x18000d15d  add     rcx, 2
0x18000d161  jmp     short loc_18000D16B
0x18000d163  cmp     al, 2
0x18000d165  jnz     short loc_18000D16B
0x18000d167  add     rcx, 4
0x18000d16b  movzx   eax, word ptr [rdi+6]
0x18000d16f  mov     dl, [rdi+8]
0x18000d172  mov     r8d, [rbp+47h+arg_28]
0x18000d176  mov     [rbp+47h+var_80], ax
0x18000d17a  mov     [rbp+47h+var_7E], dl
0x18000d17d  mov     [rbp+47h+var_7C], r8d
0x18000d181  mov     [rbp+47h+var_78], r12w
0x18000d186  mov     [rbp+47h+var_70], r9
0x18000d18a  mov     [rbp+47h+var_68], r13
0x18000d18e  test    ax, ax
0x18000d191  jnz     short loc_18000D19B
0x18000d193  movzx   eax, r12w
0x18000d197  add     rax, 2
0x18000d19b  cmp     dl, 1
0x18000d19e  jnz     short loc_18000D1A6
0x18000d1a0  add     rax, 2
0x18000d1a4  jmp     short loc_18000D1AF
0x18000d1a6  cmp     dl, 2
0x18000d1a9  jnz     short loc_18000D1AF
0x18000d1ab  add     rax, 4
0x18000d1af  mov     rdx, [rdi+28h]
0x18000d1b3  lea     rsi, [rax+rcx]
0x18000d1b7  mov     r9, [rdi+20h]
0x18000d1bb  mov     rcx, rdx
0x18000d1be  sub     rcx, r9
0x18000d1c1  cmp     r9, rdx
0x18000d1c4  sbb     rax, rax
0x18000d1c7  and     rax, rcx
0x18000d1ca  cmp     rax, rsi
0x18000d1cd  jb      loc_18000D26E
0x18000d1d3  sub     rdx, rsi
0x18000d1d6  lea     rcx, [rsi+rbx]; Destination
0x18000d1da  sub     rdx, rbx; DestinationSize
0x18000d1dd  sub     r9, rbx; SourceSize
0x18000d1e0  mov     r8, rbx; Source
0x18000d1e3  call    cs:__imp_memmove_s
0x18000d1e9  add     [rdi+20h], rsi
0x18000d1ed  xor     ebx, ebx
0x18000d1ef  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000d1f2  jnz     short loc_18000D207
0x18000d1f4  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d1f8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d1fc  lea     rcx, [rbp+47h+var_A0]; this
0x18000d200  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000d205  jmp     short loc_18000D254
0x18000d207  mov     cl, [rbp+47h+var_9E]
0x18000d20a  test    cl, cl
0x18000d20c  jz      short loc_18000D254
0x18000d20e  mov     eax, [rbp+47h+Source]
0x18000d211  lea     r8d, [rax+1]
0x18000d215  cmp     eax, r8d
0x18000d218  jz      short loc_18000D254
0x18000d21a  mov     [rbp+47h+Source], r8d
0x18000d21e  cmp     cl, 1
0x18000d221  jnz     short loc_18000D237
0x18000d223  mov     r9d, 2
0x18000d229  mov     [rbp+47h+arg_0], r8w
0x18000d22e  mov     edx, r9d
0x18000d231  lea     r8, [rbp+47h+arg_0]
0x18000d235  jmp     short loc_18000D24A
0x18000d237  cmp     cl, 2
0x18000d23a  jnz     short loc_18000D254
0x18000d23c  mov     eax, 4
0x18000d241  lea     r8, [rbp+47h+Source]; Source
0x18000d245  mov     r9d, eax; SourceSize
0x18000d248  mov     edx, eax; DestinationSize
0x18000d24a  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000d24e  call    cs:__imp_memcpy_s
0x18000d254  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000d258  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000d25c  lea     rcx, [rbp+47h+var_80]; this
0x18000d260  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000d265  mov     byte ptr [rdi+38h], 1
0x18000d269  jmp     loc_18000D13B
0x18000d26e  xor     al, al
0x18000d270  add     rsp, 0A8h
0x18000d277  pop     r15
0x18000d279  pop     r14
0x18000d27b  pop     r13
0x18000d27d  pop     r12
0x18000d27f  pop     rdi
0x18000d280  pop     rsi
0x18000d281  pop     rbx
0x18000d282  pop     rbp
0x18000d283  retn
```
