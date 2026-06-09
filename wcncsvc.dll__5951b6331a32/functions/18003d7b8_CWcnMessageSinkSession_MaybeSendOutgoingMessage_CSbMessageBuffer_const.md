# CWcnMessageSinkSession::MaybeSendOutgoingMessage(CSbMessageBuffer const *)

- ea: `0x18003d7b8`
- end: `0x18003d99e`
- name: `?MaybeSendOutgoingMessage@CWcnMessageSinkSession@@AEAA_NPEBVCSbMessageBuffer@@@Z`
- size: `486`
- prototype: `bool __fastcall(CWcnMessageSinkSession *__hidden this, const struct CSbMessageBuffer *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003da64`
- `0x18003dbec`

## callees

- `0x180004f2c`
- `0x180005014`
- `0x18003d7b8`
- `0x180053004`

## import_xrefs

- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003d85c`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003d8bf`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003d85c`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003d8bf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003d916`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003d916`

## pseudocode

```c
bool __fastcall CWcnMessageSinkSession::MaybeSendOutgoingMessage(
        CWcnMessageSinkSession *this,
        const struct CSbMessageBuffer *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // r9
  int v8; // eax
  __int64 v9; // r9
  struct _RPC_ASYNC_STATE *v10; // rcx
  unsigned int Indent; // eax
  __int64 v12; // r10
  char v13; // r11
  bool result; // al
  unsigned int NotificationsQueued; // [rsp+40h] [rbp+8h] BYREF
  int Reply; // [rsp+50h] [rbp+18h] BYREF

  if ( !*((_BYTE *)this + 128) || !*((_BYTE *)this + 168) )
    return 0;
  **((_DWORD **)this + 17) = *((_DWORD *)this + 43);
  **((_DWORD **)this + 18) = 0;
  if ( *((_DWORD *)this + 43) <= 2u )
  {
    **((_QWORD **)this + 19) = **((_QWORD **)a2 + 3);
    v3 = (_QWORD *)*((_QWORD *)a2 + 3);
    if ( v3 )
      v4 = v3[1] - *v3;
    else
      LODWORD(v4) = 0;
    **((_DWORD **)this + 18) = v4;
    *(_OWORD *)*((_QWORD *)this + 20) = *((_OWORD *)a2 + 2);
  }
  v5 = *((_QWORD *)this + 10);
  NotificationsQueued = 0;
  v6 = RpcServerUnsubscribeForNotification(
         *(RPC_BINDING_HANDLE *)(v5 + 32),
         RpcNotificationClientDisconnect,
         &NotificationsQueued);
  v7 = (unsigned int)v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids,
        v7,
        v6 | 0x80000000);
  }
  v8 = RpcServerUnsubscribeForNotification(
         *(RPC_BINDING_HANDLE *)(*((_QWORD *)this + 10) + 32LL),
         RpcNotificationCallCancel,
         &NotificationsQueued);
  v9 = (unsigned int)v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids,
        v9,
        v8 | 0x80000000);
  }
  v10 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)this + 10);
  Reply = 0;
  if ( RpcAsyncCompleteCall(v10, &Reply)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    Indent = (unsigned int)GetIndent(0);
    WPP_SF_sd(*(_QWORD *)(v12 + 16), 38, (unsigned int)WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids, Indent, v13);
  }
  *((_QWORD *)this + 10) = 0;
  result = 1;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_BYTE *)this + 128) = 0;
  *((_BYTE *)this + 168) = 0;
  return result;
}

```

## disassembly

```asm
0x18003d7b8  mov     [rsp+arg_8], rbx
0x18003d7bd  mov     [rsp+arg_18], rbp
0x18003d7c2  push    rdi
0x18003d7c3  sub     rsp, 30h
0x18003d7c7  xor     edi, edi
0x18003d7c9  mov     rbx, rcx
0x18003d7cc  cmp     [rcx+80h], dil
0x18003d7d3  jz      loc_18003D98C
0x18003d7d9  cmp     [rcx+0A8h], dil
0x18003d7e0  jz      loc_18003D98C
0x18003d7e6  mov     eax, [rcx+0ACh]
0x18003d7ec  mov     r8, [rcx+88h]
0x18003d7f3  mov     [r8], eax
0x18003d7f6  mov     rax, [rcx+90h]
0x18003d7fd  mov     [rax], edi
0x18003d7ff  cmp     dword ptr [rcx+0ACh], 2
0x18003d806  ja      short loc_18003D846
0x18003d808  mov     rax, [rdx+18h]
0x18003d80c  mov     rcx, [rcx+98h]
0x18003d813  mov     rax, [rax]
0x18003d816  mov     [rcx], rax
0x18003d819  mov     rax, [rdx+18h]
0x18003d81d  test    rax, rax
0x18003d820  jz      short loc_18003D82B
0x18003d822  mov     rcx, [rax+8]
0x18003d826  sub     rcx, [rax]
0x18003d829  jmp     short loc_18003D82E
0x18003d82b  mov     rcx, rdi
0x18003d82e  mov     rax, [rbx+90h]
0x18003d835  mov     [rax], ecx
0x18003d837  mov     rax, [rbx+0A0h]
0x18003d83e  movups  xmm0, xmmword ptr [rdx+20h]
0x18003d842  movdqu  xmmword ptr [rax], xmm0
0x18003d846  mov     rcx, [rbx+50h]
0x18003d84a  lea     r8, [rsp+38h+NotificationsQueued]; NotificationsQueued
0x18003d84f  mov     [rsp+38h+NotificationsQueued], edi
0x18003d853  mov     edx, 1; Notification
0x18003d858  mov     rcx, [rcx+20h]; Binding
0x18003d85c  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003d862  lea     rbp, WPP_GLOBAL_Control
0x18003d869  mov     r9d, eax
0x18003d86c  test    eax, eax
0x18003d86e  jz      short loc_18003D8AD
0x18003d870  test    eax, eax
0x18003d872  jle     short loc_18003D87D
0x18003d874  movzx   eax, r9w
0x18003d878  or      eax, 80070000h
0x18003d87d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d884  cmp     rcx, rbp
0x18003d887  jz      short loc_18003D8AD
0x18003d889  cmp     byte ptr [rcx+19h], 3
0x18003d88d  jb      short loc_18003D8AD
0x18003d88f  mov     rcx, [rcx+10h]
0x18003d893  lea     r8, WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids
0x18003d89a  or      eax, 80000000h
0x18003d89f  mov     edx, 24h ; '$'
0x18003d8a4  mov     [rsp+38h+var_18], eax
0x18003d8a8  call    WPP_SF_Dd
0x18003d8ad  mov     rcx, [rbx+50h]
0x18003d8b1  lea     r8, [rsp+38h+NotificationsQueued]; NotificationsQueued
0x18003d8b6  mov     edx, 2; Notification
0x18003d8bb  mov     rcx, [rcx+20h]; Binding
0x18003d8bf  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003d8c5  mov     r9d, eax
0x18003d8c8  test    eax, eax
0x18003d8ca  jz      short loc_18003D909
0x18003d8cc  test    eax, eax
0x18003d8ce  jle     short loc_18003D8D9
0x18003d8d0  movzx   eax, r9w
0x18003d8d4  or      eax, 80070000h
0x18003d8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d8e0  cmp     rcx, rbp
0x18003d8e3  jz      short loc_18003D909
0x18003d8e5  cmp     byte ptr [rcx+19h], 3
0x18003d8e9  jb      short loc_18003D909
0x18003d8eb  mov     rcx, [rcx+10h]
0x18003d8ef  lea     r8, WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids
0x18003d8f6  or      eax, 80000000h
0x18003d8fb  mov     edx, 25h ; '%'
0x18003d900  mov     [rsp+38h+var_18], eax
0x18003d904  call    WPP_SF_Dd
0x18003d909  mov     rcx, [rbx+50h]; pAsync
0x18003d90d  lea     rdx, [rsp+38h+Reply]; Reply
0x18003d912  mov     [rsp+38h+Reply], edi
0x18003d916  call    cs:__imp_RpcAsyncCompleteCall
0x18003d91c  mov     r11d, eax
0x18003d91f  test    eax, eax
0x18003d921  jz      short loc_18003D95A
0x18003d923  mov     r10, cs:WPP_GLOBAL_Control
0x18003d92a  cmp     r10, rbp
0x18003d92d  jz      short loc_18003D95A
0x18003d92f  cmp     byte ptr [r10+19h], 3
0x18003d934  jb      short loc_18003D95A
0x18003d936  xor     ecx, ecx; int
0x18003d938  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003d93d  mov     rcx, [r10+10h]
0x18003d941  lea     r8, WPP_f858ace61d993a6396e44ebc084c96fb_Traceguids
0x18003d948  mov     edx, 26h ; '&'
0x18003d94d  mov     [rsp+38h+var_18], r11d
0x18003d952  mov     r9, rax
0x18003d955  call    WPP_SF_sd
0x18003d95a  mov     [rbx+50h], rdi
0x18003d95e  mov     al, 1
0x18003d960  mov     [rbx+88h], rdi
0x18003d967  mov     [rbx+90h], rdi
0x18003d96e  mov     [rbx+98h], rdi
0x18003d975  mov     [rbx+0A0h], rdi
0x18003d97c  mov     [rbx+80h], dil
0x18003d983  mov     [rbx+0A8h], dil
0x18003d98a  jmp     short loc_18003D98E
0x18003d98c  xor     al, al
0x18003d98e  mov     rbx, [rsp+38h+arg_8]
0x18003d993  mov     rbp, [rsp+38h+arg_18]
0x18003d998  add     rsp, 30h
0x18003d99c  pop     rdi
0x18003d99d  retn
```
