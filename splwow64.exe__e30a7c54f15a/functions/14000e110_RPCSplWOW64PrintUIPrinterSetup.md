# RPCSplWOW64PrintUIPrinterSetup

- ea: `0x14000e110`
- end: `0x14000e280`
- name: `RPCSplWOW64PrintUIPrinterSetup`
- size: `368`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, LPVOID lpTlsValue, void *, unsigned int, unsigned int, unsigned __int16 *, unsigned int *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000c2b4`
- `0x14000e110`
- `0x14000e7b8`
- `0x14000f5c4`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000e12c`
- `KERNEL32!TlsSetValue` at `0x14000e271`
- `KERNEL32!TlsSetValue` at `0x14000e12c`
- `KERNEL32!TlsSetValue` at `0x14000e271`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e263`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e263`

## string_xrefs

- `0x14000e145`: `clientProcessID %u`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64PrintUIPrinterSetup(
        PRPC_ASYNC_STATE pAsync,
        LPVOID lpTlsValue,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int *a7,
        unsigned __int16 *a8)
{
  unsigned int v8; // ebx
  __int64 v12; // r8
  unsigned int Interface; // eax
  unsigned int v14; // ebx
  TPrintUIMgr *v15; // rbx
  unsigned int v16; // eax
  TPrintUIMgr *v18; // [rsp+40h] [rbp-38h] BYREF
  unsigned int Reply; // [rsp+88h] [rbp+10h] BYREF

  v8 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    SplWow64Telemetry::WriteDbgTraceInfo("RPCSplWOW64PrintUIPrinterSetup", L"clientProcessID %u", v8);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v12, v8);
  }
  v18 = 0;
  Reply = 0;
  Interface = TLoad64BitDllsMgr::QueryInterface(pGLdrObj, &IID_PRINTUIOPERATIONS, (void **)&v18);
  v14 = Interface;
  if ( Interface )
  {
    SplWow64Telemetry::WriteDbgTraceError(
      "RPCSplWOW64PrintUIPrinterSetup",
      L"Failed to instantiate a print UI object.  Error hr: 0x%x.",
      Interface);
    if ( (v14 & 0x1FFF0000) == 0x70000 )
      v14 = (unsigned __int16)v14;
    Reply = v14;
  }
  else
  {
    v15 = v18;
    v16 = TPrintUIMgr::PrinterSetup(v18, a3, a4, a5, a6, a7, a8);
    Reply = v16;
    if ( v16 )
      SplWow64Telemetry::WriteDbgTraceError(
        "RPCSplWOW64PrintUIPrinterSetup",
        L"TPrintUIMgr::PrinterSetup failed.  Error %d.",
        v16);
    (*(void (__fastcall **)(TPrintUIMgr *))(*(_QWORD *)v15 + 16LL))(v15);
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000e110  push    rbx
0x14000e112  push    rbp
0x14000e113  push    rsi
0x14000e114  push    rdi
0x14000e115  sub     rsp, 58h
0x14000e119  mov     ebx, edx
0x14000e11b  mov     rdi, rcx
0x14000e11e  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e124  mov     esi, r9d
0x14000e127  mov     edx, edx; lpTlsValue
0x14000e129  mov     rbp, r8
0x14000e12c  call    cs:__imp_TlsSetValue
0x14000e132  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x14000e139  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x14000e13e  test    al, al
0x14000e140  jz      short loc_14000E15A
0x14000e142  mov     r8d, ebx
0x14000e145  lea     rdx, aClientprocessi; "clientProcessID %u"
0x14000e14c  lea     rcx, aRpcsplwow64pri; "RPCSplWOW64PrintUIPrinterSetup"
0x14000e153  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000e158  jmp     short loc_14000E184
0x14000e15a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e161  lea     rax, WPP_GLOBAL_Control
0x14000e168  cmp     rcx, rax
0x14000e16b  jz      short loc_14000E184
0x14000e16d  test    byte ptr [rcx+1Ch], 2
0x14000e171  jz      short loc_14000E184
0x14000e173  mov     rcx, [rcx+10h]
0x14000e177  mov     edx, 0Ah
0x14000e17c  mov     r9d, ebx
0x14000e17f  call    WPP_SF_D
0x14000e184  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000e18b  lea     r8, [rsp+78h+var_38]; void **
0x14000e190  lea     rdx, ?IID_PRINTUIOPERATIONS@@3U_GUID@@A; struct _GUID *
0x14000e197  mov     [rsp+78h+var_38], 0
0x14000e1a0  mov     [rsp+78h+Reply], 0
0x14000e1ab  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000e1b0  mov     ebx, eax
0x14000e1b2  test    eax, eax
0x14000e1b4  jnz     short loc_14000E22A
0x14000e1b6  mov     rax, [rsp+78h+arg_38]
0x14000e1be  mov     r8d, esi; unsigned int
0x14000e1c1  mov     rbx, [rsp+78h+var_38]
0x14000e1c6  mov     rdx, rbp; void *
0x14000e1c9  mov     r9d, [rsp+78h+arg_20]; unsigned int
0x14000e1d1  mov     rcx, rbx; this
0x14000e1d4  mov     [rsp+78h+var_48], rax; unsigned __int16 *
0x14000e1d9  mov     rax, [rsp+78h+arg_30]
0x14000e1e1  mov     [rsp+78h+var_50], rax; unsigned int *
0x14000e1e6  mov     rax, [rsp+78h+arg_28]
0x14000e1ee  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x14000e1f3  call    ?PrinterSetup@TPrintUIMgr@@QEAAKPEAXIIPEAGPEAIPEBG@Z; TPrintUIMgr::PrinterSetup(void *,uint,uint,ushort *,uint *,ushort const *)
0x14000e1f8  mov     [rsp+78h+Reply], eax
0x14000e1ff  test    eax, eax
0x14000e201  jz      short loc_14000E219
0x14000e203  mov     r8d, eax
0x14000e206  lea     rdx, aTprintuimgrPri; "TPrintUIMgr::PrinterSetup failed.  Erro"...
0x14000e20d  lea     rcx, aRpcsplwow64pri; "RPCSplWOW64PrintUIPrinterSetup"
0x14000e214  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e219  mov     rax, [rbx]
0x14000e21c  mov     rcx, rbx
0x14000e21f  mov     rax, [rax+10h]
0x14000e223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e228  jmp     short loc_14000E258
0x14000e22a  mov     r8d, ebx
0x14000e22d  lea     rdx, aFailedToInstan_2; "Failed to instantiate a print UI object"...
0x14000e234  lea     rcx, aRpcsplwow64pri; "RPCSplWOW64PrintUIPrinterSetup"
0x14000e23b  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e240  mov     eax, ebx
0x14000e242  and     eax, 1FFF0000h
0x14000e247  cmp     eax, 70000h
0x14000e24c  jnz     short loc_14000E251
0x14000e24e  movzx   ebx, bx
0x14000e251  mov     [rsp+78h+Reply], ebx
0x14000e258  lea     rdx, [rsp+78h+Reply]; Reply
0x14000e260  mov     rcx, rdi; pAsync
0x14000e263  call    cs:__imp_RpcAsyncCompleteCall
0x14000e269  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e26f  xor     edx, edx; lpTlsValue
0x14000e271  call    cs:__imp_TlsSetValue
0x14000e277  add     rsp, 58h
0x14000e27b  pop     rdi
0x14000e27c  pop     rsi
0x14000e27d  pop     rbp
0x14000e27e  pop     rbx
0x14000e27f  retn
```
