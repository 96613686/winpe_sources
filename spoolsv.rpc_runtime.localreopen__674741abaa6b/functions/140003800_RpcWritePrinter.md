# RpcWritePrinter

- ea: `0x140003800`
- end: `0x140003918`
- name: `RpcWritePrinter`
- size: `280`
- prototype: `__int64 __fastcall(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pcWritten)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400028e0`
- `0x140003800`
- `0x140003d60`
- `0x140010cc0`
- `0x14001748c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003893`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003893`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003842`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400038fe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003842`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400038fe`
- `RPCRT4!RpcImpersonateClient` at `0x140003881`
- `RPCRT4!RpcImpersonateClient` at `0x140003881`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140003823`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140003823`

## string_xrefs

- `0x140003864`: `Rpc call is access denied.`
- `0x14000386b`: `RpcWritePrinter`
- `0x1400038dc`: `YWritePrinter`

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
0x140003800  push    rbx
0x140003802  push    rbp
0x140003803  push    rsi
0x140003804  push    rdi
0x140003805  push    r14
0x140003807  sub     rsp, 30h
0x14000380b  mov     r14, rcx
0x14000380e  xor     ebx, ebx
0x140003810  lea     rcx, [rsp+58h+Binding]; Binding
0x140003815  mov     [rsp+58h+Binding], rbx
0x14000381a  mov     rdi, r9
0x14000381d  mov     esi, r8d
0x140003820  mov     rbp, rdx
0x140003823  call    cs:__imp_RpcServerInqBindingHandle
0x14000382a  nop     dword ptr [rax+rax+00h]
0x14000382f  test    eax, eax
0x140003831  jnz     loc_14000390A
0x140003837  mov     rdx, [rsp+58h+Binding]; lpTlsValue
0x14000383c  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140003842  call    cs:__imp_TlsSetValue
0x140003849  nop     dword ptr [rax+rax+00h]
0x14000384e  test    eax, eax
0x140003850  jz      loc_14000390A
0x140003856  mov     rcx, [rsp+58h+Binding]; void *
0x14000385b  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x140003860  test    eax, eax
0x140003862  jz      short loc_14000387F
0x140003864  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x14000386b  lea     rcx, aRpcwriteprinte; "RpcWritePrinter"
0x140003872  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003877  lea     eax, [rbx+5]
0x14000387a  jmp     loc_14000390C
0x14000387f  xor     ecx, ecx; BindingHandle
0x140003881  call    cs:__imp_RpcImpersonateClient
0x140003888  nop     dword ptr [rax+rax+00h]
0x14000388d  test    eax, eax
0x14000388f  jz      short loc_1400038A1
0x140003891  mov     ecx, eax; dwErrCode
0x140003893  call    cs:__imp_SetLastError
0x14000389a  nop     dword ptr [rax+rax+00h]
0x14000389f  jmp     short loc_1400038E8
0x1400038a1  mov     r9, rdi; pcWritten
0x1400038a4  mov     r8d, esi; cbBuf
0x1400038a7  mov     rdx, rbp; pBuf
0x1400038aa  mov     rcx, r14; hPrinter
0x1400038ad  call    WritePrinter
0x1400038b2  mov     ecx, 1
0x1400038b7  mov     ebx, eax
0x1400038b9  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x1400038be  test    ebx, ebx
0x1400038c0  jz      short loc_1400038C6
0x1400038c2  xor     ebx, ebx
0x1400038c4  jmp     short loc_1400038F6
0x1400038c6  call    cs:__imp_GetLastError
0x1400038cd  nop     dword ptr [rax+rax+00h]
0x1400038d2  mov     r8d, eax
0x1400038d5  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x1400038dc  lea     rcx, aYwriteprinter_0; "YWritePrinter"
0x1400038e3  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400038e8  call    cs:__imp_GetLastError
0x1400038ef  nop     dword ptr [rax+rax+00h]
0x1400038f4  mov     ebx, eax
0x1400038f6  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400038fc  xor     edx, edx; lpTlsValue
0x1400038fe  call    cs:__imp_TlsSetValue
0x140003905  nop     dword ptr [rax+rax+00h]
0x14000390a  mov     eax, ebx
0x14000390c  add     rsp, 30h
0x140003910  pop     r14
0x140003912  pop     rdi
0x140003913  pop     rsi
0x140003914  pop     rbp
0x140003915  pop     rbx
0x140003916  retn
```
