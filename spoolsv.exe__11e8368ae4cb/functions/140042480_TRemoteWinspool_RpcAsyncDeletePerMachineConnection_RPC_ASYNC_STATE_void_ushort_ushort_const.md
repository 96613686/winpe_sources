# TRemoteWinspool::RpcAsyncDeletePerMachineConnection(_RPC_ASYNC_STATE *,void *,ushort *,ushort const *)

- ea: `0x140042480`
- end: `0x14004258a`
- name: `?RpcAsyncDeletePerMachineConnection@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAGPEBG@Z`
- size: `266`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140006b30`
- `0x140007c00`
- `0x140015fdc`
- `0x1400160a0`
- `0x14003e774`
- `0x140042480`
- `0x1400590f0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1400424ba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042531`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042574`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400424ba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042531`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140042574`

## string_xrefs

- `0x140042551`: `RestrictDriverInstallationToAdministrators policy is set and we cannot confirm this user is an Administrator. Return ERROR_ACCESS_DENIED.`
- `0x1400424c0`: `Trying to delete per machine connection asynchronously in Windows Protected Print mode.`
- `0x1400424c7`: `TRemoteWinspool::RpcAsyncDeletePerMachineConnection`
- `0x140042543`: `TRemoteWinspool::RpcAsyncDeletePerMachineConnection`
- `0x140042558`: `TRemoteWinspool::RpcAsyncDeletePerMachineConnection`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncDeletePerMachineConnection(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v4; // edi
  int v5; // esi
  int v7; // ecx
  int v8; // r9d
  int Instance; // eax
  struct NThreadingLibrary::TWorkItem *Reply[3]; // [rsp+30h] [rbp-18h] BYREF

  v4 = (int)a4;
  Reply[0] = 0;
  v5 = (int)a3;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    LODWORD(Reply[0]) = 50;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncDeletePerMachineConnection",
      L"Trying to delete per machine connection asynchronously in Windows Protected Print mode.");
  }
  else if ( YRestrictDriverInstallationToAdministrators() )
  {
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncDeletePerMachineConnection",
      L"RestrictDriverInstallationToAdministrators policy is set and we cannot confirm this user is an Administrator. Retu"
       "rn ERROR_ACCESS_DENIED.");
    LODWORD(Reply[0]) = 5;
    RpcAsyncCompleteCall(pAsync, Reply);
  }
  else
  {
    Instance = TFunction3<unsigned short *,unsigned short const *,enum Call_Route>::CreateInstance(
                 v7,
                 v5,
                 v4,
                 v8,
                 (__int64)pAsync,
                 (__int64)Reply);
    LOWORD(v4) = Instance;
    if ( Instance < 0
      || (v4 = NThreadingLibrary::TWorkCrew::AddItem(g_pWorkCrew, Reply[0]),
          NCoreLibrary::TReferenceCount::Release(Reply[0]),
          v4 < 0) )
    {
      LODWORD(Reply[0]) = (unsigned __int16)v4;
      RpcAsyncCompleteCall(pAsync, Reply);
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "TRemoteWinspool::RpcAsyncDeletePerMachineConnection",
        L"Failed.  Error %d.",
        LODWORD(Reply[0]));
    }
  }
}

```

## disassembly

```asm
0x140042480  mov     [rsp+arg_0], rbx
0x140042485  mov     [rsp+arg_8], rsi
0x14004248a  push    rdi
0x14004248b  sub     rsp, 40h
0x14004248f  mov     rdi, r9
0x140042492  mov     [rsp+48h+Reply], 0
0x14004249b  mov     rsi, r8
0x14004249e  mov     rbx, rcx
0x1400424a1  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1400424a6  test    eax, eax
0x1400424a8  jz      short loc_1400424D8
0x1400424aa  lea     rdx, [rsp+48h+Reply]; Reply
0x1400424af  mov     dword ptr [rsp+48h+Reply], 32h ; '2'
0x1400424b7  mov     rcx, rbx; pAsync
0x1400424ba  call    cs:__imp_RpcAsyncCompleteCall
0x1400424c0  lea     rdx, aTryingToDelete_5; "Trying to delete per machine connection"...
0x1400424c7  lea     rcx, aTremotewinspoo_51; "TRemoteWinspool::RpcAsyncDeletePerMachi"...
0x1400424ce  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400424d3  jmp     loc_14004257A
0x1400424d8  call    ?YRestrictDriverInstallationToAdministrators@@YAHXZ; YRestrictDriverInstallationToAdministrators(void)
0x1400424dd  test    eax, eax
0x1400424df  jnz     short loc_140042551
0x1400424e1  lea     rax, [rsp+48h+Reply]
0x1400424e6  mov     r8, rdi
0x1400424e9  mov     [rsp+48h+var_20], rax
0x1400424ee  mov     rdx, rsi
0x1400424f1  mov     [rsp+48h+var_28], rbx
0x1400424f6  call    ?CreateInstance@?$TFunction3@PEAGPEBGW4Call_Route@@@@SAJP6AKPEAGPEBGW4Call_Route@@@Z012PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction3<ushort *,ushort const *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort const *,Call_Route),ushort *,ushort const *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x1400424fb  mov     edi, eax
0x1400424fd  test    eax, eax
0x1400424ff  js      short loc_140042522
0x140042501  mov     rdx, [rsp+48h+Reply]; struct NThreadingLibrary::TWorkItem *
0x140042506  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x14004250d  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140042512  mov     rcx, [rsp+48h+Reply]; this
0x140042517  mov     edi, eax
0x140042519  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x14004251e  test    edi, edi
0x140042520  jns     short loc_14004257A
0x140042522  movzx   eax, di
0x140042525  lea     rdx, [rsp+48h+Reply]; Reply
0x14004252a  mov     rcx, rbx; pAsync
0x14004252d  mov     dword ptr [rsp+48h+Reply], eax
0x140042531  call    cs:__imp_RpcAsyncCompleteCall
0x140042537  mov     r8d, dword ptr [rsp+48h+Reply]
0x14004253c  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140042543  lea     rcx, aTremotewinspoo_51; "TRemoteWinspool::RpcAsyncDeletePerMachi"...
0x14004254a  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004254f  jmp     short loc_14004257A
0x140042551  lea     rdx, aRestrictdriver_0; "RestrictDriverInstallationToAdministrat"...
0x140042558  lea     rcx, aTremotewinspoo_51; "TRemoteWinspool::RpcAsyncDeletePerMachi"...
0x14004255f  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140042564  lea     rdx, [rsp+48h+Reply]; Reply
0x140042569  mov     dword ptr [rsp+48h+Reply], 5
0x140042571  mov     rcx, rbx; pAsync
0x140042574  call    cs:__imp_RpcAsyncCompleteCall
0x14004257a  mov     rbx, [rsp+48h+arg_0]
0x14004257f  mov     rsi, [rsp+48h+arg_8]
0x140042584  add     rsp, 40h
0x140042588  pop     rdi
0x140042589  retn
```
