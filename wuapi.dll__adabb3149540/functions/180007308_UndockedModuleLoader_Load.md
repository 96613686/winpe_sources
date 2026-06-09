# UndockedModuleLoader::Load

- ea: `0x180007308`
- end: `0x180007aeb`
- name: `UndockedModuleLoader::Load`
- size: `2019`
- prototype: `__int64 __fastcall(wchar_t *, __int64, char, __int64 *, HMODULE *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007b64`

## callees

- `0x180003760`
- `0x1800069a4`
- `0x180006f90`
- `0x180007158`
- `0x180007308`
- `0x180007af4`
- `0x180008458`
- `0x1800084c4`
- `0x1800085e8`
- `0x180008868`
- `0x18000a140`
- `0x18000a160`
- `0x18000a434`
- `0x18000aa38`
- `0x18000d9cc`
- `0x18000e630`
- `0x18000e6f8`
- `0x18000e8b8`
- `0x18000e9b0`
- `0x18000ead0`
- `0x18000fce0`
- `0x180010150`
- `0x180015a00`
- `0x180015a80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007935`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007935`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000794e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007a2e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000794e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007a2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007956`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007964`

## string_xrefs

- `0x180007aaf`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x180007596`: `UUS: Session=%ws, Module=%ws, Version=%ws, Path=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180007308  push    rbx
0x18000730a  push    rsi
0x18000730b  push    rdi
0x18000730c  push    r12
0x18000730e  push    r13
0x180007310  push    r14
0x180007312  push    r15
0x180007314  sub     rsp, 360h
0x18000731b  mov     rax, cs:__security_cookie
0x180007322  xor     rax, rsp
0x180007325  mov     [rsp+398h+var_48], rax
0x18000732d  mov     r15, r9
0x180007330  mov     edi, r8d
0x180007333  mov     r12, rcx
0x180007336  mov     [rsp+398h+var_2D8], rcx
0x18000733e  mov     rax, [rsp+398h+arg_20]
0x180007346  mov     [rsp+398h+var_320], rax
0x18000734b  xor     ebx, ebx
0x18000734d  test    rcx, rcx
0x180007350  jz      loc_180007A66
0x180007356  cmp     [rcx], bx
0x180007359  jz      loc_180007A66
0x18000735f  cmp     cs:Src, bx
0x180007366  jnz     short loc_180007370
0x180007368  lea     edx, [rbx+28h]
0x18000736b  jmp     loc_180007A6B
0x180007370  test    rax, rax
0x180007373  jnz     short loc_18000737D
0x180007375  lea     edx, [rax+29h]
0x180007378  jmp     loc_180007A6B
0x18000737d  mov     [rax], rbx
0x180007380  mov     esi, ebx
0x180007382  mov     r14, rbx
0x180007385  mov     [rsp+398h+var_328], rbx
0x18000738a  mov     [rsp+398h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x180007396  mov     [rsp+398h+var_2E8], rbx
0x18000739e  mov     [rsp+398h+lpMem], rbx
0x1800073a6  mov     al, dil
0x1800073a9  mov     r13d, 1
0x1800073af  and     al, r13b
0x1800073b2  mov     [rsp+398h+var_348], al
0x1800073b6  mov     [rsp+398h+var_347], al
0x1800073ba  mov     eax, edi
0x1800073bc  and     eax, 2
0x1800073bf  mov     [rsp+398h+var_344], eax
0x1800073c3  mov     [rsp+398h+var_334], eax
0x1800073c7  mov     eax, edi
0x1800073c9  and     eax, 4
0x1800073cc  mov     [rsp+398h+var_33C], eax
0x1800073d0  mov     [rsp+398h+var_330], eax
0x1800073d4  and     edi, 8
0x1800073d7  mov     [rsp+398h+var_338], edi
0x1800073db  cmp     [rsp+398h+var_348], bl
0x1800073df  jz      loc_1800078C5
0x1800073e5  xorps   xmm0, xmm0
0x1800073e8  movups  [rsp+398h+var_278], xmm0
0x1800073f0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800073f8  movdqu  [rsp+398h+var_268], xmm1
0x180007401  mov     word ptr [rsp+398h+var_278], bx
0x180007409  movups  xmmword ptr [rsp+398h+var_298], xmm0
0x180007411  movdqu  [rsp+398h+var_288], xmm1
0x18000741a  mov     word ptr [rsp+398h+var_298], bx
0x180007422  mov     [rsp+398h+var_340], ebx
0x180007426  cmp     [r9], rbx
0x180007429  jnz     short loc_180007471
0x18000742b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007432  lea     ecx, [r13+0Fh]; unsigned __int64
0x180007436  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000743b  mov     [rsp+398h+var_2E0], rax
0x180007443  test    rax, rax
0x180007446  jz      short loc_180007455
0x180007448  mov     rdx, r12; wchar_t *
0x18000744b  mov     rcx, rax; this
0x18000744e  call    ??0Session@uus@@QEAA@PEB_W@Z; uus::Session::Session(wchar_t const *)
0x180007453  jmp     short loc_180007458
0x180007455  mov     rax, rbx
0x180007458  mov     rcx, [r15]
0x18000745b  mov     [r15], rax
0x18000745e  test    rcx, rcx
0x180007461  jz      short loc_180007471
0x180007463  mov     rax, [rcx]
0x180007466  mov     edx, r13d
0x180007469  mov     rax, [rax]
0x18000746c  call    _guard_dispatch_icall
0x180007471  mov     rax, [r15]
0x180007474  mov     rcx, [rax+8]
0x180007478  test    rcx, rcx
0x18000747b  jz      short loc_18000748E
0x18000747d  mov     rax, [rcx]
0x180007480  mov     rax, [rax+20h]
0x180007484  call    _guard_dispatch_icall
0x180007489  mov     rdx, rax
0x18000748c  jmp     short loc_180007495
0x18000748e  lea     rdx, a0000; "0.0.0.0"
0x180007495  xorps   xmm0, xmm0
0x180007498  movups  xmmword ptr [rsp+398h+Src], xmm0
0x1800074a0  xorps   xmm1, xmm1
0x1800074a3  movdqu  [rsp+398h+var_2B8], xmm1
0x1800074ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800074b0  inc     rax
0x1800074b3  cmp     [rdx+rax*2], bx
0x1800074b7  jnz     short loc_1800074B0
0x1800074b9  mov     r8, rax
0x1800074bc  lea     rcx, [rsp+398h+Src]
0x1800074c4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800074c9  nop
0x1800074ca  lea     rdx, [rsp+398h+Src]
0x1800074d2  cmp     qword ptr [rsp+398h+var_2B8+8], 7
0x1800074db  cmova   rdx, [rsp+398h+Src]; Src
0x1800074e4  mov     r8, qword ptr [rsp+398h+var_2B8]
0x1800074ec  lea     rcx, [rsp+398h+var_278]; void *
0x1800074f4  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x1800074f9  nop
0x1800074fa  lea     rcx, [rsp+398h+Src]
0x180007502  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007507  lea     rdx, [rsp+398h+Src]
0x18000750f  mov     rcx, [r15]
0x180007512  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z; uus::Session::GetFullPath(wchar_t const *)
0x180007517  mov     rdx, rax
0x18000751a  lea     rcx, [rsp+398h+var_298]
0x180007522  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x180007527  lea     rcx, [rsp+398h+Src]
0x18000752f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007534  mov     [rsp+398h+var_340], r13d
0x180007539  mov     eax, edi
0x18000753b  neg     eax
0x18000753d  sbb     r9d, r9d
0x180007540  neg     r9d
0x180007543  add     r9d, 4
0x180007547  lea     rcx, [rsp+398h+var_298]
0x18000754f  cmp     qword ptr [rsp+398h+var_288+8], 7
0x180007558  cmova   rcx, qword ptr [rsp+398h+var_298]
0x180007561  lea     rax, [rsp+398h+var_278]
0x180007569  cmp     qword ptr [rsp+398h+var_268+8], 7
0x180007572  cmova   rax, qword ptr [rsp+398h+var_278]
0x18000757b  mov     [rsp+398h+var_350], rcx
0x180007580  mov     [rsp+398h+var_358], rax
0x180007585  lea     r14, Src
0x18000758c  mov     [rsp+398h+var_360], r14
0x180007591  mov     [rsp+398h+var_368], r12
0x180007596  lea     rax, aUusSessionWsMo; "UUS: Session=%ws, Module=%ws, Version=%"...
0x18000759d  mov     [rsp+398h+var_370], rax
0x1800075a2  mov     qword ptr [rsp+398h+var_378], rbx; int
0x1800075a7  xor     edx, edx
0x1800075a9  xor     ecx, ecx
0x1800075ab  lea     r8d, [rdx+20h]
0x1800075af  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800075b4  mov     rax, [r15]
0x1800075b7  mov     rcx, [rax+8]
0x1800075bb  test    rcx, rcx
0x1800075be  jnz     short loc_1800075CA
0x1800075c0  mov     r14, rbx
0x1800075c3  mov     [rsp+398h+var_328], rbx
0x1800075c8  jmp     short loc_18000760E
0x1800075ca  mov     [rsp+398h+var_2E0], rbx
0x1800075d2  mov     rax, [rcx]
0x1800075d5  lea     r9, [rsp+398h+var_2E0]
0x1800075dd  xor     r8d, r8d
0x1800075e0  mov     rdx, r14
0x1800075e3  mov     rax, [rax+30h]
0x1800075e7  call    _guard_dispatch_icall
0x1800075ec  mov     rcx, [rsp+398h]; this
0x1800075f4  test    eax, eax
0x1800075f6  js      loc_180007AAC
0x1800075fc  mov     r14, [rsp+398h+var_2E0]
0x180007604  mov     [rsp+398h+var_328], r14
0x180007609  test    r14, r14
0x18000760c  jnz     short loc_18000762E
0x18000760e  mov     r15d, 8000FFFFh
0x180007614  mov     esi, r15d
0x180007617  mov     rcx, [rsp+398h]; this
0x18000761f  mov     r9d, r15d; char *
0x180007622  mov     edx, 7Ah ; 'z'; void *
0x180007627  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000762c  jmp     short loc_180007634
0x18000762e  mov     r15d, 8000FFFFh
0x180007634  mov     edx, r13d
0x180007637  jmp     short loc_180007676
0x180007639  xor     ebx, ebx
0x18000763b  lea     r13d, [rbx+1]
0x18000763f  mov     r15d, 8000FFFFh
0x180007645  mov     esi, [rsp+398h+var_344]
0x180007649  mov     r14, [rsp+398h+var_328]
0x18000764e  mov     edx, [rsp+398h+var_340]
0x180007652  mov     eax, [rsp+398h+var_334]
0x180007656  mov     [rsp+398h+var_344], eax
0x18000765a  mov     eax, [rsp+398h+var_330]
0x18000765e  mov     [rsp+398h+var_33C], eax
0x180007662  mov     edi, [rsp+398h+var_338]
0x180007666  mov     al, [rsp+398h+var_347]
0x18000766a  mov     [rsp+398h+var_348], al
0x18000766e  mov     r12, [rsp+398h+var_2D8]
0x180007676  mov     r8d, esi
0x180007679  sar     r8d, 1Fh
0x18000767d  and     r8d, 0Eh
0x180007681  add     r8d, 2
0x180007685  or      r8d, edx
0x180007688  mov     [rsp+398h+var_318], 0
0x180007694  xorps   xmm0, xmm0
0x180007697  movdqu  [rsp+398h+var_310], xmm0
0x1800076a0  xorps   xmm1, xmm1
0x1800076a3  movdqu  [rsp+398h+var_300], xmm1
0x1800076ac  lea     rcx, [rsp+398h+var_278]
0x1800076b4  cmp     qword ptr [rsp+398h+var_268+8], 7
0x1800076bd  cmova   rcx, qword ptr [rsp+398h+var_278]
0x1800076c6  lea     rax, [rsp+398h+var_298]
0x1800076ce  cmp     qword ptr [rsp+398h+var_288+8], 7
0x1800076d7  cmova   rax, qword ptr [rsp+398h+var_298]
0x1800076e0  mov     [rsp+398h+var_370], rcx
0x1800076e5  mov     qword ptr [rsp+398h+var_378], rax; int
0x1800076ea  mov     r9, r12
0x1800076ed  mov     edx, esi
0x1800076ef  lea     rcx, [rsp+398h+var_318]
0x1800076f7  call    ?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z; UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800076fc  mov     rcx, [rsp+398h]; this
0x180007704  test    eax, eax
0x180007706  jns     short loc_180007715
0x180007708  mov     r9d, eax; char *
0x18000770b  mov     edx, 0AAh; void *
0x180007710  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007715  lea     rax, [rsp+398h+lpMem]
0x18000771d  mov     [rsp+398h+Src], rax
0x180007725  mov     [rsp+398h+Src+8], rbx
0x18000772d  mov     byte ptr [rsp+398h+var_2B8], r13b
0x180007735  lea     rdx, [rsp+398h+Src+8]; wchar_t **
0x18000773d  lea     rcx, [rsp+398h+var_318]; this
0x180007745  call    ?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z; UndockedComponentInfo::ToString(wchar_t * *)
0x18000774a  mov     rcx, [rsp+398h]; this
0x180007752  test    eax, eax
0x180007754  jns     short loc_180007763
0x180007756  mov     r9d, eax; char *
0x180007759  mov     edx, 0ABh; void *
0x18000775e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007763  lea     rcx, [rsp+398h+Src]
0x18000776b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x180007770  neg     edi
0x180007772  sbb     eax, eax
0x180007774  neg     eax
0x180007776  add     eax, 4
0x180007779  test    esi, esi
0x18000777b  cmovns  r13d, eax
0x18000777f  mov     rax, [rsp+398h+lpMem]
0x180007787  mov     [rsp+398h+var_368], rax
0x18000778c  lea     rax, aLoadUndockedMo; "Load undocked module: %ws"
0x180007793  mov     [rsp+398h+var_370], rax
0x180007798  mov     [rsp+398h+var_378], esi; int
0x18000779c  mov     r9d, r13d
0x18000779f  xor     edx, edx
0x1800077a1  xor     ecx, ecx
0x1800077a3  lea     r8d, [rdx+20h]
0x1800077a7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800077ac  test    esi, esi
0x1800077ae  jns     loc_18000787C
0x1800077b4  mov     [rsp+398h+Src+8], 0
0x1800077c0  xorps   xmm0, xmm0
0x1800077c3  movdqu  [rsp+398h+var_2B8], xmm0
0x1800077cc  xorps   xmm1, xmm1
0x1800077cf  movdqu  [rsp+398h+var_2A8], xmm1
0x1800077d8  lea     rax, ??_7UndockedComponentLoadFailedEvent@@6B@; const UndockedComponentLoadFailedEvent::`vftable'
0x1800077df  mov     [rsp+398h+Src], rax
0x1800077e7  lea     rdx, [rsp+398h+var_318]; struct UndockedComponentInfo *
0x1800077ef  lea     rcx, [rsp+398h+Src]; this
0x1800077f7  call    ?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z; UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)
0x1800077fc  mov     rcx, [rsp+398h]
0x180007804  test    eax, eax
0x180007806  jns     short loc_18000780F
0x180007808  mov     edx, 0B5h
0x18000780d  jmp     short loc_180007832
0x18000780f  xor     r8d, r8d; char *
0x180007812  xor     edx, edx; char *
0x180007814  lea     rcx, [rsp+398h+Src]; this
0x18000781c  call    ?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z; UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)
0x180007821  mov     rcx, [rsp+398h]; this
0x180007829  test    eax, eax
0x18000782b  jns     short loc_18000783A
0x18000782d  mov     edx, 0B7h; void *
0x180007832  mov     r9d, eax; char *
0x180007835  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000783a  lea     rcx, [rsp+398h+Src+8]; this
0x180007842  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x180007847  cmp     [rsp+398h+var_33C], ebx
0x18000784b  jz      short loc_18000787C
0x18000784d  lea     rcx, [rsp+398h+var_318]; this
0x180007855  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x18000785a  nop
0x18000785b  lea     rcx, [rsp+398h+var_298]
0x180007863  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007868  nop
0x180007869  lea     rcx, [rsp+398h+var_278]
0x180007871  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007876  mov     eax, [rsp+398h+var_33C]
0x18000787a  jmp     short loc_1800078CB
0x18000787c  mov     r13d, [rsp+398h+var_344]
0x180007881  test    r13d, r13d
0x180007884  jz      short loc_180007896
0x180007886  mov     rcx, [rsp+398h]; this
0x18000788e  test    esi, esi
0x180007890  js      loc_180007AC1
0x180007896  lea     rcx, [rsp+398h+var_318]; this
0x18000789e  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
  ... truncated ...
```
