# Windows::System::Internal::UserManagerStatics::LsaLogonUserWrapper(uint,Windows::System::Internal::ISignInContext *,ushort const *,uint,void * *,long *,long *)

- ea: `0x180094ff4`
- end: `0x180095d50`
- name: `?LsaLogonUserWrapper@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEBGIPEAPEAXPEAJ3@Z`
- size: `3420`
- prototype: `__int64 __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this, unsigned int, struct Windows::System::Internal::ISignInContext *, const unsigned __int16 *, unsigned int, void **, int *, int *)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ac9c`
- `0x1800a0128`

## callees

- `0x180002a8c`
- `0x18000acdc`
- `0x18000ce48`
- `0x180014e7c`
- `0x180015540`
- `0x180018b60`
- `0x180024828`
- `0x18003329c`
- `0x1800346b8`
- `0x180035800`
- `0x180035938`
- `0x18003afd4`
- `0x18004e4e8`
- `0x18004e58c`
- `0x1800641b8`
- `0x18006c426`
- `0x180084f5c`
- `0x18008a668`
- `0x180094ff4`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180095a2e`
- `msvcrt!_wcsicmp` at `0x180095a2e`
- `msvcrt!wcsstr` at `0x18009541e`
- `msvcrt!wcsstr` at `0x18009541e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009540e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800954ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800955e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009562c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009540e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800954ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800955e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009562c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095665`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180095a22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800953ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800953fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800954e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800954f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800953ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800953fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800954e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800954f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800953b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800959df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095ad1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095ae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800953b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800959df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095a60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095ad1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095ae7`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800952f0`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800952f0`
- `ntdll!RtlInitString` at `0x1800952bb`
- `ntdll!RtlInitString` at `0x1800952d0`
- `ntdll!RtlInitString` at `0x18009554b`
- `ntdll!RtlInitString` at `0x1800952bb`
- `ntdll!RtlInitString` at `0x1800952d0`
- `ntdll!RtlInitString` at `0x18009554b`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x18009577a`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x18009577a`

## string_xrefs

- `0x180095b60`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095b77`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095b8e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095ba3`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095bb7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095bcb`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095be2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095bf7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c0b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c1f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c33`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c4a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c5e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c73`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c87`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095c9b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095cb2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095cca`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095cdb`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095cef`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095d03`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095d17`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x180095d3d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::System::Internal::UserManagerStatics::LsaLogonUserWrapper(
        Windows::System::Internal::UserManagerStatics *this,
        unsigned int a2,
        struct Windows::System::Internal::ISignInContext *a3,
        WCHAR *a4,
        unsigned int a5,
        void **a6,
        int *a7,
        int *a8)
{
  Windows::System::Internal::UserManagerStatics *v11; // r13
  void **v12; // r14
  wchar_t *v13; // rsi
  int *v14; // r12
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  void (__fastcall *v18)(void *, __int64 *); // rbx
  NTSTATUS v19; // eax
  int v20; // eax
  __int64 (__fastcall *v21)(struct Windows::System::Internal::ISignInContext *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v22; // eax
  __int64 (__fastcall *v23)(struct Windows::System::Internal::ISignInContext *, HSTRING *); // rbx
  int v24; // eax
  UINT32 StringLen; // r12d
  UINT32 v26; // r14d
  const wchar_t *StringRawBuffer; // rax
  wchar_t *v28; // rax
  wchar_t *v29; // rdi
  __int64 v30; // rbx
  const unsigned __int16 *v31; // rax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int16 v35; // r13
  UINT32 v36; // esi
  int v37; // eax
  __int64 v38; // rdi
  __int16 v39; // r13
  PCWSTR v40; // rax
  char *v41; // r14
  char *v42; // rbx
  __int16 v43; // si
  PCWSTR v44; // rax
  __int16 v45; // r12
  PCWSTR v46; // rax
  _QWORD *v47; // rcx
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  void (__fastcall *v52)(void *, unsigned int *); // rbx
  void (__fastcall *v53)(void *, __int64 *); // rbx
  int v54; // eax
  __int64 v55; // rdi
  unsigned int (__fastcall *v56)(__int64, __int64, wchar_t **); // rbx
  const char *v57; // r9
  __int64 v58; // rdi
  __int64 (__fastcall *v59)(__int64, _QWORD, void ***); // rbx
  int v60; // eax
  int v61; // eax
  PCWSTR v62; // rdi
  __int64 (__fastcall *v63)(PCWSTR, struct _STRING *); // rbx
  int v64; // eax
  wchar_t *v65; // rbx
  const wchar_t *v66; // rax
  __int64 result; // rax
  unsigned int v68; // eax
  wil *v69; // rcx
  int v70; // r8d
  int v71; // r9d
  int v72; // [rsp+20h] [rbp-298h]
  int v73; // [rsp+20h] [rbp-298h]
  HSTRING string; // [rsp+80h] [rbp-238h] BYREF
  _QWORD *v75; // [rsp+88h] [rbp-230h] BYREF
  unsigned int v76[2]; // [rsp+90h] [rbp-228h] BYREF
  PCWSTR v77; // [rsp+98h] [rbp-220h] BYREF
  unsigned int v78; // [rsp+A0h] [rbp-218h] BYREF
  int v79; // [rsp+A4h] [rbp-214h] BYREF
  unsigned int v80; // [rsp+A8h] [rbp-210h]
  __int64 v81; // [rsp+B0h] [rbp-208h] BYREF
  __int64 v82; // [rsp+B8h] [rbp-200h] BYREF
  HSTRING v83; // [rsp+C0h] [rbp-1F8h] BYREF
  void **v84; // [rsp+C8h] [rbp-1F0h] BYREF
  wchar_t *String2; // [rsp+D0h] [rbp-1E8h] BYREF
  int v86; // [rsp+D8h] [rbp-1E0h] BYREF
  int v87; // [rsp+DCh] [rbp-1DCh] BYREF
  struct _STRING v88; // [rsp+E0h] [rbp-1D8h] BYREF
  HSTRING v89; // [rsp+F0h] [rbp-1C8h] BYREF
  __int64 (__fastcall ***v90)(_QWORD, GUID *, __int64); // [rsp+F8h] [rbp-1C0h] BYREF
  __int64 v91; // [rsp+100h] [rbp-1B8h] BYREF
  struct _WL_AUTH_INFO *v92; // [rsp+108h] [rbp-1B0h] BYREF
  __int64 v93; // [rsp+110h] [rbp-1A8h] BYREF
  struct Windows::System::Internal::ISignInContext *v94; // [rsp+118h] [rbp-1A0h] BYREF
  struct Windows::System::Internal::ISignInContext *v95; // [rsp+120h] [rbp-198h] BYREF
  WCHAR *v96; // [rsp+128h] [rbp-190h] BYREF
  __int64 v97; // [rsp+130h] [rbp-188h] BYREF
  int *v98; // [rsp+138h] [rbp-180h]
  Windows::System::Internal::UserManagerStatics *v99; // [rsp+140h] [rbp-178h]
  __int64 v100; // [rsp+148h] [rbp-170h] BYREF
  struct _STRING DestinationString; // [rsp+150h] [rbp-168h] BYREF
  struct _STRING v102; // [rsp+160h] [rbp-158h] BYREF
  _QWORD v103[6]; // [rsp+170h] [rbp-148h] BYREF
  char v104; // [rsp+1A0h] [rbp-118h]
  LUID LocallyUniqueId[2]; // [rsp+1A8h] [rbp-110h] BYREF
  HSTRING_HEADER v106; // [rsp+1B8h] [rbp-100h] BYREF
  HSTRING v107; // [rsp+1D0h] [rbp-E8h]
  _OWORD v108[3]; // [rsp+1D8h] [rbp-E0h] BYREF
  __int64 v109[12]; // [rsp+210h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v11 = this;
  v99 = this;
  v80 = a2;
  v94 = a3;
  v96 = a4;
  v12 = a6;
  v84 = a6;
  v13 = (wchar_t *)a7;
  String2 = (wchar_t *)a7;
  v14 = a8;
  v98 = a8;
  DestinationString = 0;
  v102 = 0;
  v78 = 0;
  v91 = 0;
  *(_OWORD *)&LocallyUniqueId[0].LowPart = 0;
  v81 = 0;
  v95 = a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v95);
  v90 = 0;
  v93 = 0;
  v83 = 0;
  v89 = 0;
  v75 = 0;
  v87 = 0;
  v97 = 0;
  v79 = 0;
  v100 = 0;
  memset(v108, 0, sizeof(v108));
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v106, (const WCHAR **)&v96);
  try
  {
    v92 = 0;
    v76[0] = 0;
    v86 = 0;
    if ( a3 )
      (*(void (__fastcall **)(struct Windows::System::Internal::ISignInContext *, int *))(*(_QWORD *)a3 + 64LL))(
        a3,
        &v86);
    if ( (unsigned int)dword_180146228 > 5 )
    {
      v77 = a4;
      LODWORD(v82) = a5;
      *(_DWORD *)&v88.Length = v86;
      LODWORD(string) = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v15,
        (unsigned int)byte_1801262C3,
        v16,
        v17,
        (__int64)&string,
        (__int64)&v88,
        (__int64)&v82,
        (__int64)&v77);
    }
    if ( !a6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB49,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v72);
    if ( !a7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v72);
    if ( !a8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)0x80004003LL,
        v72);
    v18 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    v18(&Windows::System::Internal::Adapters::g_AdapterCollection, &v81);
    v103[0] = &v87;
    v103[1] = &v91;
    v103[2] = &v81;
    v103[3] = &v97;
    v103[4] = &v75;
    v103[5] = &v92;
    v104 = 1;
    RtlInitString(&DestinationString, "UserManager");
    RtlInitString(&v102, "SignInUserAsync");
    LocallyUniqueId[0] = (LUID)0x72674D72657355LL;
    v19 = NtAllocateLocallyUniqueId(&LocallyUniqueId[1]);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xB6A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v19,
        v72);
    v20 = (*(__int64 (__fastcall **)(__int64, struct _STRING *, __int64 *, unsigned int *))(*(_QWORD *)v81 + 24LL))(
            v81,
            &DestinationString,
            &v91,
            &v78);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xB6C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v20,
        v72);
    v21 = *(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)a3 + 112LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
    v22 = v21(a3, &v90);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB6E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v22,
        v72);
    if ( v90 )
    {
      v49 = Microsoft::WRL::ComPtr<Windows::System::Internal::ICredentialSerialization>::As<ICredentialSerializationProvider>(
              &v90,
              (__int64)&v93);
      if ( v49 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBC2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v49,
          v72);
      v50 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v93 + 32LL))(v93, &v75);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBC3,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v50,
          v72);
      v47 = v75;
      if ( !v75 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBC4,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)0x8000FFFFLL,
          v72);
    }
    else
    {
      if ( a2 == 0x200000 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB72,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)0x80070057LL,
          v72);
      string = 0;
      v23 = *(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, HSTRING *))(*(_QWORD *)a3 + 96LL);
      WindowsDeleteString(0);
      string = 0;
      v24 = v23(a3, &string);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB76,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v24,
          v72);
      StringLen = WindowsGetStringLen(string);
      v26 = WindowsGetStringLen(v107);
      StringRawBuffer = WindowsGetStringRawBuffer(v107, 0);
      v28 = wcsstr(StringRawBuffer, L"\\");
      v29 = v28;
      if ( v28 )
      {
        v30 = -1;
        do
          ++v30;
        while ( v28[v30] );
        v31 = WindowsGetStringRawBuffer(v107, 0);
        v32 = Microsoft::WRL::Wrappers::HString::Set(
                (Microsoft::WRL::Wrappers::HString *)&v89,
                v31,
                v26 - (unsigned int)v30);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xB80,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v32,
            v72);
        v77 = v29 + 1;
        v33 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v83);
        if ( v33 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xB82,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v33,
            v72);
      }
      else
      {
        v77 = WindowsGetStringRawBuffer(v107, 0);
        v34 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v83);
        if ( v34 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xB86,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
            (const char *)(unsigned int)v34,
            v72);
      }
      v35 = WindowsGetStringLen(v83);
      v36 = WindowsGetStringLen(v89);
      v75 = CoTaskMemAlloc(2 * (v26 + StringLen + v36) + 80);
      if ( !v75 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB90,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)0x8007000ELL,
          v72);
      v88 = 0;
      RtlInitString(&v88, "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0");
      v37 = (*(__int64 (__fastcall **)(__int64, __int64, struct _STRING *, __int64))(*(_QWORD *)v81 + 40LL))(
              v81,
              v91,
              &v88,
              (__int64)v75 + 4);
      if ( v37 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xB93,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v37,
          v72);
      *(_DWORD *)v75 = 0;
      v75[2] = v75 + 3;
      *((_DWORD *)v75 + 2) = 2 * (v26 + StringLen + v36) + 56;
      v38 = v75[2];
      *(_DWORD *)v38 = 2;
      v39 = 2 * v35;
      *(_WORD *)(v38 + 24) = v39;
      *(_WORD *)(v38 + 26) = v39;
      v40 = WindowsGetStringRawBuffer(v83, 0);
      memcpy_0((void *)(v38 + 56), v40, *(unsigned __int16 *)(v38 + 24));
      *(_QWORD *)(v38 + 32) = v38 + 56;
      v41 = (char *)(v38 + 56 + *(unsigned __int16 *)(v38 + 24));
      if ( v36 )
      {
        v43 = 2 * v36;
        *(_WORD *)(v38 + 8) = v43;
        *(_WORD *)(v38 + 10) = v43;
        v44 = WindowsGetStringRawBuffer(v89, 0);
        memcpy_0(v41, v44, *(unsigned __int16 *)(v38 + 8));
        v42 = &v41[*(unsigned __int16 *)(v38 + 8)];
      }
      else
      {
        v42 = (char *)(v38 + 56 + *(unsigned __int16 *)(v38 + 24));
        *(_DWORD *)(v38 + 8) = 0;
      }
      *(_QWORD *)(v38 + 16) = v41;
      v45 = 2 * StringLen;
      *(_WORD *)(v38 + 40) = v45;
      *(_WORD *)(v38 + 42) = v45;
      v46 = WindowsGetStringRawBuffer(string, 0);
      memcpy_0(v42, v46, *(unsigned __int16 *)(v38 + 42));
      *(_QWORD *)(v38 + 48) = v42;
      WindowsDeleteString(string);
      v47 = v75;
      v13 = String2;
      v12 = v84;
      v14 = v98;
      v11 = v99;
    }
    WrapWlAuthInfo((void *)v47[2], *((unsigned int *)v47 + 2), a5, &v92, v76);
    v48 = SetNtlmThreadOptions(0, 1u);
    if ( v48 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xBCF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v48,
        v73);
    SeciAllocateAndSetCallFlags(128, &v87);
    v51 = (*(__int64 (__fastcall **)(__int64, __int64, struct _STRING *, __int64, _DWORD, struct _WL_AUTH_INFO *, unsigned int, _QWORD, LUID *, __int64 *, int *, __int64 *, void **, _OWORD *, int *))(*(_QWORD *)v81 + 32LL))(
            v81,
            v91,
            &v102,
            2,
            *((_DWORD *)v75 + 1),
            v92,
            v76[0],
            0,
            LocallyUniqueId,
            &v97,
            &v79,
            &v100,
            v12,
            v108,
            v14);
    *(_DWORD *)v13 = v51;
    if ( v51 >= 0 && a2 != 0x200000 )
    {
      LODWORD(string) = 0;
      String2 = 0;
      v84 = 0;
      v77 = 0;
      *(_QWORD *)&v88.Length = 0;
      *(_QWORD *)v76 = 0;
      v82 = 0;
      v52 = *(void (__fastcall **)(void *, unsigned int *))(Windows::System::Internal::Adapters::g_AdapterCollection
                                                          + 88LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v76);
      v52(&Windows::System::Internal::Adapters::g_AdapterCollection, v76);
      v53 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      v53(&Windows::System::Internal::Adapters::g_AdapterCollection, &v82);
      v54 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, __int64 *))(**(_QWORD **)v76 + 24LL))(
              *(_QWORD *)v76,
              *v12,
              1,
              v109);
      if ( v54 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xBF2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v54,
          84);
      v55 = v82;
      v56 = *(unsigned int (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v82 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &String2,
        0);
      if ( !v56(v55, v109[0], &String2) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xBF4,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          v57);
      v58 = *((_QWORD *)v11 + 67);
      v59 = *(__int64 (__fastcall **)(__int64, _QWORD, void ***))(*(_QWORD *)v58 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
      v60 = v59(v58, a2, &v84);
      if ( v60 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBF6,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v60,
          84);
      v61 = Microsoft::WRL::ComPtr<Windows::System::Internal::IUserProfile>::As<Windows::System::Internal::IUserProfile2>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v84,
              (__int64)&v77);
      if ( v61 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBF7,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v61,
          84);
      v62 = v77;
      v63 = *(__int64 (__fastcall **)(PCWSTR, struct _STRING *))(*(_QWORD *)v77 + 56LL);
      WindowsDeleteString(*(HSTRING *)&v88.Length);
      *(_QWORD *)&v88.Length = 0;
      v64 = v63(v62, &v88);
      if ( v64 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBF8,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v64,
          84);
      v65 = String2;
      v66 = WindowsGetStringRawBuffer(*(HSTRING *)&v88.Length, 0);
      if ( _wcsicmp(v66, v65) )
      {
        v68 = wil::verify_hresult<long>(2158104327LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC00,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)v68,
          84);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v76);
      WindowsDeleteString(*(HSTRING *)&v88.Length);
      *(_QWORD *)&v88.Length = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&String2);
    }
    SetNtlmThreadOptions(1, 1u);
    v104 = 0;
    lambda_f2af06a160b1b803c5f1834b1f615158_::operator()(v103);
    v107 = 0;
    WindowsDeleteString(v89);
    v89 = 0;
    WindowsDeleteString(v83);
    v83 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v93);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v90);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v95);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    result = 0;
  }
  catch ( ... )
  {
    v76[0] = 0;
    v69 = v94;
    if ( v94 )
      (*(void (__fastcall **)(struct Windows::System::Internal::ISignInContext *, unsigned int *))(*(_QWORD *)v94 + 64LL))(
        v94,
        v76);
    if ( (unsigned int)dword_180146228 > 5 )
    {
      v79 = wil::ResultFromCaughtException(v69);
      v94 = (struct Windows::System::Internal::ISignInContext *)v96;
      v78 = v76[0];
      LODWORD(string) = v80;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180146228,
        (unsigned int)&byte_180126257,
        v70,
        v71,
        (__int64)&string,
        (__int64)&v78,
        (__int64)&v94,
        (__int64)&v79);
    }
    return (unsigned int)wil::ResultFromCaughtException(v69);
  }
  return result;
}

```

## disassembly

```asm
0x180094ff4  mov     r11, rsp
0x180094ff7  push    rbx
0x180094ff8  push    rsi
0x180094ff9  push    rdi
0x180094ffa  push    r12
0x180094ffc  push    r13
0x180094ffe  push    r14
0x180095000  push    r15
0x180095002  sub     rsp, 280h
0x180095009  mov     rax, cs:__security_cookie
0x180095010  xor     rax, rsp
0x180095013  mov     [rsp+2B8h+var_48], rax
0x18009501b  mov     rbx, r9
0x18009501e  mov     rdi, r8
0x180095021  mov     r15d, edx
0x180095024  mov     r13, rcx
0x180095027  mov     [rsp+2B8h+var_178], rcx
0x18009502f  mov     [rsp+2B8h+var_210], edx
0x180095036  mov     [rsp+2B8h+var_1A0], r8
0x18009503e  mov     [r11-190h], rbx
0x180095045  mov     r14, [rsp+2B8h+arg_28]
0x18009504d  mov     [rsp+2B8h+var_1F0], r14
0x180095055  mov     rsi, [rsp+2B8h+arg_30]
0x18009505d  mov     [rsp+2B8h+String2], rsi
0x180095065  mov     r12, [rsp+2B8h+arg_38]
0x18009506d  mov     [rsp+2B8h+var_180], r12
0x180095075  xorps   xmm0, xmm0
0x180095078  movups  xmmword ptr [rsp+2B8h+DestinationString.Length], xmm0
0x180095080  xorps   xmm1, xmm1
0x180095083  movups  xmmword ptr [rsp+2B8h+var_158.Length], xmm1
0x18009508b  xor     eax, eax
0x18009508d  mov     [rsp+2B8h+var_218], eax
0x180095094  mov     [r11-1B8h], rax
0x18009509b  movups  xmmword ptr [rsp+2B8h+LocallyUniqueId.LowPart], xmm0
0x1800950a3  mov     [r11-208h], rax
0x1800950aa  mov     [r11-198h], r8
0x1800950b1  lea     rcx, [r11-198h]
0x1800950b8  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800950bd  nop
0x1800950be  xor     eax, eax
0x1800950c0  mov     [rsp+2B8h+var_1C0], rax
0x1800950c8  mov     [rsp+2B8h+var_1A8], rax
0x1800950d0  mov     [rsp+2B8h+var_1F8], rax
0x1800950d8  mov     [rsp+2B8h+var_1C8], rax
0x1800950e0  mov     [rsp+2B8h+var_230], rax
0x1800950e8  mov     [rsp+2B8h+var_1DC], eax
0x1800950ef  mov     [rsp+2B8h+var_188], rax
0x1800950f7  mov     [rsp+2B8h+var_214], eax
0x1800950fe  mov     [rsp+2B8h+var_170], rax
0x180095106  xorps   xmm0, xmm0
0x180095109  movups  [rsp+2B8h+var_E0], xmm0
0x180095111  movups  [rsp+2B8h+var_D0], xmm0
0x180095119  movups  [rsp+2B8h+var_C0], xmm0
0x180095121  lea     rdx, [rsp+2B8h+var_190]
0x180095129  lea     rcx, [rsp+2B8h+var_100]
0x180095131  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095136  nop
0x180095137  xor     eax, eax
0x180095139  mov     [rsp+2B8h+var_1B0], rax
0x180095141  mov     [rsp+2B8h+var_228], eax
0x180095148  mov     [rsp+2B8h+var_1E0], eax
0x18009514f  test    rdi, rdi
0x180095152  jz      short loc_18009516B
0x180095154  mov     rax, [rdi]
0x180095157  lea     rdx, [rsp+2B8h+var_1E0]
0x18009515f  mov     rcx, rdi
0x180095162  mov     rax, [rax+40h]
0x180095166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009516b  mov     eax, cs:dword_180146228
0x180095171  cmp     eax, 5
0x180095174  jbe     short loc_1800951E2
0x180095176  mov     [rsp+2B8h+var_220], rbx
0x18009517e  mov     eax, [rsp+2B8h+arg_20]
0x180095185  mov     dword ptr [rsp+2B8h+var_200], eax
0x18009518c  mov     eax, [rsp+2B8h+var_1E0]
0x180095193  mov     dword ptr [rsp+2B8h+var_1D8.Length], eax
0x18009519a  mov     dword ptr [rsp+2B8h+string], r15d
0x1800951a2  lea     rax, [rsp+2B8h+var_220]
0x1800951aa  mov     [rsp+2B8h+var_280], rax
0x1800951af  lea     rax, [rsp+2B8h+var_200]
0x1800951b7  mov     [rsp+2B8h+var_288], rax
0x1800951bc  lea     rax, [rsp+2B8h+var_1D8]
0x1800951c4  mov     [rsp+2B8h+var_290], rax
0x1800951c9  lea     rax, [rsp+2B8h+string]
0x1800951d1  mov     [rsp+2B8h+var_298], rax; int
0x1800951d6  lea     rdx, byte_1801262C3
0x1800951dd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800951e2  mov     rcx, [rsp+2B8h]; this
0x1800951ea  test    r14, r14
0x1800951ed  jz      loc_180095B5A
0x1800951f3  mov     rcx, [rsp+2B8h]; this
0x1800951fb  test    rsi, rsi
0x1800951fe  jz      loc_180095B71
0x180095204  mov     rcx, [rsp+2B8h]; this
0x18009520c  test    r12, r12
0x18009520f  jz      loc_180095B88
0x180095215  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18009521c  mov     rbx, [rax+68h]
0x180095220  lea     rcx, [rsp+2B8h+var_208]
0x180095228  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009522d  lea     rdx, [rsp+2B8h+var_208]
0x180095235  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18009523c  mov     rax, rbx
0x18009523f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095244  lea     rax, [rsp+2B8h+var_1DC]
0x18009524c  mov     [rsp+2B8h+var_148], rax
0x180095254  lea     rax, [rsp+2B8h+var_1B8]
0x18009525c  mov     [rsp+2B8h+var_140], rax
0x180095264  lea     rax, [rsp+2B8h+var_208]
0x18009526c  mov     [rsp+2B8h+var_138], rax
0x180095274  lea     rax, [rsp+2B8h+var_188]
0x18009527c  mov     [rsp+2B8h+var_130], rax
0x180095284  lea     rax, [rsp+2B8h+var_230]
0x18009528c  mov     [rsp+2B8h+var_128], rax
0x180095294  lea     rax, [rsp+2B8h+var_1B0]
0x18009529c  mov     [rsp+2B8h+var_120], rax
0x1800952a4  mov     [rsp+2B8h+var_118], 1
0x1800952ac  lea     rdx, aUsermanager_1; "UserManager"
0x1800952b3  lea     rcx, [rsp+2B8h+DestinationString]; DestinationString
0x1800952bb  call    cs:__imp_RtlInitString
0x1800952c1  lea     rdx, aSigninuserasyn; "SignInUserAsync"
0x1800952c8  lea     rcx, [rsp+2B8h+var_158]; DestinationString
0x1800952d0  call    cs:__imp_RtlInitString
0x1800952d6  mov     rax, 72674D72657355h
0x1800952e0  mov     qword ptr [rsp+2B8h+LocallyUniqueId.LowPart], rax
0x1800952e8  lea     rcx, [rsp+2B8h+LocallyUniqueId.LowPart+8]; LocallyUniqueId
0x1800952f0  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800952f6  mov     rcx, [rsp+2B8h]; this
0x1800952fe  test    eax, eax
0x180095300  js      loc_180095BA0
0x180095306  mov     rcx, [rsp+2B8h+var_208]
0x18009530e  mov     rax, [rcx]
0x180095311  lea     r9, [rsp+2B8h+var_218]
0x180095319  lea     r8, [rsp+2B8h+var_1B8]
0x180095321  lea     rdx, [rsp+2B8h+DestinationString]
0x180095329  mov     rax, [rax+18h]
0x18009532d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095332  mov     rcx, [rsp+2B8h]; this
0x18009533a  test    eax, eax
0x18009533c  js      loc_180095BB4
0x180095342  mov     rax, [rdi]
0x180095345  mov     rbx, [rax+70h]
0x180095349  lea     rcx, [rsp+2B8h+var_1C0]
0x180095351  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180095356  lea     rdx, [rsp+2B8h+var_1C0]
0x18009535e  mov     rcx, rdi
0x180095361  mov     rax, rbx
0x180095364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095369  mov     rcx, [rsp+2B8h]; this
0x180095371  xor     ebx, ebx
0x180095373  test    eax, eax
0x180095375  js      loc_180095BC8
0x18009537b  cmp     [rsp+2B8h+var_1C0], rbx
0x180095383  jnz     loc_1800956FE
0x180095389  mov     rcx, [rsp+2B8h]; this
0x180095391  cmp     r15d, 200000h
0x180095398  jz      loc_180095BDC
0x18009539e  xor     esi, esi
0x1800953a0  mov     [rsp+2B8h+string], rsi
0x1800953a8  mov     rax, [rdi]
0x1800953ab  mov     rbx, [rax+60h]
0x1800953af  xor     ecx, ecx; string
0x1800953b1  call    cs:__imp_WindowsDeleteString
0x1800953b7  mov     [rsp+2B8h+string], rsi
0x1800953bf  lea     rdx, [rsp+2B8h+string]
0x1800953c7  mov     rcx, rdi
0x1800953ca  mov     rax, rbx
0x1800953cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800953d2  mov     rcx, [rsp+2B8h]; this
0x1800953da  test    eax, eax
0x1800953dc  js      loc_180095BF4
0x1800953e2  mov     rcx, [rsp+2B8h+string]; string
0x1800953ea  call    cs:__imp_WindowsGetStringLen
0x1800953f0  mov     r12d, eax
0x1800953f3  mov     rcx, [rsp+2B8h+var_E8]; string
0x1800953fb  call    cs:__imp_WindowsGetStringLen
0x180095401  mov     r14d, eax
0x180095404  xor     edx, edx; length
0x180095406  mov     rcx, [rsp+2B8h+var_E8]; string
0x18009540e  call    cs:__imp_WindowsGetStringRawBuffer
0x180095414  lea     rdx, SubStr; "\\"
0x18009541b  mov     rcx, rax; Str
0x18009541e  call    cs:__imp_wcsstr
0x180095424  mov     rdi, rax
0x180095427  test    rax, rax
0x18009542a  jz      short loc_1800954A2
0x18009542c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180095430  inc     rbx
0x180095433  cmp     [rax+rbx*2], si
0x180095437  jnz     short loc_180095430
0x180095439  xor     edx, edx; length
0x18009543b  mov     rcx, [rsp+2B8h+var_E8]; string
0x180095443  call    cs:__imp_WindowsGetStringRawBuffer
0x180095449  mov     r8d, r14d
0x18009544c  sub     r8d, ebx; unsigned int
0x18009544f  mov     rdx, rax; unsigned __int16 *
0x180095452  lea     rcx, [rsp+2B8h+var_1C8]; this
0x18009545a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18009545f  mov     rcx, [rsp+2B8h]; this
0x180095467  test    eax, eax
0x180095469  js      loc_180095C08
0x18009546f  lea     rax, [rdi+2]
0x180095473  mov     [rsp+2B8h+var_220], rax
0x18009547b  lea     rdx, [rsp+2B8h+var_220]
0x180095483  lea     rcx, [rsp+2B8h+var_1F8]; string
0x18009548b  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180095490  mov     rcx, [rsp+2B8h]; this
0x180095498  test    eax, eax
0x18009549a  js      loc_180095C1C
0x1800954a0  jmp     short loc_1800954DF
0x1800954a2  xor     edx, edx; length
0x1800954a4  mov     rcx, [rsp+2B8h+var_E8]; string
0x1800954ac  call    cs:__imp_WindowsGetStringRawBuffer
0x1800954b2  mov     [rsp+2B8h+var_220], rax
0x1800954ba  lea     rdx, [rsp+2B8h+var_220]
0x1800954c2  lea     rcx, [rsp+2B8h+var_1F8]; string
0x1800954ca  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800954cf  mov     rcx, [rsp+2B8h]; this
0x1800954d7  test    eax, eax
0x1800954d9  js      loc_180095C30
0x1800954df  mov     rcx, [rsp+2B8h+var_1F8]; string
0x1800954e7  call    cs:__imp_WindowsGetStringLen
0x1800954ed  mov     r13d, eax
0x1800954f0  mov     rcx, [rsp+2B8h+var_1C8]; string
0x1800954f8  call    cs:__imp_WindowsGetStringLen
0x1800954fe  mov     esi, eax
0x180095500  lea     ecx, [r12+rax]
0x180095504  add     ecx, r14d
0x180095507  lea     ebx, ds:50h[rcx*2]
0x18009550e  mov     ecx, ebx; cb
0x180095510  call    cs:__imp_CoTaskMemAlloc
0x180095516  mov     [rsp+2B8h+var_230], rax
0x18009551e  mov     rcx, [rsp+2B8h]; this
0x180095526  xor     edi, edi
0x180095528  test    rax, rax
0x18009552b  jz      loc_180095C44
0x180095531  xorps   xmm0, xmm0
0x180095534  movups  xmmword ptr [rsp+2B8h+var_1D8.Length], xmm0
0x18009553c  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x180095543  lea     rcx, [rsp+2B8h+var_1D8]; DestinationString
0x18009554b  call    cs:__imp_RtlInitString
0x180095551  mov     rcx, [rsp+2B8h+var_208]
0x180095559  mov     rax, [rcx]
0x18009555c  mov     r9, [rsp+2B8h+var_230]
0x180095564  add     r9, 4
0x180095568  lea     r8, [rsp+2B8h+var_1D8]
0x180095570  mov     rdx, [rsp+2B8h+var_1B8]
0x180095578  mov     rax, [rax+28h]
0x18009557c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095581  mov     rcx, [rsp+2B8h]; this
0x180095589  test    eax, eax
0x18009558b  js      loc_180095C5B
0x180095591  mov     rax, [rsp+2B8h+var_230]
0x180095599  mov     [rax], edi
0x18009559b  mov     rcx, [rsp+2B8h+var_230]
0x1800955a3  lea     rax, [rcx+18h]
0x1800955a7  mov     [rcx+10h], rax
0x1800955ab  lea     ecx, [rbx-18h]
0x1800955ae  mov     rax, [rsp+2B8h+var_230]
0x1800955b6  mov     [rax+8], ecx
0x1800955b9  mov     rax, [rsp+2B8h+var_230]
0x1800955c1  mov     rdi, [rax+10h]
0x1800955c5  lea     rbx, [rdi+38h]
0x1800955c9  mov     dword ptr [rdi], 2
0x1800955cf  add     r13w, r13w
0x1800955d3  mov     [rdi+18h], r13w
0x1800955d8  mov     [rdi+1Ah], r13w
0x1800955dd  xor     edx, edx; length
0x1800955df  mov     rcx, [rsp+2B8h+var_1F8]; string
0x1800955e7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800955ed  movzx   r8d, word ptr [rdi+18h]; Size
0x1800955f2  mov     rdx, rax; Src
0x1800955f5  mov     rcx, rbx; void *
0x1800955f8  call    memcpy_0
0x1800955fd  mov     [rdi+20h], rbx
0x180095601  movzx   r14d, word ptr [rdi+18h]
0x180095606  add     r14, rbx
0x180095609  xor     ecx, ecx
0x18009560b  test    esi, esi
0x18009560d  jnz     short loc_180095617
0x18009560f  mov     rbx, r14
0x180095612  mov     [rdi+8], ecx
0x180095615  jmp     short loc_180095649
0x180095617  add     si, si
0x18009561a  mov     [rdi+8], si
0x18009561e  mov     [rdi+0Ah], si
0x180095622  xor     edx, edx; length
0x180095624  mov     rcx, [rsp+2B8h+var_1C8]; string
0x18009562c  call    cs:__imp_WindowsGetStringRawBuffer
0x180095632  movzx   r8d, word ptr [rdi+8]; Size
0x180095637  mov     rdx, rax; Src
0x18009563a  mov     rcx, r14; void *
0x18009563d  call    memcpy_0
0x180095642  movzx   ebx, word ptr [rdi+8]
0x180095646  add     rbx, r14
0x180095649  mov     [rdi+10h], r14
0x18009564d  add     r12w, r12w
0x180095651  mov     [rdi+28h], r12w
0x180095656  mov     [rdi+2Ah], r12w
0x18009565b  xor     edx, edx; length
  ... truncated ...
```
