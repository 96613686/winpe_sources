# RemoteSubscription::RpcStatusSubscription::Stop(void)

- ea: `0x18004b378`
- end: `0x18004b4ef`
- name: `?Stop@RpcStatusSubscription@RemoteSubscription@@QEAA_NXZ`
- size: `375`
- prototype: `char __fastcall(RemoteSubscription::RpcStatusSubscription *this, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180049df4`
- `0x18004ad50`
- `0x18004ae38`

## callees

- `0x18004b378`
- `0x1800ac8dc`
- `0x1800ac92c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004b3f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004b3f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b3d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18004b3d4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b3fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004b3fa`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18004b3a6`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18004b3a6`

## pseudocode

```c
char __fastcall RemoteSubscription::RpcStatusSubscription::Stop(
        RemoteSubscription::RpcStatusSubscription *this,
        __int64 a2,
        __int64 a3)
{
  unsigned int *v4; // r14
  unsigned int v5; // eax
  __int64 v6; // r9
  struct _TP_WAIT *v7; // rcx
  _QWORD *v9; // rcx
  __int64 v10; // rdx

  if ( !*((_BYTE *)this + 120) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, this);
    }
    return 0;
  }
  v4 = (unsigned int *)((char *)this + 116);
  v5 = RpcServerUnsubscribeForNotification(
         *(RPC_BINDING_HANDLE *)(*(_QWORD *)this + 32LL),
         *((RPC_NOTIFICATIONS *)this + 28),
         (unsigned int *)this + 29);
  if ( v5
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v5, this);
  }
  v6 = *v4;
  *((_BYTE *)this + 120) = 0;
  *(_QWORD *)this = 0;
  if ( (_DWORD)v6 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v10 = 13;
    goto LABEL_21;
  }
  if ( !WaitForSingleObject(*((HANDLE *)this + 1), 0) )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v6 = *v4;
    v10 = 14;
LABEL_21:
    WPP_SF_Dq(v9[2], v10, &WPP_939241f3766634594ecc55fb100debfa_Traceguids, v6, this);
    return 0;
  }
  v7 = (struct _TP_WAIT *)*((_QWORD *)this + 13);
  if ( v7 )
    SetThreadpoolWait(v7, 0, 0);
  SetEvent(*((HANDLE *)this + 3));
  return 1;
}

```

## disassembly

```asm
0x18004b378  mov     [rsp+arg_0], rbx
0x18004b37d  mov     [rsp+arg_8], rsi
0x18004b382  push    r14
0x18004b384  sub     rsp, 30h
0x18004b388  cmp     byte ptr [rcx+78h], 0
0x18004b38c  mov     rbx, rcx
0x18004b38f  jz      loc_18004B423
0x18004b395  mov     edx, [rbx+70h]; Notification
0x18004b398  lea     r14, [rcx+74h]
0x18004b39c  mov     rcx, [rcx]
0x18004b39f  mov     r8, r14; NotificationsQueued
0x18004b3a2  mov     rcx, [rcx+20h]; Binding
0x18004b3a6  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18004b3ac  lea     rsi, WPP_GLOBAL_Control
0x18004b3b3  test    eax, eax
0x18004b3b5  jnz     loc_18004B4A6
0x18004b3bb  mov     r9d, [r14]
0x18004b3be  mov     byte ptr [rbx+78h], 0
0x18004b3c2  mov     qword ptr [rbx], 0
0x18004b3c9  test    r9d, r9d
0x18004b3cc  jnz     short loc_18004B404
0x18004b3ce  mov     rcx, [rbx+8]; hHandle
0x18004b3d2  xor     edx, edx; dwMilliseconds
0x18004b3d4  call    cs:__imp_WaitForSingleObject
0x18004b3da  test    eax, eax
0x18004b3dc  jz      loc_18004B469
0x18004b3e2  mov     rcx, [rbx+68h]; pwa
0x18004b3e6  test    rcx, rcx
0x18004b3e9  jz      short loc_18004B3F6
0x18004b3eb  xor     r8d, r8d; pftTimeout
0x18004b3ee  xor     edx, edx; h
0x18004b3f0  call    cs:__imp_SetThreadpoolWait
0x18004b3f6  mov     rcx, [rbx+18h]; hEvent
0x18004b3fa  call    cs:__imp_SetEvent
0x18004b400  mov     al, 1
0x18004b402  jmp     short loc_18004B412
0x18004b404  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b40b  cmp     rcx, rsi
0x18004b40e  jnz     short loc_18004B453
0x18004b410  xor     al, al
0x18004b412  mov     rbx, [rsp+38h+arg_0]
0x18004b417  mov     rsi, [rsp+38h+arg_8]
0x18004b41c  add     rsp, 30h
0x18004b420  pop     r14
0x18004b422  retn
0x18004b423  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b42a  lea     rsi, WPP_GLOBAL_Control
0x18004b431  cmp     rcx, rsi
0x18004b434  jz      short loc_18004B410
0x18004b436  test    dword ptr [rcx+1Ch], 100h
0x18004b43d  jz      short loc_18004B410
0x18004b43f  cmp     byte ptr [rcx+19h], 2
0x18004b443  jb      short loc_18004B410
0x18004b445  mov     rcx, [rcx+10h]
0x18004b449  mov     r9, rbx
0x18004b44c  call    WPP_SF_q
0x18004b451  jmp     short loc_18004B410
0x18004b453  test    dword ptr [rcx+1Ch], 100h
0x18004b45a  jz      short loc_18004B410
0x18004b45c  cmp     byte ptr [rcx+19h], 2
0x18004b460  jb      short loc_18004B410
0x18004b462  mov     edx, 0Dh
0x18004b467  jmp     short loc_18004B48C
0x18004b469  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b470  cmp     rcx, rsi
0x18004b473  jz      short loc_18004B410
0x18004b475  test    dword ptr [rcx+1Ch], 100h
0x18004b47c  jz      short loc_18004B410
0x18004b47e  cmp     byte ptr [rcx+19h], 2
0x18004b482  jb      short loc_18004B410
0x18004b484  mov     r9d, [r14]
0x18004b487  mov     edx, 0Eh
0x18004b48c  mov     rcx, [rcx+10h]
0x18004b490  lea     r8, WPP_939241f3766634594ecc55fb100debfa_Traceguids
0x18004b497  mov     [rsp+38h+var_18], rbx
0x18004b49c  call    WPP_SF_Dq
0x18004b4a1  jmp     loc_18004B410
0x18004b4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b4ad  cmp     rcx, rsi
0x18004b4b0  jz      loc_18004B3BB
0x18004b4b6  test    dword ptr [rcx+1Ch], 100h
0x18004b4bd  jz      loc_18004B3BB
0x18004b4c3  cmp     byte ptr [rcx+19h], 2
0x18004b4c7  jb      loc_18004B3BB
0x18004b4cd  mov     rcx, [rcx+10h]
0x18004b4d1  lea     r8, WPP_939241f3766634594ecc55fb100debfa_Traceguids
0x18004b4d8  mov     edx, 0Ch
0x18004b4dd  mov     [rsp+38h+var_18], rbx
0x18004b4e2  mov     r9d, eax
0x18004b4e5  call    WPP_SF_Dq
0x18004b4ea  jmp     loc_18004B3BB
```
