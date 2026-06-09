# UndockedModuleLoader::Load

- ea: `0x180003128`
- end: `0x18000390b`
- name: `UndockedModuleLoader::Load`
- size: `2019`
- prototype: `__int64 __fastcall(wchar_t *, __int64, char, __int64 *, HMODULE *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003984`

## callees

- `0x1800027e4`
- `0x180002db0`
- `0x180002f78`
- `0x180003128`
- `0x180003914`
- `0x18000458c`
- `0x18000467c`
- `0x18000593c`
- `0x180005a1c`
- `0x180005a3c`
- `0x180005d10`
- `0x180006540`
- `0x180006858`
- `0x1800078ac`
- `0x18000a1e0`
- `0x18000c9d8`
- `0x18000d538`
- `0x18000d6f8`
- `0x18000d7f0`
- `0x18000d910`
- `0x18000ed40`
- `0x18000f1b0`
- `0x180015430`
- `0x1800154b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003784`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003776`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003776`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003831`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000386d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003831`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000386d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000383f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000387b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000383f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000387b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000376e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000384e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000376e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000384e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003755`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003755`

## string_xrefs

- `0x1800038cf`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x1800033b6`: `UUS: Session=%ws, Module=%ws, Version=%ws, Path=%ws`

## pseudocode

```c
__int64 __fastcall UndockedModuleLoader::Load(wchar_t *a1, __int64 a2, char a3, __int64 *a4, HMODULE *a5)
{
  const wchar_t *v6; // r12
  __int64 v7; // rdx
  signed int v8; // esi
  HMODULE v9; // r14
  unsigned int v10; // r13d
  int v11; // eax
  int v12; // edi
  uus::Session *v13; // rax
  __int64 v14; // rax
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  __int64 v16; // rcx
  const wchar_t *v17; // rdx
  __int64 v18; // rax
  void **v19; // rdx
  __int64 FullPath; // rax
  int *v21; // rcx
  __int128 *v22; // rax
  unsigned int v23; // r8d
  __int64 v24; // rcx
  int v25; // eax
  const char *v26; // r9
  int v27; // edx
  const wchar_t *v28; // rcx
  int *v29; // rax
  int v30; // eax
  unsigned int v31; // r8d
  int v32; // eax
  unsigned int v33; // r8d
  int v34; // eax
  unsigned int v35; // r8d
  wil::details::in1diag3 *v36; // rcx
  __int64 v37; // rdx
  int v38; // r13d
  unsigned __int64 v39; // rdx
  const wchar_t *v40; // r8
  int SystemFilePath; // eax
  unsigned int v42; // r8d
  HMODULE Library; // r12
  DWORD LastError; // edi
  signed int v45; // eax
  unsigned int v46; // r8d
  void *v47; // rdi
  HANDLE v48; // rax
  void *v50; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v52; // [rsp+0h] [rbp-398h] BYREF
  int v53[2]; // [rsp+20h] [rbp-378h]
  const wchar_t *v54; // [rsp+28h] [rbp-370h]
  void *v55; // [rsp+30h] [rbp-368h]
  wchar_t *v56; // [rsp+38h] [rbp-360h]
  __int128 *v57; // [rsp+40h] [rbp-358h]
  int *v58; // [rsp+48h] [rbp-350h]
  char v59; // [rsp+50h] [rbp-348h]
  char v60; // [rsp+51h] [rbp-347h]
  int v61; // [rsp+54h] [rbp-344h]
  int v62; // [rsp+58h] [rbp-340h]
  int v63; // [rsp+5Ch] [rbp-33Ch]
  int v64; // [rsp+60h] [rbp-338h]
  int v65; // [rsp+64h] [rbp-334h]
  int v66; // [rsp+68h] [rbp-330h]
  HMODULE v67; // [rsp+70h] [rbp-328h]
  HMODULE *v68; // [rsp+78h] [rbp-320h]
  __int64 v69; // [rsp+80h] [rbp-318h] BYREF
  __int128 v70; // [rsp+88h] [rbp-310h]
  __int128 v71; // [rsp+98h] [rbp-300h]
  __int64 v72; // [rsp+A8h] [rbp-2F0h]
  __int64 v73; // [rsp+B0h] [rbp-2E8h]
  uus::Session *v74; // [rsp+B8h] [rbp-2E0h] BYREF
  wchar_t *v75; // [rsp+C0h] [rbp-2D8h]
  LPVOID lpMem; // [rsp+C8h] [rbp-2D0h] BYREF
  void *Src[2]; // [rsp+D0h] [rbp-2C8h] BYREF
  __int128 v78; // [rsp+E0h] [rbp-2B8h]
  __int128 v79; // [rsp+F0h] [rbp-2A8h]
  int v80[4]; // [rsp+100h] [rbp-298h] BYREF
  __m128i v81; // [rsp+110h] [rbp-288h]
  __int128 v82; // [rsp+120h] [rbp-278h] BYREF
  __m128i si128; // [rsp+130h] [rbp-268h]
  WCHAR LibFileName[264]; // [rsp+140h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  v6 = a1;
  v75 = a1;
  v68 = a5;
  if ( !a1 || !*a1 )
  {
    v7 = 39;
    goto LABEL_80;
  }
  if ( !::Src )
  {
    v7 = 40;
LABEL_80:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)0x80070057LL,
      v53[0]);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    v7 = 41;
    goto LABEL_80;
  }
  *a5 = 0;
  v8 = 0;
  v9 = 0;
  v67 = 0;
  v72 = -1;
  v73 = 0;
  lpMem = 0;
  v10 = 1;
  v59 = a3 & 1;
  v60 = a3 & 1;
  v61 = a3 & 2;
  v65 = v61;
  v11 = a3 & 4;
  v63 = v11;
  v66 = v11;
  v12 = a3 & 8;
  v64 = v12;
  if ( (a3 & 1) == 0 )
    goto LABEL_53;
  try
  {
    v82 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v82) = 0;
    *(_OWORD *)v80 = 0;
    v81 = si128;
    LOWORD(v80[0]) = 0;
    v62 = 0;
    if ( !*a4 )
    {
      v13 = (uus::Session *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v74 = v13;
      v14 = v13 ? uus::Session::Session(v13, v6) : 0LL;
      v15 = (void (__fastcall ***)(_QWORD, __int64))*a4;
      *a4 = v14;
      if ( v15 )
        (**v15)(v15, 1);
    }
    v16 = *(_QWORD *)(*a4 + 8);
    if ( v16 )
      v17 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
    else
      v17 = L"0.0.0.0";
    *(_OWORD *)Src = 0;
    v78 = 0;
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    std::wstring::_Construct<1,wchar_t const *>(Src, v17, v18);
    v19 = Src;
    if ( *((_QWORD *)&v78 + 1) > 7u )
      v19 = (void **)Src[0];
    std::wstring::assign(&v82, v19);
    std::wstring::~wstring(Src);
    FullPath = uus::Session::GetFullPath(*a4, Src);
    std::filesystem::path::operator=(v80, FullPath);
    std::wstring::~wstring(Src);
    v62 = 1;
    v21 = v80;
    if ( v81.m128i_i64[1] > 7uLL )
      v21 = *(int **)v80;
    v22 = &v82;
    if ( si128.m128i_i64[1] > 7uLL )
      v22 = (__int128 *)v82;
    v58 = v21;
    v57 = v22;
    v56 = &::Src;
    v55 = (void *)v6;
    v54 = L"UUS: Session=%ws, Module=%ws, Version=%ws, Path=%ws";
    *(_QWORD *)v53 = 0;
    WUTrace(0, 0, 32, (unsigned int)(v12 != 0) + 4);
    v24 = *(_QWORD *)(*a4 + 8);
    if ( !v24 )
    {
      v9 = 0;
      v67 = 0;
LABEL_30:
      v8 = -2147418113;
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x7A, v23, (const char *)0x8000FFFFLL, v53[0]);
      goto LABEL_86;
    }
    v74 = 0;
    v25 = (*(__int64 (__fastcall **)(__int64, wchar_t *, _QWORD, uus::Session **))(*(_QWORD *)v24 + 48LL))(
            v24,
            &::Src,
            0,
            &v74);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
        (const char *)(unsigned int)v25,
        v53[0]);
    v9 = (HMODULE)v74;
    v67 = (HMODULE)v74;
    if ( !v74 )
      goto LABEL_30;
  }
  catch ( ... )
  {
    v61 = wil::details::in1diag3::Log_CaughtException(retaddr, &v52, v23, v26);
    v62 |= 8u;
    v10 = 1;
    v8 = v61;
    v9 = v67;
    v27 = v62;
    v61 = v65;
    v63 = v66;
    v12 = v64;
    v59 = v60;
    v6 = v75;
    goto LABEL_32;
  }
LABEL_86:
  v27 = 1;
LABEL_32:
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v28 = (const wchar_t *)&v82;
  if ( si128.m128i_i64[1] > 7uLL )
    v28 = (const wchar_t *)v82;
  v29 = v80;
  if ( v81.m128i_i64[1] > 7uLL )
    v29 = *(int **)v80;
  v54 = v28;
  *(_QWORD *)v53 = v29;
  v30 = UndockedComponentInfo::Init(&v69, (unsigned int)v8, v27 | (((v8 >> 31) & 0xEu) + 2), v6);
  if ( v30 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xAA, v31, (const char *)(unsigned int)v30, v53[0]);
  Src[0] = &lpMem;
  Src[1] = 0;
  LOBYTE(v78) = 1;
  v32 = UndockedComponentInfo::ToString((UndockedComponentInfo *)&v69, (wchar_t **)&Src[1]);
  if ( v32 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xAB, v33, (const char *)(unsigned int)v32, v53[0]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(Src);
  if ( v8 >= 0 )
    v10 = (v12 != 0) + 4;
  v55 = lpMem;
  v54 = L"Load undocked module: %ws";
  v53[0] = v8;
  WUTrace(0, 0, 32, v10);
  if ( v8 >= 0 )
    goto LABEL_50;
  Src[1] = 0;
  v78 = 0;
  v79 = 0;
  Src[0] = &UndockedComponentLoadFailedEvent::`vftable';
  v34 = UndockedComponentLoadEvent::Init((UndockedComponentLoadEvent *)Src, (const struct UndockedComponentInfo *)&v69);
  v36 = retaddr;
  if ( v34 >= 0 )
  {
    v34 = UndockedComponentLoadFailedEvent::FireAsimovEvent((UndockedComponentLoadFailedEvent *)Src, 0, 0);
    v36 = retaddr;
    if ( v34 >= 0 )
      goto LABEL_48;
    v37 = 183;
  }
  else
  {
    v37 = 181;
  }
  wil::details::in1diag3::_Log_Hr(v36, (void *)v37, v35, (const char *)(unsigned int)v34, v53[0]);
LABEL_48:
  UndockedComponentInfo::~UndockedComponentInfo((UndockedComponentInfo *)&Src[1]);
  if ( !v63 )
  {
LABEL_50:
    v38 = v61;
    if ( v61 && v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
        (const char *)(unsigned int)v8,
        v53[0]);
    UndockedComponentInfo::~UndockedComponentInfo((UndockedComponentInfo *)&v69);
    std::wstring::~wstring(v80);
    std::wstring::~wstring(&v82);
    v11 = v63;
    goto LABEL_54;
  }
  UndockedComponentInfo::~UndockedComponentInfo((UndockedComponentInfo *)&v69);
  std::wstring::~wstring(v80);
  std::wstring::~wstring(&v82);
  v11 = v63;
LABEL_53:
  v38 = v61;
LABEL_54:
  if ( !v59 )
    goto LABEL_57;
  if ( v8 >= 0 )
  {
LABEL_76:
    *v68 = v9;
    v50 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v50);
    }
    return 0;
  }
  if ( v11 )
  {
LABEL_57:
    memset(LibFileName, 0, 0x208u);
    SystemFilePath = GetSystemFilePath(LibFileName, v39, v40);
    v8 = SystemFilePath;
    if ( SystemFilePath >= 0 )
    {
      Library = LoadLibraryExW(LibFileName, 0, 0x880u);
      if ( v9 )
      {
        LastError = GetLastError();
        FreeLibrary(v9);
        SetLastError(LastError);
      }
      v9 = Library;
      if ( !Library )
      {
        v45 = GetLastError();
        v8 = (unsigned __int16)v45 | 0x80070000;
        if ( v45 <= 0 )
          v8 = v45;
        if ( v8 >= 0 )
          v8 = -2147418113;
        wil::details::in1diag3::Log_Hr(retaddr, (void *)0xDF, v46, (const char *)(unsigned int)v8, v53[0]);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xD4, v42, (const char *)(unsigned int)SystemFilePath, v53[0]);
    }
    v55 = LibFileName;
    v54 = L"Load inbox system module: %ws";
    v53[0] = v8;
    WUTrace(0, 0, 32, ((v8 >> 31) & 0xFFFFFFFD) + 4);
    if ( v38 )
    {
      if ( v8 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x110,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
          (const char *)(unsigned int)v8,
          v53[0]);
      goto LABEL_76;
    }
  }
  if ( v8 >= 0 )
    goto LABEL_76;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x114,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
    (const char *)(unsigned int)v8,
    v53[0]);
  v47 = lpMem;
  if ( lpMem )
  {
    v48 = GetProcessHeap();
    HeapFree(v48, 0, v47);
  }
  if ( v9 )
    FreeLibrary(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003128  push    rbx
0x18000312a  push    rsi
0x18000312b  push    rdi
0x18000312c  push    r12
0x18000312e  push    r13
0x180003130  push    r14
0x180003132  push    r15
0x180003134  sub     rsp, 360h
0x18000313b  mov     rax, cs:__security_cookie
0x180003142  xor     rax, rsp
0x180003145  mov     [rsp+398h+var_48], rax
0x18000314d  mov     r15, r9
0x180003150  mov     edi, r8d
0x180003153  mov     r12, rcx
0x180003156  mov     [rsp+398h+var_2D8], rcx
0x18000315e  mov     rax, [rsp+398h+arg_20]
0x180003166  mov     [rsp+398h+var_320], rax
0x18000316b  xor     ebx, ebx
0x18000316d  test    rcx, rcx
0x180003170  jz      loc_180003886
0x180003176  cmp     [rcx], bx
0x180003179  jz      loc_180003886
0x18000317f  cmp     cs:Src, bx
0x180003186  jnz     short loc_180003190
0x180003188  lea     edx, [rbx+28h]
0x18000318b  jmp     loc_18000388B
0x180003190  test    rax, rax
0x180003193  jnz     short loc_18000319D
0x180003195  lea     edx, [rax+29h]
0x180003198  jmp     loc_18000388B
0x18000319d  mov     [rax], rbx
0x1800031a0  mov     esi, ebx
0x1800031a2  mov     r14, rbx
0x1800031a5  mov     [rsp+398h+var_328], rbx
0x1800031aa  mov     [rsp+398h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x1800031b6  mov     [rsp+398h+var_2E8], rbx
0x1800031be  mov     [rsp+398h+lpMem], rbx
0x1800031c6  mov     al, dil
0x1800031c9  mov     r13d, 1
0x1800031cf  and     al, r13b
0x1800031d2  mov     [rsp+398h+var_348], al
0x1800031d6  mov     [rsp+398h+var_347], al
0x1800031da  mov     eax, edi
0x1800031dc  and     eax, 2
0x1800031df  mov     [rsp+398h+var_344], eax
0x1800031e3  mov     [rsp+398h+var_334], eax
0x1800031e7  mov     eax, edi
0x1800031e9  and     eax, 4
0x1800031ec  mov     [rsp+398h+var_33C], eax
0x1800031f0  mov     [rsp+398h+var_330], eax
0x1800031f4  and     edi, 8
0x1800031f7  mov     [rsp+398h+var_338], edi
0x1800031fb  cmp     [rsp+398h+var_348], bl
0x1800031ff  jz      loc_1800036E5
0x180003205  xorps   xmm0, xmm0
0x180003208  movups  [rsp+398h+var_278], xmm0
0x180003210  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180003218  movdqu  [rsp+398h+var_268], xmm1
0x180003221  mov     word ptr [rsp+398h+var_278], bx
0x180003229  movups  xmmword ptr [rsp+398h+var_298], xmm0
0x180003231  movdqu  [rsp+398h+var_288], xmm1
0x18000323a  mov     word ptr [rsp+398h+var_298], bx
0x180003242  mov     [rsp+398h+var_340], ebx
0x180003246  cmp     [r9], rbx
0x180003249  jnz     short loc_180003291
0x18000324b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003252  lea     ecx, [r13+0Fh]; unsigned __int64
0x180003256  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000325b  mov     [rsp+398h+var_2E0], rax
0x180003263  test    rax, rax
0x180003266  jz      short loc_180003275
0x180003268  mov     rdx, r12; wchar_t *
0x18000326b  mov     rcx, rax; this
0x18000326e  call    ??0Session@uus@@QEAA@PEB_W@Z; uus::Session::Session(wchar_t const *)
0x180003273  jmp     short loc_180003278
0x180003275  mov     rax, rbx
0x180003278  mov     rcx, [r15]
0x18000327b  mov     [r15], rax
0x18000327e  test    rcx, rcx
0x180003281  jz      short loc_180003291
0x180003283  mov     rax, [rcx]
0x180003286  mov     edx, r13d
0x180003289  mov     rax, [rax]
0x18000328c  call    _guard_dispatch_icall
0x180003291  mov     rax, [r15]
0x180003294  mov     rcx, [rax+8]
0x180003298  test    rcx, rcx
0x18000329b  jz      short loc_1800032AE
0x18000329d  mov     rax, [rcx]
0x1800032a0  mov     rax, [rax+20h]
0x1800032a4  call    _guard_dispatch_icall
0x1800032a9  mov     rdx, rax
0x1800032ac  jmp     short loc_1800032B5
0x1800032ae  lea     rdx, a0000; "0.0.0.0"
0x1800032b5  xorps   xmm0, xmm0
0x1800032b8  movups  xmmword ptr [rsp+398h+Src], xmm0
0x1800032c0  xorps   xmm1, xmm1
0x1800032c3  movdqu  [rsp+398h+var_2B8], xmm1
0x1800032cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800032d0  inc     rax
0x1800032d3  cmp     [rdx+rax*2], bx
0x1800032d7  jnz     short loc_1800032D0
0x1800032d9  mov     r8, rax
0x1800032dc  lea     rcx, [rsp+398h+Src]
0x1800032e4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800032e9  nop
0x1800032ea  lea     rdx, [rsp+398h+Src]
0x1800032f2  cmp     qword ptr [rsp+398h+var_2B8+8], 7
0x1800032fb  cmova   rdx, [rsp+398h+Src]; Src
0x180003304  mov     r8, qword ptr [rsp+398h+var_2B8]
0x18000330c  lea     rcx, [rsp+398h+var_278]; void *
0x180003314  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180003319  nop
0x18000331a  lea     rcx, [rsp+398h+Src]
0x180003322  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003327  lea     rdx, [rsp+398h+Src]
0x18000332f  mov     rcx, [r15]
0x180003332  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z; uus::Session::GetFullPath(wchar_t const *)
0x180003337  mov     rdx, rax
0x18000333a  lea     rcx, [rsp+398h+var_298]
0x180003342  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x180003347  lea     rcx, [rsp+398h+Src]
0x18000334f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003354  mov     [rsp+398h+var_340], r13d
0x180003359  mov     eax, edi
0x18000335b  neg     eax
0x18000335d  sbb     r9d, r9d
0x180003360  neg     r9d
0x180003363  add     r9d, 4
0x180003367  lea     rcx, [rsp+398h+var_298]
0x18000336f  cmp     qword ptr [rsp+398h+var_288+8], 7
0x180003378  cmova   rcx, qword ptr [rsp+398h+var_298]
0x180003381  lea     rax, [rsp+398h+var_278]
0x180003389  cmp     qword ptr [rsp+398h+var_268+8], 7
0x180003392  cmova   rax, qword ptr [rsp+398h+var_278]
0x18000339b  mov     [rsp+398h+var_350], rcx
0x1800033a0  mov     [rsp+398h+var_358], rax
0x1800033a5  lea     r14, Src
0x1800033ac  mov     [rsp+398h+var_360], r14
0x1800033b1  mov     [rsp+398h+var_368], r12
0x1800033b6  lea     rax, aUusSessionWsMo; "UUS: Session=%ws, Module=%ws, Version=%"...
0x1800033bd  mov     [rsp+398h+var_370], rax
0x1800033c2  mov     qword ptr [rsp+398h+var_378], rbx; int
0x1800033c7  xor     edx, edx
0x1800033c9  xor     ecx, ecx
0x1800033cb  lea     r8d, [rdx+20h]
0x1800033cf  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800033d4  mov     rax, [r15]
0x1800033d7  mov     rcx, [rax+8]
0x1800033db  test    rcx, rcx
0x1800033de  jnz     short loc_1800033EA
0x1800033e0  mov     r14, rbx
0x1800033e3  mov     [rsp+398h+var_328], rbx
0x1800033e8  jmp     short loc_18000342E
0x1800033ea  mov     [rsp+398h+var_2E0], rbx
0x1800033f2  mov     rax, [rcx]
0x1800033f5  lea     r9, [rsp+398h+var_2E0]
0x1800033fd  xor     r8d, r8d
0x180003400  mov     rdx, r14
0x180003403  mov     rax, [rax+30h]
0x180003407  call    _guard_dispatch_icall
0x18000340c  mov     rcx, [rsp+398h]; this
0x180003414  test    eax, eax
0x180003416  js      loc_1800038CC
0x18000341c  mov     r14, [rsp+398h+var_2E0]
0x180003424  mov     [rsp+398h+var_328], r14
0x180003429  test    r14, r14
0x18000342c  jnz     short loc_18000344E
0x18000342e  mov     r15d, 8000FFFFh
0x180003434  mov     esi, r15d
0x180003437  mov     rcx, [rsp+398h]; this
0x18000343f  mov     r9d, r15d; char *
0x180003442  mov     edx, 7Ah ; 'z'; void *
0x180003447  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000344c  jmp     short loc_180003454
0x18000344e  mov     r15d, 8000FFFFh
0x180003454  mov     edx, r13d
0x180003457  jmp     short loc_180003496
0x180003459  xor     ebx, ebx
0x18000345b  lea     r13d, [rbx+1]
0x18000345f  mov     r15d, 8000FFFFh
0x180003465  mov     esi, [rsp+398h+var_344]
0x180003469  mov     r14, [rsp+398h+var_328]
0x18000346e  mov     edx, [rsp+398h+var_340]
0x180003472  mov     eax, [rsp+398h+var_334]
0x180003476  mov     [rsp+398h+var_344], eax
0x18000347a  mov     eax, [rsp+398h+var_330]
0x18000347e  mov     [rsp+398h+var_33C], eax
0x180003482  mov     edi, [rsp+398h+var_338]
0x180003486  mov     al, [rsp+398h+var_347]
0x18000348a  mov     [rsp+398h+var_348], al
0x18000348e  mov     r12, [rsp+398h+var_2D8]
0x180003496  mov     r8d, esi
0x180003499  sar     r8d, 1Fh
0x18000349d  and     r8d, 0Eh
0x1800034a1  add     r8d, 2
0x1800034a5  or      r8d, edx
0x1800034a8  mov     [rsp+398h+var_318], 0
0x1800034b4  xorps   xmm0, xmm0
0x1800034b7  movdqu  [rsp+398h+var_310], xmm0
0x1800034c0  xorps   xmm1, xmm1
0x1800034c3  movdqu  [rsp+398h+var_300], xmm1
0x1800034cc  lea     rcx, [rsp+398h+var_278]
0x1800034d4  cmp     qword ptr [rsp+398h+var_268+8], 7
0x1800034dd  cmova   rcx, qword ptr [rsp+398h+var_278]
0x1800034e6  lea     rax, [rsp+398h+var_298]
0x1800034ee  cmp     qword ptr [rsp+398h+var_288+8], 7
0x1800034f7  cmova   rax, qword ptr [rsp+398h+var_298]
0x180003500  mov     [rsp+398h+var_370], rcx
0x180003505  mov     qword ptr [rsp+398h+var_378], rax; int
0x18000350a  mov     r9, r12
0x18000350d  mov     edx, esi
0x18000350f  lea     rcx, [rsp+398h+var_318]
0x180003517  call    ?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z; UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)
0x18000351c  mov     rcx, [rsp+398h]; this
0x180003524  test    eax, eax
0x180003526  jns     short loc_180003535
0x180003528  mov     r9d, eax; char *
0x18000352b  mov     edx, 0AAh; void *
0x180003530  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003535  lea     rax, [rsp+398h+lpMem]
0x18000353d  mov     [rsp+398h+Src], rax
0x180003545  mov     [rsp+398h+Src+8], rbx
0x18000354d  mov     byte ptr [rsp+398h+var_2B8], r13b
0x180003555  lea     rdx, [rsp+398h+Src+8]; wchar_t **
0x18000355d  lea     rcx, [rsp+398h+var_318]; this
0x180003565  call    ?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z; UndockedComponentInfo::ToString(wchar_t * *)
0x18000356a  mov     rcx, [rsp+398h]; this
0x180003572  test    eax, eax
0x180003574  jns     short loc_180003583
0x180003576  mov     r9d, eax; char *
0x180003579  mov     edx, 0ABh; void *
0x18000357e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003583  lea     rcx, [rsp+398h+Src]
0x18000358b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x180003590  neg     edi
0x180003592  sbb     eax, eax
0x180003594  neg     eax
0x180003596  add     eax, 4
0x180003599  test    esi, esi
0x18000359b  cmovns  r13d, eax
0x18000359f  mov     rax, [rsp+398h+lpMem]
0x1800035a7  mov     [rsp+398h+var_368], rax
0x1800035ac  lea     rax, aLoadUndockedMo; "Load undocked module: %ws"
0x1800035b3  mov     [rsp+398h+var_370], rax
0x1800035b8  mov     [rsp+398h+var_378], esi; int
0x1800035bc  mov     r9d, r13d
0x1800035bf  xor     edx, edx
0x1800035c1  xor     ecx, ecx
0x1800035c3  lea     r8d, [rdx+20h]
0x1800035c7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800035cc  test    esi, esi
0x1800035ce  jns     loc_18000369C
0x1800035d4  mov     [rsp+398h+Src+8], 0
0x1800035e0  xorps   xmm0, xmm0
0x1800035e3  movdqu  [rsp+398h+var_2B8], xmm0
0x1800035ec  xorps   xmm1, xmm1
0x1800035ef  movdqu  [rsp+398h+var_2A8], xmm1
0x1800035f8  lea     rax, ??_7UndockedComponentLoadFailedEvent@@6B@; const UndockedComponentLoadFailedEvent::`vftable'
0x1800035ff  mov     [rsp+398h+Src], rax
0x180003607  lea     rdx, [rsp+398h+var_318]; struct UndockedComponentInfo *
0x18000360f  lea     rcx, [rsp+398h+Src]; this
0x180003617  call    ?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z; UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)
0x18000361c  mov     rcx, [rsp+398h]
0x180003624  test    eax, eax
0x180003626  jns     short loc_18000362F
0x180003628  mov     edx, 0B5h
0x18000362d  jmp     short loc_180003652
0x18000362f  xor     r8d, r8d; char *
0x180003632  xor     edx, edx; char *
0x180003634  lea     rcx, [rsp+398h+Src]; this
0x18000363c  call    ?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z; UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)
0x180003641  mov     rcx, [rsp+398h]; this
0x180003649  test    eax, eax
0x18000364b  jns     short loc_18000365A
0x18000364d  mov     edx, 0B7h; void *
0x180003652  mov     r9d, eax; char *
0x180003655  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000365a  lea     rcx, [rsp+398h+Src+8]; this
0x180003662  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x180003667  cmp     [rsp+398h+var_33C], ebx
0x18000366b  jz      short loc_18000369C
0x18000366d  lea     rcx, [rsp+398h+var_318]; this
0x180003675  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x18000367a  nop
0x18000367b  lea     rcx, [rsp+398h+var_298]
0x180003683  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003688  nop
0x180003689  lea     rcx, [rsp+398h+var_278]
0x180003691  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180003696  mov     eax, [rsp+398h+var_33C]
0x18000369a  jmp     short loc_1800036EB
0x18000369c  mov     r13d, [rsp+398h+var_344]
0x1800036a1  test    r13d, r13d
0x1800036a4  jz      short loc_1800036B6
0x1800036a6  mov     rcx, [rsp+398h]; this
0x1800036ae  test    esi, esi
0x1800036b0  js      loc_1800038E1
0x1800036b6  lea     rcx, [rsp+398h+var_318]; this
0x1800036be  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
  ... truncated ...
```
