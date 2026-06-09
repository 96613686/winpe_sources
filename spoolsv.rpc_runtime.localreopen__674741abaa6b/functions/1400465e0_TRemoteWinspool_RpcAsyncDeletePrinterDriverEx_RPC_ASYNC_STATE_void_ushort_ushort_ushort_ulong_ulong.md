# TRemoteWinspool::RpcAsyncDeletePrinterDriverEx(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *,ulong,ulong)

- ea: `0x1400465e0`
- end: `0x14004673c`
- name: `?RpcAsyncDeletePrinterDriverEx@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22KK@Z`
- size: `348`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140007600`
- `0x1400087f0`
- `0x14001748c`
- `0x14004366c`
- `0x1400465e0`
- `0x14005e898`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004664b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140046667`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004668b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004664b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140046667`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004668b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046616`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004670c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046616`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004670c`

## string_xrefs

- `0x140046622`: `Trying to delete printer driver asynchronously in Windows Protected Print mode.`
- `0x140046629`: `TRemoteWinspool::RpcAsyncDeletePrinterDriverEx`
- `0x140046724`: `TRemoteWinspool::RpcAsyncDeletePrinterDriverEx`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncDeletePrinterDriverEx(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *Source,
        unsigned int a6,
        unsigned int a7)
{
  int v10; // ecx
  int v11; // ebx
  int Instance; // eax
  struct NThreadingLibrary::TWorkItem *Reply[7]; // [rsp+50h] [rbp-38h] BYREF

  Reply[0] = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    LODWORD(Reply[0]) = 50;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncDeletePrinterDriverEx",
      L"Trying to delete printer driver asynchronously in Windows Protected Print mode.");
    return;
  }
  if ( a4 && wcsnlen(a4, 0x104u) >= 0x104
    || a3 && wcsnlen(a3, 0x104u) >= 0x104
    || Source && wcsnlen(Source, 0x104u) >= 0x104 )
  {
    LOWORD(v11) = 87;
LABEL_12:
    LODWORD(Reply[0]) = (unsigned __int16)v11;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncDeletePrinterDriverEx",
      L"Failed.  Error %d.",
      LODWORD(Reply[0]));
    return;
  }
  Instance = TFunction6<unsigned short *,unsigned short *,unsigned short *,unsigned long,unsigned long,enum Call_Route>::CreateInstance(
               v10,
               (_DWORD)a3,
               (_DWORD)a4,
               (_DWORD)Source,
               a6,
               a7);
  LOWORD(v11) = Instance;
  if ( Instance < 0 )
    goto LABEL_12;
  v11 = NThreadingLibrary::TWorkCrew::AddItem(g_pWorkCrew, Reply[0]);
  NCoreLibrary::TReferenceCount::Release(Reply[0]);
  if ( v11 < 0 )
    goto LABEL_12;
}

```

## disassembly

```asm
0x1400465e0  push    rbx
0x1400465e2  push    rbp
0x1400465e3  push    rsi
0x1400465e4  push    rdi
0x1400465e5  push    r14
0x1400465e7  sub     rsp, 60h
0x1400465eb  mov     rdi, r9
0x1400465ee  mov     [rsp+88h+Reply], 0
0x1400465f7  mov     rsi, r8
0x1400465fa  mov     rbp, rcx
0x1400465fd  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140046602  test    eax, eax
0x140046604  jz      short loc_14004663A
0x140046606  lea     rdx, [rsp+88h+Reply]; Reply
0x14004660b  mov     dword ptr [rsp+88h+Reply], 32h ; '2'
0x140046613  mov     rcx, rbp; pAsync
0x140046616  call    cs:__imp_RpcAsyncCompleteCall
0x14004661d  nop     dword ptr [rax+rax+00h]
0x140046622  lea     rdx, aTryingToDelete_7; "Trying to delete printer driver asynchr"...
0x140046629  lea     rcx, aTremotewinspoo_54; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x140046630  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140046635  jmp     loc_140046730
0x14004663a  mov     r14d, 104h
0x140046640  test    rdi, rdi
0x140046643  jz      short loc_14004665C
0x140046645  mov     edx, r14d; MaxCount
0x140046648  mov     rcx, rdi; Source
0x14004664b  call    cs:__imp_wcsnlen
0x140046652  nop     dword ptr [rax+rax+00h]
0x140046657  cmp     rax, r14
0x14004665a  jnb     short loc_14004669C
0x14004665c  test    rsi, rsi
0x14004665f  jz      short loc_140046678
0x140046661  mov     rdx, r14; MaxCount
0x140046664  mov     rcx, rsi; Source
0x140046667  call    cs:__imp_wcsnlen
0x14004666e  nop     dword ptr [rax+rax+00h]
0x140046673  cmp     rax, r14
0x140046676  jnb     short loc_14004669C
0x140046678  mov     rbx, [rsp+88h+Source]
0x140046680  test    rbx, rbx
0x140046683  jz      short loc_1400466A3
0x140046685  mov     rdx, r14; MaxCount
0x140046688  mov     rcx, rbx; Source
0x14004668b  call    cs:__imp_wcsnlen
0x140046692  nop     dword ptr [rax+rax+00h]
0x140046697  cmp     rax, r14
0x14004669a  jb      short loc_1400466A3
0x14004669c  mov     ebx, 80070057h
0x1400466a1  jmp     short loc_1400466FD
0x1400466a3  lea     rax, [rsp+88h+Reply]
0x1400466a8  mov     r9, rbx
0x1400466ab  mov     [rsp+88h+var_48], rax
0x1400466b0  mov     r8, rdi
0x1400466b3  mov     eax, [rsp+88h+arg_30]
0x1400466ba  mov     rdx, rsi
0x1400466bd  mov     [rsp+88h+var_50], rbp
0x1400466c2  mov     [rsp+88h+var_60], eax
0x1400466c6  mov     eax, [rsp+88h+arg_28]
0x1400466cd  mov     [rsp+88h+var_68], eax
0x1400466d1  call    ?CreateInstance@?$TFunction6@PEAGPEAGPEAGKKW4Call_Route@@@@SAJP6AKPEAG00KKW4Call_Route@@@Z000KK1PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction6<ushort *,ushort *,ushort *,ulong,ulong,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,ulong,ulong,Call_Route),ushort *,ushort *,ushort *,ulong,ulong,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x1400466d6  mov     ebx, eax
0x1400466d8  test    eax, eax
0x1400466da  js      short loc_1400466FD
0x1400466dc  mov     rdx, [rsp+88h+Reply]; struct NThreadingLibrary::TWorkItem *
0x1400466e1  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x1400466e8  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x1400466ed  mov     rcx, [rsp+88h+Reply]; this
0x1400466f2  mov     ebx, eax
0x1400466f4  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x1400466f9  test    ebx, ebx
0x1400466fb  jns     short loc_140046730
0x1400466fd  movzx   eax, bx
0x140046700  lea     rdx, [rsp+88h+Reply]; Reply
0x140046705  mov     rcx, rbp; pAsync
0x140046708  mov     dword ptr [rsp+88h+Reply], eax
0x14004670c  call    cs:__imp_RpcAsyncCompleteCall
0x140046713  nop     dword ptr [rax+rax+00h]
0x140046718  mov     r8d, dword ptr [rsp+88h+Reply]
0x14004671d  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140046724  lea     rcx, aTremotewinspoo_54; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x14004672b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140046730  add     rsp, 60h
0x140046734  pop     r14
0x140046736  pop     rdi
0x140046737  pop     rsi
0x140046738  pop     rbp
0x140046739  pop     rbx
0x14004673a  retn
```
