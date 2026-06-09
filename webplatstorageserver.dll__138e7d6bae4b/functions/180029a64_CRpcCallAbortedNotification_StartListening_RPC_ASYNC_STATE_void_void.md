# CRpcCallAbortedNotification::StartListening(_RPC_ASYNC_STATE *,void *,void * *)

- ea: `0x180029a64`
- end: `0x180029be8`
- name: `?StartListening@CRpcCallAbortedNotification@@QEAAJPEAU_RPC_ASYNC_STATE@@PEAXPEAPEAX@Z`
- size: `388`
- prototype: `__int64 __fastcall(struct CRpcCallAbortedNotificationHelper **this, struct _RPC_ASYNC_STATE *, void *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800afda0`

## callees

- `0x180028b6c`
- `0x180029a64`
- `0x180050e84`
- `0x180055594`
- `0x1800573a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029b1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029ab2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029acf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029ab2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029acf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029b5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b86`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180029bad`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180029bad`

## pseudocode

```c
__int64 __fastcall CRpcCallAbortedNotification::StartListening(
        struct CRpcCallAbortedNotificationHelper **this,
        struct _RPC_ASYNC_STATE *a2,
        void *a3,
        void **a4)
{
  signed int Instance; // ebx
  CRpcCallAbortedNotificationHelper *v9; // rdi
  HANDLE EventW; // rax
  HANDLE v11; // rax
  __int64 v12; // rcx
  int v13; // edx
  _UNKNOWN **i; // rcx
  char v15; // si
  signed int LastError; // eax
  RPC_STATUS v18; // eax
  void *v19; // rax
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+20h] [rbp-58h] BYREF

  CRpcCallAbortedNotification::StopListening((CRpcCallAbortedNotification *)this);
  Instance = CRpcCallAbortedNotificationHelper::CreateInstance(this);
  if ( Instance >= 0 )
  {
    v9 = *this;
    *a4 = 0;
    CRpcCallAbortedNotificationHelper::Close(v9);
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v9 + 4) = EventW;
    if ( EventW )
    {
      v11 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)v9 + 5) = v11;
      if ( v11 )
      {
        Instance = -2147467259;
        NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)CRpcCallAbortedNotificationHelper::s_NotificationRoutine;
        memset(&NotificationInfo.NotificationRoutine + 1, 0, 24);
        CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&public: static int CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>>::AddToList(
          v12,
          v9);
        v13 = qword_180111C48;
        if ( qword_180111C48 )
        {
          EnterCriticalSection(&stru_180111C50);
          v13 = qword_180111C48;
        }
        if ( *((CRpcCallAbortedNotificationHelper **)v9 + 1) == (CRpcCallAbortedNotificationHelper *)((char *)v9 + 8) )
        {
          v15 = 0;
        }
        else
        {
          for ( i = (_UNKNOWN **)g_lstCallNotifications; ; i = (_UNKNOWN **)*i )
          {
            v15 = 0;
            if ( i == &g_lstCallNotifications )
              break;
            if ( v9 == (CRpcCallAbortedNotificationHelper *)(i - 1) )
            {
              v15 = 1;
              break;
            }
          }
        }
        if ( v13 )
          LeaveCriticalSection(&stru_180111C50);
        if ( v15 )
        {
          a2->UserInfo = v9;
          v18 = RpcServerSubscribeForNotification(
                  a3,
                  RpcNotificationCallCancel|RpcNotificationClientDisconnect,
                  RpcNotificationTypeCallback,
                  &NotificationInfo);
          Instance = v18;
          if ( v18 > 0 )
            Instance = (unsigned __int16)v18 | 0x80070000;
          if ( Instance >= 0 )
          {
            v19 = (void *)*((_QWORD *)v9 + 4);
            *((_QWORD *)v9 + 3) = a3;
            *a4 = v19;
            return (unsigned int)Instance;
          }
        }
        goto LABEL_14;
      }
    }
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
    if ( Instance < 0 )
LABEL_14:
      CRpcCallAbortedNotificationHelper::Close(v9);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180029a64  push    rbx
0x180029a66  push    rbp
0x180029a67  push    rsi
0x180029a68  push    rdi
0x180029a69  push    r14
0x180029a6b  push    r15
0x180029a6d  sub     rsp, 48h
0x180029a71  mov     r14, r9
0x180029a74  mov     rbp, r8
0x180029a77  mov     r15, rdx
0x180029a7a  mov     rdi, rcx
0x180029a7d  call    ?StopListening@CRpcCallAbortedNotification@@AEAAXXZ; CRpcCallAbortedNotification::StopListening(void)
0x180029a82  mov     rcx, rdi; struct CRpcCallAbortedNotificationHelper **
0x180029a85  call    ?CreateInstance@CRpcCallAbortedNotificationHelper@@SAJPEAPEAV1@@Z; CRpcCallAbortedNotificationHelper::CreateInstance(CRpcCallAbortedNotificationHelper * *)
0x180029a8a  mov     ebx, eax
0x180029a8c  test    eax, eax
0x180029a8e  js      loc_180029B72
0x180029a94  mov     rdi, [rdi]
0x180029a97  mov     rcx, rdi; this
0x180029a9a  mov     qword ptr [r14], 0
0x180029aa1  call    ?Close@CRpcCallAbortedNotificationHelper@@QEAAJXZ; CRpcCallAbortedNotificationHelper::Close(void)
0x180029aa6  xor     r9d, r9d; lpName
0x180029aa9  xor     r8d, r8d; bInitialState
0x180029aac  xor     ecx, ecx; lpEventAttributes
0x180029aae  lea     edx, [r9+1]; bManualReset
0x180029ab2  call    cs:__imp_CreateEventW
0x180029ab8  mov     [rdi+20h], rax
0x180029abc  test    rax, rax
0x180029abf  jz      loc_180029B86
0x180029ac5  xor     r9d, r9d; lpName
0x180029ac8  xor     r8d, r8d; bInitialState
0x180029acb  xor     edx, edx; bManualReset
0x180029acd  xor     ecx, ecx; lpEventAttributes
0x180029acf  call    cs:__imp_CreateEventW
0x180029ad5  mov     [rdi+28h], rax
0x180029ad9  test    rax, rax
0x180029adc  jz      loc_180029B86
0x180029ae2  xor     eax, eax
0x180029ae4  xorps   xmm0, xmm0
0x180029ae7  mov     qword ptr [rsp+78h+NotificationInfo+18h], rax
0x180029aec  mov     rdx, rdi
0x180029aef  lea     rax, ?s_NotificationRoutine@CRpcCallAbortedNotificationHelper@@CAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z; CRpcCallAbortedNotificationHelper::s_NotificationRoutine(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)
0x180029af6  mov     ebx, 80004005h
0x180029afb  mov     qword ptr [rsp+78h+NotificationInfo], rax
0x180029b00  movups  xmmword ptr [rsp+78h+NotificationInfo+8], xmm0
0x180029b05  call    ?AddToList@?$CThreadSafeLinkedList@VCRpcCallAbortedNotificationHelper@@V?$CDoubleLink@VCRpcCallAbortedNotificationHelper@@$1?CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset@1@SAHXZ@@@@QEAAXPEAVCRpcCallAbortedNotificationHelper@@@Z; CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>>::AddToList(CRpcCallAbortedNotificationHelper *)
0x180029b0a  mov     rdx, cs:qword_180111C48
0x180029b11  test    edx, edx
0x180029b13  jz      short loc_180029B29
0x180029b15  lea     rcx, stru_180111C50; lpCriticalSection
0x180029b1c  call    cs:__imp_EnterCriticalSection
0x180029b22  mov     rdx, cs:qword_180111C48
0x180029b29  lea     rax, [rdi+8]
0x180029b2d  cmp     [rax], rax
0x180029b30  jz      short loc_180029B81
0x180029b32  mov     rcx, cs:?g_lstCallNotifications@@3V?$CThreadSafeLinkedList@VCRpcCallAbortedNotificationHelper@@V?$CDoubleLink@VCRpcCallAbortedNotificationHelper@@$1?CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset@1@SAHXZ@@@@A; CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>> g_lstCallNotifications
0x180029b39  xor     sil, sil
0x180029b3c  lea     rax, ?g_lstCallNotifications@@3V?$CThreadSafeLinkedList@VCRpcCallAbortedNotificationHelper@@V?$CDoubleLink@VCRpcCallAbortedNotificationHelper@@$1?CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset@1@SAHXZ@@@@A; CThreadSafeLinkedList<CRpcCallAbortedNotificationHelper,CDoubleLink<CRpcCallAbortedNotificationHelper,&CRpcCallAbortedNotificationHelper::CRpcCallAbortedNotificationHelper_GetCLink_lnkOffset(void)>> g_lstCallNotifications
0x180029b43  cmp     rcx, rax
0x180029b46  jz      short loc_180029B54
0x180029b48  lea     rax, [rcx-8]
0x180029b4c  cmp     rdi, rax
0x180029b4f  jnz     short loc_180029BCA
0x180029b51  mov     sil, 1
0x180029b54  test    edx, edx
0x180029b56  jz      short loc_180029B65
0x180029b58  lea     rcx, stru_180111C50; lpCriticalSection
0x180029b5f  call    cs:__imp_LeaveCriticalSection
0x180029b65  test    sil, sil
0x180029b68  jnz     short loc_180029B98
0x180029b6a  mov     rcx, rdi; this
0x180029b6d  call    ?Close@CRpcCallAbortedNotificationHelper@@QEAAJXZ; CRpcCallAbortedNotificationHelper::Close(void)
0x180029b72  mov     eax, ebx
0x180029b74  add     rsp, 48h
0x180029b78  pop     r15
0x180029b7a  pop     r14
0x180029b7c  pop     rdi
0x180029b7d  pop     rsi
0x180029b7e  pop     rbp
0x180029b7f  pop     rbx
0x180029b80  retn
0x180029b81  xor     sil, sil
0x180029b84  jmp     short loc_180029B54
0x180029b86  call    cs:__imp_GetLastError
0x180029b8c  mov     ebx, eax
0x180029b8e  test    eax, eax
0x180029b90  jg      short loc_180029BDD
0x180029b92  test    ebx, ebx
0x180029b94  jns     short loc_180029B72
0x180029b96  jmp     short loc_180029B6A
0x180029b98  mov     edx, 3; Notification
0x180029b9d  mov     [r15+18h], rdi
0x180029ba1  lea     r9, [rsp+78h+NotificationInfo]; NotificationInfo
0x180029ba6  mov     rcx, rbp; Binding
0x180029ba9  lea     r8d, [rdx+2]; NotificationType
0x180029bad  call    cs:__imp_RpcServerSubscribeForNotification
0x180029bb3  mov     ebx, eax
0x180029bb5  test    eax, eax
0x180029bb7  jg      short loc_180029BD2
0x180029bb9  test    ebx, ebx
0x180029bbb  js      short loc_180029B6A
0x180029bbd  mov     rax, [rdi+20h]
0x180029bc1  mov     [rdi+18h], rbp
0x180029bc5  mov     [r14], rax
0x180029bc8  jmp     short loc_180029B72
0x180029bca  mov     rcx, [rcx]
0x180029bcd  jmp     loc_180029B39
0x180029bd2  movzx   ebx, ax
0x180029bd5  or      ebx, 80070000h
0x180029bdb  jmp     short loc_180029BB9
0x180029bdd  movzx   ebx, ax
0x180029be0  or      ebx, 80070000h
0x180029be6  jmp     short loc_180029B92
```
