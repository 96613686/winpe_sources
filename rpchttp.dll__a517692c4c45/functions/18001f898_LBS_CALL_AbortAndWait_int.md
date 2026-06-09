# LBS_CALL::AbortAndWait(int)

- ea: `0x18001f898`
- end: `0x18001f919`
- name: `?AbortAndWait@LBS_CALL@@QEAAXH@Z`
- size: `129`
- prototype: `void __fastcall(LBS_CALL *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023a6c`
- `0x180023d58`

## callees

- `0x18001f898`
- `0x18001f9f4`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001f8ca`
- `KERNEL32!WaitForSingleObject` at `0x18001f8ca`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f8bd`
- `RPCRT4!RpcAsyncCancelCall` at `0x18001f8bd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f8dd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001f8dd`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001f8f0`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18001f8f0`

## pseudocode

```c
void __fastcall LBS_CALL::AbortAndWait(LBS_CALL *this, int a2)
{
  int Reply; // [rsp+38h] [rbp+10h] BYREF

  Reply = 0;
  RpcAsyncCancelCall((PRPC_ASYNC_STATE)((char *)this + 8), 1);
  WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF);
  if ( a2 )
  {
    RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 8), &Reply);
    if ( *((_QWORD *)this + 17) )
      RpcSsDestroyClientContext((void **)this + 17);
    LBS_CALL::ChangeCallState(this, 6, 1818);
  }
}

```

## disassembly

```asm
0x18001f898  mov     [rsp+arg_0], rbx
0x18001f89d  mov     [rsp+arg_10], rsi
0x18001f8a2  push    rdi
0x18001f8a3  sub     rsp, 20h
0x18001f8a7  mov     ebx, edx
0x18001f8a9  mov     [rsp+28h+Reply], 0
0x18001f8b1  mov     rdi, rcx
0x18001f8b4  mov     edx, 1; fAbort
0x18001f8b9  add     rcx, 8; pAsync
0x18001f8bd  call    cs:__imp_RpcAsyncCancelCall
0x18001f8c3  mov     rcx, [rdi+38h]; hHandle
0x18001f8c7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f8ca  call    cs:__imp_WaitForSingleObject
0x18001f8d0  test    ebx, ebx
0x18001f8d2  jz      short loc_18001F909
0x18001f8d4  lea     rdx, [rsp+28h+Reply]; Reply
0x18001f8d9  lea     rcx, [rdi+8]; pAsync
0x18001f8dd  call    cs:__imp_RpcAsyncCompleteCall
0x18001f8e3  lea     rcx, [rdi+88h]; ContextHandle
0x18001f8ea  cmp     qword ptr [rcx], 0
0x18001f8ee  jz      short loc_18001F8F6
0x18001f8f0  call    cs:__imp_RpcSsDestroyClientContext
0x18001f8f6  mov     edx, 6
0x18001f8fb  mov     r8d, 71Ah
0x18001f901  mov     rcx, rdi
0x18001f904  call    ?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z; LBS_CALL::ChangeCallState(_CallStates,long)
0x18001f909  mov     rbx, [rsp+28h+arg_0]
0x18001f90e  mov     rsi, [rsp+28h+arg_10]
0x18001f913  add     rsp, 20h
0x18001f917  pop     rdi
0x18001f918  retn
```
