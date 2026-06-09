# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007164`
- end: `0x1800074e1`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `893`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180006fb4`

## callees

- `0x180001f8c`
- `0x180004d80`
- `0x180006948`
- `0x180007164`
- `0x180008c2c`
- `0x18000dbf4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180007441`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180007441`

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
0x180007164  push    rbp
0x180007166  push    rbx
0x180007167  push    rsi
0x180007168  push    rdi
0x180007169  push    r12
0x18000716b  push    r13
0x18000716d  push    r14
0x18000716f  push    r15
0x180007171  lea     rbp, [rsp-0Fh]
0x180007176  sub     rsp, 0A8h
0x18000717d  mov     rbx, [rcx+18h]
0x180007181  mov     rdi, rcx
0x180007184  xor     ecx, ecx
0x180007186  mov     r13, r9
0x180007189  mov     r14, r8
0x18000718c  mov     r15, rdx
0x18000718f  test    rbx, rbx
0x180007192  jz      loc_1800074CB
0x180007198  movzx   eax, word ptr [rdi+2]
0x18000719c  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800071a0  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800071a4  add     rbx, 0Ah
0x1800071a8  mov     [rbp+47h+var_A0], ax
0x1800071ac  xorps   xmm0, xmm0
0x1800071af  mov     al, [rdi+4]
0x1800071b2  mov     [rbp+47h+Source], ecx
0x1800071b5  mov     [rbp+47h+var_98], cx
0x1800071b9  mov     byte ptr [rbp+47h+arg_0], cl
0x1800071bc  lea     rcx, [rbp+47h+var_A0]; this
0x1800071c0  mov     [rbp+47h+var_9E], al
0x1800071c3  mov     [rbp+47h+var_A8], rbx
0x1800071c7  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x1800071cc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800071d1  mov     r12, [rbp+47h+arg_20]
0x1800071d5  jmp     loc_180007321
0x1800071da  movzx   eax, [rbp+47h+var_98]
0x1800071de  cmp     r14, rax
0x1800071e1  jnz     short loc_1800071F9
0x1800071e3  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x1800071e7  mov     r8, r14; Size
0x1800071ea  mov     rcx, r15; Buf1
0x1800071ed  call    memcmp_0
0x1800071f2  mov     ecx, eax
0x1800071f4  xor     r9d, r9d
0x1800071f7  jmp     short loc_180007202
0x1800071f9  movzx   eax, [rbp+47h+var_98]
0x1800071fd  mov     ecx, r14d
0x180007200  sub     ecx, eax
0x180007202  test    ecx, ecx
0x180007204  js      loc_1800073A6
0x18000720a  jz      loc_18000736B
0x180007210  mov     rbx, [rbp+47h+var_A8]
0x180007214  mov     [rbp+47h+var_A8], rbx
0x180007218  cmp     [rdi+10h], r9
0x18000721c  jbe     short loc_180007286
0x18000721e  mov     rax, [rdi+20h]
0x180007222  xor     edx, edx
0x180007224  sub     rax, [rdi+18h]
0x180007228  mov     rsi, rbx
0x18000722b  div     qword ptr [rdi+10h]
0x18000722f  mov     edx, [rbp+47h+Source]
0x180007232  cmp     rdx, rax
0x180007235  jbe     short loc_180007277
0x180007237  cmp     edx, eax
0x180007239  jz      short loc_180007277
0x18000723b  mov     edx, eax
0x18000723d  mov     [rbp+47h+Source], eax
0x180007240  mov     al, [rbp+47h+var_9E]
0x180007243  cmp     al, 1
0x180007245  jnz     short loc_18000725A
0x180007247  movzx   eax, dx
0x18000724a  mov     [rbp+47h+var_B0], dx
0x18000724e  mov     r9d, 2
0x180007254  lea     r8, [rbp+47h+var_B0]
0x180007258  jmp     short loc_180007268
0x18000725a  cmp     al, 2
0x18000725c  jnz     short loc_180007277
0x18000725e  mov     r9d, 4; SourceSize
0x180007264  lea     r8, [rbp+47h+Source]; Source
0x180007268  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000726c  mov     rdx, r9; DestinationSize
0x18000726f  call    memcpy_s
0x180007274  mov     edx, [rbp+47h+Source]
0x180007277  mov     ebx, edx
0x180007279  imul    rbx, [rdi+10h]
0x18000727e  add     rbx, rsi
0x180007281  jmp     loc_18000730C
0x180007286  movzx   eax, word ptr [rdi+6]
0x18000728a  xorps   xmm0, xmm0
0x18000728d  mov     [rbp+47h+var_60], ax
0x180007291  mov     esi, r9d
0x180007294  mov     al, [rdi+8]
0x180007297  mov     [rbp+47h+var_5E], al
0x18000729a  mov     eax, [rbp+47h+Source]
0x18000729d  mov     [rbp+47h+var_5C], r9d
0x1800072a1  mov     [rbp+47h+var_58], r9w
0x1800072a6  movdqu  [rbp+47h+var_50], xmm0
0x1800072ab  test    eax, eax
0x1800072ad  jz      short loc_1800072D1
0x1800072af  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800072b3  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800072b7  lea     rcx, [rbp+47h+var_60]; this
0x1800072bb  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800072c0  test    al, al
0x1800072c2  mov     eax, [rbp+47h+Source]
0x1800072c5  jz      short loc_1800072CD
0x1800072c7  inc     esi
0x1800072c9  cmp     esi, eax
0x1800072cb  jb      short loc_1800072AF
0x1800072cd  mov     rbx, [rbp+47h+var_A8]
0x1800072d1  cmp     eax, esi
0x1800072d3  jz      short loc_18000730C
0x1800072d5  mov     al, [rbp+47h+var_9E]
0x1800072d8  mov     [rbp+47h+Source], esi
0x1800072db  cmp     al, 1
0x1800072dd  jnz     short loc_1800072F3
0x1800072df  mov     eax, 2
0x1800072e4  mov     [rbp+47h+var_B0], si
0x1800072e8  mov     r9d, eax
0x1800072eb  lea     r8, [rbp+47h+var_B0]
0x1800072ef  mov     edx, eax
0x1800072f1  jmp     short loc_180007303
0x1800072f3  cmp     al, 2
0x1800072f5  jnz     short loc_18000730C
0x1800072f7  mov     edx, 4; DestinationSize
0x1800072fc  lea     r8, [rbp+47h+Source]; Source
0x180007300  mov     r9d, edx; SourceSize
0x180007303  mov     rcx, [rbp+47h+Buf2]; Destination
0x180007307  call    memcpy_s
0x18000730c  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007310  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x180007314  lea     rcx, [rbp+47h+var_A0]; this
0x180007318  mov     [rbp+47h+var_A8], rbx
0x18000731c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007321  xor     r9d, r9d
0x180007324  mov     sil, al
0x180007327  test    al, al
0x180007329  jnz     loc_1800071DA
0x18000732f  mov     rbx, [rbp+47h+var_A8]
0x180007333  mov     [rdi+20h], rbx
0x180007337  mov     rcx, r9
0x18000733a  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000733e  jnz     loc_1800073C9
0x180007344  movzx   eax, [rbp+47h+var_A0]
0x180007348  mov     [rbp+47h+Source], 1
0x18000734f  mov     [rbp+47h+var_98], r14w
0x180007354  mov     [rbp+47h+Buf2], r9
0x180007358  mov     [rbp+47h+Buf2+8], r15
0x18000735c  test    ax, ax
0x18000735f  jnz     short loc_1800073B1
0x180007361  movzx   ecx, r14w
0x180007365  add     rcx, 2
0x180007369  jmp     short loc_1800073B4
0x18000736b  mov     eax, [rbp+47h+arg_28]
0x18000736e  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x180007372  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x180007376  mov     r9, r13; void *
0x180007379  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000737d  mov     rcx, rdi; this
0x180007380  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x180007385  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000738a  xor     r9d, r9d
0x18000738d  mov     [rbp+47h+var_A8], rax
0x180007391  mov     rbx, rax
0x180007394  test    rax, rax
0x180007397  jnz     short loc_1800073A0
0x180007399  mov     al, 1
0x18000739b  jmp     loc_1800074CD
0x1800073a0  mov     byte ptr [rbp+47h+arg_0], 1
0x1800073a4  jmp     short loc_1800073AA
0x1800073a6  mov     [rbp+47h+var_A8], rbx
0x1800073aa  test    sil, sil
0x1800073ad  jnz     short loc_180007337
0x1800073af  jmp     short loc_180007333
0x1800073b1  mov     rcx, rax
0x1800073b4  mov     al, [rbp+47h+var_9E]
0x1800073b7  cmp     al, 1
0x1800073b9  jnz     short loc_1800073C1
0x1800073bb  add     rcx, 2
0x1800073bf  jmp     short loc_1800073C9
0x1800073c1  cmp     al, 2
0x1800073c3  jnz     short loc_1800073C9
0x1800073c5  add     rcx, 4
0x1800073c9  movzx   eax, word ptr [rdi+6]
0x1800073cd  mov     dl, [rdi+8]
0x1800073d0  mov     r8d, [rbp+47h+arg_28]
0x1800073d4  mov     [rbp+47h+var_80], ax
0x1800073d8  mov     [rbp+47h+var_7E], dl
0x1800073db  mov     [rbp+47h+var_7C], r8d
0x1800073df  mov     [rbp+47h+var_78], r12w
0x1800073e4  mov     [rbp+47h+var_70], r9
0x1800073e8  mov     [rbp+47h+var_68], r13
0x1800073ec  test    ax, ax
0x1800073ef  jnz     short loc_1800073F9
0x1800073f1  movzx   eax, r12w
0x1800073f5  add     rax, 2
0x1800073f9  cmp     dl, 1
0x1800073fc  jnz     short loc_180007404
0x1800073fe  add     rax, 2
0x180007402  jmp     short loc_18000740D
0x180007404  cmp     dl, 2
0x180007407  jnz     short loc_18000740D
0x180007409  add     rax, 4
0x18000740d  mov     rdx, [rdi+28h]
0x180007411  lea     rsi, [rax+rcx]
0x180007415  mov     r9, [rdi+20h]
0x180007419  mov     rcx, rdx
0x18000741c  sub     rcx, r9
0x18000741f  cmp     r9, rdx
0x180007422  sbb     rax, rax
0x180007425  and     rax, rcx
0x180007428  cmp     rax, rsi
0x18000742b  jb      loc_1800074CB
0x180007431  sub     rdx, rsi
0x180007434  lea     rcx, [rsi+rbx]; Destination
0x180007438  sub     rdx, rbx; DestinationSize
0x18000743b  sub     r9, rbx; SourceSize
0x18000743e  mov     r8, rbx; Source
0x180007441  call    cs:__imp_memmove_s
0x180007447  add     [rdi+20h], rsi
0x18000744b  xor     ebx, ebx
0x18000744d  cmp     byte ptr [rbp+47h+arg_0], bl
0x180007450  jnz     short loc_180007465
0x180007452  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007456  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000745a  lea     rcx, [rbp+47h+var_A0]; this
0x18000745e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007463  jmp     short loc_1800074B1
0x180007465  mov     cl, [rbp+47h+var_9E]
0x180007468  test    cl, cl
0x18000746a  jz      short loc_1800074B1
0x18000746c  mov     eax, [rbp+47h+Source]
0x18000746f  lea     r8d, [rax+1]
0x180007473  cmp     eax, r8d
0x180007476  jz      short loc_1800074B1
0x180007478  mov     [rbp+47h+Source], r8d
0x18000747c  cmp     cl, 1
0x18000747f  jnz     short loc_180007495
0x180007481  mov     r9d, 2
0x180007487  mov     [rbp+47h+arg_0], r8w
0x18000748c  mov     edx, r9d
0x18000748f  lea     r8, [rbp+47h+arg_0]
0x180007493  jmp     short loc_1800074A8
0x180007495  cmp     cl, 2
0x180007498  jnz     short loc_1800074B1
0x18000749a  mov     eax, 4
0x18000749f  lea     r8, [rbp+47h+Source]; Source
0x1800074a3  mov     r9d, eax; SourceSize
0x1800074a6  mov     edx, eax; DestinationSize
0x1800074a8  mov     rcx, [rbp+47h+Buf2]; Destination
0x1800074ac  call    memcpy_s
0x1800074b1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800074b5  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x1800074b9  lea     rcx, [rbp+47h+var_80]; this
0x1800074bd  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800074c2  mov     byte ptr [rdi+38h], 1
0x1800074c6  jmp     loc_180007399
0x1800074cb  xor     al, al
0x1800074cd  add     rsp, 0A8h
0x1800074d4  pop     r15
0x1800074d6  pop     r14
0x1800074d8  pop     r13
0x1800074da  pop     r12
0x1800074dc  pop     rdi
0x1800074dd  pop     rsi
0x1800074de  pop     rbx
0x1800074df  pop     rbp
0x1800074e0  retn
```
