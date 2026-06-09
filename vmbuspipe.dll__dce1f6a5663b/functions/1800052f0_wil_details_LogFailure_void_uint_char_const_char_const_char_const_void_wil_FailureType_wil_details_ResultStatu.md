# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800052f0`
- end: `0x1800055e9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003524`
- `0x180003880`

## callees

- `0x1800033c4`
- `0x1800045f4`
- `0x18000501c`
- `0x1800052f0`
- `0x180005c9c`
- `0x180005cc0`
- `0x180005cd4`
- `0x180005cf0`
- `0x180006d24`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005413`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005532`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005532`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055a4`

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
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
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
0x1800052f0  mov     [rsp+arg_10], rbx
0x1800052f5  mov     [rsp+arg_8], edx
0x1800052f9  mov     [rsp+arg_0], rcx
0x1800052fe  push    rbp
0x1800052ff  push    rsi
0x180005300  push    rdi
0x180005301  push    r12
0x180005303  push    r13
0x180005305  push    r14
0x180005307  push    r15
0x180005309  sub     rsp, 40h
0x18000530d  mov     r12, r9
0x180005310  mov     r13, r8
0x180005313  mov     r10, rcx
0x180005316  xor     eax, eax
0x180005318  mov     rsi, [rsp+78h+lpOutputString]
0x180005320  mov     [rsi], ax
0x180005323  mov     rax, [rsp+78h+arg_60]
0x18000532b  mov     byte ptr [rax], 0
0x18000532e  mov     r14, [rsp+78h+arg_38]
0x180005336  mov     edi, [r14]
0x180005339  mov     rbx, [rsp+78h+arg_78]
0x180005341  mov     [rbx+8], edi
0x180005344  mov     eax, [r14+4]
0x180005348  mov     [rbx+0Ch], eax
0x18000534b  xor     ebp, ebp
0x18000534d  mov     r15d, [rsp+78h+arg_30]
0x180005355  mov     ecx, r15d
0x180005358  test    r15d, r15d
0x18000535b  jz      short loc_1800053C3
0x18000535d  sub     ecx, 1
0x180005360  jz      short loc_1800053BA
0x180005362  sub     ecx, 1
0x180005365  jz      short loc_180005375
0x180005367  cmp     ecx, 1
0x18000536a  jnz     short loc_1800053CC
0x18000536c  mov     ecx, edi; this
0x18000536e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005373  jmp     short loc_1800053CA
0x180005375  test    edi, edi
0x180005377  js      short loc_1800053B1
0x180005379  mov     edi, 8007029Ch
0x18000537e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005382  mov     rax, [rsp+78h+arg_28]
0x18000538a  mov     [rsp+78h+var_50], rax; __int64
0x18000538f  mov     rax, [rsp+78h+arg_20]
0x180005397  mov     [rsp+78h+var_58], rax; __int64
0x18000539c  mov     rcx, r10; int
0x18000539f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800053a4  mov     [rbx+8], edi
0x1800053a7  mov     ecx, edi; this
0x1800053a9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800053ae  mov     [rbx+0Ch], eax
0x1800053b1  mov     ecx, edi; this
0x1800053b3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800053b8  jmp     short loc_1800053CA
0x1800053ba  mov     ecx, edi; this
0x1800053bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800053c1  jmp     short loc_1800053CA
0x1800053c3  mov     ecx, edi; this
0x1800053c5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800053ca  mov     ebp, eax
0x1800053cc  mov     [rbx], r15d
0x1800053cf  mov     eax, [rsp+78h+arg_70]
0x1800053d6  mov     [rbx+4], eax
0x1800053d9  cmp     dword ptr [r14+8], 1
0x1800053de  jnz     short loc_1800053E6
0x1800053e0  or      eax, 8
0x1800053e3  mov     [rbx+4], eax
0x1800053e6  mov     eax, 1
0x1800053eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800053f3  inc     eax
0x1800053f5  mov     [rbx+10h], eax
0x1800053f8  mov     rax, [rsp+78h+arg_40]
0x180005400  xor     edi, edi
0x180005402  test    rax, rax
0x180005405  jz      short loc_18000540C
0x180005407  cmp     [rax], di
0x18000540a  jnz     short loc_18000540F
0x18000540c  mov     rax, rdi
0x18000540f  mov     [rbx+18h], rax
0x180005413  call    cs:__imp_GetCurrentThreadId
0x180005419  mov     [rbx+20h], eax
0x18000541c  mov     [rbx+38h], r13
0x180005420  mov     eax, [rsp+78h+arg_8]
0x180005427  mov     [rbx+40h], eax
0x18000542a  mov     [rbx+44h], ebp
0x18000542d  mov     rax, [rsp+78h+arg_20]
0x180005435  mov     [rbx+28h], rax
0x180005439  mov     [rbx+30h], r12
0x18000543d  mov     rax, [rsp+78h+arg_28]
0x180005445  mov     [rbx+88h], rax
0x18000544c  mov     rax, [rsp+78h+arg_0]
0x180005454  mov     [rbx+90h], rax
0x18000545b  mov     [rbx+48h], rdi
0x18000545f  xorps   xmm0, xmm0
0x180005462  xor     eax, eax
0x180005464  movups  xmmword ptr [rbx+68h], xmm0
0x180005468  mov     [rbx+78h], rax
0x18000546c  movups  xmmword ptr [rbx+50h], xmm0
0x180005470  mov     [rbx+60h], rax
0x180005474  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000547b  test    rax, rax
0x18000547e  jz      short loc_180005487
0x180005480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005485  jmp     short loc_18000548A
0x180005487  mov     rax, rdi
0x18000548a  mov     [rbx+80h], rax
0x180005491  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005498  test    rax, rax
0x18000549b  jz      short loc_1800054A5
0x18000549d  mov     rcx, rbx
0x1800054a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800054ac  test    rax, rax
0x1800054af  jz      short loc_1800054C7
0x1800054b1  mov     r8d, 400h
0x1800054b7  mov     rdx, [rsp+78h+arg_60]
0x1800054bf  mov     rcx, rbx
0x1800054c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800054ce  test    rax, rax
0x1800054d1  jz      short loc_1800054DB
0x1800054d3  mov     rcx, rbx
0x1800054d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800054e2  test    rax, rax
0x1800054e5  jz      short loc_1800054F5
0x1800054e7  test    byte ptr [rbx+4], 2
0x1800054eb  jnz     short loc_1800054F5
0x1800054ed  mov     rcx, rbx
0x1800054f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f5  cmp     [rbx+8], edi
0x1800054f8  jl      short loc_180005514
0x1800054fa  cmp     r15d, 3
0x1800054fe  jnz     loc_1800055E3
0x180005504  mov     ecx, 8000FFFFh; this
0x180005509  mov     [rbx+8], ecx
0x18000550c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005511  mov     [rbx+0Ch], eax
0x180005514  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000551b  jnz     short loc_18000553C
0x18000551d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005524  test    rax, rax
0x180005527  jz      short loc_180005532
0x180005529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552e  test    al, al
0x180005530  jmp     short loc_18000553A
0x180005532  call    cs:__imp_IsDebuggerPresent
0x180005538  test    eax, eax
0x18000553a  jz      short loc_180005542
0x18000553c  test    byte ptr [rbx+4], 2
0x180005540  jz      short loc_180005566
0x180005542  mov     rax, cs:g_pfnResultLoggingCallback
0x180005549  test    rax, rax
0x18000554c  jz      short loc_1800055AA
0x18000554e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005555  jnz     short loc_1800055AA
0x180005557  xor     r8d, r8d
0x18000555a  xor     edx, edx
0x18000555c  mov     rcx, rbx
0x18000555f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005564  jmp     short loc_1800055AA
0x180005566  mov     ebp, 800h
0x18000556b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005572  test    rax, rax
0x180005575  jz      short loc_18000558E
0x180005577  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000557e  jnz     short loc_18000558E
0x180005580  mov     r8d, ebp
0x180005583  mov     rdx, rsi
0x180005586  mov     rcx, rbx
0x180005589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000558e  cmp     [rsi], di
0x180005591  jnz     short loc_1800055A1
0x180005593  mov     r8, rbx; unsigned __int64
0x180005596  mov     rdx, rbp; unsigned __int16 *
0x180005599  mov     rcx, rsi; this
0x18000559c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800055a1  mov     rcx, rsi; lpOutputString
0x1800055a4  call    cs:__imp_OutputDebugStringW
0x1800055aa  test    byte ptr [rbx+4], 4
0x1800055ae  jnz     short loc_1800055B9
0x1800055b0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800055b7  jz      short loc_1800055CB
0x1800055b9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800055c0  test    rax, rax
0x1800055c3  jz      short loc_1800055CB
0x1800055c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ca  nop
0x1800055cb  mov     rbx, [rsp+78h+arg_10]
0x1800055d3  add     rsp, 40h
0x1800055d7  pop     r15
0x1800055d9  pop     r14
0x1800055db  pop     r13
0x1800055dd  pop     r12
0x1800055df  pop     rdi
0x1800055e0  pop     rsi
0x1800055e1  pop     rbp
0x1800055e2  retn
0x1800055e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
