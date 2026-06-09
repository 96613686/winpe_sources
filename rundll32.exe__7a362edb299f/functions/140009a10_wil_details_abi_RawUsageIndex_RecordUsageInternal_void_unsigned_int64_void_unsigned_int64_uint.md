# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140009a10`
- end: `0x140009d8d`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `893`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009860`

## callees

- `0x14000220c`
- `0x140008edc`
- `0x140009454`
- `0x140009a10`
- `0x14000a9c4`
- `0x14000b1d4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x140009ced`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x140009ced`

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
0x140009a10  push    rbp
0x140009a12  push    rbx
0x140009a13  push    rsi
0x140009a14  push    rdi
0x140009a15  push    r12
0x140009a17  push    r13
0x140009a19  push    r14
0x140009a1b  push    r15
0x140009a1d  lea     rbp, [rsp-0Fh]
0x140009a22  sub     rsp, 0A8h
0x140009a29  mov     rbx, [rcx+18h]
0x140009a2d  mov     rdi, rcx
0x140009a30  xor     ecx, ecx
0x140009a32  mov     r13, r9
0x140009a35  mov     r14, r8
0x140009a38  mov     r15, rdx
0x140009a3b  test    rbx, rbx
0x140009a3e  jz      loc_140009D77
0x140009a44  movzx   eax, word ptr [rdi+2]
0x140009a48  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009a4c  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009a50  add     rbx, 0Ah
0x140009a54  mov     [rbp+47h+var_A0], ax
0x140009a58  xorps   xmm0, xmm0
0x140009a5b  mov     al, [rdi+4]
0x140009a5e  mov     [rbp+47h+Source], ecx
0x140009a61  mov     [rbp+47h+var_98], cx
0x140009a65  mov     byte ptr [rbp+47h+arg_0], cl
0x140009a68  lea     rcx, [rbp+47h+var_A0]; this
0x140009a6c  mov     [rbp+47h+var_9E], al
0x140009a6f  mov     [rbp+47h+var_A8], rbx
0x140009a73  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x140009a78  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009a7d  mov     r12, [rbp+47h+arg_20]
0x140009a81  jmp     loc_140009BCD
0x140009a86  movzx   eax, [rbp+47h+var_98]
0x140009a8a  cmp     r14, rax
0x140009a8d  jnz     short loc_140009AA5
0x140009a8f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x140009a93  mov     r8, r14; Size
0x140009a96  mov     rcx, r15; Buf1
0x140009a99  call    memcmp_0
0x140009a9e  mov     ecx, eax
0x140009aa0  xor     r9d, r9d
0x140009aa3  jmp     short loc_140009AAE
0x140009aa5  movzx   eax, [rbp+47h+var_98]
0x140009aa9  mov     ecx, r14d
0x140009aac  sub     ecx, eax
0x140009aae  test    ecx, ecx
0x140009ab0  js      loc_140009C52
0x140009ab6  jz      loc_140009C17
0x140009abc  mov     rbx, [rbp+47h+var_A8]
0x140009ac0  mov     [rbp+47h+var_A8], rbx
0x140009ac4  cmp     [rdi+10h], r9
0x140009ac8  jbe     short loc_140009B32
0x140009aca  mov     rax, [rdi+20h]
0x140009ace  xor     edx, edx
0x140009ad0  sub     rax, [rdi+18h]
0x140009ad4  mov     rsi, rbx
0x140009ad7  div     qword ptr [rdi+10h]
0x140009adb  mov     edx, [rbp+47h+Source]
0x140009ade  cmp     rdx, rax
0x140009ae1  jbe     short loc_140009B23
0x140009ae3  cmp     edx, eax
0x140009ae5  jz      short loc_140009B23
0x140009ae7  mov     edx, eax
0x140009ae9  mov     [rbp+47h+Source], eax
0x140009aec  mov     al, [rbp+47h+var_9E]
0x140009aef  cmp     al, 1
0x140009af1  jnz     short loc_140009B06
0x140009af3  movzx   eax, dx
0x140009af6  mov     [rbp+47h+var_B0], dx
0x140009afa  mov     r9d, 2
0x140009b00  lea     r8, [rbp+47h+var_B0]
0x140009b04  jmp     short loc_140009B14
0x140009b06  cmp     al, 2
0x140009b08  jnz     short loc_140009B23
0x140009b0a  mov     r9d, 4; SourceSize
0x140009b10  lea     r8, [rbp+47h+Source]; Source
0x140009b14  mov     rcx, [rbp+47h+Buf2]; Destination
0x140009b18  mov     rdx, r9; DestinationSize
0x140009b1b  call    memcpy_s
0x140009b20  mov     edx, [rbp+47h+Source]
0x140009b23  mov     ebx, edx
0x140009b25  imul    rbx, [rdi+10h]
0x140009b2a  add     rbx, rsi
0x140009b2d  jmp     loc_140009BB8
0x140009b32  movzx   eax, word ptr [rdi+6]
0x140009b36  xorps   xmm0, xmm0
0x140009b39  mov     [rbp+47h+var_60], ax
0x140009b3d  mov     esi, r9d
0x140009b40  mov     al, [rdi+8]
0x140009b43  mov     [rbp+47h+var_5E], al
0x140009b46  mov     eax, [rbp+47h+Source]
0x140009b49  mov     [rbp+47h+var_5C], r9d
0x140009b4d  mov     [rbp+47h+var_58], r9w
0x140009b52  movdqu  [rbp+47h+var_50], xmm0
0x140009b57  test    eax, eax
0x140009b59  jz      short loc_140009B7D
0x140009b5b  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009b5f  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009b63  lea     rcx, [rbp+47h+var_60]; this
0x140009b67  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009b6c  test    al, al
0x140009b6e  mov     eax, [rbp+47h+Source]
0x140009b71  jz      short loc_140009B79
0x140009b73  inc     esi
0x140009b75  cmp     esi, eax
0x140009b77  jb      short loc_140009B5B
0x140009b79  mov     rbx, [rbp+47h+var_A8]
0x140009b7d  cmp     eax, esi
0x140009b7f  jz      short loc_140009BB8
0x140009b81  mov     al, [rbp+47h+var_9E]
0x140009b84  mov     [rbp+47h+Source], esi
0x140009b87  cmp     al, 1
0x140009b89  jnz     short loc_140009B9F
0x140009b8b  mov     eax, 2
0x140009b90  mov     [rbp+47h+var_B0], si
0x140009b94  mov     r9d, eax
0x140009b97  lea     r8, [rbp+47h+var_B0]
0x140009b9b  mov     edx, eax
0x140009b9d  jmp     short loc_140009BAF
0x140009b9f  cmp     al, 2
0x140009ba1  jnz     short loc_140009BB8
0x140009ba3  mov     edx, 4; DestinationSize
0x140009ba8  lea     r8, [rbp+47h+Source]; Source
0x140009bac  mov     r9d, edx; SourceSize
0x140009baf  mov     rcx, [rbp+47h+Buf2]; Destination
0x140009bb3  call    memcpy_s
0x140009bb8  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009bbc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009bc0  lea     rcx, [rbp+47h+var_A0]; this
0x140009bc4  mov     [rbp+47h+var_A8], rbx
0x140009bc8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009bcd  xor     r9d, r9d
0x140009bd0  mov     sil, al
0x140009bd3  test    al, al
0x140009bd5  jnz     loc_140009A86
0x140009bdb  mov     rbx, [rbp+47h+var_A8]
0x140009bdf  mov     [rdi+20h], rbx
0x140009be3  mov     rcx, r9
0x140009be6  cmp     byte ptr [rbp+47h+arg_0], r9b
0x140009bea  jnz     loc_140009C75
0x140009bf0  movzx   eax, [rbp+47h+var_A0]
0x140009bf4  mov     [rbp+47h+Source], 1
0x140009bfb  mov     [rbp+47h+var_98], r14w
0x140009c00  mov     [rbp+47h+Buf2], r9
0x140009c04  mov     [rbp+47h+Buf2+8], r15
0x140009c08  test    ax, ax
0x140009c0b  jnz     short loc_140009C5D
0x140009c0d  movzx   ecx, r14w
0x140009c11  add     rcx, 2
0x140009c15  jmp     short loc_140009C60
0x140009c17  mov     eax, [rbp+47h+arg_28]
0x140009c1a  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x140009c1e  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x140009c22  mov     r9, r13; void *
0x140009c25  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x140009c29  mov     rcx, rdi; this
0x140009c2c  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x140009c31  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x140009c36  xor     r9d, r9d
0x140009c39  mov     [rbp+47h+var_A8], rax
0x140009c3d  mov     rbx, rax
0x140009c40  test    rax, rax
0x140009c43  jnz     short loc_140009C4C
0x140009c45  mov     al, 1
0x140009c47  jmp     loc_140009D79
0x140009c4c  mov     byte ptr [rbp+47h+arg_0], 1
0x140009c50  jmp     short loc_140009C56
0x140009c52  mov     [rbp+47h+var_A8], rbx
0x140009c56  test    sil, sil
0x140009c59  jnz     short loc_140009BE3
0x140009c5b  jmp     short loc_140009BDF
0x140009c5d  mov     rcx, rax
0x140009c60  mov     al, [rbp+47h+var_9E]
0x140009c63  cmp     al, 1
0x140009c65  jnz     short loc_140009C6D
0x140009c67  add     rcx, 2
0x140009c6b  jmp     short loc_140009C75
0x140009c6d  cmp     al, 2
0x140009c6f  jnz     short loc_140009C75
0x140009c71  add     rcx, 4
0x140009c75  movzx   eax, word ptr [rdi+6]
0x140009c79  mov     dl, [rdi+8]
0x140009c7c  mov     r8d, [rbp+47h+arg_28]
0x140009c80  mov     [rbp+47h+var_80], ax
0x140009c84  mov     [rbp+47h+var_7E], dl
0x140009c87  mov     [rbp+47h+var_7C], r8d
0x140009c8b  mov     [rbp+47h+var_78], r12w
0x140009c90  mov     [rbp+47h+var_70], r9
0x140009c94  mov     [rbp+47h+var_68], r13
0x140009c98  test    ax, ax
0x140009c9b  jnz     short loc_140009CA5
0x140009c9d  movzx   eax, r12w
0x140009ca1  add     rax, 2
0x140009ca5  cmp     dl, 1
0x140009ca8  jnz     short loc_140009CB0
0x140009caa  add     rax, 2
0x140009cae  jmp     short loc_140009CB9
0x140009cb0  cmp     dl, 2
0x140009cb3  jnz     short loc_140009CB9
0x140009cb5  add     rax, 4
0x140009cb9  mov     rdx, [rdi+28h]
0x140009cbd  lea     rsi, [rax+rcx]
0x140009cc1  mov     r9, [rdi+20h]
0x140009cc5  mov     rcx, rdx
0x140009cc8  sub     rcx, r9
0x140009ccb  cmp     r9, rdx
0x140009cce  sbb     rax, rax
0x140009cd1  and     rax, rcx
0x140009cd4  cmp     rax, rsi
0x140009cd7  jb      loc_140009D77
0x140009cdd  sub     rdx, rsi
0x140009ce0  lea     rcx, [rsi+rbx]; Destination
0x140009ce4  sub     rdx, rbx; DestinationSize
0x140009ce7  sub     r9, rbx; SourceSize
0x140009cea  mov     r8, rbx; Source
0x140009ced  call    cs:__imp_memmove_s
0x140009cf3  add     [rdi+20h], rsi
0x140009cf7  xor     ebx, ebx
0x140009cf9  cmp     byte ptr [rbp+47h+arg_0], bl
0x140009cfc  jnz     short loc_140009D11
0x140009cfe  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009d02  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009d06  lea     rcx, [rbp+47h+var_A0]; this
0x140009d0a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140009d0f  jmp     short loc_140009D5D
0x140009d11  mov     cl, [rbp+47h+var_9E]
0x140009d14  test    cl, cl
0x140009d16  jz      short loc_140009D5D
0x140009d18  mov     eax, [rbp+47h+Source]
0x140009d1b  lea     r8d, [rax+1]
0x140009d1f  cmp     eax, r8d
0x140009d22  jz      short loc_140009D5D
0x140009d24  mov     [rbp+47h+Source], r8d
0x140009d28  cmp     cl, 1
0x140009d2b  jnz     short loc_140009D41
0x140009d2d  mov     r9d, 2
0x140009d33  mov     [rbp+47h+arg_0], r8w
0x140009d38  mov     edx, r9d
0x140009d3b  lea     r8, [rbp+47h+arg_0]
0x140009d3f  jmp     short loc_140009D54
0x140009d41  cmp     cl, 2
0x140009d44  jnz     short loc_140009D5D
0x140009d46  mov     eax, 4
0x140009d4b  lea     r8, [rbp+47h+Source]; Source
0x140009d4f  mov     r9d, eax; SourceSize
0x140009d52  mov     edx, eax; DestinationSize
0x140009d54  mov     rcx, [rbp+47h+Buf2]; Destination
0x140009d58  call    memcpy_s
0x140009d5d  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009d61  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x140009d65  lea     rcx, [rbp+47h+var_80]; this
0x140009d69  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140009d6e  mov     byte ptr [rdi+38h], 1
0x140009d72  jmp     loc_140009C45
0x140009d77  xor     al, al
0x140009d79  add     rsp, 0A8h
0x140009d80  pop     r15
0x140009d82  pop     r14
0x140009d84  pop     r13
0x140009d86  pop     r12
0x140009d88  pop     rdi
0x140009d89  pop     rsi
0x140009d8a  pop     rbx
0x140009d8b  pop     rbp
0x140009d8c  retn
```
