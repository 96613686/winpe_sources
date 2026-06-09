# Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(void)

- ea: `0x18001e334`
- end: `0x18001eb5e`
- name: `?Configure@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJXZ`
- size: `2090`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dc54`

## callees

- `0x1800085b8`
- `0x18000abd4`
- `0x18000b92c`
- `0x18000e390`
- `0x1800158c4`
- `0x1800185b0`
- `0x180019098`
- `0x1800196b8`
- `0x18001a228`
- `0x18001b0c0`
- `0x18001ca30`
- `0x18001e0a8`
- `0x18001e334`
- `0x18001ff88`
- `0x1800208ec`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!free` at `0x18001e833`
- `msvcrt!free` at `0x18001e874`
- `msvcrt!free` at `0x18001e9d6`
- `msvcrt!free` at `0x18001ea13`
- `msvcrt!free` at `0x18001e833`
- `msvcrt!free` at `0x18001e874`
- `msvcrt!free` at `0x18001e9d6`
- `msvcrt!free` at `0x18001ea13`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e9e6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e9fa`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e9e6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e9fa`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001ea35`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001ea35`
- `KERNEL32!FreeLibrary` at `0x18001e3dc`
- `KERNEL32!FreeLibrary` at `0x18001e43f`
- `KERNEL32!FreeLibrary` at `0x18001e4d0`
- `KERNEL32!FreeLibrary` at `0x18001e70e`
- `KERNEL32!FreeLibrary` at `0x18001e3dc`
- `KERNEL32!FreeLibrary` at `0x18001e43f`
- `KERNEL32!FreeLibrary` at `0x18001e4d0`
- `KERNEL32!FreeLibrary` at `0x18001e70e`

## string_xrefs

- `0x18001e7dc`: `_NT_SYMBOL_PATH`
- `0x18001e394`: `mscoree.dll`
- `0x18001e3b1`: `CLRCreateInstance`
- `0x18001e79c`: `XPERF_NGenPdbsPath`
- `0x18001eadc`: `XPERF_NGenPdbsCachePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::Configure(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this)
{
  __int64 v2; // rbx
  __int64 (__fastcall *v3)(GUID *, GUID *, __int64 *); // rax
  int v4; // esi
  unsigned __int16 v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rcx
  unsigned __int16 v9; // si
  __int64 v10; // r8
  _QWORD *v11; // rsi
  int v12; // eax
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // ebx
  volatile signed __int32 *v18; // rdx
  _QWORD *v19; // rdx
  unsigned int Error; // ebx
  _QWORD *v21; // rdx
  unsigned __int64 v22; // rax
  _QWORD *v23; // rdx
  _QWORD *v24; // rbx
  int v25; // edx
  int v26; // ecx
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  volatile signed __int32 *v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  HMODULE hLibModule[3]; // [rsp+70h] [rbp-90h] BYREF
  char v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 v39; // [rsp+A0h] [rbp-60h]
  void *v40; // [rsp+A8h] [rbp-58h]
  _QWORD *v41; // [rsp+B0h] [rbp-50h]
  void *v42; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v43; // [rsp+C0h] [rbp-40h]
  int v44; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  __int64 v46; // [rsp+E0h] [rbp-20h]
  __int64 v47; // [rsp+E8h] [rbp-18h]
  HMODULE *v48; // [rsp+F0h] [rbp-10h] BYREF
  void *Block[2]; // [rsp+F8h] [rbp-8h]
  __int64 v50; // [rsp+108h] [rbp+8h]
  int v51; // [rsp+110h] [rbp+10h]
  __int64 v52; // [rsp+118h] [rbp+18h]
  int v53; // [rsp+120h] [rbp+20h]
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  v46 = -2;
  v2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v28 = v2;
  hLibModule[0] = 0;
  hLibModule[1] = (HMODULE)L"mscoree.dll";
  hLibModule[2] = 0;
  v36 = 0;
  v48 = hLibModule;
  Block[0] = "CLRCreateInstance";
  Block[1] = 0;
  LOBYTE(v50) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v48) )
  {
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    goto LABEL_64;
  }
  v33 = 0;
  v3 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(&v48);
  v4 = v3(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v33);
  if ( v4 < 0 )
  {
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
LABEL_10:
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return (unsigned int)v4;
  }
  v31 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 **))(*(_QWORD *)v33 + 40LL))(v33, &v31);
  if ( v4 < 0 )
  {
    if ( v31 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v31 + 16LL))(v31, *(_QWORD *)v31);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    goto LABEL_10;
  }
  v34 = 0;
  v32 = 0;
  v6 = 0;
  while ( (*(int (__fastcall **)(volatile signed __int32 *, __int64, __int64 *, int *))(*(_QWORD *)v31 + 24LL))(
            v31,
            1,
            &v34,
            &v32) >= 0
       && v32 == 1 )
  {
    v7 = v34;
    v34 = 0;
    v47 = v7;
    v8 = 0;
    v30 = 0;
    if ( v7 )
    {
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v7)(v7, &GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891, &v30);
      v8 = v30;
    }
    if ( v8 )
    {
      LODWORD(v27) = 30;
      if ( (*(int (__fastcall **)(__int64, HMODULE **, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, &v48, &v27) >= 0 )
      {
        if ( (unsigned int)v27 < 3
          || (((_WORD)v48 - 86) & 0xFFDF) != 0
          || (v9 = WORD1(v48), (unsigned __int16)(WORD1(v48) - 52) > 5u)
          || WORD2(v48) != 46
          || WORD1(v48) <= v6 )
        {
LABEL_50:
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        else
        {
          v29 = 260;
          if ( (*(int (__fastcall **)(__int64, WCHAR *, int *))(*(_QWORD *)v30 + 32LL))(v30, Buffer, &v29) >= 0 )
          {
            v10 = -1;
            do
              ++v10;
            while ( Buffer[v10] );
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v28, Buffer, v10);
            v6 = v9;
            goto LABEL_50;
          }
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
      else
      {
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
    else if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v31 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  v2 = v28;
  if ( !*(_DWORD *)(v28 - 16) )
  {
LABEL_64:
    if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
    return 2147500037LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 40,
    &v28);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace((char *)this + 40);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 48,
    &v28);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v2 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 - 24) + 8LL))(*(_QWORD *)(v2 - 24));
  v11 = (_QWORD *)((char *)this + 56);
  if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                       (char *)this + 56,
                       L"XPERF_NGenPdbsPath")
    && *(_DWORD *)(*v11 - 16LL) )
  {
LABEL_111:
    v24 = (_QWORD *)((char *)this + 64);
    if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                          (char *)this + 64,
                          L"XPERF_NGenPdbsCachePath")
      || !*(_DWORD *)(*v24 - 16LL) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        (char *)this + 64,
        (char *)this + 56);
    }
    *((_BYTE *)this + 32) = 1;
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0zzzz_EventWriteTransfer(v26, v25, *v11, *v24, *((_QWORD *)this + 5), *((_QWORD *)this + 6));
    return 0;
  }
  v27 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                        &v27,
                        L"_NT_SYMBOL_PATH") )
  {
LABEL_99:
    if ( !*(_DWORD *)(*v11 - 16LL) )
    {
      if ( !GetSystemWindowsDirectoryW(Buffer, 0x105u) )
      {
        Error = ATL::AtlHresultFromLastError();
        v21 = (_QWORD *)(v27 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
        return Error;
      }
      v22 = -1;
      do
        ++v22;
      while ( Buffer[v22] );
      if ( v22 < 2 || Buffer[1] != 58 )
        goto LABEL_76;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 56,
        L"%wc:\\Symbols",
        Buffer[0]);
    }
    v23 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 8LL))(*v23);
    goto LABEL_111;
  }
  *(_OWORD *)Block = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 1;
  LODWORD(v48) = 0;
  v12 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(&v48);
  if ( !v12 )
  {
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v37 = 0;
    v45 = 0;
    if ( (unsigned __int8)ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::GrowBuffer(&v42, 256) )
    {
      ATL::CAtlArray<void *,ATL::CElementTraits<void *>>::CallConstructors();
      *(_QWORD *)&v43 = 256;
    }
    v38 = 0;
    v39 = 0;
    v29 = 0;
    v28 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    while ( 1 )
    {
      v16 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
              &v27,
              &v31,
              v15,
              &v29);
      v17 = *(_DWORD *)(*(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
                                     &v28,
                                     v16)
                      - 16LL);
      v18 = v31 - 6;
      if ( _InterlockedDecrement(v31 - 2) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
      if ( !v17 )
        break;
      if ( (unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(&v48, v28, &v37, 0) )
      {
        if ( !v37 )
          ATL::AtlThrowImpl(-2147467259);
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 56, *v41, (__int64)(v41[1] - *v41) >> 1);
        break;
      }
    }
    v19 = (_QWORD *)(v28 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v28 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
    if ( v42 )
      free(v42);
    operator delete[](v41);
    v41 = 0;
    operator delete[](v40);
    v40 = 0;
    if ( Block[0] )
      free(Block[0]);
    goto LABEL_99;
  }
  if ( v12 == 1 )
  {
    if ( Block[0] )
      free(Block[0]);
    v14 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
    return 2147942414LL;
  }
  else
  {
    if ( Block[0] )
      free(Block[0]);
LABEL_76:
    v13 = (_QWORD *)(v27 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v27 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18001e334  push    rbp
0x18001e336  push    rbx
0x18001e337  push    rsi
0x18001e338  push    rdi
0x18001e339  push    r12
0x18001e33b  push    r13
0x18001e33d  push    r14
0x18001e33f  push    r15
0x18001e341  lea     rbp, [rsp-258h]
0x18001e349  sub     rsp, 358h
0x18001e350  mov     [rbp+290h+var_2B0], 0FFFFFFFFFFFFFFFEh
0x18001e358  mov     rax, cs:__security_cookie
0x18001e35f  xor     rax, rsp
0x18001e362  mov     [rbp+290h+var_50], rax
0x18001e369  mov     r13, rcx
0x18001e36c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e373  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e37a  mov     rax, [rax+18h]
0x18001e37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e383  lea     rbx, [rax+18h]
0x18001e387  mov     [rsp+390h+var_358], rbx
0x18001e38c  xor     r12d, r12d
0x18001e38f  mov     [rsp+390h+hLibModule], r12
0x18001e394  lea     rax, aMscoreeDll; "mscoree.dll"
0x18001e39b  mov     [rsp+390h+var_318], rax
0x18001e3a0  mov     [rbp+290h+var_310], r12
0x18001e3a4  mov     [rbp+290h+var_308], r12b
0x18001e3a8  lea     rax, [rsp+390h+hLibModule]
0x18001e3ad  mov     [rbp+290h+var_2A0], rax
0x18001e3b1  lea     rax, aClrcreateinsta; "CLRCreateInstance"
0x18001e3b8  mov     [rbp+290h+Block], rax
0x18001e3bc  mov     [rbp+290h+Block+8], r12
0x18001e3c0  mov     byte ptr [rbp+290h+var_288], r12b
0x18001e3c4  lea     rcx, [rbp+290h+var_2A0]
0x18001e3c8  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001e3cd  test    rax, rax
0x18001e3d0  jnz     short loc_18001E3F2
0x18001e3d2  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x18001e3d7  test    rcx, rcx
0x18001e3da  jz      short loc_18001E3E9
0x18001e3dc  call    cs:__imp_FreeLibrary
0x18001e3e3  nop     dword ptr [rax+rax+00h]
0x18001e3e8  nop
0x18001e3e9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e3ed  jmp     loc_18001E726
0x18001e3f2  mov     [rsp+390h+var_330], r12
0x18001e3f7  lea     rcx, [rbp+290h+var_2A0]
0x18001e3fb  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001e400  lea     r8, [rsp+390h+var_330]
0x18001e405  lea     rdx, IID_ICLRMetaHost
0x18001e40c  lea     rcx, CLSID_CLRMetaHost
0x18001e413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e418  mov     esi, eax
0x18001e41a  test    eax, eax
0x18001e41c  jns     short loc_18001E477
0x18001e41e  mov     rcx, [rsp+390h+var_330]
0x18001e423  test    rcx, rcx
0x18001e426  jz      short loc_18001E435
0x18001e428  mov     rdx, [rcx]
0x18001e42b  mov     rax, [rdx+10h]
0x18001e42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e434  nop
0x18001e435  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x18001e43a  test    rcx, rcx
0x18001e43d  jz      short loc_18001E44C
0x18001e43f  call    cs:__imp_FreeLibrary
0x18001e446  nop     dword ptr [rax+rax+00h]
0x18001e44b  nop
0x18001e44c  lea     rdx, [rbx-18h]
0x18001e450  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e454  mov     eax, edi
0x18001e456  lock xadd [rdx+10h], eax
0x18001e45b  add     eax, edi
0x18001e45d  test    eax, eax
0x18001e45f  jg      short loc_18001E470
0x18001e461  mov     rcx, [rdx]
0x18001e464  mov     rax, [rcx]
0x18001e467  mov     rax, [rax+8]
0x18001e46b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e470  mov     eax, esi
0x18001e472  jmp     loc_18001EB2F
0x18001e477  mov     [rsp+390h+var_340], r12
0x18001e47c  mov     rcx, [rsp+390h+var_330]
0x18001e481  mov     rax, [rcx]
0x18001e484  lea     rdx, [rsp+390h+var_340]
0x18001e489  mov     rax, [rax+28h]
0x18001e48d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e492  mov     esi, eax
0x18001e494  test    eax, eax
0x18001e496  jns     short loc_18001E4E2
0x18001e498  mov     rcx, [rsp+390h+var_340]
0x18001e49d  test    rcx, rcx
0x18001e4a0  jz      short loc_18001E4AF
0x18001e4a2  mov     rdx, [rcx]
0x18001e4a5  mov     rax, [rdx+10h]
0x18001e4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ae  nop
0x18001e4af  mov     rcx, [rsp+390h+var_330]
0x18001e4b4  test    rcx, rcx
0x18001e4b7  jz      short loc_18001E4C6
0x18001e4b9  mov     rax, [rcx]
0x18001e4bc  mov     rax, [rax+10h]
0x18001e4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4c5  nop
0x18001e4c6  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x18001e4cb  test    rcx, rcx
0x18001e4ce  jz      short loc_18001E4DD
0x18001e4d0  call    cs:__imp_FreeLibrary
0x18001e4d7  nop     dword ptr [rax+rax+00h]
0x18001e4dc  nop
0x18001e4dd  jmp     loc_18001E44C
0x18001e4e2  mov     [rsp+390h+var_328], r12
0x18001e4e7  mov     [rsp+390h+var_338], r12d
0x18001e4ec  mov     r14d, r12d
0x18001e4ef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001e4f3  mov     rcx, [rsp+390h+var_340]
0x18001e4f8  mov     rax, [rcx]
0x18001e4fb  lea     r9, [rsp+390h+var_338]
0x18001e500  lea     r8, [rsp+390h+var_328]
0x18001e505  mov     edx, 1
0x18001e50a  mov     rax, [rax+18h]
0x18001e50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e513  test    eax, eax
0x18001e515  js      loc_18001E6BF
0x18001e51b  cmp     [rsp+390h+var_338], 1
0x18001e520  jnz     loc_18001E6BF
0x18001e526  mov     rbx, [rsp+390h+var_328]
0x18001e52b  mov     [rsp+390h+var_328], r12
0x18001e530  mov     [rbp+290h+var_2A8], rbx
0x18001e534  mov     rcx, r12
0x18001e537  mov     [rsp+390h+var_348], rcx
0x18001e53c  test    rbx, rbx
0x18001e53f  jz      short loc_18001E560
0x18001e541  mov     rax, [rbx]
0x18001e544  lea     r8, [rsp+390h+var_348]
0x18001e549  lea     rdx, _GUID_bd39d1d2_ba2f_486a_89b0_b4b0cb466891
0x18001e550  mov     rcx, rbx
0x18001e553  mov     rax, [rax]
0x18001e556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e55b  mov     rcx, [rsp+390h+var_348]
0x18001e560  test    rcx, rcx
0x18001e563  jnz     short loc_18001E57F
0x18001e565  test    rbx, rbx
0x18001e568  jz      short loc_18001E57A
0x18001e56a  mov     rax, [rbx]
0x18001e56d  mov     rcx, rbx
0x18001e570  mov     rax, [rax+10h]
0x18001e574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e579  nop
0x18001e57a  jmp     loc_18001E4F3
0x18001e57f  mov     dword ptr [rsp+390h+var_360], 1Eh
0x18001e587  mov     rax, [rcx]
0x18001e58a  lea     r8, [rsp+390h+var_360]
0x18001e58f  lea     rdx, [rbp+290h+var_2A0]
0x18001e593  mov     rax, [rax+18h]
0x18001e597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e59c  test    eax, eax
0x18001e59e  jns     short loc_18001E5D1
0x18001e5a0  mov     rcx, [rsp+390h+var_348]
0x18001e5a5  test    rcx, rcx
0x18001e5a8  jz      short loc_18001E5B7
0x18001e5aa  mov     rax, [rcx]
0x18001e5ad  mov     rax, [rax+10h]
0x18001e5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5b6  nop
0x18001e5b7  test    rbx, rbx
0x18001e5ba  jz      short loc_18001E5CC
0x18001e5bc  mov     rax, [rbx]
0x18001e5bf  mov     rcx, rbx
0x18001e5c2  mov     rax, [rax+10h]
0x18001e5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5cb  nop
0x18001e5cc  jmp     loc_18001E4F3
0x18001e5d1  cmp     dword ptr [rsp+390h+var_360], 3
0x18001e5d6  jb      loc_18001E68E
0x18001e5dc  movzx   eax, word ptr [rbp+290h+var_2A0]
0x18001e5e0  sub     ax, 56h ; 'V'
0x18001e5e4  mov     ecx, 0FFDFh
0x18001e5e9  test    cx, ax
0x18001e5ec  jnz     loc_18001E68E
0x18001e5f2  movzx   esi, word ptr [rbp+290h+var_2A0+2]
0x18001e5f6  lea     eax, [rsi-34h]
0x18001e5f9  cmp     ax, 5
0x18001e5fd  ja      loc_18001E68E
0x18001e603  cmp     word ptr [rbp+290h+var_2A0+4], 2Eh ; '.'
0x18001e608  jnz     loc_18001E68E
0x18001e60e  cmp     si, r14w
0x18001e612  jbe     short loc_18001E68E
0x18001e614  mov     [rsp+390h+var_350], 104h
0x18001e61c  mov     rcx, [rsp+390h+var_348]
0x18001e621  mov     rax, [rcx]
0x18001e624  lea     r8, [rsp+390h+var_350]
0x18001e629  lea     rdx, [rbp+290h+Buffer]
0x18001e62d  mov     rax, [rax+20h]
0x18001e631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e636  test    eax, eax
0x18001e638  jns     short loc_18001E66B
0x18001e63a  mov     rcx, [rsp+390h+var_348]
0x18001e63f  test    rcx, rcx
0x18001e642  jz      short loc_18001E651
0x18001e644  mov     rax, [rcx]
0x18001e647  mov     rax, [rax+10h]
0x18001e64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e650  nop
0x18001e651  test    rbx, rbx
0x18001e654  jz      short loc_18001E666
0x18001e656  mov     rax, [rbx]
0x18001e659  mov     rcx, rbx
0x18001e65c  mov     rax, [rax+10h]
0x18001e660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e665  nop
0x18001e666  jmp     loc_18001E4F3
0x18001e66b  lea     rax, [rbp+290h+Buffer]
0x18001e66f  mov     r8, rdi
0x18001e672  inc     r8
0x18001e675  cmp     [rax+r8*2], r12w
0x18001e67a  jnz     short loc_18001E672
0x18001e67c  lea     rdx, [rbp+290h+Buffer]
0x18001e680  lea     rcx, [rsp+390h+var_358]
0x18001e685  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e68a  movzx   r14d, si
0x18001e68e  mov     rcx, [rsp+390h+var_348]
0x18001e693  test    rcx, rcx
0x18001e696  jz      short loc_18001E6A5
0x18001e698  mov     rax, [rcx]
0x18001e69b  mov     rax, [rax+10h]
0x18001e69f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6a4  nop
0x18001e6a5  test    rbx, rbx
0x18001e6a8  jz      short loc_18001E6BA
0x18001e6aa  mov     rax, [rbx]
0x18001e6ad  mov     rcx, rbx
0x18001e6b0  mov     rax, [rax+10h]
0x18001e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6b9  nop
0x18001e6ba  jmp     loc_18001E4F3
0x18001e6bf  mov     rcx, [rsp+390h+var_328]
0x18001e6c4  test    rcx, rcx
0x18001e6c7  jz      short loc_18001E6D6
0x18001e6c9  mov     rax, [rcx]
0x18001e6cc  mov     rax, [rax+10h]
0x18001e6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d5  nop
0x18001e6d6  mov     rcx, [rsp+390h+var_340]
0x18001e6db  test    rcx, rcx
0x18001e6de  jz      short loc_18001E6ED
0x18001e6e0  mov     rax, [rcx]
0x18001e6e3  mov     rax, [rax+10h]
0x18001e6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6ec  nop
0x18001e6ed  mov     rcx, [rsp+390h+var_330]
0x18001e6f2  test    rcx, rcx
0x18001e6f5  jz      short loc_18001E704
0x18001e6f7  mov     rax, [rcx]
0x18001e6fa  mov     rax, [rax+10h]
0x18001e6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e703  nop
0x18001e704  mov     rcx, [rsp+390h+hLibModule]; hLibModule
0x18001e709  test    rcx, rcx
0x18001e70c  jz      short loc_18001E71B
0x18001e70e  call    cs:__imp_FreeLibrary
0x18001e715  nop     dword ptr [rax+rax+00h]
0x18001e71a  nop
0x18001e71b  mov     rbx, [rsp+390h+var_358]
0x18001e720  cmp     [rbx-10h], r12d
0x18001e724  jnz     short loc_18001E750
0x18001e726  lea     rdx, [rbx-18h]
0x18001e72a  mov     eax, edi
0x18001e72c  lock xadd [rdx+10h], eax
0x18001e731  add     eax, edi
0x18001e733  test    eax, eax
0x18001e735  jg      short loc_18001E746
0x18001e737  mov     rcx, [rdx]
0x18001e73a  mov     rax, [rcx]
0x18001e73d  mov     rax, [rax+8]
0x18001e741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e746  mov     eax, 80004005h
0x18001e74b  jmp     loc_18001EB2F
0x18001e750  lea     r14, [r13+28h]
0x18001e754  lea     rdx, [rsp+390h+var_358]
0x18001e759  mov     rcx, r14
0x18001e75c  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001e761  mov     rcx, r14
0x18001e764  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18001e769  lea     rdx, [rsp+390h+var_358]
0x18001e76e  lea     rcx, [r13+30h]
0x18001e772  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001e777  nop
0x18001e778  lea     rdx, [rbx-18h]
0x18001e77c  mov     eax, edi
0x18001e77e  lock xadd [rdx+10h], eax
0x18001e783  add     eax, edi
0x18001e785  test    eax, eax
0x18001e787  jg      short loc_18001E798
0x18001e789  mov     rcx, [rdx]
0x18001e78c  mov     rax, [rcx]
0x18001e78f  mov     rax, [rax+8]
0x18001e793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e798  lea     rsi, [r13+38h]
0x18001e79c  lea     rdx, aXperfNgenpdbsp; "XPERF_NGenPdbsPath"
  ... truncated ...
```
