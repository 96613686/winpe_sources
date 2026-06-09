# LB_USE_COUNT_CONTAINER::AbortAndWait(int)

- ea: `0x18001f920`
- end: `0x18001f97c`
- name: `?AbortAndWait@LB_USE_COUNT_CONTAINER@@QEAAXH@Z`
- size: `92`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180023be8`
- `0x180023d58`

## callees

- `0x18001f920`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001f949`
- `KERNEL32!WaitForSingleObject` at `0x18001f949`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f93c`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f93c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f95b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f95b`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001f96b`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001f96b`

## pseudocode

```c
void __fastcall LB_USE_COUNT_CONTAINER::AbortAndWait(PRPC_ASYNC_STATE pAsync, int a2)
{
  int Reply; // [rsp+38h] [rbp+10h] BYREF

  Reply = 0;
  RpcAsyncCancelCall(pAsync, 1);
  WaitForSingleObject(pAsync->u.APC.NotificationRoutine, 0xFFFFFFFF);
  if ( a2 )
  {
    RpcAsyncCompleteCall(pAsync, &Reply);
    if ( *(_QWORD *)&pAsync[1].Size )
      RpcSsDestroyClientContext((void **)&pAsync[1]);
  }
}

```

## disassembly

```asm
0x18001f920  mov     [rsp+arg_0], rbx
0x18001f925  push    rdi
0x18001f926  sub     rsp, 20h
0x18001f92a  mov     ebx, edx
0x18001f92c  mov     [rsp+28h+Reply], 0
0x18001f934  mov     edx, 1; fAbort
0x18001f939  mov     rdi, rcx
0x18001f93c  call    cs:__imp_RpcAsyncCancelCall
0x18001f942  mov     rcx, [rdi+30h]; hHandle
0x18001f946  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f949  call    cs:__imp_WaitForSingleObject
0x18001f94f  test    ebx, ebx
0x18001f951  jz      short loc_18001F971
0x18001f953  lea     rdx, [rsp+28h+Reply]; Reply
0x18001f958  mov     rcx, rdi; pAsync
0x18001f95b  call    cs:__imp_RpcAsyncCompleteCall
0x18001f961  lea     rcx, [rdi+70h]; ContextHandle
0x18001f965  cmp     qword ptr [rcx], 0
0x18001f969  jz      short loc_18001F971
0x18001f96b  call    cs:__imp_RpcSsDestroyClientContext
0x18001f971  mov     rbx, [rsp+28h+arg_0]
0x18001f976  add     rsp, 20h
0x18001f97a  pop     rdi
0x18001f97b  retn
```
