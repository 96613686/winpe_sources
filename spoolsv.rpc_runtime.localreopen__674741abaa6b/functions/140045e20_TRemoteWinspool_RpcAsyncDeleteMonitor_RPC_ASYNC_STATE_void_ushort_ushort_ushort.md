# TRemoteWinspool::RpcAsyncDeleteMonitor(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *)

- ea: `0x140045e20`
- end: `0x140045f6d`
- name: `?RpcAsyncDeleteMonitor@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG22@Z`
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
- `0x140045e20`
- `0x14005e898`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045e8b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045ea7`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045ecb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045e8b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045ea7`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045ecb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045e56`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045f3d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045e56`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140045f3d`

## string_xrefs

- `0x140045e62`: `Trying to delete monitor asynchronously in Windows Protected Print mode.`
- `0x140045e69`: `TRemoteWinspool::RpcAsyncDeleteMonitor`
- `0x140045f55`: `TRemoteWinspool::RpcAsyncDeleteMonitor`

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
0x140045e20  push    rbx
0x140045e22  push    rbp
0x140045e23  push    rsi
0x140045e24  push    rdi
0x140045e25  push    r14
0x140045e27  sub     rsp, 50h
0x140045e2b  mov     rdi, r9
0x140045e2e  mov     [rsp+78h+Reply], 0
0x140045e37  mov     rsi, r8
0x140045e3a  mov     rbp, rcx
0x140045e3d  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140045e42  test    eax, eax
0x140045e44  jz      short loc_140045E7A
0x140045e46  lea     rdx, [rsp+78h+Reply]; Reply
0x140045e4b  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x140045e53  mov     rcx, rbp; pAsync
0x140045e56  call    cs:__imp_RpcAsyncCompleteCall
0x140045e5d  nop     dword ptr [rax+rax+00h]
0x140045e62  lea     rdx, aTryingToDelete_9; "Trying to delete monitor asynchronously"...
0x140045e69  lea     rcx, aTremotewinspoo_4; "TRemoteWinspool::RpcAsyncDeleteMonitor"
0x140045e70  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140045e75  jmp     loc_140045F61
0x140045e7a  mov     r14d, 104h
0x140045e80  test    rdi, rdi
0x140045e83  jz      short loc_140045E9C
0x140045e85  mov     edx, r14d; MaxCount
0x140045e88  mov     rcx, rdi; Source
0x140045e8b  call    cs:__imp_wcsnlen
0x140045e92  nop     dword ptr [rax+rax+00h]
0x140045e97  cmp     rax, r14
0x140045e9a  jnb     short loc_140045EDC
0x140045e9c  test    rsi, rsi
0x140045e9f  jz      short loc_140045EB8
0x140045ea1  mov     rdx, r14; MaxCount
0x140045ea4  mov     rcx, rsi; Source
0x140045ea7  call    cs:__imp_wcsnlen
0x140045eae  nop     dword ptr [rax+rax+00h]
0x140045eb3  cmp     rax, r14
0x140045eb6  jnb     short loc_140045EDC
0x140045eb8  mov     rbx, [rsp+78h+Source]
0x140045ec0  test    rbx, rbx
0x140045ec3  jz      short loc_140045EE3
0x140045ec5  mov     rdx, r14; MaxCount
0x140045ec8  mov     rcx, rbx; Source
0x140045ecb  call    cs:__imp_wcsnlen
0x140045ed2  nop     dword ptr [rax+rax+00h]
0x140045ed7  cmp     rax, r14
0x140045eda  jb      short loc_140045EE3
0x140045edc  mov     ebx, 80070057h
0x140045ee1  jmp     short loc_140045F2E
0x140045ee3  lea     rax, [rsp+78h+Reply]
0x140045ee8  mov     r9, rbx
0x140045eeb  mov     [rsp+78h+var_48], rax
0x140045ef0  lea     rcx, ?YDeleteMonitor@@YAKPEAG00W4Call_Route@@@Z; YDeleteMonitor(ushort *,ushort *,ushort *,Call_Route)
0x140045ef7  mov     r8, rdi
0x140045efa  mov     [rsp+78h+var_50], rbp
0x140045eff  mov     rdx, rsi
0x140045f02  call    ?CreateInstance@?$TFunction4@PEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG00W4Call_Route@@@Z0001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction4<ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x140045f07  mov     ebx, eax
0x140045f09  test    eax, eax
0x140045f0b  js      short loc_140045F2E
0x140045f0d  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x140045f12  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140045f19  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140045f1e  mov     rcx, [rsp+78h+Reply]; this
0x140045f23  mov     ebx, eax
0x140045f25  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140045f2a  test    ebx, ebx
0x140045f2c  jns     short loc_140045F61
0x140045f2e  movzx   eax, bx
0x140045f31  lea     rdx, [rsp+78h+Reply]; Reply
0x140045f36  mov     rcx, rbp; pAsync
0x140045f39  mov     dword ptr [rsp+78h+Reply], eax
0x140045f3d  call    cs:__imp_RpcAsyncCompleteCall
0x140045f44  nop     dword ptr [rax+rax+00h]
0x140045f49  mov     r8d, dword ptr [rsp+78h+Reply]
0x140045f4e  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140045f55  lea     rcx, aTremotewinspoo_4; "TRemoteWinspool::RpcAsyncDeleteMonitor"
0x140045f5c  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140045f61  add     rsp, 50h
0x140045f65  pop     r14
0x140045f67  pop     rdi
0x140045f68  pop     rsi
0x140045f69  pop     rbp
0x140045f6a  pop     rbx
0x140045f6b  retn
```
