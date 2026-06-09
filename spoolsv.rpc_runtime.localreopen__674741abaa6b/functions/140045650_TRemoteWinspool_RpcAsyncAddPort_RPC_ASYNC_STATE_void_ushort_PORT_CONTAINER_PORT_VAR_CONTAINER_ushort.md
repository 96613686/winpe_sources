# TRemoteWinspool::RpcAsyncAddPort(_RPC_ASYNC_STATE *,void *,ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *)

- ea: `0x140045650`
- end: `0x140045784`
- name: `?RpcAsyncAddPort@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAGPEAU_PORT_CONTAINER@@PEAU_PORT_VAR_CONTAINER@@2@Z`
- size: `308`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, struct _PORT_CONTAINER *@<r9>, struct _PORT_VAR_CONTAINER *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007600`
- `0x1400087f0`
- `0x14001748c`
- `0x140042fd4`
- `0x140045650`
- `0x14005e898`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400456bb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400456df`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400456bb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400456df`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045686`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045754`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045686`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045754`

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
0x140045650  push    rbx
0x140045652  push    rbp
0x140045653  push    rsi
0x140045654  push    rdi
0x140045655  push    r14
0x140045657  sub     rsp, 50h
0x14004565b  mov     rbp, r9
0x14004565e  mov     [rsp+78h+Reply], 0
0x140045667  mov     rdi, r8
0x14004566a  mov     rsi, rcx
0x14004566d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140045672  test    eax, eax
0x140045674  jz      short loc_1400456AA
0x140045676  lea     rdx, [rsp+78h+Reply]; Reply
0x14004567b  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x140045683  mov     rcx, rsi; pAsync
0x140045686  call    cs:__imp_RpcAsyncCompleteCall
0x14004568d  nop     dword ptr [rax+rax+00h]
0x140045692  lea     rdx, aTryingToAddAPo_0; "Trying to add a port asynchronously in "...
0x140045699  lea     rcx, aTremotewinspoo_32; "TRemoteWinspool::RpcAsyncAddPort"
0x1400456a0  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400456a5  jmp     loc_140045778
0x1400456aa  mov     r14d, 104h
0x1400456b0  test    rdi, rdi
0x1400456b3  jz      short loc_1400456CC
0x1400456b5  mov     edx, r14d; MaxCount
0x1400456b8  mov     rcx, rdi; Source
0x1400456bb  call    cs:__imp_wcsnlen
0x1400456c2  nop     dword ptr [rax+rax+00h]
0x1400456c7  cmp     rax, r14
0x1400456ca  jnb     short loc_1400456F0
0x1400456cc  mov     rbx, [rsp+78h+Source]
0x1400456d4  test    rbx, rbx
0x1400456d7  jz      short loc_1400456F7
0x1400456d9  mov     rdx, r14; MaxCount
0x1400456dc  mov     rcx, rbx; Source
0x1400456df  call    cs:__imp_wcsnlen
0x1400456e6  nop     dword ptr [rax+rax+00h]
0x1400456eb  cmp     rax, r14
0x1400456ee  jb      short loc_1400456F7
0x1400456f0  mov     ebx, 80070057h
0x1400456f5  jmp     short loc_140045745
0x1400456f7  mov     r9, [rsp+78h+arg_20]
0x1400456ff  lea     rax, [rsp+78h+Reply]
0x140045704  mov     [rsp+78h+var_40], rax
0x140045709  mov     r8, rbp
0x14004570c  mov     [rsp+78h+var_48], rsi
0x140045711  mov     rdx, rdi
0x140045714  mov     [rsp+78h+var_58], rbx
0x140045719  call    ?CreateInstance@?$TFunction5@PEAGPEAU_PORT_CONTAINER@@PEAU_PORT_VAR_CONTAINER@@PEAGW4Call_Route@@@@SAJP6AKPEAGPEAU_PORT_CONTAINER@@PEAU_PORT_VAR_CONTAINER@@0W4Call_Route@@@Z01203PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction5<ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *,Call_Route),ushort *,_PORT_CONTAINER *,_PORT_VAR_CONTAINER *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x14004571e  mov     ebx, eax
0x140045720  test    eax, eax
0x140045722  js      short loc_140045745
0x140045724  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x140045729  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140045730  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140045735  mov     rcx, [rsp+78h+Reply]; this
0x14004573a  mov     ebx, eax
0x14004573c  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140045741  test    ebx, ebx
0x140045743  jns     short loc_140045778
0x140045745  movzx   eax, bx
0x140045748  lea     rdx, [rsp+78h+Reply]; Reply
0x14004574d  mov     rcx, rsi; pAsync
0x140045750  mov     dword ptr [rsp+78h+Reply], eax
0x140045754  call    cs:__imp_RpcAsyncCompleteCall
0x14004575b  nop     dword ptr [rax+rax+00h]
0x140045760  mov     r8d, dword ptr [rsp+78h+Reply]
0x140045765  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x14004576c  lea     rcx, aTremotewinspoo_32; "TRemoteWinspool::RpcAsyncAddPort"
0x140045773  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140045778  add     rsp, 50h
0x14004577c  pop     r14
0x14004577e  pop     rdi
0x14004577f  pop     rsi
0x140045780  pop     rbp
0x140045781  pop     rbx
0x140045782  retn
```
