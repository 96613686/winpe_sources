# TRemoteWinspool::RpcAsyncDeletePerMachineConnection(_RPC_ASYNC_STATE *,void *,ushort *,ushort const *)

- ea: `0x140045f80`
- end: `0x14004609d`
- name: `?RpcAsyncDeletePerMachineConnection@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAGPEBG@Z`
- size: `285`
- prototype: `void __fastcall(PRPC_ASYNC_STATE pAsync, void *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140007600`
- `0x1400087f0`
- `0x1400173c0`
- `0x14001748c`
- `0x140042108`
- `0x140045f80`
- `0x14005e898`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x140045fba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046037`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046080`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045fba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046037`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140046080`

## string_xrefs

- `0x14004605d`: `RestrictDriverInstallationToAdministrators policy is set and we cannot confirm this user is an Administrator. Return ERROR_ACCESS_DENIED.`
- `0x140045fc6`: `Trying to delete per machine connection asynchronously in Windows Protected Print mode.`
- `0x140045fcd`: `TRemoteWinspool::RpcAsyncDeletePerMachineConnection`
- `0x14004604f`: `TRemoteWinspool::RpcAsyncDeletePerMachineConnection`
- `0x140046064`: `TRemoteWinspool::RpcAsyncDeletePerMachineConnection`

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
0x140045f80  mov     [rsp+arg_0], rbx
0x140045f85  mov     [rsp+arg_8], rsi
0x140045f8a  push    rdi
0x140045f8b  sub     rsp, 40h
0x140045f8f  mov     rdi, r9
0x140045f92  mov     [rsp+48h+Reply], 0
0x140045f9b  mov     rsi, r8
0x140045f9e  mov     rbx, rcx
0x140045fa1  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140045fa6  test    eax, eax
0x140045fa8  jz      short loc_140045FDE
0x140045faa  lea     rdx, [rsp+48h+Reply]; Reply
0x140045faf  mov     dword ptr [rsp+48h+Reply], 32h ; '2'
0x140045fb7  mov     rcx, rbx; pAsync
0x140045fba  call    cs:__imp_RpcAsyncCompleteCall
0x140045fc1  nop     dword ptr [rax+rax+00h]
0x140045fc6  lea     rdx, aTryingToDelete_5; "Trying to delete per machine connection"...
0x140045fcd  lea     rcx, aTremotewinspoo_51; "TRemoteWinspool::RpcAsyncDeletePerMachi"...
0x140045fd4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140045fd9  jmp     loc_14004608C
0x140045fde  call    ?YRestrictDriverInstallationToAdministrators@@YAHXZ; YRestrictDriverInstallationToAdministrators(void)
0x140045fe3  test    eax, eax
0x140045fe5  jnz     short loc_14004605D
0x140045fe7  lea     rax, [rsp+48h+Reply]
0x140045fec  mov     r8, rdi
0x140045fef  mov     [rsp+48h+var_20], rax
0x140045ff4  mov     rdx, rsi
0x140045ff7  mov     [rsp+48h+var_28], rbx
0x140045ffc  call    ?CreateInstance@?$TFunction3@PEAGPEBGW4Call_Route@@@@SAJP6AKPEAGPEBGW4Call_Route@@@Z012PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction3<ushort *,ushort const *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort const *,Call_Route),ushort *,ushort const *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x140046001  mov     edi, eax
0x140046003  test    eax, eax
0x140046005  js      short loc_140046028
0x140046007  mov     rdx, [rsp+48h+Reply]; struct NThreadingLibrary::TWorkItem *
0x14004600c  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140046013  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140046018  mov     rcx, [rsp+48h+Reply]; this
0x14004601d  mov     edi, eax
0x14004601f  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140046024  test    edi, edi
0x140046026  jns     short loc_14004608C
0x140046028  movzx   eax, di
0x14004602b  lea     rdx, [rsp+48h+Reply]; Reply
0x140046030  mov     rcx, rbx; pAsync
0x140046033  mov     dword ptr [rsp+48h+Reply], eax
0x140046037  call    cs:__imp_RpcAsyncCompleteCall
0x14004603e  nop     dword ptr [rax+rax+00h]
0x140046043  mov     r8d, dword ptr [rsp+48h+Reply]
0x140046048  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x14004604f  lea     rcx, aTremotewinspoo_51; "TRemoteWinspool::RpcAsyncDeletePerMachi"...
0x140046056  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004605b  jmp     short loc_14004608C
0x14004605d  lea     rdx, aRestrictdriver_0; "RestrictDriverInstallationToAdministrat"...
0x140046064  lea     rcx, aTremotewinspoo_51; "TRemoteWinspool::RpcAsyncDeletePerMachi"...
0x14004606b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140046070  lea     rdx, [rsp+48h+Reply]; Reply
0x140046075  mov     dword ptr [rsp+48h+Reply], 5
0x14004607d  mov     rcx, rbx; pAsync
0x140046080  call    cs:__imp_RpcAsyncCompleteCall
0x140046087  nop     dword ptr [rax+rax+00h]
0x14004608c  mov     rbx, [rsp+48h+arg_0]
0x140046091  mov     rsi, [rsp+48h+arg_8]
0x140046096  add     rsp, 40h
0x14004609a  pop     rdi
0x14004609b  retn
```
