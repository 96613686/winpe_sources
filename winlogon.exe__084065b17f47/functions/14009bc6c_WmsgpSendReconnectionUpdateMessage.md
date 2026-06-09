# WmsgpSendReconnectionUpdateMessage

- ea: `0x14009bc6c`
- end: `0x14009be19`
- name: `WmsgpSendReconnectionUpdateMessage`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14009b620`

## callees

- `0x140053720`
- `0x1400544e0`
- `0x14009bc6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14009bcd4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14009bcd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bda0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bdce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bda0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009bdce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bd91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bdef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bd91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009bdef`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x14009bcbc`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x14009bcbc`
- `RPCRT4!RpcAsyncCancelCall` at `0x14009bdbc`
- `RPCRT4!RpcAsyncCancelCall` at `0x14009bdbc`
- `RPCRT4!Ndr64AsyncClientCall` at `0x14009bd76`
- `RPCRT4!Ndr64AsyncClientCall` at `0x14009bd76`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14009bde4`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14009bde4`

## pseudocode

```c
RPC_STATUS __fastcall WmsgpSendReconnectionUpdateMessage(__int64 a1, _OWORD *a2, RPC_STATUS *a3)
{
  RPC_STATUS result; // eax
  RPCNOTIFICATION_ROUTINE *EventW; // rax
  RPCNOTIFICATION_ROUTINE *v8; // rdi
  RPC_STATUS v9; // ebx
  DWORD v10; // esi
  _OWORD v11[6]; // [rsp+50h] [rbp-108h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-A8h] BYREF

  memset_0(&pAsync, 0, sizeof(pAsync));
  result = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( !result )
  {
    EventW = (RPCNOTIFICATION_ROUTINE *)CreateEventW(0, 0, 0, 0);
    v8 = EventW;
    if ( EventW )
    {
      pAsync.UserInfo = 0;
      pAsync.NotificationType = RpcNotificationTypeEvent;
      pAsync.u.APC.NotificationRoutine = EventW;
      v9 = 0;
      v11[0] = *a2;
      v11[1] = a2[1];
      v11[2] = a2[2];
      v11[3] = a2[3];
      v11[4] = a2[4];
      v11[5] = a2[5];
      Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&stru_1400A5AF8, 3u, 0, &pAsync, a1, v11, 0);
      v10 = WaitForSingleObject(v8, 0xFFFFFFFF);
      if ( v10 == 258 )
      {
        v9 = RpcAsyncCancelCall(&pAsync, 1);
        if ( !v9 )
          v10 = WaitForSingleObject(v8, 0xFFFFFFFF);
      }
      if ( !v10 )
      {
        v9 = RpcAsyncCompleteCall(&pAsync, 0);
        CloseHandle(v8);
      }
      *a3 = v9;
      return v9;
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
0x14009bc6c  push    rbx
0x14009bc6e  push    rsi
0x14009bc6f  push    rdi
0x14009bc70  push    r14
0x14009bc72  push    r15
0x14009bc74  sub     rsp, 130h
0x14009bc7b  mov     rax, cs:__security_cookie
0x14009bc82  xor     rax, rsp
0x14009bc85  mov     [rsp+158h+var_38], rax
0x14009bc8d  mov     r14, r8
0x14009bc90  mov     rsi, rdx
0x14009bc93  mov     r15, rcx
0x14009bc96  mov     [rsp+158h+var_110], r8
0x14009bc9b  mov     ebx, 70h ; 'p'
0x14009bca0  mov     r8d, ebx; Size
0x14009bca3  xor     edx, edx; Val
0x14009bca5  lea     rcx, [rsp+158h+pAsync]; void *
0x14009bcad  call    memset_0
0x14009bcb2  mov     edx, ebx; Size
0x14009bcb4  lea     rcx, [rsp+158h+pAsync]; pAsync
0x14009bcbc  call    cs:__imp_RpcAsyncInitializeHandle
0x14009bcc2  test    eax, eax
0x14009bcc4  jnz     loc_14009BDFA
0x14009bcca  xor     r9d, r9d; lpName
0x14009bccd  xor     r8d, r8d; bInitialState
0x14009bcd0  xor     edx, edx; bManualReset
0x14009bcd2  xor     ecx, ecx; lpEventAttributes
0x14009bcd4  call    cs:__imp_CreateEventW
0x14009bcda  mov     rdi, rax
0x14009bcdd  mov     [rsp+158h+var_118], rax
0x14009bce2  test    rax, rax
0x14009bce5  jnz     short loc_14009BCEF
0x14009bce7  lea     eax, [rbx-62h]
0x14009bcea  jmp     loc_14009BDFA
0x14009bcef  mov     [rsp+158h+pAsync.UserInfo], 0
0x14009bcfb  mov     [rsp+158h+pAsync.NotificationType], 1
0x14009bd06  mov     qword ptr [rsp+158h+pAsync.u], rax
0x14009bd0e  xor     ebx, ebx
0x14009bd10  movaps  xmm0, xmmword ptr [rsi]
0x14009bd13  movaps  [rsp+158h+var_108], xmm0
0x14009bd18  movaps  xmm1, xmmword ptr [rsi+10h]
0x14009bd1c  movaps  [rsp+158h+var_F8], xmm1
0x14009bd21  movaps  xmm0, xmmword ptr [rsi+20h]
0x14009bd25  movaps  [rsp+158h+var_E8], xmm0
0x14009bd2a  movaps  xmm1, xmmword ptr [rsi+30h]
0x14009bd2e  movaps  [rsp+158h+var_D8], xmm1
0x14009bd36  movaps  xmm0, xmmword ptr [rsi+40h]
0x14009bd3a  movaps  [rsp+158h+var_C8], xmm0
0x14009bd42  movaps  xmm1, xmmword ptr [rsi+50h]
0x14009bd46  movaps  [rsp+158h+var_B8], xmm1
0x14009bd4e  mov     [rsp+158h+var_128], ebx
0x14009bd52  lea     rax, [rsp+158h+var_108]
0x14009bd57  mov     [rsp+158h+var_130], rax
0x14009bd5c  mov     [rsp+158h+var_138], r15
0x14009bd61  lea     r9, [rsp+158h+pAsync]
0x14009bd69  xor     r8d, r8d; pReturnValue
0x14009bd6c  lea     edx, [rbx+3]; nProcNum
0x14009bd6f  lea     rcx, stru_1400A5AF8; pProxyInfo
0x14009bd76  call    cs:__imp_Ndr64AsyncClientCall
0x14009bd7c  jmp     short loc_14009BD8A
0x14009bd7e  mov     ebx, eax
0x14009bd80  mov     rdi, [rsp+158h+var_118]
0x14009bd85  mov     r14, [rsp+158h+var_110]
0x14009bd8a  mov     rcx, rdi; hHandle
0x14009bd8d  test    ebx, ebx
0x14009bd8f  jz      short loc_14009BD99
0x14009bd91  call    cs:__imp_CloseHandle
0x14009bd97  jmp     short loc_14009BDF8
0x14009bd99  or      r15d, 0FFFFFFFFh
0x14009bd9d  mov     edx, r15d; dwMilliseconds
0x14009bda0  call    cs:__imp_WaitForSingleObject
0x14009bda6  mov     esi, eax
0x14009bda8  cmp     eax, 102h
0x14009bdad  jnz     short loc_14009BDD6
0x14009bdaf  mov     edx, 1; fAbort
0x14009bdb4  lea     rcx, [rsp+158h+pAsync]; pAsync
0x14009bdbc  call    cs:__imp_RpcAsyncCancelCall
0x14009bdc2  mov     ebx, eax
0x14009bdc4  test    eax, eax
0x14009bdc6  jnz     short loc_14009BDD6
0x14009bdc8  mov     edx, r15d; dwMilliseconds
0x14009bdcb  mov     rcx, rdi; hHandle
0x14009bdce  call    cs:__imp_WaitForSingleObject
0x14009bdd4  mov     esi, eax
0x14009bdd6  test    esi, esi
0x14009bdd8  jnz     short loc_14009BDF5
0x14009bdda  xor     edx, edx; Reply
0x14009bddc  lea     rcx, [rsp+158h+pAsync]; pAsync
0x14009bde4  call    cs:__imp_RpcAsyncCompleteCall
0x14009bdea  mov     ebx, eax
0x14009bdec  mov     rcx, rdi; hObject
0x14009bdef  call    cs:__imp_CloseHandle
0x14009bdf5  mov     [r14], ebx
0x14009bdf8  mov     eax, ebx
0x14009bdfa  mov     rcx, [rsp+158h+var_38]
0x14009be02  xor     rcx, rsp; StackCookie
0x14009be05  call    __security_check_cookie
0x14009be0a  add     rsp, 130h
0x14009be11  pop     r15
0x14009be13  pop     r14
0x14009be15  pop     rdi
0x14009be16  pop     rsi
0x14009be17  pop     rbx
0x14009be18  retn
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
