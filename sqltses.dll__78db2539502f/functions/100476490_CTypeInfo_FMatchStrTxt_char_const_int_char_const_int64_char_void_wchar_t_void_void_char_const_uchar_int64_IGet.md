# CTypeInfo::FMatchStrTxt(char const *,int,char const *,__int64,char (*)(void *),wchar_t (*)(void *),void *,char const *,uchar *,__int64 *,IGetDynWorkBuffer *)

- ea: `0x100476490`
- end: `0x100476c4d`
- name: `?FMatchStrTxt@CTypeInfo@@QEBA_NPEBDH0_JP6ADPEAX@ZP6A_W2@Z20PEAEPEA_JPEAVIGetDynWorkBuffer@@@Z`
- size: `1981`
- prototype: `bool __fastcall(CTypeInfo *__hidden this, const char *, int, const char *, __int64, char (*)(void *), wchar_t (*)(void *), void *, const char *, unsigned __int8 *, __int64 *, struct IGetDynWorkBuffer *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1007e1350`

## callees

- `0x100401170`
- `0x1004013e0`
- `0x100401450`
- `0x100401480`
- `0x1004024b0`
- `0x10040bca0`
- `0x10040ce20`
- `0x100424910`
- `0x10046d890`
- `0x10046ee00`
- `0x100472090`
- `0x100476490`
- `0x1004a0f00`

## import_xrefs

- `sqldk!SystemThread_TlsIndex` at `0x10047675a`
- `sqldk!SystemThread_TlsIndex` at `0x100476a16`
- `sqldk!SystemThread_TlsOffset` at `0x100476763`
- `sqldk!SystemThread_TlsOffset` at `0x100476a1f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10047677e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100476a3a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10047677e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100476a3a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047657e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10047657e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_BOOL8 __fastcall CTypeInfo::FMatchStrTxt(
        CTypeInfo *this,
        const char *a2,
        unsigned int a3,
        const char *a4,
        __int64 a5,
        char (*a6)(void *),
        wchar_t (*a7)(void *),
        _QWORD *a8,
        const char *a9,
        unsigned __int8 *a10,
        __int64 *a11,
        struct IGetDynWorkBuffer *a12)
{
  unsigned __int64 v12; // rbp
  int v16; // ecx
  unsigned int v17; // r15d
  int v18; // ecx
  __int64 *v19; // rax
  __int64 v20; // rsi
  __int64 v21; // r8
  int v22; // ecx
  _QWORD *v23; // rcx
  int v24; // edx
  char matched; // al
  __int64 v26; // rbx
  __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // r9
  bool v31; // al
  int v32; // r9d
  int v33; // r9d
  int v34; // r10d
  unsigned __int64 v35; // rax
  __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  void *v38; // rsp
  void *v39; // rsp
  int v40; // r12d
  unsigned __int64 v41; // rdi
  int v42; // eax
  int v43; // r10d
  const char *v44; // r8
  int v45; // edx
  char *v46; // rcx
  unsigned int v47; // edx
  int v48; // eax
  bool v49; // di
  __int64 v50; // r14
  __int64 v51; // rbx
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rax
  int v55; // r9d
  int v56; // r9d
  unsigned int v57; // edx
  __int16 v58; // ax
  __int16 v59; // cx
  int v61; // [rsp+20h] [rbp-90h]
  wchar_t v62[32]; // [rsp+70h] [rbp-40h] BYREF
  wchar_t v63; // [rsp+B0h] [rbp+0h] BYREF
  __int64 v64; // [rsp+1B8h] [rbp+108h]

  v64 = -2;
  v12 = (unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL;
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x100) = (unsigned __int64)v62 ^ _security_cookie;
  v16 = *((_DWORD *)this + 5);
  if ( (v16 & 0x80) != 0 )
  {
    v17 = 65001;
  }
  else if ( HIBYTE(v16) )
  {
    v17 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v16)]);
  }
  else
  {
    v17 = qword_100856AB0[4 * (v16 & 0x7F)];
  }
  v18 = 0;
  v19 = (__int64 *)((char *)CSortCacheForSqlCollations::m_pSortCache + 1936);
  while ( 1 )
  {
    v20 = *v19;
    if ( *v19 )
    {
      if ( *(_DWORD *)(v20 + 16) == v17 )
        break;
    }
    ++v18;
    ++v19;
    if ( v18 >= 17 )
    {
      ex_raise(27, 75, 16, 1, v17);
      v20 = 0;
      break;
    }
  }
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = &CCompareHashInfo::`vftable';
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = &CSQLCollation::`vftable';
  *(_OWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = 0;
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = 0;
  *(_DWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = 0;
  *(_BYTE *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0xDD) = 0;
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = &CCompareString::`vftable';
  CTypeInfo::FillCS(this, (struct CCompareString *)(v12 + 128));
  if ( v20 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(v20 + 32) + 96LL))(v20 + 32) )
    goto LABEL_16;
  if ( *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0)
    || !*(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) )
  {
    matched = TMatchPattern<char,CCharHelper>::match_pattern(
                (int)v12 + 128,
                (_DWORD)a2,
                a3,
                0,
                a8[5],
                (__int64)a9,
                (__int64)a6,
                (__int64)a8,
                (__int64)a11,
                1);
    goto LABEL_80;
  }
  if ( v20 )
  {
LABEL_16:
    if ( a3 )
    {
      _mm_lfence();
      LOBYTE(v61) = 0;
      a3 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, _QWORD, int))(*(_QWORD *)(v20 + 32) + 80LL))(
             v20 + 32,
             a2,
             a3,
             a3,
             v61);
    }
    else
    {
      a3 = 0;
    }
  }
  if ( CTypeInfo::FAnyBinarySort(this) )
  {
    v22 = *((_DWORD *)this + 5);
    if ( (v22 & 0x80) != 0 )
    {
      v23 = a8;
    }
    else
    {
      if ( HIBYTE(v22) )
        v24 = *((_DWORD *)&x_uiCodePage + (unsigned __int8)byte_10085C9DC[40 * HIBYTE(v22)]);
      else
        v24 = qword_100856AB0[4 * (v22 & 0x7F)];
      v23 = a8;
      if ( v24 != 65001 )
      {
        matched = TMatchPattern<char,CDBCSBinaryHelper>::match_pattern(v12 + 128, a2, a3, 0, a8[5], a9, a6, a8, a11, 1);
        goto LABEL_80;
      }
    }
    matched = TMatchPattern<char,CUtf8BinaryHelper>::match_pattern(v12 + 128, a2, a3, 0, v23[5], a9, a6, v23, a11, 1);
LABEL_80:
    v49 = matched;
    goto LABEL_81;
  }
  v26 = 0;
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = 0;
  if ( v20 )
  {
    v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v28 = *(_QWORD *)(v27 + 256);
    if ( !v28 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v28 = *(_QWORD *)(v27 + 256);
    }
    LOBYTE(v21) = 1;
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v20 + 32) + 88LL))(
            v20 + 32,
            *(_QWORD *)(v28 + 1000),
            v21);
    *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v26;
    (**(void (__fastcall ***)(__int64, _QWORD))v26)(v26, a8[6]);
    v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
  }
  else
  {
    v29 = a8[5];
  }
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v29;
  CTypeInfo::Init((CTypeInfo *)(v12 + 32), 0xE7u);
  v30 = *(unsigned __int8 *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
  if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v30))
    || (((_BYTE)v30 - 35) & 0xBF) == 0 )
  {
    v31 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)(v12 + 32));
    v32 = *(_DWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34);
    if ( v31 )
      v32 = -1;
    *(_DWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = v32;
  }
  if ( CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)(v12 + 32)) )
    v33 = v34;
  *(_DWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x34) = v33;
  v35 = 2LL * (int)a3;
  v36 = v35 + 15;
  if ( v35 + 15 < v35 )
    v36 = 0xFFFFFFFFFFFFFF0LL;
  v37 = v36 & 0xFFFFFFFFFFFFFFF0uLL;
  v38 = alloca(v37);
  v39 = alloca(v37);
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = v62;
  v40 = FastDBCSToUnicode(v17, a2, a3, v62, a3);
  *(_WORD *)v12 = -1;
  if ( a9 && v20 )
  {
    v41 = (unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL;
    v42 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v20 + 32) + 16LL))(v20 + 32, *(unsigned __int8 *)a9);
    v43 = v42;
    v44 = a9;
    if ( v17 >= 2 )
    {
      v45 = 0;
      v46 = (char *)CSortCacheForSqlCollations::m_pSortCache + 1936;
      while ( !*(_QWORD *)v46 || *(_DWORD *)(*(_QWORD *)v46 + 16LL) != v17 )
      {
        ++v45;
        v46 += 8;
        if ( v45 >= 17 )
          goto LABEL_49;
      }
    }
    if ( v42 == -1 )
    {
      while ( 1 )
      {
        v59 = *v44;
        if ( *v44 > 0x7Fu )
          break;
        *(_WORD *)v41 = v59;
        ++v44;
        if ( (_BYTE)v59 )
        {
          v41 += 2LL;
          if ( v44 != a9 + 1 )
            continue;
        }
        goto LABEL_50;
      }
    }
    else
    {
      if ( !v42 )
        goto LABEL_50;
      v55 = 1;
      if ( v42 < 1 )
        v55 = v42;
      v56 = v55 >> 2;
      if ( !v56 )
      {
        do
        {
LABEL_68:
          v58 = *v44;
          if ( v44 == a9 + 1 )
            break;
          if ( (unsigned __int8)v58 > 0x7Fu )
            goto LABEL_49;
          *(_WORD *)v41 = v58;
          v41 += 2LL;
          ++v44;
          --v43;
        }
        while ( v43 );
        goto LABEL_50;
      }
      while ( 1 )
      {
        v57 = *(_DWORD *)v44;
        if ( (*(_DWORD *)v44 & 0x80808080) != 0 )
          break;
        *(_DWORD *)v41 = *(_DWORD *)v44 & 0x7F | ((*(_DWORD *)v44 & 0x7F00) << 8);
        *(_DWORD *)(v41 + 4) = HIWORD(v57) & 0x7F | ((HIWORD(v57) & 0x7F00) << 8);
        v44 += 4;
        v41 += 8LL;
        v43 -= 4;
        if ( !--v56 )
        {
          if ( v43 )
            goto LABEL_68;
          goto LABEL_50;
        }
      }
    }
LABEL_49:
    EsMultiByteToWideChar(v17, 0, v44, v43, (wchar_t *)v41, 1 - ((_DWORD)v44 - (_DWORD)a9));
  }
LABEL_50:
  v47 = 738197504;
  if ( v17 != 65001 )
    v47 = 671088640;
  v48 = CTypeInfo::MatchStringW(
          (CTypeInfo *)(v12 + 32),
          v47,
          *(const wchar_t **)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40),
          v40,
          0,
          *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18),
          a7,
          a8,
          *(_WORD *)v12,
          a10,
          (__int64 *)(v12 + 16),
          0,
          a12);
  v49 = v48 == 2;
  if ( v48 == 2 && v20 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(v20 + 32) + 104LL))(v20 + 32) )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 8LL))(
      v26,
      *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10));
    v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 48LL))(v26);
    v51 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v52 = *(_QWORD *)(v51 + 256);
    if ( !v52 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v52 = *(_QWORD *)(v51 + 256);
    }
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(v20 + 32) + 88LL))(
            v20 + 32,
            *(_QWORD *)(v52 + 1000),
            0);
    v53 = *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
    if ( v53 != v26 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v53 + 96LL))(v53, 1);
    *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v26;
    (**(void (__fastcall ***)(__int64, _QWORD))v26)(v26, a8[6]);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, v50);
    v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 56LL))(v26);
    *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v54;
  }
  else
  {
    v54 = *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
  }
  *a11 = v54 + 1;
  if ( v26 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 96LL))(v26, 1);
LABEL_81:
  *(_QWORD *)(((unsigned __int64)&v63 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = &CCompareHashInfo::`vftable';
  return v49;
}

```

## disassembly

```asm
0x100476490  push    r13
0x100476492  push    rbp
0x100476493  push    r12
0x100476495  push    r14
0x100476497  push    r15
0x100476499  sub     rsp, 1C0h
0x1004764a0  lea     r13, [rsp+1E8h+var_178]
0x1004764a5  mov     qword ptr [r13+148h], 0FFFFFFFFFFFFFFFEh
0x1004764b0  mov     [r13+180h], rbx
0x1004764b7  mov     [r13+188h], rsi
0x1004764be  mov     [r13+190h], rdi
0x1004764c5  lea     rbp, [rsp+0B0h]
0x1004764cd  and     rbp, 0FFFFFFFFFFFFFFC0h
0x1004764d1  mov     rax, cs:__security_cookie
0x1004764d8  xor     rax, r13
0x1004764db  mov     [rbp+138h+var_38], rax
0x1004764e2  mov     edi, r8d
0x1004764e5  mov     r12, rdx
0x1004764e8  mov     r14, rcx
0x1004764eb  mov     ecx, [rcx+14h]
0x1004764ee  mov     eax, ecx
0x1004764f0  shr     eax, 7
0x1004764f3  lea     rbx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004764fa  test    al, 1
0x1004764fc  jz      short loc_100476506
0x1004764fe  mov     r15d, 0FDE9h
0x100476504  jmp     short loc_10047653A
0x100476506  mov     eax, ecx
0x100476508  shr     eax, 18h
0x10047650b  test    al, al
0x10047650d  jnz     short loc_100476523
0x10047650f  movzx   eax, cl
0x100476512  and     eax, 7Fh
0x100476515  shl     rax, 5
0x100476519  mov     r15d, [rax+rbx+456AB0h]
0x100476521  jmp     short loc_10047653A
0x100476523  movzx   eax, al
0x100476526  lea     rcx, [rax+rax*4]
0x10047652a  movzx   eax, ds:rva byte_10085C9DC[rbx+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x100476532  mov     r15d, ds:rva ?x_uiCodePage@@3QBIB[rbx+rax*4]; CTypeInfo const CTypeInfo::tiBit
0x10047653a  mov     rax, cs:?m_pSortCache@CSortCacheForSqlCollations@@0PEAV1@EA; CSortCacheForSqlCollations * CSortCacheForSqlCollations::m_pSortCache
0x100476541  xor     edx, edx
0x100476543  mov     ecx, edx
0x100476545  add     rax, 790h
0x10047654b  nop     dword ptr [rax+rax+00h]
0x100476550  mov     rsi, [rax]
0x100476553  test    rsi, rsi
0x100476556  jz      short loc_10047655E
0x100476558  cmp     [rsi+10h], r15d
0x10047655c  jz      short loc_100476588
0x10047655e  inc     ecx
0x100476560  add     rax, 8
0x100476564  cmp     ecx, 11h
0x100476567  jl      short loc_100476550
0x100476569  mov     dword ptr [rsp+1E8h+var_1C8], r15d
0x10047656e  mov     edx, 4Bh ; 'K'
0x100476573  lea     ecx, [rdx-30h]
0x100476576  lea     r9d, [rdx-4Ah]
0x10047657a  lea     r8d, [rdx-3Bh]
0x10047657e  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100476584  xor     edx, edx
0x100476586  mov     esi, edx
0x100476588  lea     rax, ??_7CCompareHashInfo@@6B@; const CCompareHashInfo::`vftable'
0x10047658f  mov     [rbp+138h+var_B8], rax
0x100476596  lea     rax, ??_7CSQLCollation@@6B@; const CSQLCollation::`vftable'
0x10047659d  mov     [rbp+138h+var_B8], rax
0x1004765a4  xorps   xmm0, xmm0
0x1004765a7  movdqa  [rbp+138h+var_78], xmm0
0x1004765af  mov     [rbp+138h+var_68], 0
0x1004765ba  mov     [rbp+138h+var_60], edx
0x1004765c0  mov     [rbp+138h+var_5B], 0
0x1004765c7  lea     rax, ??_7CCompareString@@6B@; const CCompareString::`vftable'
0x1004765ce  mov     [rbp+138h+var_B8], rax
0x1004765d5  lea     rdx, [rbp+138h+var_B8]; struct CCompareString *
0x1004765dc  mov     rcx, r14; this
0x1004765df  call    ?FillCS@CTypeInfo@@QEBAXPEAVCCompareString@@@Z; CTypeInfo::FillCS(CCompareString *)
0x1004765e4  test    rsi, rsi
0x1004765e7  jz      short loc_1004765F7
0x1004765e9  lea     rcx, [rsi+20h]
0x1004765ed  mov     rax, [rcx]
0x1004765f0  call    qword ptr [rax+60h]
0x1004765f3  test    al, al
0x1004765f5  jnz     short loc_100476618
0x1004765f7  cmp     qword ptr [rbp+138h+var_78], 0
0x1004765ff  jnz     loc_100476BB0
0x100476605  cmp     qword ptr [rbp+138h+var_78+8], 0
0x10047660d  jz      loc_100476BB0
0x100476613  test    rsi, rsi
0x100476616  jz      short loc_10047663D
0x100476618  test    edi, edi
0x10047661a  jz      short loc_10047663B
0x10047661c  lfence
0x10047661f  lea     rcx, [rsi+20h]
0x100476623  mov     rax, [rcx]
0x100476626  mov     byte ptr [rsp+1E8h+var_1C8], 0
0x10047662b  mov     r9d, edi
0x10047662e  mov     r8d, edi
0x100476631  mov     rdx, r12
0x100476634  call    qword ptr [rax+50h]
0x100476637  mov     edi, eax
0x100476639  jmp     short loc_10047663D
0x10047663b  xor     edi, edi
0x10047663d  mov     rcx, r14; this
0x100476640  call    ?FAnyBinarySort@CTypeInfo@@QEBA_NXZ; CTypeInfo::FAnyBinarySort(void)
0x100476645  test    al, al
0x100476647  jz      loc_100476746
0x10047664d  mov     ecx, [r14+14h]
0x100476651  mov     eax, ecx
0x100476653  shr     eax, 7
0x100476656  test    al, 1
0x100476658  jz      short loc_100476663
0x10047665a  mov     rcx, [r13+1B8h]
0x100476661  jmp     short loc_1004766A4
0x100476663  mov     eax, ecx
0x100476665  shr     eax, 18h
0x100476668  test    al, al
0x10047666a  jnz     short loc_10047667F
0x10047666c  movzx   eax, cl
0x10047666f  and     eax, 7Fh
0x100476672  shl     rax, 5
0x100476676  mov     edx, [rax+rbx+456AB0h]
0x10047667d  jmp     short loc_100476695
0x10047667f  movzx   eax, al
0x100476682  lea     rcx, [rax+rax*4]
0x100476686  movzx   eax, ds:rva byte_10085C9DC[rbx+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x10047668e  mov     edx, ds:rva ?x_uiCodePage@@3QBIB[rbx+rax*4]; CTypeInfo const CTypeInfo::tiBit
0x100476695  mov     rcx, [r13+1B8h]
0x10047669c  cmp     edx, 0FDE9h
0x1004766a2  jnz     short loc_1004766F5
0x1004766a4  mov     byte ptr [rsp+1E8h+var_1A0], 1
0x1004766a9  mov     rax, [r13+1D0h]
0x1004766b0  mov     qword ptr [rsp+1E8h+var_1A8], rax
0x1004766b5  mov     [rsp+1E8h+var_1B0], rcx
0x1004766ba  mov     rax, [r13+1A8h]
0x1004766c1  mov     [rsp+1E8h+var_1B8], rax
0x1004766c6  mov     rax, [r13+1C0h]
0x1004766cd  mov     [rsp+1E8h+var_1C0], rax
0x1004766d2  mov     rax, [rcx+28h]
0x1004766d6  mov     [rsp+1E8h+var_1C8], rax
0x1004766db  xor     r9d, r9d
0x1004766de  mov     r8d, edi
0x1004766e1  mov     rdx, r12
0x1004766e4  lea     rcx, [rbp+138h+var_B8]
0x1004766eb  call    ?match_pattern@?$TMatchPattern@DVCUtf8BinaryHelper@@@@SA_NPEBVCCompareString@@PEFBDH1_K1P6ADPEAX@Z3PEFA_J_N@Z; TMatchPattern<char,CUtf8BinaryHelper>::match_pattern(CCompareString const *,char const *,int,char const *,unsigned __int64,char const *,char (*)(void *),void *,__int64 *,bool)
0x1004766f0  jmp     loc_100476C03
0x1004766f5  mov     byte ptr [rsp+1E8h+var_1A0], 1
0x1004766fa  mov     rax, [r13+1D0h]
0x100476701  mov     qword ptr [rsp+1E8h+var_1A8], rax
0x100476706  mov     [rsp+1E8h+var_1B0], rcx
0x10047670b  mov     rax, [r13+1A8h]
0x100476712  mov     [rsp+1E8h+var_1B8], rax
0x100476717  mov     rax, [r13+1C0h]
0x10047671e  mov     [rsp+1E8h+var_1C0], rax
0x100476723  mov     rax, [rcx+28h]
0x100476727  mov     [rsp+1E8h+var_1C8], rax
0x10047672c  xor     r9d, r9d
0x10047672f  mov     r8d, edi
0x100476732  mov     rdx, r12
0x100476735  lea     rcx, [rbp+138h+var_B8]
0x10047673c  call    ?match_pattern@?$TMatchPattern@DVCDBCSBinaryHelper@@@@SA_NPEBVCCompareString@@PEFBDH1_K1P6ADPEAX@Z3PEFA_J_N@Z; TMatchPattern<char,CDBCSBinaryHelper>::match_pattern(CCompareString const *,char const *,int,char const *,unsigned __int64,char const *,char (*)(void *),void *,__int64 *,bool)
0x100476741  jmp     loc_100476C03
0x100476746  xor     ebx, ebx
0x100476748  mov     [rbp+138h+var_130], rbx
0x10047674c  test    rsi, rsi
0x10047674f  jz      short loc_1004767C4
0x100476751  mov     rdx, gs:58h
0x10047675a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100476761  mov     ecx, [rax]
0x100476763  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10047676a  mov     ebx, [rax]
0x10047676c  add     rbx, [rdx+rcx*8]
0x100476770  mov     rdx, [rbx+100h]
0x100476777  test    rdx, rdx
0x10047677a  jnz     short loc_10047678B
0x10047677c  xor     ecx, ecx
0x10047677e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100476784  mov     rdx, [rbx+100h]
0x10047678b  lea     rcx, [rsi+20h]
0x10047678f  mov     rax, [rcx]
0x100476792  mov     r8b, 1
0x100476795  mov     rdx, [rdx+3E8h]
0x10047679c  call    qword ptr [rax+58h]
0x10047679f  mov     rbx, rax
0x1004767a2  mov     [rbp+138h+var_130], rax
0x1004767a6  mov     rax, [rax]
0x1004767a9  mov     rcx, [r13+1B8h]
0x1004767b0  mov     rdx, [rcx+30h]
0x1004767b4  mov     rcx, rbx
0x1004767b7  call    qword ptr [rax]
0x1004767b9  mov     rax, [rbx]
0x1004767bc  mov     rcx, rbx
0x1004767bf  call    qword ptr [rax+50h]
0x1004767c2  jmp     short loc_1004767CF
0x1004767c4  mov     rcx, [r13+1B8h]
0x1004767cb  mov     rax, [rcx+28h]
0x1004767cf  mov     [rbp+138h+var_120], rax
0x1004767d3  mov     dl, 0E7h; unsigned __int8
0x1004767d5  lea     rcx, [rbp+138h+var_118]; this
0x1004767d9  call    ?Init@CTypeInfo@@AEAAXE@Z; CTypeInfo::Init(uchar)
0x1004767de  movzx   r9d, [rbp+138h+var_118]
0x1004767e3  lea     r10, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1004767ea  movzx   ecx, byte ptr [r9+r10+45AE60h]
0x1004767f3  cmp     byte ptr [rcx+r10+45AFC0h], 0
0x1004767fc  jnz     short loc_10047680E
0x1004767fe  sub     r9b, 23h ; '#'
0x100476802  test    r9b, 0BFh
0x100476806  jz      short loc_10047680E
0x100476808  mov     r9d, [rbp+138h+var_104]
0x10047680c  jmp     short loc_10047682A
0x10047680e  lea     rcx, [rbp+138h+var_118]; this
0x100476812  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x100476817  mov     r9d, [rbp+138h+var_104]
0x10047681b  mov     ecx, 0FFFFFFFFh
0x100476820  test    al, al
0x100476822  cmovnz  r9d, ecx
0x100476826  mov     [rbp+138h+var_104], r9d
0x10047682a  movzx   eax, byte ptr [r14]
0x10047682e  movzx   ecx, byte ptr [rax+r10+45AE60h]
0x100476837  cmp     byte ptr [rcx+r10+45AF60h], 0
0x100476840  jnz     short loc_100476859
0x100476842  movzx   eax, byte ptr [r14+17h]
0x100476847  test    al, al
0x100476849  jz      short loc_100476859
0x10047684b  lea     rcx, [rax+rax*4]
0x10047684f  mov     r10d, ds:rva dword_10085C9D8[r10+rcx*8]; CTypeInfo const CTypeInfo::tiBit ...
0x100476857  jmp     short loc_100476864
0x100476859  mov     r10d, [r14+14h]
0x10047685d  and     r10d, 0FFFFFFh
0x100476864  lea     rcx, [rbp+138h+var_118]; this
0x100476868  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10047686d  test    al, al
0x10047686f  cmovnz  r9d, r10d
0x100476873  mov     [rbp+138h+var_104], r9d
0x100476877  movsxd  rax, edi
0x10047687a  add     rax, rax
0x10047687d  lea     rcx, [rax+0Fh]
0x100476881  cmp     rcx, rax
0x100476884  ja      short loc_100476890
0x100476886  mov     rcx, 0FFFFFFFFFFFFFF0h
0x100476890  and     rcx, 0FFFFFFFFFFFFFFF0h
0x100476894  mov     rax, rcx
0x100476897  call    _alloca_probe
0x10047689c  sub     rsp, rcx
0x10047689f  lea     rax, [rsp+1E8h+var_178]
0x1004768a4  mov     [rbp+138h+var_F8], rax
0x1004768a8  mov     dword ptr [rsp+1E8h+var_1C8], edi; int
0x1004768ac  mov     r9, rax; wchar_t *
0x1004768af  mov     r8d, edi; int
0x1004768b2  mov     rdx, r12; char *
0x1004768b5  mov     ecx, r15d; unsigned int
0x1004768b8  call    ?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x1004768bd  mov     r12d, eax
0x1004768c0  mov     eax, 0FFFFh
0x1004768c5  mov     [rbp+138h+var_138], ax
0x1004768c9  mov     r14, [r13+1C0h]
0x1004768d0  test    r14, r14
0x1004768d3  jz      short loc_100476950
0x1004768d5  test    rsi, rsi
0x1004768d8  jz      short loc_100476950
0x1004768da  lea     rcx, [rsi+20h]
0x1004768de  lea     rdi, [rbp+138h+var_138]
0x1004768e2  mov     r8, [rcx]
0x1004768e5  movzx   edx, byte ptr [r14]
0x1004768e9  call    qword ptr [r8+10h]
0x1004768ed  mov     r10d, eax
0x1004768f0  mov     r8, r14; char *
0x1004768f3  cmp     r15d, 2
0x1004768f7  jb      loc_100476AA1
0x1004768fd  mov     rcx, cs:?m_pSortCache@CSortCacheForSqlCollations@@0PEAV1@EA; CSortCacheForSqlCollations * CSortCacheForSqlCollations::m_pSortCache
0x100476904  xor     edx, edx
0x100476906  add     rcx, 790h
0x10047690d  nop     dword ptr [rax]
0x100476910  mov     r9, [rcx]
0x100476913  test    r9, r9
0x100476916  jz      short loc_100476922
0x100476918  cmp     [r9+10h], r15d
0x10047691c  jz      loc_100476AA1
0x100476922  inc     edx
0x100476924  add     rcx, 8
0x100476928  cmp     edx, 11h
0x10047692b  jl      short loc_100476910
0x10047692d  mov     ecx, r8d
0x100476930  sub     ecx, r14d
0x100476933  mov     eax, 1
0x100476938  sub     eax, ecx
0x10047693a  mov     dword ptr [rsp+1E8h+var_1C0], eax; int
0x10047693e  mov     [rsp+1E8h+var_1C8], rdi; wchar_t *
0x100476943  mov     r9d, r10d; int
0x100476946  xor     edx, edx; unsigned int
0x100476948  mov     ecx, r15d; unsigned int
0x10047694b  call    ?EsMultiByteToWideChar@@YAHIKPEBDHPEA_WH@Z; EsMultiByteToWideChar(uint,ulong,char const *,int,wchar_t *,int)
0x100476950  mov     edx, 2C000000h
0x100476955  mov     eax, 28000000h
0x10047695a  cmp     r15d, 0FDE9h
0x100476961  cmovnz  edx, eax; unsigned int
0x100476964  mov     rax, [r13+1D8h]
0x10047696b  mov     [rsp+1E8h+var_188], rax; struct IGetDynWorkBuffer *
0x100476970  xor     ecx, ecx
0x100476972  mov     [rsp+1E8h+var_190], rcx; int *
0x100476977  lea     rax, [rbp+138h+var_128]
  ... truncated ...
```
