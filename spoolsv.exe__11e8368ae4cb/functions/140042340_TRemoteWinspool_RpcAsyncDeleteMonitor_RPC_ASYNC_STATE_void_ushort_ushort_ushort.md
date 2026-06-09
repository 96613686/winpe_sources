# TRemoteWinspool::RpcAsyncDeleteMonitor(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *)

- ea: `0x140042340`
- end: `0x14004246e`
- name: `?RpcAsyncDeleteMonitor@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22@Z`
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
- `0x140042340`
- `0x1400590f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400423a5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400423bb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400423d9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400423a5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400423bb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400423d9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042376`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042445`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042376`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042445`

## string_xrefs

- `0x14004237c`: `Trying to delete monitor asynchronously in Windows Protected Print mode.`
- `0x140042383`: `TRemoteWinspool::RpcAsyncDeleteMonitor`
- `0x140042457`: `TRemoteWinspool::RpcAsyncDeleteMonitor`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncDeleteMonitor(
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
      "TRemoteWinspool::RpcAsyncDeleteMonitor",
      L"Trying to delete monitor asynchronously in Windows Protected Print mode.");
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
      "TRemoteWinspool::RpcAsyncDeleteMonitor",
      L"Failed.  Error %d.",
      LODWORD(Reply[0]));
    return;
  }
  Instance = TFunction4<unsigned short *,unsigned short *,unsigned short *,enum Call_Route>::CreateInstance(
               (unsigned int)&YDeleteMonitor,
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
0x140042340  push    rbx
0x140042342  push    rbp
0x140042343  push    rsi
0x140042344  push    rdi
0x140042345  push    r14
0x140042347  sub     rsp, 50h
0x14004234b  mov     rdi, r9
0x14004234e  mov     [rsp+78h+Reply], 0
0x140042357  mov     rsi, r8
0x14004235a  mov     rbp, rcx
0x14004235d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140042362  test    eax, eax
0x140042364  jz      short loc_140042394
0x140042366  lea     rdx, [rsp+78h+Reply]; Reply
0x14004236b  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x140042373  mov     rcx, rbp; pAsync
0x140042376  call    cs:__imp_RpcAsyncCompleteCall
0x14004237c  lea     rdx, aTryingToDelete_9; "Trying to delete monitor asynchronously"...
0x140042383  lea     rcx, aTremotewinspoo_4; "TRemoteWinspool::RpcAsyncDeleteMonitor"
0x14004238a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004238f  jmp     loc_140042463
0x140042394  mov     r14d, 104h
0x14004239a  test    rdi, rdi
0x14004239d  jz      short loc_1400423B0
0x14004239f  mov     edx, r14d; MaxCount
0x1400423a2  mov     rcx, rdi; Source
0x1400423a5  call    cs:__imp_wcsnlen
0x1400423ab  cmp     rax, r14
0x1400423ae  jnb     short loc_1400423E4
0x1400423b0  test    rsi, rsi
0x1400423b3  jz      short loc_1400423C6
0x1400423b5  mov     rdx, r14; MaxCount
0x1400423b8  mov     rcx, rsi; Source
0x1400423bb  call    cs:__imp_wcsnlen
0x1400423c1  cmp     rax, r14
0x1400423c4  jnb     short loc_1400423E4
0x1400423c6  mov     rbx, [rsp+78h+Source]
0x1400423ce  test    rbx, rbx
0x1400423d1  jz      short loc_1400423EB
0x1400423d3  mov     rdx, r14; MaxCount
0x1400423d6  mov     rcx, rbx; Source
0x1400423d9  call    cs:__imp_wcsnlen
0x1400423df  cmp     rax, r14
0x1400423e2  jb      short loc_1400423EB
0x1400423e4  mov     ebx, 80070057h
0x1400423e9  jmp     short loc_140042436
0x1400423eb  lea     rax, [rsp+78h+Reply]
0x1400423f0  mov     r9, rbx
0x1400423f3  mov     [rsp+78h+var_48], rax
0x1400423f8  lea     rcx, ?YDeleteMonitor@@YAKPEAG00W4Call_Route@@@Z; YDeleteMonitor(ushort *,ushort *,ushort *,Call_Route)
0x1400423ff  mov     r8, rdi
0x140042402  mov     [rsp+78h+var_50], rbp
0x140042407  mov     rdx, rsi
0x14004240a  call    ?CreateInstance@?$TFunction4@PEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG00W4Call_Route@@@Z0001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction4<ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x14004240f  mov     ebx, eax
0x140042411  test    eax, eax
0x140042413  js      short loc_140042436
0x140042415  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x14004241a  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140042421  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140042426  mov     rcx, [rsp+78h+Reply]; this
0x14004242b  mov     ebx, eax
0x14004242d  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140042432  test    ebx, ebx
0x140042434  jns     short loc_140042463
0x140042436  movzx   eax, bx
0x140042439  lea     rdx, [rsp+78h+Reply]; Reply
0x14004243e  mov     rcx, rbp; pAsync
0x140042441  mov     dword ptr [rsp+78h+Reply], eax
0x140042445  call    cs:__imp_RpcAsyncCompleteCall
0x14004244b  mov     r8d, dword ptr [rsp+78h+Reply]
0x140042450  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140042457  lea     rcx, aTremotewinspoo_4; "TRemoteWinspool::RpcAsyncDeleteMonitor"
0x14004245e  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140042463  add     rsp, 50h
0x140042467  pop     r14
0x140042469  pop     rdi
0x14004246a  pop     rsi
0x14004246b  pop     rbp
0x14004246c  pop     rbx
0x14004246d  retn
```
