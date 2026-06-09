# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800051fc`
- end: `0x180005487`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004ebc`

## callees

- `0x180002610`
- `0x180002f94`
- `0x1800051fc`
- `0x180007204`
- `0x180008da0`
- `0x18000ab78`
- `0x18000b068`
- `0x18001e340`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005427`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005427`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000539d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000539d`

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
  wil::details::in1diag3 *v17; // rcx
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
  __int64 v29; // [rsp+58h] [rbp-A8h]
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
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
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
0x1800051fc  push    rbp
0x1800051fe  push    rbx
0x1800051ff  push    rsi
0x180005200  push    rdi
0x180005201  push    r12
0x180005203  push    r14
0x180005205  push    r15
0x180005207  lea     rbp, [rsp-13D0h]
0x18000520f  mov     eax, 14D0h
0x180005214  call    _alloca_probe
0x180005219  sub     rsp, rax
0x18000521c  mov     rax, cs:__security_cookie
0x180005223  xor     rax, rsp
0x180005226  mov     [rbp+1400h+var_40], rax
0x18000522d  mov     rdi, [rbp+1400h+arg_28]
0x180005234  mov     r14, r8
0x180005237  mov     esi, edx
0x180005239  mov     r15, rcx
0x18000523c  xor     edx, edx; Val
0x18000523e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005243  mov     r8d, 98h; Size
0x180005249  call    memset_0
0x18000524e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180005255  xor     r12d, r12d
0x180005258  mov     [rbp+1400h+OutputString], r12w
0x180005260  mov     [rbp+1400h+var_1440], r12b
0x180005264  mov     ecx, [rdx]; this
0x180005266  mov     eax, [rdx+4]
0x180005269  mov     [rsp+1500h+var_14D8], ecx
0x18000526d  mov     [rsp+1500h+var_14D4], eax
0x180005271  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005276  cmp     dword ptr [rdx+8], 1
0x18000527a  mov     ebx, eax
0x18000527c  lea     eax, [r12+8]
0x180005281  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005289  mov     ecx, r12d
0x18000528c  cmovz   ecx, eax
0x18000528f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005293  lea     ecx, [rax-7]
0x180005296  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000529e  inc     ecx
0x1800052a0  mov     [rsp+1500h+var_14C8], r12
0x1800052a5  mov     [rsp+1500h+var_14D0], ecx
0x1800052a9  call    cs:__imp_GetCurrentThreadId
0x1800052af  xorps   xmm0, xmm0
0x1800052b2  mov     [rsp+1500h+var_14A8], r14
0x1800052b7  mov     [rsp+1500h+var_14C0], eax
0x1800052bb  xorps   xmm1, xmm1
0x1800052be  xor     eax, eax
0x1800052c0  mov     [rsp+1500h+var_14A0], esi
0x1800052c4  mov     [rbp+1400h+var_1468], rax
0x1800052c8  mov     [rbp+1400h+var_1480], rax
0x1800052cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800052d3  mov     [rsp+1500h+var_149C], ebx
0x1800052d7  mov     [rsp+1500h+var_14B8], r12
0x1800052dc  mov     [rsp+1500h+var_14B0], r12
0x1800052e1  mov     [rbp+1400h+var_1458], rdi
0x1800052e5  mov     [rbp+1400h+var_1450], r15
0x1800052e9  mov     [rsp+1500h+var_1498], r12
0x1800052ee  movups  [rbp+1400h+var_1478], xmm0
0x1800052f2  movups  [rsp+1500h+var_1490], xmm1
0x1800052f7  test    rax, rax
0x1800052fa  jz      short loc_180005307
0x1800052fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005301  mov     [rbp+1400h+var_1460], rax
0x180005305  jmp     short loc_18000530B
0x180005307  mov     [rbp+1400h+var_1460], r12
0x18000530b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005312  test    rax, rax
0x180005315  jz      short loc_180005321
0x180005317  lea     rcx, [rsp+1500h+var_14E0]
0x18000531c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005321  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005328  test    rax, rax
0x18000532b  jz      short loc_180005341
0x18000532d  mov     r8d, 400h
0x180005333  lea     rdx, [rbp+1400h+var_1440]
0x180005337  lea     rcx, [rsp+1500h+var_14E0]
0x18000533c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005341  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005348  test    rax, rax
0x18000534b  jz      short loc_180005357
0x18000534d  lea     rcx, [rsp+1500h+var_14E0]
0x180005352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005357  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000535e  test    rax, rax
0x180005361  jz      short loc_180005374
0x180005363  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005368  jnz     short loc_180005374
0x18000536a  lea     rcx, [rsp+1500h+var_14E0]
0x18000536f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005374  cmp     [rsp+1500h+var_14D8], r12d
0x180005379  jge     loc_180005476
0x18000537f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005386  jnz     short loc_1800053A7
0x180005388  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000538f  test    rax, rax
0x180005392  jz      short loc_18000539D
0x180005394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005399  test    al, al
0x18000539b  jmp     short loc_1800053A5
0x18000539d  call    cs:__imp_IsDebuggerPresent
0x1800053a3  test    eax, eax
0x1800053a5  jz      short loc_1800053AE
0x1800053a7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800053ac  jz      short loc_1800053D4
0x1800053ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800053b5  test    rax, rax
0x1800053b8  jz      short loc_18000542D
0x1800053ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800053c1  jnz     short loc_18000542D
0x1800053c3  xor     r8d, r8d
0x1800053c6  lea     rcx, [rsp+1500h+var_14E0]
0x1800053cb  xor     edx, edx
0x1800053cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d2  jmp     short loc_18000542D
0x1800053d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800053db  mov     ebx, 800h
0x1800053e0  test    rax, rax
0x1800053e3  jz      short loc_180005402
0x1800053e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800053ec  jnz     short loc_180005402
0x1800053ee  mov     r8d, ebx
0x1800053f1  lea     rdx, [rbp+1400h+OutputString]
0x1800053f8  lea     rcx, [rsp+1500h+var_14E0]
0x1800053fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005402  cmp     [rbp+1400h+OutputString], r12w
0x18000540a  jnz     short loc_180005420
0x18000540c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005411  mov     rdx, rbx; unsigned __int16 *
0x180005414  lea     rcx, [rbp+1400h+OutputString]; this
0x18000541b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005420  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005427  call    cs:__imp_OutputDebugStringW
0x18000542d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005432  jnz     short loc_18000543D
0x180005434  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000543b  jz      short loc_18000544E
0x18000543d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005444  test    rax, rax
0x180005447  jz      short loc_18000544E
0x180005449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000544e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005453  jnz     short loc_18000547C
0x180005455  mov     rcx, [rbp+1400h+var_40]
0x18000545c  xor     rcx, rsp; StackCookie
0x18000545f  call    __security_check_cookie
0x180005464  add     rsp, 14D0h
0x18000546b  pop     r15
0x18000546d  pop     r14
0x18000546f  pop     r12
0x180005471  pop     rdi
0x180005472  pop     rsi
0x180005473  pop     rbx
0x180005474  pop     rbp
0x180005475  retn
0x180005476  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000547c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005481  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
