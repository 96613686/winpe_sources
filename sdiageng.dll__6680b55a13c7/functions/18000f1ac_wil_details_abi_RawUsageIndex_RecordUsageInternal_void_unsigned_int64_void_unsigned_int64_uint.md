# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000f1ac`
- end: `0x18000f52c`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `896`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000effc`

## callees

- `0x18000b304`
- `0x18000e8e0`
- `0x18000f1ac`
- `0x1800123cc`
- `0x180029876`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f2b7`
- `msvcrt!memcpy_s` at `0x18000f350`
- `msvcrt!memcpy_s` at `0x18000f4f6`
- `msvcrt!memcpy_s` at `0x18000f2b7`
- `msvcrt!memcpy_s` at `0x18000f350`
- `msvcrt!memcpy_s` at `0x18000f4f6`
- `msvcrt!memmove_s` at `0x18000f48b`
- `msvcrt!memmove_s` at `0x18000f48b`

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
0x18000f1ac  push    rbp
0x18000f1ae  push    rbx
0x18000f1af  push    rsi
0x18000f1b0  push    rdi
0x18000f1b1  push    r12
0x18000f1b3  push    r13
0x18000f1b5  push    r14
0x18000f1b7  push    r15
0x18000f1b9  lea     rbp, [rsp-0Fh]
0x18000f1be  sub     rsp, 0A8h
0x18000f1c5  mov     rbx, [rcx+18h]
0x18000f1c9  mov     rdi, rcx
0x18000f1cc  xor     ecx, ecx
0x18000f1ce  mov     r13, r9
0x18000f1d1  mov     r14, r8
0x18000f1d4  mov     r15, rdx
0x18000f1d7  test    rbx, rbx
0x18000f1da  jz      loc_18000F516
0x18000f1e0  movzx   eax, word ptr [rdi+2]
0x18000f1e4  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000f1e8  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000f1ec  add     rbx, 0Ah
0x18000f1f0  mov     [rbp+47h+var_A0], ax
0x18000f1f4  xorps   xmm0, xmm0
0x18000f1f7  mov     al, [rdi+4]
0x18000f1fa  mov     [rbp+47h+Source], ecx
0x18000f1fd  mov     [rbp+47h+var_98], cx
0x18000f201  mov     byte ptr [rbp+47h+arg_0], cl
0x18000f204  lea     rcx, [rbp+47h+var_A0]; this
0x18000f208  mov     [rbp+47h+var_9E], al
0x18000f20b  mov     [rbp+47h+var_A8], rbx
0x18000f20f  movdqu  xmmword ptr [rbp+47h+Buf2], xmm0
0x18000f214  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000f219  mov     r12, [rbp+47h+arg_20]
0x18000f21d  jmp     loc_18000F36B
0x18000f222  movzx   eax, [rbp+47h+var_98]
0x18000f226  cmp     r14, rax
0x18000f229  jnz     short loc_18000F241
0x18000f22b  mov     rdx, [rbp+47h+Buf2+8]; Buf2
0x18000f22f  mov     r8, r14; Size
0x18000f232  mov     rcx, r15; Buf1
0x18000f235  call    memcmp_0
0x18000f23a  mov     ecx, eax
0x18000f23c  xor     r9d, r9d
0x18000f23f  jmp     short loc_18000F24A
0x18000f241  movzx   eax, [rbp+47h+var_98]
0x18000f245  mov     ecx, r14d
0x18000f248  sub     ecx, eax
0x18000f24a  test    ecx, ecx
0x18000f24c  js      loc_18000F3F0
0x18000f252  jz      loc_18000F3B5
0x18000f258  mov     rbx, [rbp+47h+var_A8]
0x18000f25c  mov     [rbp+47h+var_A8], rbx
0x18000f260  cmp     [rdi+10h], r9
0x18000f264  jbe     short loc_18000F2CF
0x18000f266  mov     rax, [rdi+20h]
0x18000f26a  xor     edx, edx
0x18000f26c  sub     rax, [rdi+18h]
0x18000f270  mov     rsi, rbx
0x18000f273  div     qword ptr [rdi+10h]
0x18000f277  mov     edx, [rbp+47h+Source]
0x18000f27a  cmp     rdx, rax
0x18000f27d  jbe     short loc_18000F2C0
0x18000f27f  cmp     edx, eax
0x18000f281  jz      short loc_18000F2C0
0x18000f283  mov     edx, eax
0x18000f285  mov     [rbp+47h+Source], eax
0x18000f288  mov     al, [rbp+47h+var_9E]
0x18000f28b  cmp     al, 1
0x18000f28d  jnz     short loc_18000F2A2
0x18000f28f  movzx   eax, dx
0x18000f292  mov     [rbp+47h+var_B0], dx
0x18000f296  mov     r9d, 2
0x18000f29c  lea     r8, [rbp+47h+var_B0]
0x18000f2a0  jmp     short loc_18000F2B0
0x18000f2a2  cmp     al, 2
0x18000f2a4  jnz     short loc_18000F2C0
0x18000f2a6  mov     r9d, 4; SourceSize
0x18000f2ac  lea     r8, [rbp+47h+Source]; Source
0x18000f2b0  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000f2b4  mov     rdx, r9; DestinationSize
0x18000f2b7  call    cs:__imp_memcpy_s
0x18000f2bd  mov     edx, [rbp+47h+Source]
0x18000f2c0  mov     ebx, edx
0x18000f2c2  imul    rbx, [rdi+10h]
0x18000f2c7  add     rbx, rsi
0x18000f2ca  jmp     loc_18000F356
0x18000f2cf  movzx   eax, word ptr [rdi+6]
0x18000f2d3  xorps   xmm0, xmm0
0x18000f2d6  mov     [rbp+47h+var_60], ax
0x18000f2da  mov     esi, r9d
0x18000f2dd  mov     al, [rdi+8]
0x18000f2e0  mov     [rbp+47h+var_5E], al
0x18000f2e3  mov     eax, [rbp+47h+Source]
0x18000f2e6  mov     [rbp+47h+var_5C], r9d
0x18000f2ea  mov     [rbp+47h+var_58], r9w
0x18000f2ef  movdqu  [rbp+47h+var_50], xmm0
0x18000f2f4  test    eax, eax
0x18000f2f6  jz      short loc_18000F31A
0x18000f2f8  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000f2fc  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000f300  lea     rcx, [rbp+47h+var_60]; this
0x18000f304  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000f309  test    al, al
0x18000f30b  mov     eax, [rbp+47h+Source]
0x18000f30e  jz      short loc_18000F316
0x18000f310  inc     esi
0x18000f312  cmp     esi, eax
0x18000f314  jb      short loc_18000F2F8
0x18000f316  mov     rbx, [rbp+47h+var_A8]
0x18000f31a  cmp     eax, esi
0x18000f31c  jz      short loc_18000F356
0x18000f31e  mov     al, [rbp+47h+var_9E]
0x18000f321  mov     [rbp+47h+Source], esi
0x18000f324  cmp     al, 1
0x18000f326  jnz     short loc_18000F33C
0x18000f328  mov     eax, 2
0x18000f32d  mov     [rbp+47h+var_B0], si
0x18000f331  mov     r9d, eax
0x18000f334  lea     r8, [rbp+47h+var_B0]
0x18000f338  mov     edx, eax
0x18000f33a  jmp     short loc_18000F34C
0x18000f33c  cmp     al, 2
0x18000f33e  jnz     short loc_18000F356
0x18000f340  mov     edx, 4; DestinationSize
0x18000f345  lea     r8, [rbp+47h+Source]; Source
0x18000f349  mov     r9d, edx; SourceSize
0x18000f34c  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000f350  call    cs:__imp_memcpy_s
0x18000f356  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000f35a  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000f35e  lea     rcx, [rbp+47h+var_A0]; this
0x18000f362  mov     [rbp+47h+var_A8], rbx
0x18000f366  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000f36b  xor     r9d, r9d
0x18000f36e  mov     sil, al
0x18000f371  test    al, al
0x18000f373  jnz     loc_18000F222
0x18000f379  mov     rbx, [rbp+47h+var_A8]
0x18000f37d  mov     [rdi+20h], rbx
0x18000f381  mov     rcx, r9
0x18000f384  cmp     byte ptr [rbp+47h+arg_0], r9b
0x18000f388  jnz     loc_18000F413
0x18000f38e  movzx   eax, [rbp+47h+var_A0]
0x18000f392  mov     [rbp+47h+Source], 1
0x18000f399  mov     [rbp+47h+var_98], r14w
0x18000f39e  mov     [rbp+47h+Buf2], r9
0x18000f3a2  mov     [rbp+47h+Buf2+8], r15
0x18000f3a6  test    ax, ax
0x18000f3a9  jnz     short loc_18000F3FB
0x18000f3ab  movzx   ecx, r14w
0x18000f3af  add     rcx, 2
0x18000f3b3  jmp     short loc_18000F3FE
0x18000f3b5  mov     eax, [rbp+47h+arg_28]
0x18000f3b8  lea     rdx, [rbp+47h+var_A0]; struct wil::details_abi::UsageIndexProperty *
0x18000f3bc  mov     r8, [rbp+47h+var_A8]; unsigned __int8 *
0x18000f3c0  mov     r9, r13; void *
0x18000f3c3  mov     [rsp+0E0h+var_B8], eax; unsigned int
0x18000f3c7  mov     rcx, rdi; this
0x18000f3ca  mov     [rsp+0E0h+var_C0], r12; unsigned __int64
0x18000f3cf  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000f3d4  xor     r9d, r9d
0x18000f3d7  mov     [rbp+47h+var_A8], rax
0x18000f3db  mov     rbx, rax
0x18000f3de  test    rax, rax
0x18000f3e1  jnz     short loc_18000F3EA
0x18000f3e3  mov     al, 1
0x18000f3e5  jmp     loc_18000F518
0x18000f3ea  mov     byte ptr [rbp+47h+arg_0], 1
0x18000f3ee  jmp     short loc_18000F3F4
0x18000f3f0  mov     [rbp+47h+var_A8], rbx
0x18000f3f4  test    sil, sil
0x18000f3f7  jnz     short loc_18000F381
0x18000f3f9  jmp     short loc_18000F37D
0x18000f3fb  mov     rcx, rax
0x18000f3fe  mov     al, [rbp+47h+var_9E]
0x18000f401  cmp     al, 1
0x18000f403  jnz     short loc_18000F40B
0x18000f405  add     rcx, 2
0x18000f409  jmp     short loc_18000F413
0x18000f40b  cmp     al, 2
0x18000f40d  jnz     short loc_18000F413
0x18000f40f  add     rcx, 4
0x18000f413  movzx   eax, word ptr [rdi+6]
0x18000f417  mov     dl, [rdi+8]
0x18000f41a  mov     r8d, [rbp+47h+arg_28]
0x18000f41e  mov     [rbp+47h+var_80], ax
0x18000f422  mov     [rbp+47h+var_7E], dl
0x18000f425  mov     [rbp+47h+var_7C], r8d
0x18000f429  mov     [rbp+47h+var_78], r12w
0x18000f42e  mov     [rbp+47h+var_70], r9
0x18000f432  mov     [rbp+47h+var_68], r13
0x18000f436  test    ax, ax
0x18000f439  jnz     short loc_18000F443
0x18000f43b  movzx   eax, r12w
0x18000f43f  add     rax, 2
0x18000f443  cmp     dl, 1
0x18000f446  jnz     short loc_18000F44E
0x18000f448  add     rax, 2
0x18000f44c  jmp     short loc_18000F457
0x18000f44e  cmp     dl, 2
0x18000f451  jnz     short loc_18000F457
0x18000f453  add     rax, 4
0x18000f457  mov     rdx, [rdi+28h]
0x18000f45b  lea     rsi, [rax+rcx]
0x18000f45f  mov     r9, [rdi+20h]
0x18000f463  mov     rcx, rdx
0x18000f466  sub     rcx, r9
0x18000f469  cmp     r9, rdx
0x18000f46c  sbb     rax, rax
0x18000f46f  and     rax, rcx
0x18000f472  cmp     rax, rsi
0x18000f475  jb      loc_18000F516
0x18000f47b  sub     rdx, rsi
0x18000f47e  lea     rcx, [rsi+rbx]; Destination
0x18000f482  sub     rdx, rbx; DestinationSize
0x18000f485  sub     r9, rbx; SourceSize
0x18000f488  mov     r8, rbx; Source
0x18000f48b  call    cs:__imp_memmove_s
0x18000f491  add     [rdi+20h], rsi
0x18000f495  xor     ebx, ebx
0x18000f497  cmp     byte ptr [rbp+47h+arg_0], bl
0x18000f49a  jnz     short loc_18000F4AF
0x18000f49c  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000f4a0  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000f4a4  lea     rcx, [rbp+47h+var_A0]; this
0x18000f4a8  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000f4ad  jmp     short loc_18000F4FC
0x18000f4af  mov     cl, [rbp+47h+var_9E]
0x18000f4b2  test    cl, cl
0x18000f4b4  jz      short loc_18000F4FC
0x18000f4b6  mov     eax, [rbp+47h+Source]
0x18000f4b9  lea     r8d, [rax+1]
0x18000f4bd  cmp     eax, r8d
0x18000f4c0  jz      short loc_18000F4FC
0x18000f4c2  mov     [rbp+47h+Source], r8d
0x18000f4c6  cmp     cl, 1
0x18000f4c9  jnz     short loc_18000F4DF
0x18000f4cb  mov     r9d, 2
0x18000f4d1  mov     [rbp+47h+arg_0], r8w
0x18000f4d6  mov     edx, r9d
0x18000f4d9  lea     r8, [rbp+47h+arg_0]
0x18000f4dd  jmp     short loc_18000F4F2
0x18000f4df  cmp     cl, 2
0x18000f4e2  jnz     short loc_18000F4FC
0x18000f4e4  mov     eax, 4
0x18000f4e9  lea     r8, [rbp+47h+Source]; Source
0x18000f4ed  mov     r9d, eax; SourceSize
0x18000f4f0  mov     edx, eax; DestinationSize
0x18000f4f2  mov     rcx, [rbp+47h+Buf2]; Destination
0x18000f4f6  call    cs:__imp_memcpy_s
0x18000f4fc  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000f500  lea     rdx, [rbp+47h+var_A8]; unsigned __int8 **
0x18000f504  lea     rcx, [rbp+47h+var_80]; this
0x18000f508  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000f50d  mov     byte ptr [rdi+38h], 1
0x18000f511  jmp     loc_18000F3E3
0x18000f516  xor     al, al
0x18000f518  add     rsp, 0A8h
0x18000f51f  pop     r15
0x18000f521  pop     r14
0x18000f523  pop     r13
0x18000f525  pop     r12
0x18000f527  pop     rdi
0x18000f528  pop     rsi
0x18000f529  pop     rbx
0x18000f52a  pop     rbp
0x18000f52b  retn
```
