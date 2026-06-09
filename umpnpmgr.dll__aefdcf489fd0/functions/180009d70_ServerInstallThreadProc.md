# ServerInstallThreadProc

- ea: `0x180009d70`
- end: `0x18000a174`
- name: `ServerInstallThreadProc`
- size: `1028`
- prototype: `__int64 __fastcall(HANDLE *Parameter)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800056d0`
- `0x180009890`
- `0x180009d70`
- `0x18000a180`
- `0x18000a210`
- `0x18000a248`
- `0x18000a2f8`
- `0x18000a9e0`
- `0x18000e4e0`
- `0x18000f8d4`
- `0x1800106dc`
- `0x1800117d4`
- `0x180011964`
- `0x180012058`
- `0x1800120b0`
- `0x180013670`
- `0x180013ed8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000a0da`
- `ntdll!RtlFreeHeap` at `0x18000a0da`
- `ntdll!RtlPublishWnfStateData` at `0x180009fa5`
- `ntdll!RtlPublishWnfStateData` at `0x180009fa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a111`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a111`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a0ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018c74`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e70`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a0ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018c74`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009ef8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180009ef8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a002`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a0be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018c04`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a002`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a0be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018c04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a12b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a12b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d9f`

## pseudocode

```c
__int64 __fastcall ServerInstallThreadProc(HANDLE *Parameter)
{
  int v2; // r12d
  int v3; // esi
  DWORD CurrentThreadId; // edi
  __int64 v5; // rdx
  _QWORD *v6; // rbx
  void *v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  int v10; // r8d
  int v11; // r15d
  BOOL v12; // eax
  __int64 v13; // rcx
  _DWORD *v14; // rax
  void *v15; // rcx
  int v16; // ecx
  int v17; // eax
  int v18; // eax
  int v20; // [rsp+D8h] [rbp+8h] BYREF
  ULONG pulStatus; // [rsp+E0h] [rbp+10h] BYREF
  DWORD v22; // [rsp+E8h] [rbp+18h]
  ULONG pulProblemNumber; // [rsp+F0h] [rbp+20h] BYREF

  pulStatus = 0;
  pulProblemNumber = 0;
  v2 = 0;
  v3 = 0;
  v20 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v22 = CurrentThreadId;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  ServerInstallAddThreadIdToList(CurrentThreadId);
  v6 = Parameter[1];
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, CurrentThreadId);
  if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
    McTemplateU0qz_EtwEventWriteTransfer((__int64)v7, v5, CurrentThreadId, (const wchar_t *)v6[4]);
  SetServerInstallEntry(CurrentThreadId, v6);
  pSetupBeginSynchronizedAccess(&Handles);
  v8 = *v6;
  if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v9 = (_QWORD *)v6[1], (_QWORD *)*v9 != v6) )
    __fastfail(3u);
  *v9 = v8;
  *(_QWORD *)(v8 + 8) = v9;
  ReleaseMutex(hMutex);
  v11 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v10, CurrentThreadId, v6[4]);
  v12 = 1;
  if ( (v6[10] & 1) == 0 && *((_DWORD *)v6 + 4) == 1 )
  {
    DeviceIdNeedsInstall((DEVINSTID_W)v6[4], &v20);
    v3 = v20;
    v12 = v20 != 0;
  }
  if ( v12 )
  {
    ResetEvent(PnpNoPendingInstallEvents);
    v11 = PnpInstallDevice(
            *((_DWORD *)v6 + 4),
            v6[3],
            (WCHAR *)v6[4],
            v6[6],
            (void *)v6[7],
            v6[8],
            *((_DWORD *)v6 + 20),
            v3);
    if ( !v11
      && !(unsigned int)GetDeviceStatus((DEVINSTID_W)v6[4], &pulStatus, &pulProblemNumber)
      && (pulStatus & 0x100) != 0 )
    {
      PnpDeviceInstallRebootNeeded = 1;
      if ( (byte_180023989 & 1) != 0 )
        McTemplateU0z_EtwEventWriteTransfer(v13, (int)PNP_REBOOT_REQUIRED, (const wchar_t *)v6[4]);
      if ( (v6[10] & 1) == 0 )
        RtlPublishWnfStateData(WNF_PNPC_REBOOT_REQUIRED, 0, 0, 0, 0);
    }
    if ( v11 == 480 || v11 == 481 || v11 == 482 )
    {
      v2 = 1;
    }
    else if ( v11 != 1460 )
    {
      goto LABEL_33;
    }
    if ( (byte_180023989 & 4) != 0 )
      McTemplateU0z_EtwEventWriteTransfer(v13, (int)TIMEOUT_DETECTED, (const wchar_t *)v6[4]);
  }
LABEL_33:
  v14 = (_DWORD *)v6[9];
  if ( v14 )
    *v14 = v11;
  v15 = (void *)v6[12];
  if ( v15 )
    SetEvent(v15);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v10, CurrentThreadId, v6[4]);
  SetServerInstallEntry(CurrentThreadId, 0);
  FreeServerInstallEntry(v6);
  if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v16, (int)WORKER_THREAD_STOP, CurrentThreadId);
  pSetupBeginSynchronizedAccess(&Handles);
  v17 = -1;
  if ( ServerInstallBatchComplete + 1 >= (unsigned int)ServerInstallBatchComplete )
    v17 = ServerInstallBatchComplete + 1;
  ServerInstallBatchComplete = v17;
  v18 = ServerInstallBatchTimeoutDetected;
  if ( v2 )
    v18 = 1;
  ServerInstallBatchTimeoutDetected = v18;
  ServerInstallUpdateStatus();
  ReleaseMutex(hMutex);
  ServerInstallRemoveThreadIdFromList(CurrentThreadId);
  SetEvent(*Parameter);
  CloseHandle(*Parameter);
  RtlFreeHeap(PnpHeapHandle, 0, Parameter);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, CurrentThreadId);
  EnterCriticalSection(&PnpIdleStopLock);
  if ( !--PnpServiceOutstandingInstalls )
    EvaluateIdleStopPolicy();
  LeaveCriticalSection(&PnpIdleStopLock);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180009d70  mov     rax, rsp
0x180009d73  push    rbx
0x180009d74  push    rsi
0x180009d75  push    rdi
0x180009d76  push    r12
0x180009d78  push    r13
0x180009d7a  push    r14
0x180009d7c  push    r15
0x180009d7e  sub     rsp, 60h
0x180009d82  mov     r13, rcx
0x180009d85  mov     dword ptr [rax+10h], 0
0x180009d8c  mov     dword ptr [rax+20h], 0
0x180009d93  xor     r12d, r12d
0x180009d96  mov     [rax-50h], r12d
0x180009d9a  xor     esi, esi
0x180009d9c  mov     [rax+8], esi
0x180009d9f  call    cs:__imp_GetCurrentThreadId
0x180009da5  mov     edi, eax
0x180009da7  mov     [rsp+98h+arg_10], eax
0x180009dae  lea     r14, WPP_GLOBAL_Control
0x180009db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dbc  cmp     rcx, r14
0x180009dbf  jz      short loc_180009DDD
0x180009dc1  test    dword ptr [rcx+1Ch], 10000000h
0x180009dc8  jz      short loc_180009DDD
0x180009dca  lea     edx, [rsi+23h]
0x180009dcd  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180009dd4  mov     rcx, [rcx+10h]
0x180009dd8  call    WPP_SF_
0x180009ddd  mov     ecx, edi
0x180009ddf  call    ServerInstallAddThreadIdToList
0x180009de4  mov     rbx, [r13+8]
0x180009de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009def  cmp     rcx, r14
0x180009df2  mov     r14d, 800000h
0x180009df8  jz      short loc_180009E18
0x180009dfa  test    [rcx+1Ch], r14d
0x180009dfe  jz      short loc_180009E18
0x180009e00  mov     edx, 24h ; '$'
0x180009e05  mov     r9d, edi
0x180009e08  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180009e0f  mov     rcx, [rcx+10h]
0x180009e13  call    WPP_SF_d
0x180009e18  test    cs:Microsoft_Windows_UserPnpEnableBits, 1
0x180009e1f  jz      short loc_180009E2D
0x180009e21  mov     r9, [rbx+20h]
0x180009e25  mov     r8d, edi
0x180009e28  call    McTemplateU0qz_EtwEventWriteTransfer
0x180009e2d  mov     rdx, rbx
0x180009e30  mov     ecx, edi
0x180009e32  call    SetServerInstallEntry
0x180009e37  lea     rcx, Handles; lpHandles
0x180009e3e  call    pSetupBeginSynchronizedAccess
0x180009e43  mov     rcx, [rbx]
0x180009e46  cmp     [rcx+8], rbx
0x180009e4a  jnz     loc_18000A16D
0x180009e50  mov     rax, [rbx+8]
0x180009e54  cmp     [rax], rbx
0x180009e57  jnz     loc_18000A16D
0x180009e5d  mov     [rsp+98h+var_48], rbx
0x180009e62  mov     [rax], rcx
0x180009e65  mov     [rcx+8], rax
0x180009e69  mov     rcx, cs:hMutex; hMutex
0x180009e70  call    cs:__imp_ReleaseMutex
0x180009e76  xor     r15d, r15d
0x180009e79  mov     [rsp+98h+var_58], r15d
0x180009e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e85  lea     rax, WPP_GLOBAL_Control
0x180009e8c  cmp     rcx, rax
0x180009e8f  jz      short loc_180009EB1
0x180009e91  test    [rcx+1Ch], r14d
0x180009e95  jz      short loc_180009EB1
0x180009e97  lea     edx, [r15+25h]
0x180009e9b  mov     rax, [rbx+20h]
0x180009e9f  mov     [rsp+98h+var_78], rax
0x180009ea4  mov     r9d, edi
0x180009ea7  mov     rcx, [rcx+10h]
0x180009eab  call    WPP_SF_dS
0x180009eb0  nop
0x180009eb1  mov     ecx, 1
0x180009eb6  mov     eax, ecx
0x180009eb8  mov     [rsp+98h+var_54], ecx
0x180009ebc  test    [rbx+50h], cl
0x180009ebf  jnz     short loc_180009EE9
0x180009ec1  cmp     [rbx+10h], ecx
0x180009ec4  jnz     short loc_180009EE9
0x180009ec6  lea     rdx, [rsp+98h+arg_0]
0x180009ece  mov     rcx, [rbx+20h]; pDeviceID
0x180009ed2  call    DeviceIdNeedsInstall
0x180009ed7  xor     eax, eax
0x180009ed9  mov     esi, [rsp+98h+arg_0]
0x180009ee0  test    esi, esi
0x180009ee2  setnz   al
0x180009ee5  mov     [rsp+98h+var_54], eax
0x180009ee9  test    eax, eax
0x180009eeb  jz      loc_180009FED
0x180009ef1  mov     rcx, cs:PnpNoPendingInstallEvents; hEvent
0x180009ef8  call    cs:__imp_ResetEvent
0x180009efe  mov     [rsp+98h+var_60], esi
0x180009f02  mov     eax, [rbx+50h]
0x180009f05  mov     [rsp+98h+var_68], eax
0x180009f09  mov     rax, [rbx+40h]
0x180009f0d  mov     [rsp+98h+var_70], rax
0x180009f12  mov     rax, [rbx+38h]
0x180009f16  mov     [rsp+98h+var_78], rax
0x180009f1b  mov     r9, [rbx+30h]
0x180009f1f  mov     r8, [rbx+20h]
0x180009f23  mov     rdx, [rbx+18h]
0x180009f27  mov     ecx, [rbx+10h]
0x180009f2a  call    PnpInstallDevice
0x180009f2f  mov     r15d, eax
0x180009f32  mov     [rsp+98h+var_58], eax
0x180009f36  test    eax, eax
0x180009f38  jnz     short loc_180009FAB
0x180009f3a  lea     r8, [rsp+98h+pulProblemNumber]; pulProblemNumber
0x180009f42  lea     rdx, [rsp+98h+pulStatus]; pulStatus
0x180009f4a  mov     rcx, [rbx+20h]; pDeviceID
0x180009f4e  call    GetDeviceStatus
0x180009f53  test    eax, eax
0x180009f55  jnz     short loc_180009FAB
0x180009f57  test    [rsp+98h+pulStatus], 100h
0x180009f62  jz      short loc_180009FAB
0x180009f64  mov     cs:PnpDeviceInstallRebootNeeded, 1
0x180009f6e  test    cs:byte_180023989, 1
0x180009f75  jz      short loc_180009F87
0x180009f77  mov     r8, [rbx+20h]
0x180009f7b  lea     rdx, PNP_REBOOT_REQUIRED
0x180009f82  call    McTemplateU0z_EtwEventWriteTransfer
0x180009f87  test    byte ptr [rbx+50h], 1
0x180009f8b  jnz     short loc_180009FAB
0x180009f8d  mov     [rsp+98h+var_78], 0
0x180009f96  xor     r9d, r9d
0x180009f99  xor     r8d, r8d
0x180009f9c  xor     edx, edx
0x180009f9e  mov     rcx, cs:WNF_PNPC_REBOOT_REQUIRED
0x180009fa5  call    cs:__imp_RtlPublishWnfStateData
0x180009fab  mov     eax, r15d
0x180009fae  sub     eax, 1E0h
0x180009fb3  jz      short loc_180009FC8
0x180009fb5  sub     eax, 1
0x180009fb8  jz      short loc_180009FC8
0x180009fba  sub     eax, 1
0x180009fbd  jz      short loc_180009FC8
0x180009fbf  cmp     eax, 3D2h
0x180009fc4  jz      short loc_180009FD3
0x180009fc6  jmp     short loc_180009FED
0x180009fc8  mov     r12d, 1
0x180009fce  mov     [rsp+98h+var_50], r12d
0x180009fd3  test    cs:byte_180023989, 4
0x180009fda  jz      short loc_180009FED
0x180009fdc  mov     r8, [rbx+20h]
0x180009fe0  lea     rdx, TIMEOUT_DETECTED
0x180009fe7  call    McTemplateU0z_EtwEventWriteTransfer
0x180009fec  nop
0x180009fed  mov     rax, [rbx+48h]
0x180009ff1  test    rax, rax
0x180009ff4  jz      short loc_180009FF9
0x180009ff6  mov     [rax], r15d
0x180009ff9  mov     rcx, [rbx+60h]; hEvent
0x180009ffd  test    rcx, rcx
0x18000a000  jz      short loc_18000A008
0x18000a002  call    cs:__imp_SetEvent
0x18000a008  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a00f  lea     r15, WPP_GLOBAL_Control
0x18000a016  cmp     rcx, r15
0x18000a019  jz      short loc_18000A03B
0x18000a01b  test    [rcx+1Ch], r14d
0x18000a01f  jz      short loc_18000A03B
0x18000a021  mov     edx, 26h ; '&'
0x18000a026  mov     rax, [rbx+20h]
0x18000a02a  mov     [rsp+98h+var_78], rax
0x18000a02f  mov     r9d, edi
0x18000a032  mov     rcx, [rcx+10h]
0x18000a036  call    WPP_SF_dS
0x18000a03b  xor     edx, edx
0x18000a03d  mov     ecx, edi
0x18000a03f  call    SetServerInstallEntry
0x18000a044  mov     rcx, rbx; P
0x18000a047  call    FreeServerInstallEntry
0x18000a04c  mov     ebx, 1
0x18000a051  test    cs:Microsoft_Windows_UserPnpEnableBits, bl
0x18000a057  jz      short loc_18000A068
0x18000a059  mov     r8d, edi
0x18000a05c  lea     rdx, WORKER_THREAD_STOP
0x18000a063  call    McTemplateU0q_EtwEventWriteTransfer
0x18000a068  lea     rcx, Handles; lpHandles
0x18000a06f  call    pSetupBeginSynchronizedAccess
0x18000a074  nop
0x18000a075  mov     edx, cs:ServerInstallBatchComplete
0x18000a07b  lea     ecx, [rdx+1]
0x18000a07e  or      esi, 0FFFFFFFFh
0x18000a081  mov     eax, esi
0x18000a083  cmp     ecx, edx
0x18000a085  cmovnb  eax, ecx
0x18000a088  mov     cs:ServerInstallBatchComplete, eax
0x18000a08e  mov     eax, cs:ServerInstallBatchTimeoutDetected
0x18000a094  test    r12d, r12d
0x18000a097  cmovnz  eax, ebx
0x18000a09a  mov     cs:ServerInstallBatchTimeoutDetected, eax
0x18000a0a0  call    ServerInstallUpdateStatus
0x18000a0a5  nop
0x18000a0a6  mov     rcx, cs:hMutex; hMutex
0x18000a0ad  call    cs:__imp_ReleaseMutex
0x18000a0b3  mov     ecx, edi
0x18000a0b5  call    ServerInstallRemoveThreadIdFromList
0x18000a0ba  mov     rcx, [r13+0]; hEvent
0x18000a0be  call    cs:__imp_SetEvent
0x18000a0c4  mov     rcx, [r13+0]; hObject
0x18000a0c8  call    cs:__imp_CloseHandle
0x18000a0ce  mov     r8, r13; P
0x18000a0d1  xor     edx, edx; Flags
0x18000a0d3  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x18000a0da  call    cs:__imp_RtlFreeHeap
0x18000a0e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0e7  cmp     rcx, r15
0x18000a0ea  jz      short loc_18000A10A
0x18000a0ec  test    [rcx+1Ch], r14d
0x18000a0f0  jz      short loc_18000A10A
0x18000a0f2  mov     edx, 27h ; '''
0x18000a0f7  mov     r9d, edi
0x18000a0fa  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a101  mov     rcx, [rcx+10h]
0x18000a105  call    WPP_SF_d
0x18000a10a  lea     rcx, PnpIdleStopLock; lpCriticalSection
0x18000a111  call    cs:__imp_EnterCriticalSection
0x18000a117  add     cs:PnpServiceOutstandingInstalls, esi
0x18000a11d  jnz     short loc_18000A124
0x18000a11f  call    EvaluateIdleStopPolicy
0x18000a124  lea     rcx, PnpIdleStopLock; lpCriticalSection
0x18000a12b  call    cs:__imp_LeaveCriticalSection
0x18000a131  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a138  cmp     rcx, r15
0x18000a13b  jz      short loc_18000A15B
0x18000a13d  test    dword ptr [rcx+1Ch], 10000000h
0x18000a144  jz      short loc_18000A15B
0x18000a146  mov     edx, 28h ; '('
0x18000a14b  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a152  mov     rcx, [rcx+10h]
0x18000a156  call    WPP_SF_
0x18000a15b  xor     eax, eax
0x18000a15d  add     rsp, 60h
0x18000a161  pop     r15
0x18000a163  pop     r14
0x18000a165  pop     r13
0x18000a167  pop     r12
0x18000a169  pop     rdi
0x18000a16a  pop     rsi
0x18000a16b  pop     rbx
0x18000a16c  retn
0x18000a16d  mov     ecx, 3
0x18000a172  int     29h; Win8: RtlFailFast(ecx)
0x180018bdb  push    rbx
0x180018bdd  push    rbp
0x180018bde  sub     rsp, 48h
0x180018be2  mov     rbp, rdx
0x180018be5  mov     rbx, [rbp+50h]
0x180018be9  cmp     qword ptr [rbx+48h], 0
0x180018bee  jz      short loc_180018BF9
0x180018bf0  mov     rcx, [rbx+48h]
0x180018bf4  mov     eax, [rbp+40h]
0x180018bf7  mov     [rcx], eax
0x180018bf9  cmp     qword ptr [rbx+60h], 0
0x180018bfe  jz      short loc_180018C0B
0x180018c00  mov     rcx, [rbx+60h]; hEvent
0x180018c04  call    cs:__imp_SetEvent
0x180018c0a  nop
0x180018c0b  lea     rax, WPP_GLOBAL_Control
0x180018c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c19  cmp     rcx, rax
0x180018c1c  jz      short loc_180018C46
0x180018c1e  test    dword ptr [rcx+1Ch], 800000h
0x180018c25  jz      short loc_180018C46
0x180018c27  mov     edx, 26h ; '&'
0x180018c2c  mov     rax, [rbx+20h]
0x180018c30  mov     [rsp+58h+var_38], rax
0x180018c35  mov     r9d, [rbp+0B0h]
0x180018c3c  mov     rcx, [rcx+10h]
0x180018c40  call    WPP_SF_dS
0x180018c45  nop
0x180018c46  xor     edx, edx
0x180018c48  mov     ecx, [rbp+0B0h]
0x180018c4e  call    SetServerInstallEntry
0x180018c53  mov     rcx, rbx; P
0x180018c56  call    FreeServerInstallEntry
0x180018c5b  nop
0x180018c5c  add     rsp, 48h
0x180018c60  pop     rbp
0x180018c61  pop     rbx
0x180018c62  retn
0x180018c64  push    rbp
0x180018c66  sub     rsp, 40h
0x180018c6a  mov     rbp, rdx
0x180018c6d  mov     rcx, cs:hMutex; hMutex
0x180018c74  call    cs:__imp_ReleaseMutex
0x180018c7a  nop
0x180018c7b  add     rsp, 40h
0x180018c7f  pop     rbp
0x180018c80  retn
```
