# CTEsConvertToWstr<59,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100709230`
- end: `0x100709775`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DL@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1349`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1006ff600`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x100416790`
- `0x10047a590`
- `0x100709230`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100709614`
- `sqldk!??_V@YAXPEAX@Z` at `0x100709614`
- `sqldk!SystemThread_TlsIndex` at `0x100709504`
- `sqldk!SystemThread_TlsOffset` at `0x10070950d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100709528`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100709528`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100709653`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100709653`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007092c6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007092f5`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100709323`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007092c6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007092f5`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100709323`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007092d2`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100709301`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070932f`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007092d2`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100709301`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070932f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007092e5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100709314`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100709342`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007092e5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100709314`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100709342`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1007095e7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1007095fe`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1007095e7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1007095fe`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070960a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070960a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<59,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  unsigned int v5; // r12d
  char v6; // si
  __int64 v7; // rax
  __int64 v8; // rax
  bool v9; // di
  struct CSessionTraceFlags *v10; // rax
  struct CSessionTraceFlags *v11; // rax
  struct CSessionTraceFlags *v12; // rax
  __int64 v13; // rdx
  unsigned __int8 *v14; // r8
  __int64 v15; // rsi
  int v16; // esi
  bool v17; // al
  int v18; // ecx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rax
  unsigned __int16 v22; // ax
  __int64 v23; // r9
  const struct CTypeInfo *v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rdx
  wchar_t *v27; // rdi
  unsigned int v28; // eax
  unsigned __int64 v29; // rbx
  CDbAndSetOpts *v30; // rax
  unsigned int v31; // ebx
  CDbAndSetOpts *v32; // rax
  unsigned int v33; // edi
  CDbAndSetOpts *v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // [rsp+60h] [rbp-A0h]
  int v37; // [rsp+60h] [rbp-A0h]
  unsigned __int8 *v38; // [rsp+68h] [rbp-98h] BYREF
  __m256i v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  struct CDefaultCollation *v41; // [rsp+98h] [rbp-68h]
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[16]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v46; // [rsp+C8h] [rbp-38h]
  int v47; // [rsp+CCh] [rbp-34h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  wchar_t *v49; // [rsp+E0h] [rbp-20h]
  _BYTE v50[208]; // [rsp+F0h] [rbp-10h] BYREF

  v48 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v5 = *(unsigned __int8 *)(v4 + 14);
  }
  else
  {
    if ( *(_BYTE *)(a2 + 32) == 3 )
    {
      *(_BYTE *)a2 = 3;
      return;
    }
    v5 = *(_DWORD *)(a2 + 40);
  }
  v6 = *(_BYTE *)(v4 + 16);
  v7 = a1[9];
  v9 = 0;
  if ( v7 )
  {
    v8 = *(_QWORD *)(v7 + 408);
    if ( v8 )
    {
      if ( *(_QWORD *)(v8 + 424) )
        v9 = 1;
    }
  }
  if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 0x10) != 0
     || (v10 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v10, 0x1CCu))
    && v6 == 1
    && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) != 0
     || (v11 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v11, 0x1CBu)
     || !v9)
    && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) == 0 )
  {
    v12 = PSessTraceFlags();
    if ( v12 )
      CSessionTraceFlags::CheckSessionTraceInternal(v12, 0x1CBu);
  }
  v36 = *(unsigned __int8 *)(v4 + 15);
  v13 = *(unsigned __int16 *)(a1[4] + 18LL);
  v14 = *(unsigned __int8 **)(a1[7] + 8 * v13);
  v38 = v14;
  v15 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v13);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v14;
    *(_QWORD *)(a2 + 16) = v15;
    v16 = 0;
    v37 = 0;
  }
  else
  {
    v39.m256i_i32[0] = 59139;
    memset(&v39.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v45, 0xE7u, v15);
    if ( v45[0] == 98 )
      v46 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v45[0]))
      || ((v45[0] - 35) & 0xBF) == 0 )
    {
      v17 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v45);
      v18 = v47;
      if ( v17 )
        v18 = -1;
      v47 = v18;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v39, v38, v15, (const struct CTypeInfo *)v45, 0);
    if ( v5 == 126 )
    {
      v20 = 1;
    }
    else
    {
      v20 = v5;
      if ( v5 == 128 )
        v20 = 129;
    }
    v16 = CXVariant::WstrConvertFromR8(&v39, v19, v36, v20);
    v37 = v16;
    if ( !v16 )
    {
      *(__m256i *)a2 = v39;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v21 = 0;
    LODWORD(v38) = 0;
    if ( !v9 )
    {
LABEL_56:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v21, v50);
      goto LABEL_57;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v40);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider
                                                                                     + 8LL))(
      x_pContextProvider,
      v40);
    v22 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v41 = (struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                        x_pIDbTableProvider,
                                        v22);
    v23 = a1[4];
    v24 = (const struct CTypeInfo *)(*(_QWORD *)(a1[2] + 168LL) + 32LL * *(unsigned __int16 *)(v23 + 24));
    v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v26 = *(_QWORD *)(v25 + 256);
    if ( !v26 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v26 = *(_QWORD *)(v25 + 256);
      v23 = a1[4];
    }
    v27 = CXVariant::PwchConvertToStringInternal(
            *(CXVariant **)(a1[6] + 8LL * *(unsigned int *)(v23 + 12)),
            *(struct IMemObj **)(v26 + 1000),
            (unsigned int *)&v38,
            *(struct IMemObj **)(v26 + 1000),
            v24,
            v41,
            2,
            0,
            0,
            0,
            0,
            0);
    v49 = v27;
    if ( v27 )
    {
      v28 = (unsigned int)v38;
      if ( (unsigned int)v38 >= 0x64 )
        v28 = 100;
    }
    else
    {
      v28 = 0;
    }
    LODWORD(v38) = v28;
    v29 = 2LL * v28;
    if ( v29 )
    {
      if ( !v27 || v29 > 0xC8 )
      {
        memset_0(v50, 0, 0xC8u);
        if ( v27 )
        {
          if ( v29 <= 0xC8 )
            goto LABEL_55;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_55;
      }
      memmove(v50, v27, 2LL * v28);
    }
LABEL_55:
    operator delete[](v27);
    v21 = (unsigned int)v38;
    goto LABEL_56;
  }
LABEL_57:
  if ( v16 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v42);
    v30 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v42);
    v31 = CDbAndSetOpts::LUserOpt1Get(v30, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v43);
    v32 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v43);
    v33 = CDbAndSetOpts::LUserOpt1Get(v32, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v44);
    v34 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v44);
    v35 = CDbAndSetOpts::LUserOpt1Get(v34, 0x1000u);
    ESConvertErrorHandler(
      v37,
      (struct CXVariant *)a2,
      0xE7u,
      0x3Bu,
      0,
      v5,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v35 != 0,
      v33 != 0,
      v31 != 0);
  }
}

```

## disassembly

```asm
0x100709230  push    rbp
0x100709232  push    rsi
0x100709233  push    rdi
0x100709234  push    r12
0x100709236  push    r13
0x100709238  push    r14
0x10070923a  push    r15
0x10070923c  lea     rbp, [rsp-0D0h]
0x100709244  sub     rsp, 1D0h
0x10070924b  mov     [rbp+100h+var_128], 0FFFFFFFFFFFFFFFEh
0x100709253  mov     [rsp+200h+arg_10], rbx
0x10070925b  mov     rax, cs:__security_cookie
0x100709262  xor     rax, rsp
0x100709265  mov     [rbp+100h+var_40], rax
0x10070926c  mov     r15, rdx
0x10070926f  mov     r13, rcx
0x100709272  mov     rbx, [rcx+20h]
0x100709276  cmp     dword ptr [rbx+8], 0
0x10070927a  jle     short loc_100709296
0x10070927c  cmp     byte ptr [rdx+20h], 3
0x100709280  mov     r12d, 0FFFFFFFFh
0x100709286  jz      short loc_10070928E
0x100709288  mov     r12d, [rdx+28h]
0x10070928c  jmp     short loc_10070929B
0x10070928e  mov     byte ptr [rdx], 3
0x100709291  jmp     loc_10070974B
0x100709296  movzx   r12d, byte ptr [rbx+0Eh]
0x10070929b  movzx   esi, byte ptr [rbx+10h]
0x10070929f  mov     rax, [rcx+48h]
0x1007092a3  test    rax, rax
0x1007092a6  jz      short loc_1007092C3
0x1007092a8  mov     rax, [rax+198h]
0x1007092af  test    rax, rax
0x1007092b2  jz      short loc_1007092C3
0x1007092b4  cmp     qword ptr [rax+1A8h], 0
0x1007092bc  jz      short loc_1007092C3
0x1007092be  mov     dil, 1
0x1007092c1  jmp     short loc_1007092C6
0x1007092c3  xor     dil, dil
0x1007092c6  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007092cc  test    byte ptr [rax+39h], 10h
0x1007092d0  jnz     short loc_1007092EF
0x1007092d2  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007092d8  test    rax, rax
0x1007092db  jz      short loc_100709348
0x1007092dd  mov     edx, 1CCh
0x1007092e2  mov     rcx, rax
0x1007092e5  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007092eb  test    eax, eax
0x1007092ed  jz      short loc_100709348
0x1007092ef  cmp     sil, 1
0x1007092f3  jnz     short loc_100709348
0x1007092f5  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007092fb  test    byte ptr [rax+39h], 8
0x1007092ff  jnz     short loc_100709323
0x100709301  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100709307  test    rax, rax
0x10070930a  jz      short loc_10070931E
0x10070930c  mov     edx, 1CBh
0x100709311  mov     rcx, rax
0x100709314  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070931a  test    eax, eax
0x10070931c  jnz     short loc_100709323
0x10070931e  test    dil, dil
0x100709321  jnz     short loc_100709348
0x100709323  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100709329  test    byte ptr [rax+39h], 8
0x10070932d  jnz     short loc_100709348
0x10070932f  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100709335  test    rax, rax
0x100709338  jz      short loc_100709348
0x10070933a  mov     edx, 1CBh
0x10070933f  mov     rcx, rax
0x100709342  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100709348  movzx   eax, byte ptr [rbx+0Fh]
0x10070934c  mov     [rsp+200h+var_1A0], eax
0x100709350  mov     rax, [r13+20h]
0x100709354  movzx   edx, word ptr [rax+12h]
0x100709358  mov     rax, [r13+38h]
0x10070935c  mov     r8, [rax+rdx*8]
0x100709360  mov     [rsp+200h+var_198], r8
0x100709365  mov     rax, [r13+10h]
0x100709369  mov     rcx, [rax+20h]
0x10070936d  movzx   esi, word ptr [rcx+rdx*2]
0x100709371  xor     r14d, r14d
0x100709374  cmp     [r15], r14b
0x100709377  jz      short loc_10070938E
0x100709379  mov     [r15+8], r8
0x10070937d  mov     [r15+10h], rsi
0x100709381  mov     esi, r14d
0x100709384  mov     [rsp+200h+var_1A0], r14d
0x100709389  jmp     loc_100709476
0x10070938e  mov     dword ptr [rsp+200h+var_190], 0E703h
0x100709396  xorps   xmm0, xmm0
0x100709399  movdqu  [rsp+200h+var_190+8], xmm0
0x10070939f  mov     [rbp+100h+var_178], r14d
0x1007093a3  mov     r8d, esi; int
0x1007093a6  mov     dl, 0E7h; unsigned __int8
0x1007093a8  lea     rcx, [rbp+100h+var_148]; this
0x1007093ac  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x1007093b1  movzx   edx, [rbp+100h+var_148]
0x1007093b5  cmp     dl, 62h ; 'b'
0x1007093b8  jnz     short loc_1007093C3
0x1007093ba  mov     eax, 2
0x1007093bf  mov     [rbp+100h+var_138], ax
0x1007093c3  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1007093ca  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x1007093d2  cmp     [rax+rcx+45AFC0h], r14b
0x1007093da  jnz     short loc_1007093E4
0x1007093dc  sub     dl, 23h ; '#'
0x1007093df  test    dl, 0BFh
0x1007093e2  jnz     short loc_1007093FD
0x1007093e4  lea     rcx, [rbp+100h+var_148]; this
0x1007093e8  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x1007093ed  mov     ecx, [rbp+100h+var_134]
0x1007093f0  mov     edx, 0FFFFFFFFh
0x1007093f5  test    al, al
0x1007093f7  cmovnz  ecx, edx
0x1007093fa  mov     [rbp+100h+var_134], ecx
0x1007093fd  mov     dword ptr [rsp+200h+var_1E0], r14d; int
0x100709402  lea     r9, [rbp+100h+var_148]; struct CTypeInfo *
0x100709406  mov     r8d, esi; unsigned int
0x100709409  mov     rdx, [rsp+200h+var_198]; unsigned __int8 *
0x10070940e  lea     rcx, [rsp+200h+var_190]; this
0x100709413  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x100709418  cmp     r12d, 7Eh ; '~'
0x10070941c  jnz     short loc_100709425
0x10070941e  lea     r9d, [r12-7Dh]
0x100709423  jmp     short loc_100709438
0x100709425  mov     r9d, r12d
0x100709428  mov     eax, 81h
0x10070942d  cmp     r12d, 80h
0x100709434  cmovz   r9d, eax
0x100709438  movss   xmm1, dword ptr [r15+8]
0x10070943e  cvtps2pd xmm1, xmm1
0x100709441  mov     r8d, [rsp+200h+var_1A0]
0x100709446  lea     rcx, [rsp+200h+var_190]
0x10070944b  call    ?WstrConvertFromR8@CXVariant@@QEAAJNW4EPadding@@J@Z; CXVariant::WstrConvertFromR8(double,EPadding,long)
0x100709450  mov     esi, eax
0x100709452  mov     [rsp+200h+var_1A0], eax
0x100709456  test    eax, eax
0x100709458  jnz     short loc_100709476
0x10070945a  movups  xmm0, [rsp+200h+var_190]
0x10070945f  movups  xmmword ptr [r15], xmm0
0x100709463  movups  xmm1, xmmword ptr [rbp-80h]
0x100709467  movups  xmmword ptr [r15+10h], xmm1
0x10070946c  mov     eax, 0FFFEh
0x100709471  and     [r15+2], ax
0x100709476  cmp     byte ptr [rbx+10h], 1
0x10070947a  jnz     loc_100709659
0x100709480  movzx   eax, word ptr [r15+2]
0x100709485  shr     ax, 0Ch
0x100709489  test    al, 1
0x10070948b  jz      loc_100709659
0x100709491  mov     eax, r14d
0x100709494  mov     dword ptr [rsp+200h+var_198], eax
0x100709498  test    dil, dil
0x10070949b  jz      loc_10070961E
0x1007094a1  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007094a8  mov     rax, [rcx]
0x1007094ab  lea     rdx, [rbp+100h+var_170]
0x1007094af  call    qword ptr [rax]
0x1007094b1  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007094b8  mov     rax, [rcx]
0x1007094bb  mov     rdx, [rbp+100h+var_170]
0x1007094bf  call    qword ptr [rax+8]
0x1007094c2  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x1007094c9  mov     rax, [rcx]
0x1007094cc  call    qword ptr [rax]
0x1007094ce  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x1007094d5  mov     r8, [rcx]
0x1007094d8  movzx   edx, ax
0x1007094db  call    qword ptr [r8+8]
0x1007094df  mov     [rbp+100h+var_168], rax
0x1007094e3  mov     r9, [r13+20h]
0x1007094e7  movzx   ebx, word ptr [r9+18h]
0x1007094ec  shl     rbx, 5
0x1007094f0  mov     rcx, [r13+10h]
0x1007094f4  add     rbx, [rcx+0A8h]
0x1007094fb  mov     r8, gs:58h
0x100709504  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10070950b  mov     edx, [rcx]
0x10070950d  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100709514  mov     edi, [rcx]
0x100709516  add     rdi, [r8+rdx*8]
0x10070951a  mov     rdx, [rdi+100h]
0x100709521  test    rdx, rdx
0x100709524  jnz     short loc_100709539
0x100709526  xor     ecx, ecx
0x100709528  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10070952e  mov     rdx, [rdi+100h]
0x100709535  mov     r9, [r13+20h]
0x100709539  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100709540  mov     ecx, [r9+0Ch]
0x100709544  mov     rax, [r13+30h]
0x100709548  mov     [rsp+200h+var_1A8], r14d; int
0x10070954d  mov     [rsp+200h+var_1B0], r14d; unsigned int
0x100709552  mov     [rsp+200h+var_1B8], r14; wchar_t *
0x100709557  mov     [rsp+200h+var_1C0], r14d; unsigned int
0x10070955c  mov     [rsp+200h+Src], r14; Src
0x100709561  mov     [rsp+200h+var_1D0], 2; int
0x100709569  mov     r8, [rbp+100h+var_168]
0x10070956d  mov     [rsp+200h+var_1D8], r8; struct CDefaultCollation *
0x100709572  mov     [rsp+200h+var_1E0], rbx; struct CTypeInfo *
0x100709577  mov     r9, rdx; struct IMemObj *
0x10070957a  lea     r8, [rsp+200h+var_198]; unsigned int *
0x10070957f  mov     rcx, [rax+rcx*8]; this
0x100709583  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x100709588  mov     rdi, rax
0x10070958b  mov     [rbp+100h+var_120], rax
0x10070958f  test    rax, rax
0x100709592  jnz     short loc_100709599
0x100709594  mov     eax, r14d
0x100709597  jmp     short loc_1007095A7
0x100709599  mov     eax, dword ptr [rsp+200h+var_198]
0x10070959d  mov     ecx, 64h ; 'd'
0x1007095a2  cmp     eax, ecx
0x1007095a4  cmovnb  eax, ecx
0x1007095a7  mov     dword ptr [rsp+200h+var_198], eax
0x1007095ab  mov     ebx, eax
0x1007095ad  add     rbx, rbx
0x1007095b0  jz      short loc_100709611
0x1007095b2  test    rdi, rdi
0x1007095b5  jz      short loc_1007095D1
0x1007095b7  cmp     rbx, 0C8h
0x1007095be  ja      short loc_1007095D1
0x1007095c0  mov     r8, rbx; Size
0x1007095c3  mov     rdx, rdi; Src
0x1007095c6  lea     rcx, [rbp+100h+var_110]; void *
0x1007095ca  call    memmove
0x1007095cf  jmp     short loc_100709611
0x1007095d1  xor     edx, edx; Val
0x1007095d3  mov     r8d, 0C8h; Size
0x1007095d9  lea     rcx, [rbp+100h+var_110]; void *
0x1007095dd  call    memset_0
0x1007095e2  test    rdi, rdi
0x1007095e5  jnz     short loc_1007095F5
0x1007095e7  call    cs:__imp__errno
0x1007095ed  mov     dword ptr [rax], 16h
0x1007095f3  jmp     short loc_10070960A
0x1007095f5  cmp     rbx, 0C8h
0x1007095fc  jbe     short loc_100709611
0x1007095fe  call    cs:__imp__errno
0x100709604  mov     dword ptr [rax], 22h ; '"'
0x10070960a  call    cs:__imp__invalid_parameter_noinfo
0x100709610  nop
0x100709611  mov     rcx, rdi
0x100709614  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10070961a  mov     eax, dword ptr [rsp+200h+var_198]
0x10070961e  add     rax, rax
0x100709621  lea     rcx, [rbp+100h+var_110]
0x100709625  mov     [rsp+200h+var_1B8], rcx
0x10070962a  mov     qword ptr [rsp+200h+var_1C0], rax
0x10070962f  mov     [rsp+200h+Src], r14
0x100709634  mov     qword ptr [rsp+200h+var_1D0], r14
0x100709639  mov     [rsp+200h+var_1D8], r14
0x10070963e  mov     [rsp+200h+var_1E0], r14
0x100709643  mov     edx, 1Ch
0x100709648  lea     ecx, [rdx-2]
0x10070964b  lea     r9d, [rdx-1Ah]
0x10070964f  lea     r8d, [rdx-0Ch]
0x100709653  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100709659  test    esi, esi
0x10070965b  jz      loc_10070974B
0x100709661  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100709668  mov     rax, [rcx]
0x10070966b  lea     rdx, [rbp+100h+var_160]
0x10070966f  call    qword ptr [rax]
0x100709671  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100709678  mov     rax, [rcx]
0x10070967b  mov     rdx, [rbp+100h+var_160]
0x10070967f  call    qword ptr [rax+8]
0x100709682  mov     edx, 800h; unsigned int
0x100709687  mov     rcx, rax; this
0x10070968a  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10070968f  mov     ebx, eax
0x100709691  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100709698  mov     r8, [rcx]
0x10070969b  lea     rdx, [rbp+100h+var_158]
0x10070969f  call    qword ptr [r8]
0x1007096a2  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007096a9  mov     r8, [rcx]
0x1007096ac  mov     rdx, [rbp+100h+var_158]
0x1007096b0  call    qword ptr [r8+8]
0x1007096b4  mov     edx, 10000000h; unsigned int
0x1007096b9  mov     rcx, rax; this
0x1007096bc  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x1007096c1  mov     edi, eax
0x1007096c3  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007096ca  mov     r8, [rcx]
0x1007096cd  lea     rdx, [rbp+100h+var_150]
0x1007096d1  call    qword ptr [r8]
0x1007096d4  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007096db  mov     r8, [rcx]
0x1007096de  mov     rdx, [rbp+100h+var_150]
0x1007096e2  call    qword ptr [r8+8]
0x1007096e6  mov     esi, r14d
0x1007096e9  test    ebx, ebx
0x1007096eb  setnz   sil
0x1007096ef  mov     ebx, r14d
  ... truncated ...
```
