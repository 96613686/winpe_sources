# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400021b8`
- end: `0x1400024bb`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140001bb4`

## callees

- `0x140001b7c`
- `0x140001b98`
- `0x140001d30`
- `0x140001d94`
- `0x140001db0`
- `0x140001dc4`
- `0x140001efc`
- `0x1400021b8`
- `0x140002868`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002476`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002476`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400023fc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400023fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400022dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400022dd`

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
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  int IsDebuggerPresent; // ecx
  wil::details *v28; // [rsp+30h] [rbp-48h]

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
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
    ModuleName = wil::details::g_pfnGetModuleName();
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1400021b8  mov     [rsp+arg_10], rbx
0x1400021bd  mov     [rsp+arg_8], edx
0x1400021c1  mov     [rsp+arg_0], rcx
0x1400021c6  push    rbp
0x1400021c7  push    rsi
0x1400021c8  push    rdi
0x1400021c9  push    r12
0x1400021cb  push    r13
0x1400021cd  push    r14
0x1400021cf  push    r15
0x1400021d1  sub     rsp, 40h
0x1400021d5  mov     r12, r9
0x1400021d8  mov     r13, r8
0x1400021db  mov     r10, rcx
0x1400021de  xor     r8d, r8d
0x1400021e1  mov     r14, [rsp+78h+lpOutputString]
0x1400021e9  mov     [r14], r8w
0x1400021ed  mov     rax, [rsp+78h+arg_60]
0x1400021f5  mov     [rax], r8b
0x1400021f8  mov     r15, [rsp+78h+arg_38]
0x140002200  mov     edi, [r15]
0x140002203  mov     rbx, [rsp+78h+arg_78]
0x14000220b  mov     [rbx+8], edi
0x14000220e  mov     eax, [r15+4]
0x140002212  mov     [rbx+0Ch], eax
0x140002215  mov     esi, r8d
0x140002218  mov     ebp, [rsp+78h+arg_30]
0x14000221f  mov     ecx, ebp
0x140002221  test    ebp, ebp
0x140002223  jz      short loc_14000228E
0x140002225  sub     ecx, 1
0x140002228  jz      short loc_140002285
0x14000222a  sub     ecx, 1
0x14000222d  jz      short loc_14000223D
0x14000222f  cmp     ecx, 1
0x140002232  jnz     short loc_140002297
0x140002234  mov     ecx, edi; this
0x140002236  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000223b  jmp     short loc_140002295
0x14000223d  test    edi, edi
0x14000223f  js      short loc_14000227C
0x140002241  mov     edi, 8007029Ch
0x140002246  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000224a  mov     rax, [rsp+78h+arg_28]
0x140002252  mov     [rsp+78h+var_50], rax; __int64
0x140002257  mov     rax, [rsp+78h+arg_20]
0x14000225f  mov     [rsp+78h+var_58], rax; __int64
0x140002264  mov     r8, r13; int
0x140002267  mov     rcx, r10; int
0x14000226a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000226f  mov     [rbx+8], edi
0x140002272  mov     ecx, edi; this
0x140002274  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002279  mov     [rbx+0Ch], eax
0x14000227c  mov     ecx, edi; this
0x14000227e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140002283  jmp     short loc_140002295
0x140002285  mov     ecx, edi; this
0x140002287  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000228c  jmp     short loc_140002295
0x14000228e  mov     ecx, edi; this
0x140002290  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140002295  mov     esi, eax
0x140002297  mov     [rbx], ebp
0x140002299  mov     eax, [rsp+78h+arg_70]
0x1400022a0  mov     [rbx+4], eax
0x1400022a3  cmp     dword ptr [r15+8], 1
0x1400022a8  jnz     short loc_1400022B0
0x1400022aa  or      eax, 8
0x1400022ad  mov     [rbx+4], eax
0x1400022b0  mov     eax, 1
0x1400022b5  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400022bd  inc     eax
0x1400022bf  mov     [rbx+10h], eax
0x1400022c2  mov     rax, [rsp+78h+arg_40]
0x1400022ca  xor     edi, edi
0x1400022cc  test    rax, rax
0x1400022cf  jz      short loc_1400022D6
0x1400022d1  cmp     [rax], di
0x1400022d4  jnz     short loc_1400022D9
0x1400022d6  mov     rax, rdi
0x1400022d9  mov     [rbx+18h], rax
0x1400022dd  call    cs:__imp_GetCurrentThreadId
0x1400022e3  mov     [rbx+20h], eax
0x1400022e6  mov     [rbx+38h], r13
0x1400022ea  mov     eax, [rsp+78h+arg_8]
0x1400022f1  mov     [rbx+40h], eax
0x1400022f4  mov     [rbx+44h], esi
0x1400022f7  mov     rax, [rsp+78h+arg_20]
0x1400022ff  mov     [rbx+28h], rax
0x140002303  mov     [rbx+30h], r12
0x140002307  mov     rax, [rsp+78h+arg_28]
0x14000230f  mov     [rbx+88h], rax
0x140002316  mov     rax, [rsp+78h+arg_0]
0x14000231e  mov     [rbx+90h], rax
0x140002325  mov     [rbx+48h], rdi
0x140002329  xorps   xmm0, xmm0
0x14000232c  xor     eax, eax
0x14000232e  movups  xmmword ptr [rbx+68h], xmm0
0x140002332  mov     [rbx+78h], rax
0x140002336  movups  xmmword ptr [rbx+50h], xmm0
0x14000233a  mov     [rbx+60h], rax
0x14000233e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002345  test    rax, rax
0x140002348  jz      short loc_140002351
0x14000234a  call    _guard_dispatch_icall
0x14000234f  jmp     short loc_140002354
0x140002351  mov     rax, rdi
0x140002354  mov     [rbx+80h], rax
0x14000235b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002362  test    rax, rax
0x140002365  jz      short loc_14000236F
0x140002367  mov     rcx, rbx
0x14000236a  call    _guard_dispatch_icall
0x14000236f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002376  test    rax, rax
0x140002379  jz      short loc_140002391
0x14000237b  mov     r8d, 400h
0x140002381  mov     rdx, [rsp+78h+arg_60]
0x140002389  mov     rcx, rbx
0x14000238c  call    _guard_dispatch_icall
0x140002391  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002398  test    rax, rax
0x14000239b  jz      short loc_1400023A5
0x14000239d  mov     rcx, rbx
0x1400023a0  call    _guard_dispatch_icall
0x1400023a5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400023ac  test    rax, rax
0x1400023af  jz      short loc_1400023BF
0x1400023b1  test    byte ptr [rbx+4], 2
0x1400023b5  jnz     short loc_1400023BF
0x1400023b7  mov     rcx, rbx
0x1400023ba  call    _guard_dispatch_icall
0x1400023bf  cmp     [rbx+8], edi
0x1400023c2  jl      short loc_1400023DD
0x1400023c4  cmp     ebp, 3
0x1400023c7  jnz     loc_1400024B5
0x1400023cd  mov     ecx, 8000FFFFh; this
0x1400023d2  mov     [rbx+8], ecx
0x1400023d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400023da  mov     [rbx+0Ch], eax
0x1400023dd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400023e4  jnz     short loc_14000240D
0x1400023e6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400023ed  test    rax, rax
0x1400023f0  jz      short loc_1400023FC
0x1400023f2  call    _guard_dispatch_icall
0x1400023f7  movzx   ecx, al
0x1400023fa  jmp     short loc_140002409
0x1400023fc  call    cs:__imp_IsDebuggerPresent
0x140002402  mov     ecx, edi
0x140002404  test    eax, eax
0x140002406  setnz   cl
0x140002409  test    ecx, ecx
0x14000240b  jz      short loc_140002413
0x14000240d  test    byte ptr [rbx+4], 2
0x140002411  jz      short loc_140002437
0x140002413  mov     rax, cs:g_pfnResultLoggingCallback
0x14000241a  test    rax, rax
0x14000241d  jz      short loc_14000247C
0x14000241f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140002426  jnz     short loc_14000247C
0x140002428  xor     r8d, r8d
0x14000242b  xor     edx, edx
0x14000242d  mov     rcx, rbx
0x140002430  call    _guard_dispatch_icall
0x140002435  jmp     short loc_14000247C
0x140002437  mov     esi, 800h
0x14000243c  mov     rax, cs:g_pfnResultLoggingCallback
0x140002443  test    rax, rax
0x140002446  jz      short loc_14000245F
0x140002448  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000244f  jnz     short loc_14000245F
0x140002451  mov     r8d, esi
0x140002454  mov     rdx, r14
0x140002457  mov     rcx, rbx
0x14000245a  call    _guard_dispatch_icall
0x14000245f  cmp     [r14], di
0x140002463  jnz     short loc_140002473
0x140002465  mov     r8, rbx; unsigned __int64
0x140002468  mov     rdx, rsi; wchar_t *
0x14000246b  mov     rcx, r14; this
0x14000246e  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140002473  mov     rcx, r14; lpOutputString
0x140002476  call    cs:__imp_OutputDebugStringW
0x14000247c  test    byte ptr [rbx+4], 4
0x140002480  jnz     short loc_14000248B
0x140002482  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140002489  jz      short loc_14000249D
0x14000248b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002492  test    rax, rax
0x140002495  jz      short loc_14000249D
0x140002497  call    _guard_dispatch_icall
0x14000249c  nop
0x14000249d  mov     rbx, [rsp+78h+arg_10]
0x1400024a5  add     rsp, 40h
0x1400024a9  pop     r15
0x1400024ab  pop     r14
0x1400024ad  pop     r13
0x1400024af  pop     r12
0x1400024b1  pop     rdi
0x1400024b2  pop     rsi
0x1400024b3  pop     rbp
0x1400024b4  retn
0x1400024b5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
