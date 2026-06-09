# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008084`
- end: `0x180008390`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005c80`

## callees

- `0x180005694`
- `0x180007494`
- `0x180007d7c`
- `0x180008084`
- `0x180008d24`
- `0x180008d50`
- `0x180008ef0`
- `0x180008f10`
- `0x18000a7e8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081a7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800082cc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800082cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008344`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008344`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x180008084  mov     [rsp+arg_10], rbx
0x180008089  mov     [rsp+arg_8], edx
0x18000808d  mov     [rsp+arg_0], rcx
0x180008092  push    rbp
0x180008093  push    rsi
0x180008094  push    rdi
0x180008095  push    r12
0x180008097  push    r13
0x180008099  push    r14
0x18000809b  push    r15
0x18000809d  sub     rsp, 40h
0x1800080a1  mov     r12, r9
0x1800080a4  mov     r13, r8
0x1800080a7  mov     r10, rcx
0x1800080aa  xor     eax, eax
0x1800080ac  mov     rsi, [rsp+78h+lpOutputString]
0x1800080b4  mov     [rsi], ax
0x1800080b7  mov     rax, [rsp+78h+arg_60]
0x1800080bf  mov     byte ptr [rax], 0
0x1800080c2  mov     r14, [rsp+78h+arg_38]
0x1800080ca  mov     edi, [r14]
0x1800080cd  mov     rbx, [rsp+78h+arg_78]
0x1800080d5  mov     [rbx+8], edi
0x1800080d8  mov     eax, [r14+4]
0x1800080dc  mov     [rbx+0Ch], eax
0x1800080df  xor     ebp, ebp
0x1800080e1  mov     r15d, [rsp+78h+arg_30]
0x1800080e9  mov     ecx, r15d
0x1800080ec  test    r15d, r15d
0x1800080ef  jz      short loc_180008157
0x1800080f1  sub     ecx, 1
0x1800080f4  jz      short loc_18000814E
0x1800080f6  sub     ecx, 1
0x1800080f9  jz      short loc_180008109
0x1800080fb  cmp     ecx, 1
0x1800080fe  jnz     short loc_180008160
0x180008100  mov     ecx, edi; this
0x180008102  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008107  jmp     short loc_18000815E
0x180008109  test    edi, edi
0x18000810b  js      short loc_180008145
0x18000810d  mov     edi, 8007029Ch
0x180008112  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008116  mov     rax, [rsp+78h+arg_28]
0x18000811e  mov     [rsp+78h+var_50], rax; __int64
0x180008123  mov     rax, [rsp+78h+arg_20]
0x18000812b  mov     [rsp+78h+var_58], rax; __int64
0x180008130  mov     rcx, r10; int
0x180008133  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008138  mov     [rbx+8], edi
0x18000813b  mov     ecx, edi; this
0x18000813d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008142  mov     [rbx+0Ch], eax
0x180008145  mov     ecx, edi; this
0x180008147  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000814c  jmp     short loc_18000815E
0x18000814e  mov     ecx, edi; this
0x180008150  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008155  jmp     short loc_18000815E
0x180008157  mov     ecx, edi; this
0x180008159  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000815e  mov     ebp, eax
0x180008160  mov     [rbx], r15d
0x180008163  mov     eax, [rsp+78h+arg_70]
0x18000816a  mov     [rbx+4], eax
0x18000816d  cmp     dword ptr [r14+8], 1
0x180008172  jnz     short loc_18000817A
0x180008174  or      eax, 8
0x180008177  mov     [rbx+4], eax
0x18000817a  mov     eax, 1
0x18000817f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008187  inc     eax
0x180008189  mov     [rbx+10h], eax
0x18000818c  mov     rax, [rsp+78h+arg_40]
0x180008194  xor     edi, edi
0x180008196  test    rax, rax
0x180008199  jz      short loc_1800081A0
0x18000819b  cmp     [rax], di
0x18000819e  jnz     short loc_1800081A3
0x1800081a0  mov     rax, rdi
0x1800081a3  mov     [rbx+18h], rax
0x1800081a7  call    cs:__imp_GetCurrentThreadId
0x1800081ae  nop     dword ptr [rax+rax+00h]
0x1800081b3  mov     [rbx+20h], eax
0x1800081b6  mov     [rbx+38h], r13
0x1800081ba  mov     eax, [rsp+78h+arg_8]
0x1800081c1  mov     [rbx+40h], eax
0x1800081c4  mov     [rbx+44h], ebp
0x1800081c7  mov     rax, [rsp+78h+arg_20]
0x1800081cf  mov     [rbx+28h], rax
0x1800081d3  mov     [rbx+30h], r12
0x1800081d7  mov     rax, [rsp+78h+arg_28]
0x1800081df  mov     [rbx+88h], rax
0x1800081e6  mov     rax, [rsp+78h+arg_0]
0x1800081ee  mov     [rbx+90h], rax
0x1800081f5  mov     [rbx+48h], rdi
0x1800081f9  xorps   xmm0, xmm0
0x1800081fc  xor     eax, eax
0x1800081fe  movups  xmmword ptr [rbx+68h], xmm0
0x180008202  mov     [rbx+78h], rax
0x180008206  movups  xmmword ptr [rbx+50h], xmm0
0x18000820a  mov     [rbx+60h], rax
0x18000820e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008215  test    rax, rax
0x180008218  jz      short loc_180008221
0x18000821a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000821f  jmp     short loc_180008224
0x180008221  mov     rax, rdi
0x180008224  mov     [rbx+80h], rax
0x18000822b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008232  test    rax, rax
0x180008235  jz      short loc_18000823F
0x180008237  mov     rcx, rbx
0x18000823a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000823f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008246  test    rax, rax
0x180008249  jz      short loc_180008261
0x18000824b  mov     r8d, 400h
0x180008251  mov     rdx, [rsp+78h+arg_60]
0x180008259  mov     rcx, rbx
0x18000825c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008261  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008268  test    rax, rax
0x18000826b  jz      short loc_180008275
0x18000826d  mov     rcx, rbx
0x180008270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008275  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000827c  test    rax, rax
0x18000827f  jz      short loc_18000828F
0x180008281  test    byte ptr [rbx+4], 2
0x180008285  jnz     short loc_18000828F
0x180008287  mov     rcx, rbx
0x18000828a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000828f  cmp     [rbx+8], edi
0x180008292  jl      short loc_1800082AE
0x180008294  cmp     r15d, 3
0x180008298  jnz     loc_18000838A
0x18000829e  mov     ecx, 8000FFFFh; this
0x1800082a3  mov     [rbx+8], ecx
0x1800082a6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800082ab  mov     [rbx+0Ch], eax
0x1800082ae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800082b5  jnz     short loc_1800082DC
0x1800082b7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800082be  test    rax, rax
0x1800082c1  jz      short loc_1800082CC
0x1800082c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c8  test    al, al
0x1800082ca  jmp     short loc_1800082DA
0x1800082cc  call    cs:__imp_IsDebuggerPresent
0x1800082d3  nop     dword ptr [rax+rax+00h]
0x1800082d8  test    eax, eax
0x1800082da  jz      short loc_1800082E2
0x1800082dc  test    byte ptr [rbx+4], 2
0x1800082e0  jz      short loc_180008306
0x1800082e2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800082e9  test    rax, rax
0x1800082ec  jz      short loc_180008350
0x1800082ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800082f5  jnz     short loc_180008350
0x1800082f7  xor     r8d, r8d
0x1800082fa  xor     edx, edx
0x1800082fc  mov     rcx, rbx
0x1800082ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008304  jmp     short loc_180008350
0x180008306  mov     ebp, 800h
0x18000830b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008312  test    rax, rax
0x180008315  jz      short loc_18000832E
0x180008317  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000831e  jnz     short loc_18000832E
0x180008320  mov     r8d, ebp
0x180008323  mov     rdx, rsi
0x180008326  mov     rcx, rbx
0x180008329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000832e  cmp     [rsi], di
0x180008331  jnz     short loc_180008341
0x180008333  mov     r8, rbx; unsigned __int64
0x180008336  mov     rdx, rbp; wchar_t *
0x180008339  mov     rcx, rsi; pszDest
0x18000833c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008341  mov     rcx, rsi; lpOutputString
0x180008344  call    cs:__imp_OutputDebugStringW
0x18000834b  nop     dword ptr [rax+rax+00h]
0x180008350  test    byte ptr [rbx+4], 4
0x180008354  jnz     short loc_18000835F
0x180008356  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000835d  jz      short loc_180008371
0x18000835f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008366  test    rax, rax
0x180008369  jz      short loc_180008371
0x18000836b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008370  nop
0x180008371  mov     rbx, [rsp+78h+arg_10]
0x180008379  add     rsp, 40h
0x18000837d  pop     r15
0x18000837f  pop     r14
0x180008381  pop     r13
0x180008383  pop     r12
0x180008385  pop     rdi
0x180008386  pop     rsi
0x180008387  pop     rbp
0x180008388  retn
0x18000838a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
