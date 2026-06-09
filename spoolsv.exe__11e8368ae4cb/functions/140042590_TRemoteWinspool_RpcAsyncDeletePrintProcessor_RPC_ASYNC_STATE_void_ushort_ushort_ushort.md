# TRemoteWinspool::RpcAsyncDeletePrintProcessor(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *)

- ea: `0x140042590`
- end: `0x1400426be`
- name: `?RpcAsyncDeletePrintProcessor@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22@Z`
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
- `0x140042590`
- `0x1400590f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400425f5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004260b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042629`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400425f5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004260b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042629`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400425c6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042695`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400425c6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042695`

## string_xrefs

- `0x1400425cc`: `Trying to delete print processor asynchronously in Windows Protected Print mode.`
- `0x1400425d3`: `TRemoteWinspool::RpcAsyncDeletePrintProcessor`
- `0x1400426a7`: `TRemoteWinspool::RpcAsyncDeletePrintProcessor`

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
0x140042590  push    rbx
0x140042592  push    rbp
0x140042593  push    rsi
0x140042594  push    rdi
0x140042595  push    r14
0x140042597  sub     rsp, 50h
0x14004259b  mov     rdi, r9
0x14004259e  mov     [rsp+78h+Reply], 0
0x1400425a7  mov     rsi, r8
0x1400425aa  mov     rbp, rcx
0x1400425ad  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1400425b2  test    eax, eax
0x1400425b4  jz      short loc_1400425E4
0x1400425b6  lea     rdx, [rsp+78h+Reply]; Reply
0x1400425bb  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x1400425c3  mov     rcx, rbp; pAsync
0x1400425c6  call    cs:__imp_RpcAsyncCompleteCall
0x1400425cc  lea     rdx, aTryingToDelete_3; "Trying to delete print processor asynch"...
0x1400425d3  lea     rcx, aTremotewinspoo_17; "TRemoteWinspool::RpcAsyncDeletePrintPro"...
0x1400425da  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400425df  jmp     loc_1400426B3
0x1400425e4  mov     r14d, 104h
0x1400425ea  test    rdi, rdi
0x1400425ed  jz      short loc_140042600
0x1400425ef  mov     edx, r14d; MaxCount
0x1400425f2  mov     rcx, rdi; Source
0x1400425f5  call    cs:__imp_wcsnlen
0x1400425fb  cmp     rax, r14
0x1400425fe  jnb     short loc_140042634
0x140042600  test    rsi, rsi
0x140042603  jz      short loc_140042616
0x140042605  mov     rdx, r14; MaxCount
0x140042608  mov     rcx, rsi; Source
0x14004260b  call    cs:__imp_wcsnlen
0x140042611  cmp     rax, r14
0x140042614  jnb     short loc_140042634
0x140042616  mov     rbx, [rsp+78h+Source]
0x14004261e  test    rbx, rbx
0x140042621  jz      short loc_14004263B
0x140042623  mov     rdx, r14; MaxCount
0x140042626  mov     rcx, rbx; Source
0x140042629  call    cs:__imp_wcsnlen
0x14004262f  cmp     rax, r14
0x140042632  jb      short loc_14004263B
0x140042634  mov     ebx, 80070057h
0x140042639  jmp     short loc_140042686
0x14004263b  lea     rax, [rsp+78h+Reply]
0x140042640  mov     r9, rbx
0x140042643  mov     [rsp+78h+var_48], rax
0x140042648  lea     rcx, ?YDeletePrintProcessor@@YAKPEAG00W4Call_Route@@@Z; YDeletePrintProcessor(ushort *,ushort *,ushort *,Call_Route)
0x14004264f  mov     r8, rdi
0x140042652  mov     [rsp+78h+var_50], rbp
0x140042657  mov     rdx, rsi
0x14004265a  call    ?CreateInstance@?$TFunction4@PEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG00W4Call_Route@@@Z0001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction4<ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x14004265f  mov     ebx, eax
0x140042661  test    eax, eax
0x140042663  js      short loc_140042686
0x140042665  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x14004266a  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140042671  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140042676  mov     rcx, [rsp+78h+Reply]; this
0x14004267b  mov     ebx, eax
0x14004267d  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140042682  test    ebx, ebx
0x140042684  jns     short loc_1400426B3
0x140042686  movzx   eax, bx
0x140042689  lea     rdx, [rsp+78h+Reply]; Reply
0x14004268e  mov     rcx, rbp; pAsync
0x140042691  mov     dword ptr [rsp+78h+Reply], eax
0x140042695  call    cs:__imp_RpcAsyncCompleteCall
0x14004269b  mov     r8d, dword ptr [rsp+78h+Reply]
0x1400426a0  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x1400426a7  lea     rcx, aTremotewinspoo_17; "TRemoteWinspool::RpcAsyncDeletePrintPro"...
0x1400426ae  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400426b3  add     rsp, 50h
0x1400426b7  pop     r14
0x1400426b9  pop     rdi
0x1400426ba  pop     rsi
0x1400426bb  pop     rbp
0x1400426bc  pop     rbx
0x1400426bd  retn
```
