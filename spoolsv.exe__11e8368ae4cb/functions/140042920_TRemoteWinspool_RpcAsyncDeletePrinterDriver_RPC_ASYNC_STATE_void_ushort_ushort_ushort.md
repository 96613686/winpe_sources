# TRemoteWinspool::RpcAsyncDeletePrinterDriver(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *)

- ea: `0x140042920`
- end: `0x140042a4e`
- name: `?RpcAsyncDeletePrinterDriver@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22@Z`
- size: `302`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140006b30`
- `0x140007c00`
- `0x1400160a0`
- `0x14003ed74`
- `0x140042920`
- `0x1400590f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042985`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004299b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400429b9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042985`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004299b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400429b9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042956`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042a25`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042956`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042a25`

## string_xrefs

- `0x14004295c`: `Trying to delete printer driver asynchronously in Windows Protected Print mode.`
- `0x140042963`: `TRemoteWinspool::RpcAsyncDeletePrinterDriver`
- `0x140042a37`: `TRemoteWinspool::RpcAsyncDeletePrinterDriver`

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
0x140042920  push    rbx
0x140042922  push    rbp
0x140042923  push    rsi
0x140042924  push    rdi
0x140042925  push    r14
0x140042927  sub     rsp, 50h
0x14004292b  mov     rdi, r9
0x14004292e  mov     [rsp+78h+Reply], 0
0x140042937  mov     rsi, r8
0x14004293a  mov     rbp, rcx
0x14004293d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140042942  test    eax, eax
0x140042944  jz      short loc_140042974
0x140042946  lea     rdx, [rsp+78h+Reply]; Reply
0x14004294b  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x140042953  mov     rcx, rbp; pAsync
0x140042956  call    cs:__imp_RpcAsyncCompleteCall
0x14004295c  lea     rdx, aTryingToDelete_7; "Trying to delete printer driver asynchr"...
0x140042963  lea     rcx, aTremotewinspoo_60; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x14004296a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004296f  jmp     loc_140042A43
0x140042974  mov     r14d, 104h
0x14004297a  test    rdi, rdi
0x14004297d  jz      short loc_140042990
0x14004297f  mov     edx, r14d; MaxCount
0x140042982  mov     rcx, rdi; Source
0x140042985  call    cs:__imp_wcsnlen
0x14004298b  cmp     rax, r14
0x14004298e  jnb     short loc_1400429C4
0x140042990  test    rsi, rsi
0x140042993  jz      short loc_1400429A6
0x140042995  mov     rdx, r14; MaxCount
0x140042998  mov     rcx, rsi; Source
0x14004299b  call    cs:__imp_wcsnlen
0x1400429a1  cmp     rax, r14
0x1400429a4  jnb     short loc_1400429C4
0x1400429a6  mov     rbx, [rsp+78h+Source]
0x1400429ae  test    rbx, rbx
0x1400429b1  jz      short loc_1400429CB
0x1400429b3  mov     rdx, r14; MaxCount
0x1400429b6  mov     rcx, rbx; Source
0x1400429b9  call    cs:__imp_wcsnlen
0x1400429bf  cmp     rax, r14
0x1400429c2  jb      short loc_1400429CB
0x1400429c4  mov     ebx, 80070057h
0x1400429c9  jmp     short loc_140042A16
0x1400429cb  lea     rax, [rsp+78h+Reply]
0x1400429d0  mov     r9, rbx
0x1400429d3  mov     [rsp+78h+var_48], rax
0x1400429d8  lea     rcx, ?YDeletePrinterDriver@@YAKPEAG00W4Call_Route@@@Z; YDeletePrinterDriver(ushort *,ushort *,ushort *,Call_Route)
0x1400429df  mov     r8, rdi
0x1400429e2  mov     [rsp+78h+var_50], rbp
0x1400429e7  mov     rdx, rsi
0x1400429ea  call    ?CreateInstance@?$TFunction4@PEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG00W4Call_Route@@@Z0001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction4<ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x1400429ef  mov     ebx, eax
0x1400429f1  test    eax, eax
0x1400429f3  js      short loc_140042A16
0x1400429f5  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x1400429fa  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140042a01  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140042a06  mov     rcx, [rsp+78h+Reply]; this
0x140042a0b  mov     ebx, eax
0x140042a0d  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140042a12  test    ebx, ebx
0x140042a14  jns     short loc_140042A43
0x140042a16  movzx   eax, bx
0x140042a19  lea     rdx, [rsp+78h+Reply]; Reply
0x140042a1e  mov     rcx, rbp; pAsync
0x140042a21  mov     dword ptr [rsp+78h+Reply], eax
0x140042a25  call    cs:__imp_RpcAsyncCompleteCall
0x140042a2b  mov     r8d, dword ptr [rsp+78h+Reply]
0x140042a30  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140042a37  lea     rcx, aTremotewinspoo_60; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x140042a3e  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140042a43  add     rsp, 50h
0x140042a47  pop     r14
0x140042a49  pop     rdi
0x140042a4a  pop     rsi
0x140042a4b  pop     rbp
0x140042a4c  pop     rbx
0x140042a4d  retn
```
