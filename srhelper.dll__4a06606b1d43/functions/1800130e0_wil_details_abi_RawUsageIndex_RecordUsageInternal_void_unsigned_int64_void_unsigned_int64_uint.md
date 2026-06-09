# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800130e0`
- end: `0x180013460`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012f30`

## callees

- `0x18001138c`
- `0x180012aac`
- `0x1800130e0`
- `0x1800148ac`
- `0x1800157a6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800131eb`
- `msvcrt!memcpy_s` at `0x180013284`
- `msvcrt!memcpy_s` at `0x18001342a`
- `msvcrt!memcpy_s` at `0x1800131eb`
- `msvcrt!memcpy_s` at `0x180013284`
- `msvcrt!memcpy_s` at `0x18001342a`
- `msvcrt!memmove_s` at `0x1800133bf`
- `msvcrt!memmove_s` at `0x1800133bf`

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
0x1800130e0  push    rbp
0x1800130e2  push    rbx
0x1800130e3  push    rsi
0x1800130e4  push    rdi
0x1800130e5  push    r12
0x1800130e7  push    r13
0x1800130e9  push    r14
0x1800130eb  push    r15
0x1800130ed  lea     rbp, [rsp-0Fh]
0x1800130f2  sub     rsp, 0A8h
0x1800130f9  mov     rbx, [rcx+18h]
0x1800130fd  mov     rdi, rcx
0x180013100  xor     ecx, ecx
0x180013102  mov     r13, r9
0x180013105  mov     r14, r8
0x180013108  mov     r15, rdx
0x18001310b  test    rbx, rbx
0x18001310e  jz      loc_18001344A
0x180013114  movzx   eax, word ptr [rdi+2]
0x180013118  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18001311c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180013120  add     rbx, 0Ah
0x180013124  mov     [rbp+47h+var_A0], ax
0x180013128  xorps   xmm0, xmm0
0x18001312b  mov     al, [rdi+4]
0x18001312e  mov     [rbp+47h+Source], ecx
0x180013131  mov     [rbp+47h+var_98], cx
0x180013135  mov     byte ptr [rbp+47h+arg_0], cl
0x180013138  lea     rcx, [rbp+47h+var_A0]; this
0x18001313c  mov     [rbp+47h+var_9E], al
0x18001313f  mov     [rbp+47h+var_A8], rbx
0x180013143  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x180013148  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001314d  mov     r12, [rbp+47h+arg_20]
0x180013151  jmp     loc_18001329F
0x180013156  movzx   eax, [rbp+47h+var_98]
0x18001315a  cmp     r14, rax
0x18001315d  jnz     short loc_180013175
0x18001315f  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x180013163  mov     r8, r14; Size
0x180013166  mov     rcx, r15; Buf1
0x180013169  call    memcmp_0
0x18001316e  mov     ecx, eax
0x180013170  xor     r9d, r9d
0x180013173  jmp     short loc_18001317E
0x180013175  movzx   eax, [rbp+47h+var_98]
0x180013179  mov     ecx, r14d
0x18001317c  sub     ecx, eax
0x18001317e  test    ecx, ecx
0x180013180  js      loc_180013324
0x180013186  jz      loc_1800132E9
0x18001318c  mov     rbx, [rbp+47h+var_A8]
0x180013190  mov     [rbp+47h+var_A8], rbx
0x180013194  cmp     [rdi+10h], r9
0x180013198  jbe     short loc_180013203
0x18001319a  mov     rax, [rdi+20h]
0x18001319e  xor     edx, edx
0x1800131a0  sub     rax, [rdi+18h]
0x1800131a4  mov     rsi, rbx
0x1800131a7  div     qword ptr [rdi+10h]
0x1800131ab  mov     edx, [rbp+47h+Source]
0x1800131ae  cmp     rdx, rax
0x1800131b1  jbe     short loc_1800131F4
0x1800131b3  cmp     edx, eax
0x1800131b5  jz      short loc_1800131F4
0x1800131b7  mov     edx, eax
0x1800131b9  mov     [rbp+47h+Source], eax
0x1800131bc  mov     al, [rbp+47h+var_9E]
0x1800131bf  cmp     al, 1
0x1800131c1  jnz     short loc_1800131D6
0x1800131c3  movzx   eax, dx
0x1800131c6  mov     [rbp+47h+var_B0], dx
0x1800131ca  mov     r9d, 2
0x1800131d0  lea     r8, [rbp+47h+var_B0]
0x1800131d4  jmp     short loc_1800131E4
0x1800131d6  cmp     al, 2
0x1800131d8  jnz     short loc_1800131F4
0x1800131da  mov     r9d, 4; SourceSize
0x1800131e0  lea     r8, [rbp+47h+Source]; Source
0x1800131e4  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800131e8  mov     rdx, r9; DestinationSize
0x1800131eb  call    cs:__imp_memcpy_s
0x1800131f1  mov     edx, [rbp+47h+Source]
0x1800131f4  mov     ebx, edx
0x1800131f6  imul    rbx, [rdi+10h]
0x1800131fb  add     rbx, rsi
0x1800131fe  jmp     loc_18001328A
0x180013203  movzx   eax, word ptr [rdi+6]
0x180013207  xorps   xmm0, xmm0
0x18001320a  mov     [rbp+47h+var_60], ax
0x18001320e  mov     esi, r9d
0x180013211  mov     al, [rdi+8]
0x180013214  mov     [rbp+47h+var_5E], al
0x180013217  mov     eax, [rbp+47h+Source]
0x18001321a  mov     [rbp+47h+var_5C], r9d
0x18001321e  mov     [rbp+47h+var_58], r9w
0x180013223  movdqu  [rbp+47h+var_50], xmm0
0x180013228  test    eax, eax
0x18001322a  jz      short loc_18001324E
0x18001322c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180013230  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180013234  lea     rcx, [rbp+47h+var_60]; this
0x180013238  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001323d  test    al, al
0x18001323f  mov     eax, [rbp+47h+Source]
0x180013242  jz      short loc_18001324A
0x180013244  inc     esi
0x180013246  cmp     esi, eax
0x180013248  jb      short loc_18001322C
0x18001324a  mov     rbx, [rbp+47h+var_A8]
0x18001324e  cmp     eax, esi
0x180013250  jz      short loc_18001328A
0x180013252  mov     al, [rbp+47h+var_9E]
0x180013255  mov     [rbp+47h+Source], esi
0x180013258  cmp     al, 1
0x18001325a  jnz     short loc_180013270
0x18001325c  mov     eax, 2
0x180013261  mov     [rbp+47h+var_B0], si
0x180013265  mov     r9d, eax
0x180013268  lea     r8, [rbp+47h+var_B0]
0x18001326c  mov     edx, eax
0x18001326e  jmp     short loc_180013280
0x180013270  cmp     al, 2
0x180013272  jnz     short loc_18001328A
0x180013274  mov     edx, 4; DestinationSize
0x180013279  lea     r8, [rbp+47h+Source]; Source
0x18001327d  mov     r9d, edx; SourceSize
0x180013280  mov     rcx, [rbp+47h+Buf2]; Destination
0x180013284  call    cs:__imp_memcpy_s
0x18001328a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001328e  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180013292  lea     rcx, [rbp+47h+var_A0]; this
0x180013296  mov     [rbp+47h+var_A8], rbx
0x18001329a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001329f  xor     r9d, r9d
0x1800132a2  mov     sil, al
0x1800132a5  test    al, al
0x1800132a7  jnz     loc_180013156
0x1800132ad  mov     rbx, [rbp+47h+var_A8]
0x1800132b1  mov     [rdi+20h], rbx
0x1800132b5  mov     rcx, r9
0x1800132b8  cmp     byte ptr [rbp+47h+arg_0], r9b
0x1800132bc  jnz     loc_180013347
0x1800132c2  movzx   eax, [rbp+47h+var_A0]
0x1800132c6  mov     [rbp+47h+Source], 1
0x1800132cd  mov     [rbp+47h+var_98], r14w
0x1800132d2  mov     [rbp+47h+Buf2], r9
0x1800132d6  mov     [rbp+47h+Buf2+8], r15
0x1800132da  test    ax, ax
0x1800132dd  jnz     short loc_18001332F
0x1800132df  movzx   ecx, r14w
0x1800132e3  add     rcx, 2
0x1800132e7  jmp     short loc_180013332
0x1800132e9  mov     eax, [rbp+47h+arg_28]
0x1800132ec  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x1800132f0  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x1800132f4  mov     r9, r13; void *
0x1800132f7  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x1800132fb  mov     rcx, rdi; this
0x1800132fe  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180013303  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180013308  xor     r9d, r9d
0x18001330b  mov     [rbp+47h+var_A8], rax
0x18001330f  mov     rbx, rax
0x180013312  test    rax, rax
0x180013315  jnz     short loc_18001331E
0x180013317  mov     al, 1
0x180013319  jmp     loc_18001344C
0x18001331e  mov     byte ptr [rbp+47h+arg_0], 1
0x180013322  jmp     short loc_180013328
0x180013324  mov     [rbp+47h+var_A8], rbx
0x180013328  test    sil, sil
0x18001332b  jnz     short loc_1800132B5
0x18001332d  jmp     short loc_1800132B1
0x18001332f  mov     rcx, rax
0x180013332  mov     al, [rbp+47h+var_9E]
0x180013335  cmp     al, 1
0x180013337  jnz     short loc_18001333F
0x180013339  add     rcx, 2
0x18001333d  jmp     short loc_180013347
0x18001333f  cmp     al, 2
0x180013341  jnz     short loc_180013347
0x180013343  add     rcx, 4
0x180013347  movzx   eax, word ptr [rdi+6]
0x18001334b  mov     dl, [rdi+8]
0x18001334e  mov     r8d, [rbp+47h+arg_28]
0x180013352  mov     [rbp+47h+var_80], ax
0x180013356  mov     [rbp+47h+var_7E], dl
0x180013359  mov     [rbp+47h+var_7C], r8d
0x18001335d  mov     [rbp+47h+var_78], r12w
0x180013362  mov     [rbp+47h+var_70], r9
0x180013366  mov     [rbp+47h+var_68], r13
0x18001336a  test    ax, ax
0x18001336d  jnz     short loc_180013377
0x18001336f  movzx   eax, r12w
0x180013373  add     rax, 2
0x180013377  cmp     dl, 1
0x18001337a  jnz     short loc_180013382
0x18001337c  add     rax, 2
0x180013380  jmp     short loc_18001338B
0x180013382  cmp     dl, 2
0x180013385  jnz     short loc_18001338B
0x180013387  add     rax, 4
0x18001338b  mov     rdx, [rdi+28h]
0x18001338f  lea     rsi, [rax+rcx]
0x180013393  mov     r9, [rdi+20h]
0x180013397  mov     rcx, rdx
0x18001339a  sub     rcx, r9
0x18001339d  cmp     r9, rdx
0x1800133a0  sbb     rax, rax
0x1800133a3  and     rax, rcx
0x1800133a6  cmp     rax, rsi
0x1800133a9  jb      loc_18001344A
0x1800133af  sub     rdx, rsi
0x1800133b2  lea     rcx, [rsi+rbx]; Destination
0x1800133b6  sub     rdx, rbx; DestinationSize
0x1800133b9  sub     r9, rbx; SourceSize
0x1800133bc  mov     r8, rbx; Source
0x1800133bf  call    cs:__imp_memmove_s
0x1800133c5  add     [rdi+20h], rsi
0x1800133c9  xor     ebx, ebx
0x1800133cb  cmp     byte ptr [rbp+47h+arg_0], bl
0x1800133ce  jnz     short loc_1800133E3
0x1800133d0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800133d4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800133d8  lea     rcx, [rbp+47h+var_A0]; this
0x1800133dc  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800133e1  jmp     short loc_180013430
0x1800133e3  mov     cl, [rbp+47h+var_9E]
0x1800133e6  test    cl, cl
0x1800133e8  jz      short loc_180013430
0x1800133ea  mov     eax, [rbp+47h+Source]
0x1800133ed  lea     r8d, [rax+1]
0x1800133f1  cmp     eax, r8d
0x1800133f4  jz      short loc_180013430
0x1800133f6  mov     [rbp+47h+Source], r8d
0x1800133fa  cmp     cl, 1
0x1800133fd  jnz     short loc_180013413
0x1800133ff  mov     r9d, 2
0x180013405  mov     [rbp+47h+arg_0], r8w
0x18001340a  mov     edx, r9d
0x18001340d  lea     r8, [rbp+47h+arg_0]
0x180013411  jmp     short loc_180013426
0x180013413  cmp     cl, 2
0x180013416  jnz     short loc_180013430
0x180013418  mov     eax, 4
0x18001341d  lea     r8, [rbp+47h+Source]; Source
0x180013421  mov     r9d, eax; SourceSize
0x180013424  mov     edx, eax; DestinationSize
0x180013426  mov     rcx, [rbp+47h+Buf2]; Destination
0x18001342a  call    cs:__imp_memcpy_s
0x180013430  mov     r8, [rdi+20h]; unsigned __int8 *
0x180013434  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180013438  lea     rcx, [rbp+47h+var_80]; this
0x18001343c  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180013441  mov     byte ptr [rdi+38h], 1
0x180013445  jmp     loc_180013317
0x18001344a  xor     al, al
0x18001344c  add     rsp, 0A8h
0x180013453  pop     r15
0x180013455  pop     r14
0x180013457  pop     r13
0x180013459  pop     r12
0x18001345b  pop     rdi
0x18001345c  pop     rsi
0x18001345d  pop     rbx
0x18001345e  pop     rbp
0x18001345f  retn
```
