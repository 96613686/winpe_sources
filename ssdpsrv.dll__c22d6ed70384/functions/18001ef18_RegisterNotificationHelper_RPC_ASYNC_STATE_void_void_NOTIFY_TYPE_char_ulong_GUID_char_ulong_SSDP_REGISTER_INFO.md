# _RegisterNotificationHelper(_RPC_ASYNC_STATE *,void * *,void *,_NOTIFY_TYPE,char *,ulong,_GUID,char *,ulong,_SSDP_REGISTER_INFO * *)

- ea: `0x18001ef18`
- end: `0x18001f2fc`
- name: `?_RegisterNotificationHelper@@YAHPEAU_RPC_ASYNC_STATE@@PEAPEAXPEAXW4_NOTIFY_TYPE@@PEADKU_GUID@@4KPEAPEAU_SSDP_REGISTER_INFO@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(struct _RPC_ASYNC_STATE *, void **, void *, int, char *, unsigned int, struct _GUID *, __int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ee40`
- `0x18001eeb0`

## callees

- `0x1800092f4`
- `0x180019ce4`
- `0x180019f00`
- `0x18001c7e8`
- `0x18001ef18`
- `0x180022aa8`
- `0x1800255a8`
- `0x18002c8cc`
- `0x18002c90c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f198`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f198`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f067`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f067`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f23b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f23b`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18001f0ad`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18001f0ad`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18001f184`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18001f184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f21b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f21b`

## string_xrefs

- `0x18001f133`: `_RegisterNotificationAsyncRpc: CreateHandleFailed`
- `0x18001f26d`: `_RegisterNotificationAsyncRpc: Failed to complete the RPC call.`

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
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids, a3);
  return 87;
}

```

## disassembly

```asm
0x18001ef18  push    rbp
0x18001ef1a  push    rbx
0x18001ef1b  push    rsi
0x18001ef1c  push    rdi
0x18001ef1d  push    r12
0x18001ef1f  push    r13
0x18001ef21  push    r14
0x18001ef23  push    r15
0x18001ef25  lea     rbp, [rsp-7]
0x18001ef2a  sub     rsp, 0A8h
0x18001ef31  xor     edi, edi
0x18001ef33  xorps   xmm0, xmm0
0x18001ef36  xor     eax, eax
0x18001ef38  mov     [rbp+3Fh+Reply], edi
0x18001ef3b  mov     qword ptr [rbp+3Fh+NotificationInfo+18h], rax
0x18001ef3f  mov     r15d, r9d
0x18001ef42  mov     [rbp+3Fh+var_70], rax
0x18001ef46  mov     rsi, r8
0x18001ef49  mov     r12, rdx
0x18001ef4c  mov     qword ptr [rbp+3Fh+NotificationInfo], rdi
0x18001ef50  mov     r13, rcx
0x18001ef53  mov     [rbp+3Fh+NotificationsQueued], edi
0x18001ef56  movups  xmmword ptr [rbp+3Fh+NotificationInfo+8], xmm0
0x18001ef5a  movups  [rbp+3Fh+var_80], xmm0
0x18001ef5e  test    rdx, rdx
0x18001ef61  jz      loc_18001F2B2
0x18001ef67  test    r8, r8
0x18001ef6a  jz      loc_18001F2B2
0x18001ef70  cmp     [rbp+3Fh+arg_48], rdi
0x18001ef77  jz      loc_18001F2B2
0x18001ef7d  lea     edx, [rdi+1]
0x18001ef80  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; CSsdpNotifyRequestManager CSsdpNotifyRequestManager::s_instance
0x18001ef87  call    ?IsNotifySemaphoreInList@CSsdpNotifyRequestManager@@QEAAHW4_List_TYPE@@PEAX@Z; CSsdpNotifyRequestManager::IsNotifySemaphoreInList(_List_TYPE,void *)
0x18001ef8c  test    eax, eax
0x18001ef8e  jz      loc_18001F2B2
0x18001ef94  mov     [r12], rdi
0x18001ef98  mov     ebx, edi
0x18001ef9a  lea     rdi, WPP_GLOBAL_Control
0x18001efa1  lea     r14, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18001efa8  test    r15d, r15d
0x18001efab  jnz     short loc_18001EFF9
0x18001efad  mov     r8, [rbp+3Fh+arg_20]; char *
0x18001efb1  test    r8, r8
0x18001efb4  jz      loc_18001F22F
0x18001efba  mov     rax, [rbp+3Fh+arg_30]
0x18001efbe  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x18001efc5  mov     r9d, [rbp+3Fh+arg_28]; unsigned int
0x18001efc9  mov     rdx, r12; void **
0x18001efcc  movaps  xmm0, xmmword ptr [rax]
0x18001efcf  mov     eax, [rbp+3Fh+arg_40]
0x18001efd5  mov     [rsp+0E0h+var_B0], eax; unsigned int
0x18001efd9  lea     rax, [rbp+3Fh+var_90]
0x18001efdd  mov     [rsp+0E0h+var_B8], rsi; void *
0x18001efe2  mov     [rsp+0E0h+var_C0], rax; struct _GUID
0x18001efe7  movdqa  xmmword ptr [rbp+3Fh+var_90.Data1], xmm0
0x18001efec  call    ?HrCreateAliveNotifyRequest@CSsdpNotifyRequestManager@@QEAAJPEAPEAXPEBDKU_GUID@@PEAXK@Z; CSsdpNotifyRequestManager::HrCreateAliveNotifyRequest(void * *,char const *,ulong,_GUID,void *,ulong)
0x18001eff1  mov     [rbp+3Fh+Reply], eax
0x18001eff4  jmp     loc_18001F22F
0x18001eff9  cmp     r15d, 1
0x18001effd  jnz     loc_18001F22F
0x18001f003  mov     r8, [rbp+3Fh+arg_38]
0x18001f00a  test    r8, r8
0x18001f00d  jz      loc_18001F22F
0x18001f013  mov     eax, [rbp+3Fh+arg_40]
0x18001f019  lea     rdx, [rbp+3Fh+var_90]
0x18001f01d  mov     r9d, [rbp+3Fh+arg_28]
0x18001f021  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x18001f028  mov     dword ptr [rsp+0E0h+var_B8], eax; unsigned int
0x18001f02c  mov     [rsp+0E0h+var_C0], rsi; void *
0x18001f031  mov     qword ptr [rbp+3Fh+var_90.Data1], rbx
0x18001f035  call    ?HrBeginPropChangeNotifyRequest@CSsdpNotifyRequestManager@@QEAAJAEAV?$CUList@VCSsdpNotifyRequest@@@@PEBDKPEAXK@Z; CSsdpNotifyRequestManager::HrBeginPropChangeNotifyRequest(CUList<CSsdpNotifyRequest> &,char const *,ulong,void *,ulong)
0x18001f03a  mov     [rbp+3Fh+Reply], eax
0x18001f03d  test    eax, eax
0x18001f03f  jnz     loc_18001F221
0x18001f045  mov     rax, qword ptr [rbp+3Fh+var_90.Data1]
0x18001f049  xor     r15d, r15d
0x18001f04c  add     rax, 8
0x18001f050  mov     [r12], rax
0x18001f054  test    r13, r13
0x18001f057  jz      loc_18001F14B
0x18001f05d  xor     r9d, r9d; lpName
0x18001f060  xor     r8d, r8d; bInitialState
0x18001f063  xor     edx, edx; bManualReset
0x18001f065  xor     ecx, ecx; lpEventAttributes
0x18001f067  call    cs:__imp_CreateEventA
0x18001f06d  mov     r15, rax
0x18001f070  test    rax, rax
0x18001f073  jz      loc_18001F104
0x18001f079  mov     rcx, [r12]
0x18001f07d  lea     rax, ?RPCCleanupNotification@CSsdpNotifyRequestManager@@SAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z; CSsdpNotifyRequestManager::RPCCleanupNotification(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)
0x18001f084  mov     qword ptr [rbp+3Fh+NotificationInfo], rax
0x18001f088  mov     qword ptr [rbp+3Fh+var_80], rcx
0x18001f08c  mov     qword ptr [rbp+3Fh+var_80+8], r15
0x18001f090  mov     rcx, [r13+20h]; Binding
0x18001f094  lea     rax, [rbp+3Fh+var_80]
0x18001f098  mov     edx, 2; Notification
0x18001f09d  mov     [rbp+3Fh+var_70], rsi
0x18001f0a1  lea     r9, [rbp+3Fh+NotificationInfo]; NotificationInfo
0x18001f0a5  mov     [r13+18h], rax
0x18001f0a9  lea     r8d, [rdx+3]; NotificationType
0x18001f0ad  call    cs:__imp_RpcServerSubscribeForNotification
0x18001f0b3  mov     ebx, eax
0x18001f0b5  test    eax, eax
0x18001f0b7  jz      loc_18001F14B
0x18001f0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0c4  cmp     rcx, rdi
0x18001f0c7  jz      loc_18001F218
0x18001f0cd  test    byte ptr [rcx+1Ch], 1
0x18001f0d1  jz      loc_18001F218
0x18001f0d7  test    eax, eax
0x18001f0d9  jle     short loc_18001F0E3
0x18001f0db  movzx   eax, ax
0x18001f0de  or      eax, 80070000h
0x18001f0e3  mov     edx, 1Ch
0x18001f0e8  lea     r9, aRegisternotifi_3; "_RegisterNotificationAsyncRpc: Failed t"...
0x18001f0ef  mov     rcx, [rcx+10h]
0x18001f0f3  mov     r8, r14
0x18001f0f6  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18001f0fa  call    WPP_SF_sd
0x18001f0ff  jmp     loc_18001F218
0x18001f104  call    cs:__imp_GetLastError
0x18001f10a  test    eax, eax
0x18001f10c  jle     short loc_18001F116
0x18001f10e  movzx   eax, ax
0x18001f111  or      eax, 80070000h
0x18001f116  mov     [rbp+3Fh+Reply], eax
0x18001f119  test    eax, eax
0x18001f11b  jz      short loc_18001F14B
0x18001f11d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f124  cmp     rcx, rdi
0x18001f127  jz      short loc_18001F14B
0x18001f129  test    byte ptr [rcx+1Ch], 1
0x18001f12d  jz      short loc_18001F14B
0x18001f12f  mov     rcx, [rcx+10h]
0x18001f133  lea     r9, aRegisternotifi_2; "_RegisterNotificationAsyncRpc: CreateHa"...
0x18001f13a  mov     edx, 19h
0x18001f13f  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18001f143  mov     r8, r14
0x18001f146  call    WPP_SF_sd
0x18001f14b  mov     r8, [rbp+3Fh+arg_48]
0x18001f152  lea     rdx, [rbp+3Fh+var_90]
0x18001f156  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; CSsdpNotifyRequestManager CSsdpNotifyRequestManager::s_instance
0x18001f15d  call    ?HrEndPropChangeNotifyRequest@CSsdpNotifyRequestManager@@QEAAJAEAV?$CUList@VCSsdpNotifyRequest@@@@PEAPEAU_SSDP_REGISTER_INFO@@@Z; CSsdpNotifyRequestManager::HrEndPropChangeNotifyRequest(CUList<CSsdpNotifyRequest> &,_SSDP_REGISTER_INFO * *)
0x18001f162  mov     [rbp+3Fh+Reply], eax
0x18001f165  test    r13, r13
0x18001f168  jz      loc_18001F213
0x18001f16e  test    r15, r15
0x18001f171  jz      loc_18001F221
0x18001f177  mov     rcx, [r13+20h]; Binding
0x18001f17b  lea     r8, [rbp+3Fh+NotificationsQueued]; NotificationsQueued
0x18001f17f  mov     edx, 2; Notification
0x18001f184  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18001f18a  cmp     [rbp+3Fh+NotificationsQueued], 0
0x18001f18e  mov     ebx, eax
0x18001f190  jbe     short loc_18001F1DF
0x18001f192  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f195  mov     rcx, r15; hHandle
0x18001f198  call    cs:__imp_WaitForSingleObject
0x18001f19e  test    eax, eax
0x18001f1a0  jz      short loc_18001F1DF
0x18001f1a2  jle     short loc_18001F1AC
0x18001f1a4  movzx   eax, ax
0x18001f1a7  or      eax, 80070000h
0x18001f1ac  mov     ecx, eax
0x18001f1ae  mov     [rbp+3Fh+Reply], eax
0x18001f1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1b8  cmp     rcx, rdi
0x18001f1bb  jz      short loc_18001F1E6
0x18001f1bd  test    byte ptr [rcx+1Ch], 1
0x18001f1c1  jz      short loc_18001F1E6
0x18001f1c3  mov     rcx, [rcx+10h]
0x18001f1c7  lea     r9, aRegisternotifi_0; "_RegisterNotificationAsyncRpc: Wait on "...
0x18001f1ce  mov     edx, 1Ah
0x18001f1d3  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18001f1d7  mov     r8, r14
0x18001f1da  call    WPP_SF_sd
0x18001f1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1e6  test    ebx, ebx
0x18001f1e8  jz      short loc_18001F218
0x18001f1ea  movzx   eax, bx
0x18001f1ed  or      eax, 80070000h
0x18001f1f2  cmp     rcx, rdi
0x18001f1f5  jz      short loc_18001F218
0x18001f1f7  test    byte ptr [rcx+1Ch], 1
0x18001f1fb  jz      short loc_18001F218
0x18001f1fd  test    ebx, ebx
0x18001f1ff  lea     r9, aRegisternotifi; "_RegisterNotificationAsyncRpc: Failed t"...
0x18001f206  mov     edx, 1Bh
0x18001f20b  cmovle  eax, ebx
0x18001f20e  jmp     loc_18001F0EF
0x18001f213  test    r15, r15
0x18001f216  jz      short loc_18001F221
0x18001f218  mov     rcx, r15; hObject
0x18001f21b  call    cs:__imp_CloseHandle
0x18001f221  mov     rcx, qword ptr [rbp+3Fh+var_90.Data1]; void *
0x18001f225  test    rcx, rcx
0x18001f228  jz      short loc_18001F22F
0x18001f22a  call    ??_GNode@?$CUList@VCSsdpNotifyRequest@@@@QEAAPEAXI@Z; CUList<CSsdpNotifyRequest>::Node::`scalar deleting destructor'(uint)
0x18001f22f  test    r13, r13
0x18001f232  jz      short loc_18001F243
0x18001f234  lea     rdx, [rbp+3Fh+Reply]; Reply
0x18001f238  mov     rcx, r13; pAsync
0x18001f23b  call    cs:__imp_RpcAsyncCompleteCall
0x18001f241  mov     ebx, eax
0x18001f243  test    ebx, ebx
0x18001f245  jz      short loc_18001F285
0x18001f247  jle     short loc_18001F252
0x18001f249  movzx   ebx, bx
0x18001f24c  or      ebx, 80070000h
0x18001f252  mov     eax, ebx
0x18001f254  mov     [rbp+3Fh+Reply], ebx
0x18001f257  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f25e  cmp     rcx, rdi
0x18001f261  jz      short loc_18001F2AC
0x18001f263  test    byte ptr [rcx+1Ch], 1
0x18001f267  jz      short loc_18001F28C
0x18001f269  mov     rcx, [rcx+10h]
0x18001f26d  lea     r9, aRegisternotifi_1; "_RegisterNotificationAsyncRpc: Failed t"...
0x18001f274  mov     edx, 1Dh
0x18001f279  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18001f27d  mov     r8, r14
0x18001f280  call    WPP_SF_sd
0x18001f285  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f28c  cmp     rcx, rdi
0x18001f28f  jz      short loc_18001F2AC
0x18001f291  test    byte ptr [rcx+1Ch], 8
0x18001f295  jz      short loc_18001F2AC
0x18001f297  mov     r9d, [rbp+3Fh+Reply]
0x18001f29b  mov     edx, 1Eh
0x18001f2a0  mov     rcx, [rcx+10h]
0x18001f2a4  mov     r8, r14
0x18001f2a7  call    WPP_SF_d
0x18001f2ac  movzx   eax, word ptr [rbp+3Fh+Reply]
0x18001f2b0  jmp     short loc_18001F2E8
0x18001f2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2b9  lea     rdi, WPP_GLOBAL_Control
0x18001f2c0  cmp     rcx, rdi
0x18001f2c3  jz      short loc_18001F2E3
0x18001f2c5  test    byte ptr [rcx+1Ch], 8
0x18001f2c9  jz      short loc_18001F2E3
0x18001f2cb  mov     rcx, [rcx+10h]
0x18001f2cf  lea     r8, WPP_1b47134a19a23ae61e8d70f792424297_Traceguids
0x18001f2d6  mov     edx, 18h
0x18001f2db  mov     r9, rsi
0x18001f2de  call    WPP_SF_q
0x18001f2e3  mov     eax, 57h ; 'W'
0x18001f2e8  add     rsp, 0A8h
0x18001f2ef  pop     r15
0x18001f2f1  pop     r14
0x18001f2f3  pop     r13
0x18001f2f5  pop     r12
0x18001f2f7  pop     rdi
0x18001f2f8  pop     rsi
0x18001f2f9  pop     rbx
0x18001f2fa  pop     rbp
0x18001f2fb  retn
```
