# Windows::System::Internal::UserProfile::ScanConnectedAccount(HSTRING__ * *)

- ea: `0x18004b5a0`
- end: `0x18004b935`
- name: `?ScanConnectedAccount@UserProfile@Internal@System@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `917`
- prototype: `int(Windows::System::Internal::UserProfile *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000acdc`
- `0x18000ce48`
- `0x18004b4e4`
- `0x18004b5a0`
- `0x18004d578`
- `0x18004e58c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b671`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b671`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b6a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b6a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004b7e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18004b7e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b7f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b84d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b7f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b84d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b88f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004b88f`

## string_xrefs

- `0x18004b5ca`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b642`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b683`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b6cb`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b72f`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b778`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b7c7`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b828`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b873`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x18004b8a1`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::System::Internal::UserProfile::ScanConnectedAccount(
        Windows::System::Internal::UserProfile *this,
        HSTRING *a2)
{
  void (__fastcall *v4)(void *, __int64 *); // rbx
  HRESULT v5; // eax
  __int64 v6; // rdi
  unsigned int (__fastcall *v7)(__int64, PCWSTR, _QWORD *); // rbx
  PCWSTR StringRawBuffer; // rax
  const char *v9; // r9
  LPVOID v10; // rbx
  __int64 (__fastcall *v11)(LPVOID, _QWORD, _QWORD, __int64 *); // rdi
  unsigned int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, struct IPropertyStore **); // rbx
  int v16; // eax
  Windows::System::Internal::UserProfile *v17; // rcx
  int PropertyAsString; // eax
  Windows::System::Internal::UserProfile *v19; // rcx
  int v20; // eax
  HSTRING v21; // rcx
  HRESULT v22; // eax
  HRESULT v23; // eax
  const char *v24; // r9
  LPVOID v25; // rcx
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  __int64 v29; // [rsp+30h] [rbp-48h] BYREF
  LPVOID v30; // [rsp+38h] [rbp-40h] BYREF
  _QWORD v31[7]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HSTRING string; // [rsp+88h] [rbp+10h] BYREF
  __int64 v34; // [rsp+90h] [rbp+18h] BYREF
  struct IPropertyStore *v35; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    if ( !a2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3BC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)0x80004003LL,
        ppv);
    v30 = 0;
    v29 = 0;
    v35 = 0;
    v34 = 0;
    v4 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v4(&Windows::System::Internal::Adapters::g_AdapterCollection, &v34);
    v31[0] = 0;
    string = 0;
    if ( !*((_QWORD *)this + 12) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3C6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)0x8000FFFFLL,
        ppv);
    v5 = CoCreateInstance(
           &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
           0,
           0x17u,
           &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
           &v30);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3CC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v5,
        ppva);
    v6 = v34;
    v7 = *(unsigned int (__fastcall **)(__int64, PCWSTR, _QWORD *))(*(_QWORD *)v34 + 40LL);
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
    if ( !v7(v6, StringRawBuffer, v31) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3CE,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        v9);
    v10 = v30;
    v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v30 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 64LL))(v34, v31[0]);
    v13 = v11(v10, v31[0], v12, &v29);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3CF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v13,
        ppva);
    v14 = v29;
    v15 = *(__int64 (__fastcall **)(__int64, struct IPropertyStore **))(*(_QWORD *)v29 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v16 = v15(v14, &v35);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v16,
        ppva);
    WindowsDeleteString(string);
    string = 0;
    PropertyAsString = Windows::System::Internal::UserProfile::GetPropertyAsString(
                         v17,
                         v35,
                         &PKEY_Identity_PrimaryEmailAddress,
                         &string);
    if ( PropertyAsString < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)PropertyAsString,
        ppva);
    if ( !WindowsGetStringLen(string) )
    {
      WindowsDeleteString(string);
      string = 0;
      v20 = Windows::System::Internal::UserProfile::GetPropertyAsString(v19, v35, &PKEY_Identity_UserName, &string);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D4,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v20,
          ppva);
    }
    v21 = string;
    if ( string )
    {
      WindowsDeleteString(*((HSTRING *)this + 9));
      *((_QWORD *)this + 9) = 0;
      v22 = WindowsDuplicateString(string, (HSTRING *)this + 9);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D9,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v22,
          ppva);
      v23 = WindowsDuplicateString(string, a2);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3DA,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v23,
          ppva);
      Windows::System::Internal::UserProfile::PersistEmailAddress((Windows::System::Internal::UserProfile *)((char *)this - 24));
      v21 = string;
    }
    WindowsDeleteString(v21);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v25 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
    }
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x3E1,
                        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
                        v24);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x18004b5a0  mov     [rsp+arg_0], rbx
0x18004b5a5  push    rsi
0x18004b5a6  push    rdi
0x18004b5a7  push    r12
0x18004b5a9  push    r14
0x18004b5ab  push    r15
0x18004b5ad  sub     rsp, 50h
0x18004b5b1  mov     r15, rdx
0x18004b5b4  mov     r14, rcx
0x18004b5b7  mov     rcx, [rsp+78h]; this
0x18004b5bc  xor     r12d, r12d
0x18004b5bf  test    rdx, rdx
0x18004b5c2  jnz     short loc_18004B5DB
0x18004b5c4  mov     r9d, 80004003h; char *
0x18004b5ca  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b5d1  mov     edx, 3BCh; void *
0x18004b5d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b5db  mov     [rsp+78h+var_40], r12
0x18004b5e0  mov     [rsp+78h+var_48], r12
0x18004b5e5  mov     [rsp+78h+arg_18], r12
0x18004b5ed  mov     [rsp+78h+arg_10], r12
0x18004b5f5  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004b5fc  mov     rbx, [rax+38h]
0x18004b600  lea     rcx, [rsp+78h+arg_10]
0x18004b608  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b60d  lea     rdx, [rsp+78h+arg_10]
0x18004b615  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18004b61c  mov     rax, rbx
0x18004b61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b624  mov     [rsp+78h+var_38], r12
0x18004b629  mov     [rsp+78h+string], r12
0x18004b631  mov     rcx, [rsp+78h]; this
0x18004b636  cmp     [r14+60h], r12
0x18004b63a  jnz     short loc_18004B653
0x18004b63c  mov     r9d, 8000FFFFh; char *
0x18004b642  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b649  mov     edx, 3C6h; void *
0x18004b64e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b653  lea     rax, [rsp+78h+var_40]
0x18004b658  mov     qword ptr [rsp+78h+ppv], rax; int
0x18004b65d  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x18004b664  xor     edx, edx; pUnkOuter
0x18004b666  lea     r8d, [rdx+17h]; dwClsContext
0x18004b66a  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x18004b671  call    cs:__imp_CoCreateInstance
0x18004b677  mov     rcx, [rsp+78h]; this
0x18004b67c  test    eax, eax
0x18004b67e  jns     short loc_18004B694
0x18004b680  mov     r9d, eax; char *
0x18004b683  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b68a  mov     edx, 3CCh; void *
0x18004b68f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b694  mov     rdi, [rsp+78h+arg_10]
0x18004b69c  mov     rax, [rdi]
0x18004b69f  mov     rbx, [rax+28h]
0x18004b6a3  xor     edx, edx; length
0x18004b6a5  mov     rcx, [r14+60h]; string
0x18004b6a9  call    cs:__imp_WindowsGetStringRawBuffer
0x18004b6af  lea     r8, [rsp+78h+var_38]
0x18004b6b4  mov     rdx, rax
0x18004b6b7  mov     rcx, rdi
0x18004b6ba  mov     rax, rbx
0x18004b6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6c2  mov     rcx, [rsp+78h]; this
0x18004b6c7  test    eax, eax
0x18004b6c9  jnz     short loc_18004B6DC
0x18004b6cb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b6d2  mov     edx, 3CEh; void *
0x18004b6d7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004b6dc  mov     rbx, [rsp+78h+var_40]
0x18004b6e1  mov     rax, [rbx]
0x18004b6e4  mov     rdi, [rax+38h]
0x18004b6e8  lea     rcx, [rsp+78h+var_48]
0x18004b6ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b6f2  mov     rcx, [rsp+78h+arg_10]
0x18004b6fa  mov     rax, [rcx]
0x18004b6fd  mov     rdx, [rsp+78h+var_38]
0x18004b702  mov     rax, [rax+40h]
0x18004b706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b70b  lea     r9, [rsp+78h+var_48]
0x18004b710  mov     r8d, eax
0x18004b713  mov     rdx, [rsp+78h+var_38]
0x18004b718  mov     rcx, rbx
0x18004b71b  mov     rax, rdi
0x18004b71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b723  mov     rcx, [rsp+78h]; this
0x18004b728  test    eax, eax
0x18004b72a  jns     short loc_18004B740
0x18004b72c  mov     r9d, eax; char *
0x18004b72f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b736  mov     edx, 3CFh; void *
0x18004b73b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b740  mov     rdi, [rsp+78h+var_48]
0x18004b745  mov     rax, [rdi]
0x18004b748  mov     rbx, [rax+18h]
0x18004b74c  lea     rcx, [rsp+78h+arg_18]
0x18004b754  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b759  lea     rdx, [rsp+78h+arg_18]
0x18004b761  mov     rcx, rdi
0x18004b764  mov     rax, rbx
0x18004b767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b76c  mov     rcx, [rsp+78h]; this
0x18004b771  test    eax, eax
0x18004b773  jns     short loc_18004B789
0x18004b775  mov     r9d, eax; char *
0x18004b778  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b77f  mov     edx, 3D0h; void *
0x18004b784  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b789  mov     rcx, [rsp+78h+string]; string
0x18004b791  call    cs:__imp_WindowsDeleteString
0x18004b797  mov     [rsp+78h+string], r12
0x18004b79f  lea     r9, [rsp+78h+string]; HSTRING *
0x18004b7a7  lea     r8, PKEY_Identity_PrimaryEmailAddress; struct _tagpropertykey *
0x18004b7ae  mov     rdx, [rsp+78h+arg_18]; struct IPropertyStore *
0x18004b7b6  call    ?GetPropertyAsString@UserProfile@Internal@System@Windows@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserProfile::GetPropertyAsString(IPropertyStore *,_tagpropertykey const &,HSTRING__ * *)
0x18004b7bb  mov     rcx, [rsp+78h]; this
0x18004b7c0  test    eax, eax
0x18004b7c2  jns     short loc_18004B7D8
0x18004b7c4  mov     r9d, eax; char *
0x18004b7c7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b7ce  mov     edx, 3D1h; void *
0x18004b7d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b7d8  mov     rcx, [rsp+78h+string]; string
0x18004b7e0  call    cs:__imp_WindowsGetStringLen
0x18004b7e6  test    eax, eax
0x18004b7e8  jnz     short loc_18004B839
0x18004b7ea  mov     rcx, [rsp+78h+string]; string
0x18004b7f2  call    cs:__imp_WindowsDeleteString
0x18004b7f8  mov     [rsp+78h+string], r12
0x18004b800  lea     r9, [rsp+78h+string]; HSTRING *
0x18004b808  lea     r8, PKEY_Identity_UserName; struct _tagpropertykey *
0x18004b80f  mov     rdx, [rsp+78h+arg_18]; struct IPropertyStore *
0x18004b817  call    ?GetPropertyAsString@UserProfile@Internal@System@Windows@@AEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserProfile::GetPropertyAsString(IPropertyStore *,_tagpropertykey const &,HSTRING__ * *)
0x18004b81c  mov     rcx, [rsp+78h]; this
0x18004b821  test    eax, eax
0x18004b823  jns     short loc_18004B839
0x18004b825  mov     r9d, eax; char *
0x18004b828  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b82f  mov     edx, 3D4h; void *
0x18004b834  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b839  mov     rcx, [rsp+78h+string]
0x18004b841  test    rcx, rcx
0x18004b844  jz      short loc_18004B8C3
0x18004b846  lea     rbx, [r14+48h]
0x18004b84a  mov     rcx, [rbx]; string
0x18004b84d  call    cs:__imp_WindowsDeleteString
0x18004b853  mov     [rbx], r12
0x18004b856  mov     rdx, rbx; newString
0x18004b859  mov     rcx, [rsp+78h+string]; string
0x18004b861  call    cs:__imp_WindowsDuplicateString
0x18004b867  mov     rcx, [rsp+78h]; this
0x18004b86c  test    eax, eax
0x18004b86e  jns     short loc_18004B884
0x18004b870  mov     r9d, eax; char *
0x18004b873  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b87a  mov     edx, 3D9h; void *
0x18004b87f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b884  mov     rdx, r15; newString
0x18004b887  mov     rcx, [rsp+78h+string]; string
0x18004b88f  call    cs:__imp_WindowsDuplicateString
0x18004b895  mov     rcx, [rsp+78h]; this
0x18004b89a  test    eax, eax
0x18004b89c  jns     short loc_18004B8B2
0x18004b89e  mov     r9d, eax; char *
0x18004b8a1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x18004b8a8  mov     edx, 3DAh; void *
0x18004b8ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004b8b2  lea     rcx, [r14-18h]; this
0x18004b8b6  call    ?PersistEmailAddress@UserProfile@Internal@System@Windows@@AEAAJXZ; Windows::System::Internal::UserProfile::PersistEmailAddress(void)
0x18004b8bb  mov     rcx, [rsp+78h+string]; string
0x18004b8c3  call    cs:__imp_WindowsDeleteString
0x18004b8c9  mov     [rsp+78h+string], r12
0x18004b8d1  lea     rcx, [rsp+78h+arg_10]
0x18004b8d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b8de  nop
0x18004b8df  lea     rcx, [rsp+78h+arg_18]
0x18004b8e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b8ec  nop
0x18004b8ed  lea     rcx, [rsp+78h+var_48]
0x18004b8f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b8f7  nop
0x18004b8f8  mov     rcx, [rsp+78h+var_40]
0x18004b8fd  test    rcx, rcx
0x18004b900  jz      short loc_18004B914
0x18004b902  mov     [rsp+78h+var_40], r12
0x18004b907  mov     rax, [rcx]
0x18004b90a  mov     rax, [rax+10h]
0x18004b90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b913  nop
0x18004b914  xor     eax, eax
0x18004b916  jmp     short loc_18004B91F
0x18004b918  mov     eax, dword ptr [rsp+78h+string]
0x18004b91f  mov     rbx, [rsp+78h+arg_0]
0x18004b927  add     rsp, 50h
0x18004b92b  pop     r15
0x18004b92d  pop     r14
0x18004b92f  pop     r12
0x18004b931  pop     rdi
0x18004b932  pop     rsi
0x18004b933  retn
```
