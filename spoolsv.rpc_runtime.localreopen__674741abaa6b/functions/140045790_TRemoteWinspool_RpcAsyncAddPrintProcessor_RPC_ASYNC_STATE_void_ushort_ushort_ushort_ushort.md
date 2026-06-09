# TRemoteWinspool::RpcAsyncAddPrintProcessor(_RPC_ASYNC_STATE *,void *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x140045790`
- end: `0x14004590d`
- name: `?RpcAsyncAddPrintProcessor@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAG222@Z`
- size: `381`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007600`
- `0x1400087f0`
- `0x14001748c`
- `0x140042ee4`
- `0x140045790`
- `0x14005e898`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400457fc`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045818`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045843`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045867`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400457fc`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045818`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045843`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140045867`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400457c7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400458dc`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400457c7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1400458dc`

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
0x140045790  push    rbx
0x140045792  push    rbp
0x140045793  push    rsi
0x140045794  push    r14
0x140045796  push    r15
0x140045798  sub     rsp, 50h
0x14004579c  mov     rsi, r9
0x14004579f  mov     [rsp+78h+Reply], 0
0x1400457a8  mov     rbp, r8
0x1400457ab  mov     r14, rcx
0x1400457ae  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1400457b3  test    eax, eax
0x1400457b5  jz      short loc_1400457EB
0x1400457b7  lea     rdx, [rsp+78h+Reply]; Reply
0x1400457bc  mov     dword ptr [rsp+78h+Reply], 32h ; '2'
0x1400457c4  mov     rcx, r14; pAsync
0x1400457c7  call    cs:__imp_RpcAsyncCompleteCall
0x1400457ce  nop     dword ptr [rax+rax+00h]
0x1400457d3  lea     rdx, aTryingToAddPri_1; "Trying to add print processor asynchron"...
0x1400457da  lea     rcx, aTremotewinspoo_27; "TRemoteWinspool::RpcAsyncAddPrintProces"...
0x1400457e1  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400457e6  jmp     loc_140045900
0x1400457eb  mov     r15d, 104h
0x1400457f1  test    rsi, rsi
0x1400457f4  jz      short loc_14004580D
0x1400457f6  mov     edx, r15d; MaxCount
0x1400457f9  mov     rcx, rsi; Source
0x1400457fc  call    cs:__imp_wcsnlen
0x140045803  nop     dword ptr [rax+rax+00h]
0x140045808  cmp     rax, r15
0x14004580b  jnb     short loc_140045878
0x14004580d  test    rbp, rbp
0x140045810  jz      short loc_140045829
0x140045812  mov     rdx, r15; MaxCount
0x140045815  mov     rcx, rbp; Source
0x140045818  call    cs:__imp_wcsnlen
0x14004581f  nop     dword ptr [rax+rax+00h]
0x140045824  cmp     rax, r15
0x140045827  jnb     short loc_140045878
0x140045829  cmp     [rsp+78h+Source], 0
0x140045832  jz      short loc_140045854
0x140045834  mov     rcx, [rsp+78h+Source]; Source
0x14004583c  mov     ebx, 207h
0x140045841  mov     edx, ebx; MaxCount
0x140045843  call    cs:__imp_wcsnlen
0x14004584a  nop     dword ptr [rax+rax+00h]
0x14004584f  cmp     rax, rbx
0x140045852  jnb     short loc_140045878
0x140045854  mov     rbx, [rsp+78h+arg_28]
0x14004585c  test    rbx, rbx
0x14004585f  jz      short loc_14004587F
0x140045861  mov     rdx, r15; MaxCount
0x140045864  mov     rcx, rbx; Source
0x140045867  call    cs:__imp_wcsnlen
0x14004586e  nop     dword ptr [rax+rax+00h]
0x140045873  cmp     rax, r15
0x140045876  jb      short loc_14004587F
0x140045878  mov     ebx, 80070057h
0x14004587d  jmp     short loc_1400458CD
0x14004587f  mov     r9, [rsp+78h+Source]
0x140045887  lea     rax, [rsp+78h+Reply]
0x14004588c  mov     [rsp+78h+var_40], rax
0x140045891  mov     r8, rsi
0x140045894  mov     [rsp+78h+var_48], r14
0x140045899  mov     rdx, rbp
0x14004589c  mov     [rsp+78h+var_58], rbx
0x1400458a1  call    ?CreateInstance@?$TFunction5@PEAGPEAGPEAGPEAGW4Call_Route@@@@SAJP6AKPEAG000W4Call_Route@@@Z00001PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction5<ushort *,ushort *,ushort *,ushort *,Call_Route>::CreateInstance(ulong (*)(ushort *,ushort *,ushort *,ushort *,Call_Route),ushort *,ushort *,ushort *,ushort *,Call_Route,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x1400458a6  mov     ebx, eax
0x1400458a8  test    eax, eax
0x1400458aa  js      short loc_1400458CD
0x1400458ac  mov     rdx, [rsp+78h+Reply]; struct NThreadingLibrary::TWorkItem *
0x1400458b1  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x1400458b8  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x1400458bd  mov     rcx, [rsp+78h+Reply]; this
0x1400458c2  mov     ebx, eax
0x1400458c4  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x1400458c9  test    ebx, ebx
0x1400458cb  jns     short loc_140045900
0x1400458cd  movzx   eax, bx
0x1400458d0  lea     rdx, [rsp+78h+Reply]; Reply
0x1400458d5  mov     rcx, r14; pAsync
0x1400458d8  mov     dword ptr [rsp+78h+Reply], eax
0x1400458dc  call    cs:__imp_RpcAsyncCompleteCall
0x1400458e3  nop     dword ptr [rax+rax+00h]
0x1400458e8  mov     r8d, dword ptr [rsp+78h+Reply]
0x1400458ed  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x1400458f4  lea     rcx, aTremotewinspoo_27; "TRemoteWinspool::RpcAsyncAddPrintProces"...
0x1400458fb  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140045900  add     rsp, 50h
0x140045904  pop     r15
0x140045906  pop     r14
0x140045908  pop     rsi
0x140045909  pop     rbp
0x14004590a  pop     rbx
0x14004590b  retn
```
