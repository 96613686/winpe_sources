# InitializeWirelessDiagnostics

- ea: `0x1801c58f8`
- end: `0x1801c5cdc`
- name: `InitializeWirelessDiagnostics`
- size: `996`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180117260`

## callees

- `0x1800036c4`
- `0x18000aa0c`
- `0x180011530`
- `0x180091ec8`
- `0x1800d7618`
- `0x180107330`
- `0x1801c5630`
- `0x1801c573c`
- `0x1801c58f8`
- `0x1801c9040`
- `0x1801caf74`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1801c59d3`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1801c59d3`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1801c59db`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1801c59db`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801c5a3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801c5a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5c34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c5c34`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1801c5c2a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1801c5c2a`

## pseudocode

```c
__int64 InitializeWirelessDiagnostics()
{
  unsigned int v0; // edi
  int v1; // eax
  PVOID *v2; // rcx
  DWORD v3; // ebx
  unsigned int v4; // eax
  DWORD v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  DWORD started; // eax
  unsigned int v9; // eax
  DWORD LastError; // eax

  v0 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 57) & 0x200) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids);
  v1 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18029E6C8);
  if ( v1 >= 0 )
    goto LABEL_9;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225)
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      11,
      WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids,
      (unsigned int)v1);
LABEL_9:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_bNotifyWDiag )
  {
    if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 225) >= 2u && (*((_BYTE *)v2 + 228) & 1) != 0 )
    {
      WPP_SF_(v2[27], 12, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 1056;
    goto LABEL_54;
  }
  v4 = _time64(0);
  _o_srand(v4);
  memset_0(&g_WDiag, 0, 0x140u);
  qword_1802A3678 = (__int64)&qword_1802A3670;
  qword_1802A3670 = (struct _WD_INTERFACE_CONTEXT *)&qword_1802A3670;
  qword_1802A3688 = (__int64)&qword_1802A3680;
  qword_1802A3680 = (struct _WD_HELPER_CLASS_CONTEXT *)&qword_1802A3680;
  qword_1802A3698 = (__int64)&qword_1802A3690;
  qword_1802A3690 = &qword_1802A3690;
  hEvent = CreateEventW(0, 1, 0, 0);
  if ( hEvent )
  {
    v6 = WDiagInitializeRWLock((struct _WDIAG_RW_LOCK *)&qword_1802A35E8);
    v3 = v6;
    if ( v6 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids, v6);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      v0 = 2;
      goto LABEL_54;
    }
    v7 = WDiagRegisterWMIEvents(1u);
    v3 = v7;
    if ( v7 )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids, v7);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      v0 = 1;
      goto LABEL_54;
    }
    started = WdiagStartRpcServer();
    v3 = started;
    if ( started )
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids, started);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      v0 = 4;
      goto LABEL_54;
    }
    v9 = WdiagStartWNFSubscriptions();
    v3 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids, v9);
      }
      v0 = 8;
      v3 = 0;
    }
    g_bPeriodicOrDiagnosticPacketStatsEnabled = ArePeriodicOrDiagnosticPacketStatsEnabled();
    if ( g_bPeriodicOrDiagnosticPacketStatsEnabled
      && !CreateTimerQueueTimer(&phNewTimer, 0, (WAITORTIMERCALLBACK)WDiagQueryPktStatisticsTimeout, 0, 0, 0xEA60u, 0) )
    {
      LastError = GetLastError();
      v3 = LastError;
      phNewTimer = 0;
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225)
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 18, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids, LastError);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      v0 = 5;
      goto LABEL_54;
    }
    _InterlockedAdd(&dword_1802A35A4, 1u);
    g_bNotifyWDiag = 1;
    goto LABEL_53;
  }
  v3 = GetLastError();
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_57;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 225) && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0 )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids, v5);
LABEL_53:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_54:
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 57) & 0x200) != 0 )
    WPP_SF_(v2[27], 19, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids);
LABEL_57:
  if ( v3 )
    WDiagCleanup(v0);
  return v3;
}

```

## disassembly

```asm
0x1801c58f8  push    rbx
0x1801c58fa  push    rsi
0x1801c58fb  push    rdi
0x1801c58fc  push    r14
0x1801c58fe  push    r15
0x1801c5900  sub     rsp, 40h
0x1801c5904  xor     edi, edi
0x1801c5906  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c590d  lea     r14, WPP_GLOBAL_Control
0x1801c5914  lea     r15, WPP_332c115b1ff83ac227c5d3aaa30b05ed_Traceguids
0x1801c591b  cmp     rcx, r14
0x1801c591e  jz      short loc_1801C593E
0x1801c5920  test    dword ptr [rcx+0E4h], 200h
0x1801c592a  jz      short loc_1801C593E
0x1801c592c  mov     rcx, [rcx+0D8h]
0x1801c5933  lea     edx, [rdi+0Ah]
0x1801c5936  mov     r8, r15
0x1801c5939  call    WPP_SF_
0x1801c593e  lea     rcx, dword_18029E6C8; CallbackContext
0x1801c5945  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1801c594a  mov     esi, 1
0x1801c594f  test    eax, eax
0x1801c5951  jns     short loc_1801C5986
0x1801c5953  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c595a  cmp     rcx, r14
0x1801c595d  jz      short loc_1801C598D
0x1801c595f  cmp     [rcx+0E1h], sil
0x1801c5966  jb      short loc_1801C598D
0x1801c5968  test    [rcx+0E4h], sil
0x1801c596f  jz      short loc_1801C598D
0x1801c5971  mov     rcx, [rcx+0D8h]
0x1801c5978  lea     edx, [rsi+0Ah]
0x1801c597b  mov     r9d, eax
0x1801c597e  mov     r8, r15
0x1801c5981  call    WPP_SF_d
0x1801c5986  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c598d  cmp     cs:g_bNotifyWDiag, edi
0x1801c5993  jz      short loc_1801C59D1
0x1801c5995  cmp     rcx, r14
0x1801c5998  jz      short loc_1801C59C7
0x1801c599a  cmp     byte ptr [rcx+0E1h], 2
0x1801c59a1  jb      short loc_1801C59C7
0x1801c59a3  test    [rcx+0E4h], sil
0x1801c59aa  jz      short loc_1801C59C7
0x1801c59ac  mov     rcx, [rcx+0D8h]
0x1801c59b3  mov     edx, 0Ch
0x1801c59b8  mov     r8, r15
0x1801c59bb  call    WPP_SF_
0x1801c59c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c59c7  mov     ebx, 420h
0x1801c59cc  jmp     loc_1801C5C9E
0x1801c59d1  xor     ecx, ecx; Time
0x1801c59d3  call    cs:__imp__time64
0x1801c59d9  mov     ecx, eax
0x1801c59db  call    cs:__imp__o_srand
0x1801c59e1  xor     edx, edx; Val
0x1801c59e3  lea     rcx, ?g_WDiag@@3U_WDIAG_GLOBAL_CONTEXT@@A; void *
0x1801c59ea  mov     r8d, 140h; Size
0x1801c59f0  call    memset_0
0x1801c59f5  lea     rax, qword_1802A3670
0x1801c59fc  xor     r9d, r9d; lpName
0x1801c59ff  mov     cs:qword_1802A3678, rax
0x1801c5a06  xor     r8d, r8d; bInitialState
0x1801c5a09  mov     cs:qword_1802A3670, rax
0x1801c5a10  mov     edx, esi; bManualReset
0x1801c5a12  lea     rax, qword_1802A3680
0x1801c5a19  xor     ecx, ecx; lpEventAttributes
0x1801c5a1b  mov     cs:qword_1802A3688, rax
0x1801c5a22  mov     cs:qword_1802A3680, rax
0x1801c5a29  lea     rax, qword_1802A3690
0x1801c5a30  mov     cs:qword_1802A3698, rax
0x1801c5a37  mov     cs:qword_1802A3690, rax
0x1801c5a3e  call    cs:__imp_CreateEventW
0x1801c5a44  mov     cs:hEvent, rax
0x1801c5a4b  test    rax, rax
0x1801c5a4e  jnz     short loc_1801C5AAB
0x1801c5a50  call    cs:__imp_GetLastError
0x1801c5a56  mov     ebx, eax
0x1801c5a58  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5a5f  cmp     rcx, r14
0x1801c5a62  jz      loc_1801C5CC3
0x1801c5a68  cmp     [rcx+0E1h], sil
0x1801c5a6f  jb      loc_1801C5C9E
0x1801c5a75  test    [rcx+0E4h], sil
0x1801c5a7c  jz      loc_1801C5C9E
0x1801c5a82  call    cs:__imp_GetLastError
0x1801c5a88  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5a8f  mov     edx, 0Dh
0x1801c5a94  mov     r9d, eax
0x1801c5a97  mov     r8, r15
0x1801c5a9a  mov     rcx, [rcx+0D8h]
0x1801c5aa1  call    WPP_SF_d
0x1801c5aa6  jmp     loc_1801C5C97
0x1801c5aab  lea     rcx, qword_1802A35E8; struct _WDIAG_RW_LOCK *
0x1801c5ab2  call    ?WDiagInitializeRWLock@@YAKPEAU_WDIAG_RW_LOCK@@@Z; WDiagInitializeRWLock(_WDIAG_RW_LOCK *)
0x1801c5ab7  mov     ebx, eax
0x1801c5ab9  test    eax, eax
0x1801c5abb  jz      short loc_1801C5B03
0x1801c5abd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5ac4  cmp     rcx, r14
0x1801c5ac7  jz      short loc_1801C5AF9
0x1801c5ac9  cmp     [rcx+0E1h], sil
0x1801c5ad0  jb      short loc_1801C5AF9
0x1801c5ad2  test    [rcx+0E4h], sil
0x1801c5ad9  jz      short loc_1801C5AF9
0x1801c5adb  mov     rcx, [rcx+0D8h]
0x1801c5ae2  mov     edx, 0Eh
0x1801c5ae7  mov     r9d, eax
0x1801c5aea  mov     r8, r15
0x1801c5aed  call    WPP_SF_d
0x1801c5af2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5af9  mov     edi, 2
0x1801c5afe  jmp     loc_1801C5C9E
0x1801c5b03  mov     cl, sil; unsigned __int8
0x1801c5b06  call    ?WDiagRegisterWMIEvents@@YAKE@Z; WDiagRegisterWMIEvents(uchar)
0x1801c5b0b  mov     ebx, eax
0x1801c5b0d  test    eax, eax
0x1801c5b0f  jz      short loc_1801C5B54
0x1801c5b11  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5b18  cmp     rcx, r14
0x1801c5b1b  jz      short loc_1801C5B4D
0x1801c5b1d  cmp     [rcx+0E1h], sil
0x1801c5b24  jb      short loc_1801C5B4D
0x1801c5b26  test    [rcx+0E4h], sil
0x1801c5b2d  jz      short loc_1801C5B4D
0x1801c5b2f  mov     rcx, [rcx+0D8h]
0x1801c5b36  mov     edx, 0Fh
0x1801c5b3b  mov     r9d, eax
0x1801c5b3e  mov     r8, r15
0x1801c5b41  call    WPP_SF_d
0x1801c5b46  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5b4d  mov     edi, esi
0x1801c5b4f  jmp     loc_1801C5C9E
0x1801c5b54  call    ?WdiagStartRpcServer@@YAKXZ; WdiagStartRpcServer(void)
0x1801c5b59  mov     ebx, eax
0x1801c5b5b  test    eax, eax
0x1801c5b5d  jz      short loc_1801C5BA5
0x1801c5b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5b66  cmp     rcx, r14
0x1801c5b69  jz      short loc_1801C5B9B
0x1801c5b6b  cmp     [rcx+0E1h], sil
0x1801c5b72  jb      short loc_1801C5B9B
0x1801c5b74  test    [rcx+0E4h], sil
0x1801c5b7b  jz      short loc_1801C5B9B
0x1801c5b7d  mov     rcx, [rcx+0D8h]
0x1801c5b84  mov     edx, 10h
0x1801c5b89  mov     r9d, eax
0x1801c5b8c  mov     r8, r15
0x1801c5b8f  call    WPP_SF_d
0x1801c5b94  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5b9b  mov     edi, 4
0x1801c5ba0  jmp     loc_1801C5C9E
0x1801c5ba5  call    ?WdiagStartWNFSubscriptions@@YAKXZ; WdiagStartWNFSubscriptions(void)
0x1801c5baa  mov     ebx, eax
0x1801c5bac  test    eax, eax
0x1801c5bae  jz      short loc_1801C5BEC
0x1801c5bb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5bb7  cmp     rcx, r14
0x1801c5bba  jz      short loc_1801C5BE5
0x1801c5bbc  cmp     [rcx+0E1h], sil
0x1801c5bc3  jb      short loc_1801C5BE5
0x1801c5bc5  test    [rcx+0E4h], sil
0x1801c5bcc  jz      short loc_1801C5BE5
0x1801c5bce  mov     rcx, [rcx+0D8h]
0x1801c5bd5  mov     edx, 11h
0x1801c5bda  mov     r9d, eax
0x1801c5bdd  mov     r8, r15
0x1801c5be0  call    WPP_SF_d
0x1801c5be5  mov     edi, 8
0x1801c5bea  xor     ebx, ebx
0x1801c5bec  call    ?ArePeriodicOrDiagnosticPacketStatsEnabled@@YAHXZ; ArePeriodicOrDiagnosticPacketStatsEnabled(void)
0x1801c5bf1  mov     cs:?g_bPeriodicOrDiagnosticPacketStatsEnabled@@3HA, eax; int g_bPeriodicOrDiagnosticPacketStatsEnabled
0x1801c5bf7  test    eax, eax
0x1801c5bf9  jz      loc_1801C5C8A
0x1801c5bff  mov     [rsp+68h+Flags], 0; Flags
0x1801c5c07  lea     r8, ?WDiagQueryPktStatisticsTimeout@@YAXPEAXE@Z; Callback
0x1801c5c0e  mov     [rsp+68h+Period], 0EA60h; Period
0x1801c5c16  lea     rcx, phNewTimer; phNewTimer
0x1801c5c1d  xor     r9d, r9d; Parameter
0x1801c5c20  mov     [rsp+68h+DueTime], 0; DueTime
0x1801c5c28  xor     edx, edx; TimerQueue
0x1801c5c2a  call    cs:__imp_CreateTimerQueueTimer
0x1801c5c30  test    eax, eax
0x1801c5c32  jnz     short loc_1801C5C8A
0x1801c5c34  call    cs:__imp_GetLastError
0x1801c5c3a  mov     ebx, eax
0x1801c5c3c  mov     cs:phNewTimer, 0
0x1801c5c47  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5c4e  cmp     rcx, r14
0x1801c5c51  jz      short loc_1801C5C83
0x1801c5c53  cmp     [rcx+0E1h], sil
0x1801c5c5a  jb      short loc_1801C5C83
0x1801c5c5c  test    [rcx+0E4h], sil
0x1801c5c63  jz      short loc_1801C5C83
0x1801c5c65  mov     rcx, [rcx+0D8h]
0x1801c5c6c  mov     edx, 12h
0x1801c5c71  mov     r9d, eax
0x1801c5c74  mov     r8, r15
0x1801c5c77  call    WPP_SF_d
0x1801c5c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5c83  mov     edi, 5
0x1801c5c88  jmp     short loc_1801C5C9E
0x1801c5c8a  lock add cs:dword_1802A35A4, esi
0x1801c5c91  mov     cs:g_bNotifyWDiag, esi
0x1801c5c97  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5c9e  cmp     rcx, r14
0x1801c5ca1  jz      short loc_1801C5CC3
0x1801c5ca3  test    dword ptr [rcx+0E4h], 200h
0x1801c5cad  jz      short loc_1801C5CC3
0x1801c5caf  mov     rcx, [rcx+0D8h]
0x1801c5cb6  mov     edx, 13h
0x1801c5cbb  mov     r8, r15
0x1801c5cbe  call    WPP_SF_
0x1801c5cc3  test    ebx, ebx
0x1801c5cc5  jz      short loc_1801C5CCE
0x1801c5cc7  mov     ecx, edi
0x1801c5cc9  call    ?WDiagCleanup@@YAKW4WDIAG_ENUM_CLEANUP_STAGE@@@Z; WDiagCleanup(WDIAG_ENUM_CLEANUP_STAGE)
0x1801c5cce  mov     eax, ebx
0x1801c5cd0  add     rsp, 40h
0x1801c5cd4  pop     r15
0x1801c5cd6  pop     r14
0x1801c5cd8  pop     rdi
0x1801c5cd9  pop     rsi
0x1801c5cda  pop     rbx
0x1801c5cdb  retn
```
