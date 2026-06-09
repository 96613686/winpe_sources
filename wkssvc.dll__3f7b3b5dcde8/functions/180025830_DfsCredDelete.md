# DfsCredDelete

- ea: `0x180025830`
- end: `0x1800258e9`
- name: `DfsCredDelete`
- size: `185`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, RPC_BINDING_HANDLE BindingHandle, LPCWSTR TargetName, DWORD Type)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180025830`

## import_xrefs

- `ntdll!DbgPrint` at `0x180025890`
- `ntdll!DbgPrint` at `0x1800258cd`
- `ntdll!DbgPrint` at `0x180025890`
- `ntdll!DbgPrint` at `0x1800258cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258be`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800258d3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800258d3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800258de`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800258de`
- `RPCRT4!RpcImpersonateClient` at `0x18002589a`
- `RPCRT4!RpcImpersonateClient` at `0x18002589a`
- `RPCRT4!RpcServerTestCancel` at `0x18002586f`
- `RPCRT4!RpcServerTestCancel` at `0x18002586f`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025856`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025881`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025856`
- `RPCRT4!RpcAsyncAbortCall` at `0x180025881`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800258a2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800258a2`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800258b4`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x1800258b4`

## string_xrefs

- `0x180025889`: `DfsCredDelete: RPC has been cancelled by client %X\n`
- `0x1800258c6`: `DfsCredDelete: CredDelete failed with status %X\n`

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
0x180025830  mov     [rsp+arg_0], rbx
0x180025835  mov     [rsp+arg_8], rsi
0x18002583a  push    rdi
0x18002583b  sub     rsp, 20h
0x18002583f  mov     esi, r9d
0x180025842  mov     rdi, r8
0x180025845  mov     rbx, rcx
0x180025848  test    r8, r8
0x18002584b  jnz     short loc_18002586C
0x18002584d  lea     eax, [r8+57h]
0x180025851  mov     edx, eax; ExceptionCode
0x180025853  mov     rcx, rbx; pAsync
0x180025856  call    cs:__imp_RpcAsyncAbortCall
0x18002585c  mov     rbx, [rsp+28h+arg_0]
0x180025861  mov     rsi, [rsp+28h+arg_8]
0x180025866  add     rsp, 20h
0x18002586a  pop     rdi
0x18002586b  retn
0x18002586c  mov     rcx, rdx; BindingHandle
0x18002586f  call    cs:__imp_RpcServerTestCancel
0x180025875  test    eax, eax
0x180025877  jnz     short loc_180025898
0x180025879  mov     edx, 71Ah; ExceptionCode
0x18002587e  mov     rcx, rbx; pAsync
0x180025881  call    cs:__imp_RpcAsyncAbortCall
0x180025887  mov     edx, eax
0x180025889  lea     rcx, aDfscreddeleteR; "DfsCredDelete: RPC has been cancelled b"...
0x180025890  call    cs:__imp_DbgPrint
0x180025896  jmp     short loc_1800258D9
0x180025898  xor     ecx, ecx; BindingHandle
0x18002589a  call    cs:__imp_RpcImpersonateClient
0x1800258a0  mov     ecx, eax; Status
0x1800258a2  call    cs:__imp_I_RpcMapWin32Status
0x1800258a8  test    eax, eax
0x1800258aa  jnz     short loc_180025851
0x1800258ac  xor     r8d, r8d; Flags
0x1800258af  mov     edx, esi; Type
0x1800258b1  mov     rcx, rdi; TargetName
0x1800258b4  call    cs:__imp_CredDeleteW
0x1800258ba  test    eax, eax
0x1800258bc  jnz     short loc_1800258D3
0x1800258be  call    cs:__imp_GetLastError
0x1800258c4  mov     edx, eax
0x1800258c6  lea     rcx, aDfscreddeleteC; "DfsCredDelete: CredDelete failed with s"...
0x1800258cd  call    cs:__imp_DbgPrint
0x1800258d3  call    cs:__imp_RevertToSelf
0x1800258d9  xor     edx, edx; Reply
0x1800258db  mov     rcx, rbx; pAsync
0x1800258de  call    cs:__imp_RpcAsyncCompleteCall
0x1800258e4  jmp     loc_18002585C
```
