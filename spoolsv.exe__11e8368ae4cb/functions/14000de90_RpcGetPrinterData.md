# RpcGetPrinterData

- ea: `0x14000de90`
- end: `0x14000e027`
- name: `RpcGetPrinterData`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000de90`
- `0x1400160a0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dff4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000df29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dff4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000df23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e004`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000df23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e004`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000ded2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000e012`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000ded2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000e012`
- `RPCRT4!RpcRevertToSelf` at `0x14000dffc`
- `RPCRT4!RpcRevertToSelf` at `0x14000dffc`
- `RPCRT4!RpcImpersonateClient` at `0x14000df13`
- `RPCRT4!RpcImpersonateClient` at `0x14000df13`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14000df52`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14000df52`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000deb9`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000deb9`

## string_xrefs

- `0x14000defa`: `RpcApiValidSecurityLevel`
- `0x14000df66`: `RpcApiValidSecurityLevel`
- `0x14000df82`: `RpcApiValidSecurityLevel`
- `0x14000df8e`: `Rpc call is access denied.`
- `0x14000df7b`: `Authentication level is not RPC_C_AUTHN_LEVEL_PKT_PRIVACY! Returning RPC_S_ACCESS_DENIED.`

## pseudocode

```c
__int64 __fastcall RpcGetPrinterData(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, _DWORD *a6)
{
  DWORD LastError; // edi
  RPC_STATUS v11; // eax
  unsigned int v12; // eax
  DWORD v14; // ebx
  unsigned int AuthnLevel; // [rsp+40h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-50h] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+50h] [rbp-48h] BYREF

  Binding = 0;
  LastError = 0;
  if ( !RpcServerInqBindingHandle(&Binding) && TlsSetValue(gdwTlsBindingHandle, Binding) )
  {
    Privs = 0;
    AuthnLevel = 0;
    if ( !*(_DWORD *)&g_dwRpcAuthnLevelPrivacyEnabled )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "RpcApiValidSecurityLevel",
        L"Rpc authentication level PKT privacy is not enabled.");
LABEL_5:
      *a6 = 0;
      v11 = RpcImpersonateClient(0);
      if ( v11 )
      {
        SetLastError(v11);
        LastError = GetLastError();
      }
      else
      {
        if ( a1 && *(_DWORD *)a1 == 24672 )
        {
          LastError = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, int, _DWORD *))(*(_QWORD *)(a1 + 8)
                                                                                                  + 256LL))(
                        *(_QWORD *)(a1 + 16),
                        a2,
                        a3,
                        a4,
                        a5,
                        a6);
        }
        else
        {
          SetLastError(6u);
          LastError = 0;
        }
        v14 = GetLastError();
        RpcRevertToSelf();
        SetLastError(v14);
      }
      TlsSetValue(gdwTlsBindingHandle, 0);
      return LastError;
    }
    v12 = RpcBindingInqAuthClientW(Binding, &Privs, 0, &AuthnLevel, 0, 0);
    if ( v12 )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "RpcApiValidSecurityLevel",
        L"RpcBindingInqAuthClient returned: 0x%x",
        v12);
    }
    else
    {
      if ( AuthnLevel >= 6 )
        goto LABEL_5;
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "RpcApiValidSecurityLevel",
        L"Authentication level is not RPC_C_AUTHN_LEVEL_PKT_PRIVACY! Returning RPC_S_ACCESS_DENIED.");
    }
    SpoolerServiceTelemetry::WriteDbgTraceError("RpcGetPrinterData", L"Rpc call is access denied.");
    return 5;
  }
  return LastError;
}

```

## disassembly

```asm
0x14000de90  push    rbx
0x14000de92  push    rbp
0x14000de93  push    rsi
0x14000de94  push    rdi
0x14000de95  push    r14
0x14000de97  push    r15
0x14000de99  sub     rsp, 68h
0x14000de9d  mov     rbx, rcx
0x14000dea0  xor     r15d, r15d
0x14000dea3  lea     rcx, [rsp+98h+Binding]; Binding
0x14000dea8  mov     [rsp+98h+Binding], r15
0x14000dead  mov     edi, r15d
0x14000deb0  mov     rsi, r9
0x14000deb3  mov     rbp, r8
0x14000deb6  mov     r14, rdx
0x14000deb9  call    cs:__imp_RpcServerInqBindingHandle
0x14000debf  test    eax, eax
0x14000dec1  jnz     loc_14000E018
0x14000dec7  mov     rdx, [rsp+98h+Binding]; lpTlsValue
0x14000decc  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000ded2  call    cs:__imp_TlsSetValue
0x14000ded8  test    eax, eax
0x14000deda  jz      loc_14000E018
0x14000dee0  cmp     cs:?g_dwRpcAuthnLevelPrivacyEnabled@@3KA, r15d; ulong g_dwRpcAuthnLevelPrivacyEnabled
0x14000dee7  mov     [rsp+98h+Privs], r15
0x14000deec  mov     [rsp+98h+AuthnLevel], r15d
0x14000def1  jnz     short loc_14000DF36
0x14000def3  lea     rdx, aRpcAuthenticat; "Rpc authentication level PKT privacy is"...
0x14000defa  lea     rcx, aRpcapivalidsec; "RpcApiValidSecurityLevel"
0x14000df01  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000df06  mov     rdi, [rsp+98h+arg_28]
0x14000df0e  xor     ecx, ecx; BindingHandle
0x14000df10  mov     [rdi], r15d
0x14000df13  call    cs:__imp_RpcImpersonateClient
0x14000df19  test    eax, eax
0x14000df1b  jz      loc_14000DFA8
0x14000df21  mov     ecx, eax; dwErrCode
0x14000df23  call    cs:__imp_SetLastError
0x14000df29  call    cs:__imp_GetLastError
0x14000df2f  mov     edi, eax
0x14000df31  jmp     loc_14000E00A
0x14000df36  mov     rcx, [rsp+98h+Binding]; ClientBinding
0x14000df3b  lea     r9, [rsp+98h+AuthnLevel]; AuthnLevel
0x14000df40  mov     [rsp+98h+AuthzSvc], r15; AuthzSvc
0x14000df45  lea     rdx, [rsp+98h+Privs]; Privs
0x14000df4a  xor     r8d, r8d; ServerPrincName
0x14000df4d  mov     [rsp+98h+AuthnSvc], r15; AuthnSvc
0x14000df52  call    cs:__imp_RpcBindingInqAuthClientW
0x14000df58  test    eax, eax
0x14000df5a  jz      short loc_14000DF74
0x14000df5c  mov     r8d, eax
0x14000df5f  lea     rdx, aRpcbindinginqa; "RpcBindingInqAuthClient returned: 0x%x"
0x14000df66  lea     rcx, aRpcapivalidsec; "RpcApiValidSecurityLevel"
0x14000df6d  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000df72  jmp     short loc_14000DF8E
0x14000df74  cmp     [rsp+98h+AuthnLevel], 6
0x14000df79  jnb     short loc_14000DF06
0x14000df7b  lea     rdx, aAuthentication; "Authentication level is not RPC_C_AUTHN"...
0x14000df82  lea     rcx, aRpcapivalidsec; "RpcApiValidSecurityLevel"
0x14000df89  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000df8e  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x14000df95  lea     rcx, aRpcgetprinterd_2; "RpcGetPrinterData"
0x14000df9c  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000dfa1  mov     eax, 5
0x14000dfa6  jmp     short loc_14000E01A
0x14000dfa8  test    rbx, rbx
0x14000dfab  jz      short loc_14000DFE6
0x14000dfad  cmp     dword ptr [rbx], 6060h
0x14000dfb3  jnz     short loc_14000DFE6
0x14000dfb5  mov     rax, [rbx+8]
0x14000dfb9  mov     r9, rsi
0x14000dfbc  mov     ecx, [rsp+98h+arg_20]
0x14000dfc3  mov     r8, rbp
0x14000dfc6  mov     [rsp+98h+AuthzSvc], rdi
0x14000dfcb  mov     rdx, r14
0x14000dfce  mov     dword ptr [rsp+98h+AuthnSvc], ecx
0x14000dfd2  mov     rax, [rax+100h]
0x14000dfd9  mov     rcx, [rbx+10h]
0x14000dfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfe2  mov     edi, eax
0x14000dfe4  jmp     short loc_14000DFF4
0x14000dfe6  mov     ecx, 6; dwErrCode
0x14000dfeb  call    cs:__imp_SetLastError
0x14000dff1  mov     edi, r15d
0x14000dff4  call    cs:__imp_GetLastError
0x14000dffa  mov     ebx, eax
0x14000dffc  call    cs:__imp_RpcRevertToSelf
0x14000e002  mov     ecx, ebx; dwErrCode
0x14000e004  call    cs:__imp_SetLastError
0x14000e00a  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000e010  xor     edx, edx; lpTlsValue
0x14000e012  call    cs:__imp_TlsSetValue
0x14000e018  mov     eax, edi
0x14000e01a  add     rsp, 68h
0x14000e01e  pop     r15
0x14000e020  pop     r14
0x14000e022  pop     rdi
0x14000e023  pop     rsi
0x14000e024  pop     rbp
0x14000e025  pop     rbx
0x14000e026  retn
```
