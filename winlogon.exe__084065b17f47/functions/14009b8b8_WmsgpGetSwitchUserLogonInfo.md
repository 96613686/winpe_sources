# WmsgpGetSwitchUserLogonInfo

- ea: `0x14009b8b8`
- end: `0x14009ba17`
- name: `WmsgpGetSwitchUserLogonInfo`
- size: `351`
- prototype: `RPC_STATUS __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14004f830`

## callees

- `0x140053720`
- `0x1400544e0`
- `0x14009b8b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14009b924`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14009b924`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009b9a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009b9ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009b9a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009b9ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009b9ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009b9ec`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x14009b90c`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x14009b90c`
- `RPCRT4!RpcAsyncCancelCall` at `0x14009b9bc`
- `RPCRT4!RpcAsyncCancelCall` at `0x14009b9bc`
- `RPCRT4!Ndr64AsyncClientCall` at `0x14009b988`
- `RPCRT4!Ndr64AsyncClientCall` at `0x14009b988`
- `RPCRT4!I_RpcExceptionFilter` at `0x1400a0811`
- `RPCRT4!I_RpcExceptionFilter` at `0x1400a0811`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14009b9e1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14009b9e1`

## pseudocode

```c
RPC_STATUS __fastcall WmsgpGetSwitchUserLogonInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  RPC_STATUS result; // eax
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  RPCNOTIFICATION_ROUTINE *v11; // rdi
  RPC_STATUS v12; // ebx
  DWORD v13; // esi
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-B8h] BYREF

  memset_0(&pAsync, 0, sizeof(pAsync));
  result = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( !result )
  {
    EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 0, 0, 0);
    v11 = EventW;
    if ( EventW )
    {
      pAsync.UserInfo = 0;
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.APC.NotificationRoutine = EventW;
      v12 = 0;
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&stru_1400A5AF8, 4u, 0, &pAsync, a1, a2, a3, a4, a5);
      v13 = WaitForSingleObject(v11, 0xFFFFFFFF);
      if ( v13 == 258 )
      {
        v12 = RpcAsyncCancelCall(&pAsync, 1);
        if ( !v12 )
          v13 = WaitForSingleObject(v11, 0xFFFFFFFF);
      }
      if ( !v13 )
      {
        v12 = RpcAsyncCompleteCall(&pAsync, 0);
        CloseHandle(v11);
      }
      return v12;
    }
    else
    {
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14009b8b8  push    rbx
0x14009b8ba  push    rsi
0x14009b8bb  push    rdi
0x14009b8bc  push    r12
0x14009b8be  push    r13
0x14009b8c0  push    r14
0x14009b8c2  push    r15
0x14009b8c4  sub     rsp, 0E0h
0x14009b8cb  mov     rax, cs:__security_cookie
0x14009b8d2  xor     rax, rsp
0x14009b8d5  mov     [rsp+118h+var_48], rax
0x14009b8dd  mov     r12, r9
0x14009b8e0  mov     r15, r8
0x14009b8e3  mov     r14, rdx
0x14009b8e6  mov     rsi, rcx
0x14009b8e9  mov     r13, [rsp+118h+arg_20]
0x14009b8f1  mov     ebx, 70h ; 'p'
0x14009b8f6  mov     r8d, ebx; Size
0x14009b8f9  xor     edx, edx; Val
0x14009b8fb  lea     rcx, [rsp+118h+pAsync]; void *
0x14009b900  call    memset_0
0x14009b905  mov     edx, ebx; Size
0x14009b907  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14009b90c  call    cs:__imp_RpcAsyncInitializeHandle
0x14009b912  test    eax, eax
0x14009b914  jnz     loc_14009B9F4
0x14009b91a  xor     r9d, r9d; lpName
0x14009b91d  xor     r8d, r8d; bInitialState
0x14009b920  xor     edx, edx; bManualReset
0x14009b922  xor     ecx, ecx; lpEventAttributes
0x14009b924  call    cs:__imp_CreateEventW
0x14009b92a  mov     rdi, rax
0x14009b92d  mov     [rsp+118h+var_C8], rax
0x14009b932  test    rax, rax
0x14009b935  jnz     short loc_14009B93F
0x14009b937  lea     eax, [rbx-62h]
0x14009b93a  jmp     loc_14009B9F4
0x14009b93f  mov     [rsp+118h+pAsync.UserInfo], 0
0x14009b948  mov     [rsp+118h+pAsync.NotificationType], 1
0x14009b953  mov     qword ptr [rsp+118h+pAsync.u], rax
0x14009b95b  xor     ebx, ebx
0x14009b95d  mov     [rsp+118h+var_D8], r13
0x14009b962  mov     [rsp+118h+var_E0], r12
0x14009b967  mov     [rsp+118h+var_E8], r15
0x14009b96c  mov     [rsp+118h+var_F0], r14
0x14009b971  mov     [rsp+118h+var_F8], rsi
0x14009b976  lea     r9, [rsp+118h+pAsync]
0x14009b97b  xor     r8d, r8d; pReturnValue
0x14009b97e  lea     edx, [rbx+4]; nProcNum
0x14009b981  lea     rcx, stru_1400A5AF8; pProxyInfo
0x14009b988  call    cs:__imp_Ndr64AsyncClientCall
0x14009b98e  jmp     short loc_14009B997
0x14009b990  mov     ebx, eax
0x14009b992  mov     rdi, [rsp+118h+var_C8]
0x14009b997  mov     rcx, rdi; hHandle
0x14009b99a  test    ebx, ebx
0x14009b99c  jnz     short loc_14009B9EC
0x14009b99e  or      r14d, 0FFFFFFFFh
0x14009b9a2  mov     edx, r14d; dwMilliseconds
0x14009b9a5  call    cs:__imp_WaitForSingleObject
0x14009b9ab  mov     esi, eax
0x14009b9ad  cmp     eax, 102h
0x14009b9b2  jnz     short loc_14009B9D6
0x14009b9b4  lea     edx, [rbx+1]; fAbort
0x14009b9b7  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14009b9bc  call    cs:__imp_RpcAsyncCancelCall
0x14009b9c2  mov     ebx, eax
0x14009b9c4  test    eax, eax
0x14009b9c6  jnz     short loc_14009B9D6
0x14009b9c8  mov     edx, r14d; dwMilliseconds
0x14009b9cb  mov     rcx, rdi; hHandle
0x14009b9ce  call    cs:__imp_WaitForSingleObject
0x14009b9d4  mov     esi, eax
0x14009b9d6  test    esi, esi
0x14009b9d8  jnz     short loc_14009B9F2
0x14009b9da  xor     edx, edx; Reply
0x14009b9dc  lea     rcx, [rsp+118h+pAsync]; pAsync
0x14009b9e1  call    cs:__imp_RpcAsyncCompleteCall
0x14009b9e7  mov     ebx, eax
0x14009b9e9  mov     rcx, rdi; hObject
0x14009b9ec  call    cs:__imp_CloseHandle
0x14009b9f2  mov     eax, ebx
0x14009b9f4  mov     rcx, [rsp+118h+var_48]
0x14009b9fc  xor     rcx, rsp; StackCookie
0x14009b9ff  call    __security_check_cookie
0x14009ba04  add     rsp, 0E0h
0x14009ba0b  pop     r15
0x14009ba0d  pop     r14
0x14009ba0f  pop     r13
0x14009ba11  pop     r12
0x14009ba13  pop     rdi
0x14009ba14  pop     rsi
0x14009ba15  pop     rbx
0x14009ba16  retn
0x1400a0803  push    rbp
0x1400a0805  sub     rsp, 50h
0x1400a0809  mov     rbp, rdx
0x1400a080c  mov     rcx, [rcx]
0x1400a080f  mov     ecx, [rcx]; ExceptionCode
0x1400a0811  call    cs:__imp_I_RpcExceptionFilter
0x1400a0817  nop
0x1400a0818  add     rsp, 50h
0x1400a081c  pop     rbp
0x1400a081d  retn
```
