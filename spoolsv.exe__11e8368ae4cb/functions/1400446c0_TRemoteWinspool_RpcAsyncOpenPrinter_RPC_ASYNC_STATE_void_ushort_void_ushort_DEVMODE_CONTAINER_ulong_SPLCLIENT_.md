# TRemoteWinspool::RpcAsyncOpenPrinter(_RPC_ASYNC_STATE *,void *,ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,_SPLCLIENT_CONTAINER *)

- ea: `0x1400446c0`
- end: `0x14004481b`
- name: `?RpcAsyncOpenPrinter@TRemoteWinspool@@SAXPEAU_RPC_ASYNC_STATE@@PEAXPEAGPEAPEAX2PEAU_DEVMODE_CONTAINER@@KPEAU_SPLCLIENT_CONTAINER@@@Z`
- size: `347`
- prototype: `void __usercall(PRPC_ASYNC_STATE pAsync@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, void **@<r9>, wchar_t *Source, struct _DEVMODE_CONTAINER *, unsigned int, struct _SPLCLIENT_CONTAINER *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400353d0`
- `0x140035410`

## callees

- `0x140006b30`
- `0x140007c00`
- `0x1400160a0`
- `0x1400403b4`
- `0x1400446c0`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400446fe`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004471e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1400446fe`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004471e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140044740`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140044808`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140044740`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140044808`

## string_xrefs

- `0x140044752`: `TRemoteWinspool::RpcAsyncOpenPrinter`

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
0x1400446c0  push    rbx
0x1400446c2  push    rbp
0x1400446c3  push    rsi
0x1400446c4  push    rdi
0x1400446c5  push    r14
0x1400446c7  sub     rsp, 60h
0x1400446cb  mov     r14, r9
0x1400446ce  mov     [rsp+88h+Reply], 0
0x1400446d7  mov     rdi, r8
0x1400446da  mov     rbp, rcx
0x1400446dd  mov     rsi, [rsp+88h+arg_38]
0x1400446e5  test    rsi, rsi
0x1400446e8  jz      short loc_1400446EF
0x1400446ea  cmp     dword ptr [rsi], 4
0x1400446ed  jz      short loc_14004472C
0x1400446ef  test    rdi, rdi
0x1400446f2  jz      short loc_140044709
0x1400446f4  mov     ebx, 21Bh
0x1400446f9  mov     rcx, rdi; Source
0x1400446fc  mov     edx, ebx; MaxCount
0x1400446fe  call    cs:__imp_wcsnlen
0x140044704  cmp     rax, rbx
0x140044707  jnb     short loc_14004472C
0x140044709  mov     rbx, [rsp+88h+Source]
0x140044711  test    rbx, rbx
0x140044714  jz      short loc_140044769
0x140044716  mov     edx, 104h; MaxCount
0x14004471b  mov     rcx, rbx; Source
0x14004471e  call    cs:__imp_wcsnlen
0x140044724  cmp     rax, 104h
0x14004472a  jb      short loc_140044769
0x14004472c  mov     eax, 80070057h
0x140044731  movzx   eax, ax
0x140044734  lea     rdx, [rsp+88h+Reply]; Reply
0x140044739  mov     rcx, rbp; pAsync
0x14004473c  mov     dword ptr [rsp+88h+Reply], eax
0x140044740  call    cs:__imp_RpcAsyncCompleteCall
0x140044746  mov     r8d, dword ptr [rsp+88h+Reply]
0x14004474b  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140044752  lea     rcx, aTremotewinspoo_44; "TRemoteWinspool::RpcAsyncOpenPrinter"
0x140044759  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004475e  add     rsp, 60h
0x140044762  pop     r14
0x140044764  pop     rdi
0x140044765  pop     rsi
0x140044766  pop     rbp
0x140044767  pop     rbx
0x140044768  retn
0x140044769  lea     rax, [rsp+88h+Reply]
0x14004476e  mov     r9, rbx
0x140044771  mov     [rsp+88h+var_40], rax
0x140044776  mov     r8, r14
0x140044779  mov     eax, [rsp+88h+arg_30]
0x140044780  mov     rdx, rdi
0x140044783  mov     [rsp+88h+var_48], rbp
0x140044788  mov     [rsp+88h+var_50], rsi
0x14004478d  mov     [rsp+88h+var_60], eax
0x140044791  mov     rax, [rsp+88h+arg_28]
0x140044799  mov     [rsp+88h+var_68], rax
0x14004479e  call    ?CreateInstance@?$TFunction7@PEAGPEAPEAXPEAGPEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@@SAJP6AKPEAGPEAPEAX0PEAU_DEVMODE_CONTAINER@@KW4Call_Route@@PEAU_SPLCLIENT_CONTAINER@@@Z0102K34PEAU_RPC_ASYNC_STATE@@PEAPEAVTWorkItem@NThreadingLibrary@@@Z; TFunction7<ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *>::CreateInstance(ulong (*)(ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *),ushort *,void * *,ushort *,_DEVMODE_CONTAINER *,ulong,Call_Route,_SPLCLIENT_CONTAINER *,_RPC_ASYNC_STATE *,NThreadingLibrary::TWorkItem * *)
0x1400447a3  test    eax, eax
0x1400447a5  js      short loc_140044731
0x1400447a7  mov     eax, 1
0x1400447ac  lock xadd cs:?g_directHandledCalls@@3JA, eax; long g_directHandledCalls
0x1400447b4  inc     eax
0x1400447b6  cmp     eax, 0C8h
0x1400447bb  jge     short loc_1400447DA
0x1400447bd  mov     rbx, [rsp+88h+Reply]
0x1400447c2  mov     rcx, rbx
0x1400447c5  mov     rax, [rbx]
0x1400447c8  mov     rax, [rax+18h]
0x1400447cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400447d1  lock dec cs:?g_directHandledCalls@@3JA; long g_directHandledCalls
0x1400447d8  jmp     short loc_14004480E
0x1400447da  lock dec cs:?g_directHandledCalls@@3JA; long g_directHandledCalls
0x1400447e1  mov     rbx, [rsp+88h+Reply]
0x1400447e6  mov     rcx, cs:?g_pWorkCrew@@3PEAVTWorkCrew@NThreadingLibrary@@EA; this
0x1400447ed  mov     rdx, rbx; struct NThreadingLibrary::TWorkItem *
0x1400447f0  call    ?AddItem@TWorkCrew@NThreadingLibrary@@QEAAJPEAVTWorkItem@2@@Z; NThreadingLibrary::TWorkCrew::AddItem(NThreadingLibrary::TWorkItem *)
0x1400447f5  test    eax, eax
0x1400447f7  jns     short loc_14004480E
0x1400447f9  movzx   eax, ax
0x1400447fc  lea     rdx, [rsp+88h+Reply]; Reply
0x140044801  mov     rcx, rbp; pAsync
0x140044804  mov     dword ptr [rsp+88h+Reply], eax
0x140044808  call    cs:__imp_RpcAsyncCompleteCall
0x14004480e  mov     rcx, rbx; this
0x140044811  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x140044816  jmp     loc_14004475E
```
