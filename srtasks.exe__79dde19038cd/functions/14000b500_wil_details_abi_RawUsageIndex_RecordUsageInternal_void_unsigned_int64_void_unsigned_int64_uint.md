# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000b500`
- end: `0x14000b880`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000b350`

## callees

- `0x14000985c`
- `0x14000aed8`
- `0x14000b500`
- `0x14000cccc`
- `0x140010936`

## import_xrefs

- `msvcrt!memmove_s` at `0x14000b7df`
- `msvcrt!memmove_s` at `0x14000b7df`
- `msvcrt!memcpy_s` at `0x14000b60b`
- `msvcrt!memcpy_s` at `0x14000b6a4`
- `msvcrt!memcpy_s` at `0x14000b84a`
- `msvcrt!memcpy_s` at `0x14000b60b`
- `msvcrt!memcpy_s` at `0x14000b6a4`
- `msvcrt!memcpy_s` at `0x14000b84a`

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
0x14000b500  push    rbp
0x14000b502  push    rbx
0x14000b503  push    rsi
0x14000b504  push    rdi
0x14000b505  push    r12
0x14000b507  push    r13
0x14000b509  push    r14
0x14000b50b  push    r15
0x14000b50d  lea     rbp, [rsp-0Fh]
0x14000b512  sub     rsp, 0A8h
0x14000b519  mov     rbx, [rcx+18h]
0x14000b51d  mov     rdi, rcx
0x14000b520  xor     ecx, ecx
0x14000b522  mov     r13, r9
0x14000b525  mov     r14, r8
0x14000b528  mov     r15, rdx
0x14000b52b  test    rbx, rbx
0x14000b52e  jz      loc_14000B86A
0x14000b534  movzx   eax, word ptr [rdi+2]
0x14000b538  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b53c  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b540  add     rbx, 0Ah
0x14000b544  mov     [rbp+47h+var_A0], ax
0x14000b548  xorps   xmm0, xmm0
0x14000b54b  mov     al, [rdi+4]
0x14000b54e  mov     [rbp+47h+Source], ecx
0x14000b551  mov     [rbp+47h+var_98], cx
0x14000b555  mov     byte ptr [rbp+47h+arg_0], cl
0x14000b558  lea     rcx, [rbp+47h+var_A0]; this
0x14000b55c  mov     [rbp+47h+var_9E], al
0x14000b55f  mov     [rbp+47h+var_A8], rbx
0x14000b563  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x14000b568  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b56d  mov     r12, [rbp+47h+arg_20]
0x14000b571  jmp     loc_14000B6BF
0x14000b576  movzx   eax, [rbp+47h+var_98]
0x14000b57a  cmp     r14, rax
0x14000b57d  jnz     short loc_14000B595
0x14000b57f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x14000b583  mov     r8, r14; Size
0x14000b586  mov     rcx, r15; Buf1
0x14000b589  call    memcmp_0
0x14000b58e  mov     ecx, eax
0x14000b590  xor     r9d, r9d
0x14000b593  jmp     short loc_14000B59E
0x14000b595  movzx   eax, [rbp+47h+var_98]
0x14000b599  mov     ecx, r14d
0x14000b59c  sub     ecx, eax
0x14000b59e  test    ecx, ecx
0x14000b5a0  js      loc_14000B744
0x14000b5a6  jz      loc_14000B709
0x14000b5ac  mov     rbx, [rbp+47h+var_A8]
0x14000b5b0  mov     [rbp+47h+var_A8], rbx
0x14000b5b4  cmp     [rdi+10h], r9
0x14000b5b8  jbe     short loc_14000B623
0x14000b5ba  mov     rax, [rdi+20h]
0x14000b5be  xor     edx, edx
0x14000b5c0  sub     rax, [rdi+18h]
0x14000b5c4  mov     rsi, rbx
0x14000b5c7  div     qword ptr [rdi+10h]
0x14000b5cb  mov     edx, [rbp+47h+Source]
0x14000b5ce  cmp     rdx, rax
0x14000b5d1  jbe     short loc_14000B614
0x14000b5d3  cmp     edx, eax
0x14000b5d5  jz      short loc_14000B614
0x14000b5d7  mov     edx, eax
0x14000b5d9  mov     [rbp+47h+Source], eax
0x14000b5dc  mov     al, [rbp+47h+var_9E]
0x14000b5df  cmp     al, 1
0x14000b5e1  jnz     short loc_14000B5F6
0x14000b5e3  movzx   eax, dx
0x14000b5e6  mov     [rbp+47h+var_B0], dx
0x14000b5ea  mov     r9d, 2
0x14000b5f0  lea     r8, [rbp+47h+var_B0]
0x14000b5f4  jmp     short loc_14000B604
0x14000b5f6  cmp     al, 2
0x14000b5f8  jnz     short loc_14000B614
0x14000b5fa  mov     r9d, 4; SourceSize
0x14000b600  lea     r8, [rbp+47h+Source]; Source
0x14000b604  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000b608  mov     rdx, r9; DestinationSize
0x14000b60b  call    cs:__imp_memcpy_s
0x14000b611  mov     edx, [rbp+47h+Source]
0x14000b614  mov     ebx, edx
0x14000b616  imul    rbx, [rdi+10h]
0x14000b61b  add     rbx, rsi
0x14000b61e  jmp     loc_14000B6AA
0x14000b623  movzx   eax, word ptr [rdi+6]
0x14000b627  xorps   xmm0, xmm0
0x14000b62a  mov     [rbp+47h+var_60], ax
0x14000b62e  mov     esi, r9d
0x14000b631  mov     al, [rdi+8]
0x14000b634  mov     [rbp+47h+var_5E], al
0x14000b637  mov     eax, [rbp+47h+Source]
0x14000b63a  mov     [rbp+47h+var_5C], r9d
0x14000b63e  mov     [rbp+47h+var_58], r9w
0x14000b643  movdqu  [rbp+47h+var_50], xmm0
0x14000b648  test    eax, eax
0x14000b64a  jz      short loc_14000B66E
0x14000b64c  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b650  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b654  lea     rcx, [rbp+47h+var_60]; this
0x14000b658  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b65d  test    al, al
0x14000b65f  mov     eax, [rbp+47h+Source]
0x14000b662  jz      short loc_14000B66A
0x14000b664  inc     esi
0x14000b666  cmp     esi, eax
0x14000b668  jb      short loc_14000B64C
0x14000b66a  mov     rbx, [rbp+47h+var_A8]
0x14000b66e  cmp     eax, esi
0x14000b670  jz      short loc_14000B6AA
0x14000b672  mov     al, [rbp+47h+var_9E]
0x14000b675  mov     [rbp+47h+Source], esi
0x14000b678  cmp     al, 1
0x14000b67a  jnz     short loc_14000B690
0x14000b67c  mov     eax, 2
0x14000b681  mov     [rbp+47h+var_B0], si
0x14000b685  mov     r9d, eax
0x14000b688  lea     r8, [rbp+47h+var_B0]
0x14000b68c  mov     edx, eax
0x14000b68e  jmp     short loc_14000B6A0
0x14000b690  cmp     al, 2
0x14000b692  jnz     short loc_14000B6AA
0x14000b694  mov     edx, 4; DestinationSize
0x14000b699  lea     r8, [rbp+47h+Source]; Source
0x14000b69d  mov     r9d, edx; SourceSize
0x14000b6a0  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000b6a4  call    cs:__imp_memcpy_s
0x14000b6aa  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b6ae  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b6b2  lea     rcx, [rbp+47h+var_A0]; this
0x14000b6b6  mov     [rbp+47h+var_A8], rbx
0x14000b6ba  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000b6bf  xor     r9d, r9d
0x14000b6c2  mov     sil, al
0x14000b6c5  test    al, al
0x14000b6c7  jnz     loc_14000B576
0x14000b6cd  mov     rbx, [rbp+47h+var_A8]
0x14000b6d1  mov     [rdi+20h], rbx
0x14000b6d5  mov     rcx, r9
0x14000b6d8  cmp     byte ptr [rbp+47h+arg_0], r9b
0x14000b6dc  jnz     loc_14000B767
0x14000b6e2  movzx   eax, [rbp+47h+var_A0]
0x14000b6e6  mov     [rbp+47h+Source], 1
0x14000b6ed  mov     [rbp+47h+var_98], r14w
0x14000b6f2  mov     [rbp+47h+Buf2], r9
0x14000b6f6  mov     [rbp+47h+Buf2+8], r15
0x14000b6fa  test    ax, ax
0x14000b6fd  jnz     short loc_14000B74F
0x14000b6ff  movzx   ecx, r14w
0x14000b703  add     rcx, 2
0x14000b707  jmp     short loc_14000B752
0x14000b709  mov     eax, [rbp+47h+arg_28]
0x14000b70c  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x14000b710  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x14000b714  mov     r9, r13; void *
0x14000b717  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x14000b71b  mov     rcx, rdi; this
0x14000b71e  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x14000b723  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x14000b728  xor     r9d, r9d
0x14000b72b  mov     [rbp+47h+var_A8], rax
0x14000b72f  mov     rbx, rax
0x14000b732  test    rax, rax
0x14000b735  jnz     short loc_14000B73E
0x14000b737  mov     al, 1
0x14000b739  jmp     loc_14000B86C
0x14000b73e  mov     byte ptr [rbp+47h+arg_0], 1
0x14000b742  jmp     short loc_14000B748
0x14000b744  mov     [rbp+47h+var_A8], rbx
0x14000b748  test    sil, sil
0x14000b74b  jnz     short loc_14000B6D5
0x14000b74d  jmp     short loc_14000B6D1
0x14000b74f  mov     rcx, rax
0x14000b752  mov     al, [rbp+47h+var_9E]
0x14000b755  cmp     al, 1
0x14000b757  jnz     short loc_14000B75F
0x14000b759  add     rcx, 2
0x14000b75d  jmp     short loc_14000B767
0x14000b75f  cmp     al, 2
0x14000b761  jnz     short loc_14000B767
0x14000b763  add     rcx, 4
0x14000b767  movzx   eax, word ptr [rdi+6]
0x14000b76b  mov     dl, [rdi+8]
0x14000b76e  mov     r8d, [rbp+47h+arg_28]
0x14000b772  mov     [rbp+47h+var_80], ax
0x14000b776  mov     [rbp+47h+var_7E], dl
0x14000b779  mov     [rbp+47h+var_7C], r8d
0x14000b77d  mov     [rbp+47h+var_78], r12w
0x14000b782  mov     [rbp+47h+var_70], r9
0x14000b786  mov     [rbp+47h+var_68], r13
0x14000b78a  test    ax, ax
0x14000b78d  jnz     short loc_14000B797
0x14000b78f  movzx   eax, r12w
0x14000b793  add     rax, 2
0x14000b797  cmp     dl, 1
0x14000b79a  jnz     short loc_14000B7A2
0x14000b79c  add     rax, 2
0x14000b7a0  jmp     short loc_14000B7AB
0x14000b7a2  cmp     dl, 2
0x14000b7a5  jnz     short loc_14000B7AB
0x14000b7a7  add     rax, 4
0x14000b7ab  mov     rdx, [rdi+28h]
0x14000b7af  lea     rsi, [rax+rcx]
0x14000b7b3  mov     r9, [rdi+20h]
0x14000b7b7  mov     rcx, rdx
0x14000b7ba  sub     rcx, r9
0x14000b7bd  cmp     r9, rdx
0x14000b7c0  sbb     rax, rax
0x14000b7c3  and     rax, rcx
0x14000b7c6  cmp     rax, rsi
0x14000b7c9  jb      loc_14000B86A
0x14000b7cf  sub     rdx, rsi
0x14000b7d2  lea     rcx, [rsi+rbx]; Destination
0x14000b7d6  sub     rdx, rbx; DestinationSize
0x14000b7d9  sub     r9, rbx; SourceSize
0x14000b7dc  mov     r8, rbx; Source
0x14000b7df  call    cs:__imp_memmove_s
0x14000b7e5  add     [rdi+20h], rsi
0x14000b7e9  xor     ebx, ebx
0x14000b7eb  cmp     byte ptr [rbp+47h+arg_0], bl
0x14000b7ee  jnz     short loc_14000B803
0x14000b7f0  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b7f4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b7f8  lea     rcx, [rbp+47h+var_A0]; this
0x14000b7fc  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000b801  jmp     short loc_14000B850
0x14000b803  mov     cl, [rbp+47h+var_9E]
0x14000b806  test    cl, cl
0x14000b808  jz      short loc_14000B850
0x14000b80a  mov     eax, [rbp+47h+Source]
0x14000b80d  lea     r8d, [rax+1]
0x14000b811  cmp     eax, r8d
0x14000b814  jz      short loc_14000B850
0x14000b816  mov     [rbp+47h+Source], r8d
0x14000b81a  cmp     cl, 1
0x14000b81d  jnz     short loc_14000B833
0x14000b81f  mov     r9d, 2
0x14000b825  mov     [rbp+47h+arg_0], r8w
0x14000b82a  mov     edx, r9d
0x14000b82d  lea     r8, [rbp+47h+arg_0]
0x14000b831  jmp     short loc_14000B846
0x14000b833  cmp     cl, 2
0x14000b836  jnz     short loc_14000B850
0x14000b838  mov     eax, 4
0x14000b83d  lea     r8, [rbp+47h+Source]; Source
0x14000b841  mov     r9d, eax; SourceSize
0x14000b844  mov     edx, eax; DestinationSize
0x14000b846  mov     rcx, [rbp+47h+Buf2]; Destination
0x14000b84a  call    cs:__imp_memcpy_s
0x14000b850  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000b854  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x14000b858  lea     rcx, [rbp+47h+var_80]; this
0x14000b85c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x14000b861  mov     byte ptr [rdi+38h], 1
0x14000b865  jmp     loc_14000B737
0x14000b86a  xor     al, al
0x14000b86c  add     rsp, 0A8h
0x14000b873  pop     r15
0x14000b875  pop     r14
0x14000b877  pop     r13
0x14000b879  pop     r12
0x14000b87b  pop     rdi
0x14000b87c  pop     rsi
0x14000b87d  pop     rbx
0x14000b87e  pop     rbp
0x14000b87f  retn
```
