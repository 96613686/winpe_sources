# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001b934`
- end: `0x18001bcb4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b784`

## callees

- `0x18001ab9c`
- `0x18001b340`
- `0x18001b934`
- `0x18001cc34`
- `0x18001d316`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001ba3f`
- `msvcrt!memcpy_s` at `0x18001bad8`
- `msvcrt!memcpy_s` at `0x18001bc7e`
- `msvcrt!memcpy_s` at `0x18001ba3f`
- `msvcrt!memcpy_s` at `0x18001bad8`
- `msvcrt!memcpy_s` at `0x18001bc7e`
- `msvcrt!memmove_s` at `0x18001bc13`
- `msvcrt!memmove_s` at `0x18001bc13`

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
0x18001b934  push    rbp
0x18001b936  push    rbx
0x18001b937  push    rsi
0x18001b938  push    rdi
0x18001b939  push    r12
0x18001b93b  push    r13
0x18001b93d  push    r14
0x18001b93f  push    r15
0x18001b941  lea     rbp, [rsp-0Fh]
0x18001b946  sub     rsp, 0A8h
0x18001b94d  mov     rbx, [rcx+18h]
0x18001b951  mov     rdi, rcx
0x18001b954  xor     ecx, ecx
0x18001b956  mov     r13, r9
0x18001b959  mov     r14, r8
0x18001b95c  mov     r15, rdx
0x18001b95f  test    rbx, rbx
0x18001b962  jz      loc_18001BC9E
0x18001b968  movzx   eax, word ptr [rdi+2]
0x18001b96c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001b970  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001b974  add     rbx, 0Ah
0x18001b978  mov     [rbp+47h+var_A0], ax
0x18001b97c  xorps   xmm0, xmm0
0x18001b97f  mov     al, [rdi+4]
0x18001b982  mov     [rbp+47h+Source], ecx
0x18001b985  mov     [rbp+47h+var_98], cx
0x18001b989  mov     byte ptr [rbp+47h+arg_0], cl
0x18001b98c  lea     rcx, [rbp+47h+var_A0]; this
0x18001b990  mov     [rbp+47h+var_9E], al
0x18001b993  mov     [rbp+47h+var_A8], rbx
0x18001b997  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18001b99c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001b9a1  mov     r12, [rbp+47h+arg_20]
0x18001b9a5  jmp     loc_18001BAF3
0x18001b9aa  movzx   eax, [rbp+47h+var_98]
0x18001b9ae  cmp     r14, rax
0x18001b9b1  jnz     short loc_18001B9C9
0x18001b9b3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18001b9b7  mov     r8, r14; Size
0x18001b9ba  mov     rcx, r15; Buf1
0x18001b9bd  call    memcmp_0
0x18001b9c2  mov     ecx, eax
0x18001b9c4  xor     r9d, r9d
0x18001b9c7  jmp     short loc_18001B9D2
0x18001b9c9  movzx   eax, [rbp+47h+var_98]
0x18001b9cd  mov     ecx, r14d
0x18001b9d0  sub     ecx, eax
0x18001b9d2  test    ecx, ecx
0x18001b9d4  js      loc_18001BB78
0x18001b9da  jz      loc_18001BB3D
0x18001b9e0  mov     rbx, [rbp+47h+var_A8]
0x18001b9e4  mov     [rbp+47h+var_A8], rbx
0x18001b9e8  cmp     [rdi+10h], r9
0x18001b9ec  jbe     short loc_18001BA57
0x18001b9ee  mov     rax, [rdi+20h]
0x18001b9f2  xor     edx, edx
0x18001b9f4  sub     rax, [rdi+18h]
0x18001b9f8  mov     rsi, rbx
0x18001b9fb  div     qword ptr [rdi+10h]
0x18001b9ff  mov     edx, [rbp+47h+Source]
0x18001ba02  cmp     rdx, rax
0x18001ba05  jbe     short loc_18001BA48
0x18001ba07  cmp     edx, eax
0x18001ba09  jz      short loc_18001BA48
0x18001ba0b  mov     edx, eax
0x18001ba0d  mov     [rbp+47h+Source], eax
0x18001ba10  mov     al, [rbp+47h+var_9E]
0x18001ba13  cmp     al, 1
0x18001ba15  jnz     short loc_18001BA2A
0x18001ba17  movzx   eax, dx
0x18001ba1a  mov     [rbp+47h+var_B0], dx
0x18001ba1e  mov     r9d, 2
0x18001ba24  lea     r8, [rbp+47h+var_B0]
0x18001ba28  jmp     short loc_18001BA38
0x18001ba2a  cmp     al, 2
0x18001ba2c  jnz     short loc_18001BA48
0x18001ba2e  mov     r9d, 4; SourceSize
0x18001ba34  lea     r8, [rbp+47h+Source]; Source
0x18001ba38  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001ba3c  mov     rdx, r9; DestinationSize
0x18001ba3f  call    cs:__imp_memcpy_s
0x18001ba45  mov     edx, [rbp+47h+Source]
0x18001ba48  mov     ebx, edx
0x18001ba4a  imul    rbx, [rdi+10h]
0x18001ba4f  add     rbx, rsi
0x18001ba52  jmp     loc_18001BADE
0x18001ba57  movzx   eax, word ptr [rdi+6]
0x18001ba5b  xorps   xmm0, xmm0
0x18001ba5e  mov     [rbp+47h+var_60], ax
0x18001ba62  mov     esi, r9d
0x18001ba65  mov     al, [rdi+8]
0x18001ba68  mov     [rbp+47h+var_5E], al
0x18001ba6b  mov     eax, [rbp+47h+Source]
0x18001ba6e  mov     [rbp+47h+var_5C], r9d
0x18001ba72  mov     [rbp+47h+var_58], r9w
0x18001ba77  movdqu  [rbp+47h+var_50], xmm0
0x18001ba7c  test    eax, eax
0x18001ba7e  jz      short loc_18001BAA2
0x18001ba80  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001ba84  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001ba88  lea     rcx, [rbp+47h+var_60]; this
0x18001ba8c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001ba91  test    al, al
0x18001ba93  mov     eax, [rbp+47h+Source]
0x18001ba96  jz      short loc_18001BA9E
0x18001ba98  inc     esi
0x18001ba9a  cmp     esi, eax
0x18001ba9c  jb      short loc_18001BA80
0x18001ba9e  mov     rbx, [rbp+47h+var_A8]
0x18001baa2  cmp     eax, esi
0x18001baa4  jz      short loc_18001BADE
0x18001baa6  mov     al, [rbp+47h+var_9E]
0x18001baa9  mov     [rbp+47h+Source], esi
0x18001baac  cmp     al, 1
0x18001baae  jnz     short loc_18001BAC4
0x18001bab0  mov     eax, 2
0x18001bab5  mov     [rbp+47h+var_B0], si
0x18001bab9  mov     r9d, eax
0x18001babc  lea     r8, [rbp+47h+var_B0]
0x18001bac0  mov     edx, eax
0x18001bac2  jmp     short loc_18001BAD4
0x18001bac4  cmp     al, 2
0x18001bac6  jnz     short loc_18001BADE
0x18001bac8  mov     edx, 4; DestinationSize
0x18001bacd  lea     r8, [rbp+47h+Source]; Source
0x18001bad1  mov     r9d, edx; SourceSize
0x18001bad4  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001bad8  call    cs:__imp_memcpy_s
0x18001bade  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001bae2  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001bae6  lea     rcx, [rbp+47h+var_A0]; this
0x18001baea  mov     [rbp+47h+var_A8], rbx
0x18001baee  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001baf3  xor     r9d, r9d
0x18001baf6  mov     sil, al
0x18001baf9  test    al, al
0x18001bafb  jnz     loc_18001B9AA
0x18001bb01  mov     rbx, [rbp+47h+var_A8]
0x18001bb05  mov     [rdi+20h], rbx
0x18001bb09  mov     rcx, r9
0x18001bb0c  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18001bb10  jnz     loc_18001BB9B
0x18001bb16  movzx   eax, [rbp+47h+var_A0]
0x18001bb1a  mov     [rbp+47h+Source], 1
0x18001bb21  mov     [rbp+47h+var_98], r14w
0x18001bb26  mov     [rbp+47h+Buf2], r9
0x18001bb2a  mov     [rbp+47h+Buf2+8], r15
0x18001bb2e  test    ax, ax
0x18001bb31  jnz     short loc_18001BB83
0x18001bb33  movzx   ecx, r14w
0x18001bb37  add     rcx, 2
0x18001bb3b  jmp     short loc_18001BB86
0x18001bb3d  mov     eax, [rbp+47h+arg_28]
0x18001bb40  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18001bb44  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18001bb48  mov     r9, r13; void *
0x18001bb4b  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18001bb4f  mov     rcx, rdi; this
0x18001bb52  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18001bb57  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001bb5c  xor     r9d, r9d
0x18001bb5f  mov     [rbp+47h+var_A8], rax
0x18001bb63  mov     rbx, rax
0x18001bb66  test    rax, rax
0x18001bb69  jnz     short loc_18001BB72
0x18001bb6b  mov     al, 1
0x18001bb6d  jmp     loc_18001BCA0
0x18001bb72  mov     byte ptr [rbp+47h+arg_0], 1
0x18001bb76  jmp     short loc_18001BB7C
0x18001bb78  mov     [rbp+47h+var_A8], rbx
0x18001bb7c  test    sil, sil
0x18001bb7f  jnz     short loc_18001BB09
0x18001bb81  jmp     short loc_18001BB05
0x18001bb83  mov     rcx, rax
0x18001bb86  mov     al, [rbp+47h+var_9E]
0x18001bb89  cmp     al, 1
0x18001bb8b  jnz     short loc_18001BB93
0x18001bb8d  add     rcx, 2
0x18001bb91  jmp     short loc_18001BB9B
0x18001bb93  cmp     al, 2
0x18001bb95  jnz     short loc_18001BB9B
0x18001bb97  add     rcx, 4
0x18001bb9b  movzx   eax, word ptr [rdi+6]
0x18001bb9f  mov     dl, [rdi+8]
0x18001bba2  mov     r8d, [rbp+47h+arg_28]
0x18001bba6  mov     [rbp+47h+var_80], ax
0x18001bbaa  mov     [rbp+47h+var_7E], dl
0x18001bbad  mov     [rbp+47h+var_7C], r8d
0x18001bbb1  mov     [rbp+47h+var_78], r12w
0x18001bbb6  mov     [rbp+47h+var_70], r9
0x18001bbba  mov     [rbp+47h+var_68], r13
0x18001bbbe  test    ax, ax
0x18001bbc1  jnz     short loc_18001BBCB
0x18001bbc3  movzx   eax, r12w
0x18001bbc7  add     rax, 2
0x18001bbcb  cmp     dl, 1
0x18001bbce  jnz     short loc_18001BBD6
0x18001bbd0  add     rax, 2
0x18001bbd4  jmp     short loc_18001BBDF
0x18001bbd6  cmp     dl, 2
0x18001bbd9  jnz     short loc_18001BBDF
0x18001bbdb  add     rax, 4
0x18001bbdf  mov     rdx, [rdi+28h]
0x18001bbe3  lea     rsi, [rax+rcx]
0x18001bbe7  mov     r9, [rdi+20h]
0x18001bbeb  mov     rcx, rdx
0x18001bbee  sub     rcx, r9
0x18001bbf1  cmp     r9, rdx
0x18001bbf4  sbb     rax, rax
0x18001bbf7  and     rax, rcx
0x18001bbfa  cmp     rax, rsi
0x18001bbfd  jb      loc_18001BC9E
0x18001bc03  sub     rdx, rsi
0x18001bc06  lea     rcx, [rsi+rbx]; Destination
0x18001bc0a  sub     rdx, rbx; DestinationSize
0x18001bc0d  sub     r9, rbx; SourceSize
0x18001bc10  mov     r8, rbx; Source
0x18001bc13  call    cs:__imp_memmove_s
0x18001bc19  add     [rdi+20h], rsi
0x18001bc1d  xor     ebx, ebx
0x18001bc1f  cmp     byte ptr [rbp+47h+arg_0], bl
0x18001bc22  jnz     short loc_18001BC37
0x18001bc24  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001bc28  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001bc2c  lea     rcx, [rbp+47h+var_A0]; this
0x18001bc30  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001bc35  jmp     short loc_18001BC84
0x18001bc37  mov     cl, [rbp+47h+var_9E]
0x18001bc3a  test    cl, cl
0x18001bc3c  jz      short loc_18001BC84
0x18001bc3e  mov     eax, [rbp+47h+Source]
0x18001bc41  lea     r8d, [rax+1]
0x18001bc45  cmp     eax, r8d
0x18001bc48  jz      short loc_18001BC84
0x18001bc4a  mov     [rbp+47h+Source], r8d
0x18001bc4e  cmp     cl, 1
0x18001bc51  jnz     short loc_18001BC67
0x18001bc53  mov     r9d, 2
0x18001bc59  mov     [rbp+47h+arg_0], r8w
0x18001bc5e  mov     edx, r9d
0x18001bc61  lea     r8, [rbp+47h+arg_0]
0x18001bc65  jmp     short loc_18001BC7A
0x18001bc67  cmp     cl, 2
0x18001bc6a  jnz     short loc_18001BC84
0x18001bc6c  mov     eax, 4
0x18001bc71  lea     r8, [rbp+47h+Source]; Source
0x18001bc75  mov     r9d, eax; SourceSize
0x18001bc78  mov     edx, eax; DestinationSize
0x18001bc7a  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001bc7e  call    cs:__imp_memcpy_s
0x18001bc84  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001bc88  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001bc8c  lea     rcx, [rbp+47h+var_80]; this
0x18001bc90  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001bc95  mov     byte ptr [rdi+38h], 1
0x18001bc99  jmp     loc_18001BB6B
0x18001bc9e  xor     al, al
0x18001bca0  add     rsp, 0A8h
0x18001bca7  pop     r15
0x18001bca9  pop     r14
0x18001bcab  pop     r13
0x18001bcad  pop     r12
0x18001bcaf  pop     rdi
0x18001bcb0  pop     rsi
0x18001bcb1  pop     rbx
0x18001bcb2  pop     rbp
0x18001bcb3  retn
```
