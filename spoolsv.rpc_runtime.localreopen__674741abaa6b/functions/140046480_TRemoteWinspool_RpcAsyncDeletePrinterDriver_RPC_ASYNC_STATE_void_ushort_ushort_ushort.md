# TRemoteWinspool::RpcAsyncDeletePrinterDriver(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *)

- ea: `0x140046480`
- end: `0x1400465cd`
- name: `?RpcAsyncDeletePrinterDriver@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22@Z`
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
- `0x140046480`
- `0x14005e898`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400464eb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140046507`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004652b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400464eb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140046507`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004652b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400464b6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004659d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400464b6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004659d`

## string_xrefs

- `0x1400464c2`: `Trying to delete printer driver asynchronously in Windows Protected Print mode.`
- `0x1400464c9`: `TRemoteWinspool::RpcAsyncDeletePrinterDriver`
- `0x1400465b5`: `TRemoteWinspool::RpcAsyncDeletePrinterDriver`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncDeletePrinterDriver(
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
      "TRemoteWinspool::RpcAsyncDeletePrinterDriver",
      L"Trying to delete printer driver asynchronously in Windows Protected Print mode.");
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
      "TRemoteWinspool::RpcAsyncDeletePrinterDriver",
      L"Failed.  Error %d.",
      LODWORD(Reply[0]));
    return;
  }
  Instance = TFunction4<unsigned short *,unsigned short *,unsigned short *,enum Call_Route>::CreateInstance(
               (unsigned int)&YDeletePrinterDriver,
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
0x140046480  push    rbx
0x140046482  push    rbp
0x140046483  push    rsi
0x140046484  push    rdi
0x140046485  push    r14
0x140046487  sub     rsp, 50h
0x14004648b  mov     rdi, r9
0x14004648e  mov     [rsp+78h+Reply], 0
0x140046497  mov     rsi, r8
0x14004649a  mov     rbp, rcx
0x14004649d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1400464a2  test    eax, eax
0x1400464a4  jz      short loc_1400464DA
0x1400464a6  lea     rdx, [rsp+78h+Reply]; Reply
0x1400464ab  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x1400464b3  mov     rcx, rbp; pAsync
0x1400464b6  call    cs:__imp_RpcAsyncCompleteCall
0x1400464bd  nop     dword ptr [rax+rax+00h]
0x1400464c2  lea     rdx, aTryingToDelete_7; "Trying to delete printer driver asynchr"...
0x1400464c9  lea     rcx, aTremotewinspoo_60; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x1400464d0  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400464d5  jmp     loc_1400465C1
0x1400464da  mov     r14d, 104h
0x1400464e0  test    rdi, rdi
0x1400464e3  jz      short loc_1400464FC
0x1400464e5  mov     edx, r14d; MaxCount
0x1400464e8  mov     rcx, rdi; Source
0x1400464eb  call    cs:__imp_wcsnlen
0x1400464f2  nop     dword ptr [rax+rax+00h]
0x1400464f7  cmp     rax, r14
0x1400464fa  jnb     short loc_14004653C
0x1400464fc  test    rsi, rsi
0x1400464ff  jz      short loc_140046518
0x140046501  mov     rdx, r14; MaxCount
0x140046504  mov     rcx, rsi; Source
0x140046507  call    cs:__imp_wcsnlen
0x14004650e  nop     dword ptr [rax+rax+00h]
0x140046513  cmp     rax, r14
0x140046516  jnb     short loc_14004653C
0x140046518  mov     rbx, [rsp+78h+Source]
0x140046520  test    rbx, rbx
0x140046523  jz      short loc_140046543
0x140046525  mov     rdx, r14; MaxCount
0x140046528  mov     rcx, rbx; Source
0x14004652b  call    cs:__imp_wcsnlen
0x140046532  nop     dword ptr [rax+rax+00h]
0x140046537  cmp     rax, r14
0x14004653a  jb      short loc_140046543
0x14004653c  mov     ebx, 80070057h
0x140046541  jmp     short loc_14004658E
0x140046543  lea     rax, [rsp+78h+Reply]
0x140046548  mov     r9, rbx
0x14004654b  mov     [rsp+78h+var_48], rax
0x140046550  lea     rcx, ?YDeletePrinterDriver@@YAKPEAG00W4Call_Route@@@Z; YDeletePrinterDriver(ushort *,ushort *,ushort *,Call_Route)
0x140046557  mov     r8, rdi
0x14004655a  mov     [rsp+78h+var_50], rbp
0x14004655f  mov     rdx, rsi
0x140046562  call    ?CreateInstance@?$TFunction4@PEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG00W4Call_Route@@@Z0001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction4<ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x140046567  mov     ebx, eax
0x140046569  test    eax, eax
0x14004656b  js      short loc_14004658E
0x14004656d  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x140046572  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140046579  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x14004657e  mov     rcx, [rsp+78h+Reply]; this
0x140046583  mov     ebx, eax
0x140046585  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x14004658a  test    ebx, ebx
0x14004658c  jns     short loc_1400465C1
0x14004658e  movzx   eax, bx
0x140046591  lea     rdx, [rsp+78h+Reply]; Reply
0x140046596  mov     rcx, rbp; pAsync
0x140046599  mov     dword ptr [rsp+78h+Reply], eax
0x14004659d  call    cs:__imp_RpcAsyncCompleteCall
0x1400465a4  nop     dword ptr [rax+rax+00h]
0x1400465a9  mov     r8d, dword ptr [rsp+78h+Reply]
0x1400465ae  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x1400465b5  lea     rcx, aTremotewinspoo_60; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x1400465bc  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400465c1  add     rsp, 50h
0x1400465c5  pop     r14
0x1400465c7  pop     rdi
0x1400465c8  pop     rsi
0x1400465c9  pop     rbp
0x1400465ca  pop     rbx
0x1400465cb  retn
```
