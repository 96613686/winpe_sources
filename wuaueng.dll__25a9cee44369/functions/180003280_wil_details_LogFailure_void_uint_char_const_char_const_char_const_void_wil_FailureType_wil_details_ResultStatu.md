# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180003280`
- end: `0x180003583`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004a38`

## callees

- `0x180001e74`
- `0x1800022e0`
- `0x1800022fc`
- `0x180002318`
- `0x180002340`
- `0x180002580`
- `0x180003280`
- `0x1800037f0`
- `0x180004440`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800034c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000353e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000353e`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // esi
  int v20; // eax
  _WORD *v21; // rax
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  wil::details *v25; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v25) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v25);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
}

```

## disassembly

```asm
0x180003280  mov     [rsp+arg_10], rbx
0x180003285  mov     [rsp+arg_8], edx
0x180003289  mov     [rsp+arg_0], rcx
0x18000328e  push    rbp
0x18000328f  push    rsi
0x180003290  push    rdi
0x180003291  push    r12
0x180003293  push    r13
0x180003295  push    r14
0x180003297  push    r15
0x180003299  sub     rsp, 40h
0x18000329d  mov     r12, r9
0x1800032a0  mov     r13, r8
0x1800032a3  mov     r10, rcx
0x1800032a6  xor     r8d, r8d
0x1800032a9  mov     r14, [rsp+78h+lpOutputString]
0x1800032b1  mov     [r14], r8w
0x1800032b5  mov     rax, [rsp+78h+arg_60]
0x1800032bd  mov     [rax], r8b
0x1800032c0  mov     r15, [rsp+78h+arg_38]
0x1800032c8  mov     edi, [r15]
0x1800032cb  mov     rbx, [rsp+78h+arg_78]
0x1800032d3  mov     [rbx+8], edi
0x1800032d6  mov     eax, [r15+4]
0x1800032da  mov     [rbx+0Ch], eax
0x1800032dd  mov     esi, r8d
0x1800032e0  mov     ebp, [rsp+78h+arg_30]
0x1800032e7  mov     ecx, ebp
0x1800032e9  test    ebp, ebp
0x1800032eb  jz      short loc_180003356
0x1800032ed  sub     ecx, 1
0x1800032f0  jz      short loc_18000334D
0x1800032f2  sub     ecx, 1
0x1800032f5  jz      short loc_180003305
0x1800032f7  cmp     ecx, 1
0x1800032fa  jnz     short loc_18000335F
0x1800032fc  mov     ecx, edi; this
0x1800032fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003303  jmp     short loc_18000335D
0x180003305  test    edi, edi
0x180003307  js      short loc_180003344
0x180003309  mov     edi, 8007029Ch
0x18000330e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180003312  mov     rax, [rsp+78h+arg_28]
0x18000331a  mov     [rsp+78h+var_50], rax; __int64
0x18000331f  mov     rax, [rsp+78h+arg_20]
0x180003327  mov     [rsp+78h+var_58], rax; __int64
0x18000332c  mov     r8, r13; int
0x18000332f  mov     rcx, r10; int
0x180003332  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003337  mov     [rbx+8], edi
0x18000333a  mov     ecx, edi; this
0x18000333c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003341  mov     [rbx+0Ch], eax
0x180003344  mov     ecx, edi; this
0x180003346  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000334b  jmp     short loc_18000335D
0x18000334d  mov     ecx, edi; this
0x18000334f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003354  jmp     short loc_18000335D
0x180003356  mov     ecx, edi; this
0x180003358  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000335d  mov     esi, eax
0x18000335f  mov     [rbx], ebp
0x180003361  mov     eax, [rsp+78h+arg_70]
0x180003368  mov     [rbx+4], eax
0x18000336b  cmp     dword ptr [r15+8], 1
0x180003370  jnz     short loc_180003378
0x180003372  or      eax, 8
0x180003375  mov     [rbx+4], eax
0x180003378  mov     eax, 1
0x18000337d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003385  inc     eax
0x180003387  mov     [rbx+10h], eax
0x18000338a  mov     rax, [rsp+78h+arg_40]
0x180003392  xor     edi, edi
0x180003394  test    rax, rax
0x180003397  jz      short loc_18000339E
0x180003399  cmp     [rax], di
0x18000339c  jnz     short loc_1800033A1
0x18000339e  mov     rax, rdi
0x1800033a1  mov     [rbx+18h], rax
0x1800033a5  call    cs:__imp_GetCurrentThreadId
0x1800033ab  mov     [rbx+20h], eax
0x1800033ae  mov     [rbx+38h], r13
0x1800033b2  mov     eax, [rsp+78h+arg_8]
0x1800033b9  mov     [rbx+40h], eax
0x1800033bc  mov     [rbx+44h], esi
0x1800033bf  mov     rax, [rsp+78h+arg_20]
0x1800033c7  mov     [rbx+28h], rax
0x1800033cb  mov     [rbx+30h], r12
0x1800033cf  mov     rax, [rsp+78h+arg_28]
0x1800033d7  mov     [rbx+88h], rax
0x1800033de  mov     rax, [rsp+78h+arg_0]
0x1800033e6  mov     [rbx+90h], rax
0x1800033ed  mov     [rbx+48h], rdi
0x1800033f1  xorps   xmm0, xmm0
0x1800033f4  xor     eax, eax
0x1800033f6  movups  xmmword ptr [rbx+68h], xmm0
0x1800033fa  mov     [rbx+78h], rax
0x1800033fe  movups  xmmword ptr [rbx+50h], xmm0
0x180003402  mov     [rbx+60h], rax
0x180003406  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000340d  test    rax, rax
0x180003410  jz      short loc_180003419
0x180003412  call    _guard_dispatch_icall
0x180003417  jmp     short loc_18000341C
0x180003419  mov     rax, rdi
0x18000341c  mov     [rbx+80h], rax
0x180003423  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000342a  test    rax, rax
0x18000342d  jz      short loc_180003437
0x18000342f  mov     rcx, rbx
0x180003432  call    _guard_dispatch_icall
0x180003437  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000343e  test    rax, rax
0x180003441  jz      short loc_180003459
0x180003443  mov     r8d, 400h
0x180003449  mov     rdx, [rsp+78h+arg_60]
0x180003451  mov     rcx, rbx
0x180003454  call    _guard_dispatch_icall
0x180003459  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003460  test    rax, rax
0x180003463  jz      short loc_18000346D
0x180003465  mov     rcx, rbx
0x180003468  call    _guard_dispatch_icall
0x18000346d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003474  test    rax, rax
0x180003477  jz      short loc_180003487
0x180003479  test    byte ptr [rbx+4], 2
0x18000347d  jnz     short loc_180003487
0x18000347f  mov     rcx, rbx
0x180003482  call    _guard_dispatch_icall
0x180003487  cmp     [rbx+8], edi
0x18000348a  jl      short loc_1800034A5
0x18000348c  cmp     ebp, 3
0x18000348f  jnz     loc_18000357D
0x180003495  mov     ecx, 8000FFFFh; this
0x18000349a  mov     [rbx+8], ecx
0x18000349d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800034a2  mov     [rbx+0Ch], eax
0x1800034a5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800034ac  jnz     short loc_1800034D5
0x1800034ae  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800034b5  test    rax, rax
0x1800034b8  jz      short loc_1800034C4
0x1800034ba  call    _guard_dispatch_icall
0x1800034bf  movzx   ecx, al
0x1800034c2  jmp     short loc_1800034D1
0x1800034c4  call    cs:__imp_IsDebuggerPresent
0x1800034ca  mov     ecx, edi
0x1800034cc  test    eax, eax
0x1800034ce  setnz   cl
0x1800034d1  test    ecx, ecx
0x1800034d3  jz      short loc_1800034DB
0x1800034d5  test    byte ptr [rbx+4], 2
0x1800034d9  jz      short loc_1800034FF
0x1800034db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034e2  test    rax, rax
0x1800034e5  jz      short loc_180003544
0x1800034e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800034ee  jnz     short loc_180003544
0x1800034f0  xor     r8d, r8d
0x1800034f3  xor     edx, edx
0x1800034f5  mov     rcx, rbx
0x1800034f8  call    _guard_dispatch_icall
0x1800034fd  jmp     short loc_180003544
0x1800034ff  mov     esi, 800h
0x180003504  mov     rax, cs:g_pfnResultLoggingCallback
0x18000350b  test    rax, rax
0x18000350e  jz      short loc_180003527
0x180003510  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180003517  jnz     short loc_180003527
0x180003519  mov     r8d, esi
0x18000351c  mov     rdx, r14
0x18000351f  mov     rcx, rbx
0x180003522  call    _guard_dispatch_icall
0x180003527  cmp     [r14], di
0x18000352b  jnz     short loc_18000353B
0x18000352d  mov     r8, rbx; unsigned __int64
0x180003530  mov     rdx, rsi; wchar_t *
0x180003533  mov     rcx, r14; this
0x180003536  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000353b  mov     rcx, r14; lpOutputString
0x18000353e  call    cs:__imp_OutputDebugStringW
0x180003544  test    byte ptr [rbx+4], 4
0x180003548  jnz     short loc_180003553
0x18000354a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180003551  jz      short loc_180003565
0x180003553  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000355a  test    rax, rax
0x18000355d  jz      short loc_180003565
0x18000355f  call    _guard_dispatch_icall
0x180003564  nop
0x180003565  mov     rbx, [rsp+78h+arg_10]
0x18000356d  add     rsp, 40h
0x180003571  pop     r15
0x180003573  pop     r14
0x180003575  pop     r13
0x180003577  pop     r12
0x180003579  pop     rdi
0x18000357a  pop     rsi
0x18000357b  pop     rbp
0x18000357c  retn
0x18000357d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
