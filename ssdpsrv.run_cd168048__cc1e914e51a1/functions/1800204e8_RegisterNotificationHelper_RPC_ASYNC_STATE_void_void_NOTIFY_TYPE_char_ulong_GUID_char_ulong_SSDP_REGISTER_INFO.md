# _RegisterNotificationHelper(_RPC_ASYNC_STATE *,void * *,void *,_NOTIFY_TYPE,char *,ulong,_GUID,char *,ulong,_SSDP_REGISTER_INFO * *)

- ea: `0x1800204e8`
- end: `0x1800208f7`
- name: `?_RegisterNotificationHelper@@YAHPEAU_RPC_ASYNC_STATE@@PEAPEAXPEAXW4_NOTIFY_TYPE@@PEADKU_GUID@@4KPEAPEAU_SSDP_REGISTER_INFO@@@Z`
- size: `1039`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180020410`
- `0x180020480`

## callees

- `0x18000a934`
- `0x18001af78`
- `0x18001b1a8`
- `0x18001dc44`
- `0x1800204e8`
- `0x1800244b8`
- `0x1800271fc`
- `0x18002e8ac`
- `0x18002e8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020780`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020780`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180020637`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180020637`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002082f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002082f`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180020683`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180020683`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180020766`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180020766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800206e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020809`

## string_xrefs

- `0x180020715`: `_RegisterNotificationAsyncRpc: CreateHandleFailed`
- `0x180020867`: `_RegisterNotificationAsyncRpc: Failed to complete the RPC call.`

## pseudocode

```c
__int64 __fastcall _RegisterNotificationHelper(
        struct _RPC_ASYNC_STATE *a1,
        void **a2,
        void *a3,
        int a4,
        char *a5,
        unsigned int a6,
        struct _GUID *a7,
        __int64 a8,
        unsigned int a9,
        __int64 a10)
{
  int v14; // ebx
  void *v15; // r15
  HANDLE EventA; // rax
  void *v17; // rcx
  void *RuntimeInfo; // rcx
  RPC_STATUS v19; // eax
  LPCSTR v20; // rcx
  int v21; // edx
  const char *v22; // r9
  signed int LastError; // eax
  signed int v24; // eax
  LPCSTR v25; // rcx
  unsigned int Reply; // [rsp+40h] [rbp-61h] BYREF
  unsigned int NotificationsQueued[3]; // [rsp+44h] [rbp-5Dh] BYREF
  struct _GUID v29; // [rsp+50h] [rbp-51h] BYREF
  __int128 v30; // [rsp+60h] [rbp-41h] BYREF
  void *v31; // [rsp+70h] [rbp-31h]
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+78h] [rbp-29h] BYREF

  Reply = 0;
  v31 = 0;
  memset(&NotificationInfo, 0, sizeof(NotificationInfo));
  NotificationsQueued[0] = 0;
  v30 = 0;
  if ( a2
    && a3
    && a10
    && (unsigned int)CSsdpNotifyRequestManager::IsNotifySemaphoreInList(&CSsdpNotifyRequestManager::s_instance, 1) )
  {
    *a2 = 0;
    v14 = 0;
    if ( !a4 )
    {
      if ( a5 )
      {
        v29 = *a7;
        Reply = CSsdpNotifyRequestManager::HrCreateAliveNotifyRequest(
                  (CSsdpNotifyRequestManager *)&CSsdpNotifyRequestManager::s_instance,
                  a2,
                  a5,
                  a6,
                  &v29,
                  a3,
                  a9);
      }
      goto LABEL_44;
    }
    if ( a4 != 1 || !a8 )
      goto LABEL_44;
    *(_QWORD *)&v29.Data1 = 0;
    Reply = CSsdpNotifyRequestManager::HrBeginPropChangeNotifyRequest(
              (CSsdpNotifyRequestManager *)&CSsdpNotifyRequestManager::s_instance,
              a3,
              a9);
    if ( Reply )
    {
LABEL_42:
      if ( *(_QWORD *)&v29.Data1 )
        CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(*(void **)&v29.Data1);
LABEL_44:
      if ( a1 )
        v14 = RpcAsyncCompleteCall(a1, &Reply);
      if ( v14 )
      {
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        Reply = v14;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
          return (unsigned __int16)Reply;
        if ( (WPP_GLOBAL_Control[28] & 1) == 0 )
        {
LABEL_53:
          if ( v25 != (LPCSTR)&WPP_GLOBAL_Control && (v25[28] & 8) != 0 )
            WPP_SF_d(*((_QWORD *)v25 + 2), 30, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids, Reply);
          return (unsigned __int16)Reply;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)WPP_1b47134a19a23ae61e8d70f792424297_Traceguids,
          (unsigned int)"_RegisterNotificationAsyncRpc: Failed to complete the RPC call.",
          v14);
      }
      v25 = WPP_GLOBAL_Control;
      goto LABEL_53;
    }
    v15 = 0;
    *a2 = (void *)(*(_QWORD *)&v29.Data1 + 8LL);
    if ( a1 )
    {
      EventA = CreateEventA(0, 0, 0, 0);
      v15 = EventA;
      if ( EventA )
      {
        v17 = *a2;
        NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CSsdpNotifyRequestManager::RPCCleanupNotification;
        *(_QWORD *)&v30 = v17;
        *((_QWORD *)&v30 + 1) = EventA;
        RuntimeInfo = a1->RuntimeInfo;
        v31 = a3;
        a1->UserInfo = &v30;
        v19 = RpcServerSubscribeForNotification(
                RuntimeInfo,
                RpcNotificationCallCancel,
                RpcNotificationTypeCallback,
                &NotificationInfo);
        v14 = v19;
        if ( v19 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
            goto LABEL_41;
          v21 = 28;
          v22 = "_RegisterNotificationAsyncRpc: Failed to subscribe RPC notification.";
LABEL_17:
          WPP_SF_sd(
            *((_QWORD *)v20 + 2),
            v21,
            (unsigned int)WPP_1b47134a19a23ae61e8d70f792424297_Traceguids,
            (_DWORD)v22,
            v19);
LABEL_41:
          CloseHandle(v15);
          goto LABEL_42;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Reply = LastError;
        if ( LastError && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_1b47134a19a23ae61e8d70f792424297_Traceguids,
            (unsigned int)"_RegisterNotificationAsyncRpc: CreateHandleFailed",
            LastError);
      }
    }
    Reply = CSsdpNotifyRequestManager::HrEndPropChangeNotifyRequest(&CSsdpNotifyRequestManager::s_instance, &v29, a10);
    if ( !a1 )
    {
      if ( !v15 )
        goto LABEL_42;
      goto LABEL_41;
    }
    if ( !v15 )
      goto LABEL_42;
    v14 = RpcServerUnsubscribeForNotification(a1->RuntimeInfo, RpcNotificationCallCancel, NotificationsQueued);
    if ( NotificationsQueued[0] )
    {
      v24 = WaitForSingleObject(v15, 0xFFFFFFFF);
      if ( v24 )
      {
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        Reply = v24;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
          goto LABEL_34;
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          (unsigned int)WPP_1b47134a19a23ae61e8d70f792424297_Traceguids,
          (unsigned int)"_RegisterNotificationAsyncRpc: Wait on Single Object Failed.",
          v24);
      }
    }
    v20 = WPP_GLOBAL_Control;
LABEL_34:
    if ( !v14 )
      goto LABEL_41;
    LOBYTE(v19) = v14;
    if ( v20 == (LPCSTR)&WPP_GLOBAL_Control || (v20[28] & 1) == 0 )
      goto LABEL_41;
    v22 = "_RegisterNotificationAsyncRpc: Failed to unsubscribe RPC notification.";
    v21 = 27;
    if ( v14 <= 0 )
      LOBYTE(v19) = v14;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids);
  return 87;
}

```

## disassembly

```asm
0x1800204e8  push    rbp
0x1800204ea  push    rbx
0x1800204eb  push    rsi
0x1800204ec  push    rdi
0x1800204ed  push    r12
0x1800204ef  push    r13
0x1800204f1  push    r14
0x1800204f3  push    r15
0x1800204f5  lea     rbp, [rsp-7]
0x1800204fa  sub     rsp, 0A8h
0x180020501  xor     edi, edi
0x180020503  xorps   xmm0, xmm0
0x180020506  xor     eax, eax
0x180020508  mov     [rbp+3Fh+Reply], edi
0x18002050b  mov     qword ptr [rbp+3Fh+NotificationInfo+18h], rax
0x18002050f  mov     r15d, r9d
0x180020512  mov     [rbp+3Fh+var_70], rax
0x180020516  mov     rsi, r8
0x180020519  mov     r12, rdx
0x18002051c  mov     qword ptr [rbp+3Fh+NotificationInfo], rdi
0x180020520  mov     r13, rcx
0x180020523  mov     [rbp+3Fh+NotificationsQueued], edi
0x180020526  movups  xmmword ptr [rbp+3Fh+NotificationInfo+8], xmm0
0x18002052a  movups  [rbp+3Fh+var_80], xmm0
0x18002052e  test    rdx, rdx
0x180020531  jz      loc_1800208AC
0x180020537  test    r8, r8
0x18002053a  jz      loc_1800208AC
0x180020540  cmp     [rbp+3Fh+arg_48], rdi
0x180020547  jz      loc_1800208AC
0x18002054d  lea     edx, [rdi+1]
0x180020550  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; CSsdpNotifyRequestManager CSsdpNotifyRequestManager::s_instance
0x180020557  call    ?IsNotifySemaphoreInList@CSsdpNotifyRequestManager@@QEAAHW4_List_TYPE@@PEAX@Z; CSsdpNotifyRequestManager::IsNotifySemaphoreInList(_List_TYPE,void *)
0x18002055c  test    eax, eax
0x18002055e  jz      loc_1800208AC
0x180020564  mov     [r12], rdi
0x180020568  mov     ebx, edi
0x18002056a  lea     rdi, WPP_GLOBAL_Control
0x180020571  lea     r14, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x180020578  test    r15d, r15d
0x18002057b  jnz     short loc_1800205C9
0x18002057d  mov     r8, [rbp+3Fh+arg_20]; char *
0x180020581  test    r8, r8
0x180020584  jz      loc_180020823
0x18002058a  mov     rax, [rbp+3Fh+arg_30]
0x18002058e  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x180020595  mov     r9d, [rbp+3Fh+arg_28]; unsigned int
0x180020599  mov     rdx, r12; void **
0x18002059c  movaps  xmm0, xmmword ptr [rax]
0x18002059f  mov     eax, [rbp+3Fh+arg_40]
0x1800205a5  mov     [rsp+0E0h+var_B0], eax; unsigned int
0x1800205a9  lea     rax, [rbp+3Fh+var_90]
0x1800205ad  mov     [rsp+0E0h+var_B8], rsi; void *
0x1800205b2  mov     [rsp+0E0h+var_C0], rax; struct _GUID
0x1800205b7  movdqa  xmmword ptr [rbp+3Fh+var_90.Data1], xmm0
0x1800205bc  call    ?HrCreateAliveNotifyRequest@CSsdpNotifyRequestManager@@QEAAJPEAPEAXPEBDKU_GUID@@PEAXK@Z; CSsdpNotifyRequestManager::HrCreateAliveNotifyRequest(void * *,char const *,ulong,_GUID,void *,ulong)
0x1800205c1  mov     [rbp+3Fh+Reply], eax
0x1800205c4  jmp     loc_180020823
0x1800205c9  cmp     r15d, 1
0x1800205cd  jnz     loc_180020823
0x1800205d3  mov     r8, [rbp+3Fh+arg_38]
0x1800205da  test    r8, r8
0x1800205dd  jz      loc_180020823
0x1800205e3  mov     eax, [rbp+3Fh+arg_40]
0x1800205e9  lea     rdx, [rbp+3Fh+var_90]
0x1800205ed  mov     r9d, [rbp+3Fh+arg_28]
0x1800205f1  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x1800205f8  mov     dword ptr [rsp+0E0h+var_B8], eax; unsigned int
0x1800205fc  mov     [rsp+0E0h+var_C0], rsi; void *
0x180020601  mov     qword ptr [rbp+3Fh+var_90.Data1], rbx
0x180020605  call    ?HrBeginPropChangeNotifyRequest@CSsdpNotifyRequestManager@@QEAAJAEAV?$CUList@VCSsdpNotifyRequest@@@@PEBDKPEAXK@Z; CSsdpNotifyRequestManager::HrBeginPropChangeNotifyRequest(CUList<CSsdpNotifyRequest> &,char const *,ulong,void *,ulong)
0x18002060a  mov     [rbp+3Fh+Reply], eax
0x18002060d  test    eax, eax
0x18002060f  jnz     loc_180020815
0x180020615  mov     rax, qword ptr [rbp+3Fh+var_90.Data1]
0x180020619  xor     r15d, r15d
0x18002061c  add     rax, 8
0x180020620  mov     [r12], rax
0x180020624  test    r13, r13
0x180020627  jz      loc_18002072D
0x18002062d  xor     r9d, r9d; lpName
0x180020630  xor     r8d, r8d; bInitialState
0x180020633  xor     edx, edx; bManualReset
0x180020635  xor     ecx, ecx; lpEventAttributes
0x180020637  call    cs:__imp_CreateEventA
0x18002063e  nop     dword ptr [rax+rax+00h]
0x180020643  mov     r15, rax
0x180020646  test    rax, rax
0x180020649  jz      loc_1800206E0
0x18002064f  mov     rcx, [r12]
0x180020653  lea     rax, ?RPCCleanupNotification@CSsdpNotifyRequestManager@@SAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z; CSsdpNotifyRequestManager::RPCCleanupNotification(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)
0x18002065a  mov     qword ptr [rbp+3Fh+NotificationInfo], rax
0x18002065e  mov     qword ptr [rbp+3Fh+var_80], rcx
0x180020662  mov     qword ptr [rbp+3Fh+var_80+8], r15
0x180020666  mov     rcx, [r13+20h]; Binding
0x18002066a  lea     rax, [rbp+3Fh+var_80]
0x18002066e  mov     edx, 2; Notification
0x180020673  mov     [rbp+3Fh+var_70], rsi
0x180020677  lea     r9, [rbp+3Fh+NotificationInfo]; NotificationInfo
0x18002067b  mov     [r13+18h], rax
0x18002067f  lea     r8d, [rdx+3]; NotificationType
0x180020683  call    cs:__imp_RpcServerSubscribeForNotification
0x18002068a  nop     dword ptr [rax+rax+00h]
0x18002068f  mov     ebx, eax
0x180020691  test    eax, eax
0x180020693  jz      loc_18002072D
0x180020699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206a0  cmp     rcx, rdi
0x1800206a3  jz      loc_180020806
0x1800206a9  test    byte ptr [rcx+1Ch], 1
0x1800206ad  jz      loc_180020806
0x1800206b3  test    eax, eax
0x1800206b5  jle     short loc_1800206BF
0x1800206b7  movzx   eax, ax
0x1800206ba  or      eax, 80070000h
0x1800206bf  mov     edx, 1Ch
0x1800206c4  lea     r9, aRegisternotifi_3; "_RegisterNotificationAsyncRpc: Failed t"...
0x1800206cb  mov     rcx, [rcx+10h]
0x1800206cf  mov     r8, r14
0x1800206d2  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800206d6  call    WPP_SF_sd
0x1800206db  jmp     loc_180020806
0x1800206e0  call    cs:__imp_GetLastError
0x1800206e7  nop     dword ptr [rax+rax+00h]
0x1800206ec  test    eax, eax
0x1800206ee  jle     short loc_1800206F8
0x1800206f0  movzx   eax, ax
0x1800206f3  or      eax, 80070000h
0x1800206f8  mov     [rbp+3Fh+Reply], eax
0x1800206fb  test    eax, eax
0x1800206fd  jz      short loc_18002072D
0x1800206ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180020706  cmp     rcx, rdi
0x180020709  jz      short loc_18002072D
0x18002070b  test    byte ptr [rcx+1Ch], 1
0x18002070f  jz      short loc_18002072D
0x180020711  mov     rcx, [rcx+10h]
0x180020715  lea     r9, aRegisternotifi_2; "_RegisterNotificationAsyncRpc: CreateHa"...
0x18002071c  mov     edx, 19h
0x180020721  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180020725  mov     r8, r14
0x180020728  call    WPP_SF_sd
0x18002072d  mov     r8, [rbp+3Fh+arg_48]
0x180020734  lea     rdx, [rbp+3Fh+var_90]
0x180020738  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; CSsdpNotifyRequestManager CSsdpNotifyRequestManager::s_instance
0x18002073f  call    ?HrEndPropChangeNotifyRequest@CSsdpNotifyRequestManager@@QEAAJAEAV?$CUList@VCSsdpNotifyRequest@@@@PEAPEAU_SSDP_REGISTER_INFO@@@Z; CSsdpNotifyRequestManager::HrEndPropChangeNotifyRequest(CUList<CSsdpNotifyRequest> &,_SSDP_REGISTER_INFO * *)
0x180020744  mov     [rbp+3Fh+Reply], eax
0x180020747  test    r13, r13
0x18002074a  jz      loc_180020801
0x180020750  test    r15, r15
0x180020753  jz      loc_180020815
0x180020759  mov     rcx, [r13+20h]; Binding
0x18002075d  lea     r8, [rbp+3Fh+NotificationsQueued]; NotificationsQueued
0x180020761  mov     edx, 2; Notification
0x180020766  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18002076d  nop     dword ptr [rax+rax+00h]
0x180020772  cmp     [rbp+3Fh+NotificationsQueued], 0
0x180020776  mov     ebx, eax
0x180020778  jbe     short loc_1800207CD
0x18002077a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002077d  mov     rcx, r15; hHandle
0x180020780  call    cs:__imp_WaitForSingleObject
0x180020787  nop     dword ptr [rax+rax+00h]
0x18002078c  test    eax, eax
0x18002078e  jz      short loc_1800207CD
0x180020790  jle     short loc_18002079A
0x180020792  movzx   eax, ax
0x180020795  or      eax, 80070000h
0x18002079a  mov     ecx, eax
0x18002079c  mov     [rbp+3Fh+Reply], eax
0x18002079f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207a6  cmp     rcx, rdi
0x1800207a9  jz      short loc_1800207D4
0x1800207ab  test    byte ptr [rcx+1Ch], 1
0x1800207af  jz      short loc_1800207D4
0x1800207b1  mov     rcx, [rcx+10h]
0x1800207b5  lea     r9, aRegisternotifi_0; "_RegisterNotificationAsyncRpc: Wait on "...
0x1800207bc  mov     edx, 1Ah
0x1800207c1  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800207c5  mov     r8, r14
0x1800207c8  call    WPP_SF_sd
0x1800207cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207d4  test    ebx, ebx
0x1800207d6  jz      short loc_180020806
0x1800207d8  movzx   eax, bx
0x1800207db  or      eax, 80070000h
0x1800207e0  cmp     rcx, rdi
0x1800207e3  jz      short loc_180020806
0x1800207e5  test    byte ptr [rcx+1Ch], 1
0x1800207e9  jz      short loc_180020806
0x1800207eb  test    ebx, ebx
0x1800207ed  lea     r9, aRegisternotifi; "_RegisterNotificationAsyncRpc: Failed t"...
0x1800207f4  mov     edx, 1Bh
0x1800207f9  cmovle  eax, ebx
0x1800207fc  jmp     loc_1800206CB
0x180020801  test    r15, r15
0x180020804  jz      short loc_180020815
0x180020806  mov     rcx, r15; hObject
0x180020809  call    cs:__imp_CloseHandle
0x180020810  nop     dword ptr [rax+rax+00h]
0x180020815  mov     rcx, qword ptr [rbp+3Fh+var_90.Data1]; void *
0x180020819  test    rcx, rcx
0x18002081c  jz      short loc_180020823
0x18002081e  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x180020823  test    r13, r13
0x180020826  jz      short loc_18002083D
0x180020828  lea     rdx, [rbp+3Fh+Reply]; Reply
0x18002082c  mov     rcx, r13; pAsync
0x18002082f  call    cs:__imp_RpcAsyncCompleteCall
0x180020836  nop     dword ptr [rax+rax+00h]
0x18002083b  mov     ebx, eax
0x18002083d  test    ebx, ebx
0x18002083f  jz      short loc_18002087F
0x180020841  jle     short loc_18002084C
0x180020843  movzx   ebx, bx
0x180020846  or      ebx, 80070000h
0x18002084c  mov     eax, ebx
0x18002084e  mov     [rbp+3Fh+Reply], ebx
0x180020851  mov     rcx, cs:WPP_GLOBAL_Control
0x180020858  cmp     rcx, rdi
0x18002085b  jz      short loc_1800208A6
0x18002085d  test    byte ptr [rcx+1Ch], 1
0x180020861  jz      short loc_180020886
0x180020863  mov     rcx, [rcx+10h]
0x180020867  lea     r9, aRegisternotifi_1; "_RegisterNotificationAsyncRpc: Failed t"...
0x18002086e  mov     edx, 1Dh
0x180020873  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180020877  mov     r8, r14
0x18002087a  call    WPP_SF_sd
0x18002087f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020886  cmp     rcx, rdi
0x180020889  jz      short loc_1800208A6
0x18002088b  test    byte ptr [rcx+1Ch], 8
0x18002088f  jz      short loc_1800208A6
0x180020891  mov     r9d, [rbp+3Fh+Reply]
0x180020895  mov     edx, 1Eh
0x18002089a  mov     rcx, [rcx+10h]
0x18002089e  mov     r8, r14
0x1800208a1  call    WPP_SF_d
0x1800208a6  movzx   eax, word ptr [rbp+3Fh+Reply]
0x1800208aa  jmp     short loc_1800208E2
0x1800208ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208b3  lea     rdi, WPP_GLOBAL_Control
0x1800208ba  cmp     rcx, rdi
0x1800208bd  jz      short loc_1800208DD
0x1800208bf  test    byte ptr [rcx+1Ch], 8
0x1800208c3  jz      short loc_1800208DD
0x1800208c5  mov     rcx, [rcx+10h]
0x1800208c9  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x1800208d0  mov     edx, 18h
0x1800208d5  mov     r9, rsi
0x1800208d8  call    WPP_SF_q
0x1800208dd  mov     eax, 57h ; 'W'
0x1800208e2  add     rsp, 0A8h
0x1800208e9  pop     r15
0x1800208eb  pop     r14
0x1800208ed  pop     r13
0x1800208ef  pop     r12
0x1800208f1  pop     rdi
0x1800208f2  pop     rsi
0x1800208f3  pop     rbx
0x1800208f4  pop     rbp
0x1800208f5  retn
```
