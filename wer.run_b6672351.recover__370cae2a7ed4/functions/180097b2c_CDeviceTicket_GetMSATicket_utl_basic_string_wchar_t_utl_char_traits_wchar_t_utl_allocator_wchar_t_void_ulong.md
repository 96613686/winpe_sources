# CDeviceTicket::GetMSATicket(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *,ulong)

- ea: `0x180097b2c`
- end: `0x180098721`
- name: `?GetMSATicket@CDeviceTicket@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAXK@Z`
- size: `3061`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800931fc`

## callees

- `0x180004c64`
- `0x18000da00`
- `0x18001b39c`
- `0x18001c368`
- `0x180020680`
- `0x18002687c`
- `0x18002f8bc`
- `0x180030f50`
- `0x180031cd0`
- `0x180045c84`
- `0x18004b648`
- `0x18004caf0`
- `0x18004ebdc`
- `0x180053300`
- `0x180097b2c`
- `0x180098728`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180097bac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098041`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098155`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098528`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180097bac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098041`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098155`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180098528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e67`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180097e53`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180097e53`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800980c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800980c9`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18009812c`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18009812c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800986e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800986e8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180097bc0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180097bc0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180097cc2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180097cc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800984b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800984b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180097d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180097d79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180097d1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180097d79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009845b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800986a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800986ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097cfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009845b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180098686`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800986a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800986ba`

## string_xrefs

- `0x180097d18`: `https://watson.telemetry.microsoft.com`
- `0x180097bfd`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x180097c1c`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CDeviceTicket::GetMSATicket(void *a1, void *a2)
{
  DWORD v4; // ebx
  HRESULT v5; // esi
  void *v6; // rdi
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  HRESULT ActivationFactory; // eax
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, HSTRING, HSTRING, __int64 *); // rbx
  HANDLE Event; // rbx
  DWORD LastError; // eax
  HANDLE v15; // rax
  void **v16; // rax
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
  WCHAR *StringRawBuffer; // rax
  ULONGLONG v38; // r14
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+48h] [rbp-B8h] BYREF
  int v42; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD dwindex[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v45; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v48; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  ULONGLONG TickCount64; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+98h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-50h] BYREF
  void **v56; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE pHandles; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE v58; // [rsp+C8h] [rbp-38h] BYREF
  HRESULT v59; // [rsp+D0h] [rbp-30h]
  __int128 v60; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER v61; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v62; // [rsp+108h] [rbp+8h]
  HSTRING_HEADER hstringHeader; // [rsp+110h] [rbp+10h] BYREF
  __int64 v64; // [rsp+128h] [rbp+28h]
  char v65[32]; // [rsp+130h] [rbp+30h] BYREF
  __int128 *v66; // [rsp+150h] [rbp+50h]
  __int64 v67; // [rsp+158h] [rbp+58h]
  ULONGLONG *p_TickCount64; // [rsp+160h] [rbp+60h]
  __int64 v69; // [rsp+168h] [rbp+68h]
  DWORD *v70; // [rsp+170h] [rbp+70h]
  __int64 v71; // [rsp+178h] [rbp+78h]

  if ( !a1 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, 2147942487LL);
    return v4;
  }
  TickCount64 = GetTickCount64();
  v5 = CoInitializeEx(0, 0);
  v59 = v5;
  pHandles = 0;
  v56 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  string = 0;
  v46 = 0;
  v45 = 0;
  v64 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
    0x42u,
    0x41u);
  v62 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v61,
    L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
    0x46u,
    0x45u);
  v55 = 0;
  v54 = 0;
  v50 = 0;
  v6 = 0;
  v58 = 0;
  v44 = 0;
  v40 = 0;
  v53 = 0;
  v52 = 0;
  v49 = 0;
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
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v55);
  ActivationFactory = RoGetActivationFactory(v62, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v55);
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
  WindowsDeleteString(v46);
  v46 = 0;
  ActivationFactory = WindowsCreateString(L"MBI_SSL", 7u, &v46);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 14;
    goto LABEL_15;
  }
  v11 = v55;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 *))(*(_QWORD *)v55 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v54);
  ActivationFactory = v12(v11, string, v46, &v54);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 15;
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v50);
  ActivationFactory = Windows::Foundation::ActivateInstance<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>(
                        v64,
                        &v50);
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
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v56);
    v15 = Event;
    pHandles = Event;
  }
  v58 = v15;
  v16 = (void **)Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(
                   dwindex,
                   &v58);
  v6 = *v16;
  *v16 = 0;
  v58 = v6;
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
  v60 = xmmword_1800C7C40;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v50 + 72LL))(v50, &v60);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 17;
    goto LABEL_15;
  }
  v18 = v50;
  v19 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v50 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v44);
  ActivationFactory = v19(v18, v54, &v44);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 18;
    goto LABEL_15;
  }
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), void *))(*v44)[6])(
                        v44,
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
  v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
  v21 = **v44;
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v40);
  ActivationFactory = v21(v20, &GUID_00000036_0000_0000_c000_000000000046, &v40);
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
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 72LL))(v40);
        v23 = 1;
      }
      if ( a2 && !WaitForSingleObject(a2, 0) )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 72LL))(v40);
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
  v41 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 64LL))(v40, &v41);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 25;
    goto LABEL_15;
  }
  v4 = v41;
  if ( v41 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)v41);
      v4 = v41;
    }
    goto LABEL_132;
  }
  v48 = 0;
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 56LL))(v40, &v48);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 27;
    goto LABEL_15;
  }
  if ( v48 != 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids, v48);
    v4 = -2147467260;
    goto LABEL_132;
  }
  v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
  v30 = (*v44)[8];
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v53);
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v30)(
                        v29,
                        &v53);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 29;
    goto LABEL_15;
  }
  v31 = v53;
  if ( !v53 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(v53 + 30),
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids);
LABEL_131:
    v4 = -2147467261;
    goto LABEL_132;
  }
  v42 = 0;
  v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v52);
  ActivationFactory = v32(v31, &v52);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 31;
    goto LABEL_15;
  }
  v33 = v52;
  v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v49);
  ActivationFactory = v34(v33, 0, &v49);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 32;
    goto LABEL_15;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 64LL))(v49, &v42);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_132;
    v8 = 33;
    goto LABEL_15;
  }
  v4 = v42;
  if ( v42 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)v42);
      v4 = v42;
    }
    goto LABEL_132;
  }
  v35 = v49;
  v36 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v49 + 48LL);
  WindowsDeleteString(v45);
  v45 = 0;
  ActivationFactory = v36(v35, &v45);
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
  if ( !v45 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids,
        (unsigned int)ActivationFactory);
    goto LABEL_131;
  }
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(v45, 0);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           a1,
                           StringRawBuffer) )
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
  v38 = GetTickCount64() - TickCount64;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_SSdi(*((_QWORD *)WPP_GLOBAL_Control + 2));
  if ( (unsigned int)dword_1800DE000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 0x400000000000LL) )
  {
    dwindex[0] = v4;
    TickCount64 = v38;
    *(_QWORD *)&v60 = 0x1000000;
    v70 = dwindex;
    v71 = 4;
    p_TickCount64 = &TickCount64;
    v69 = 8;
    v66 = &v60;
    v67 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800DE000, byte_1800CE77D, 0, 0, 5, v65);
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 80LL))(v40);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v53);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v44);
  if ( v6 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(&v55);
  v62 = 0;
  v64 = 0;
  WindowsDeleteString(v45);
  v45 = 0;
  WindowsDeleteString(v46);
  v46 = 0;
  WindowsDeleteString(string);
  string = 0;
  v56 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(&v56);
  if ( v5 >= 0 )
    CoUninitialize();
  return v4;
}

```

## disassembly

```asm
0x180097b2c  mov     [rsp-8+arg_10], rbx
0x180097b31  push    rbp
0x180097b32  push    rsi
0x180097b33  push    rdi
0x180097b34  push    r12
0x180097b36  push    r13
0x180097b38  push    r14
0x180097b3a  push    r15
0x180097b3c  lea     rbp, [rsp-90h]
0x180097b44  sub     rsp, 190h
0x180097b4b  mov     rax, cs:__security_cookie
0x180097b52  xor     rax, rsp
0x180097b55  mov     [rbp+0C0h+var_40], rax
0x180097b5c  mov     r12, rdx
0x180097b5f  mov     r13, rcx
0x180097b62  xor     r14d, r14d
0x180097b65  test    rcx, rcx
0x180097b68  jnz     short loc_180097BAC
0x180097b6a  lea     r15, WPP_GLOBAL_Control
0x180097b71  mov     ebx, 80070057h
0x180097b76  mov     rcx, cs:WPP_GLOBAL_Control
0x180097b7d  cmp     rcx, r15
0x180097b80  jz      loc_1800986F4
0x180097b86  test    byte ptr [rcx+1Ch], 1
0x180097b8a  jz      loc_1800986F4
0x180097b90  lea     edx, [r13+0Ah]
0x180097b94  mov     r9d, ebx
0x180097b97  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x180097b9e  mov     rcx, [rcx+10h]
0x180097ba2  call    WPP_SF_d
0x180097ba7  jmp     loc_1800986F4
0x180097bac  call    cs:__imp_GetTickCount64
0x180097bb3  nop     dword ptr [rax+rax+00h]
0x180097bb8  mov     [rbp+0C0h+var_130], rax
0x180097bbc  xor     edx, edx; dwCoInit
0x180097bbe  xor     ecx, ecx; pvReserved
0x180097bc0  call    cs:__imp_CoInitializeEx
0x180097bc7  nop     dword ptr [rax+rax+00h]
0x180097bcc  mov     esi, eax
0x180097bce  mov     [rbp+0C0h+var_F0], eax
0x180097bd1  mov     [rbp+0C0h+pHandles], r14
0x180097bd5  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180097bdc  mov     [rbp+0C0h+var_108], rax
0x180097be0  mov     [rsp+1C0h+string], r14
0x180097be5  mov     [rsp+1C0h+var_158], r14
0x180097bea  mov     [rsp+1C0h+var_160], r14
0x180097bef  mov     [rbp+0C0h+var_98], r14
0x180097bf3  mov     r9d, 41h ; 'A'; unsigned int
0x180097bf9  lea     r8d, [r9+1]; unsigned int
0x180097bfd  lea     rdx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QB_WB; "Windows.Internal.Security.WebAuthentica"...
0x180097c04  lea     rcx, [rbp+0C0h+hstringHeader]; hstringHeader
0x180097c08  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180097c0d  nop
0x180097c0e  mov     [rbp+0C0h+var_B8], r14
0x180097c12  mov     r9d, 45h ; 'E'; unsigned int
0x180097c18  lea     r8d, [r9+1]; unsigned int
0x180097c1c  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QB_WB; "Windows.Security.Authentication.OnlineI"...
0x180097c23  lea     rcx, [rbp+0C0h+var_D0]; hstringHeader
0x180097c27  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)
0x180097c2c  nop
0x180097c2d  mov     [rbp+0C0h+var_110], r14
0x180097c31  mov     [rbp+0C0h+var_118], r14
0x180097c35  mov     [rbp+0C0h+var_138], r14
0x180097c39  mov     rdi, r14
0x180097c3c  mov     [rbp+0C0h+var_F8], r14
0x180097c40  mov     [rsp+1C0h+var_168], r14
0x180097c45  mov     [rsp+1C0h+var_180], r14
0x180097c4a  mov     [rbp+0C0h+var_120], r14
0x180097c4e  mov     [rbp+0C0h+var_128], r14
0x180097c52  mov     [rbp+0C0h+var_140], r14
0x180097c56  mov     ecx, 80000000h
0x180097c5b  lea     eax, [rsi+rcx]
0x180097c5e  lea     r15, WPP_GLOBAL_Control
0x180097c65  test    ecx, eax
0x180097c67  jnz     short loc_180097CAA
0x180097c69  cmp     esi, 80010106h
0x180097c6f  jz      short loc_180097CAA
0x180097c71  mov     ebx, esi
0x180097c73  mov     rcx, cs:WPP_GLOBAL_Control
0x180097c7a  cmp     rcx, r15
0x180097c7d  jz      loc_180098528
0x180097c83  test    byte ptr [rcx+1Ch], 1
0x180097c87  jz      loc_180098528
0x180097c8d  mov     edx, 0Bh
0x180097c92  mov     r9d, esi
0x180097c95  lea     r8, WPP_22990224b7aa36bbe1cc6db997248c54_Traceguids
0x180097c9c  mov     rcx, [rcx+10h]
0x180097ca0  call    WPP_SF_d
0x180097ca5  jmp     loc_180098528
0x180097caa  lea     rcx, [rbp+0C0h+var_110]
0x180097cae  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180097cb3  lea     r8, [rbp+0C0h+var_110]
0x180097cb7  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180097cbe  mov     rcx, [rbp+0C0h+var_B8]
0x180097cc2  call    cs:__imp_RoGetActivationFactory
0x180097cc9  nop     dword ptr [rax+rax+00h]
0x180097cce  mov     ebx, eax
0x180097cd0  test    eax, eax
0x180097cd2  jns     short loc_180097CF8
0x180097cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180097cdb  cmp     rcx, r15
0x180097cde  jz      loc_180098528
0x180097ce4  test    byte ptr [rcx+1Ch], 1
0x180097ce8  jz      loc_180098528
0x180097cee  mov     edx, 0Ch
0x180097cf3  mov     r9d, eax
0x180097cf6  jmp     short loc_180097C95
0x180097cf8  mov     rcx, [rsp+1C0h+string]; string
0x180097cfd  call    cs:__imp_WindowsDeleteString
0x180097d04  nop     dword ptr [rax+rax+00h]
0x180097d09  mov     [rsp+1C0h+string], r14
0x180097d0e  lea     r8, [rsp+1C0h+string]; string
0x180097d13  mov     edx, 26h ; '&'; length
0x180097d18  lea     rcx, sourceString; "https://watson.telemetry.microsoft.com"
0x180097d1f  call    cs:__imp_WindowsCreateString
0x180097d26  nop     dword ptr [rax+rax+00h]
0x180097d2b  mov     ebx, eax
0x180097d2d  test    eax, eax
0x180097d2f  jns     short loc_180097D52
0x180097d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d38  cmp     rcx, r15
0x180097d3b  jz      loc_180098528
0x180097d41  test    byte ptr [rcx+1Ch], 1
0x180097d45  jz      loc_180098528
0x180097d4b  mov     edx, 0Dh
0x180097d50  jmp     short loc_180097CF3
0x180097d52  mov     rcx, [rsp+1C0h+var_158]; string
0x180097d57  call    cs:__imp_WindowsDeleteString
0x180097d5e  nop     dword ptr [rax+rax+00h]
0x180097d63  mov     [rsp+1C0h+var_158], r14
0x180097d68  lea     r8, [rsp+1C0h+var_158]; string
0x180097d6d  mov     edx, 7; length
0x180097d72  lea     rcx, aMbiSsl; "MBI_SSL"
0x180097d79  call    cs:__imp_WindowsCreateString
0x180097d80  nop     dword ptr [rax+rax+00h]
0x180097d85  mov     ebx, eax
0x180097d87  test    eax, eax
0x180097d89  jns     short loc_180097DAF
0x180097d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d92  cmp     rcx, r15
0x180097d95  jz      loc_180098528
0x180097d9b  test    byte ptr [rcx+1Ch], 1
0x180097d9f  jz      loc_180098528
0x180097da5  mov     edx, 0Eh
0x180097daa  jmp     loc_180097CF3
0x180097daf  mov     r14, [rbp+0C0h+var_110]
0x180097db3  mov     rax, [r14]
0x180097db6  mov     rbx, [rax+30h]
0x180097dba  lea     rcx, [rbp+0C0h+var_118]
0x180097dbe  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180097dc3  lea     r9, [rbp+0C0h+var_118]
0x180097dc7  mov     r8, [rsp+1C0h+var_158]
0x180097dcc  mov     rdx, [rsp+1C0h+string]
0x180097dd1  mov     rcx, r14
0x180097dd4  mov     rax, rbx
0x180097dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ddc  mov     ebx, eax
0x180097dde  test    eax, eax
0x180097de0  jns     short loc_180097E06
0x180097de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180097de9  cmp     rcx, r15
0x180097dec  jz      loc_180098528
0x180097df2  test    byte ptr [rcx+1Ch], 1
0x180097df6  jz      loc_180098528
0x180097dfc  mov     edx, 0Fh
0x180097e01  jmp     loc_180097CF3
0x180097e06  lea     rcx, [rbp+0C0h+var_138]
0x180097e0a  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180097e0f  lea     rdx, [rbp+0C0h+var_138]
0x180097e13  mov     rcx, [rbp+0C0h+var_98]
0x180097e17  call    ??$ActivateInstance@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAuthenticationManager@WebAuthentication@Security@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>(HSTRING__ *,Windows::Internal::Security::WebAuthentication::IAuthenticationManager * *)
0x180097e1c  mov     ebx, eax
0x180097e1e  test    eax, eax
0x180097e20  jns     short loc_180097E46
0x180097e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180097e29  cmp     rcx, r15
0x180097e2c  jz      loc_180098528
0x180097e32  test    byte ptr [rcx+1Ch], 1
0x180097e36  jz      loc_180098528
0x180097e3c  mov     edx, 10h
0x180097e41  jmp     loc_180097CF3
0x180097e46  mov     r9d, 1F0003h; dwDesiredAccess
0x180097e4c  xor     r8d, r8d; dwFlags
0x180097e4f  xor     edx, edx; lpName
0x180097e51  xor     ecx, ecx; lpEventAttributes
0x180097e53  call    cs:__imp_CreateEventExW
0x180097e5a  nop     dword ptr [rax+rax+00h]
0x180097e5f  mov     rbx, rax
0x180097e62  test    rax, rax
0x180097e65  jnz     short loc_180097E81
0x180097e67  call    cs:__imp_GetLastError
0x180097e6e  nop     dword ptr [rax+rax+00h]
0x180097e73  mov     ecx, eax; unsigned int
0x180097e75  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180097e7a  mov     ebx, eax
0x180097e7c  jmp     loc_180098528
0x180097e81  mov     rax, [rbp+0C0h+pHandles]
0x180097e85  cmp     rbx, rax
0x180097e88  jz      short loc_180097E9A
0x180097e8a  lea     rcx, [rbp+0C0h+var_108]
0x180097e8e  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x180097e93  mov     rax, rbx
0x180097e96  mov     [rbp+0C0h+pHandles], rbx
0x180097e9a  mov     [rbp+0C0h+var_F8], rax
0x180097e9e  lea     rdx, [rbp+0C0h+var_F8]
0x180097ea2  lea     rcx, [rsp+1C0h+dwindex]
0x180097ea7  call    ??$Make@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@PEAX@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@@12@$$QEAPEAX@Z; Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>,void *>(void * &&)
0x180097eac  mov     rdi, [rax]
0x180097eaf  mov     qword ptr [rax], 0
0x180097eb6  mov     [rbp+0C0h+var_F8], rdi
0x180097eba  mov     rcx, qword ptr [rsp+1C0h+dwindex]
0x180097ebf  test    rcx, rcx
0x180097ec2  jz      short loc_180097EDA
0x180097ec4  mov     qword ptr [rsp+1C0h+dwindex], 0
0x180097ecd  mov     rax, [rcx]
0x180097ed0  mov     rax, [rax+10h]
0x180097ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ed9  nop
0x180097eda  test    rdi, rdi
0x180097edd  jnz     short loc_180097EE9
0x180097edf  mov     ebx, 8007000Eh
0x180097ee4  jmp     loc_180098528
0x180097ee9  mov     rcx, [rbp+0C0h+var_138]
0x180097eed  movups  xmm0, cs:xmmword_1800C7C40
0x180097ef4  movdqu  [rbp+0C0h+var_E0], xmm0
0x180097ef9  mov     rax, [rcx]
0x180097efc  lea     rdx, [rbp+0C0h+var_E0]
0x180097f00  mov     rax, [rax+48h]
0x180097f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f09  mov     ebx, eax
0x180097f0b  test    eax, eax
0x180097f0d  jns     short loc_180097F33
0x180097f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180097f16  cmp     rcx, r15
0x180097f19  jz      loc_180098528
0x180097f1f  test    byte ptr [rcx+1Ch], 1
0x180097f23  jz      loc_180098528
0x180097f29  mov     edx, 11h
0x180097f2e  jmp     loc_180097CF3
0x180097f33  mov     r14, [rbp+0C0h+var_138]
0x180097f37  mov     rax, [r14]
0x180097f3a  mov     rbx, [rax+38h]
0x180097f3e  lea     rcx, [rsp+1C0h+var_168]
0x180097f43  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180097f48  lea     r8, [rsp+1C0h+var_168]
0x180097f4d  mov     rdx, [rbp+0C0h+var_118]
0x180097f51  mov     rcx, r14
0x180097f54  mov     rax, rbx
0x180097f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f5c  mov     ebx, eax
0x180097f5e  test    eax, eax
0x180097f60  jns     short loc_180097F86
0x180097f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180097f69  cmp     rcx, r15
0x180097f6c  jz      loc_180098528
0x180097f72  test    byte ptr [rcx+1Ch], 1
0x180097f76  jz      loc_180098528
0x180097f7c  mov     edx, 12h
0x180097f81  jmp     loc_180097CF3
0x180097f86  mov     rcx, [rsp+1C0h+var_168]
0x180097f8b  mov     rax, [rcx]
0x180097f8e  mov     rdx, rdi
0x180097f91  mov     rax, [rax+30h]
0x180097f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097f9a  mov     ebx, eax
0x180097f9c  test    eax, eax
0x180097f9e  jns     short loc_180097FC4
0x180097fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180097fa7  cmp     rcx, r15
0x180097faa  jz      loc_180098528
0x180097fb0  test    byte ptr [rcx+1Ch], 1
0x180097fb4  jz      loc_180098528
0x180097fba  mov     edx, 13h
0x180097fbf  jmp     loc_180097CF3
0x180097fc4  mov     rbx, [rsp+1C0h+var_168]
0x180097fc9  mov     rax, [rbx]
0x180097fcc  mov     r14, [rax]
0x180097fcf  lea     rcx, [rsp+1C0h+var_180]
0x180097fd4  call    ?InternalRelease@?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>::InternalRelease(void)
0x180097fd9  lea     r8, [rsp+1C0h+var_180]
0x180097fde  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180097fe5  mov     rcx, rbx
0x180097fe8  mov     rax, r14
0x180097feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ff0  mov     ebx, eax
0x180097ff2  test    eax, eax
0x180097ff4  jns     short loc_18009801A
0x180097ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180097ffd  cmp     rcx, r15
0x180098000  jz      loc_180098528
0x180098006  test    byte ptr [rcx+1Ch], 1
0x18009800a  jz      loc_180098528
0x180098010  mov     edx, 14h
0x180098015  jmp     loc_180097CF3
0x18009801a  mov     [rsp+1C0h+dwindex], 0
0x180098022  xor     r14d, r14d
0x180098025  xor     bl, bl
0x180098027  mov     rax, cs:WPP_GLOBAL_Control
0x18009802e  cmp     rax, r15
0x180098031  jz      loc_180098111
  ... truncated ...
```
