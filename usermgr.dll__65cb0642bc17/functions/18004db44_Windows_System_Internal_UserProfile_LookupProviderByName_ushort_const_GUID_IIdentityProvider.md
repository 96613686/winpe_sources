# Windows::System::Internal::UserProfile::LookupProviderByName(ushort const *,_GUID *,IIdentityProvider * *)

- ea: `0x18004db44`
- end: `0x18004ddf4`
- name: `?LookupProviderByName@UserProfile@Internal@System@Windows@@AEAAJPEBGPEAU_GUID@@PEAPEAUIIdentityProvider@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserProfile *__hidden this, const unsigned __int16 *, struct _GUID *, struct IIdentityProvider **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004cf48`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x18004d578`
- `0x18004db44`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004dcf2`
- `msvcrt!_wcsicmp` at `0x18004dcf2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004dbb0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004dbb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004dce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004dce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dcae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dcae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004dd30`

## string_xrefs

- `0x18004dbc1`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004dbf2`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004dda3`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004ddb8`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004ddcd`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004dde2`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::System::Internal::UserProfile::LookupProviderByName(
        Windows::System::Internal::UserProfile *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct IIdentityProvider **a4)
{
  HRESULT v5; // eax
  int v6; // eax
  unsigned int i; // esi
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, _QWORD, struct _GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, struct IPropertyStore **); // rbx
  int v14; // eax
  Windows::System::Internal::UserProfile *v15; // rcx
  int PropertyAsString; // eax
  const wchar_t *StringRawBuffer; // rax
  LPVOID v18; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-40h] BYREF
  LPVOID v24; // [rsp+48h] [rbp-38h] BYREF
  struct IPropertyStore *v25; // [rsp+50h] [rbp-30h] BYREF
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  struct _GUID v27; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v24 = 0;
  v26 = 0;
  v25 = 0;
  v22 = 0;
  v27 = 0;
  v5 = CoCreateInstance(
         &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
         0,
         0x17u,
         &GUID_df586fa5_6f35_44f1_b209_b38e169772eb,
         &v24);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46A,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)v24 + 24LL))(v24, &v22);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  for ( i = 0; i < v22; ++i )
  {
    v23 = 0;
    string = 0;
    v8 = v24;
    v9 = *(__int64 (__fastcall **)(LPVOID, _QWORD, struct _GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v24 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v10 = v9(v8, i, &v27, &v23);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x472,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v10,
        ppv);
    v11 = (**v23)(v23, &GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5, &v26);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x473,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v11,
        ppv);
    v12 = v26;
    v13 = *(__int64 (__fastcall **)(__int64, struct IPropertyStore **))(*(_QWORD *)v26 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
    v14 = v13(v12, &v25);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x474,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v14,
        ppv);
    WindowsDeleteString(string);
    string = 0;
    PropertyAsString = Windows::System::Internal::UserProfile::GetPropertyAsString(
                         v15,
                         v25,
                         &PKEY_IdentityProvider_Name,
                         &string);
    if ( PropertyAsString < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x476,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)PropertyAsString,
        ppv);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !_wcsicmp(L"MicrosoftAccount", StringRawBuffer) )
    {
      if ( a3 )
        *a3 = v27;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
      break;
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v18 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18004db44  mov     [rsp-18h+arg_0], rbx
0x18004db49  mov     [rsp-18h+arg_8], rsi
0x18004db4e  push    rbp
0x18004db4f  push    rdi
0x18004db50  push    r14
0x18004db52  mov     rbp, rsp
0x18004db55  sub     rsp, 80h
0x18004db5c  mov     rax, cs:__security_cookie
0x18004db63  xor     rax, rsp
0x18004db66  mov     [rbp+var_10], rax
0x18004db6a  mov     r14, r8
0x18004db6d  mov     [rbp+var_38], 0
0x18004db75  mov     [rbp+var_28], 0
0x18004db7d  mov     [rbp+var_30], 0
0x18004db85  mov     [rbp+var_48], 0
0x18004db8c  xorps   xmm0, xmm0
0x18004db8f  movups  [rbp+var_20], xmm0
0x18004db93  lea     rax, [rbp+var_38]
0x18004db97  mov     qword ptr [rsp+80h+ppv], rax; int
0x18004db9c  lea     r9, _GUID_df586fa5_6f35_44f1_b209_b38e169772eb; riid
0x18004dba3  xor     edx, edx; pUnkOuter
0x18004dba5  lea     r8d, [rdx+17h]; dwClsContext
0x18004dba9  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x18004dbb0  call    cs:__imp_CoCreateInstance
0x18004dbb6  mov     rcx, [rbp+18h]; this
0x18004dbba  test    eax, eax
0x18004dbbc  jns     short loc_18004DBD3
0x18004dbbe  mov     r9d, eax; char *
0x18004dbc1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004dbc8  mov     edx, 46Ah; void *
0x18004dbcd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dbd3  mov     rcx, [rbp+var_38]
0x18004dbd7  mov     rax, [rcx]
0x18004dbda  lea     rdx, [rbp+var_48]
0x18004dbde  mov     rax, [rax+18h]
0x18004dbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbe7  mov     rcx, [rbp+18h]; this
0x18004dbeb  test    eax, eax
0x18004dbed  jns     short loc_18004DC04
0x18004dbef  mov     r9d, eax; char *
0x18004dbf2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004dbf9  mov     edx, 46Ch; void *
0x18004dbfe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dc04  xor     esi, esi
0x18004dc06  cmp     esi, [rbp+var_48]
0x18004dc09  jnb     loc_18004DD48
0x18004dc0f  mov     [rbp+var_40], 0
0x18004dc17  mov     [rbp+string], 0
0x18004dc1f  mov     rdi, [rbp+var_38]
0x18004dc23  mov     rax, [rdi]
0x18004dc26  mov     rbx, [rax+20h]
0x18004dc2a  lea     rcx, [rbp+var_40]
0x18004dc2e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc33  lea     r9, [rbp+var_40]
0x18004dc37  lea     r8, [rbp+var_20]
0x18004dc3b  mov     edx, esi
0x18004dc3d  mov     rcx, rdi
0x18004dc40  mov     rax, rbx
0x18004dc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc48  mov     rcx, [rbp+18h]; this
0x18004dc4c  test    eax, eax
0x18004dc4e  js      loc_18004DDDF
0x18004dc54  mov     rcx, [rbp+var_40]
0x18004dc58  mov     rax, [rcx]
0x18004dc5b  lea     r8, [rbp+var_28]
0x18004dc5f  lea     rdx, _GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5
0x18004dc66  mov     rax, [rax]
0x18004dc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc6e  nop
0x18004dc6f  mov     rcx, [rbp+18h]; this
0x18004dc73  test    eax, eax
0x18004dc75  js      loc_18004DDCA
0x18004dc7b  mov     rdi, [rbp+var_28]
0x18004dc7f  mov     rax, [rdi]
0x18004dc82  mov     rbx, [rax+40h]
0x18004dc86  lea     rcx, [rbp+var_30]
0x18004dc8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc8f  lea     rdx, [rbp+var_30]
0x18004dc93  mov     rcx, rdi
0x18004dc96  mov     rax, rbx
0x18004dc99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc9e  mov     rcx, [rbp+18h]; this
0x18004dca2  test    eax, eax
0x18004dca4  js      loc_18004DDB5
0x18004dcaa  mov     rcx, [rbp+string]; string
0x18004dcae  call    cs:__imp_WindowsDeleteString
0x18004dcb4  mov     [rbp+string], 0
0x18004dcbc  lea     r9, [rbp+string]; HSTRING *
0x18004dcc0  lea     r8, PKEY_IdentityProvider_Name; struct _tagpropertykey *
0x18004dcc7  mov     rdx, [rbp+var_30]; struct IPropertyStore *
0x18004dccb  call    ?GetPropertyAsString@UserProfile@Internal@System@Windows@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserProfile::GetPropertyAsString(IPropertyStore *,_tagpropertykey const &,HSTRING__ * *)
0x18004dcd0  mov     rcx, [rbp+18h]; this
0x18004dcd4  test    eax, eax
0x18004dcd6  js      loc_18004DDA0
0x18004dcdc  xor     edx, edx; length
0x18004dcde  mov     rcx, [rbp+string]; string
0x18004dce2  call    cs:__imp_WindowsGetStringRawBuffer
0x18004dce8  mov     rdx, rax; String2
0x18004dceb  lea     rcx, aMicrosoftaccou_0; "MicrosoftAccount"
0x18004dcf2  call    cs:__imp__wcsicmp
0x18004dcf8  test    eax, eax
0x18004dcfa  jz      short loc_18004DD1E
0x18004dcfc  mov     rcx, [rbp+string]; string
0x18004dd00  call    cs:__imp_WindowsDeleteString
0x18004dd06  mov     [rbp+string], 0
0x18004dd0e  lea     rcx, [rbp+var_40]
0x18004dd12  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dd17  inc     esi
0x18004dd19  jmp     loc_18004DC06
0x18004dd1e  test    r14, r14
0x18004dd21  jz      short loc_18004DD2C
0x18004dd23  movups  xmm0, [rbp+var_20]
0x18004dd27  movdqu  xmmword ptr [r14], xmm0
0x18004dd2c  mov     rcx, [rbp+string]; string
0x18004dd30  call    cs:__imp_WindowsDeleteString
0x18004dd36  mov     [rbp+string], 0
0x18004dd3e  lea     rcx, [rbp+var_40]
0x18004dd42  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dd47  nop
0x18004dd48  lea     rcx, [rbp+var_30]
0x18004dd4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dd51  nop
0x18004dd52  lea     rcx, [rbp+var_28]
0x18004dd56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dd5b  nop
0x18004dd5c  mov     rcx, [rbp+var_38]
0x18004dd60  test    rcx, rcx
0x18004dd63  jz      short loc_18004DD7A
0x18004dd65  mov     [rbp+var_38], 0
0x18004dd6d  mov     rax, [rcx]
0x18004dd70  mov     rax, [rax+10h]
0x18004dd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd79  nop
0x18004dd7a  xor     eax, eax
0x18004dd7c  mov     rcx, [rbp+var_10]
0x18004dd80  xor     rcx, rsp; StackCookie
0x18004dd83  call    __security_check_cookie
0x18004dd88  lea     r11, [rsp+80h+var_s0]
0x18004dd90  mov     rbx, [r11+20h]
0x18004dd94  mov     rsi, [r11+28h]
0x18004dd98  mov     rsp, r11
0x18004dd9b  pop     r14
0x18004dd9d  pop     rdi
0x18004dd9e  pop     rbp
0x18004dd9f  retn
0x18004dda0  mov     r9d, eax; char *
0x18004dda3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ddaa  mov     edx, 476h; void *
0x18004ddaf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ddb5  mov     r9d, eax; char *
0x18004ddb8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ddbf  mov     edx, 474h; void *
0x18004ddc4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ddca  mov     r9d, eax; char *
0x18004ddcd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004ddd4  mov     edx, 473h; void *
0x18004ddd9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004dddf  mov     r9d, eax; char *
0x18004dde2  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004dde9  mov     edx, 472h; void *
0x18004ddee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
