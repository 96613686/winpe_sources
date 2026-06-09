# TRemoteWinspool::RpcAsyncDeletePrinterDriverEx(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *,ulong,ulong)

- ea: `0x140042a60`
- end: `0x140042b9d`
- name: `?RpcAsyncDeletePrinterDriverEx@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22KK@Z`
- size: `317`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140006b30`
- `0x140007c00`
- `0x1400160a0`
- `0x14003fccc`
- `0x140042a60`
- `0x1400590f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042ac5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042adb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042af9`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042ac5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042adb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140042af9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042a96`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042b74`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042a96`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042b74`

## string_xrefs

- `0x140042a9c`: `Trying to delete printer driver asynchronously in Windows Protected Print mode.`
- `0x140042aa3`: `TRemoteWinspool::RpcAsyncDeletePrinterDriverEx`
- `0x140042b86`: `TRemoteWinspool::RpcAsyncDeletePrinterDriverEx`

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
0x140042a60  push    rbx
0x140042a62  push    rbp
0x140042a63  push    rsi
0x140042a64  push    rdi
0x140042a65  push    r14
0x140042a67  sub     rsp, 60h
0x140042a6b  mov     rdi, r9
0x140042a6e  mov     [rsp+88h+Reply], 0
0x140042a77  mov     rsi, r8
0x140042a7a  mov     rbp, rcx
0x140042a7d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140042a82  test    eax, eax
0x140042a84  jz      short loc_140042AB4
0x140042a86  lea     rdx, [rsp+88h+Reply]; Reply
0x140042a8b  mov     dword ptr [rsp+88h+Reply], 32h ; '2'
0x140042a93  mov     rcx, rbp; pAsync
0x140042a96  call    cs:__imp_RpcAsyncCompleteCall
0x140042a9c  lea     rdx, aTryingToDelete_7; "Trying to delete printer driver asynchr"...
0x140042aa3  lea     rcx, aTremotewinspoo_54; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x140042aaa  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140042aaf  jmp     loc_140042B92
0x140042ab4  mov     r14d, 104h
0x140042aba  test    rdi, rdi
0x140042abd  jz      short loc_140042AD0
0x140042abf  mov     edx, r14d; MaxCount
0x140042ac2  mov     rcx, rdi; Source
0x140042ac5  call    cs:__imp_wcsnlen
0x140042acb  cmp     rax, r14
0x140042ace  jnb     short loc_140042B04
0x140042ad0  test    rsi, rsi
0x140042ad3  jz      short loc_140042AE6
0x140042ad5  mov     rdx, r14; MaxCount
0x140042ad8  mov     rcx, rsi; Source
0x140042adb  call    cs:__imp_wcsnlen
0x140042ae1  cmp     rax, r14
0x140042ae4  jnb     short loc_140042B04
0x140042ae6  mov     rbx, [rsp+88h+Source]
0x140042aee  test    rbx, rbx
0x140042af1  jz      short loc_140042B0B
0x140042af3  mov     rdx, r14; MaxCount
0x140042af6  mov     rcx, rbx; Source
0x140042af9  call    cs:__imp_wcsnlen
0x140042aff  cmp     rax, r14
0x140042b02  jb      short loc_140042B0B
0x140042b04  mov     ebx, 80070057h
0x140042b09  jmp     short loc_140042B65
0x140042b0b  lea     rax, [rsp+88h+Reply]
0x140042b10  mov     r9, rbx
0x140042b13  mov     [rsp+88h+var_48], rax
0x140042b18  mov     r8, rdi
0x140042b1b  mov     eax, [rsp+88h+arg_30]
0x140042b22  mov     rdx, rsi
0x140042b25  mov     [rsp+88h+var_50], rbp
0x140042b2a  mov     [rsp+88h+var_60], eax
0x140042b2e  mov     eax, [rsp+88h+arg_28]
0x140042b35  mov     [rsp+88h+var_68], eax
0x140042b39  call    ?CreateInstance@?$TFunction6@PEAGPEAGPEAGKKW4Call_Route@@@@SAJP6AKPEAG00KKW4Call_Route@@@Z000KK1PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction6<ushort *,ushort *,ushort *,ulong,ulong,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,ulong,ulong,Call_Route),ushort *,ushort *,ushort *,ulong,ulong,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x140042b3e  mov     ebx, eax
0x140042b40  test    eax, eax
0x140042b42  js      short loc_140042B65
0x140042b44  mov     rdx, [rsp+88h+Reply]; struct NThreadingLibrary::TWorkItem *
0x140042b49  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140042b50  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140042b55  mov     rcx, [rsp+88h+Reply]; this
0x140042b5a  mov     ebx, eax
0x140042b5c  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140042b61  test    ebx, ebx
0x140042b63  jns     short loc_140042B92
0x140042b65  movzx   eax, bx
0x140042b68  lea     rdx, [rsp+88h+Reply]; Reply
0x140042b6d  mov     rcx, rbp; pAsync
0x140042b70  mov     dword ptr [rsp+88h+Reply], eax
0x140042b74  call    cs:__imp_RpcAsyncCompleteCall
0x140042b7a  mov     r8d, dword ptr [rsp+88h+Reply]
0x140042b7f  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140042b86  lea     rcx, aTremotewinspoo_54; "TRemoteWinspool::RpcAsyncDeletePrinterD"...
0x140042b8d  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140042b92  add     rsp, 60h
0x140042b96  pop     r14
0x140042b98  pop     rdi
0x140042b99  pop     rsi
0x140042b9a  pop     rbp
0x140042b9b  pop     rbx
0x140042b9c  retn
```
