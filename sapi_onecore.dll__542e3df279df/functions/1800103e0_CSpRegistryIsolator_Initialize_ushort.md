# CSpRegistryIsolator::Initialize(ushort *)

- ea: `0x1800103e0`
- end: `0x1800107d0`
- name: `?Initialize@CSpRegistryIsolator@@AEAAJPEAG@Z`
- size: `1008`
- prototype: `__int64 __fastcall(CSpRegistryIsolator *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a420`

## callees

- `0x18000f96c`
- `0x1800103e0`
- `0x1800107d8`
- `0x18001fdac`
- `0x180021fbc`
- `0x180021fe0`
- `0x180026508`
- `0x1800265e0`
- `0x18002895c`
- `0x18003c6f8`
- `0x180046f00`
- `0x180079e30`
- `0x18007a350`
- `0x18007d7a5`
- `0x18007d7b1`
- `0x1800fcba4`
- `0x1800fe680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800104ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800104ae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800105ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800105ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010565`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010565`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800105a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800105a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010655`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001074c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001075c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001079b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800107ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010475`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001074c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001075c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001079b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800107ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800104c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800104c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800105bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800105bf`
- `USERENV!GetAppContainerRegistryLocation` at `0x18001050f`
- `USERENV!GetAppContainerRegistryLocation` at `0x18001050f`

## string_xrefs

- `0x180010419`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x180010458`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x1800104d6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x180010522`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x180010574`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x180010626`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x18001071c`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\registryisolator.cpp`
- `0x1800106dd`: `HKEY_CURRENT_CONFIG`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSpRegistryIsolator::Initialize(CSpRegistryIsolator *this, unsigned __int16 *a2)
{
  CSpRegistryIsolator *v4; // rcx
  int v5; // eax
  unsigned int v6; // edi
  HRESULT v7; // eax
  HRESULT v8; // eax
  int AppContainerRegistryLocation; // eax
  unsigned int Key; // eax
  __int64 v11; // rdx
  HKEY *v12; // r15
  HKEY v13; // rdi
  const WCHAR *StringRawBuffer; // rax
  char *Reserved1; // r14
  int v16; // eax
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  void *v20; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HSTRING newString; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string2; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD Src[8]; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 Buf1[32]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  if ( a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
      (const char *)0x80070057LL,
      phkResult);
    return 2147942487LL;
  }
  WindowsDeleteString(0);
  string2 = 0;
  v5 = CSpRegistryIsolator::GenerateUniqueRegKeyName(v4, &string2);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
LABEL_34:
    WindowsDeleteString(string2);
    return v6;
  }
  WindowsDeleteString(0);
  newString = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"SOFTWARE\\Microsoft\\Speech_OneCore\\Isolated\\", 0x2Bu, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  v8 = WindowsConcatString(string, string2, &newString);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
LABEL_33:
    WindowsDeleteString(newString);
    newString = 0;
    goto LABEL_34;
  }
  hKey = 0;
  if ( (NtCurrentPeb()->BitField & 0x20) != 0 )
  {
    hKey = 0;
    AppContainerRegistryLocation = GetAppContainerRegistryLocation(983103, &hKey);
    v6 = AppContainerRegistryLocation;
    if ( AppContainerRegistryLocation < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
        (const char *)(unsigned int)AppContainerRegistryLocation,
        phkResult);
LABEL_32:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_33;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    Key = RegOpenKeyExW(HKEY_CURRENT_USER, &cchOriginalDestLength, 0, 0xF003Fu, &hKey);
    if ( Key )
    {
      v11 = 51;
LABEL_14:
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
             (const char *)Key,
             phkResulta);
      goto LABEL_32;
    }
  }
  v12 = (HKEY *)((char *)this + 24);
  v13 = (HKEY)*((_QWORD *)this + 3);
  if ( v13 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&hstringHeader);
    RegCloseKey(v13);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&hstringHeader);
  }
  *v12 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(newString, 0);
  Key = RegCreateKeyExW(hKey, StringRawBuffer, 0, 0, 0, 0xF003Fu, 0, (PHKEY)this + 3, 0);
  if ( Key )
  {
    v11 = 54;
    goto LABEL_14;
  }
  std::make_shared<CSpTokenFileManager,>(&hstringHeader);
  Reserved1 = (char *)hstringHeader.Reserved.Reserved1;
  v16 = CSpTokenFileManager::Initialize((CSpTokenFileManager *)hstringHeader.Reserved.Reserved1);
  v6 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
      (const char *)(unsigned int)v16,
      phkResulta);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_33;
  }
  if ( (int)CSpRegistryIsolator::GetExistingFileTimeHash(this, Buf1) < 0 || memcmp_0(Buf1, Reserved1 + 24, 0x20u) )
  {
    v17 = CSpTokenFileManager::Load((CSpTokenFileManager *)Reserved1, *v12);
    v6 = v17;
    if ( v17 < 0 )
    {
      v18 = (unsigned int)v17;
      v19 = 64;
      goto LABEL_30;
    }
  }
  Src[0] = L"HKEY_CLASSES_ROOT";
  Src[1] = 0xFFFFFFFF80000000uLL;
  Src[2] = L"HKEY_LOCAL_MACHINE";
  Src[3] = -2147483646;
  Src[4] = L"HKEY_CURRENT_USER";
  Src[5] = -2147483647;
  Src[6] = L"HKEY_CURRENT_CONFIG";
  Src[7] = -2147483643;
  *((_QWORD *)this + 1) = 4;
  v20 = operator new[](0x40u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)this = v20;
  if ( !v20 )
  {
    v6 = -2147024882;
    v18 = 2147942414LL;
    v19 = 79;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\registryisolator.cpp",
      (const char *)v18,
      phkResulta);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
    goto LABEL_32;
  }
  memcpy_0(v20, Src, 16LL * *((_QWORD *)this + 1));
  if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)&hstringHeader.Reserved.Reserved2[8]);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(string2);
  return 0;
}

```

## disassembly

```asm
0x1800103e0  push    rbp
0x1800103e2  push    rsi
0x1800103e3  push    rdi
0x1800103e4  push    r12
0x1800103e6  push    r14
0x1800103e8  push    r15
0x1800103ea  lea     rbp, [rsp-8]
0x1800103ef  sub     rsp, 108h
0x1800103f6  mov     rax, cs:__security_cookie
0x1800103fd  xor     rax, rsp
0x180010400  mov     [rbp+30h+var_40], rax
0x180010404  mov     rsi, rcx
0x180010407  xor     r12d, r12d
0x18001040a  test    rdx, rdx
0x18001040d  jz      short loc_180010434
0x18001040f  mov     rcx, [rbp+38h]; this
0x180010413  mov     r9d, 80070057h; char *
0x180010419  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180010420  lea     edx, [r12+22h]; void *
0x180010425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001042a  mov     eax, 80070057h
0x18001042f  jmp     loc_1800107B3
0x180010434  xor     ecx, ecx; string
0x180010436  call    cs:__imp_WindowsDeleteString
0x18001043c  mov     [rsp+130h+string2], r12
0x180010441  lea     rdx, [rsp+130h+string2]; HSTRING *
0x180010446  call    ?GenerateUniqueRegKeyName@CSpRegistryIsolator@@AEAAJPEAPEAUHSTRING__@@@Z; CSpRegistryIsolator::GenerateUniqueRegKeyName(HSTRING__ * *)
0x18001044b  mov     edi, eax
0x18001044d  test    eax, eax
0x18001044f  jns     short loc_18001046E
0x180010451  mov     rcx, [rbp+38h]; this
0x180010455  mov     r9d, eax; char *
0x180010458  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18001045f  mov     edx, 25h ; '%'; void *
0x180010464  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010469  jmp     loc_180010757
0x18001046e  mov     [rsp+130h+newString], r12
0x180010473  xor     ecx, ecx; string
0x180010475  call    cs:__imp_WindowsDeleteString
0x18001047b  mov     [rsp+130h+newString], r12
0x180010480  mov     [rbp+30h+string], r12
0x180010484  lea     r9, [rbp+30h+string]; string
0x180010488  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18001048c  mov     edx, 2Bh ; '+'; length
0x180010491  lea     rcx, sourceString; "SOFTWARE\\Microsoft\\Speech_OneCore\\Is"...
0x180010498  call    cs:__imp_WindowsCreateStringReference
0x18001049e  test    eax, eax
0x1800104a0  jns     short loc_1800104B5
0x1800104a2  xor     r9d, r9d; lpArguments
0x1800104a5  xor     r8d, r8d; nNumberOfArguments
0x1800104a8  lea     edx, [r9+1]; dwExceptionFlags
0x1800104ac  mov     ecx, eax; dwExceptionCode
0x1800104ae  call    cs:__imp_RaiseException
0x1800104b4  int     3; Trap to Debugger
0x1800104b5  lea     r8, [rsp+130h+newString]; newString
0x1800104ba  mov     rdx, [rsp+130h+string2]; string2
0x1800104bf  mov     rcx, [rbp+30h+string]; string1
0x1800104c3  call    cs:__imp_WindowsConcatString
0x1800104c9  mov     edi, eax
0x1800104cb  test    eax, eax
0x1800104cd  jns     short loc_1800104EC
0x1800104cf  mov     rcx, [rbp+38h]; this
0x1800104d3  mov     r9d, eax; char *
0x1800104d6  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800104dd  mov     edx, 28h ; '('; void *
0x1800104e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800104e7  jmp     loc_180010747
0x1800104ec  mov     [rsp+130h+hKey], r12
0x1800104f1  mov     rax, gs:60h
0x1800104fa  test    byte ptr [rax+3], 20h
0x1800104fe  jz      short loc_180010538
0x180010500  mov     [rsp+130h+hKey], r12
0x180010505  lea     rdx, [rsp+130h+hKey]
0x18001050a  mov     ecx, 0F003Fh
0x18001050f  call    cs:__imp_GetAppContainerRegistryLocation
0x180010515  mov     edi, eax
0x180010517  test    eax, eax
0x180010519  jns     short loc_18001058E
0x18001051b  mov     rcx, [rbp+38h]; this
0x18001051f  mov     r9d, eax; char *
0x180010522  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180010529  mov     edx, 2Fh ; '/'; void *
0x18001052e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010533  jmp     loc_18001073C
0x180010538  xor     edx, edx
0x18001053a  lea     rcx, [rsp+130h+hKey]
0x18001053f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010544  lea     rax, [rsp+130h+hKey]
0x180010549  mov     [rsp+130h+phkResult], rax; unsigned int
0x18001054e  mov     r9d, 0F003Fh; samDesired
0x180010554  xor     r8d, r8d; ulOptions
0x180010557  lea     rdx, cchOriginalDestLength; lpSubKey
0x18001055e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180010565  call    cs:__imp_RegOpenKeyExW
0x18001056b  test    eax, eax
0x18001056d  jz      short loc_18001058E
0x18001056f  mov     edx, 33h ; '3'; void *
0x180010574  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18001057b  mov     r9d, eax; char *
0x18001057e  mov     rcx, [rbp+38h]; this
0x180010582  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010587  mov     edi, eax
0x180010589  jmp     loc_18001073C
0x18001058e  lea     r15, [rsi+18h]
0x180010592  mov     rdi, [r15]
0x180010595  test    rdi, rdi
0x180010598  jz      short loc_1800105B5
0x18001059a  lea     rcx, [rbp+30h+hstringHeader]; this
0x18001059e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800105a3  mov     rcx, rdi; hKey
0x1800105a6  call    cs:__imp_RegCloseKey
0x1800105ac  lea     rcx, [rbp+30h+hstringHeader]; this
0x1800105b0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800105b5  mov     [r15], r12
0x1800105b8  xor     edx, edx; length
0x1800105ba  mov     rcx, [rsp+130h+newString]; string
0x1800105bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800105c5  mov     [rsp+130h+lpdwDisposition], r12; lpdwDisposition
0x1800105ca  mov     [rsp+130h+var_F8], r15; phkResult
0x1800105cf  mov     [rsp+130h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800105d4  mov     [rsp+130h+samDesired], 0F003Fh; samDesired
0x1800105dc  mov     dword ptr [rsp+130h+phkResult], r12d; int
0x1800105e1  xor     r9d, r9d; lpClass
0x1800105e4  xor     r8d, r8d; Reserved
0x1800105e7  mov     rdx, rax; lpSubKey
0x1800105ea  mov     rcx, [rsp+130h+hKey]; hKey
0x1800105ef  call    cs:__imp_RegCreateKeyExW
0x1800105f5  test    eax, eax
0x1800105f7  jz      short loc_180010603
0x1800105f9  mov     edx, 36h ; '6'
0x1800105fe  jmp     loc_180010574
0x180010603  lea     rcx, [rbp+30h+hstringHeader]
0x180010607  call    ??$make_shared@VCSpTokenFileManager@@$$V@std@@YA?AV?$shared_ptr@VCSpTokenFileManager@@@0@XZ; std::make_shared<CSpTokenFileManager,>(void)
0x18001060c  nop
0x18001060d  mov     r14, qword ptr [rbp+30h+hstringHeader.Reserved]
0x180010611  mov     rcx, r14; this
0x180010614  call    ?Initialize@CSpTokenFileManager@@QEAAJXZ; CSpTokenFileManager::Initialize(void)
0x180010619  mov     edi, eax
0x18001061b  test    eax, eax
0x18001061d  jns     short loc_180010660
0x18001061f  mov     rcx, [rbp+38h]; this
0x180010623  mov     r9d, eax; char *
0x180010626  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x18001062d  mov     edx, 39h ; '9'; void *
0x180010632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010637  nop
0x180010638  mov     rcx, qword ptr [rbp+30h+hstringHeader.Reserved+8]; this
0x18001063c  test    rcx, rcx
0x18001063f  jz      short loc_180010647
0x180010641  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010646  nop
0x180010647  mov     rcx, [rsp+130h+hKey]; hKey
0x18001064c  test    rcx, rcx
0x18001064f  jz      loc_180010747
0x180010655  call    cs:__imp_RegCloseKey
0x18001065b  jmp     loc_180010747
0x180010660  lea     rdx, [rbp+30h+Buf1]; unsigned __int8 *
0x180010664  mov     rcx, rsi; this
0x180010667  call    ?GetExistingFileTimeHash@CSpRegistryIsolator@@AEAAJPEAE@Z; CSpRegistryIsolator::GetExistingFileTimeHash(uchar *)
0x18001066c  test    eax, eax
0x18001066e  js      short loc_180010687
0x180010670  lea     rdx, [r14+18h]; Buf2
0x180010674  mov     r8d, 20h ; ' '; Size
0x18001067a  lea     rcx, [rbp+30h+Buf1]; Buf1
0x18001067e  call    memcmp_0
0x180010683  test    eax, eax
0x180010685  jz      short loc_1800106A2
0x180010687  mov     rdx, [r15]; HKEY
0x18001068a  mov     rcx, r14; this
0x18001068d  call    ?Load@CSpTokenFileManager@@QEAAJPEAUHKEY__@@@Z; CSpTokenFileManager::Load(HKEY__ *)
0x180010692  mov     edi, eax
0x180010694  test    eax, eax
0x180010696  jns     short loc_1800106A2
0x180010698  mov     r9d, eax
0x18001069b  mov     edx, 40h ; '@'
0x1800106a0  jmp     short loc_18001071C
0x1800106a2  lea     rax, aHkeyClassesRoo_0; "HKEY_CLASSES_ROOT"
0x1800106a9  mov     [rsp+130h+Src], rax
0x1800106ae  mov     [rsp+130h+var_B8], 0FFFFFFFF80000000h
0x1800106b7  lea     rax, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE"
0x1800106be  mov     [rbp+30h+var_B0], rax
0x1800106c2  mov     [rbp+30h+var_A8], 0FFFFFFFF80000002h
0x1800106ca  lea     rax, aHkeyCurrentUse_2; "HKEY_CURRENT_USER"
0x1800106d1  mov     [rbp+30h+var_A0], rax
0x1800106d5  mov     [rbp+30h+var_98], 0FFFFFFFF80000001h
0x1800106dd  lea     rax, aHkeyCurrentCon_0; "HKEY_CURRENT_CONFIG"
0x1800106e4  mov     [rbp+30h+var_90], rax
0x1800106e8  mov     [rbp+30h+var_88], 0FFFFFFFF80000005h
0x1800106f0  mov     qword ptr [rsi+8], 4
0x1800106f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800106ff  mov     ecx, 40h ; '@'; unsigned __int64
0x180010704  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010709  mov     [rsi], rax
0x18001070c  test    rax, rax
0x18001070f  jnz     short loc_180010766
0x180010711  mov     edi, 8007000Eh
0x180010716  mov     r9d, edi; char *
0x180010719  lea     edx, [rax+4Fh]; void *
0x18001071c  lea     r8, aOnecoreuapEndu_24; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180010723  mov     rcx, [rbp+38h]; this
0x180010727  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001072c  nop
0x18001072d  mov     rcx, qword ptr [rbp+30h+hstringHeader.Reserved+8]; this
0x180010731  test    rcx, rcx
0x180010734  jz      short loc_18001073C
0x180010736  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001073b  nop
0x18001073c  lea     rcx, [rsp+130h+hKey]
0x180010741  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010746  nop
0x180010747  mov     rcx, [rsp+130h+newString]; string
0x18001074c  call    cs:__imp_WindowsDeleteString
0x180010752  mov     [rsp+130h+newString], r12
0x180010757  mov     rcx, [rsp+130h+string2]; string
0x18001075c  call    cs:__imp_WindowsDeleteString
0x180010762  mov     eax, edi
0x180010764  jmp     short loc_1800107B3
0x180010766  mov     r8, [rsi+8]
0x18001076a  shl     r8, 4; Size
0x18001076e  lea     rdx, [rsp+130h+Src]; Src
0x180010773  mov     rcx, rax; void *
0x180010776  call    memcpy_0
0x18001077b  nop
0x18001077c  mov     rcx, qword ptr [rbp+30h+hstringHeader.Reserved+8]; this
0x180010780  test    rcx, rcx
0x180010783  jz      short loc_18001078B
0x180010785  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001078a  nop
0x18001078b  lea     rcx, [rsp+130h+hKey]
0x180010790  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010795  nop
0x180010796  mov     rcx, [rsp+130h+newString]; string
0x18001079b  call    cs:__imp_WindowsDeleteString
0x1800107a1  mov     [rsp+130h+newString], r12
0x1800107a6  mov     rcx, [rsp+130h+string2]; string
0x1800107ab  call    cs:__imp_WindowsDeleteString
0x1800107b1  xor     eax, eax
0x1800107b3  mov     rcx, [rbp+30h+var_40]
0x1800107b7  xor     rcx, rsp; StackCookie
0x1800107ba  call    __security_check_cookie
0x1800107bf  add     rsp, 108h
0x1800107c6  pop     r15
0x1800107c8  pop     r14
0x1800107ca  pop     r12
0x1800107cc  pop     rdi
0x1800107cd  pop     rsi
0x1800107ce  pop     rbp
0x1800107cf  retn
```
