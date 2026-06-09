# CWNPNet::ProcessTridMsg(ulong,ulong,char const *,unsigned __int64,uchar *,long *,PDC_INCOMING_PACKET_POLICY *)

- ea: `0x18003fb38`
- end: `0x1800408ae`
- name: `?ProcessTridMsg@CWNPNet@@IEAA_NKKPEBD_KPEAEPEAJPEAUPDC_INCOMING_PACKET_POLICY@@@Z`
- size: `3446`
- prototype: `char __fastcall(CWNPNet *this, __int64, _BOOL8, const char *, struct IWNPNetEvents *Size, unsigned __int8 *Src, int *, struct PDC_INCOMING_PACKET_POLICY *)`
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d1b0`

## callees

- `0x180007924`
- `0x180008a9c`
- `0x180008b67`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180010044`
- `0x18001344c`
- `0x18001c06c`
- `0x18002e0b4`
- `0x18002f808`
- `0x180033edc`
- `0x180034ec4`
- `0x180035b80`
- `0x18003603c`
- `0x18003715c`
- `0x180037810`
- `0x180037934`
- `0x180038920`
- `0x180038a10`
- `0x180038b84`
- `0x180039ac4`
- `0x180039c44`
- `0x18003aa70`
- `0x18003d5c0`
- `0x18003deb4`
- `0x18003e5dc`
- `0x18003f0a0`
- `0x18003fb38`
- `0x1800421c0`
- `0x180044428`
- `0x1800447e8`
- `0x18004548c`
- `0x180045644`
- `0x180045ac8`
- `0x180045b44`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ffa1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ffa1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ff93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ff93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040059`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004013c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800403e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800404ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004058c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040599`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040059`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004013c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800403e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800404ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18004058c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040599`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CWNPNet::ProcessTridMsg(
        CWNPNet *this,
        __int64 a2,
        _BOOL8 a3,
        const char *a4,
        struct IWNPNetEvents *Size,
        unsigned __int8 *Src,
        int *a7,
        struct PDC_INCOMING_PACKET_POLICY *a8)
{
  unsigned int v9; // edi
  PVOID v11; // rcx
  unsigned __int64 v12; // r15
  unsigned __int8 *v13; // r13
  __int64 v14; // rdx
  CWNPNet *v15; // rcx
  char v16; // bl
  unsigned int v17; // edi
  struct PDC_INCOMING_PACKET_POLICY *v18; // rax
  PVOID *v19; // rcx
  CWNPNet *v20; // rcx
  int v21; // r8d
  __int64 v22; // r9
  struct IWNPNetEvents *v23; // r12
  PVOID *v24; // rcx
  CWNPRequest *v25; // r15
  int v26; // eax
  unsigned int v27; // r14d
  bool v28; // r8
  struct PDC_INCOMING_PACKET_POLICY *v29; // rax
  PVOID v30; // rcx
  struct PDC_INCOMING_PACKET_POLICY *v31; // rax
  HANDLE ProcessHeap; // rax
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r9
  struct PDC_INCOMING_PACKET_POLICY *v36; // rax
  int v37; // eax
  ULONGLONG v38; // rax
  unsigned __int8 *v39; // r8
  struct PDC_INCOMING_PACKET_POLICY *v40; // rax
  void *v41; // rcx
  void *v42; // rax
  void *v43; // rcx
  int v44; // eax
  unsigned __int64 v45; // rdx
  unsigned __int8 *v46; // r8
  unsigned __int64 v47; // rdx
  unsigned __int8 *v48; // r8
  __int64 v49; // rcx
  __int64 v50; // rcx
  ULONGLONG TickCount64; // rax
  __int64 v52; // rdx
  size_t v53; // rdi
  int NetworkInterfaceType; // eax
  int User; // eax
  int v56; // r14d
  int v57; // eax
  struct PDC_INCOMING_PACKET_POLICY *v58; // rax
  unsigned int v59; // edx
  int v61; // [rsp+20h] [rbp-38h]
  unsigned __int8 *v62; // [rsp+40h] [rbp-18h] BYREF
  CWNPRequestQueue *v63; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  CWNPRequest *RequestByTrID; // [rsp+A0h] [rbp+48h]
  unsigned int v66; // [rsp+A8h] [rbp+50h] BYREF
  BOOL v67; // [rsp+B0h] [rbp+58h]
  struct IWNPNetEvents *v68; // [rsp+B8h] [rbp+60h] BYREF

  v67 = a3;
  v66 = a2;
  v9 = a3;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v61 = a2;
    WPP_SF_Lddc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((unsigned int *)this + 52));
  }
  if ( !a4 || !*a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
  v12 = (unsigned __int64)Size;
  v13 = Src;
  if ( Size )
  {
    if ( Src )
      goto LABEL_13;
  }
  else if ( !Src )
  {
    goto LABEL_13;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(v11);
LABEL_13:
  if ( !a7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v11);
  LODWORD(Size) = 0;
  v63 = (CWNPNet *)((char *)this + 216);
  RequestByTrID = CWNPRequestQueue::FindRequestByTrID((CWNPNet *)((char *)this + 216), v9, a3);
  if ( RequestByTrID )
  {
    if ( CWNPNet::IsInCONNamespace(v15, a4) )
    {
      v23 = 0;
      if ( CWNPNet::GetErrorCodeFromVerb(v20, v66, (int *)&Size) )
      {
        v24 = (PVOID *)WPP_GLOBAL_Control;
        v17 = (unsigned int)Size;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          LOBYTE(v61) = *((_BYTE *)this + 1597);
          WPP_SF_dc(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            351,
            &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
            (unsigned int)Size,
            v61);
          v24 = (PVOID *)WPP_GLOBAL_Control;
        }
        v25 = RequestByTrID;
        v26 = *((_DWORD *)RequestByTrID + 1);
        switch ( v26 )
        {
          case 541344341:
            LODWORD(Size) = 541344341;
            if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 4) != 0 && *((_BYTE *)v24 + 25) >= 5u )
              WPP_SF_sdc(
                (unsigned int)v24[2],
                354,
                (unsigned int)&WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                (unsigned int)&Size,
                v17,
                *((_BYTE *)this + 1597));
            v27 = 5;
            break;
          case 541347394:
          case 541611073:
            LODWORD(Size) = *((_DWORD *)RequestByTrID + 1);
            if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 4) != 0 && *((_BYTE *)v24 + 25) >= 5u )
            {
              WPP_SF_sdc(
                (unsigned int)v24[2],
                353,
                (unsigned int)&WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                (unsigned int)&Size,
                v17,
                *((_BYTE *)this + 1597));
              v26 = (int)Size;
            }
            v27 = (v26 != 541611073) + 3;
            CWNPNet::ClearFastReconnectInfo(this);
            *((_DWORD *)this + 18) = v17;
            break;
          case 542395971:
            v27 = 2;
            if ( v17 == -2013002867 )
            {
              if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 4) != 0 && *((_BYTE *)v24 + 25) >= 5u )
              {
                LOBYTE(v22) = *((_BYTE *)this + 1597);
                WPP_SF_c(v24[2], 352, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, v22);
              }
              CWNPNet::ClearFastReconnectInfo(this);
              *((_DWORD *)this + 18) = -2013002867;
            }
            break;
          default:
            v17 = -2147418113;
            if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 4) != 0 && *((_BYTE *)v24 + 25) >= 5u )
            {
              LOBYTE(v61) = *((_BYTE *)this + 1597);
              WPP_SF_dc(v24[2], 355, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, 2147549183LL, v61);
            }
            v27 = 6;
            MicrosoftTelemetryAssertTriggeredNoArgs(v24);
            break;
        }
        CWNPNet::LogWnpConnectEnd(this, v17);
        CWNPNet::DisconnectInternal(this, v17, v27);
        v29 = a8;
        *(_DWORD *)a8 = 0;
        *((_DWORD *)v29 + 1) = 100;
        goto LABEL_186;
      }
      switch ( v66 )
      {
        case 0x20444255u:
          if ( v12 )
          {
            v17 = CWNPNet::SkipMimeHeaders(v12, v13, (unsigned __int64 *)&v68, (unsigned __int8 **)&Size);
            if ( (v17 & 0x80000000) != 0 )
            {
              Size = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                (char *)this + 1584,
                0);
              *((_BYTE *)this + 1596) = 0;
              if ( CWNPNet::GetEvents(this, &Size) )
                (*(void (__fastcall **)(struct IWNPNetEvents *, _QWORD, _QWORD))(*(_QWORD *)Size + 64LL))(
                  Size,
                  *((_QWORD *)this + 47),
                  v17);
              *((_QWORD *)this + 47) = 0;
              *((_QWORD *)this + 48) = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  366,
                  &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                  v17);
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xDC9,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)v17,
                v61);
              v19 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                goto LABEL_189;
              v34 = 367;
              goto LABEL_76;
            }
          }
          else
          {
            v17 = (unsigned int)Size;
          }
          *((_QWORD *)this + 202) = GetTickCount64();
          CWNPNet::OnServerUBD(this, v47, v48);
          break;
        case 0x20444E42u:
          if ( !*((_BYTE *)this + 1580) )
          {
            v41 = (void *)*((_QWORD *)this + 61);
            *((_DWORD *)this + 76) = 0;
            if ( v41 )
            {
              operator delete(v41, (const struct std::nothrow_t *)0x20444255);
              *((_QWORD *)this + 61) = 0;
            }
            if ( !v12 )
              goto LABEL_80;
            v42 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
            *((_QWORD *)this + 61) = v42;
            v17 = -2147024882;
            if ( !v42
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                360,
                &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                2147942414LL);
            }
            v43 = (void *)*((_QWORD *)this + 61);
            if ( !v43 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xD85,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)0x8007000ELL,
                v61);
              v19 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                goto LABEL_189;
              v34 = 361;
              v35 = 2147942414LL;
              goto LABEL_77;
            }
            memcpy_0(v43, v13, v12);
            v44 = ULongLongToULong(v12, (unsigned int *)this + 124);
            v17 = v44;
            if ( v44 >= 0 )
            {
LABEL_143:
              if ( (unsigned __int8)CWNPNet::IsStateMachineState(this, 3)
                && *((_DWORD *)this + 74) == (_DWORD)v23
                && *((_DWORD *)this + 75) == (_DWORD)v23
                && *((_DWORD *)this + 76) == (_DWORD)v23 )
              {
                if ( *((_BYTE *)this + 1599) == (_BYTE)v23 )
                  MicrosoftTelemetryAssertTriggeredNoArgs(v49);
                *((_BYTE *)this + 1599) = (_BYTE)v23;
                Size = v23;
                if ( !(unsigned __int8)CWNPNet::ChangeStateMachineState(this, 7) )
                  MicrosoftTelemetryAssertTriggeredNoArgs(v50);
                *((_BYTE *)this + 416) = 1;
                *((_QWORD *)this + 59) = GetTickCount64();
                TickCount64 = GetTickCount64();
                *((_BYTE *)this + 520) = (_BYTE)v23;
                *((_QWORD *)this + 202) = TickCount64;
                *((_QWORD *)this + 63) = v23;
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                  (char *)this + 1560,
                  0);
                *((_DWORD *)this + 92) = 1;
                CWNPNet::LogWnpConnectEnd(this, 0);
                if ( CWNPNet::GetEvents(this, &Size) )
                {
                  v52 = *((_QWORD *)this + 47);
                  v53 = (size_t)Size;
                  if ( v52 || *((_DWORD *)this + 96) != (_DWORD)v23 )
                  {
                    CWNPNet::UpdateBindingStatus(this, v52, 2);
                    (*(void (__fastcall **)(size_t, _QWORD, _QWORD))(*(_QWORD *)v53 + 56LL))(
                      v53,
                      *((_QWORD *)this + 47),
                      0);
                  }
                  LODWORD(Size) = (_DWORD)v23;
                  NetworkInterfaceType = CWNPNet::GetNetworkInterfaceType(
                                           this,
                                           (enum __MIDL___MIDL_itf_wpnconn_0000_0000_0001 *)&Size);
                  if ( NetworkInterfaceType < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0xE3A,
                      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                      (const char *)(unsigned int)NetworkInterfaceType,
                      v61);
                  (*(void (__fastcall **)(size_t, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v53 + 24LL))(
                    v53,
                    0,
                    *((unsigned int *)this + 124),
                    *((_QWORD *)this + 61),
                    (_DWORD)Size,
                    (_DWORD)v23);
                }
                *((_QWORD *)this + 47) = v23;
                *((_QWORD *)this + 48) = 0;
                User = CWNPNet::BindNextUser(this);
                v17 = User;
                if ( User < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    373,
                    &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                    (unsigned int)User);
                }
              }
              else if ( !(unsigned __int8)CWNPNet::IsStateMachineState(this, 3)
                     && *((_DWORD *)this + 74) == (_DWORD)v23
                     && *((_DWORD *)this + 75) == (_DWORD)v23
                     && *((_DWORD *)this + 76) == (_DWORD)v23 )
              {
                if ( *((_BYTE *)this + 1599) != (_BYTE)v23 )
                  CWNPNet::LogWnpConnectEnd(this, -2147177302);
                *((_BYTE *)this + 1599) = (_BYTE)v23;
              }
LABEL_185:
              v25 = RequestByTrID;
LABEL_186:
              if ( CWNPRequestQueue::FindOrRemoveRequest(v63, v25, v28) )
                CWNPRequest::`scalar deleting destructor'(v25, v59);
              goto LABEL_188;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                362,
                &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                (unsigned int)v44);
            }
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xD8A,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
              (const char *)v17,
              v61);
            v19 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
              goto LABEL_189;
            v34 = 363;
LABEL_76:
            v35 = v17;
LABEL_77:
            WPP_SF_d(v19[2], v34, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, v35);
LABEL_188:
            v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_189:
            v16 = 1;
            goto LABEL_190;
          }
          if ( v12 )
          {
            v17 = CWNPNet::SkipMimeHeaders(v12, v13, (unsigned __int64 *)&v68, (unsigned __int8 **)&Size);
            if ( (v17 & 0x80000000) != 0 )
            {
              Size = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void DeleteWakeTimer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                (char *)this + 1568,
                0);
              *((_BYTE *)this + 1580) = 0;
              if ( CWNPNet::GetEvents(this, &Size) )
                (*(void (__fastcall **)(struct IWNPNetEvents *, _QWORD, _QWORD))(*(_QWORD *)Size + 56LL))(
                  Size,
                  *((_QWORD *)this + 47),
                  v17);
              CWNPNet::UpdateBindingStatus(this, *((_QWORD *)this + 47), 3);
              *((_QWORD *)this + 47) = 0;
              *((_QWORD *)this + 48) = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  364,
                  &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                  v17);
              }
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xDA5,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                (const char *)v17,
                v61);
              v19 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                goto LABEL_189;
              v34 = 365;
              goto LABEL_76;
            }
          }
          else
          {
            v17 = (unsigned int)Size;
          }
          *((_QWORD *)this + 202) = GetTickCount64();
          CWNPNet::OnServerBND(this, v45, v46);
          break;
        case 0x20474E50u:
          if ( *((_DWORD *)RequestByTrID + 1) == 541544016 )
          {
            v68 = 0;
            v62 = 0;
            if ( v12 )
            {
              v37 = CWNPNet::SkipMimeHeaders(v12, v13, (unsigned __int64 *)&v68, &v62);
              v17 = v37;
              if ( v37 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    368,
                    &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                    (unsigned int)v37);
                }
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xDE0,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                  (const char *)v17,
                  v61);
                v19 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                  goto LABEL_189;
                v34 = 369;
                goto LABEL_76;
              }
              v23 = v68;
            }
            else
            {
              v17 = (unsigned int)Size;
            }
            v38 = GetTickCount64();
            v39 = v62;
            *((_QWORD *)this + 202) = v38;
            CWNPNet::OnServerPNG(this, (unsigned __int64)v23, v39);
            v40 = a8;
            v23 = 0;
            *((_DWORD *)a8 + 1) = 100;
LABEL_142:
            *(_DWORD *)v40 = (_DWORD)v23;
            goto LABEL_143;
          }
LABEL_80:
          v17 = (unsigned int)Size;
          goto LABEL_143;
        default:
          if ( v66 != 541544268 )
          {
            if ( v66 != 541611073 )
            {
              if ( v66 != 542395971 )
              {
                v17 = -2147418113;
                v30 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_sc(*((_QWORD *)WPP_GLOBAL_Control + 2), 372, v21, (unsigned int)&v66, *((_BYTE *)this + 1597));
                }
                MicrosoftTelemetryAssertTriggeredNoArgs(v30);
                v31 = a8;
                v23 = 0;
                *(_DWORD *)a8 = 0;
                *((_DWORD *)v31 + 1) = 100;
                goto LABEL_143;
              }
              *((_DWORD *)this + 74) = 0;
              v23 = (struct IWNPNetEvents *)*((_QWORD *)this + 57);
              if ( v23 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v23);
                v23 = 0;
                *((_QWORD *)this + 57) = 0;
              }
              v33 = CWNPNet::ParseCntResponsePayload(v13, v12, 0, (char **)this + 57, (unsigned int *)this + 116);
              v17 = v33;
              if ( v33 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    356,
                    &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
                    (unsigned int)v33);
                }
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xD5E,
                  (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
                  (const char *)v17,
                  v61);
                v19 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
                  goto LABEL_189;
                v34 = 357;
                goto LABEL_76;
              }
              *((_QWORD *)this + 202) = GetTickCount64();
              break;
            }
            v36 = a8;
            v23 = 0;
            *((_DWORD *)this + 75) = 0;
            *(_DWORD *)v36 = 0;
            *((_DWORD *)v36 + 1) = 2000;
          }
          goto LABEL_80;
      }
      v40 = a8;
      *((_DWORD *)a8 + 1) = 2000;
      goto LABEL_142;
    }
    v68 = 0;
    LODWORD(Size) = 0;
    if ( CWNPNet::GetErrorCodeFromVerb(v20, v66, (int *)&Size) )
    {
      v56 = (int)Size;
      *((_DWORD *)this + 77) = (_DWORD)Size;
    }
    else
    {
      v56 = 0;
    }
    if ( CWNPNet::GetEvents(this, &v68) )
    {
      LODWORD(Size) = 0;
      v57 = ULongLongToULong(v12, (unsigned int *)&Size);
      v17 = v57;
      if ( v57 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            374,
            &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids,
            (unsigned int)v57);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE7B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
          (const char *)v17,
          v61);
        v19 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_189;
        v34 = 375;
        goto LABEL_76;
      }
      (*(void (__fastcall **)(struct IWNPNetEvents *, BOOL, const char *, _QWORD, _DWORD, unsigned __int8 *))(*(_QWORD *)v68 + 80LL))(
        v68,
        v67,
        a4,
        (unsigned int)v56,
        (_DWORD)Size,
        v13);
    }
    v17 = v56;
    if ( v56 >= 0 )
    {
      v58 = a8;
      *(_DWORD *)a8 = 0;
      *((_DWORD *)v58 + 1) = 100;
    }
    goto LABEL_185;
  }
  v16 = 0;
  v17 = -2013002772;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v61 = -2013002772;
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 349, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
  }
  LOBYTE(v14) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout>::GetImpl'::`2'::impl,
    v14);
  v18 = a8;
  *(_DWORD *)a8 = 0;
  *((_DWORD *)v18 + 1) = 100;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xD00,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpnet.cpp",
    (const char *)0x880403ECLL,
    v61);
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 350, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, 2281964524LL);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_190:
  *a7 = v17;
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 && *((_BYTE *)v19 + 25) >= 6u )
    WPP_SF_(v19[2], 376, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
  return v16;
}

```

## disassembly

```asm
0x18003fb38  mov     [rsp-40h+arg_10], r8d
0x18003fb3d  mov     [rsp-40h+arg_8], edx
0x18003fb41  push    rbp
0x18003fb42  push    rbx
0x18003fb43  push    rsi
0x18003fb44  push    rdi
0x18003fb45  push    r12
0x18003fb47  push    r13
0x18003fb49  push    r14
0x18003fb4b  push    r15
0x18003fb4d  mov     rbp, rsp
0x18003fb50  sub     rsp, 58h
0x18003fb54  mov     r12, r9
0x18003fb57  mov     edi, r8d
0x18003fb5a  mov     rbx, rcx
0x18003fb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb64  lea     rax, WPP_GLOBAL_Control
0x18003fb6b  mov     r14b, 4
0x18003fb6e  cmp     rcx, rax
0x18003fb71  jz      short loc_18003FBA2
0x18003fb73  test    [rcx+1Ch], r14b
0x18003fb77  jz      short loc_18003FBA2
0x18003fb79  cmp     byte ptr [rcx+19h], 6
0x18003fb7d  jb      short loc_18003FBA2
0x18003fb7f  mov     al, [rbx+63Dh]
0x18003fb85  mov     r9d, [rbx+0D0h]
0x18003fb8c  mov     rcx, [rcx+10h]
0x18003fb90  mov     [rsp+58h+var_28], al
0x18003fb94  mov     dword ptr [rsp+58h+var_30], r8d
0x18003fb99  mov     dword ptr [rsp+58h+var_38], edx; int
0x18003fb9d  call    WPP_SF_Lddc
0x18003fba2  test    r12, r12
0x18003fba5  jz      short loc_18003FBAE
0x18003fba7  cmp     byte ptr [r12], 0
0x18003fbac  jnz     short loc_18003FBB3
0x18003fbae  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003fbb3  mov     r15, [rbp+Size]
0x18003fbb7  mov     r13, [rbp+Src]
0x18003fbbb  test    r15, r15
0x18003fbbe  jz      short loc_18003FBC7
0x18003fbc0  test    r13, r13
0x18003fbc3  jnz     short loc_18003FBD1
0x18003fbc5  jmp     short loc_18003FBCC
0x18003fbc7  test    r13, r13
0x18003fbca  jz      short loc_18003FBD1
0x18003fbcc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003fbd1  cmp     [rbp+arg_30], 0
0x18003fbd6  jnz     short loc_18003FBDD
0x18003fbd8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003fbdd  lea     rax, [rbx+0D8h]
0x18003fbe4  mov     dword ptr [rbp+Size], 0
0x18003fbeb  mov     rcx, rax; this
0x18003fbee  mov     [rbp+var_10], rax
0x18003fbf2  mov     edx, edi; unsigned int
0x18003fbf4  call    ?FindRequestByTrID@CWNPRequestQueue@@QEAAPEAVCWNPRequest@@K_N@Z; CWNPRequestQueue::FindRequestByTrID(ulong,bool)
0x18003fbf9  mov     [rbp+arg_0], rax
0x18003fbfd  mov     rdi, rax
0x18003fc00  test    rax, rax
0x18003fc03  jnz     loc_18003FCCA
0x18003fc09  xor     bl, bl
0x18003fc0b  mov     edi, 880403ECh
0x18003fc10  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc17  lea     r15, WPP_GLOBAL_Control
0x18003fc1e  lea     rsi, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x18003fc25  cmp     rcx, r15
0x18003fc28  jz      short loc_18003FC53
0x18003fc2a  test    [rcx+1Ch], r14b
0x18003fc2e  jz      short loc_18003FC53
0x18003fc30  lea     r14d, [rax+2]
0x18003fc34  cmp     [rcx+19h], r14b
0x18003fc38  jb      short loc_18003FC53
0x18003fc3a  mov     r9d, [rbp+arg_10]
0x18003fc3e  mov     edx, 15Dh
0x18003fc43  mov     rcx, [rcx+10h]
0x18003fc47  mov     r8, rsi
0x18003fc4a  mov     dword ptr [rsp+58h+var_38], edi; int
0x18003fc4e  call    WPP_SF_Dd
0x18003fc53  mov     dl, 1
0x18003fc55  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout>::GetImpl(void)'::`2'::impl
0x18003fc5c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WNS_PDCTimeout>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003fc61  mov     rax, [rbp+arg_38]
0x18003fc68  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003fc6f  mov     rcx, [rbp+40h]; this
0x18003fc73  mov     r9d, edi; char *
0x18003fc76  mov     edx, 0D00h; void *
0x18003fc7b  mov     dword ptr [rax], 0
0x18003fc81  mov     dword ptr [rax+4], 64h ; 'd'
0x18003fc88  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003fc8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc94  cmp     rcx, r15
0x18003fc97  jz      loc_18004086C
0x18003fc9d  test    byte ptr [rcx+1Ch], 80h
0x18003fca1  jz      loc_18004086C
0x18003fca7  mov     rcx, [rcx+10h]
0x18003fcab  mov     edx, 15Eh
0x18003fcb0  mov     r9d, 880403ECh
0x18003fcb6  mov     r8, rsi
0x18003fcb9  call    WPP_SF_d
0x18003fcbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fcc5  jmp     loc_18004086C
0x18003fcca  mov     rdx, r12; char *
0x18003fccd  call    ?IsInCONNamespace@CWNPNet@@IEAA_NPEBD@Z; CWNPNet::IsInCONNamespace(char const *)
0x18003fcd2  mov     edx, [rbp+arg_8]; unsigned int
0x18003fcd5  lea     rsi, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x18003fcdc  lea     r8, [rbp+Size]; int *
0x18003fce0  test    al, al
0x18003fce2  jz      loc_18004073D
0x18003fce8  call    ?GetErrorCodeFromVerb@CWNPNet@@IEAA_NKPEAJ@Z; CWNPNet::GetErrorCodeFromVerb(ulong,long *)
0x18003fced  xor     r12d, r12d
0x18003fcf0  test    al, al
0x18003fcf2  jz      loc_18003FECD
0x18003fcf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fcff  lea     r8, WPP_GLOBAL_Control
0x18003fd06  mov     edi, dword ptr [rbp+Size]
0x18003fd09  cmp     rcx, r8
0x18003fd0c  jz      short loc_18003FD46
0x18003fd0e  test    [rcx+1Ch], r14b
0x18003fd12  jz      short loc_18003FD46
0x18003fd14  cmp     byte ptr [rcx+19h], 5
0x18003fd18  jb      short loc_18003FD46
0x18003fd1a  mov     al, [rbx+63Dh]
0x18003fd20  mov     edx, 15Fh
0x18003fd25  mov     rcx, [rcx+10h]
0x18003fd29  mov     r9d, edi
0x18003fd2c  mov     r8, rsi
0x18003fd2f  mov     byte ptr [rsp+58h+var_38], al
0x18003fd33  call    WPP_SF_dc
0x18003fd38  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fd3f  lea     r8, WPP_GLOBAL_Control
0x18003fd46  mov     r15, [rbp+arg_0]
0x18003fd4a  mov     edx, 20444255h
0x18003fd4f  mov     eax, [r15+4]
0x18003fd53  cmp     eax, edx
0x18003fd55  jz      loc_18003FE8B
0x18003fd5b  mov     r12d, 20485441h
0x18003fd61  cmp     eax, 20444E42h
0x18003fd66  jz      loc_18003FE33
0x18003fd6c  cmp     eax, r12d
0x18003fd6f  jz      loc_18003FE33
0x18003fd75  cmp     eax, 20544E43h
0x18003fd7a  jz      short loc_18003FDEB
0x18003fd7c  mov     edi, 8000FFFFh
0x18003fd81  cmp     rcx, r8
0x18003fd84  jz      short loc_18003FDB0
0x18003fd86  test    [rcx+1Ch], r14b
0x18003fd8a  jz      short loc_18003FDB0
0x18003fd8c  cmp     byte ptr [rcx+19h], 5
0x18003fd90  jb      short loc_18003FDB0
0x18003fd92  mov     al, [rbx+63Dh]
0x18003fd98  mov     edx, 163h
0x18003fd9d  mov     rcx, [rcx+10h]
0x18003fda1  mov     r9d, edi
0x18003fda4  mov     r8, rsi
0x18003fda7  mov     byte ptr [rsp+58h+var_38], al
0x18003fdab  call    WPP_SF_dc
0x18003fdb0  mov     r14d, 6
0x18003fdb6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003fdbb  xor     r12d, r12d
0x18003fdbe  mov     edx, edi; int
0x18003fdc0  mov     rcx, rbx; this
0x18003fdc3  call    ?LogWnpConnectEnd@CWNPNet@@AEAAXJ@Z; CWNPNet::LogWnpConnectEnd(long)
0x18003fdc8  mov     r8d, r14d
0x18003fdcb  mov     edx, edi
0x18003fdcd  mov     rcx, rbx
0x18003fdd0  call    ?DisconnectInternal@CWNPNet@@IEAAJJW4_WNP_CP_DISCONNECT_REASON@@@Z; CWNPNet::DisconnectInternal(long,_WNP_CP_DISCONNECT_REASON)
0x18003fdd5  mov     rax, [rbp+arg_38]
0x18003fddc  mov     [rax], r12d
0x18003fddf  mov     dword ptr [rax+4], 64h ; 'd'
0x18003fde6  jmp     loc_18004084B
0x18003fdeb  mov     r12d, 8804038Dh
0x18003fdf1  mov     r14d, 2
0x18003fdf7  cmp     edi, r12d
0x18003fdfa  jnz     short loc_18003FDBB
0x18003fdfc  cmp     rcx, r8
0x18003fdff  jz      short loc_18003FE25
0x18003fe01  test    byte ptr [rcx+1Ch], 4
0x18003fe05  jz      short loc_18003FE25
0x18003fe07  cmp     byte ptr [rcx+19h], 5
0x18003fe0b  jb      short loc_18003FE25
0x18003fe0d  mov     r9b, [rbx+63Dh]
0x18003fe14  mov     edx, 160h
0x18003fe19  mov     rcx, [rcx+10h]
0x18003fe1d  mov     r8, rsi
0x18003fe20  call    WPP_SF_c
0x18003fe25  mov     rcx, rbx; this
0x18003fe28  call    ?ClearFastReconnectInfo@CWNPNet@@IEAAXXZ; CWNPNet::ClearFastReconnectInfo(void)
0x18003fe2d  mov     [rbx+48h], r12d
0x18003fe31  jmp     short loc_18003FDBB
0x18003fe33  mov     dword ptr [rbp+Size], eax
0x18003fe36  cmp     rcx, r8
0x18003fe39  jz      short loc_18003FE6D
0x18003fe3b  test    [rcx+1Ch], r14b
0x18003fe3f  jz      short loc_18003FE6D
0x18003fe41  cmp     byte ptr [rcx+19h], 5
0x18003fe45  jb      short loc_18003FE6D
0x18003fe47  mov     al, [rbx+63Dh]
0x18003fe4d  lea     r9, [rbp+Size]
0x18003fe51  mov     rcx, [rcx+10h]
0x18003fe55  mov     edx, 161h
0x18003fe5a  mov     byte ptr [rsp+58h+var_30], al
0x18003fe5e  mov     r8, rsi
0x18003fe61  mov     dword ptr [rsp+58h+var_38], edi
0x18003fe65  call    WPP_SF_sdc
0x18003fe6a  mov     eax, dword ptr [rbp+Size]
0x18003fe6d  xor     r14d, r14d
0x18003fe70  mov     rcx, rbx; this
0x18003fe73  cmp     eax, r12d
0x18003fe76  setnz   r14b
0x18003fe7a  add     r14d, 3
0x18003fe7e  call    ?ClearFastReconnectInfo@CWNPNet@@IEAAXXZ; CWNPNet::ClearFastReconnectInfo(void)
0x18003fe83  mov     [rbx+48h], edi
0x18003fe86  jmp     loc_18003FDBB
0x18003fe8b  mov     dword ptr [rbp+Size], edx
0x18003fe8e  cmp     rcx, r8
0x18003fe91  jz      short loc_18003FEC2
0x18003fe93  test    [rcx+1Ch], r14b
0x18003fe97  jz      short loc_18003FEC2
0x18003fe99  cmp     byte ptr [rcx+19h], 5
0x18003fe9d  jb      short loc_18003FEC2
0x18003fe9f  mov     al, [rbx+63Dh]
0x18003fea5  lea     r9, [rbp+Size]
0x18003fea9  mov     rcx, [rcx+10h]
0x18003fead  mov     edx, 162h
0x18003feb2  mov     byte ptr [rsp+58h+var_30], al
0x18003feb6  mov     r8, rsi
0x18003feb9  mov     dword ptr [rsp+58h+var_38], edi
0x18003febd  call    WPP_SF_sdc
0x18003fec2  mov     r14d, 5
0x18003fec8  jmp     loc_18003FDBE
0x18003fecd  mov     eax, [rbp+arg_8]
0x18003fed0  mov     edx, 20444255h; struct std::nothrow_t *
0x18003fed5  mov     r14d, 2
0x18003fedb  cmp     eax, edx
0x18003fedd  jz      loc_1800403FD
0x18003fee3  cmp     eax, 20444E42h
0x18003fee8  jz      loc_18004016E
0x18003feee  mov     ecx, 20474E50h
0x18003fef3  cmp     eax, ecx
0x18003fef5  jz      loc_18004008E
0x18003fefb  cmp     eax, 20474F4Ch
0x18003ff00  jz      loc_180040086
0x18003ff06  mov     r12d, 20485441h
0x18003ff0c  cmp     eax, r12d
0x18003ff0f  jz      loc_18004006B
0x18003ff15  cmp     eax, 20544E43h
0x18003ff1a  jz      short loc_18003FF7A
0x18003ff1c  mov     edi, 8000FFFFh
0x18003ff21  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff28  lea     r15, WPP_GLOBAL_Control
0x18003ff2f  cmp     rcx, r15
0x18003ff32  jz      short loc_18003FF5C
0x18003ff34  test    byte ptr [rcx+1Ch], 4
0x18003ff38  jz      short loc_18003FF5C
0x18003ff3a  cmp     byte ptr [rcx+19h], 5
0x18003ff3e  jb      short loc_18003FF5C
0x18003ff40  mov     al, [rbx+63Dh]
0x18003ff46  lea     r9, [rbp+arg_8]
0x18003ff4a  mov     rcx, [rcx+10h]
0x18003ff4e  mov     edx, 174h
0x18003ff53  mov     byte ptr [rsp+58h+var_38], al
0x18003ff57  call    WPP_SF_sc
0x18003ff5c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003ff61  mov     rax, [rbp+arg_38]
0x18003ff68  xor     r12d, r12d
0x18003ff6b  mov     [rax], r12d
0x18003ff6e  mov     dword ptr [rax+4], 64h ; 'd'
0x18003ff75  jmp     loc_18004051A
0x18003ff7a  lea     rdi, [rbx+1C8h]
0x18003ff81  mov     dword ptr [rbx+128h], 0
0x18003ff8b  mov     r12, [rdi]
0x18003ff8e  test    r12, r12
0x18003ff91  jz      short loc_18003FFAD
0x18003ff93  call    cs:__imp_GetProcessHeap
0x18003ff99  mov     r8, r12; lpMem
0x18003ff9c  xor     edx, edx; dwFlags
0x18003ff9e  mov     rcx, rax; hHeap
0x18003ffa1  call    cs:__imp_HeapFree
0x18003ffa7  xor     r12d, r12d
0x18003ffaa  mov     [rdi], r12
0x18003ffad  lea     rax, [rbx+1D0h]
0x18003ffb4  mov     r9, rdi; char **
0x18003ffb7  xor     r8d, r8d; int
0x18003ffba  mov     [rsp+58h+var_38], rax; int
0x18003ffbf  mov     rdx, r15; unsigned __int64
0x18003ffc2  mov     rcx, r13; unsigned __int8 *
0x18003ffc5  call    ?ParseCntResponsePayload@CWNPNet@@KAJPEAE_KHPEAPEADPEAK@Z; CWNPNet::ParseCntResponsePayload(uchar *,unsigned __int64,int,char * *,ulong *)
0x18003ffca  mov     edi, eax
0x18003ffcc  test    eax, eax
0x18003ffce  jns     loc_180040059
0x18003ffd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ffdb  lea     rbx, WPP_GLOBAL_Control
0x18003ffe2  lea     rsi, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x18003ffe9  cmp     rcx, rbx
0x18003ffec  jz      short loc_18004000E
0x18003ffee  test    byte ptr [rcx+1Ch], 4
0x18003fff2  jz      short loc_18004000E
0x18003fff4  cmp     [rcx+19h], r14b
0x18003fff8  jb      short loc_18004000E
0x18003fffa  mov     rcx, [rcx+10h]
0x18003fffe  mov     edx, 164h
  ... truncated ...
```
