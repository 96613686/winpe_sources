# TRemoteWinspool::RpcAsyncDeletePrintProcessor(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *)

- ea: `0x1400460b0`
- end: `0x1400461fd`
- name: `?RpcAsyncDeletePrintProcessor@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22@Z`
- size: `333`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140007600`
- `0x1400087f0`
- `0x14001748c`
- `0x140042708`
- `0x1400460b0`
- `0x14005e898`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004611b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140046137`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004615b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004611b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140046137`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004615b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400460e6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400461cd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400460e6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400461cd`

## string_xrefs

- `0x1400460f2`: `Trying to delete print processor asynchronously in Windows Protected Print mode.`
- `0x1400460f9`: `TRemoteWinspool::RpcAsyncDeletePrintProcessor`
- `0x1400461e5`: `TRemoteWinspool::RpcAsyncDeletePrintProcessor`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncDeletePrintProcessor(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *Source)
{
  int v8; // ebx
  int Instance; // eax
  struct NThreadingLibrary::TWorkItem *Reply[7]; // [rsp+40h] [rbp-38h] BYREF

  Reply[0] = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    LODWORD(Reply[0]) = 50;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncDeletePrintProcessor",
      L"Trying to delete print processor asynchronously in Windows Protected Print mode.");
    return;
  }
  if ( a4 && wcsnlen(a4, 0x104u) >= 0x104
    || a3 && wcsnlen(a3, 0x104u) >= 0x104
    || Source && wcsnlen(Source, 0x104u) >= 0x104 )
  {
    LOWORD(v8) = 87;
LABEL_12:
    LODWORD(Reply[0]) = (unsigned __int16)v8;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncDeletePrintProcessor",
      L"Failed.  Error %d.",
      LODWORD(Reply[0]));
    return;
  }
  Instance = TFunction4<unsigned short *,unsigned short *,unsigned short *,enum Call_Route>::CreateInstance(
               (unsigned int)&YDeletePrintProcessor,
               (_DWORD)a3,
               (_DWORD)a4,
               (_DWORD)Source);
  LOWORD(v8) = Instance;
  if ( Instance < 0 )
    goto LABEL_12;
  v8 = NThreadingLibrary::TWorkCrew::AddItem(g_pWorkCrew, Reply[0]);
  NCoreLibrary::TReferenceCount::Release(Reply[0]);
  if ( v8 < 0 )
    goto LABEL_12;
}

```

## disassembly

```asm
0x1400460b0  push    rbx
0x1400460b2  push    rbp
0x1400460b3  push    rsi
0x1400460b4  push    rdi
0x1400460b5  push    r14
0x1400460b7  sub     rsp, 50h
0x1400460bb  mov     rdi, r9
0x1400460be  mov     [rsp+78h+Reply], 0
0x1400460c7  mov     rsi, r8
0x1400460ca  mov     rbp, rcx
0x1400460cd  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1400460d2  test    eax, eax
0x1400460d4  jz      short loc_14004610A
0x1400460d6  lea     rdx, [rsp+78h+Reply]; Reply
0x1400460db  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x1400460e3  mov     rcx, rbp; pAsync
0x1400460e6  call    cs:__imp_RpcAsyncCompleteCall
0x1400460ed  nop     dword ptr [rax+rax+00h]
0x1400460f2  lea     rdx, aTryingToDelete_3; "Trying to delete print processor asynch"...
0x1400460f9  lea     rcx, aTremotewinspoo_17; "TRemoteWinspool::RpcAsyncDeletePrintPro"...
0x140046100  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140046105  jmp     loc_1400461F1
0x14004610a  mov     r14d, 104h
0x140046110  test    rdi, rdi
0x140046113  jz      short loc_14004612C
0x140046115  mov     edx, r14d; MaxCount
0x140046118  mov     rcx, rdi; Source
0x14004611b  call    cs:__imp_wcsnlen
0x140046122  nop     dword ptr [rax+rax+00h]
0x140046127  cmp     rax, r14
0x14004612a  jnb     short loc_14004616C
0x14004612c  test    rsi, rsi
0x14004612f  jz      short loc_140046148
0x140046131  mov     rdx, r14; MaxCount
0x140046134  mov     rcx, rsi; Source
0x140046137  call    cs:__imp_wcsnlen
0x14004613e  nop     dword ptr [rax+rax+00h]
0x140046143  cmp     rax, r14
0x140046146  jnb     short loc_14004616C
0x140046148  mov     rbx, [rsp+78h+Source]
0x140046150  test    rbx, rbx
0x140046153  jz      short loc_140046173
0x140046155  mov     rdx, r14; MaxCount
0x140046158  mov     rcx, rbx; Source
0x14004615b  call    cs:__imp_wcsnlen
0x140046162  nop     dword ptr [rax+rax+00h]
0x140046167  cmp     rax, r14
0x14004616a  jb      short loc_140046173
0x14004616c  mov     ebx, 80070057h
0x140046171  jmp     short loc_1400461BE
0x140046173  lea     rax, [rsp+78h+Reply]
0x140046178  mov     r9, rbx
0x14004617b  mov     [rsp+78h+var_48], rax
0x140046180  lea     rcx, ?YDeletePrintProcessor@@YAKPEAG00W4Call_Route@@@Z; YDeletePrintProcessor(ushort *,ushort *,ushort *,Call_Route)
0x140046187  mov     r8, rdi
0x14004618a  mov     [rsp+78h+var_50], rbp
0x14004618f  mov     rdx, rsi
0x140046192  call    ?CreateInstance@?$TFunction4@PEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG00W4Call_Route@@@Z0001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction4<ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x140046197  mov     ebx, eax
0x140046199  test    eax, eax
0x14004619b  js      short loc_1400461BE
0x14004619d  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x1400461a2  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x1400461a9  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x1400461ae  mov     rcx, [rsp+78h+Reply]; this
0x1400461b3  mov     ebx, eax
0x1400461b5  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x1400461ba  test    ebx, ebx
0x1400461bc  jns     short loc_1400461F1
0x1400461be  movzx   eax, bx
0x1400461c1  lea     rdx, [rsp+78h+Reply]; Reply
0x1400461c6  mov     rcx, rbp; pAsync
0x1400461c9  mov     dword ptr [rsp+78h+Reply], eax
0x1400461cd  call    cs:__imp_RpcAsyncCompleteCall
0x1400461d4  nop     dword ptr [rax+rax+00h]
0x1400461d9  mov     r8d, dword ptr [rsp+78h+Reply]
0x1400461de  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x1400461e5  lea     rcx, aTremotewinspoo_17; "TRemoteWinspool::RpcAsyncDeletePrintPro"...
0x1400461ec  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400461f1  add     rsp, 50h
0x1400461f5  pop     r14
0x1400461f7  pop     rdi
0x1400461f8  pop     rsi
0x1400461f9  pop     rbp
0x1400461fa  pop     rbx
0x1400461fb  retn
```
