# CTEsConvertToWstr<122,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x10071f100`
- end: `0x10071f62f`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0HK@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1327`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x100700e40`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x10041d440`
- `0x10047a590`
- `0x10071f100`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10071f4cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x10071f4cb`
- `sqldk!SystemThread_TlsIndex` at `0x10071f3bf`
- `sqldk!SystemThread_TlsOffset` at `0x10071f3c8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071f3e3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071f3e3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071f50a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071f50a`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071f1a0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071f1cf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071f1fd`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071f1a0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071f1cf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071f1fd`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071f1ac`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071f1db`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071f209`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071f1ac`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071f1db`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071f209`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071f1bf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071f1ee`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071f21c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071f1bf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071f1ee`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071f21c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071f49e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071f4b5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071f49e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071f4b5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071f4c1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071f4c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<122,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  bool v5; // zf
  unsigned int v6; // r12d
  char v7; // si
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // di
  struct CSessionTraceFlags *v11; // rax
  struct CSessionTraceFlags *v12; // rax
  struct CSessionTraceFlags *v13; // rax
  __int64 v14; // rdx
  unsigned __int8 *v15; // r8
  __int64 v16; // rsi
  int v17; // r12d
  bool v18; // al
  int v19; // ecx
  __int64 v20; // rax
  unsigned __int16 v21; // ax
  const struct CDefaultCollation *v22; // rsi
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
  unsigned int v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 *v38; // [rsp+68h] [rbp-98h] BYREF
  __m256i v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v43[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v44; // [rsp+B8h] [rbp-48h]
  int v45; // [rsp+BCh] [rbp-44h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  wchar_t *v47; // [rsp+D0h] [rbp-30h]
  _BYTE v48[208]; // [rsp+E0h] [rbp-20h] BYREF

  v46 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v6 = *(unsigned __int8 *)(v4 + 14);
    v37 = v6;
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 32) == 3;
    v6 = -1;
    if ( *(_BYTE *)(a2 + 32) != 3 )
      v6 = *(_DWORD *)(a2 + 40);
    v37 = v6;
    if ( v5 )
    {
      *(_BYTE *)a2 = 3;
      return;
    }
  }
  v7 = *(_BYTE *)(v4 + 16);
  v8 = a1[9];
  v10 = 0;
  if ( v8 )
  {
    v9 = *(_QWORD *)(v8 + 408);
    if ( v9 )
    {
      if ( *(_QWORD *)(v9 + 424) )
        v10 = 1;
    }
  }
  if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 0x10) != 0
     || (v11 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v11, 0x1CCu))
    && v7 == 1
    && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) != 0
     || (v12 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v12, 0x1CBu)
     || !v10)
    && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) == 0 )
  {
    v13 = PSessTraceFlags();
    if ( v13 )
      CSessionTraceFlags::CheckSessionTraceInternal(v13, 0x1CBu);
  }
  v36 = *(unsigned __int8 *)(v4 + 15);
  v14 = *(unsigned __int16 *)(a1[4] + 18LL);
  v15 = *(unsigned __int8 **)(a1[7] + 8 * v14);
  v38 = v15;
  v16 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v14);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v15;
    *(_QWORD *)(a2 + 16) = v16;
    v17 = 0;
  }
  else
  {
    v39.m256i_i32[0] = 59139;
    memset(&v39.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v43, 0xE7u, v16);
    if ( v43[0] == 98 )
      v44 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v43[0]))
      || ((v43[0] - 35) & 0xBF) == 0 )
    {
      v18 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v43);
      v19 = v45;
      if ( v18 )
        v19 = -1;
      v45 = v19;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v39, v38, v16, (const struct CTypeInfo *)v43, 0);
    v38 = (unsigned __int8 *)*(int *)(a2 + 8);
    v17 = CSsMoney8::ConvertToWstr(&v38, &v39, v6, v36);
    if ( !v17 )
    {
      *(__m256i *)a2 = v39;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v20 = 0;
    v36 = 0;
    if ( !v10 )
    {
LABEL_53:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v20, v48);
      goto LABEL_54;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 **))x_pContextProvider)(
      x_pContextProvider,
      &v38);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 *))(*(_QWORD *)x_pContextProvider
                                                                                               + 8LL))(
      x_pContextProvider,
      v38);
    v21 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v22 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                              x_pIDbTableProvider,
                                              v21);
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
            &v36,
            *(struct IMemObj **)(v26 + 1000),
            v24,
            v22,
            2,
            0,
            0,
            0,
            0,
            0);
    v47 = v27;
    if ( v27 )
    {
      v28 = v36;
      if ( v36 >= 0x64 )
        v28 = 100;
    }
    else
    {
      v28 = 0;
    }
    v36 = v28;
    v29 = 2LL * v28;
    if ( v29 )
    {
      if ( !v27 || v29 > 0xC8 )
      {
        memset_0(v48, 0, 0xC8u);
        if ( v27 )
        {
          if ( v29 <= 0xC8 )
            goto LABEL_52;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_52;
      }
      memmove(v48, v27, 2LL * v28);
    }
LABEL_52:
    operator delete[](v27);
    v20 = v36;
    goto LABEL_53;
  }
LABEL_54:
  if ( v17 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v40);
    v30 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v40);
    v31 = CDbAndSetOpts::LUserOpt1Get(v30, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v41);
    v32 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v41);
    v33 = CDbAndSetOpts::LUserOpt1Get(v32, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v42);
    v34 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v42);
    v35 = CDbAndSetOpts::LUserOpt1Get(v34, 0x1000u);
    ESConvertErrorHandler(
      v17,
      (struct CXVariant *)a2,
      0xE7u,
      0x7Au,
      0,
      v37,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v35 != 0,
      v33 != 0,
      v31 != 0);
  }
}

```

## disassembly

```asm
0x10071f100  push    rbp
0x10071f102  push    rsi
0x10071f103  push    rdi
0x10071f104  push    r12
0x10071f106  push    r13
0x10071f108  push    r14
0x10071f10a  push    r15
0x10071f10c  lea     rbp, [rsp-0C0h]
0x10071f114  sub     rsp, 1C0h
0x10071f11b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x10071f123  mov     [rsp+1F0h+arg_10], rbx
0x10071f12b  mov     rax, cs:__security_cookie
0x10071f132  xor     rax, rsp
0x10071f135  mov     [rbp+0F0h+var_40], rax
0x10071f13c  mov     r15, rdx
0x10071f13f  mov     r13, rcx
0x10071f142  mov     rbx, [rcx+20h]
0x10071f146  cmp     dword ptr [rbx+8], 0
0x10071f14a  jle     short loc_10071F16B
0x10071f14c  cmp     byte ptr [rdx+20h], 3
0x10071f150  mov     r12d, 0FFFFFFFFh
0x10071f156  jz      short loc_10071F15C
0x10071f158  mov     r12d, [rdx+28h]
0x10071f15c  mov     [rsp+1F0h+var_18C], r12d
0x10071f161  jnz     short loc_10071F175
0x10071f163  mov     byte ptr [rdx], 3
0x10071f166  jmp     loc_10071F605
0x10071f16b  movzx   r12d, byte ptr [rbx+0Eh]
0x10071f170  mov     [rsp+1F0h+var_18C], r12d
0x10071f175  movzx   esi, byte ptr [rbx+10h]
0x10071f179  mov     rax, [rcx+48h]
0x10071f17d  test    rax, rax
0x10071f180  jz      short loc_10071F19D
0x10071f182  mov     rax, [rax+198h]
0x10071f189  test    rax, rax
0x10071f18c  jz      short loc_10071F19D
0x10071f18e  cmp     qword ptr [rax+1A8h], 0
0x10071f196  jz      short loc_10071F19D
0x10071f198  mov     dil, 1
0x10071f19b  jmp     short loc_10071F1A0
0x10071f19d  xor     dil, dil
0x10071f1a0  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071f1a6  test    byte ptr [rax+39h], 10h
0x10071f1aa  jnz     short loc_10071F1C9
0x10071f1ac  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071f1b2  test    rax, rax
0x10071f1b5  jz      short loc_10071F222
0x10071f1b7  mov     edx, 1CCh
0x10071f1bc  mov     rcx, rax
0x10071f1bf  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071f1c5  test    eax, eax
0x10071f1c7  jz      short loc_10071F222
0x10071f1c9  cmp     sil, 1
0x10071f1cd  jnz     short loc_10071F222
0x10071f1cf  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071f1d5  test    byte ptr [rax+39h], 8
0x10071f1d9  jnz     short loc_10071F1FD
0x10071f1db  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071f1e1  test    rax, rax
0x10071f1e4  jz      short loc_10071F1F8
0x10071f1e6  mov     edx, 1CBh
0x10071f1eb  mov     rcx, rax
0x10071f1ee  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071f1f4  test    eax, eax
0x10071f1f6  jnz     short loc_10071F1FD
0x10071f1f8  test    dil, dil
0x10071f1fb  jnz     short loc_10071F222
0x10071f1fd  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071f203  test    byte ptr [rax+39h], 8
0x10071f207  jnz     short loc_10071F222
0x10071f209  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071f20f  test    rax, rax
0x10071f212  jz      short loc_10071F222
0x10071f214  mov     edx, 1CBh
0x10071f219  mov     rcx, rax
0x10071f21c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071f222  movzx   eax, byte ptr [rbx+0Fh]
0x10071f226  mov     [rsp+1F0h+var_190], eax
0x10071f22a  mov     rax, [r13+20h]
0x10071f22e  movzx   edx, word ptr [rax+12h]
0x10071f232  mov     rax, [r13+38h]
0x10071f236  mov     r8, [rax+rdx*8]
0x10071f23a  mov     [rsp+1F0h+var_188], r8
0x10071f23f  mov     rax, [r13+10h]
0x10071f243  mov     rcx, [rax+20h]
0x10071f247  movzx   esi, word ptr [rcx+rdx*2]
0x10071f24b  xor     r14d, r14d
0x10071f24e  cmp     [r15], r14b
0x10071f251  jz      short loc_10071F263
0x10071f253  mov     [r15+8], r8
0x10071f257  mov     [r15+10h], rsi
0x10071f25b  mov     r12d, r14d
0x10071f25e  jmp     loc_10071F330
0x10071f263  mov     dword ptr [rsp+1F0h+var_180], 0E703h
0x10071f26b  xorps   xmm0, xmm0
0x10071f26e  movdqu  [rsp+1F0h+var_180+8], xmm0
0x10071f274  mov     [rbp+0F0h+var_168], r14d
0x10071f278  mov     r8d, esi; int
0x10071f27b  mov     dl, 0E7h; unsigned __int8
0x10071f27d  lea     rcx, [rbp+0F0h+var_148]; this
0x10071f281  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10071f286  movzx   edx, [rbp+0F0h+var_148]
0x10071f28a  cmp     dl, 62h ; 'b'
0x10071f28d  jnz     short loc_10071F298
0x10071f28f  mov     eax, 2
0x10071f294  mov     [rbp+0F0h+var_138], ax
0x10071f298  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10071f29f  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x10071f2a7  cmp     [rax+rcx+45AFC0h], r14b
0x10071f2af  jnz     short loc_10071F2B9
0x10071f2b1  sub     dl, 23h ; '#'
0x10071f2b4  test    dl, 0BFh
0x10071f2b7  jnz     short loc_10071F2D2
0x10071f2b9  lea     rcx, [rbp+0F0h+var_148]; this
0x10071f2bd  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10071f2c2  mov     ecx, [rbp+0F0h+var_134]
0x10071f2c5  mov     edx, 0FFFFFFFFh
0x10071f2ca  test    al, al
0x10071f2cc  cmovnz  ecx, edx
0x10071f2cf  mov     [rbp+0F0h+var_134], ecx
0x10071f2d2  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x10071f2d7  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x10071f2db  mov     r8d, esi; unsigned int
0x10071f2de  mov     rdx, [rsp+1F0h+var_188]; unsigned __int8 *
0x10071f2e3  lea     rcx, [rsp+1F0h+var_180]; this
0x10071f2e8  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10071f2ed  movsxd  rax, dword ptr [r15+8]
0x10071f2f1  mov     [rsp+1F0h+var_188], rax
0x10071f2f6  mov     r9d, [rsp+1F0h+var_190]
0x10071f2fb  mov     r8d, r12d
0x10071f2fe  lea     rdx, [rsp+1F0h+var_180]
0x10071f303  lea     rcx, [rsp+1F0h+var_188]
0x10071f308  call    ?ConvertToWstr@CSsMoney8@@QEBAJPEAVCXVariant@@JW4EPadding@@@Z; CSsMoney8::ConvertToWstr(CXVariant *,long,EPadding)
0x10071f30d  mov     r12d, eax
0x10071f310  test    eax, eax
0x10071f312  jnz     short loc_10071F330
0x10071f314  movups  xmm0, [rsp+1F0h+var_180]
0x10071f319  movups  xmmword ptr [r15], xmm0
0x10071f31d  movups  xmm1, xmmword ptr [rbp-80h]
0x10071f321  movups  xmmword ptr [r15+10h], xmm1
0x10071f326  mov     eax, 0FFFEh
0x10071f32b  and     [r15+2], ax
0x10071f330  cmp     byte ptr [rbx+10h], 1
0x10071f334  jnz     loc_10071F510
0x10071f33a  movzx   eax, word ptr [r15+2]
0x10071f33f  shr     ax, 0Ch
0x10071f343  test    al, 1
0x10071f345  jz      loc_10071F510
0x10071f34b  mov     eax, r14d
0x10071f34e  mov     [rsp+1F0h+var_190], eax
0x10071f352  test    dil, dil
0x10071f355  jz      loc_10071F4D5
0x10071f35b  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f362  mov     rax, [rcx]
0x10071f365  lea     rdx, [rsp+1F0h+var_188]
0x10071f36a  call    qword ptr [rax]
0x10071f36c  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f373  mov     rax, [rcx]
0x10071f376  mov     rdx, [rsp+1F0h+var_188]
0x10071f37b  call    qword ptr [rax+8]
0x10071f37e  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x10071f385  mov     rax, [rcx]
0x10071f388  call    qword ptr [rax]
0x10071f38a  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10071f391  mov     r8, [rcx]
0x10071f394  movzx   edx, ax
0x10071f397  call    qword ptr [r8+8]
0x10071f39b  mov     rsi, rax
0x10071f39e  mov     r9, [r13+20h]
0x10071f3a2  movzx   ebx, word ptr [r9+18h]
0x10071f3a7  shl     rbx, 5
0x10071f3ab  mov     rcx, [r13+10h]
0x10071f3af  add     rbx, [rcx+0A8h]
0x10071f3b6  mov     r8, gs:58h
0x10071f3bf  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10071f3c6  mov     edx, [rcx]
0x10071f3c8  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10071f3cf  mov     edi, [rcx]
0x10071f3d1  add     rdi, [r8+rdx*8]
0x10071f3d5  mov     rdx, [rdi+100h]
0x10071f3dc  test    rdx, rdx
0x10071f3df  jnz     short loc_10071F3F4
0x10071f3e1  xor     ecx, ecx
0x10071f3e3  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10071f3e9  mov     rdx, [rdi+100h]
0x10071f3f0  mov     r9, [r13+20h]
0x10071f3f4  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10071f3fb  mov     ecx, [r9+0Ch]
0x10071f3ff  mov     rax, [r13+30h]
0x10071f403  mov     [rsp+1F0h+var_198], r14d; int
0x10071f408  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x10071f40d  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x10071f412  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x10071f417  mov     [rsp+1F0h+Src], r14; Src
0x10071f41c  mov     [rsp+1F0h+var_1C0], 2; int
0x10071f424  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x10071f429  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x10071f42e  mov     r9, rdx; struct IMemObj *
0x10071f431  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x10071f436  mov     rcx, [rax+rcx*8]; this
0x10071f43a  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10071f43f  mov     rdi, rax
0x10071f442  mov     [rbp+0F0h+var_120], rax
0x10071f446  test    rax, rax
0x10071f449  jnz     short loc_10071F450
0x10071f44b  mov     eax, r14d
0x10071f44e  jmp     short loc_10071F45E
0x10071f450  mov     eax, [rsp+1F0h+var_190]
0x10071f454  mov     ecx, 64h ; 'd'
0x10071f459  cmp     eax, ecx
0x10071f45b  cmovnb  eax, ecx
0x10071f45e  mov     [rsp+1F0h+var_190], eax
0x10071f462  mov     ebx, eax
0x10071f464  add     rbx, rbx
0x10071f467  jz      short loc_10071F4C8
0x10071f469  test    rdi, rdi
0x10071f46c  jz      short loc_10071F488
0x10071f46e  cmp     rbx, 0C8h
0x10071f475  ja      short loc_10071F488
0x10071f477  mov     r8, rbx; Size
0x10071f47a  mov     rdx, rdi; Src
0x10071f47d  lea     rcx, [rbp+0F0h+var_110]; void *
0x10071f481  call    memmove
0x10071f486  jmp     short loc_10071F4C8
0x10071f488  xor     edx, edx; Val
0x10071f48a  mov     r8d, 0C8h; Size
0x10071f490  lea     rcx, [rbp+0F0h+var_110]; void *
0x10071f494  call    memset_0
0x10071f499  test    rdi, rdi
0x10071f49c  jnz     short loc_10071F4AC
0x10071f49e  call    cs:__imp__errno
0x10071f4a4  mov     dword ptr [rax], 16h
0x10071f4aa  jmp     short loc_10071F4C1
0x10071f4ac  cmp     rbx, 0C8h
0x10071f4b3  jbe     short loc_10071F4C8
0x10071f4b5  call    cs:__imp__errno
0x10071f4bb  mov     dword ptr [rax], 22h ; '"'
0x10071f4c1  call    cs:__imp__invalid_parameter_noinfo
0x10071f4c7  nop
0x10071f4c8  mov     rcx, rdi
0x10071f4cb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10071f4d1  mov     eax, [rsp+1F0h+var_190]
0x10071f4d5  add     rax, rax
0x10071f4d8  lea     rcx, [rbp+0F0h+var_110]
0x10071f4dc  mov     [rsp+1F0h+var_1A8], rcx
0x10071f4e1  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x10071f4e6  mov     [rsp+1F0h+Src], r14
0x10071f4eb  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x10071f4f0  mov     [rsp+1F0h+var_1C8], r14
0x10071f4f5  mov     [rsp+1F0h+var_1D0], r14
0x10071f4fa  mov     edx, 1Ch
0x10071f4ff  lea     ecx, [rdx-2]
0x10071f502  lea     r9d, [rdx-1Ah]
0x10071f506  lea     r8d, [rdx-0Ch]
0x10071f50a  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10071f510  test    r12d, r12d
0x10071f513  jz      loc_10071F605
0x10071f519  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f520  mov     rax, [rcx]
0x10071f523  lea     rdx, [rbp+0F0h+var_160]
0x10071f527  call    qword ptr [rax]
0x10071f529  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f530  mov     rax, [rcx]
0x10071f533  mov     rdx, [rbp+0F0h+var_160]
0x10071f537  call    qword ptr [rax+8]
0x10071f53a  mov     edx, 800h; unsigned int
0x10071f53f  mov     rcx, rax; this
0x10071f542  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10071f547  mov     ebx, eax
0x10071f549  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f550  mov     r8, [rcx]
0x10071f553  lea     rdx, [rbp+0F0h+var_158]
0x10071f557  call    qword ptr [r8]
0x10071f55a  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f561  mov     r8, [rcx]
0x10071f564  mov     rdx, [rbp+0F0h+var_158]
0x10071f568  call    qword ptr [r8+8]
0x10071f56c  mov     edx, 10000000h; unsigned int
0x10071f571  mov     rcx, rax; this
0x10071f574  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10071f579  mov     edi, eax
0x10071f57b  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f582  mov     r8, [rcx]
0x10071f585  lea     rdx, [rbp+0F0h+var_150]
0x10071f589  call    qword ptr [r8]
0x10071f58c  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071f593  mov     r8, [rcx]
0x10071f596  mov     rdx, [rbp+0F0h+var_150]
0x10071f59a  call    qword ptr [r8+8]
0x10071f59e  mov     esi, r14d
0x10071f5a1  test    ebx, ebx
0x10071f5a3  setnz   sil
0x10071f5a7  mov     ebx, r14d
0x10071f5aa  test    edi, edi
0x10071f5ac  setnz   bl
0x10071f5af  mov     edx, 1000h; unsigned int
0x10071f5b4  mov     rcx, rax; this
0x10071f5b7  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10071f5bc  mov     r9d, r14d
0x10071f5bf  test    eax, eax
  ... truncated ...
```
