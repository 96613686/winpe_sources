# AuthManagerImpl::GetAuthContext(char * *,char * *,bool)

- ea: `0x180086e60`
- end: `0x180087c12`
- name: `?GetAuthContext@AuthManagerImpl@@UEAAJPEAPEAD0_N@Z`
- size: `3506`
- prototype: `__int64 __fastcall(AuthManagerImpl *this, char **, char **, __int64)`
- caller_count: `0`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007440`
- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180010044`
- `0x18001c06c`
- `0x18002f27c`
- `0x18002f2d8`
- `0x18002f808`
- `0x18003145c`
- `0x1800317d4`
- `0x180039a7c`
- `0x180045140`
- `0x180086294`
- `0x180086534`
- `0x180086668`
- `0x180086e60`
- `0x180087c18`
- `0x1800881d4`
- `0x180088450`
- `0x180088b5c`
- `0x180088ccc`
- `0x180088ddc`
- `0x180088f40`
- `0x1800892d4`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180087466`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180087466`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800875c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800875c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087a36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086f58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087627`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180086f58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087627`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087023`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180087023`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008758f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18008758f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008700a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008700a`

## string_xrefs

- `0x180087003`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`

## pseudocode

```c
__int64 __fastcall AuthManagerImpl::GetAuthContext(AuthManagerImpl *this, char **a2, char **a3, __int64 a4)
{
  unsigned __int8 v5; // cl
  __int64 v6; // r14
  unsigned int v7; // r13d
  __int64 v8; // r15
  bool v9; // bl
  __int64 v10; // rcx
  WpnconTelemetry *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  int v13; // r12d
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rdi
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  PVOID v41; // rcx
  int v42; // eax
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  unsigned __int64 v50; // rdx
  unsigned __int8 v51; // cl
  bool v52; // di
  bool v53; // si
  __int64 v54; // rcx
  WpnconTelemetry *v55; // rax
  int v57; // [rsp+20h] [rbp-69h]
  char v58; // [rsp+30h] [rbp-59h]
  char v59; // [rsp+31h] [rbp-58h]
  struct IAsyncInfo *v60; // [rsp+38h] [rbp-51h] BYREF
  __int64 v61; // [rsp+40h] [rbp-49h] BYREF
  int v62; // [rsp+48h] [rbp-41h] BYREF
  int v63; // [rsp+4Ch] [rbp-3Dh] BYREF
  struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest *v64; // [rsp+50h] [rbp-39h] BYREF
  __int64 (__fastcall ***v65)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-31h] BYREF
  __int64 v66; // [rsp+60h] [rbp-29h] BYREF
  __int64 v67; // [rsp+68h] [rbp-21h] BYREF
  char **v68; // [rsp+70h] [rbp-19h]
  char **v69; // [rsp+78h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v59 = a4;
  v68 = a3;
  v69 = a2;
  v5 = (unsigned __int8)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = *((_DWORD *)this + 2) == 1;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, a4);
  }
  v6 = 0;
  v7 = 0;
  v64 = 0;
  v61 = 0;
  v60 = 0;
  v62 = 0;
  v8 = 0;
  v9 = *((_DWORD *)this + 2) == 1;
  if ( WpnconTelemetry::IsEnabled(v5, (unsigned __int64)a2) )
  {
    v11 = (WpnconTelemetry *)wil::details::static_lazy<WpnconTelemetry>::get(
                               v10,
                               _lambda_de4d36b645fed666bcd49a481e929f91_::_lambda_invoker_cdecl_);
    WpnconTelemetry::AuthenticationStart_(v11, v9);
  }
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  do
  {
    v58 = 0;
    v13 = 0;
    v63 = 0;
    v64 = 0;
    v61 = 0;
    v66 = 0;
    v60 = 0;
    *v69 = 0;
    *v68 = 0;
    v67 = 0;
    v65 = 0;
    EnterCriticalSection(v12);
    if ( *((_QWORD *)this + 3) )
    {
      v14 = -2147483638;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, 2147483658LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
        (const char *)0x8000000ALL,
        v57);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v16 = 30;
        v17 = 2147483658LL;
        goto LABEL_16;
      }
    }
    else
    {
      if ( WindowsCreateStringReference(
             L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
             0x41u,
             (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
             (HSTRING *)&hstringHeader) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>(
              hstringHeader.Reserved.Reserved1,
              &v65);
      v14 = v18;
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
            (unsigned int)v18);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
          (const char *)v14,
          v57);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v16 = 32;
          goto LABEL_27;
        }
        goto LABEL_166;
      }
      if ( v59 )
      {
        v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v65;
        v23 = **v65;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67, v19, v20, v21);
        v24 = v23(v22, &GUID_f2d7a32c_a4f9_483c_bbc5_3cff03609807, &v67);
        v14 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x106,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
            (const char *)(unsigned int)v24,
            v57);
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v16 = 33;
            goto LABEL_27;
          }
          goto LABEL_166;
        }
        v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 24LL))(v67);
        v14 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x109,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
            (const char *)(unsigned int)v25,
            v57);
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v16 = 34;
            goto LABEL_27;
          }
          goto LABEL_166;
        }
        v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
      }
      *(GUID *)&hstringHeader.Reserved.Reserved1 = AuthManagerImpl::s_AppId;
      v26 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING_HEADER *))(*v65)[9])(
              v65,
              &hstringHeader);
      v14 = v26;
      if ( v26 >= 0 )
      {
        v27 = AuthManagerImpl::LoadRequest(this, &v64);
        v14 = v27;
        if ( v27 >= 0 )
        {
          LOBYTE(v28) = *((_DWORD *)this + 2) == 1;
          v8 = PdcActivateNetwork(0, v28, v29, v30);
          if ( v8 )
          {
            v31 = (*v65)[7](v65, (GUID *)v64, &v61);
            v14 = v31;
            if ( v31 >= 0 )
            {
              v32 = DeviceAuthenticationOperationSink::CreateInstance(*((_QWORD *)this + 4), &v66);
              v14 = v32;
              if ( v32 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    43,
                    WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                    (unsigned int)v32);
                }
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                  (const char *)v14,
                  v57);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    44,
                    WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                    v14);
                v6 = v66;
                goto LABEL_166;
              }
              ResetEvent(*((HANDLE *)this + 4));
              v6 = v66;
              v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v61 + 48LL))(v61, v66);
              v14 = v33;
              if ( v33 >= 0 )
              {
                v34 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IAsyncInfo **))v61)(
                        v61,
                        &GUID_00000036_0000_0000_c000_000000000046,
                        &v60);
                v14 = v34;
                if ( v34 >= 0 )
                {
                  *((_QWORD *)this + 2) = GetTickCount64();
                  if ( (byte_1800AFD82 & 0x40) != 0 )
                    McTemplateU0q_EventWriteTransfer(v35, WPNPRV_AUTH_DEVICE_ID_REQUEST, *((_DWORD *)this + 2) == 1);
                  *((_QWORD *)this + 3) = v60;
                  LeaveCriticalSection(v12);
                  v14 = AuthManagerImpl::WaitForCompletion(this);
                  if ( (v14 & 0x80000000) != 0
                    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      49,
                      WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                      v14);
                  }
                  LOBYTE(v36) = *((_DWORD *)this + 2) == 1;
                  PdcDeactivateNetwork(v8, 0, v36, v37);
                  v8 = 0;
                  EnterCriticalSection(v12);
                  if ( (v14 & 0x80000000) == 0 )
                  {
                    v38 = *((_QWORD *)this + 3);
                    if ( v38 )
                    {
                      v39 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 56LL))(v38, &v62);
                      v14 = v39;
                      if ( v39 >= 0 )
                      {
                        switch ( v62 )
                        {
                          case 1:
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                            {
                              WPP_SF_(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                55,
                                WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids);
                            }
                            v42 = AuthManagerImpl::OnCompleted(this);
                            v14 = v42;
                            if ( v42 >= 0 )
                            {
LABEL_160:
                              v43 = ((__int64 (__fastcall *)(struct IAsyncInfo *))v60->lpVtbl->Close)(v60);
                              v14 = v43;
                              if ( v43 < 0 )
                              {
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                {
                                  WPP_SF_d(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    63,
                                    WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                                    (unsigned int)v43);
                                }
                                v14 = 0;
                              }
                              break;
                            }
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                56,
                                WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                                (unsigned int)v42);
                            }
                            wil::details::in1diag3::_Log_Hr(
                              retaddr,
                              (void *)0x164,
                              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                              (const char *)v14,
                              v57);
                            v15 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                            {
                              v16 = 57;
LABEL_27:
                              v17 = v14;
LABEL_16:
                              WPP_SF_d(v15[2], v16, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v17);
                            }
                            break;
                          case 2:
                            v14 = -2147467260;
                            v41 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                61,
                                WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                                2147500036LL);
                            }
                            if ( (byte_1800AFD83 & 1) != 0 )
                              McTemplateU0qq_EventWriteTransfer(
                                v41,
                                WPNPRV_AUTH_DEVICE_ID_FAILURE,
                                2147500036LL,
                                *((_DWORD *)this + 2) == 1);
                            AuthManagerImpl::LogQos(this, -2147467260);
                            wil::details::in1diag3::_Log_Hr(
                              retaddr,
                              (void *)0x17A,
                              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                              (const char *)0x80004004LL,
                              v57);
                            v15 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                            {
                              v16 = 62;
                              goto LABEL_114;
                            }
                            break;
                          case 3:
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                            {
                              WPP_SF_(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                58,
                                WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids);
                            }
                            v40 = AuthManagerImpl::OnError(this, v60, &v63);
                            v14 = v40;
                            v13 = v63;
                            if ( v40 >= 0 )
                            {
                              v14 = v63;
                              if ( v63 >= 0 )
                                goto LABEL_160;
                            }
                            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                59,
                                WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                                (unsigned int)v40);
                            }
                            wil::details::in1diag3::_Log_Hr(
                              retaddr,
                              (void *)0x171,
                              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                              (const char *)v14,
                              v57);
                            v15 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                            {
                              v16 = 60;
                              goto LABEL_27;
                            }
                            break;
                          default:
                            goto LABEL_160;
                        }
                      }
                      else
                      {
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            53,
                            WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                            (unsigned int)v39);
                        }
                        wil::details::in1diag3::_Log_Hr(
                          retaddr,
                          (void *)0x15B,
                          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                          (const char *)v14,
                          v57);
                        v15 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                        {
                          v16 = 54;
                          goto LABEL_27;
                        }
                      }
                    }
                    else
                    {
                      v14 = -2147467260;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v57 = -2147467260;
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          51,
                          WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids);
                      }
                      wil::details::in1diag3::_Log_Hr(
                        retaddr,
                        (void *)0x156,
                        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                        (const char *)0x80004004LL,
                        v57);
                      v15 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                      {
                        v16 = 52;
LABEL_114:
                        v17 = 2147500036LL;
                        goto LABEL_16;
                      }
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x14E,
                      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                      (const char *)v14,
                      v57);
                    v15 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                    {
                      v16 = 50;
                      goto LABEL_27;
                    }
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      47,
                      WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                      (unsigned int)v34);
                  }
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x136,
                    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                    (const char *)v14,
                    v57);
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                  {
                    v16 = 48;
                    goto LABEL_27;
                  }
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    45,
                    WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                    (unsigned int)v33);
                }
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x132,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                  (const char *)v14,
                  v57);
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
                {
                  v16 = 46;
                  goto LABEL_27;
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  41,
                  WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
                  (unsigned int)v31);
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x122,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
                (const char *)v14,
                v57);
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
              {
                v16 = 42;
                goto LABEL_27;
              }
            }
          }
          else
          {
            v14 = -2147467259;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x11D,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
              (const char *)0x80004005LL,
              v57);
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v16 = 40;
              v17 = 2147500037LL;
              goto LABEL_16;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              37,
              WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
              (unsigned int)v27);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x112,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
            (const char *)v14,
            v57);
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v16 = 38;
            goto LABEL_27;
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids,
            (unsigned int)v26);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10E,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\auth\\authmanagerimpl.cpp",
          (const char *)v14,
          v57);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v16 = 36;
          goto LABEL_27;
        }
      }
    }
LABEL_166:
    if ( v60 )
      *((_QWORD *)this + 3) = 0;
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
    if ( v8 )
    {
      LOBYTE(v45) = *((_DWORD *)this + 2) == 1;
      PdcDeactivateNetwork(v8, 0, v45, v46);
      v8 = 0;
    }
    if ( v60 )
    {
      ((void (__fastcall *)(struct IAsyncInfo *))v60->lpVtbl->Release)(v60);
      v60 = 0;
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v6 = 0;
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( v64 )
    {
      (*(void (__fastcall **)(struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest *))(*(_QWORD *)v64 + 16LL))(v64);
      v64 = 0;
    }
    if ( v14 == -2147023665 )
    {
      if ( ++v7 > 3 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, 3);
        }
        AuthManagerImpl::ProbeNcsi(this);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v7);
        }
        v58 = 1;
        AuthManagerImpl::WaitForAnotherAuthRetry(this);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v44, v45, v46);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67, v47, v48, v49);
  }
  while ( v58 );
  v52 = *((_DWORD *)this + 2) == 1;
  v53 = *v68 == 0;
  if ( WpnconTelemetry::IsEnabled(v51, v50) )
  {
    v55 = (WpnconTelemetry *)wil::details::static_lazy<WpnconTelemetry>::get(
                               v54,
                               _lambda_de4d36b645fed666bcd49a481e929f91_::_lambda_invoker_cdecl_);
    WpnconTelemetry::AuthenticationEnd_(v55, v53, v52, v14, v13);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x180086e60  mov     [rsp-8+arg_18], rbx
0x180086e65  push    rbp
0x180086e66  push    rsi
0x180086e67  push    rdi
0x180086e68  push    r12
0x180086e6a  push    r13
0x180086e6c  push    r14
0x180086e6e  push    r15
0x180086e70  lea     rbp, [rsp-27h]
0x180086e75  sub     rsp, 0B0h
0x180086e7c  mov     rax, cs:__security_cookie
0x180086e83  xor     rax, rsp
0x180086e86  mov     [rbp+57h+var_40], rax
0x180086e8a  mov     [rbp+57h+var_AF], r9b
0x180086e8e  mov     [rbp+57h+var_70], r8
0x180086e92  mov     [rbp+57h+var_68], rdx
0x180086e96  mov     rsi, rcx
0x180086e99  lea     rax, WPP_GLOBAL_Control
0x180086ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180086ea7  cmp     rcx, rax
0x180086eaa  jz      short loc_180086ED5
0x180086eac  test    byte ptr [rcx+1Ch], 10h
0x180086eb0  jz      short loc_180086ED5
0x180086eb2  cmp     byte ptr [rcx+19h], 6
0x180086eb6  jb      short loc_180086ED5
0x180086eb8  cmp     dword ptr [rsi+8], 1
0x180086ebc  setz    r9b
0x180086ec0  mov     edx, 1Ch
0x180086ec5  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086ecc  mov     rcx, [rcx+10h]
0x180086ed0  call    WPP_SF_c
0x180086ed5  xor     r14d, r14d
0x180086ed8  mov     r13d, r14d
0x180086edb  mov     [rbp+57h+var_90], r14
0x180086edf  mov     [rbp+57h+var_A0], r14
0x180086ee3  mov     [rbp+57h+var_A8], r14
0x180086ee7  mov     [rbp+57h+var_98], r14d
0x180086eeb  mov     r15d, r14d
0x180086eee  cmp     dword ptr [rsi+8], 1
0x180086ef2  setz    bl
0x180086ef5  call    ?IsEnabled@WpnconTelemetry@@SA_NE_K@Z; WpnconTelemetry::IsEnabled(uchar,unsigned __int64)
0x180086efa  test    al, al
0x180086efc  jz      short loc_180086F14
0x180086efe  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_de4d36b645fed666bcd49a481e929f91_@@CA@XZ; _lambda_de4d36b645fed666bcd49a481e929f91_::_lambda_invoker_cdecl_(void)
0x180086f05  call    ?get@?$static_lazy@VWpnconTelemetry@@@details@wil@@QEAAPEAVWpnconTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpnconTelemetry>::get(void (*)(void))
0x180086f0a  mov     dl, bl; bool
0x180086f0c  mov     rcx, rax; this
0x180086f0f  call    ?AuthenticationStart_@WpnconTelemetry@@QEAAX_N@Z; WpnconTelemetry::AuthenticationStart_(bool)
0x180086f14  lea     rdi, [rsi+28h]
0x180086f18  mov     [rbp+57h+var_B0], r14b
0x180086f1c  mov     r12d, r14d
0x180086f1f  mov     [rbp+57h+var_94], r14d
0x180086f23  mov     [rbp+57h+var_90], r14
0x180086f27  mov     [rbp+57h+var_A0], r14
0x180086f2b  mov     [rbp+57h+var_80], r14
0x180086f2f  xor     ebx, ebx
0x180086f31  mov     [rbp+57h+var_A8], rbx
0x180086f35  mov     rax, [rbp+57h+var_68]
0x180086f39  mov     [rax], rbx
0x180086f3c  mov     rax, [rbp+57h+var_70]
0x180086f40  mov     [rax], rbx
0x180086f43  mov     [rbp+57h+var_78], rbx
0x180086f47  mov     [rbp+57h+var_88], rbx
0x180086f4b  test    r15, r15
0x180086f4e  jz      short loc_180086F55
0x180086f50  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180086f55  mov     rcx, rdi; lpCriticalSection
0x180086f58  call    cs:__imp_EnterCriticalSection
0x180086f5e  cmp     [rsi+18h], rbx
0x180086f62  jz      loc_180086FF6
0x180086f68  mov     ebx, 8000000Ah
0x180086f6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180086f74  lea     rdi, WPP_GLOBAL_Control
0x180086f7b  cmp     rcx, rdi
0x180086f7e  jz      short loc_180086FA4
0x180086f80  test    byte ptr [rcx+1Ch], 10h
0x180086f84  jz      short loc_180086FA4
0x180086f86  cmp     byte ptr [rcx+19h], 2
0x180086f8a  jb      short loc_180086FA4
0x180086f8c  mov     edx, 1Dh
0x180086f91  mov     r9d, ebx
0x180086f94  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086f9b  mov     rcx, [rcx+10h]
0x180086f9f  call    WPP_SF_d
0x180086fa4  mov     rcx, [rbp+5Fh]; this
0x180086fa8  mov     r9d, ebx; char *
0x180086fab  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180086fb2  mov     edx, 0F7h; void *
0x180086fb7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180086fc3  cmp     rcx, rdi
0x180086fc6  jz      loc_180087A20
0x180086fcc  test    byte ptr [rcx+1Ch], 80h
0x180086fd0  jz      loc_180087A20
0x180086fd6  mov     edx, 1Eh
0x180086fdb  mov     r9d, 8000000Ah
0x180086fe1  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180086fe8  mov     rcx, [rcx+10h]
0x180086fec  call    WPP_SF_d
0x180086ff1  jmp     loc_180087A20
0x180086ff6  lea     r9, [rbp+57h+hstringHeader]; string
0x180086ffa  lea     r8, [rbp+57h+hstringHeader.Reserved+8]; hstringHeader
0x180086ffe  mov     edx, 41h ; 'A'; length
0x180087003  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x18008700a  call    cs:__imp_WindowsCreateStringReference
0x180087010  test    eax, eax
0x180087012  jns     short loc_180087029
0x180087014  xor     r9d, r9d; lpArguments
0x180087017  xor     r8d, r8d; nNumberOfArguments
0x18008701a  lea     edx, [r9+1]; dwExceptionFlags
0x18008701e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180087023  call    cs:__imp_RaiseException
0x180087029  lea     rdx, [rbp+57h+var_88]
0x18008702d  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x180087031  call    ??$ActivateInstance@V?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>)
0x180087036  mov     ebx, eax
0x180087038  test    eax, eax
0x18008703a  jns     short loc_1800870B2
0x18008703c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087043  lea     rdi, WPP_GLOBAL_Control
0x18008704a  cmp     rcx, rdi
0x18008704d  jz      short loc_180087073
0x18008704f  test    byte ptr [rcx+1Ch], 10h
0x180087053  jz      short loc_180087073
0x180087055  cmp     byte ptr [rcx+19h], 2
0x180087059  jb      short loc_180087073
0x18008705b  mov     edx, 1Fh
0x180087060  mov     r9d, eax
0x180087063  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x18008706a  mov     rcx, [rcx+10h]
0x18008706e  call    WPP_SF_d
0x180087073  mov     rcx, [rbp+5Fh]; this
0x180087077  mov     r9d, ebx; char *
0x18008707a  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180087081  mov     edx, 0FFh; void *
0x180087086  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008708b  mov     rcx, cs:WPP_GLOBAL_Control
0x180087092  cmp     rcx, rdi
0x180087095  jz      loc_180087A20
0x18008709b  test    byte ptr [rcx+1Ch], 80h
0x18008709f  jz      loc_180087A20
0x1800870a5  mov     edx, 20h ; ' '
0x1800870aa  mov     r9d, ebx
0x1800870ad  jmp     loc_180086FE1
0x1800870b2  cmp     [rbp+57h+var_AF], 0
0x1800870b6  jz      loc_18008718B
0x1800870bc  mov     rbx, [rbp+57h+var_88]
0x1800870c0  mov     rax, [rbx]
0x1800870c3  mov     rdi, [rax]
0x1800870c6  lea     rcx, [rbp+57h+var_78]
0x1800870ca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800870cf  lea     r8, [rbp+57h+var_78]
0x1800870d3  lea     rdx, _GUID_f2d7a32c_a4f9_483c_bbc5_3cff03609807
0x1800870da  mov     rcx, rbx
0x1800870dd  mov     rax, rdi
0x1800870e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870e5  mov     ebx, eax
0x1800870e7  test    eax, eax
0x1800870e9  jns     short loc_18008712E
0x1800870eb  mov     rcx, [rbp+5Fh]; this
0x1800870ef  mov     r9d, eax; char *
0x1800870f2  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800870f9  mov     edx, 106h; void *
0x1800870fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087103  mov     rcx, cs:WPP_GLOBAL_Control
0x18008710a  lea     rax, WPP_GLOBAL_Control
0x180087111  cmp     rcx, rax
0x180087114  jz      loc_180087A20
0x18008711a  test    byte ptr [rcx+1Ch], 80h
0x18008711e  jz      loc_180087A20
0x180087124  mov     edx, 21h ; '!'
0x180087129  jmp     loc_1800870AA
0x18008712e  mov     rcx, [rbp+57h+var_78]
0x180087132  mov     rax, [rcx]
0x180087135  mov     rax, [rax+18h]
0x180087139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008713e  mov     ebx, eax
0x180087140  test    eax, eax
0x180087142  jns     short loc_180087187
0x180087144  mov     rcx, [rbp+5Fh]; this
0x180087148  mov     r9d, eax; char *
0x18008714b  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180087152  mov     edx, 109h; void *
0x180087157  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008715c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087163  lea     rax, WPP_GLOBAL_Control
0x18008716a  cmp     rcx, rax
0x18008716d  jz      loc_180087A20
0x180087173  test    byte ptr [rcx+1Ch], 80h
0x180087177  jz      loc_180087A20
0x18008717d  mov     edx, 22h ; '"'
0x180087182  jmp     loc_1800870AA
0x180087187  lea     rdi, [rsi+28h]
0x18008718b  mov     rcx, [rbp+57h+var_88]
0x18008718f  movups  xmm0, xmmword ptr cs:?s_AppId@AuthManagerImpl@@0U_GUID@@A.Data1; _GUID AuthManagerImpl::s_AppId ...
0x180087196  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18008719b  mov     rax, [rcx]
0x18008719e  lea     rdx, [rbp+57h+hstringHeader]
0x1800871a2  mov     rax, [rax+48h]
0x1800871a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871ab  mov     ebx, eax
0x1800871ad  test    eax, eax
0x1800871af  jns     short loc_180087224
0x1800871b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800871b8  lea     rdi, WPP_GLOBAL_Control
0x1800871bf  cmp     rcx, rdi
0x1800871c2  jz      short loc_1800871E8
0x1800871c4  test    byte ptr [rcx+1Ch], 10h
0x1800871c8  jz      short loc_1800871E8
0x1800871ca  cmp     byte ptr [rcx+19h], 2
0x1800871ce  jb      short loc_1800871E8
0x1800871d0  mov     edx, 23h ; '#'
0x1800871d5  mov     r9d, eax
0x1800871d8  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x1800871df  mov     rcx, [rcx+10h]
0x1800871e3  call    WPP_SF_d
0x1800871e8  mov     rcx, [rbp+5Fh]; this
0x1800871ec  mov     r9d, ebx; char *
0x1800871ef  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800871f6  mov     edx, 10Eh; void *
0x1800871fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087200  mov     rcx, cs:WPP_GLOBAL_Control
0x180087207  cmp     rcx, rdi
0x18008720a  jz      loc_180087A20
0x180087210  test    byte ptr [rcx+1Ch], 80h
0x180087214  jz      loc_180087A20
0x18008721a  mov     edx, 24h ; '$'
0x18008721f  jmp     loc_1800870AA
0x180087224  lea     rdx, [rbp+57h+var_90]; struct Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest **
0x180087228  mov     rcx, rsi; this
0x18008722b  call    ?LoadRequest@AuthManagerImpl@@AEAAJPEAPEAUIOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Z; AuthManagerImpl::LoadRequest(Windows::Security::Authentication::OnlineId::IOnlineIdServiceTicketRequest * *)
0x180087230  mov     ebx, eax
0x180087232  test    eax, eax
0x180087234  jns     short loc_1800872A9
0x180087236  mov     rcx, cs:WPP_GLOBAL_Control
0x18008723d  lea     rdi, WPP_GLOBAL_Control
0x180087244  cmp     rcx, rdi
0x180087247  jz      short loc_18008726D
0x180087249  test    byte ptr [rcx+1Ch], 10h
0x18008724d  jz      short loc_18008726D
0x18008724f  cmp     byte ptr [rcx+19h], 2
0x180087253  jb      short loc_18008726D
0x180087255  mov     edx, 25h ; '%'
0x18008725a  mov     r9d, eax
0x18008725d  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x180087264  mov     rcx, [rcx+10h]
0x180087268  call    WPP_SF_d
0x18008726d  mov     rcx, [rbp+5Fh]; this
0x180087271  mov     r9d, ebx; char *
0x180087274  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18008727b  mov     edx, 112h; void *
0x180087280  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180087285  mov     rcx, cs:WPP_GLOBAL_Control
0x18008728c  cmp     rcx, rdi
0x18008728f  jz      loc_180087A20
0x180087295  test    byte ptr [rcx+1Ch], 80h
0x180087299  jz      loc_180087A20
0x18008729f  mov     edx, 26h ; '&'
0x1800872a4  jmp     loc_1800870AA
0x1800872a9  cmp     dword ptr [rsi+8], 1
0x1800872ad  setz    dl
0x1800872b0  xor     ecx, ecx
0x1800872b2  call    ?PdcActivateNetwork@@YAPEAXW4_PDC_REAOSN@@_N@Z; PdcActivateNetwork(_PDC_REAOSN,bool)
0x1800872b7  mov     r15, rax
0x1800872ba  test    rax, rax
0x1800872bd  jnz     short loc_180087338
0x1800872bf  mov     ebx, 80004005h
0x1800872c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800872cb  lea     rdi, WPP_GLOBAL_Control
0x1800872d2  cmp     rcx, rdi
0x1800872d5  jz      short loc_1800872F6
0x1800872d7  test    byte ptr [rcx+1Ch], 10h
0x1800872db  jz      short loc_1800872F6
0x1800872dd  cmp     byte ptr [rcx+19h], 2
0x1800872e1  jb      short loc_1800872F6
0x1800872e3  lea     edx, [rax+27h]
0x1800872e6  lea     r8, WPP_1958f0148acf3fcf82ef847767d864c5_Traceguids
0x1800872ed  mov     rcx, [rcx+10h]
0x1800872f1  call    WPP_SF_
0x1800872f6  mov     rcx, [rbp+5Fh]; this
0x1800872fa  mov     r9d, ebx; char *
0x1800872fd  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180087304  mov     edx, 11Dh; void *
0x180087309  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008730e  mov     rcx, cs:WPP_GLOBAL_Control
0x180087315  cmp     rcx, rdi
0x180087318  jz      loc_180087A20
0x18008731e  test    byte ptr [rcx+1Ch], 80h
0x180087322  jz      loc_180087A20
0x180087328  mov     edx, 28h ; '('
0x18008732d  mov     r9d, 80004005h
0x180087333  jmp     loc_180086FE1
0x180087338  mov     rcx, [rbp+57h+var_88]
0x18008733c  mov     rax, [rcx]
0x18008733f  lea     r8, [rbp+57h+var_A0]
0x180087343  mov     rdx, [rbp+57h+var_90]
0x180087347  mov     rax, [rax+38h]
0x18008734b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087350  mov     ebx, eax
0x180087352  test    eax, eax
  ... truncated ...
```
