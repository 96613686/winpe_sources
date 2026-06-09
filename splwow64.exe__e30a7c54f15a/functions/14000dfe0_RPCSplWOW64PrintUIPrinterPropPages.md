# RPCSplWOW64PrintUIPrinterPropPages

- ea: `0x14000dfe0`
- end: `0x14000e107`
- name: `RPCSplWOW64PrintUIPrinterPropPages`
- size: `295`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, LPVOID lpTlsValue@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000dfe0`
- `0x14000f42c`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000dffc`
- `KERNEL32!TlsSetValue` at `0x14000e0f8`
- `KERNEL32!TlsSetValue` at `0x14000dffc`
- `KERNEL32!TlsSetValue` at `0x14000e0f8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e0ea`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e0ea`

## string_xrefs

- `0x14000e005`: `clientProcessID %u pszPrinterName %ws`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64PrintUIPrinterPropPages(
        PRPC_ASYNC_STATE pAsync,
        LPVOID lpTlsValue,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned int v6; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  void *v12; // rbx
  unsigned int v13; // eax
  void *v15; // [rsp+40h] [rbp-38h] BYREF
  unsigned int Reply; // [rsp+88h] [rbp+10h] BYREF

  v6 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo(
    "RPCSplWOW64PrintUIPrinterPropPages",
    L"clientProcessID %u pszPrinterName %ws",
    v6,
    a4);
  v15 = 0;
  Reply = 0;
  v10 = TLoad64BitDllsMgr::QueryInterface(pGLdrObj, &IID_PRINTUIOPERATIONS, &v15);
  v11 = v10;
  if ( v10 )
  {
    SplWow64Telemetry::WriteDbgTraceError(
      "RPCSplWOW64PrintUIPrinterPropPages",
      L"Failed to instantiate a print UI object.  Error hr: 0x%x.",
      v10);
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    Reply = v11;
  }
  else
  {
    v12 = v15;
    v13 = TPrintUIMgr::PrintUIMethod((__int64)v15, "vPrinterPropPages", a3, a4, a5, a6);
    Reply = v13;
    if ( v13 )
      SplWow64Telemetry::WriteDbgTraceError(
        "RPCSplWOW64PrintUIPrinterPropPages",
        L"TPrintUIMgr::PrinterPropPages failed.  Error %d.",
        v13);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000dfe0  push    rbx
0x14000dfe2  push    rbp
0x14000dfe3  push    rsi
0x14000dfe4  push    rdi
0x14000dfe5  sub     rsp, 58h
0x14000dfe9  mov     ebx, edx
0x14000dfeb  mov     rdi, rcx
0x14000dfee  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000dff4  mov     rsi, r9
0x14000dff7  mov     edx, edx; lpTlsValue
0x14000dff9  mov     rbp, r8
0x14000dffc  call    cs:__imp_TlsSetValue
0x14000e002  mov     r9, rsi
0x14000e005  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000e00c  mov     r8d, ebx
0x14000e00f  lea     rcx, aRpcsplwow64pri_5; "RPCSplWOW64PrintUIPrinterPropPages"
0x14000e016  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000e01b  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000e022  lea     r8, [rsp+78h+var_38]; void **
0x14000e027  lea     rdx, ?IID_PRINTUIOPERATIONS@@3U_GUID@@A; struct _GUID *
0x14000e02e  mov     [rsp+78h+var_38], 0
0x14000e037  mov     [rsp+78h+Reply], 0
0x14000e042  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000e047  mov     ebx, eax
0x14000e049  test    eax, eax
0x14000e04b  jnz     short loc_14000E0B1
0x14000e04d  mov     rax, [rsp+78h+arg_28]
0x14000e055  lea     rdx, aVprinterproppa; "vPrinterPropPages"
0x14000e05c  mov     rbx, [rsp+78h+var_38]
0x14000e061  mov     r9, rsi
0x14000e064  mov     [rsp+78h+var_50], rax
0x14000e069  mov     r8, rbp
0x14000e06c  mov     eax, [rsp+78h+arg_20]
0x14000e073  mov     rcx, rbx
0x14000e076  mov     [rsp+78h+var_58], eax
0x14000e07a  call    ?PrintUIMethod@TPrintUIMgr@@QEAAKPEBDPEAXPEBGH_JW4EPrintUIOp@1@@Z; TPrintUIMgr::PrintUIMethod(char const *,void *,ushort const *,int,__int64,TPrintUIMgr::EPrintUIOp)
0x14000e07f  mov     [rsp+78h+Reply], eax
0x14000e086  test    eax, eax
0x14000e088  jz      short loc_14000E0A0
0x14000e08a  mov     r8d, eax
0x14000e08d  lea     rdx, aTprintuimgrPri_1; "TPrintUIMgr::PrinterPropPages failed.  "...
0x14000e094  lea     rcx, aRpcsplwow64pri_5; "RPCSplWOW64PrintUIPrinterPropPages"
0x14000e09b  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e0a0  mov     rax, [rbx]
0x14000e0a3  mov     rcx, rbx
0x14000e0a6  mov     rax, [rax+10h]
0x14000e0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0af  jmp     short loc_14000E0DF
0x14000e0b1  mov     r8d, ebx
0x14000e0b4  lea     rdx, aFailedToInstan_2; "Failed to instantiate a print UI object"...
0x14000e0bb  lea     rcx, aRpcsplwow64pri_5; "RPCSplWOW64PrintUIPrinterPropPages"
0x14000e0c2  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e0c7  mov     eax, ebx
0x14000e0c9  and     eax, 1FFF0000h
0x14000e0ce  cmp     eax, 70000h
0x14000e0d3  jnz     short loc_14000E0D8
0x14000e0d5  movzx   ebx, bx
0x14000e0d8  mov     [rsp+78h+Reply], ebx
0x14000e0df  lea     rdx, [rsp+78h+Reply]; Reply
0x14000e0e7  mov     rcx, rdi; pAsync
0x14000e0ea  call    cs:__imp_RpcAsyncCompleteCall
0x14000e0f0  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e0f6  xor     edx, edx; lpTlsValue
0x14000e0f8  call    cs:__imp_TlsSetValue
0x14000e0fe  add     rsp, 58h
0x14000e102  pop     rdi
0x14000e103  pop     rsi
0x14000e104  pop     rbp
0x14000e105  pop     rbx
0x14000e106  retn
```
