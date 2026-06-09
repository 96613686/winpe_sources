# WFDSConMgr::RPC::CServer::CompleteAsyncCall(_RPC_ASYNC_STATE *,ulong,bool,bool)

- ea: `0x1800072fc`
- end: `0x1800074cf`
- name: `?CompleteAsyncCall@CServer@RPC@WFDSConMgr@@QEAAXPEAU_RPC_ASYNC_STATE@@K_N1@Z`
- size: `467`
- prototype: `void __usercall(WFDSConMgr::RPC::CServer *__hidden this@<rcx>, PRPC_ASYNC_STATE pAsync@<rdx>, unsigned int@<r8d>, bool@<r9b>, bool)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007004`
- `0x18000a02c`
- `0x18000a138`
- `0x18000a208`
- `0x18000a6f4`

## callees

- `0x180004898`
- `0x1800072fc`
- `0x18005c888`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180007480`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180007480`
- `RPCRT4!RpcAsyncAbortCall` at `0x180007408`
- `RPCRT4!RpcAsyncAbortCall` at `0x180007408`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180007348`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180007390`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180007348`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180007390`

## string_xrefs

- `0x18000743a`: `WFDSConMgr::RPC::CServer::CompleteAsyncCall`
- `0x1800074ae`: `WFDSConMgr::RPC::CServer::CompleteAsyncCall`
- `0x180007494`: `RpcAsyncCompleteCall failed`

## pseudocode

```c
void __fastcall WFDSConMgr::RPC::CServer::CompleteAsyncCall(
        WFDSConMgr::RPC::CServer *this,
        PRPC_ASYNC_STATE pAsync,
        unsigned int a3,
        char a4,
        bool a5)
{
  unsigned int v8; // eax
  unsigned int v9; // eax
  PVOID *v10; // rcx
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  unsigned int NotificationsQueued[10]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int ExceptionCode; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+20h] BYREF

  ExceptionCode = a3;
  v15 = 0;
  NotificationsQueued[0] = 0;
  if ( !a5 )
    goto LABEL_12;
  v8 = RpcServerUnsubscribeForNotification(pAsync->RuntimeInfo, RpcNotificationClientDisconnect, &v15);
  if ( v8
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, v8);
  }
  v9 = RpcServerUnsubscribeForNotification(pAsync->RuntimeInfo, RpcNotificationCallCancel, NotificationsQueued);
  if ( !v9 )
    goto LABEL_12;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, v9);
LABEL_12:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 4u && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_d(v10[2], 63, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, ExceptionCode);
    v11 = RpcAsyncAbortCall(pAsync, ExceptionCode);
    if ( v11 )
      WFDSConMgr::CException::Throw(
        v11,
        "WFDSConMgr::RPC::CServer::CompleteAsyncCall",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
        44,
        L"RpcAsyncAbortCall failed",
        this);
  }
  else
  {
    if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 4u && (*((_BYTE *)v10 + 28) & 1) != 0 )
      WPP_SF_d(v10[2], 64, &WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids, ExceptionCode);
    v12 = RpcAsyncCompleteCall(pAsync, &ExceptionCode);
    if ( v12 )
      WFDSConMgr::CException::Throw(
        v12,
        "WFDSConMgr::RPC::CServer::CompleteAsyncCall",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\server\\src\\rpcserver.cpp",
        50,
        L"RpcAsyncCompleteCall failed",
        this);
  }
}

```

## disassembly

```asm
0x1800072fc  mov     rax, rsp
0x1800072ff  mov     [rax+8], rbx
0x180007303  mov     [rax+18h], r8d
0x180007307  push    rsi
0x180007308  push    rdi
0x180007309  push    r15
0x18000730b  sub     rsp, 40h
0x18000730f  cmp     [rsp+58h+arg_20], 0
0x180007317  lea     r15, WPP_GLOBAL_Control
0x18000731e  mov     dil, r9b
0x180007321  mov     dword ptr [rax+20h], 0
0x180007328  mov     rbx, rdx
0x18000732b  mov     dword ptr [rax-28h], 0
0x180007332  mov     rsi, rcx
0x180007335  jz      loc_1800073CA
0x18000733b  mov     rcx, [rbx+20h]; Binding
0x18000733f  lea     r8, [rax+20h]; NotificationsQueued
0x180007343  mov     edx, 1; Notification
0x180007348  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18000734e  test    eax, eax
0x180007350  jz      short loc_180007382
0x180007352  mov     rcx, cs:WPP_GLOBAL_Control
0x180007359  cmp     rcx, r15
0x18000735c  jz      short loc_180007382
0x18000735e  cmp     byte ptr [rcx+19h], 2
0x180007362  jb      short loc_180007382
0x180007364  test    byte ptr [rcx+1Ch], 1
0x180007368  jz      short loc_180007382
0x18000736a  mov     rcx, [rcx+10h]
0x18000736e  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x180007375  mov     edx, 3Dh ; '='
0x18000737a  mov     r9d, eax
0x18000737d  call    WPP_SF_d
0x180007382  mov     rcx, [rbx+20h]; Binding
0x180007386  lea     r8, [rsp+58h+NotificationsQueued]; NotificationsQueued
0x18000738b  mov     edx, 2; Notification
0x180007390  call    cs:__imp_RpcServerUnsubscribeForNotification
0x180007396  test    eax, eax
0x180007398  jz      short loc_1800073CA
0x18000739a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073a1  cmp     rcx, r15
0x1800073a4  jz      short loc_1800073D1
0x1800073a6  cmp     byte ptr [rcx+19h], 2
0x1800073aa  jb      short loc_1800073D1
0x1800073ac  test    byte ptr [rcx+1Ch], 1
0x1800073b0  jz      short loc_1800073D1
0x1800073b2  mov     rcx, [rcx+10h]
0x1800073b6  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x1800073bd  mov     edx, 3Eh ; '>'
0x1800073c2  mov     r9d, eax
0x1800073c5  call    WPP_SF_d
0x1800073ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073d1  test    dil, dil
0x1800073d4  jz      short loc_18000744D
0x1800073d6  cmp     rcx, r15
0x1800073d9  jz      short loc_180007401
0x1800073db  cmp     byte ptr [rcx+19h], 4
0x1800073df  jb      short loc_180007401
0x1800073e1  test    byte ptr [rcx+1Ch], 1
0x1800073e5  jz      short loc_180007401
0x1800073e7  mov     r9d, [rsp+58h+ExceptionCode]
0x1800073ec  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x1800073f3  mov     rcx, [rcx+10h]
0x1800073f7  mov     edx, 3Fh ; '?'
0x1800073fc  call    WPP_SF_d
0x180007401  mov     edx, [rsp+58h+ExceptionCode]; ExceptionCode
0x180007405  mov     rcx, rbx; pAsync
0x180007408  call    cs:__imp_RpcAsyncAbortCall
0x18000740e  test    eax, eax
0x180007410  jz      loc_1800074C1
0x180007416  jle     short loc_180007420
0x180007418  movzx   eax, ax
0x18000741b  or      eax, 80070000h
0x180007420  lea     rcx, aRpcasyncabortc; "RpcAsyncAbortCall failed"
0x180007427  mov     [rsp+58h+var_30], rsi; void *
0x18000742c  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x180007431  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x180007438  mov     ecx, eax; char
0x18000743a  lea     rdx, aWfdsconmgrRpcC_2; "WFDSConMgr::RPC::CServer::CompleteAsync"...
0x180007441  mov     r9d, 42Ch; char
0x180007447  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18000744d  cmp     rcx, r15
0x180007450  jz      short loc_180007478
0x180007452  cmp     byte ptr [rcx+19h], 4
0x180007456  jb      short loc_180007478
0x180007458  test    byte ptr [rcx+1Ch], 1
0x18000745c  jz      short loc_180007478
0x18000745e  mov     r9d, [rsp+58h+ExceptionCode]
0x180007463  lea     r8, WPP_6ceeda260a0234f4bac1ee7bc3ef1298_Traceguids
0x18000746a  mov     rcx, [rcx+10h]
0x18000746e  mov     edx, 40h ; '@'
0x180007473  call    WPP_SF_d
0x180007478  lea     rdx, [rsp+58h+ExceptionCode]; Reply
0x18000747d  mov     rcx, rbx; pAsync
0x180007480  call    cs:__imp_RpcAsyncCompleteCall
0x180007486  test    eax, eax
0x180007488  jz      short loc_1800074C1
0x18000748a  jle     short loc_180007494
0x18000748c  movzx   eax, ax
0x18000748f  or      eax, 80070000h
0x180007494  lea     rcx, aRpcasynccomple; "RpcAsyncCompleteCall failed"
0x18000749b  mov     [rsp+58h+var_30], rsi; void *
0x1800074a0  mov     [rsp+58h+var_38], rcx; unsigned __int16 *
0x1800074a5  lea     r8, aOnecoreuapNetW_2; "onecoreuap\\net\\wlan\\wfdsconmgr\\serv"...
0x1800074ac  mov     ecx, eax; char
0x1800074ae  lea     rdx, aWfdsconmgrRpcC_2; "WFDSConMgr::RPC::CServer::CompleteAsync"...
0x1800074b5  mov     r9d, 432h; char
0x1800074bb  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800074c1  mov     rbx, [rsp+58h+arg_0]
0x1800074c6  add     rsp, 40h
0x1800074ca  pop     r15
0x1800074cc  pop     rdi
0x1800074cd  pop     rsi
0x1800074ce  retn
```
