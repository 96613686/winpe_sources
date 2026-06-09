# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000bc54`
- end: `0x18000c005`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `945`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000badc`

## callees

- `0x180009e1c`
- `0x18000b5fc`
- `0x18000bc54`
- `0x18000d958`
- `0x18002f396`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000bf46`
- `msvcrt!memmove_s` at `0x18000bf46`
- `msvcrt!memcpy_s` at `0x18000bd66`
- `msvcrt!memcpy_s` at `0x18000be05`
- `msvcrt!memcpy_s` at `0x18000bfbb`
- `msvcrt!memcpy_s` at `0x18000bd66`
- `msvcrt!memcpy_s` at `0x18000be05`
- `msvcrt!memcpy_s` at `0x18000bfbb`

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
0x18000bc54  mov     rax, rsp
0x18000bc57  mov     [rax+10h], rbx
0x18000bc5b  mov     [rax+18h], rsi
0x18000bc5f  mov     [rax+20h], rdi
0x18000bc63  push    rbp
0x18000bc64  push    r12
0x18000bc66  push    r13
0x18000bc68  push    r14
0x18000bc6a  push    r15
0x18000bc6c  lea     rbp, [rax-4Fh]
0x18000bc70  sub     rsp, 0A0h
0x18000bc77  mov     rdi, [rcx+18h]
0x18000bc7b  mov     rbx, rcx
0x18000bc7e  xor     ecx, ecx
0x18000bc80  mov     r13, r9
0x18000bc83  mov     r14, r8
0x18000bc86  mov     r15, rdx
0x18000bc89  test    rdi, rdi
0x18000bc8c  jz      loc_18000BFE1
0x18000bc92  movzx   eax, word ptr [rbx+2]
0x18000bc96  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000bc9a  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000bc9e  add     rdi, 0Ah
0x18000bca2  mov     [rbp+47h+var_88], ax
0x18000bca6  xorps   xmm0, xmm0
0x18000bca9  mov     al, [rbx+4]
0x18000bcac  mov     [rbp+47h+Source], ecx
0x18000bcaf  mov     [rbp+47h+var_80], cx
0x18000bcb3  mov     byte ptr [rbp+47h+arg_0], cl
0x18000bcb6  lea     rcx, [rbp+47h+var_88]; this
0x18000bcba  mov     [rbp+47h+var_86], al
0x18000bcbd  mov     [rbp+47h+var_90], rdi
0x18000bcc1  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000bcc6  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000bccb  mov     r12, [rbp+47h+arg_20]
0x18000bccf  jmp     loc_18000BE26
0x18000bcd4  movzx   ecx, [rbp+47h+var_80]
0x18000bcd8  cmp     r14, rcx
0x18000bcdb  jnz     short loc_18000BCF3
0x18000bcdd  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000bce1  mov     r8, r14; Size
0x18000bce4  mov     rcx, r15; Buf1
0x18000bce7  call    memcmp_0
0x18000bcec  mov     ecx, eax
0x18000bcee  xor     r9d, r9d
0x18000bcf1  jmp     short loc_18000BCFC
0x18000bcf3  movzx   eax, [rbp+47h+var_80]
0x18000bcf7  mov     ecx, r14d
0x18000bcfa  sub     ecx, eax
0x18000bcfc  test    ecx, ecx
0x18000bcfe  js      loc_18000BEAB
0x18000bd04  jz      loc_18000BE70
0x18000bd0a  mov     rdi, [rbp+47h+var_90]
0x18000bd0e  mov     [rbp+47h+var_90], rdi
0x18000bd12  cmp     [rbx+10h], r9
0x18000bd16  jbe     short loc_18000BD84
0x18000bd18  mov     rax, [rbx+20h]
0x18000bd1c  xor     edx, edx
0x18000bd1e  sub     rax, [rbx+18h]
0x18000bd22  div     qword ptr [rbx+10h]
0x18000bd26  mov     edx, [rbp+47h+Source]
0x18000bd29  cmp     rdx, rax
0x18000bd2c  jbe     short loc_18000BD75
0x18000bd2e  cmp     edx, eax
0x18000bd30  jz      short loc_18000BD75
0x18000bd32  mov     edx, eax
0x18000bd34  mov     [rbp+47h+Source], eax
0x18000bd37  mov     al, [rbp+47h+var_86]
0x18000bd3a  cmp     al, 1
0x18000bd3c  jnz     short loc_18000BD51
0x18000bd3e  movzx   eax, dx
0x18000bd41  mov     [rbp+47h+var_68], dx
0x18000bd45  mov     r9d, 2
0x18000bd4b  lea     r8, [rbp+47h+var_68]
0x18000bd4f  jmp     short loc_18000BD5F
0x18000bd51  cmp     al, 2
0x18000bd53  jnz     short loc_18000BD75
0x18000bd55  mov     r9d, 4; SourceSize
0x18000bd5b  lea     r8, [rbp+47h+Source]; Source
0x18000bd5f  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000bd63  mov     rdx, r9; DestinationSize
0x18000bd66  call    cs:__imp_memcpy_s
0x18000bd6d  nop     dword ptr [rax+rax+00h]
0x18000bd72  mov     edx, [rbp+47h+Source]
0x18000bd75  mov     eax, edx
0x18000bd77  imul    rax, [rbx+10h]
0x18000bd7c  add     rdi, rax
0x18000bd7f  jmp     loc_18000BE11
0x18000bd84  movzx   eax, word ptr [rbx+6]
0x18000bd88  xorps   xmm0, xmm0
0x18000bd8b  mov     [rbp+47h+var_40], ax
0x18000bd8f  mov     esi, r9d
0x18000bd92  mov     al, [rbx+8]
0x18000bd95  mov     [rbp+47h+var_3E], al
0x18000bd98  mov     eax, [rbp+47h+Source]
0x18000bd9b  mov     [rbp+47h+var_3C], r9d
0x18000bd9f  mov     [rbp+47h+var_38], r9w
0x18000bda4  movdqu  [rbp+47h+var_30], xmm0
0x18000bda9  test    eax, eax
0x18000bdab  jz      short loc_18000BDCF
0x18000bdad  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000bdb1  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000bdb5  lea     rcx, [rbp+47h+var_40]; this
0x18000bdb9  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000bdbe  test    al, al
0x18000bdc0  mov     eax, [rbp+47h+Source]
0x18000bdc3  jz      short loc_18000BDCB
0x18000bdc5  inc     esi
0x18000bdc7  cmp     esi, eax
0x18000bdc9  jb      short loc_18000BDAD
0x18000bdcb  mov     rdi, [rbp+47h+var_90]
0x18000bdcf  cmp     eax, esi
0x18000bdd1  jz      short loc_18000BE11
0x18000bdd3  mov     al, [rbp+47h+var_86]
0x18000bdd6  mov     [rbp+47h+Source], esi
0x18000bdd9  cmp     al, 1
0x18000bddb  jnz     short loc_18000BDF1
0x18000bddd  mov     eax, 2
0x18000bde2  mov     [rbp+47h+var_64], si
0x18000bde6  mov     r9d, eax
0x18000bde9  lea     r8, [rbp+47h+var_64]
0x18000bded  mov     edx, eax
0x18000bdef  jmp     short loc_18000BE01
0x18000bdf1  cmp     al, 2
0x18000bdf3  jnz     short loc_18000BE11
0x18000bdf5  mov     edx, 4; DestinationSize
0x18000bdfa  lea     r8, [rbp+47h+Source]; Source
0x18000bdfe  mov     r9d, edx; SourceSize
0x18000be01  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000be05  call    cs:__imp_memcpy_s
0x18000be0c  nop     dword ptr [rax+rax+00h]
0x18000be11  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000be15  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000be19  lea     rcx, [rbp+47h+var_88]; this
0x18000be1d  mov     [rbp+47h+var_90], rdi
0x18000be21  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000be26  xor     r9d, r9d
0x18000be29  mov     sil, al
0x18000be2c  test    al, al
0x18000be2e  jnz     loc_18000BCD4
0x18000be34  mov     rdi, [rbp+47h+var_90]
0x18000be38  mov     [rbx+20h], rdi
0x18000be3c  mov     rcx, r9
0x18000be3f  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000be43  jnz     loc_18000BECE
0x18000be49  movzx   eax, [rbp+47h+var_88]
0x18000be4d  mov     [rbp+47h+Source], 1
0x18000be54  mov     [rbp+47h+var_80], r14w
0x18000be59  mov     [rbp+47h+Buf2], r9
0x18000be5d  mov     [rbp+47h+Buf2+8], r15
0x18000be61  test    ax, ax
0x18000be64  jnz     short loc_18000BEB6
0x18000be66  movzx   ecx, r14w
0x18000be6a  add     rcx, 2
0x18000be6e  jmp     short loc_18000BEB9
0x18000be70  mov     eax, [rbp+47h+arg_28]
0x18000be73  lea     rdx, [rbp+47h+var_88]; struct wil::details_abi::UsageIndexProperty *
0x18000be77  mov     r8, [rbp+47h+var_90]; unsigned __int8 *
0x18000be7b  mov     r9, r13; void *
0x18000be7e  mov     [rsp+0C0h+var_98], eax; unsigned int
0x18000be82  mov     rcx, rbx; this
0x18000be85  mov     [rsp+0C0h+Size], r12; Size
0x18000be8a  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000be8f  xor     r9d, r9d
0x18000be92  mov     [rbp+47h+var_90], rax
0x18000be96  mov     rdi, rax
0x18000be99  test    rax, rax
0x18000be9c  jnz     short loc_18000BEA5
0x18000be9e  mov     al, 1
0x18000bea0  jmp     loc_18000BFE3
0x18000bea5  mov     byte ptr [rbp+47h+arg_0], 1
0x18000bea9  jmp     short loc_18000BEAF
0x18000beab  mov     [rbp+47h+var_90], rdi
0x18000beaf  test    sil, sil
0x18000beb2  jnz     short loc_18000BE3C
0x18000beb4  jmp     short loc_18000BE38
0x18000beb6  mov     rcx, rax
0x18000beb9  mov     al, [rbp+47h+var_86]
0x18000bebc  cmp     al, 1
0x18000bebe  jnz     short loc_18000BEC6
0x18000bec0  add     rcx, 2
0x18000bec4  jmp     short loc_18000BECE
0x18000bec6  cmp     al, 2
0x18000bec8  jnz     short loc_18000BECE
0x18000beca  add     rcx, 4
0x18000bece  movzx   eax, word ptr [rbx+6]
0x18000bed2  mov     dl, [rbx+8]
0x18000bed5  mov     r8d, [rbp+47h+arg_28]
0x18000bed9  mov     [rbp+47h+var_60], ax
0x18000bedd  mov     [rbp+47h+var_5E], dl
0x18000bee0  mov     [rbp+47h+var_5C], r8d
0x18000bee4  mov     [rbp+47h+var_58], r12w
0x18000bee9  mov     [rbp+47h+var_50], r9
0x18000beed  mov     [rbp+47h+var_48], r13
0x18000bef1  test    ax, ax
0x18000bef4  jnz     short loc_18000BEFE
0x18000bef6  movzx   eax, r12w
0x18000befa  add     rax, 2
0x18000befe  cmp     dl, 1
0x18000bf01  jnz     short loc_18000BF09
0x18000bf03  add     rax, 2
0x18000bf07  jmp     short loc_18000BF12
0x18000bf09  cmp     dl, 2
0x18000bf0c  jnz     short loc_18000BF12
0x18000bf0e  add     rax, 4
0x18000bf12  mov     rdx, [rbx+28h]
0x18000bf16  lea     rsi, [rax+rcx]
0x18000bf1a  mov     r9, [rbx+20h]
0x18000bf1e  mov     rcx, rdx
0x18000bf21  sub     rcx, r9
0x18000bf24  cmp     r9, rdx
0x18000bf27  sbb     rax, rax
0x18000bf2a  and     rax, rcx
0x18000bf2d  cmp     rax, rsi
0x18000bf30  jb      loc_18000BFE1
0x18000bf36  sub     rdx, rsi
0x18000bf39  lea     rcx, [rsi+rdi]; Destination
0x18000bf3d  sub     rdx, rdi; DestinationSize
0x18000bf40  sub     r9, rdi; SourceSize
0x18000bf43  mov     r8, rdi; Source
0x18000bf46  call    cs:__imp_memmove_s
0x18000bf4d  nop     dword ptr [rax+rax+00h]
0x18000bf52  mov     r8, [rbx+20h]
0x18000bf56  xor     edi, edi
0x18000bf58  add     r8, rsi; unsigned __int8 *
0x18000bf5b  mov     [rbx+20h], r8
0x18000bf5f  cmp     byte ptr [rbp+47h+arg_0], dil
0x18000bf63  jnz     short loc_18000BF74
0x18000bf65  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000bf69  lea     rcx, [rbp+47h+var_88]; this
0x18000bf6d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000bf72  jmp     short loc_18000BFC7
0x18000bf74  mov     cl, [rbp+47h+var_86]
0x18000bf77  test    cl, cl
0x18000bf79  jz      short loc_18000BFC7
0x18000bf7b  mov     eax, [rbp+47h+Source]
0x18000bf7e  lea     r8d, [rax+1]
0x18000bf82  cmp     eax, r8d
0x18000bf85  jz      short loc_18000BFC7
0x18000bf87  mov     [rbp+47h+Source], r8d
0x18000bf8b  cmp     cl, 1
0x18000bf8e  jnz     short loc_18000BFA4
0x18000bf90  mov     r9d, 2
0x18000bf96  mov     [rbp+47h+arg_0], r8w
0x18000bf9b  mov     edx, r9d
0x18000bf9e  lea     r8, [rbp+47h+arg_0]
0x18000bfa2  jmp     short loc_18000BFB7
0x18000bfa4  cmp     cl, 2
0x18000bfa7  jnz     short loc_18000BFC7
0x18000bfa9  mov     eax, 4
0x18000bfae  lea     r8, [rbp+47h+Source]; Source
0x18000bfb2  mov     r9d, eax; SourceSize
0x18000bfb5  mov     edx, eax; DestinationSize
0x18000bfb7  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000bfbb  call    cs:__imp_memcpy_s
0x18000bfc2  nop     dword ptr [rax+rax+00h]
0x18000bfc7  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000bfcb  lea     rdx, [rbp+47h+var_90]; unsigned __int8 **
0x18000bfcf  lea     rcx, [rbp+47h+var_60]; this
0x18000bfd3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000bfd8  mov     byte ptr [rbx+38h], 1
0x18000bfdc  jmp     loc_18000BE9E
0x18000bfe1  xor     al, al
0x18000bfe3  lea     r11, [rsp+0C0h+var_20]
0x18000bfeb  mov     rbx, [r11+38h]
0x18000bfef  mov     rsi, [r11+40h]
0x18000bff3  mov     rdi, [r11+48h]
0x18000bff7  mov     rsp, r11
0x18000bffa  pop     r15
0x18000bffc  pop     r14
0x18000bffe  pop     r13
0x18000c000  pop     r12
0x18000c002  pop     rbp
0x18000c003  retn
```
