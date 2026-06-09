# Windows::System::Internal::ValidateCredentialsAsyncOperation::DoWork(void)

- ea: `0x1800c89f0`
- end: `0x1800c984f`
- name: `?DoWork@ValidateCredentialsAsyncOperation@Internal@System@Windows@@UEAAJXZ`
- size: `3679`
- prototype: `__int64 __fastcall(Windows::System::Internal::ValidateCredentialsAsyncOperation *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003b8c`
- `0x180006130`
- `0x180007920`
- `0x18000acdc`
- `0x18000cd30`
- `0x18000ce48`
- `0x18000ed00`
- `0x180012890`
- `0x180014e7c`
- `0x180018b60`
- `0x180035938`
- `0x18004e4e8`
- `0x18004e58c`
- `0x1800624bc`
- `0x180084f5c`
- `0x1800c8280`
- `0x1800c82bc`
- `0x1800c879c`
- `0x1800c89f0`
- `0x1800ca0f0`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800c917f`
- `msvcrt!_wcsicmp` at `0x1800c917f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c91ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c91ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c8a26`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c94a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c8a26`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c94a0`
- `ntdll!NtQueryInformationToken` at `0x1800c8da1`
- `ntdll!NtQueryInformationToken` at `0x1800c8da1`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800c8ea5`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800c8ea5`
- `ntdll!RtlInitString` at `0x1800c8e70`
- `ntdll!RtlInitString` at `0x1800c8e85`
- `ntdll!RtlInitString` at `0x1800c8e70`
- `ntdll!RtlInitString` at `0x1800c8e85`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x1800c8f04`
- `SspiCli!SeciAllocateAndSetCallFlags` at `0x1800c8f04`

## string_xrefs

- `0x1800c9612`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9626`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c963a`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c964e`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9665`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9679`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c968d`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c96a1`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c96b8`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c96cf`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c96e6`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c96fd`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9711`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9725`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9739`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c974d`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9762`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9773`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9787`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c979b`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c97b0`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c97c4`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c97d8`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c97ec`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9800`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9814`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c9828`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`
- `0x1800c983c`: `onecore\ds\security\umstartup\usermgr\lib\validatecredentialsasyncoperation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall Windows::System::Internal::ValidateCredentialsAsyncOperation::DoWork(
        Windows::System::Internal::ValidateCredentialsAsyncOperation *this)
{
  int v2; // r15d
  void (__fastcall *v3)(void *, __int64 *); // rbx
  void (__fastcall *v4)(void *, __int64 *); // rbx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 (__fastcall ****v11)(_QWORD, GUID *, __int64 *); // r13
  __int64 v12; // rbx
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // r14d
  int v21; // eax
  bool v22; // zf
  void (__fastcall *v23)(void *, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdi
  unsigned int (__fastcall *v26)(__int64, __int64, wchar_t **); // rbx
  const char *v27; // r9
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  int v31; // eax
  wchar_t *v32; // rbx
  const wchar_t *StringRawBuffer; // rax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64, Windows::System::Internal::ValidateCredentialsAsyncOperation **); // rbx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // ebx
  char *v41; // rcx
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // edi
  ULONGLONG v46; // rbx
  const struct _tlgProvider_t *v47; // rax
  int v48; // r8d
  int v49; // r9d
  int ReturnLength; // [rsp+20h] [rbp-2D8h]
  int ReturnLengtha; // [rsp+20h] [rbp-2D8h]
  int ReturnLengthb; // [rsp+20h] [rbp-2D8h]
  int v54; // [rsp+80h] [rbp-278h] BYREF
  int v55; // [rsp+84h] [rbp-274h] BYREF
  int v56; // [rsp+88h] [rbp-270h] BYREF
  int v57; // [rsp+8Ch] [rbp-26Ch] BYREF
  int v58; // [rsp+90h] [rbp-268h] BYREF
  HSTRING string; // [rsp+98h] [rbp-260h] BYREF
  Windows::System::Internal::ValidateCredentialsAsyncOperation *v60; // [rsp+A0h] [rbp-258h] BYREF
  int v61[2]; // [rsp+A8h] [rbp-250h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-248h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-240h] BYREF
  int v64; // [rsp+C0h] [rbp-238h] BYREF
  int v65; // [rsp+C4h] [rbp-234h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-230h] BYREF
  __int64 (__fastcall ***v67)(_QWORD, GUID *, __int64); // [rsp+D0h] [rbp-228h] BYREF
  __int64 v68; // [rsp+D8h] [rbp-220h] BYREF
  __int64 v69; // [rsp+E0h] [rbp-218h] BYREF
  __int64 v70; // [rsp+E8h] [rbp-210h] BYREF
  Windows::System::Internal::ValidateCredentialsAsyncOperation *v71; // [rsp+F0h] [rbp-208h] BYREF
  __int64 v72; // [rsp+F8h] [rbp-200h] BYREF
  wchar_t *String2; // [rsp+100h] [rbp-1F8h] BYREF
  __int64 v74; // [rsp+108h] [rbp-1F0h] BYREF
  __int64 v75; // [rsp+110h] [rbp-1E8h] BYREF
  __int64 v76; // [rsp+118h] [rbp-1E0h] BYREF
  ULONG v77; // [rsp+120h] [rbp-1D8h] BYREF
  _DWORD v78[2]; // [rsp+124h] [rbp-1D4h] BYREF
  int v79; // [rsp+12Ch] [rbp-1CCh] BYREF
  __int64 v80; // [rsp+130h] [rbp-1C8h] BYREF
  __int64 v81; // [rsp+138h] [rbp-1C0h] BYREF
  ULONGLONG TickCount64; // [rsp+140h] [rbp-1B8h] BYREF
  HANDLE TokenHandle; // [rsp+148h] [rbp-1B0h] BYREF
  __int64 v84; // [rsp+150h] [rbp-1A8h]
  _QWORD v85[2]; // [rsp+158h] [rbp-1A0h] BYREF
  struct _STRING DestinationString; // [rsp+168h] [rbp-190h] BYREF
  struct _STRING v87; // [rsp+178h] [rbp-180h] BYREF
  _QWORD v88[7]; // [rsp+190h] [rbp-168h] BYREF
  char v89; // [rsp+1C8h] [rbp-130h]
  LUID LocallyUniqueId[2]; // [rsp+1D0h] [rbp-128h] BYREF
  int TokenInformation; // [rsp+1E0h] [rbp-118h] BYREF
  __int128 v92; // [rsp+1E4h] [rbp-114h]
  __int128 v93; // [rsp+1F4h] [rbp-104h]
  __int128 v94; // [rsp+204h] [rbp-F4h]
  int v95; // [rsp+214h] [rbp-E4h]
  __int128 v96; // [rsp+218h] [rbp-E0h]
  __int128 v97; // [rsp+228h] [rbp-D0h]
  __int128 v98; // [rsp+238h] [rbp-C0h]
  __int64 v99[12]; // [rsp+250h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  v71 = this;
  v85[1] = this;
  TickCount64 = GetTickCount64();
  v68 = 0;
  v62 = 0;
  v60 = 0;
  v70 = 0;
  v69 = 0;
  v76 = 0;
  v67 = 0;
  v75 = 0;
  v78[0] = 0;
  v81 = 0;
  v66 = 0;
  v58 = 0;
  v64 = 0;
  DestinationString = 0;
  v87 = 0;
  *(_OWORD *)&LocallyUniqueId[0].LowPart = 0;
  v74 = -1;
  v84 = 0;
  v80 = 0;
  v78[1] = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v54 = 0;
  v55 = 0;
  v65 = 0;
  *(_QWORD *)v61 = 0;
  v79 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v77 = 0;
  v2 = 2;
  v56 = 2;
  v85[0] = -1;
  v88[0] = &v64;
  v88[1] = &v74;
  v88[2] = v85;
  v88[3] = &v81;
  v88[4] = &v62;
  v88[5] = &v80;
  v88[6] = &v66;
  v89 = 1;
  v3 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  v3(&Windows::System::Internal::Adapters::g_AdapterCollection, &v68);
  v4 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  v4(&Windows::System::Internal::Adapters::g_AdapterCollection, &v62);
  v5 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(&v76);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v5,
      ReturnLength);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  v6 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
         (char *)this + 224,
         &GUID_c39ab8a5_824f_4acf_92e0_bb53b8a90555,
         &v67);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v6,
      ReturnLength);
  v7 = Microsoft::WRL::ComPtr<Windows::System::Internal::ICredentialSerialization>::As<ICredentialSerializationProvider>(
         &v67,
         (__int64)&v75);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v7,
      ReturnLength);
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v75 + 32LL))(v75, &v66);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v8,
      ReturnLength);
  v10 = v66;
  if ( !v66 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLength);
  if ( (byte_180147C81 & 1) != 0 )
  {
    McTemplateU0qq_EventWriteTransfer(retaddr, v9, *(unsigned int *)(v66 + 4), *(unsigned int *)(v66 + 8));
    v10 = v66;
  }
  v11 = (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))((char *)this + 208);
  if ( *((_QWORD *)this + 26) )
  {
    v12 = *(_QWORD *)(v10 + 16);
    v13 = *(_DWORD *)(v10 + 8);
    v14 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            v11,
            &v69);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
        (const char *)(unsigned int)v14,
        ReturnLength);
    v15 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v69 + 80LL))(v69, &TokenHandle);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
        (const char *)(unsigned int)v15,
        ReturnLength);
    v16 = NtQueryInformationToken(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &v77);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
        (const char *)(unsigned int)v16,
        ReturnLength);
    v63 = *(_QWORD *)((char *)&v92 + 4);
    v84 = *(_QWORD *)((char *)&v92 + 4);
    switch ( *(_DWORD *)v12 )
    {
      case 7:
        if ( v13 < 0x40 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBA,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
            (const char *)0x80070057LL,
            ReturnLength);
        *(_QWORD *)(v12 + 56) = *(_QWORD *)((char *)&v92 + 4);
        break;
      case 8:
        if ( v13 < 0x30 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
            (const char *)0x80070057LL,
            ReturnLength);
        *(_QWORD *)(v12 + 40) = *(_QWORD *)((char *)&v92 + 4);
        break;
      case 0xB:
        if ( v13 < 0x28 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC4,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
            (const char *)0x80070057LL,
            ReturnLength);
        *(_QWORD *)(v12 + 32) = *(_QWORD *)((char *)&v92 + 4);
        break;
      case 0xF:
        if ( v13 < 0x50 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC9,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
            (const char *)0x80070057LL,
            ReturnLength);
        *(_QWORD *)(v12 + 72) = *(_QWORD *)((char *)&v92 + 4);
        break;
      default:
        goto LABEL_25;
    }
    v2 = 7;
    v56 = 7;
  }
LABEL_25:
  RtlInitString(&DestinationString, "UserManager");
  RtlInitString(&v87, "ValidateCredentialsAsync");
  LocallyUniqueId[0] = (LUID)0x72674D72657355LL;
  v17 = NtAllocateLocallyUniqueId(&LocallyUniqueId[1]);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v17,
      ReturnLength);
  v18 = (*(__int64 (__fastcall **)(__int64, struct _STRING *, __int64 *, _DWORD *))(*(_QWORD *)v62 + 24LL))(
          v62,
          &DestinationString,
          &v81,
          v78);
  if ( v18 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v18,
      ReturnLength);
  SeciAllocateAndSetCallFlags(128, &v64);
  v19 = SetNtlmThreadOptions(0, 1u);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v19,
      ReturnLength);
  ReturnLengtha = *(_DWORD *)(v66 + 4);
  v20 = (*(__int64 (__fastcall **)(__int64, __int64, struct _STRING *, __int64))(*(_QWORD *)v62 + 32LL))(
          v62,
          v81,
          &v87,
          7);
  v54 = v20;
  v21 = SetNtlmThreadOptions(1, 1u);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v21,
      ReturnLengtha);
  v22 = v20 == 0;
  if ( v20 >= 0 )
  {
    if ( *v11 )
    {
      v57 = 0;
      String2 = 0;
      v63 = 0;
      string = 0;
      v72 = 0;
      v23 = *(void (__fastcall **)(void *, __int64 *))(Windows::System::Internal::Adapters::g_AdapterCollection + 88LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      v23(&Windows::System::Internal::Adapters::g_AdapterCollection, &v72);
      ReturnLengtha = 84;
      v24 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v72 + 24LL))(v72, v74, 1, v99);
      if ( v24 < 0 )
        wil::details::in1diag3::_Throw_NtStatus(
          retaddr,
          (void *)0xFC,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
          (const char *)(unsigned int)v24,
          84);
      v25 = v68;
      v26 = *(unsigned int (__fastcall **)(__int64, __int64, wchar_t **))(*(_QWORD *)v68 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &String2,
        0);
      if ( !v26(v25, v99[0], &String2) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
          v27);
      v28 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              v11,
              &v63);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
          (const char *)(unsigned int)v28,
          84);
      v29 = v63;
      v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v63 + 72LL);
      WindowsDeleteString(string);
      string = 0;
      v31 = v30(v29, &string);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
          (const char *)(unsigned int)v31,
          84);
      v32 = String2;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( _wcsicmp(StringRawBuffer, v32) )
        v20 = -2136862969;
      v54 = v20;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v63);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&String2);
    }
    v22 = v20 == 0;
  }
  if ( v22 )
  {
    v55 = 0;
  }
  else if ( v20 < 0 )
  {
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x10D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v20,
      ReturnLengtha);
  }
  if ( v80 && (*(_DWORD *)v80 == 2 || *(_DWORD *)v80 == 4 || *(_DWORD *)v80 == 6) )
    *(_QWORD *)v61 = *(_QWORD *)(v80 + 96);
  v34 = v76;
  v35 = *(__int64 (__fastcall **)(__int64, __int64, Windows::System::Internal::ValidateCredentialsAsyncOperation **))(*(_QWORD *)v76 + 176LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
  v36 = v35(v34, v74, &v60);
  if ( v36 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v36,
      ReturnLengtha);
  if ( !v60 )
  {
    if ( v2 == 7 )
      MicrosoftTelemetryAssertTriggeredNoArgs(retaddr);
    v44 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::ValidateCredentialsResult,Windows::System::Internal::IValidateCredentialsResult,long &,long &,unsigned short const * &>(
            (char *)v71 + 240,
            &v54,
            &v55,
            v61);
    if ( v44 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
        (const char *)(unsigned int)v44,
        ReturnLengtha);
    goto LABEL_61;
  }
  v37 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v60,
          &v70);
  if ( v37 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v37,
      ReturnLengtha);
  v38 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v70 + 48LL))(v70, &v79);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v38,
      ReturnLengtha);
  v39 = (*(__int64 (__fastcall **)(Windows::System::Internal::ValidateCredentialsAsyncOperation *, int *))(*(_QWORD *)v60 + 56LL))(
          v60,
          &v65);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v39,
      ReturnLengtha);
  v40 = (_DWORD)v71 + 240;
  v41 = (char *)v71 + 240;
  if ( !v65 )
  {
    v42 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::ValidateCredentialsResult,Windows::System::Internal::IValidateCredentialsResult,long &,long &,unsigned short const * &>(
            v41,
            &v54,
            &v55,
            v61);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
        (const char *)(unsigned int)v42,
        ReturnLengtha);
LABEL_61:
    v20 = v54;
    goto LABEL_62;
  }
  v71 = v60;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v41);
  v43 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::ValidateCredentialsResult,Windows::System::Internal::IValidateCredentialsResult,Windows::System::IUser *,long &,long &,unsigned short const * &>(
          v40,
          (unsigned int)&v71,
          (unsigned int)&v54,
          (unsigned int)&v55,
          (__int64)v61);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\validatecredentialsasyncoperation.cpp",
      (const char *)(unsigned int)v43,
      ReturnLengthb);
LABEL_62:
  v45 = v58;
  v46 = GetTickCount64();
  v47 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v47 > 5u )
  {
    TickCount64 = v46 - TickCount64;
    v58 = v2;
    v57 = 0;
    v56 = v55;
    v54 = v20;
    v61[0] = 0;
    LODWORD(string) = v45;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v47,
      (unsigned int)byte_18012C693,
      v48,
      v49,
      (__int64)&string,
      (__int64)v61,
      (__int64)&v54,
      (__int64)&v56,
      (__int64)&v57,
      (__int64)&v58,
      (__int64)&TickCount64);
  }
  v89 = 0;
  lambda_78714a471044187c885e2f5bf8802d89_::operator()(v88);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v60);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68);
  return 0;
}

```

## disassembly

```asm
0x1800c89f0  push    rbx
0x1800c89f2  push    rsi
0x1800c89f3  push    rdi
0x1800c89f4  push    r13
0x1800c89f6  push    r14
0x1800c89f8  push    r15
0x1800c89fa  sub     rsp, 2C8h
0x1800c8a01  mov     rax, cs:__security_cookie
0x1800c8a08  xor     rax, rsp
0x1800c8a0b  mov     [rsp+2F8h+var_48], rax
0x1800c8a13  mov     rdi, rcx
0x1800c8a16  mov     [rsp+2F8h+var_208], rcx
0x1800c8a1e  mov     [rsp+2F8h+var_198], rcx
0x1800c8a26  call    cs:__imp_GetTickCount64
0x1800c8a2c  mov     [rsp+2F8h+var_1B8], rax
0x1800c8a34  xor     esi, esi
0x1800c8a36  mov     [rsp+2F8h+var_220], rsi
0x1800c8a3e  mov     [rsp+2F8h+var_248], rsi
0x1800c8a46  mov     [rsp+2F8h+var_258], rsi
0x1800c8a4e  mov     [rsp+2F8h+var_210], rsi
0x1800c8a56  mov     [rsp+2F8h+var_218], rsi
0x1800c8a5e  mov     [rsp+2F8h+var_1E0], rsi
0x1800c8a66  mov     [rsp+2F8h+var_228], rsi
0x1800c8a6e  mov     [rsp+2F8h+var_1E8], rsi
0x1800c8a76  mov     [rsp+2F8h+var_1D4], esi
0x1800c8a7d  mov     [rsp+2F8h+var_1C0], rsi
0x1800c8a85  mov     [rsp+2F8h+var_230], rsi
0x1800c8a8d  mov     [rsp+2F8h+var_268], esi
0x1800c8a94  mov     [rsp+2F8h+var_238], esi
0x1800c8a9b  xorps   xmm0, xmm0
0x1800c8a9e  movups  xmmword ptr [rsp+2F8h+DestinationString.Length], xmm0
0x1800c8aa6  xorps   xmm1, xmm1
0x1800c8aa9  movups  xmmword ptr [rsp+2F8h+var_180.Length], xmm1
0x1800c8ab1  movups  xmmword ptr [rsp+2F8h+LocallyUniqueId.LowPart], xmm0
0x1800c8ab9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c8abd  mov     [rsp+2F8h+var_1F0], rcx
0x1800c8ac5  mov     [rsp+2F8h+var_1A8], rsi
0x1800c8acd  mov     [rsp+2F8h+var_1C8], rsi
0x1800c8ad5  mov     [rsp+2F8h+var_1D0], esi
0x1800c8adc  movups  [rsp+2F8h+var_E0], xmm0
0x1800c8ae4  movups  [rsp+2F8h+var_D0], xmm0
0x1800c8aec  movups  [rsp+2F8h+var_C0], xmm0
0x1800c8af4  mov     [rsp+2F8h+var_278], esi
0x1800c8afb  mov     [rsp+2F8h+var_274], esi
0x1800c8b02  mov     [rsp+2F8h+var_234], esi
0x1800c8b09  mov     qword ptr [rsp+2F8h+var_250], rsi
0x1800c8b11  mov     [rsp+2F8h+var_1CC], esi
0x1800c8b18  mov     [rsp+2F8h+TokenHandle], rsi
0x1800c8b20  mov     [rsp+2F8h+TokenInformation], esi
0x1800c8b27  xor     eax, eax
0x1800c8b29  movups  [rsp+2F8h+var_114], xmm0
0x1800c8b31  movups  [rsp+2F8h+var_104], xmm0
0x1800c8b39  movups  [rsp+2F8h+var_F4], xmm0
0x1800c8b41  mov     [rsp+2F8h+var_E4], eax
0x1800c8b48  mov     [rsp+2F8h+var_1D8], esi
0x1800c8b4f  lea     r15d, [rsi+2]
0x1800c8b53  mov     [rsp+2F8h+var_270], r15d
0x1800c8b5b  mov     [rsp+2F8h+var_1A0], rcx
0x1800c8b63  lea     rax, [rsp+2F8h+var_238]
0x1800c8b6b  mov     [rsp+2F8h+var_168], rax
0x1800c8b73  lea     rax, [rsp+2F8h+var_1F0]
0x1800c8b7b  mov     [rsp+2F8h+var_160], rax
0x1800c8b83  lea     rax, [rsp+2F8h+var_1A0]
0x1800c8b8b  mov     [rsp+2F8h+var_158], rax
0x1800c8b93  lea     rax, [rsp+2F8h+var_1C0]
0x1800c8b9b  mov     [rsp+2F8h+var_150], rax
0x1800c8ba3  lea     rax, [rsp+2F8h+var_248]
0x1800c8bab  mov     [rsp+2F8h+var_148], rax
0x1800c8bb3  lea     rax, [rsp+2F8h+var_1C8]
0x1800c8bbb  mov     [rsp+2F8h+var_140], rax
0x1800c8bc3  lea     rax, [rsp+2F8h+var_230]
0x1800c8bcb  mov     [rsp+2F8h+var_138], rax
0x1800c8bd3  mov     [rsp+2F8h+var_130], 1
0x1800c8bdb  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800c8be2  mov     rbx, [rax+38h]
0x1800c8be6  lea     rcx, [rsp+2F8h+var_220]
0x1800c8bee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8bf3  lea     rdx, [rsp+2F8h+var_220]
0x1800c8bfb  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800c8c02  mov     rax, rbx
0x1800c8c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8c0a  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800c8c11  mov     rbx, [rax+68h]
0x1800c8c15  lea     rcx, [rsp+2F8h+var_248]
0x1800c8c1d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8c22  lea     rdx, [rsp+2F8h+var_248]
0x1800c8c2a  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800c8c31  mov     rax, rbx
0x1800c8c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8c39  lea     rcx, [rsp+2F8h+var_1E0]
0x1800c8c41  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x1800c8c46  mov     rcx, [rsp+2F8h]; this
0x1800c8c4e  test    eax, eax
0x1800c8c50  js      loc_1800C960F
0x1800c8c56  lea     rcx, [rsp+2F8h+var_228]
0x1800c8c5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8c63  lea     rcx, [rdi+0E0h]
0x1800c8c6a  lea     r8, [rsp+2F8h+var_228]
0x1800c8c72  lea     rdx, _GUID_c39ab8a5_824f_4acf_92e0_bb53b8a90555
0x1800c8c79  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x1800c8c7e  mov     rcx, [rsp+2F8h]; this
0x1800c8c86  test    eax, eax
0x1800c8c88  js      loc_1800C9623
0x1800c8c8e  lea     rdx, [rsp+2F8h+var_1E8]
0x1800c8c96  lea     rcx, [rsp+2F8h+var_228]
0x1800c8c9e  call    ??$As@UICredentialSerializationProvider@@@?$ComPtr@UICredentialSerialization@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICredentialSerializationProvider@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::ICredentialSerialization>::As<ICredentialSerializationProvider>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ICredentialSerializationProvider>>)
0x1800c8ca3  mov     rcx, [rsp+2F8h]; this
0x1800c8cab  test    eax, eax
0x1800c8cad  js      loc_1800C9637
0x1800c8cb3  mov     rcx, [rsp+2F8h+var_1E8]
0x1800c8cbb  mov     rax, [rcx]
0x1800c8cbe  lea     rdx, [rsp+2F8h+var_230]
0x1800c8cc6  mov     rax, [rax+20h]
0x1800c8cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8ccf  mov     rcx, [rsp+2F8h]; this
0x1800c8cd7  test    eax, eax
0x1800c8cd9  js      loc_1800C964B
0x1800c8cdf  mov     rcx, [rsp+2F8h]; this
0x1800c8ce7  mov     rax, [rsp+2F8h+var_230]
0x1800c8cef  test    rax, rax
0x1800c8cf2  jz      loc_1800C965F
0x1800c8cf8  test    cs:byte_180147C81, 1
0x1800c8cff  jz      short loc_1800C8D16
0x1800c8d01  mov     r9d, [rax+8]
0x1800c8d05  mov     r8d, [rax+4]
0x1800c8d09  call    McTemplateU0qq_EventWriteTransfer
0x1800c8d0e  mov     rax, [rsp+2F8h+var_230]
0x1800c8d16  lea     r13, [rdi+0D0h]
0x1800c8d1d  cmp     [r13+0], rsi
0x1800c8d21  jz      loc_1800C8E61
0x1800c8d27  mov     rbx, [rax+10h]
0x1800c8d2b  mov     edi, [rax+8]
0x1800c8d2e  lea     rdx, [rsp+2F8h+var_218]
0x1800c8d36  mov     rcx, r13
0x1800c8d39  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x1800c8d3e  mov     rcx, [rsp+2F8h]; this
0x1800c8d46  test    eax, eax
0x1800c8d48  js      loc_1800C9676
0x1800c8d4e  mov     rcx, [rsp+2F8h+var_218]
0x1800c8d56  mov     rax, [rcx]
0x1800c8d59  lea     rdx, [rsp+2F8h+TokenHandle]
0x1800c8d61  mov     rax, [rax+50h]
0x1800c8d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8d6a  mov     rcx, [rsp+2F8h]; this
0x1800c8d72  test    eax, eax
0x1800c8d74  js      loc_1800C968A
0x1800c8d7a  lea     rax, [rsp+2F8h+var_1D8]
0x1800c8d82  mov     [rsp+2F8h+ReturnLength], rax; int
0x1800c8d87  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800c8d8d  lea     r8, [rsp+2F8h+TokenInformation]; TokenInformation
0x1800c8d95  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800c8d99  mov     rcx, [rsp+2F8h+TokenHandle]; TokenHandle
0x1800c8da1  call    cs:__imp_NtQueryInformationToken
0x1800c8da7  mov     rcx, [rsp+2F8h]; this
0x1800c8daf  test    eax, eax
0x1800c8db1  js      loc_1800C969E
0x1800c8db7  mov     eax, dword ptr [rsp+2F8h+var_114+8]
0x1800c8dbe  mov     dword ptr [rsp+2F8h+var_240+4], eax
0x1800c8dc5  mov     eax, dword ptr [rsp+2F8h+var_114+4]
0x1800c8dcc  mov     dword ptr [rsp+2F8h+var_240], eax
0x1800c8dd3  mov     rax, [rsp+2F8h+var_240]
0x1800c8ddb  mov     [rsp+2F8h+var_1A8], rax
0x1800c8de3  mov     edx, [rbx]
0x1800c8de5  sub     edx, 7
0x1800c8de8  jz      short loc_1800C8E3E
0x1800c8dea  sub     edx, 1
0x1800c8ded  jz      short loc_1800C8E27
0x1800c8def  sub     edx, 3
0x1800c8df2  jz      short loc_1800C8E10
0x1800c8df4  cmp     edx, 4
0x1800c8df7  jnz     short loc_1800C8E61
0x1800c8df9  mov     rcx, [rsp+2F8h]; this
0x1800c8e01  cmp     edi, 50h ; 'P'
0x1800c8e04  jb      loc_1800C96B2
0x1800c8e0a  mov     [rbx+48h], rax
0x1800c8e0e  jmp     short loc_1800C8E53
0x1800c8e10  mov     rcx, [rsp+2F8h]; this
0x1800c8e18  cmp     edi, 28h ; '('
0x1800c8e1b  jb      loc_1800C96C9
0x1800c8e21  mov     [rbx+20h], rax
0x1800c8e25  jmp     short loc_1800C8E53
0x1800c8e27  mov     rcx, [rsp+2F8h]; this
0x1800c8e2f  cmp     edi, 30h ; '0'
0x1800c8e32  jb      loc_1800C96E0
0x1800c8e38  mov     [rbx+28h], rax
0x1800c8e3c  jmp     short loc_1800C8E53
0x1800c8e3e  mov     rcx, [rsp+2F8h]; this
0x1800c8e46  cmp     edi, 40h ; '@'
0x1800c8e49  jb      loc_1800C96F7
0x1800c8e4f  mov     [rbx+38h], rax
0x1800c8e53  mov     r15d, 7
0x1800c8e59  mov     [rsp+2F8h+var_270], r15d
0x1800c8e61  lea     rdx, aUsermanager_2; "UserManager"
0x1800c8e68  lea     rcx, [rsp+2F8h+DestinationString]; DestinationString
0x1800c8e70  call    cs:__imp_RtlInitString
0x1800c8e76  lea     rdx, aValidatecreden; "ValidateCredentialsAsync"
0x1800c8e7d  lea     rcx, [rsp+2F8h+var_180]; DestinationString
0x1800c8e85  call    cs:__imp_RtlInitString
0x1800c8e8b  mov     rax, 72674D72657355h
0x1800c8e95  mov     qword ptr [rsp+2F8h+LocallyUniqueId.LowPart], rax
0x1800c8e9d  lea     rcx, [rsp+2F8h+LocallyUniqueId.LowPart+8]; LocallyUniqueId
0x1800c8ea5  call    cs:__imp_NtAllocateLocallyUniqueId
0x1800c8eab  mov     rcx, [rsp+2F8h]; this
0x1800c8eb3  test    eax, eax
0x1800c8eb5  js      loc_1800C970E
0x1800c8ebb  mov     rcx, [rsp+2F8h+var_248]
0x1800c8ec3  mov     rax, [rcx]
0x1800c8ec6  lea     r9, [rsp+2F8h+var_1D4]
0x1800c8ece  lea     r8, [rsp+2F8h+var_1C0]
0x1800c8ed6  lea     rdx, [rsp+2F8h+DestinationString]
0x1800c8ede  mov     rax, [rax+18h]
0x1800c8ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8ee7  mov     rcx, [rsp+2F8h]; this
0x1800c8eef  test    eax, eax
0x1800c8ef1  js      loc_1800C9722
0x1800c8ef7  lea     rdx, [rsp+2F8h+var_238]
0x1800c8eff  mov     ecx, 80h
0x1800c8f04  call    cs:__imp_SeciAllocateAndSetCallFlags
0x1800c8f0a  mov     edx, 1; unsigned int
0x1800c8f0f  xor     ecx, ecx; int
0x1800c8f11  call    ?SetNtlmThreadOptions@@YAJHK@Z; SetNtlmThreadOptions(int,ulong)
0x1800c8f16  mov     rcx, [rsp+2F8h]; this
0x1800c8f1e  test    eax, eax
0x1800c8f20  js      loc_1800C9736
0x1800c8f26  mov     rcx, [rsp+2F8h+var_248]
0x1800c8f2e  mov     rax, [rcx]
0x1800c8f31  lea     rdx, [rsp+2F8h+var_274]
0x1800c8f39  mov     [rsp+2F8h+var_288], rdx
0x1800c8f3e  lea     rdx, [rsp+2F8h+var_E0]
0x1800c8f46  mov     [rsp+2F8h+var_290], rdx
0x1800c8f4b  lea     rdx, [rsp+2F8h+var_1F0]
0x1800c8f53  mov     [rsp+2F8h+var_298], rdx
0x1800c8f58  lea     rdx, [rsp+2F8h+var_1A8]
0x1800c8f60  mov     [rsp+2F8h+var_2A0], rdx
0x1800c8f65  lea     rdx, [rsp+2F8h+var_1D0]
0x1800c8f6d  mov     [rsp+2F8h+var_2A8], rdx
0x1800c8f72  lea     rdx, [rsp+2F8h+var_1C8]
0x1800c8f7a  mov     [rsp+2F8h+var_2B0], rdx
0x1800c8f7f  lea     rdx, [rsp+2F8h+LocallyUniqueId]
0x1800c8f87  mov     [rsp+2F8h+var_2B8], rdx
0x1800c8f8c  mov     [rsp+2F8h+var_2C0], rsi
0x1800c8f91  mov     r9, [rsp+2F8h+var_230]
0x1800c8f99  mov     r8d, [r9+8]
0x1800c8f9d  mov     dword ptr [rsp+2F8h+var_2C8], r8d
0x1800c8fa2  mov     r8, [r9+10h]
0x1800c8fa6  mov     [rsp+2F8h+var_2D0], r8
0x1800c8fab  mov     r8d, [r9+4]
0x1800c8faf  mov     dword ptr [rsp+2F8h+ReturnLength], r8d; int
0x1800c8fb4  mov     r9d, 7
0x1800c8fba  lea     r8, [rsp+2F8h+var_180]
0x1800c8fc2  mov     rdx, [rsp+2F8h+var_1C0]
0x1800c8fca  mov     rax, [rax+20h]
0x1800c8fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8fd3  mov     r14d, eax
0x1800c8fd6  mov     [rsp+2F8h+var_278], eax
0x1800c8fdd  mov     edi, 1
0x1800c8fe2  mov     edx, edi; unsigned int
0x1800c8fe4  mov     ecx, edi; int
0x1800c8fe6  call    ?SetNtlmThreadOptions@@YAJHK@Z; SetNtlmThreadOptions(int,ulong)
0x1800c8feb  mov     rcx, [rsp+2F8h]; this
0x1800c8ff3  test    eax, eax
0x1800c8ff5  js      loc_1800C974A
0x1800c8ffb  test    r14d, r14d
0x1800c8ffe  js      loc_1800C91DA
0x1800c9004  cmp     [r13+0], rsi
0x1800c9008  jz      loc_1800C91D7
0x1800c900e  mov     [rsp+2F8h+var_26C], esi
0x1800c9015  mov     [rsp+2F8h+String2], rsi
0x1800c901d  mov     [rsp+2F8h+var_240], rsi
0x1800c9025  mov     [rsp+2F8h+string], rsi
0x1800c902d  mov     [rsp+2F8h+var_200], rsi
0x1800c9035  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800c903c  mov     rbx, [rax+58h]
0x1800c9040  lea     rcx, [rsp+2F8h+var_200]
0x1800c9048  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c904d  lea     rdx, [rsp+2F8h+var_200]
0x1800c9055  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x1800c905c  mov     rax, rbx
0x1800c905f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9064  mov     rcx, [rsp+2F8h+var_200]
0x1800c906c  mov     rax, [rcx]
0x1800c906f  lea     rdx, [rsp+2F8h+var_26C]
0x1800c9077  mov     [rsp+2F8h+var_2D0], rdx
0x1800c907c  mov     dword ptr [rsp+2F8h+ReturnLength], 54h ; 'T'; int
0x1800c9084  lea     r9, [rsp+2F8h+var_A8]
0x1800c908c  mov     r8d, edi
0x1800c908f  mov     rdx, [rsp+2F8h+var_1F0]
0x1800c9097  mov     rax, [rax+18h]
0x1800c909b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c90a0  mov     rcx, [rsp+2F8h]; this
0x1800c90a8  test    eax, eax
0x1800c90aa  js      loc_1800C975F
0x1800c90b0  mov     rdi, [rsp+2F8h+var_220]
0x1800c90b8  mov     rax, [rdi]
0x1800c90bb  mov     rbx, [rax+20h]
0x1800c90bf  xor     edx, edx
0x1800c90c1  lea     rcx, [rsp+2F8h+String2]
0x1800c90c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800c90ce  lea     r8, [rsp+2F8h+String2]
0x1800c90d6  mov     rdx, [rsp+2F8h+var_A8]
  ... truncated ...
```
