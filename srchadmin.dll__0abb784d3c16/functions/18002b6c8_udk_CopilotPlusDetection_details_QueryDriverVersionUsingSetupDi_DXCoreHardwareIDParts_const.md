# udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)

- ea: `0x18002b6c8`
- end: `0x18002bcfc`
- name: `?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z`
- size: `1588`
- prototype: `__int64 __fastcall(udk::CopilotPlusDetection::details *__hidden this, const struct DXCoreHardwareIDParts *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002ae48`

## callees

- `0x1800058c0`
- `0x180005cc0`
- `0x18000f82c`
- `0x18000fbb0`
- `0x18000fc9c`
- `0x180029078`
- `0x180029aa0`
- `0x180029c8c`
- `0x18002ad54`
- `0x18002b650`
- `0x18002b6c8`
- `0x18002c060`
- `0x18002c164`
- `0x18002c180`
- `0x180032010`

## import_xrefs

- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18002bb14`
- `msvcp_win!?_Xinvalid_argument@std@@YAXPEBD@Z` at `0x18002bb14`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002bb2e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18002bb2e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18002bafb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18002bafb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002babd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002babd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b71d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b71d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b746`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b777`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b80c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b746`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b777`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b7d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b80c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bc64`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b9ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002b9ec`

## string_xrefs

- `0x18002b716`: `setupapi.dll`

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
  const char *v7; // r9
  FARPROC ProcAddress; // r14
  const char *v9; // r9
  FARPROC v10; // r13
  const char *v11; // r9
  FARPROC v12; // r12
  const char *v13; // r9
  const char *v14; // r9
  __int64 v15; // rax
  __int64 v16; // r15
  unsigned int v17; // esi
  wchar_t *v18; // r14
  const char *v19; // r9
  __int64 trivial_2; // rbx
  __int64 v21; // rax
  __int64 v22; // rcx
  const WCHAR *v23; // r8
  const WCHAR *v24; // rcx
  const char *v25; // r9
  __int16 v26; // ax
  unsigned __int64 v27; // rsi
  unsigned __int64 i; // rbx
  _DWORD *v29; // rax
  const wchar_t *v30; // r12
  __int16 v31; // cx
  wchar_t *v32; // r14
  unsigned __int64 v33; // rdx
  __int16 v34; // ax
  void *v36; // rdx
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // [rsp+50h] [rbp-138h] BYREF
  __int64 v40; // [rsp+60h] [rbp-128h]
  wchar_t *EndPtr; // [rsp+68h] [rbp-120h] BYREF
  int v42; // [rsp+70h] [rbp-118h] BYREF
  _QWORD v43[2]; // [rsp+78h] [rbp-110h] BYREF
  _DWORD *v44; // [rsp+88h] [rbp-100h]
  __int64 v45; // [rsp+90h] [rbp-F8h]
  FARPROC v46; // [rsp+98h] [rbp-F0h]
  char v47; // [rsp+A0h] [rbp-E8h]
  FARPROC v48; // [rsp+A8h] [rbp-E0h]
  _DWORD v49[4]; // [rsp+B0h] [rbp-D8h] BYREF
  LPCWCH lpString1[2]; // [rsp+C0h] [rbp-C8h] BYREF
  int cchCount2[2]; // [rsp+D0h] [rbp-B8h]
  unsigned __int64 v52; // [rsp+D8h] [rbp-B0h]
  _OWORD v53[2]; // [rsp+E0h] [rbp-A8h] BYREF
  wchar_t *String[4]; // [rsp+100h] [rbp-88h] BYREF
  _WORD v55[24]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v43[1] = this;
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<unsigned int const &,unsigned int const &>(
    a2,
    (char *)a2 + 4);
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0x800u);
  v6 = Library;
  v43[0] = Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x86,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v5);
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  if ( !ProcAddress )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x89,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v7);
  v10 = GetProcAddress(v6, "SetupDiDestroyDeviceInfoList");
  if ( !v10 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x8B,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v9);
  v12 = GetProcAddress(v6, "SetupDiEnumDeviceInfo");
  if ( !v12 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x8D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v11);
  EndPtr = (wchar_t *)GetProcAddress(v6, "SetupDiGetDeviceInstanceIdW");
  if ( !EndPtr )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x8F,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v13);
  v48 = GetProcAddress(v6, "SetupDiGetDevicePropertyW");
  if ( !v48 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x91,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
      v14);
  udk::npu_detection::HardwareIdToVendorProductString(lpString1, a2);
  v49[0] = -266691245;
  v49[1] = 1221738486;
  v49[2] = -1480026209;
  v49[3] = 216091392;
  v15 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, _QWORD, __int64))ProcAddress)(v49, 0, 0, 2);
  v16 = v15;
  if ( v15 != -1 )
  {
    v45 = v15;
    v46 = v10;
    v47 = 1;
    memset(v53, 0, sizeof(v53));
    LODWORD(v53[0]) = 32;
    v17 = 0;
    v18 = EndPtr;
    while ( ((unsigned int (__fastcall *)(__int64, _QWORD, _OWORD *))v12)(v16, v17, v53) )
    {
      v39 = 0;
      v40 = 0;
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&v39);
      if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, __int64, _QWORD))v18)(
              v16,
              v53,
              v39,
              (__int64)(*((_QWORD *)&v39 + 1) - v39) >> 1,
              0) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xAB,
          (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
          v19);
      trivial_2 = _std_find_trivial_2(v39, *((_QWORD *)&v39 + 1), 0);
      v21 = _std_find_trivial_2(v39, trivial_2, 92);
      if ( v21 != *((_QWORD *)&v39 + 1) && trivial_2 != *((_QWORD *)&v39 + 1) )
      {
        v22 = v21 + 2;
        if ( v21 + 2 != trivial_2 && (unsigned __int64)((trivial_2 - v22) >> 1) >= *(_QWORD *)cchCount2 )
        {
          v23 = (const WCHAR *)(v39 + 2 * ((v22 - (__int64)v39) >> 1));
          v24 = (const WCHAR *)lpString1;
          if ( v52 > 7 )
            v24 = lpString1[0];
          if ( CompareStringOrdinal(v24, cchCount2[0], v23, cchCount2[0], 1) == 2 )
          {
            v42 = 0;
            if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, const DEVPROPKEY *, int *))v48)(
                    v16,
                    v53,
                    &DEVPKEY_Device_DriverVersion,
                    &v42) )
              wil::details::in1diag3::_Throw_GetLastError(
                retaddr,
                (void *)0xC2,
                (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                v25);
            v26 = 0;
            v48 = 0;
            v27 = 0;
            for ( i = 0; i < 4; ++i )
            {
              if ( v27 >= 0x18 )
                wil::details::in1diag3::_Throw_Hr(
                  retaddr,
                  (void *)0xCB,
                  (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                  (const char *)0x80070057LL,
                  (int)v55);
              std::wstring::wstring(String, &v55[v27]);
              v29 = (_DWORD *)_o__errno();
              v44 = v29;
              v30 = (const wchar_t *)String;
              if ( String[3] > (wchar_t *)7 )
                v30 = String[0];
              EndPtr = 0;
              *v29 = 0;
              v31 = wcstol(v30, &EndPtr, 10);
              v32 = EndPtr;
              if ( v30 == EndPtr )
                std::_Xinvalid_argument("invalid stoi argument");
              if ( *v44 == 34 )
                std::_Xout_of_range("stoi argument out of range");
              *((_WORD *)&v49[-2] + i) = v31;
              std::wstring::~wstring(String);
              v33 = v32 - v30 + v27;
              v34 = v55[v33];
              if ( i == 3 )
              {
                if ( v34 )
                  wil::details::in1diag3::_Throw_Hr(
                    retaddr,
                    (void *)0xDB,
                    (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v55);
              }
              else
              {
                if ( v34 != 46 )
                  wil::details::in1diag3::_Throw_Hr(
                    retaddr,
                    (void *)0xD3,
                    (unsigned int)"OneCore\\Internal\\Shell\\inc\\CopilotPlusPCDetection.h",
                    (const char *)0x80070057LL,
                    (int)v55);
                v27 = v33 + 1;
              }
              v26 = (__int16)v48;
            }
            *(_WORD *)this = HIWORD(v48);
            *((_WORD *)this + 1) = WORD2(v48);
            *((_WORD *)this + 2) = WORD1(v48);
            *((_WORD *)this + 3) = v26;
            if ( (_QWORD)v39 )
            {
              std::_Deallocate<16>((_QWORD *)v39, 2 * ((v40 - (__int64)v39) >> 1));
              v39 = 0;
              v40 = 0;
            }
            ((void (__fastcall *)(__int64))v10)(v16);
            std::wstring::~wstring(lpString1);
            wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v43);
            return this;
          }
        }
      }
      ++v17;
      if ( (_QWORD)v39 )
        std::_Deallocate<16>((_QWORD *)v39, 2 * ((v40 - (__int64)v39) >> 1));
    }
    if ( GetLastError() != 259 )
      wil::details::in1diag3::Throw_GetLastError(retaddr, v36, v37, v38);
    ((void (__fastcall *)(__int64))v10)(v16);
  }
  udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed();
  *(_QWORD *)this = 0;
  std::wstring::~wstring(lpString1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v43);
  return this;
}

```

## disassembly

```asm
0x18002b6c8  mov     [rsp+arg_10], rbx
0x18002b6cd  mov     [rsp+arg_18], rsi
0x18002b6d2  push    rdi
0x18002b6d3  push    r12
0x18002b6d5  push    r13
0x18002b6d7  push    r14
0x18002b6d9  push    r15
0x18002b6db  sub     rsp, 160h
0x18002b6e2  mov     rax, cs:__security_cookie
0x18002b6e9  xor     rax, rsp
0x18002b6ec  mov     [rsp+188h+var_38], rax
0x18002b6f4  mov     rsi, rdx
0x18002b6f7  mov     rdi, rcx
0x18002b6fa  mov     [rsp+188h+var_108], rcx
0x18002b702  add     rdx, 4
0x18002b706  mov     rcx, rsi
0x18002b709  call    ??$NpuDriverVersionFallbackUsed@AEBIAEBI@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXAEBI0@Z; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackUsed<uint const &,uint const &>(uint const &,uint const &)
0x18002b70e  xor     edx, edx; hFile
0x18002b710  mov     r8d, 800h; dwFlags
0x18002b716  lea     rcx, aSetupapiDll; "setupapi.dll"
0x18002b71d  call    cs:__imp_LoadLibraryExW
0x18002b723  mov     rbx, rax
0x18002b726  mov     [rsp+188h+var_110], rax
0x18002b72b  mov     rcx, [rsp+188h]; this
0x18002b733  test    rax, rax
0x18002b736  jz      loc_18002BCB4
0x18002b73c  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x18002b743  mov     rcx, rax; hModule
0x18002b746  call    cs:__imp_GetProcAddress
0x18002b74c  mov     r14, rax
0x18002b74f  mov     rcx, [rsp+188h]; this
0x18002b757  test    rax, rax
0x18002b75a  jnz     short loc_18002B76D
0x18002b75c  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002b763  mov     edx, 89h; void *
0x18002b768  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b76d  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x18002b774  mov     rcx, rbx; hModule
0x18002b777  call    cs:__imp_GetProcAddress
0x18002b77d  mov     r13, rax
0x18002b780  mov     rcx, [rsp+188h]; this
0x18002b788  test    rax, rax
0x18002b78b  jnz     short loc_18002B79E
0x18002b78d  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002b794  mov     edx, 8Bh; void *
0x18002b799  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b79e  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInfo"
0x18002b7a5  mov     rcx, rbx; hModule
0x18002b7a8  call    cs:__imp_GetProcAddress
0x18002b7ae  mov     r12, rax
0x18002b7b1  mov     rcx, [rsp+188h]; this
0x18002b7b9  test    rax, rax
0x18002b7bc  jnz     short loc_18002B7CF
0x18002b7be  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002b7c5  mov     edx, 8Dh; void *
0x18002b7ca  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b7cf  lea     rdx, aSetupdigetdevi_0; "SetupDiGetDeviceInstanceIdW"
0x18002b7d6  mov     rcx, rbx; hModule
0x18002b7d9  call    cs:__imp_GetProcAddress
0x18002b7df  mov     [rsp+188h+EndPtr], rax
0x18002b7e4  mov     rcx, [rsp+188h]; this
0x18002b7ec  test    rax, rax
0x18002b7ef  jnz     short loc_18002B802
0x18002b7f1  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002b7f8  mov     edx, 8Fh; void *
0x18002b7fd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b802  lea     rdx, aSetupdigetdevi; "SetupDiGetDevicePropertyW"
0x18002b809  mov     rcx, rbx; hModule
0x18002b80c  call    cs:__imp_GetProcAddress
0x18002b812  mov     [rsp+188h+var_E0], rax
0x18002b81a  mov     rcx, [rsp+188h]; this
0x18002b822  xor     ebx, ebx
0x18002b824  test    rax, rax
0x18002b827  jnz     short loc_18002B83A
0x18002b829  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002b830  mov     edx, 91h; void *
0x18002b835  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b83a  mov     rdx, rsi
0x18002b83d  lea     rcx, [rsp+188h+lpString1]
0x18002b845  call    ?HardwareIdToVendorProductString@npu_detection@udk@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUDXCoreHardwareIDParts@@@Z; udk::npu_detection::HardwareIdToVendorProductString(DXCoreHardwareIDParts const &)
0x18002b84a  nop
0x18002b84b  mov     [rsp+188h+var_D8], 0F01A9D53h
0x18002b856  mov     [rsp+188h+var_D4], 48D23FF6h
0x18002b861  mov     [rsp+188h+var_D0], 0A7C8979Fh
0x18002b86c  mov     [rsp+188h+var_CC], 0CE14B00h
0x18002b877  mov     r9d, 2
0x18002b87d  xor     r8d, r8d
0x18002b880  xor     edx, edx
0x18002b882  lea     rcx, [rsp+188h+var_D8]
0x18002b88a  mov     rax, r14
0x18002b88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b892  mov     r15, rax
0x18002b895  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b899  jz      loc_18002BC8B
0x18002b89f  mov     [rsp+188h+var_F8], rax
0x18002b8a7  mov     [rsp+188h+var_F0], r13
0x18002b8af  mov     [rsp+188h+var_E8], 1
0x18002b8b7  xorps   xmm0, xmm0
0x18002b8ba  movups  [rsp+188h+var_A8], xmm0
0x18002b8c2  movups  [rsp+188h+var_98], xmm0
0x18002b8ca  mov     dword ptr [rsp+188h+var_A8], 20h ; ' '
0x18002b8d5  mov     esi, ebx
0x18002b8d7  mov     r14, [rsp+188h+EndPtr]
0x18002b8dc  lea     r8, [rsp+188h+var_A8]
0x18002b8e4  mov     edx, esi
0x18002b8e6  mov     rcx, r15
0x18002b8e9  mov     rax, r12
0x18002b8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8f1  test    eax, eax
0x18002b8f3  jz      loc_18002BC64
0x18002b8f9  xorps   xmm0, xmm0
0x18002b8fc  movdqu  [rsp+188h+var_138], xmm0
0x18002b902  mov     [rsp+188h+var_128], rbx
0x18002b907  lea     rcx, [rsp+188h+var_138]
0x18002b90c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002b911  mov     r8, qword ptr [rsp+188h+var_138]
0x18002b916  mov     r9, qword ptr [rsp+188h+var_138+8]
0x18002b91b  sub     r9, r8
0x18002b91e  sar     r9, 1
0x18002b921  mov     qword ptr [rsp+188h+bIgnoreCase], rbx
0x18002b926  lea     rdx, [rsp+188h+var_A8]
0x18002b92e  mov     rcx, r15
0x18002b931  mov     rax, r14
0x18002b934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b939  mov     rcx, [rsp+188h]; this
0x18002b941  test    eax, eax
0x18002b943  jnz     short loc_18002B956
0x18002b945  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002b94c  mov     edx, 0ABh; void *
0x18002b951  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002b956  xor     r8d, r8d
0x18002b959  mov     rdx, qword ptr [rsp+188h+var_138+8]
0x18002b95e  mov     rcx, qword ptr [rsp+188h+var_138]
0x18002b963  call    __std_find_trivial_2
0x18002b968  mov     rbx, rax
0x18002b96b  mov     r8d, 5Ch ; '\'
0x18002b971  mov     rdx, rax
0x18002b974  mov     rcx, qword ptr [rsp+188h+var_138]
0x18002b979  call    __std_find_trivial_2
0x18002b97e  cmp     rax, qword ptr [rsp+188h+var_138+8]
0x18002b983  jz      loc_18002BC3A
0x18002b989  cmp     rbx, qword ptr [rsp+188h+var_138+8]
0x18002b98e  jz      loc_18002BC3A
0x18002b994  lea     rcx, [rax+2]
0x18002b998  cmp     rcx, rbx
0x18002b99b  jz      loc_18002BC3A
0x18002b9a1  sub     rbx, rcx
0x18002b9a4  sar     rbx, 1
0x18002b9a7  mov     rdx, qword ptr [rsp+188h+cchCount2]; cchCount1
0x18002b9af  cmp     rbx, rdx
0x18002b9b2  jb      loc_18002BC3A
0x18002b9b8  mov     rax, qword ptr [rsp+188h+var_138]
0x18002b9bd  sub     rcx, rax
0x18002b9c0  sar     rcx, 1
0x18002b9c3  lea     r8, [rax+rcx*2]; lpString2
0x18002b9c7  lea     rcx, [rsp+188h+lpString1]
0x18002b9cf  cmp     [rsp+188h+var_B0], 7
0x18002b9d8  cmova   rcx, [rsp+188h+lpString1]; lpString1
0x18002b9e1  mov     [rsp+188h+bIgnoreCase], 1; bIgnoreCase
0x18002b9e9  mov     r9d, edx; cchCount2
0x18002b9ec  call    cs:__imp_CompareStringOrdinal
0x18002b9f2  cmp     eax, 2
0x18002b9f5  jnz     loc_18002BC3A
0x18002b9fb  xor     r14d, r14d
0x18002b9fe  mov     [rsp+188h+var_118], r14d
0x18002ba03  mov     [rsp+188h+var_150], r14d
0x18002ba08  mov     [rsp+188h+var_158], r14
0x18002ba0d  mov     [rsp+188h+var_160], 30h ; '0'
0x18002ba15  lea     rax, [rsp+188h+var_68]
0x18002ba1d  mov     qword ptr [rsp+188h+bIgnoreCase], rax; int
0x18002ba22  lea     r9, [rsp+188h+var_118]
0x18002ba27  lea     r8, DEVPKEY_Device_DriverVersion
0x18002ba2e  lea     rdx, [rsp+188h+var_A8]
0x18002ba36  mov     rcx, r15
0x18002ba39  mov     rax, [rsp+188h+var_E0]
0x18002ba41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba46  mov     rcx, [rsp+188h]; this
0x18002ba4e  test    eax, eax
0x18002ba50  jnz     short loc_18002BA63
0x18002ba52  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002ba59  mov     edx, 0C2h; void *
0x18002ba5e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002ba63  mov     rax, r14
0x18002ba66  mov     [rsp+188h+var_E0], rax
0x18002ba6e  mov     rsi, r14
0x18002ba71  mov     rbx, r14
0x18002ba74  cmp     rbx, 4
0x18002ba78  jnb     loc_18002BBBC
0x18002ba7e  mov     rcx, [rsp+188h]; this
0x18002ba86  cmp     rsi, 18h
0x18002ba8a  jb      short loc_18002BAA3
0x18002ba8c  mov     r9d, 80070057h; char *
0x18002ba92  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002ba99  mov     edx, 0CBh; void *
0x18002ba9e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002baa3  lea     rdx, [rsp+188h+var_68]
0x18002baab  lea     rdx, [rdx+rsi*2]
0x18002baaf  lea     rcx, [rsp+188h+String]
0x18002bab7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002babc  nop
0x18002babd  call    cs:__imp__o__errno
0x18002bac3  mov     [rsp+188h+var_100], rax
0x18002bacb  lea     r12, [rsp+188h+String]
0x18002bad3  cmp     [rsp+188h+var_70], 7
0x18002badc  cmova   r12, [rsp+188h+String]
0x18002bae5  mov     [rsp+188h+EndPtr], r14
0x18002baea  mov     [rax], r14d
0x18002baed  mov     r8d, 0Ah; Radix
0x18002baf3  lea     rdx, [rsp+188h+EndPtr]; EndPtr
0x18002baf8  mov     rcx, r12; String
0x18002bafb  call    cs:__imp_wcstol
0x18002bb01  mov     ecx, eax
0x18002bb03  mov     r14, [rsp+188h+EndPtr]
0x18002bb08  cmp     r12, r14
0x18002bb0b  jnz     short loc_18002BB1A
0x18002bb0d  lea     rcx, aInvalidStoiArg; "invalid stoi argument"
0x18002bb14  call    cs:__imp_?_Xinvalid_argument@std@@YAXPEBD@Z; std::_Xinvalid_argument(char const *)
0x18002bb1a  mov     rax, [rsp+188h+var_100]
0x18002bb22  cmp     dword ptr [rax], 22h ; '"'
0x18002bb25  jnz     short loc_18002BB34
0x18002bb27  lea     rcx, aStoiArgumentOu; "stoi argument out of range"
0x18002bb2e  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18002bb34  sub     r14, r12
0x18002bb37  sar     r14, 1
0x18002bb3a  mov     word ptr [rsp+rbx*2+188h+var_E0], cx
0x18002bb42  lea     rcx, [rsp+188h+String]
0x18002bb4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bb4f  lea     rdx, [r14+rsi]
0x18002bb53  movzx   eax, [rsp+rdx*2+188h+var_68]
0x18002bb5b  mov     rcx, [rsp+188h]; this
0x18002bb63  cmp     rbx, 3
0x18002bb67  jz      short loc_18002BB9D
0x18002bb69  cmp     ax, 2Eh ; '.'
0x18002bb6d  jz      short loc_18002BB86
0x18002bb6f  mov     r9d, 80070057h; char *
0x18002bb75  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002bb7c  mov     edx, 0D3h; void *
0x18002bb81  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002bb86  lea     rsi, [rdx+1]
0x18002bb8a  xor     r14d, r14d
0x18002bb8d  inc     rbx
0x18002bb90  mov     rax, [rsp+188h+var_E0]
0x18002bb98  jmp     loc_18002BA74
0x18002bb9d  xor     r14d, r14d
0x18002bba0  test    ax, ax
0x18002bba3  jz      short loc_18002BB8D
0x18002bba5  mov     r9d, 80070057h; char *
0x18002bbab  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Shell\\inc\\CopilotP"...
0x18002bbb2  mov     edx, 0DBh; void *
0x18002bbb7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002bbbc  movzx   ecx, word ptr [rsp+188h+var_E0+6]
0x18002bbc4  mov     [rdi], cx
0x18002bbc7  movzx   ecx, word ptr [rsp+188h+var_E0+4]
0x18002bbcf  mov     [rdi+2], cx
0x18002bbd3  movzx   ecx, word ptr [rsp+188h+var_E0+2]
0x18002bbdb  mov     [rdi+4], cx
0x18002bbdf  mov     [rdi+6], ax
0x18002bbe3  mov     rcx, qword ptr [rsp+188h+var_138]
0x18002bbe8  test    rcx, rcx
0x18002bbeb  jz      short loc_18002BC0E
0x18002bbed  mov     rdx, [rsp+188h+var_128]
0x18002bbf2  sub     rdx, rcx
0x18002bbf5  sar     rdx, 1
0x18002bbf8  add     rdx, rdx
0x18002bbfb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002bc00  xorps   xmm0, xmm0
0x18002bc03  movdqu  [rsp+188h+var_138], xmm0
0x18002bc09  mov     [rsp+188h+var_128], r14
0x18002bc0e  mov     rcx, r15
0x18002bc11  mov     rax, r13
0x18002bc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc19  nop
0x18002bc1a  lea     rcx, [rsp+188h+lpString1]
0x18002bc22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bc27  nop
0x18002bc28  lea     rcx, [rsp+188h+var_110]
0x18002bc2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18002bc32  mov     rax, rdi
0x18002bc35  jmp     loc_18002BCCE
0x18002bc3a  inc     esi
0x18002bc3c  mov     rcx, qword ptr [rsp+188h+var_138]
0x18002bc41  xor     ebx, ebx
0x18002bc43  test    rcx, rcx
0x18002bc46  jz      loc_18002B8DC
0x18002bc4c  mov     rdx, [rsp+188h+var_128]
0x18002bc51  sub     rdx, rcx
0x18002bc54  sar     rdx, 1
0x18002bc57  add     rdx, rdx
0x18002bc5a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002bc5f  jmp     loc_18002B8DC
0x18002bc64  call    cs:__imp_GetLastError
0x18002bc6a  cmp     eax, 103h
0x18002bc6f  jz      short loc_18002BC7F
0x18002bc71  mov     rcx, [rsp+188h]; this
0x18002bc79  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002bc7f  mov     rcx, r15
0x18002bc82  mov     rax, r13
0x18002bc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc8a  nop
0x18002bc8b  call    ?NpuDriverVersionFallbackFailed@HardwareRequirementsTelemetry@CopilotPlusDetection@udk@@SAXXZ; udk::CopilotPlusDetection::HardwareRequirementsTelemetry::NpuDriverVersionFallbackFailed(void)
  ... truncated ...
```
