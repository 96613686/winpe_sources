# Windows::System::Internal::UserProfile::RuntimeClassInitialize(uint,HKEY__ *,HSTRING__ *,uchar,ulong,uchar)

- ea: `0x1800cef78`
- end: `0x1800cf44a`
- name: `?RuntimeClassInitialize@UserProfile@Internal@System@Windows@@QEAAJIPEAUHKEY__@@PEAUHSTRING__@@EKE@Z`
- size: `1234`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserProfile *__hidden this@<rcx>, unsigned int@<edx>, HKEY@<r8>, HSTRING@<r9>, unsigned __int8, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063504`

## callees

- `0x180003fb8`
- `0x18000407c`
- `0x18000acdc`
- `0x18000ce48`
- `0x180012890`
- `0x1800181f0`
- `0x180041bb0`
- `0x18004b4a8`
- `0x18004ba28`
- `0x18004cef4`
- `0x18004cf48`
- `0x18004e134`
- `0x18004e508`
- `0x18004ea38`
- `0x180050c38`
- `0x1800513d0`
- `0x1800cef78`
- `0x1800de450`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800cf10e`
- `msvcrt!wcsstr` at `0x1800cf10e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ceff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf0a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf0fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ceff1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf0a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf0fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf302`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800cf1b4`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800cf1b4`

## string_xrefs

- `0x1800cf38f`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf3a4`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf3b8`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf3cf`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf3e3`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf3f8`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf40d`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf422`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`
- `0x1800cf437`: `onecore\ds\security\umstartup\usermgr\lib\userprofile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::System::Internal::UserProfile::RuntimeClassInitialize(
        Windows::System::Internal::UserProfile *this,
        unsigned int a2,
        WCHAR *a3,
        HSTRING a4,
        unsigned __int8 a5,
        unsigned int a6,
        unsigned __int8 a7)
{
  HKEY v8; // rbx
  unsigned int v9; // r15d
  Windows::System::Internal::UserProfile *v10; // rsi
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  unsigned __int8 v13; // r13
  unsigned int v14; // r12d
  int v15; // r8d
  int v16; // r9d
  HSTRING *v17; // r14
  int v18; // eax
  const unsigned __int16 *v19; // rax
  const char *v20; // r9
  const wchar_t *v21; // rax
  int v22; // eax
  HSTRING v23; // r8
  unsigned int v24; // eax
  int v25; // eax
  int v26; // eax
  HSTRING v27; // rbx
  int v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  const struct _tlgProvider_t *v31; // rbx
  int v32; // r8d
  int v33; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v35; // rax
  int v36; // ebx
  wil *v37; // rcx
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // [rsp+20h] [rbp-D8h]
  unsigned __int8 v41; // [rsp+50h] [rbp-A8h] BYREF
  _BYTE v42[3]; // [rsp+51h] [rbp-A7h] BYREF
  unsigned int v43; // [rsp+54h] [rbp-A4h] BYREF
  unsigned int v44; // [rsp+58h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+60h] [rbp-98h] BYREF
  PCWSTR v46; // [rsp+68h] [rbp-90h] BYREF
  __int64 v47; // [rsp+70h] [rbp-88h] BYREF
  HSTRING v48; // [rsp+78h] [rbp-80h] BYREF
  PCWSTR StringRawBuffer; // [rsp+80h] [rbp-78h] BYREF
  Windows::System::Internal::UserProfile *v50; // [rsp+88h] [rbp-70h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-68h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  string = a4;
  v8 = (HKEY)a3;
  v9 = a2;
  v10 = this;
  v50 = this;
  v46 = a3;
  v48 = a4;
  v11 = UserMgrUserModelTelemetry::Provider();
  v12 = (int)v11;
  v13 = a7;
  if ( *(_DWORD *)v11 <= 5u )
  {
    v14 = a6;
  }
  else
  {
    v41 = a7;
    v14 = a6;
    v43 = a6;
    StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
    v44 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v12,
      (unsigned int)&dword_18012DBFC,
      v15,
      v16,
      (__int64)&v44,
      (__int64)&StringRawBuffer,
      (__int64)&v43,
      (__int64)&v41);
  }
  try
  {
    if ( v9 - 16 > 0xFFFEF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)0x80070057LL,
        v40);
    *((_DWORD *)v10 + 21) = v9;
    v47 = 0;
    v42[0] = 0;
    v17 = (HSTRING *)((char *)v10 + 88);
    StringRawBuffer = (PCWSTR)((char *)v10 + 88);
    v18 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v10 + 11, &v48);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v18,
        v40);
    v19 = WindowsGetStringRawBuffer(string, 0);
    try
    {
      Windows::System::Internal::UserProfile::InitSidAndAccountType(v10, v19);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        v20);
      v13 = a7;
      v14 = a6;
      v9 = a2;
      v10 = v50;
      v8 = (HKEY)v46;
      string = v48;
      v17 = (HSTRING *)StringRawBuffer;
    }
    if ( v13 || (v21 = WindowsGetStringRawBuffer(*v17, 0), wcsstr(v21, L"@")) )
    {
      v22 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v10 + 12, &v48);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v22,
          v40);
      if ( !*((_BYTE *)v10 + 80) )
        Windows::System::Internal::UserProfile::CreateConnectedProfile((HSTRING *)v10);
    }
    else
    {
      Windows::System::Internal::UserProfile::CreateNTProfile(v10);
    }
    Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(v8, L"ProfileName", *v17);
    v23 = (HSTRING)*((_QWORD *)v10 + 15);
    if ( !v23 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)0x8000FFFFLL,
        v40);
    Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(v8, L"Sid", v23);
    Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(
      v8,
      L"EmailAddress",
      *((HSTRING *)v10 + 12));
    *((_DWORD *)v10 + 33) = v14;
    Windows::System::Internal::Implementation::RegUtil::WriteValue<unsigned long>(v8, L"UserTypeInternal", v14);
    v24 = RegFlushKey(v8);
    if ( v24 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)v24,
        v40);
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.PropertySet",
      0x2Bu,
      0x2Au);
    v25 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
            v52,
            (_QWORD *)v10 + 14);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v25,
        v40);
    v26 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v10 + 14,
            (__int64)&v47);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v26,
        v40);
    v27 = *v17;
    v52 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProfileName", 0xCu, 0xBu);
    v28 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
            v47,
            v52,
            (__int64)v27,
            (__int64)v42);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
        (const char *)(unsigned int)v28,
        v40);
    v29 = *((_QWORD *)v10 + 15);
    if ( v29 )
    {
      v52 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Sid", 4u, 3u);
      v30 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v47,
              v52,
              v29,
              (__int64)v42);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBB,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userprofile.cpp",
          (const char *)(unsigned int)v30,
          v40);
    }
    v31 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v31 > 5u )
    {
      v44 = 0;
      v41 = v13;
      v43 = v14;
      v46 = WindowsGetStringRawBuffer(string, 0);
      LODWORD(string) = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        (_DWORD)v31,
        (unsigned int)byte_18012DA93,
        v32,
        v33,
        (__int64)&string,
        (__int64)&v46,
        (__int64)&v43,
        (__int64)&v41,
        (__int64)&v44);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    result = 0;
  }
  catch ( ... )
  {
    v35 = UserMgrUserModelTelemetry::Provider();
    v36 = (int)v35;
    v37 = (wil *)*(unsigned int *)v35;
    if ( (unsigned int)v37 > 5 )
    {
      LODWORD(string) = wil::ResultFromCaughtException(v37);
      v41 = a7;
      v44 = a6;
      v46 = WindowsGetStringRawBuffer(v48, 0);
      v43 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        v36,
        (unsigned int)&unk_18012DA08,
        v38,
        v39,
        (__int64)&v43,
        (__int64)&v46,
        (__int64)&v44,
        (__int64)&v41,
        (__int64)&string);
    }
    return (unsigned int)wil::ResultFromCaughtException(v37);
  }
  return result;
}

```

## disassembly

```asm
0x1800cef78  mov     [rsp+arg_8], edx
0x1800cef7c  push    rbx
0x1800cef7d  push    rsi
0x1800cef7e  push    rdi
0x1800cef7f  push    r12
0x1800cef81  push    r13
0x1800cef83  push    r14
0x1800cef85  push    r15
0x1800cef87  sub     rsp, 0C0h
0x1800cef8e  mov     rax, cs:__security_cookie
0x1800cef95  xor     rax, rsp
0x1800cef98  mov     [rsp+0F8h+var_48], rax
0x1800cefa0  mov     r14, r9
0x1800cefa3  mov     [rsp+0F8h+string], r9
0x1800cefa8  mov     rbx, r8
0x1800cefab  mov     r15d, edx
0x1800cefae  mov     rsi, rcx
0x1800cefb1  mov     [rsp+0F8h+var_70], rcx
0x1800cefb9  mov     [rsp+0F8h+var_90], rbx
0x1800cefbe  mov     [rsp+0F8h+var_80], r9
0x1800cefc3  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800cefc8  mov     rdi, rax
0x1800cefcb  mov     edx, [rax]
0x1800cefcd  cmp     edx, 5
0x1800cefd0  jbe     short loc_1800CF040
0x1800cefd2  mov     r13b, [rsp+0F8h+arg_30]
0x1800cefda  mov     [rsp+0F8h+var_A8], r13b
0x1800cefdf  mov     r12d, [rsp+0F8h+arg_28]
0x1800cefe7  mov     [rsp+0F8h+var_A4], r12d
0x1800cefec  xor     edx, edx; length
0x1800cefee  mov     rcx, r14; string
0x1800ceff1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ceff7  mov     [rsp+0F8h+var_78], rax
0x1800cefff  mov     [rsp+0F8h+var_A0], r15d
0x1800cf004  lea     rax, [rsp+0F8h+var_A8]
0x1800cf009  mov     [rsp+0F8h+var_C0], rax
0x1800cf00e  lea     rax, [rsp+0F8h+var_A4]
0x1800cf013  mov     [rsp+0F8h+var_C8], rax
0x1800cf018  lea     rax, [rsp+0F8h+var_78]
0x1800cf020  mov     [rsp+0F8h+var_D0], rax
0x1800cf025  lea     rax, [rsp+0F8h+var_A0]
0x1800cf02a  mov     [rsp+0F8h+var_D8], rax
0x1800cf02f  lea     rdx, dword_18012DBFC
0x1800cf036  mov     rcx, rdi
0x1800cf039  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1800cf03e  jmp     short loc_1800CF050
0x1800cf040  mov     r13b, [rsp+0F8h+arg_30]
0x1800cf048  mov     r12d, [rsp+0F8h+arg_28]
0x1800cf050  mov     rcx, [rsp+0F8h]; this
0x1800cf058  lea     eax, [r15-10h]
0x1800cf05c  cmp     eax, 0FFFEFh
0x1800cf061  ja      loc_1800CF389
0x1800cf067  mov     [rsi+54h], r15d
0x1800cf06b  xor     edi, edi
0x1800cf06d  mov     [rsp+0F8h+var_88], rdi
0x1800cf072  mov     [rsp+0F8h+var_A7], dil
0x1800cf077  lea     r14, [rsi+58h]
0x1800cf07b  mov     [rsp+0F8h+var_78], r14
0x1800cf083  lea     rdx, [rsp+0F8h+var_80]; HSTRING *
0x1800cf088  mov     rcx, r14; newString
0x1800cf08b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800cf090  mov     rcx, [rsp+0F8h]; this
0x1800cf098  test    eax, eax
0x1800cf09a  js      loc_1800CF3A1
0x1800cf0a0  xor     edx, edx; length
0x1800cf0a2  mov     rcx, [rsp+0F8h+string]; string
0x1800cf0a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf0ad  mov     rdx, rax; unsigned __int16 *
0x1800cf0b0  mov     rcx, rsi; this
0x1800cf0b3  call    ?InitSidAndAccountType@UserProfile@Internal@System@Windows@@AEAAJPEBG@Z; Windows::System::Internal::UserProfile::InitSidAndAccountType(ushort const *)
0x1800cf0b8  nop
0x1800cf0b9  jmp     short loc_1800CF0F4
0x1800cf0bb  xor     edi, edi
0x1800cf0bd  mov     r13b, [rsp+0F8h+arg_30]
0x1800cf0c5  mov     r12d, [rsp+0F8h+arg_28]
0x1800cf0cd  mov     r15d, [rsp+0F8h+arg_8]
0x1800cf0d5  mov     rsi, [rsp+0F8h+var_70]
0x1800cf0dd  mov     rbx, [rsp+0F8h+var_90]
0x1800cf0e2  mov     rax, [rsp+0F8h+var_80]
0x1800cf0e7  mov     [rsp+0F8h+string], rax
0x1800cf0ec  mov     r14, [rsp+0F8h+var_78]
0x1800cf0f4  test    r13b, r13b
0x1800cf0f7  jnz     short loc_1800CF123
0x1800cf0f9  xor     edx, edx; length
0x1800cf0fb  mov     rcx, [r14]; string
0x1800cf0fe  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf104  lea     rdx, asc_1801118C4; "@"
0x1800cf10b  mov     rcx, rax; Str
0x1800cf10e  call    cs:__imp_wcsstr
0x1800cf114  test    rax, rax
0x1800cf117  jnz     short loc_1800CF123
0x1800cf119  mov     rcx, rsi; this
0x1800cf11c  call    ?CreateNTProfile@UserProfile@Internal@System@Windows@@AEAAJXZ; Windows::System::Internal::UserProfile::CreateNTProfile(void)
0x1800cf121  jmp     short loc_1800CF14F
0x1800cf123  lea     rcx, [rsi+60h]; newString
0x1800cf127  lea     rdx, [rsp+0F8h+var_80]; HSTRING *
0x1800cf12c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800cf131  mov     rcx, [rsp+0F8h]; this
0x1800cf139  test    eax, eax
0x1800cf13b  js      loc_1800CF3B5
0x1800cf141  cmp     [rsi+50h], dil
0x1800cf145  jnz     short loc_1800CF14F
0x1800cf147  mov     rcx, rsi; this
0x1800cf14a  call    ?CreateConnectedProfile@UserProfile@Internal@System@Windows@@AEAAJXZ; Windows::System::Internal::UserProfile::CreateConnectedProfile(void)
0x1800cf14f  mov     r8, [r14]
0x1800cf152  lea     rdx, aProfilename_0; "ProfileName"
0x1800cf159  mov     rcx, rbx
0x1800cf15c  call    ??$WriteValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ *)
0x1800cf161  mov     r8, [rsi+78h]
0x1800cf165  mov     rcx, [rsp+0F8h]; this
0x1800cf16d  test    r8, r8
0x1800cf170  jz      loc_1800CF3C9
0x1800cf176  lea     rdx, aSid_2; "Sid"
0x1800cf17d  mov     rcx, rbx
0x1800cf180  call    ??$WriteValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ *)
0x1800cf185  mov     r8, [rsi+60h]
0x1800cf189  lea     rdx, aEmailaddress; "EmailAddress"
0x1800cf190  mov     rcx, rbx
0x1800cf193  call    ??$WriteValue@PEAUHSTRING__@@@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGPEAUHSTRING__@@@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<HSTRING__ *>(HKEY__ *,ushort const *,HSTRING__ *)
0x1800cf198  mov     [rsi+84h], r12d
0x1800cf19f  mov     r8d, r12d
0x1800cf1a2  lea     rdx, aUsertypeintern_0; "UserTypeInternal"
0x1800cf1a9  mov     rcx, rbx
0x1800cf1ac  call    ??$WriteValue@K@RegUtil@Implementation@Internal@System@Windows@@SAJPEAUHKEY__@@PEBGK@Z; Windows::System::Internal::Implementation::RegUtil::WriteValue<ulong>(HKEY__ *,ushort const *,ulong)
0x1800cf1b1  mov     rcx, rbx; hKey
0x1800cf1b4  call    cs:__imp_RegFlushKey
0x1800cf1ba  mov     rcx, [rsp+0F8h]; this
0x1800cf1c2  test    eax, eax
0x1800cf1c4  jnz     loc_1800CF3E0
0x1800cf1ca  mov     [rsp+0F8h+var_50], rdi
0x1800cf1d2  mov     r9d, 2Ah ; '*'; unsigned int
0x1800cf1d8  lea     r8d, [r9+1]; unsigned int
0x1800cf1dc  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x1800cf1e3  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x1800cf1eb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800cf1f0  nop
0x1800cf1f1  lea     rdx, [rsi+70h]
0x1800cf1f5  mov     rcx, [rsp+0F8h+var_50]
0x1800cf1fd  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x1800cf202  mov     rcx, [rsp+0F8h]; this
0x1800cf20a  test    eax, eax
0x1800cf20c  js      loc_1800CF3F5
0x1800cf212  lea     rdx, [rsp+0F8h+var_88]
0x1800cf217  lea     rcx, [rsi+70h]
0x1800cf21b  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800cf220  mov     rcx, [rsp+0F8h]; this
0x1800cf228  test    eax, eax
0x1800cf22a  js      loc_1800CF40A
0x1800cf230  mov     rbx, [r14]
0x1800cf233  mov     [rsp+0F8h+var_50], rdi
0x1800cf23b  mov     r9d, 0Bh; unsigned int
0x1800cf241  lea     r8d, [r9+1]; unsigned int
0x1800cf245  lea     rdx, aProfilename_0; "ProfileName"
0x1800cf24c  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x1800cf254  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800cf259  nop
0x1800cf25a  lea     r9, [rsp+0F8h+var_A7]
0x1800cf25f  mov     r8, rbx
0x1800cf262  mov     rdx, [rsp+0F8h+var_50]
0x1800cf26a  mov     rcx, [rsp+0F8h+var_88]
0x1800cf26f  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800cf274  mov     rcx, [rsp+0F8h]; this
0x1800cf27c  test    eax, eax
0x1800cf27e  js      loc_1800CF41F
0x1800cf284  mov     rbx, [rsi+78h]
0x1800cf288  test    rbx, rbx
0x1800cf28b  jz      short loc_1800CF2DE
0x1800cf28d  mov     [rsp+0F8h+var_50], rdi
0x1800cf295  mov     r9d, 3; unsigned int
0x1800cf29b  lea     r8d, [r9+1]; unsigned int
0x1800cf29f  lea     rdx, aSid_2; "Sid"
0x1800cf2a6  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x1800cf2ae  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800cf2b3  nop
0x1800cf2b4  lea     r9, [rsp+0F8h+var_A7]
0x1800cf2b9  mov     r8, rbx
0x1800cf2bc  mov     rdx, [rsp+0F8h+var_50]
0x1800cf2c4  mov     rcx, [rsp+0F8h+var_88]
0x1800cf2c9  call    ??$IntoPropertyMap@PEAUHSTRING__@@@ComUtils@Implementation@Internal@System@Windows@@SAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@4@PEAUHSTRING__@@1PEAE@Z; Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,uchar *)
0x1800cf2ce  mov     rcx, [rsp+0F8h]; this
0x1800cf2d6  test    eax, eax
0x1800cf2d8  js      loc_1800CF434
0x1800cf2de  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800cf2e3  mov     rbx, rax
0x1800cf2e6  mov     edx, [rax]
0x1800cf2e8  cmp     edx, 5
0x1800cf2eb  jbe     short loc_1800CF354
0x1800cf2ed  mov     [rsp+0F8h+var_A0], edi
0x1800cf2f1  mov     [rsp+0F8h+var_A8], r13b
0x1800cf2f6  mov     [rsp+0F8h+var_A4], r12d
0x1800cf2fb  xor     edx, edx; length
0x1800cf2fd  mov     rcx, [rsp+0F8h+string]; string
0x1800cf302  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cf308  mov     [rsp+0F8h+var_90], rax
0x1800cf30d  mov     dword ptr [rsp+0F8h+string], r15d
0x1800cf312  lea     rax, [rsp+0F8h+var_A0]
0x1800cf317  mov     [rsp+0F8h+var_B8], rax
0x1800cf31c  lea     rax, [rsp+0F8h+var_A8]
0x1800cf321  mov     [rsp+0F8h+var_C0], rax
0x1800cf326  lea     rax, [rsp+0F8h+var_A4]
0x1800cf32b  mov     [rsp+0F8h+var_C8], rax
0x1800cf330  lea     rax, [rsp+0F8h+var_90]
0x1800cf335  mov     [rsp+0F8h+var_D0], rax
0x1800cf33a  lea     rax, [rsp+0F8h+string]
0x1800cf33f  mov     [rsp+0F8h+var_D8], rax
0x1800cf344  lea     rdx, byte_18012DA93
0x1800cf34b  mov     rcx, rbx
0x1800cf34e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x1800cf353  nop
0x1800cf354  lea     rcx, [rsp+0F8h+var_88]
0x1800cf359  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cf35e  xor     eax, eax
0x1800cf360  jmp     short loc_1800CF366
0x1800cf362  mov     eax, dword ptr [rsp+0F8h+string]
0x1800cf366  mov     rcx, [rsp+0F8h+var_48]
0x1800cf36e  xor     rcx, rsp; StackCookie
0x1800cf371  call    __security_check_cookie
0x1800cf376  add     rsp, 0C0h
0x1800cf37d  pop     r15
0x1800cf37f  pop     r14
0x1800cf381  pop     r13
0x1800cf383  pop     r12
0x1800cf385  pop     rdi
0x1800cf386  pop     rsi
0x1800cf387  pop     rbx
0x1800cf388  retn
0x1800cf389  mov     r9d, 80070057h; char *
0x1800cf38f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf396  mov     edx, 8Ah; void *
0x1800cf39b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf3a1  mov     r9d, eax; char *
0x1800cf3a4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf3ab  mov     edx, 90h; void *
0x1800cf3b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf3b5  mov     r9d, eax; char *
0x1800cf3b8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf3bf  mov     edx, 9Bh; void *
0x1800cf3c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf3c9  mov     r9d, 8000FFFFh; char *
0x1800cf3cf  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf3d6  mov     edx, 0AAh; void *
0x1800cf3db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf3e0  mov     r9d, eax; char *
0x1800cf3e3  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf3ea  mov     edx, 0B1h; void *
0x1800cf3ef  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800cf3f5  mov     r9d, eax; char *
0x1800cf3f8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf3ff  mov     edx, 0B5h; void *
0x1800cf404  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf40a  mov     r9d, eax; char *
0x1800cf40d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf414  mov     edx, 0B7h; void *
0x1800cf419  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf41f  mov     r9d, eax; char *
0x1800cf422  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf429  mov     edx, 0B8h; void *
0x1800cf42e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cf434  mov     r9d, eax; char *
0x1800cf437  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\umstartup\\userm"...
0x1800cf43e  mov     edx, 0BBh; void *
0x1800cf443  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
