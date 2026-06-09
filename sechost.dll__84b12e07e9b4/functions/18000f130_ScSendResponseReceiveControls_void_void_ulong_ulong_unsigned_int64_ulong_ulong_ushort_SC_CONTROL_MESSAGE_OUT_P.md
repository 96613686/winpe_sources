# ScSendResponseReceiveControls(void *,void *,ulong,ulong,unsigned __int64,ulong,ulong *,ushort * *,_SC_CONTROL_MESSAGE_OUT_PARAMS *)

- ea: `0x18000f130`
- end: `0x18000f306`
- name: `?ScSendResponseReceiveControls@@YAKPEAX0KK_KKPEAKPEAPEAGPEAU_SC_CONTROL_MESSAGE_OUT_PARAMS@@@Z`
- size: `470`
- prototype: `unsigned int(void *, void *, unsigned int, unsigned int, unsigned __int64, unsigned int, unsigned int *, unsigned __int16 **, struct _SC_CONTROL_MESSAGE_OUT_PARAMS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bfb0`

## callees

- `0x18000f130`
- `0x18004abac`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2f7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f1dc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f1dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f277`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f2ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f277`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f2ed`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000f1ef`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18000f1ef`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f28e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f28e`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000f2d2`
- `RPCRT4!RpcAsyncCancelCall` at `0x18000f2d2`
- `RPCRT4!NdrAsyncClientCall` at `0x18000f24a`
- `RPCRT4!NdrAsyncClientCall` at `0x18000f24a`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fe9e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fe9e`

## pseudocode

```c
unsigned int __fastcall ScSendResponseReceiveControls(
        void *a1,
        void *a2,
        int a3,
        int a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned __int16 **a8,
        struct _SC_CONTROL_MESSAGE_OUT_PARAMS *a9)
{
  CLIENT_CALL_RETURN v11; // rax
  RPC_STATUS v12; // eax
  DWORD Reply; // [rsp+40h] [rbp-E8h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+48h] [rbp-E0h]
  void *v16; // [rsp+50h] [rbp-D8h]
  _DWORD v17[2]; // [rsp+58h] [rbp-D0h] BYREF
  unsigned __int64 v18; // [rsp+60h] [rbp-C8h]
  int v19; // [rsp+68h] [rbp-C0h]
  unsigned int v20; // [rsp+6Ch] [rbp-BCh]
  unsigned int *v21; // [rsp+70h] [rbp-B8h]
  _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v16 = a2;
  Reply = 0;
  memset(&pAsync, 0, sizeof(pAsync));
  v17[1] = 0;
  v17[0] = a3;
  v19 = a4;
  v18 = a5;
  v20 = a6;
  v21 = a7;
  ResetEvent(a2);
  LODWORD(v11.Pointer) = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( !LODWORD(v11.Pointer) )
  {
    pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)a2;
    pAsync.UserInfo = 0;
    pAsync.NotificationType = RpcNotificationTypeEvent;
    v11.Pointer = NdrAsyncClientCall(&stru_1800523A0, &byte_180061362, &pAsync, a1, v17, a8, a9).Pointer;
    v15.Pointer = v11.Pointer;
    Reply = (DWORD)v11.Pointer;
    if ( !LODWORD(v11.Pointer) )
    {
      if ( WaitForSingleObject(a2, 0xFFFFFFFF) )
      {
        Reply = GetLastError();
        v12 = RpcAsyncCancelCall(&pAsync, 1);
        if ( v12 )
          Reply = v12;
        if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0xFFFFFFFF) )
          Reply = GetLastError();
      }
      LODWORD(v11.Pointer) = RpcAsyncCompleteCall(&pAsync, &Reply);
      if ( !LODWORD(v11.Pointer) )
        LODWORD(v11.Pointer) = Reply;
    }
  }
  return (unsigned int)v11.Pointer;
}

```

## disassembly

```asm
0x18000f130  mov     r11, rsp
0x18000f133  push    rbx
0x18000f134  push    rsi
0x18000f135  push    rdi
0x18000f136  push    r14
0x18000f138  push    r15
0x18000f13a  sub     rsp, 100h
0x18000f141  mov     rax, cs:__security_cookie
0x18000f148  xor     rax, rsp
0x18000f14b  mov     [rsp+128h+var_38], rax
0x18000f153  mov     rbx, rdx
0x18000f156  mov     rdi, rcx
0x18000f159  mov     [rsp+128h+var_D8], rdx
0x18000f15e  mov     rcx, [rsp+128h+arg_30]
0x18000f166  mov     rsi, [rsp+128h+arg_38]
0x18000f16e  mov     r14, [rsp+128h+arg_40]
0x18000f176  xor     r15d, r15d
0x18000f179  mov     [rsp+128h+Reply], r15d
0x18000f17e  xorps   xmm0, xmm0
0x18000f181  movups  xmmword ptr [rsp+128h+pAsync.Size], xmm0
0x18000f189  movups  xmmword ptr [rsp+128h+pAsync.StubInfo], xmm0
0x18000f191  movups  xmmword ptr [rsp+128h+pAsync.RuntimeInfo], xmm0
0x18000f199  movups  xmmword ptr [r11-78h], xmm0
0x18000f19e  movups  xmmword ptr [r11-68h], xmm0
0x18000f1a3  movups  xmmword ptr [r11-58h], xmm0
0x18000f1a8  movups  xmmword ptr [r11-48h], xmm0
0x18000f1ad  mov     [rsp+128h+var_CC], r15d
0x18000f1b2  mov     [rsp+128h+var_D0], r8d
0x18000f1b7  mov     [rsp+128h+var_C0], r9d
0x18000f1bc  mov     rax, [rsp+128h+arg_20]
0x18000f1c4  mov     [rsp+128h+var_C8], rax
0x18000f1c9  mov     eax, [rsp+128h+arg_28]
0x18000f1d0  mov     [rsp+128h+var_BC], eax
0x18000f1d4  mov     [rsp+128h+var_B8], rcx
0x18000f1d9  mov     rcx, rdx; hEvent
0x18000f1dc  call    cs:__imp_ResetEvent
0x18000f1e2  mov     edx, 70h ; 'p'; Size
0x18000f1e7  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000f1ef  call    cs:__imp_RpcAsyncInitializeHandle
0x18000f1f5  test    eax, eax
0x18000f1f7  jnz     loc_18000F29C
0x18000f1fd  mov     qword ptr [rsp+128h+pAsync.u], rbx
0x18000f205  mov     [rsp+128h+pAsync.UserInfo], r15
0x18000f20d  mov     [rsp+128h+pAsync.NotificationType], 1
0x18000f218  mov     [rsp+128h+var_E0], r15
0x18000f21d  mov     [rsp+128h+var_F8], r14
0x18000f222  mov     [rsp+128h+var_100], rsi
0x18000f227  lea     rax, [rsp+128h+var_D0]
0x18000f22c  mov     [rsp+128h+var_108], rax
0x18000f231  mov     r9, rdi
0x18000f234  lea     r8, [rsp+128h+pAsync]
0x18000f23c  lea     rdx, byte_180061362; pFormat
0x18000f243  lea     rcx, stru_1800523A0; pStubDescriptor
0x18000f24a  call    cs:__imp_NdrAsyncClientCall
0x18000f250  mov     [rsp+128h+var_E0], rax
0x18000f255  mov     [rsp+128h+Reply], eax
0x18000f259  jmp     short loc_18000F26B
0x18000f25b  mov     ecx, eax; unsigned int
0x18000f25d  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000f262  mov     [rsp+128h+Reply], eax
0x18000f266  mov     rbx, [rsp+128h+var_D8]
0x18000f26b  test    eax, eax
0x18000f26d  jnz     short loc_18000F29C
0x18000f26f  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000f274  mov     rcx, rbx; hHandle
0x18000f277  call    cs:__imp_WaitForSingleObject
0x18000f27d  test    eax, eax
0x18000f27f  jnz     short loc_18000F2BB
0x18000f281  lea     rdx, [rsp+128h+Reply]; Reply
0x18000f286  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000f28e  call    cs:__imp_RpcAsyncCompleteCall
0x18000f294  test    eax, eax
0x18000f296  jnz     short loc_18000F29C
0x18000f298  mov     eax, [rsp+128h+Reply]
0x18000f29c  mov     rcx, [rsp+128h+var_38]
0x18000f2a4  xor     rcx, rsp; StackCookie
0x18000f2a7  call    __security_check_cookie
0x18000f2ac  add     rsp, 100h
0x18000f2b3  pop     r15
0x18000f2b5  pop     r14
0x18000f2b7  pop     rdi
0x18000f2b8  pop     rsi
0x18000f2b9  pop     rbx
0x18000f2ba  retn
0x18000f2bb  call    cs:__imp_GetLastError
0x18000f2c1  mov     [rsp+128h+Reply], eax
0x18000f2c5  mov     edx, 1; fAbort
0x18000f2ca  lea     rcx, [rsp+128h+pAsync]; pAsync
0x18000f2d2  call    cs:__imp_RpcAsyncCancelCall
0x18000f2d8  test    eax, eax
0x18000f2da  jz      short loc_18000F2E0
0x18000f2dc  mov     [rsp+128h+Reply], eax
0x18000f2e0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000f2e5  mov     rcx, qword ptr [rsp+128h+pAsync.u]; hHandle
0x18000f2ed  call    cs:__imp_WaitForSingleObject
0x18000f2f3  test    eax, eax
0x18000f2f5  jz      short loc_18000F281
0x18000f2f7  call    cs:__imp_GetLastError
0x18000f2fd  mov     [rsp+128h+Reply], eax
0x18000f301  jmp     loc_18000F281
0x18004fe90  push    rbp
0x18004fe92  sub     rsp, 40h
0x18004fe96  mov     rbp, rdx
0x18004fe99  mov     rcx, [rcx]
0x18004fe9c  mov     ecx, [rcx]; ExceptionCode
0x18004fe9e  call    cs:__imp_I_RpcExceptionFilter
0x18004fea4  nop
0x18004fea5  add     rsp, 40h
0x18004fea9  pop     rbp
0x18004feaa  retn
```
