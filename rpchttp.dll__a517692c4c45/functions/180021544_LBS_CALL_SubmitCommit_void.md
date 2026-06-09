# LBS_CALL::SubmitCommit(void)

- ea: `0x180021544`
- end: `0x1800215dd`
- name: `?SubmitCommit@LBS_CALL@@QEAAXXZ`
- size: `153`
- prototype: `void __fastcall(LBS_CALL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020c3c`

## callees

- `0x18001f9f4`
- `0x180021544`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180021561`
- `KERNEL32!ResetEvent` at `0x180021561`
- `RPCRT4!NdrAsyncClientCall` at `0x180021581`
- `RPCRT4!NdrAsyncClientCall` at `0x180021581`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800215ad`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800215ad`

## pseudocode

```c
void __fastcall LBS_CALL::SubmitCommit(HANDLE *this)
{
  ResetEvent(this[7]);
  NdrAsyncClientCall(&pStubDescriptor, &byte_180028870, this + 1, this[17]);
  *((_DWORD *)this + 38) = 1;
  LBS_CALL::ChangeCallState(this, 4, 0);
}

```

## disassembly

```asm
0x180021544  mov     [rsp+arg_8], rbx
0x180021549  mov     [rsp+arg_10], rsi
0x18002154e  mov     [rsp+arg_0], rcx
0x180021553  push    rdi
0x180021554  sub     rsp, 20h
0x180021558  mov     rbx, rcx
0x18002155b  xor     edi, edi
0x18002155d  mov     rcx, [rcx+38h]; hEvent
0x180021561  call    cs:__imp_ResetEvent
0x180021567  nop
0x180021568  mov     r9, [rbx+88h]
0x18002156f  lea     r8, [rbx+8]
0x180021573  lea     rdx, byte_180028870; pFormat
0x18002157a  lea     rcx, pStubDescriptor; pStubDescriptor
0x180021581  call    cs:__imp_NdrAsyncClientCall
0x180021587  jmp     short loc_180021590
0x180021589  mov     edi, eax
0x18002158b  mov     rbx, [rsp+28h+arg_0]
0x180021590  test    edi, edi
0x180021592  jnz     short loc_1800215A6
0x180021594  mov     dword ptr [rbx+98h], 1
0x18002159e  xor     r8d, r8d
0x1800215a1  lea     edx, [rdi+4]
0x1800215a4  jmp     short loc_1800215C5
0x1800215a6  lea     rcx, [rbx+88h]; ContextHandle
0x1800215ad  call    cs:__imp_RpcSsDestroyClientContext
0x1800215b3  mov     dword ptr [rbx+98h], 0
0x1800215bd  mov     r8d, edi
0x1800215c0  mov     edx, 6
0x1800215c5  mov     rcx, rbx
0x1800215c8  call    ?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z; LBS_CALL::ChangeCallState(_CallStates,long)
0x1800215cd  mov     rbx, [rsp+28h+arg_8]
0x1800215d2  mov     rsi, [rsp+28h+arg_10]
0x1800215d7  add     rsp, 20h
0x1800215db  pop     rdi
0x1800215dc  retn
0x180024744  push    rbp
0x180024746  sub     rsp, 20h
0x18002474a  mov     rbp, rdx
0x18002474d  mov     rcx, [rcx]
0x180024750  mov     ecx, [rcx]; ExceptionCode
0x180024752  call    cs:__imp_RpcExceptionFilter
0x180024758  nop
0x180024759  add     rsp, 20h
0x18002475d  pop     rbp
0x18002475e  retn
```
