# CWnpConnector::ConnectEx(char const *,ushort,int,ulong,ulong,ulong,bool)

- ea: `0x180051e60`
- end: `0x1800527d6`
- name: `?ConnectEx@CWnpConnector@@QEAAJPEBDGHKKK_N@Z`
- size: `2422`
- prototype: `__int64 __fastcall(CWnpConnector *this, const char *, __int16, int, unsigned int, unsigned int, unsigned int, char)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180064168`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001ca78`
- `0x18002f808`
- `0x18002fc80`
- `0x180039c24`
- `0x180050f9c`
- `0x180051298`
- `0x18005133c`
- `0x180051434`
- `0x1800514ec`
- `0x180051760`
- `0x180051e60`
- `0x1800527dc`
- `0x180052c8c`
- `0x180054348`
- `0x180056378`
- `0x180059d24`
- `0x18005fa10`
- `0x180060260`
- `0x180096010`

## import_xrefs

- `SspiCli!InitSecurityInterfaceW` at `0x18005219b`
- `SspiCli!InitSecurityInterfaceW` at `0x18005219b`

## pseudocode

```c
__int64 __fastcall CWnpConnector::ConnectEx(
        CWnpConnector *this,
        const char *a2,
        __int16 a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        char a8)
{
  PVOID *v12; // r8
  char v13; // r14
  unsigned int v14; // r13d
  unsigned int v15; // r12d
  unsigned int v16; // r15d
  int v17; // eax
  unsigned int v18; // edi
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int IpInterfaceAddressFamily; // eax
  PVOID *v22; // rcx
  int v23; // eax
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // r9
  int v27; // ecx
  __int64 v28; // rcx
  const wchar_t *v29; // rdx
  int v30; // eax
  PVOID v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  int v34; // eax
  struct CIEProxyFromWinHttp *v35; // rax
  int v36; // eax
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  struct addrinfoexW *v39; // rdx
  int v40; // eax
  PVOID v41; // rcx
  int v42; // eax
  PVOID v43; // rcx
  struct CIEProxyFromWinHttp *Instance; // rax
  int v45; // eax
  int v47; // [rsp+20h] [rbp-98h]
  unsigned __int16 v48[44]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  unsigned __int16 v50; // [rsp+C0h] [rbp+8h] BYREF

  v12 = (PVOID *)WPP_GLOBAL_Control;
  v13 = a8;
  v14 = a7;
  v15 = a6;
  v16 = a5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_dsdcdddc(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)WPP_GLOBAL_Control,
        *((_DWORD *)this + 16),
        (__int64)a2,
        a3,
        a4 != 0,
        a5,
        a6,
        a7,
        a8);
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 5u )
    {
      v47 = *((_DWORD *)this + 22);
      WPP_SF_LLcL(v12[2]);
    }
  }
  if ( *((_DWORD *)this + 22) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v50 = 0;
  v48[0] = 0;
  v17 = WpnStrCpyA(a2, (char **)this + 12);
  v18 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
        (unsigned int)v17);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
      (const char *)v18,
      v47);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_156;
    v20 = 32;
    goto LABEL_154;
  }
  *((_BYTE *)this + 120) = v13;
  *((_WORD *)this + 52) = a3;
  *((_DWORD *)this + 54) = a4;
  if ( !v16 )
    goto LABEL_25;
  IpInterfaceAddressFamily = GetIpInterfaceAddressFamily(v16, &v50);
  if ( IpInterfaceAddressFamily >= 0 )
    goto LABEL_25;
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
      (unsigned int)IpInterfaceAddressFamily);
LABEL_25:
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v15 )
    goto LABEL_33;
  v23 = GetIpInterfaceAddressFamily(v15, v48);
  if ( v23 >= 0 )
    goto LABEL_32;
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
      (unsigned int)v23);
LABEL_32:
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_33:
  if ( v14 )
  {
    v24 = GetIpInterfaceAddressFamily(v15, v48);
    if ( v24 < 0 )
    {
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_40;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
        (unsigned int)v24);
    }
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_40:
  if ( *((_DWORD *)this + 31) != v16 || v16 && *((_WORD *)this + 64) != v50 || (*((_BYTE *)this + 108) & 0x10) != 0 )
  {
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 4) != 0 && *((_BYTE *)v22 + 25) >= 5u )
      WPP_SF_(v22[2], 36, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
    *((_DWORD *)this + 54) = 0;
  }
  *((_WORD *)this + 64) = v50;
  *((_WORD *)this + 68) = v48[0];
  *((_DWORD *)this + 31) = v16;
  *((_DWORD *)this + 33) = v15;
  *((_DWORD *)this + 35) = v14;
  *((_WORD *)this + 72) = 0;
  if ( !*((_DWORD *)this + 54) )
    CWnpConnector::ClearCachedConnectionInfo(this);
  if ( !CWnpConnector::s_pSSPI )
  {
    CWnpConnector::s_pSSPI = InitSecurityInterfaceW();
    if ( !CWnpConnector::s_pSSPI )
    {
      v18 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
          2147549183LL);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x209,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)0x8000FFFFLL,
        v47);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_156;
      v20 = 38;
      v25 = 2147549183LL;
      goto LABEL_155;
    }
  }
  if ( !CMsgrWndBase::IsMsgrWindow(this) )
  {
    v27 = *((_DWORD *)this + 16);
    if ( v27 )
    {
      v28 = (unsigned int)(v27 - 1);
      if ( (_DWORD)v28 )
      {
        if ( (_DWORD)v28 == 1 )
        {
          v29 = L"WnpConnectorId3";
        }
        else
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v28);
          v29 = L"MSNUnnamedWindow";
        }
      }
      else
      {
        v29 = L"WnpConnectorId2";
      }
    }
    else
    {
      v29 = L"WnpConnectorId1";
    }
    v30 = (*(__int64 (__fastcall **)(CWnpConnector *, const wchar_t *, __int64))(*(_QWORD *)this + 8LL))(this, v29, -3);
    v18 = v30;
    if ( v30 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
          (unsigned int)v30);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)v18,
        v47);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_156;
      v20 = 40;
      goto LABEL_154;
    }
  }
  if ( !*((_DWORD *)this + 54) || !*((_QWORD *)this + 28) )
  {
    v40 = *((_DWORD *)this + 27);
    if ( (v40 & 1) != 0 )
    {
      v41 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LOBYTE(v26) = (v40 & 8) != 0;
        WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v26);
      }
      if ( (*((_BYTE *)this + 108) & 2) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v41);
      *((_DWORD *)this + 102) = 2;
      CWnpConnector::ClearDnsLookupRetry(this, 1);
      CWnpConnector::ClearDirectConnectRetry(this, 1);
      v42 = CWnpConnector::ConnectDirect(this);
      v18 = v42;
      if ( v42 >= 0 )
        goto LABEL_157;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
          (unsigned int)v42);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x26B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)v18,
        v47);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_156;
      v20 = 50;
    }
    else
    {
      if ( (v40 & 2) == 0 )
        goto LABEL_157;
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LOBYTE(v26) = (v40 & 8) != 0;
        WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v26);
      }
      if ( (*((_BYTE *)this + 108) & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v43);
      *((_DWORD *)this + 102) = 3;
      if ( *((_QWORD *)this + 29) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v43);
      Instance = CIEProxyFromWinHttp::CreateInstance((*((_BYTE *)this + 108) & 8) != 0, *((HWND *)this + 3));
      *((_QWORD *)this + 29) = Instance;
      if ( !Instance )
      {
        v18 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x27D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
          (const char *)0x8007000ELL,
          v47);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_156;
        v20 = 53;
LABEL_98:
        v25 = 2147942414LL;
LABEL_155:
        WPP_SF_d(v19[2], v20, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v25);
LABEL_156:
        CWnpConnector::OnError(this, v18);
        goto LABEL_157;
      }
      CWnpConnector::ChangeConnectorState(this, 4);
      v45 = CWnpConnector::ConnectToProxy(this);
      v18 = v45;
      if ( v45 >= 0 )
        goto LABEL_157;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
          (unsigned int)v45);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x282,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)v18,
        v47);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_156;
      v20 = 55;
    }
LABEL_154:
    v25 = v18;
    goto LABEL_155;
  }
  v31 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids);
  }
  if ( *((_QWORD *)this + 10) != -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v31);
  if ( *((_DWORD *)this + 22) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v31);
  v32 = *((unsigned int *)this + 55);
  *((_QWORD *)this + 14) = *((_QWORD *)this + 28);
  CWnpConnector::ChangeConnectorState(this, v32);
  v34 = *((_DWORD *)this + 55);
  if ( v34 == 4 )
  {
    *((_DWORD *)this + 102) = 3;
    if ( *((_QWORD *)this + 29) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v33);
    v35 = CIEProxyFromWinHttp::CreateInstance((*((_BYTE *)this + 108) & 8) != 0, *((HWND *)this + 3));
    *((_QWORD *)this + 29) = v35;
    if ( !v35
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, 2147942414LL);
    }
    if ( !*((_QWORD *)this + 29) )
    {
      v18 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x247,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)0x8007000ELL,
        v47);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_156;
      v20 = 43;
      goto LABEL_98;
    }
    v36 = CWnpConnector::ConnectToProxy(this);
    v18 = v36;
    if ( v36 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_111;
      }
      v38 = 44;
LABEL_110:
      WPP_SF_d(v37[2], v38, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, (unsigned int)v36);
LABEL_111:
      CWnpConnector::AbortFastReconnect(this);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids, v18);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x259,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnector.cpp",
        (const char *)v18,
        v47);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_156;
      v20 = 47;
      goto LABEL_154;
    }
  }
  else if ( v34 == 3 )
  {
    v39 = (struct addrinfoexW *)*((_QWORD *)this + 14);
    *((_DWORD *)this + 102) = 2;
    v36 = CWnpConnector::ConnectWithAddrInfo(this, v39, (unsigned __int64 *)this + 10);
    v18 = v36;
    if ( v36 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_111;
      }
      v38 = 45;
      goto LABEL_110;
    }
  }
LABEL_157:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(v47) = (*((_BYTE *)this + 108) & 8) != 0;
    WPP_SF_dcd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      &WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids,
      *((unsigned int *)this + 16),
      v47,
      v18);
  }
  return v18;
}

```

## disassembly

```asm
0x180051e60  mov     r11, rsp
0x180051e63  push    rbx
0x180051e64  push    rbp
0x180051e65  push    rsi
0x180051e66  push    rdi
0x180051e67  push    r12
0x180051e69  push    r13
0x180051e6b  push    r14
0x180051e6d  push    r15
0x180051e6f  sub     rsp, 78h
0x180051e73  mov     esi, r9d
0x180051e76  movzx   ebp, r8w
0x180051e7a  mov     rdi, rdx
0x180051e7d  mov     rbx, rcx
0x180051e80  mov     r8, cs:WPP_GLOBAL_Control
0x180051e87  lea     rax, WPP_GLOBAL_Control
0x180051e8e  mov     r14b, [rsp+0B8h+arg_38]
0x180051e96  mov     r13d, [rsp+0B8h+arg_30]
0x180051e9e  mov     r12d, [rsp+0B8h+arg_28]
0x180051ea6  mov     r15d, [rsp+0B8h+arg_20]
0x180051eae  cmp     r8, rax
0x180051eb1  jz      loc_180051F3F
0x180051eb7  test    byte ptr [r8+1Ch], 4
0x180051ebc  jz      short loc_180051F03
0x180051ebe  cmp     byte ptr [r8+19h], 6
0x180051ec3  jb      short loc_180051F03
0x180051ec5  mov     [r11-68h], r14b
0x180051ec9  test    r9d, r9d
0x180051ecc  mov     r9d, [rcx+40h]
0x180051ed0  mov     rcx, [r8+10h]
0x180051ed4  setnz   al
0x180051ed7  mov     [r11-70h], r13d
0x180051edb  mov     [r11-78h], r12d
0x180051edf  mov     [r11-80h], r15d
0x180051ee3  mov     byte ptr [rsp+0B8h+var_88], al
0x180051ee7  mov     [rsp+0B8h+var_90], ebp
0x180051eeb  mov     qword ptr [rsp+0B8h+var_98], rdx
0x180051ef0  call    WPP_SF_dsdcdddc
0x180051ef5  mov     r8, cs:WPP_GLOBAL_Control
0x180051efc  lea     rax, WPP_GLOBAL_Control
0x180051f03  cmp     r8, rax
0x180051f06  jz      short loc_180051F3F
0x180051f08  test    byte ptr [r8+1Ch], 4
0x180051f0d  jz      short loc_180051F3F
0x180051f0f  cmp     byte ptr [r8+19h], 5
0x180051f14  jb      short loc_180051F3F
0x180051f16  mov     eax, [rbx+0DCh]
0x180051f1c  mov     r9d, [rbx+6Ch]
0x180051f20  test    r9b, 8
0x180051f24  mov     [rsp+0B8h+var_88], eax
0x180051f28  mov     eax, [rbx+58h]
0x180051f2b  setnbe  cl
0x180051f2e  mov     byte ptr [rsp+0B8h+var_90], cl
0x180051f32  mov     rcx, [r8+10h]
0x180051f36  mov     [rsp+0B8h+var_98], eax; int
0x180051f3a  call    WPP_SF_LLcL
0x180051f3f  cmp     dword ptr [rbx+58h], 0
0x180051f43  jz      short loc_180051F4A
0x180051f45  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180051f4a  xor     eax, eax
0x180051f4c  lea     rdx, [rbx+60h]; char **
0x180051f50  mov     rcx, rdi; char *
0x180051f53  mov     [rsp+0B8h+arg_0], ax
0x180051f5b  mov     [rsp+0B8h+var_58], ax
0x180051f60  call    ?WpnStrCpyA@@YAJPEBDPEAPEAD@Z; WpnStrCpyA(char const *,char * *)
0x180051f65  mov     edi, eax
0x180051f67  test    eax, eax
0x180051f69  jns     short loc_180051FE8
0x180051f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180051f72  lea     r12, WPP_GLOBAL_Control
0x180051f79  lea     rsi, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x180051f80  cmp     rcx, r12
0x180051f83  jz      short loc_180051FA8
0x180051f85  test    byte ptr [rcx+1Ch], 4
0x180051f89  jz      short loc_180051FA8
0x180051f8b  mov     ebp, 2
0x180051f90  cmp     [rcx+19h], bpl
0x180051f94  jb      short loc_180051FA8
0x180051f96  mov     rcx, [rcx+10h]
0x180051f9a  lea     edx, [rbp+1Dh]
0x180051f9d  mov     r9d, eax
0x180051fa0  mov     r8, rsi
0x180051fa3  call    WPP_SF_d
0x180051fa8  mov     rcx, [rsp+0B8h]; this
0x180051fb0  lea     r8, aOnecoreuapBase_32; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180051fb7  mov     r9d, edi; char *
0x180051fba  mov     edx, 1D1h; void *
0x180051fbf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180051fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180051fcb  cmp     rcx, r12
0x180051fce  jz      loc_180052776
0x180051fd4  test    byte ptr [rcx+1Ch], 80h
0x180051fd8  jz      loc_180052776
0x180051fde  mov     edx, 20h ; ' '
0x180051fe3  jmp     loc_180052767
0x180051fe8  mov     [rbx+78h], r14b
0x180051fec  xor     r14d, r14d
0x180051fef  mov     [rbx+68h], bp
0x180051ff3  mov     ebp, 2
0x180051ff8  mov     [rbx+0D8h], esi
0x180051ffe  lea     rsi, WPP_c39f4e8e303a33f6949d0d5b27db82be_Traceguids
0x180052005  test    r15d, r15d
0x180052008  jz      short loc_18005204F
0x18005200a  lea     rdx, [rsp+0B8h+arg_0]; unsigned __int16 *
0x180052012  mov     ecx, r15d; unsigned int
0x180052015  call    ?GetIpInterfaceAddressFamily@@YAJKPEAG@Z; GetIpInterfaceAddressFamily(ulong,ushort *)
0x18005201a  test    eax, eax
0x18005201c  jns     short loc_18005204F
0x18005201e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052025  lea     rdx, WPP_GLOBAL_Control
0x18005202c  cmp     rcx, rdx
0x18005202f  jz      short loc_180052056
0x180052031  test    byte ptr [rcx+1Ch], 4
0x180052035  jz      short loc_180052056
0x180052037  cmp     [rcx+19h], bpl
0x18005203b  jb      short loc_180052056
0x18005203d  mov     rcx, [rcx+10h]
0x180052041  lea     edx, [rbp+1Fh]
0x180052044  mov     r9d, eax
0x180052047  mov     r8, rsi
0x18005204a  call    WPP_SF_d
0x18005204f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052056  test    r12d, r12d
0x180052059  jz      short loc_1800520A6
0x18005205b  lea     rdx, [rsp+0B8h+var_58]; unsigned __int16 *
0x180052060  mov     ecx, r12d; unsigned int
0x180052063  call    ?GetIpInterfaceAddressFamily@@YAJKPEAG@Z; GetIpInterfaceAddressFamily(ulong,ushort *)
0x180052068  test    eax, eax
0x18005206a  jns     short loc_18005209F
0x18005206c  mov     rcx, cs:WPP_GLOBAL_Control
0x180052073  lea     rdx, WPP_GLOBAL_Control
0x18005207a  cmp     rcx, rdx
0x18005207d  jz      short loc_1800520A6
0x18005207f  test    byte ptr [rcx+1Ch], 4
0x180052083  jz      short loc_1800520A6
0x180052085  cmp     [rcx+19h], bpl
0x180052089  jb      short loc_1800520A6
0x18005208b  mov     rcx, [rcx+10h]
0x18005208f  mov     edx, 22h ; '"'
0x180052094  mov     r9d, eax
0x180052097  mov     r8, rsi
0x18005209a  call    WPP_SF_d
0x18005209f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520a6  test    r13d, r13d
0x1800520a9  jz      short loc_1800520F6
0x1800520ab  lea     rdx, [rsp+0B8h+var_58]; unsigned __int16 *
0x1800520b0  mov     ecx, r12d; unsigned int
0x1800520b3  call    ?GetIpInterfaceAddressFamily@@YAJKPEAG@Z; GetIpInterfaceAddressFamily(ulong,ushort *)
0x1800520b8  test    eax, eax
0x1800520ba  jns     short loc_1800520EF
0x1800520bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520c3  lea     rdx, WPP_GLOBAL_Control
0x1800520ca  cmp     rcx, rdx
0x1800520cd  jz      short loc_1800520FD
0x1800520cf  test    byte ptr [rcx+1Ch], 4
0x1800520d3  jz      short loc_1800520FD
0x1800520d5  cmp     [rcx+19h], bpl
0x1800520d9  jb      short loc_1800520FD
0x1800520db  mov     rcx, [rcx+10h]
0x1800520df  mov     edx, 23h ; '#'
0x1800520e4  mov     r9d, eax
0x1800520e7  mov     r8, rsi
0x1800520ea  call    WPP_SF_d
0x1800520ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520f6  lea     rdx, WPP_GLOBAL_Control
0x1800520fd  cmp     [rbx+7Ch], r15d
0x180052101  jnz     short loc_18005211F
0x180052103  test    r15d, r15d
0x180052106  jz      short loc_180052119
0x180052108  movzx   eax, [rsp+0B8h+arg_0]
0x180052110  cmp     [rbx+80h], ax
0x180052117  jnz     short loc_18005211F
0x180052119  test    byte ptr [rbx+6Ch], 10h
0x18005211d  jz      short loc_180052148
0x18005211f  cmp     rcx, rdx
0x180052122  jz      short loc_180052141
0x180052124  test    byte ptr [rcx+1Ch], 4
0x180052128  jz      short loc_180052141
0x18005212a  cmp     byte ptr [rcx+19h], 5
0x18005212e  jb      short loc_180052141
0x180052130  mov     rcx, [rcx+10h]
0x180052134  mov     edx, 24h ; '$'
0x180052139  mov     r8, rsi
0x18005213c  call    WPP_SF_
0x180052141  mov     [rbx+0D8h], r14d
0x180052148  movzx   eax, [rsp+0B8h+arg_0]
0x180052150  mov     [rbx+80h], ax
0x180052157  movzx   eax, [rsp+0B8h+var_58]
0x18005215c  mov     [rbx+88h], ax
0x180052163  mov     [rbx+7Ch], r15d
0x180052167  mov     [rbx+84h], r12d
0x18005216e  mov     [rbx+8Ch], r13d
0x180052175  mov     [rbx+90h], r14w
0x18005217d  cmp     [rbx+0D8h], r14d
0x180052184  jnz     short loc_18005218E
0x180052186  mov     rcx, rbx; this
0x180052189  call    ?ClearCachedConnectionInfo@CWnpConnector@@AEAAXXZ; CWnpConnector::ClearCachedConnectionInfo(void)
0x18005218e  cmp     cs:?s_pSSPI@CWnpConnector@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA, r14; _SECURITY_FUNCTION_TABLE_W * CWnpConnector::s_pSSPI
0x180052195  jnz     loc_180052229
0x18005219b  call    cs:__imp_InitSecurityInterfaceW
0x1800521a1  mov     cs:?s_pSSPI@CWnpConnector@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * CWnpConnector::s_pSSPI
0x1800521a8  test    rax, rax
0x1800521ab  jnz     short loc_180052229
0x1800521ad  mov     edi, 8000FFFFh
0x1800521b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521b9  lea     r12, WPP_GLOBAL_Control
0x1800521c0  cmp     rcx, r12
0x1800521c3  jz      short loc_1800521E3
0x1800521c5  test    byte ptr [rcx+1Ch], 4
0x1800521c9  jz      short loc_1800521E3
0x1800521cb  cmp     [rcx+19h], bpl
0x1800521cf  jb      short loc_1800521E3
0x1800521d1  mov     rcx, [rcx+10h]
0x1800521d5  lea     edx, [rax+25h]
0x1800521d8  mov     r9d, edi
0x1800521db  mov     r8, rsi
0x1800521de  call    WPP_SF_d
0x1800521e3  mov     rcx, [rsp+0B8h]; this
0x1800521eb  lea     r8, aOnecoreuapBase_32; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800521f2  mov     r9d, edi; char *
0x1800521f5  mov     edx, 209h; void *
0x1800521fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800521ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180052206  cmp     rcx, r12
0x180052209  jz      loc_180052776
0x18005220f  test    byte ptr [rcx+1Ch], 80h
0x180052213  jz      loc_180052776
0x180052219  mov     edx, 26h ; '&'
0x18005221e  mov     r9d, 8000FFFFh
0x180052224  jmp     loc_18005276A
0x180052229  mov     rcx, rbx; this
0x18005222c  call    ?IsMsgrWindow@CMsgrWndBase@@IEAA_NXZ; CMsgrWndBase::IsMsgrWindow(void)
0x180052231  test    al, al
0x180052233  jnz     loc_180052300
0x180052239  mov     ecx, [rbx+40h]
0x18005223c  test    ecx, ecx
0x18005223e  jz      short loc_18005226A
0x180052240  sub     ecx, 1
0x180052243  jz      short loc_180052261
0x180052245  cmp     ecx, 1
0x180052248  jz      short loc_180052258
0x18005224a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005224f  lea     rdx, aMsnunnamedwind; "MSNUnnamedWindow"
0x180052256  jmp     short loc_180052271
0x180052258  lea     rdx, ?g_ConnectorId3WindowName@@3QBGB; "WnpConnectorId3"
0x18005225f  jmp     short loc_180052271
0x180052261  lea     rdx, ?g_ConnectorId2WindowName@@3QBGB; "WnpConnectorId2"
0x180052268  jmp     short loc_180052271
0x18005226a  lea     rdx, ?g_ConnectorId1WindowName@@3QBGB; "WnpConnectorId1"
0x180052271  mov     rax, [rbx]
0x180052274  mov     r8, 0FFFFFFFFFFFFFFFDh
0x18005227b  mov     rcx, rbx
0x18005227e  mov     rax, [rax+8]
0x180052282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052287  mov     edi, eax
0x180052289  test    eax, eax
0x18005228b  jns     short loc_180052300
0x18005228d  mov     rcx, cs:WPP_GLOBAL_Control
0x180052294  lea     r12, WPP_GLOBAL_Control
0x18005229b  cmp     rcx, r12
0x18005229e  jz      short loc_1800522C0
0x1800522a0  test    byte ptr [rcx+1Ch], 4
0x1800522a4  jz      short loc_1800522C0
0x1800522a6  cmp     [rcx+19h], bpl
0x1800522aa  jb      short loc_1800522C0
0x1800522ac  mov     rcx, [rcx+10h]
0x1800522b0  mov     edx, 27h ; '''
0x1800522b5  mov     r9d, eax
0x1800522b8  mov     r8, rsi
0x1800522bb  call    WPP_SF_d
0x1800522c0  mov     rcx, [rsp+0B8h]; this
0x1800522c8  lea     r8, aOnecoreuapBase_32; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800522cf  mov     r9d, edi; char *
0x1800522d2  mov     edx, 22Ch; void *
0x1800522d7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800522dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800522e3  cmp     rcx, r12
0x1800522e6  jz      loc_180052776
0x1800522ec  test    byte ptr [rcx+1Ch], 80h
0x1800522f0  jz      loc_180052776
0x1800522f6  mov     edx, 28h ; '('
0x1800522fb  jmp     loc_180052767
0x180052300  cmp     [rbx+0D8h], r14d
0x180052307  jz      loc_18005253F
0x18005230d  cmp     [rbx+0E0h], r14
0x180052314  jz      loc_18005253F
0x18005231a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052321  lea     r12, WPP_GLOBAL_Control
0x180052328  cmp     rcx, r12
0x18005232b  jz      short loc_18005234A
0x18005232d  test    byte ptr [rcx+1Ch], 4
0x180052331  jz      short loc_18005234A
0x180052333  cmp     byte ptr [rcx+19h], 4
0x180052337  jb      short loc_18005234A
0x180052339  mov     rcx, [rcx+10h]
0x18005233d  mov     edx, 29h ; ')'
0x180052342  mov     r8, rsi
0x180052345  call    WPP_SF_
0x18005234a  cmp     qword ptr [rbx+50h], 0FFFFFFFFFFFFFFFFh
0x18005234f  jz      short loc_180052356
  ... truncated ...
```
