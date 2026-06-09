# RpcWritePrinter

- ea: `0x140003300`
- end: `0x1400033ea`
- name: `RpcWritePrinter`
- size: `234`
- prototype: `__int64 __fastcall(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pcWritten)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002a70`
- `0x140003300`
- `0x1400037d0`
- `0x14000f9e0`
- `0x1400160a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000337e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000337e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000333c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400033d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000333c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400033d7`
- `RPCRT4!RpcImpersonateClient` at `0x140003372`
- `RPCRT4!RpcImpersonateClient` at `0x140003372`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140003323`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140003323`

## string_xrefs

- `0x140003358`: `Rpc call is access denied.`
- `0x14000335f`: `RpcWritePrinter`
- `0x1400033bb`: `YWritePrinter`

## pseudocode

```c
__int64 __fastcall RpcWritePrinter(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pcWritten)
{
  DWORD LastError; // ebx
  RPC_STATUS v10; // eax
  BOOL v11; // ebx
  DWORD v12; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-38h] BYREF

  LastError = 0;
  Binding = 0;
  if ( RpcServerInqBindingHandle(&Binding) || !TlsSetValue(gdwTlsBindingHandle, Binding) )
    return LastError;
  if ( (unsigned int)RpcApiValidSecurityLevel(Binding) )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError("RpcWritePrinter", L"Rpc call is access denied.");
    return 5;
  }
  v10 = RpcImpersonateClient(0);
  if ( v10 )
  {
    SetLastError(v10);
LABEL_10:
    LastError = GetLastError();
    goto LABEL_11;
  }
  v11 = WritePrinter(hPrinter, pBuf, cbBuf, pcWritten);
  YRevertToSelf(1);
  if ( !v11 )
  {
    v12 = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError("YWritePrinter", L"Failed. Error %d", v12);
    goto LABEL_10;
  }
  LastError = 0;
LABEL_11:
  TlsSetValue(gdwTlsBindingHandle, 0);
  return LastError;
}

```

## disassembly

```asm
0x140003300  push    rbx
0x140003302  push    rbp
0x140003303  push    rsi
0x140003304  push    rdi
0x140003305  push    r14
0x140003307  sub     rsp, 30h
0x14000330b  mov     r14, rcx
0x14000330e  xor     ebx, ebx
0x140003310  lea     rcx, [rsp+58h+Binding]; Binding
0x140003315  mov     [rsp+58h+Binding], rbx
0x14000331a  mov     rdi, r9
0x14000331d  mov     esi, r8d
0x140003320  mov     rbp, rdx
0x140003323  call    cs:__imp_RpcServerInqBindingHandle
0x140003329  test    eax, eax
0x14000332b  jnz     loc_1400033DD
0x140003331  mov     rdx, [rsp+58h+Binding]; lpTlsValue
0x140003336  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000333c  call    cs:__imp_TlsSetValue
0x140003342  test    eax, eax
0x140003344  jz      loc_1400033DD
0x14000334a  mov     rcx, [rsp+58h+Binding]; void *
0x14000334f  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x140003354  test    eax, eax
0x140003356  jz      short loc_140003370
0x140003358  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x14000335f  lea     rcx, aRpcwriteprinte; "RpcWritePrinter"
0x140003366  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000336b  lea     eax, [rbx+5]
0x14000336e  jmp     short loc_1400033DF
0x140003370  xor     ecx, ecx; BindingHandle
0x140003372  call    cs:__imp_RpcImpersonateClient
0x140003378  test    eax, eax
0x14000337a  jz      short loc_140003386
0x14000337c  mov     ecx, eax; dwErrCode
0x14000337e  call    cs:__imp_SetLastError
0x140003384  jmp     short loc_1400033C7
0x140003386  mov     r9, rdi; pcWritten
0x140003389  mov     r8d, esi; cbBuf
0x14000338c  mov     rdx, rbp; pBuf
0x14000338f  mov     rcx, r14; hPrinter
0x140003392  call    WritePrinter
0x140003397  mov     ecx, 1
0x14000339c  mov     ebx, eax
0x14000339e  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x1400033a3  test    ebx, ebx
0x1400033a5  jz      short loc_1400033AB
0x1400033a7  xor     ebx, ebx
0x1400033a9  jmp     short loc_1400033CF
0x1400033ab  call    cs:__imp_GetLastError
0x1400033b1  mov     r8d, eax
0x1400033b4  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x1400033bb  lea     rcx, aYwriteprinter_0; "YWritePrinter"
0x1400033c2  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400033c7  call    cs:__imp_GetLastError
0x1400033cd  mov     ebx, eax
0x1400033cf  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400033d5  xor     edx, edx; lpTlsValue
0x1400033d7  call    cs:__imp_TlsSetValue
0x1400033dd  mov     eax, ebx
0x1400033df  add     rsp, 30h
0x1400033e3  pop     r14
0x1400033e5  pop     rdi
0x1400033e6  pop     rsi
0x1400033e7  pop     rbp
0x1400033e8  pop     rbx
0x1400033e9  retn
```
