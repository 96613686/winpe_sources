# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000500c`
- end: `0x1800052c5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000493c`

## callees

- `0x180002280`
- `0x180002f34`
- `0x18000500c`
- `0x180006374`
- `0x1800074a4`
- `0x18000852c`
- `0x1800086c4`
- `0x1800556e0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000525d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000525d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800051cd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800051cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18000500c  push    rbp
0x18000500e  push    rbx
0x18000500f  push    rsi
0x180005010  push    rdi
0x180005011  push    r12
0x180005013  push    r14
0x180005015  push    r15
0x180005017  lea     rbp, [rsp-13D0h]
0x18000501f  mov     eax, 14D0h
0x180005024  call    _alloca_probe
0x180005029  sub     rsp, rax
0x18000502c  mov     rax, cs:__security_cookie
0x180005033  xor     rax, rsp
0x180005036  mov     [rbp+1400h+var_40], rax
0x18000503d  mov     rsi, r8
0x180005040  mov     edi, edx
0x180005042  mov     rbx, rcx
0x180005045  mov     r14, [rbp+1400h+arg_28]
0x18000504c  xor     edx, edx; Val
0x18000504e  mov     r8d, 98h; Size
0x180005054  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005059  call    memset_0
0x18000505e  nop
0x18000505f  xor     r12d, r12d
0x180005062  mov     [rbp+1400h+OutputString], r12w
0x18000506a  mov     [rbp+1400h+var_1440], r12b
0x18000506e  mov     rdx, [rbp+1400h+arg_30]; int
0x180005075  mov     ecx, [rdx]; this
0x180005077  mov     [rsp+1500h+var_14D8], ecx
0x18000507b  mov     eax, [rdx+4]
0x18000507e  mov     [rsp+1500h+var_14D4], eax
0x180005082  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005087  mov     r15d, eax
0x18000508a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005092  mov     ecx, r12d
0x180005095  lea     eax, [r12+8]
0x18000509a  cmp     dword ptr [rdx+8], 1
0x18000509e  cmovz   ecx, eax
0x1800050a1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800050a5  lea     ecx, [rax-7]
0x1800050a8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800050b0  inc     ecx
0x1800050b2  mov     [rsp+1500h+var_14D0], ecx
0x1800050b6  mov     rcx, [rbp+1400h+arg_38]
0x1800050bd  test    rcx, rcx
0x1800050c0  jz      short loc_1800050CD
0x1800050c2  cmp     [rcx], r12w
0x1800050c6  mov     [rsp+1500h+var_14C8], rcx
0x1800050cb  jnz     short loc_1800050D2
0x1800050cd  mov     [rsp+1500h+var_14C8], r12
0x1800050d2  call    cs:__imp_GetCurrentThreadId
0x1800050d9  nop     dword ptr [rax+rax+00h]
0x1800050de  mov     [rsp+1500h+var_14C0], eax
0x1800050e2  mov     [rsp+1500h+var_14A8], rsi
0x1800050e7  mov     [rsp+1500h+var_14A0], edi
0x1800050eb  mov     [rsp+1500h+var_149C], r15d
0x1800050f0  mov     [rsp+1500h+var_14B8], r12
0x1800050f5  mov     [rsp+1500h+var_14B0], r12
0x1800050fa  mov     [rbp+1400h+var_1458], r14
0x1800050fe  mov     [rbp+1400h+var_1450], rbx
0x180005102  mov     [rsp+1500h+var_1498], r12
0x180005107  xorps   xmm0, xmm0
0x18000510a  xor     eax, eax
0x18000510c  movups  [rbp+1400h+var_1478], xmm0
0x180005110  mov     [rbp+1400h+var_1468], rax
0x180005114  xorps   xmm1, xmm1
0x180005117  movups  [rsp+1500h+var_1490], xmm1
0x18000511c  mov     [rbp+1400h+var_1480], rax
0x180005120  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005127  test    rax, rax
0x18000512a  jz      short loc_180005137
0x18000512c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005131  mov     [rbp+1400h+var_1460], rax
0x180005135  jmp     short loc_18000513B
0x180005137  mov     [rbp+1400h+var_1460], r12
0x18000513b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005142  test    rax, rax
0x180005145  jz      short loc_180005151
0x180005147  lea     rcx, [rsp+1500h+var_14E0]
0x18000514c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005151  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005158  test    rax, rax
0x18000515b  jz      short loc_180005171
0x18000515d  mov     r8d, 400h
0x180005163  lea     rdx, [rbp+1400h+var_1440]
0x180005167  lea     rcx, [rsp+1500h+var_14E0]
0x18000516c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005171  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005178  test    rax, rax
0x18000517b  jz      short loc_180005187
0x18000517d  lea     rcx, [rsp+1500h+var_14E0]
0x180005182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005187  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000518e  test    rax, rax
0x180005191  jz      short loc_1800051A4
0x180005193  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005198  jnz     short loc_1800051A4
0x18000519a  lea     rcx, [rsp+1500h+var_14E0]
0x18000519f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051a4  cmp     [rsp+1500h+var_14D8], r12d
0x1800051a9  jge     loc_1800052BF
0x1800051af  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800051b6  jnz     short loc_1800051DD
0x1800051b8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800051bf  test    rax, rax
0x1800051c2  jz      short loc_1800051CD
0x1800051c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c9  test    al, al
0x1800051cb  jmp     short loc_1800051DB
0x1800051cd  call    cs:__imp_IsDebuggerPresent
0x1800051d4  nop     dword ptr [rax+rax+00h]
0x1800051d9  test    eax, eax
0x1800051db  jz      short loc_1800051E4
0x1800051dd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800051e2  jz      short loc_18000520A
0x1800051e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800051eb  test    rax, rax
0x1800051ee  jz      short loc_180005269
0x1800051f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800051f7  jnz     short loc_180005269
0x1800051f9  xor     r8d, r8d
0x1800051fc  xor     edx, edx
0x1800051fe  lea     rcx, [rsp+1500h+var_14E0]
0x180005203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005208  jmp     short loc_180005269
0x18000520a  mov     ebx, 800h
0x18000520f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005216  test    rax, rax
0x180005219  jz      short loc_180005238
0x18000521b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005222  jnz     short loc_180005238
0x180005224  mov     r8d, ebx
0x180005227  lea     rdx, [rbp+1400h+OutputString]
0x18000522e  lea     rcx, [rsp+1500h+var_14E0]
0x180005233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005238  cmp     [rbp+1400h+OutputString], r12w
0x180005240  jnz     short loc_180005256
0x180005242  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005247  mov     rdx, rbx; unsigned __int16 *
0x18000524a  lea     rcx, [rbp+1400h+OutputString]; this
0x180005251  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005256  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000525d  call    cs:__imp_OutputDebugStringW
0x180005264  nop     dword ptr [rax+rax+00h]
0x180005269  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000526e  jnz     short loc_180005279
0x180005270  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005277  jz      short loc_18000528B
0x180005279  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005280  test    rax, rax
0x180005283  jz      short loc_18000528B
0x180005285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528a  nop
0x18000528b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005290  jnz     short loc_1800052B4
0x180005292  mov     rcx, [rbp+1400h+var_40]
0x180005299  xor     rcx, rsp; StackCookie
0x18000529c  call    __security_check_cookie
0x1800052a1  add     rsp, 14D0h
0x1800052a8  pop     r15
0x1800052aa  pop     r14
0x1800052ac  pop     r12
0x1800052ae  pop     rdi
0x1800052af  pop     rsi
0x1800052b0  pop     rbx
0x1800052b1  pop     rbp
0x1800052b2  retn
0x1800052b4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800052b9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800052bf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
