# TRemoteWinspool::RpcAsyncAddPort(_RPC_ASYNC_STATE *,void *,ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *)

- ea: `0x140041c20`
- end: `0x140041d3b`
- name: `?RpcAsyncAddPort@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAGPEAU_PORT_CONTAINER@@PEAU_PORT_VAR_CONTAINER@@2@Z`
- size: `283`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, struct _PORT_CONTAINER *@<r9>, struct _PORT_VAR_CONTAINER *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006b30`
- `0x140007c00`
- `0x1400160a0`
- `0x14003f640`
- `0x140041c20`
- `0x1400590f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041c85`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041ca3`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041c85`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041ca3`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041c56`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041d12`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041c56`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041d12`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncAddPort(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        struct _PORT_CONTAINER *a4,
        struct _PORT_VAR_CONTAINER *a5,
        unsigned __int16 *Source)
{
  int v6; // ebp
  int v9; // ecx
  int v10; // ebx
  int Instance; // eax
  struct NThreadingLibrary::TWorkItem *Reply[7]; // [rsp+40h] [rbp-38h] BYREF

  v6 = (int)a4;
  Reply[0] = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    LODWORD(Reply[0]) = 50;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncAddPort",
      L"Trying to add a port asynchronously in Windows Protected Print mode.");
    return;
  }
  if ( a3 && wcsnlen(a3, 0x104u) >= 0x104 || Source && wcsnlen(Source, 0x104u) >= 0x104 )
  {
    LOWORD(v10) = 87;
LABEL_10:
    LODWORD(Reply[0]) = (unsigned __int16)v10;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncAddPort",
      L"Failed.  Error %d.",
      LODWORD(Reply[0]));
    return;
  }
  Instance = TFunction5<unsigned short *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,unsigned short *,enum Call_Route>::CreateInstance(
               v9,
               (_DWORD)a3,
               v6,
               (_DWORD)a5,
               (__int64)Source);
  LOWORD(v10) = Instance;
  if ( Instance < 0 )
    goto LABEL_10;
  v10 = NThreadingLibrary::TWorkCrew::AddItem(g_pWorkCrew, Reply[0]);
  NCoreLibrary::TReferenceCount::Release(Reply[0]);
  if ( v10 < 0 )
    goto LABEL_10;
}

```

## disassembly

```asm
0x140041c20  push    rbx
0x140041c22  push    rbp
0x140041c23  push    rsi
0x140041c24  push    rdi
0x140041c25  push    r14
0x140041c27  sub     rsp, 50h
0x140041c2b  mov     rbp, r9
0x140041c2e  mov     [rsp+78h+Reply], 0
0x140041c37  mov     rdi, r8
0x140041c3a  mov     rsi, rcx
0x140041c3d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140041c42  test    eax, eax
0x140041c44  jz      short loc_140041C74
0x140041c46  lea     rdx, [rsp+78h+Reply]; Reply
0x140041c4b  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x140041c53  mov     rcx, rsi; pAsync
0x140041c56  call    cs:__imp_RpcAsyncCompleteCall
0x140041c5c  lea     rdx, aTryingToAddAPo_0; "Trying to add a port asynchronously in "...
0x140041c63  lea     rcx, aTremotewinspoo_32; "TRemoteWinspool::RpcAsyncAddPort"
0x140041c6a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140041c6f  jmp     loc_140041D30
0x140041c74  mov     r14d, 104h
0x140041c7a  test    rdi, rdi
0x140041c7d  jz      short loc_140041C90
0x140041c7f  mov     edx, r14d; MaxCount
0x140041c82  mov     rcx, rdi; Source
0x140041c85  call    cs:__imp_wcsnlen
0x140041c8b  cmp     rax, r14
0x140041c8e  jnb     short loc_140041CAE
0x140041c90  mov     rbx, [rsp+78h+Source]
0x140041c98  test    rbx, rbx
0x140041c9b  jz      short loc_140041CB5
0x140041c9d  mov     rdx, r14; MaxCount
0x140041ca0  mov     rcx, rbx; Source
0x140041ca3  call    cs:__imp_wcsnlen
0x140041ca9  cmp     rax, r14
0x140041cac  jb      short loc_140041CB5
0x140041cae  mov     ebx, 80070057h
0x140041cb3  jmp     short loc_140041D03
0x140041cb5  mov     r9, [rsp+78h+arg_20]
0x140041cbd  lea     rax, [rsp+78h+Reply]
0x140041cc2  mov     [rsp+78h+var_40], rax
0x140041cc7  mov     r8, rbp
0x140041cca  mov     [rsp+78h+var_48], rsi
0x140041ccf  mov     rdx, rdi
0x140041cd2  mov     [rsp+78h+var_58], rbx
0x140041cd7  call    ?CreateInstance@?$TFunction5@PEAGPEAU_PORT_CONTAINER@@PEAU_PORT_VAR_CONTAINER@@PEAGW4Call_Route@@@@SAJP6AKPEAGPEAU_PORT_CONTAINER@@PEAU_PORT_VAR_CONTAINER@@0W4Call_Route@@@Z01203PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction5<ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *,Call_Route),ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x140041cdc  mov     ebx, eax
0x140041cde  test    eax, eax
0x140041ce0  js      short loc_140041D03
0x140041ce2  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x140041ce7  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140041cee  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140041cf3  mov     rcx, [rsp+78h+Reply]; this
0x140041cf8  mov     ebx, eax
0x140041cfa  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140041cff  test    ebx, ebx
0x140041d01  jns     short loc_140041D30
0x140041d03  movzx   eax, bx
0x140041d06  lea     rdx, [rsp+78h+Reply]; Reply
0x140041d0b  mov     rcx, rsi; pAsync
0x140041d0e  mov     dword ptr [rsp+78h+Reply], eax
0x140041d12  call    cs:__imp_RpcAsyncCompleteCall
0x140041d18  mov     r8d, dword ptr [rsp+78h+Reply]
0x140041d1d  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140041d24  lea     rcx, aTremotewinspoo_32; "TRemoteWinspool::RpcAsyncAddPort"
0x140041d2b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140041d30  add     rsp, 50h
0x140041d34  pop     r14
0x140041d36  pop     rdi
0x140041d37  pop     rsi
0x140041d38  pop     rbp
0x140041d39  pop     rbx
0x140041d3a  retn
```
