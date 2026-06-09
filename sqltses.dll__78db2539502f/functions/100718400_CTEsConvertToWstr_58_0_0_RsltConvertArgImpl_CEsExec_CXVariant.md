# CTEsConvertToWstr<58,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100718400`
- end: `0x1007189af`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DK@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1455`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x100700680`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x10040c990`
- `0x100410bc0`
- `0x10047a590`
- `0x100718400`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10071884e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10071884e`
- `sqldk!SystemThread_TlsIndex` at `0x10071873e`
- `sqldk!SystemThread_TlsOffset` at `0x100718747`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100718762`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100718762`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071888d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071888d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007184c7`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007184f6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100718524`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007184c7`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007184f6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100718524`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007184d3`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100718502`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100718530`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007184d3`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100718502`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100718530`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007184e6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100718515`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100718543`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007184e6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100718515`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100718543`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100718821`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100718838`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100718821`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100718838`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100718844`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100718844`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<58,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
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
  unsigned __int8 *v14; // rsi
  __int64 v15; // rdi
  int v16; // esi
  bool v17; // al
  int v18; // ecx
  struct CLangInfo near **v19; // r9
  wchar_t *const *v20; // r9
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
  bool v36; // [rsp+60h] [rbp-A0h]
  unsigned int v37[2]; // [rsp+68h] [rbp-98h] BYREF
  int v38[2]; // [rsp+70h] [rbp-90h] BYREF
  __m256i v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  struct CDefaultCollation *v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v45[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v46; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+D4h] [rbp-2Ch]
  __int64 v48; // [rsp+E0h] [rbp-20h]
  wchar_t *v49; // [rsp+E8h] [rbp-18h]
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
  (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, int *))x_pContextProvider)(
    x_pContextProvider,
    v38);
  LOWORD(v37[0]) = *(_WORD *)((*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, _QWORD))(*(_QWORD *)x_pContextProvider + 8LL))(
                                x_pContextProvider,
                                *(_QWORD *)v38)
                            + 16);
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
  v36 = v9;
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
  v38[0] = *(unsigned __int8 *)(v4 + 15);
  v13 = *(unsigned __int16 *)(a1[4] + 18LL);
  v14 = *(unsigned __int8 **)(a1[7] + 8 * v13);
  v15 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v13);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v14;
    *(_QWORD *)(a2 + 16) = v15;
    v16 = 0;
    v38[0] = 0;
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
    CXVariant::CopyFromPbInternal((CXVariant *)&v39, v14, v15, (const struct CTypeInfo *)v45, 0);
    if ( v5 - 130 <= 1 )
    {
      v20 = &rgwszHijriMonth;
    }
    else if ( LOWORD(v37[0]) <= 0x21u && (v19 = &xrg_Languages + 37 * SLOWORD(v37[0])) != 0 )
    {
      v20 = (wchar_t *const *)(v19 + 17);
    }
    else
    {
      v20 = (wchar_t *const *)&rgwszShortmths;
    }
    v37[1] = *(unsigned __int16 *)(a2 + 10);
    v37[0] = 18000 * *(unsigned __int16 *)(a2 + 8);
    v16 = SQLDATE::ConvertToWstr(v37, &v39, v5, v20, v38[0]);
    v38[0] = v16;
    if ( !v16 )
    {
      *(__m256i *)a2 = v39;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v21 = 0;
    v37[0] = 0;
    if ( !v36 )
    {
LABEL_58:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v21, v50);
      goto LABEL_59;
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
            v37,
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
      v28 = v37[0];
      if ( v37[0] >= 0x64 )
        v28 = 100;
    }
    else
    {
      v28 = 0;
    }
    v37[0] = v28;
    v29 = 2LL * v28;
    if ( v29 )
    {
      if ( !v27 || v29 > 0xC8 )
      {
        memset_0(v50, 0, 0xC8u);
        if ( v27 )
        {
          if ( v29 <= 0xC8 )
            goto LABEL_57;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_57;
      }
      memmove(v50, v27, 2LL * v28);
    }
LABEL_57:
    operator delete[](v27);
    v21 = v37[0];
    goto LABEL_58;
  }
LABEL_59:
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
      v38[0],
      (struct CXVariant *)a2,
      0xE7u,
      0x3Au,
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
0x100718400  push    rbp
0x100718402  push    rsi
0x100718403  push    rdi
0x100718404  push    r12
0x100718406  push    r13
0x100718408  push    r14
0x10071840a  push    r15
0x10071840c  lea     rbp, [rsp-0D0h]
0x100718414  sub     rsp, 1D0h
0x10071841b  mov     [rbp+100h+var_120], 0FFFFFFFFFFFFFFFEh
0x100718423  mov     [rsp+200h+arg_10], rbx
0x10071842b  mov     rax, cs:__security_cookie
0x100718432  xor     rax, rsp
0x100718435  mov     [rbp+100h+var_40], rax
0x10071843c  mov     r15, rdx
0x10071843f  mov     r13, rcx
0x100718442  mov     rbx, [rcx+20h]
0x100718446  cmp     dword ptr [rbx+8], 0
0x10071844a  jle     short loc_100718466
0x10071844c  cmp     byte ptr [rdx+20h], 3
0x100718450  mov     r12d, 0FFFFFFFFh
0x100718456  jz      short loc_10071845E
0x100718458  mov     r12d, [rdx+28h]
0x10071845c  jmp     short loc_10071846B
0x10071845e  mov     byte ptr [rdx], 3
0x100718461  jmp     loc_100718985
0x100718466  movzx   r12d, byte ptr [rbx+0Eh]
0x10071846b  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100718472  mov     rax, [rcx]
0x100718475  lea     rdx, [rsp+200h+var_190]
0x10071847a  call    qword ptr [rax]
0x10071847c  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100718483  mov     rax, [rcx]
0x100718486  mov     rdx, qword ptr [rsp+200h+var_190]
0x10071848b  call    qword ptr [rax+8]
0x10071848e  movzx   ecx, word ptr [rax+10h]
0x100718492  mov     word ptr [rsp+200h+var_198], cx
0x100718497  movzx   esi, byte ptr [rbx+10h]
0x10071849b  mov     rax, [r13+48h]
0x10071849f  test    rax, rax
0x1007184a2  jz      short loc_1007184BF
0x1007184a4  mov     rax, [rax+198h]
0x1007184ab  test    rax, rax
0x1007184ae  jz      short loc_1007184BF
0x1007184b0  cmp     qword ptr [rax+1A8h], 0
0x1007184b8  jz      short loc_1007184BF
0x1007184ba  mov     dil, 1
0x1007184bd  jmp     short loc_1007184C2
0x1007184bf  xor     dil, dil
0x1007184c2  mov     [rsp+200h+var_1A0], dil
0x1007184c7  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007184cd  test    byte ptr [rax+39h], 10h
0x1007184d1  jnz     short loc_1007184F0
0x1007184d3  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007184d9  test    rax, rax
0x1007184dc  jz      short loc_100718549
0x1007184de  mov     edx, 1CCh
0x1007184e3  mov     rcx, rax
0x1007184e6  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007184ec  test    eax, eax
0x1007184ee  jz      short loc_100718549
0x1007184f0  cmp     sil, 1
0x1007184f4  jnz     short loc_100718549
0x1007184f6  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007184fc  test    byte ptr [rax+39h], 8
0x100718500  jnz     short loc_100718524
0x100718502  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100718508  test    rax, rax
0x10071850b  jz      short loc_10071851F
0x10071850d  mov     edx, 1CBh
0x100718512  mov     rcx, rax
0x100718515  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071851b  test    eax, eax
0x10071851d  jnz     short loc_100718524
0x10071851f  test    dil, dil
0x100718522  jnz     short loc_100718549
0x100718524  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071852a  test    byte ptr [rax+39h], 8
0x10071852e  jnz     short loc_100718549
0x100718530  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100718536  test    rax, rax
0x100718539  jz      short loc_100718549
0x10071853b  mov     edx, 1CBh
0x100718540  mov     rcx, rax
0x100718543  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100718549  movzx   eax, byte ptr [rbx+0Fh]
0x10071854d  mov     [rsp+200h+var_190], eax
0x100718551  mov     rax, [r13+20h]
0x100718555  movzx   edx, word ptr [rax+12h]
0x100718559  mov     rax, [r13+38h]
0x10071855d  mov     rsi, [rax+rdx*8]
0x100718561  mov     rax, [r13+10h]
0x100718565  mov     rcx, [rax+20h]
0x100718569  movzx   edi, word ptr [rcx+rdx*2]
0x10071856d  xor     r14d, r14d
0x100718570  cmp     [r15], r14b
0x100718573  jz      short loc_10071858A
0x100718575  mov     [r15+8], rsi
0x100718579  mov     [r15+10h], rdi
0x10071857d  mov     esi, r14d
0x100718580  mov     [rsp+200h+var_190], r14d
0x100718585  jmp     loc_1007186AE
0x10071858a  mov     dword ptr [rsp+200h+var_188], 0E703h
0x100718592  xorps   xmm0, xmm0
0x100718595  movdqu  [rbp+100h+var_188+8], xmm0
0x10071859a  mov     [rbp+100h+var_170], r14d
0x10071859e  mov     r8d, edi; int
0x1007185a1  mov     dl, 0E7h; unsigned __int8
0x1007185a3  lea     rcx, [rbp+100h+var_140]; this
0x1007185a7  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x1007185ac  movzx   edx, [rbp+100h+var_140]
0x1007185b0  cmp     dl, 62h ; 'b'
0x1007185b3  jnz     short loc_1007185BE
0x1007185b5  mov     eax, 2
0x1007185ba  mov     [rbp+100h+var_130], ax
0x1007185be  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1007185c5  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x1007185cd  cmp     [rax+rcx+45AFC0h], r14b
0x1007185d5  jnz     short loc_1007185DF
0x1007185d7  sub     dl, 23h ; '#'
0x1007185da  test    dl, 0BFh
0x1007185dd  jnz     short loc_1007185F8
0x1007185df  lea     rcx, [rbp+100h+var_140]; this
0x1007185e3  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x1007185e8  mov     ecx, [rbp+100h+var_12C]
0x1007185eb  mov     edx, 0FFFFFFFFh
0x1007185f0  test    al, al
0x1007185f2  cmovnz  ecx, edx
0x1007185f5  mov     [rbp+100h+var_12C], ecx
0x1007185f8  mov     dword ptr [rsp+200h+var_1E0], r14d; int
0x1007185fd  lea     r9, [rbp+100h+var_140]; struct CTypeInfo *
0x100718601  mov     r8d, edi; unsigned int
0x100718604  mov     rdx, rsi; unsigned __int8 *
0x100718607  lea     rcx, [rsp+200h+var_188]; this
0x10071860c  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x100718611  lea     eax, [r12-82h]
0x100718619  cmp     eax, 1
0x10071861c  jbe     short loc_10071864F
0x10071861e  movsx   rax, word ptr [rsp+200h+var_198]
0x100718624  cmp     ax, 21h ; '!'
0x100718628  ja      short loc_100718646
0x10071862a  imul    r9, rax, 128h
0x100718631  lea     rax, ?xrg_Languages@@3PAUCLangInfo@@A; CLangInfo near * xrg_Languages
0x100718638  add     r9, rax
0x10071863b  jz      short loc_100718646
0x10071863d  add     r9, 88h
0x100718644  jmp     short loc_100718656
0x100718646  lea     r9, ?rgwszShortmths@@3QBQEB_WB; wchar_t const * const near * const rgwszShortmths
0x10071864d  jmp     short loc_100718656
0x10071864f  lea     r9, ?rgwszHijriMonth@@3QBQEB_WB; wchar_t const * const near * const rgwszHijriMonth
0x100718656  movzx   eax, word ptr [r15+0Ah]
0x10071865b  mov     [rsp+200h+var_194], eax
0x10071865f  movzx   eax, word ptr [r15+8]
0x100718664  imul    ecx, eax, 4650h
0x10071866a  mov     [rsp+200h+var_198], ecx
0x10071866e  mov     eax, [rsp+200h+var_190]
0x100718672  mov     dword ptr [rsp+200h+var_1E0], eax
0x100718676  mov     r8d, r12d
0x100718679  lea     rdx, [rsp+200h+var_188]
0x10071867e  lea     rcx, [rsp+200h+var_198]
0x100718683  call    ?ConvertToWstr@SQLDATE@@QEBAJPEAVCXVariant@@JPEBQEB_WW4EPadding@@@Z; SQLDATE::ConvertToWstr(CXVariant *,long,wchar_t const * const *,EPadding)
0x100718688  mov     esi, eax
0x10071868a  mov     [rsp+200h+var_190], eax
0x10071868e  test    eax, eax
0x100718690  jnz     short loc_1007186AE
0x100718692  movups  xmm0, [rsp+200h+var_188]
0x100718697  movups  xmmword ptr [r15], xmm0
0x10071869b  movups  xmm1, xmmword ptr [rbp-78h]
0x10071869f  movups  xmmword ptr [r15+10h], xmm1
0x1007186a4  mov     eax, 0FFFEh
0x1007186a9  and     [r15+2], ax
0x1007186ae  cmp     byte ptr [rbx+10h], 1
0x1007186b2  jnz     loc_100718893
0x1007186b8  movzx   eax, word ptr [r15+2]
0x1007186bd  shr     ax, 0Ch
0x1007186c1  test    al, 1
0x1007186c3  jz      loc_100718893
0x1007186c9  mov     eax, r14d
0x1007186cc  mov     [rsp+200h+var_198], eax
0x1007186d0  cmp     [rsp+200h+var_1A0], 0
0x1007186d5  jz      loc_100718858
0x1007186db  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007186e2  mov     rax, [rcx]
0x1007186e5  lea     rdx, [rbp+100h+var_168]
0x1007186e9  call    qword ptr [rax]
0x1007186eb  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007186f2  mov     rax, [rcx]
0x1007186f5  mov     rdx, [rbp+100h+var_168]
0x1007186f9  call    qword ptr [rax+8]
0x1007186fc  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100718703  mov     rax, [rcx]
0x100718706  call    qword ptr [rax]
0x100718708  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10071870f  mov     r8, [rcx]
0x100718712  movzx   edx, ax
0x100718715  call    qword ptr [r8+8]
0x100718719  mov     [rbp+100h+var_160], rax
0x10071871d  mov     r9, [r13+20h]
0x100718721  movzx   ebx, word ptr [r9+18h]
0x100718726  shl     rbx, 5
0x10071872a  mov     rcx, [r13+10h]
0x10071872e  add     rbx, [rcx+0A8h]
0x100718735  mov     r8, gs:58h
0x10071873e  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100718745  mov     edx, [rcx]
0x100718747  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10071874e  mov     edi, [rcx]
0x100718750  add     rdi, [r8+rdx*8]
0x100718754  mov     rdx, [rdi+100h]
0x10071875b  test    rdx, rdx
0x10071875e  jnz     short loc_100718773
0x100718760  xor     ecx, ecx
0x100718762  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100718768  mov     rdx, [rdi+100h]
0x10071876f  mov     r9, [r13+20h]
0x100718773  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10071877a  mov     ecx, [r9+0Ch]
0x10071877e  mov     rax, [r13+30h]
0x100718782  mov     [rsp+200h+var_1A8], r14d; int
0x100718787  mov     [rsp+200h+var_1B0], r14d; unsigned int
0x10071878c  mov     [rsp+200h+var_1B8], r14; wchar_t *
0x100718791  mov     [rsp+200h+var_1C0], r14d; unsigned int
0x100718796  mov     [rsp+200h+Src], r14; Src
0x10071879b  mov     [rsp+200h+var_1D0], 2; int
0x1007187a3  mov     r8, [rbp+100h+var_160]
0x1007187a7  mov     [rsp+200h+var_1D8], r8; struct CDefaultCollation *
0x1007187ac  mov     [rsp+200h+var_1E0], rbx; struct CTypeInfo *
0x1007187b1  mov     r9, rdx; struct IMemObj *
0x1007187b4  lea     r8, [rsp+200h+var_198]; unsigned int *
0x1007187b9  mov     rcx, [rax+rcx*8]; this
0x1007187bd  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x1007187c2  mov     rdi, rax
0x1007187c5  mov     [rbp+100h+var_118], rax
0x1007187c9  test    rax, rax
0x1007187cc  jnz     short loc_1007187D3
0x1007187ce  mov     eax, r14d
0x1007187d1  jmp     short loc_1007187E1
0x1007187d3  mov     eax, [rsp+200h+var_198]
0x1007187d7  mov     ecx, 64h ; 'd'
0x1007187dc  cmp     eax, ecx
0x1007187de  cmovnb  eax, ecx
0x1007187e1  mov     [rsp+200h+var_198], eax
0x1007187e5  mov     ebx, eax
0x1007187e7  add     rbx, rbx
0x1007187ea  jz      short loc_10071884B
0x1007187ec  test    rdi, rdi
0x1007187ef  jz      short loc_10071880B
0x1007187f1  cmp     rbx, 0C8h
0x1007187f8  ja      short loc_10071880B
0x1007187fa  mov     r8, rbx; Size
0x1007187fd  mov     rdx, rdi; Src
0x100718800  lea     rcx, [rbp+100h+var_110]; void *
0x100718804  call    memmove
0x100718809  jmp     short loc_10071884B
0x10071880b  xor     edx, edx; Val
0x10071880d  mov     r8d, 0C8h; Size
0x100718813  lea     rcx, [rbp+100h+var_110]; void *
0x100718817  call    memset_0
0x10071881c  test    rdi, rdi
0x10071881f  jnz     short loc_10071882F
0x100718821  call    cs:__imp__errno
0x100718827  mov     dword ptr [rax], 16h
0x10071882d  jmp     short loc_100718844
0x10071882f  cmp     rbx, 0C8h
0x100718836  jbe     short loc_10071884B
0x100718838  call    cs:__imp__errno
0x10071883e  mov     dword ptr [rax], 22h ; '"'
0x100718844  call    cs:__imp__invalid_parameter_noinfo
0x10071884a  nop
0x10071884b  mov     rcx, rdi
0x10071884e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100718854  mov     eax, [rsp+200h+var_198]
0x100718858  add     rax, rax
0x10071885b  lea     rcx, [rbp+100h+var_110]
0x10071885f  mov     [rsp+200h+var_1B8], rcx
0x100718864  mov     qword ptr [rsp+200h+var_1C0], rax
0x100718869  mov     [rsp+200h+Src], r14
0x10071886e  mov     qword ptr [rsp+200h+var_1D0], r14
0x100718873  mov     [rsp+200h+var_1D8], r14
0x100718878  mov     [rsp+200h+var_1E0], r14
0x10071887d  mov     edx, 1Ch
0x100718882  lea     ecx, [rdx-2]
0x100718885  lea     r9d, [rdx-1Ah]
0x100718889  lea     r8d, [rdx-0Ch]
0x10071888d  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100718893  test    esi, esi
0x100718895  jz      loc_100718985
0x10071889b  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007188a2  mov     rax, [rcx]
0x1007188a5  lea     rdx, [rbp+100h+var_158]
0x1007188a9  call    qword ptr [rax]
0x1007188ab  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007188b2  mov     rax, [rcx]
0x1007188b5  mov     rdx, [rbp+100h+var_158]
0x1007188b9  call    qword ptr [rax+8]
0x1007188bc  mov     edx, 800h; unsigned int
0x1007188c1  mov     rcx, rax; this
0x1007188c4  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x1007188c9  mov     ebx, eax
0x1007188cb  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
  ... truncated ...
```
