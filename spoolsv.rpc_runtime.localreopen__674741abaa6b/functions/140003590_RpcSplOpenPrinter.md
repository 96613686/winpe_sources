# RpcSplOpenPrinter

- ea: `0x140003590`
- end: `0x140003744`
- name: `RpcSplOpenPrinter`
- size: `436`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pPrinterName@<rcx>, LPHANDLE phPrinter@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400028e0`
- `0x140003590`
- `0x14000374c`
- `0x140003d60`
- `0x140003e10`
- `0x140005240`
- `0x140005520`
- `0x140007090`
- `0x14001748c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400036d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003714`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003670`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003670`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400036f2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400035d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000372a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400035d7`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000372a`
- `RPCRT4!RpcRevertToSelf` at `0x1400036e4`
- `RPCRT4!RpcRevertToSelf` at `0x1400036e4`
- `RPCRT4!RpcImpersonateClient` at `0x14000365e`
- `RPCRT4!RpcImpersonateClient` at `0x14000365e`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1400035b8`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1400035b8`

## string_xrefs

- `0x1400035f9`: `Rpc call is access denied.`
- `0x140003600`: `RpcSplOpenPrinter`

## pseudocode

```c
__int64 __fastcall RpcSplOpenPrinter(
        unsigned __int16 *pPrinterName,
        LPHANDLE phPrinter,
        WCHAR *a3,
        __int64 a4,
        ACCESS_MASK a5,
        struct _SPLCLIENT_CONTAINER *a6)
{
  DWORD v6; // ebx
  RPC_STATUS v12; // eax
  int v13; // eax
  int v14; // edi
  DWORD LastError; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-48h] BYREF
  _PRINTER_DEFAULTSW pDefault; // [rsp+28h] [rbp-40h] BYREF

  v6 = 0;
  Binding = 0;
  CheckCallerRpcContext();
  if ( RpcServerInqBindingHandle(&Binding) || !TlsSetValue(gdwTlsBindingHandle, Binding) )
    return v6;
  if ( (unsigned int)RpcApiValidSecurityLevel(Binding) )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError("RpcSplOpenPrinter", L"Rpc call is access denied.");
    return 5;
  }
  memset(&pDefault, 0, sizeof(pDefault));
  if ( !g_bNoPrintersMode || (unsigned int)CheckLocalCall() )
  {
    if ( a6 && !*((_QWORD *)a6 + 1) )
      goto LABEL_10;
    v12 = RpcImpersonateClient(0);
    if ( v12 )
    {
      SetLastError(v12);
    }
    else
    {
      if ( (unsigned int)InvalidDevModeContainer((struct _DEVMODE_CONTAINER *)a4) )
      {
        YRevertToSelf(1);
LABEL_10:
        v6 = 87;
        goto LABEL_22;
      }
      pDefault.pDevMode = *(LPDEVMODEW *)(a4 + 8);
      pDefault.DesiredAccess = a5;
      pDefault.pDatatype = a3;
      if ( a6 )
        v13 = OpenPrinterExW(pPrinterName, phPrinter, &pDefault, a6);
      else
        v13 = OpenPrinter2W(pPrinterName, phPrinter, &pDefault, 0);
      v14 = v13;
      LastError = GetLastError();
      RpcRevertToSelf();
      SetLastError(LastError);
      if ( v14 )
      {
        _InterlockedIncrement(&ServerHandleCount);
        v6 = 0;
        goto LABEL_22;
      }
      *phPrinter = 0;
    }
    v6 = GetLastError();
    goto LABEL_22;
  }
  v6 = 1801;
LABEL_22:
  TlsSetValue(gdwTlsBindingHandle, 0);
  return v6;
}

```

## disassembly

```asm
0x140003590  push    rbx
0x140003592  push    rbp
0x140003593  push    rsi
0x140003594  push    rdi
0x140003595  push    r14
0x140003597  sub     rsp, 40h
0x14000359b  xor     ebx, ebx
0x14000359d  mov     rdi, r9
0x1400035a0  mov     [rsp+68h+Binding], rbx
0x1400035a5  mov     r14, r8
0x1400035a8  mov     rsi, rdx
0x1400035ab  mov     rbp, rcx
0x1400035ae  call    ?CheckCallerRpcContext@@YAXXZ; CheckCallerRpcContext(void)
0x1400035b3  lea     rcx, [rsp+68h+Binding]; Binding
0x1400035b8  call    cs:__imp_RpcServerInqBindingHandle
0x1400035bf  nop     dword ptr [rax+rax+00h]
0x1400035c4  test    eax, eax
0x1400035c6  jnz     loc_140003736
0x1400035cc  mov     rdx, [rsp+68h+Binding]; lpTlsValue
0x1400035d1  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x1400035d7  call    cs:__imp_TlsSetValue
0x1400035de  nop     dword ptr [rax+rax+00h]
0x1400035e3  test    eax, eax
0x1400035e5  jz      loc_140003736
0x1400035eb  mov     rcx, [rsp+68h+Binding]; void *
0x1400035f0  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x1400035f5  test    eax, eax
0x1400035f7  jz      short loc_140003614
0x1400035f9  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x140003600  lea     rcx, aRpcsplopenprin; "RpcSplOpenPrinter"
0x140003607  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000360c  lea     eax, [rbx+5]
0x14000360f  jmp     loc_140003738
0x140003614  xor     eax, eax
0x140003616  xorps   xmm0, xmm0
0x140003619  cmp     cs:?g_bNoPrintersMode@@3_NA, al; bool g_bNoPrintersMode
0x14000361f  movups  xmmword ptr [rsp+68h+pDefault.pDatatype], xmm0
0x140003624  mov     qword ptr [rsp+68h+pDefault.DesiredAccess], rax
0x140003629  jz      short loc_14000363E
0x14000362b  call    CheckLocalCall
0x140003630  test    eax, eax
0x140003632  jnz     short loc_14000363E
0x140003634  mov     ebx, 709h
0x140003639  jmp     loc_140003722
0x14000363e  mov     rbx, [rsp+68h+arg_28]
0x140003646  test    rbx, rbx
0x140003649  jz      short loc_14000365C
0x14000364b  cmp     qword ptr [rbx+8], 0
0x140003650  jnz     short loc_14000365C
0x140003652  mov     ebx, 57h ; 'W'
0x140003657  jmp     loc_140003722
0x14000365c  xor     ecx, ecx; BindingHandle
0x14000365e  call    cs:__imp_RpcImpersonateClient
0x140003665  nop     dword ptr [rax+rax+00h]
0x14000366a  test    eax, eax
0x14000366c  jz      short loc_140003681
0x14000366e  mov     ecx, eax; dwErrCode
0x140003670  call    cs:__imp_SetLastError
0x140003677  nop     dword ptr [rax+rax+00h]
0x14000367c  jmp     loc_140003714
0x140003681  mov     rcx, rdi; struct _DEVMODE_CONTAINER *
0x140003684  call    ?InvalidDevModeContainer@@YAHPEAU_DEVMODE_CONTAINER@@@Z; InvalidDevModeContainer(_DEVMODE_CONTAINER *)
0x140003689  test    eax, eax
0x14000368b  jz      short loc_140003699
0x14000368d  mov     ecx, 1
0x140003692  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x140003697  jmp     short loc_140003652
0x140003699  mov     rax, [rdi+8]
0x14000369d  lea     r8, [rsp+68h+pDefault]; struct _PRINTER_DEFAULTSW *
0x1400036a2  mov     [rsp+68h+pDefault.pDevMode], rax
0x1400036a7  mov     rdx, rsi; void **
0x1400036aa  mov     eax, [rsp+68h+arg_20]
0x1400036b1  mov     rcx, rbp; unsigned __int16 *
0x1400036b4  mov     [rsp+68h+pDefault.DesiredAccess], eax
0x1400036b8  mov     [rsp+68h+pDefault.pDatatype], r14
0x1400036bd  test    rbx, rbx
0x1400036c0  jz      short loc_1400036CC
0x1400036c2  mov     r9, rbx; struct _SPLCLIENT_CONTAINER *
0x1400036c5  call    ?OpenPrinterExW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAU_SPLCLIENT_CONTAINER@@@Z; OpenPrinterExW(ushort *,void * *,_PRINTER_DEFAULTSW *,_SPLCLIENT_CONTAINER *)
0x1400036ca  jmp     short loc_1400036D4
0x1400036cc  xor     r9d, r9d; pOptions
0x1400036cf  call    OpenPrinter2W
0x1400036d4  mov     edi, eax
0x1400036d6  call    cs:__imp_GetLastError
0x1400036dd  nop     dword ptr [rax+rax+00h]
0x1400036e2  mov     ebx, eax
0x1400036e4  call    cs:__imp_RpcRevertToSelf
0x1400036eb  nop     dword ptr [rax+rax+00h]
0x1400036f0  mov     ecx, ebx; dwErrCode
0x1400036f2  call    cs:__imp_SetLastError
0x1400036f9  nop     dword ptr [rax+rax+00h]
0x1400036fe  test    edi, edi
0x140003700  jz      short loc_14000370D
0x140003702  lock inc cs:?ServerHandleCount@@3JA; long ServerHandleCount
0x140003709  xor     ebx, ebx
0x14000370b  jmp     short loc_140003722
0x14000370d  mov     qword ptr [rsi], 0
0x140003714  call    cs:__imp_GetLastError
0x14000371b  nop     dword ptr [rax+rax+00h]
0x140003720  mov     ebx, eax
0x140003722  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140003728  xor     edx, edx; lpTlsValue
0x14000372a  call    cs:__imp_TlsSetValue
0x140003731  nop     dword ptr [rax+rax+00h]
0x140003736  mov     eax, ebx
0x140003738  add     rsp, 40h
0x14000373c  pop     r14
0x14000373e  pop     rdi
0x14000373f  pop     rsi
0x140003740  pop     rbp
0x140003741  pop     rbx
0x140003742  retn
```
