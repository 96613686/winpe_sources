# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000c794`
- end: `0x18000cb45`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `945`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c61c`

## callees

- `0x18000a95c`
- `0x18000c13c`
- `0x18000c794`
- `0x18000e498`
- `0x180030356`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000ca86`
- `msvcrt!memmove_s` at `0x18000ca86`
- `msvcrt!memcpy_s` at `0x18000c8a6`
- `msvcrt!memcpy_s` at `0x18000c945`
- `msvcrt!memcpy_s` at `0x18000cafb`
- `msvcrt!memcpy_s` at `0x18000c8a6`
- `msvcrt!memcpy_s` at `0x18000c945`
- `msvcrt!memcpy_s` at `0x18000cafb`

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
0x18000c794  mov     rax, rsp
0x18000c797  mov     [rax+10h], rbx
0x18000c79b  mov     [rax+18h], rsi
0x18000c79f  mov     [rax+20h], rdi
0x18000c7a3  push    rbp
0x18000c7a4  push    r12
0x18000c7a6  push    r13
0x18000c7a8  push    r14
0x18000c7aa  push    r15
0x18000c7ac  lea     rbp, [rax-4Fh]
0x18000c7b0  sub     rsp, 0A0h
0x18000c7b7  mov     rdi, [rcx+18h]
0x18000c7bb  mov     rbx, rcx
0x18000c7be  xor     ecx, ecx
0x18000c7c0  mov     r13, r9
0x18000c7c3  mov     r14, r8
0x18000c7c6  mov     r15, rdx
0x18000c7c9  test    rdi, rdi
0x18000c7cc  jz      loc_18000CB21
0x18000c7d2  movzx   eax, word ptr [rbx+2]
0x18000c7d6  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000c7da  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000c7de  add     rdi, 0Ah
0x18000c7e2  mov     [rbp+47h+var_88], ax
0x18000c7e6  xorps   xmm0, xmm0
0x18000c7e9  mov     al, [rbx+4]
0x18000c7ec  mov     [rbp+47h+Source], ecx
0x18000c7ef  mov     [rbp+47h+var_80], cx
0x18000c7f3  mov     byte ptr [rbp+47h+arg_0], cl
0x18000c7f6  lea     rcx, [rbp+47h+var_88]; this
0x18000c7fa  mov     [rbp+47h+var_86], al
0x18000c7fd  mov     [rbp+47h+var_90], rdi
0x18000c801  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000c806  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000c80b  mov     r12, [rbp+47h+arg_20]
0x18000c80f  jmp     loc_18000C966
0x18000c814  movzx   ecx, [rbp+47h+var_80]
0x18000c818  cmp     r14, rcx
0x18000c81b  jnz     short loc_18000C833
0x18000c81d  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000c821  mov     r8, r14; Size
0x18000c824  mov     rcx, r15; Buf1
0x18000c827  call    memcmp_0
0x18000c82c  mov     ecx, eax
0x18000c82e  xor     r9d, r9d
0x18000c831  jmp     short loc_18000C83C
0x18000c833  movzx   eax, [rbp+47h+var_80]
0x18000c837  mov     ecx, r14d
0x18000c83a  sub     ecx, eax
0x18000c83c  test    ecx, ecx
0x18000c83e  js      loc_18000C9EB
0x18000c844  jz      loc_18000C9B0
0x18000c84a  mov     rdi, [rbp+47h+var_90]
0x18000c84e  mov     [rbp+47h+var_90], rdi
0x18000c852  cmp     [rbx+10h], r9
0x18000c856  jbe     short loc_18000C8C4
0x18000c858  mov     rax, [rbx+20h]
0x18000c85c  xor     edx, edx
0x18000c85e  sub     rax, [rbx+18h]
0x18000c862  div     qword ptr [rbx+10h]
0x18000c866  mov     edx, [rbp+47h+Source]
0x18000c869  cmp     rdx, rax
0x18000c86c  jbe     short loc_18000C8B5
0x18000c86e  cmp     edx, eax
0x18000c870  jz      short loc_18000C8B5
0x18000c872  mov     edx, eax
0x18000c874  mov     [rbp+47h+Source], eax
0x18000c877  mov     al, [rbp+47h+var_86]
0x18000c87a  cmp     al, 1
0x18000c87c  jnz     short loc_18000C891
0x18000c87e  movzx   eax, dx
0x18000c881  mov     [rbp+47h+var_68], dx
0x18000c885  mov     r9d, 2
0x18000c88b  lea     r8, [rbp+47h+var_68]
0x18000c88f  jmp     short loc_18000C89F
0x18000c891  cmp     al, 2
0x18000c893  jnz     short loc_18000C8B5
0x18000c895  mov     r9d, 4; SourceSize
0x18000c89b  lea     r8, [rbp+47h+Source]; Source
0x18000c89f  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000c8a3  mov     rdx, r9; DestinationSize
0x18000c8a6  call    cs:__imp_memcpy_s
0x18000c8ad  nop     dword ptr [rax+rax+00h]
0x18000c8b2  mov     edx, [rbp+47h+Source]
0x18000c8b5  mov     eax, edx
0x18000c8b7  imul    rax, [rbx+10h]
0x18000c8bc  add     rdi, rax
0x18000c8bf  jmp     loc_18000C951
0x18000c8c4  movzx   eax, word ptr [rbx+6]
0x18000c8c8  xorps   xmm0, xmm0
0x18000c8cb  mov     [rbp+47h+var_40], ax
0x18000c8cf  mov     esi, r9d
0x18000c8d2  mov     al, [rbx+8]
0x18000c8d5  mov     [rbp+47h+var_3E], al
0x18000c8d8  mov     eax, [rbp+47h+Source]
0x18000c8db  mov     [rbp+47h+var_3C], r9d
0x18000c8df  mov     [rbp+47h+var_38], r9w
0x18000c8e4  movdqu  [rbp+47h+var_30], xmm0
0x18000c8e9  test    eax, eax
0x18000c8eb  jz      short loc_18000C90F
0x18000c8ed  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000c8f1  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000c8f5  lea     rcx, [rbp+47h+var_40]; this
0x18000c8f9  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000c8fe  test    al, al
0x18000c900  mov     eax, [rbp+47h+Source]
0x18000c903  jz      short loc_18000C90B
0x18000c905  inc     esi
0x18000c907  cmp     esi, eax
0x18000c909  jb      short loc_18000C8ED
0x18000c90b  mov     rdi, [rbp+47h+var_90]
0x18000c90f  cmp     eax, esi
0x18000c911  jz      short loc_18000C951
0x18000c913  mov     al, [rbp+47h+var_86]
0x18000c916  mov     [rbp+47h+Source], esi
0x18000c919  cmp     al, 1
0x18000c91b  jnz     short loc_18000C931
0x18000c91d  mov     eax, 2
0x18000c922  mov     [rbp+47h+var_64], si
0x18000c926  mov     r9d, eax
0x18000c929  lea     r8, [rbp+47h+var_64]
0x18000c92d  mov     edx, eax
0x18000c92f  jmp     short loc_18000C941
0x18000c931  cmp     al, 2
0x18000c933  jnz     short loc_18000C951
0x18000c935  mov     edx, 4; DestinationSize
0x18000c93a  lea     r8, [rbp+47h+Source]; Source
0x18000c93e  mov     r9d, edx; SourceSize
0x18000c941  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000c945  call    cs:__imp_memcpy_s
0x18000c94c  nop     dword ptr [rax+rax+00h]
0x18000c951  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000c955  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000c959  lea     rcx, [rbp+47h+var_88]; this
0x18000c95d  mov     [rbp+47h+var_90], rdi
0x18000c961  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000c966  xor     r9d, r9d
0x18000c969  mov     sil, al
0x18000c96c  test    al, al
0x18000c96e  jnz     loc_18000C814
0x18000c974  mov     rdi, [rbp+47h+var_90]
0x18000c978  mov     [rbx+20h], rdi
0x18000c97c  mov     rcx, r9
0x18000c97f  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000c983  jnz     loc_18000CA0E
0x18000c989  movzx   eax, [rbp+47h+var_88]
0x18000c98d  mov     [rbp+47h+Source], 1
0x18000c994  mov     [rbp+47h+var_80], r14w
0x18000c999  mov     [rbp+47h+Buf2], r9
0x18000c99d  mov     [rbp+47h+Buf2+8], r15
0x18000c9a1  test    ax, ax
0x18000c9a4  jnz     short loc_18000C9F6
0x18000c9a6  movzx   ecx, r14w
0x18000c9aa  add     rcx, 2
0x18000c9ae  jmp     short loc_18000C9F9
0x18000c9b0  mov     eax, [rbp+47h+arg_28]
0x18000c9b3  lea     rdx, [rbp+47h+var_88]; struct wil::details_abi::UsageIndexProperty *
0x18000c9b7  mov     r8, [rbp+47h+var_90]; unsigned __int8 *
0x18000c9bb  mov     r9, r13; void *
0x18000c9be  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18000c9c2  mov     rcx, rbx; this
0x18000c9c5  mov     [rsp+0C0h+Size], r12; Size
0x18000c9ca  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000c9cf  xor     r9d, r9d
0x18000c9d2  mov     [rbp+47h+var_90], rax
0x18000c9d6  mov     rdi, rax
0x18000c9d9  test    rax, rax
0x18000c9dc  jnz     short loc_18000C9E5
0x18000c9de  mov     al, 1
0x18000c9e0  jmp     loc_18000CB23
0x18000c9e5  mov     byte ptr [rbp+47h+arg_0], 1
0x18000c9e9  jmp     short loc_18000C9EF
0x18000c9eb  mov     [rbp+47h+var_90], rdi
0x18000c9ef  test    sil, sil
0x18000c9f2  jnz     short loc_18000C97C
0x18000c9f4  jmp     short loc_18000C978
0x18000c9f6  mov     rcx, rax
0x18000c9f9  mov     al, [rbp+47h+var_86]
0x18000c9fc  cmp     al, 1
0x18000c9fe  jnz     short loc_18000CA06
0x18000ca00  add     rcx, 2
0x18000ca04  jmp     short loc_18000CA0E
0x18000ca06  cmp     al, 2
0x18000ca08  jnz     short loc_18000CA0E
0x18000ca0a  add     rcx, 4
0x18000ca0e  movzx   eax, word ptr [rbx+6]
0x18000ca12  mov     dl, [rbx+8]
0x18000ca15  mov     r8d, [rbp+47h+arg_28]
0x18000ca19  mov     [rbp+47h+var_60], ax
0x18000ca1d  mov     [rbp+47h+var_5E], dl
0x18000ca20  mov     [rbp+47h+var_5C], r8d
0x18000ca24  mov     [rbp+47h+var_58], r12w
0x18000ca29  mov     [rbp+47h+var_50], r9
0x18000ca2d  mov     [rbp+47h+var_48], r13
0x18000ca31  test    ax, ax
0x18000ca34  jnz     short loc_18000CA3E
0x18000ca36  movzx   eax, r12w
0x18000ca3a  add     rax, 2
0x18000ca3e  cmp     dl, 1
0x18000ca41  jnz     short loc_18000CA49
0x18000ca43  add     rax, 2
0x18000ca47  jmp     short loc_18000CA52
0x18000ca49  cmp     dl, 2
0x18000ca4c  jnz     short loc_18000CA52
0x18000ca4e  add     rax, 4
0x18000ca52  mov     rdx, [rbx+28h]
0x18000ca56  lea     rsi, [rax+rcx]
0x18000ca5a  mov     r9, [rbx+20h]
0x18000ca5e  mov     rcx, rdx
0x18000ca61  sub     rcx, r9
0x18000ca64  cmp     r9, rdx
0x18000ca67  sbb     rax, rax
0x18000ca6a  and     rax, rcx
0x18000ca6d  cmp     rax, rsi
0x18000ca70  jb      loc_18000CB21
0x18000ca76  sub     rdx, rsi
0x18000ca79  lea     rcx, [rsi+rdi]; Destination
0x18000ca7d  sub     rdx, rdi; DestinationSize
0x18000ca80  sub     r9, rdi; SourceSize
0x18000ca83  mov     r8, rdi; Source
0x18000ca86  call    cs:__imp_memmove_s
0x18000ca8d  nop     dword ptr [rax+rax+00h]
0x18000ca92  mov     r8, [rbx+20h]
0x18000ca96  xor     edi, edi
0x18000ca98  add     r8, rsi; unsigned __int8 *
0x18000ca9b  mov     [rbx+20h], r8
0x18000ca9f  cmp     byte ptr [rbp+47h+arg_0], dil
0x18000caa3  jnz     short loc_18000CAB4
0x18000caa5  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000caa9  lea     rcx, [rbp+47h+var_88]; this
0x18000caad  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000cab2  jmp     short loc_18000CB07
0x18000cab4  mov     cl, [rbp+47h+var_86]
0x18000cab7  test    cl, cl
0x18000cab9  jz      short loc_18000CB07
0x18000cabb  mov     eax, [rbp+47h+Source]
0x18000cabe  lea     r8d, [rax+1]
0x18000cac2  cmp     eax, r8d
0x18000cac5  jz      short loc_18000CB07
0x18000cac7  mov     [rbp+47h+Source], r8d
0x18000cacb  cmp     cl, 1
0x18000cace  jnz     short loc_18000CAE4
0x18000cad0  mov     r9d, 2
0x18000cad6  mov     [rbp+47h+arg_0], r8w
0x18000cadb  mov     edx, r9d
0x18000cade  lea     r8, [rbp+47h+arg_0]
0x18000cae2  jmp     short loc_18000CAF7
0x18000cae4  cmp     cl, 2
0x18000cae7  jnz     short loc_18000CB07
0x18000cae9  mov     eax, 4
0x18000caee  lea     r8, [rbp+47h+Source]; Source
0x18000caf2  mov     r9d, eax; SourceSize
0x18000caf5  mov     edx, eax; DestinationSize
0x18000caf7  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000cafb  call    cs:__imp_memcpy_s
0x18000cb02  nop     dword ptr [rax+rax+00h]
0x18000cb07  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000cb0b  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000cb0f  lea     rcx, [rbp+47h+var_60]; this
0x18000cb13  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000cb18  mov     byte ptr [rbx+38h], 1
0x18000cb1c  jmp     loc_18000C9DE
0x18000cb21  xor     al, al
0x18000cb23  lea     r11, [rsp+0C0h+var_20]
0x18000cb2b  mov     rbx, [r11+38h]
0x18000cb2f  mov     rsi, [r11+40h]
0x18000cb33  mov     rdi, [r11+48h]
0x18000cb37  mov     rsp, r11
0x18000cb3a  pop     r15
0x18000cb3c  pop     r14
0x18000cb3e  pop     r13
0x18000cb40  pop     r12
0x18000cb42  pop     rbp
0x18000cb43  retn
```
