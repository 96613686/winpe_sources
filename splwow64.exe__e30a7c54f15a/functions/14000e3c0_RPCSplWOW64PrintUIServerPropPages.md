# RPCSplWOW64PrintUIServerPropPages

- ea: `0x14000e3c0`
- end: `0x14000e520`
- name: `RPCSplWOW64PrintUIServerPropPages`
- size: `352`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, LPVOID lpTlsValue@<rdx>, int, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140007a9c`
- `0x1400085d8`
- `0x1400086e0`
- `0x14000c2b4`
- `0x14000e3c0`
- `0x14000e7b8`
- `0x14000f42c`
- `0x140016010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x14000e3dc`
- `KERNEL32!TlsSetValue` at `0x14000e511`
- `KERNEL32!TlsSetValue` at `0x14000e3dc`
- `KERNEL32!TlsSetValue` at `0x14000e511`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e503`
- `RPCRT4!RpcAsyncCompleteCall` at `0x14000e503`

## string_xrefs

- `0x14000e3f5`: `clientProcessID %u`

## pseudocode

```c
BOOL __fastcall RPCSplWOW64PrintUIServerPropPages(
        PRPC_ASYNC_STATE pAsync,
        LPVOID lpTlsValue,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned int v6; // ebx
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // ebx
  void *v13; // rbx
  unsigned int v14; // eax
  void *v16; // [rsp+40h] [rbp-38h] BYREF
  unsigned int Reply; // [rsp+88h] [rbp+10h] BYREF

  v6 = (unsigned int)lpTlsValue;
  TlsSetValue(g_GlobalTlsIndex, (LPVOID)(unsigned int)lpTlsValue);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
  {
    SplWow64Telemetry::WriteDbgTraceInfo("RPCSplWOW64PrintUIServerPropPages", L"clientProcessID %u", v6);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v10, v6);
  }
  v16 = 0;
  Reply = 0;
  v11 = TLoad64BitDllsMgr::QueryInterface(pGLdrObj, &IID_PRINTUIOPERATIONS, &v16);
  v12 = v11;
  if ( v11 )
  {
    SplWow64Telemetry::WriteDbgTraceError(
      "RPCSplWOW64PrintUIServerPropPages",
      L"Failed to instantiate a print UI object.  Error hr: 0x%x.",
      v11);
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v12;
    Reply = v12;
  }
  else
  {
    v13 = v16;
    v14 = TPrintUIMgr::PrintUIMethod((__int64)v16, "vServerPropPages", a3, a4, a5, a6);
    Reply = v14;
    if ( v14 )
      SplWow64Telemetry::WriteDbgTraceError(
        "RPCSplWOW64PrintUIServerPropPages",
        L"TPrintUIMgr::ServerPropPages failed.  Error %d.",
        v14);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  RpcAsyncCompleteCall(pAsync, &Reply);
  return TlsSetValue(g_GlobalTlsIndex, 0);
}

```

## disassembly

```asm
0x14000e3c0  push    rbx
0x14000e3c2  push    rbp
0x14000e3c3  push    rsi
0x14000e3c4  push    rdi
0x14000e3c5  sub     rsp, 58h
0x14000e3c9  mov     ebx, edx
0x14000e3cb  mov     rdi, rcx
0x14000e3ce  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e3d4  mov     rsi, r9
0x14000e3d7  mov     edx, edx; lpTlsValue
0x14000e3d9  mov     rbp, r8
0x14000e3dc  call    cs:__imp_TlsSetValue
0x14000e3e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x14000e3e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x14000e3ee  test    al, al
0x14000e3f0  jz      short loc_14000E40A
0x14000e3f2  mov     r8d, ebx
0x14000e3f5  lea     rdx, aClientprocessi; "clientProcessID %u"
0x14000e3fc  lea     rcx, aRpcsplwow64pri_3; "RPCSplWOW64PrintUIServerPropPages"
0x14000e403  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14000e408  jmp     short loc_14000E434
0x14000e40a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e411  lea     rax, WPP_GLOBAL_Control
0x14000e418  cmp     rcx, rax
0x14000e41b  jz      short loc_14000E434
0x14000e41d  test    byte ptr [rcx+1Ch], 2
0x14000e421  jz      short loc_14000E434
0x14000e423  mov     rcx, [rcx+10h]
0x14000e427  mov     edx, 0Bh
0x14000e42c  mov     r9d, ebx
0x14000e42f  call    WPP_SF_D
0x14000e434  mov     rcx, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; this
0x14000e43b  lea     r8, [rsp+78h+var_38]; void **
0x14000e440  lea     rdx, ?IID_PRINTUIOPERATIONS@@3U_GUID@@A; struct _GUID *
0x14000e447  mov     [rsp+78h+var_38], 0
0x14000e450  mov     [rsp+78h+Reply], 0
0x14000e45b  call    ?QueryInterface@TLoad64BitDllsMgr@@QEAAJAEBU_GUID@@PEAPEAX@Z; TLoad64BitDllsMgr::QueryInterface(_GUID const &,void * *)
0x14000e460  mov     ebx, eax
0x14000e462  test    eax, eax
0x14000e464  jnz     short loc_14000E4CA
0x14000e466  mov     rax, [rsp+78h+arg_28]
0x14000e46e  lea     rdx, aVserverproppag; "vServerPropPages"
0x14000e475  mov     rbx, [rsp+78h+var_38]
0x14000e47a  mov     r9, rsi
0x14000e47d  mov     [rsp+78h+var_50], rax
0x14000e482  mov     r8, rbp
0x14000e485  mov     eax, [rsp+78h+arg_20]
0x14000e48c  mov     rcx, rbx
0x14000e48f  mov     [rsp+78h+var_58], eax
0x14000e493  call    ?PrintUIMethod@TPrintUIMgr@@QEAAKPEBDPEAXPEBGH_JW4EPrintUIOp@1@@Z; TPrintUIMgr::PrintUIMethod(char const *,void *,ushort const *,int,__int64,TPrintUIMgr::EPrintUIOp)
0x14000e498  mov     [rsp+78h+Reply], eax
0x14000e49f  test    eax, eax
0x14000e4a1  jz      short loc_14000E4B9
0x14000e4a3  mov     r8d, eax
0x14000e4a6  lea     rdx, aTprintuimgrSer; "TPrintUIMgr::ServerPropPages failed.  E"...
0x14000e4ad  lea     rcx, aRpcsplwow64pri_3; "RPCSplWOW64PrintUIServerPropPages"
0x14000e4b4  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e4b9  mov     rax, [rbx]
0x14000e4bc  mov     rcx, rbx
0x14000e4bf  mov     rax, [rax+10h]
0x14000e4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4c8  jmp     short loc_14000E4F8
0x14000e4ca  mov     r8d, ebx
0x14000e4cd  lea     rdx, aFailedToInstan_2; "Failed to instantiate a print UI object"...
0x14000e4d4  lea     rcx, aRpcsplwow64pri_3; "RPCSplWOW64PrintUIServerPropPages"
0x14000e4db  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e4e0  mov     eax, ebx
0x14000e4e2  and     eax, 1FFF0000h
0x14000e4e7  cmp     eax, 70000h
0x14000e4ec  jnz     short loc_14000E4F1
0x14000e4ee  movzx   ebx, bx
0x14000e4f1  mov     [rsp+78h+Reply], ebx
0x14000e4f8  lea     rdx, [rsp+78h+Reply]; Reply
0x14000e500  mov     rcx, rdi; pAsync
0x14000e503  call    cs:__imp_RpcAsyncCompleteCall
0x14000e509  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x14000e50f  xor     edx, edx; lpTlsValue
0x14000e511  call    cs:__imp_TlsSetValue
0x14000e517  add     rsp, 58h
0x14000e51b  pop     rdi
0x14000e51c  pop     rsi
0x14000e51d  pop     rbp
0x14000e51e  pop     rbx
0x14000e51f  retn
```
