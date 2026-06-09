# COMMON_ListenForPNPNotifications(void)

- ea: `0x18009c5a4`
- end: `0x18009c79d`
- name: `?COMMON_ListenForPNPNotifications@@YAXXZ`
- size: `505`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b0c70`
- `0x1800b97d4`
- `0x1800c6ae0`

## callees

- `0x180021e70`
- `0x18005de08`
- `0x18006108c`
- `0x18009c5a4`
- `0x1800c7204`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c6dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c6dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c68b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c68b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c78c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009c78c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009c5c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009c5c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18009c66c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18009c66c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18009c6bb`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18009c6bb`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009c6f3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009c6f3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18009c63b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18009c63b`
- `WS2_32!WSAProviderConfigChange` at `0x18009c604`
- `WS2_32!WSAProviderConfigChange` at `0x18009c6d2`
- `WS2_32!WSAProviderConfigChange` at `0x18009c604`
- `WS2_32!WSAProviderConfigChange` at `0x18009c6d2`

## pseudocode

```c
void COMMON_ListenForPNPNotifications(void)
{
  HANDLE v0; // rbx
  struct _TP_IO *ThreadpoolIo; // rbx
  RPC_THREAD_POOL_IO *v2; // rax
  HANDLE v3; // rcx
  unsigned int v4; // edx
  unsigned int v5; // edx

  if ( fWinsockLoaded )
  {
    EnterCriticalSection(&PNPNotificationsLock);
    if ( _InterlockedIncrement(&g_ListeningForPNPNotifications) != 1 )
    {
LABEL_31:
      LeaveCriticalSection(&PNPNotificationsLock);
      return;
    }
    if ( g_ProtocolChangeNotification )
      goto LABEL_23;
    if ( !g_NotificationHandle )
    {
      if ( WSAProviderConfigChange(&g_NotificationHandle, 0, 0) )
      {
        v3 = g_NotificationHandle;
        if ( g_NotificationHandle )
          goto LABEL_14;
      }
      else
      {
        v0 = g_NotificationHandle;
        if ( g_NotificationHandle )
        {
          if ( !(unsigned int)RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary() )
          {
            ThreadpoolIo = CreateThreadpoolIo(
                             v0,
                             COMMON_AddressChangeThreadPoolCallback,
                             0,
                             RPC_THREAD_POOL::CallbackEnvironment);
            if ( ThreadpoolIo )
            {
              v2 = (RPC_THREAD_POOL_IO *)AllocWrapper(8u);
              if ( v2 )
              {
                *(_QWORD *)v2 = ThreadpoolIo;
                g_NotificationIo = v2;
                goto LABEL_16;
              }
              g_NotificationIo = 0;
              CloseThreadpoolIo(ThreadpoolIo);
            }
          }
LABEL_12:
          v3 = g_NotificationHandle;
LABEL_14:
          CloseHandle(v3);
        }
      }
LABEL_28:
      g_ProtocolChangeNotification = 0;
      g_AddressChangeNotification = 0;
      g_ListeningForPNPNotifications = 0;
      g_NotificationHandle = 0;
      goto LABEL_31;
    }
    v2 = g_NotificationIo;
LABEL_16:
    if ( g_Overlapped.Internal != 259 )
    {
      g_Overlapped.hEvent = 0;
      g_Overlapped.Pointer = 0;
      StartThreadpoolIo(*(PTP_IO *)v2);
      if ( WSAProviderConfigChange(&g_NotificationHandle, &g_Overlapped, 0) )
      {
        if ( GetLastError() != 997 )
        {
          CancelThreadpoolIo(*(PTP_IO *)g_NotificationIo);
          if ( g_NotificationIo )
            RPC_THREAD_POOL_IO::`scalar deleting destructor'(g_NotificationIo, v4);
          g_NotificationIo = 0;
          goto LABEL_12;
        }
      }
    }
    g_ProtocolChangeNotification = 1;
LABEL_23:
    if ( !g_AddressChangeNotification )
    {
      if ( !(unsigned int)TransportProtocol::ResubmitQueriesIfNecessary() )
      {
        CloseHandle(g_NotificationHandle);
        if ( g_NotificationIo )
          RPC_THREAD_POOL_IO::`scalar deleting destructor'(g_NotificationIo, v5);
        g_NotificationIo = 0;
        goto LABEL_28;
      }
      g_AddressChangeNotification = 1;
    }
    g_ListeningForPNPNotifications = 2;
    goto LABEL_31;
  }
}

```

## disassembly

```asm
0x18009c5a4  mov     [rsp+arg_0], rbx
0x18009c5a9  push    rdi
0x18009c5aa  sub     rsp, 20h
0x18009c5ae  xor     edi, edi
0x18009c5b0  cmp     cs:?fWinsockLoaded@@3HA, edi; int fWinsockLoaded
0x18009c5b6  jz      loc_18009C792
0x18009c5bc  lea     rcx, PNPNotificationsLock; lpCriticalSection
0x18009c5c3  call    cs:__imp_EnterCriticalSection
0x18009c5c9  lea     eax, [rdi+1]
0x18009c5cc  lock xadd cs:g_ListeningForPNPNotifications, eax
0x18009c5d4  inc     eax
0x18009c5d6  cmp     eax, 1
0x18009c5d9  jnz     loc_18009C785
0x18009c5df  cmp     cs:g_ProtocolChangeNotification, edi
0x18009c5e5  jnz     loc_18009C720
0x18009c5eb  cmp     cs:?g_NotificationHandle@@3PEAXEA, rdi; void * g_NotificationHandle
0x18009c5f2  jnz     loc_18009C696
0x18009c5f8  xor     r8d, r8d; lpCompletionRoutine
0x18009c5fb  lea     rcx, ?g_NotificationHandle@@3PEAXEA; lpNotificationHandle
0x18009c602  xor     edx, edx; lpOverlapped
0x18009c604  call    cs:__imp_WSAProviderConfigChange
0x18009c60a  test    eax, eax
0x18009c60c  jnz     short loc_18009C67B
0x18009c60e  mov     rbx, cs:?g_NotificationHandle@@3PEAXEA; void * g_NotificationHandle
0x18009c615  test    rbx, rbx
0x18009c618  jz      loc_18009C756
0x18009c61e  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18009c623  test    eax, eax
0x18009c625  jnz     short loc_18009C672
0x18009c627  mov     r9, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18009c62e  lea     rdx, ?COMMON_AddressChangeThreadPoolCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18009c635  xor     r8d, r8d; pv
0x18009c638  mov     rcx, rbx; fl
0x18009c63b  call    cs:__imp_CreateThreadpoolIo
0x18009c641  mov     rbx, rax
0x18009c644  test    rax, rax
0x18009c647  jz      short loc_18009C672
0x18009c649  lea     ecx, [rdi+8]; dwBytes
0x18009c64c  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009c651  test    rax, rax
0x18009c654  jz      short loc_18009C662
0x18009c656  mov     [rax], rbx
0x18009c659  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rax; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009c660  jmp     short loc_18009C69D
0x18009c662  mov     rcx, rbx; pio
0x18009c665  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rdi; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009c66c  call    cs:__imp_CloseThreadpoolIo
0x18009c672  mov     rcx, cs:?g_NotificationHandle@@3PEAXEA; void * g_NotificationHandle
0x18009c679  jmp     short loc_18009C68B
0x18009c67b  mov     rcx, cs:?g_NotificationHandle@@3PEAXEA; hObject
0x18009c682  test    rcx, rcx
0x18009c685  jz      loc_18009C756
0x18009c68b  call    cs:__imp_CloseHandle
0x18009c691  jmp     loc_18009C756
0x18009c696  mov     rax, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009c69d  cmp     cs:?g_Overlapped@@3U_OVERLAPPED@@A.Internal, 103h; _OVERLAPPED g_Overlapped ...
0x18009c6a8  jz      short loc_18009C716
0x18009c6aa  mov     cs:?g_Overlapped@@3U_OVERLAPPED@@A.hEvent, rdi; _OVERLAPPED g_Overlapped ...
0x18009c6b1  mov     qword ptr cs:?g_Overlapped@@3U_OVERLAPPED@@A.10h, rdi; _OVERLAPPED g_Overlapped ...
0x18009c6b8  mov     rcx, [rax]; pio
0x18009c6bb  call    cs:__imp_StartThreadpoolIo
0x18009c6c1  xor     r8d, r8d; lpCompletionRoutine
0x18009c6c4  lea     rdx, ?g_Overlapped@@3U_OVERLAPPED@@A; lpOverlapped
0x18009c6cb  lea     rcx, ?g_NotificationHandle@@3PEAXEA; lpNotificationHandle
0x18009c6d2  call    cs:__imp_WSAProviderConfigChange
0x18009c6d8  test    eax, eax
0x18009c6da  jz      short loc_18009C716
0x18009c6dc  call    cs:__imp_GetLastError
0x18009c6e2  cmp     eax, 3E5h
0x18009c6e7  jz      short loc_18009C716
0x18009c6e9  mov     rcx, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009c6f0  mov     rcx, [rcx]; pio
0x18009c6f3  call    cs:__imp_CancelThreadpoolIo
0x18009c6f9  mov     rcx, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; this
0x18009c700  test    rcx, rcx
0x18009c703  jz      short loc_18009C70A
0x18009c705  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x18009c70a  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rdi; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009c711  jmp     loc_18009C672
0x18009c716  mov     cs:g_ProtocolChangeNotification, 1
0x18009c720  cmp     cs:g_AddressChangeNotification, edi
0x18009c726  jnz     short loc_18009C77B
0x18009c728  call    ?ResubmitQueriesIfNecessary@TransportProtocol@@SAHXZ; TransportProtocol::ResubmitQueriesIfNecessary(void)
0x18009c72d  test    eax, eax
0x18009c72f  jnz     short loc_18009C771
0x18009c731  mov     rcx, cs:?g_NotificationHandle@@3PEAXEA; hObject
0x18009c738  call    cs:__imp_CloseHandle
0x18009c73e  mov     rcx, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; this
0x18009c745  test    rcx, rcx
0x18009c748  jz      short loc_18009C74F
0x18009c74a  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x18009c74f  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rdi; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009c756  mov     cs:g_ProtocolChangeNotification, edi
0x18009c75c  mov     cs:g_AddressChangeNotification, edi
0x18009c762  mov     cs:g_ListeningForPNPNotifications, edi
0x18009c768  mov     cs:?g_NotificationHandle@@3PEAXEA, rdi; void * g_NotificationHandle
0x18009c76f  jmp     short loc_18009C785
0x18009c771  mov     cs:g_AddressChangeNotification, 1
0x18009c77b  mov     cs:g_ListeningForPNPNotifications, 2
0x18009c785  lea     rcx, PNPNotificationsLock; lpCriticalSection
0x18009c78c  call    cs:__imp_LeaveCriticalSection
0x18009c792  mov     rbx, [rsp+28h+arg_0]
0x18009c797  add     rsp, 20h
0x18009c79b  pop     rdi
0x18009c79c  retn
```
