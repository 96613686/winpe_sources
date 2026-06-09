# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008b5c`
- end: `0x180008dee`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008638`

## callees

- `0x180008b5c`
- `0x18000b2ac`
- `0x18000cc38`
- `0x18000edc4`
- `0x18000f200`
- `0x18001218a`
- `0x1800121b0`
- `0x180012240`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d8e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d8e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008d04`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008d04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c09`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag4 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  const char *v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v30 = a2;
  v26 = CurrentThreadId;
  v31 = v13;
  v29 = "wil";
  v36 = 0;
  v34 = 0;
  v27 = 0;
  v28 = a4;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag4::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180008b5c  push    rbp
0x180008b5e  push    rbx
0x180008b5f  push    rsi
0x180008b60  push    rdi
0x180008b61  push    r12
0x180008b63  push    r14
0x180008b65  push    r15
0x180008b67  lea     rbp, [rsp-13D0h]
0x180008b6f  mov     eax, 14D0h
0x180008b74  call    _alloca_probe
0x180008b79  sub     rsp, rax
0x180008b7c  mov     rax, cs:__security_cookie
0x180008b83  xor     rax, rsp
0x180008b86  mov     [rbp+1400h+var_40], rax
0x180008b8d  mov     rdi, [rbp+1400h+arg_28]
0x180008b94  mov     esi, edx
0x180008b96  mov     r14, rcx
0x180008b99  xor     edx, edx; Val
0x180008b9b  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008ba0  mov     r8d, 98h; Size
0x180008ba6  mov     r15, r9
0x180008ba9  call    memset_0
0x180008bae  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180008bb5  xor     r12d, r12d
0x180008bb8  mov     [rbp+1400h+OutputString], r12w
0x180008bc0  mov     [rbp+1400h+var_1440], r12b
0x180008bc4  mov     ecx, [rdx]; this
0x180008bc6  mov     eax, [rdx+4]
0x180008bc9  mov     [rsp+1500h+var_14D8], ecx
0x180008bcd  mov     [rsp+1500h+var_14D4], eax
0x180008bd1  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008bd6  cmp     dword ptr [rdx+8], 1
0x180008bda  mov     ebx, eax
0x180008bdc  lea     eax, [r12+8]
0x180008be1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180008be9  mov     ecx, r12d
0x180008bec  cmovz   ecx, eax
0x180008bef  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008bf3  lea     ecx, [rax-7]
0x180008bf6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008bfe  inc     ecx
0x180008c00  mov     [rsp+1500h+var_14C8], r12
0x180008c05  mov     [rsp+1500h+var_14D0], ecx
0x180008c09  call    cs:__imp_GetCurrentThreadId
0x180008c0f  xorps   xmm0, xmm0
0x180008c12  mov     [rsp+1500h+var_14A0], esi
0x180008c16  mov     [rsp+1500h+var_14C0], eax
0x180008c1a  xorps   xmm1, xmm1
0x180008c1d  lea     rax, aWil; "wil"
0x180008c24  mov     [rsp+1500h+var_149C], ebx
0x180008c28  mov     [rsp+1500h+var_14A8], rax
0x180008c2d  xor     eax, eax
0x180008c2f  mov     [rbp+1400h+var_1468], rax
0x180008c33  mov     [rbp+1400h+var_1480], rax
0x180008c37  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008c3e  mov     [rsp+1500h+var_14B8], r12
0x180008c43  mov     [rsp+1500h+var_14B0], r15
0x180008c48  mov     [rbp+1400h+var_1458], rdi
0x180008c4c  mov     [rbp+1400h+var_1450], r14
0x180008c50  mov     [rsp+1500h+var_1498], r12
0x180008c55  movups  [rbp+1400h+var_1478], xmm0
0x180008c59  movups  [rsp+1500h+var_1490], xmm1
0x180008c5e  test    rax, rax
0x180008c61  jz      short loc_180008C6E
0x180008c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c68  mov     [rbp+1400h+var_1460], rax
0x180008c6c  jmp     short loc_180008C72
0x180008c6e  mov     [rbp+1400h+var_1460], r12
0x180008c72  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008c79  test    rax, rax
0x180008c7c  jz      short loc_180008C88
0x180008c7e  lea     rcx, [rsp+1500h+var_14E0]
0x180008c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c88  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008c8f  test    rax, rax
0x180008c92  jz      short loc_180008CA8
0x180008c94  mov     r8d, 400h
0x180008c9a  lea     rdx, [rbp+1400h+var_1440]
0x180008c9e  lea     rcx, [rsp+1500h+var_14E0]
0x180008ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ca8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008caf  test    rax, rax
0x180008cb2  jz      short loc_180008CBE
0x180008cb4  lea     rcx, [rsp+1500h+var_14E0]
0x180008cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cbe  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008cc5  test    rax, rax
0x180008cc8  jz      short loc_180008CDB
0x180008cca  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008ccf  jnz     short loc_180008CDB
0x180008cd1  lea     rcx, [rsp+1500h+var_14E0]
0x180008cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdb  cmp     [rsp+1500h+var_14D8], r12d
0x180008ce0  jge     loc_180008DDD
0x180008ce6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008ced  jnz     short loc_180008D0E
0x180008cef  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008cf6  test    rax, rax
0x180008cf9  jz      short loc_180008D04
0x180008cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d00  test    al, al
0x180008d02  jmp     short loc_180008D0C
0x180008d04  call    cs:__imp_IsDebuggerPresent
0x180008d0a  test    eax, eax
0x180008d0c  jz      short loc_180008D15
0x180008d0e  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008d13  jz      short loc_180008D3B
0x180008d15  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d1c  test    rax, rax
0x180008d1f  jz      short loc_180008D94
0x180008d21  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008d28  jnz     short loc_180008D94
0x180008d2a  xor     r8d, r8d
0x180008d2d  lea     rcx, [rsp+1500h+var_14E0]
0x180008d32  xor     edx, edx
0x180008d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d39  jmp     short loc_180008D94
0x180008d3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d42  mov     ebx, 800h
0x180008d47  test    rax, rax
0x180008d4a  jz      short loc_180008D69
0x180008d4c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008d53  jnz     short loc_180008D69
0x180008d55  mov     r8d, ebx
0x180008d58  lea     rdx, [rbp+1400h+OutputString]
0x180008d5f  lea     rcx, [rsp+1500h+var_14E0]
0x180008d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d69  cmp     [rbp+1400h+OutputString], r12w
0x180008d71  jnz     short loc_180008D87
0x180008d73  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008d78  mov     rdx, rbx; unsigned __int16 *
0x180008d7b  lea     rcx, [rbp+1400h+OutputString]; this
0x180008d82  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008d87  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008d8e  call    cs:__imp_OutputDebugStringW
0x180008d94  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008d99  jnz     short loc_180008DA4
0x180008d9b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008da2  jz      short loc_180008DB5
0x180008da4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008dab  test    rax, rax
0x180008dae  jz      short loc_180008DB5
0x180008db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008db5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008dba  jnz     short loc_180008DE3
0x180008dbc  mov     rcx, [rbp+1400h+var_40]
0x180008dc3  xor     rcx, rsp; StackCookie
0x180008dc6  call    __security_check_cookie
0x180008dcb  add     rsp, 14D0h
0x180008dd2  pop     r15
0x180008dd4  pop     r14
0x180008dd6  pop     r12
0x180008dd8  pop     rdi
0x180008dd9  pop     rsi
0x180008dda  pop     rbx
0x180008ddb  pop     rbp
0x180008ddc  retn
0x180008ddd  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x180008de3  lea     rcx, [rsp+1500h+var_14E0]; this
0x180008de8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
