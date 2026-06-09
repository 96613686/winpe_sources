# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004bb8`
- end: `0x180004e45`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004888`

## callees

- `0x1800027f0`
- `0x1800033b4`
- `0x180004bb8`
- `0x1800067d4`
- `0x1800082c0`
- `0x180009348`
- `0x1800095c4`
- `0x1800105e0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c66`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d5a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d5a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004de4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004de4`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180004bb8  push    rbp
0x180004bba  push    rbx
0x180004bbb  push    rsi
0x180004bbc  push    rdi
0x180004bbd  push    r12
0x180004bbf  push    r14
0x180004bc1  push    r15
0x180004bc3  lea     rbp, [rsp-13D0h]
0x180004bcb  mov     eax, 14D0h
0x180004bd0  call    _alloca_probe
0x180004bd5  sub     rsp, rax
0x180004bd8  mov     rax, cs:__security_cookie
0x180004bdf  xor     rax, rsp
0x180004be2  mov     [rbp+1400h+var_40], rax
0x180004be9  mov     r14, r8
0x180004bec  mov     esi, edx
0x180004bee  mov     r15, rcx
0x180004bf1  mov     rdi, [rbp+1400h+arg_28]
0x180004bf8  xor     edx, edx; Val
0x180004bfa  mov     r8d, 98h; Size
0x180004c00  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004c05  call    memset_0
0x180004c0a  nop
0x180004c0b  xor     r12d, r12d
0x180004c0e  mov     [rbp+1400h+OutputString], r12w
0x180004c16  mov     [rbp+1400h+var_1440], r12b
0x180004c1a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004c21  mov     ecx, [rdx]; this
0x180004c23  mov     [rsp+1500h+var_14D8], ecx
0x180004c27  mov     eax, [rdx+4]
0x180004c2a  mov     [rsp+1500h+var_14D4], eax
0x180004c2e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004c33  mov     ebx, eax
0x180004c35  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004c3d  mov     ecx, r12d
0x180004c40  lea     eax, [r12+8]
0x180004c45  cmp     dword ptr [rdx+8], 1
0x180004c49  cmovz   ecx, eax
0x180004c4c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004c50  lea     ecx, [rax-7]
0x180004c53  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004c5b  inc     ecx
0x180004c5d  mov     [rsp+1500h+var_14D0], ecx
0x180004c61  mov     [rsp+1500h+var_14C8], r12
0x180004c66  call    cs:__imp_GetCurrentThreadId
0x180004c6c  mov     [rsp+1500h+var_14C0], eax
0x180004c70  mov     [rsp+1500h+var_14A8], r14
0x180004c75  mov     [rsp+1500h+var_14A0], esi
0x180004c79  mov     [rsp+1500h+var_149C], ebx
0x180004c7d  mov     [rsp+1500h+var_14B8], r12
0x180004c82  mov     [rsp+1500h+var_14B0], r12
0x180004c87  mov     [rbp+1400h+var_1458], rdi
0x180004c8b  mov     [rbp+1400h+var_1450], r15
0x180004c8f  mov     [rsp+1500h+var_1498], r12
0x180004c94  xorps   xmm0, xmm0
0x180004c97  xor     eax, eax
0x180004c99  movups  [rbp+1400h+var_1478], xmm0
0x180004c9d  mov     [rbp+1400h+var_1468], rax
0x180004ca1  xorps   xmm1, xmm1
0x180004ca4  movups  [rsp+1500h+var_1490], xmm1
0x180004ca9  mov     [rbp+1400h+var_1480], rax
0x180004cad  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004cb4  test    rax, rax
0x180004cb7  jz      short loc_180004CC4
0x180004cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cbe  mov     [rbp+1400h+var_1460], rax
0x180004cc2  jmp     short loc_180004CC8
0x180004cc4  mov     [rbp+1400h+var_1460], r12
0x180004cc8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ccf  test    rax, rax
0x180004cd2  jz      short loc_180004CDE
0x180004cd4  lea     rcx, [rsp+1500h+var_14E0]
0x180004cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cde  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ce5  test    rax, rax
0x180004ce8  jz      short loc_180004CFE
0x180004cea  mov     r8d, 400h
0x180004cf0  lea     rdx, [rbp+1400h+var_1440]
0x180004cf4  lea     rcx, [rsp+1500h+var_14E0]
0x180004cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cfe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004d05  test    rax, rax
0x180004d08  jz      short loc_180004D14
0x180004d0a  lea     rcx, [rsp+1500h+var_14E0]
0x180004d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d14  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004d1b  test    rax, rax
0x180004d1e  jz      short loc_180004D31
0x180004d20  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004d25  jnz     short loc_180004D31
0x180004d27  lea     rcx, [rsp+1500h+var_14E0]
0x180004d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d31  cmp     [rsp+1500h+var_14D8], r12d
0x180004d36  jge     loc_180004E3F
0x180004d3c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004d43  jnz     short loc_180004D64
0x180004d45  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004d4c  test    rax, rax
0x180004d4f  jz      short loc_180004D5A
0x180004d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d56  test    al, al
0x180004d58  jmp     short loc_180004D62
0x180004d5a  call    cs:__imp_IsDebuggerPresent
0x180004d60  test    eax, eax
0x180004d62  jz      short loc_180004D6B
0x180004d64  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004d69  jz      short loc_180004D91
0x180004d6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d72  test    rax, rax
0x180004d75  jz      short loc_180004DEA
0x180004d77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004d7e  jnz     short loc_180004DEA
0x180004d80  xor     r8d, r8d
0x180004d83  xor     edx, edx
0x180004d85  lea     rcx, [rsp+1500h+var_14E0]
0x180004d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8f  jmp     short loc_180004DEA
0x180004d91  mov     ebx, 800h
0x180004d96  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d9d  test    rax, rax
0x180004da0  jz      short loc_180004DBF
0x180004da2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004da9  jnz     short loc_180004DBF
0x180004dab  mov     r8d, ebx
0x180004dae  lea     rdx, [rbp+1400h+OutputString]
0x180004db5  lea     rcx, [rsp+1500h+var_14E0]
0x180004dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dbf  cmp     [rbp+1400h+OutputString], r12w
0x180004dc7  jnz     short loc_180004DDD
0x180004dc9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004dce  mov     rdx, rbx; unsigned __int16 *
0x180004dd1  lea     rcx, [rbp+1400h+OutputString]; this
0x180004dd8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004ddd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004de4  call    cs:__imp_OutputDebugStringW
0x180004dea  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004def  jnz     short loc_180004DFA
0x180004df1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004df8  jz      short loc_180004E0C
0x180004dfa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004e01  test    rax, rax
0x180004e04  jz      short loc_180004E0C
0x180004e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e0b  nop
0x180004e0c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004e11  jnz     short loc_180004E34
0x180004e13  mov     rcx, [rbp+1400h+var_40]
0x180004e1a  xor     rcx, rsp; StackCookie
0x180004e1d  call    __security_check_cookie
0x180004e22  add     rsp, 14D0h
0x180004e29  pop     r15
0x180004e2b  pop     r14
0x180004e2d  pop     r12
0x180004e2f  pop     rdi
0x180004e30  pop     rsi
0x180004e31  pop     rbx
0x180004e32  pop     rbp
0x180004e33  retn
0x180004e34  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004e39  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004e3f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
