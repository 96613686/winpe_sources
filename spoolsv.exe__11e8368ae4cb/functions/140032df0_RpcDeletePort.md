# RpcDeletePort

- ea: `0x140032df0`
- end: `0x140032ef2`
- name: `RpcDeletePort`
- size: `258`
- prototype: `__int64 __fastcall(LPWSTR pName, HWND hWnd, LPWSTR pPortName)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002a70`
- `0x140002ac0`
- `0x1400037d0`
- `0x1400160a0`
- `0x140032df0`
- `0x1400590f0`
- `0x140062a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032ed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140032ed1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140032e51`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140032ee1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140032e51`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140032ee1`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140032e38`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140032e38`

## string_xrefs

- `0x140032e6d`: `Rpc call is access denied.`
- `0x140032e14`: `Trying to delete a port in Windows Protected Print mode.`
- `0x140032e1b`: `RpcDeletePort`
- `0x140032e74`: `RpcDeletePort`
- `0x140032ec5`: `YDeletePort`

## pseudocode

```c
__int64 __fastcall RpcDeletePort(LPWSTR pName, HWND hWnd, LPWSTR pPortName)
{
  DWORD v7; // ebx
  BOOL v8; // ebx
  DWORD LastError; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp+20h] BYREF

  Binding = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "RpcDeletePort",
      L"Trying to delete a port in Windows Protected Print mode.");
    return 50;
  }
  v7 = 0;
  if ( RpcServerInqBindingHandle(&Binding) || !TlsSetValue(gdwTlsBindingHandle, Binding) )
    return v7;
  if ( (unsigned int)RpcApiValidSecurityLevel(Binding) )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError("RpcDeletePort", L"Rpc call is access denied.");
    return 5;
  }
  if ( !(unsigned int)YImpersonateClient(1) )
    goto LABEL_11;
  v8 = DeletePortW(pName, hWnd, pPortName);
  YRevertToSelf(1);
  if ( !v8 )
  {
    LastError = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError("YDeletePort", L"Failed. Error %d", LastError);
LABEL_11:
    v7 = GetLastError();
    goto LABEL_12;
  }
  v7 = 0;
LABEL_12:
  TlsSetValue(gdwTlsBindingHandle, 0);
  return v7;
}

```

## disassembly

```asm
0x140032df0  push    rbx
0x140032df2  push    rbp
0x140032df3  push    rsi
0x140032df4  push    rdi
0x140032df5  sub     rsp, 28h
0x140032df9  mov     rdi, r8
0x140032dfc  mov     [rsp+48h+Binding], 0
0x140032e05  mov     rsi, rdx
0x140032e08  mov     rbp, rcx
0x140032e0b  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140032e10  test    eax, eax
0x140032e12  jz      short loc_140032E31
0x140032e14  lea     rdx, aTryingToDelete_10; "Trying to delete a port in Windows Prot"...
0x140032e1b  lea     rcx, aRpcdeleteport; "RpcDeletePort"
0x140032e22  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140032e27  mov     eax, 32h ; '2'
0x140032e2c  jmp     loc_140032EE9
0x140032e31  lea     rcx, [rsp+48h+Binding]; Binding
0x140032e36  xor     ebx, ebx
0x140032e38  call    cs:__imp_RpcServerInqBindingHandle
0x140032e3e  test    eax, eax
0x140032e40  jnz     loc_140032EE7
0x140032e46  mov     rdx, [rsp+48h+Binding]; lpTlsValue
0x140032e4b  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140032e51  call    cs:__imp_TlsSetValue
0x140032e57  test    eax, eax
0x140032e59  jz      loc_140032EE7
0x140032e5f  mov     rcx, [rsp+48h+Binding]; void *
0x140032e64  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x140032e69  test    eax, eax
0x140032e6b  jz      short loc_140032E85
0x140032e6d  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x140032e74  lea     rcx, aRpcdeleteport; "RpcDeletePort"
0x140032e7b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140032e80  lea     eax, [rbx+5]
0x140032e83  jmp     short loc_140032EE9
0x140032e85  mov     ecx, 1
0x140032e8a  call    ?YImpersonateClient@@YAHW4Call_Route@@@Z; YImpersonateClient(Call_Route)
0x140032e8f  test    eax, eax
0x140032e91  jz      short loc_140032ED1
0x140032e93  mov     r8, rdi; pPortName
0x140032e96  mov     rdx, rsi; hWnd
0x140032e99  mov     rcx, rbp; pName
0x140032e9c  call    DeletePortW
0x140032ea1  mov     ecx, 1
0x140032ea6  mov     ebx, eax
0x140032ea8  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x140032ead  test    ebx, ebx
0x140032eaf  jz      short loc_140032EB5
0x140032eb1  xor     ebx, ebx
0x140032eb3  jmp     short loc_140032ED9
0x140032eb5  call    cs:__imp_GetLastError
0x140032ebb  mov     r8d, eax
0x140032ebe  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x140032ec5  lea     rcx, aYdeleteport; "YDeletePort"
0x140032ecc  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140032ed1  call    cs:__imp_GetLastError
0x140032ed7  mov     ebx, eax
0x140032ed9  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140032edf  xor     edx, edx; lpTlsValue
0x140032ee1  call    cs:__imp_TlsSetValue
0x140032ee7  mov     eax, ebx
0x140032ee9  add     rsp, 28h
0x140032eed  pop     rdi
0x140032eee  pop     rsi
0x140032eef  pop     rbp
0x140032ef0  pop     rbx
0x140032ef1  retn
```
