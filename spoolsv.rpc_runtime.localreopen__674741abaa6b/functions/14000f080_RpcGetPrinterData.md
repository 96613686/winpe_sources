# RpcGetPrinterData

- ea: `0x14000f080`
- end: `0x14000f261`
- name: `RpcGetPrinterData`
- size: `481`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000f080`
- `0x14001748c`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f215`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f206`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f231`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f125`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f206`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f231`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000f0c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000f245`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000f0c8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000f245`
- `RPCRT4!RpcRevertToSelf` at `0x14000f223`
- `RPCRT4!RpcRevertToSelf` at `0x14000f223`
- `RPCRT4!RpcImpersonateClient` at `0x14000f10f`
- `RPCRT4!RpcImpersonateClient` at `0x14000f10f`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14000f160`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14000f160`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000f0a9`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14000f0a9`

## string_xrefs

- `0x14000f0f6`: `RpcApiValidSecurityLevel`
- `0x14000f17a`: `RpcApiValidSecurityLevel`
- `0x14000f19a`: `RpcApiValidSecurityLevel`
- `0x14000f1a6`: `Rpc call is access denied.`
- `0x14000f193`: `Authentication level is not RPC_C_AUTHN_LEVEL_PKT_PRIVACY! Returning RPC_S_ACCESS_DENIED.`

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
0x14000f080  push    rbx
0x14000f082  push    rbp
0x14000f083  push    rsi
0x14000f084  push    rdi
0x14000f085  push    r14
0x14000f087  push    r15
0x14000f089  sub     rsp, 68h
0x14000f08d  mov     rbx, rcx
0x14000f090  xor     r15d, r15d
0x14000f093  lea     rcx, [rsp+98h+Binding]; Binding
0x14000f098  mov     [rsp+98h+Binding], r15
0x14000f09d  mov     edi, r15d
0x14000f0a0  mov     rsi, r9
0x14000f0a3  mov     rbp, r8
0x14000f0a6  mov     r14, rdx
0x14000f0a9  call    cs:__imp_RpcServerInqBindingHandle
0x14000f0b0  nop     dword ptr [rax+rax+00h]
0x14000f0b5  test    eax, eax
0x14000f0b7  jnz     loc_14000F251
0x14000f0bd  mov     rdx, [rsp+98h+Binding]; lpTlsValue
0x14000f0c2  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000f0c8  call    cs:__imp_TlsSetValue
0x14000f0cf  nop     dword ptr [rax+rax+00h]
0x14000f0d4  test    eax, eax
0x14000f0d6  jz      loc_14000F251
0x14000f0dc  cmp     cs:?g_dwRpcAuthnLevelPrivacyEnabled@@3KA, r15d; ulong g_dwRpcAuthnLevelPrivacyEnabled
0x14000f0e3  mov     [rsp+98h+Privs], r15
0x14000f0e8  mov     [rsp+98h+AuthnLevel], r15d
0x14000f0ed  jnz     short loc_14000F144
0x14000f0ef  lea     rdx, aRpcAuthenticat; "Rpc authentication level PKT privacy is"...
0x14000f0f6  lea     rcx, aRpcapivalidsec; "RpcApiValidSecurityLevel"
0x14000f0fd  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f102  mov     rdi, [rsp+98h+arg_28]
0x14000f10a  xor     ecx, ecx; BindingHandle
0x14000f10c  mov     [rdi], r15d
0x14000f10f  call    cs:__imp_RpcImpersonateClient
0x14000f116  nop     dword ptr [rax+rax+00h]
0x14000f11b  test    eax, eax
0x14000f11d  jz      loc_14000F1C3
0x14000f123  mov     ecx, eax; dwErrCode
0x14000f125  call    cs:__imp_SetLastError
0x14000f12c  nop     dword ptr [rax+rax+00h]
0x14000f131  call    cs:__imp_GetLastError
0x14000f138  nop     dword ptr [rax+rax+00h]
0x14000f13d  mov     edi, eax
0x14000f13f  jmp     loc_14000F23D
0x14000f144  mov     rcx, [rsp+98h+Binding]; ClientBinding
0x14000f149  lea     r9, [rsp+98h+AuthnLevel]; AuthnLevel
0x14000f14e  mov     [rsp+98h+AuthzSvc], r15; AuthzSvc
0x14000f153  lea     rdx, [rsp+98h+Privs]; Privs
0x14000f158  xor     r8d, r8d; ServerPrincName
0x14000f15b  mov     [rsp+98h+AuthnSvc], r15; AuthnSvc
0x14000f160  call    cs:__imp_RpcBindingInqAuthClientW
0x14000f167  nop     dword ptr [rax+rax+00h]
0x14000f16c  test    eax, eax
0x14000f16e  jz      short loc_14000F188
0x14000f170  mov     r8d, eax
0x14000f173  lea     rdx, aRpcbindinginqa; "RpcBindingInqAuthClient returned: 0x%x"
0x14000f17a  lea     rcx, aRpcapivalidsec; "RpcApiValidSecurityLevel"
0x14000f181  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f186  jmp     short loc_14000F1A6
0x14000f188  cmp     [rsp+98h+AuthnLevel], 6
0x14000f18d  jnb     loc_14000F102
0x14000f193  lea     rdx, aAuthentication; "Authentication level is not RPC_C_AUTHN"...
0x14000f19a  lea     rcx, aRpcapivalidsec; "RpcApiValidSecurityLevel"
0x14000f1a1  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f1a6  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x14000f1ad  lea     rcx, aRpcgetprinterd_2; "RpcGetPrinterData"
0x14000f1b4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f1b9  mov     eax, 5
0x14000f1be  jmp     loc_14000F253
0x14000f1c3  test    rbx, rbx
0x14000f1c6  jz      short loc_14000F201
0x14000f1c8  cmp     dword ptr [rbx], 6060h
0x14000f1ce  jnz     short loc_14000F201
0x14000f1d0  mov     rax, [rbx+8]
0x14000f1d4  mov     r9, rsi
0x14000f1d7  mov     ecx, [rsp+98h+arg_20]
0x14000f1de  mov     r8, rbp
0x14000f1e1  mov     [rsp+98h+AuthzSvc], rdi
0x14000f1e6  mov     rdx, r14
0x14000f1e9  mov     dword ptr [rsp+98h+AuthnSvc], ecx
0x14000f1ed  mov     rax, [rax+100h]
0x14000f1f4  mov     rcx, [rbx+10h]
0x14000f1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f1fd  mov     edi, eax
0x14000f1ff  jmp     short loc_14000F215
0x14000f201  mov     ecx, 6; dwErrCode
0x14000f206  call    cs:__imp_SetLastError
0x14000f20d  nop     dword ptr [rax+rax+00h]
0x14000f212  mov     edi, r15d
0x14000f215  call    cs:__imp_GetLastError
0x14000f21c  nop     dword ptr [rax+rax+00h]
0x14000f221  mov     ebx, eax
0x14000f223  call    cs:__imp_RpcRevertToSelf
0x14000f22a  nop     dword ptr [rax+rax+00h]
0x14000f22f  mov     ecx, ebx; dwErrCode
0x14000f231  call    cs:__imp_SetLastError
0x14000f238  nop     dword ptr [rax+rax+00h]
0x14000f23d  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x14000f243  xor     edx, edx; lpTlsValue
0x14000f245  call    cs:__imp_TlsSetValue
0x14000f24c  nop     dword ptr [rax+rax+00h]
0x14000f251  mov     eax, edi
0x14000f253  add     rsp, 68h
0x14000f257  pop     r15
0x14000f259  pop     r14
0x14000f25b  pop     rdi
0x14000f25c  pop     rsi
0x14000f25d  pop     rbp
0x14000f25e  pop     rbx
0x14000f25f  retn
```
