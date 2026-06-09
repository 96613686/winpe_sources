# RpcSplOpenPrinter

- ea: `0x1400030d0`
- end: `0x14000324d`
- name: `RpcSplOpenPrinter`
- size: `381`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pPrinterName@<rcx>, LPHANDLE phPrinter@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140002a70`
- `0x1400030d0`
- `0x140003254`
- `0x1400037d0`
- `0x140003880`
- `0x140004ae0`
- `0x140004da0`
- `0x1400065f0`
- `0x1400160a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000322a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400031fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000322a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000319e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000320e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000319e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000320e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003111`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000323a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140003111`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14000323a`
- `RPCRT4!RpcRevertToSelf` at `0x140003206`
- `RPCRT4!RpcRevertToSelf` at `0x140003206`
- `RPCRT4!RpcImpersonateClient` at `0x140003192`
- `RPCRT4!RpcImpersonateClient` at `0x140003192`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1400030f8`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1400030f8`

## string_xrefs

- `0x14000312d`: `Rpc call is access denied.`
- `0x140003134`: `RpcSplOpenPrinter`

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
0x1400030d0  push    rbx
0x1400030d2  push    rbp
0x1400030d3  push    rsi
0x1400030d4  push    rdi
0x1400030d5  push    r14
0x1400030d7  sub     rsp, 40h
0x1400030db  xor     ebx, ebx
0x1400030dd  mov     rdi, r9
0x1400030e0  mov     [rsp+68h+Binding], rbx
0x1400030e5  mov     r14, r8
0x1400030e8  mov     rsi, rdx
0x1400030eb  mov     rbp, rcx
0x1400030ee  call    ?CheckCallerRpcContext@@YAXXZ; CheckCallerRpcContext(void)
0x1400030f3  lea     rcx, [rsp+68h+Binding]; Binding
0x1400030f8  call    cs:__imp_RpcServerInqBindingHandle
0x1400030fe  test    eax, eax
0x140003100  jnz     loc_140003240
0x140003106  mov     rdx, [rsp+68h+Binding]; lpTlsValue
0x14000310b  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140003111  call    cs:__imp_TlsSetValue
0x140003117  test    eax, eax
0x140003119  jz      loc_140003240
0x14000311f  mov     rcx, [rsp+68h+Binding]; void *
0x140003124  call    ?RpcApiValidSecurityLevel@@YAJPEAX@Z; RpcApiValidSecurityLevel(void *)
0x140003129  test    eax, eax
0x14000312b  jz      short loc_140003148
0x14000312d  lea     rdx, aRpcCallIsAcces; "Rpc call is access denied."
0x140003134  lea     rcx, aRpcsplopenprin; "RpcSplOpenPrinter"
0x14000313b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140003140  lea     eax, [rbx+5]
0x140003143  jmp     loc_140003242
0x140003148  xor     eax, eax
0x14000314a  xorps   xmm0, xmm0
0x14000314d  cmp     cs:?g_bNoPrintersMode@@3_NA, al; bool g_bNoPrintersMode
0x140003153  movups  xmmword ptr [rsp+68h+pDefault.pDatatype], xmm0
0x140003158  mov     qword ptr [rsp+68h+pDefault.DesiredAccess], rax
0x14000315d  jz      short loc_140003172
0x14000315f  call    CheckLocalCall
0x140003164  test    eax, eax
0x140003166  jnz     short loc_140003172
0x140003168  mov     ebx, 709h
0x14000316d  jmp     loc_140003232
0x140003172  mov     rbx, [rsp+68h+arg_28]
0x14000317a  test    rbx, rbx
0x14000317d  jz      short loc_140003190
0x14000317f  cmp     qword ptr [rbx+8], 0
0x140003184  jnz     short loc_140003190
0x140003186  mov     ebx, 57h ; 'W'
0x14000318b  jmp     loc_140003232
0x140003190  xor     ecx, ecx; BindingHandle
0x140003192  call    cs:__imp_RpcImpersonateClient
0x140003198  test    eax, eax
0x14000319a  jz      short loc_1400031A9
0x14000319c  mov     ecx, eax; dwErrCode
0x14000319e  call    cs:__imp_SetLastError
0x1400031a4  jmp     loc_14000322A
0x1400031a9  mov     rcx, rdi; struct _DEVMODE_CONTAINER *
0x1400031ac  call    ?InvalidDevModeContainer@@YAHPEAU_DEVMODE_CONTAINER@@@Z; InvalidDevModeContainer(_DEVMODE_CONTAINER *)
0x1400031b1  test    eax, eax
0x1400031b3  jz      short loc_1400031C1
0x1400031b5  mov     ecx, 1
0x1400031ba  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x1400031bf  jmp     short loc_140003186
0x1400031c1  mov     rax, [rdi+8]
0x1400031c5  lea     r8, [rsp+68h+pDefault]; struct _PRINTER_DEFAULTSW *
0x1400031ca  mov     [rsp+68h+pDefault.pDevMode], rax
0x1400031cf  mov     rdx, rsi; void **
0x1400031d2  mov     eax, [rsp+68h+arg_20]
0x1400031d9  mov     rcx, rbp; unsigned __int16 *
0x1400031dc  mov     [rsp+68h+pDefault.DesiredAccess], eax
0x1400031e0  mov     [rsp+68h+pDefault.pDatatype], r14
0x1400031e5  test    rbx, rbx
0x1400031e8  jz      short loc_1400031F4
0x1400031ea  mov     r9, rbx; struct _SPLCLIENT_CONTAINER *
0x1400031ed  call    ?OpenPrinterExW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAU_SPLCLIENT_CONTAINER@@@Z; OpenPrinterExW(ushort *,void * *,_PRINTER_DEFAULTSW *,_SPLCLIENT_CONTAINER *)
0x1400031f2  jmp     short loc_1400031FC
0x1400031f4  xor     r9d, r9d; pOptions
0x1400031f7  call    OpenPrinter2W
0x1400031fc  mov     edi, eax
0x1400031fe  call    cs:__imp_GetLastError
0x140003204  mov     ebx, eax
0x140003206  call    cs:__imp_RpcRevertToSelf
0x14000320c  mov     ecx, ebx; dwErrCode
0x14000320e  call    cs:__imp_SetLastError
0x140003214  test    edi, edi
0x140003216  jz      short loc_140003223
0x140003218  lock inc cs:?ServerHandleCount@@3JA; long ServerHandleCount
0x14000321f  xor     ebx, ebx
0x140003221  jmp     short loc_140003232
0x140003223  mov     qword ptr [rsi], 0
0x14000322a  call    cs:__imp_GetLastError
0x140003230  mov     ebx, eax
0x140003232  mov     ecx, cs:?gdwTlsBindingHandle@@3KA; dwTlsIndex
0x140003238  xor     edx, edx; lpTlsValue
0x14000323a  call    cs:__imp_TlsSetValue
0x140003240  mov     eax, ebx
0x140003242  add     rsp, 40h
0x140003246  pop     r14
0x140003248  pop     rdi
0x140003249  pop     rsi
0x14000324a  pop     rbp
0x14000324b  pop     rbx
0x14000324c  retn
```
