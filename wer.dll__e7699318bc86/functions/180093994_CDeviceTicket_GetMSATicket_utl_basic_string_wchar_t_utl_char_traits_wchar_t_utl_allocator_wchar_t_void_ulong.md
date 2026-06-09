# CDeviceTicket::GetMSATicket(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *,ulong)

- ea: `0x180093994`
- end: `0x180094510`
- name: `?GetMSATicket@CDeviceTicket@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAXK@Z`
- size: `2940`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18008f14c`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000c390`
- `0x180019b50`
- `0x18001fe24`
- `0x1800269c4`
- `0x18002e390`
- `0x18002f570`
- `0x1800303dc`
- `0x180043fac`
- `0x180049530`
- `0x18004a8e0`
- `0x18004c824`
- `0x180050db0`
- `0x180093994`
- `0x180094518`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093a14`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093e73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093f75`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180094336`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093a14`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093e73`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180093f75`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180094336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c9f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180093c91`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180093c91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093ef5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093ef5`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180093f52`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180093f52`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800944de`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800944de`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180093a22`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180093a22`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093b1e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093b1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800942ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800942ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093b6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093bbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093b6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180093bbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009448e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800944a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800944b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ba1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094275`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009448e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800944a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800944b6`

## string_xrefs

- `0x180093b68`: `https://watson.telemetry.microsoft.com`
- `0x180093a59`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x180093a78`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CDeviceTicket::GetMSATicket(__int64 a1, void *a2)
{
  DWORD v4; // ebx
  HRESULT v5; // esi
  __int64 v6; // rdi
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int ActivationFactory; // eax
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  HANDLE Event; // rbx
  DWORD LastError; // eax
  HANDLE v15; // rax
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r14
  __int64 (__fastcall *v19)(__int64, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64 *); // r14
  int v22; // r14d
  char v23; // bl
  ULONGLONG v24; // rax
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  const char *v28; // rax
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // r14
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, __int64 *); // r14
  __int64 v33; // r14
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64 *); // rbx
  __int64 v35; // r14
  __int64 (__fastcall *v36)(__int64, HSTRING *); // rbx
  ULONGLONG v37; // r14
  __int64 v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+48h] [rbp-B8h] BYREF
  int v41; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD dwindex[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v44; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v45; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v47; // [rsp+78h] [rbp-88h] BYREF
  __int64 v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  ULONGLONG TickCount64; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h] BYREF
  void **v55; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE pHandles; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h] BYREF
  HRESULT v58; // [rsp+D0h] [rbp-30h]
  __int128 v59; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER v60; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v61; // [rsp+108h] [rbp+8h]
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  __int64 v63; // [rsp+128h] [rbp+28h]
  char v64[32]; // [rsp+130h] [rbp+30h] BYREF
  __int128 *v65; // [rsp+150h] [rbp+50h]
  __int64 v66; // [rsp+158h] [rbp+58h]
  ULONGLONG *p_TickCount64; // [rsp+160h] [rbp+60h]
  __int64 v68; // [rsp+168h] [rbp+68h]
  DWORD *v69; // [rsp+170h] [rbp+70h]
  __int64 v70; // [rsp+178h] [rbp+78h]

  if ( !a1 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, 2147942487LL);
    return v4;
  }
  TickCount64 = GetTickCount64();
  v5 = CoInitializeEx(0, 0);
  v58 = v5;
  pHandles = 0;
  v55 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  string = 0;
  v45 = 0;
  v44 = 0;
  v63 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
    0x42u,
    0x41u);
  v61 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v60,
    L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
    0x46u,
    0x45u);
  v54 = 0;
  v53 = 0;
  v49 = 0;
  v6 = 0;
  v57 = 0;
  v43 = 0;
  v39 = 0;
  v52 = 0;
  v51 = 0;
  v48 = 0;
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147417850 )
  {
    v4 = v5;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 11;
    v9 = (unsigned int)v5;
    goto LABEL_10;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v54);
  ActivationFactory = RoGetActivationFactory(v61, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v54);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 12;
    goto LABEL_15;
  }
  WindowsDeleteString(string);
  string = 0;
  ActivationFactory = WindowsCreateString(L"https://watson.telemetry.microsoft.com", 0x26u, &string);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 13;
    goto LABEL_15;
  }
  WindowsDeleteString(v45);
  v45 = 0;
  ActivationFactory = WindowsCreateString(L"MBI_SSL", 7u, &v45);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 14;
    goto LABEL_15;
  }
  v11 = v54;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v54 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v53);
  ActivationFactory = v12(v11, string, v45, &v53);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 15;
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v49);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>(
                        v63,
                        &v49);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 16;
    goto LABEL_15;
  }
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
  {
    LastError = GetLastError();
    v4 = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_132;
  }
  v15 = pHandles;
  if ( Event != pHandles )
  {
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v55);
    v15 = Event;
    pHandles = Event;
  }
  v57 = (__int64)v15;
  v16 = Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(
          (__int64 *)dwindex,
          &v57);
  v6 = *v16;
  *v16 = 0;
  v57 = v6;
  v17 = *(_QWORD *)dwindex;
  if ( *(_QWORD *)dwindex )
  {
    *(_QWORD *)dwindex = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  if ( !v6 )
  {
    v4 = -2147024882;
    goto LABEL_132;
  }
  v59 = xmmword_1800C2C70;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v49 + 72LL))(v49, &v59);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 17;
    goto LABEL_15;
  }
  v18 = v49;
  v19 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v43);
  ActivationFactory = v19(v18, v53, &v43);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 18;
    goto LABEL_15;
  }
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v43)[6])(
                        v43,
                        v6);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 19;
    goto LABEL_15;
  }
  v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
  v21 = **v43;
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v39);
  ActivationFactory = v21(v20, &GUID_00000036_0000_0000_c000_000000000046, &v39);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 20;
    goto LABEL_15;
  }
  dwindex[0] = 0;
  v22 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v24 = GetTickCount64();
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
      v24 - TickCount64);
  }
  while ( CoWaitForMultipleHandles(0x18u, 0x64u, 1u, &pHandles, dwindex) == -2147417835 )
  {
    if ( !v23 )
    {
      if ( (unsigned int)++v22 > 0x1E )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 72LL))(v39);
        v23 = 1;
      }
      if ( a2 && !WaitForSingleObject(a2, 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 72LL))(v39);
        v23 = 1;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v27 = GetTickCount64() - TickCount64;
    v28 = "true";
    if ( !v23 )
      v28 = "false";
    WPP_SF_is(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v26, v27, (__int64)v28);
  }
  v40 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 64LL))(v39, &v40);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 25;
    goto LABEL_15;
  }
  v4 = v40;
  if ( v40 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)v40);
      v4 = v40;
    }
    goto LABEL_132;
  }
  v47 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 56LL))(v39, &v47);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 27;
    goto LABEL_15;
  }
  if ( v47 != 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, v47);
    v4 = -2147467260;
    goto LABEL_132;
  }
  v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
  v30 = (*v43)[8];
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v52);
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v30)(
                        v29,
                        &v52);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 29;
    goto LABEL_15;
  }
  v31 = v52;
  if ( !v52 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(v52 + 30),
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
LABEL_131:
    v4 = -2147467261;
    goto LABEL_132;
  }
  v41 = 0;
  v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v51);
  ActivationFactory = v32(v31, &v51);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 31;
    goto LABEL_15;
  }
  v33 = v51;
  v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v48);
  ActivationFactory = v34(v33, 0, &v48);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 32;
    goto LABEL_15;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 64LL))(v48, &v41);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 33;
    goto LABEL_15;
  }
  v4 = v41;
  if ( v41 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)v41);
      v4 = v41;
    }
    goto LABEL_132;
  }
  v35 = v48;
  v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v48 + 48LL);
  WindowsDeleteString(v44);
  v44 = 0;
  ActivationFactory = v36(v35, &v44);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 35;
LABEL_15:
    v9 = (unsigned int)ActivationFactory;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, v9);
    goto LABEL_132;
  }
  if ( !v44 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)ActivationFactory);
    goto LABEL_131;
  }
  WindowsGetStringRawBuffer(v44, 0);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1) )
  {
    v4 = -2147024882;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 36;
    v9 = 2147942414LL;
    goto LABEL_10;
  }
  v4 = 0;
LABEL_132:
  v37 = GetTickCount64() - TickCount64;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_SSdi(*((_QWORD *)WPP_GLOBAL_Control + 2));
  if ( (unsigned int)dword_1800D9000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 0x400000000000LL) )
  {
    dwindex[0] = v4;
    TickCount64 = v37;
    *(_QWORD *)&v59 = 0x1000000;
    v69 = dwindex;
    v70 = 4;
    p_TickCount64 = &TickCount64;
    v68 = 8;
    v65 = &v59;
    v66 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800D9000, byte_1800C96CD, 0, 0, 5, v64);
  }
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 80LL))(v39);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v48);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v51);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v43);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v54);
  v61 = 0;
  v63 = 0;
  WindowsDeleteString(v44);
  v44 = 0;
  WindowsDeleteString(v45);
  v45 = 0;
  WindowsDeleteString(string);
  string = 0;
  v55 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v55);
  if ( v5 >= 0 )
    CoUninitialize();
  return v4;
}

```

## disassembly

```asm
0x180093994  mov     [rsp-8+arg_10], rbx
0x180093999  push    rbp
0x18009399a  push    rsi
0x18009399b  push    rdi
0x18009399c  push    r12
0x18009399e  push    r13
0x1800939a0  push    r14
0x1800939a2  push    r15
0x1800939a4  lea     rbp, [rsp-90h]
0x1800939ac  sub     rsp, 190h
0x1800939b3  mov     rax, cs:__security_cookie
0x1800939ba  xor     rax, rsp
0x1800939bd  mov     [rbp+0C0h+var_40], rax
0x1800939c4  mov     r12, rdx
0x1800939c7  mov     r13, rcx
0x1800939ca  xor     r14d, r14d
0x1800939cd  test    rcx, rcx
0x1800939d0  jnz     short loc_180093A14
0x1800939d2  lea     r15, WPP_GLOBAL_Control
0x1800939d9  mov     ebx, 80070057h
0x1800939de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800939e5  cmp     rcx, r15
0x1800939e8  jz      loc_1800944E4
0x1800939ee  test    byte ptr [rcx+1Ch], 1
0x1800939f2  jz      loc_1800944E4
0x1800939f8  lea     edx, [r13+0Ah]
0x1800939fc  mov     r9d, ebx
0x1800939ff  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x180093a06  mov     rcx, [rcx+10h]
0x180093a0a  call    WPP_SF_d
0x180093a0f  jmp     loc_1800944E4
0x180093a14  call    cs:__imp_GetTickCount64
0x180093a1a  mov     [rbp+0C0h+var_130], rax
0x180093a1e  xor     edx, edx; dwCoInit
0x180093a20  xor     ecx, ecx; pvReserved
0x180093a22  call    cs:__imp_CoInitializeEx
0x180093a28  mov     esi, eax
0x180093a2a  mov     [rbp+0C0h+var_F0], eax
0x180093a2d  mov     [rbp+0C0h+pHandles], r14
0x180093a31  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180093a38  mov     [rbp+0C0h+var_108], rax
0x180093a3c  mov     [rsp+1C0h+string], r14
0x180093a41  mov     [rsp+1C0h+var_158], r14
0x180093a46  mov     [rsp+1C0h+var_160], r14
0x180093a4b  mov     [rbp+0C0h+var_98], r14
0x180093a4f  mov     r9d, 41h ; 'A'; unsigned int
0x180093a55  lea     r8d, [r9+1]; unsigned int
0x180093a59  lea     rdx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QB_WB; "Windows.Internal.Security.WebAuthentica"...
0x180093a60  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x180093a64  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180093a69  nop
0x180093a6a  mov     [rbp+0C0h+var_B8], r14
0x180093a6e  mov     r9d, 45h ; 'E'; unsigned int
0x180093a74  lea     r8d, [r9+1]; unsigned int
0x180093a78  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QB_WB; "Windows.Security.Authentication.OnlineI"...
0x180093a7f  lea     rcx, [rbp+0C0h+var_D0]; hstringHeader
0x180093a83  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180093a88  nop
0x180093a89  mov     [rbp+0C0h+var_110], r14
0x180093a8d  mov     [rbp+0C0h+var_118], r14
0x180093a91  mov     [rbp+0C0h+var_138], r14
0x180093a95  mov     rdi, r14
0x180093a98  mov     [rbp+0C0h+var_F8], r14
0x180093a9c  mov     [rsp+1C0h+var_168], r14
0x180093aa1  mov     [rsp+1C0h+var_180], r14
0x180093aa6  mov     [rbp+0C0h+var_120], r14
0x180093aaa  mov     [rbp+0C0h+var_128], r14
0x180093aae  mov     [rbp+0C0h+var_140], r14
0x180093ab2  mov     ecx, 80000000h
0x180093ab7  lea     eax, [rsi+rcx]
0x180093aba  lea     r15, WPP_GLOBAL_Control
0x180093ac1  test    ecx, eax
0x180093ac3  jnz     short loc_180093B06
0x180093ac5  cmp     esi, 80010106h
0x180093acb  jz      short loc_180093B06
0x180093acd  mov     ebx, esi
0x180093acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180093ad6  cmp     rcx, r15
0x180093ad9  jz      loc_180094336
0x180093adf  test    byte ptr [rcx+1Ch], 1
0x180093ae3  jz      loc_180094336
0x180093ae9  mov     edx, 0Bh
0x180093aee  mov     r9d, esi
0x180093af1  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x180093af8  mov     rcx, [rcx+10h]
0x180093afc  call    WPP_SF_d
0x180093b01  jmp     loc_180094336
0x180093b06  lea     rcx, [rbp+0C0h+var_110]
0x180093b0a  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093b0f  lea     r8, [rbp+0C0h+var_110]
0x180093b13  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180093b1a  mov     rcx, [rbp+0C0h+var_B8]
0x180093b1e  call    cs:__imp_RoGetActivationFactory
0x180093b24  mov     ebx, eax
0x180093b26  test    eax, eax
0x180093b28  jns     short loc_180093B4E
0x180093b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180093b31  cmp     rcx, r15
0x180093b34  jz      loc_180094336
0x180093b3a  test    byte ptr [rcx+1Ch], 1
0x180093b3e  jz      loc_180094336
0x180093b44  mov     edx, 0Ch
0x180093b49  mov     r9d, eax
0x180093b4c  jmp     short loc_180093AF1
0x180093b4e  mov     rcx, [rsp+1C0h+string]; string
0x180093b53  call    cs:__imp_WindowsDeleteString
0x180093b59  mov     [rsp+1C0h+string], r14
0x180093b5e  lea     r8, [rsp+1C0h+string]; string
0x180093b63  mov     edx, 26h ; '&'; length
0x180093b68  lea     rcx, sourceString; "https://watson.telemetry.microsoft.com"
0x180093b6f  call    cs:__imp_WindowsCreateString
0x180093b75  mov     ebx, eax
0x180093b77  test    eax, eax
0x180093b79  jns     short loc_180093B9C
0x180093b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180093b82  cmp     rcx, r15
0x180093b85  jz      loc_180094336
0x180093b8b  test    byte ptr [rcx+1Ch], 1
0x180093b8f  jz      loc_180094336
0x180093b95  mov     edx, 0Dh
0x180093b9a  jmp     short loc_180093B49
0x180093b9c  mov     rcx, [rsp+1C0h+var_158]; string
0x180093ba1  call    cs:__imp_WindowsDeleteString
0x180093ba7  mov     [rsp+1C0h+var_158], r14
0x180093bac  lea     r8, [rsp+1C0h+var_158]; string
0x180093bb1  mov     edx, 7; length
0x180093bb6  lea     rcx, aMbiSsl; "MBI_SSL"
0x180093bbd  call    cs:__imp_WindowsCreateString
0x180093bc3  mov     ebx, eax
0x180093bc5  test    eax, eax
0x180093bc7  jns     short loc_180093BED
0x180093bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180093bd0  cmp     rcx, r15
0x180093bd3  jz      loc_180094336
0x180093bd9  test    byte ptr [rcx+1Ch], 1
0x180093bdd  jz      loc_180094336
0x180093be3  mov     edx, 0Eh
0x180093be8  jmp     loc_180093B49
0x180093bed  mov     r14, [rbp+0C0h+var_110]
0x180093bf1  mov     rax, [r14]
0x180093bf4  mov     rbx, [rax+30h]
0x180093bf8  lea     rcx, [rbp+0C0h+var_118]
0x180093bfc  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093c01  lea     r9, [rbp+0C0h+var_118]
0x180093c05  mov     r8, [rsp+1C0h+var_158]
0x180093c0a  mov     rdx, [rsp+1C0h+string]
0x180093c0f  mov     rcx, r14
0x180093c12  mov     rax, rbx
0x180093c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c1a  mov     ebx, eax
0x180093c1c  test    eax, eax
0x180093c1e  jns     short loc_180093C44
0x180093c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180093c27  cmp     rcx, r15
0x180093c2a  jz      loc_180094336
0x180093c30  test    byte ptr [rcx+1Ch], 1
0x180093c34  jz      loc_180094336
0x180093c3a  mov     edx, 0Fh
0x180093c3f  jmp     loc_180093B49
0x180093c44  lea     rcx, [rbp+0C0h+var_138]
0x180093c48  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093c4d  lea     rdx, [rbp+0C0h+var_138]
0x180093c51  mov     rcx, [rbp+0C0h+var_98]
0x180093c55  call    ??$ActivateInstance@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAuthenticationManager@WebAuthentication@Security@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>(HSTRING__ *,Windows::Internal::Security::WebAuthentication::IAuthenticationManager * *)
0x180093c5a  mov     ebx, eax
0x180093c5c  test    eax, eax
0x180093c5e  jns     short loc_180093C84
0x180093c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180093c67  cmp     rcx, r15
0x180093c6a  jz      loc_180094336
0x180093c70  test    byte ptr [rcx+1Ch], 1
0x180093c74  jz      loc_180094336
0x180093c7a  mov     edx, 10h
0x180093c7f  jmp     loc_180093B49
0x180093c84  mov     r9d, 1F0003h; dwDesiredAccess
0x180093c8a  xor     r8d, r8d; dwFlags
0x180093c8d  xor     edx, edx; lpName
0x180093c8f  xor     ecx, ecx; lpEventAttributes
0x180093c91  call    cs:__imp_CreateEventExW
0x180093c97  mov     rbx, rax
0x180093c9a  test    rax, rax
0x180093c9d  jnz     short loc_180093CB3
0x180093c9f  call    cs:__imp_GetLastError
0x180093ca5  mov     ecx, eax; unsigned int
0x180093ca7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180093cac  mov     ebx, eax
0x180093cae  jmp     loc_180094336
0x180093cb3  mov     rax, [rbp+0C0h+pHandles]
0x180093cb7  cmp     rbx, rax
0x180093cba  jz      short loc_180093CCC
0x180093cbc  lea     rcx, [rbp+0C0h+var_108]
0x180093cc0  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180093cc5  mov     rax, rbx
0x180093cc8  mov     [rbp+0C0h+pHandles], rbx
0x180093ccc  mov     [rbp+0C0h+var_F8], rax
0x180093cd0  lea     rdx, [rbp+0C0h+var_F8]
0x180093cd4  lea     rcx, [rsp+1C0h+dwindex]
0x180093cd9  call    ??$Make@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@PEAX@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@@12@$$QEAPEAX@Z; Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(void * &&)
0x180093cde  mov     rdi, [rax]
0x180093ce1  mov     qword ptr [rax], 0
0x180093ce8  mov     [rbp+0C0h+var_F8], rdi
0x180093cec  mov     rcx, qword ptr [rsp+1C0h+dwindex]
0x180093cf1  test    rcx, rcx
0x180093cf4  jz      short loc_180093D0C
0x180093cf6  mov     qword ptr [rsp+1C0h+dwindex], 0
0x180093cff  mov     rax, [rcx]
0x180093d02  mov     rax, [rax+10h]
0x180093d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d0b  nop
0x180093d0c  test    rdi, rdi
0x180093d0f  jnz     short loc_180093D1B
0x180093d11  mov     ebx, 8007000Eh
0x180093d16  jmp     loc_180094336
0x180093d1b  mov     rcx, [rbp+0C0h+var_138]
0x180093d1f  movups  xmm0, cs:xmmword_1800C2C70
0x180093d26  movdqu  [rbp+0C0h+var_E0], xmm0
0x180093d2b  mov     rax, [rcx]
0x180093d2e  lea     rdx, [rbp+0C0h+var_E0]
0x180093d32  mov     rax, [rax+48h]
0x180093d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d3b  mov     ebx, eax
0x180093d3d  test    eax, eax
0x180093d3f  jns     short loc_180093D65
0x180093d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180093d48  cmp     rcx, r15
0x180093d4b  jz      loc_180094336
0x180093d51  test    byte ptr [rcx+1Ch], 1
0x180093d55  jz      loc_180094336
0x180093d5b  mov     edx, 11h
0x180093d60  jmp     loc_180093B49
0x180093d65  mov     r14, [rbp+0C0h+var_138]
0x180093d69  mov     rax, [r14]
0x180093d6c  mov     rbx, [rax+38h]
0x180093d70  lea     rcx, [rsp+1C0h+var_168]
0x180093d75  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093d7a  lea     r8, [rsp+1C0h+var_168]
0x180093d7f  mov     rdx, [rbp+0C0h+var_118]
0x180093d83  mov     rcx, r14
0x180093d86  mov     rax, rbx
0x180093d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d8e  mov     ebx, eax
0x180093d90  test    eax, eax
0x180093d92  jns     short loc_180093DB8
0x180093d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180093d9b  cmp     rcx, r15
0x180093d9e  jz      loc_180094336
0x180093da4  test    byte ptr [rcx+1Ch], 1
0x180093da8  jz      loc_180094336
0x180093dae  mov     edx, 12h
0x180093db3  jmp     loc_180093B49
0x180093db8  mov     rcx, [rsp+1C0h+var_168]
0x180093dbd  mov     rax, [rcx]
0x180093dc0  mov     rdx, rdi
0x180093dc3  mov     rax, [rax+30h]
0x180093dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093dcc  mov     ebx, eax
0x180093dce  test    eax, eax
0x180093dd0  jns     short loc_180093DF6
0x180093dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180093dd9  cmp     rcx, r15
0x180093ddc  jz      loc_180094336
0x180093de2  test    byte ptr [rcx+1Ch], 1
0x180093de6  jz      loc_180094336
0x180093dec  mov     edx, 13h
0x180093df1  jmp     loc_180093B49
0x180093df6  mov     rbx, [rsp+1C0h+var_168]
0x180093dfb  mov     rax, [rbx]
0x180093dfe  mov     r14, [rax]
0x180093e01  lea     rcx, [rsp+1C0h+var_180]
0x180093e06  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180093e0b  lea     r8, [rsp+1C0h+var_180]
0x180093e10  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180093e17  mov     rcx, rbx
0x180093e1a  mov     rax, r14
0x180093e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e22  mov     ebx, eax
0x180093e24  test    eax, eax
0x180093e26  jns     short loc_180093E4C
0x180093e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e2f  cmp     rcx, r15
0x180093e32  jz      loc_180094336
0x180093e38  test    byte ptr [rcx+1Ch], 1
0x180093e3c  jz      loc_180094336
0x180093e42  mov     edx, 14h
0x180093e47  jmp     loc_180093B49
0x180093e4c  mov     [rsp+1C0h+dwindex], 0
0x180093e54  xor     r14d, r14d
0x180093e57  xor     bl, bl
0x180093e59  mov     rax, cs:WPP_GLOBAL_Control
0x180093e60  cmp     rax, r15
0x180093e63  jz      loc_180093F37
0x180093e69  test    byte ptr [rax+1Ch], 4
0x180093e6d  jz      loc_180093F37
0x180093e73  call    cs:__imp_GetTickCount64
0x180093e79  sub     rax, [rbp+0C0h+var_130]
0x180093e7d  lea     edx, [r14+15h]
0x180093e81  mov     r9, rax
0x180093e84  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x180093e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e92  mov     rcx, [rcx+10h]
  ... truncated ...
```
