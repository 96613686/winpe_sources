# Windows::System::Internal::UserProfile::ScanAssociatedAccount(unsigned __int64,HSTRING__ * *)

- ea: `0x18004b080`
- end: `0x18004b3c9`
- name: `?ScanAssociatedAccount@UserProfile@Internal@System@Windows@@UEAAJ_KPEAPEAUHSTRING__@@@Z`
- size: `841`
- prototype: `int(Windows::System::Internal::UserProfile *__hidden this, unsigned __int64, HSTRING *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x18004b080`
- `0x18004b3d0`
- `0x18004b4e4`
- `0x18004d578`
- `0x1800c0008`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b0ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b0ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b26b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b2ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b36b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b26b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b2ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b36b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b2fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b32b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b2fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b32b`

## string_xrefs

- `0x18004b104`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b152`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b1a7`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b21b`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b29f`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b2d4`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b312`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b340`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::System::Internal::UserProfile::ScanAssociatedAccount(HSTRING *this, void *a2, HSTRING *a3)
{
  HRESULT v5; // eax
  LPVOID v6; // rbx
  __int64 (__fastcall *v7)(LPVOID, GUID *, __int64 *); // rdi
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD); // rbx
  int v11; // eax
  int v12; // esi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, int (__fastcall ****)(_QWORD, GUID *, struct IPropertyStore **), int *); // rbx
  int v15; // eax
  int (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v17)(_QWORD, GUID *, struct IPropertyStore **); // rdi
  Windows::System::Internal::UserProfile *v18; // rcx
  int PropertyAsString; // eax
  HRESULT v20; // eax
  HRESULT v21; // eax
  const char *v22; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-B8h]
  HSTRING string; // [rsp+30h] [rbp-A8h] BYREF
  struct IPropertyStore *v26; // [rsp+38h] [rbp-A0h] BYREF
  int (__fastcall ***v27)(_QWORD, GUID *, struct IPropertyStore **); // [rsp+40h] [rbp-98h] BYREF
  int v28[2]; // [rsp+48h] [rbp-90h] BYREF
  __int64 v29; // [rsp+50h] [rbp-88h] BYREF
  LPVOID v30; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v31[120]; // [rsp+60h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  int v33; // [rsp+F8h] [rbp+20h] BYREF

  v30 = 0;
  v29 = 0;
  *(_QWORD *)v28 = 0;
  v27 = 0;
  v26 = 0;
  string = 0;
  try
  {
    Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(
      (Windows::System::Internal::Implementation::AutoUserContext *)v31,
      a2,
      0);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v5 = CoCreateInstance(
           &GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f,
           0,
           1u,
           &GUID_b7417b54_e08c_429b_96c8_678d1369ecb1,
           &v30);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    v6 = v30;
    v7 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v30;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v8 = v7(v6, &GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5, &v29);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v8,
        ppv);
    v9 = v29;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v29 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
    v11 = v10(v9, 1, 0);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v11,
        (int)v28);
    v12 = 0;
    while ( !string && v12 != 1 )
    {
      v33 = 0;
      v13 = *(_QWORD *)v28;
      v14 = *(__int64 (__fastcall **)(__int64, __int64, int (__fastcall ****)(_QWORD, GUID *, struct IPropertyStore **), int *))(**(_QWORD **)v28 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      v15 = v14(v13, 1, &v27, &v33);
      v12 = v15;
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F9,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v15,
          (int)v28);
      v16 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v27;
      if ( v27 )
      {
        v17 = **v27;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
        if ( v17(v16, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v26) >= 0 )
        {
          WindowsDeleteString(string);
          string = 0;
          PropertyAsString = Windows::System::Internal::UserProfile::GetPropertyAsString(
                               v18,
                               v26,
                               &PKEY_Identity_UserName,
                               &string);
          if ( PropertyAsString < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3FD,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
              (const char *)(unsigned int)PropertyAsString,
              (int)v28);
        }
      }
    }
    Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v31);
    if ( !string )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x404,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)0x80070490LL,
        (int)v28);
    WindowsDeleteString(this[9]);
    this[9] = 0;
    v20 = WindowsDuplicateString(string, this + 9);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x405,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v20,
        (int)v28);
    v21 = WindowsDuplicateString(string, a3);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x406,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v21,
        (int)v28);
    Windows::System::Internal::UserProfile::PersistEmailAddress((Windows::System::Internal::UserProfile *)(this - 3));
    Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)v31);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x40B,
                           (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x18004b080  push    rbx
0x18004b082  push    rsi
0x18004b083  push    rdi
0x18004b084  push    r12
0x18004b086  push    r14
0x18004b088  push    r15
0x18004b08a  sub     rsp, 0A8h
0x18004b091  mov     r15, r8
0x18004b094  mov     r14, rcx
0x18004b097  xor     r12d, r12d
0x18004b09a  mov     [rsp+0D8h+var_80], r12
0x18004b09f  mov     [rsp+0D8h+var_88], r12
0x18004b0a4  mov     qword ptr [rsp+0D8h+var_90], r12
0x18004b0a9  mov     [rsp+0D8h+var_98], r12
0x18004b0ae  mov     [rsp+0D8h+var_A0], r12
0x18004b0b3  mov     [rsp+0D8h+string], r12
0x18004b0b8  xor     r8d, r8d; unsigned __int16 *
0x18004b0bb  lea     rcx, [rsp+0D8h+var_78]; this
0x18004b0c0  call    ??0AutoUserContext@Implementation@Internal@System@Windows@@QEAA@PEAXPEBG@Z; Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(void *,ushort const *)
0x18004b0c5  nop
0x18004b0c6  lea     rcx, [rsp+0D8h+var_80]
0x18004b0cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b0d0  lea     rax, [rsp+0D8h+var_80]
0x18004b0d5  mov     qword ptr [rsp+0D8h+ppv], rax; int
0x18004b0da  lea     r9, _GUID_b7417b54_e08c_429b_96c8_678d1369ecb1; riid
0x18004b0e1  xor     edx, edx; pUnkOuter
0x18004b0e3  lea     r8d, [r12+1]; dwClsContext
0x18004b0e8  lea     rcx, _GUID_d7f9888f_e3fc_49b0_9ea6_a85b5f392a4f; rclsid
0x18004b0ef  call    cs:__imp_CoCreateInstance
0x18004b0f5  mov     rcx, [rsp+0D8h]; this
0x18004b0fd  test    eax, eax
0x18004b0ff  jns     short loc_18004B116
0x18004b101  mov     r9d, eax; char *
0x18004b104  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b10b  mov     edx, 3F0h; void *
0x18004b110  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b116  mov     rbx, [rsp+0D8h+var_80]
0x18004b11b  mov     rax, [rbx]
0x18004b11e  mov     rdi, [rax]
0x18004b121  lea     rcx, [rsp+0D8h+var_88]
0x18004b126  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b12b  lea     r8, [rsp+0D8h+var_88]
0x18004b130  lea     rdx, _GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5
0x18004b137  mov     rcx, rbx
0x18004b13a  mov     rax, rdi
0x18004b13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b142  nop
0x18004b143  mov     rcx, [rsp+0D8h]; this
0x18004b14b  test    eax, eax
0x18004b14d  jns     short loc_18004B163
0x18004b14f  mov     r9d, eax; char *
0x18004b152  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b159  mov     edx, 3F1h; void *
0x18004b15e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b163  mov     rdi, [rsp+0D8h+var_88]
0x18004b168  mov     rax, [rdi]
0x18004b16b  mov     rbx, [rax+18h]
0x18004b16f  lea     rcx, [rsp+0D8h+var_90]
0x18004b174  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b179  lea     rax, [rsp+0D8h+var_90]
0x18004b17e  mov     qword ptr [rsp+0D8h+ppv], rax; int
0x18004b183  xor     r9d, r9d
0x18004b186  xor     r8d, r8d
0x18004b189  lea     edx, [r9+1]
0x18004b18d  mov     rcx, rdi
0x18004b190  mov     rax, rbx
0x18004b193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b198  mov     rcx, [rsp+0D8h]; this
0x18004b1a0  test    eax, eax
0x18004b1a2  jns     short loc_18004B1B8
0x18004b1a4  mov     r9d, eax; char *
0x18004b1a7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b1ae  mov     edx, 3F2h; void *
0x18004b1b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b1b8  mov     esi, r12d
0x18004b1bb  cmp     [rsp+0D8h+string], r12
0x18004b1c0  jnz     loc_18004B2B0
0x18004b1c6  cmp     esi, 1
0x18004b1c9  jz      loc_18004B2B0
0x18004b1cf  mov     [rsp+0D8h+arg_18], r12d
0x18004b1d7  mov     rdi, qword ptr [rsp+0D8h+var_90]
0x18004b1dc  mov     rax, [rdi]
0x18004b1df  mov     rbx, [rax+18h]
0x18004b1e3  lea     rcx, [rsp+0D8h+var_98]
0x18004b1e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b1ed  lea     r9, [rsp+0D8h+arg_18]
0x18004b1f5  lea     r8, [rsp+0D8h+var_98]
0x18004b1fa  mov     edx, 1
0x18004b1ff  mov     rcx, rdi
0x18004b202  mov     rax, rbx
0x18004b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b20a  mov     esi, eax
0x18004b20c  mov     rcx, [rsp+0D8h]; this
0x18004b214  test    eax, eax
0x18004b216  jns     short loc_18004B22C
0x18004b218  mov     r9d, eax; char *
0x18004b21b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b222  mov     edx, 3F9h; void *
0x18004b227  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b22c  mov     rbx, [rsp+0D8h+var_98]
0x18004b231  test    rbx, rbx
0x18004b234  jz      short loc_18004B1BB
0x18004b236  mov     rax, [rbx]
0x18004b239  mov     rdi, [rax]
0x18004b23c  lea     rcx, [rsp+0D8h+var_A0]
0x18004b241  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b246  lea     r8, [rsp+0D8h+var_A0]
0x18004b24b  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18004b252  mov     rcx, rbx
0x18004b255  mov     rax, rdi
0x18004b258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b25d  nop
0x18004b25e  test    eax, eax
0x18004b260  js      loc_18004B1BB
0x18004b266  mov     rcx, [rsp+0D8h+string]; string
0x18004b26b  call    cs:__imp_WindowsDeleteString
0x18004b271  mov     [rsp+0D8h+string], r12
0x18004b276  lea     r9, [rsp+0D8h+string]; HSTRING *
0x18004b27b  lea     r8, PKEY_Identity_UserName; struct _tagpropertykey *
0x18004b282  mov     rdx, [rsp+0D8h+var_A0]; struct IPropertyStore *
0x18004b287  call    ?GetPropertyAsString@UserProfile@Internal@System@Windows@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserProfile::GetPropertyAsString(IPropertyStore *,_tagpropertykey const &,HSTRING__ * *)
0x18004b28c  mov     rcx, [rsp+0D8h]; this
0x18004b294  test    eax, eax
0x18004b296  jns     loc_18004B1BB
0x18004b29c  mov     r9d, eax; char *
0x18004b29f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b2a6  mov     edx, 3FDh; void *
0x18004b2ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b2b0  lea     rcx, [rsp+0D8h+var_78]; this
0x18004b2b5  call    ?Revoke@AutoUserContext@Implementation@Internal@System@Windows@@QEAAXXZ; Windows::System::Internal::Implementation::AutoUserContext::Revoke(void)
0x18004b2ba  cmp     [rsp+0D8h+string], r12
0x18004b2bf  setnz   al
0x18004b2c2  mov     rcx, [rsp+0D8h]; this
0x18004b2ca  test    al, al
0x18004b2cc  jnz     short loc_18004B2E5
0x18004b2ce  mov     r9d, 80070490h; char *
0x18004b2d4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b2db  mov     edx, 404h; void *
0x18004b2e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b2e5  lea     rbx, [r14+48h]
0x18004b2e9  mov     rcx, [rbx]; string
0x18004b2ec  call    cs:__imp_WindowsDeleteString
0x18004b2f2  mov     [rbx], r12
0x18004b2f5  mov     rdx, rbx; newString
0x18004b2f8  mov     rcx, [rsp+0D8h+string]; string
0x18004b2fd  call    cs:__imp_WindowsDuplicateString
0x18004b303  mov     rcx, [rsp+0D8h]; this
0x18004b30b  test    eax, eax
0x18004b30d  jns     short loc_18004B323
0x18004b30f  mov     r9d, eax; char *
0x18004b312  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b319  mov     edx, 405h; void *
0x18004b31e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b323  mov     rdx, r15; newString
0x18004b326  mov     rcx, [rsp+0D8h+string]; string
0x18004b32b  call    cs:__imp_WindowsDuplicateString
0x18004b331  mov     rcx, [rsp+0D8h]; this
0x18004b339  test    eax, eax
0x18004b33b  jns     short loc_18004B351
0x18004b33d  mov     r9d, eax; char *
0x18004b340  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b347  mov     edx, 406h; void *
0x18004b34c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b351  lea     rcx, [r14-18h]; this
0x18004b355  call    ?PersistEmailAddress@UserProfile@Internal@System@Windows@@AEAAJXZ; Windows::System::Internal::UserProfile::PersistEmailAddress(void)
0x18004b35a  nop
0x18004b35b  lea     rcx, [rsp+0D8h+var_78]; this
0x18004b360  call    ?Revoke@AutoUserContext@Implementation@Internal@System@Windows@@QEAAXXZ; Windows::System::Internal::Implementation::AutoUserContext::Revoke(void)
0x18004b365  nop
0x18004b366  mov     rcx, [rsp+0D8h+string]; string
0x18004b36b  call    cs:__imp_WindowsDeleteString
0x18004b371  mov     [rsp+0D8h+string], r12
0x18004b376  lea     rcx, [rsp+0D8h+var_A0]
0x18004b37b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b380  nop
0x18004b381  lea     rcx, [rsp+0D8h+var_98]
0x18004b386  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b38b  nop
0x18004b38c  lea     rcx, [rsp+0D8h+var_90]
0x18004b391  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b396  nop
0x18004b397  lea     rcx, [rsp+0D8h+var_88]
0x18004b39c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b3a1  nop
0x18004b3a2  lea     rcx, [rsp+0D8h+var_80]
0x18004b3a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b3ac  xor     eax, eax
0x18004b3ae  jmp     short loc_18004B3B7
0x18004b3b0  mov     eax, [rsp+0D8h+arg_18]
0x18004b3b7  add     rsp, 0A8h
0x18004b3be  pop     r15
0x18004b3c0  pop     r14
0x18004b3c2  pop     r12
0x18004b3c4  pop     rdi
0x18004b3c5  pop     rsi
0x18004b3c6  pop     rbx
0x18004b3c7  retn
```
