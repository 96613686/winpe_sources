# CTEsConvertToWstr<40,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100719210`
- end: `0x1007197bf`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0CI@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1455`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x100700760`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x100419040`
- `0x10047a590`
- `0x100719210`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100719657`
- `sqldk!??_V@YAXPEAX@Z` at `0x100719657`
- `sqldk!SystemThread_TlsIndex` at `0x10071954b`
- `sqldk!SystemThread_TlsOffset` at `0x100719554`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071956f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071956f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100719696`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100719696`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100719331`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100719360`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071938e`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100719331`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100719360`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071938e`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071933d`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071936c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071939a`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071933d`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071936c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071939a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100719350`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071937f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007193ad`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100719350`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071937f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007193ad`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071962a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100719641`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071962a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100719641`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071964d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071964d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<40,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  __int16 v5; // r12
  bool v6; // zf
  char v7; // si
  __int64 v8; // rax
  __int64 v9; // rcx
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
  int v20; // r9d
  __int64 v21; // rax
  unsigned __int16 v22; // ax
  const struct CDefaultCollation *v23; // rsi
  __int64 v24; // r9
  const struct CTypeInfo *v25; // rbx
  __int64 v26; // rdi
  __int64 v27; // rdx
  wchar_t *v28; // rdi
  unsigned int v29; // eax
  unsigned __int64 v30; // rbx
  CDbAndSetOpts *v31; // rax
  unsigned int v32; // ebx
  CDbAndSetOpts *v33; // rax
  unsigned int v34; // edi
  CDbAndSetOpts *v35; // rax
  unsigned int v36; // eax
  unsigned int v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 *v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  __m256i v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v44[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v45; // [rsp+B8h] [rbp-48h]
  int v46; // [rsp+BCh] [rbp-44h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  wchar_t *v48; // [rsp+D0h] [rbp-30h]
  _BYTE v49[208]; // [rsp+E0h] [rbp-20h] BYREF

  v47 = -2;
  v4 = a1[4];
  v5 = -1;
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v38 = *(unsigned __int8 *)(v4 + 14);
  }
  else
  {
    v6 = *(_BYTE *)(a2 + 32) == 3;
    if ( *(_BYTE *)(a2 + 32) == 3 )
      v38 = -1;
    else
      v38 = *(_DWORD *)(a2 + 40);
    if ( v6 )
    {
      *(_BYTE *)a2 = 3;
      return;
    }
  }
  (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
    x_pContextProvider,
    &v40);
  (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned int *, __int64))(*(_QWORD *)x_pContextProvider + 32LL))(
    x_pContextProvider,
    &v37,
    v40);
  if ( (int)v37 >= 120
    || ((**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
          x_pContextProvider,
          &v41),
        (*(unsigned __int8 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 24LL))(
          x_pContextProvider,
          v41)) )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 **))x_pContextProvider)(
      x_pContextProvider,
      &v39);
    v5 = *(_WORD *)((*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 *))(*(_QWORD *)x_pContextProvider + 8LL))(
                      x_pContextProvider,
                      v39)
                  + 16);
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
  v37 = *(unsigned __int8 *)(v4 + 15);
  v14 = *(unsigned __int16 *)(a1[4] + 18LL);
  v15 = *(unsigned __int8 **)(a1[7] + 8 * v14);
  v39 = v15;
  v16 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v14);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v15;
    *(_QWORD *)(a2 + 16) = v16;
    v17 = 0;
  }
  else
  {
    v42.m256i_i32[0] = 59139;
    memset(&v42.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v44, 0xE7u, v16);
    if ( v44[0] == 98 )
      v45 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v44[0]))
      || ((v44[0] - 35) & 0xBF) == 0 )
    {
      v18 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v44);
      v19 = v46;
      if ( v18 )
        v19 = -1;
      v46 = v19;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v42, v39, v16, (const struct CTypeInfo *)v44, 0);
    v17 = CXVariantPerformConvertToWstr<40,0,0>::Convert((unsigned int)&v42, a2, v37, v20, v38, v5);
    if ( !v17 )
    {
      *(__m256i *)a2 = v42;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v21 = 0;
    v37 = 0;
    if ( !v10 )
    {
LABEL_57:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v21, v49);
      goto LABEL_58;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 **))x_pContextProvider)(
      x_pContextProvider,
      &v39);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 *))(*(_QWORD *)x_pContextProvider
                                                                                               + 8LL))(
      x_pContextProvider,
      v39);
    v22 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v23 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                              x_pIDbTableProvider,
                                              v22);
    v24 = a1[4];
    v25 = (const struct CTypeInfo *)(*(_QWORD *)(a1[2] + 168LL) + 32LL * *(unsigned __int16 *)(v24 + 24));
    v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v27 = *(_QWORD *)(v26 + 256);
    if ( !v27 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v27 = *(_QWORD *)(v26 + 256);
      v24 = a1[4];
    }
    v28 = CXVariant::PwchConvertToStringInternal(
            *(CXVariant **)(a1[6] + 8LL * *(unsigned int *)(v24 + 12)),
            *(struct IMemObj **)(v27 + 1000),
            &v37,
            *(struct IMemObj **)(v27 + 1000),
            v25,
            v23,
            2,
            0,
            0,
            0,
            0,
            0);
    v48 = v28;
    if ( v28 )
    {
      v29 = v37;
      if ( v37 >= 0x64 )
        v29 = 100;
    }
    else
    {
      v29 = 0;
    }
    v37 = v29;
    v30 = 2LL * v29;
    if ( v30 )
    {
      if ( !v28 || v30 > 0xC8 )
      {
        memset_0(v49, 0, 0xC8u);
        if ( v28 )
        {
          if ( v30 <= 0xC8 )
            goto LABEL_56;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_56;
      }
      memmove(v49, v28, 2LL * v29);
    }
LABEL_56:
    operator delete[](v28);
    v21 = v37;
    goto LABEL_57;
  }
LABEL_58:
  if ( v17 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v41);
    v31 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v41);
    v32 = CDbAndSetOpts::LUserOpt1Get(v31, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v40);
    v33 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v40);
    v34 = CDbAndSetOpts::LUserOpt1Get(v33, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v43);
    v35 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v43);
    v36 = CDbAndSetOpts::LUserOpt1Get(v35, 0x1000u);
    ESConvertErrorHandler(
      v17,
      (struct CXVariant *)a2,
      0xE7u,
      0x28u,
      0,
      v38,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v36 != 0,
      v34 != 0,
      v32 != 0);
  }
}

```

## disassembly

```asm
0x100719210  push    rbp
0x100719212  push    rsi
0x100719213  push    rdi
0x100719214  push    r12
0x100719216  push    r13
0x100719218  push    r14
0x10071921a  push    r15
0x10071921c  lea     rbp, [rsp-0C0h]
0x100719224  sub     rsp, 1C0h
0x10071922b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x100719233  mov     [rsp+1F0h+arg_10], rbx
0x10071923b  mov     rax, cs:__security_cookie
0x100719242  xor     rax, rsp
0x100719245  mov     [rbp+0F0h+var_40], rax
0x10071924c  mov     r15, rdx
0x10071924f  mov     r13, rcx
0x100719252  mov     rbx, [rcx+20h]
0x100719256  mov     r12d, 0FFFFFFFFh
0x10071925c  cmp     dword ptr [rbx+8], 0
0x100719260  jle     short loc_100719280
0x100719262  cmp     byte ptr [rdx+20h], 3
0x100719266  jnz     short loc_10071926F
0x100719268  mov     [rsp+1F0h+var_18C], r12d
0x10071926d  jmp     short loc_100719276
0x10071926f  mov     edi, [rdx+28h]
0x100719272  mov     [rsp+1F0h+var_18C], edi
0x100719276  jnz     short loc_100719288
0x100719278  mov     byte ptr [rdx], 3
0x10071927b  jmp     loc_100719795
0x100719280  movzx   eax, byte ptr [rbx+0Eh]
0x100719284  mov     [rsp+1F0h+var_18C], eax
0x100719288  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071928f  mov     rax, [rcx]
0x100719292  lea     rdx, [rsp+1F0h+var_180]
0x100719297  call    qword ptr [rax]
0x100719299  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007192a0  mov     rax, [rcx]
0x1007192a3  mov     r8, [rsp+1F0h+var_180]
0x1007192a8  lea     rdx, [rsp+1F0h+var_190]
0x1007192ad  call    qword ptr [rax+20h]
0x1007192b0  cmp     [rsp+1F0h+var_190], 78h ; 'x'
0x1007192b5  jge     short loc_1007192DE
0x1007192b7  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007192be  mov     rax, [rcx]
0x1007192c1  lea     rdx, [rsp+1F0h+var_178]
0x1007192c6  call    qword ptr [rax]
0x1007192c8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007192cf  mov     rax, [rcx]
0x1007192d2  mov     rdx, [rsp+1F0h+var_178]
0x1007192d7  call    qword ptr [rax+18h]
0x1007192da  test    al, al
0x1007192dc  jz      short loc_100719306
0x1007192de  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007192e5  mov     rax, [rcx]
0x1007192e8  lea     rdx, [rsp+1F0h+var_188]
0x1007192ed  call    qword ptr [rax]
0x1007192ef  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007192f6  mov     rax, [rcx]
0x1007192f9  mov     rdx, [rsp+1F0h+var_188]
0x1007192fe  call    qword ptr [rax+8]
0x100719301  movzx   r12d, word ptr [rax+10h]
0x100719306  movzx   esi, byte ptr [rbx+10h]
0x10071930a  mov     rax, [r13+48h]
0x10071930e  test    rax, rax
0x100719311  jz      short loc_10071932E
0x100719313  mov     rcx, [rax+198h]
0x10071931a  test    rcx, rcx
0x10071931d  jz      short loc_10071932E
0x10071931f  cmp     qword ptr [rcx+1A8h], 0
0x100719327  jz      short loc_10071932E
0x100719329  mov     dil, 1
0x10071932c  jmp     short loc_100719331
0x10071932e  xor     dil, dil
0x100719331  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100719337  test    byte ptr [rax+39h], 10h
0x10071933b  jnz     short loc_10071935A
0x10071933d  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100719343  test    rax, rax
0x100719346  jz      short loc_1007193B3
0x100719348  mov     edx, 1CCh
0x10071934d  mov     rcx, rax
0x100719350  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100719356  test    eax, eax
0x100719358  jz      short loc_1007193B3
0x10071935a  cmp     sil, 1
0x10071935e  jnz     short loc_1007193B3
0x100719360  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100719366  test    byte ptr [rax+39h], 8
0x10071936a  jnz     short loc_10071938E
0x10071936c  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100719372  test    rax, rax
0x100719375  jz      short loc_100719389
0x100719377  mov     edx, 1CBh
0x10071937c  mov     rcx, rax
0x10071937f  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100719385  test    eax, eax
0x100719387  jnz     short loc_10071938E
0x100719389  test    dil, dil
0x10071938c  jnz     short loc_1007193B3
0x10071938e  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100719394  test    byte ptr [rax+39h], 8
0x100719398  jnz     short loc_1007193B3
0x10071939a  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007193a0  test    rax, rax
0x1007193a3  jz      short loc_1007193B3
0x1007193a5  mov     edx, 1CBh
0x1007193aa  mov     rcx, rax
0x1007193ad  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007193b3  movzx   eax, byte ptr [rbx+0Fh]
0x1007193b7  mov     [rsp+1F0h+var_190], eax
0x1007193bb  mov     rax, [r13+20h]
0x1007193bf  movzx   edx, word ptr [rax+12h]
0x1007193c3  mov     rax, [r13+38h]
0x1007193c7  mov     r8, [rax+rdx*8]
0x1007193cb  mov     [rsp+1F0h+var_188], r8
0x1007193d0  mov     rax, [r13+10h]
0x1007193d4  mov     rcx, [rax+20h]
0x1007193d8  movzx   esi, word ptr [rcx+rdx*2]
0x1007193dc  xor     r14d, r14d
0x1007193df  cmp     [r15], r14b
0x1007193e2  jz      short loc_1007193F4
0x1007193e4  mov     [r15+8], r8
0x1007193e8  mov     [r15+10h], rsi
0x1007193ec  mov     r12d, r14d
0x1007193ef  jmp     loc_1007194BC
0x1007193f4  mov     dword ptr [rbp+0F0h+var_170], 0E703h
0x1007193fb  xorps   xmm0, xmm0
0x1007193fe  movdqu  [rbp+0F0h+var_170+8], xmm0
0x100719403  mov     [rbp+0F0h+var_158], r14d
0x100719407  mov     r8d, esi; int
0x10071940a  mov     dl, 0E7h; unsigned __int8
0x10071940c  lea     rcx, [rbp+0F0h+var_148]; this
0x100719410  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x100719415  movzx   edx, [rbp+0F0h+var_148]
0x100719419  cmp     dl, 62h ; 'b'
0x10071941c  jnz     short loc_100719427
0x10071941e  mov     eax, 2
0x100719423  mov     [rbp+0F0h+var_138], ax
0x100719427  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10071942e  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x100719436  cmp     [rax+rcx+45AFC0h], r14b
0x10071943e  jnz     short loc_100719448
0x100719440  sub     dl, 23h ; '#'
0x100719443  test    dl, 0BFh
0x100719446  jnz     short loc_100719461
0x100719448  lea     rcx, [rbp+0F0h+var_148]; this
0x10071944c  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x100719451  mov     ecx, [rbp+0F0h+var_134]
0x100719454  mov     edx, 0FFFFFFFFh
0x100719459  test    al, al
0x10071945b  cmovnz  ecx, edx
0x10071945e  mov     [rbp+0F0h+var_134], ecx
0x100719461  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x100719466  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x10071946a  mov     r8d, esi; unsigned int
0x10071946d  mov     rdx, [rsp+1F0h+var_188]; unsigned __int8 *
0x100719472  lea     rcx, [rbp+0F0h+var_170]; this
0x100719476  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10071947b  mov     word ptr [rsp+1F0h+var_1C8], r12w
0x100719481  mov     eax, [rsp+1F0h+var_18C]
0x100719485  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x100719489  mov     r8d, [rsp+1F0h+var_190]
0x10071948e  mov     rdx, r15
0x100719491  lea     rcx, [rbp+0F0h+var_170]
0x100719495  call    ?Convert@?$CXVariantPerformConvertToWstr@$0CI@$0A@$0A@@@SAJPEAVCXVariant@@0W4EPadding@@IJFW4EErrorHandling@@@Z; CXVariantPerformConvertToWstr<40,0,0>::Convert(CXVariant *,CXVariant *,EPadding,uint,long,short,EErrorHandling)
0x10071949a  mov     r12d, eax
0x10071949d  test    eax, eax
0x10071949f  jnz     short loc_1007194BC
0x1007194a1  movups  xmm0, [rbp+0F0h+var_170]
0x1007194a5  movups  xmmword ptr [r15], xmm0
0x1007194a9  movups  xmm1, xmmword ptr [rbp-70h]
0x1007194ad  movups  xmmword ptr [r15+10h], xmm1
0x1007194b2  mov     eax, 0FFFEh
0x1007194b7  and     [r15+2], ax
0x1007194bc  cmp     byte ptr [rbx+10h], 1
0x1007194c0  jnz     loc_10071969C
0x1007194c6  movzx   eax, word ptr [r15+2]
0x1007194cb  shr     ax, 0Ch
0x1007194cf  test    al, 1
0x1007194d1  jz      loc_10071969C
0x1007194d7  mov     eax, r14d
0x1007194da  mov     [rsp+1F0h+var_190], eax
0x1007194de  test    dil, dil
0x1007194e1  jz      loc_100719661
0x1007194e7  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007194ee  mov     rax, [rcx]
0x1007194f1  lea     rdx, [rsp+1F0h+var_188]
0x1007194f6  call    qword ptr [rax]
0x1007194f8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007194ff  mov     rax, [rcx]
0x100719502  mov     rdx, [rsp+1F0h+var_188]
0x100719507  call    qword ptr [rax+8]
0x10071950a  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100719511  mov     rax, [rcx]
0x100719514  call    qword ptr [rax]
0x100719516  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10071951d  mov     r8, [rcx]
0x100719520  movzx   edx, ax
0x100719523  call    qword ptr [r8+8]
0x100719527  mov     rsi, rax
0x10071952a  mov     r9, [r13+20h]
0x10071952e  movzx   ebx, word ptr [r9+18h]
0x100719533  shl     rbx, 5
0x100719537  mov     rcx, [r13+10h]
0x10071953b  add     rbx, [rcx+0A8h]
0x100719542  mov     r8, gs:58h
0x10071954b  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100719552  mov     edx, [rcx]
0x100719554  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10071955b  mov     edi, [rcx]
0x10071955d  add     rdi, [r8+rdx*8]
0x100719561  mov     rdx, [rdi+100h]
0x100719568  test    rdx, rdx
0x10071956b  jnz     short loc_100719580
0x10071956d  xor     ecx, ecx
0x10071956f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100719575  mov     rdx, [rdi+100h]
0x10071957c  mov     r9, [r13+20h]
0x100719580  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100719587  mov     ecx, [r9+0Ch]
0x10071958b  mov     rax, [r13+30h]
0x10071958f  mov     [rsp+1F0h+var_198], r14d; int
0x100719594  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x100719599  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x10071959e  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x1007195a3  mov     [rsp+1F0h+Src], r14; Src
0x1007195a8  mov     [rsp+1F0h+var_1C0], 2; int
0x1007195b0  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x1007195b5  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x1007195ba  mov     r9, rdx; struct IMemObj *
0x1007195bd  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x1007195c2  mov     rcx, [rax+rcx*8]; this
0x1007195c6  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x1007195cb  mov     rdi, rax
0x1007195ce  mov     [rbp+0F0h+var_120], rax
0x1007195d2  test    rax, rax
0x1007195d5  jnz     short loc_1007195DC
0x1007195d7  mov     eax, r14d
0x1007195da  jmp     short loc_1007195EA
0x1007195dc  mov     eax, [rsp+1F0h+var_190]
0x1007195e0  mov     ecx, 64h ; 'd'
0x1007195e5  cmp     eax, ecx
0x1007195e7  cmovnb  eax, ecx
0x1007195ea  mov     [rsp+1F0h+var_190], eax
0x1007195ee  mov     ebx, eax
0x1007195f0  add     rbx, rbx
0x1007195f3  jz      short loc_100719654
0x1007195f5  test    rdi, rdi
0x1007195f8  jz      short loc_100719614
0x1007195fa  cmp     rbx, 0C8h
0x100719601  ja      short loc_100719614
0x100719603  mov     r8, rbx; Size
0x100719606  mov     rdx, rdi; Src
0x100719609  lea     rcx, [rbp+0F0h+var_110]; void *
0x10071960d  call    memmove
0x100719612  jmp     short loc_100719654
0x100719614  xor     edx, edx; Val
0x100719616  mov     r8d, 0C8h; Size
0x10071961c  lea     rcx, [rbp+0F0h+var_110]; void *
0x100719620  call    memset_0
0x100719625  test    rdi, rdi
0x100719628  jnz     short loc_100719638
0x10071962a  call    cs:__imp__errno
0x100719630  mov     dword ptr [rax], 16h
0x100719636  jmp     short loc_10071964D
0x100719638  cmp     rbx, 0C8h
0x10071963f  jbe     short loc_100719654
0x100719641  call    cs:__imp__errno
0x100719647  mov     dword ptr [rax], 22h ; '"'
0x10071964d  call    cs:__imp__invalid_parameter_noinfo
0x100719653  nop
0x100719654  mov     rcx, rdi
0x100719657  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10071965d  mov     eax, [rsp+1F0h+var_190]
0x100719661  add     rax, rax
0x100719664  lea     rcx, [rbp+0F0h+var_110]
0x100719668  mov     [rsp+1F0h+var_1A8], rcx
0x10071966d  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x100719672  mov     [rsp+1F0h+Src], r14
0x100719677  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x10071967c  mov     [rsp+1F0h+var_1C8], r14
0x100719681  mov     [rsp+1F0h+var_1D0], r14
0x100719686  mov     edx, 1Ch
0x10071968b  lea     ecx, [rdx-2]
0x10071968e  lea     r9d, [rdx-1Ah]
0x100719692  lea     r8d, [rdx-0Ch]
0x100719696  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10071969c  test    r12d, r12d
0x10071969f  jz      loc_100719795
0x1007196a5  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007196ac  mov     rax, [rcx]
0x1007196af  lea     rdx, [rsp+1F0h+var_178]
0x1007196b4  call    qword ptr [rax]
0x1007196b6  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007196bd  mov     rax, [rcx]
0x1007196c0  mov     rdx, [rsp+1F0h+var_178]
0x1007196c5  call    qword ptr [rax+8]
0x1007196c8  mov     edx, 800h; unsigned int
0x1007196cd  mov     rcx, rax; this
0x1007196d0  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
  ... truncated ...
```
