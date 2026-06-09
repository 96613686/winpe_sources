# RPCSplWOW64PrintUIDocumentDefaults

- ea: `0x14000ddd0`
- end: `0x14000def7`
- name: `RPCSplWOW64PrintUIDocumentDefaults`
- size: `295`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, LPVOID lpTlsValue@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000ddd0`
- `0x14000f42c`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000ddec`
- `KERNEL32!TlsSetValue` at `0x14000dee8`
- `KERNEL32!TlsSetValue` at `0x14000ddec`
- `KERNEL32!TlsSetValue` at `0x14000dee8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000deda`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000deda`

## string_xrefs

- `0x14000ddf5`: `clientProcessID %u pszPrinterName %ws`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64PrintUIDocumentDefaults(
        PRPC_ASYNC_STATE pAsync,
        LPVOID lpTlsValue,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
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
    "RPCSplWOW64PrintUIDocumentDefaults",
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
      "RPCSplWOW64PrintUIDocumentDefaults",
      L"Failed to instantiate a print UI object.  Error hr: 0x%x.",
      v10);
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    Reply = v11;
  }
  else
  {
    v12 = v15;
    v13 = TPrintUIMgr::PrintUIMethod((__int64)v15, "vDocumentDefaults", a3, a4, a5, a6);
    Reply = v13;
    if ( v13 )
      SplWow64Telemetry::WriteDbgTraceError(
        "RPCSplWOW64PrintUIDocumentDefaults",
        L"TPrintUIMgr::DocumentDefaults failed.  Error %d.",
        v13);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000ddd0  push    rbx
0x14000ddd2  push    rbp
0x14000ddd3  push    rsi
0x14000ddd4  push    rdi
0x14000ddd5  sub     rsp, 58h
0x14000ddd9  mov     ebx, edx
0x14000dddb  mov     rdi, rcx
0x14000ddde  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000dde4  mov     rsi, r9
0x14000dde7  mov     edx, edx; lpTlsValue
0x14000dde9  mov     rbp, r8
0x14000ddec  call    cs:__imp_TlsSetValue
0x14000ddf2  mov     r9, rsi
0x14000ddf5  lea     rdx, aClientprocessi_1; "clientProcessID %u pszPrinterName %ws"
0x14000ddfc  mov     r8d, ebx
0x14000ddff  lea     rcx, aRpcsplwow64pri_2; "RPCSplWOW64PrintUIDocumentDefaults"
0x14000de06  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000de0b  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000de12  lea     r8, [rsp+78h+var_38]; void **
0x14000de17  lea     rdx, ?IID_PRINTUIOPERATIONS@@3U_GUID@@A; struct _GUID *
0x14000de1e  mov     [rsp+78h+var_38], 0
0x14000de27  mov     [rsp+78h+Reply], 0
0x14000de32  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000de37  mov     ebx, eax
0x14000de39  test    eax, eax
0x14000de3b  jnz     short loc_14000DEA1
0x14000de3d  mov     rax, [rsp+78h+arg_28]
0x14000de45  lea     rdx, aVdocumentdefau; "vDocumentDefaults"
0x14000de4c  mov     rbx, [rsp+78h+var_38]
0x14000de51  mov     r9, rsi
0x14000de54  mov     [rsp+78h+var_50], rax
0x14000de59  mov     r8, rbp
0x14000de5c  mov     eax, [rsp+78h+arg_20]
0x14000de63  mov     rcx, rbx
0x14000de66  mov     [rsp+78h+var_58], eax
0x14000de6a  call    ?PrintUIMethod@TPrintUIMgr@@QEAAKPEBDPEAXPEBGH_JW4EPrintUIOp@1@@Z; TPrintUIMgr::PrintUIMethod(char const *,void *,ushort const *,int,__int64,TPrintUIMgr::EPrintUIOp)
0x14000de6f  mov     [rsp+78h+Reply], eax
0x14000de76  test    eax, eax
0x14000de78  jz      short loc_14000DE90
0x14000de7a  mov     r8d, eax
0x14000de7d  lea     rdx, aTprintuimgrDoc; "TPrintUIMgr::DocumentDefaults failed.  "...
0x14000de84  lea     rcx, aRpcsplwow64pri_2; "RPCSplWOW64PrintUIDocumentDefaults"
0x14000de8b  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000de90  mov     rax, [rbx]
0x14000de93  mov     rcx, rbx
0x14000de96  mov     rax, [rax+10h]
0x14000de9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de9f  jmp     short loc_14000DECF
0x14000dea1  mov     r8d, ebx
0x14000dea4  lea     rdx, aFailedToInstan_2; "Failed to instantiate a print UI object"...
0x14000deab  lea     rcx, aRpcsplwow64pri_2; "RPCSplWOW64PrintUIDocumentDefaults"
0x14000deb2  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000deb7  mov     eax, ebx
0x14000deb9  and     eax, 1FFF0000h
0x14000debe  cmp     eax, 70000h
0x14000dec3  jnz     short loc_14000DEC8
0x14000dec5  movzx   ebx, bx
0x14000dec8  mov     [rsp+78h+Reply], ebx
0x14000decf  lea     rdx, [rsp+78h+Reply]; Reply
0x14000ded7  mov     rcx, rdi; pAsync
0x14000deda  call    cs:__imp_RpcAsyncCompleteCall
0x14000dee0  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000dee6  xor     edx, edx; lpTlsValue
0x14000dee8  call    cs:__imp_TlsSetValue
0x14000deee  add     rsp, 58h
0x14000def2  pop     rdi
0x14000def3  pop     rsi
0x14000def4  pop     rbp
0x14000def5  pop     rbx
0x14000def6  retn
```
