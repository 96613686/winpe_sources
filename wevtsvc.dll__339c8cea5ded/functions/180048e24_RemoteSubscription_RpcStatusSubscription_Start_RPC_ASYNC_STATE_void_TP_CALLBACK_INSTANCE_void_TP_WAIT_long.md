# RemoteSubscription::RpcStatusSubscription::Start(_RPC_ASYNC_STATE *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long))

- ea: `0x180048e24`
- end: `0x180048f3d`
- name: `?Start@RpcStatusSubscription@RemoteSubscription@@QEAAJPEAU_RPC_ASYNC_STATE@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z@Z`
- size: `281`
- prototype: `DWORD __fastcall(RemoteSubscription::RpcStatusSubscription *this, struct _RPC_ASYNC_STATE *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int))`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800475b4`
- `0x1800716bc`

## callees

- `0x180048e24`
- `0x1800934e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180048e73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180048efa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180048e73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180048efa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180048e88`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180048e88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180048e9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180048e9b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180048e3b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180048e4d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180048e3b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180048e4d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048f2b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048f11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048f11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048f35`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180048ee3`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180048ee3`

## pseudocode

```c
DWORD __fastcall RemoteSubscription::RpcStatusSubscription::Start(
        RemoteSubscription::RpcStatusSubscription *this,
        struct _RPC_ASYNC_STATE *a2,
        void (*a3)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WAIT *, int))
{
  struct _TP_WAIT *v5; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  struct _TP_WAIT *v7; // rcx
  RPC_BINDING_HANDLE *v8; // rcx
  RPCNOTIFICATION_ROUTINE *v9; // rax
  RPC_NOTIFICATIONS v10; // edx
  RPC_STATUS v11; // edi
  DWORD result; // eax
  DWORD LastError; // ebx
  RemoteSubscription::RpcStatusSubscription *v14; // [rsp+20h] [rbp-38h] BYREF
  char v15; // [rsp+28h] [rbp-30h]
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)this = a2;
  if ( !ResetEvent(*((HANDLE *)this + 1)) || !ResetEvent(*((HANDLE *)this + 3)) )
    return GetLastError();
  v5 = (struct _TP_WAIT *)*((_QWORD *)this + 13);
  v14 = this;
  v15 = 1;
  if ( v5 )
    SetThreadpoolWait(v5, 0, 0);
  ThreadpoolWait = CreateThreadpoolWait(
                     RemoteSubscription::RpcServerNotificationTpCallback,
                     a2->UserInfo,
                     (PTP_CALLBACK_ENVIRON)((char *)this + 32));
  v7 = (struct _TP_WAIT *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = ThreadpoolWait;
  if ( v7 )
    CloseThreadpoolWait(v7);
  if ( *((_QWORD *)this + 13) )
  {
    v8 = *(RPC_BINDING_HANDLE **)this;
    v9 = (RPCNOTIFICATION_ROUTINE *)*((_QWORD *)this + 1);
    v10 = *((_DWORD *)this + 28);
    memset(&NotificationInfo.NotificationRoutine + 1, 0, 24);
    NotificationInfo.APC.NotificationRoutine = v9;
    *((_DWORD *)this + 29) = 0;
    *((_BYTE *)this + 120) = 0;
    v11 = RpcServerSubscribeForNotification(v8[4], v10, RpcNotificationTypeEvent, &NotificationInfo);
    if ( v11 )
    {
      SetEvent(*((HANDLE *)this + 3));
      return v11;
    }
    else
    {
      SetThreadpoolWait(*((PTP_WAIT *)this + 13), *((HANDLE *)this + 1), 0);
      result = 0;
      *((_BYTE *)this + 120) = 1;
    }
  }
  else
  {
    LastError = GetLastError();
    tlx::_UndoSolo__RemoteSubscription::RpcStatusSubscription::Start_::_2_::_lambda_1___::__UndoSolo__RemoteSubscription::RpcStatusSubscription::Start_::_2_::_lambda_1___(&v14);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180048e24  mov     [rsp+arg_0], rbx
0x180048e29  push    rdi
0x180048e2a  sub     rsp, 50h
0x180048e2e  mov     rbx, rcx
0x180048e31  mov     [rcx], rdx
0x180048e34  mov     rcx, [rcx+8]; hEvent
0x180048e38  mov     rdi, rdx
0x180048e3b  call    cs:__imp_ResetEvent
0x180048e41  test    eax, eax
0x180048e43  jz      loc_180048F35
0x180048e49  mov     rcx, [rbx+18h]; hEvent
0x180048e4d  call    cs:__imp_ResetEvent
0x180048e53  test    eax, eax
0x180048e55  jz      loc_180048F35
0x180048e5b  mov     rcx, [rbx+68h]; pwa
0x180048e5f  mov     [rsp+58h+var_38], rbx
0x180048e64  mov     [rsp+58h+var_30], 1
0x180048e69  test    rcx, rcx
0x180048e6c  jz      short loc_180048E79
0x180048e6e  xor     r8d, r8d; pftTimeout
0x180048e71  xor     edx, edx; h
0x180048e73  call    cs:__imp_SetThreadpoolWait
0x180048e79  mov     rdx, [rdi+18h]; pv
0x180048e7d  lea     r8, [rbx+20h]; pcbe
0x180048e81  lea     rcx, ?RpcServerNotificationTpCallback@RemoteSubscription@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180048e88  call    cs:__imp_CreateThreadpoolWait
0x180048e8e  mov     rcx, [rbx+68h]; pwa
0x180048e92  mov     [rbx+68h], rax
0x180048e96  test    rcx, rcx
0x180048e99  jz      short loc_180048EA1
0x180048e9b  call    cs:__imp_CloseThreadpoolWait
0x180048ea1  cmp     qword ptr [rbx+68h], 0
0x180048ea6  jz      short loc_180048F11
0x180048ea8  mov     rcx, [rbx]
0x180048eab  lea     r9, [rsp+58h+NotificationInfo]; NotificationInfo
0x180048eb0  mov     rax, [rbx+8]
0x180048eb4  xorps   xmm0, xmm0
0x180048eb7  mov     edx, [rbx+70h]; Notification
0x180048eba  mov     r8d, 1; NotificationType
0x180048ec0  movdqu  xmmword ptr [rsp+58h+NotificationInfo+8], xmm0
0x180048ec6  mov     qword ptr [rsp+58h+NotificationInfo+18h], 0
0x180048ecf  mov     qword ptr [rsp+58h+NotificationInfo], rax
0x180048ed4  mov     dword ptr [rbx+74h], 0
0x180048edb  mov     byte ptr [rbx+78h], 0
0x180048edf  mov     rcx, [rcx+20h]; Binding
0x180048ee3  call    cs:__imp_RpcServerSubscribeForNotification
0x180048ee9  mov     edi, eax
0x180048eeb  test    eax, eax
0x180048eed  jnz     short loc_180048F27
0x180048eef  mov     rdx, [rbx+8]; h
0x180048ef3  xor     r8d, r8d; pftTimeout
0x180048ef6  mov     rcx, [rbx+68h]; pwa
0x180048efa  call    cs:__imp_SetThreadpoolWait
0x180048f00  xor     eax, eax
0x180048f02  mov     byte ptr [rbx+78h], 1
0x180048f06  mov     rbx, [rsp+58h+arg_0]
0x180048f0b  add     rsp, 50h
0x180048f0f  pop     rdi
0x180048f10  retn
0x180048f11  call    cs:__imp_GetLastError
0x180048f17  lea     rcx, [rsp+58h+var_38]
0x180048f1c  mov     ebx, eax
0x180048f1e  call    tlx___UndoSolo__RemoteSubscription__RpcStatusSubscription__Start____2____lambda_1_______UndoSolo__RemoteSubscription__RpcStatusSubscription__Start____2____lambda_1___
0x180048f23  mov     eax, ebx
0x180048f25  jmp     short loc_180048F06
0x180048f27  mov     rcx, [rbx+18h]; hEvent
0x180048f2b  call    cs:__imp_SetEvent
0x180048f31  mov     eax, edi
0x180048f33  jmp     short loc_180048F06
0x180048f35  call    cs:__imp_GetLastError
0x180048f3b  jmp     short loc_180048F06
```
