# Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::String &,Windows::Internal::String &,Windows::Internal::String &)

- ea: `0x180031cf8`
- end: `0x180032393`
- name: `?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@AEAVString@56@11@Z`
- size: `1691`
- prototype: `__int64 __fastcall(struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Internal::String *, struct Windows::Internal::String *, struct Windows::Internal::String *)`
- caller_count: `8`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800262f0`
- `0x180063ff0`
- `0x180070660`
- `0x180083a54`
- `0x1800dae5c`
- `0x1800db234`
- `0x1800e4294`
- `0x180109a4c`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180031cf8`
- `0x1800337b0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032110`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180032110`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031e15`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800322f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031e15`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800322f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031e28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031e28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180032343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180032343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800322bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800322bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180032100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180032100`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003203c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003204c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003205a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003206a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800320c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800320d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032171`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032290`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800322a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003203c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003204c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003205a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003206a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800320c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800320d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032171`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800321f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032290`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800322a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180031d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180031fe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180031d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180031fe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032029`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003215e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032029`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003215e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031ea9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180031ea9`

## string_xrefs

- `0x180031e61`: `Windows.Foundation.Uri`
- `0x180032184`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x1800321ad`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x1800321db`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x18003221c`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x180032253`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x180032302`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
        __int64 (__fastcall ***a1)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        HSTRING *a2,
        HSTRING *a3,
        HSTRING *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 (__fastcall *v7)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rbx
  int v8; // eax
  int v9; // eax
  HSTRING v10; // r13
  HSTRING v11; // rbx
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rsi
  char v14; // r15
  HSTRING v15; // rsi
  HSTRING v16; // r12
  __int64 v17; // rcx
  __int64 v18; // r12
  int (__fastcall *v19)(__int64, HSTRING, __int64 *); // r13
  __int64 v20; // rcx
  __int64 v21; // r12
  int (__fastcall *v22)(__int64, HSTRING, __int64 *); // r13
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  HSTRING v27; // rsi
  HRESULT v28; // esi
  HSTRING *v29; // rdi
  HSTRING *v30; // rbx
  HSTRING *v31; // rbx
  HSTRING v32; // rcx
  __int64 v33; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v36; // rdx
  HSTRING v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  HRESULT v40; // eax
  int v41; // eax
  int v42; // [rsp+20h] [rbp-A9h] BYREF
  HSTRING string; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v44; // [rsp+30h] [rbp-99h] BYREF
  HSTRING v45; // [rsp+38h] [rbp-91h] BYREF
  HSTRING v46; // [rsp+40h] [rbp-89h] BYREF
  __int64 v47; // [rsp+48h] [rbp-81h] BYREF
  __int64 v48; // [rsp+50h] [rbp-79h] BYREF
  __int64 v49; // [rsp+58h] [rbp-71h] BYREF
  HSTRING newString; // [rsp+60h] [rbp-69h] BYREF
  INT32 result; // [rsp+68h] [rbp-61h] BYREF
  HSTRING v52; // [rsp+70h] [rbp-59h]
  HSTRING *v53; // [rsp+78h] [rbp-51h]
  HSTRING *v54; // [rsp+80h] [rbp-49h]
  HSTRING *v55; // [rsp+88h] [rbp-41h]
  __int64 v56; // [rsp+90h] [rbp-39h]
  HSTRING string2; // [rsp+98h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-29h] BYREF
  HSTRING v59; // [rsp+B8h] [rbp-11h] BYREF
  HSTRING_HEADER v60; // [rsp+C0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v53 = a4;
  v55 = a3;
  v54 = a2;
  string = 0;
  v45 = 0;
  v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *), HSTRING *))(*a1)[6])(
         a1,
         &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
      (const char *)(unsigned int)v5,
      v42);
LABEL_64:
    if ( v45 )
      WindowsDeleteString(v45);
    if ( string )
      WindowsDeleteString(string);
    return v6;
  }
  if ( !WindowsIsStringEmpty(string) )
  {
    v44 = 0;
    v7 = **a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    v8 = v7(
           (struct Windows::Security::Credentials::IWebAccountProvider *)a1,
           &GUID_4a01eb05_4e42_41d4_b518_e008a5163614,
           &v44);
    v6 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
        (const char *)(unsigned int)v8,
        v42);
      v38 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      }
    }
    else
    {
      v9 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 56LL))(v44, &v45);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v56 = 0;
        v52 = v45;
        v10 = string;
        newString = string;
        v11 = 0;
        v46 = 0;
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( aHttpsLoginMicr[v13] );
        v14 = 1;
        if ( v13 > 0xFFFFFFFF )
        {
          LODWORD(v13) = -1;
          RaiseException(0xC000000D, 1u, 0, 0);
        }
        WindowsCreateStringReference(L"https://login.microsoft.com", v13, &hstringHeader, &string2);
        v15 = string2;
        if ( !v10 )
        {
          if ( !string2 )
          {
LABEL_32:
            v27 = v52;
            if ( WindowsIsStringEmpty(v52)
              || (StringRawBuffer = WindowsGetStringRawBuffer(v27, 0),
                  !(unsigned int)_o__wcsicmp(StringRawBuffer, L"consumers")) )
            {
              if ( L"https://login.live.com" )
              {
                v46 = 0;
                do
                  ++v12;
                while ( aHttpsLoginLive[v12] );
                if ( v12 <= 0xFFFFFFFF )
                {
                  v28 = WindowsCreateString(L"https://login.live.com", v12, &v46);
                  if ( v28 >= 0 )
                  {
                    v11 = v46;
                    WindowsDeleteString(0);
                  }
                }
                else
                {
                  v28 = -2147024362;
                }
                if ( v28 >= 0 )
                  goto LABEL_41;
              }
              else
              {
                v28 = -2147467261;
              }
              v36 = 123;
              goto LABEL_59;
            }
            if ( !L"https://login.windows.net" )
            {
              v28 = -2147467261;
LABEL_58:
              v36 = 127;
LABEL_59:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v36,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
                (const char *)(unsigned int)v28,
                v42);
              if ( !v11 )
              {
LABEL_62:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xAE,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
                  (const char *)(unsigned int)v28,
                  v42);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                v32 = v45;
LABEL_43:
                if ( v32 )
                  WindowsDeleteString(v32);
                if ( string )
                  WindowsDeleteString(string);
                return (unsigned int)v28;
              }
              v37 = v11;
LABEL_61:
              WindowsDeleteString(v37);
              goto LABEL_62;
            }
            v46 = 0;
            do
              ++v12;
            while ( aHttpsLoginWind_0[v12] );
            if ( v12 <= 0xFFFFFFFF )
            {
              v28 = WindowsCreateString(L"https://login.windows.net", v12, &v46);
              if ( v28 >= 0 )
              {
                v11 = v46;
                WindowsDeleteString(0);
              }
            }
            else
            {
              v28 = -2147024362;
            }
            if ( v28 < 0 )
              goto LABEL_58;
LABEL_41:
            WindowsDeleteString(0);
            v29 = v53;
            WindowsDeleteString(*v53);
            *v29 = v11;
            v30 = v54;
            WindowsDeleteString(*v54);
            *v30 = string;
            string = 0;
            v31 = v55;
            WindowsDeleteString(*v55);
            *v31 = v45;
            v32 = 0;
            v45 = 0;
            v33 = v44;
            if ( v44 )
            {
              v44 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              v32 = v45;
            }
            goto LABEL_43;
          }
LABEL_80:
          newString = 0;
          v40 = WindowsDuplicateString(v10, &newString);
          v41 = Windows::Internal::String::FreeAndAssignOnSuccess(v40, newString, &v46);
          v28 = v41;
          if ( v41 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x84,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
              (const char *)(unsigned int)v41,
              v42);
            v37 = v46;
            if ( !v46 )
              goto LABEL_62;
            goto LABEL_61;
          }
          v11 = v46;
          goto LABEL_41;
        }
        if ( !string2 )
          goto LABEL_80;
        v47 = 0;
        v49 = 0;
        v48 = 0;
        if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &v60, &v59) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v16 = v59;
        v17 = v47;
        if ( v47 )
        {
          v47 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        if ( (int)RoGetActivationFactory(v16, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v47) >= 0 )
        {
          v18 = v47;
          v19 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v47 + 48LL);
          v20 = v49;
          if ( v49 )
          {
            v49 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          if ( v19(v18, newString, &v49) >= 0 )
          {
            v21 = v47;
            v22 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v47 + 48LL);
            v23 = v48;
            if ( v48 )
            {
              v48 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            }
            if ( v22(v21, v15, &v48) >= 0 )
            {
              LOBYTE(v42) = 0;
              if ( (*(int (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v49 + 168LL))(v49, v48, &v42) < 0
                || !(_BYTE)v42 )
              {
                v14 = 0;
              }
              v24 = v48;
              if ( v48 )
              {
                v48 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              }
              v25 = v49;
              if ( v49 )
              {
                v49 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              }
              v26 = v47;
              if ( v47 )
              {
                v47 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              v10 = newString;
              goto LABEL_31;
            }
          }
          v10 = newString;
        }
        result = 0;
        if ( WindowsCompareStringOrdinal(v10, v15, &result) < 0 || result )
          v14 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
LABEL_31:
        if ( v14 )
          goto LABEL_32;
        goto LABEL_80;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
        (const char *)(unsigned int)v9,
        v42);
      v39 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      }
    }
    goto LABEL_64;
  }
  if ( v45 )
    WindowsDeleteString(v45);
  if ( string )
    WindowsDeleteString(string);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180031cf8  push    rbp
0x180031cfa  push    rbx
0x180031cfb  push    rsi
0x180031cfc  push    rdi
0x180031cfd  push    r12
0x180031cff  push    r13
0x180031d01  push    r14
0x180031d03  push    r15
0x180031d05  lea     rbp, [rsp-1Fh]
0x180031d0a  sub     rsp, 0E8h
0x180031d11  mov     rax, cs:__security_cookie
0x180031d18  xor     rax, rsp
0x180031d1b  mov     [rbp+57h+var_48], rax
0x180031d1f  mov     [rbp+57h+var_A8], r9
0x180031d23  mov     [rbp+57h+var_98], r8
0x180031d27  mov     [rbp+57h+var_A0], rdx
0x180031d2b  mov     rdi, rcx
0x180031d2e  xor     r15d, r15d
0x180031d31  mov     [rsp+120h+string], r15
0x180031d36  mov     [rsp+120h+var_E8], r15
0x180031d3b  mov     rax, [rcx]
0x180031d3e  lea     rdx, [rsp+120h+string]
0x180031d43  mov     rax, [rax+30h]
0x180031d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d4c  mov     ebx, eax
0x180031d4e  test    eax, eax
0x180031d50  js      loc_1800321D4
0x180031d56  mov     rcx, [rsp+120h+string]; string
0x180031d5b  call    cs:__imp_WindowsIsStringEmpty
0x180031d61  test    eax, eax
0x180031d63  jnz     loc_180032286
0x180031d69  mov     [rsp+120h+var_F0], r15
0x180031d6e  mov     rax, [rdi]
0x180031d71  mov     rbx, [rax]
0x180031d74  lea     rcx, [rsp+120h+var_F0]
0x180031d79  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180031d7e  lea     r8, [rsp+120h+var_F0]
0x180031d83  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x180031d8a  mov     rcx, rdi
0x180031d8d  mov     rax, rbx
0x180031d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d95  mov     ebx, eax
0x180031d97  test    eax, eax
0x180031d99  js      loc_180032215
0x180031d9f  mov     rcx, [rsp+120h+var_F0]
0x180031da4  mov     rax, [rcx]
0x180031da7  lea     rdx, [rsp+120h+var_E8]
0x180031dac  mov     rax, [rax+38h]
0x180031db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031db5  mov     ebx, eax
0x180031db7  test    eax, eax
0x180031db9  js      loc_18003224C
0x180031dbf  mov     [rbp+57h+var_90], r15
0x180031dc3  mov     rax, [rsp+120h+var_E8]
0x180031dc8  mov     [rbp+57h+var_B0], rax
0x180031dcc  mov     r13, [rsp+120h+string]
0x180031dd1  mov     [rbp+57h+newString], r13
0x180031dd5  mov     ebx, r15d
0x180031dd8  mov     [rsp+120h+var_E0], rbx
0x180031ddd  mov     r12, cs:off_18011D6C0; "https://login.microsoft.com"
0x180031de4  or      r14, 0FFFFFFFFFFFFFFFFh
0x180031de8  mov     rsi, r14
0x180031deb  inc     rsi
0x180031dee  cmp     [r12+rsi*2], r15w
0x180031df3  jnz     short loc_180031DEB
0x180031df5  mov     eax, 0FFFFFFFFh
0x180031dfa  mov     r15d, 1
0x180031e00  cmp     rsi, rax
0x180031e03  jbe     short loc_180031E1B
0x180031e05  mov     esi, eax
0x180031e07  xor     r9d, r9d; lpArguments
0x180031e0a  xor     r8d, r8d; nNumberOfArguments
0x180031e0d  mov     edx, r15d; dwExceptionFlags
0x180031e10  mov     ecx, 0C000000Dh; dwExceptionCode
0x180031e15  call    cs:__imp_RaiseException
0x180031e1b  lea     r9, [rbp+57h+string2]; string
0x180031e1f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180031e23  mov     edx, esi; length
0x180031e25  mov     rcx, r12; sourceString
0x180031e28  call    cs:__imp_WindowsCreateStringReference
0x180031e2e  mov     rsi, [rbp+57h+string2]
0x180031e32  xor     r12d, r12d
0x180031e35  test    r13, r13
0x180031e38  jz      loc_180032327
0x180031e3e  test    rsi, rsi
0x180031e41  jz      loc_1800322B1
0x180031e47  mov     [rsp+120h+var_D8], r12
0x180031e4c  mov     [rbp+57h+var_C8], r12
0x180031e50  mov     [rbp+57h+var_D0], r12
0x180031e54  lea     r9, [rbp+57h+var_68]; string
0x180031e58  lea     r8, [rbp+57h+var_60]; hstringHeader
0x180031e5c  lea     edx, [r12+16h]; length
0x180031e61  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180031e68  call    cs:__imp_WindowsCreateStringReference
0x180031e6e  test    eax, eax
0x180031e70  js      loc_1800322E2
0x180031e76  mov     r12, [rbp+57h+var_68]
0x180031e7a  mov     rcx, [rsp+120h+var_D8]
0x180031e7f  test    rcx, rcx
0x180031e82  jz      short loc_180031E9A
0x180031e84  mov     [rsp+120h+var_D8], 0
0x180031e8d  mov     rax, [rcx]
0x180031e90  mov     rax, [rax+10h]
0x180031e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e99  nop
0x180031e9a  lea     r8, [rsp+120h+var_D8]
0x180031e9f  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x180031ea6  mov     rcx, r12
0x180031ea9  call    cs:__imp_RoGetActivationFactory
0x180031eaf  xor     r12d, r12d
0x180031eb2  test    eax, eax
0x180031eb4  js      loc_180032335
0x180031eba  mov     r12, [rsp+120h+var_D8]
0x180031ebf  mov     rax, [r12]
0x180031ec3  mov     r13, [rax+30h]
0x180031ec7  mov     rcx, [rbp+57h+var_C8]
0x180031ecb  test    rcx, rcx
0x180031ece  jz      short loc_180031EE5
0x180031ed0  mov     [rbp+57h+var_C8], 0
0x180031ed8  mov     rdx, [rcx]
0x180031edb  mov     rax, [rdx+10h]
0x180031edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ee4  nop
0x180031ee5  lea     r8, [rbp+57h+var_C8]
0x180031ee9  mov     rdx, [rbp+57h+newString]
0x180031eed  mov     rcx, r12
0x180031ef0  mov     rax, r13
0x180031ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ef8  xor     r12d, r12d
0x180031efb  test    eax, eax
0x180031efd  js      loc_180032331
0x180031f03  mov     r12, [rsp+120h+var_D8]
0x180031f08  mov     rax, [r12]
0x180031f0c  mov     r13, [rax+30h]
0x180031f10  mov     rcx, [rbp+57h+var_D0]
0x180031f14  test    rcx, rcx
0x180031f17  jz      short loc_180031F2E
0x180031f19  mov     [rbp+57h+var_D0], 0
0x180031f21  mov     rdx, [rcx]
0x180031f24  mov     rax, [rdx+10h]
0x180031f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f2d  nop
0x180031f2e  lea     r8, [rbp+57h+var_D0]
0x180031f32  mov     rdx, rsi
0x180031f35  mov     rcx, r12
0x180031f38  mov     rax, r13
0x180031f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f40  xor     r12d, r12d
0x180031f43  test    eax, eax
0x180031f45  js      loc_180032331
0x180031f4b  mov     byte ptr [rsp+120h+var_100], r12b; int
0x180031f50  mov     rcx, [rbp+57h+var_C8]
0x180031f54  mov     rax, [rcx]
0x180031f57  lea     r8, [rsp+120h+var_100]
0x180031f5c  mov     rdx, [rbp+57h+var_D0]
0x180031f60  mov     rax, [rax+0A8h]
0x180031f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f6c  test    eax, eax
0x180031f6e  js      loc_18003214E
0x180031f74  cmp     byte ptr [rsp+120h+var_100], r12b
0x180031f79  jz      loc_18003214E
0x180031f7f  mov     rcx, [rbp+57h+var_D0]
0x180031f83  test    rcx, rcx
0x180031f86  jz      short loc_180031F99
0x180031f88  mov     [rbp+57h+var_D0], r12
0x180031f8c  mov     rax, [rcx]
0x180031f8f  mov     rax, [rax+10h]
0x180031f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f98  nop
0x180031f99  mov     rcx, [rbp+57h+var_C8]
0x180031f9d  test    rcx, rcx
0x180031fa0  jz      short loc_180031FB3
0x180031fa2  mov     [rbp+57h+var_C8], r12
0x180031fa6  mov     rax, [rcx]
0x180031fa9  mov     rax, [rax+10h]
0x180031fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fb2  nop
0x180031fb3  mov     rcx, [rsp+120h+var_D8]
0x180031fb8  test    rcx, rcx
0x180031fbb  jz      short loc_180031FCF
0x180031fbd  mov     [rsp+120h+var_D8], r12
0x180031fc2  mov     rax, [rcx]
0x180031fc5  mov     rax, [rax+10h]
0x180031fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fce  nop
0x180031fcf  mov     r13, [rbp+57h+newString]
0x180031fd3  test    r15b, r15b
0x180031fd6  jz      loc_1800322B1
0x180031fdc  mov     rsi, [rbp+57h+var_B0]
0x180031fe0  mov     rcx, rsi; string
0x180031fe3  call    cs:__imp_WindowsIsStringEmpty
0x180031fe9  test    eax, eax
0x180031feb  jz      loc_1800320FB
0x180031ff1  mov     rcx, cs:off_18011D6B8; sourceString
0x180031ff8  test    rcx, rcx
0x180031ffb  jz      loc_180032383
0x180032001  mov     [rsp+120h+var_E0], r12
0x180032006  inc     r14
0x180032009  cmp     [rcx+r14*2], r12w
0x18003200e  jnz     short loc_180032006
0x180032010  mov     eax, 0FFFFFFFFh
0x180032015  cmp     r14, rax
0x180032018  jbe     short loc_180032021
0x18003201a  mov     esi, 80070216h
0x18003201f  jmp     short loc_180032042
0x180032021  mov     edx, r14d; length
0x180032024  lea     r8, [rsp+120h+var_E0]; string
0x180032029  call    cs:__imp_WindowsCreateString
0x18003202f  mov     esi, eax
0x180032031  test    eax, eax
0x180032033  js      short loc_180032042
0x180032035  mov     rbx, [rsp+120h+var_E0]
0x18003203a  xor     ecx, ecx; string
0x18003203c  call    cs:__imp_WindowsDeleteString
0x180032042  test    esi, esi
0x180032044  js      loc_180032388
0x18003204a  xor     ecx, ecx; string
0x18003204c  call    cs:__imp_WindowsDeleteString
0x180032052  nop
0x180032053  mov     rdi, [rbp+57h+var_A8]
0x180032057  mov     rcx, [rdi]; string
0x18003205a  call    cs:__imp_WindowsDeleteString
0x180032060  mov     [rdi], rbx
0x180032063  mov     rbx, [rbp+57h+var_A0]
0x180032067  mov     rcx, [rbx]; string
0x18003206a  call    cs:__imp_WindowsDeleteString
0x180032070  mov     rax, [rsp+120h+string]
0x180032075  mov     [rbx], rax
0x180032078  mov     [rsp+120h+string], r12
0x18003207d  mov     rbx, [rbp+57h+var_98]
0x180032081  mov     rcx, [rbx]; string
0x180032084  call    cs:__imp_WindowsDeleteString
0x18003208a  mov     rax, [rsp+120h+var_E8]
0x18003208f  mov     [rbx], rax
0x180032092  mov     rcx, r12
0x180032095  mov     [rsp+120h+var_E8], rcx
0x18003209a  mov     rdx, [rsp+120h+var_F0]
0x18003209f  test    rdx, rdx
0x1800320a2  jz      short loc_1800320BD
0x1800320a4  mov     [rsp+120h+var_F0], r12
0x1800320a9  mov     rax, [rdx]
0x1800320ac  mov     rcx, rdx
0x1800320af  mov     rax, [rax+10h]
0x1800320b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320b8  mov     rcx, [rsp+120h+var_E8]; string
0x1800320bd  test    rcx, rcx
0x1800320c0  jz      short loc_1800320C9
0x1800320c2  call    cs:__imp_WindowsDeleteString
0x1800320c8  nop
0x1800320c9  mov     rcx, [rsp+120h+string]; string
0x1800320ce  test    rcx, rcx
0x1800320d1  jz      short loc_1800320D9
0x1800320d3  call    cs:__imp_WindowsDeleteString
0x1800320d9  mov     eax, esi
0x1800320db  mov     rcx, [rbp+57h+var_48]
0x1800320df  xor     rcx, rsp; StackCookie
0x1800320e2  call    __security_check_cookie
0x1800320e7  add     rsp, 0E8h
0x1800320ee  pop     r15
0x1800320f0  pop     r14
0x1800320f2  pop     r13
0x1800320f4  pop     r12
0x1800320f6  pop     rdi
0x1800320f7  pop     rsi
0x1800320f8  pop     rbx
0x1800320f9  pop     rbp
0x1800320fa  retn
0x1800320fb  xor     edx, edx; length
0x1800320fd  mov     rcx, rsi; string
0x180032100  call    cs:__imp_WindowsGetStringRawBuffer
0x180032106  lea     rdx, aConsumers; "consumers"
0x18003210d  mov     rcx, rax
0x180032110  call    cs:__imp__o__wcsicmp
0x180032116  test    eax, eax
0x180032118  jz      loc_180031FF1
0x18003211e  mov     rcx, cs:off_18011D600; sourceString
0x180032125  test    rcx, rcx
0x180032128  jz      loc_180032379
0x18003212e  mov     [rsp+120h+var_E0], r12
0x180032133  inc     r14
0x180032136  cmp     [rcx+r14*2], r12w
0x18003213b  jnz     short loc_180032133
0x18003213d  mov     eax, 0FFFFFFFFh
0x180032142  cmp     r14, rax
0x180032145  jbe     short loc_180032156
0x180032147  mov     esi, 80070216h
0x18003214c  jmp     short loc_180032177
0x18003214e  mov     r15b, r12b
0x180032151  jmp     loc_180031F7F
0x180032156  mov     edx, r14d; length
0x180032159  lea     r8, [rsp+120h+var_E0]; string
0x18003215e  call    cs:__imp_WindowsCreateString
0x180032164  mov     esi, eax
0x180032166  test    eax, eax
0x180032168  js      short loc_180032177
0x18003216a  mov     rbx, [rsp+120h+var_E0]
0x18003216f  xor     ecx, ecx; string
0x180032171  call    cs:__imp_WindowsDeleteString
0x180032177  test    esi, esi
0x180032179  jns     loc_18003204A
  ... truncated ...
```
