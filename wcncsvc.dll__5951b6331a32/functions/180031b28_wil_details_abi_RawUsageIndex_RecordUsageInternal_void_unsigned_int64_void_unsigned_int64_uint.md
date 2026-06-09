# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180031b28`
- end: `0x180031ea8`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180031978`

## callees

- `0x18002ebb8`
- `0x1800312f4`
- `0x180031b28`
- `0x18003418c`
- `0x180056de6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180031e07`
- `msvcrt!memmove_s` at `0x180031e07`
- `msvcrt!memcpy_s` at `0x180031c33`
- `msvcrt!memcpy_s` at `0x180031ccc`
- `msvcrt!memcpy_s` at `0x180031e72`
- `msvcrt!memcpy_s` at `0x180031c33`
- `msvcrt!memcpy_s` at `0x180031ccc`
- `msvcrt!memcpy_s` at `0x180031e72`

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
0x180031b28  push    rbp
0x180031b2a  push    rbx
0x180031b2b  push    rsi
0x180031b2c  push    rdi
0x180031b2d  push    r12
0x180031b2f  push    r13
0x180031b31  push    r14
0x180031b33  push    r15
0x180031b35  lea     rbp, [rsp-0Fh]
0x180031b3a  sub     rsp, 0A8h
0x180031b41  mov     rbx, [rcx+18h]
0x180031b45  mov     rdi, rcx
0x180031b48  xor     ecx, ecx
0x180031b4a  mov     r13, r9
0x180031b4d  mov     r14, r8
0x180031b50  mov     r15, rdx
0x180031b53  test    rbx, rbx
0x180031b56  jz      loc_180031E92
0x180031b5c  movzx   eax, word ptr [rdi+2]
0x180031b60  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180031b64  mov     r8, [rdi+20h]; unsigned __int8 *
0x180031b68  add     rbx, 0Ah
0x180031b6c  mov     [rbp+47h+var_A0], ax
0x180031b70  xorps   xmm0, xmm0
0x180031b73  mov     al, [rdi+4]
0x180031b76  mov     [rbp+47h+Source], ecx
0x180031b79  mov     [rbp+47h+var_98], cx
0x180031b7d  mov     byte ptr [rbp+47h+arg_0], cl
0x180031b80  lea     rcx, [rbp+47h+var_A0]; this
0x180031b84  mov     [rbp+47h+var_9E], al
0x180031b87  mov     [rbp+47h+var_A8], rbx
0x180031b8b  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180031b90  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180031b95  mov     r12, [rbp+47h+arg_20]
0x180031b99  jmp     loc_180031CE7
0x180031b9e  movzx   eax, [rbp+47h+var_98]
0x180031ba2  cmp     r14, rax
0x180031ba5  jnz     short loc_180031BBD
0x180031ba7  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180031bab  mov     r8, r14; Size
0x180031bae  mov     rcx, r15; Buf1
0x180031bb1  call    memcmp_0
0x180031bb6  mov     ecx, eax
0x180031bb8  xor     r9d, r9d
0x180031bbb  jmp     short loc_180031BC6
0x180031bbd  movzx   eax, [rbp+47h+var_98]
0x180031bc1  mov     ecx, r14d
0x180031bc4  sub     ecx, eax
0x180031bc6  test    ecx, ecx
0x180031bc8  js      loc_180031D6C
0x180031bce  jz      loc_180031D31
0x180031bd4  mov     rbx, [rbp+47h+var_A8]
0x180031bd8  mov     [rbp+47h+var_A8], rbx
0x180031bdc  cmp     [rdi+10h], r9
0x180031be0  jbe     short loc_180031C4B
0x180031be2  mov     rax, [rdi+20h]
0x180031be6  xor     edx, edx
0x180031be8  sub     rax, [rdi+18h]
0x180031bec  mov     rsi, rbx
0x180031bef  div     qword ptr [rdi+10h]
0x180031bf3  mov     edx, [rbp+47h+Source]
0x180031bf6  cmp     rdx, rax
0x180031bf9  jbe     short loc_180031C3C
0x180031bfb  cmp     edx, eax
0x180031bfd  jz      short loc_180031C3C
0x180031bff  mov     edx, eax
0x180031c01  mov     [rbp+47h+Source], eax
0x180031c04  mov     al, [rbp+47h+var_9E]
0x180031c07  cmp     al, 1
0x180031c09  jnz     short loc_180031C1E
0x180031c0b  movzx   eax, dx
0x180031c0e  mov     [rbp+47h+var_B0], dx
0x180031c12  mov     r9d, 2
0x180031c18  lea     r8, [rbp+47h+var_B0]
0x180031c1c  jmp     short loc_180031C2C
0x180031c1e  cmp     al, 2
0x180031c20  jnz     short loc_180031C3C
0x180031c22  mov     r9d, 4; SourceSize
0x180031c28  lea     r8, [rbp+47h+Source]; Source
0x180031c2c  mov     rcx, [rbp+47h+Buf2]; Destination
0x180031c30  mov     rdx, r9; DestinationSize
0x180031c33  call    cs:__imp_memcpy_s
0x180031c39  mov     edx, [rbp+47h+Source]
0x180031c3c  mov     ebx, edx
0x180031c3e  imul    rbx, [rdi+10h]
0x180031c43  add     rbx, rsi
0x180031c46  jmp     loc_180031CD2
0x180031c4b  movzx   eax, word ptr [rdi+6]
0x180031c4f  xorps   xmm0, xmm0
0x180031c52  mov     [rbp+47h+var_60], ax
0x180031c56  mov     esi, r9d
0x180031c59  mov     al, [rdi+8]
0x180031c5c  mov     [rbp+47h+var_5E], al
0x180031c5f  mov     eax, [rbp+47h+Source]
0x180031c62  mov     [rbp+47h+var_5C], r9d
0x180031c66  mov     [rbp+47h+var_58], r9w
0x180031c6b  movdqu  [rbp+47h+var_50], xmm0
0x180031c70  test    eax, eax
0x180031c72  jz      short loc_180031C96
0x180031c74  mov     r8, [rdi+20h]; unsigned __int8 *
0x180031c78  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180031c7c  lea     rcx, [rbp+47h+var_60]; this
0x180031c80  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180031c85  test    al, al
0x180031c87  mov     eax, [rbp+47h+Source]
0x180031c8a  jz      short loc_180031C92
0x180031c8c  inc     esi
0x180031c8e  cmp     esi, eax
0x180031c90  jb      short loc_180031C74
0x180031c92  mov     rbx, [rbp+47h+var_A8]
0x180031c96  cmp     eax, esi
0x180031c98  jz      short loc_180031CD2
0x180031c9a  mov     al, [rbp+47h+var_9E]
0x180031c9d  mov     [rbp+47h+Source], esi
0x180031ca0  cmp     al, 1
0x180031ca2  jnz     short loc_180031CB8
0x180031ca4  mov     eax, 2
0x180031ca9  mov     [rbp+47h+var_B0], si
0x180031cad  mov     r9d, eax
0x180031cb0  lea     r8, [rbp+47h+var_B0]
0x180031cb4  mov     edx, eax
0x180031cb6  jmp     short loc_180031CC8
0x180031cb8  cmp     al, 2
0x180031cba  jnz     short loc_180031CD2
0x180031cbc  mov     edx, 4; DestinationSize
0x180031cc1  lea     r8, [rbp+47h+Source]; Source
0x180031cc5  mov     r9d, edx; SourceSize
0x180031cc8  mov     rcx, [rbp+47h+Buf2]; Destination
0x180031ccc  call    cs:__imp_memcpy_s
0x180031cd2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180031cd6  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180031cda  lea     rcx, [rbp+47h+var_A0]; this
0x180031cde  mov     [rbp+47h+var_A8], rbx
0x180031ce2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180031ce7  xor     r9d, r9d
0x180031cea  mov     sil, al
0x180031ced  test    al, al
0x180031cef  jnz     loc_180031B9E
0x180031cf5  mov     rbx, [rbp+47h+var_A8]
0x180031cf9  mov     [rdi+20h], rbx
0x180031cfd  mov     rcx, r9
0x180031d00  cmp     byte ptr [rbp+47h+arg_0], r9b
0x180031d04  jnz     loc_180031D8F
0x180031d0a  movzx   eax, [rbp+47h+var_A0]
0x180031d0e  mov     [rbp+47h+Source], 1
0x180031d15  mov     [rbp+47h+var_98], r14w
0x180031d1a  mov     [rbp+47h+Buf2], r9
0x180031d1e  mov     [rbp+47h+Buf2+8], r15
0x180031d22  test    ax, ax
0x180031d25  jnz     short loc_180031D77
0x180031d27  movzx   ecx, r14w
0x180031d2b  add     rcx, 2
0x180031d2f  jmp     short loc_180031D7A
0x180031d31  mov     eax, [rbp+47h+arg_28]
0x180031d34  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180031d38  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180031d3c  mov     r9, r13; void *
0x180031d3f  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x180031d43  mov     rcx, rdi; this
0x180031d46  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180031d4b  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180031d50  xor     r9d, r9d
0x180031d53  mov     [rbp+47h+var_A8], rax
0x180031d57  mov     rbx, rax
0x180031d5a  test    rax, rax
0x180031d5d  jnz     short loc_180031D66
0x180031d5f  mov     al, 1
0x180031d61  jmp     loc_180031E94
0x180031d66  mov     byte ptr [rbp+47h+arg_0], 1
0x180031d6a  jmp     short loc_180031D70
0x180031d6c  mov     [rbp+47h+var_A8], rbx
0x180031d70  test    sil, sil
0x180031d73  jnz     short loc_180031CFD
0x180031d75  jmp     short loc_180031CF9
0x180031d77  mov     rcx, rax
0x180031d7a  mov     al, [rbp+47h+var_9E]
0x180031d7d  cmp     al, 1
0x180031d7f  jnz     short loc_180031D87
0x180031d81  add     rcx, 2
0x180031d85  jmp     short loc_180031D8F
0x180031d87  cmp     al, 2
0x180031d89  jnz     short loc_180031D8F
0x180031d8b  add     rcx, 4
0x180031d8f  movzx   eax, word ptr [rdi+6]
0x180031d93  mov     dl, [rdi+8]
0x180031d96  mov     r8d, [rbp+47h+arg_28]
0x180031d9a  mov     [rbp+47h+var_80], ax
0x180031d9e  mov     [rbp+47h+var_7E], dl
0x180031da1  mov     [rbp+47h+var_7C], r8d
0x180031da5  mov     [rbp+47h+var_78], r12w
0x180031daa  mov     [rbp+47h+var_70], r9
0x180031dae  mov     [rbp+47h+var_68], r13
0x180031db2  test    ax, ax
0x180031db5  jnz     short loc_180031DBF
0x180031db7  movzx   eax, r12w
0x180031dbb  add     rax, 2
0x180031dbf  cmp     dl, 1
0x180031dc2  jnz     short loc_180031DCA
0x180031dc4  add     rax, 2
0x180031dc8  jmp     short loc_180031DD3
0x180031dca  cmp     dl, 2
0x180031dcd  jnz     short loc_180031DD3
0x180031dcf  add     rax, 4
0x180031dd3  mov     rdx, [rdi+28h]
0x180031dd7  lea     rsi, [rax+rcx]
0x180031ddb  mov     r9, [rdi+20h]
0x180031ddf  mov     rcx, rdx
0x180031de2  sub     rcx, r9
0x180031de5  cmp     r9, rdx
0x180031de8  sbb     rax, rax
0x180031deb  and     rax, rcx
0x180031dee  cmp     rax, rsi
0x180031df1  jb      loc_180031E92
0x180031df7  sub     rdx, rsi
0x180031dfa  lea     rcx, [rsi+rbx]; Destination
0x180031dfe  sub     rdx, rbx; DestinationSize
0x180031e01  sub     r9, rbx; SourceSize
0x180031e04  mov     r8, rbx; Source
0x180031e07  call    cs:__imp_memmove_s
0x180031e0d  add     [rdi+20h], rsi
0x180031e11  xor     ebx, ebx
0x180031e13  cmp     byte ptr [rbp+47h+arg_0], bl
0x180031e16  jnz     short loc_180031E2B
0x180031e18  mov     r8, [rdi+20h]; unsigned __int8 *
0x180031e1c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180031e20  lea     rcx, [rbp+47h+var_A0]; this
0x180031e24  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180031e29  jmp     short loc_180031E78
0x180031e2b  mov     cl, [rbp+47h+var_9E]
0x180031e2e  test    cl, cl
0x180031e30  jz      short loc_180031E78
0x180031e32  mov     eax, [rbp+47h+Source]
0x180031e35  lea     r8d, [rax+1]
0x180031e39  cmp     eax, r8d
0x180031e3c  jz      short loc_180031E78
0x180031e3e  mov     [rbp+47h+Source], r8d
0x180031e42  cmp     cl, 1
0x180031e45  jnz     short loc_180031E5B
0x180031e47  mov     r9d, 2
0x180031e4d  mov     [rbp+47h+arg_0], r8w
0x180031e52  mov     edx, r9d
0x180031e55  lea     r8, [rbp+47h+arg_0]
0x180031e59  jmp     short loc_180031E6E
0x180031e5b  cmp     cl, 2
0x180031e5e  jnz     short loc_180031E78
0x180031e60  mov     eax, 4
0x180031e65  lea     r8, [rbp+47h+Source]; Source
0x180031e69  mov     r9d, eax; SourceSize
0x180031e6c  mov     edx, eax; DestinationSize
0x180031e6e  mov     rcx, [rbp+47h+Buf2]; Destination
0x180031e72  call    cs:__imp_memcpy_s
0x180031e78  mov     r8, [rdi+20h]; unsigned __int8 *
0x180031e7c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180031e80  lea     rcx, [rbp+47h+var_80]; this
0x180031e84  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180031e89  mov     byte ptr [rdi+38h], 1
0x180031e8d  jmp     loc_180031D5F
0x180031e92  xor     al, al
0x180031e94  add     rsp, 0A8h
0x180031e9b  pop     r15
0x180031e9d  pop     r14
0x180031e9f  pop     r13
0x180031ea1  pop     r12
0x180031ea3  pop     rdi
0x180031ea4  pop     rsi
0x180031ea5  pop     rbx
0x180031ea6  pop     rbp
0x180031ea7  retn
```
