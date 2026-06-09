# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140009950`
- end: `0x140009cd0`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140009794`

## callees

- `0x140006b28`
- `0x140008f08`
- `0x140009950`
- `0x14000bffc`
- `0x1400148d6`

## import_xrefs

- `msvcrt!memmove_s` at `0x140009c2f`
- `msvcrt!memmove_s` at `0x140009c2f`
- `msvcrt!memcpy_s` at `0x140009a5b`
- `msvcrt!memcpy_s` at `0x140009af4`
- `msvcrt!memcpy_s` at `0x140009c9a`
- `msvcrt!memcpy_s` at `0x140009a5b`
- `msvcrt!memcpy_s` at `0x140009af4`
- `msvcrt!memcpy_s` at `0x140009c9a`

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
0x140009950  push    rbp
0x140009952  push    rbx
0x140009953  push    rsi
0x140009954  push    rdi
0x140009955  push    r12
0x140009957  push    r13
0x140009959  push    r14
0x14000995b  push    r15
0x14000995d  lea     rbp, [rsp-0Fh]
0x140009962  sub     rsp, 0A8h
0x140009969  mov     rbx, [rcx+18h]
0x14000996d  mov     rdi, rcx
0x140009970  xor     ecx, ecx
0x140009972  mov     r13, r9
0x140009975  mov     r14, r8
0x140009978  mov     r15, rdx
0x14000997b  test    rbx, rbx
0x14000997e  jz      loc_140009CBA
0x140009984  movzx   eax, word ptr [rdi+2]
0x140009988  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000998c  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009990  add     rbx, 0Ah
0x140009994  mov     [rbp+47h+var_A0], ax
0x140009998  xorps   xmm0, xmm0
0x14000999b  mov     al, [rdi+4]
0x14000999e  mov     [rbp+47h+Source], ecx
0x1400099a1  mov     [rbp+47h+var_98], cx
0x1400099a5  mov     byte ptr [rbp+47h+arg_0], cl
0x1400099a8  lea     rcx, [rbp+47h+var_A0]; this
0x1400099ac  mov     [rbp+47h+var_9E], al
0x1400099af  mov     [rbp+47h+var_A8], rbx
0x1400099b3  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1400099b8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400099bd  mov     r12, [rbp+47h+arg_20]
0x1400099c1  jmp     loc_140009B0F
0x1400099c6  movzx   eax, [rbp+47h+var_98]
0x1400099ca  cmp     r14, rax
0x1400099cd  jnz     short loc_1400099E5
0x1400099cf  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1400099d3  mov     r8, r14; Size
0x1400099d6  mov     rcx, r15; Buf1
0x1400099d9  call    memcmp_0
0x1400099de  mov     ecx, eax
0x1400099e0  xor     r9d, r9d
0x1400099e3  jmp     short loc_1400099EE
0x1400099e5  movzx   eax, [rbp+47h+var_98]
0x1400099e9  mov     ecx, r14d
0x1400099ec  sub     ecx, eax
0x1400099ee  test    ecx, ecx
0x1400099f0  js      loc_140009B94
0x1400099f6  jz      loc_140009B59
0x1400099fc  mov     rbx, [rbp+47h+var_A8]
0x140009a00  mov     [rbp+47h+var_A8], rbx
0x140009a04  cmp     [rdi+10h], r9
0x140009a08  jbe     short loc_140009A73
0x140009a0a  mov     rax, [rdi+20h]
0x140009a0e  xor     edx, edx
0x140009a10  sub     rax, [rdi+18h]
0x140009a14  mov     rsi, rbx
0x140009a17  div     qword ptr [rdi+10h]
0x140009a1b  mov     edx, [rbp+47h+Source]
0x140009a1e  cmp     rdx, rax
0x140009a21  jbe     short loc_140009A64
0x140009a23  cmp     edx, eax
0x140009a25  jz      short loc_140009A64
0x140009a27  mov     edx, eax
0x140009a29  mov     [rbp+47h+Source], eax
0x140009a2c  mov     al, [rbp+47h+var_9E]
0x140009a2f  cmp     al, 1
0x140009a31  jnz     short loc_140009A46
0x140009a33  movzx   eax, dx
0x140009a36  mov     [rbp+47h+var_B0], dx
0x140009a3a  mov     r9d, 2
0x140009a40  lea     r8, [rbp+47h+var_B0]
0x140009a44  jmp     short loc_140009A54
0x140009a46  cmp     al, 2
0x140009a48  jnz     short loc_140009A64
0x140009a4a  mov     r9d, 4; SourceSize
0x140009a50  lea     r8, [rbp+47h+Source]; Source
0x140009a54  mov     rcx, [rbp+47h+Buf2]; Destination
0x140009a58  mov     rdx, r9; DestinationSize
0x140009a5b  call    cs:__imp_memcpy_s
0x140009a61  mov     edx, [rbp+47h+Source]
0x140009a64  mov     ebx, edx
0x140009a66  imul    rbx, [rdi+10h]
0x140009a6b  add     rbx, rsi
0x140009a6e  jmp     loc_140009AFA
0x140009a73  movzx   eax, word ptr [rdi+6]
0x140009a77  xorps   xmm0, xmm0
0x140009a7a  mov     [rbp+47h+var_60], ax
0x140009a7e  mov     esi, r9d
0x140009a81  mov     al, [rdi+8]
0x140009a84  mov     [rbp+47h+var_5E], al
0x140009a87  mov     eax, [rbp+47h+Source]
0x140009a8a  mov     [rbp+47h+var_5C], r9d
0x140009a8e  mov     [rbp+47h+var_58], r9w
0x140009a93  movdqu  [rbp+47h+var_50], xmm0
0x140009a98  test    eax, eax
0x140009a9a  jz      short loc_140009ABE
0x140009a9c  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009aa0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009aa4  lea     rcx, [rbp+47h+var_60]; this
0x140009aa8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009aad  test    al, al
0x140009aaf  mov     eax, [rbp+47h+Source]
0x140009ab2  jz      short loc_140009ABA
0x140009ab4  inc     esi
0x140009ab6  cmp     esi, eax
0x140009ab8  jb      short loc_140009A9C
0x140009aba  mov     rbx, [rbp+47h+var_A8]
0x140009abe  cmp     eax, esi
0x140009ac0  jz      short loc_140009AFA
0x140009ac2  mov     al, [rbp+47h+var_9E]
0x140009ac5  mov     [rbp+47h+Source], esi
0x140009ac8  cmp     al, 1
0x140009aca  jnz     short loc_140009AE0
0x140009acc  mov     eax, 2
0x140009ad1  mov     [rbp+47h+var_B0], si
0x140009ad5  mov     r9d, eax
0x140009ad8  lea     r8, [rbp+47h+var_B0]
0x140009adc  mov     edx, eax
0x140009ade  jmp     short loc_140009AF0
0x140009ae0  cmp     al, 2
0x140009ae2  jnz     short loc_140009AFA
0x140009ae4  mov     edx, 4; DestinationSize
0x140009ae9  lea     r8, [rbp+47h+Source]; Source
0x140009aed  mov     r9d, edx; SourceSize
0x140009af0  mov     rcx, [rbp+47h+Buf2]; Destination
0x140009af4  call    cs:__imp_memcpy_s
0x140009afa  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009afe  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009b02  lea     rcx, [rbp+47h+var_A0]; this
0x140009b06  mov     [rbp+47h+var_A8], rbx
0x140009b0a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009b0f  xor     r9d, r9d
0x140009b12  mov     sil, al
0x140009b15  test    al, al
0x140009b17  jnz     loc_1400099C6
0x140009b1d  mov     rbx, [rbp+47h+var_A8]
0x140009b21  mov     [rdi+20h], rbx
0x140009b25  mov     rcx, r9
0x140009b28  cmp     byte ptr [rbp+47h+arg_0], r9b
0x140009b2c  jnz     loc_140009BB7
0x140009b32  movzx   eax, [rbp+47h+var_A0]
0x140009b36  mov     [rbp+47h+Source], 1
0x140009b3d  mov     [rbp+47h+var_98], r14w
0x140009b42  mov     [rbp+47h+Buf2], r9
0x140009b46  mov     [rbp+47h+Buf2+8], r15
0x140009b4a  test    ax, ax
0x140009b4d  jnz     short loc_140009B9F
0x140009b4f  movzx   ecx, r14w
0x140009b53  add     rcx, 2
0x140009b57  jmp     short loc_140009BA2
0x140009b59  mov     eax, [rbp+47h+arg_28]
0x140009b5c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x140009b60  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x140009b64  mov     r9, r13; void *
0x140009b67  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140009b6b  mov     rcx, rdi; this
0x140009b6e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x140009b73  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140009b78  xor     r9d, r9d
0x140009b7b  mov     [rbp+47h+var_A8], rax
0x140009b7f  mov     rbx, rax
0x140009b82  test    rax, rax
0x140009b85  jnz     short loc_140009B8E
0x140009b87  mov     al, 1
0x140009b89  jmp     loc_140009CBC
0x140009b8e  mov     byte ptr [rbp+47h+arg_0], 1
0x140009b92  jmp     short loc_140009B98
0x140009b94  mov     [rbp+47h+var_A8], rbx
0x140009b98  test    sil, sil
0x140009b9b  jnz     short loc_140009B25
0x140009b9d  jmp     short loc_140009B21
0x140009b9f  mov     rcx, rax
0x140009ba2  mov     al, [rbp+47h+var_9E]
0x140009ba5  cmp     al, 1
0x140009ba7  jnz     short loc_140009BAF
0x140009ba9  add     rcx, 2
0x140009bad  jmp     short loc_140009BB7
0x140009baf  cmp     al, 2
0x140009bb1  jnz     short loc_140009BB7
0x140009bb3  add     rcx, 4
0x140009bb7  movzx   eax, word ptr [rdi+6]
0x140009bbb  mov     dl, [rdi+8]
0x140009bbe  mov     r8d, [rbp+47h+arg_28]
0x140009bc2  mov     [rbp+47h+var_80], ax
0x140009bc6  mov     [rbp+47h+var_7E], dl
0x140009bc9  mov     [rbp+47h+var_7C], r8d
0x140009bcd  mov     [rbp+47h+var_78], r12w
0x140009bd2  mov     [rbp+47h+var_70], r9
0x140009bd6  mov     [rbp+47h+var_68], r13
0x140009bda  test    ax, ax
0x140009bdd  jnz     short loc_140009BE7
0x140009bdf  movzx   eax, r12w
0x140009be3  add     rax, 2
0x140009be7  cmp     dl, 1
0x140009bea  jnz     short loc_140009BF2
0x140009bec  add     rax, 2
0x140009bf0  jmp     short loc_140009BFB
0x140009bf2  cmp     dl, 2
0x140009bf5  jnz     short loc_140009BFB
0x140009bf7  add     rax, 4
0x140009bfb  mov     rdx, [rdi+28h]
0x140009bff  lea     rsi, [rax+rcx]
0x140009c03  mov     r9, [rdi+20h]
0x140009c07  mov     rcx, rdx
0x140009c0a  sub     rcx, r9
0x140009c0d  cmp     r9, rdx
0x140009c10  sbb     rax, rax
0x140009c13  and     rax, rcx
0x140009c16  cmp     rax, rsi
0x140009c19  jb      loc_140009CBA
0x140009c1f  sub     rdx, rsi
0x140009c22  lea     rcx, [rsi+rbx]; Destination
0x140009c26  sub     rdx, rbx; DestinationSize
0x140009c29  sub     r9, rbx; SourceSize
0x140009c2c  mov     r8, rbx; Source
0x140009c2f  call    cs:__imp_memmove_s
0x140009c35  add     [rdi+20h], rsi
0x140009c39  xor     ebx, ebx
0x140009c3b  cmp     byte ptr [rbp+47h+arg_0], bl
0x140009c3e  jnz     short loc_140009C53
0x140009c40  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009c44  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009c48  lea     rcx, [rbp+47h+var_A0]; this
0x140009c4c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140009c51  jmp     short loc_140009CA0
0x140009c53  mov     cl, [rbp+47h+var_9E]
0x140009c56  test    cl, cl
0x140009c58  jz      short loc_140009CA0
0x140009c5a  mov     eax, [rbp+47h+Source]
0x140009c5d  lea     r8d, [rax+1]
0x140009c61  cmp     eax, r8d
0x140009c64  jz      short loc_140009CA0
0x140009c66  mov     [rbp+47h+Source], r8d
0x140009c6a  cmp     cl, 1
0x140009c6d  jnz     short loc_140009C83
0x140009c6f  mov     r9d, 2
0x140009c75  mov     [rbp+47h+arg_0], r8w
0x140009c7a  mov     edx, r9d
0x140009c7d  lea     r8, [rbp+47h+arg_0]
0x140009c81  jmp     short loc_140009C96
0x140009c83  cmp     cl, 2
0x140009c86  jnz     short loc_140009CA0
0x140009c88  mov     eax, 4
0x140009c8d  lea     r8, [rbp+47h+Source]; Source
0x140009c91  mov     r9d, eax; SourceSize
0x140009c94  mov     edx, eax; DestinationSize
0x140009c96  mov     rcx, [rbp+47h+Buf2]; Destination
0x140009c9a  call    cs:__imp_memcpy_s
0x140009ca0  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009ca4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009ca8  lea     rcx, [rbp+47h+var_80]; this
0x140009cac  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140009cb1  mov     byte ptr [rdi+38h], 1
0x140009cb5  jmp     loc_140009B87
0x140009cba  xor     al, al
0x140009cbc  add     rsp, 0A8h
0x140009cc3  pop     r15
0x140009cc5  pop     r14
0x140009cc7  pop     r13
0x140009cc9  pop     r12
0x140009ccb  pop     rdi
0x140009ccc  pop     rsi
0x140009ccd  pop     rbx
0x140009cce  pop     rbp
0x140009ccf  retn
```
