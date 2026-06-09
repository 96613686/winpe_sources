# ScGetNotifyResults(void *,void *,_SC_RPC_NOTIFY_PARAMS_LIST * *)

- ea: `0x18003bccc`
- end: `0x18003be28`
- name: `?ScGetNotifyResults@@YAKPEAX0PEAPEAU_SC_RPC_NOTIFY_PARAMS_LIST@@@Z`
- size: `348`
- prototype: `unsigned int(void *, void *, struct _SC_RPC_NOTIFY_PARAMS_LIST **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003b8a4`
- `0x18003be30`

## callees

- `0x18003bccc`
- `0x18004abac`
- `0x18004f91a`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bda8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bda8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdde`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003bd1b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003bd1b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bd9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bdd4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bd9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003bdd4`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18003bd28`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18003bd28`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003bdf2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18003bdf2`
- `RPCRT4!RpcAsyncCancelCall` at `0x18003bdbc`
- `RPCRT4!RpcAsyncCancelCall` at `0x18003bdbc`
- `RPCRT4!NdrAsyncClientCall` at `0x18003bd6d`
- `RPCRT4!NdrAsyncClientCall` at `0x18003bd6d`

## pseudocode

```c
__int64 __fastcall ScGetNotifyResults(void *a1, void *a2, struct _SC_RPC_NOTIFY_PARAMS_LIST **a3)
{
  unsigned int v6; // eax
  RPC_STATUS v7; // eax
  DWORD Reply; // [rsp+30h] [rbp-B8h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+38h] [rbp-B0h]
  void *v11; // [rsp+40h] [rbp-A8h]
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-98h] BYREF

  v11 = a2;
  Reply = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  ResetEvent(a2);
  v6 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v6 )
    return v6;
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)a2;
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  v10.Pointer = NdrAsyncClientCall(&pStubDescriptor, &byte_180060D1C, &pAsync, a1, a3).Pointer;
  Reply = (DWORD)v10.Pointer;
  if ( WaitForSingleObject(a2, 0xFFFFFFFF) )
  {
    Reply = GetLastError();
    v7 = RpcAsyncCancelCall(&pAsync, 1);
    if ( v7 )
      Reply = v7;
    if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
      Reply = GetLastError();
  }
  v6 = RpcAsyncCompleteCall(&pAsync, &Reply);
  if ( v6 )
    return v6;
  return Reply;
}

```

## disassembly

```asm
0x18003bccc  mov     [rsp+arg_18], rbx
0x18003bcd1  push    rsi
0x18003bcd2  push    rdi
0x18003bcd3  push    r14
0x18003bcd5  sub     rsp, 0D0h
0x18003bcdc  mov     rax, cs:__security_cookie
0x18003bce3  xor     rax, rsp
0x18003bce6  mov     [rsp+0E8h+var_28], rax
0x18003bcee  mov     r14, r8
0x18003bcf1  mov     rdi, rdx
0x18003bcf4  mov     rsi, rcx
0x18003bcf7  mov     [rsp+0E8h+var_A8], rdx
0x18003bcfc  mov     [rsp+0E8h+Reply], 0
0x18003bd04  mov     ebx, 70h ; 'p'
0x18003bd09  mov     r8d, ebx; Size
0x18003bd0c  xor     edx, edx; Val
0x18003bd0e  lea     rcx, [rsp+0E8h+pAsync]; void *
0x18003bd13  call    memset_0
0x18003bd18  mov     rcx, rdi; hEvent
0x18003bd1b  call    cs:__imp_ResetEvent
0x18003bd21  mov     edx, ebx; Size
0x18003bd23  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18003bd28  call    cs:__imp_RpcAsyncInitializeHandle
0x18003bd2e  test    eax, eax
0x18003bd30  jnz     loc_18003BDFC
0x18003bd36  xor     ebx, ebx
0x18003bd38  mov     qword ptr [rsp+0E8h+pAsync.u], rdi
0x18003bd40  mov     [rsp+0E8h+pAsync.UserInfo], rbx
0x18003bd45  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x18003bd4d  mov     [rsp+0E8h+var_B0], rbx
0x18003bd52  mov     [rsp+0E8h+var_C8], r14
0x18003bd57  mov     r9, rsi
0x18003bd5a  lea     r8, [rsp+0E8h+pAsync]
0x18003bd5f  lea     rdx, byte_180060D1C; pFormat
0x18003bd66  lea     rcx, pStubDescriptor; pStubDescriptor
0x18003bd6d  call    cs:__imp_NdrAsyncClientCall
0x18003bd73  mov     [rsp+0E8h+var_B0], rax
0x18003bd78  mov     [rsp+0E8h+Reply], eax
0x18003bd7c  jmp     short loc_18003BD8C
0x18003bd7e  mov     ecx, eax; unsigned int
0x18003bd80  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18003bd85  mov     ebx, eax
0x18003bd87  mov     rdi, [rsp+0E8h+var_A8]
0x18003bd8c  test    ebx, ebx
0x18003bd8e  jz      short loc_18003BD96
0x18003bd90  mov     [rsp+0E8h+Reply], ebx
0x18003bd94  jmp     short loc_18003BE00
0x18003bd96  or      ebx, 0FFFFFFFFh
0x18003bd99  mov     edx, ebx; dwMilliseconds
0x18003bd9b  mov     rcx, rdi; hHandle
0x18003bd9e  call    cs:__imp_WaitForSingleObject
0x18003bda4  test    eax, eax
0x18003bda6  jz      short loc_18003BDE8
0x18003bda8  call    cs:__imp_GetLastError
0x18003bdae  mov     [rsp+0E8h+Reply], eax
0x18003bdb2  mov     edx, 1; fAbort
0x18003bdb7  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18003bdbc  call    cs:__imp_RpcAsyncCancelCall
0x18003bdc2  test    eax, eax
0x18003bdc4  jz      short loc_18003BDCA
0x18003bdc6  mov     [rsp+0E8h+Reply], eax
0x18003bdca  mov     edx, ebx; dwMilliseconds
0x18003bdcc  mov     rcx, qword ptr [rsp+0E8h+pAsync.u]; hHandle
0x18003bdd4  call    cs:__imp_WaitForSingleObject
0x18003bdda  test    eax, eax
0x18003bddc  jz      short loc_18003BDE8
0x18003bdde  call    cs:__imp_GetLastError
0x18003bde4  mov     [rsp+0E8h+Reply], eax
0x18003bde8  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18003bded  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18003bdf2  call    cs:__imp_RpcAsyncCompleteCall
0x18003bdf8  test    eax, eax
0x18003bdfa  jz      short loc_18003BE00
0x18003bdfc  mov     [rsp+0E8h+Reply], eax
0x18003be00  mov     eax, [rsp+0E8h+Reply]
0x18003be04  mov     rcx, [rsp+0E8h+var_28]
0x18003be0c  xor     rcx, rsp; StackCookie
0x18003be0f  call    __security_check_cookie
0x18003be14  mov     rbx, [rsp+0E8h+arg_18]
0x18003be1c  add     rsp, 0D0h
0x18003be23  pop     r14
0x18003be25  pop     rdi
0x18003be26  pop     rsi
0x18003be27  retn
0x18005048a  push    rbp
0x18005048c  sub     rsp, 30h
0x180050490  mov     rbp, rdx
0x180050493  mov     rcx, [rcx]
0x180050496  mov     ecx, [rcx]; ExceptionCode
0x180050498  call    cs:__imp_I_RpcExceptionFilter
0x18005049e  nop
0x18005049f  add     rsp, 30h
0x1800504a3  pop     rbp
0x1800504a4  retn
```
