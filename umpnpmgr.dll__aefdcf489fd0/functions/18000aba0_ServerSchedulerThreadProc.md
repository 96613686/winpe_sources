# ServerSchedulerThreadProc

- ea: `0x18000aba0`
- end: `0x18000b105`
- name: `ServerSchedulerThreadProc`
- size: `1381`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800010e0`
- `0x1800086c0`
- `0x180009bc4`
- `0x18000a210`
- `0x18000a9e0`
- `0x18000aba0`
- `0x18000b10c`
- `0x1800117d4`
- `0x180011964`
- `0x180012058`
- `0x1800136f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ac30`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aecd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000af66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018db0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018dce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ac30`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aecd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000af66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018db0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018dce`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000acb9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000af8a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000acb9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000af8a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b04c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000b04c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000af32`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000af32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af95`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000ad54`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000ad54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000abff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ad20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ad29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ad20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ad29`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ae87`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ae87`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000ae2e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000ae2e`

## pseudocode

```c
__int64 __fastcall ServerSchedulerThreadProc(PVOID Parameter)
{
  int v1; // ecx
  DWORD v2; // r12d
  int v3; // r15d
  int v4; // r14d
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  PVOID *v7; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v9; // rax
  DWORD LastError; // eax
  _QWORD *v11; // rax
  void *v12; // rsi
  DWORD v13; // eax
  unsigned int i; // ebx
  int v15; // ecx
  DWORD v16; // eax
  DWORD v17; // eax
  _QWORD *v18; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  HANDLE TargetHandle; // [rsp+88h] [rbp+10h] BYREF

  TargetHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  pSetupBeginSynchronizedAccess(&Handles);
  PnpSchedulerThreadId = GetCurrentThreadId();
  ServerInstallBatchTotal = ServerInstallListSize;
  ServerInstallBatchComplete = 0;
  ServerInstallBatchTimeoutDetected = 0;
  ServerInstallUpdateStatus();
  ReleaseMutex(hMutex);
  if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v1, (int)SCHEDULER_START, PnpSchedulerThreadId);
  v2 = 0;
  v3 = 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
  {
    v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_d(v5, 42, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, CurrentThreadId);
  }
  while ( 1 )
  {
    WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
    if ( v4 || (v7 = (PVOID *)ServerInstallList, ServerInstallList == &ServerInstallList) )
    {
      if ( !(unsigned int)GetCurrentOutstandingServerThreads() )
      {
        v3 = 1;
        if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v15, (int)SCHEDULER_STOP, PnpSchedulerThreadId);
        PnpSchedulerThreadId = 0;
        SetEvent(PnpNoPendingInstallEvents);
        if ( ServerInstallList == &ServerInstallList )
        {
          ServerInstallBatchComplete = 0;
          ServerInstallBatchTotal = 0;
          ServerInstallBatchTimeoutDetected = 0;
          ServerInstallUpdateStatus();
        }
      }
    }
    else
    {
      while ( v7 != &ServerInstallList )
      {
        if ( ((_BYTE)v7[13] & 0x10) == 0
          && ((unsigned int)GetCurrentOutstandingServerThreads() < ServerInstallMaxThreads
           || (unsigned int)IsDeviceSpecial((__int64)v7))
          && !(unsigned int)IsDeviceChild((__int64)v7) )
        {
          CurrentProcess = GetCurrentProcess();
          v9 = GetCurrentProcess();
          if ( !DuplicateHandle(v9, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
          {
            LastError = GetLastError();
            v2 = LastError;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                43,
                WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
                LastError);
            break;
          }
          v11 = PnpHeapAlloc(0x10u);
          v12 = v11;
          if ( !v11 )
          {
            v13 = GetLastError();
            v2 = v13;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v13);
            break;
          }
          v11[1] = v7;
          *v11 = TargetHandle;
          for ( i = 0; i <= 0xA; Sleep(1000 * i) )
          {
            if ( QueueUserWorkItem((LPTHREAD_START_ROUTINE)ServerInstallThreadProc, v12, 0x10u) )
            {
              *((_DWORD *)v7 + 26) |= 0x10u;
              if ( (unsigned int)IsDeviceSpecial((__int64)v7) )
                --ServerInstallSpecialDeviceCount;
              --ServerInstallListSize;
              v2 = 0;
              pSetupBeginSynchronizedAccess(&qword_1800239B0);
              ++ServerInstallThreadTotal;
              ReleaseMutex(qword_1800239B8);
              break;
            }
            v2 = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, i, v2);
            ++i;
          }
        }
        if ( (unsigned int)GetCurrentOutstandingServerThreads() >= ServerInstallMaxThreads
          && !ServerInstallSpecialDeviceCount )
        {
          break;
        }
        v7 = (PVOID *)*v7;
      }
    }
    ReleaseMutex(hMutex);
    if ( v3 )
      goto LABEL_48;
    v16 = WaitForMultipleObjectsEx(3u, &SchedulerWaitEvents, 0, 0xFFFFFFFF, 0);
    if ( v16 == -1 )
      break;
    if ( v16 == 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
      }
      ResetEvent(hObject);
    }
    else if ( v16 == 2 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        v21 = 48;
        goto LABEL_70;
      }
    }
    else if ( v16 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
      {
        v21 = 50;
LABEL_70:
        WPP_SF_(v20[2], v21, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
      }
      v4 = 1;
    }
  }
  v17 = GetLastError();
  v2 = v17;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v17);
LABEL_48:
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x10000000) != 0 )
    WPP_SF_(v18[2], 51, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x18000aba0  mov     [rsp+arg_0], rbx
0x18000aba5  mov     [rsp+arg_10], rsi
0x18000abaa  push    rdi
0x18000abab  push    r12
0x18000abad  push    r13
0x18000abaf  push    r14
0x18000abb1  push    r15
0x18000abb3  sub     rsp, 50h
0x18000abb7  xor     esi, esi
0x18000abb9  mov     [rsp+78h+TargetHandle], rsi
0x18000abc1  lea     rdi, WPP_GLOBAL_Control
0x18000abc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abcf  cmp     rcx, rdi
0x18000abd2  jz      short loc_18000ABF2
0x18000abd4  test    dword ptr [rcx+1Ch], 10000000h
0x18000abdb  jz      short loc_18000ABF2
0x18000abdd  mov     edx, 29h ; ')'
0x18000abe2  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000abe9  mov     rcx, [rcx+10h]
0x18000abed  call    WPP_SF_
0x18000abf2  lea     rcx, Handles; lpHandles
0x18000abf9  call    pSetupBeginSynchronizedAccess
0x18000abfe  nop
0x18000abff  call    cs:__imp_GetCurrentThreadId
0x18000ac05  mov     cs:PnpSchedulerThreadId, eax
0x18000ac0b  mov     eax, cs:ServerInstallListSize
0x18000ac11  mov     cs:ServerInstallBatchTotal, eax
0x18000ac17  mov     cs:ServerInstallBatchComplete, esi
0x18000ac1d  mov     cs:ServerInstallBatchTimeoutDetected, esi
0x18000ac23  call    ServerInstallUpdateStatus
0x18000ac28  nop
0x18000ac29  mov     rcx, cs:hMutex; hMutex
0x18000ac30  call    cs:__imp_ReleaseMutex
0x18000ac36  test    cs:Microsoft_Windows_UserPnpEnableBits, 1
0x18000ac3d  jz      short loc_18000AC52
0x18000ac3f  mov     r8d, cs:PnpSchedulerThreadId
0x18000ac46  lea     rdx, SCHEDULER_START
0x18000ac4d  call    McTemplateU0q_EtwEventWriteTransfer
0x18000ac52  mov     r12d, esi
0x18000ac55  mov     r15d, esi
0x18000ac58  mov     r14d, esi
0x18000ac5b  mov     rbx, cs:WPP_GLOBAL_Control
0x18000ac62  cmp     rbx, rdi
0x18000ac65  jz      short loc_18000AC91
0x18000ac67  test    dword ptr [rbx+1Ch], 800000h
0x18000ac6e  jz      short loc_18000AC91
0x18000ac70  mov     rbx, [rbx+10h]
0x18000ac74  call    cs:__imp_GetCurrentThreadId
0x18000ac7a  mov     r9d, eax
0x18000ac7d  mov     edx, 2Ah ; '*'
0x18000ac82  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000ac89  mov     rcx, rbx
0x18000ac8c  call    WPP_SF_d
0x18000ac91  lea     r13, ServerInstallList
0x18000ac98  nop     dword ptr [rax+rax+00000000h]
0x18000aca0  mov     [rsp+78h+bAlertable], esi; bAlertable
0x18000aca4  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000acaa  xor     r8d, r8d; bWaitAll
0x18000acad  lea     rdx, Handles; lpHandles
0x18000acb4  mov     ecx, 2; nCount
0x18000acb9  call    cs:__imp_WaitForMultipleObjectsEx
0x18000acbf  nop
0x18000acc0  test    r14d, r14d
0x18000acc3  jnz     loc_18000AEF5
0x18000acc9  mov     rdi, cs:ServerInstallList
0x18000acd0  cmp     rdi, r13
0x18000acd3  jz      loc_18000AEF5
0x18000acd9  nop     dword ptr [rax+00000000h]
0x18000ace0  cmp     rdi, r13
0x18000ace3  jz      loc_18000AF58
0x18000ace9  test    byte ptr [rdi+68h], 10h
0x18000aced  jnz     loc_18000AED7
0x18000acf3  call    GetCurrentOutstandingServerThreads
0x18000acf8  cmp     eax, cs:ServerInstallMaxThreads
0x18000acfe  jb      short loc_18000AD10
0x18000ad00  mov     rcx, rdi
0x18000ad03  call    IsDeviceSpecial
0x18000ad08  test    eax, eax
0x18000ad0a  jz      loc_18000AED7
0x18000ad10  mov     rcx, rdi
0x18000ad13  call    IsDeviceChild
0x18000ad18  test    eax, eax
0x18000ad1a  jnz     loc_18000AED7
0x18000ad20  call    cs:__imp_GetCurrentProcess
0x18000ad26  mov     rbx, rax
0x18000ad29  call    cs:__imp_GetCurrentProcess
0x18000ad2f  mov     rcx, rax; hSourceProcessHandle
0x18000ad32  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18000ad3a  mov     [rsp+78h+bInheritHandle], esi; bInheritHandle
0x18000ad3e  mov     [rsp+78h+bAlertable], esi; dwDesiredAccess
0x18000ad42  lea     r9, [rsp+78h+TargetHandle]; lpTargetHandle
0x18000ad4a  mov     r8, rbx; hTargetProcessHandle
0x18000ad4d  mov     rdx, cs:hSourceHandle; hSourceHandle
0x18000ad54  call    cs:__imp_DuplicateHandle
0x18000ad5a  test    eax, eax
0x18000ad5c  jnz     short loc_18000ADA9
0x18000ad5e  call    cs:__imp_GetLastError
0x18000ad64  mov     r12d, eax
0x18000ad67  mov     [rsp+78h+var_38], eax
0x18000ad6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad72  lea     rbx, WPP_GLOBAL_Control
0x18000ad79  cmp     rcx, rbx
0x18000ad7c  jz      loc_18000AF5F
0x18000ad82  test    byte ptr [rcx+1Ch], 1
0x18000ad86  jz      loc_18000AF5F
0x18000ad8c  mov     edx, 2Bh ; '+'
0x18000ad91  mov     r9d, eax
0x18000ad94  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000ad9b  mov     rcx, [rcx+10h]
0x18000ad9f  call    WPP_SF_d
0x18000ada4  jmp     loc_18000AF5F
0x18000ada9  mov     ecx, 10h
0x18000adae  call    PnpHeapAlloc
0x18000adb3  mov     rsi, rax
0x18000adb6  test    rax, rax
0x18000adb9  jnz     short loc_18000AE00
0x18000adbb  call    cs:__imp_GetLastError
0x18000adc1  mov     r12d, eax
0x18000adc4  mov     [rsp+78h+var_38], eax
0x18000adc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adcf  lea     rbx, WPP_GLOBAL_Control
0x18000add6  cmp     rcx, rbx
0x18000add9  jz      short loc_18000ADF9
0x18000addb  test    byte ptr [rcx+1Ch], 1
0x18000addf  jz      short loc_18000ADF9
0x18000ade1  mov     edx, 2Ch ; ','
0x18000ade6  mov     r9d, eax
0x18000ade9  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000adf0  mov     rcx, [rcx+10h]
0x18000adf4  call    WPP_SF_d
0x18000adf9  xor     esi, esi
0x18000adfb  jmp     loc_18000AF5F
0x18000ae00  mov     [rax+8], rdi
0x18000ae04  mov     rax, [rsp+78h+TargetHandle]
0x18000ae0c  mov     [rsi], rax
0x18000ae0f  xor     ebx, ebx
0x18000ae11  mov     [rsp+78h+var_34], ebx
0x18000ae15  cmp     ebx, 0Ah
0x18000ae18  ja      loc_18000AED5
0x18000ae1e  mov     r8d, 10h; Flags
0x18000ae24  mov     rdx, rsi; Context
0x18000ae27  lea     rcx, ServerInstallThreadProc; Function
0x18000ae2e  call    cs:__imp_QueueUserWorkItem
0x18000ae34  test    eax, eax
0x18000ae36  jnz     short loc_18000AE8F
0x18000ae38  call    cs:__imp_GetLastError
0x18000ae3e  mov     r12d, eax
0x18000ae41  mov     [rsp+78h+var_38], eax
0x18000ae45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae4c  lea     rax, WPP_GLOBAL_Control
0x18000ae53  cmp     rcx, rax
0x18000ae56  jz      short loc_18000AE7B
0x18000ae58  test    byte ptr [rcx+1Ch], 1
0x18000ae5c  jz      short loc_18000AE7B
0x18000ae5e  mov     edx, 2Dh ; '-'
0x18000ae63  mov     [rsp+78h+bAlertable], r12d
0x18000ae68  mov     r9d, ebx
0x18000ae6b  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000ae72  mov     rcx, [rcx+10h]
0x18000ae76  call    WPP_SF_dd
0x18000ae7b  inc     ebx
0x18000ae7d  mov     [rsp+78h+var_34], ebx
0x18000ae81  imul    ecx, ebx, 3E8h; dwMilliseconds
0x18000ae87  call    cs:__imp_Sleep
0x18000ae8d  jmp     short loc_18000AE15
0x18000ae8f  or      dword ptr [rdi+68h], 10h
0x18000ae93  mov     rcx, rdi
0x18000ae96  call    IsDeviceSpecial
0x18000ae9b  test    eax, eax
0x18000ae9d  jz      short loc_18000AEA5
0x18000ae9f  dec     cs:ServerInstallSpecialDeviceCount
0x18000aea5  dec     cs:ServerInstallListSize
0x18000aeab  xor     esi, esi
0x18000aead  mov     r12d, esi
0x18000aeb0  mov     [rsp+78h+var_38], esi
0x18000aeb4  lea     rcx, qword_1800239B0; lpHandles
0x18000aebb  call    pSetupBeginSynchronizedAccess
0x18000aec0  inc     cs:ServerInstallThreadTotal
0x18000aec6  mov     rcx, cs:qword_1800239B8; hMutex
0x18000aecd  call    cs:__imp_ReleaseMutex
0x18000aed3  jmp     short loc_18000AED7
0x18000aed5  xor     esi, esi
0x18000aed7  call    GetCurrentOutstandingServerThreads
0x18000aedc  cmp     eax, cs:ServerInstallMaxThreads
0x18000aee2  jb      short loc_18000AEED
0x18000aee4  cmp     cs:ServerInstallSpecialDeviceCount, 0
0x18000aeeb  jbe     short loc_18000AF58
0x18000aeed  mov     rdi, [rdi]
0x18000aef0  jmp     loc_18000ACE0
0x18000aef5  call    GetCurrentOutstandingServerThreads
0x18000aefa  test    eax, eax
0x18000aefc  jnz     short loc_18000AF58
0x18000aefe  mov     r15d, 1
0x18000af04  mov     [rsp+78h+var_30], r15d
0x18000af09  test    cs:Microsoft_Windows_UserPnpEnableBits, r15b
0x18000af10  jz      short loc_18000AF25
0x18000af12  mov     r8d, cs:PnpSchedulerThreadId
0x18000af19  lea     rdx, SCHEDULER_STOP
0x18000af20  call    McTemplateU0q_EtwEventWriteTransfer
0x18000af25  mov     cs:PnpSchedulerThreadId, esi
0x18000af2b  mov     rcx, cs:PnpNoPendingInstallEvents; hEvent
0x18000af32  call    cs:__imp_SetEvent
0x18000af38  cmp     cs:ServerInstallList, r13
0x18000af3f  jnz     short loc_18000AF58
0x18000af41  mov     cs:ServerInstallBatchComplete, esi
0x18000af47  mov     cs:ServerInstallBatchTotal, esi
0x18000af4d  mov     cs:ServerInstallBatchTimeoutDetected, esi
0x18000af53  call    ServerInstallUpdateStatus
0x18000af58  lea     rbx, WPP_GLOBAL_Control
0x18000af5f  mov     rcx, cs:hMutex; hMutex
0x18000af66  call    cs:__imp_ReleaseMutex
0x18000af6c  test    r15d, r15d
0x18000af6f  jnz     short loc_18000AFC8
0x18000af71  mov     [rsp+78h+bAlertable], esi; bAlertable
0x18000af75  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000af7b  xor     r8d, r8d; bWaitAll
0x18000af7e  lea     rdx, SchedulerWaitEvents; lpHandles
0x18000af85  mov     ecx, 3; nCount
0x18000af8a  call    cs:__imp_WaitForMultipleObjectsEx
0x18000af90  cmp     eax, 0FFFFFFFFh
0x18000af93  jnz     short loc_18000B00F
0x18000af95  call    cs:__imp_GetLastError
0x18000af9b  mov     r12d, eax
0x18000af9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afa5  cmp     rcx, rbx
0x18000afa8  jz      short loc_18000AFF2
0x18000afaa  test    byte ptr [rcx+1Ch], 1
0x18000afae  jz      short loc_18000AFCF
0x18000afb0  mov     edx, 2Eh ; '.'
0x18000afb5  mov     r9d, eax
0x18000afb8  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000afbf  mov     rcx, [rcx+10h]
0x18000afc3  call    WPP_SF_d
0x18000afc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afcf  cmp     rcx, rbx
0x18000afd2  jz      short loc_18000AFF2
0x18000afd4  test    dword ptr [rcx+1Ch], 10000000h
0x18000afdb  jz      short loc_18000AFF2
0x18000afdd  mov     edx, 33h ; '3'
0x18000afe2  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000afe9  mov     rcx, [rcx+10h]
0x18000afed  call    WPP_SF_
0x18000aff2  mov     eax, r12d
0x18000aff5  lea     r11, [rsp+78h+var_28]
0x18000affa  mov     rbx, [r11+30h]
0x18000affe  mov     rsi, [r11+40h]
0x18000b002  mov     rsp, r11
0x18000b005  pop     r15
0x18000b007  pop     r14
0x18000b009  pop     r13
0x18000b00b  pop     r12
0x18000b00d  pop     rdi
0x18000b00e  retn
0x18000b00f  cmp     eax, 1
0x18000b012  jnz     short loc_18000B057
0x18000b014  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b01b  lea     rdi, WPP_GLOBAL_Control
0x18000b022  cmp     rcx, rdi
0x18000b025  jz      short loc_18000B045
0x18000b027  test    dword ptr [rcx+1Ch], 400000h
0x18000b02e  jz      short loc_18000B045
0x18000b030  mov     edx, 2Fh ; '/'
0x18000b035  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000b03c  mov     rcx, [rcx+10h]
0x18000b040  call    WPP_SF_
0x18000b045  mov     rcx, cs:hObject; hEvent
0x18000b04c  call    cs:__imp_ResetEvent
0x18000b052  jmp     loc_18000ACA0
0x18000b057  cmp     eax, 2
0x18000b05a  jnz     short loc_18000B087
0x18000b05c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b063  lea     rax, WPP_GLOBAL_Control
0x18000b06a  cmp     rcx, rax
0x18000b06d  jz      loc_18000ACA0
0x18000b073  test    dword ptr [rcx+1Ch], 400000h
0x18000b07a  jz      loc_18000ACA0
0x18000b080  mov     edx, 30h ; '0'
0x18000b085  jmp     short loc_18000B0F0
0x18000b087  test    eax, eax
0x18000b089  jnz     short loc_18000B0C7
0x18000b08b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b092  lea     rax, WPP_GLOBAL_Control
0x18000b099  cmp     rcx, rax
0x18000b09c  jz      short loc_18000B0BC
0x18000b09e  test    dword ptr [rcx+1Ch], 400000h
0x18000b0a5  jz      short loc_18000B0BC
0x18000b0a7  mov     edx, 31h ; '1'
0x18000b0ac  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000b0b3  mov     rcx, [rcx+10h]
0x18000b0b7  call    WPP_SF_
0x18000b0bc  mov     r14d, 1
0x18000b0c2  jmp     loc_18000ACA0
0x18000b0c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0ce  lea     rax, WPP_GLOBAL_Control
0x18000b0d5  cmp     rcx, rax
0x18000b0d8  jz      loc_18000ACA0
0x18000b0de  test    dword ptr [rcx+1Ch], 100000h
0x18000b0e5  jz      loc_18000ACA0
0x18000b0eb  mov     edx, 32h ; '2'
0x18000b0f0  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
  ... truncated ...
```
