# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000923c`
- end: `0x180009535`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003b40`

## callees

- `0x18000323c`
- `0x180007e34`
- `0x18000884c`
- `0x18000923c`
- `0x18000a128`
- `0x18000a150`
- `0x18000a27c`
- `0x18000a298`
- `0x18000d1fc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000935f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000935f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800094f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800094f0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000947e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000947e`

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
  int v19; // ebp
  int v20; // eax
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x18000923c  mov     [rsp+arg_10], rbx
0x180009241  mov     [rsp+arg_8], edx
0x180009245  mov     [rsp+arg_0], rcx
0x18000924a  push    rbp
0x18000924b  push    rsi
0x18000924c  push    rdi
0x18000924d  push    r12
0x18000924f  push    r13
0x180009251  push    r14
0x180009253  push    r15
0x180009255  sub     rsp, 40h
0x180009259  mov     r12, r9
0x18000925c  mov     r13, r8
0x18000925f  mov     r10, rcx
0x180009262  xor     eax, eax
0x180009264  mov     rsi, [rsp+78h+lpOutputString]
0x18000926c  mov     [rsi], ax
0x18000926f  mov     rax, [rsp+78h+arg_60]
0x180009277  mov     byte ptr [rax], 0
0x18000927a  mov     r14, [rsp+78h+arg_38]
0x180009282  mov     edi, [r14]
0x180009285  mov     rbx, [rsp+78h+arg_78]
0x18000928d  mov     [rbx+8], edi
0x180009290  mov     eax, [r14+4]
0x180009294  mov     [rbx+0Ch], eax
0x180009297  xor     ebp, ebp
0x180009299  mov     r15d, [rsp+78h+arg_30]
0x1800092a1  mov     ecx, r15d
0x1800092a4  test    r15d, r15d
0x1800092a7  jz      short loc_18000930F
0x1800092a9  sub     ecx, 1
0x1800092ac  jz      short loc_180009306
0x1800092ae  sub     ecx, 1
0x1800092b1  jz      short loc_1800092C1
0x1800092b3  cmp     ecx, 1
0x1800092b6  jnz     short loc_180009318
0x1800092b8  mov     ecx, edi; this
0x1800092ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800092bf  jmp     short loc_180009316
0x1800092c1  test    edi, edi
0x1800092c3  js      short loc_1800092FD
0x1800092c5  mov     edi, 8007029Ch
0x1800092ca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800092ce  mov     rax, [rsp+78h+arg_28]
0x1800092d6  mov     [rsp+78h+var_50], rax; __int64
0x1800092db  mov     rax, [rsp+78h+arg_20]
0x1800092e3  mov     [rsp+78h+var_58], rax; __int64
0x1800092e8  mov     rcx, r10; int
0x1800092eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800092f0  mov     [rbx+8], edi
0x1800092f3  mov     ecx, edi; this
0x1800092f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800092fa  mov     [rbx+0Ch], eax
0x1800092fd  mov     ecx, edi; this
0x1800092ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009304  jmp     short loc_180009316
0x180009306  mov     ecx, edi; this
0x180009308  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000930d  jmp     short loc_180009316
0x18000930f  mov     ecx, edi; this
0x180009311  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009316  mov     ebp, eax
0x180009318  mov     [rbx], r15d
0x18000931b  mov     eax, [rsp+78h+arg_70]
0x180009322  mov     [rbx+4], eax
0x180009325  cmp     dword ptr [r14+8], 1
0x18000932a  jnz     short loc_180009332
0x18000932c  or      eax, 8
0x18000932f  mov     [rbx+4], eax
0x180009332  mov     eax, 1
0x180009337  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000933f  inc     eax
0x180009341  mov     [rbx+10h], eax
0x180009344  mov     rax, [rsp+78h+arg_40]
0x18000934c  xor     edi, edi
0x18000934e  test    rax, rax
0x180009351  jz      short loc_180009358
0x180009353  cmp     [rax], di
0x180009356  jnz     short loc_18000935B
0x180009358  mov     rax, rdi
0x18000935b  mov     [rbx+18h], rax
0x18000935f  call    cs:__imp_GetCurrentThreadId
0x180009365  mov     [rbx+20h], eax
0x180009368  mov     [rbx+38h], r13
0x18000936c  mov     eax, [rsp+78h+arg_8]
0x180009373  mov     [rbx+40h], eax
0x180009376  mov     [rbx+44h], ebp
0x180009379  mov     rax, [rsp+78h+arg_20]
0x180009381  mov     [rbx+28h], rax
0x180009385  mov     [rbx+30h], r12
0x180009389  mov     rax, [rsp+78h+arg_28]
0x180009391  mov     [rbx+88h], rax
0x180009398  mov     rax, [rsp+78h+arg_0]
0x1800093a0  mov     [rbx+90h], rax
0x1800093a7  mov     [rbx+48h], rdi
0x1800093ab  xorps   xmm0, xmm0
0x1800093ae  xor     eax, eax
0x1800093b0  movups  xmmword ptr [rbx+68h], xmm0
0x1800093b4  mov     [rbx+78h], rax
0x1800093b8  movups  xmmword ptr [rbx+50h], xmm0
0x1800093bc  mov     [rbx+60h], rax
0x1800093c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800093c7  test    rax, rax
0x1800093ca  jz      short loc_1800093D3
0x1800093cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093d1  jmp     short loc_1800093D6
0x1800093d3  mov     rax, rdi
0x1800093d6  mov     [rbx+80h], rax
0x1800093dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800093e4  test    rax, rax
0x1800093e7  jz      short loc_1800093F1
0x1800093e9  mov     rcx, rbx
0x1800093ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800093f8  test    rax, rax
0x1800093fb  jz      short loc_180009413
0x1800093fd  mov     r8d, 400h
0x180009403  mov     rdx, [rsp+78h+arg_60]
0x18000940b  mov     rcx, rbx
0x18000940e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009413  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000941a  test    rax, rax
0x18000941d  jz      short loc_180009427
0x18000941f  mov     rcx, rbx
0x180009422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009427  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000942e  test    rax, rax
0x180009431  jz      short loc_180009441
0x180009433  test    byte ptr [rbx+4], 2
0x180009437  jnz     short loc_180009441
0x180009439  mov     rcx, rbx
0x18000943c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009441  cmp     [rbx+8], edi
0x180009444  jl      short loc_180009460
0x180009446  cmp     r15d, 3
0x18000944a  jnz     loc_18000952F
0x180009450  mov     ecx, 8000FFFFh; this
0x180009455  mov     [rbx+8], ecx
0x180009458  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000945d  mov     [rbx+0Ch], eax
0x180009460  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009467  jnz     short loc_180009488
0x180009469  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009470  test    rax, rax
0x180009473  jz      short loc_18000947E
0x180009475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000947a  test    al, al
0x18000947c  jmp     short loc_180009486
0x18000947e  call    cs:__imp_IsDebuggerPresent
0x180009484  test    eax, eax
0x180009486  jz      short loc_18000948E
0x180009488  test    byte ptr [rbx+4], 2
0x18000948c  jz      short loc_1800094B2
0x18000948e  mov     rax, cs:g_pfnResultLoggingCallback
0x180009495  test    rax, rax
0x180009498  jz      short loc_1800094F6
0x18000949a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800094a1  jnz     short loc_1800094F6
0x1800094a3  xor     r8d, r8d
0x1800094a6  xor     edx, edx
0x1800094a8  mov     rcx, rbx
0x1800094ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b0  jmp     short loc_1800094F6
0x1800094b2  mov     ebp, 800h
0x1800094b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800094be  test    rax, rax
0x1800094c1  jz      short loc_1800094DA
0x1800094c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800094ca  jnz     short loc_1800094DA
0x1800094cc  mov     r8d, ebp
0x1800094cf  mov     rdx, rsi
0x1800094d2  mov     rcx, rbx
0x1800094d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094da  cmp     [rsi], di
0x1800094dd  jnz     short loc_1800094ED
0x1800094df  mov     r8, rbx; unsigned __int64
0x1800094e2  mov     rdx, rbp; wchar_t *
0x1800094e5  mov     rcx, rsi; this
0x1800094e8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800094ed  mov     rcx, rsi; lpOutputString
0x1800094f0  call    cs:__imp_OutputDebugStringW
0x1800094f6  test    byte ptr [rbx+4], 4
0x1800094fa  jnz     short loc_180009505
0x1800094fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009503  jz      short loc_180009517
0x180009505  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000950c  test    rax, rax
0x18000950f  jz      short loc_180009517
0x180009511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009516  nop
0x180009517  mov     rbx, [rsp+78h+arg_10]
0x18000951f  add     rsp, 40h
0x180009523  pop     r15
0x180009525  pop     r14
0x180009527  pop     r13
0x180009529  pop     r12
0x18000952b  pop     rdi
0x18000952c  pop     rsi
0x18000952d  pop     rbp
0x18000952e  retn
0x18000952f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
