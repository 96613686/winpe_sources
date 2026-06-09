# RPCSplWOW64PrinterProperties

- ea: `0x14000e530`
- end: `0x14000e66f`
- name: `RPCSplWOW64PrinterProperties`
- size: `319`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, LPVOID lpTlsValue, unsigned __int64, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000e530`
- `0x14000ef6c`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000e555`
- `KERNEL32!TlsSetValue` at `0x14000e656`
- `KERNEL32!TlsSetValue` at `0x14000e555`
- `KERNEL32!TlsSetValue` at `0x14000e656`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e648`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e648`

## string_xrefs

- `0x14000e55e`: `clientProcessID %u pszPrinterName %ws`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64PrinterProperties(
        PRPC_ASYNC_STATE pAsync,
        LPVOID lpTlsValue,
        __int64 a3,
        unsigned __int16 *a4,
        __int16 a5,
        unsigned int *a6)
{
  unsigned int v6; // ebx
  unsigned int Interface; // eax
  unsigned int v11; // ebx
  TPrinterCfgMgr *v12; // rbx
  unsigned int *v13; // rdi
  TPrinterCfgMgr *v15; // [rsp+30h] [rbp-28h] BYREF
  int Reply; // [rsp+68h] [rbp+10h] BYREF

  v6 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo("RPCSplWOW64PrinterProperties", L"clientProcessID %u pszPrinterName %ws", v6, a4);
  v15 = 0;
  Reply = 0;
  Interface = TLoad64BitDllsMgr::QueryInterface(pGLdrObj, &IID_PRINTERCONFIGURATION, (void **)&v15);
  v11 = Interface;
  if ( Interface )
  {
    SplWow64Telemetry::WriteDbgTraceError(
      "RPCSplWOW64PrinterProperties",
      L"Failed to instantiate a print event object.  Error hr: 0x%x",
      Interface);
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    *a6 = v11;
  }
  else
  {
    v12 = v15;
    if ( v15 )
    {
      v13 = a6;
      Reply = TPrinterCfgMgr::PrinterProperties((TLoad64BitDllsMgr **)v15, a3, a4, a5, a6);
      if ( !Reply )
        SplWow64Telemetry::WriteDbgTraceError(
          "RPCSplWOW64PrinterProperties",
          L"TPrinterEventMgr::PrinterProperties failed.  Error %d",
          *v13);
      (*(void (__fastcall **)(TPrinterCfgMgr *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    else
    {
      *a6 = -2147467262;
    }
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000e530  mov     [rsp+arg_0], rbx
0x14000e535  mov     [rsp+arg_10], rbp
0x14000e53a  push    rsi
0x14000e53b  push    rdi
0x14000e53c  push    r14
0x14000e53e  sub     rsp, 40h
0x14000e542  mov     ebx, edx
0x14000e544  mov     rbp, rcx
0x14000e547  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e54d  mov     rsi, r9
0x14000e550  mov     edx, edx; lpTlsValue
0x14000e552  mov     r14, r8
0x14000e555  call    cs:__imp_TlsSetValue
0x14000e55b  mov     r9, rsi
0x14000e55e  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000e565  mov     r8d, ebx
0x14000e568  lea     rcx, aRpcsplwow64pri_4; "RPCSplWOW64PrinterProperties"
0x14000e56f  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000e574  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000e57b  lea     r8, [rsp+58h+var_28]; void **
0x14000e580  lea     rdx, ?IID_PRINTERCONFIGURATION@@3U_GUID@@A; struct _GUID *
0x14000e587  mov     [rsp+58h+var_28], 0
0x14000e590  mov     [rsp+58h+Reply], 0
0x14000e598  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000e59d  mov     ebx, eax
0x14000e59f  test    eax, eax
0x14000e5a1  jnz     short loc_14000E60F
0x14000e5a3  mov     rbx, [rsp+58h+var_28]
0x14000e5a8  test    rbx, rbx
0x14000e5ab  jz      short loc_14000E5FF
0x14000e5ad  mov     rdi, [rsp+58h+arg_28]
0x14000e5b5  mov     r8, rsi; unsigned __int16 *
0x14000e5b8  mov     r9d, dword ptr [rsp+58h+arg_20]; unsigned int
0x14000e5c0  mov     rdx, r14; unsigned __int64
0x14000e5c3  mov     rcx, rbx; this
0x14000e5c6  mov     [rsp+58h+var_38], rdi; unsigned int *
0x14000e5cb  call    ?PrinterProperties@TPrinterCfgMgr@@QEAAH_KPEBGKPEAK@Z; TPrinterCfgMgr::PrinterProperties(unsigned __int64,ushort const *,ulong,ulong *)
0x14000e5d0  mov     [rsp+58h+Reply], eax
0x14000e5d4  test    eax, eax
0x14000e5d6  jnz     short loc_14000E5EE
0x14000e5d8  mov     r8d, [rdi]
0x14000e5db  lea     rdx, aTprintereventm_1; "TPrinterEventMgr::PrinterProperties fai"...
0x14000e5e2  lea     rcx, aRpcsplwow64pri_4; "RPCSplWOW64PrinterProperties"
0x14000e5e9  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e5ee  mov     rax, [rbx]
0x14000e5f1  mov     rcx, rbx
0x14000e5f4  mov     rax, [rax+10h]
0x14000e5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5fd  jmp     short loc_14000E640
0x14000e5ff  mov     rax, [rsp+58h+arg_28]
0x14000e607  mov     dword ptr [rax], 80004002h
0x14000e60d  jmp     short loc_14000E640
0x14000e60f  mov     r8d, ebx
0x14000e612  lea     rdx, aFailedToInstan_1; "Failed to instantiate a print event obj"...
0x14000e619  lea     rcx, aRpcsplwow64pri_4; "RPCSplWOW64PrinterProperties"
0x14000e620  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e625  mov     eax, ebx
0x14000e627  and     eax, 1FFF0000h
0x14000e62c  cmp     eax, 70000h
0x14000e631  jnz     short loc_14000E636
0x14000e633  movzx   ebx, bx
0x14000e636  mov     rax, [rsp+58h+arg_28]
0x14000e63e  mov     [rax], ebx
0x14000e640  lea     rdx, [rsp+58h+Reply]; Reply
0x14000e645  mov     rcx, rbp; pAsync
0x14000e648  call    cs:__imp_RpcAsyncCompleteCall
0x14000e64e  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e654  xor     edx, edx; lpTlsValue
0x14000e656  call    cs:__imp_TlsSetValue
0x14000e65c  mov     rbx, [rsp+58h+arg_0]
0x14000e661  mov     rbp, [rsp+58h+arg_10]
0x14000e666  add     rsp, 40h
0x14000e66a  pop     r14
0x14000e66c  pop     rdi
0x14000e66d  pop     rsi
0x14000e66e  retn
```
