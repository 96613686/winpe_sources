# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x1801581c0`
- end: `0x18015882f`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1647`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1803488d8`

## callees

- `0x18000dfa8`
- `0x180025264`
- `0x180026860`
- `0x180091454`
- `0x1800e488c`
- `0x180142eb0`
- `0x1801581c0`
- `0x180158838`
- `0x1801588c4`
- `0x18015c6d0`
- `0x18015cb00`
- `0x18015d868`
- `0x180346394`
- `0x180349820`
- `0x1804a2010`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180158673`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x180158673`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18015868a`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18015868a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18015865a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18015865a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18015861f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18015861f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18015876c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801587dc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18015876c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801587dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158244`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158275`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801582ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801582e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158317`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158244`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158275`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801582ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801582e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180158317`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180158215`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180158215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015878c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015878c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180158551`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180158551`

## string_xrefs

- `0x18015820e`: `setupapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
udk::CopilotPlusDetection::details *__fastcall udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(
        udk::CopilotPlusDetection::details *this,
        const struct DXCoreHardwareIDParts *a2)
{
  HMODULE Library; // rax
  const char *v5; // r9
  HMODULE v6; // rbx
  unsigned int v7; // r12d
  const char *v8; // r9
  FARPROC ProcAddress; // r14
  const char *v10; // r9
  FARPROC v11; // r15
  const char *v12; // r9
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // rax
  __int64 v16; // r13
  char *v17; // r14
  unsigned __int64 v18; // rcx
  size_t v19; // rdi
  const char *v20; // r9
  char *trivial_2; // rdi
  char *v22; // rax
  char *v23; // rcx
  const WCHAR *v24; // r8
  const WCHAR *v25; // rcx
  const char *v26; // r9
  __int16 v27; // ax
  unsigned __int64 v28; // r14
  unsigned __int64 i; // rdi
  INT_PTR (__stdcall *v30)(); // rax
  const wchar_t *v31; // r12
  __int16 v32; // cx
  wchar_t *v33; // r15
  unsigned __int64 v34; // rdx
  __int16 v35; // ax
  const char *v37; // r9
  __int64 v38; // [rsp+50h] [rbp-138h] BYREF
  void *v39; // [rsp+58h] [rbp-130h]
  __int64 v40; // [rsp+60h] [rbp-128h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-120h] BYREF
  int v42; // [rsp+70h] [rbp-118h] BYREF
  FARPROC v43; // [rsp+78h] [rbp-110h]
  udk::CopilotPlusDetection::details *v44; // [rsp+80h] [rbp-108h]
  void (__fastcall *v45)(__int64); // [rsp+88h] [rbp-100h]
  HMODULE v46; // [rsp+90h] [rbp-F8h]
  __int64 v47; // [rsp+98h] [rbp-F0h]
  FARPROC v48; // [rsp+A0h] [rbp-E8h]
  char v49; // [rsp+A8h] [rbp-E0h]
  FARPROC v50; // [rsp+B0h] [rbp-D8h]
  _DWORD v51[4]; // [rsp+B8h] [rbp-D0h] BYREF
  LPCWCH lpString1[2]; // [rsp+C8h] [rbp-C0h] BYREF
  int cchCount2[2]; // [rsp+D8h] [rbp-B0h]
  unsigned __int64 v54; // [rsp+E0h] [rbp-A8h]
  _OWORD v55[2]; // [rsp+E8h] [rbp-A0h] BYREF
  wchar_t *String[4]; // [rsp+108h] [rbp-80h] BYREF
  _WORD v57[24]; // [rsp+128h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v44 = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v6 = Library;
  v46 = Library;
  v7 = 0;
  if ( !Library )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v5);
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v8);
  v11 = GetProcAddress(v6, "SetupDiDestroyDeviceInfoList");
  v45 = (void (__fastcall *)(__int64))v11;
  if ( !v11 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v10);
  EndPtr = (wchar_t *)GetProcAddress(v6, "SetupDiEnumDeviceInfo");
  if ( !EndPtr )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v12);
  v50 = GetProcAddress(v6, "SetupDiGetDeviceInstanceIdW");
  if ( !v50 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v13);
  v43 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
  if ( !v43 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v14);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v51[0] = -266691245;
  v51[1] = 1221738486;
  v51[2] = -1480026209;
  v51[3] = 216091392;
  v15 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v51, 0, 0, 2);
  v16 = v15;
  if ( v15 == -1 )
    goto LABEL_55;
  v47 = v15;
  v48 = v11;
  v49 = 1;
  memset(v55, 0, sizeof(v55));
  LODWORD(v55[0]) = 32;
  while ( ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))EndPtr)(v16, v7, v55) )
  {
    std::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>(&v38);
    v17 = (char *)v39;
    v18 = ((__int64)v39 - v38) >> 1;
    if ( v18 <= 0xC8 )
    {
      if ( v18 >= 0xC8 )
        goto LABEL_22;
      if ( (unsigned __int64)((v40 - v38) >> 1) < 0xC8 )
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(&v38);
        v17 = (char *)v39;
        goto LABEL_22;
      }
      v19 = 2 * (200 - v18);
      memset_0(v39, 0, v19);
      v17 += v19;
    }
    else
    {
      v17 = (char *)(v38 + 400);
    }
    v39 = v17;
LABEL_22:
    if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, __int64, _QWORD, _QWORD))v50)(
            v16,
            v55,
            v38,
            (unsigned int)((__int64)&v17[-v38] >> 1),
            0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
        v20);
    trivial_2 = (char *)_std_find_trivial_2(v38, v39, 0);
    v22 = (char *)_std_find_trivial_2(v38, trivial_2, 92);
    if ( v22 != v39 && trivial_2 != v39 )
    {
      v23 = v22 + 2;
      if ( v22 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v23) >> 1) >= *(_QWORD *)cchCount2 )
      {
        v24 = (const WCHAR *)(v38 + 2 * ((__int64)&v23[-v38] >> 1));
        v25 = (const WCHAR *)lpString1;
        if ( v54 > 7 )
          v25 = lpString1[0];
        if ( CompareStringOrdinal(v25, cchCount2[0], v24, cchCount2[0], 1) == 2 )
        {
          v42 = 0;
          if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v43)(
                  v16,
                  v55,
                  &DEVPKEY_Device_DriverVersion,
                  &v42) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xC2,
              (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
              v26);
          v27 = 0;
          v50 = 0;
          v28 = 0;
          for ( i = 0; i < 4; ++i )
          {
            if ( v28 >= 0x18 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                (const char *)0x80070057LL,
                (int)v57);
            std::wstring::wstring(String, &v57[v28]);
            v30 = (INT_PTR (__stdcall *)())_o__errno();
            v43 = v30;
            v31 = (const wchar_t *)String;
            if ( String[3] > (wchar_t *)7 )
              v31 = String[0];
            EndPtr = 0;
            *(_DWORD *)v30 = 0;
            v32 = wcstol(v31, &EndPtr, 10);
            v33 = EndPtr;
            if ( v31 == EndPtr )
              std::_Xinvalid_argument("invalid stoi argument");
            if ( *(_DWORD *)v43 == 34 )
              std::_Xout_of_range("stoi argument out of range");
            *((_WORD *)&v51[-2] + i) = v32;
            std::filesystem::path::~path((std::filesystem::path *)String);
            v34 = v33 - v31 + v28;
            v35 = v57[v34];
            if ( i == 3 )
            {
              if ( v35 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xDB,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v57);
            }
            else
            {
              if ( v35 != 46 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0xD3,
                  (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v57);
              v28 = v34 + 1;
            }
            v27 = (__int16)v50;
          }
          *(_WORD *)this = HIWORD(v50);
          *((_WORD *)this + 1) = WORD2(v50);
          *((_WORD *)this + 2) = WORD1(v50);
          *((_WORD *)this + 3) = v27;
          std::vector<wchar_t>::_Tidy(&v38);
          v45(v16);
          std::filesystem::path::~path((std::filesystem::path *)lpString1);
          FreeLibrary(v6);
          return this;
        }
      }
    }
    ++v7;
    std::vector<wchar_t>::_Tidy(&v38);
  }
  if ( GetLastError() != 259 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\internal\\shell\\inc\\CopilotPlusPCDetection.h",
      v37);
  ((void (__fastcall *)(__int64))v11)(v16);
LABEL_55:
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::filesystem::path::~path((std::filesystem::path *)lpString1);
  FreeLibrary(v6);
  return this;
}

```

## disassembly

```asm
0x1801581c0  mov     [rsp+arg_10], rbx
0x1801581c5  mov     [rsp+arg_18], rsi
0x1801581ca  push    rdi
0x1801581cb  push    r12
0x1801581cd  push    r13
0x1801581cf  push    r14
0x1801581d1  push    r15
0x1801581d3  sub     rsp, 160h
0x1801581da  mov     rax, cs:__security_cookie
0x1801581e1  xor     rax, rsp
0x1801581e4  mov     [rsp+188h+var_30], rax
0x1801581ec  mov     rdi, rdx
0x1801581ef  mov     rsi, rcx
0x1801581f2  mov     [rsp+188h+var_108], rcx
0x1801581fa  add     rdx, 4
0x1801581fe  mov     rcx, rdi
0x180158201  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x180158206  xor     edx, edx; hFile
0x180158208  mov     r8d, 800h; dwFlags
0x18015820e  lea     rcx, aSetupapiDll; "setupapi.dll"
0x180158215  call    cs:__imp_LoadLibraryExW
0x18015821b  mov     rbx, rax
0x18015821e  mov     [rsp+188h+var_F8], rax
0x180158226  mov     rcx, [rsp+188h]; this
0x18015822e  xor     r12d, r12d
0x180158231  test    rax, rax
0x180158234  jz      loc_1801587E7
0x18015823a  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x180158241  mov     rcx, rax; hModule
0x180158244  call    cs:__imp_GetProcAddress
0x18015824a  mov     r14, rax
0x18015824d  mov     rcx, [rsp+188h]; this
0x180158255  test    rax, rax
0x180158258  jnz     short loc_18015826B
0x18015825a  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180158261  mov     edx, 89h; void *
0x180158266  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015826b  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x180158272  mov     rcx, rbx; hModule
0x180158275  call    cs:__imp_GetProcAddress
0x18015827b  mov     r15, rax
0x18015827e  mov     [rsp+188h+var_100], rax
0x180158286  mov     rcx, [rsp+188h]; this
0x18015828e  test    rax, rax
0x180158291  jnz     short loc_1801582A4
0x180158293  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18015829a  mov     edx, 8Bh; void *
0x18015829f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801582a4  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x1801582ab  mov     rcx, rbx; hModule
0x1801582ae  call    cs:__imp_GetProcAddress
0x1801582b4  mov     [rsp+188h+EndPtr], rax
0x1801582b9  mov     rcx, [rsp+188h]; this
0x1801582c1  test    rax, rax
0x1801582c4  jnz     short loc_1801582D7
0x1801582c6  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801582cd  mov     edx, 8Dh; void *
0x1801582d2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801582d7  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x1801582de  mov     rcx, rbx; hModule
0x1801582e1  call    cs:__imp_GetProcAddress
0x1801582e7  mov     [rsp+188h+var_D8], rax
0x1801582ef  mov     rcx, [rsp+188h]; this
0x1801582f7  test    rax, rax
0x1801582fa  jnz     short loc_18015830D
0x1801582fc  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180158303  mov     edx, 8Fh; void *
0x180158308  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015830d  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x180158314  mov     rcx, rbx; hModule
0x180158317  call    cs:__imp_GetProcAddress
0x18015831d  mov     [rsp+188h+var_110], rax
0x180158322  mov     rcx, [rsp+188h]; this
0x18015832a  test    rax, rax
0x18015832d  jnz     short loc_180158340
0x18015832f  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x180158336  mov     edx, 91h; void *
0x18015833b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180158340  mov     rdx, rdi
0x180158343  lea     rcx, [rsp+188h+lpString1]
0x18015834b  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x180158350  nop
0x180158351  mov     [rsp+188h+var_D0], 0F01A9D53h
0x18015835c  mov     [rsp+188h+var_CC], 48D23FF6h
0x180158367  mov     [rsp+188h+var_C8], 0A7C8979Fh
0x180158372  mov     [rsp+188h+var_C4], 0CE14B00h
0x18015837d  mov     r9d, 2
0x180158383  xor     r8d, r8d
0x180158386  xor     edx, edx
0x180158388  lea     rcx, [rsp+188h+var_D0]
0x180158390  mov     rax, r14
0x180158393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158398  mov     r13, rax
0x18015839b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18015839f  jz      loc_1801587BF
0x1801583a5  mov     [rsp+188h+var_F0], rax
0x1801583ad  mov     [rsp+188h+var_E8], r15
0x1801583b5  mov     [rsp+188h+var_E0], 1
0x1801583bd  xorps   xmm0, xmm0
0x1801583c0  movups  [rsp+188h+var_A0], xmm0
0x1801583c8  movups  [rsp+188h+var_90], xmm0
0x1801583d0  mov     dword ptr [rsp+188h+var_A0], 20h ; ' '
0x1801583db  lea     r8, [rsp+188h+var_A0]
0x1801583e3  mov     edx, r12d
0x1801583e6  mov     rcx, r13
0x1801583e9  mov     rax, [rsp+188h+EndPtr]
0x1801583ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801583f3  xor     edi, edi
0x1801583f5  test    eax, eax
0x1801583f7  jz      loc_18015878C
0x1801583fd  lea     rcx, [rsp+188h+var_138]
0x180158402  call    ??0?$vector@U?$com_ptr@UTextInputCandidateWindowState@implementation@OnScreenInput@ApplicationModel@WindowsUdk@winrt@@@winrt@@V?$allocator@U?$com_ptr@UTextInputCandidateWindowState@implementation@OnScreenInput@ApplicationModel@WindowsUdk@winrt@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>::vector<winrt::com_ptr<winrt::WindowsUdk::ApplicationModel::OnScreenInput::implementation::TextInputCandidateWindowState>>(void)
0x180158407  nop
0x180158408  mov     rdx, [rsp+188h+var_138]
0x18015840d  mov     r14, [rsp+188h+var_130]
0x180158412  mov     rcx, r14
0x180158415  sub     rcx, rdx
0x180158418  sar     rcx, 1
0x18015841b  mov     r8d, 0C8h
0x180158421  cmp     rcx, r8
0x180158424  jbe     short loc_18015842F
0x180158426  lea     r14, [rdx+190h]
0x18015842d  jmp     short loc_18015846E
0x18015842f  jnb     short loc_180158473
0x180158431  mov     rax, [rsp+188h+var_128]
0x180158436  sub     rax, rdx
0x180158439  sar     rax, 1
0x18015843c  cmp     rax, r8
0x18015843f  jnb     short loc_180158452
0x180158441  lea     rcx, [rsp+188h+var_138]
0x180158446  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18015844b  mov     r14, [rsp+188h+var_130]
0x180158450  jmp     short loc_180158473
0x180158452  mov     rax, r8
0x180158455  sub     rax, rcx
0x180158458  lea     rdi, [rax+rax]
0x18015845c  mov     r8, rdi; Size
0x18015845f  xor     edx, edx; Val
0x180158461  mov     rcx, r14; void *
0x180158464  call    memset_0
0x180158469  add     r14, rdi
0x18015846c  xor     edi, edi
0x18015846e  mov     [rsp+188h+var_130], r14
0x180158473  mov     r8, [rsp+188h+var_138]
0x180158478  sub     r14, r8
0x18015847b  sar     r14, 1
0x18015847e  mov     qword ptr [rsp+188h+bIgnoreCase], rdi
0x180158483  mov     r9d, r14d
0x180158486  lea     rdx, [rsp+188h+var_A0]
0x18015848e  mov     rcx, r13
0x180158491  mov     rax, [rsp+188h+var_D8]
0x180158499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015849e  mov     rcx, [rsp+188h]; this
0x1801584a6  test    eax, eax
0x1801584a8  jnz     short loc_1801584BB
0x1801584aa  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801584b1  mov     edx, 0ABh; void *
0x1801584b6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801584bb  xor     r8d, r8d
0x1801584be  mov     rdx, [rsp+188h+var_130]
0x1801584c3  mov     rcx, [rsp+188h+var_138]
0x1801584c8  call    __std_find_trivial_2
0x1801584cd  mov     rdi, rax
0x1801584d0  mov     r8d, 5Ch ; '\'
0x1801584d6  mov     rdx, rax
0x1801584d9  mov     rcx, [rsp+188h+var_138]
0x1801584de  call    __std_find_trivial_2
0x1801584e3  cmp     rax, [rsp+188h+var_130]
0x1801584e8  jz      loc_18015877A
0x1801584ee  cmp     rdi, [rsp+188h+var_130]
0x1801584f3  jz      loc_18015877A
0x1801584f9  lea     rcx, [rax+2]
0x1801584fd  cmp     rcx, rdi
0x180158500  jz      loc_18015877A
0x180158506  sub     rdi, rcx
0x180158509  sar     rdi, 1
0x18015850c  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x180158514  cmp     rdi, rdx
0x180158517  jb      loc_18015877A
0x18015851d  mov     rax, [rsp+188h+var_138]
0x180158522  sub     rcx, rax
0x180158525  sar     rcx, 1
0x180158528  lea     r8, [rax+rcx*2]; lpString2
0x18015852c  lea     rcx, [rsp+188h+lpString1]
0x180158534  cmp     [rsp+188h+var_A8], 7
0x18015853d  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x180158546  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x18015854e  mov     r9d, edx; cchCount2
0x180158551  call    cs:__imp_CompareStringOrdinal
0x180158557  cmp     eax, 2
0x18015855a  jnz     loc_18015877A
0x180158560  xor     r15d, r15d
0x180158563  mov     [rsp+188h+var_118], r15d
0x180158568  mov     [rsp+188h+var_150], r15d
0x18015856d  mov     [rsp+188h+var_158], r15
0x180158572  mov     [rsp+188h+var_160], 30h ; '0'
0x18015857a  lea     rax, [rsp+188h+var_60]
0x180158582  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x180158587  lea     r9, [rsp+188h+var_118]
0x18015858c  lea     r8, DEVPKEY_Device_DriverVersion
0x180158593  lea     rdx, [rsp+188h+var_A0]
0x18015859b  mov     rcx, r13
0x18015859e  mov     rax, [rsp+188h+var_110]
0x1801585a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801585a8  mov     rcx, [rsp+188h]; this
0x1801585b0  test    eax, eax
0x1801585b2  jnz     short loc_1801585C5
0x1801585b4  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801585bb  mov     edx, 0C2h; void *
0x1801585c0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801585c5  mov     rax, r15
0x1801585c8  mov     [rsp+188h+var_D8], rax
0x1801585d0  mov     r14, r15
0x1801585d3  mov     rdi, r15
0x1801585d6  cmp     rdi, 4
0x1801585da  jnb     loc_180158718
0x1801585e0  mov     rcx, [rsp+188h]; this
0x1801585e8  cmp     r14, 18h
0x1801585ec  jb      short loc_180158605
0x1801585ee  mov     r9d, 80070057h; char *
0x1801585f4  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801585fb  mov     edx, 0CBh; void *
0x180158600  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180158605  lea     rdx, [rsp+188h+var_60]
0x18015860d  lea     rdx, [rdx+r14*2]
0x180158611  lea     rcx, [rsp+188h+String]
0x180158619  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18015861e  nop
0x18015861f  call    cs:__imp__o__errno
0x180158625  mov     [rsp+188h+var_110], rax
0x18015862a  lea     r12, [rsp+188h+String]
0x180158632  cmp     [rsp+188h+var_68], 7
0x18015863b  cmova   r12, [rsp+188h+String]
0x180158644  mov     [rsp+188h+EndPtr], r15
0x180158649  mov     [rax], r15d
0x18015864c  mov     r8d, 0Ah; Radix
0x180158652  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x180158657  mov     rcx, r12; String
0x18015865a  call    cs:__imp_wcstol
0x180158660  mov     ecx, eax
0x180158662  mov     r15, [rsp+188h+EndPtr]
0x180158667  cmp     r12, r15
0x18015866a  jnz     short loc_180158679
0x18015866c  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x180158673  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x180158679  mov     rax, [rsp+188h+var_110]
0x18015867e  cmp     dword ptr [rax], 22h ; '"'
0x180158681  jnz     short loc_180158690
0x180158683  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x18015868a  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180158690  sub     r15, r12
0x180158693  sar     r15, 1
0x180158696  mov     word ptr [rsp+rdi*2+188h+var_D8], cx
0x18015869e  lea     rcx, [rsp+188h+String]; this
0x1801586a6  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x1801586ab  lea     rdx, [r15+r14]
0x1801586af  movzx   eax, [rsp+rdx*2+188h+var_60]
0x1801586b7  mov     rcx, [rsp+188h]; this
0x1801586bf  cmp     rdi, 3
0x1801586c3  jz      short loc_1801586F9
0x1801586c5  cmp     ax, 2Eh ; '.'
0x1801586c9  jz      short loc_1801586E2
0x1801586cb  mov     r9d, 80070057h; char *
0x1801586d1  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x1801586d8  mov     edx, 0D3h; void *
0x1801586dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801586e2  lea     r14, [rdx+1]
0x1801586e6  xor     r15d, r15d
0x1801586e9  inc     rdi
0x1801586ec  mov     rax, [rsp+188h+var_D8]
0x1801586f4  jmp     loc_1801585D6
0x1801586f9  xor     r15d, r15d
0x1801586fc  test    ax, ax
0x1801586ff  jz      short loc_1801586E9
0x180158701  mov     r9d, 80070057h; char *
0x180158707  lea     r8, aOnecoreInterna; "onecore\\internal\\shell\\inc\\CopilotP"...
0x18015870e  mov     edx, 0DBh; void *
0x180158713  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180158718  movzx   ecx, word ptr [rsp+188h+var_D8+6]
0x180158720  mov     [rsi], cx
0x180158723  movzx   ecx, word ptr [rsp+188h+var_D8+4]
0x18015872b  mov     [rsi+2], cx
0x18015872f  movzx   ecx, word ptr [rsp+188h+var_D8+2]
0x180158737  mov     [rsi+4], cx
0x18015873b  mov     [rsi+6], ax
0x18015873f  lea     rcx, [rsp+188h+var_138]
0x180158744  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x180158749  nop
0x18015874a  mov     rcx, r13
0x18015874d  mov     rax, [rsp+188h+var_100]
0x180158755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015875a  nop
0x18015875b  lea     rcx, [rsp+188h+lpString1]; this
0x180158763  call    ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
0x180158768  nop
0x180158769  mov     rcx, rbx; hLibModule
0x18015876c  call    cs:__imp_FreeLibrary
0x180158772  mov     rax, rsi
0x180158775  jmp     loc_180158801
0x18015877a  inc     r12d
  ... truncated ...
```
