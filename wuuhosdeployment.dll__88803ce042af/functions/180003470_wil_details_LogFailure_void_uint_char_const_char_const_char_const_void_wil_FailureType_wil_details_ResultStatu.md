# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180003470`
- end: `0x180003773`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005374`

## callees

- `0x180002064`
- `0x1800024d0`
- `0x1800024ec`
- `0x180002508`
- `0x180002530`
- `0x180002770`
- `0x180003470`
- `0x1800039e0`
- `0x180004d6c`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003595`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003595`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000372e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000372e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036b4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036b4`

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
0x180003470  mov     [rsp+arg_10], rbx
0x180003475  mov     [rsp+arg_8], edx
0x180003479  mov     [rsp+arg_0], rcx
0x18000347e  push    rbp
0x18000347f  push    rsi
0x180003480  push    rdi
0x180003481  push    r12
0x180003483  push    r13
0x180003485  push    r14
0x180003487  push    r15
0x180003489  sub     rsp, 40h
0x18000348d  mov     r12, r9
0x180003490  mov     r13, r8
0x180003493  mov     r10, rcx
0x180003496  xor     r8d, r8d
0x180003499  mov     r14, [rsp+78h+lpOutputString]
0x1800034a1  mov     [r14], r8w
0x1800034a5  mov     rax, [rsp+78h+arg_60]
0x1800034ad  mov     [rax], r8b
0x1800034b0  mov     r15, [rsp+78h+arg_38]
0x1800034b8  mov     edi, [r15]
0x1800034bb  mov     rbx, [rsp+78h+arg_78]
0x1800034c3  mov     [rbx+8], edi
0x1800034c6  mov     eax, [r15+4]
0x1800034ca  mov     [rbx+0Ch], eax
0x1800034cd  mov     esi, r8d
0x1800034d0  mov     ebp, [rsp+78h+arg_30]
0x1800034d7  mov     ecx, ebp
0x1800034d9  test    ebp, ebp
0x1800034db  jz      short loc_180003546
0x1800034dd  sub     ecx, 1
0x1800034e0  jz      short loc_18000353D
0x1800034e2  sub     ecx, 1
0x1800034e5  jz      short loc_1800034F5
0x1800034e7  cmp     ecx, 1
0x1800034ea  jnz     short loc_18000354F
0x1800034ec  mov     ecx, edi; this
0x1800034ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800034f3  jmp     short loc_18000354D
0x1800034f5  test    edi, edi
0x1800034f7  js      short loc_180003534
0x1800034f9  mov     edi, 8007029Ch
0x1800034fe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180003502  mov     rax, [rsp+78h+arg_28]
0x18000350a  mov     [rsp+78h+var_50], rax; __int64
0x18000350f  mov     rax, [rsp+78h+arg_20]
0x180003517  mov     [rsp+78h+var_58], rax; __int64
0x18000351c  mov     r8, r13; int
0x18000351f  mov     rcx, r10; int
0x180003522  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003527  mov     [rbx+8], edi
0x18000352a  mov     ecx, edi; this
0x18000352c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003531  mov     [rbx+0Ch], eax
0x180003534  mov     ecx, edi; this
0x180003536  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000353b  jmp     short loc_18000354D
0x18000353d  mov     ecx, edi; this
0x18000353f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003544  jmp     short loc_18000354D
0x180003546  mov     ecx, edi; this
0x180003548  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000354d  mov     esi, eax
0x18000354f  mov     [rbx], ebp
0x180003551  mov     eax, [rsp+78h+arg_70]
0x180003558  mov     [rbx+4], eax
0x18000355b  cmp     dword ptr [r15+8], 1
0x180003560  jnz     short loc_180003568
0x180003562  or      eax, 8
0x180003565  mov     [rbx+4], eax
0x180003568  mov     eax, 1
0x18000356d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003575  inc     eax
0x180003577  mov     [rbx+10h], eax
0x18000357a  mov     rax, [rsp+78h+arg_40]
0x180003582  xor     edi, edi
0x180003584  test    rax, rax
0x180003587  jz      short loc_18000358E
0x180003589  cmp     [rax], di
0x18000358c  jnz     short loc_180003591
0x18000358e  mov     rax, rdi
0x180003591  mov     [rbx+18h], rax
0x180003595  call    cs:__imp_GetCurrentThreadId
0x18000359b  mov     [rbx+20h], eax
0x18000359e  mov     [rbx+38h], r13
0x1800035a2  mov     eax, [rsp+78h+arg_8]
0x1800035a9  mov     [rbx+40h], eax
0x1800035ac  mov     [rbx+44h], esi
0x1800035af  mov     rax, [rsp+78h+arg_20]
0x1800035b7  mov     [rbx+28h], rax
0x1800035bb  mov     [rbx+30h], r12
0x1800035bf  mov     rax, [rsp+78h+arg_28]
0x1800035c7  mov     [rbx+88h], rax
0x1800035ce  mov     rax, [rsp+78h+arg_0]
0x1800035d6  mov     [rbx+90h], rax
0x1800035dd  mov     [rbx+48h], rdi
0x1800035e1  xorps   xmm0, xmm0
0x1800035e4  xor     eax, eax
0x1800035e6  movups  xmmword ptr [rbx+68h], xmm0
0x1800035ea  mov     [rbx+78h], rax
0x1800035ee  movups  xmmword ptr [rbx+50h], xmm0
0x1800035f2  mov     [rbx+60h], rax
0x1800035f6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800035fd  test    rax, rax
0x180003600  jz      short loc_180003609
0x180003602  call    _guard_dispatch_icall
0x180003607  jmp     short loc_18000360C
0x180003609  mov     rax, rdi
0x18000360c  mov     [rbx+80h], rax
0x180003613  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000361a  test    rax, rax
0x18000361d  jz      short loc_180003627
0x18000361f  mov     rcx, rbx
0x180003622  call    _guard_dispatch_icall
0x180003627  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000362e  test    rax, rax
0x180003631  jz      short loc_180003649
0x180003633  mov     r8d, 400h
0x180003639  mov     rdx, [rsp+78h+arg_60]
0x180003641  mov     rcx, rbx
0x180003644  call    _guard_dispatch_icall
0x180003649  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003650  test    rax, rax
0x180003653  jz      short loc_18000365D
0x180003655  mov     rcx, rbx
0x180003658  call    _guard_dispatch_icall
0x18000365d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003664  test    rax, rax
0x180003667  jz      short loc_180003677
0x180003669  test    byte ptr [rbx+4], 2
0x18000366d  jnz     short loc_180003677
0x18000366f  mov     rcx, rbx
0x180003672  call    _guard_dispatch_icall
0x180003677  cmp     [rbx+8], edi
0x18000367a  jl      short loc_180003695
0x18000367c  cmp     ebp, 3
0x18000367f  jnz     loc_18000376D
0x180003685  mov     ecx, 8000FFFFh; this
0x18000368a  mov     [rbx+8], ecx
0x18000368d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003692  mov     [rbx+0Ch], eax
0x180003695  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000369c  jnz     short loc_1800036C5
0x18000369e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800036a5  test    rax, rax
0x1800036a8  jz      short loc_1800036B4
0x1800036aa  call    _guard_dispatch_icall
0x1800036af  movzx   ecx, al
0x1800036b2  jmp     short loc_1800036C1
0x1800036b4  call    cs:__imp_IsDebuggerPresent
0x1800036ba  mov     ecx, edi
0x1800036bc  test    eax, eax
0x1800036be  setnz   cl
0x1800036c1  test    ecx, ecx
0x1800036c3  jz      short loc_1800036CB
0x1800036c5  test    byte ptr [rbx+4], 2
0x1800036c9  jz      short loc_1800036EF
0x1800036cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036d2  test    rax, rax
0x1800036d5  jz      short loc_180003734
0x1800036d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800036de  jnz     short loc_180003734
0x1800036e0  xor     r8d, r8d
0x1800036e3  xor     edx, edx
0x1800036e5  mov     rcx, rbx
0x1800036e8  call    _guard_dispatch_icall
0x1800036ed  jmp     short loc_180003734
0x1800036ef  mov     esi, 800h
0x1800036f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036fb  test    rax, rax
0x1800036fe  jz      short loc_180003717
0x180003700  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180003707  jnz     short loc_180003717
0x180003709  mov     r8d, esi
0x18000370c  mov     rdx, r14
0x18000370f  mov     rcx, rbx
0x180003712  call    _guard_dispatch_icall
0x180003717  cmp     [r14], di
0x18000371b  jnz     short loc_18000372B
0x18000371d  mov     r8, rbx; unsigned __int64
0x180003720  mov     rdx, rsi; wchar_t *
0x180003723  mov     rcx, r14; this
0x180003726  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000372b  mov     rcx, r14; lpOutputString
0x18000372e  call    cs:__imp_OutputDebugStringW
0x180003734  test    byte ptr [rbx+4], 4
0x180003738  jnz     short loc_180003743
0x18000373a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180003741  jz      short loc_180003755
0x180003743  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000374a  test    rax, rax
0x18000374d  jz      short loc_180003755
0x18000374f  call    _guard_dispatch_icall
0x180003754  nop
0x180003755  mov     rbx, [rsp+78h+arg_10]
0x18000375d  add     rsp, 40h
0x180003761  pop     r15
0x180003763  pop     r14
0x180003765  pop     r13
0x180003767  pop     r12
0x180003769  pop     rdi
0x18000376a  pop     rsi
0x18000376b  pop     rbp
0x18000376c  retn
0x18000376d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
