# RPCSplWOW64SpoolerPrinterEvent

- ea: `0x14000e6a0`
- end: `0x14000e7af`
- name: `RPCSplWOW64SpoolerPrinterEvent`
- size: `271`
- prototype: `__int64 __fastcall(LPVOID lpTlsValue, unsigned __int16 *, int, unsigned int, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000e6a0`
- `0x14000ed78`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000e6be`
- `KERNEL32!TlsSetValue` at `0x14000e79c`
- `KERNEL32!TlsSetValue` at `0x14000e6be`
- `KERNEL32!TlsSetValue` at `0x14000e79c`

## string_xrefs

- `0x14000e6c7`: `clientProcessID %u pszPrinterName %ws`

## pseudocode

```c
__int64 __fastcall RPCSplWOW64SpoolerPrinterEvent(
        LPVOID lpTlsValue,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int *a6)
{
  unsigned int v7; // ebx
  unsigned int Interface; // eax
  unsigned int v11; // ebx
  TPrinterEventMgr *v12; // rbx
  unsigned int v13; // edi
  TPrinterEventMgr *v15; // [rsp+30h] [rbp-38h] BYREF

  v7 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  SplWow64Telemetry::WriteDbgTraceInfo(
    "RPCSplWOW64SpoolerPrinterEvent",
    L"clientProcessID %u pszPrinterName %ws",
    v7,
    a2);
  v15 = 0;
  Interface = TLoad64BitDllsMgr::QueryInterface(pGLdrObj, &IID_PRINTEREVENT, (void **)&v15);
  v11 = Interface;
  if ( Interface )
  {
    v13 = 0;
    SplWow64Telemetry::WriteDbgTraceError(
      "RPCSplWOW64SpoolerPrinterEvent",
      L"Failed to instantiate a print event object.  Error hr: 0x%x.",
      Interface);
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    *a6 = v11;
  }
  else
  {
    v12 = v15;
    v13 = TPrinterEventMgr::SpoolerPrinterEvent(v15, a2, a3, a4, a5, a6);
    if ( !v13 )
      SplWow64Telemetry::WriteDbgTraceError(
        "RPCSplWOW64SpoolerPrinterEvent",
        L"TPrinterEventMgr::SpoolerPrinterEvent failed.  Error %d.",
        *a6);
    (*(void (__fastcall **)(TPrinterEventMgr *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  TlsSetValue(g_GlobalTlsIndex, 0);
  return v13;
}

```

## disassembly

```asm
0x14000e6a0  push    rbx
0x14000e6a2  push    rbp
0x14000e6a3  push    rsi
0x14000e6a4  push    rdi
0x14000e6a5  push    r14
0x14000e6a7  sub     rsp, 40h
0x14000e6ab  mov     rdi, rdx
0x14000e6ae  mov     ebx, ecx
0x14000e6b0  mov     edx, ecx; lpTlsValue
0x14000e6b2  mov     ebp, r9d
0x14000e6b5  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e6bb  mov     r14d, r8d
0x14000e6be  call    cs:__imp_TlsSetValue
0x14000e6c4  mov     r9, rdi
0x14000e6c7  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000e6ce  mov     r8d, ebx
0x14000e6d1  lea     rcx, aRpcsplwow64spo; "RPCSplWOW64SpoolerPrinterEvent"
0x14000e6d8  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000e6dd  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000e6e4  lea     r8, [rsp+68h+var_38]; void **
0x14000e6e9  lea     rdx, ?IID_PRINTEREVENT@@3U_GUID@@A; struct _GUID *
0x14000e6f0  mov     [rsp+68h+var_38], 0
0x14000e6f9  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000e6fe  mov     ebx, eax
0x14000e700  test    eax, eax
0x14000e702  jnz     short loc_14000E761
0x14000e704  mov     rax, [rsp+68h+arg_20]
0x14000e70c  mov     r9d, ebp; unsigned int
0x14000e70f  mov     rsi, [rsp+68h+arg_28]
0x14000e717  mov     r8d, r14d; int
0x14000e71a  mov     rbx, [rsp+68h+var_38]
0x14000e71f  mov     rdx, rdi; unsigned __int16 *
0x14000e722  mov     [rsp+68h+var_40], rsi; unsigned int *
0x14000e727  mov     rcx, rbx; this
0x14000e72a  mov     [rsp+68h+var_48], rax; __int64
0x14000e72f  call    ?SpoolerPrinterEvent@TPrinterEventMgr@@QEAAHPEAGHK_JPEAK@Z; TPrinterEventMgr::SpoolerPrinterEvent(ushort *,int,ulong,__int64,ulong *)
0x14000e734  mov     edi, eax
0x14000e736  test    eax, eax
0x14000e738  jnz     short loc_14000E750
0x14000e73a  mov     r8d, [rsi]
0x14000e73d  lea     rdx, aTprintereventm; "TPrinterEventMgr::SpoolerPrinterEvent f"...
0x14000e744  lea     rcx, aRpcsplwow64spo; "RPCSplWOW64SpoolerPrinterEvent"
0x14000e74b  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e750  mov     rdx, [rbx]
0x14000e753  mov     rcx, rbx
0x14000e756  mov     rax, [rdx+10h]
0x14000e75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e75f  jmp     short loc_14000E794
0x14000e761  mov     r8d, ebx
0x14000e764  lea     rdx, aFailedToInstan; "Failed to instantiate a print event obj"...
0x14000e76b  lea     rcx, aRpcsplwow64spo; "RPCSplWOW64SpoolerPrinterEvent"
0x14000e772  xor     edi, edi
0x14000e774  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e779  mov     eax, ebx
0x14000e77b  and     eax, 1FFF0000h
0x14000e780  cmp     eax, 70000h
0x14000e785  jnz     short loc_14000E78A
0x14000e787  movzx   ebx, bx
0x14000e78a  mov     rax, [rsp+68h+arg_28]
0x14000e792  mov     [rax], ebx
0x14000e794  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e79a  xor     edx, edx; lpTlsValue
0x14000e79c  call    cs:__imp_TlsSetValue
0x14000e7a2  mov     eax, edi
0x14000e7a4  add     rsp, 40h
0x14000e7a8  pop     r14
0x14000e7aa  pop     rdi
0x14000e7ab  pop     rsi
0x14000e7ac  pop     rbp
0x14000e7ad  pop     rbx
0x14000e7ae  retn
```
