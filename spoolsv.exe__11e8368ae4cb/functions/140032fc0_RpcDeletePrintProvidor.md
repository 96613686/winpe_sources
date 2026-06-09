# RpcDeletePrintProvidor

- ea: `0x140032fc0`
- end: `0x1400330c2`
- name: `RpcDeletePrintProvidor`
- size: `258`
- prototype: `__int64 __fastcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002a70`
- `0x140002ac0`
- `0x1400037d0`
- `0x1400160a0`
- `0x140032fc0`
- `0x1400590f0`
- `0x14005ef30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400330a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140033085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400330a1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140033021`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400330b1`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140033021`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400330b1`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140033008`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140033008`

## string_xrefs

- `0x14003303d`: `Rpc call is access denied.`
- `0x140032fe4`: `Trying to delete a print providor in Windows Protected Print mode.`
- `0x140032feb`: `RpcDeletePrintProvidor`
- `0x140033044`: `RpcDeletePrintProvidor`
- `0x140033095`: `YDeletePrintProvidor`

## pseudocode

```c
__int64 __fastcall RpcDeletePrintProvidor(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPrintProvidorName)
{
  DWORD v7; // ebx
  BOOL v8; // ebx
  DWORD LastError; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp+20h] BYREF

  Binding = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "RpcDeletePrintProvidor",
      L"Trying to delete a print providor in Windows Protected Print mode.");
    return 50;
  }
  v7 = 0;
  if ( RpcServerInqBindingHandle(&Binding) || !TlsSetValue(gdwTlsBindingHandle, Binding) )
    return v7;
  if ( (unsigned int)RpcApiValidSecurityLevel(Binding) )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError("RpcDeletePrintProvidor", L"Rpc call is access denied.");
    return 5;
  }
  if ( !(unsigned int)YImpersonateClient(1) )
    goto LABEL_11;
  v8 = DeletePrintProvidorW(pName, pEnvironment, pPrintProvidorName);
  YRevertToSelf(1);
  if ( !v8 )
  {
    LastError = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError("YDeletePrintProvidor", L"Failed. Error %d", LastError);
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
0x140032fc0  push    rbx
0x140032fc2  push    rbp
0x140032fc3  push    rsi
0x140032fc4  push    rdi
0x140032fc5  sub     rsp, 28h
0x140032fc9  mov     rdi, r8
0x140032fcc  mov     [rsp+48h+Binding], 0
0x140032fd5  mov     rsi, rdx
0x140032fd8  mov     rbp, rcx
0x140032fdb  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140032fe0  test    eax, eax
0x140032fe2  jz      short loc_140033001
0x140032fe4  lea     rdx, aTryingToDelete_4; "Trying to delete a print providor in Wi"...
0x140032feb  lea     rcx, aRpcdeleteprint; "RpcDeletePrintProvidor"
0x140032ff2  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140032ff7  mov     eax, 32h ; '2'
0x140032ffc  jmp     loc_1400330B9
0x140033001  lea     rcx, [rsp+48h+Binding]; Binding
0x140033006  xor     ebx, ebx
0x140033008  call    cs:__imp_RpcServerInqBindingHandle
0x14003300e  test    eax, eax
0x140033010  jnz     loc_1400330B7
0x140033016  mov     rdx, [rsp+48h+Binding]; lpTlsValue
0x14003301b  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140033021  call    cs:__imp_TlsSetValue
0x140033027  test    eax, eax
0x140033029  jz      loc_1400330B7
0x14003302f  mov     rcx, [rsp+48h+Binding]; void *
0x140033034  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x140033039  test    eax, eax
0x14003303b  jz      short loc_140033055
0x14003303d  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x140033044  lea     rcx, aRpcdeleteprint; "RpcDeletePrintProvidor"
0x14003304b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140033050  lea     eax, [rbx+5]
0x140033053  jmp     short loc_1400330B9
0x140033055  mov     ecx, 1
0x14003305a  call    ?YImpersonateClient@@YAHW4Call_Route@@@Z; YImpersonateClient(Call_Route)
0x14003305f  test    eax, eax
0x140033061  jz      short loc_1400330A1
0x140033063  mov     r8, rdi; pPrintProvidorName
0x140033066  mov     rdx, rsi; pEnvironment
0x140033069  mov     rcx, rbp; pName
0x14003306c  call    DeletePrintProvidorW
0x140033071  mov     ecx, 1
0x140033076  mov     ebx, eax
0x140033078  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x14003307d  test    ebx, ebx
0x14003307f  jz      short loc_140033085
0x140033081  xor     ebx, ebx
0x140033083  jmp     short loc_1400330A9
0x140033085  call    cs:__imp_GetLastError
0x14003308b  mov     r8d, eax
0x14003308e  lea     rdx, aFailedErrorD_1; "Failed. Error %d"
0x140033095  lea     rcx, aYdeleteprintpr; "YDeletePrintProvidor"
0x14003309c  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400330a1  call    cs:__imp_GetLastError
0x1400330a7  mov     ebx, eax
0x1400330a9  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400330af  xor     edx, edx; lpTlsValue
0x1400330b1  call    cs:__imp_TlsSetValue
0x1400330b7  mov     eax, ebx
0x1400330b9  add     rsp, 28h
0x1400330bd  pop     rdi
0x1400330be  pop     rsi
0x1400330bf  pop     rbp
0x1400330c0  pop     rbx
0x1400330c1  retn
```
