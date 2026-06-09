# DfsCredDelete

- ea: `0x180027570`
- end: `0x18002766c`
- name: `DfsCredDelete`
- size: `252`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, LPCWSTR TargetName, DWORD Type)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180027570`

## import_xrefs

- `ntdll!DbgPrint` at `0x1800275e3`
- `ntdll!DbgPrint` at `0x18002763e`
- `ntdll!DbgPrint` at `0x1800275e3`
- `ntdll!DbgPrint` at `0x18002763e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027629`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002764a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002764a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002765b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002765b`
- `RPCRT4!RpcImpersonateClient` at `0x1800275f3`
- `RPCRT4!RpcImpersonateClient` at `0x1800275f3`
- `RPCRT4!RpcServerTestCancel` at `0x1800275b6`
- `RPCRT4!RpcServerTestCancel` at `0x1800275b6`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027596`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800275ce`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027596`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800275ce`
- `RPCRT4!I_RpcMapWin32Status` at `0x180027601`
- `RPCRT4!I_RpcMapWin32Status` at `0x180027601`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180027619`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180027619`

## string_xrefs

- `0x1800275dc`: `DfsCredDelete: RPC has been cancelled by client %X\n`
- `0x180027637`: `DfsCredDelete: CredDelete failed with status %X\n`

## pseudocode

```c
RPC_STATUS __fastcall DfsCredDelete(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        LPCWSTR TargetName,
        DWORD Type)
{
  unsigned int v7; // eax
  RPC_STATUS v9; // eax
  RPC_STATUS v10; // eax
  DWORD LastError; // eax

  if ( !TargetName )
  {
    v7 = 87;
    return RpcAsyncAbortCall(pAsync, v7);
  }
  if ( RpcServerTestCancel(BindingHandle) )
  {
    v10 = RpcImpersonateClient(0);
    v7 = I_RpcMapWin32Status(v10);
    if ( v7 )
      return RpcAsyncAbortCall(pAsync, v7);
    if ( !CredDeleteW(TargetName, Type, 0) )
    {
      LastError = GetLastError();
      DbgPrint("DfsCredDelete: CredDelete failed with status %X\n", LastError);
    }
    RevertToSelf();
  }
  else
  {
    v9 = RpcAsyncAbortCall(pAsync, 0x71Au);
    DbgPrint("DfsCredDelete: RPC has been cancelled by client %X\n", v9);
  }
  return RpcAsyncCompleteCall(pAsync, 0);
}

```

## disassembly

```asm
0x180027570  mov     [rsp+arg_0], rbx
0x180027575  mov     [rsp+arg_8], rsi
0x18002757a  push    rdi
0x18002757b  sub     rsp, 20h
0x18002757f  mov     esi, r9d
0x180027582  mov     rdi, r8
0x180027585  mov     rbx, rcx
0x180027588  test    r8, r8
0x18002758b  jnz     short loc_1800275B3
0x18002758d  lea     eax, [r8+57h]
0x180027591  mov     edx, eax; ExceptionCode
0x180027593  mov     rcx, rbx; pAsync
0x180027596  call    cs:__imp_RpcAsyncAbortCall
0x18002759d  nop     dword ptr [rax+rax+00h]
0x1800275a2  mov     rbx, [rsp+28h+arg_0]
0x1800275a7  mov     rsi, [rsp+28h+arg_8]
0x1800275ac  add     rsp, 20h
0x1800275b0  pop     rdi
0x1800275b1  retn
0x1800275b3  mov     rcx, rdx; BindingHandle
0x1800275b6  call    cs:__imp_RpcServerTestCancel
0x1800275bd  nop     dword ptr [rax+rax+00h]
0x1800275c2  test    eax, eax
0x1800275c4  jnz     short loc_1800275F1
0x1800275c6  mov     edx, 71Ah; ExceptionCode
0x1800275cb  mov     rcx, rbx; pAsync
0x1800275ce  call    cs:__imp_RpcAsyncAbortCall
0x1800275d5  nop     dword ptr [rax+rax+00h]
0x1800275da  mov     edx, eax
0x1800275dc  lea     rcx, aDfscreddeleteR; "DfsCredDelete: RPC has been cancelled b"...
0x1800275e3  call    cs:__imp_DbgPrint
0x1800275ea  nop     dword ptr [rax+rax+00h]
0x1800275ef  jmp     short loc_180027656
0x1800275f1  xor     ecx, ecx; BindingHandle
0x1800275f3  call    cs:__imp_RpcImpersonateClient
0x1800275fa  nop     dword ptr [rax+rax+00h]
0x1800275ff  mov     ecx, eax; Status
0x180027601  call    cs:__imp_I_RpcMapWin32Status
0x180027608  nop     dword ptr [rax+rax+00h]
0x18002760d  test    eax, eax
0x18002760f  jnz     short loc_180027591
0x180027611  xor     r8d, r8d; Flags
0x180027614  mov     edx, esi; Type
0x180027616  mov     rcx, rdi; TargetName
0x180027619  call    cs:__imp_CredDeleteW
0x180027620  nop     dword ptr [rax+rax+00h]
0x180027625  test    eax, eax
0x180027627  jnz     short loc_18002764A
0x180027629  call    cs:__imp_GetLastError
0x180027630  nop     dword ptr [rax+rax+00h]
0x180027635  mov     edx, eax
0x180027637  lea     rcx, aDfscreddeleteC; "DfsCredDelete: CredDelete failed with s"...
0x18002763e  call    cs:__imp_DbgPrint
0x180027645  nop     dword ptr [rax+rax+00h]
0x18002764a  call    cs:__imp_RevertToSelf
0x180027651  nop     dword ptr [rax+rax+00h]
0x180027656  xor     edx, edx; Reply
0x180027658  mov     rcx, rbx; pAsync
0x18002765b  call    cs:__imp_RpcAsyncCompleteCall
0x180027662  nop     dword ptr [rax+rax+00h]
0x180027667  jmp     loc_1800275A2
```
