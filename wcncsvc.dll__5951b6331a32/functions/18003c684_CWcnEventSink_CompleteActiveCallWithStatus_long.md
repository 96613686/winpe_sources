# CWcnEventSink::CompleteActiveCallWithStatus(long)

- ea: `0x18003c684`
- end: `0x18003c84c`
- name: `?CompleteActiveCallWithStatus@CWcnEventSink@@QEAAXJ@Z`
- size: `456`
- prototype: `void __fastcall(CWcnEventSink *__hidden this, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034be0`
- `0x180039dac`
- `0x18003a0c8`
- `0x18003c470`

## callees

- `0x180004f2c`
- `0x180004fb8`
- `0x18003c5c8`
- `0x18003c684`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c6db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c6db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c809`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c704`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c760`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c704`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c760`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003c7b3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003c7b3`

## pseudocode

```c
void __fastcall CWcnEventSink::CompleteActiveCallWithStatus(CWcnEventSink *this, int a2)
{
  const char *Indent; // rax
  __int64 v4; // r10
  __int64 v5; // rcx
  RPC_STATUS v6; // eax
  unsigned int v7; // ecx
  RPC_STATUS v8; // eax
  unsigned int v9; // ecx
  RPC_STATUS v10; // eax
  unsigned int v11; // ecx
  const char *v12; // rax
  __int64 v13; // r10
  unsigned int NotificationsQueued; // [rsp+50h] [rbp+8h] BYREF
  int Reply; // [rsp+58h] [rbp+10h] BYREF

  Reply = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 34, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, Indent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = *((_QWORD *)this + 8);
  if ( v5 )
  {
    NotificationsQueued = 0;
    v6 = RpcServerUnsubscribeForNotification(
           *(RPC_BINDING_HANDLE *)(v5 + 32),
           RpcNotificationClientDisconnect,
           &NotificationsQueued);
    if ( v6 )
    {
      v7 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
          (unsigned int)v6,
          v7 | 0x80000000);
    }
    v8 = RpcServerUnsubscribeForNotification(
           *(RPC_BINDING_HANDLE *)(*((_QWORD *)this + 8) + 32LL),
           RpcNotificationCallCancel,
           &NotificationsQueued);
    if ( v8 )
    {
      v9 = v8 > 0 ? (unsigned __int16)v8 | 0x80070000 : v8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
          (unsigned int)v8,
          v9 | 0x80000000);
    }
    v10 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)this + 8), &Reply);
    if ( v10 )
    {
      v11 = v10 > 0 ? (unsigned __int16)v10 | 0x80070000 : v10;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
          (unsigned int)v10,
          v11 | 0x80000000);
    }
    CWcnEventSink::ClearActiveCall(this);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v12 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v13 + 16), 38, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v12);
  }
}

```

## disassembly

```asm
0x18003c684  mov     [rsp+arg_10], rbx
0x18003c689  mov     [rsp+Reply], edx
0x18003c68d  push    rsi
0x18003c68e  push    rdi
0x18003c68f  push    r14
0x18003c691  sub     rsp, 30h
0x18003c695  mov     rbx, rcx
0x18003c698  mov     r10, cs:WPP_GLOBAL_Control
0x18003c69f  lea     rsi, WPP_GLOBAL_Control
0x18003c6a6  lea     r14, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids
0x18003c6ad  cmp     r10, rsi
0x18003c6b0  jz      short loc_18003C6D7
0x18003c6b2  cmp     byte ptr [r10+19h], 6
0x18003c6b7  jb      short loc_18003C6D7
0x18003c6b9  mov     ecx, 1; int
0x18003c6be  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003c6c3  mov     rcx, [r10+10h]
0x18003c6c7  mov     edx, 22h ; '"'
0x18003c6cc  mov     r9, rax
0x18003c6cf  mov     r8, r14
0x18003c6d2  call    WPP_SF_s
0x18003c6d7  lea     rcx, [rbx+18h]; lpCriticalSection
0x18003c6db  call    cs:__imp_EnterCriticalSection
0x18003c6e1  mov     rcx, [rbx+40h]
0x18003c6e5  test    rcx, rcx
0x18003c6e8  jz      loc_18003C805
0x18003c6ee  mov     [rsp+48h+NotificationsQueued], 0
0x18003c6f6  lea     r8, [rsp+48h+NotificationsQueued]; NotificationsQueued
0x18003c6fb  mov     rcx, [rcx+20h]; Binding
0x18003c6ff  mov     edx, 1; Notification
0x18003c704  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003c70a  test    eax, eax
0x18003c70c  jz      short loc_18003C74E
0x18003c70e  jg      short loc_18003C714
0x18003c710  mov     ecx, eax
0x18003c712  jmp     short loc_18003C71D
0x18003c714  movzx   ecx, ax
0x18003c717  or      ecx, 80070000h
0x18003c71d  mov     r10, cs:WPP_GLOBAL_Control
0x18003c724  cmp     r10, rsi
0x18003c727  jz      short loc_18003C74E
0x18003c729  cmp     byte ptr [r10+19h], 3
0x18003c72e  jb      short loc_18003C74E
0x18003c730  or      ecx, 80000000h
0x18003c736  mov     edx, 23h ; '#'
0x18003c73b  mov     [rsp+48h+var_28], ecx
0x18003c73f  mov     r9d, eax
0x18003c742  mov     rcx, [r10+10h]
0x18003c746  mov     r8, r14
0x18003c749  call    WPP_SF_Dd
0x18003c74e  mov     rcx, [rbx+40h]
0x18003c752  lea     r8, [rsp+48h+NotificationsQueued]; NotificationsQueued
0x18003c757  mov     edx, 2; Notification
0x18003c75c  mov     rcx, [rcx+20h]; Binding
0x18003c760  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003c766  test    eax, eax
0x18003c768  jz      short loc_18003C7AA
0x18003c76a  jg      short loc_18003C770
0x18003c76c  mov     ecx, eax
0x18003c76e  jmp     short loc_18003C779
0x18003c770  movzx   ecx, ax
0x18003c773  or      ecx, 80070000h
0x18003c779  mov     r10, cs:WPP_GLOBAL_Control
0x18003c780  cmp     r10, rsi
0x18003c783  jz      short loc_18003C7AA
0x18003c785  cmp     byte ptr [r10+19h], 3
0x18003c78a  jb      short loc_18003C7AA
0x18003c78c  or      ecx, 80000000h
0x18003c792  mov     edx, 24h ; '$'
0x18003c797  mov     [rsp+48h+var_28], ecx
0x18003c79b  mov     r9d, eax
0x18003c79e  mov     rcx, [r10+10h]
0x18003c7a2  mov     r8, r14
0x18003c7a5  call    WPP_SF_Dd
0x18003c7aa  mov     rcx, [rbx+40h]; pAsync
0x18003c7ae  lea     rdx, [rsp+48h+Reply]; Reply
0x18003c7b3  call    cs:__imp_RpcAsyncCompleteCall
0x18003c7b9  test    eax, eax
0x18003c7bb  jz      short loc_18003C7FD
0x18003c7bd  jg      short loc_18003C7C3
0x18003c7bf  mov     ecx, eax
0x18003c7c1  jmp     short loc_18003C7CC
0x18003c7c3  movzx   ecx, ax
0x18003c7c6  or      ecx, 80070000h
0x18003c7cc  mov     r10, cs:WPP_GLOBAL_Control
0x18003c7d3  cmp     r10, rsi
0x18003c7d6  jz      short loc_18003C7FD
0x18003c7d8  cmp     byte ptr [r10+19h], 3
0x18003c7dd  jb      short loc_18003C7FD
0x18003c7df  or      ecx, 80000000h
0x18003c7e5  mov     edx, 25h ; '%'
0x18003c7ea  mov     [rsp+48h+var_28], ecx
0x18003c7ee  mov     r9d, eax
0x18003c7f1  mov     rcx, [r10+10h]
0x18003c7f5  mov     r8, r14
0x18003c7f8  call    WPP_SF_Dd
0x18003c7fd  mov     rcx, rbx; this
0x18003c800  call    ?ClearActiveCall@CWcnEventSink@@QEAAXXZ; CWcnEventSink::ClearActiveCall(void)
0x18003c805  lea     rcx, [rbx+18h]; lpCriticalSection
0x18003c809  call    cs:__imp_LeaveCriticalSection
0x18003c80f  mov     r10, cs:WPP_GLOBAL_Control
0x18003c816  cmp     r10, rsi
0x18003c819  jz      short loc_18003C83E
0x18003c81b  cmp     byte ptr [r10+19h], 6
0x18003c820  jb      short loc_18003C83E
0x18003c822  or      ecx, 0FFFFFFFFh; int
0x18003c825  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003c82a  mov     rcx, [r10+10h]
0x18003c82e  mov     edx, 26h ; '&'
0x18003c833  mov     r9, rax
0x18003c836  mov     r8, r14
0x18003c839  call    WPP_SF_s
0x18003c83e  mov     rbx, [rsp+48h+arg_10]
0x18003c843  add     rsp, 30h
0x18003c847  pop     r14
0x18003c849  pop     rdi
0x18003c84a  pop     rsi
0x18003c84b  retn
```
