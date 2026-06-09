# UserMgrCli::GetUserMarshalData(void *,ulong,_USER_DATA * *)

- ea: `0x18003b764`
- end: `0x18003bef2`
- name: `?GetUserMarshalData@UserMgrCli@@QEAAJPEAXKPEAPEAU_USER_DATA@@@Z`
- size: `1934`
- prototype: `__int64 __fastcall(UserMgrCli *__hidden this, void *, unsigned int, struct _USER_DATA **)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b750`

## callees

- `0x180006130`
- `0x180007920`
- `0x180008b10`
- `0x180009af0`
- `0x18000acdc`
- `0x18000ad00`
- `0x18000c350`
- `0x18000cd30`
- `0x18000ce48`
- `0x180012890`
- `0x180014e7c`
- `0x180014e9c`
- `0x1800154b0`
- `0x180015960`
- `0x18002618c`
- `0x180026d04`
- `0x18002799c`
- `0x18003329c`
- `0x18003b764`
- `0x18004e508`
- `0x18004e58c`
- `0x18006f1c9`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b98e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b98e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bc52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003bb2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003bb39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003bb2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x18003bb39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bcee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bcfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b949`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b9e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bad4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bb9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bbd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bcee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003bcfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bcc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bcd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bcc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bcd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ba81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bb53`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ba81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003bb53`
- `ntdll!RtlEqualSid` at `0x18003b9c9`
- `ntdll!RtlEqualSid` at `0x18003b9c9`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18003b8cf`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18003b8cf`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18003ba4b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18003baac`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18003ba4b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18003baac`

## string_xrefs

- `0x18003bd56`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bd6a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bd7e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bd95`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bda9`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bdbd`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bdd2`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bde6`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bdf7`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003be0e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003be23`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003be3a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003be4e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003be63`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003be7b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003be8f`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bea3`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003beb7`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003becb`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003bedf`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall UserMgrCli::GetUserMarshalData(UserMgrCli *this, void *a2, unsigned int a3, struct _USER_DATA **a4)
{
  unsigned __int64 v4; // rbp
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, unsigned __int64); // rbx
  int v13; // eax
  void *v14; // rdx
  int ExtendedCallerInformation; // eax
  int valid; // eax
  void (__fastcall *v17)(void *, unsigned __int64); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, unsigned __int64); // rbx
  int v21; // eax
  __int64 v22; // rdi
  unsigned int (__fastcall *v23)(__int64, PCWSTR, unsigned __int64); // rbx
  PCWSTR StringRawBuffer; // rax
  const char *v25; // r9
  LONG PackageFamilyNameFromToken; // eax
  unsigned __int64 v27; // r9
  _WORD *v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, PVOID, unsigned __int64); // rbx
  HSTRING_HEADER *v32; // rax
  int v33; // eax
  UINT32 StringLen; // ebx
  UINT32 v35; // edi
  _QWORD *v36; // rax
  int v37; // eax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, unsigned __int64); // rbx
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, unsigned __int64); // rbx
  int v43; // eax
  _QWORD *v44; // rcx
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rdi
  const unsigned __int16 *v47; // rax
  int v48; // eax
  const unsigned __int16 *v49; // rax
  int v50; // eax
  const struct _tlgProvider_t *v51; // rax
  int v52; // r8d
  int v53; // r9d
  void *v54; // rcx
  void *v55; // rcx
  __int64 result; // rax
  const struct _tlgProvider_t *v57; // rax
  int v58; // ebx
  wil *v59; // rcx
  int v60; // r8d
  int v61; // r9d
  int v62; // [rsp+20h] [rbp-30h]
  PSID Sid2; // [rsp+50h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+2E8h] [rbp+298h]

  v4 = (unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_DWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = a3;
  v7 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    *(_DWORD *)v4 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v7,
      (unsigned int)&unk_1801293C0,
      v8,
      v9,
      (unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL);
  }
  memset_0((void *)(v4 + 128), 0, 0x1C0u);
  try
  {
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    *(_DWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = ((unsigned __int64)&Sid2
                                                                           & 0xFFFFFFFFFFFFFFE0uLL)
                                                                          + 64;
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = ((unsigned __int64)&Sid2
                                                                           & 0xFFFFFFFFFFFFFFE0uLL)
                                                                          + 24;
    *(_BYTE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 1;
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x88C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80004003LL,
        v62);
    v10 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v4 + 96));
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x88E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v10,
        v62);
    v11 = *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60);
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64))(*(_QWORD *)v11 + 192LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v4 + 32);
    v13 = v12(v11, a3, v4 + 32);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x890,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v13,
        v62);
    if ( !*(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x891,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        v62);
    ExtendedCallerInformation = UserMgrCli::GetExtendedCallerInformation(
                                  retaddr,
                                  v14,
                                  (struct _EXTENDED_CALLER_INFORMATION *)(v4 + 128));
    if ( ExtendedCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x893,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)ExtendedCallerInformation,
        v62);
    if ( *(_BYTE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x82) )
    {
      valid = IsValidCallerForUser(
                *(struct Windows::System::IUser **)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
                (struct _BASIC_CALLER_INFORMATION *)(v4 + 128));
      if ( valid < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x89A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)valid,
          v62);
    }
    else if ( *(_DWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) != (unsigned int)RtlGetCurrentServiceSessionId(retaddr)
           || !*(_BYTE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x8C) )
    {
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
      v17 = *(void (__fastcall **)(void *, unsigned __int64))(Windows::System::Internal::Adapters::g_AdapterCollection
                                                            + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4 + 88);
      v17(&Windows::System::Internal::Adapters::g_AdapterCollection, v4 + 88);
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      *(_QWORD *)v4 = 0;
      v18 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v4 + 32),
              (__int64 *)(v4 + 80));
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8A4,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v18,
          v62);
      v19 = *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
      v20 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v19 + 72LL);
      WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8));
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      v21 = v20(v19, v4 + 8);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8A5,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v21,
          v62);
      v22 = *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58);
      v23 = *(unsigned int (__fastcall **)(__int64, PCWSTR, unsigned __int64))(*(_QWORD *)v22 + 40LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        (unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL,
        0);
      StringRawBuffer = WindowsGetStringRawBuffer(
                          *(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8),
                          0);
      if ( !v23(v22, StringRawBuffer, (unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x8A6,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          v25);
      if ( !RtlEqualSid(*(PSID *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0xF8), *(PSID *)v4) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8A8,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)0x80070520LL,
          v62);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL);
      WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8));
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4 + 88);
    }
    if ( !*(_BYTE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x81)
      || *(_BYTE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x82)
      || *(_BYTE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x221)
      || *(_BYTE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x222) )
    {
      v37 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v4 + 32),
              (__int64 *)(v4 + 80));
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8CA,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v37,
          v62);
      v38 = *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
      v39 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v38 + 104LL);
      WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28));
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
      v40 = v39(v38, v4 + 40);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8CC,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v40,
          v62);
      v41 = *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
      v42 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v41 + 48LL);
      WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      v43 = v42(v41, v4 + 16);
      if ( v43 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8CD,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v43,
          v62);
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v4 + 72,
        0);
      GetCallerToken((PHANDLE)(v4 + 72));
      PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(
                                     *(HANDLE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48),
                                     (UINT32 *)(v4 + 48),
                                     0);
      if ( PackageFamilyNameFromToken > 0 )
        v27 = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
      else
        v27 = (unsigned int)PackageFamilyNameFromToken;
      if ( PackageFamilyNameFromToken != 122 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8BC,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)v27,
          v62);
      v28 = LocalAlloc(0x40u, 2LL * *(unsigned int *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30));
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = v28;
      if ( !v28 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8BF,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)0x8007000ELL,
          v62);
      *v28 = 0;
      v29 = GetPackageFamilyNameFromToken(
              *(HANDLE *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48),
              (UINT32 *)(v4 + 48),
              *(PWSTR *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40));
      if ( v29 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x8C2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)v29,
          v62);
      v30 = *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60);
      v31 = *(__int64 (__fastcall **)(__int64, _QWORD, PVOID, unsigned __int64))(*(_QWORD *)v30 + 200LL);
      WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              (HSTRING_HEADER *)(v4 + 576),
              (const WCHAR **)(v4 + 64));
      v33 = v31(
              v30,
              *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
              v32[1].Reserved.Reserved1,
              v4 + 16);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8C4,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v33,
          v62);
      Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)(v4 + 40), &cchOriginalDestLength, 0);
    }
    StringLen = WindowsGetStringLen(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28));
    v35 = WindowsGetStringLen(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
    v36 = LocalAlloc(0x40u, 2LL * (StringLen + v35 + 2) + 16);
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = v36;
    if ( !v36 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8007000ELL,
        v62);
    v44 = v36 + 2;
    *v36 = v36 + 2;
    v45 = v35 + 1;
    v46 = v45;
    *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) + 8LL) = (char *)v44 + 2 * v45;
    v47 = WindowsGetStringRawBuffer(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28), 0);
    v48 = StringCchCopyW(
            *(unsigned __int16 **)(*(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) + 8LL),
            StringLen + 1,
            v47);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v48,
        v62);
    v49 = WindowsGetStringRawBuffer(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10), 0);
    v50 = StringCchCopyW(**(unsigned __int16 ***)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18), v46, v49);
    if ( v50 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v50,
        v62);
    *a4 = *(struct _USER_DATA **)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    v51 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v51 > 5u )
    {
      *(_DWORD *)v4 = 0;
      *(_DWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v51,
        (unsigned int)&word_18012937E,
        v52,
        v53,
        v4 + 8,
        (unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL);
    }
    v54 = *(void **)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
    if ( v54 )
    {
      LocalFree(v54);
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    }
    v55 = *(void **)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v55 )
    {
      LocalFree(v55);
      *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v4 + 72);
    WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28));
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    WindowsDeleteString(*(HSTRING *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10));
    *(_QWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v4 + 80);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v4 + 32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4 + 96);
    result = 0;
  }
  catch ( ... )
  {
    v57 = UserMgrUserModelTelemetry::Provider();
    v58 = (int)v57;
    v59 = (wil *)*(unsigned int *)v57;
    if ( (unsigned int)v59 > 5 )
    {
      *(_DWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v59);
      *(_DWORD *)((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) = *(_DWORD *)(((unsigned __int64)&Sid2
                                                                                & 0xFFFFFFFFFFFFFFE0uLL)
                                                                               + 0x38);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v58,
        (unsigned int)byte_180129329,
        v60,
        v61,
        (unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL,
        ((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    }
    *(_DWORD *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = wil::ResultFromCaughtException(v59);
    return *(unsigned int *)(((unsigned __int64)&Sid2 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
  }
  return result;
}

```

## disassembly

```asm
0x18003b764  mov     [rsp-8+arg_0], rbx
0x18003b769  push    rbp
0x18003b76a  push    rsi
0x18003b76b  push    rdi
0x18003b76c  push    r14
0x18003b76e  push    r15
0x18003b770  sub     rsp, 2C0h
0x18003b777  lea     rbp, [rsp+50h]
0x18003b77c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18003b780  mov     rax, cs:__security_cookie
0x18003b787  xor     rax, rsp
0x18003b78a  mov     [rbp+290h+var_30], rax
0x18003b791  mov     r14, r9
0x18003b794  mov     esi, r8d
0x18003b797  mov     [rbp+290h+var_258], r8d
0x18003b79b  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18003b7a0  mov     ecx, [rax]
0x18003b7a2  cmp     ecx, 5
0x18003b7a5  jbe     short loc_18003B7C2
0x18003b7a7  mov     dword ptr [rbp+290h+Sid2], esi
0x18003b7aa  lea     rcx, [rbp+290h+Sid2]
0x18003b7ae  mov     qword ptr [rsp+2E0h+var_2C0], rcx; int
0x18003b7b3  lea     rdx, unk_1801293C0
0x18003b7ba  mov     rcx, rax
0x18003b7bd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003b7c2  xor     edx, edx; Val
0x18003b7c4  mov     r8d, 1C0h; Size
0x18003b7ca  lea     rcx, [rbp+290h+var_210]; void *
0x18003b7d1  call    memset_0
0x18003b7d6  xor     r15d, r15d
0x18003b7d9  mov     [rbp+290h+var_230], r15
0x18003b7dd  mov     [rbp+290h+var_270], r15
0x18003b7e1  mov     [rbp+290h+var_240], r15
0x18003b7e5  mov     [rbp+290h+var_280], r15
0x18003b7e9  mov     [rbp+290h+var_268], r15
0x18003b7ed  mov     [rbp+290h+hMem], r15
0x18003b7f1  mov     [rbp+290h+token], r15
0x18003b7f5  mov     [rbp+290h+packageFamilyName], r15
0x18003b7f9  mov     [rbp+290h+packageFamilyNameLength], r15d
0x18003b7fd  lea     rax, [rbp+290h+packageFamilyName]
0x18003b801  mov     [rbp+290h+var_228], rax
0x18003b805  lea     rax, [rbp+290h+hMem]
0x18003b809  mov     [rbp+290h+var_220], rax
0x18003b80d  mov     [rbp+290h+var_218], 1
0x18003b811  mov     rcx, [rsp+2E8h]; this
0x18003b819  test    r14, r14
0x18003b81c  jz      loc_18003BD50
0x18003b822  lea     rcx, [rbp+290h+var_230]
0x18003b826  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x18003b82b  mov     rcx, [rsp+2E8h]; this
0x18003b833  test    eax, eax
0x18003b835  js      loc_18003BD67
0x18003b83b  mov     rdi, [rbp+290h+var_230]
0x18003b83f  mov     rax, [rdi]
0x18003b842  mov     rbx, [rax+0C0h]
0x18003b849  lea     rcx, [rbp+290h+var_270]
0x18003b84d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003b852  lea     r8, [rbp+290h+var_270]
0x18003b856  mov     edx, esi
0x18003b858  mov     rcx, rdi
0x18003b85b  mov     rax, rbx
0x18003b85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b863  mov     rcx, [rsp+2E8h]; this
0x18003b86b  test    eax, eax
0x18003b86d  js      loc_18003BD7B
0x18003b873  mov     rcx, [rsp+2E8h]; this
0x18003b87b  cmp     [rbp+290h+var_270], r15
0x18003b87f  jz      loc_18003BD8F
0x18003b885  lea     r8, [rbp+290h+var_210]; struct _EXTENDED_CALLER_INFORMATION *
0x18003b88c  call    ?GetExtendedCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_EXTENDED_CALLER_INFORMATION@@@Z; UserMgrCli::GetExtendedCallerInformation(void *,_EXTENDED_CALLER_INFORMATION *)
0x18003b891  mov     rcx, [rsp+2E8h]; this
0x18003b899  test    eax, eax
0x18003b89b  js      loc_18003BDA6
0x18003b8a1  cmp     [rbp+290h+var_20E], r15b
0x18003b8a8  jz      short loc_18003B8CF
0x18003b8aa  lea     rdx, [rbp+290h+var_210]; struct _BASIC_CALLER_INFORMATION *
0x18003b8b1  mov     rcx, [rbp+290h+var_270]; struct Windows::System::IUser *
0x18003b8b5  call    ?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z; IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)
0x18003b8ba  mov     rcx, [rsp+2E8h]; this
0x18003b8c2  test    eax, eax
0x18003b8c4  js      loc_18003BDBA
0x18003b8ca  jmp     loc_18003B9F8
0x18003b8cf  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18003b8d5  cmp     [rbp+290h+var_208], eax
0x18003b8db  jnz     short loc_18003B8EA
0x18003b8dd  cmp     [rbp+290h+var_204], r15b
0x18003b8e4  jnz     loc_18003B9F8
0x18003b8ea  mov     [rbp+290h+var_238], r15
0x18003b8ee  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18003b8f5  mov     rbx, [rax+38h]
0x18003b8f9  lea     rcx, [rbp+290h+var_238]
0x18003b8fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b902  lea     rdx, [rbp+290h+var_238]
0x18003b906  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18003b90d  mov     rax, rbx
0x18003b910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b915  mov     [rbp+290h+string], r15
0x18003b919  mov     [rbp+290h+Sid2], r15
0x18003b91d  lea     rdx, [rbp+290h+var_240]
0x18003b921  lea     rcx, [rbp+290h+var_270]
0x18003b925  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18003b92a  mov     rcx, [rsp+2E8h]; this
0x18003b932  test    eax, eax
0x18003b934  js      loc_18003BDCF
0x18003b93a  mov     rdi, [rbp+290h+var_240]
0x18003b93e  mov     rax, [rdi]
0x18003b941  mov     rbx, [rax+48h]
0x18003b945  mov     rcx, [rbp+290h+string]; string
0x18003b949  call    cs:__imp_WindowsDeleteString
0x18003b94f  mov     [rbp+290h+string], r15
0x18003b953  lea     rdx, [rbp+290h+string]
0x18003b957  mov     rcx, rdi
0x18003b95a  mov     rax, rbx
0x18003b95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b962  mov     rcx, [rsp+2E8h]; this
0x18003b96a  test    eax, eax
0x18003b96c  js      loc_18003BDE3
0x18003b972  mov     rdi, [rbp+290h+var_238]
0x18003b976  mov     rax, [rdi]
0x18003b979  mov     rbx, [rax+28h]
0x18003b97d  xor     edx, edx
0x18003b97f  lea     rcx, [rbp+290h+Sid2]
0x18003b983  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003b988  xor     edx, edx; length
0x18003b98a  mov     rcx, [rbp+290h+string]; string
0x18003b98e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b994  lea     r8, [rbp+290h+Sid2]
0x18003b998  mov     rdx, rax
0x18003b99b  mov     rcx, rdi
0x18003b99e  mov     rax, rbx
0x18003b9a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9a6  mov     rcx, [rsp+2E8h]; this
0x18003b9ae  test    eax, eax
0x18003b9b0  jz      loc_18003BDF7
0x18003b9b6  mov     rbx, [rsp+2E8h]
0x18003b9be  mov     rdx, [rbp+290h+Sid2]; Sid2
0x18003b9c2  mov     rcx, [rbp+290h+Sid1]; Sid1
0x18003b9c9  call    cs:__imp_RtlEqualSid
0x18003b9cf  test    al, al
0x18003b9d1  jz      loc_18003BE08
0x18003b9d7  lea     rcx, [rbp+290h+Sid2]
0x18003b9db  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003b9e0  nop
0x18003b9e1  mov     rcx, [rbp+290h+string]; string
0x18003b9e5  call    cs:__imp_WindowsDeleteString
0x18003b9eb  mov     [rbp+290h+string], r15
0x18003b9ef  lea     rcx, [rbp+290h+var_238]
0x18003b9f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b9f8  cmp     [rbp+290h+var_20F], r15b
0x18003b9ff  jz      loc_18003BB73
0x18003ba05  cmp     [rbp+290h+var_20E], r15b
0x18003ba0c  jnz     loc_18003BB73
0x18003ba12  cmp     [rbp+290h+var_6F], r15b
0x18003ba19  jnz     loc_18003BB73
0x18003ba1f  cmp     [rbp+290h+var_6E], r15b
0x18003ba26  jnz     loc_18003BB73
0x18003ba2c  xor     edx, edx
0x18003ba2e  lea     rcx, [rbp+290h+token]
0x18003ba32  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003ba37  lea     rcx, [rbp+290h+token]; phNewToken
0x18003ba3b  call    ?GetCallerToken@@YAJPEAPEAX@Z; GetCallerToken(void * *)
0x18003ba40  xor     r8d, r8d; packageFamilyName
0x18003ba43  lea     rdx, [rbp+290h+packageFamilyNameLength]; packageFamilyNameLength
0x18003ba47  mov     rcx, [rbp+290h+token]; token
0x18003ba4b  call    cs:__imp_GetPackageFamilyNameFromToken
0x18003ba51  test    eax, eax
0x18003ba53  jg      short loc_18003BA5A
0x18003ba55  mov     r9d, eax
0x18003ba58  jmp     short loc_18003BA65
0x18003ba5a  movzx   r9d, ax
0x18003ba5e  or      r9d, 80070000h; char *
0x18003ba65  mov     rcx, [rsp+2E8h]; this
0x18003ba6d  cmp     eax, 7Ah ; 'z'
0x18003ba70  jnz     loc_18003BE23
0x18003ba76  mov     edx, [rbp+290h+packageFamilyNameLength]
0x18003ba79  add     rdx, rdx; uBytes
0x18003ba7c  mov     ecx, 40h ; '@'; uFlags
0x18003ba81  call    cs:__imp_LocalAlloc
0x18003ba87  mov     [rbp+290h+packageFamilyName], rax
0x18003ba8b  mov     rcx, [rsp+2E8h]; this
0x18003ba93  test    rax, rax
0x18003ba96  jz      loc_18003BE34
0x18003ba9c  mov     [rax], r15w
0x18003baa0  mov     r8, [rbp+290h+packageFamilyName]; packageFamilyName
0x18003baa4  lea     rdx, [rbp+290h+packageFamilyNameLength]; packageFamilyNameLength
0x18003baa8  mov     rcx, [rbp+290h+token]; token
0x18003baac  call    cs:__imp_GetPackageFamilyNameFromToken
0x18003bab2  mov     rcx, [rsp+2E8h]; this
0x18003baba  test    eax, eax
0x18003babc  jnz     loc_18003BE4B
0x18003bac2  mov     rdi, [rbp+290h+var_230]
0x18003bac6  mov     rax, [rdi]
0x18003bac9  mov     rbx, [rax+0C8h]
0x18003bad0  mov     rcx, [rbp+290h+var_280]; string
0x18003bad4  call    cs:__imp_WindowsDeleteString
0x18003bada  mov     [rbp+290h+var_280], r15
0x18003bade  lea     rdx, [rbp+290h+packageFamilyName]
0x18003bae2  lea     rcx, [rbp+290h+var_50]
0x18003bae9  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18003baee  nop
0x18003baef  lea     r9, [rbp+290h+var_280]
0x18003baf3  mov     r8, [rax+18h]
0x18003baf7  mov     rdx, [rbp+290h+var_270]
0x18003bafb  mov     rcx, rdi
0x18003bafe  mov     rax, rbx
0x18003bb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb06  mov     rcx, [rsp+2E8h]; this
0x18003bb0e  test    eax, eax
0x18003bb10  js      loc_18003BE60
0x18003bb16  xor     r8d, r8d; unsigned int
0x18003bb19  lea     rdx, cchOriginalDestLength; unsigned __int16 *
0x18003bb20  lea     rcx, [rbp+290h+var_268]; this
0x18003bb24  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18003bb29  mov     rcx, [rbp+290h+var_268]; string
0x18003bb2d  call    cs:__imp_WindowsGetStringLen
0x18003bb33  mov     ebx, eax
0x18003bb35  mov     rcx, [rbp+290h+var_280]; string
0x18003bb39  call    cs:__imp_WindowsGetStringLen
0x18003bb3f  mov     edi, eax
0x18003bb41  lea     edx, [rax+2]
0x18003bb44  add     edx, ebx
0x18003bb46  lea     rdx, ds:10h[rdx*2]; uBytes
0x18003bb4e  mov     ecx, 40h ; '@'; uFlags
0x18003bb53  call    cs:__imp_LocalAlloc
0x18003bb59  mov     [rbp+290h+hMem], rax
0x18003bb5d  mov     rcx, [rsp+2E8h]; this
0x18003bb65  test    rax, rax
0x18003bb68  jz      loc_18003BE75
0x18003bb6e  jmp     loc_18003BC05
0x18003bb73  lea     rdx, [rbp+290h+var_240]
0x18003bb77  lea     rcx, [rbp+290h+var_270]
0x18003bb7b  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18003bb80  mov     rcx, [rsp+2E8h]; this
0x18003bb88  test    eax, eax
0x18003bb8a  js      loc_18003BE8C
0x18003bb90  mov     rdi, [rbp+290h+var_240]
0x18003bb94  mov     rax, [rdi]
0x18003bb97  mov     rbx, [rax+68h]
0x18003bb9b  mov     rcx, [rbp+290h+var_268]; string
0x18003bb9f  call    cs:__imp_WindowsDeleteString
0x18003bba5  mov     [rbp+290h+var_268], r15
0x18003bba9  lea     rdx, [rbp+290h+var_268]
0x18003bbad  mov     rcx, rdi
0x18003bbb0  mov     rax, rbx
0x18003bbb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbb8  mov     rcx, [rsp+2E8h]; this
0x18003bbc0  test    eax, eax
0x18003bbc2  js      loc_18003BEA0
0x18003bbc8  mov     rdi, [rbp+290h+var_270]
0x18003bbcc  mov     rax, [rdi]
0x18003bbcf  mov     rbx, [rax+30h]
0x18003bbd3  mov     rcx, [rbp+290h+var_280]; string
0x18003bbd7  call    cs:__imp_WindowsDeleteString
0x18003bbdd  mov     [rbp+290h+var_280], r15
0x18003bbe1  lea     rdx, [rbp+290h+var_280]
0x18003bbe5  mov     rcx, rdi
0x18003bbe8  mov     rax, rbx
0x18003bbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbf0  mov     rcx, [rsp+2E8h]; this
0x18003bbf8  test    eax, eax
0x18003bbfa  js      loc_18003BEB4
0x18003bc00  jmp     loc_18003BB29
0x18003bc05  lea     rcx, [rax+10h]
0x18003bc09  mov     [rax], rcx
0x18003bc0c  lea     eax, [rdi+1]
0x18003bc0f  mov     edi, eax
0x18003bc11  lea     rcx, [rcx+rax*2]
0x18003bc15  mov     rax, [rbp+290h+hMem]
0x18003bc19  mov     [rax+8], rcx
0x18003bc1d  xor     edx, edx; length
0x18003bc1f  mov     rcx, [rbp+290h+var_268]; string
0x18003bc23  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bc29  lea     edx, [rbx+1]; unsigned __int64
0x18003bc2c  mov     r8, rax; unsigned __int16 *
0x18003bc2f  mov     rcx, [rbp+290h+hMem]
0x18003bc33  mov     rcx, [rcx+8]; unsigned __int16 *
0x18003bc37  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bc3c  mov     rcx, [rsp+2E8h]; this
0x18003bc44  test    eax, eax
0x18003bc46  js      loc_18003BEC8
0x18003bc4c  xor     edx, edx; length
0x18003bc4e  mov     rcx, [rbp+290h+var_280]; string
0x18003bc52  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bc58  mov     r8, rax; unsigned __int16 *
0x18003bc5b  mov     rdx, rdi; unsigned __int64
0x18003bc5e  mov     rcx, [rbp+290h+hMem]
0x18003bc62  mov     rcx, [rcx]; unsigned __int16 *
0x18003bc65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bc6a  mov     rcx, [rsp+2E8h]; this
0x18003bc72  test    eax, eax
0x18003bc74  js      loc_18003BEDC
0x18003bc7a  mov     rax, [rbp+290h+hMem]
0x18003bc7e  mov     [r14], rax
0x18003bc81  mov     [rbp+290h+hMem], r15
0x18003bc85  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18003bc8a  mov     ecx, [rax]
0x18003bc8c  cmp     ecx, 5
0x18003bc8f  jbe     short loc_18003BCBA
0x18003bc91  mov     dword ptr [rbp+290h+Sid2], r15d
0x18003bc95  mov     dword ptr [rbp+290h+string], esi
  ... truncated ...
```
