# UndockedModuleLoader::Load

- ea: `0x180005524`
- end: `0x180005d07`
- name: `UndockedModuleLoader::Load`
- size: `2019`
- prototype: `__int64 __fastcall(wchar_t *, __int64, char, __int64 *, HMODULE *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005d80`

## callees

- `0x180003760`
- `0x180005524`
- `0x180005d10`
- `0x180006934`
- `0x180008848`
- `0x180008ac8`
- `0x180008ae8`
- `0x180008dbc`
- `0x180009e68`
- `0x18000a430`
- `0x18000a574`
- `0x18000a620`
- `0x18000a85c`
- `0x18000a98c`
- `0x18000b248`
- `0x18000da40`
- `0x18000e6a4`
- `0x18000e864`
- `0x18000e95c`
- `0x18000ea80`
- `0x18000fc90`
- `0x180010100`
- `0x1800159b0`
- `0x180015a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005b51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005b51`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005b6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005c4a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005b6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005c4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005b72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b80`

## string_xrefs

- `0x1800057b2`: `UUS: Session=%ws, Module=%ws, Version=%ws, Path=%ws`
- `0x180005ccb`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`

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
0x180005524  push    rbx
0x180005526  push    rsi
0x180005527  push    rdi
0x180005528  push    r12
0x18000552a  push    r13
0x18000552c  push    r14
0x18000552e  push    r15
0x180005530  sub     rsp, 360h
0x180005537  mov     rax, cs:__security_cookie
0x18000553e  xor     rax, rsp
0x180005541  mov     [rsp+398h+var_48], rax
0x180005549  mov     r15, r9
0x18000554c  mov     edi, r8d
0x18000554f  mov     r12, rcx
0x180005552  mov     [rsp+398h+var_2D8], rcx
0x18000555a  mov     rax, [rsp+398h+arg_20]
0x180005562  mov     [rsp+398h+var_320], rax
0x180005567  xor     ebx, ebx
0x180005569  test    rcx, rcx
0x18000556c  jz      loc_180005C82
0x180005572  cmp     [rcx], bx
0x180005575  jz      loc_180005C82
0x18000557b  cmp     cs:Src, bx
0x180005582  jnz     short loc_18000558C
0x180005584  lea     edx, [rbx+28h]
0x180005587  jmp     loc_180005C87
0x18000558c  test    rax, rax
0x18000558f  jnz     short loc_180005599
0x180005591  lea     edx, [rax+29h]
0x180005594  jmp     loc_180005C87
0x180005599  mov     [rax], rbx
0x18000559c  mov     esi, ebx
0x18000559e  mov     r14, rbx
0x1800055a1  mov     [rsp+398h+var_328], rbx
0x1800055a6  mov     [rsp+398h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x1800055b2  mov     [rsp+398h+var_2E8], rbx
0x1800055ba  mov     [rsp+398h+lpMem], rbx
0x1800055c2  mov     al, dil
0x1800055c5  mov     r13d, 1
0x1800055cb  and     al, r13b
0x1800055ce  mov     [rsp+398h+var_348], al
0x1800055d2  mov     [rsp+398h+var_347], al
0x1800055d6  mov     eax, edi
0x1800055d8  and     eax, 2
0x1800055db  mov     [rsp+398h+var_344], eax
0x1800055df  mov     [rsp+398h+var_334], eax
0x1800055e3  mov     eax, edi
0x1800055e5  and     eax, 4
0x1800055e8  mov     [rsp+398h+var_33C], eax
0x1800055ec  mov     [rsp+398h+var_330], eax
0x1800055f0  and     edi, 8
0x1800055f3  mov     [rsp+398h+var_338], edi
0x1800055f7  cmp     [rsp+398h+var_348], bl
0x1800055fb  jz      loc_180005AE1
0x180005601  xorps   xmm0, xmm0
0x180005604  movups  [rsp+398h+var_278], xmm0
0x18000560c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180005614  movdqu  [rsp+398h+var_268], xmm1
0x18000561d  mov     word ptr [rsp+398h+var_278], bx
0x180005625  movups  xmmword ptr [rsp+398h+var_298], xmm0
0x18000562d  movdqu  [rsp+398h+var_288], xmm1
0x180005636  mov     word ptr [rsp+398h+var_298], bx
0x18000563e  mov     [rsp+398h+var_340], ebx
0x180005642  cmp     [r9], rbx
0x180005645  jnz     short loc_18000568D
0x180005647  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000564e  lea     ecx, [r13+0Fh]; unsigned __int64
0x180005652  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005657  mov     [rsp+398h+var_2E0], rax
0x18000565f  test    rax, rax
0x180005662  jz      short loc_180005671
0x180005664  mov     rdx, r12; wchar_t *
0x180005667  mov     rcx, rax; this
0x18000566a  call    ??0Session@uus@@QEAA@PEB_W@Z; uus::Session::Session(wchar_t const *)
0x18000566f  jmp     short loc_180005674
0x180005671  mov     rax, rbx
0x180005674  mov     rcx, [r15]
0x180005677  mov     [r15], rax
0x18000567a  test    rcx, rcx
0x18000567d  jz      short loc_18000568D
0x18000567f  mov     rax, [rcx]
0x180005682  mov     edx, r13d
0x180005685  mov     rax, [rax]
0x180005688  call    _guard_dispatch_icall
0x18000568d  mov     rax, [r15]
0x180005690  mov     rcx, [rax+8]
0x180005694  test    rcx, rcx
0x180005697  jz      short loc_1800056AA
0x180005699  mov     rax, [rcx]
0x18000569c  mov     rax, [rax+20h]
0x1800056a0  call    _guard_dispatch_icall
0x1800056a5  mov     rdx, rax
0x1800056a8  jmp     short loc_1800056B1
0x1800056aa  lea     rdx, a0000; "0.0.0.0"
0x1800056b1  xorps   xmm0, xmm0
0x1800056b4  movups  xmmword ptr [rsp+398h+Src], xmm0
0x1800056bc  xorps   xmm1, xmm1
0x1800056bf  movdqu  [rsp+398h+var_2B8], xmm1
0x1800056c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800056cc  inc     rax
0x1800056cf  cmp     [rdx+rax*2], bx
0x1800056d3  jnz     short loc_1800056CC
0x1800056d5  mov     r8, rax
0x1800056d8  lea     rcx, [rsp+398h+Src]
0x1800056e0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800056e5  nop
0x1800056e6  lea     rdx, [rsp+398h+Src]
0x1800056ee  cmp     qword ptr [rsp+398h+var_2B8+8], 7
0x1800056f7  cmova   rdx, [rsp+398h+Src]; Src
0x180005700  mov     r8, qword ptr [rsp+398h+var_2B8]
0x180005708  lea     rcx, [rsp+398h+var_278]; void *
0x180005710  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180005715  nop
0x180005716  lea     rcx, [rsp+398h+Src]
0x18000571e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005723  lea     rdx, [rsp+398h+Src]
0x18000572b  mov     rcx, [r15]
0x18000572e  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z; uus::Session::GetFullPath(wchar_t const *)
0x180005733  mov     rdx, rax
0x180005736  lea     rcx, [rsp+398h+var_298]
0x18000573e  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x180005743  lea     rcx, [rsp+398h+Src]
0x18000574b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005750  mov     [rsp+398h+var_340], r13d
0x180005755  mov     eax, edi
0x180005757  neg     eax
0x180005759  sbb     r9d, r9d
0x18000575c  neg     r9d
0x18000575f  add     r9d, 4
0x180005763  lea     rcx, [rsp+398h+var_298]
0x18000576b  cmp     qword ptr [rsp+398h+var_288+8], 7
0x180005774  cmova   rcx, qword ptr [rsp+398h+var_298]
0x18000577d  lea     rax, [rsp+398h+var_278]
0x180005785  cmp     qword ptr [rsp+398h+var_268+8], 7
0x18000578e  cmova   rax, qword ptr [rsp+398h+var_278]
0x180005797  mov     [rsp+398h+var_350], rcx
0x18000579c  mov     [rsp+398h+var_358], rax
0x1800057a1  lea     r14, Src
0x1800057a8  mov     [rsp+398h+var_360], r14
0x1800057ad  mov     [rsp+398h+var_368], r12
0x1800057b2  lea     rax, aUusSessionWsMo; "UUS: Session=%ws, Module=%ws, Version=%"...
0x1800057b9  mov     [rsp+398h+var_370], rax
0x1800057be  mov     qword ptr [rsp+398h+var_378], rbx; int
0x1800057c3  xor     edx, edx
0x1800057c5  xor     ecx, ecx
0x1800057c7  lea     r8d, [rdx+20h]
0x1800057cb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800057d0  mov     rax, [r15]
0x1800057d3  mov     rcx, [rax+8]
0x1800057d7  test    rcx, rcx
0x1800057da  jnz     short loc_1800057E6
0x1800057dc  mov     r14, rbx
0x1800057df  mov     [rsp+398h+var_328], rbx
0x1800057e4  jmp     short loc_18000582A
0x1800057e6  mov     [rsp+398h+var_2E0], rbx
0x1800057ee  mov     rax, [rcx]
0x1800057f1  lea     r9, [rsp+398h+var_2E0]
0x1800057f9  xor     r8d, r8d
0x1800057fc  mov     rdx, r14
0x1800057ff  mov     rax, [rax+30h]
0x180005803  call    _guard_dispatch_icall
0x180005808  mov     rcx, [rsp+398h]; this
0x180005810  test    eax, eax
0x180005812  js      loc_180005CC8
0x180005818  mov     r14, [rsp+398h+var_2E0]
0x180005820  mov     [rsp+398h+var_328], r14
0x180005825  test    r14, r14
0x180005828  jnz     short loc_18000584A
0x18000582a  mov     r15d, 8000FFFFh
0x180005830  mov     esi, r15d
0x180005833  mov     rcx, [rsp+398h]; this
0x18000583b  mov     r9d, r15d; char *
0x18000583e  mov     edx, 7Ah ; 'z'; void *
0x180005843  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180005848  jmp     short loc_180005850
0x18000584a  mov     r15d, 8000FFFFh
0x180005850  mov     edx, r13d
0x180005853  jmp     short loc_180005892
0x180005855  xor     ebx, ebx
0x180005857  lea     r13d, [rbx+1]
0x18000585b  mov     r15d, 8000FFFFh
0x180005861  mov     esi, [rsp+398h+var_344]
0x180005865  mov     r14, [rsp+398h+var_328]
0x18000586a  mov     edx, [rsp+398h+var_340]
0x18000586e  mov     eax, [rsp+398h+var_334]
0x180005872  mov     [rsp+398h+var_344], eax
0x180005876  mov     eax, [rsp+398h+var_330]
0x18000587a  mov     [rsp+398h+var_33C], eax
0x18000587e  mov     edi, [rsp+398h+var_338]
0x180005882  mov     al, [rsp+398h+var_347]
0x180005886  mov     [rsp+398h+var_348], al
0x18000588a  mov     r12, [rsp+398h+var_2D8]
0x180005892  mov     r8d, esi
0x180005895  sar     r8d, 1Fh
0x180005899  and     r8d, 0Eh
0x18000589d  add     r8d, 2
0x1800058a1  or      r8d, edx
0x1800058a4  mov     [rsp+398h+var_318], 0
0x1800058b0  xorps   xmm0, xmm0
0x1800058b3  movdqu  [rsp+398h+var_310], xmm0
0x1800058bc  xorps   xmm1, xmm1
0x1800058bf  movdqu  [rsp+398h+var_300], xmm1
0x1800058c8  lea     rcx, [rsp+398h+var_278]
0x1800058d0  cmp     qword ptr [rsp+398h+var_268+8], 7
0x1800058d9  cmova   rcx, qword ptr [rsp+398h+var_278]
0x1800058e2  lea     rax, [rsp+398h+var_298]
0x1800058ea  cmp     qword ptr [rsp+398h+var_288+8], 7
0x1800058f3  cmova   rax, qword ptr [rsp+398h+var_298]
0x1800058fc  mov     [rsp+398h+var_370], rcx
0x180005901  mov     qword ptr [rsp+398h+var_378], rax; int
0x180005906  mov     r9, r12
0x180005909  mov     edx, esi
0x18000590b  lea     rcx, [rsp+398h+var_318]
0x180005913  call    ?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z; UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)
0x180005918  mov     rcx, [rsp+398h]; this
0x180005920  test    eax, eax
0x180005922  jns     short loc_180005931
0x180005924  mov     r9d, eax; char *
0x180005927  mov     edx, 0AAh; void *
0x18000592c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005931  lea     rax, [rsp+398h+lpMem]
0x180005939  mov     [rsp+398h+Src], rax
0x180005941  mov     [rsp+398h+Src+8], rbx
0x180005949  mov     byte ptr [rsp+398h+var_2B8], r13b
0x180005951  lea     rdx, [rsp+398h+Src+8]; wchar_t **
0x180005959  lea     rcx, [rsp+398h+var_318]; this
0x180005961  call    ?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z; UndockedComponentInfo::ToString(wchar_t * *)
0x180005966  mov     rcx, [rsp+398h]; this
0x18000596e  test    eax, eax
0x180005970  jns     short loc_18000597F
0x180005972  mov     r9d, eax; char *
0x180005975  mov     edx, 0ABh; void *
0x18000597a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000597f  lea     rcx, [rsp+398h+Src]
0x180005987  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x18000598c  neg     edi
0x18000598e  sbb     eax, eax
0x180005990  neg     eax
0x180005992  add     eax, 4
0x180005995  test    esi, esi
0x180005997  cmovns  r13d, eax
0x18000599b  mov     rax, [rsp+398h+lpMem]
0x1800059a3  mov     [rsp+398h+var_368], rax
0x1800059a8  lea     rax, aLoadUndockedMo; "Load undocked module: %ws"
0x1800059af  mov     [rsp+398h+var_370], rax
0x1800059b4  mov     [rsp+398h+var_378], esi; int
0x1800059b8  mov     r9d, r13d
0x1800059bb  xor     edx, edx
0x1800059bd  xor     ecx, ecx
0x1800059bf  lea     r8d, [rdx+20h]
0x1800059c3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800059c8  test    esi, esi
0x1800059ca  jns     loc_180005A98
0x1800059d0  mov     [rsp+398h+Src+8], 0
0x1800059dc  xorps   xmm0, xmm0
0x1800059df  movdqu  [rsp+398h+var_2B8], xmm0
0x1800059e8  xorps   xmm1, xmm1
0x1800059eb  movdqu  [rsp+398h+var_2A8], xmm1
0x1800059f4  lea     rax, ??_7UndockedComponentLoadFailedEvent@@6B@; const UndockedComponentLoadFailedEvent::`vftable'
0x1800059fb  mov     [rsp+398h+Src], rax
0x180005a03  lea     rdx, [rsp+398h+var_318]; struct UndockedComponentInfo *
0x180005a0b  lea     rcx, [rsp+398h+Src]; this
0x180005a13  call    ?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z; UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)
0x180005a18  mov     rcx, [rsp+398h]
0x180005a20  test    eax, eax
0x180005a22  jns     short loc_180005A2B
0x180005a24  mov     edx, 0B5h
0x180005a29  jmp     short loc_180005A4E
0x180005a2b  xor     r8d, r8d; char *
0x180005a2e  xor     edx, edx; char *
0x180005a30  lea     rcx, [rsp+398h+Src]; this
0x180005a38  call    ?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z; UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)
0x180005a3d  mov     rcx, [rsp+398h]; this
0x180005a45  test    eax, eax
0x180005a47  jns     short loc_180005A56
0x180005a49  mov     edx, 0B7h; void *
0x180005a4e  mov     r9d, eax; char *
0x180005a51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180005a56  lea     rcx, [rsp+398h+Src+8]; this
0x180005a5e  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x180005a63  cmp     [rsp+398h+var_33C], ebx
0x180005a67  jz      short loc_180005A98
0x180005a69  lea     rcx, [rsp+398h+var_318]; this
0x180005a71  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x180005a76  nop
0x180005a77  lea     rcx, [rsp+398h+var_298]
0x180005a7f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005a84  nop
0x180005a85  lea     rcx, [rsp+398h+var_278]
0x180005a8d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180005a92  mov     eax, [rsp+398h+var_33C]
0x180005a96  jmp     short loc_180005AE7
0x180005a98  mov     r13d, [rsp+398h+var_344]
0x180005a9d  test    r13d, r13d
0x180005aa0  jz      short loc_180005AB2
0x180005aa2  mov     rcx, [rsp+398h]; this
0x180005aaa  test    esi, esi
0x180005aac  js      loc_180005CDD
0x180005ab2  lea     rcx, [rsp+398h+var_318]; this
0x180005aba  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
  ... truncated ...
```
