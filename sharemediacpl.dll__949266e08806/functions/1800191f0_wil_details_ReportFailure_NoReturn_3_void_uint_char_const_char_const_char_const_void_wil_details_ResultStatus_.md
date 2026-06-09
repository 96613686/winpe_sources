# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800191f0`
- end: `0x180019457`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180018fa4`

## callees

- `0x18000291e`
- `0x1800191f0`
- `0x18001a8c4`
- `0x18001b05c`
- `0x18001bae0`
- `0x18001c950`
- `0x18001d290`
- `0x18001e010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180019425`
- `KERNEL32!OutputDebugStringW` at `0x180019425`
- `KERNEL32!IsDebuggerPresent` at `0x18001939b`
- `KERNEL32!IsDebuggerPresent` at `0x18001939b`
- `KERNEL32!GetCurrentThreadId` at `0x180019291`
- `KERNEL32!GetCurrentThreadId` at `0x180019291`

## string_xrefs

- `0x1800192a6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1800191f0  mov     [rsp-8+arg_10], rbx
0x1800191f5  mov     [rsp-8+arg_18], rsi
0x1800191fa  push    rbp
0x1800191fb  push    rdi
0x1800191fc  push    r12
0x1800191fe  push    r14
0x180019200  push    r15
0x180019202  lea     rbp, [rsp-13C0h]
0x18001920a  mov     eax, 14C0h
0x18001920f  call    _alloca_probe
0x180019214  sub     rsp, rax
0x180019217  mov     rsi, [rbp+13E0h+arg_28]
0x18001921e  mov     r14d, edx
0x180019221  mov     r15, rcx
0x180019224  xor     edx, edx; Val
0x180019226  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18001922b  mov     r8d, 98h; Size
0x180019231  call    memset_0
0x180019236  mov     rbx, [rbp+13E0h+arg_30]
0x18001923d  xor     r12d, r12d
0x180019240  mov     [rbp+13E0h+OutputString], r12w
0x180019248  mov     [rbp+13E0h+var_1420], r12b
0x18001924c  mov     ecx, [rbx]; this
0x18001924e  mov     eax, [rbx+4]
0x180019251  mov     [rsp+14E0h+var_14B8], ecx
0x180019255  mov     [rsp+14E0h+var_14B4], eax
0x180019259  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001925e  cmp     dword ptr [rbx+8], 1
0x180019262  mov     edi, eax
0x180019264  lea     eax, [r12+8]
0x180019269  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180019271  mov     ecx, r12d
0x180019274  cmovz   ecx, eax
0x180019277  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18001927b  lea     ecx, [rax-7]
0x18001927e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180019286  inc     ecx
0x180019288  mov     [rsp+14E0h+var_14A8], r12
0x18001928d  mov     [rsp+14E0h+var_14B0], ecx
0x180019291  call    cs:__imp_GetCurrentThreadId
0x180019297  xorps   xmm0, xmm0
0x18001929a  mov     [rsp+14E0h+var_1480], r14d
0x18001929f  mov     [rsp+14E0h+var_14A0], eax
0x1800192a3  xorps   xmm1, xmm1
0x1800192a6  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800192ad  mov     [rsp+14E0h+var_147C], edi
0x1800192b1  mov     [rsp+14E0h+var_1488], rax
0x1800192b6  xor     eax, eax
0x1800192b8  mov     [rbp+13E0h+var_1448], rax
0x1800192bc  mov     [rbp+13E0h+var_1460], rax
0x1800192c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800192c7  mov     [rsp+14E0h+var_1498], r12
0x1800192cc  mov     [rsp+14E0h+var_1490], r12
0x1800192d1  mov     [rbp+13E0h+var_1438], rsi
0x1800192d5  mov     [rbp+13E0h+var_1430], r15
0x1800192d9  mov     [rsp+14E0h+var_1478], r12
0x1800192de  movups  [rbp+13E0h+var_1458], xmm0
0x1800192e2  movups  [rsp+14E0h+var_1470], xmm1
0x1800192e7  test    rax, rax
0x1800192ea  jz      short loc_1800192F7
0x1800192ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f1  mov     [rbp+13E0h+var_1440], rax
0x1800192f5  jmp     short loc_1800192FB
0x1800192f7  mov     [rbp+13E0h+var_1440], r12
0x1800192fb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180019302  test    rax, rax
0x180019305  jz      short loc_180019311
0x180019307  lea     rcx, [rsp+14E0h+var_14C0]
0x18001930c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019311  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180019318  test    rax, rax
0x18001931b  jz      short loc_180019331
0x18001931d  mov     r8d, 400h
0x180019323  lea     rdx, [rbp+13E0h+var_1420]
0x180019327  lea     rcx, [rsp+14E0h+var_14C0]
0x18001932c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019331  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019338  test    rax, rax
0x18001933b  jz      short loc_180019347
0x18001933d  lea     rcx, [rsp+14E0h+var_14C0]
0x180019342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019347  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001934e  test    rax, rax
0x180019351  jz      short loc_180019364
0x180019353  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180019358  jnz     short loc_180019364
0x18001935a  lea     rcx, [rsp+14E0h+var_14C0]
0x18001935f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019364  cmp     [rsp+14E0h+var_14B8], r12d
0x180019369  jl      short loc_18001937D
0x18001936b  mov     ecx, 8000FFFFh; this
0x180019370  mov     [rsp+14E0h+var_14B8], ecx
0x180019374  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180019379  mov     [rsp+14E0h+var_14B4], eax
0x18001937d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180019384  jnz     short loc_1800193A5
0x180019386  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001938d  test    rax, rax
0x180019390  jz      short loc_18001939B
0x180019392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019397  test    al, al
0x180019399  jmp     short loc_1800193A3
0x18001939b  call    cs:__imp_IsDebuggerPresent
0x1800193a1  test    eax, eax
0x1800193a3  jz      short loc_1800193AC
0x1800193a5  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800193aa  jz      short loc_1800193D2
0x1800193ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800193b3  test    rax, rax
0x1800193b6  jz      short loc_18001942B
0x1800193b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800193bf  jnz     short loc_18001942B
0x1800193c1  xor     r8d, r8d
0x1800193c4  lea     rcx, [rsp+14E0h+var_14C0]
0x1800193c9  xor     edx, edx
0x1800193cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193d0  jmp     short loc_18001942B
0x1800193d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800193d9  mov     ebx, 800h
0x1800193de  test    rax, rax
0x1800193e1  jz      short loc_180019400
0x1800193e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800193ea  jnz     short loc_180019400
0x1800193ec  mov     r8d, ebx
0x1800193ef  lea     rdx, [rbp+13E0h+OutputString]
0x1800193f6  lea     rcx, [rsp+14E0h+var_14C0]
0x1800193fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019400  cmp     [rbp+13E0h+OutputString], r12w
0x180019408  jnz     short loc_18001941E
0x18001940a  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18001940f  mov     rdx, rbx; unsigned __int16 *
0x180019412  lea     rcx, [rbp+13E0h+OutputString]; this
0x180019419  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001941e  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180019425  call    cs:__imp_OutputDebugStringW
0x18001942b  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180019430  jnz     short loc_18001943B
0x180019432  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180019439  jz      short loc_18001944C
0x18001943b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180019442  test    rax, rax
0x180019445  jz      short loc_18001944C
0x180019447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001944c  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180019451  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
