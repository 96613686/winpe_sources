# TRemoteWinspool::RpcAsyncAddPrintProcessor(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x140041d50`
- end: `0x140041ea8`
- name: `?RpcAsyncAddPrintProcessor@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG222@Z`
- size: `344`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006b30`
- `0x140007c00`
- `0x1400160a0`
- `0x14003f550`
- `0x140041d50`
- `0x1400590f0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041db6`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041dcc`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041df1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041e0f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041db6`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041dcc`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041df1`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140041e0f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041d87`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041e7e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041d87`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140041e7e`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncAddPrintProcessor(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *Source,
        unsigned __int16 *a6)
{
  int v9; // ecx
  int v10; // ebx
  int Instance; // eax
  struct NThreadingLibrary::TWorkItem *Reply[7]; // [rsp+40h] [rbp-38h] BYREF

  Reply[0] = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    LODWORD(Reply[0]) = 50;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncAddPrintProcessor",
      L"Trying to add print processor asynchronously in Windows Protected Print mode.");
    return;
  }
  if ( a4 && wcsnlen(a4, 0x104u) >= 0x104
    || a3 && wcsnlen(a3, 0x104u) >= 0x104
    || Source && wcsnlen(Source, 0x207u) >= 0x207
    || a6 && wcsnlen(a6, 0x104u) >= 0x104 )
  {
    LOWORD(v10) = 87;
LABEL_14:
    LODWORD(Reply[0]) = (unsigned __int16)v10;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncAddPrintProcessor",
      L"Failed.  Error %d.",
      LODWORD(Reply[0]));
    return;
  }
  Instance = TFunction5<unsigned short *,unsigned short *,unsigned short *,unsigned short *,enum Call_Route>::CreateInstance(
               v9,
               (_DWORD)a3,
               (_DWORD)a4,
               (_DWORD)Source,
               (__int64)a6);
  LOWORD(v10) = Instance;
  if ( Instance < 0 )
    goto LABEL_14;
  v10 = NThreadingLibrary::TWorkCrew::AddItem(g_pWorkCrew, Reply[0]);
  NCoreLibrary::TReferenceCount::Release(Reply[0]);
  if ( v10 < 0 )
    goto LABEL_14;
}

```

## disassembly

```asm
0x140041d50  push    rbx
0x140041d52  push    rbp
0x140041d53  push    rsi
0x140041d54  push    r14
0x140041d56  push    r15
0x140041d58  sub     rsp, 50h
0x140041d5c  mov     rsi, r9
0x140041d5f  mov     [rsp+78h+Reply], 0
0x140041d68  mov     rbp, r8
0x140041d6b  mov     r14, rcx
0x140041d6e  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140041d73  test    eax, eax
0x140041d75  jz      short loc_140041DA5
0x140041d77  lea     rdx, [rsp+78h+Reply]; Reply
0x140041d7c  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x140041d84  mov     rcx, r14; pAsync
0x140041d87  call    cs:__imp_RpcAsyncCompleteCall
0x140041d8d  lea     rdx, aTryingToAddPri_1; "Trying to add print processor asynchron"...
0x140041d94  lea     rcx, aTremotewinspoo_27; "TRemoteWinspool::RpcAsyncAddPrintProces"...
0x140041d9b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140041da0  jmp     loc_140041E9C
0x140041da5  mov     r15d, 104h
0x140041dab  test    rsi, rsi
0x140041dae  jz      short loc_140041DC1
0x140041db0  mov     edx, r15d; MaxCount
0x140041db3  mov     rcx, rsi; Source
0x140041db6  call    cs:__imp_wcsnlen
0x140041dbc  cmp     rax, r15
0x140041dbf  jnb     short loc_140041E1A
0x140041dc1  test    rbp, rbp
0x140041dc4  jz      short loc_140041DD7
0x140041dc6  mov     rdx, r15; MaxCount
0x140041dc9  mov     rcx, rbp; Source
0x140041dcc  call    cs:__imp_wcsnlen
0x140041dd2  cmp     rax, r15
0x140041dd5  jnb     short loc_140041E1A
0x140041dd7  cmp     [rsp+78h+Source], 0
0x140041de0  jz      short loc_140041DFC
0x140041de2  mov     rcx, [rsp+78h+Source]; Source
0x140041dea  mov     ebx, 207h
0x140041def  mov     edx, ebx; MaxCount
0x140041df1  call    cs:__imp_wcsnlen
0x140041df7  cmp     rax, rbx
0x140041dfa  jnb     short loc_140041E1A
0x140041dfc  mov     rbx, [rsp+78h+arg_28]
0x140041e04  test    rbx, rbx
0x140041e07  jz      short loc_140041E21
0x140041e09  mov     rdx, r15; MaxCount
0x140041e0c  mov     rcx, rbx; Source
0x140041e0f  call    cs:__imp_wcsnlen
0x140041e15  cmp     rax, r15
0x140041e18  jb      short loc_140041E21
0x140041e1a  mov     ebx, 80070057h
0x140041e1f  jmp     short loc_140041E6F
0x140041e21  mov     r9, [rsp+78h+Source]
0x140041e29  lea     rax, [rsp+78h+Reply]
0x140041e2e  mov     [rsp+78h+var_40], rax
0x140041e33  mov     r8, rsi
0x140041e36  mov     [rsp+78h+var_48], r14
0x140041e3b  mov     rdx, rbp
0x140041e3e  mov     [rsp+78h+var_58], rbx
0x140041e43  call    ?CreateInstance@?$TFunction5@PEAGPEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG000W4Call_Route@@@Z00001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction5<ushort *,ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x140041e48  mov     ebx, eax
0x140041e4a  test    eax, eax
0x140041e4c  js      short loc_140041E6F
0x140041e4e  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x140041e53  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140041e5a  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140041e5f  mov     rcx, [rsp+78h+Reply]; this
0x140041e64  mov     ebx, eax
0x140041e66  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140041e6b  test    ebx, ebx
0x140041e6d  jns     short loc_140041E9C
0x140041e6f  movzx   eax, bx
0x140041e72  lea     rdx, [rsp+78h+Reply]; Reply
0x140041e77  mov     rcx, r14; pAsync
0x140041e7a  mov     dword ptr [rsp+78h+Reply], eax
0x140041e7e  call    cs:__imp_RpcAsyncCompleteCall
0x140041e84  mov     r8d, dword ptr [rsp+78h+Reply]
0x140041e89  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140041e90  lea     rcx, aTremotewinspoo_27; "TRemoteWinspool::RpcAsyncAddPrintProces"...
0x140041e97  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140041e9c  add     rsp, 50h
0x140041ea0  pop     r15
0x140041ea2  pop     r14
0x140041ea4  pop     rsi
0x140041ea5  pop     rbp
0x140041ea6  pop     rbx
0x140041ea7  retn
```
