# CService::ServiceControlHandler(ulong,ulong,void *,void *)

- ea: `0x1800031b0`
- end: `0x1800036dc`
- name: `?ServiceControlHandler@CService@@SAKKKPEAX0@Z`
- size: `1324`
- prototype: `__int64 __fastcall(DWORD dwControl, __int16 *dwEventType, struct _DEV_BROADCAST_DEVICEINTERFACE_W *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800031b0`
- `0x1800036f0`
- `0x1800038d0`
- `0x180003980`
- `0x180003cd0`
- `0x180003ed0`
- `0x180007f28`
- `0x1800089c4`
- `0x18000dfd4`
- `0x18000e1b8`
- `0x18000e260`
- `0x18000e360`
- `0x18000ea08`
- `0x18000ebc0`
- `0x18000ec84`
- `0x18000ecd8`
- `0x18000ed3c`
- `0x180011b04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800032d2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800032d2`

## pseudocode

```c
__int64 __fastcall CService::ServiceControlHandler(
        DWORD dwControl,
        __int16 *dwEventType,
        struct _DEV_BROADCAST_DEVICEINTERFACE_W *lpEventData,
        LPVOID lpContext)
{
  unsigned int v5; // r14d
  CBthActiveConnector *v7; // rcx
  unsigned int v8; // edi
  int v9; // r15d
  __int16 *v10; // kr00_8
  CPnPNotification *v11; // rcx
  unsigned int SystemTime; // eax
  unsigned int v13; // eax
  int v14; // eax
  int v15; // eax
  CGroupPolicy *v16; // rcx
  CPnPNotification *v17; // rcx
  __int64 v18; // rdx

  v5 = (unsigned int)dwEventType;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_DDid(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      dwEventType,
      lpEventData,
      dwControl,
      (_DWORD)dwEventType,
      qword_18001F2B0,
      g_RefCount);
  }
  _m_prefetchw(&qword_18001F2B0);
  if ( (_InterlockedOr64(&qword_18001F2B0, 1u) & 2) != 0 )
  {
    v8 = 1115;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v18 = 57;
LABEL_73:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, dwControl);
    }
  }
  else if ( dwControl == 4 )
  {
LABEL_12:
    v8 = 0;
  }
  else
  {
    v8 = 120;
    v10 = dwEventType;
    v9 = 0;
    dwEventType = &_ImageBase;
    switch ( dwControl )
    {
      case 1u:
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
        }
        _InterlockedOr64(&qword_18001F2B0, 2u);
        CService::ReportStatus((CService *)&_Service, 3, (__int64)lpEventData, 3, 0x2710u);
        if ( hEvent )
          SetEvent(hEvent);
        goto LABEL_12;
      case 5u:
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
        }
        CService::ReportStatus((CService *)&_Service, 3, (__int64)lpEventData, 4, 0x7D0u);
        CService::Shutdown((CService *)&_Service);
        v8 = 0;
        break;
      case 0xBu:
        if ( ((v5 - 0x8000) & 0xFFFFFFFB) != 0 )
          goto LABEL_65;
        if ( !lpEventData )
        {
          if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_qd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
              0,
              -2147418113);
          }
          break;
        }
        if ( !g_PnPNotification || lpEventData->dbcc_devicetype != 5 || !(unsigned int)IsPortableDeviceAPIPresent() )
          goto LABEL_65;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          SystemTime = GetSystemTime();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_d6c0160876fc3ccd83c22976e57f4139_Traceguids, SystemTime);
          v11 = WPP_GLOBAL_Control;
        }
        if ( v5 == 0x8000 )
        {
          CPnPNotification::HandleDeviceArrival(v11, lpEventData);
        }
        else
        {
          if ( v5 != 32772 )
            goto LABEL_33;
          CPnPNotification::HandleDeviceRemoval(v11, lpEventData);
        }
        v11 = WPP_GLOBAL_Control;
LABEL_33:
        if ( v11 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x100) != 0 )
        {
          v13 = GetSystemTime();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d6c0160876fc3ccd83c22976e57f4139_Traceguids, v13);
        }
        if ( v5 == 32772 )
          v9 = 1;
LABEL_65:
        v8 = 0;
        if ( v9 )
          ResetTimerToSpawnThread();
        break;
      case 0xDu:
        if ( g_BthActiveConnector )
        {
          v15 = CBthActiveConnector::OnPowerStateChange(v7, v5, lpEventData);
          if ( v15 < 0
            && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
              v5,
              v15);
          }
        }
        break;
      case 0xEu:
        if ( v5 == 5 )
        {
          if ( g_WPDBus && g_PnPNotification )
          {
            CGroupPolicy::StartProcessGPSettings(v7);
            v9 = 1;
          }
          else
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, lpEventData, lpContext);
            }
          }
        }
        if ( g_BthActiveConnector )
        {
          v14 = CBthActiveConnector::OnSessionChange(v7, v5);
          if ( v14 < 0
            && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
              v5,
              v14);
          }
        }
        goto LABEL_65;
      case 0x20u:
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
            ServiceStatus.dwCurrentState);
        }
        if ( g_WPDBus && g_PnPNotification )
        {
          CGroupPolicy::StartProcessGPSettings(v16);
          v9 = 1;
        }
        else if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, lpEventData, lpContext);
        }
        goto LABEL_65;
      default:
        dwEventType = v10;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        {
          break;
        }
        v18 = 56;
        goto LABEL_73;
    }
  }
  _InterlockedAnd64(&qword_18001F2B0, 0xFFFFFFFFFFFFFFFEuLL);
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), dwEventType, lpEventData, (unsigned int)g_RefCount, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1800031b0  mov     [rsp+arg_8], edx
0x1800031b4  push    rbx
0x1800031b5  push    rsi
0x1800031b6  push    rdi
0x1800031b7  push    r12
0x1800031b9  push    r14
0x1800031bb  push    r15
0x1800031bd  sub     rsp, 58h
0x1800031c1  mov     r12, r8
0x1800031c4  mov     r14d, edx
0x1800031c7  mov     esi, ecx
0x1800031c9  lea     rbx, WPP_GLOBAL_Control
0x1800031d0  mov     rax, cs:WPP_GLOBAL_Control
0x1800031d7  cmp     rax, rbx
0x1800031da  jz      short loc_180003212
0x1800031dc  test    dword ptr [rax+1Ch], 100h
0x1800031e3  jz      short loc_180003212
0x1800031e5  mov     eax, cs:?g_RefCount@@3JA; long g_RefCount
0x1800031eb  mov     rcx, cs:qword_18001F2B0
0x1800031f2  mov     [rsp+88h+var_58], eax
0x1800031f6  mov     [rsp+88h+var_60], rcx
0x1800031fb  mov     [rsp+88h+var_68], edx
0x1800031ff  mov     r9d, esi
0x180003202  mov     rcx, cs:WPP_GLOBAL_Control
0x180003209  mov     rcx, [rcx+10h]
0x18000320d  call    WPP_SF_DDid
0x180003212  prefetchw byte ptr cs:qword_18001F2B0
0x180003219  mov     rax, cs:qword_18001F2B0
0x180003220  mov     rcx, rax
0x180003223  or      rcx, 1
0x180003227  lock cmpxchg cs:qword_18001F2B0, rcx
0x180003230  jnz     short loc_180003220
0x180003232  test    al, 2
0x180003234  jnz     loc_18000362D
0x18000323a  cmp     esi, 4
0x18000323d  jz      loc_1800032D8
0x180003243  mov     edi, 78h ; 'x'
0x180003248  lea     eax, [rsi-1]; switch 32 cases
0x18000324b  cmp     eax, 1Fh
0x18000324e  ja      def_180003275; jumptable 0000000180003275 default case, cases 2-4,6-10,12,15-31
0x180003254  xor     r15d, r15d
0x180003257  mov     [rsp+88h+var_48], r15d
0x18000325c  lea     rdx, __ImageBase
0x180003263  movzx   eax, ds:(byte_1800036BC - 180000000h)[rdx+rax]
0x18000326b  mov     ecx, ds:(jpt_180003275 - 180000000h)[rdx+rax*4]
0x180003272  add     rcx, rdx; this
0x180003275  jmp     rcx; switch jump
0x180003277  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180003275 case 1
0x18000327e  cmp     rcx, rbx
0x180003281  jz      short loc_1800032A1
0x180003283  test    dword ptr [rcx+1Ch], 200h
0x18000328a  jz      short loc_1800032A1
0x18000328c  mov     edx, 2Eh ; '.'
0x180003291  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003298  mov     rcx, [rcx+10h]
0x18000329c  call    WPP_SF_
0x1800032a1  lock or cs:qword_18001F2B0, 2
0x1800032aa  mov     [rsp+88h+var_68], 2710h; unsigned int
0x1800032b2  mov     edx, 3; unsigned int
0x1800032b7  mov     r9d, edx; unsigned int
0x1800032ba  lea     rcx, ?_Service@@3VCService@@A; this
0x1800032c1  call    ?ReportStatus@CService@@QEAAJKKKK@Z; CService::ReportStatus(ulong,ulong,ulong,ulong)
0x1800032c6  mov     rcx, cs:hEvent; hEvent
0x1800032cd  test    rcx, rcx
0x1800032d0  jz      short loc_1800032D8
0x1800032d2  call    cs:__imp_SetEvent
0x1800032d8  xor     edi, edi
0x1800032da  jmp     loc_18000365C
0x1800032df  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180003275 case 5
0x1800032e6  cmp     rcx, rbx
0x1800032e9  jz      short loc_180003309
0x1800032eb  test    dword ptr [rcx+1Ch], 200h
0x1800032f2  jz      short loc_180003309
0x1800032f4  mov     edx, 2Fh ; '/'
0x1800032f9  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003300  mov     rcx, [rcx+10h]
0x180003304  call    WPP_SF_
0x180003309  mov     [rsp+88h+var_68], 7D0h; unsigned int
0x180003311  mov     edx, 3; unsigned int
0x180003316  mov     r9d, 4; unsigned int
0x18000331c  lea     rcx, ?_Service@@3VCService@@A; this
0x180003323  call    ?ReportStatus@CService@@QEAAJKKKK@Z; CService::ReportStatus(ulong,ulong,ulong,ulong)
0x180003328  lea     rcx, ?_Service@@3VCService@@A; this
0x18000332f  call    ?Shutdown@CService@@QEAAXXZ; CService::Shutdown(void)
0x180003334  xor     edi, edi
0x180003336  jmp     loc_18000365C
0x18000333b  lea     eax, [r14-8000h]; jumptable 0000000180003275 case 11
0x180003342  test    eax, 0FFFFFFFBh
0x180003347  jnz     loc_180003606
0x18000334d  test    r12, r12
0x180003350  jnz     short loc_180003391
0x180003352  mov     rcx, cs:WPP_GLOBAL_Control
0x180003359  cmp     rcx, rbx
0x18000335c  jz      loc_18000365C
0x180003362  test    byte ptr [rcx+1Ch], 2
0x180003366  jz      loc_18000365C
0x18000336c  mov     edx, 30h ; '0'
0x180003371  mov     [rsp+88h+var_68], 8000FFFFh
0x180003379  xor     r9d, r9d
0x18000337c  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003383  mov     rcx, [rcx+10h]
0x180003387  call    WPP_SF_qd
0x18000338c  jmp     loc_18000365C
0x180003391  cmp     cs:?g_PnPNotification@@3PEAVCPnPNotification@@EA, r15; CPnPNotification * g_PnPNotification
0x180003398  jz      loc_180003606
0x18000339e  cmp     dword ptr [r12+4], 5
0x1800033a4  jnz     loc_180003606
0x1800033aa  call    ?IsPortableDeviceAPIPresent@@YAHXZ; IsPortableDeviceAPIPresent(void)
0x1800033af  test    eax, eax
0x1800033b1  jz      loc_180003606
0x1800033b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033be  cmp     rcx, rbx
0x1800033c1  jz      short loc_1800033F7
0x1800033c3  test    dword ptr [rcx+1Ch], 100h
0x1800033ca  jz      short loc_1800033F7
0x1800033cc  call    ?GetSystemTime@@YAKXZ; GetSystemTime(void)
0x1800033d1  mov     edx, 13h
0x1800033d6  mov     r9d, eax
0x1800033d9  lea     r8, WPP_d6c0160876fc3ccd83c22976e57f4139_Traceguids
0x1800033e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033e7  mov     rcx, [rcx+10h]
0x1800033eb  call    WPP_SF_d
0x1800033f0  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800033f7  mov     eax, r14d
0x1800033fa  sub     eax, 8000h
0x1800033ff  jz      short loc_180003410
0x180003401  cmp     eax, 4
0x180003404  jnz     short loc_18000341F
0x180003406  mov     rdx, r12; struct _DEV_BROADCAST_DEVICEINTERFACE_W *
0x180003409  call    ?HandleDeviceRemoval@CPnPNotification@@IEAA_JPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z; CPnPNotification::HandleDeviceRemoval(_DEV_BROADCAST_DEVICEINTERFACE_W *)
0x18000340e  jmp     short loc_180003418
0x180003410  mov     rdx, r12; struct _DEV_BROADCAST_DEVICEINTERFACE_W *
0x180003413  call    ?HandleDeviceArrival@CPnPNotification@@IEAA_JPEAU_DEV_BROADCAST_DEVICEINTERFACE_W@@@Z; CPnPNotification::HandleDeviceArrival(_DEV_BROADCAST_DEVICEINTERFACE_W *)
0x180003418  mov     rcx, cs:WPP_GLOBAL_Control
0x18000341f  cmp     rcx, rbx
0x180003422  jz      short loc_180003451
0x180003424  test    dword ptr [rcx+1Ch], 100h
0x18000342b  jz      short loc_180003451
0x18000342d  call    ?GetSystemTime@@YAKXZ; GetSystemTime(void)
0x180003432  mov     edx, 14h
0x180003437  mov     r9d, eax
0x18000343a  lea     r8, WPP_d6c0160876fc3ccd83c22976e57f4139_Traceguids
0x180003441  mov     rcx, cs:WPP_GLOBAL_Control
0x180003448  mov     rcx, [rcx+10h]
0x18000344c  call    WPP_SF_d
0x180003451  mov     eax, 1
0x180003456  cmp     r14d, 8004h
0x18000345d  cmovz   r15d, eax
0x180003461  jmp     loc_180003606
0x180003466  cmp     r14d, 5; jumptable 0000000180003275 case 14
0x18000346a  jnz     short loc_1800034CA
0x18000346c  cmp     cs:?g_WPDBus@@3PEAVCWPDBus@@EA, 0; CWPDBus * g_WPDBus
0x180003474  jz      short loc_180003493
0x180003476  cmp     cs:?g_PnPNotification@@3PEAVCPnPNotification@@EA, 0; CPnPNotification * g_PnPNotification
0x18000347e  jz      short loc_180003493
0x180003480  call    ?StartProcessGPSettings@CGroupPolicy@@QEAAXXZ; CGroupPolicy::StartProcessGPSettings(void)
0x180003485  mov     eax, 1
0x18000348a  mov     r15d, eax
0x18000348d  mov     [rsp+88h+var_48], eax
0x180003491  jmp     short loc_1800034B4
0x180003493  mov     rcx, cs:WPP_GLOBAL_Control
0x18000349a  cmp     rcx, rbx
0x18000349d  jz      short loc_1800034B4
0x18000349f  test    byte ptr [rcx+1Ch], 2
0x1800034a3  jz      short loc_1800034B4
0x1800034a5  mov     edx, 31h ; '1'
0x1800034aa  mov     rcx, [rcx+10h]
0x1800034ae  call    WPP_SF_qq
0x1800034b3  nop
0x1800034b4  jmp     short loc_1800034CA
0x1800034b6  lea     rbx, WPP_GLOBAL_Control
0x1800034bd  mov     r14d, [rsp+88h+arg_8]
0x1800034c5  mov     r15d, [rsp+88h+var_48]
0x1800034ca  cmp     cs:?g_BthActiveConnector@@3PEAVCBthActiveConnector@@EA, 0; CBthActiveConnector * g_BthActiveConnector
0x1800034d2  jz      loc_180003606
0x1800034d8  mov     edx, r14d; unsigned int
0x1800034db  call    ?OnSessionChange@CBthActiveConnector@@QEAAJK@Z; CBthActiveConnector::OnSessionChange(ulong)
0x1800034e0  test    eax, eax
0x1800034e2  jns     loc_180003606
0x1800034e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034ef  cmp     rcx, rbx
0x1800034f2  jz      loc_180003606
0x1800034f8  test    byte ptr [rcx+1Ch], 2
0x1800034fc  jz      loc_180003606
0x180003502  mov     edx, 33h ; '3'
0x180003507  mov     [rsp+88h+var_68], eax
0x18000350b  mov     r9d, r14d
0x18000350e  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003515  mov     rcx, [rcx+10h]
0x180003519  call    WPP_SF_dd
0x18000351e  jmp     loc_180003606
0x180003523  cmp     cs:?g_BthActiveConnector@@3PEAVCBthActiveConnector@@EA, r15; jumptable 0000000180003275 case 13
0x18000352a  jz      loc_18000365C
0x180003530  mov     r8, r12; void *
0x180003533  mov     edx, r14d; unsigned int
0x180003536  call    ?OnPowerStateChange@CBthActiveConnector@@QEAAJKPEAX@Z; CBthActiveConnector::OnPowerStateChange(ulong,void *)
0x18000353b  test    eax, eax
0x18000353d  jns     loc_18000365C
0x180003543  mov     rcx, cs:WPP_GLOBAL_Control
0x18000354a  cmp     rcx, rbx
0x18000354d  jz      loc_18000365C
0x180003553  test    byte ptr [rcx+1Ch], 2
0x180003557  jz      loc_18000365C
0x18000355d  mov     edx, 34h ; '4'
0x180003562  mov     [rsp+88h+var_68], eax
0x180003566  mov     r9d, r14d
0x180003569  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003570  mov     rcx, [rcx+10h]
0x180003574  call    WPP_SF_dd
0x180003579  jmp     loc_18000365C
0x18000357e  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180003275 case 32
0x180003585  cmp     rcx, rbx
0x180003588  jz      short loc_1800035B0
0x18000358a  test    dword ptr [rcx+1Ch], 200h
0x180003591  jz      short loc_1800035B0
0x180003593  mov     edx, 35h ; '5'
0x180003598  mov     r9d, cs:ServiceStatus.dwCurrentState
0x18000359f  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x1800035a6  mov     rcx, [rcx+10h]
0x1800035aa  call    WPP_SF_d
0x1800035af  nop
0x1800035b0  cmp     cs:?g_WPDBus@@3PEAVCWPDBus@@EA, 0; CWPDBus * g_WPDBus
0x1800035b8  jz      short loc_1800035D7
0x1800035ba  cmp     cs:?g_PnPNotification@@3PEAVCPnPNotification@@EA, 0; CPnPNotification * g_PnPNotification
0x1800035c2  jz      short loc_1800035D7
0x1800035c4  call    ?StartProcessGPSettings@CGroupPolicy@@QEAAXXZ; CGroupPolicy::StartProcessGPSettings(void)
0x1800035c9  mov     eax, 1
0x1800035ce  mov     r15d, eax
0x1800035d1  mov     [rsp+88h+var_48], eax
0x1800035d5  jmp     short loc_1800035F8
0x1800035d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035de  cmp     rcx, rbx
0x1800035e1  jz      short loc_1800035F8
0x1800035e3  test    byte ptr [rcx+1Ch], 2
0x1800035e7  jz      short loc_1800035F8
0x1800035e9  mov     edx, 36h ; '6'
0x1800035ee  mov     rcx, [rcx+10h]
0x1800035f2  call    WPP_SF_qq
0x1800035f7  nop
0x1800035f8  jmp     short loc_180003606
0x1800035fa  lea     rbx, WPP_GLOBAL_Control
0x180003601  mov     r15d, [rsp+88h+var_48]
0x180003606  xor     edi, edi
0x180003608  test    r15d, r15d
0x18000360b  jz      short loc_18000365C
0x18000360d  call    ?ResetTimerToSpawnThread@@YAXXZ; ResetTimerToSpawnThread(void)
0x180003612  jmp     short loc_18000365C
0x180003614  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180003275 default case, cases 2-4,6-10,12,15-31
0x18000361b  cmp     rcx, rbx
0x18000361e  jz      short loc_18000365C
0x180003620  test    byte ptr [rcx+1Ch], 4
0x180003624  jz      short loc_18000365C
0x180003626  mov     edx, 38h ; '8'
0x18000362b  jmp     short loc_180003649
0x18000362d  mov     edi, 45Bh
0x180003632  mov     rcx, cs:WPP_GLOBAL_Control
0x180003639  cmp     rcx, rbx
0x18000363c  jz      short loc_18000365C
0x18000363e  test    byte ptr [rcx+1Ch], 4
0x180003642  jz      short loc_18000365C
0x180003644  mov     edx, 39h ; '9'
0x180003649  mov     r9d, esi
0x18000364c  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180003653  mov     rcx, [rcx+10h]
0x180003657  call    WPP_SF_d
0x18000365c  lock and cs:qword_18001F2B0, 0FFFFFFFFFFFFFFFEh
0x180003665  mov     rcx, cs:WPP_GLOBAL_Control
0x18000366c  cmp     rcx, rbx
0x18000366f  jz      short loc_18000368E
0x180003671  test    dword ptr [rcx+1Ch], 100h
0x180003678  jz      short loc_18000368E
0x18000367a  mov     [rsp+88h+var_68], edi
0x18000367e  mov     r9d, cs:?g_RefCount@@3JA; long g_RefCount
0x180003685  mov     rcx, [rcx+10h]
0x180003689  call    WPP_SF_dD
0x18000368e  mov     eax, edi
0x180003690  add     rsp, 58h
0x180003694  pop     r15
0x180003696  pop     r14
0x180003698  pop     r12
0x18000369a  pop     rdi
0x18000369b  pop     rsi
0x18000369c  pop     rbx
0x18000369d  retn
```
