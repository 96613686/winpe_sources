# Windows::System::Internal::UserManagerStatics::GetUserProperty(unsigned __int64,HSTRING__ *,IInspectable * *)

- ea: `0x180093d60`
- end: `0x180093fda`
- name: `?GetUserProperty@UserManagerStatics@Internal@System@Windows@@UEAAJ_KPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `634`
- prototype: `int(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned __int64, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800010dc`
- `0x1800013a4`
- `0x180006130`
- `0x180007920`
- `0x18000acdc`
- `0x180012890`
- `0x1800391d4`
- `0x18003b578`
- `0x18005286c`
- `0x1800641b8`
- `0x180066f6c`
- `0x180093d60`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093ef2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093d97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093ef2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ebd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ebd`

## string_xrefs

- `0x180093f65`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093f7a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093f8e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093fa2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180093fc7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::System::Internal::UserManagerStatics::GetUserProperty(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned __int64 a2,
        HSTRING a3,
        struct IInspectable **a4)
{
  const struct _tlgProvider_t *v8; // rax
  int v9; // ebx
  int v10; // r8d
  int v11; // r9d
  int UserForContext; // eax
  int v13; // eax
  int v14; // ebx
  struct IInspectable **v15; // rax
  struct IInspectable *v16; // rcx
  const struct _tlgProvider_t *v17; // rbx
  int v18; // r8d
  int v19; // r9d
  __int64 result; // rax
  unsigned int v21; // eax
  const struct _tlgProvider_t *v22; // rax
  int v23; // ebx
  wil *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  int v27; // [rsp+20h] [rbp-78h]
  struct Windows::System::IUser *v28; // [rsp+40h] [rbp-58h] BYREF
  __int64 v29; // [rsp+48h] [rbp-50h] BYREF
  int v30[2]; // [rsp+50h] [rbp-48h] BYREF
  PCWSTR v31; // [rsp+58h] [rbp-40h] BYREF
  HSTRING string; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  PCWSTR StringRawBuffer; // [rsp+B8h] [rbp+20h] BYREF

  v8 = UserMgrUserModelTelemetry::Provider();
  v9 = (int)v8;
  if ( *(_DWORD *)v8 > 5u )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    *(_QWORD *)v30 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      v9,
      (unsigned int)&byte_180124C67,
      v10,
      v11,
      (__int64)v30,
      (__int64)&StringRawBuffer);
  }
  try
  {
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19D4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v27);
    *a4 = 0;
    v28 = 0;
    v29 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    UserForContext = Windows::System::Internal::UserManagerStatics::GetUserForContext(
                       (Windows::System::Internal::UserManagerStatics *)((char *)this - 128),
                       a2,
                       &v28,
                       1);
    if ( UserForContext < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19DA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)UserForContext,
        v27);
    v13 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v28,
            &v29);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19DB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v13,
        v27);
    v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct IInspectable **))(*(_QWORD *)v29 + 152LL))(v29, a3, a4);
    if ( v14 == -2147023728 )
    {
      Windows::System::Internal::GetUnknownUserPropertyValueFromWebAccount((Windows::System::Internal *)&v31, a2, a3);
      if ( !(_BYTE)v31 )
      {
        v21 = wil::verify_hresult<long>(2147943568LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19EA,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)v21,
          v27);
      }
      v15 = (struct IInspectable **)Windows::System::Internal::CreatePropertyValue(&StringRawBuffer, string);
      v16 = *v15;
      *v15 = 0;
      *a4 = v16;
      wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&StringRawBuffer);
      v14 = 0;
      WindowsDeleteString(string);
    }
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x19ED,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v14,
        v27);
    v17 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v17 > 5u )
    {
      LODWORD(StringRawBuffer) = 0;
      *(_QWORD *)v30 = WindowsGetStringRawBuffer(a3, 0);
      v31 = (PCWSTR)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v17,
        (unsigned int)&dword_180124C1C,
        v18,
        v19,
        (__int64)&v31,
        (__int64)v30,
        (__int64)&StringRawBuffer);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
    result = 0;
  }
  catch ( ... )
  {
    v22 = UserMgrUserModelTelemetry::Provider();
    v23 = (int)v22;
    v24 = (wil *)*(unsigned int *)v22;
    if ( (unsigned int)v24 > 5 )
    {
      LODWORD(StringRawBuffer) = wil::ResultFromCaughtException(v24);
      v31 = WindowsGetStringRawBuffer(a3, 0);
      *(_QWORD *)v30 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)&word_180124BBE,
        v25,
        v26,
        (__int64)v30,
        (__int64)&v31,
        (__int64)&StringRawBuffer);
    }
    LODWORD(StringRawBuffer) = wil::ResultFromCaughtException(v24);
    return (unsigned int)StringRawBuffer;
  }
  return result;
}

```

## disassembly

```asm
0x180093d60  mov     [rsp+arg_10], r8
0x180093d65  mov     [rsp+arg_8], rdx
0x180093d6a  push    rbx
0x180093d6b  push    rsi
0x180093d6c  push    rdi
0x180093d6d  push    r14
0x180093d6f  push    r15
0x180093d71  sub     rsp, 70h
0x180093d75  mov     r14, r9
0x180093d78  mov     rsi, r8
0x180093d7b  mov     rdi, rdx
0x180093d7e  mov     r15, rcx
0x180093d81  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180093d86  mov     rbx, rax
0x180093d89  mov     r10d, [rax]
0x180093d8c  cmp     r10d, 5
0x180093d90  jbe     short loc_180093DD0
0x180093d92  xor     edx, edx; length
0x180093d94  mov     rcx, rsi; string
0x180093d97  call    cs:__imp_WindowsGetStringRawBuffer
0x180093d9d  mov     [rsp+98h+arg_18], rax
0x180093da5  mov     qword ptr [rsp+98h+var_48], rdi
0x180093daa  lea     rax, [rsp+98h+arg_18]
0x180093db2  mov     [rsp+98h+var_70], rax
0x180093db7  lea     rax, [rsp+98h+var_48]
0x180093dbc  mov     qword ptr [rsp+98h+var_78], rax; int
0x180093dc1  lea     rdx, byte_180124C67
0x180093dc8  mov     rcx, rbx
0x180093dcb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x180093dd0  mov     rcx, [rsp+98h]; this
0x180093dd8  test    r14, r14
0x180093ddb  jz      loc_180093F5F
0x180093de1  mov     qword ptr [r14], 0
0x180093de8  mov     [rsp+98h+var_58], 0
0x180093df1  mov     [rsp+98h+var_50], 0
0x180093dfa  lea     rcx, [rsp+98h+var_58]
0x180093dff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180093e04  lea     rcx, [r15-80h]; this
0x180093e08  mov     r9b, 1; bool
0x180093e0b  lea     r8, [rsp+98h+var_58]; struct Windows::System::IUser **
0x180093e10  mov     rdx, rdi; unsigned __int64
0x180093e13  call    ?GetUserForContext@UserManagerStatics@Internal@System@Windows@@AEAAJ_KPEAPEAUIUser@34@_N@Z; Windows::System::Internal::UserManagerStatics::GetUserForContext(unsigned __int64,Windows::System::IUser * *,bool)
0x180093e18  mov     rcx, [rsp+98h]; this
0x180093e20  test    eax, eax
0x180093e22  js      loc_180093F77
0x180093e28  lea     rdx, [rsp+98h+var_50]
0x180093e2d  lea     rcx, [rsp+98h+var_58]
0x180093e32  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180093e37  mov     rcx, [rsp+98h]; this
0x180093e3f  test    eax, eax
0x180093e41  js      loc_180093F8B
0x180093e47  mov     rcx, [rsp+98h+var_50]
0x180093e4c  mov     rax, [rcx]
0x180093e4f  mov     r8, r14
0x180093e52  mov     rdx, rsi
0x180093e55  mov     rax, [rax+98h]
0x180093e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e61  mov     ebx, eax
0x180093e63  mov     r15d, 80070490h
0x180093e69  cmp     eax, r15d
0x180093e6c  jnz     short loc_180093EC3
0x180093e6e  mov     r8, rsi; HSTRING
0x180093e71  mov     rdx, rdi; unsigned __int64
0x180093e74  lea     rcx, [rsp+98h+var_40]; this
0x180093e79  call    ?GetUnknownUserPropertyValueFromWebAccount@Internal@System@Windows@@YA@_KPEAUHSTRING__@@@Z; Windows::System::Internal::GetUnknownUserPropertyValueFromWebAccount(unsigned __int64,HSTRING__ *)
0x180093e7e  nop
0x180093e7f  cmp     byte ptr [rsp+98h+var_40], 0
0x180093e84  jz      loc_180093FB4
0x180093e8a  mov     rdx, [rsp+98h+string]
0x180093e8f  lea     rcx, [rsp+98h+arg_18]
0x180093e97  call    ?CreatePropertyValue@Internal@System@Windows@@YA?AV?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@PEAUHSTRING__@@@Z; Windows::System::Internal::CreatePropertyValue(HSTRING__ *)
0x180093e9c  mov     rcx, [rax]
0x180093e9f  mov     qword ptr [rax], 0
0x180093ea6  mov     [r14], rcx
0x180093ea9  lea     rcx, [rsp+98h+arg_18]
0x180093eb1  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180093eb6  xor     ebx, ebx
0x180093eb8  mov     rcx, [rsp+98h+string]; string
0x180093ebd  call    cs:__imp_WindowsDeleteString
0x180093ec3  mov     rcx, [rsp+98h]; this
0x180093ecb  test    ebx, ebx
0x180093ecd  js      loc_180093F9F
0x180093ed3  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180093ed8  mov     rbx, rax
0x180093edb  mov     ecx, [rax]
0x180093edd  cmp     ecx, 5
0x180093ee0  jbe     short loc_180093F33
0x180093ee2  mov     dword ptr [rsp+98h+arg_18], 0
0x180093eed  xor     edx, edx; length
0x180093eef  mov     rcx, rsi; string
0x180093ef2  call    cs:__imp_WindowsGetStringRawBuffer
0x180093ef8  mov     qword ptr [rsp+98h+var_48], rax
0x180093efd  mov     [rsp+98h+var_40], rdi
0x180093f02  lea     rax, [rsp+98h+arg_18]
0x180093f0a  mov     [rsp+98h+var_68], rax
0x180093f0f  lea     rax, [rsp+98h+var_48]
0x180093f14  mov     [rsp+98h+var_70], rax
0x180093f19  lea     rax, [rsp+98h+var_40]
0x180093f1e  mov     qword ptr [rsp+98h+var_78], rax
0x180093f23  lea     rdx, dword_180124C1C
0x180093f2a  mov     rcx, rbx
0x180093f2d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180093f32  nop
0x180093f33  lea     rcx, [rsp+98h+var_50]
0x180093f38  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180093f3d  nop
0x180093f3e  lea     rcx, [rsp+98h+var_58]
0x180093f43  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180093f48  xor     eax, eax
0x180093f4a  jmp     short loc_180093F53
0x180093f4c  mov     eax, dword ptr [rsp+98h+arg_18]
0x180093f53  add     rsp, 70h
0x180093f57  pop     r15
0x180093f59  pop     r14
0x180093f5b  pop     rdi
0x180093f5c  pop     rsi
0x180093f5d  pop     rbx
0x180093f5e  retn
0x180093f5f  mov     r9d, 80004003h; char *
0x180093f65  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093f6c  mov     edx, 19D4h; void *
0x180093f71  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093f77  mov     r9d, eax; char *
0x180093f7a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093f81  mov     edx, 19DAh; void *
0x180093f86  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093f8b  mov     r9d, eax; char *
0x180093f8e  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093f95  mov     edx, 19DBh; void *
0x180093f9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093f9f  mov     r9d, ebx; char *
0x180093fa2  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093fa9  mov     edx, 19EDh; void *
0x180093fae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180093fb4  mov     ecx, r15d
0x180093fb7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180093fbc  mov     r9d, eax; char *
0x180093fbf  mov     rcx, [rsp+98h]; this
0x180093fc7  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180093fce  mov     edx, 19EAh; void *
0x180093fd3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
