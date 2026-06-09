# LBS_CALL::SubmitRollback(void)

- ea: `0x180021744`
- end: `0x1800217dd`
- name: `?SubmitRollback@LBS_CALL@@QEAAXXZ`
- size: `153`
- prototype: `void __fastcall(LBS_CALL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180020c3c`

## callees

- `0x18001f9f4`
- `0x180021744`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180021761`
- `KERNEL32!ResetEvent` at `0x180021761`
- `RPCRT4!NdrAsyncClientCall` at `0x180021781`
- `RPCRT4!NdrAsyncClientCall` at `0x180021781`
- `RPCRT4!RpcExceptionFilter` at `0x180024752`
- `RPCRT4!RpcExceptionFilter` at `0x180024752`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800217ad`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800217ad`

## pseudocode

```c
void __fastcall LBS_CALL::SubmitRollback(HANDLE *this)
{
  ResetEvent(this[7]);
  NdrAsyncClientCall(&pStubDescriptor, &byte_180028896, this + 1, this + 17);
  *((_DWORD *)this + 38) = 1;
  LBS_CALL::ChangeCallState(this, 3, 0);
}

```

## disassembly

```asm
0x180021744  mov     [rsp+arg_8], rbx
0x180021749  mov     [rsp+arg_10], rsi
0x18002174e  mov     [rsp+arg_0], rcx
0x180021753  push    rdi
0x180021754  sub     rsp, 20h
0x180021758  mov     rbx, rcx
0x18002175b  xor     edi, edi
0x18002175d  mov     rcx, [rcx+38h]; hEvent
0x180021761  call    cs:__imp_ResetEvent
0x180021767  nop
0x180021768  lea     r9, [rbx+88h]
0x18002176f  lea     r8, [rbx+8]
0x180021773  lea     rdx, byte_180028896; pFormat
0x18002177a  lea     rcx, pStubDescriptor; pStubDescriptor
0x180021781  call    cs:__imp_NdrAsyncClientCall
0x180021787  jmp     short loc_180021790
0x180021789  mov     edi, eax
0x18002178b  mov     rbx, [rsp+28h+arg_0]
0x180021790  test    edi, edi
0x180021792  jnz     short loc_1800217A6
0x180021794  mov     dword ptr [rbx+98h], 1
0x18002179e  xor     r8d, r8d
0x1800217a1  lea     edx, [rdi+3]
0x1800217a4  jmp     short loc_1800217C5
0x1800217a6  lea     rcx, [rbx+88h]; ContextHandle
0x1800217ad  call    cs:__imp_RpcSsDestroyClientContext
0x1800217b3  mov     dword ptr [rbx+98h], 0
0x1800217bd  mov     r8d, edi
0x1800217c0  mov     edx, 6
0x1800217c5  mov     rcx, rbx
0x1800217c8  call    ?ChangeCallState@LBS_CALL@@QEAAXW4_CallStates@@J@Z; LBS_CALL::ChangeCallState(_CallStates,long)
0x1800217cd  mov     rbx, [rsp+28h+arg_8]
0x1800217d2  mov     rsi, [rsp+28h+arg_10]
0x1800217d7  add     rsp, 20h
0x1800217db  pop     rdi
0x1800217dc  retn
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
