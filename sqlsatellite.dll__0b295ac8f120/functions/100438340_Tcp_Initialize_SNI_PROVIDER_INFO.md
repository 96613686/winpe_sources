# Tcp::Initialize(SNI_PROVIDER_INFO *)

- ea: `0x100438340`
- end: `0x100438962`
- name: `?Initialize@Tcp@@SAKPEAUSNI_PROVIDER_INFO@@@Z`
- size: `1570`
- prototype: `unsigned int __fastcall(struct SNI_PROVIDER_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x100433d30`

## callees

- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100435240`
- `0x100435530`
- `0x100438340`
- `0x100459c30`
- `0x100459e90`
- `0x100486af0`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x10043847f`
- `KERNEL32!InitializeSListHead` at `0x10043847f`
- `KERNEL32!FreeLibrary` at `0x100438860`
- `KERNEL32!FreeLibrary` at `0x100438860`
- `KERNEL32!GetLastError` at `0x10043886a`
- `KERNEL32!GetLastError` at `0x10043886a`
- `sqldk!?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z` at `0x100438548`
- `sqldk!?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z` at `0x100438548`
- `sqldk!SystemThread_TlsIndex` at `0x1004384ef`
- `sqldk!SystemThread_TlsOffset` at `0x1004384f8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100438511`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100438511`
- `WS2_32!__imp_WSAGetLastError` at `0x1004387aa`
- `WS2_32!__imp_WSAGetLastError` at `0x1004387aa`
- `WS2_32!__imp_WSAStartup` at `0x1004383d6`
- `WS2_32!__imp_WSAStartup` at `0x1004383f1`
- `WS2_32!__imp_WSAStartup` at `0x1004383d6`
- `WS2_32!__imp_WSAStartup` at `0x1004383f1`
- `WS2_32!__imp_WSACleanup` at `0x10043879f`
- `WS2_32!__imp_WSACleanup` at `0x10043879f`

## string_xrefs

- `0x100438485`: `sql\common\dk\sni\src\sni.cpp`
- `0x100438491`: `SNIEnqueueTimerTask`
- `0x100438580`: `SNIEnqueueTimerTask`
- `0x1004385c7`: `SNIEnqueueTimerTask`
- `0x1004385e7`: `SNIEnqueueTimerTask`
- `0x10043837d`: `sql\common\dk\sni\src\tcp.cpp`
- `0x1004387bd`: `ERR|SNIWSACleanup failed: %d{WINERR}.\n`
- `0x10043887d`: `ERR|SNIFreeLibrary(WS2_32.dll) failed: %d{WINERR}.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Tcp::Initialize(struct SNI_PROVIDER_INFO *a1)
{
  char v2; // bp
  char v3; // r14
  unsigned int v4; // ebx
  char v5; // al
  const wchar_t *v6; // r9
  __int64 v7; // rbx
  __int64 v8; // rcx
  const wchar_t *v9; // r9
  char v10; // al
  unsigned int v11; // eax
  int v12; // eax
  volatile signed __int32 *v13; // rax
  int v14; // eax
  unsigned __int32 v15; // eax
  unsigned __int32 v16; // eax
  unsigned __int32 v17; // eax
  unsigned __int32 v18; // eax
  unsigned int WSAPoll; // eax
  int Error; // eax
  DWORD LastError; // eax
  __int64 v23; // [rsp+20h] [rbp-238h]
  __int64 v24; // [rsp+28h] [rbp-230h]
  __int64 v25; // [rsp+30h] [rbp-228h]
  __int128 v26; // [rsp+40h] [rbp-218h]
  __int64 v27; // [rsp+50h] [rbp-208h]
  WSAData WSAData; // [rsp+80h] [rbp-1D8h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\tcp.cpp",
      "Tcp::Initialize",
      6057,
      L"API|SNIpInfo: %p{PSNI_PROVIDER_INFO}\n",
      a1);
  v2 = 0;
  v3 = 0;
  if ( WSAStartup(0x202u, &WSAData) )
  {
    v4 = WSAStartup(0x101u, &WSAData);
    if ( v4 )
    {
      v5 = g_XeSniPkg_enabledBitmap;
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::Initialize",
          6077,
          L"ERR|SNIWinsock library initialization failed\n");
        v5 = g_XeSniPkg_enabledBitmap;
      }
      if ( (v5 & 2) != 0 )
      {
        LODWORD(v23) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\tcp.cpp",
          "Tcp::Initialize",
          6078,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v23,
          0,
          v4);
      }
      SNISetLastError(7, v4, 50100);
LABEL_48:
      if ( Tcp::s_fAutoTuning )
        g_hCleanupSendNotificationTimer = 0;
      if ( v2 )
        SNI::detail::Transport::StaticTerminate();
      if ( v3 )
      {
        *(_QWORD *)&v26 = 0;
        *((_QWORD *)&v26 + 1) = -1;
        LODWORD(v27) = -1;
        *(_OWORD *)&TcpRIO::sm_IPV4 = v26;
        qword_100505838 = v27;
        *(_QWORD *)&v26 = 0;
        *((_QWORD *)&v26 + 1) = -1;
        LODWORD(v27) = -1;
        TcpRIO::sm_IPV6 = v26;
        qword_100505968 = v27;
      }
      if ( Tcp::s_hWS2_32 )
      {
        if ( !FreeLibrary(Tcp::s_hWS2_32) )
        {
          LastError = GetLastError();
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v23) = LastError;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\tcp.cpp",
              "Tcp::Initialize",
              6187,
              L"ERR|SNIFreeLibrary(WS2_32.dll) failed: %d{WINERR}.\n",
              v23);
          }
        }
        Tcp::s_hWS2_32 = 0;
      }
      Tcp::s_pfnWSAPoll = 0;
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v23) = v4;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Initialize", 6194, L"RET|SNI%d{WINERR}\n", v23);
      }
      goto LABEL_64;
    }
  }
  if ( Tcp::s_fAutoTuning )
  {
    InitializeSListHead(&Tcp::s_slhNotificationsToClose);
    if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
      SNIXE_SNI_ENTER_ON(
        "sql\\common\\dk\\sni\\src\\sni.cpp",
        "SNIEnqueueTimerTask",
        7274,
        L"API|SNIpfnAsyncWait: %p{SOS_TimerExecFunc}, pParam: %d{PVOID}, timeout: %d{DWORD}\n",
        &Tcp::CleanupSendNotifications,
        0,
        5000);
    g_hCleanupSendNotificationTimer = 0;
    v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v8 = *(_QWORD *)(v7 + 256);
    if ( !v8 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v8 = *(_QWORD *)(v7 + 256);
    }
    if ( (unsigned int)SOS_Node::EnqueueTimerTaskDirectInternal(
                         *(_QWORD *)(v8 + 992),
                         &Tcp::CleanupSendNotifications,
                         0,
                         0,
                         0,
                         0,
                         5000,
                         0,
                         "sql\\common\\dk\\sni\\src\\sni.cpp",
                         "SNIEnqueueTimerTask",
                         7274,
                         -2,
                         "sql\\common\\dk\\sni\\src\\tcp.cpp",
                         "Tcp::Initialize",
                         6057) )
    {
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v25) = -1;
        LODWORD(v24) = 23;
        LODWORD(v23) = 10;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "SNIEnqueueTimerTask",
          7283,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v23,
          v24,
          v25);
      }
      SNISetLastError(10, 0xFFFFFFFFLL, 50123);
      v4 = -1;
    }
    else
    {
      v4 = 0;
    }
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v23) = v4;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIEnqueueTimerTask", 7290, L"RET|SNI%d{WINERR}\n", v23);
    }
    v10 = g_XeSniPkg_enabledBitmap;
    if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    {
      SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "SNIEnqueueTimerTask", 7274, v9);
      v10 = g_XeSniPkg_enabledBitmap;
    }
    if ( v4 )
    {
      if ( (v10 & 1) != 0 )
      {
        LODWORD(v23) = v4;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Initialize", 6098, L"RET|SNI%d{WINERR}\n", v23);
      }
LABEL_45:
      if ( WSACleanup() == -1 )
      {
        Error = WSAGetLastError();
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v23) = Error;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\tcp.cpp",
            "Tcp::Initialize",
            6152,
            L"ERR|SNIWSACleanup failed: %d{WINERR}.\n",
            v23);
        }
      }
      goto LABEL_48;
    }
  }
  v11 = SNI::detail::Transport::StaticInitialize();
  v4 = v11;
  if ( v11 )
  {
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v23) = v11;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Initialize", 6107, L"RET|SNI%d{WINERR}\n", v23);
    }
    goto LABEL_45;
  }
  v2 = 1;
  v12 = _InterlockedIncrement(&SNI_MemRegions::s_lMaxMemRegionProvider);
  if ( v12 >= 16 )
  {
    v13 = &SNI_MemRegions::s_lMaxMemRegionProvider;
    goto LABEL_39;
  }
  dword_100505830 = v12;
  v14 = _InterlockedIncrement(&SNI_MemRegions::s_lMaxMemRegionProvider);
  if ( v14 >= 16 )
  {
    v13 = &SNI_MemRegions::s_lMaxMemRegionProvider;
    goto LABEL_39;
  }
  dword_100505960 = v14;
  v15 = _InterlockedIncrement((volatile signed __int32 *)&SNI_NodeIOCompletionQueues::sm_cMaxQueue);
  if ( v15 >= 0x11
    || (dword_100505834 = v15,
        v16 = _InterlockedIncrement((volatile signed __int32 *)&SNI_NodeIOCompletionQueues::sm_cMaxQueue),
        v16 >= 0x11)
    || (LODWORD(qword_100505838) = v16,
        v17 = _InterlockedIncrement((volatile signed __int32 *)&SNI_NodeIOCompletionQueues::sm_cMaxQueue),
        v17 >= 0x11)
    || (dword_100505964 = v17,
        v18 = _InterlockedIncrement((volatile signed __int32 *)&SNI_NodeIOCompletionQueues::sm_cMaxQueue),
        v18 >= 0x11) )
  {
    v13 = (volatile signed __int32 *)&SNI_NodeIOCompletionQueues::sm_cMaxQueue;
LABEL_39:
    _InterlockedDecrement(v13);
    v4 = -1;
    if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    {
      LODWORD(v23) = -1;
      SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Initialize", 6115, L"RET|SNI%d{WINERR}\n", v23);
    }
    goto LABEL_45;
  }
  LODWORD(qword_100505968) = v18;
  v3 = 1;
  if ( g_osviSNI.dwMajorVersion >= 6 )
  {
    WSAPoll = LoadWSAPoll(&Tcp::s_pfnWSAPoll, &Tcp::s_hWS2_32);
    v4 = WSAPoll;
    if ( WSAPoll )
    {
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v23) = WSAPoll;
        SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Initialize", 6126, L"RET|SNI%d{WINERR}\n", v23);
      }
      goto LABEL_45;
    }
  }
  Tcp::s_fSupportsFlagNoHandleInherit = FOSSupportsFlagNoHandleInherit();
  *((_DWORD *)a1 + 3) = 1;
  *(_QWORD *)((char *)a1 + 4) = 0;
  *(_DWORD *)a1 = 7;
  *((_DWORD *)a1 + 4) = 1;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
    SNIXE_SNI_TRACE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Initialize", 6142, L"RET|SNI%d{WINERR}\n", 0);
  v4 = 0;
LABEL_64:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\tcp.cpp", "Tcp::Initialize", 6057, v6);
  return v4;
}

```

## disassembly

```asm
0x100438340  mov     rax, rsp
0x100438343  push    rdi
0x100438344  push    r12
0x100438346  push    r13
0x100438348  push    r14
0x10043834a  push    r15
0x10043834c  sub     rsp, 230h
0x100438353  mov     [rsp+258h+var_200], 0FFFFFFFFFFFFFFFEh
0x10043835c  mov     [rax+10h], rbx
0x100438360  mov     [rax+18h], rbp
0x100438364  mov     [rax+20h], rsi
0x100438368  mov     rax, cs:__security_cookie
0x10043836f  xor     rax, rsp
0x100438372  mov     [rsp+258h+var_38], rax
0x10043837a  mov     rsi, rcx
0x10043837d  lea     r15, aSqlCommonDkSni_3; "sql\\common\\dk\\sni\\src\\tcp.cpp"
0x100438384  mov     [rsp+258h+var_1F8], r15
0x100438389  lea     r12, aTcpInitialize; "Tcp::Initialize"
0x100438390  mov     [rsp+258h+var_1F0], r12
0x100438395  mov     [rsp+258h+var_1E8], 17A9h
0x10043839d  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004383a4  jz      short loc_1004383C3
0x1004383a6  mov     [rsp+258h+var_238], rcx
0x1004383ab  lea     r9, aApiSnipinfoPPs; "API|SNIpInfo: %p{PSNI_PROVIDER_INFO}\n"
0x1004383b2  mov     r8d, 17A9h; int
0x1004383b8  mov     rdx, r12; char *
0x1004383bb  mov     rcx, r15; char *
0x1004383be  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004383c3  xor     bpl, bpl
0x1004383c6  xor     r14b, r14b
0x1004383c9  mov     ecx, 202h; wVersionRequested
0x1004383ce  lea     rdx, [rsp+258h+WSAData]; lpWSAData
0x1004383d6  call    cs:__imp_WSAStartup
0x1004383dc  test    eax, eax
0x1004383de  jz      loc_10043846A
0x1004383e4  mov     ecx, 101h; wVersionRequested
0x1004383e9  lea     rdx, [rsp+258h+WSAData]; lpWSAData
0x1004383f1  call    cs:__imp_WSAStartup
0x1004383f7  mov     ebx, eax
0x1004383f9  test    eax, eax
0x1004383fb  jz      short loc_10043846A
0x1004383fd  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438403  test    al, 2
0x100438405  jz      short loc_100438425
0x100438407  lea     r9, aErrSniwinsockL; "ERR|SNIWinsock library initialization f"...
0x10043840e  mov     r8d, 17BDh; int
0x100438414  mov     rdx, r12; char *
0x100438417  mov     rcx, r15; char *
0x10043841a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043841f  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438425  xor     edi, edi
0x100438427  test    al, 2
0x100438429  jz      short loc_100438453
0x10043842b  mov     dword ptr [rsp+258h+var_228], ebx
0x10043842f  mov     dword ptr [rsp+258h+var_230], edi
0x100438433  mov     dword ptr [rsp+258h+var_238], 7
0x10043843b  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100438442  mov     r8d, 17BEh; int
0x100438448  mov     rdx, r12; char *
0x10043844b  mov     rcx, r15; char *
0x10043844e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100438453  mov     r8d, 0C3B4h
0x100438459  mov     edx, ebx
0x10043845b  mov     ecx, 7
0x100438460  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100438465  jmp     loc_1004387D5
0x10043846a  xor     edi, edi
0x10043846c  cmp     cs:?s_fAutoTuning@Tcp@@2HA, edi; int Tcp::s_fAutoTuning
0x100438472  jz      loc_100438629
0x100438478  lea     rcx, ?s_slhNotificationsToClose@Tcp@@1T_SLIST_HEADER@@A; ListHead
0x10043847f  call    cs:__imp_InitializeSListHead
0x100438485  lea     r13, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x10043848c  mov     qword ptr [rsp+258h+var_218], r13
0x100438491  lea     rax, aSnienqueuetime; "SNIEnqueueTimerTask"
0x100438498  mov     qword ptr [rsp+258h+var_218+8], rax
0x10043849d  mov     dword ptr [rsp+258h+var_208], 1C6Ah
0x1004384a5  lea     rcx, ?CleanupSendNotifications@Tcp@@CA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z; Tcp::CleanupSendNotifications(void *,ulong *,ulong *)
0x1004384ac  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004384b3  jz      short loc_1004384DF
0x1004384b5  mov     dword ptr [rsp+258h+var_228], 1388h
0x1004384bd  mov     [rsp+258h+var_230], rdi
0x1004384c2  mov     [rsp+258h+var_238], rcx
0x1004384c7  lea     r9, aApiSnipfnasync; "API|SNIpfnAsyncWait: %p{SOS_TimerExecFu"...
0x1004384ce  mov     r8d, 1C6Ah; int
0x1004384d4  mov     rdx, rax; char *
0x1004384d7  mov     rcx, r13; char *
0x1004384da  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004384df  mov     cs:?g_hCleanupSendNotificationTimer@@3PEAXEA, rdi; void * g_hCleanupSendNotificationTimer
0x1004384e6  mov     rdx, gs:58h
0x1004384ef  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004384f6  mov     ecx, [rax]
0x1004384f8  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004384ff  mov     ebx, [rax]
0x100438501  add     rbx, [rdx+rcx*8]
0x100438505  mov     rcx, [rbx+100h]
0x10043850c  test    rcx, rcx
0x10043850f  jnz     short loc_10043851E
0x100438511  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100438517  mov     rcx, [rbx+100h]
0x10043851e  mov     [rsp+258h+var_220], rdi
0x100438523  mov     dword ptr [rsp+258h+var_228], 1388h
0x10043852b  mov     dword ptr [rsp+258h+var_230], edi
0x10043852f  mov     [rsp+258h+var_238], rdi
0x100438534  xor     r9d, r9d
0x100438537  xor     r8d, r8d
0x10043853a  lea     rdx, ?CleanupSendNotifications@Tcp@@CA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z; Tcp::CleanupSendNotifications(void *,ulong *,ulong *)
0x100438541  mov     rcx, [rcx+3E0h]
0x100438548  call    cs:__imp_?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z; SOS_Node::EnqueueTimerTaskDirectInternal(SOS_TIMERRESULT (*)(void *,ulong *,ulong *),SOS_TIMERRESULT (*)(void *),SOS_TIMERRESULT (*)(void *),void *,ulong,ulong,SOSHost *)
0x10043854e  test    eax, eax
0x100438550  jz      short loc_1004385AB
0x100438552  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438559  jz      short loc_10043858F
0x10043855b  mov     dword ptr [rsp+258h+var_228], 0FFFFFFFFh
0x100438563  mov     dword ptr [rsp+258h+var_230], 17h
0x10043856b  mov     dword ptr [rsp+258h+var_238], 0Ah
0x100438573  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10043857a  mov     r8d, 1C73h; int
0x100438580  lea     rdx, aSnienqueuetime; "SNIEnqueueTimerTask"
0x100438587  mov     rcx, r13; char *
0x10043858a  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x10043858f  mov     edx, 0FFFFFFFFh
0x100438594  mov     ecx, 0Ah
0x100438599  mov     r8d, 0C3CBh
0x10043859f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004385a4  mov     ebx, 0FFFFFFFFh
0x1004385a9  jmp     short loc_1004385AD
0x1004385ab  mov     ebx, edi
0x1004385ad  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004385b4  jz      short loc_1004385D7
0x1004385b6  mov     dword ptr [rsp+258h+var_238], ebx
0x1004385ba  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004385c1  mov     r8d, 1C7Ah; int
0x1004385c7  lea     rdx, aSnienqueuetime; "SNIEnqueueTimerTask"
0x1004385ce  mov     rcx, r13; char *
0x1004385d1  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004385d6  nop
0x1004385d7  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004385dd  test    al, al
0x1004385df  jns     short loc_1004385FC
0x1004385e1  mov     r8d, 1C6Ah; int
0x1004385e7  lea     rdx, aSnienqueuetime; "SNIEnqueueTimerTask"
0x1004385ee  mov     rcx, r13; char *
0x1004385f1  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004385f6  mov     eax, cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004385fc  test    ebx, ebx
0x1004385fe  jz      short loc_100438629
0x100438600  test    al, 1
0x100438602  jz      loc_10043879F
0x100438608  mov     dword ptr [rsp+258h+var_238], ebx
0x10043860c  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100438613  mov     r8d, 17D2h; int
0x100438619  mov     rdx, r12; char *
0x10043861c  mov     rcx, r15; char *
0x10043861f  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100438624  jmp     loc_10043879F
0x100438629  call    ?StaticInitialize@Transport@detail@SNI@@SAKXZ; SNI::detail::Transport::StaticInitialize(void)
0x10043862e  mov     ebx, eax
0x100438630  test    eax, eax
0x100438632  jz      short loc_100438662
0x100438634  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10043863b  jz      loc_10043879F
0x100438641  mov     dword ptr [rsp+258h+var_238], eax
0x100438645  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043864c  mov     r8d, 17DBh; int
0x100438652  mov     rdx, r12; char *
0x100438655  mov     rcx, r15; char *
0x100438658  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043865d  jmp     loc_10043879F
0x100438662  mov     bpl, 1
0x100438665  mov     eax, 1
0x10043866a  lock xadd cs:?s_lMaxMemRegionProvider@SNI_MemRegions@@2JA, eax; long SNI_MemRegions::s_lMaxMemRegionProvider
0x100438672  inc     eax
0x100438674  cmp     eax, 10h
0x100438677  jl      short loc_100438685
0x100438679  lea     rax, ?s_lMaxMemRegionProvider@SNI_MemRegions@@2JA; long SNI_MemRegions::s_lMaxMemRegionProvider
0x100438680  jmp     loc_100438717
0x100438685  mov     cs:dword_100505830, eax
0x10043868b  mov     eax, 1
0x100438690  lock xadd cs:?s_lMaxMemRegionProvider@SNI_MemRegions@@2JA, eax; long SNI_MemRegions::s_lMaxMemRegionProvider
0x100438698  inc     eax
0x10043869a  cmp     eax, 10h
0x10043869d  jl      short loc_1004386A8
0x10043869f  lea     rax, ?s_lMaxMemRegionProvider@SNI_MemRegions@@2JA; long SNI_MemRegions::s_lMaxMemRegionProvider
0x1004386a6  jmp     short loc_100438717
0x1004386a8  mov     cs:dword_100505960, eax
0x1004386ae  mov     eax, 1
0x1004386b3  lock xadd cs:?sm_cMaxQueue@SNI_NodeIOCompletionQueues@@0KA, eax; ulong SNI_NodeIOCompletionQueues::sm_cMaxQueue
0x1004386bb  inc     eax
0x1004386bd  cmp     eax, 11h
0x1004386c0  jnb     short loc_100438710
0x1004386c2  mov     cs:dword_100505834, eax
0x1004386c8  mov     eax, 1
0x1004386cd  lock xadd cs:?sm_cMaxQueue@SNI_NodeIOCompletionQueues@@0KA, eax; ulong SNI_NodeIOCompletionQueues::sm_cMaxQueue
0x1004386d5  inc     eax
0x1004386d7  cmp     eax, 11h
0x1004386da  jnb     short loc_100438710
0x1004386dc  mov     dword ptr cs:qword_100505838, eax
0x1004386e2  mov     eax, 1
0x1004386e7  lock xadd cs:?sm_cMaxQueue@SNI_NodeIOCompletionQueues@@0KA, eax; ulong SNI_NodeIOCompletionQueues::sm_cMaxQueue
0x1004386ef  inc     eax
0x1004386f1  cmp     eax, 11h
0x1004386f4  jnb     short loc_100438710
0x1004386f6  mov     cs:dword_100505964, eax
0x1004386fc  mov     eax, 1
0x100438701  lock xadd cs:?sm_cMaxQueue@SNI_NodeIOCompletionQueues@@0KA, eax; ulong SNI_NodeIOCompletionQueues::sm_cMaxQueue
0x100438709  inc     eax
0x10043870b  cmp     eax, 11h
0x10043870e  jb      short loc_100438746
0x100438710  lea     rax, ?sm_cMaxQueue@SNI_NodeIOCompletionQueues@@0KA; ulong SNI_NodeIOCompletionQueues::sm_cMaxQueue
0x100438717  lock dec dword ptr [rax]
0x10043871a  mov     ebx, 0FFFFFFFFh
0x10043871f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, bpl; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438726  jz      short loc_10043879F
0x100438728  mov     dword ptr [rsp+258h+var_238], ebx
0x10043872c  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100438733  mov     r8d, 17E3h; int
0x100438739  mov     rdx, r12; char *
0x10043873c  mov     rcx, r15; char *
0x10043873f  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100438744  jmp     short loc_10043879F
0x100438746  mov     dword ptr cs:qword_100505968, eax
0x10043874c  movzx   r14d, bpl
0x100438750  cmp     cs:?g_osviSNI@@3U_OSVERSIONINFOEXW@@A.dwMajorVersion, 6; _OSVERSIONINFOEXW g_osviSNI ...
0x100438757  jb      loc_1004388CA
0x10043875d  lea     rdx, ?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; HINSTANCE *
0x100438764  lea     rcx, ?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA; int (**)(struct pollfd *const, unsigned int, int)
0x10043876b  call    ?LoadWSAPoll@@YAKPEAP6AHQEAUpollfd@@KH@ZPEAPEAUHINSTANCE__@@@Z; LoadWSAPoll(int (**)(pollfd * const,ulong,int),HINSTANCE__ * *)
0x100438770  mov     ebx, eax
0x100438772  test    eax, eax
0x100438774  jz      loc_1004388CA
0x10043877a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, bpl; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438781  jz      short loc_10043879F
0x100438783  mov     dword ptr [rsp+258h+var_238], eax
0x100438787  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x10043878e  mov     r8d, 17EEh; int
0x100438794  mov     rdx, r12; char *
0x100438797  mov     rcx, r15; char *
0x10043879a  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10043879f  call    cs:__imp_WSACleanup
0x1004387a5  cmp     eax, 0FFFFFFFFh
0x1004387a8  jnz     short loc_1004387D5
0x1004387aa  call    cs:__imp_WSAGetLastError
0x1004387b0  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004387b7  jz      short loc_1004387D5
0x1004387b9  mov     dword ptr [rsp+258h+var_238], eax
0x1004387bd  lea     r9, aErrSniwsaclean; "ERR|SNIWSACleanup failed: %d{WINERR}.\n"
0x1004387c4  mov     r8d, 1808h; int
0x1004387ca  mov     rdx, r12; char *
0x1004387cd  mov     rcx, r15; char *
0x1004387d0  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004387d5  cmp     cs:?s_fAutoTuning@Tcp@@2HA, 0; int Tcp::s_fAutoTuning
0x1004387dc  jz      short loc_1004387E5
0x1004387de  mov     cs:?g_hCleanupSendNotificationTimer@@3PEAXEA, rdi; void * g_hCleanupSendNotificationTimer
0x1004387e5  test    bpl, bpl
0x1004387e8  jz      short loc_1004387EF
0x1004387ea  call    ?StaticTerminate@Transport@detail@SNI@@SAXXZ; SNI::detail::Transport::StaticTerminate(void)
0x1004387ef  test    r14b, r14b
0x1004387f2  jz      short loc_100438854
0x1004387f4  mov     qword ptr [rsp+258h+var_218], rdi
0x1004387f9  mov     qword ptr [rsp+258h+var_218+8], 0FFFFFFFFFFFFFFFFh
0x100438802  mov     dword ptr [rsp+258h+var_208], 0FFFFFFFFh
0x10043880a  movups  xmm0, [rsp+258h+var_218]
0x10043880f  movups  xmmword ptr cs:?sm_IPV4@TcpRIO@@2UTcpRIOProviderData@@A, xmm0; TcpRIOProviderData TcpRIO::sm_IPV4
0x100438816  movsd   xmm1, [rsp+258h+var_208]
0x10043881c  movsd   cs:qword_100505838, xmm1
0x100438824  mov     qword ptr [rsp+258h+var_218], rdi
0x100438829  mov     qword ptr [rsp+258h+var_218+8], 0FFFFFFFFFFFFFFFFh
0x100438832  mov     dword ptr [rsp+258h+var_208], 0FFFFFFFFh
0x10043883a  movups  xmm0, [rsp+258h+var_218]
0x10043883f  movups  xmmword ptr cs:?sm_IPV6@TcpRIO@@2UTcpRIOProviderData@@A, xmm0; TcpRIOProviderData TcpRIO::sm_IPV6
0x100438846  movsd   xmm1, [rsp+258h+var_208]
0x10043884c  movsd   cs:qword_100505968, xmm1
0x100438854  mov     rcx, cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA; hLibModule
0x10043885b  test    rcx, rcx
0x10043885e  jz      short loc_10043889C
0x100438860  call    cs:__imp_FreeLibrary
0x100438866  test    eax, eax
0x100438868  jnz     short loc_100438895
0x10043886a  call    cs:__imp_GetLastError
0x100438870  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100438877  jz      short loc_100438895
0x100438879  mov     dword ptr [rsp+258h+var_238], eax
0x10043887d  lea     r9, aErrSnifreelibr_0; "ERR|SNIFreeLibrary(WS2_32.dll) failed: "...
0x100438884  mov     r8d, 182Bh; int
0x10043888a  mov     rdx, r12; char *
0x10043888d  mov     rcx, r15; char *
0x100438890  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100438895  mov     cs:?s_hWS2_32@Tcp@@1PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * Tcp::s_hWS2_32
0x10043889c  mov     cs:?s_pfnWSAPoll@Tcp@@1P6AHQEAUpollfd@@KH@ZEA, rdi; int (*Tcp::s_pfnWSAPoll)(pollfd * const,ulong,int)
0x1004388a3  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004388aa  jz      short loc_100438915
0x1004388ac  mov     dword ptr [rsp+258h+var_238], ebx
0x1004388b0  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004388b7  mov     r8d, 1832h; int
0x1004388bd  mov     rdx, r12; char *
0x1004388c0  mov     rcx, r15; char *
0x1004388c3  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004388c8  jmp     short loc_100438915
0x1004388ca  call    ?FOSSupportsFlagNoHandleInherit@@YA_NXZ; FOSSupportsFlagNoHandleInherit(void)
0x1004388cf  mov     cs:?s_fSupportsFlagNoHandleInherit@Tcp@@1_NA, al; bool Tcp::s_fSupportsFlagNoHandleInherit
  ... truncated ...
```
