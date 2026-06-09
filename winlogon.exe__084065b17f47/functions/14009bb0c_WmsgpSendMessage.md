# WmsgpSendMessage

- ea: `0x14009bb0c`
- end: `0x14009bc64`
- name: `WmsgpSendMessage`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14009b5c0`

## callees

- `0x140053720`
- `0x1400544e0`
- `0x14009bb0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14009bb6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14009bb6e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bbf1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bc1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bbf1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bc1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bbe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bc3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bbe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bc3a`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x14009bb56`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x14009bb56`
- `RPCRT4!RpcAsyncCancelCall` at `0x14009bc0a`
- `RPCRT4!RpcAsyncCancelCall` at `0x14009bc0a`
- `RPCRT4!Ndr64AsyncClientCall` at `0x14009bbc7`
- `RPCRT4!Ndr64AsyncClientCall` at `0x14009bbc7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14009bc2f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14009bc2f`

## pseudocode

```c
RPC_STATUS __fastcall WmsgpSendMessage(__int64 a1, int a2, __int64 a3, RPC_STATUS *a4)
{
  RPC_STATUS result; // eax
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  RPCNOTIFICATION_ROUTINE *v9; // rdi
  RPC_STATUS v10; // ebx
  DWORD v11; // esi
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-A8h] BYREF

  memset_0(&pAsync, 0, sizeof(pAsync));
  result = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( !result )
  {
    EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 0, 0, 0);
    v9 = EventW;
    if ( EventW )
    {
      pAsync.UserInfo = 0;
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.APC.NotificationRoutine = EventW;
      v10 = 0;
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&stru_1400A5AF8, 0, 0, &pAsync, a1, a2, 0, 0, EventW, a4);
      v11 = WaitForSingleObject(v9, 0xFFFFFFFF);
      if ( v11 == 258 )
      {
        v10 = RpcAsyncCancelCall(&pAsync, 1);
        if ( !v10 )
          v11 = WaitForSingleObject(v9, 0xFFFFFFFF);
      }
      if ( !v11 )
      {
        v10 = RpcAsyncCompleteCall(&pAsync, 0);
        CloseHandle(v9);
      }
      *a4 = v10;
      return v10;
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
0x14009bb0c  push    rbx
0x14009bb0e  push    rsi
0x14009bb0f  push    rdi
0x14009bb10  push    r14
0x14009bb12  push    r15
0x14009bb14  sub     rsp, 0D0h
0x14009bb1b  mov     rax, cs:__security_cookie
0x14009bb22  xor     rax, rsp
0x14009bb25  mov     [rsp+0F8h+var_38], rax
0x14009bb2d  mov     r14, r9
0x14009bb30  mov     r15d, edx
0x14009bb33  mov     rsi, rcx
0x14009bb36  mov     [rsp+0F8h+var_B0], r9
0x14009bb3b  mov     ebx, 70h ; 'p'
0x14009bb40  mov     r8d, ebx; Size
0x14009bb43  xor     edx, edx; Val
0x14009bb45  lea     rcx, [rsp+0F8h+pAsync]; void *
0x14009bb4a  call    memset_0
0x14009bb4f  mov     edx, ebx; Size
0x14009bb51  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x14009bb56  call    cs:__imp_RpcAsyncInitializeHandle
0x14009bb5c  test    eax, eax
0x14009bb5e  jnz     loc_14009BC45
0x14009bb64  xor     r9d, r9d; lpName
0x14009bb67  xor     r8d, r8d; bInitialState
0x14009bb6a  xor     edx, edx; bManualReset
0x14009bb6c  xor     ecx, ecx; lpEventAttributes
0x14009bb6e  call    cs:__imp_CreateEventW
0x14009bb74  mov     rdi, rax
0x14009bb77  mov     [rsp+0F8h+var_B8], rax
0x14009bb7c  test    rax, rax
0x14009bb7f  jnz     short loc_14009BB89
0x14009bb81  lea     eax, [rbx-62h]
0x14009bb84  jmp     loc_14009BC45
0x14009bb89  mov     [rsp+0F8h+pAsync.UserInfo], 0
0x14009bb92  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x14009bb9a  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x14009bba2  xor     ebx, ebx
0x14009bba4  mov     [rsp+0F8h+var_C0], ebx
0x14009bba8  mov     [rsp+0F8h+var_C8], ebx
0x14009bbac  mov     [rsp+0F8h+var_D0], r15d
0x14009bbb1  mov     [rsp+0F8h+var_D8], rsi
0x14009bbb6  lea     r9, [rsp+0F8h+pAsync]
0x14009bbbb  xor     r8d, r8d; pReturnValue
0x14009bbbe  xor     edx, edx; nProcNum
0x14009bbc0  lea     rcx, stru_1400A5AF8; pProxyInfo
0x14009bbc7  call    cs:__imp_Ndr64AsyncClientCall
0x14009bbcd  jmp     short loc_14009BBDB
0x14009bbcf  mov     ebx, eax
0x14009bbd1  mov     rdi, [rsp+0F8h+var_B8]
0x14009bbd6  mov     r14, [rsp+0F8h+var_B0]
0x14009bbdb  mov     rcx, rdi; hHandle
0x14009bbde  test    ebx, ebx
0x14009bbe0  jz      short loc_14009BBEA
0x14009bbe2  call    cs:__imp_CloseHandle
0x14009bbe8  jmp     short loc_14009BC43
0x14009bbea  or      r15d, 0FFFFFFFFh
0x14009bbee  mov     edx, r15d; dwMilliseconds
0x14009bbf1  call    cs:__imp_WaitForSingleObject
0x14009bbf7  mov     esi, eax
0x14009bbf9  cmp     eax, 102h
0x14009bbfe  jnz     short loc_14009BC24
0x14009bc00  mov     edx, 1; fAbort
0x14009bc05  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x14009bc0a  call    cs:__imp_RpcAsyncCancelCall
0x14009bc10  mov     ebx, eax
0x14009bc12  test    eax, eax
0x14009bc14  jnz     short loc_14009BC24
0x14009bc16  mov     edx, r15d; dwMilliseconds
0x14009bc19  mov     rcx, rdi; hHandle
0x14009bc1c  call    cs:__imp_WaitForSingleObject
0x14009bc22  mov     esi, eax
0x14009bc24  test    esi, esi
0x14009bc26  jnz     short loc_14009BC40
0x14009bc28  xor     edx, edx; Reply
0x14009bc2a  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x14009bc2f  call    cs:__imp_RpcAsyncCompleteCall
0x14009bc35  mov     ebx, eax
0x14009bc37  mov     rcx, rdi; hObject
0x14009bc3a  call    cs:__imp_CloseHandle
0x14009bc40  mov     [r14], ebx
0x14009bc43  mov     eax, ebx
0x14009bc45  mov     rcx, [rsp+0F8h+var_38]
0x14009bc4d  xor     rcx, rsp; StackCookie
0x14009bc50  call    __security_check_cookie
0x14009bc55  add     rsp, 0D0h
0x14009bc5c  pop     r15
0x14009bc5e  pop     r14
0x14009bc60  pop     rdi
0x14009bc61  pop     rsi
0x14009bc62  pop     rbx
0x14009bc63  retn
0x14009e9e5  push    rbp
0x14009e9e7  sub     rsp, 40h
0x14009e9eb  mov     rbp, rdx
0x14009e9ee  mov     rcx, [rcx]
0x14009e9f1  mov     ecx, [rcx]; ExceptionCode
0x14009e9f3  call    cs:__imp_I_RpcExceptionFilter
0x14009e9f9  nop
0x14009e9fa  add     rsp, 40h
0x14009e9fe  pop     rbp
0x14009e9ff  retn
```
