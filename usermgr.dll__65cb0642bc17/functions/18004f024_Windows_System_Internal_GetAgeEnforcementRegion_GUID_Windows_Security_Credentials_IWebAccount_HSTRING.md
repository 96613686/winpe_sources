# Windows::System::Internal::GetAgeEnforcementRegion(_GUID,Windows::Security::Credentials::IWebAccount *,HSTRING__ * *)

- ea: `0x18004f024`
- end: `0x18004f28b`
- name: `?GetAgeEnforcementRegion@Internal@System@Windows@@YAJU_GUID@@PEAUIWebAccount@Credentials@Security@3@PEAPEAUHSTRING__@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(Windows::System::Internal *__hidden this, struct _GUID *__struct_ptr, struct Windows::Security::Credentials::IWebAccount *, HSTRING *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d2540`

## callees

- `0x18000acdc`
- `0x1800132d0`
- `0x1800181f0`
- `0x18003322c`
- `0x18003b578`
- `0x18004e508`
- `0x18004f024`
- `0x18005290c`
- `0x1800616c0`
- `0x18006f1e1`
- `0x1800c354c`
- `0x1800d28a4`
- `0x1800de450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f17c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f243`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x18004f16f`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x18004f1c9`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x18004f16f`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x18004f1c9`

## string_xrefs

- `0x18004f0e1`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x18004f143`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x18004f18e`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x18004f1e5`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x18004f21f`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::System::Internal::GetAgeEnforcementRegion(
        Windows::System::Internal *this,
        struct _GUID *a2,
        struct Windows::Security::Credentials::IWebAccount *a3,
        HSTRING *a4)
{
  int PropertyFromWebAccount; // eax
  char v7; // bl
  int v8; // eax
  int UserDefaultGeoName; // eax
  __int64 v10; // rbx
  DWORD LastError; // eax
  int v12; // edx
  PVOID Reserved1; // rbx
  DWORD v14; // eax
  int v15; // eax
  HSTRING v16; // rax
  HSTRING v18; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v20[8]; // [rsp+30h] [rbp-48h] BYREF
  PVOID v21; // [rsp+38h] [rbp-40h]
  HSTRING_HEADER geoName; // [rsp+40h] [rbp-38h] BYREF
  struct Windows::Security::Credentials::IWebAccount2 *v23; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(
    v20,
    a2);
  LOBYTE(v18) = 0;
  if ( memcmp_0(this, qword_18010E118, 0x10u) && memcmp_0(this, qword_18010E280, 0x10u) )
    goto LABEL_10;
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(
    v20,
    &string);
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&geoName, L"Country", 8u, 7u);
  PropertyFromWebAccount = Windows::System::Internal::GetPropertyFromWebAccount(
                             (Windows::System::Internal *)string,
                             v23,
                             (HSTRING)a3,
                             &v18,
                             (unsigned __int8 *)v18);
  if ( PropertyFromWebAccount < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
      (const char *)(unsigned int)PropertyFromWebAccount,
      (int)v18);
  v7 = (char)v18;
  if ( !(_BYTE)v18 )
  {
    v23 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&geoName, L"CountryOrRegion", 0x10u, 0xFu);
    v8 = Windows::System::Internal::GetPropertyFromWebAccount(
           (Windows::System::Internal *)string,
           v23,
           (HSTRING)a3,
           &v18,
           (unsigned __int8 *)v18);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
        (const char *)(unsigned int)v8,
        (int)v18);
    v7 = (char)v18;
  }
  wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&string);
  if ( !v7 )
  {
LABEL_10:
    UserDefaultGeoName = GetUserDefaultGeoName(0, 0);
    v10 = UserDefaultGeoName;
    if ( !UserDefaultGeoName )
    {
      LastError = GetLastError();
      if ( LastError )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
          (const char *)LastError,
          (unsigned int)v18);
    }
    memset(&geoName, 0, sizeof(geoName));
    std::vector<unsigned short>::resize(&geoName, v10);
    v12 = v10;
    Reserved1 = geoName.Reserved.Reserved1;
    if ( !GetUserDefaultGeoName((LPWSTR)geoName.Reserved.Reserved1, v12) )
    {
      v14 = GetLastError();
      if ( v14 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x102,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
          (const char *)v14,
          (unsigned int)v18);
    }
    string = 0;
    v21 = Reserved1;
    v15 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\common\\lib\\useraccounthelper.cpp",
        (const char *)(unsigned int)v15,
        (int)v18);
    v16 = string;
    string = 0;
    *(_QWORD *)a3 = v16;
    WindowsDeleteString(0);
    string = 0;
    std::vector<unsigned short>::_Tidy(&geoName);
  }
  wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v20);
  return 0;
}

```

## disassembly

```asm
0x18004f024  mov     [rsp+arg_0], rbx
0x18004f029  push    rdi
0x18004f02a  sub     rsp, 70h
0x18004f02e  mov     rax, cs:__security_cookie
0x18004f035  xor     rax, rsp
0x18004f038  mov     [rsp+78h+var_18], rax
0x18004f03d  mov     rdi, r8
0x18004f040  mov     rbx, rcx
0x18004f043  lea     rcx, [rsp+78h+var_48]
0x18004f048  call    ??0?$com_ptr_t@UISignInContext@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUISignInContext@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::ISignInContext,wil::err_exception_policy>(Windows::System::Internal::ISignInContext *)
0x18004f04d  nop
0x18004f04e  mov     byte ptr [rsp+78h+var_58], 0; int
0x18004f053  mov     r8d, 10h; Size
0x18004f059  lea     rdx, qword_18010E118; Buf2
0x18004f060  mov     rcx, rbx; Buf1
0x18004f063  call    memcmp_0
0x18004f068  test    eax, eax
0x18004f06a  jz      short loc_18004F089
0x18004f06c  mov     r8d, 10h; Size
0x18004f072  lea     rdx, qword_18010E280; Buf2
0x18004f079  mov     rcx, rbx; Buf1
0x18004f07c  call    memcmp_0
0x18004f081  test    eax, eax
0x18004f083  jnz     loc_18004F16B
0x18004f089  lea     rdx, [rsp+78h+string]
0x18004f08e  lea     rcx, [rsp+78h+var_48]
0x18004f093  call    ??$query@UIWebAccount2@Credentials@Security@Windows@@@?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIWebAccount2@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::query<Windows::Security::Credentials::IWebAccount2>(void)
0x18004f098  nop
0x18004f099  mov     [rsp+78h+var_20], 0
0x18004f0a2  mov     r9d, 7; unsigned int
0x18004f0a8  lea     r8d, [r9+1]; unsigned int
0x18004f0ac  lea     rdx, aCountry; "Country"
0x18004f0b3  lea     rcx, [rsp+78h+geoName]; hstringHeader
0x18004f0b8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004f0bd  nop
0x18004f0be  lea     r9, [rsp+78h+var_58]; HSTRING *
0x18004f0c3  mov     r8, rdi; HSTRING
0x18004f0c6  mov     rdx, [rsp+78h+var_20]; struct Windows::Security::Credentials::IWebAccount2 *
0x18004f0cb  mov     rcx, [rsp+78h+string]; this
0x18004f0d0  call    ?GetPropertyFromWebAccount@Internal@System@Windows@@YAJPEAUIWebAccount2@Credentials@Security@3@PEAUHSTRING__@@PEAPEAU7@PEAE@Z; Windows::System::Internal::GetPropertyFromWebAccount(Windows::Security::Credentials::IWebAccount2 *,HSTRING__ *,HSTRING__ * *,uchar *)
0x18004f0d5  mov     rcx, [rsp+78h]; this
0x18004f0da  test    eax, eax
0x18004f0dc  jns     short loc_18004F0F3
0x18004f0de  mov     r9d, eax; char *
0x18004f0e1  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f0e8  mov     edx, 0EEh; void *
0x18004f0ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f0f3  mov     bl, byte ptr [rsp+78h+var_58]
0x18004f0f7  test    bl, bl
0x18004f0f9  jnz     short loc_18004F159
0x18004f0fb  mov     [rsp+78h+var_20], 0
0x18004f104  mov     r9d, 0Fh; unsigned int
0x18004f10a  lea     r8d, [r9+1]; unsigned int
0x18004f10e  lea     rdx, aCountryorregio; "CountryOrRegion"
0x18004f115  lea     rcx, [rsp+78h+geoName]; hstringHeader
0x18004f11a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004f11f  nop
0x18004f120  lea     r9, [rsp+78h+var_58]; HSTRING *
0x18004f125  mov     r8, rdi; HSTRING
0x18004f128  mov     rdx, [rsp+78h+var_20]; struct Windows::Security::Credentials::IWebAccount2 *
0x18004f12d  mov     rcx, [rsp+78h+string]; this
0x18004f132  call    ?GetPropertyFromWebAccount@Internal@System@Windows@@YAJPEAUIWebAccount2@Credentials@Security@3@PEAUHSTRING__@@PEAPEAU7@PEAE@Z; Windows::System::Internal::GetPropertyFromWebAccount(Windows::Security::Credentials::IWebAccount2 *,HSTRING__ *,HSTRING__ * *,uchar *)
0x18004f137  mov     rcx, [rsp+78h]; this
0x18004f13c  test    eax, eax
0x18004f13e  jns     short loc_18004F155
0x18004f140  mov     r9d, eax; char *
0x18004f143  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f14a  mov     edx, 0F1h; void *
0x18004f14f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f155  mov     bl, byte ptr [rsp+78h+var_58]
0x18004f159  lea     rcx, [rsp+78h+string]
0x18004f15e  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x18004f163  test    bl, bl
0x18004f165  jnz     loc_18004F25D
0x18004f16b  xor     edx, edx; geoNameCount
0x18004f16d  xor     ecx, ecx; geoName
0x18004f16f  call    cs:__imp_GetUserDefaultGeoName
0x18004f175  movsxd  rbx, eax
0x18004f178  test    eax, eax
0x18004f17a  jnz     short loc_18004F19F
0x18004f17c  call    cs:__imp_GetLastError
0x18004f182  mov     rcx, [rsp+78h]; this
0x18004f187  test    eax, eax
0x18004f189  jz      short loc_18004F19F
0x18004f18b  mov     r9d, eax; char *
0x18004f18e  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f195  mov     edx, 0FBh; void *
0x18004f19a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004f19f  xorps   xmm0, xmm0
0x18004f1a2  movdqu  xmmword ptr [rsp+78h+geoName], xmm0
0x18004f1a8  mov     [rsp+78h+var_28], 0
0x18004f1b1  mov     rdx, rbx
0x18004f1b4  lea     rcx, [rsp+78h+geoName]
0x18004f1b9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004f1be  nop
0x18004f1bf  mov     edx, ebx; geoNameCount
0x18004f1c1  mov     rbx, [rsp+78h+geoName]
0x18004f1c6  mov     rcx, rbx; geoName
0x18004f1c9  call    cs:__imp_GetUserDefaultGeoName
0x18004f1cf  test    eax, eax
0x18004f1d1  jnz     short loc_18004F1F6
0x18004f1d3  call    cs:__imp_GetLastError
0x18004f1d9  mov     rcx, [rsp+78h]; this
0x18004f1de  test    eax, eax
0x18004f1e0  jz      short loc_18004F1F6
0x18004f1e2  mov     r9d, eax; char *
0x18004f1e5  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f1ec  mov     edx, 102h; void *
0x18004f1f1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004f1f6  mov     [rsp+78h+string], 0
0x18004f1ff  mov     [rsp+78h+var_40], rbx
0x18004f204  lea     rdx, [rsp+78h+var_40]
0x18004f209  lea     rcx, [rsp+78h+string]; string
0x18004f20e  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18004f213  mov     rcx, [rsp+78h]; this
0x18004f218  test    eax, eax
0x18004f21a  jns     short loc_18004F230
0x18004f21c  mov     r9d, eax; char *
0x18004f21f  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\umstartup\\userm"...
0x18004f226  mov     edx, 106h; void *
0x18004f22b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f230  mov     rax, [rsp+78h+string]
0x18004f235  mov     [rsp+78h+string], 0
0x18004f23e  mov     [rdi], rax
0x18004f241  xor     ecx, ecx; string
0x18004f243  call    cs:__imp_WindowsDeleteString
0x18004f249  mov     [rsp+78h+string], 0
0x18004f252  lea     rcx, [rsp+78h+geoName]
0x18004f257  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@IEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004f25c  nop
0x18004f25d  lea     rcx, [rsp+78h+var_48]
0x18004f262  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x18004f267  xor     eax, eax
0x18004f269  jmp     short loc_18004F26F
0x18004f26b  mov     eax, dword ptr [rsp+78h+string]
0x18004f26f  mov     rcx, [rsp+78h+var_18]
0x18004f274  xor     rcx, rsp; StackCookie
0x18004f277  call    __security_check_cookie
0x18004f27c  mov     rbx, [rsp+78h+arg_0]
0x18004f284  add     rsp, 70h
0x18004f288  pop     rdi
0x18004f289  retn
```
