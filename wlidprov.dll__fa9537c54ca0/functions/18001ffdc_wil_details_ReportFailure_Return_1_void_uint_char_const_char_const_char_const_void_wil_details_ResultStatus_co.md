# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001ffdc`
- end: `0x180020282`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180015b4c`

## callees

- `0x18001a0d0`
- `0x18001ac3c`
- `0x18001ffdc`
- `0x180020e64`
- `0x180021c10`
- `0x1800226d8`
- `0x180022894`
- `0x180053560`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020197`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180020197`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020221`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020221`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800200a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800200a2`

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
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x18001ffdc  push    rbp
0x18001ffde  push    rbx
0x18001ffdf  push    rsi
0x18001ffe0  push    rdi
0x18001ffe1  push    r12
0x18001ffe3  push    r14
0x18001ffe5  push    r15
0x18001ffe7  lea     rbp, [rsp-13D0h]
0x18001ffef  mov     eax, 14D0h
0x18001fff4  call    _alloca_probe
0x18001fff9  sub     rsp, rax
0x18001fffc  mov     rax, cs:__security_cookie
0x180020003  xor     rax, rsp
0x180020006  mov     [rbp+1400h+var_40], rax
0x18002000d  mov     rsi, r8
0x180020010  mov     edi, edx
0x180020012  mov     rbx, rcx
0x180020015  mov     r14, [rbp+1400h+arg_28]
0x18002001c  xor     edx, edx; Val
0x18002001e  mov     r8d, 98h; Size
0x180020024  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180020029  call    memset_0
0x18002002e  nop
0x18002002f  xor     r12d, r12d
0x180020032  mov     [rbp+1400h+OutputString], r12w
0x18002003a  mov     [rbp+1400h+var_1440], r12b
0x18002003e  mov     rdx, [rbp+1400h+arg_30]; int
0x180020045  mov     ecx, [rdx]; this
0x180020047  mov     [rsp+1500h+var_14D8], ecx
0x18002004b  mov     eax, [rdx+4]
0x18002004e  mov     [rsp+1500h+var_14D4], eax
0x180020052  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180020057  mov     r15d, eax
0x18002005a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180020062  mov     ecx, r12d
0x180020065  lea     eax, [r12+8]
0x18002006a  cmp     dword ptr [rdx+8], 1
0x18002006e  cmovz   ecx, eax
0x180020071  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180020075  lea     ecx, [rax-7]
0x180020078  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180020080  inc     ecx
0x180020082  mov     [rsp+1500h+var_14D0], ecx
0x180020086  mov     rcx, [rbp+1400h+arg_38]
0x18002008d  test    rcx, rcx
0x180020090  jz      short loc_18002009D
0x180020092  cmp     [rcx], r12w
0x180020096  mov     [rsp+1500h+var_14C8], rcx
0x18002009b  jnz     short loc_1800200A2
0x18002009d  mov     [rsp+1500h+var_14C8], r12
0x1800200a2  call    cs:__imp_GetCurrentThreadId
0x1800200a8  mov     [rsp+1500h+var_14C0], eax
0x1800200ac  mov     [rsp+1500h+var_14A8], rsi
0x1800200b1  mov     [rsp+1500h+var_14A0], edi
0x1800200b5  mov     [rsp+1500h+var_149C], r15d
0x1800200ba  mov     [rsp+1500h+var_14B8], r12
0x1800200bf  mov     [rsp+1500h+var_14B0], r12
0x1800200c4  mov     [rbp+1400h+var_1458], r14
0x1800200c8  mov     [rbp+1400h+var_1450], rbx
0x1800200cc  mov     [rsp+1500h+var_1498], r12
0x1800200d1  xorps   xmm0, xmm0
0x1800200d4  xor     eax, eax
0x1800200d6  movups  [rbp+1400h+var_1478], xmm0
0x1800200da  mov     [rbp+1400h+var_1468], rax
0x1800200de  xorps   xmm1, xmm1
0x1800200e1  movups  [rsp+1500h+var_1490], xmm1
0x1800200e6  mov     [rbp+1400h+var_1480], rax
0x1800200ea  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800200f1  test    rax, rax
0x1800200f4  jz      short loc_180020101
0x1800200f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200fb  mov     [rbp+1400h+var_1460], rax
0x1800200ff  jmp     short loc_180020105
0x180020101  mov     [rbp+1400h+var_1460], r12
0x180020105  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002010c  test    rax, rax
0x18002010f  jz      short loc_18002011B
0x180020111  lea     rcx, [rsp+1500h+var_14E0]
0x180020116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002011b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180020122  test    rax, rax
0x180020125  jz      short loc_18002013B
0x180020127  mov     r8d, 400h
0x18002012d  lea     rdx, [rbp+1400h+var_1440]
0x180020131  lea     rcx, [rsp+1500h+var_14E0]
0x180020136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002013b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020142  test    rax, rax
0x180020145  jz      short loc_180020151
0x180020147  lea     rcx, [rsp+1500h+var_14E0]
0x18002014c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020151  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020158  test    rax, rax
0x18002015b  jz      short loc_18002016E
0x18002015d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180020162  jnz     short loc_18002016E
0x180020164  lea     rcx, [rsp+1500h+var_14E0]
0x180020169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002016e  cmp     [rsp+1500h+var_14D8], r12d
0x180020173  jge     loc_18002027C
0x180020179  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180020180  jnz     short loc_1800201A1
0x180020182  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180020189  test    rax, rax
0x18002018c  jz      short loc_180020197
0x18002018e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020193  test    al, al
0x180020195  jmp     short loc_18002019F
0x180020197  call    cs:__imp_IsDebuggerPresent
0x18002019d  test    eax, eax
0x18002019f  jz      short loc_1800201A8
0x1800201a1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800201a6  jz      short loc_1800201CE
0x1800201a8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800201af  test    rax, rax
0x1800201b2  jz      short loc_180020227
0x1800201b4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800201bb  jnz     short loc_180020227
0x1800201bd  xor     r8d, r8d
0x1800201c0  xor     edx, edx
0x1800201c2  lea     rcx, [rsp+1500h+var_14E0]
0x1800201c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201cc  jmp     short loc_180020227
0x1800201ce  mov     ebx, 800h
0x1800201d3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800201da  test    rax, rax
0x1800201dd  jz      short loc_1800201FC
0x1800201df  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800201e6  jnz     short loc_1800201FC
0x1800201e8  mov     r8d, ebx
0x1800201eb  lea     rdx, [rbp+1400h+OutputString]
0x1800201f2  lea     rcx, [rsp+1500h+var_14E0]
0x1800201f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201fc  cmp     [rbp+1400h+OutputString], r12w
0x180020204  jnz     short loc_18002021A
0x180020206  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18002020b  mov     rdx, rbx; unsigned __int16 *
0x18002020e  lea     rcx, [rbp+1400h+OutputString]; this
0x180020215  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002021a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180020221  call    cs:__imp_OutputDebugStringW
0x180020227  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18002022c  jnz     short loc_180020237
0x18002022e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180020235  jz      short loc_180020249
0x180020237  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002023e  test    rax, rax
0x180020241  jz      short loc_180020249
0x180020243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020248  nop
0x180020249  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18002024e  jnz     short loc_180020271
0x180020250  mov     rcx, [rbp+1400h+var_40]
0x180020257  xor     rcx, rsp; StackCookie
0x18002025a  call    __security_check_cookie
0x18002025f  add     rsp, 14D0h
0x180020266  pop     r15
0x180020268  pop     r14
0x18002026a  pop     r12
0x18002026c  pop     rdi
0x18002026d  pop     rsi
0x18002026e  pop     rbx
0x18002026f  pop     rbp
0x180020270  retn
0x180020271  lea     rcx, [rsp+1500h+var_14E0]; this
0x180020276  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002027c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
