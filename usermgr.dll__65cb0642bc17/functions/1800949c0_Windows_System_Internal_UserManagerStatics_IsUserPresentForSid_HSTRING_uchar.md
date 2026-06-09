# Windows::System::Internal::UserManagerStatics::IsUserPresentForSid(HSTRING__ *,uchar *)

- ea: `0x1800949c0`
- end: `0x180094dc0`
- name: `?IsUserPresentForSid@UserManagerStatics@Internal@System@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `1024`
- prototype: `int(Windows::System::Internal::UserManagerStatics *__hidden this, HSTRING, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006130`
- `0x180007920`
- `0x180008b10`
- `0x18000a4a0`
- `0x18000acdc`
- `0x18000c254`
- `0x18000ca64`
- `0x18000ce48`
- `0x180011880`
- `0x180012890`
- `0x180015960`
- `0x180016c50`
- `0x1800332e8`
- `0x18006f1c9`
- `0x1800949c0`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180094bdf`
- `msvcrt!_wcsicmp` at `0x180094bdf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094a0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094a0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094b96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094b96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094cc7`

## string_xrefs

- `0x180094cf1`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d06`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d1a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d31`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d46`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d5a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d6f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d84`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094d99`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180094dad`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::System::Internal::UserManagerStatics::IsUserPresentForSid(
        Windows::System::Internal::UserManagerStatics *this,
        HSTRING a2,
        unsigned __int8 *a3)
{
  unsigned __int64 v3; // rbp
  const struct _tlgProvider_t *v7; // rax
  int v8; // ebx
  int v9; // r9d
  int v10; // eax
  int CallerInformationFromToken; // eax
  bool v12; // zf
  char v13; // al
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // rdi
  __int64 (__fastcall *v15)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, unsigned __int64); // rbx
  int v16; // eax
  int v17; // eax
  unsigned int i; // esi
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, unsigned __int64); // rbx
  int v23; // eax
  const wchar_t *StringRawBuffer; // rbx
  const wchar_t *v25; // rax
  int v26; // eax
  const struct _tlgProvider_t *v27; // rbx
  int v28; // r8d
  int v29; // r9d
  wil *v30; // rcx
  __int64 result; // rax
  _DWORD *v32; // rbp
  int v33; // ebx
  const struct _tlgProvider_t *v34; // rax
  int v35; // edi
  int v36; // r8d
  int v37; // r9d
  int v38; // [rsp+20h] [rbp-30h]
  int v39; // [rsp+50h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+228h]

  v3 = (unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = a2;
  v7 = UserMgrUserModelTelemetry::Provider();
  v8 = (int)v7;
  if ( *(_DWORD *)v7 > 4u )
  {
    *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = WindowsGetStringRawBuffer(a2, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v8,
      (unsigned int)byte_180124A33,
      0,
      v9,
      v3 + 8);
  }
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C35,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)0x80004003LL,
      v38);
  *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v3 + 40,
    0);
  try
  {
    v10 = GetCallerTokenFromComCall((PHANDLE)(v3 + 40));
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C38,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v10,
        v38);
    memset_0((void *)(v3 + 64), 0, 0x1A0u);
    CallerInformationFromToken = GetCallerInformationFromToken(
                                   *(HANDLE *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
                                   (struct _BASIC_CALLER_INFORMATION *)(v3 + 64),
                                   0);
    if ( CallerInformationFromToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C3A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)CallerInformationFromToken,
        v38);
    if ( !*(_BYTE *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x41)
      || (v12 = !HasSigninCapability(*(void **)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28)), v13 = 0, v12) )
    {
      v13 = 1;
    }
    if ( v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C3D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80070005LL,
        v38);
    *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    *(_DWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
    UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal((Windows::System::Internal::UserManagerStatics *)((char *)this - 104));
    v15 = *(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, unsigned __int64))(*(_QWORD *)UserStaticsInternal + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3 + 32);
    v16 = v15(UserStaticsInternal, v3 + 32);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C42,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v16,
        v38);
    v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v39
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x20)
                                                              + 56LL))(
            *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
            v3 + 4);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C43,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v17,
        v38);
    for ( i = 0; i < *(_DWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 4); ++i )
    {
      *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v39
                                                                                       & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                      + 0x20)
                                                                        + 48LL))(
              *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
              i,
              v3 + 24);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C48,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v19,
          v38);
      *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      v20 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v3 + 24),
              (__int64 *)(v3 + 8));
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C4A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v20,
          v38);
      *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      v21 = *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
      v22 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v21 + 72LL);
      WindowsDeleteString(0);
      *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      v23 = v22(v21, v3 + 16);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1C4C,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v23,
          v38);
      StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
      v25 = WindowsGetStringRawBuffer(*(HSTRING *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10), 0);
      if ( !_wcsicmp(v25, StringRawBuffer) )
      {
        *(_DWORD *)v3 = 0;
        v26 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&v39
                                                                                 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                + 0x18)
                                                                  + 56LL))(
                *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
                (unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL);
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1C51,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v26,
            v38);
        if ( *(_DWORD *)v3 )
        {
          *a3 = 1;
          WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
          *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3 + 8);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3 + 24);
          break;
        }
      }
      WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
      *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3 + 8);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v3 + 24);
    }
    v27 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v27 > 4u )
    {
      *(_DWORD *)v3 = 0;
      *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = WindowsGetStringRawBuffer(a2, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v27,
        (unsigned int)word_1801249F2,
        v28,
        v29,
        v3 + 8,
        (unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3 + 32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v3 + 40);
    result = 0;
  }
  catch ( ... )
  {
    v32 = (_DWORD *)((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL);
    v33 = wil::ResultFromCaughtException(v30);
    *(_DWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = v33;
    v34 = UserMgrUserModelTelemetry::Provider();
    v35 = (int)v34;
    if ( *(_DWORD *)v34 > 4u )
    {
      *v32 = v33;
      *(_QWORD *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = WindowsGetStringRawBuffer(
                                                                               *(HSTRING *)(((unsigned __int64)&v39
                                                                                           & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                          + 0x30),
                                                                               0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v35,
        (unsigned int)&dword_1801249BC,
        v36,
        v37,
        (__int64)(v32 + 12),
        (__int64)v32);
    }
    return *(unsigned int *)(((unsigned __int64)&v39 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
  }
  return result;
}

```

## disassembly

```asm
0x1800949c0  push    rbp
0x1800949c2  push    rbx
0x1800949c3  push    rsi
0x1800949c4  push    rdi
0x1800949c5  push    r12
0x1800949c7  push    r14
0x1800949c9  push    r15
0x1800949cb  sub     rsp, 240h
0x1800949d2  lea     rbp, [rsp+50h]
0x1800949d7  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800949db  mov     rax, cs:__security_cookie
0x1800949e2  xor     rax, rsp
0x1800949e5  mov     [rbp+220h+var_40], rax
0x1800949ec  mov     r15, r8
0x1800949ef  mov     r14, rdx
0x1800949f2  mov     rdi, rcx
0x1800949f5  mov     [rbp+220h+var_1F0], rdx
0x1800949f9  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800949fe  mov     rbx, rax
0x180094a01  mov     edx, [rax]
0x180094a03  cmp     edx, 4
0x180094a06  jbe     short loc_180094A32
0x180094a08  xor     edx, edx; length
0x180094a0a  mov     rcx, r14; string
0x180094a0d  call    cs:__imp_WindowsGetStringRawBuffer
0x180094a13  mov     qword ptr [rbp+220h+var_218], rax
0x180094a17  lea     rax, [rbp+220h+var_218]
0x180094a1b  mov     qword ptr [rsp+270h+var_250], rax; int
0x180094a20  xor     r8d, r8d
0x180094a23  lea     rdx, byte_180124A33
0x180094a2a  mov     rcx, rbx
0x180094a2d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180094a32  mov     rcx, [rsp+278h]; this
0x180094a3a  xor     r12d, r12d
0x180094a3d  test    r15, r15
0x180094a40  jz      loc_180094CEB
0x180094a46  mov     [rbp+220h+ClientToken], r12
0x180094a4a  xor     edx, edx
0x180094a4c  lea     rcx, [rbp+220h+ClientToken]
0x180094a50  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180094a55  lea     rcx, [rbp+220h+ClientToken]; phNewToken
0x180094a59  call    ?GetCallerTokenFromComCall@@YAJPEAPEAX@Z; GetCallerTokenFromComCall(void * *)
0x180094a5e  mov     rcx, [rsp+278h]; this
0x180094a66  test    eax, eax
0x180094a68  js      loc_180094D03
0x180094a6e  xor     edx, edx; Val
0x180094a70  mov     r8d, 1A0h; Size
0x180094a76  lea     rcx, [rbp+220h+var_1E0]; void *
0x180094a7a  call    memset_0
0x180094a7f  xor     r8d, r8d; struct _EXTENDED_CALLER_INFORMATION *
0x180094a82  lea     rdx, [rbp+220h+var_1E0]; struct _BASIC_CALLER_INFORMATION *
0x180094a86  mov     rcx, [rbp+220h+ClientToken]; ClientToken
0x180094a8a  call    ?GetCallerInformationFromToken@@YAJPEAXPEAU_BASIC_CALLER_INFORMATION@@PEAU_EXTENDED_CALLER_INFORMATION@@@Z; GetCallerInformationFromToken(void *,_BASIC_CALLER_INFORMATION *,_EXTENDED_CALLER_INFORMATION *)
0x180094a8f  mov     rcx, [rsp+278h]; this
0x180094a97  test    eax, eax
0x180094a99  js      loc_180094D17
0x180094a9f  cmp     [rbp+220h+var_1DF], r12b
0x180094aa3  jz      short loc_180094AB5
0x180094aa5  mov     rcx, [rbp+220h+ClientToken]; void *
0x180094aa9  call    ?HasSigninCapability@@YA_NPEAX@Z; HasSigninCapability(void *)
0x180094aae  test    al, al
0x180094ab0  mov     al, r12b
0x180094ab3  jnz     short loc_180094AB7
0x180094ab5  mov     al, 1
0x180094ab7  mov     rcx, [rsp+278h]; this
0x180094abf  test    al, al
0x180094ac1  jnz     loc_180094D2B
0x180094ac7  mov     [rbp+220h+var_200], r12
0x180094acb  mov     [rbp+220h+var_21C], r12d
0x180094acf  lea     rcx, [rdi-68h]; this
0x180094ad3  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x180094ad8  mov     rdi, rax
0x180094adb  mov     rcx, [rax]
0x180094ade  mov     rbx, [rcx+30h]
0x180094ae2  lea     rcx, [rbp+220h+var_200]
0x180094ae6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180094aeb  lea     rdx, [rbp+220h+var_200]
0x180094aef  mov     rcx, rdi
0x180094af2  mov     rax, rbx
0x180094af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094afa  mov     rcx, [rsp+278h]; this
0x180094b02  test    eax, eax
0x180094b04  js      loc_180094D43
0x180094b0a  mov     rcx, [rbp+220h+var_200]
0x180094b0e  mov     rax, [rcx]
0x180094b11  lea     rdx, [rbp+220h+var_21C]
0x180094b15  mov     rax, [rax+38h]
0x180094b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094b1e  mov     rcx, [rsp+278h]; this
0x180094b26  test    eax, eax
0x180094b28  js      loc_180094D57
0x180094b2e  mov     esi, r12d
0x180094b31  cmp     esi, [rbp+220h+var_21C]
0x180094b34  jnb     loc_180094C44
0x180094b3a  mov     [rbp+220h+var_208], r12
0x180094b3e  mov     rcx, [rbp+220h+var_200]
0x180094b42  mov     rax, [rcx]
0x180094b45  lea     r8, [rbp+220h+var_208]
0x180094b49  mov     edx, esi
0x180094b4b  mov     rax, [rax+30h]
0x180094b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094b54  mov     rcx, [rsp+278h]; this
0x180094b5c  test    eax, eax
0x180094b5e  js      loc_180094D6C
0x180094b64  mov     qword ptr [rbp+220h+var_218], r12
0x180094b68  lea     rdx, [rbp+220h+var_218]
0x180094b6c  lea     rcx, [rbp+220h+var_208]
0x180094b70  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x180094b75  mov     rcx, [rsp+278h]; this
0x180094b7d  test    eax, eax
0x180094b7f  js      loc_180094D81
0x180094b85  mov     [rbp+220h+string], r12
0x180094b89  mov     rdi, qword ptr [rbp+220h+var_218]
0x180094b8d  mov     rax, [rdi]
0x180094b90  mov     rbx, [rax+48h]
0x180094b94  xor     ecx, ecx; string
0x180094b96  call    cs:__imp_WindowsDeleteString
0x180094b9c  mov     [rbp+220h+string], r12
0x180094ba0  lea     rdx, [rbp+220h+string]
0x180094ba4  mov     rcx, rdi
0x180094ba7  mov     rax, rbx
0x180094baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094baf  mov     rcx, [rsp+278h]; this
0x180094bb7  test    eax, eax
0x180094bb9  js      loc_180094D96
0x180094bbf  xor     edx, edx; length
0x180094bc1  mov     rcx, r14; string
0x180094bc4  call    cs:__imp_WindowsGetStringRawBuffer
0x180094bca  mov     rbx, rax
0x180094bcd  xor     edx, edx; length
0x180094bcf  mov     rcx, [rbp+220h+string]; string
0x180094bd3  call    cs:__imp_WindowsGetStringRawBuffer
0x180094bd9  mov     rdx, rbx; String2
0x180094bdc  mov     rcx, rax; String1
0x180094bdf  call    cs:__imp__wcsicmp
0x180094be5  test    eax, eax
0x180094be7  jnz     loc_180094CC3
0x180094bed  mov     [rbp+220h+var_220], r12d
0x180094bf1  mov     rcx, [rbp+220h+var_208]
0x180094bf5  mov     rax, [rcx]
0x180094bf8  lea     rdx, [rbp+220h+var_220]
0x180094bfc  mov     rax, [rax+38h]
0x180094c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c05  mov     rcx, [rsp+278h]; this
0x180094c0d  test    eax, eax
0x180094c0f  js      loc_180094DAA
0x180094c15  cmp     [rbp+220h+var_220], r12d
0x180094c19  jz      loc_180094CC3
0x180094c1f  mov     byte ptr [r15], 1
0x180094c23  mov     rcx, [rbp+220h+string]; string
0x180094c27  call    cs:__imp_WindowsDeleteString
0x180094c2d  mov     [rbp+220h+string], r12
0x180094c31  lea     rcx, [rbp+220h+var_218]
0x180094c35  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180094c3a  nop
0x180094c3b  lea     rcx, [rbp+220h+var_208]
0x180094c3f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180094c44  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x180094c49  mov     rbx, rax
0x180094c4c  mov     edx, [rax]
0x180094c4e  cmp     edx, 4
0x180094c51  jbe     short loc_180094C88
0x180094c53  mov     [rbp+220h+var_220], r12d
0x180094c57  xor     edx, edx; length
0x180094c59  mov     rcx, r14; string
0x180094c5c  call    cs:__imp_WindowsGetStringRawBuffer
0x180094c62  mov     qword ptr [rbp+220h+var_218], rax
0x180094c66  lea     rax, [rbp+220h+var_220]
0x180094c6a  mov     [rsp+270h+var_248], rax
0x180094c6f  lea     rax, [rbp+220h+var_218]
0x180094c73  mov     qword ptr [rsp+270h+var_250], rax
0x180094c78  lea     rdx, word_1801249F2
0x180094c7f  mov     rcx, rbx
0x180094c82  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180094c87  nop
0x180094c88  lea     rcx, [rbp+220h+var_200]
0x180094c8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180094c91  nop
0x180094c92  lea     rcx, [rbp+220h+ClientToken]
0x180094c96  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180094c9b  xor     eax, eax
0x180094c9d  jmp     short loc_180094CA2
0x180094c9f  mov     eax, [rbp+220h+var_21C]
0x180094ca2  mov     rcx, [rbp+220h+var_40]
0x180094ca9  xor     rcx, rsp; StackCookie
0x180094cac  call    __security_check_cookie
0x180094cb1  add     rsp, 240h
0x180094cb8  pop     r15
0x180094cba  pop     r14
0x180094cbc  pop     r12
0x180094cbe  pop     rdi
0x180094cbf  pop     rsi
0x180094cc0  pop     rbx
0x180094cc1  pop     rbp
0x180094cc2  retn
0x180094cc3  mov     rcx, [rbp+220h+string]; string
0x180094cc7  call    cs:__imp_WindowsDeleteString
0x180094ccd  mov     [rbp+220h+string], r12
0x180094cd1  lea     rcx, [rbp+220h+var_218]
0x180094cd5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180094cda  nop
0x180094cdb  lea     rcx, [rbp+220h+var_208]
0x180094cdf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180094ce4  inc     esi
0x180094ce6  jmp     loc_180094B31
0x180094ceb  mov     r9d, 80004003h; char *
0x180094cf1  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094cf8  mov     edx, 1C35h; void *
0x180094cfd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d03  mov     r9d, eax; char *
0x180094d06  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094d0d  mov     edx, 1C38h; void *
0x180094d12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d17  mov     r9d, eax; char *
0x180094d1a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094d21  mov     edx, 1C3Ah; void *
0x180094d26  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d2b  mov     r9d, 80070005h; char *
0x180094d31  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094d38  mov     edx, 1C3Dh; void *
0x180094d3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d43  mov     r9d, eax; char *
0x180094d46  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094d4d  mov     edx, 1C42h; void *
0x180094d52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d57  mov     r9d, eax; char *
0x180094d5a  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094d61  mov     edx, 1C43h; void *
0x180094d66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d6c  mov     r9d, eax; char *
0x180094d6f  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094d76  mov     edx, 1C48h; void *
0x180094d7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d81  mov     r9d, eax; char *
0x180094d84  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094d8b  mov     edx, 1C4Ah; void *
0x180094d90  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094d96  mov     r9d, eax; char *
0x180094d99  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094da0  mov     edx, 1C4Ch; void *
0x180094da5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180094daa  mov     r9d, eax; char *
0x180094dad  lea     r8, aOnecoreDsSecur_66; "onecore\\ds\\security\\umstartup\\userm"...
0x180094db4  mov     edx, 1C51h; void *
0x180094db9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
