# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002832c`
- end: `0x180028637`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800262b8`
- `0x180026610`

## callees

- `0x180014b58`
- `0x180026200`
- `0x180027d34`
- `0x18002832c`
- `0x18002893c`
- `0x180028960`
- `0x180028974`
- `0x180028994`
- `0x18002932c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002844f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002844f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800285ec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800285ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180028574`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180028574`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x18002832c  mov     [rsp+arg_10], rbx
0x180028331  mov     [rsp+arg_8], edx
0x180028335  mov     [rsp+arg_0], rcx
0x18002833a  push    rbp
0x18002833b  push    rsi
0x18002833c  push    rdi
0x18002833d  push    r12
0x18002833f  push    r13
0x180028341  push    r14
0x180028343  push    r15
0x180028345  sub     rsp, 40h
0x180028349  mov     r14, [rsp+78h+arg_38]
0x180028351  xor     eax, eax
0x180028353  mov     rbx, [rsp+78h+arg_78]
0x18002835b  xor     ebp, ebp
0x18002835d  mov     r15d, [rsp+78h+arg_30]
0x180028365  mov     r10, rcx
0x180028368  mov     rsi, [rsp+78h+lpOutputString]
0x180028370  mov     r12, r9
0x180028373  mov     r13, r8
0x180028376  mov     ecx, r15d
0x180028379  mov     [rsi], ax
0x18002837c  mov     rax, [rsp+78h+arg_60]
0x180028384  mov     byte ptr [rax], 0
0x180028387  mov     edi, [r14]
0x18002838a  mov     [rbx+8], edi
0x18002838d  mov     eax, [r14+4]
0x180028391  mov     [rbx+0Ch], eax
0x180028394  test    r15d, r15d
0x180028397  jz      short loc_1800283FF
0x180028399  sub     ecx, 1
0x18002839c  jz      short loc_1800283F6
0x18002839e  sub     ecx, 1
0x1800283a1  jz      short loc_1800283B1
0x1800283a3  cmp     ecx, 1
0x1800283a6  jnz     short loc_180028408
0x1800283a8  mov     ecx, edi; this
0x1800283aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800283af  jmp     short loc_180028406
0x1800283b1  test    edi, edi
0x1800283b3  js      short loc_1800283ED
0x1800283b5  mov     rax, [rsp+78h+arg_28]
0x1800283bd  mov     edi, 8007029Ch
0x1800283c2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800283c6  mov     rcx, r10; int
0x1800283c9  mov     [rsp+78h+var_50], rax; __int64
0x1800283ce  mov     rax, [rsp+78h+arg_20]
0x1800283d6  mov     [rsp+78h+var_58], rax; __int64
0x1800283db  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800283e0  mov     ecx, edi; this
0x1800283e2  mov     [rbx+8], edi
0x1800283e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800283ea  mov     [rbx+0Ch], eax
0x1800283ed  mov     ecx, edi; this
0x1800283ef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800283f4  jmp     short loc_180028406
0x1800283f6  mov     ecx, edi; this
0x1800283f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800283fd  jmp     short loc_180028406
0x1800283ff  mov     ecx, edi; this
0x180028401  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180028406  mov     ebp, eax
0x180028408  mov     eax, [rsp+78h+arg_70]
0x18002840f  mov     [rbx+4], eax
0x180028412  mov     [rbx], r15d
0x180028415  cmp     dword ptr [r14+8], 1
0x18002841a  jnz     short loc_180028422
0x18002841c  or      eax, 8
0x18002841f  mov     [rbx+4], eax
0x180028422  mov     eax, 1
0x180028427  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002842f  inc     eax
0x180028431  xor     edi, edi
0x180028433  mov     [rbx+10h], eax
0x180028436  mov     rax, [rsp+78h+arg_40]
0x18002843e  test    rax, rax
0x180028441  jz      short loc_180028448
0x180028443  cmp     [rax], di
0x180028446  jnz     short loc_18002844B
0x180028448  mov     rax, rdi
0x18002844b  mov     [rbx+18h], rax
0x18002844f  call    cs:__imp_GetCurrentThreadId
0x180028456  nop     dword ptr [rax+rax+00h]
0x18002845b  mov     [rbx+38h], r13
0x18002845f  xorps   xmm0, xmm0
0x180028462  mov     [rbx+20h], eax
0x180028465  mov     eax, [rsp+78h+arg_8]
0x18002846c  mov     [rbx+40h], eax
0x18002846f  mov     rax, [rsp+78h+arg_20]
0x180028477  mov     [rbx+28h], rax
0x18002847b  mov     rax, [rsp+78h+arg_28]
0x180028483  mov     [rbx+88h], rax
0x18002848a  mov     rax, [rsp+78h+arg_0]
0x180028492  mov     [rbx+90h], rax
0x180028499  xor     eax, eax
0x18002849b  mov     [rbx+44h], ebp
0x18002849e  mov     [rbx+30h], r12
0x1800284a2  mov     [rbx+48h], rdi
0x1800284a6  movups  xmmword ptr [rbx+68h], xmm0
0x1800284aa  mov     [rbx+78h], rax
0x1800284ae  movups  xmmword ptr [rbx+50h], xmm0
0x1800284b2  mov     [rbx+60h], rax
0x1800284b6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800284bd  test    rax, rax
0x1800284c0  jz      short loc_1800284C9
0x1800284c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284c7  jmp     short loc_1800284CC
0x1800284c9  mov     rax, rdi
0x1800284cc  mov     [rbx+80h], rax
0x1800284d3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800284da  test    rax, rax
0x1800284dd  jz      short loc_1800284E7
0x1800284df  mov     rcx, rbx
0x1800284e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284e7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800284ee  test    rax, rax
0x1800284f1  jz      short loc_180028509
0x1800284f3  mov     rdx, [rsp+78h+arg_60]
0x1800284fb  mov     r8d, 400h
0x180028501  mov     rcx, rbx
0x180028504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028509  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180028510  test    rax, rax
0x180028513  jz      short loc_18002851D
0x180028515  mov     rcx, rbx
0x180028518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002851d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180028524  test    rax, rax
0x180028527  jz      short loc_180028537
0x180028529  test    byte ptr [rbx+4], 2
0x18002852d  jnz     short loc_180028537
0x18002852f  mov     rcx, rbx
0x180028532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028537  cmp     [rbx+8], edi
0x18002853a  jl      short loc_180028556
0x18002853c  cmp     r15d, 3
0x180028540  jnz     loc_180028631
0x180028546  mov     ecx, 8000FFFFh; this
0x18002854b  mov     [rbx+8], ecx
0x18002854e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180028553  mov     [rbx+0Ch], eax
0x180028556  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002855d  jnz     short loc_180028584
0x18002855f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180028566  test    rax, rax
0x180028569  jz      short loc_180028574
0x18002856b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028570  test    al, al
0x180028572  jmp     short loc_180028582
0x180028574  call    cs:__imp_IsDebuggerPresent
0x18002857b  nop     dword ptr [rax+rax+00h]
0x180028580  test    eax, eax
0x180028582  jz      short loc_18002858A
0x180028584  test    byte ptr [rbx+4], 2
0x180028588  jz      short loc_1800285AE
0x18002858a  mov     rax, cs:g_pfnResultLoggingCallback
0x180028591  test    rax, rax
0x180028594  jz      short loc_1800285F8
0x180028596  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002859d  jnz     short loc_1800285F8
0x18002859f  xor     r8d, r8d
0x1800285a2  xor     edx, edx
0x1800285a4  mov     rcx, rbx
0x1800285a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285ac  jmp     short loc_1800285F8
0x1800285ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800285b5  mov     ebp, 800h
0x1800285ba  test    rax, rax
0x1800285bd  jz      short loc_1800285D6
0x1800285bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800285c6  jnz     short loc_1800285D6
0x1800285c8  mov     r8d, ebp
0x1800285cb  mov     rdx, rsi
0x1800285ce  mov     rcx, rbx
0x1800285d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285d6  cmp     [rsi], di
0x1800285d9  jnz     short loc_1800285E9
0x1800285db  mov     r8, rbx; unsigned __int64
0x1800285de  mov     rdx, rbp; unsigned __int16 *
0x1800285e1  mov     rcx, rsi; this
0x1800285e4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800285e9  mov     rcx, rsi; lpOutputString
0x1800285ec  call    cs:__imp_OutputDebugStringW
0x1800285f3  nop     dword ptr [rax+rax+00h]
0x1800285f8  test    byte ptr [rbx+4], 4
0x1800285fc  jnz     short loc_180028607
0x1800285fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180028605  jz      short loc_180028618
0x180028607  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002860e  test    rax, rax
0x180028611  jz      short loc_180028618
0x180028613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028618  mov     rbx, [rsp+78h+arg_10]
0x180028620  add     rsp, 40h
0x180028624  pop     r15
0x180028626  pop     r14
0x180028628  pop     r13
0x18002862a  pop     r12
0x18002862c  pop     rdi
0x18002862d  pop     rsi
0x18002862e  pop     rbp
0x18002862f  retn
0x180028631  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
