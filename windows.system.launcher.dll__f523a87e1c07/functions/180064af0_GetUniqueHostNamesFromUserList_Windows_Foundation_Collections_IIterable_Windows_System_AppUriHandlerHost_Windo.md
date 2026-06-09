# GetUniqueHostNamesFromUserList(Windows::Foundation::Collections::IIterable<Windows::System::AppUriHandlerHost *> *,Windows::Foundation::Collections::IIterable<HSTRING__ *> * *)

- ea: `0x180064af0`
- end: `0x180064d9f`
- name: `?GetUniqueHostNamesFromUserList@@YAJPEAU?$IIterable@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@Windows@@PEAPEAU?$IIterable@PEAUHSTRING__@@@234@@Z`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800647b4`

## callees

- `0x1800049bc`
- `0x18000f194`
- `0x180063ec0`
- `0x180063f24`
- `0x180064af0`
- `0x180064da8`
- `0x180064e14`
- `0x1800b2238`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180064c8f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180064c8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064c65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064c65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180064c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064cde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064c9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064cac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180064cde`

## string_xrefs

- `0x180064b30`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180064cf5`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180064d0a`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180064d1f`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180064d34`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180064d49`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetUniqueHostNamesFromUserList(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  unsigned int i; // esi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, HSTRING *); // rbx
  int v17; // eax
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v19; // rax
  int v20; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-40h] BYREF
  HSTRING v24; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v25[8]; // [rsp+40h] [rbp-30h] BYREF
  int v26; // [rsp+48h] [rbp-28h]
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  int v28; // [rsp+60h] [rbp-10h]
  __int64 v29; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned int v31; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v32; // [rsp+B0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+48h] BYREF

  *a2 = 0;
  v32 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
         v4,
         &v32);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
    v25,
    a1);
  v27 = 0;
  v28 = -1;
  v29 = 0;
  while ( v26 != -1 )
  {
    v6 = wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator*(v25);
    v24 = 0;
    v7 = *(_QWORD *)v6;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v6 + 48LL);
    WindowsDeleteString(0);
    v24 = 0;
    v9 = v8(v7, &v24);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
    v23 = 0;
    v10 = v32;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v12 = v11(v10, &v23);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v12,
        bIgnoreCase);
    v31 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 56LL))(v23, &v31);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D2,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
    for ( i = 0; i < v31; ++i )
    {
      string = 0;
      v15 = v23;
      v16 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v23 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = v16(v15, i, &string);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D6,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
          (const char *)(unsigned int)v17,
          bIgnoreCase);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v19 = WindowsGetStringRawBuffer(v24, 0);
      if ( CompareStringOrdinal(v19, -1, StringRawBuffer, -1, 1) == 2 )
      {
        WindowsDeleteString(string);
        goto LABEL_15;
      }
      WindowsDeleteString(string);
    }
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v32 + 104LL))(v32, v24);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    WindowsDeleteString(v24);
    wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator++(v25);
  }
  wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v27);
  wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v25);
  (**(void (__fastcall ***)(__int64, GUID *, _QWORD *))v32)(v32, &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e, a2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  return 0;
}

```

## disassembly

```asm
0x180064af0  push    rbp
0x180064af2  push    rbx
0x180064af3  push    rsi
0x180064af4  push    rdi
0x180064af5  push    r14
0x180064af7  mov     rbp, rsp
0x180064afa  sub     rsp, 70h
0x180064afe  mov     r14, rdx
0x180064b01  mov     rbx, rcx
0x180064b04  mov     qword ptr [rdx], 0
0x180064b0b  mov     [rbp+arg_10], 0
0x180064b13  lea     rcx, [rbp+arg_10]
0x180064b17  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064b1c  lea     rdx, [rbp+arg_10]
0x180064b20  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180064b25  mov     rcx, [rbp+28h]; this
0x180064b29  test    eax, eax
0x180064b2b  jns     short loc_180064B42
0x180064b2d  mov     r9d, eax; char *
0x180064b30  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180064b37  mov     edx, 1C6h; void *
0x180064b3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064b42  mov     rdx, rbx
0x180064b45  lea     rcx, [rbp+var_30]
0x180064b49  call    ??0iterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAVAppUriHandlerHost@System@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::System::AppUriHandlerHost *> *)
0x180064b4e  nop
0x180064b4f  mov     [rbp+var_18], 0
0x180064b57  mov     [rbp+var_10], 0FFFFFFFFh
0x180064b5e  mov     [rbp+var_8], 0
0x180064b66  cmp     [rbp+var_28], 0FFFFFFFFh
0x180064b6a  jz      loc_180064D5B
0x180064b70  lea     rcx, [rbp+var_30]
0x180064b74  call    ??Diterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIAppUriHandlerHost@System@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x180064b79  mov     [rbp+var_38], 0
0x180064b81  mov     rdi, [rax]
0x180064b84  mov     rax, [rdi]
0x180064b87  mov     rbx, [rax+30h]
0x180064b8b  xor     ecx, ecx; string
0x180064b8d  call    cs:__imp_WindowsDeleteString
0x180064b93  mov     [rbp+var_38], 0
0x180064b9b  lea     rdx, [rbp+var_38]
0x180064b9f  mov     rcx, rdi
0x180064ba2  mov     rax, rbx
0x180064ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064baa  mov     rcx, [rbp+28h]; this
0x180064bae  test    eax, eax
0x180064bb0  js      loc_180064D46
0x180064bb6  mov     [rbp+var_40], 0
0x180064bbe  mov     rdi, [rbp+arg_10]
0x180064bc2  mov     rax, [rdi]
0x180064bc5  mov     rbx, [rax+40h]
0x180064bc9  lea     rcx, [rbp+var_40]
0x180064bcd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064bd2  lea     rdx, [rbp+var_40]
0x180064bd6  mov     rcx, rdi
0x180064bd9  mov     rax, rbx
0x180064bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064be1  mov     rcx, [rbp+28h]; this
0x180064be5  test    eax, eax
0x180064be7  js      loc_180064D31
0x180064bed  mov     [rbp+arg_8], 0
0x180064bf4  mov     rcx, [rbp+var_40]
0x180064bf8  mov     rax, [rcx]
0x180064bfb  lea     rdx, [rbp+arg_8]
0x180064bff  mov     rax, [rax+38h]
0x180064c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c08  mov     rcx, [rbp+28h]; this
0x180064c0c  test    eax, eax
0x180064c0e  js      loc_180064D1C
0x180064c14  xor     esi, esi
0x180064c16  cmp     esi, [rbp+arg_8]
0x180064c19  jnb     loc_180064CB4
0x180064c1f  mov     [rbp+string], 0
0x180064c27  mov     rdi, [rbp+var_40]
0x180064c2b  mov     rax, [rdi]
0x180064c2e  mov     rbx, [rax+30h]
0x180064c32  xor     ecx, ecx; string
0x180064c34  call    cs:__imp_WindowsDeleteString
0x180064c3a  mov     [rbp+string], 0
0x180064c42  lea     r8, [rbp+string]
0x180064c46  mov     edx, esi
0x180064c48  mov     rcx, rdi
0x180064c4b  mov     rax, rbx
0x180064c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c53  mov     rcx, [rbp+28h]; this
0x180064c57  test    eax, eax
0x180064c59  js      loc_180064CF2
0x180064c5f  xor     edx, edx; length
0x180064c61  mov     rcx, [rbp+string]; string
0x180064c65  call    cs:__imp_WindowsGetStringRawBuffer
0x180064c6b  mov     rbx, rax
0x180064c6e  xor     edx, edx; length
0x180064c70  mov     rcx, [rbp+var_38]; string
0x180064c74  call    cs:__imp_WindowsGetStringRawBuffer
0x180064c7a  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180064c82  or      r9d, 0FFFFFFFFh; cchCount2
0x180064c86  mov     r8, rbx; lpString2
0x180064c89  or      edx, r9d; cchCount1
0x180064c8c  mov     rcx, rax; lpString1
0x180064c8f  call    cs:__imp_CompareStringOrdinal
0x180064c95  nop
0x180064c96  mov     rcx, [rbp+string]; string
0x180064c9a  cmp     eax, 2
0x180064c9d  jz      short loc_180064CAC
0x180064c9f  call    cs:__imp_WindowsDeleteString
0x180064ca5  inc     esi
0x180064ca7  jmp     loc_180064C16
0x180064cac  call    cs:__imp_WindowsDeleteString
0x180064cb2  jmp     short loc_180064CD0
0x180064cb4  mov     rcx, [rbp+arg_10]
0x180064cb8  mov     rax, [rcx]
0x180064cbb  mov     rdx, [rbp+var_38]
0x180064cbf  mov     rax, [rax+68h]
0x180064cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064cc8  mov     rcx, [rbp+28h]; this
0x180064ccc  test    eax, eax
0x180064cce  js      short loc_180064D07
0x180064cd0  lea     rcx, [rbp+var_40]
0x180064cd4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064cd9  nop
0x180064cda  mov     rcx, [rbp+var_38]; string
0x180064cde  call    cs:__imp_WindowsDeleteString
0x180064ce4  lea     rcx, [rbp+var_30]
0x180064ce8  call    ??Eiterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x180064ced  jmp     loc_180064B66
0x180064cf2  mov     r9d, eax; char *
0x180064cf5  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180064cfc  mov     edx, 1D6h; void *
0x180064d01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064d07  mov     r9d, eax; char *
0x180064d0a  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180064d11  mov     edx, 1E1h; void *
0x180064d16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064d1c  mov     r9d, eax; char *
0x180064d1f  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180064d26  mov     edx, 1D2h; void *
0x180064d2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064d31  mov     r9d, eax; char *
0x180064d34  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180064d3b  mov     edx, 1CFh; void *
0x180064d40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064d46  mov     r9d, eax; char *
0x180064d49  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180064d50  mov     edx, 1CBh; void *
0x180064d55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064d5b  lea     rcx, [rbp+var_18]
0x180064d5f  call    ??1iterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180064d64  nop
0x180064d65  lea     rcx, [rbp+var_30]
0x180064d69  call    ??1iterable_iterator@?$iterable_range@PEAVAppUriHandlerHost@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::System::AppUriHandlerHost *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180064d6e  nop
0x180064d6f  mov     rcx, [rbp+arg_10]
0x180064d73  mov     rax, [rcx]
0x180064d76  mov     r8, r14
0x180064d79  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x180064d80  mov     rax, [rax]
0x180064d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d88  nop
0x180064d89  lea     rcx, [rbp+arg_10]
0x180064d8d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064d92  xor     eax, eax
0x180064d94  add     rsp, 70h
0x180064d98  pop     r14
0x180064d9a  pop     rdi
0x180064d9b  pop     rsi
0x180064d9c  pop     rbx
0x180064d9d  pop     rbp
0x180064d9e  retn
```
