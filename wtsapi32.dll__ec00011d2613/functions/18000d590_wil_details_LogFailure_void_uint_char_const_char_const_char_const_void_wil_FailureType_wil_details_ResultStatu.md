# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000d590`
- end: `0x18000d884`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000b7bc`
- `0x18000b870`
- `0x18000b960`

## callees

- `0x18000b710`
- `0x18000cb14`
- `0x18000d2ec`
- `0x18000d590`
- `0x18000dcec`
- `0x18000dd10`
- `0x18000dd24`
- `0x18000dd40`
- `0x18000e75c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d6b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d7d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d7d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d846`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d846`

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
0x18000d590  mov     [rsp+arg_10], rbx
0x18000d595  mov     [rsp+arg_8], edx
0x18000d599  mov     [rsp+arg_0], rcx
0x18000d59e  push    rbp
0x18000d59f  push    rsi
0x18000d5a0  push    rdi
0x18000d5a1  push    r12
0x18000d5a3  push    r13
0x18000d5a5  push    r14
0x18000d5a7  push    r15
0x18000d5a9  sub     rsp, 40h
0x18000d5ad  mov     r14, [rsp+78h+arg_38]
0x18000d5b5  xor     eax, eax
0x18000d5b7  mov     rbx, [rsp+78h+arg_78]
0x18000d5bf  xor     ebp, ebp
0x18000d5c1  mov     r15d, [rsp+78h+arg_30]
0x18000d5c9  mov     r10, rcx
0x18000d5cc  mov     rsi, [rsp+78h+lpOutputString]
0x18000d5d4  mov     r12, r9
0x18000d5d7  mov     r13, r8
0x18000d5da  mov     ecx, r15d
0x18000d5dd  mov     [rsi], ax
0x18000d5e0  mov     rax, [rsp+78h+arg_60]
0x18000d5e8  mov     byte ptr [rax], 0
0x18000d5eb  mov     edi, [r14]
0x18000d5ee  mov     [rbx+8], edi
0x18000d5f1  mov     eax, [r14+4]
0x18000d5f5  mov     [rbx+0Ch], eax
0x18000d5f8  test    r15d, r15d
0x18000d5fb  jz      short loc_18000D663
0x18000d5fd  sub     ecx, 1
0x18000d600  jz      short loc_18000D65A
0x18000d602  sub     ecx, 1
0x18000d605  jz      short loc_18000D615
0x18000d607  cmp     ecx, 1
0x18000d60a  jnz     short loc_18000D66C
0x18000d60c  mov     ecx, edi; this
0x18000d60e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000d613  jmp     short loc_18000D66A
0x18000d615  test    edi, edi
0x18000d617  js      short loc_18000D651
0x18000d619  mov     rax, [rsp+78h+arg_28]
0x18000d621  mov     edi, 8007029Ch
0x18000d626  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000d62a  mov     rcx, r10; int
0x18000d62d  mov     [rsp+78h+var_50], rax; __int64
0x18000d632  mov     rax, [rsp+78h+arg_20]
0x18000d63a  mov     [rsp+78h+var_58], rax; __int64
0x18000d63f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d644  mov     ecx, edi; this
0x18000d646  mov     [rbx+8], edi
0x18000d649  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d64e  mov     [rbx+0Ch], eax
0x18000d651  mov     ecx, edi; this
0x18000d653  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000d658  jmp     short loc_18000D66A
0x18000d65a  mov     ecx, edi; this
0x18000d65c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d661  jmp     short loc_18000D66A
0x18000d663  mov     ecx, edi; this
0x18000d665  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d66a  mov     ebp, eax
0x18000d66c  mov     eax, [rsp+78h+arg_70]
0x18000d673  mov     [rbx+4], eax
0x18000d676  mov     [rbx], r15d
0x18000d679  cmp     dword ptr [r14+8], 1
0x18000d67e  jnz     short loc_18000D686
0x18000d680  or      eax, 8
0x18000d683  mov     [rbx+4], eax
0x18000d686  mov     eax, 1
0x18000d68b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d693  inc     eax
0x18000d695  xor     edi, edi
0x18000d697  mov     [rbx+10h], eax
0x18000d69a  mov     rax, [rsp+78h+arg_40]
0x18000d6a2  test    rax, rax
0x18000d6a5  jz      short loc_18000D6AC
0x18000d6a7  cmp     [rax], di
0x18000d6aa  jnz     short loc_18000D6AF
0x18000d6ac  mov     rax, rdi
0x18000d6af  mov     [rbx+18h], rax
0x18000d6b3  call    cs:__imp_GetCurrentThreadId
0x18000d6b9  mov     [rbx+38h], r13
0x18000d6bd  xorps   xmm0, xmm0
0x18000d6c0  mov     [rbx+20h], eax
0x18000d6c3  mov     eax, [rsp+78h+arg_8]
0x18000d6ca  mov     [rbx+40h], eax
0x18000d6cd  mov     rax, [rsp+78h+arg_20]
0x18000d6d5  mov     [rbx+28h], rax
0x18000d6d9  mov     rax, [rsp+78h+arg_28]
0x18000d6e1  mov     [rbx+88h], rax
0x18000d6e8  mov     rax, [rsp+78h+arg_0]
0x18000d6f0  mov     [rbx+90h], rax
0x18000d6f7  xor     eax, eax
0x18000d6f9  mov     [rbx+44h], ebp
0x18000d6fc  mov     [rbx+30h], r12
0x18000d700  mov     [rbx+48h], rdi
0x18000d704  movups  xmmword ptr [rbx+68h], xmm0
0x18000d708  mov     [rbx+78h], rax
0x18000d70c  movups  xmmword ptr [rbx+50h], xmm0
0x18000d710  mov     [rbx+60h], rax
0x18000d714  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d71b  test    rax, rax
0x18000d71e  jz      short loc_18000D727
0x18000d720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d725  jmp     short loc_18000D72A
0x18000d727  mov     rax, rdi
0x18000d72a  mov     [rbx+80h], rax
0x18000d731  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d738  test    rax, rax
0x18000d73b  jz      short loc_18000D745
0x18000d73d  mov     rcx, rbx
0x18000d740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d745  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d74c  test    rax, rax
0x18000d74f  jz      short loc_18000D767
0x18000d751  mov     rdx, [rsp+78h+arg_60]
0x18000d759  mov     r8d, 400h
0x18000d75f  mov     rcx, rbx
0x18000d762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d767  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d76e  test    rax, rax
0x18000d771  jz      short loc_18000D77B
0x18000d773  mov     rcx, rbx
0x18000d776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d77b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d782  test    rax, rax
0x18000d785  jz      short loc_18000D795
0x18000d787  test    byte ptr [rbx+4], 2
0x18000d78b  jnz     short loc_18000D795
0x18000d78d  mov     rcx, rbx
0x18000d790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d795  cmp     [rbx+8], edi
0x18000d798  jl      short loc_18000D7B6
0x18000d79a  cmp     r15d, 3
0x18000d79e  jz      short loc_18000D7A6
0x18000d7a0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000d7a6  mov     ecx, 8000FFFFh; this
0x18000d7ab  mov     [rbx+8], ecx
0x18000d7ae  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d7b3  mov     [rbx+0Ch], eax
0x18000d7b6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000d7bd  jnz     short loc_18000D7DE
0x18000d7bf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d7c6  test    rax, rax
0x18000d7c9  jz      short loc_18000D7D4
0x18000d7cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d0  test    al, al
0x18000d7d2  jmp     short loc_18000D7DC
0x18000d7d4  call    cs:__imp_IsDebuggerPresent
0x18000d7da  test    eax, eax
0x18000d7dc  jz      short loc_18000D7E4
0x18000d7de  test    byte ptr [rbx+4], 2
0x18000d7e2  jz      short loc_18000D808
0x18000d7e4  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d7eb  test    rax, rax
0x18000d7ee  jz      short loc_18000D84C
0x18000d7f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d7f7  jnz     short loc_18000D84C
0x18000d7f9  xor     r8d, r8d
0x18000d7fc  xor     edx, edx
0x18000d7fe  mov     rcx, rbx
0x18000d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d806  jmp     short loc_18000D84C
0x18000d808  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d80f  mov     ebp, 800h
0x18000d814  test    rax, rax
0x18000d817  jz      short loc_18000D830
0x18000d819  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d820  jnz     short loc_18000D830
0x18000d822  mov     r8d, ebp
0x18000d825  mov     rdx, rsi
0x18000d828  mov     rcx, rbx
0x18000d82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d830  cmp     [rsi], di
0x18000d833  jnz     short loc_18000D843
0x18000d835  mov     r8, rbx; unsigned __int64
0x18000d838  mov     rdx, rbp; unsigned __int16 *
0x18000d83b  mov     rcx, rsi; this
0x18000d83e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000d843  mov     rcx, rsi; lpOutputString
0x18000d846  call    cs:__imp_OutputDebugStringW
0x18000d84c  test    byte ptr [rbx+4], 4
0x18000d850  jnz     short loc_18000D85B
0x18000d852  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000d859  jz      short loc_18000D86C
0x18000d85b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d862  test    rax, rax
0x18000d865  jz      short loc_18000D86C
0x18000d867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d86c  mov     rbx, [rsp+78h+arg_10]
0x18000d874  add     rsp, 40h
0x18000d878  pop     r15
0x18000d87a  pop     r14
0x18000d87c  pop     r13
0x18000d87e  pop     r12
0x18000d880  pop     rdi
0x18000d881  pop     rsi
0x18000d882  pop     rbp
0x18000d883  retn
```
