# COMMON_ListenForPNPNotifications(void)

- ea: `0x18009fe30`
- end: `0x1800a0070`
- name: `?COMMON_ListenForPNPNotifications@@YAXXZ`
- size: `576`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b4a50`
- `0x1800bdccc`
- `0x1800cb580`

## callees

- `0x180023020`
- `0x18006e4c0`
- `0x180081cf4`
- `0x18009fe30`
- `0x1800cbd08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ff96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009ff2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fffe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0058`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0058`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009fe4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009fe4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18009ff0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18009ff0a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18009ff69`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18009ff69`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009ffb3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009ffb3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18009fed3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x18009fed3`
- `WS2_32!WSAProviderConfigChange` at `0x18009fe96`
- `WS2_32!WSAProviderConfigChange` at `0x18009ff86`
- `WS2_32!WSAProviderConfigChange` at `0x18009fe96`
- `WS2_32!WSAProviderConfigChange` at `0x18009ff86`

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
0x18009fe30  mov     [rsp+arg_0], rbx
0x18009fe35  push    rdi
0x18009fe36  sub     rsp, 20h
0x18009fe3a  xor     edi, edi
0x18009fe3c  cmp     cs:?fWinsockLoaded@@3HA, edi; int fWinsockLoaded
0x18009fe42  jz      loc_1800A0064
0x18009fe48  lea     rcx, PNPNotificationsLock; lpCriticalSection
0x18009fe4f  call    cs:__imp_EnterCriticalSection
0x18009fe56  nop     dword ptr [rax+rax+00h]
0x18009fe5b  lea     eax, [rdi+1]
0x18009fe5e  lock xadd cs:g_ListeningForPNPNotifications, eax
0x18009fe66  inc     eax
0x18009fe68  cmp     eax, 1
0x18009fe6b  jnz     loc_1800A0051
0x18009fe71  cmp     cs:g_ProtocolChangeNotification, edi
0x18009fe77  jnz     loc_18009FFE6
0x18009fe7d  cmp     cs:?g_NotificationHandle@@3PEAXEA, rdi; void * g_NotificationHandle
0x18009fe84  jnz     loc_18009FF40
0x18009fe8a  xor     r8d, r8d; lpCompletionRoutine
0x18009fe8d  lea     rcx, ?g_NotificationHandle@@3PEAXEA; lpNotificationHandle
0x18009fe94  xor     edx, edx; lpOverlapped
0x18009fe96  call    cs:__imp_WSAProviderConfigChange
0x18009fe9d  nop     dword ptr [rax+rax+00h]
0x18009fea2  test    eax, eax
0x18009fea4  jnz     short loc_18009FF1F
0x18009fea6  mov     rbx, cs:?g_NotificationHandle@@3PEAXEA; void * g_NotificationHandle
0x18009fead  test    rbx, rbx
0x18009feb0  jz      loc_1800A0022
0x18009feb6  call    ?InitializeCallbackEnvironmentIfNecessary@RPC_THREAD_POOL@@CAJXZ; RPC_THREAD_POOL::InitializeCallbackEnvironmentIfNecessary(void)
0x18009febb  test    eax, eax
0x18009febd  jnz     short loc_18009FF16
0x18009febf  mov     r9, cs:?CallbackEnvironment@RPC_THREAD_POOL@@0REAU_TP_CALLBACK_ENVIRON_V3@@EA; pcbe
0x18009fec6  lea     rdx, ?COMMON_AddressChangeThreadPoolCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18009fecd  xor     r8d, r8d; pv
0x18009fed0  mov     rcx, rbx; fl
0x18009fed3  call    cs:__imp_CreateThreadpoolIo
0x18009feda  nop     dword ptr [rax+rax+00h]
0x18009fedf  mov     rbx, rax
0x18009fee2  test    rax, rax
0x18009fee5  jz      short loc_18009FF16
0x18009fee7  lea     ecx, [rdi+8]; dwBytes
0x18009feea  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009feef  test    rax, rax
0x18009fef2  jz      short loc_18009FF00
0x18009fef4  mov     [rax], rbx
0x18009fef7  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rax; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009fefe  jmp     short loc_18009FF47
0x18009ff00  mov     rcx, rbx; pio
0x18009ff03  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rdi; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009ff0a  call    cs:__imp_CloseThreadpoolIo
0x18009ff11  nop     dword ptr [rax+rax+00h]
0x18009ff16  mov     rcx, cs:?g_NotificationHandle@@3PEAXEA; void * g_NotificationHandle
0x18009ff1d  jmp     short loc_18009FF2F
0x18009ff1f  mov     rcx, cs:?g_NotificationHandle@@3PEAXEA; hObject
0x18009ff26  test    rcx, rcx
0x18009ff29  jz      loc_1800A0022
0x18009ff2f  call    cs:__imp_CloseHandle
0x18009ff36  nop     dword ptr [rax+rax+00h]
0x18009ff3b  jmp     loc_1800A0022
0x18009ff40  mov     rax, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009ff47  cmp     cs:?g_Overlapped@@3U_OVERLAPPED@@A.Internal, 103h; _OVERLAPPED g_Overlapped ...
0x18009ff52  jz      loc_18009FFDC
0x18009ff58  mov     cs:?g_Overlapped@@3U_OVERLAPPED@@A.hEvent, rdi; _OVERLAPPED g_Overlapped ...
0x18009ff5f  mov     qword ptr cs:?g_Overlapped@@3U_OVERLAPPED@@A.10h, rdi; _OVERLAPPED g_Overlapped ...
0x18009ff66  mov     rcx, [rax]; pio
0x18009ff69  call    cs:__imp_StartThreadpoolIo
0x18009ff70  nop     dword ptr [rax+rax+00h]
0x18009ff75  xor     r8d, r8d; lpCompletionRoutine
0x18009ff78  lea     rdx, ?g_Overlapped@@3U_OVERLAPPED@@A; lpOverlapped
0x18009ff7f  lea     rcx, ?g_NotificationHandle@@3PEAXEA; lpNotificationHandle
0x18009ff86  call    cs:__imp_WSAProviderConfigChange
0x18009ff8d  nop     dword ptr [rax+rax+00h]
0x18009ff92  test    eax, eax
0x18009ff94  jz      short loc_18009FFDC
0x18009ff96  call    cs:__imp_GetLastError
0x18009ff9d  nop     dword ptr [rax+rax+00h]
0x18009ffa2  cmp     eax, 3E5h
0x18009ffa7  jz      short loc_18009FFDC
0x18009ffa9  mov     rcx, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009ffb0  mov     rcx, [rcx]; pio
0x18009ffb3  call    cs:__imp_CancelThreadpoolIo
0x18009ffba  nop     dword ptr [rax+rax+00h]
0x18009ffbf  mov     rcx, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; this
0x18009ffc6  test    rcx, rcx
0x18009ffc9  jz      short loc_18009FFD0
0x18009ffcb  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x18009ffd0  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rdi; RPC_THREAD_POOL_IO * g_NotificationIo
0x18009ffd7  jmp     loc_18009FF16
0x18009ffdc  mov     cs:g_ProtocolChangeNotification, 1
0x18009ffe6  cmp     cs:g_AddressChangeNotification, edi
0x18009ffec  jnz     short loc_1800A0047
0x18009ffee  call    ?ResubmitQueriesIfNecessary@TransportProtocol@@SAHXZ; TransportProtocol::ResubmitQueriesIfNecessary(void)
0x18009fff3  test    eax, eax
0x18009fff5  jnz     short loc_1800A003D
0x18009fff7  mov     rcx, cs:?g_NotificationHandle@@3PEAXEA; hObject
0x18009fffe  call    cs:__imp_CloseHandle
0x1800a0005  nop     dword ptr [rax+rax+00h]
0x1800a000a  mov     rcx, cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA; this
0x1800a0011  test    rcx, rcx
0x1800a0014  jz      short loc_1800A001B
0x1800a0016  call    ??_GRPC_THREAD_POOL_IO@@QEAAPEAXI@Z; RPC_THREAD_POOL_IO::`scalar deleting destructor'(uint)
0x1800a001b  mov     cs:?g_NotificationIo@@3PEAVRPC_THREAD_POOL_IO@@EA, rdi; RPC_THREAD_POOL_IO * g_NotificationIo
0x1800a0022  mov     cs:g_ProtocolChangeNotification, edi
0x1800a0028  mov     cs:g_AddressChangeNotification, edi
0x1800a002e  mov     cs:g_ListeningForPNPNotifications, edi
0x1800a0034  mov     cs:?g_NotificationHandle@@3PEAXEA, rdi; void * g_NotificationHandle
0x1800a003b  jmp     short loc_1800A0051
0x1800a003d  mov     cs:g_AddressChangeNotification, 1
0x1800a0047  mov     cs:g_ListeningForPNPNotifications, 2
0x1800a0051  lea     rcx, PNPNotificationsLock; lpCriticalSection
0x1800a0058  call    cs:__imp_LeaveCriticalSection
0x1800a005f  nop     dword ptr [rax+rax+00h]
0x1800a0064  mov     rbx, [rsp+28h+arg_0]
0x1800a0069  add     rsp, 20h
0x1800a006d  pop     rdi
0x1800a006e  retn
```
