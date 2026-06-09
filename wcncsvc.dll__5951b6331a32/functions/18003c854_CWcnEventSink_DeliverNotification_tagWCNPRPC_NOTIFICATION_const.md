# CWcnEventSink::DeliverNotification(tagWCNPRPC_NOTIFICATION const *)

- ea: `0x18003c854`
- end: `0x18003cac8`
- name: `?DeliverNotification@CWcnEventSink@@AEAAJPEBUtagWCNPRPC_NOTIFICATION@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(CWcnEventSink *__hidden this, const struct tagWCNPRPC_NOTIFICATION *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003c1dc`
- `0x18003cad0`

## callees

- `0x180004f2c`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18003c5c8`
- `0x18003c854`
- `0x180053004`
- `0x180056490`

## import_xrefs

- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c974`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c9cf`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c974`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003c9cf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ca21`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003ca21`

## pseudocode

```c
__int64 __fastcall CWcnEventSink::DeliverNotification(CWcnEventSink *this, const struct tagWCNPRPC_NOTIFICATION *a2)
{
  _BYTE *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  unsigned int v8; // eax
  __int64 v9; // r10
  int v10; // eax
  signed int v11; // ebx
  _BYTE *v12; // r10
  RPC_STATUS v13; // eax
  unsigned int v14; // ebx
  RPC_STATUS v15; // eax
  unsigned int v16; // ebx
  RPC_STATUS v17; // edi
  unsigned int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // r10
  unsigned int v21; // eax
  __int64 v22; // r10
  unsigned int NotificationsQueued; // [rsp+58h] [rbp+10h] BYREF
  int Reply; // [rsp+60h] [rbp+18h] BYREF

  Reply = 0;
  NotificationsQueued = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 44, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 5u )
    {
      v8 = (unsigned int)GetIndent(0);
      WPP_SF_sd(
        *(_QWORD *)(v9 + 16),
        46,
        (unsigned int)WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
        v8,
        *(_DWORD *)a2);
    }
    v10 = WcnCopyNotification(*((struct tagWCNPRPC_NOTIFICATION **)this + 9), a2);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v13 = RpcServerUnsubscribeForNotification(
              *(RPC_BINDING_HANDLE *)(*((_QWORD *)this + 8) + 32LL),
              RpcNotificationClientDisconnect,
              &NotificationsQueued);
      if ( v13 )
      {
        v14 = v13 > 0 ? (unsigned __int16)v13 | 0x80070000 : v13;
        v11 = v14 | 0x80000000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
            (unsigned int)v13,
            v11);
      }
      v15 = RpcServerUnsubscribeForNotification(
              *(RPC_BINDING_HANDLE *)(*((_QWORD *)this + 8) + 32LL),
              RpcNotificationCallCancel,
              &NotificationsQueued);
      if ( v15 )
      {
        v16 = v15 > 0 ? (unsigned __int16)v15 | 0x80070000 : v15;
        v11 = v16 | 0x80000000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
            (unsigned int)v15,
            v11);
      }
      v17 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)this + 8), &Reply);
      CWcnEventSink::ClearActiveCall(this);
      if ( !v17 )
        goto LABEL_37;
      if ( v17 > 0 )
        v18 = (unsigned __int16)v17 | 0x80070000;
      else
        v18 = v17;
      v11 = v18 | 0x80000000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = (unsigned int)GetIndent(0);
          WPP_SF_sd(*(_QWORD *)(v20 + 16), 50, (unsigned int)WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v19, v11);
          goto LABEL_37;
        }
LABEL_38:
        if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (v11 < 0 || v12[25] >= 6u) )
        {
          v21 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v22 + 16), 51, (unsigned int)WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, v21, v11);
        }
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids,
            (unsigned int)v10);
LABEL_37:
          v12 = WPP_GLOBAL_Control;
          goto LABEL_38;
        }
        goto LABEL_38;
      }
    }
    return (unsigned int)v11;
  }
  if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 2u )
    WPP_SF_s(*((_QWORD *)v4 + 2), 45, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids, "pNotification");
  return 2147500035LL;
}

```

## disassembly

```asm
0x18003c854  mov     rax, rsp
0x18003c857  mov     [rax+8], rbx
0x18003c85b  mov     [rax+20h], rbp
0x18003c85f  push    rsi
0x18003c860  push    rdi
0x18003c861  push    r14
0x18003c863  sub     rsp, 30h
0x18003c867  mov     rbx, rdx
0x18003c86a  mov     dword ptr [rax+18h], 0
0x18003c871  mov     rsi, rcx
0x18003c874  mov     dword ptr [rax+10h], 0
0x18003c87b  mov     r10, cs:WPP_GLOBAL_Control
0x18003c882  lea     rbp, WPP_GLOBAL_Control
0x18003c889  lea     r14, WPP_5d51192a8202375b23254a09b83c8f5c_Traceguids
0x18003c890  mov     edi, 1
0x18003c895  cmp     r10, rbp
0x18003c898  jz      short loc_18003C8C1
0x18003c89a  cmp     byte ptr [r10+19h], 6
0x18003c89f  jb      short loc_18003C8C1
0x18003c8a1  mov     ecx, edi; int
0x18003c8a3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003c8a8  mov     rcx, [r10+10h]
0x18003c8ac  lea     edx, [rdi+2Bh]
0x18003c8af  mov     r9, rax
0x18003c8b2  mov     r8, r14
0x18003c8b5  call    WPP_SF_s
0x18003c8ba  mov     r10, cs:WPP_GLOBAL_Control
0x18003c8c1  test    rbx, rbx
0x18003c8c4  jnz     short loc_18003C8F2
0x18003c8c6  cmp     r10, rbp
0x18003c8c9  jz      short loc_18003C8E8
0x18003c8cb  cmp     byte ptr [r10+19h], 2
0x18003c8d0  jb      short loc_18003C8E8
0x18003c8d2  mov     rcx, [r10+10h]
0x18003c8d6  lea     edx, [rbx+2Dh]
0x18003c8d9  lea     r9, aPnotification; "pNotification"
0x18003c8e0  mov     r8, r14
0x18003c8e3  call    WPP_SF_s
0x18003c8e8  mov     eax, 80004003h
0x18003c8ed  jmp     loc_18003CAB5
0x18003c8f2  cmp     r10, rbp
0x18003c8f5  jz      short loc_18003C91F
0x18003c8f7  cmp     byte ptr [r10+19h], 5
0x18003c8fc  jb      short loc_18003C91F
0x18003c8fe  xor     ecx, ecx; int
0x18003c900  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003c905  mov     ecx, [rbx]
0x18003c907  mov     edx, 2Eh ; '.'
0x18003c90c  mov     [rsp+48h+var_28], ecx
0x18003c910  mov     r9, rax
0x18003c913  mov     rcx, [r10+10h]
0x18003c917  mov     r8, r14
0x18003c91a  call    WPP_SF_sd
0x18003c91f  mov     rcx, [rsi+48h]; struct tagWCNPRPC_NOTIFICATION *
0x18003c923  mov     rdx, rbx; struct tagWCNPRPC_NOTIFICATION *
0x18003c926  call    ?WcnCopyNotification@@YAJPEAUtagWCNPRPC_NOTIFICATION@@PEBU1@@Z; WcnCopyNotification(tagWCNPRPC_NOTIFICATION *,tagWCNPRPC_NOTIFICATION const *)
0x18003c92b  mov     ebx, eax
0x18003c92d  test    eax, eax
0x18003c92f  jns     short loc_18003C965
0x18003c931  mov     r10, cs:WPP_GLOBAL_Control
0x18003c938  cmp     r10, rbp
0x18003c93b  jz      loc_18003CAB3
0x18003c941  cmp     byte ptr [r10+19h], 2
0x18003c946  jb      loc_18003CA83
0x18003c94c  mov     rcx, [r10+10h]
0x18003c950  mov     edx, 2Fh ; '/'
0x18003c955  mov     r9d, eax
0x18003c958  mov     r8, r14
0x18003c95b  call    WPP_SF_d
0x18003c960  jmp     loc_18003CA7C
0x18003c965  mov     rcx, [rsi+40h]
0x18003c969  lea     r8, [rsp+48h+NotificationsQueued]; NotificationsQueued
0x18003c96e  mov     edx, edi; Notification
0x18003c970  mov     rcx, [rcx+20h]; Binding
0x18003c974  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003c97a  test    eax, eax
0x18003c97c  jz      short loc_18003C9BD
0x18003c97e  jg      short loc_18003C984
0x18003c980  mov     ebx, eax
0x18003c982  jmp     short loc_18003C98D
0x18003c984  movzx   ebx, ax
0x18003c987  or      ebx, 80070000h
0x18003c98d  or      ebx, 80000000h
0x18003c993  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c99a  cmp     rcx, rbp
0x18003c99d  jz      short loc_18003C9BD
0x18003c99f  cmp     byte ptr [rcx+19h], 3
0x18003c9a3  jb      short loc_18003C9BD
0x18003c9a5  mov     rcx, [rcx+10h]
0x18003c9a9  mov     edx, 30h ; '0'
0x18003c9ae  mov     r9d, eax
0x18003c9b1  mov     [rsp+48h+var_28], ebx
0x18003c9b5  mov     r8, r14
0x18003c9b8  call    WPP_SF_Dd
0x18003c9bd  mov     rcx, [rsi+40h]
0x18003c9c1  lea     r8, [rsp+48h+NotificationsQueued]; NotificationsQueued
0x18003c9c6  mov     edx, 2; Notification
0x18003c9cb  mov     rcx, [rcx+20h]; Binding
0x18003c9cf  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003c9d5  test    eax, eax
0x18003c9d7  jz      short loc_18003CA18
0x18003c9d9  jg      short loc_18003C9DF
0x18003c9db  mov     ebx, eax
0x18003c9dd  jmp     short loc_18003C9E8
0x18003c9df  movzx   ebx, ax
0x18003c9e2  or      ebx, 80070000h
0x18003c9e8  or      ebx, 80000000h
0x18003c9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9f5  cmp     rcx, rbp
0x18003c9f8  jz      short loc_18003CA18
0x18003c9fa  cmp     byte ptr [rcx+19h], 3
0x18003c9fe  jb      short loc_18003CA18
0x18003ca00  mov     rcx, [rcx+10h]
0x18003ca04  mov     edx, 31h ; '1'
0x18003ca09  mov     r9d, eax
0x18003ca0c  mov     [rsp+48h+var_28], ebx
0x18003ca10  mov     r8, r14
0x18003ca13  call    WPP_SF_Dd
0x18003ca18  mov     rcx, [rsi+40h]; pAsync
0x18003ca1c  lea     rdx, [rsp+48h+Reply]; Reply
0x18003ca21  call    cs:__imp_RpcAsyncCompleteCall
0x18003ca27  mov     rcx, rsi; this
0x18003ca2a  mov     edi, eax
0x18003ca2c  call    ?ClearActiveCall@CWcnEventSink@@QEAAXXZ; CWcnEventSink::ClearActiveCall(void)
0x18003ca31  test    edi, edi
0x18003ca33  jz      short loc_18003CA7C
0x18003ca35  jg      short loc_18003CA3B
0x18003ca37  mov     ebx, edi
0x18003ca39  jmp     short loc_18003CA44
0x18003ca3b  movzx   ebx, di
0x18003ca3e  or      ebx, 80070000h
0x18003ca44  or      ebx, 80000000h
0x18003ca4a  mov     r10, cs:WPP_GLOBAL_Control
0x18003ca51  cmp     r10, rbp
0x18003ca54  jz      short loc_18003CAB3
0x18003ca56  cmp     byte ptr [r10+19h], 2
0x18003ca5b  jb      short loc_18003CA83
0x18003ca5d  xor     ecx, ecx; int
0x18003ca5f  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003ca64  mov     rcx, [r10+10h]
0x18003ca68  mov     edx, 32h ; '2'
0x18003ca6d  mov     r9, rax
0x18003ca70  mov     [rsp+48h+var_28], ebx
0x18003ca74  mov     r8, r14
0x18003ca77  call    WPP_SF_sd
0x18003ca7c  mov     r10, cs:WPP_GLOBAL_Control
0x18003ca83  cmp     r10, rbp
0x18003ca86  jz      short loc_18003CAB3
0x18003ca88  test    ebx, ebx
0x18003ca8a  js      short loc_18003CA93
0x18003ca8c  cmp     byte ptr [r10+19h], 6
0x18003ca91  jb      short loc_18003CAB3
0x18003ca93  or      ecx, 0FFFFFFFFh; int
0x18003ca96  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003ca9b  mov     rcx, [r10+10h]
0x18003ca9f  mov     edx, 33h ; '3'
0x18003caa4  mov     r9, rax
0x18003caa7  mov     [rsp+48h+var_28], ebx
0x18003caab  mov     r8, r14
0x18003caae  call    WPP_SF_sd
0x18003cab3  mov     eax, ebx
0x18003cab5  mov     rbx, [rsp+48h+arg_0]
0x18003caba  mov     rbp, [rsp+48h+arg_18]
0x18003cabf  add     rsp, 30h
0x18003cac3  pop     r14
0x18003cac5  pop     rdi
0x18003cac6  pop     rsi
0x18003cac7  retn
```
