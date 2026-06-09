# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000d924`
- end: `0x18000dcd5`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `945`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d7ac`

## callees

- `0x18000b290`
- `0x18000d03c`
- `0x18000d924`
- `0x180010928`
- `0x180011a56`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000dc16`
- `msvcrt!memmove_s` at `0x18000dc16`
- `msvcrt!memcpy_s` at `0x18000da36`
- `msvcrt!memcpy_s` at `0x18000dad5`
- `msvcrt!memcpy_s` at `0x18000dc8b`
- `msvcrt!memcpy_s` at `0x18000da36`
- `msvcrt!memcpy_s` at `0x18000dad5`
- `msvcrt!memcpy_s` at `0x18000dc8b`

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
0x18000d924  mov     rax, rsp
0x18000d927  mov     [rax+10h], rbx
0x18000d92b  mov     [rax+18h], rsi
0x18000d92f  mov     [rax+20h], rdi
0x18000d933  push    rbp
0x18000d934  push    r12
0x18000d936  push    r13
0x18000d938  push    r14
0x18000d93a  push    r15
0x18000d93c  lea     rbp, [rax-4Fh]
0x18000d940  sub     rsp, 0A0h
0x18000d947  mov     rdi, [rcx+18h]
0x18000d94b  mov     rbx, rcx
0x18000d94e  xor     ecx, ecx
0x18000d950  mov     r13, r9
0x18000d953  mov     r14, r8
0x18000d956  mov     r15, rdx
0x18000d959  test    rdi, rdi
0x18000d95c  jz      loc_18000DCB1
0x18000d962  movzx   eax, word ptr [rbx+2]
0x18000d966  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000d96a  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000d96e  add     rdi, 0Ah
0x18000d972  mov     [rbp+47h+var_88], ax
0x18000d976  xorps   xmm0, xmm0
0x18000d979  mov     al, [rbx+4]
0x18000d97c  mov     [rbp+47h+Source], ecx
0x18000d97f  mov     [rbp+47h+var_80], cx
0x18000d983  mov     byte ptr [rbp+47h+arg_0], cl
0x18000d986  lea     rcx, [rbp+47h+var_88]; this
0x18000d98a  mov     [rbp+47h+var_86], al
0x18000d98d  mov     [rbp+47h+var_90], rdi
0x18000d991  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000d996  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d99b  mov     r12, [rbp+47h+arg_20]
0x18000d99f  jmp     loc_18000DAF6
0x18000d9a4  movzx   ecx, [rbp+47h+var_80]
0x18000d9a8  cmp     r14, rcx
0x18000d9ab  jnz     short loc_18000D9C3
0x18000d9ad  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000d9b1  mov     r8, r14; Size
0x18000d9b4  mov     rcx, r15; Buf1
0x18000d9b7  call    memcmp_0
0x18000d9bc  mov     ecx, eax
0x18000d9be  xor     r9d, r9d
0x18000d9c1  jmp     short loc_18000D9CC
0x18000d9c3  movzx   eax, [rbp+47h+var_80]
0x18000d9c7  mov     ecx, r14d
0x18000d9ca  sub     ecx, eax
0x18000d9cc  test    ecx, ecx
0x18000d9ce  js      loc_18000DB7B
0x18000d9d4  jz      loc_18000DB40
0x18000d9da  mov     rdi, [rbp+47h+var_90]
0x18000d9de  mov     [rbp+47h+var_90], rdi
0x18000d9e2  cmp     [rbx+10h], r9
0x18000d9e6  jbe     short loc_18000DA54
0x18000d9e8  mov     rax, [rbx+20h]
0x18000d9ec  xor     edx, edx
0x18000d9ee  sub     rax, [rbx+18h]
0x18000d9f2  div     qword ptr [rbx+10h]
0x18000d9f6  mov     edx, [rbp+47h+Source]
0x18000d9f9  cmp     rdx, rax
0x18000d9fc  jbe     short loc_18000DA45
0x18000d9fe  cmp     edx, eax
0x18000da00  jz      short loc_18000DA45
0x18000da02  mov     edx, eax
0x18000da04  mov     [rbp+47h+Source], eax
0x18000da07  mov     al, [rbp+47h+var_86]
0x18000da0a  cmp     al, 1
0x18000da0c  jnz     short loc_18000DA21
0x18000da0e  movzx   eax, dx
0x18000da11  mov     [rbp+47h+var_68], dx
0x18000da15  mov     r9d, 2
0x18000da1b  lea     r8, [rbp+47h+var_68]
0x18000da1f  jmp     short loc_18000DA2F
0x18000da21  cmp     al, 2
0x18000da23  jnz     short loc_18000DA45
0x18000da25  mov     r9d, 4; SourceSize
0x18000da2b  lea     r8, [rbp+47h+Source]; Source
0x18000da2f  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000da33  mov     rdx, r9; DestinationSize
0x18000da36  call    cs:__imp_memcpy_s
0x18000da3d  nop     dword ptr [rax+rax+00h]
0x18000da42  mov     edx, [rbp+47h+Source]
0x18000da45  mov     eax, edx
0x18000da47  imul    rax, [rbx+10h]
0x18000da4c  add     rdi, rax
0x18000da4f  jmp     loc_18000DAE1
0x18000da54  movzx   eax, word ptr [rbx+6]
0x18000da58  xorps   xmm0, xmm0
0x18000da5b  mov     [rbp+47h+var_40], ax
0x18000da5f  mov     esi, r9d
0x18000da62  mov     al, [rbx+8]
0x18000da65  mov     [rbp+47h+var_3E], al
0x18000da68  mov     eax, [rbp+47h+Source]
0x18000da6b  mov     [rbp+47h+var_3C], r9d
0x18000da6f  mov     [rbp+47h+var_38], r9w
0x18000da74  movdqu  [rbp+47h+var_30], xmm0
0x18000da79  test    eax, eax
0x18000da7b  jz      short loc_18000DA9F
0x18000da7d  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000da81  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000da85  lea     rcx, [rbp+47h+var_40]; this
0x18000da89  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000da8e  test    al, al
0x18000da90  mov     eax, [rbp+47h+Source]
0x18000da93  jz      short loc_18000DA9B
0x18000da95  inc     esi
0x18000da97  cmp     esi, eax
0x18000da99  jb      short loc_18000DA7D
0x18000da9b  mov     rdi, [rbp+47h+var_90]
0x18000da9f  cmp     eax, esi
0x18000daa1  jz      short loc_18000DAE1
0x18000daa3  mov     al, [rbp+47h+var_86]
0x18000daa6  mov     [rbp+47h+Source], esi
0x18000daa9  cmp     al, 1
0x18000daab  jnz     short loc_18000DAC1
0x18000daad  mov     eax, 2
0x18000dab2  mov     [rbp+47h+var_64], si
0x18000dab6  mov     r9d, eax
0x18000dab9  lea     r8, [rbp+47h+var_64]
0x18000dabd  mov     edx, eax
0x18000dabf  jmp     short loc_18000DAD1
0x18000dac1  cmp     al, 2
0x18000dac3  jnz     short loc_18000DAE1
0x18000dac5  mov     edx, 4; DestinationSize
0x18000daca  lea     r8, [rbp+47h+Source]; Source
0x18000dace  mov     r9d, edx; SourceSize
0x18000dad1  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000dad5  call    cs:__imp_memcpy_s
0x18000dadc  nop     dword ptr [rax+rax+00h]
0x18000dae1  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000dae5  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000dae9  lea     rcx, [rbp+47h+var_88]; this
0x18000daed  mov     [rbp+47h+var_90], rdi
0x18000daf1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000daf6  xor     r9d, r9d
0x18000daf9  mov     sil, al
0x18000dafc  test    al, al
0x18000dafe  jnz     loc_18000D9A4
0x18000db04  mov     rdi, [rbp+47h+var_90]
0x18000db08  mov     [rbx+20h], rdi
0x18000db0c  mov     rcx, r9
0x18000db0f  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000db13  jnz     loc_18000DB9E
0x18000db19  movzx   eax, [rbp+47h+var_88]
0x18000db1d  mov     [rbp+47h+Source], 1
0x18000db24  mov     [rbp+47h+var_80], r14w
0x18000db29  mov     [rbp+47h+Buf2], r9
0x18000db2d  mov     [rbp+47h+Buf2+8], r15
0x18000db31  test    ax, ax
0x18000db34  jnz     short loc_18000DB86
0x18000db36  movzx   ecx, r14w
0x18000db3a  add     rcx, 2
0x18000db3e  jmp     short loc_18000DB89
0x18000db40  mov     eax, [rbp+47h+arg_28]
0x18000db43  lea     rdx, [rbp+47h+var_88]; struct wil::details_abi::UsageIndexProperty *
0x18000db47  mov     r8, [rbp+47h+var_90]; unsigned __int8 *
0x18000db4b  mov     r9, r13; void *
0x18000db4e  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18000db52  mov     rcx, rbx; this
0x18000db55  mov     [rsp+0C0h+Size], r12; Size
0x18000db5a  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000db5f  xor     r9d, r9d
0x18000db62  mov     [rbp+47h+var_90], rax
0x18000db66  mov     rdi, rax
0x18000db69  test    rax, rax
0x18000db6c  jnz     short loc_18000DB75
0x18000db6e  mov     al, 1
0x18000db70  jmp     loc_18000DCB3
0x18000db75  mov     byte ptr [rbp+47h+arg_0], 1
0x18000db79  jmp     short loc_18000DB7F
0x18000db7b  mov     [rbp+47h+var_90], rdi
0x18000db7f  test    sil, sil
0x18000db82  jnz     short loc_18000DB0C
0x18000db84  jmp     short loc_18000DB08
0x18000db86  mov     rcx, rax
0x18000db89  mov     al, [rbp+47h+var_86]
0x18000db8c  cmp     al, 1
0x18000db8e  jnz     short loc_18000DB96
0x18000db90  add     rcx, 2
0x18000db94  jmp     short loc_18000DB9E
0x18000db96  cmp     al, 2
0x18000db98  jnz     short loc_18000DB9E
0x18000db9a  add     rcx, 4
0x18000db9e  movzx   eax, word ptr [rbx+6]
0x18000dba2  mov     dl, [rbx+8]
0x18000dba5  mov     r8d, [rbp+47h+arg_28]
0x18000dba9  mov     [rbp+47h+var_60], ax
0x18000dbad  mov     [rbp+47h+var_5E], dl
0x18000dbb0  mov     [rbp+47h+var_5C], r8d
0x18000dbb4  mov     [rbp+47h+var_58], r12w
0x18000dbb9  mov     [rbp+47h+var_50], r9
0x18000dbbd  mov     [rbp+47h+var_48], r13
0x18000dbc1  test    ax, ax
0x18000dbc4  jnz     short loc_18000DBCE
0x18000dbc6  movzx   eax, r12w
0x18000dbca  add     rax, 2
0x18000dbce  cmp     dl, 1
0x18000dbd1  jnz     short loc_18000DBD9
0x18000dbd3  add     rax, 2
0x18000dbd7  jmp     short loc_18000DBE2
0x18000dbd9  cmp     dl, 2
0x18000dbdc  jnz     short loc_18000DBE2
0x18000dbde  add     rax, 4
0x18000dbe2  mov     rdx, [rbx+28h]
0x18000dbe6  lea     rsi, [rax+rcx]
0x18000dbea  mov     r9, [rbx+20h]
0x18000dbee  mov     rcx, rdx
0x18000dbf1  sub     rcx, r9
0x18000dbf4  cmp     r9, rdx
0x18000dbf7  sbb     rax, rax
0x18000dbfa  and     rax, rcx
0x18000dbfd  cmp     rax, rsi
0x18000dc00  jb      loc_18000DCB1
0x18000dc06  sub     rdx, rsi
0x18000dc09  lea     rcx, [rsi+rdi]; Destination
0x18000dc0d  sub     rdx, rdi; DestinationSize
0x18000dc10  sub     r9, rdi; SourceSize
0x18000dc13  mov     r8, rdi; Source
0x18000dc16  call    cs:__imp_memmove_s
0x18000dc1d  nop     dword ptr [rax+rax+00h]
0x18000dc22  mov     r8, [rbx+20h]
0x18000dc26  xor     edi, edi
0x18000dc28  add     r8, rsi; unsigned __int8 *
0x18000dc2b  mov     [rbx+20h], r8
0x18000dc2f  cmp     byte ptr [rbp+47h+arg_0], dil
0x18000dc33  jnz     short loc_18000DC44
0x18000dc35  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000dc39  lea     rcx, [rbp+47h+var_88]; this
0x18000dc3d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000dc42  jmp     short loc_18000DC97
0x18000dc44  mov     cl, [rbp+47h+var_86]
0x18000dc47  test    cl, cl
0x18000dc49  jz      short loc_18000DC97
0x18000dc4b  mov     eax, [rbp+47h+Source]
0x18000dc4e  lea     r8d, [rax+1]
0x18000dc52  cmp     eax, r8d
0x18000dc55  jz      short loc_18000DC97
0x18000dc57  mov     [rbp+47h+Source], r8d
0x18000dc5b  cmp     cl, 1
0x18000dc5e  jnz     short loc_18000DC74
0x18000dc60  mov     r9d, 2
0x18000dc66  mov     [rbp+47h+arg_0], r8w
0x18000dc6b  mov     edx, r9d
0x18000dc6e  lea     r8, [rbp+47h+arg_0]
0x18000dc72  jmp     short loc_18000DC87
0x18000dc74  cmp     cl, 2
0x18000dc77  jnz     short loc_18000DC97
0x18000dc79  mov     eax, 4
0x18000dc7e  lea     r8, [rbp+47h+Source]; Source
0x18000dc82  mov     r9d, eax; SourceSize
0x18000dc85  mov     edx, eax; DestinationSize
0x18000dc87  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000dc8b  call    cs:__imp_memcpy_s
0x18000dc92  nop     dword ptr [rax+rax+00h]
0x18000dc97  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000dc9b  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000dc9f  lea     rcx, [rbp+47h+var_60]; this
0x18000dca3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000dca8  mov     byte ptr [rbx+38h], 1
0x18000dcac  jmp     loc_18000DB6E
0x18000dcb1  xor     al, al
0x18000dcb3  lea     r11, [rsp+0C0h+var_20]
0x18000dcbb  mov     rbx, [r11+38h]
0x18000dcbf  mov     rsi, [r11+40h]
0x18000dcc3  mov     rdi, [r11+48h]
0x18000dcc7  mov     rsp, r11
0x18000dcca  pop     r15
0x18000dccc  pop     r14
0x18000dcce  pop     r13
0x18000dcd0  pop     r12
0x18000dcd2  pop     rbp
0x18000dcd3  retn
```
