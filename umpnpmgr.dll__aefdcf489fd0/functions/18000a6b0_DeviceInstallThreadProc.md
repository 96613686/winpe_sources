# DeviceInstallThreadProc

- ea: `0x18000a6b0`
- end: `0x18000a9d8`
- name: `DeviceInstallThreadProc`
- size: `808`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800083b0`
- `0x18000a6b0`
- `0x18000a9e0`
- `0x18001078c`
- `0x180011964`
- `0x180011df0`
- `0x180011e44`
- `0x180011ef8`
- `0x180012004`
- `0x180013a40`
- `0x180013ad0`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a801`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a916`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a801`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a916`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d60`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018d7e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a7cb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a8ce`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a7cb`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a8ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a9a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a9a4`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18000a838`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18000a838`

## pseudocode

```c
__int64 __fastcall DeviceInstallThreadProc(PVOID Parameter)
{
  unsigned int started; // eax
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  DWORD LastError; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  _DWORD v9[104]; // [rsp+30h] [rbp-1B8h] BYREF

  memset_0(v9, 0, sizeof(v9));
  if ( (PnpGlobalFlags & 4) == 0 )
  {
    started = WaitForScAutoStartEvent();
    if ( started )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, started);
    }
  }
  if ( !PnpInstallThreadExit )
  {
    if ( (PnpGlobalFlags & 0xB) != 0
      && (unsigned int)IsSysprepPresent()
      && (!(unsigned int)IsSysprepComplete() || (PnpGlobalFlags & 8) != 0)
      && !(unsigned int)IsSysprepInVmMode()
      && !(unsigned int)IsMiniNT() )
    {
      v2 = WaitForSetupEvent();
      if ( v2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v2);
      }
    }
    if ( !PnpInstallThreadExit )
    {
      WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
      ServerInstallProcessingEnabled = 1;
      ServerInstallBatchComplete = 0;
      ServerInstallBatchTotal = ServerInstallListSize;
      ServerInstallBatchTimeoutDetected = 0;
      ServerInstallUpdateStatus();
      ReleaseMutex(hMutex);
      v9[0] = 416;
      v9[2] = 2;
      v9[1] = 2;
      v9[3] = 0;
      v3 = CM_Register_Notification(v9, 0, DeviceNotifyCallback, &PnpNotifyHandle);
      if ( v3 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v3);
      if ( (PnpGlobalFlags & 2) == 0 )
      {
        v4 = QueueInstallForAllDevices();
        if ( v4 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v4);
        }
      }
      if ( !PnpInstallThreadExit )
      {
        WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
        if ( !(unsigned int)QueueServerInstallWorkItem() )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              63,
              WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids,
              LastError);
        }
        ReleaseMutex(hMutex);
        if ( !PnpInstallThreadExit && (PnpGlobalFlags & 4) != 0 )
        {
          v6 = WaitForScAutoStartEvent();
          if ( v6
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v6);
          }
          if ( !PnpInstallThreadExit )
          {
            v7 = QueueInstallForAllDevices();
            if ( v7 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, v7);
              }
            }
          }
        }
      }
    }
  }
  CloseHandle(PnpInstallThread);
  PnpInstallThread = (HANDLE)-1LL;
  return 0;
}

```

## disassembly

```asm
0x18000a6b0  mov     [rsp+arg_0], rbx
0x18000a6b5  push    rdi
0x18000a6b6  sub     rsp, 1E0h
0x18000a6bd  mov     rax, cs:__security_cookie
0x18000a6c4  xor     rax, rsp
0x18000a6c7  mov     [rsp+1E8h+var_18], rax
0x18000a6cf  xor     edx, edx; Val
0x18000a6d1  mov     r8d, 1A0h; Size
0x18000a6d7  lea     rcx, [rsp+1E8h+var_1B8]; void *
0x18000a6dc  call    memset_0
0x18000a6e1  test    byte ptr cs:PnpGlobalFlags, 4
0x18000a6e8  jnz     short loc_18000A726
0x18000a6ea  call    WaitForScAutoStartEvent
0x18000a6ef  test    eax, eax
0x18000a6f1  jz      short loc_18000A726
0x18000a6f3  lea     rbx, WPP_GLOBAL_Control
0x18000a6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a701  cmp     rcx, rbx
0x18000a704  jz      short loc_18000A72D
0x18000a706  test    byte ptr [rcx+1Ch], 1
0x18000a70a  jz      short loc_18000A72D
0x18000a70c  mov     edx, 3Bh ; ';'
0x18000a711  mov     r9d, eax
0x18000a714  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a71b  mov     rcx, [rcx+10h]
0x18000a71f  call    WPP_SF_d
0x18000a724  jmp     short loc_18000A72D
0x18000a726  lea     rbx, WPP_GLOBAL_Control
0x18000a72d  cmp     cs:PnpInstallThreadExit, 0
0x18000a734  jnz     loc_18000A99D
0x18000a73a  test    byte ptr cs:PnpGlobalFlags, 0Bh
0x18000a741  jz      short loc_18000A7A3
0x18000a743  call    IsSysprepPresent
0x18000a748  test    eax, eax
0x18000a74a  jz      short loc_18000A7A3
0x18000a74c  call    IsSysprepComplete
0x18000a751  test    eax, eax
0x18000a753  jz      short loc_18000A75E
0x18000a755  test    byte ptr cs:PnpGlobalFlags, 8
0x18000a75c  jz      short loc_18000A7A3
0x18000a75e  call    IsSysprepInVmMode
0x18000a763  test    eax, eax
0x18000a765  jnz     short loc_18000A7A3
0x18000a767  call    IsMiniNT
0x18000a76c  test    eax, eax
0x18000a76e  jnz     short loc_18000A7A3
0x18000a770  call    WaitForSetupEvent
0x18000a775  test    eax, eax
0x18000a777  jz      short loc_18000A7A3
0x18000a779  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a780  cmp     rcx, rbx
0x18000a783  jz      short loc_18000A7A3
0x18000a785  test    byte ptr [rcx+1Ch], 1
0x18000a789  jz      short loc_18000A7A3
0x18000a78b  mov     edx, 3Ch ; '<'
0x18000a790  mov     r9d, eax
0x18000a793  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a79a  mov     rcx, [rcx+10h]
0x18000a79e  call    WPP_SF_d
0x18000a7a3  cmp     cs:PnpInstallThreadExit, 0
0x18000a7aa  jnz     loc_18000A99D
0x18000a7b0  xor     edi, edi
0x18000a7b2  mov     [rsp+1E8h+bAlertable], edi; bAlertable
0x18000a7b6  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000a7bc  xor     r8d, r8d; bWaitAll
0x18000a7bf  lea     rdx, Handles; lpHandles
0x18000a7c6  mov     ecx, 2; nCount
0x18000a7cb  call    cs:__imp_WaitForMultipleObjectsEx
0x18000a7d1  nop
0x18000a7d2  mov     cs:ServerInstallProcessingEnabled, 1
0x18000a7dc  mov     cs:ServerInstallBatchComplete, edi
0x18000a7e2  mov     eax, cs:ServerInstallListSize
0x18000a7e8  mov     cs:ServerInstallBatchTotal, eax
0x18000a7ee  mov     cs:ServerInstallBatchTimeoutDetected, edi
0x18000a7f4  call    ServerInstallUpdateStatus
0x18000a7f9  nop
0x18000a7fa  mov     rcx, cs:hMutex; hMutex
0x18000a801  call    cs:__imp_ReleaseMutex
0x18000a807  mov     [rsp+1E8h+var_1B8], 1A0h
0x18000a80f  mov     [rsp+1E8h+var_1B0], 2
0x18000a817  mov     [rsp+1E8h+var_1B4], 2
0x18000a81f  mov     [rsp+1E8h+var_1AC], edi
0x18000a823  lea     r9, PnpNotifyHandle
0x18000a82a  lea     r8, DeviceNotifyCallback
0x18000a831  xor     edx, edx
0x18000a833  lea     rcx, [rsp+1E8h+var_1B8]
0x18000a838  call    cs:__imp_CM_Register_Notification
0x18000a83e  test    eax, eax
0x18000a840  jz      short loc_18000A86C
0x18000a842  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a849  cmp     rcx, rbx
0x18000a84c  jz      short loc_18000A86C
0x18000a84e  test    byte ptr [rcx+1Ch], 1
0x18000a852  jz      short loc_18000A86C
0x18000a854  mov     edx, 3Dh ; '='
0x18000a859  mov     r9d, eax
0x18000a85c  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a863  mov     rcx, [rcx+10h]
0x18000a867  call    WPP_SF_d
0x18000a86c  test    byte ptr cs:PnpGlobalFlags, 2
0x18000a873  jnz     short loc_18000A8A8
0x18000a875  call    QueueInstallForAllDevices
0x18000a87a  test    eax, eax
0x18000a87c  jz      short loc_18000A8A8
0x18000a87e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a885  cmp     rcx, rbx
0x18000a888  jz      short loc_18000A8A8
0x18000a88a  test    byte ptr [rcx+1Ch], 1
0x18000a88e  jz      short loc_18000A8A8
0x18000a890  mov     edx, 3Eh ; '>'
0x18000a895  mov     r9d, eax
0x18000a898  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a89f  mov     rcx, [rcx+10h]
0x18000a8a3  call    WPP_SF_d
0x18000a8a8  cmp     cs:PnpInstallThreadExit, 0
0x18000a8af  jnz     loc_18000A99D
0x18000a8b5  mov     [rsp+1E8h+bAlertable], edi; bAlertable
0x18000a8b9  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000a8bf  xor     r8d, r8d; bWaitAll
0x18000a8c2  lea     rdx, Handles; lpHandles
0x18000a8c9  mov     ecx, 2; nCount
0x18000a8ce  call    cs:__imp_WaitForMultipleObjectsEx
0x18000a8d4  nop
0x18000a8d5  call    QueueServerInstallWorkItem
0x18000a8da  test    eax, eax
0x18000a8dc  jnz     short loc_18000A90F
0x18000a8de  call    cs:__imp_GetLastError
0x18000a8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8eb  cmp     rcx, rbx
0x18000a8ee  jz      short loc_18000A90F
0x18000a8f0  test    byte ptr [rcx+1Ch], 1
0x18000a8f4  jz      short loc_18000A90F
0x18000a8f6  mov     edx, 3Fh ; '?'
0x18000a8fb  mov     r9d, eax
0x18000a8fe  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a905  mov     rcx, [rcx+10h]
0x18000a909  call    WPP_SF_d
0x18000a90e  nop
0x18000a90f  mov     rcx, cs:hMutex; hMutex
0x18000a916  call    cs:__imp_ReleaseMutex
0x18000a91c  cmp     cs:PnpInstallThreadExit, 0
0x18000a923  jnz     short loc_18000A99D
0x18000a925  test    byte ptr cs:PnpGlobalFlags, 4
0x18000a92c  jz      short loc_18000A99D
0x18000a92e  call    WaitForScAutoStartEvent
0x18000a933  test    eax, eax
0x18000a935  jz      short loc_18000A961
0x18000a937  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a93e  cmp     rcx, rbx
0x18000a941  jz      short loc_18000A961
0x18000a943  test    byte ptr [rcx+1Ch], 1
0x18000a947  jz      short loc_18000A961
0x18000a949  mov     edx, 40h ; '@'
0x18000a94e  mov     r9d, eax
0x18000a951  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a958  mov     rcx, [rcx+10h]
0x18000a95c  call    WPP_SF_d
0x18000a961  cmp     cs:PnpInstallThreadExit, 0
0x18000a968  jnz     short loc_18000A99D
0x18000a96a  call    QueueInstallForAllDevices
0x18000a96f  test    eax, eax
0x18000a971  jz      short loc_18000A99D
0x18000a973  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a97a  cmp     rcx, rbx
0x18000a97d  jz      short loc_18000A99D
0x18000a97f  test    byte ptr [rcx+1Ch], 1
0x18000a983  jz      short loc_18000A99D
0x18000a985  mov     edx, 41h ; 'A'
0x18000a98a  mov     r9d, eax
0x18000a98d  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x18000a994  mov     rcx, [rcx+10h]
0x18000a998  call    WPP_SF_d
0x18000a99d  mov     rcx, cs:PnpInstallThread; hObject
0x18000a9a4  call    cs:__imp_CloseHandle
0x18000a9aa  mov     cs:PnpInstallThread, 0FFFFFFFFFFFFFFFFh
0x18000a9b5  xor     eax, eax
0x18000a9b7  mov     rcx, [rsp+1E8h+var_18]
0x18000a9bf  xor     rcx, rsp; StackCookie
0x18000a9c2  call    __security_check_cookie
0x18000a9c7  mov     rbx, [rsp+1E8h+arg_0]
0x18000a9cf  add     rsp, 1E0h
0x18000a9d6  pop     rdi
0x18000a9d7  retn
0x180018d50  push    rbp
0x180018d52  sub     rsp, 30h
0x180018d56  mov     rbp, rdx
0x180018d59  mov     rcx, cs:hMutex; hMutex
0x180018d60  call    cs:__imp_ReleaseMutex
0x180018d66  nop
0x180018d67  add     rsp, 30h
0x180018d6b  pop     rbp
0x180018d6c  retn
0x180018d6e  push    rbp
0x180018d70  sub     rsp, 30h
0x180018d74  mov     rbp, rdx
0x180018d77  mov     rcx, cs:hMutex; hMutex
0x180018d7e  call    cs:__imp_ReleaseMutex
0x180018d84  nop
0x180018d85  add     rsp, 30h
0x180018d89  pop     rbp
0x180018d8a  retn
```
