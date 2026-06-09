# Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(HSTRING__ *,HSTRING__ *,Windows::Internal::String &)

- ea: `0x18004132c`
- end: `0x18004176a`
- name: `?MapAliasesToPluginId@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@0AEAVString@56@@Z`
- size: `1086`
- prototype: `__int64 __fastcall(HSTRING string1, HSTRING, struct Windows::Internal::String *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028290`
- `0x18006e4c4`
- `0x1800889b0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18004132c`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180041655`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180041655`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800413a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800416db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800413a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800416db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800413b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800413f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800413b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800413f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800416fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800416fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800416ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800416ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041645`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800416c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800415e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041611`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800416c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180041559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180041559`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004159c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800415d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004159c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800415d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041431`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041431`

## string_xrefs

- `0x1800413ee`: `Windows.Foundation.Uri`
- `0x1800415f5`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`
- `0x180041753`: `onecore\ds\security\tokenbroker\pluginmgr\lib\pluginmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::PluginManager::MapAliasesToPluginId(
        HSTRING string1,
        HSTRING a2,
        HSTRING *a3)
{
  HSTRING v3; // r12
  HSTRING v5; // rbx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rsi
  char v8; // r14
  HSTRING v9; // rsi
  __int64 v10; // r15
  int (__fastcall *v11)(__int64, HSTRING, __int64 *); // r12
  __int64 v12; // rcx
  __int64 v13; // rcx
  HSTRING v14; // rcx
  __int64 v15; // rcx
  HRESULT v16; // edi
  HSTRING *v17; // rsi
  __int64 v18; // rdx
  PCWSTR StringRawBuffer; // rax
  HRESULT v21; // eax
  int v22; // [rsp+20h] [rbp-69h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-61h] BYREF
  __int64 v24; // [rsp+30h] [rbp-59h] BYREF
  __int64 v25; // [rsp+38h] [rbp-51h] BYREF
  INT32 result; // [rsp+40h] [rbp-49h] BYREF
  HSTRING v27; // [rsp+48h] [rbp-41h]
  HSTRING *v28; // [rsp+50h] [rbp-39h]
  __int64 v29; // [rsp+58h] [rbp-31h]
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-21h] BYREF
  HSTRING v32; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER v33; // [rsp+88h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v28 = a3;
  v3 = a2;
  v27 = a2;
  v5 = 0;
  v29 = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( aHttpsLoginMicr[v7] );
  v8 = 1;
  if ( v7 > 0xFFFFFFFF )
  {
    LODWORD(v7) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(L"https://login.microsoft.com", v7, &hstringHeader, &string);
  v9 = string;
  if ( !string1 )
  {
    if ( !string )
      goto LABEL_24;
LABEL_48:
    newString = 0;
    v21 = WindowsDuplicateString(string1, &newString);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
        (const char *)(unsigned int)v21,
        v22);
      return (unsigned int)v16;
    }
    v5 = newString;
    WindowsDeleteString(0);
    goto LABEL_33;
  }
  if ( !string )
    goto LABEL_48;
  v24 = 0;
  newString = 0;
  v25 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &v33, &v32) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( (int)RoGetActivationFactory(v32, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v24) < 0
    || (*(int (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v24 + 48LL))(v24, string1, &newString) < 0 )
  {
    goto LABEL_52;
  }
  v10 = v24;
  v11 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v24 + 48LL);
  v12 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v11(v10, v9, &v25) < 0 )
  {
LABEL_52:
    result = 0;
    if ( WindowsCompareStringOrdinal(string1, v9, &result) < 0 || result )
      v8 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&newString);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  }
  else
  {
    LOBYTE(v22) = 0;
    if ( (*(int (__fastcall **)(HSTRING, __int64, int *))(*(_QWORD *)newString + 168LL))(newString, v25, &v22) < 0
      || !(_BYTE)v22 )
    {
      v8 = 0;
    }
    v13 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v14 = newString;
    if ( newString )
    {
      newString = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  if ( !v8 )
    goto LABEL_48;
  v3 = v27;
LABEL_24:
  if ( !WindowsIsStringEmpty(v3) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v3, 0);
    if ( (unsigned int)_o__wcsicmp(StringRawBuffer, L"consumers") )
    {
      if ( !L"https://login.windows.net" )
      {
        v16 = -2147467261;
LABEL_37:
        v18 = 127;
        goto LABEL_38;
      }
      newString = 0;
      do
        ++v6;
      while ( aHttpsLoginWind_0[v6] );
      if ( v6 <= 0xFFFFFFFF )
      {
        v16 = WindowsCreateString(L"https://login.windows.net", v6, &newString);
        if ( v16 >= 0 )
        {
          v5 = newString;
          WindowsDeleteString(0);
        }
      }
      else
      {
        v16 = -2147024362;
      }
      if ( v16 < 0 )
        goto LABEL_37;
LABEL_33:
      v17 = v28;
      WindowsDeleteString(*v28);
      *v17 = v5;
      return (unsigned int)v16;
    }
  }
  if ( L"https://login.live.com" )
  {
    newString = 0;
    do
      ++v6;
    while ( aHttpsLoginLive[v6] );
    if ( v6 <= 0xFFFFFFFF )
    {
      v16 = WindowsCreateString(L"https://login.live.com", v6, &newString);
      if ( v16 >= 0 )
      {
        v5 = newString;
        WindowsDeleteString(0);
      }
    }
    else
    {
      v16 = -2147024362;
    }
    if ( v16 >= 0 )
      goto LABEL_33;
  }
  else
  {
    v16 = -2147467261;
  }
  v18 = 123;
LABEL_38:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\pluginmgr\\lib\\pluginmgr.cpp",
    (const char *)(unsigned int)v16,
    v22);
  if ( v5 )
    WindowsDeleteString(v5);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18004132c  mov     [rsp-8+arg_8], rbx
0x180041331  push    rbp
0x180041332  push    rsi
0x180041333  push    rdi
0x180041334  push    r12
0x180041336  push    r13
0x180041338  push    r14
0x18004133a  push    r15
0x18004133c  lea     rbp, [rsp-27h]
0x180041341  sub     rsp, 0B0h
0x180041348  mov     rax, cs:__security_cookie
0x18004134f  xor     rax, rsp
0x180041352  mov     [rbp+57h+var_40], rax
0x180041356  mov     [rbp+57h+var_90], r8
0x18004135a  mov     r12, rdx
0x18004135d  mov     [rbp+57h+var_98], rdx
0x180041361  mov     r13, rcx
0x180041364  xor     eax, eax
0x180041366  mov     ebx, eax
0x180041368  mov     [rbp+57h+var_88], rax
0x18004136c  mov     r15, cs:off_18011D6C0; "https://login.microsoft.com"
0x180041373  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041377  mov     rsi, rdi
0x18004137a  inc     rsi
0x18004137d  cmp     [r15+rsi*2], ax
0x180041382  jnz     short loc_18004137A
0x180041384  mov     eax, 0FFFFFFFFh
0x180041389  mov     r14d, 1
0x18004138f  cmp     rsi, rax
0x180041392  jbe     short loc_1800413AA
0x180041394  mov     esi, eax
0x180041396  xor     r9d, r9d; lpArguments
0x180041399  xor     r8d, r8d; nNumberOfArguments
0x18004139c  mov     edx, r14d; dwExceptionFlags
0x18004139f  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800413a4  call    cs:__imp_RaiseException
0x1800413aa  lea     r9, [rbp+57h+string]; string
0x1800413ae  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800413b2  mov     edx, esi; length
0x1800413b4  mov     rcx, r15; sourceString
0x1800413b7  call    cs:__imp_WindowsCreateStringReference
0x1800413bd  mov     rsi, [rbp+57h+string]
0x1800413c1  xor     r15d, r15d
0x1800413c4  test    r13, r13
0x1800413c7  jz      loc_1800416E6
0x1800413cd  test    rsi, rsi
0x1800413d0  jz      loc_1800416A1
0x1800413d6  mov     [rbp+57h+var_B0], r15
0x1800413da  mov     [rbp+57h+newString], r15
0x1800413de  mov     [rbp+57h+var_A8], r15
0x1800413e2  lea     r9, [rbp+57h+var_60]; string
0x1800413e6  lea     r8, [rbp+57h+var_58]; hstringHeader
0x1800413ea  lea     edx, [r15+16h]; length
0x1800413ee  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800413f5  call    cs:__imp_WindowsCreateStringReference
0x1800413fb  test    eax, eax
0x1800413fd  js      loc_1800416CD
0x180041403  mov     r15, [rbp+57h+var_60]
0x180041407  mov     rcx, [rbp+57h+var_B0]
0x18004140b  xor     eax, eax
0x18004140d  test    rcx, rcx
0x180041410  jz      short loc_180041423
0x180041412  mov     [rbp+57h+var_B0], rax
0x180041416  mov     rax, [rcx]
0x180041419  mov     rax, [rax+10h]
0x18004141d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041422  nop
0x180041423  lea     r8, [rbp+57h+var_B0]
0x180041427  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18004142e  mov     rcx, r15
0x180041431  call    cs:__imp_RoGetActivationFactory
0x180041437  xor     r15d, r15d
0x18004143a  test    eax, eax
0x18004143c  js      loc_1800416F0
0x180041442  mov     r15, [rbp+57h+var_B0]
0x180041446  mov     rax, [r15]
0x180041449  mov     r12, [rax+30h]
0x18004144d  mov     rcx, [rbp+57h+newString]
0x180041451  xor     eax, eax
0x180041453  test    rcx, rcx
0x180041456  jz      short loc_180041469
0x180041458  mov     [rbp+57h+newString], rax
0x18004145c  mov     rdx, [rcx]
0x18004145f  mov     rax, [rdx+10h]
0x180041463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041468  nop
0x180041469  lea     r8, [rbp+57h+newString]
0x18004146d  mov     rdx, r13
0x180041470  mov     rcx, r15
0x180041473  mov     rax, r12
0x180041476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004147b  xor     r15d, r15d
0x18004147e  test    eax, eax
0x180041480  js      loc_1800416F0
0x180041486  mov     r15, [rbp+57h+var_B0]
0x18004148a  mov     rax, [r15]
0x18004148d  mov     r12, [rax+30h]
0x180041491  mov     rcx, [rbp+57h+var_A8]
0x180041495  xor     eax, eax
0x180041497  test    rcx, rcx
0x18004149a  jz      short loc_1800414AD
0x18004149c  mov     [rbp+57h+var_A8], rax
0x1800414a0  mov     rdx, [rcx]
0x1800414a3  mov     rax, [rdx+10h]
0x1800414a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414ac  nop
0x1800414ad  lea     r8, [rbp+57h+var_A8]
0x1800414b1  mov     rdx, rsi
0x1800414b4  mov     rcx, r15
0x1800414b7  mov     rax, r12
0x1800414ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414bf  xor     r15d, r15d
0x1800414c2  test    eax, eax
0x1800414c4  js      loc_1800416F0
0x1800414ca  mov     byte ptr [rbp+57h+var_C0], r15b
0x1800414ce  mov     rcx, [rbp+57h+newString]
0x1800414d2  mov     rax, [rcx]
0x1800414d5  lea     r8, [rbp+57h+var_C0]
0x1800414d9  mov     rdx, [rbp+57h+var_A8]
0x1800414dd  mov     rax, [rax+0A8h]
0x1800414e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414e9  test    eax, eax
0x1800414eb  js      loc_180041699
0x1800414f1  cmp     byte ptr [rbp+57h+var_C0], r15b
0x1800414f5  jz      loc_180041699
0x1800414fb  mov     rcx, [rbp+57h+var_A8]
0x1800414ff  test    rcx, rcx
0x180041502  jz      short loc_180041515
0x180041504  mov     [rbp+57h+var_A8], r15
0x180041508  mov     rax, [rcx]
0x18004150b  mov     rax, [rax+10h]
0x18004150f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041514  nop
0x180041515  mov     rcx, [rbp+57h+newString]
0x180041519  test    rcx, rcx
0x18004151c  jz      short loc_18004152F
0x18004151e  mov     [rbp+57h+newString], r15
0x180041522  mov     rax, [rcx]
0x180041525  mov     rax, [rax+10h]
0x180041529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004152e  nop
0x18004152f  mov     rcx, [rbp+57h+var_B0]
0x180041533  test    rcx, rcx
0x180041536  jz      short loc_180041549
0x180041538  mov     [rbp+57h+var_B0], r15
0x18004153c  mov     rax, [rcx]
0x18004153f  mov     rax, [rax+10h]
0x180041543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041548  nop
0x180041549  test    r14b, r14b
0x18004154c  jz      loc_1800416A1
0x180041552  mov     r12, [rbp+57h+var_98]
0x180041556  mov     rcx, r12; string
0x180041559  call    cs:__imp_WindowsIsStringEmpty
0x18004155f  test    eax, eax
0x180041561  jz      loc_180041640
0x180041567  mov     rcx, cs:off_18011D6B8; sourceString
0x18004156e  test    rcx, rcx
0x180041571  jz      loc_18004173D
0x180041577  mov     [rbp+57h+newString], r15
0x18004157b  inc     rdi
0x18004157e  cmp     [rcx+rdi*2], r15w
0x180041583  jnz     short loc_18004157B
0x180041585  mov     eax, 0FFFFFFFFh
0x18004158a  cmp     rdi, rax
0x18004158d  jbe     short loc_180041596
0x18004158f  mov     edi, 80070216h
0x180041594  jmp     short loc_1800415B4
0x180041596  mov     edx, edi; length
0x180041598  lea     r8, [rbp+57h+newString]; string
0x18004159c  call    cs:__imp_WindowsCreateString
0x1800415a2  mov     edi, eax
0x1800415a4  test    eax, eax
0x1800415a6  js      short loc_1800415B4
0x1800415a8  mov     rbx, [rbp+57h+newString]
0x1800415ac  xor     ecx, ecx; string
0x1800415ae  call    cs:__imp_WindowsDeleteString
0x1800415b4  test    edi, edi
0x1800415b6  js      loc_180041742
0x1800415bc  mov     rsi, [rbp+57h+var_90]
0x1800415c0  mov     rcx, [rsi]; string
0x1800415c3  call    cs:__imp_WindowsDeleteString
0x1800415c9  mov     [rsi], rbx
0x1800415cc  jmp     short loc_180041617
0x1800415ce  mov     edx, edi; length
0x1800415d0  lea     r8, [rbp+57h+newString]; string
0x1800415d4  call    cs:__imp_WindowsCreateString
0x1800415da  mov     edi, eax
0x1800415dc  test    eax, eax
0x1800415de  js      short loc_1800415EC
0x1800415e0  mov     rbx, [rbp+57h+newString]
0x1800415e4  xor     ecx, ecx; string
0x1800415e6  call    cs:__imp_WindowsDeleteString
0x1800415ec  test    edi, edi
0x1800415ee  jns     short loc_1800415BC
0x1800415f0  mov     edx, 7Fh; void *
0x1800415f5  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\tokenbroker\\plu"...
0x1800415fc  mov     r9d, edi; char *
0x1800415ff  mov     rcx, [rbp+5Fh]; this
0x180041603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041608  nop
0x180041609  test    rbx, rbx
0x18004160c  jz      short loc_180041617
0x18004160e  mov     rcx, rbx; string
0x180041611  call    cs:__imp_WindowsDeleteString
0x180041617  mov     eax, edi
0x180041619  mov     rcx, [rbp+57h+var_40]
0x18004161d  xor     rcx, rsp; StackCookie
0x180041620  call    __security_check_cookie
0x180041625  mov     rbx, [rsp+0E0h+arg_8]
0x18004162d  add     rsp, 0B0h
0x180041634  pop     r15
0x180041636  pop     r14
0x180041638  pop     r13
0x18004163a  pop     r12
0x18004163c  pop     rdi
0x18004163d  pop     rsi
0x18004163e  pop     rbp
0x18004163f  retn
0x180041640  xor     edx, edx; length
0x180041642  mov     rcx, r12; string
0x180041645  call    cs:__imp_WindowsGetStringRawBuffer
0x18004164b  lea     rdx, aConsumers; "consumers"
0x180041652  mov     rcx, rax
0x180041655  call    cs:__imp__o__wcsicmp
0x18004165b  test    eax, eax
0x18004165d  jz      loc_180041567
0x180041663  mov     rcx, cs:off_18011D600; sourceString
0x18004166a  test    rcx, rcx
0x18004166d  jz      loc_180041733
0x180041673  mov     [rbp+57h+newString], r15
0x180041677  inc     rdi
0x18004167a  cmp     [rcx+rdi*2], r15w
0x18004167f  jnz     short loc_180041677
0x180041681  mov     eax, 0FFFFFFFFh
0x180041686  cmp     rdi, rax
0x180041689  jbe     loc_1800415CE
0x18004168f  mov     edi, 80070216h
0x180041694  jmp     loc_1800415EC
0x180041699  mov     r14b, r15b
0x18004169c  jmp     loc_1800414FB
0x1800416a1  mov     [rbp+57h+newString], r15
0x1800416a5  lea     rdx, [rbp+57h+newString]; newString
0x1800416a9  mov     rcx, r13; string
0x1800416ac  call    cs:__imp_WindowsDuplicateString
0x1800416b2  mov     edi, eax
0x1800416b4  test    eax, eax
0x1800416b6  js      loc_18004174C
0x1800416bc  mov     rbx, [rbp+57h+newString]
0x1800416c0  xor     ecx, ecx; string
0x1800416c2  call    cs:__imp_WindowsDeleteString
0x1800416c8  jmp     loc_1800415BC
0x1800416cd  xor     r9d, r9d; lpArguments
0x1800416d0  xor     r8d, r8d; nNumberOfArguments
0x1800416d3  mov     edx, r14d; dwExceptionFlags
0x1800416d6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800416db  call    cs:__imp_RaiseException
0x1800416e1  jmp     loc_180041403
0x1800416e6  test    rsi, rsi
0x1800416e9  jnz     short loc_1800416A1
0x1800416eb  jmp     loc_180041556
0x1800416f0  mov     [rbp+57h+result], r15d
0x1800416f4  lea     r8, [rbp+57h+result]; result
0x1800416f8  mov     rdx, rsi; string2
0x1800416fb  mov     rcx, r13; string1
0x1800416fe  call    cs:__imp_WindowsCompareStringOrdinal
0x180041704  test    eax, eax
0x180041706  js      short loc_18004170E
0x180041708  cmp     [rbp+57h+result], r15d
0x18004170c  jz      short loc_180041711
0x18004170e  mov     r14b, r15b
0x180041711  lea     rcx, [rbp+57h+var_A8]
0x180041715  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004171a  nop
0x18004171b  lea     rcx, [rbp+57h+newString]
0x18004171f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041724  nop
0x180041725  lea     rcx, [rbp+57h+var_B0]
0x180041729  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004172e  jmp     loc_180041549
0x180041733  mov     edi, 80004003h
0x180041738  jmp     loc_1800415F0
0x18004173d  mov     edi, 80004003h
0x180041742  mov     edx, 7Bh ; '{'
0x180041747  jmp     loc_1800415F5
0x18004174c  mov     rcx, [rbp+5Fh]; this
0x180041750  mov     r9d, eax; char *
0x180041753  lea     r8, aOnecoreDsSecur_45; "onecore\\ds\\security\\tokenbroker\\plu"...
0x18004175a  mov     edx, 84h; void *
0x18004175f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041764  jmp     loc_1800415CC
```
