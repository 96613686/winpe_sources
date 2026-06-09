# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800067d4`
- end: `0x180006b54`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006624`

## callees

- `0x180004710`
- `0x180005fb8`
- `0x1800067d4`
- `0x18000830c`
- `0x1800216e6`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006ab3`
- `msvcrt!memmove_s` at `0x180006ab3`
- `msvcrt!memcpy_s` at `0x1800068df`
- `msvcrt!memcpy_s` at `0x180006978`
- `msvcrt!memcpy_s` at `0x180006b1e`
- `msvcrt!memcpy_s` at `0x1800068df`
- `msvcrt!memcpy_s` at `0x180006978`
- `msvcrt!memcpy_s` at `0x180006b1e`

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
0x1800067d4  push    rbp
0x1800067d6  push    rbx
0x1800067d7  push    rsi
0x1800067d8  push    rdi
0x1800067d9  push    r12
0x1800067db  push    r13
0x1800067dd  push    r14
0x1800067df  push    r15
0x1800067e1  lea     rbp, [rsp-0Fh]
0x1800067e6  sub     rsp, 0A8h
0x1800067ed  mov     rbx, [rcx+18h]
0x1800067f1  mov     rdi, rcx
0x1800067f4  xor     ecx, ecx
0x1800067f6  mov     r13, r9
0x1800067f9  mov     r14, r8
0x1800067fc  mov     r15, rdx
0x1800067ff  test    rbx, rbx
0x180006802  jz      loc_180006B3E
0x180006808  movzx   eax, word ptr [rdi+2]
0x18000680c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006810  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006814  add     rbx, 0Ah
0x180006818  mov     [rbp+47h+var_A0], ax
0x18000681c  xorps   xmm0, xmm0
0x18000681f  mov     al, [rdi+4]
0x180006822  mov     [rbp+47h+Source], ecx
0x180006825  mov     [rbp+47h+var_98], cx
0x180006829  mov     byte ptr [rbp+47h+arg_0], cl
0x18000682c  lea     rcx, [rbp+47h+var_A0]; this
0x180006830  mov     [rbp+47h+var_9E], al
0x180006833  mov     [rbp+47h+var_A8], rbx
0x180006837  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000683c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006841  mov     r12, [rbp+47h+arg_20]
0x180006845  jmp     loc_180006993
0x18000684a  movzx   eax, [rbp+47h+var_98]
0x18000684e  cmp     r14, rax
0x180006851  jnz     short loc_180006869
0x180006853  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180006857  mov     r8, r14; Size
0x18000685a  mov     rcx, r15; Buf1
0x18000685d  call    memcmp_0
0x180006862  mov     ecx, eax
0x180006864  xor     r9d, r9d
0x180006867  jmp     short loc_180006872
0x180006869  movzx   eax, [rbp+47h+var_98]
0x18000686d  mov     ecx, r14d
0x180006870  sub     ecx, eax
0x180006872  test    ecx, ecx
0x180006874  js      loc_180006A18
0x18000687a  jz      loc_1800069DD
0x180006880  mov     rbx, [rbp+47h+var_A8]
0x180006884  mov     [rbp+47h+var_A8], rbx
0x180006888  cmp     [rdi+10h], r9
0x18000688c  jbe     short loc_1800068F7
0x18000688e  mov     rax, [rdi+20h]
0x180006892  xor     edx, edx
0x180006894  sub     rax, [rdi+18h]
0x180006898  mov     rsi, rbx
0x18000689b  div     qword ptr [rdi+10h]
0x18000689f  mov     edx, [rbp+47h+Source]
0x1800068a2  cmp     rdx, rax
0x1800068a5  jbe     short loc_1800068E8
0x1800068a7  cmp     edx, eax
0x1800068a9  jz      short loc_1800068E8
0x1800068ab  mov     edx, eax
0x1800068ad  mov     [rbp+47h+Source], eax
0x1800068b0  mov     al, [rbp+47h+var_9E]
0x1800068b3  cmp     al, 1
0x1800068b5  jnz     short loc_1800068CA
0x1800068b7  movzx   eax, dx
0x1800068ba  mov     [rbp+47h+var_B0], dx
0x1800068be  mov     r9d, 2
0x1800068c4  lea     r8, [rbp+47h+var_B0]
0x1800068c8  jmp     short loc_1800068D8
0x1800068ca  cmp     al, 2
0x1800068cc  jnz     short loc_1800068E8
0x1800068ce  mov     r9d, 4; SourceSize
0x1800068d4  lea     r8, [rbp+47h+Source]; Source
0x1800068d8  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800068dc  mov     rdx, r9; DestinationSize
0x1800068df  call    cs:__imp_memcpy_s
0x1800068e5  mov     edx, [rbp+47h+Source]
0x1800068e8  mov     ebx, edx
0x1800068ea  imul    rbx, [rdi+10h]
0x1800068ef  add     rbx, rsi
0x1800068f2  jmp     loc_18000697E
0x1800068f7  movzx   eax, word ptr [rdi+6]
0x1800068fb  xorps   xmm0, xmm0
0x1800068fe  mov     [rbp+47h+var_60], ax
0x180006902  mov     esi, r9d
0x180006905  mov     al, [rdi+8]
0x180006908  mov     [rbp+47h+var_5E], al
0x18000690b  mov     eax, [rbp+47h+Source]
0x18000690e  mov     [rbp+47h+var_5C], r9d
0x180006912  mov     [rbp+47h+var_58], r9w
0x180006917  movdqu  [rbp+47h+var_50], xmm0
0x18000691c  test    eax, eax
0x18000691e  jz      short loc_180006942
0x180006920  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006924  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006928  lea     rcx, [rbp+47h+var_60]; this
0x18000692c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006931  test    al, al
0x180006933  mov     eax, [rbp+47h+Source]
0x180006936  jz      short loc_18000693E
0x180006938  inc     esi
0x18000693a  cmp     esi, eax
0x18000693c  jb      short loc_180006920
0x18000693e  mov     rbx, [rbp+47h+var_A8]
0x180006942  cmp     eax, esi
0x180006944  jz      short loc_18000697E
0x180006946  mov     al, [rbp+47h+var_9E]
0x180006949  mov     [rbp+47h+Source], esi
0x18000694c  cmp     al, 1
0x18000694e  jnz     short loc_180006964
0x180006950  mov     eax, 2
0x180006955  mov     [rbp+47h+var_B0], si
0x180006959  mov     r9d, eax
0x18000695c  lea     r8, [rbp+47h+var_B0]
0x180006960  mov     edx, eax
0x180006962  jmp     short loc_180006974
0x180006964  cmp     al, 2
0x180006966  jnz     short loc_18000697E
0x180006968  mov     edx, 4; DestinationSize
0x18000696d  lea     r8, [rbp+47h+Source]; Source
0x180006971  mov     r9d, edx; SourceSize
0x180006974  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006978  call    cs:__imp_memcpy_s
0x18000697e  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006982  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006986  lea     rcx, [rbp+47h+var_A0]; this
0x18000698a  mov     [rbp+47h+var_A8], rbx
0x18000698e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006993  xor     r9d, r9d
0x180006996  mov     sil, al
0x180006999  test    al, al
0x18000699b  jnz     loc_18000684A
0x1800069a1  mov     rbx, [rbp+47h+var_A8]
0x1800069a5  mov     [rdi+20h], rbx
0x1800069a9  mov     rcx, r9
0x1800069ac  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800069b0  jnz     loc_180006A3B
0x1800069b6  movzx   eax, [rbp+47h+var_A0]
0x1800069ba  mov     [rbp+47h+Source], 1
0x1800069c1  mov     [rbp+47h+var_98], r14w
0x1800069c6  mov     [rbp+47h+Buf2], r9
0x1800069ca  mov     [rbp+47h+Buf2+8], r15
0x1800069ce  test    ax, ax
0x1800069d1  jnz     short loc_180006A23
0x1800069d3  movzx   ecx, r14w
0x1800069d7  add     rcx, 2
0x1800069db  jmp     short loc_180006A26
0x1800069dd  mov     eax, [rbp+47h+arg_28]
0x1800069e0  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1800069e4  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1800069e8  mov     r9, r13; void *
0x1800069eb  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800069ef  mov     rcx, rdi; this
0x1800069f2  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x1800069f7  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800069fc  xor     r9d, r9d
0x1800069ff  mov     [rbp+47h+var_A8], rax
0x180006a03  mov     rbx, rax
0x180006a06  test    rax, rax
0x180006a09  jnz     short loc_180006A12
0x180006a0b  mov     al, 1
0x180006a0d  jmp     loc_180006B40
0x180006a12  mov     byte ptr [rbp+47h+arg_0], 1
0x180006a16  jmp     short loc_180006A1C
0x180006a18  mov     [rbp+47h+var_A8], rbx
0x180006a1c  test    sil, sil
0x180006a1f  jnz     short loc_1800069A9
0x180006a21  jmp     short loc_1800069A5
0x180006a23  mov     rcx, rax
0x180006a26  mov     al, [rbp+47h+var_9E]
0x180006a29  cmp     al, 1
0x180006a2b  jnz     short loc_180006A33
0x180006a2d  add     rcx, 2
0x180006a31  jmp     short loc_180006A3B
0x180006a33  cmp     al, 2
0x180006a35  jnz     short loc_180006A3B
0x180006a37  add     rcx, 4
0x180006a3b  movzx   eax, word ptr [rdi+6]
0x180006a3f  mov     dl, [rdi+8]
0x180006a42  mov     r8d, [rbp+47h+arg_28]
0x180006a46  mov     [rbp+47h+var_80], ax
0x180006a4a  mov     [rbp+47h+var_7E], dl
0x180006a4d  mov     [rbp+47h+var_7C], r8d
0x180006a51  mov     [rbp+47h+var_78], r12w
0x180006a56  mov     [rbp+47h+var_70], r9
0x180006a5a  mov     [rbp+47h+var_68], r13
0x180006a5e  test    ax, ax
0x180006a61  jnz     short loc_180006A6B
0x180006a63  movzx   eax, r12w
0x180006a67  add     rax, 2
0x180006a6b  cmp     dl, 1
0x180006a6e  jnz     short loc_180006A76
0x180006a70  add     rax, 2
0x180006a74  jmp     short loc_180006A7F
0x180006a76  cmp     dl, 2
0x180006a79  jnz     short loc_180006A7F
0x180006a7b  add     rax, 4
0x180006a7f  mov     rdx, [rdi+28h]
0x180006a83  lea     rsi, [rax+rcx]
0x180006a87  mov     r9, [rdi+20h]
0x180006a8b  mov     rcx, rdx
0x180006a8e  sub     rcx, r9
0x180006a91  cmp     r9, rdx
0x180006a94  sbb     rax, rax
0x180006a97  and     rax, rcx
0x180006a9a  cmp     rax, rsi
0x180006a9d  jb      loc_180006B3E
0x180006aa3  sub     rdx, rsi
0x180006aa6  lea     rcx, [rsi+rbx]; Destination
0x180006aaa  sub     rdx, rbx; DestinationSize
0x180006aad  sub     r9, rbx; SourceSize
0x180006ab0  mov     r8, rbx; Source
0x180006ab3  call    cs:__imp_memmove_s
0x180006ab9  add     [rdi+20h], rsi
0x180006abd  xor     ebx, ebx
0x180006abf  cmp     byte ptr [rbp+47h+arg_0], bl
0x180006ac2  jnz     short loc_180006AD7
0x180006ac4  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006ac8  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006acc  lea     rcx, [rbp+47h+var_A0]; this
0x180006ad0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006ad5  jmp     short loc_180006B24
0x180006ad7  mov     cl, [rbp+47h+var_9E]
0x180006ada  test    cl, cl
0x180006adc  jz      short loc_180006B24
0x180006ade  mov     eax, [rbp+47h+Source]
0x180006ae1  lea     r8d, [rax+1]
0x180006ae5  cmp     eax, r8d
0x180006ae8  jz      short loc_180006B24
0x180006aea  mov     [rbp+47h+Source], r8d
0x180006aee  cmp     cl, 1
0x180006af1  jnz     short loc_180006B07
0x180006af3  mov     r9d, 2
0x180006af9  mov     [rbp+47h+arg_0], r8w
0x180006afe  mov     edx, r9d
0x180006b01  lea     r8, [rbp+47h+arg_0]
0x180006b05  jmp     short loc_180006B1A
0x180006b07  cmp     cl, 2
0x180006b0a  jnz     short loc_180006B24
0x180006b0c  mov     eax, 4
0x180006b11  lea     r8, [rbp+47h+Source]; Source
0x180006b15  mov     r9d, eax; SourceSize
0x180006b18  mov     edx, eax; DestinationSize
0x180006b1a  mov     rcx, [rbp+47h+Buf2]; Destination
0x180006b1e  call    cs:__imp_memcpy_s
0x180006b24  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006b28  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180006b2c  lea     rcx, [rbp+47h+var_80]; this
0x180006b30  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006b35  mov     byte ptr [rdi+38h], 1
0x180006b39  jmp     loc_180006A0B
0x180006b3e  xor     al, al
0x180006b40  add     rsp, 0A8h
0x180006b47  pop     r15
0x180006b49  pop     r14
0x180006b4b  pop     r13
0x180006b4d  pop     r12
0x180006b4f  pop     rdi
0x180006b50  pop     rsi
0x180006b51  pop     rbx
0x180006b52  pop     rbp
0x180006b53  retn
```
