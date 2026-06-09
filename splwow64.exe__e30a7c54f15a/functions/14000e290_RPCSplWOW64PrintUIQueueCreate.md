# RPCSplWOW64PrintUIQueueCreate

- ea: `0x14000e290`
- end: `0x14000e3b7`
- name: `RPCSplWOW64PrintUIQueueCreate`
- size: `295`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, LPVOID lpTlsValue@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000e290`
- `0x14000f42c`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000e2ac`
- `KERNEL32!TlsSetValue` at `0x14000e3a8`
- `KERNEL32!TlsSetValue` at `0x14000e2ac`
- `KERNEL32!TlsSetValue` at `0x14000e3a8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e39a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e39a`

## string_xrefs

- `0x14000e2b5`: `clientProcessID %u pszPrinterName %ws`
- `0x14000e2bf`: `RPCSplWOW64PrintUIQueueCreate`
- `0x14000e344`: `RPCSplWOW64PrintUIQueueCreate`
- `0x14000e36b`: `RPCSplWOW64PrintUIQueueCreate`
- `0x14000e305`: `vQueueCreate`
- `0x14000e33d`: `TPrintUIMgr::QueueCreate failed.  Error %d.`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64PrintUIQueueCreate(
        PRPC_ASYNC_STATE pAsync,
        LPVOID lpTlsValue,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  unsigned int v6; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  void *v12; // rbx
  unsigned int v13; // eax
  void *v15; // [rsp+40h] [rbp-38h] BYREF
  unsigned int Reply; // [rsp+88h] [rbp+10h] BYREF

  v6 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo(
    "RPCSplWOW64PrintUIQueueCreate",
    L"clientProcessID %u pszPrinterName %ws",
    v6,
    a4);
  v15 = 0;
  Reply = 0;
  v10 = TLoad64BitDllsMgr::QueryInterface(pGLdrObj, &IID_PRINTUIOPERATIONS, &v15);
  v11 = v10;
  if ( v10 )
  {
    SplWow64Telemetry::WriteDbgTraceError(
      "RPCSplWOW64PrintUIQueueCreate",
      L"Failed to instantiate a print UI object.  Error hr: 0x%x.",
      v10);
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    Reply = v11;
  }
  else
  {
    v12 = v15;
    v13 = TPrintUIMgr::PrintUIMethod(v15, "vQueueCreate", a3, a4, a5, a6);
    Reply = v13;
    if ( v13 )
      SplWow64Telemetry::WriteDbgTraceError(
        "RPCSplWOW64PrintUIQueueCreate",
        L"TPrintUIMgr::QueueCreate failed.  Error %d.",
        v13);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000e290  push    rbx
0x14000e292  push    rbp
0x14000e293  push    rsi
0x14000e294  push    rdi
0x14000e295  sub     rsp, 58h
0x14000e299  mov     ebx, edx
0x14000e29b  mov     rdi, rcx
0x14000e29e  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e2a4  mov     rsi, r9
0x14000e2a7  mov     edx, edx; lpTlsValue
0x14000e2a9  mov     rbp, r8
0x14000e2ac  call    cs:__imp_TlsSetValue
0x14000e2b2  mov     r9, rsi
0x14000e2b5  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000e2bc  mov     r8d, ebx
0x14000e2bf  lea     rcx, aRpcsplwow64pri_1; "RPCSplWOW64PrintUIQueueCreate"
0x14000e2c6  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000e2cb  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000e2d2  lea     r8, [rsp+78h+var_38]; void **
0x14000e2d7  lea     rdx, ?IID_PRINTUIOPERATIONS@@3U_GUID@@A; struct _GUID *
0x14000e2de  mov     [rsp+78h+var_38], 0
0x14000e2e7  mov     [rsp+78h+Reply], 0
0x14000e2f2  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000e2f7  mov     ebx, eax
0x14000e2f9  test    eax, eax
0x14000e2fb  jnz     short loc_14000E361
0x14000e2fd  mov     rax, [rsp+78h+arg_28]
0x14000e305  lea     rdx, aVqueuecreate; "vQueueCreate"
0x14000e30c  mov     rbx, [rsp+78h+var_38]
0x14000e311  mov     r9, rsi
0x14000e314  mov     [rsp+78h+var_50], rax
0x14000e319  mov     r8, rbp
0x14000e31c  mov     eax, [rsp+78h+arg_20]
0x14000e323  mov     rcx, rbx
0x14000e326  mov     [rsp+78h+var_58], eax
0x14000e32a  call    ?PrintUIMethod@TPrintUIMgr@@QEAAKPEBDPEAXPEBGH_JW4EPrintUIOp@1@@Z; TPrintUIMgr::PrintUIMethod(char const *,void *,ushort const *,int,__int64,TPrintUIMgr::EPrintUIOp)
0x14000e32f  mov     [rsp+78h+Reply], eax
0x14000e336  test    eax, eax
0x14000e338  jz      short loc_14000E350
0x14000e33a  mov     r8d, eax
0x14000e33d  lea     rdx, aTprintuimgrQue; "TPrintUIMgr::QueueCreate failed.  Error"...
0x14000e344  lea     rcx, aRpcsplwow64pri_1; "RPCSplWOW64PrintUIQueueCreate"
0x14000e34b  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e350  mov     rax, [rbx]
0x14000e353  mov     rcx, rbx
0x14000e356  mov     rax, [rax+10h]
0x14000e35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e35f  jmp     short loc_14000E38F
0x14000e361  mov     r8d, ebx
0x14000e364  lea     rdx, aFailedToInstan_2; "Failed to instantiate a print UI object"...
0x14000e36b  lea     rcx, aRpcsplwow64pri_1; "RPCSplWOW64PrintUIQueueCreate"
0x14000e372  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e377  mov     eax, ebx
0x14000e379  and     eax, 1FFF0000h
0x14000e37e  cmp     eax, 70000h
0x14000e383  jnz     short loc_14000E388
0x14000e385  movzx   ebx, bx
0x14000e388  mov     [rsp+78h+Reply], ebx
0x14000e38f  lea     rdx, [rsp+78h+Reply]; Reply
0x14000e397  mov     rcx, rdi; pAsync
0x14000e39a  call    cs:__imp_RpcAsyncCompleteCall
0x14000e3a0  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e3a6  xor     edx, edx; lpTlsValue
0x14000e3a8  call    cs:__imp_TlsSetValue
0x14000e3ae  add     rsp, 58h
0x14000e3b2  pop     rdi
0x14000e3b3  pop     rsi
0x14000e3b4  pop     rbp
0x14000e3b5  pop     rbx
0x14000e3b6  retn
```
