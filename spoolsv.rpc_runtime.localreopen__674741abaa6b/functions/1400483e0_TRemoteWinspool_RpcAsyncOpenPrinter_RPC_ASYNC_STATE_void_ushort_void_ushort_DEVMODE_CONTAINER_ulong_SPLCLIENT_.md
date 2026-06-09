# TRemoteWinspool::RpcAsyncOpenPrinter(_RPC_ASYNC_STATE *,void *,ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,_SPLCLIENT_CONTAINER *)

- ea: `0x1400483e0`
- end: `0x140048554`
- name: `?RpcAsyncOpenPrinter@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAGPEAPEAX2PEAU_DEVMODE_CONTAINER@@KPEAU_SPLCLIENT_CONTAINER@@@Z`
- size: `372`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, void **@<r9>, wchar_t *Source, struct _DEVMODE_CONTAINER *, unsigned int, struct _SPLCLIENT_CONTAINER *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140038070`
- `0x1400380b0`

## callees

- `0x140007600`
- `0x1400087f0`
- `0x14001748c`
- `0x140043d54`
- `0x1400483e0`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004841e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140048444`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004841e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140048444`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004846c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004853b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004846c`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14004853b`

## string_xrefs

- `0x140048484`: `TRemoteWinspool::RpcAsyncOpenPrinter`

## pseudocode

```c
void __fastcall TRemoteWinspool::RpcAsyncOpenPrinter(
        PRPC_ASYNC_STATE pAsync,
        void *a2,
        unsigned __int16 *a3,
        void **a4,
        wchar_t *Source,
        struct _DEVMODE_CONTAINER *a6,
        unsigned int a7,
        struct _SPLCLIENT_CONTAINER *a8)
{
  int v8; // r14d
  int v9; // edi
  int Instance; // eax
  NCoreLibrary::TReferenceCount *v12; // rbx
  int v13; // eax
  struct NThreadingLibrary::TWorkItem *Reply[7]; // [rsp+50h] [rbp-38h] BYREF

  v8 = (int)a4;
  Reply[0] = 0;
  v9 = (int)a3;
  if ( a8 && *(_DWORD *)a8 == 4 || a3 && wcsnlen(a3, 0x21Bu) >= 0x21B || Source && wcsnlen(Source, 0x104u) >= 0x104 )
  {
    LOWORD(Instance) = 87;
LABEL_8:
    LODWORD(Reply[0]) = (unsigned __int16)Instance;
    RpcAsyncCompleteCall(pAsync, Reply);
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "TRemoteWinspool::RpcAsyncOpenPrinter",
      L"Failed.  Error %d.",
      LODWORD(Reply[0]));
    return;
  }
  Instance = TFunction7<unsigned short *,void * *,unsigned short *,_DEVMODE_CONTAINER *,unsigned long,enum Call_Route,_SPLCLIENT_CONTAINER *>::CreateInstance(
               (_DWORD)pAsync,
               v9,
               v8,
               (_DWORD)Source,
               (__int64)a6,
               a7);
  if ( Instance < 0 )
    goto LABEL_8;
  if ( _InterlockedIncrement(&g_directHandledCalls) >= 200 )
  {
    _InterlockedDecrement(&g_directHandledCalls);
    v12 = Reply[0];
    v13 = NThreadingLibrary::TWorkCrew::AddItem(g_pWorkCrew, Reply[0]);
    if ( v13 < 0 )
    {
      LODWORD(Reply[0]) = (unsigned __int16)v13;
      RpcAsyncCompleteCall(pAsync, Reply);
    }
  }
  else
  {
    v12 = Reply[0];
    (*(void (__fastcall **)(struct NThreadingLibrary::TWorkItem *))(*(_QWORD *)Reply[0] + 24LL))(Reply[0]);
    _InterlockedDecrement(&g_directHandledCalls);
  }
  NCoreLibrary::TReferenceCount::Release(v12);
}

```

## disassembly

```asm
0x1400483e0  push    rbx
0x1400483e2  push    rbp
0x1400483e3  push    rsi
0x1400483e4  push    rdi
0x1400483e5  push    r14
0x1400483e7  sub     rsp, 60h
0x1400483eb  mov     r14, r9
0x1400483ee  mov     [rsp+88h+Reply], 0
0x1400483f7  mov     rdi, r8
0x1400483fa  mov     rbp, rcx
0x1400483fd  mov     rsi, [rsp+88h+arg_38]
0x140048405  test    rsi, rsi
0x140048408  jz      short loc_14004840F
0x14004840a  cmp     dword ptr [rsi], 4
0x14004840d  jz      short loc_140048458
0x14004840f  test    rdi, rdi
0x140048412  jz      short loc_14004842F
0x140048414  mov     ebx, 21Bh
0x140048419  mov     rcx, rdi; Source
0x14004841c  mov     edx, ebx; MaxCount
0x14004841e  call    cs:__imp_wcsnlen
0x140048425  nop     dword ptr [rax+rax+00h]
0x14004842a  cmp     rax, rbx
0x14004842d  jnb     short loc_140048458
0x14004842f  mov     rbx, [rsp+88h+Source]
0x140048437  test    rbx, rbx
0x14004843a  jz      short loc_14004849C
0x14004843c  mov     edx, 104h; MaxCount
0x140048441  mov     rcx, rbx; Source
0x140048444  call    cs:__imp_wcsnlen
0x14004844b  nop     dword ptr [rax+rax+00h]
0x140048450  cmp     rax, 104h
0x140048456  jb      short loc_14004849C
0x140048458  mov     eax, 80070057h
0x14004845d  movzx   eax, ax
0x140048460  lea     rdx, [rsp+88h+Reply]; Reply
0x140048465  mov     rcx, rbp; pAsync
0x140048468  mov     dword ptr [rsp+88h+Reply], eax
0x14004846c  call    cs:__imp_RpcAsyncCompleteCall
0x140048473  nop     dword ptr [rax+rax+00h]
0x140048478  mov     r8d, dword ptr [rsp+88h+Reply]
0x14004847d  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140048484  lea     rcx, aTremotewinspoo_44; "TRemoteWinspool::RpcAsyncOpenPrinter"
0x14004848b  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140048490  add     rsp, 60h
0x140048494  pop     r14
0x140048496  pop     rdi
0x140048497  pop     rsi
0x140048498  pop     rbp
0x140048499  pop     rbx
0x14004849a  retn
0x14004849c  lea     rax, [rsp+88h+Reply]
0x1400484a1  mov     r9, rbx
0x1400484a4  mov     [rsp+88h+var_40], rax
0x1400484a9  mov     r8, r14
0x1400484ac  mov     eax, [rsp+88h+arg_30]
0x1400484b3  mov     rdx, rdi
0x1400484b6  mov     [rsp+88h+var_48], rbp
0x1400484bb  mov     [rsp+88h+var_50], rsi
0x1400484c0  mov     [rsp+88h+var_60], eax
0x1400484c4  mov     rax, [rsp+88h+arg_28]
0x1400484cc  mov     [rsp+88h+var_68], rax
0x1400484d1  call    ?CreateInstance@?$TFunction7@PEAGPEAPEAXPEAGPEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@@SAJP6AKPEAGPEAPEAX0PEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@Z0102K34PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction7<ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *>::CreateInstance(ulong (*)(ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *),ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x1400484d6  test    eax, eax
0x1400484d8  js      short loc_14004845D
0x1400484da  mov     eax, 1
0x1400484df  lock xadd cs:?g_directHandledCalls@@3JA, eax; long g_directHandledCalls
0x1400484e7  inc     eax
0x1400484e9  cmp     eax, 0C8h
0x1400484ee  jge     short loc_14004850D
0x1400484f0  mov     rbx, [rsp+88h+Reply]
0x1400484f5  mov     rcx, rbx
0x1400484f8  mov     rax, [rbx]
0x1400484fb  mov     rax, [rax+18h]
0x1400484ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048504  lock dec cs:?g_directHandledCalls@@3JA; long g_directHandledCalls
0x14004850b  jmp     short loc_140048547
0x14004850d  lock dec cs:?g_directHandledCalls@@3JA; long g_directHandledCalls
0x140048514  mov     rbx, [rsp+88h+Reply]
0x140048519  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x140048520  mov     rdx, rbx; struct NThreadingLibrary::TWorkItem *
0x140048523  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x140048528  test    eax, eax
0x14004852a  jns     short loc_140048547
0x14004852c  movzx   eax, ax
0x14004852f  lea     rdx, [rsp+88h+Reply]; Reply
0x140048534  mov     rcx, rbp; pAsync
0x140048537  mov     dword ptr [rsp+88h+Reply], eax
0x14004853b  call    cs:__imp_RpcAsyncCompleteCall
0x140048542  nop     dword ptr [rax+rax+00h]
0x140048547  mov     rcx, rbx; this
0x14004854a  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x14004854f  jmp     loc_140048490
```
