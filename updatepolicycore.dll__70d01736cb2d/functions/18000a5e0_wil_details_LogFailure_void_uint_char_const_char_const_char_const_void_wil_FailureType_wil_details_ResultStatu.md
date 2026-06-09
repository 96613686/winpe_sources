# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a5e0`
- end: `0x18000a8e3`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000be28`

## callees

- `0x1800091d4`
- `0x180009640`
- `0x18000965c`
- `0x180009678`
- `0x1800096a0`
- `0x1800098e0`
- `0x18000a5e0`
- `0x18000ab40`
- `0x18000b820`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a705`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a705`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a89e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a89e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a824`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a824`

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
0x18000a5e0  mov     [rsp+arg_10], rbx
0x18000a5e5  mov     [rsp+arg_8], edx
0x18000a5e9  mov     [rsp+arg_0], rcx
0x18000a5ee  push    rbp
0x18000a5ef  push    rsi
0x18000a5f0  push    rdi
0x18000a5f1  push    r12
0x18000a5f3  push    r13
0x18000a5f5  push    r14
0x18000a5f7  push    r15
0x18000a5f9  sub     rsp, 40h
0x18000a5fd  mov     r12, r9
0x18000a600  mov     r13, r8
0x18000a603  mov     r10, rcx
0x18000a606  xor     r8d, r8d
0x18000a609  mov     r14, [rsp+78h+lpOutputString]
0x18000a611  mov     [r14], r8w
0x18000a615  mov     rax, [rsp+78h+arg_60]
0x18000a61d  mov     [rax], r8b
0x18000a620  mov     r15, [rsp+78h+arg_38]
0x18000a628  mov     edi, [r15]
0x18000a62b  mov     rbx, [rsp+78h+arg_78]
0x18000a633  mov     [rbx+8], edi
0x18000a636  mov     eax, [r15+4]
0x18000a63a  mov     [rbx+0Ch], eax
0x18000a63d  mov     esi, r8d
0x18000a640  mov     ebp, [rsp+78h+arg_30]
0x18000a647  mov     ecx, ebp
0x18000a649  test    ebp, ebp
0x18000a64b  jz      short loc_18000A6B6
0x18000a64d  sub     ecx, 1
0x18000a650  jz      short loc_18000A6AD
0x18000a652  sub     ecx, 1
0x18000a655  jz      short loc_18000A665
0x18000a657  cmp     ecx, 1
0x18000a65a  jnz     short loc_18000A6BF
0x18000a65c  mov     ecx, edi; this
0x18000a65e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a663  jmp     short loc_18000A6BD
0x18000a665  test    edi, edi
0x18000a667  js      short loc_18000A6A4
0x18000a669  mov     edi, 8007029Ch
0x18000a66e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a672  mov     rax, [rsp+78h+arg_28]
0x18000a67a  mov     [rsp+78h+var_50], rax; __int64
0x18000a67f  mov     rax, [rsp+78h+arg_20]
0x18000a687  mov     [rsp+78h+var_58], rax; __int64
0x18000a68c  mov     r8, r13; int
0x18000a68f  mov     rcx, r10; int
0x18000a692  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a697  mov     [rbx+8], edi
0x18000a69a  mov     ecx, edi; this
0x18000a69c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a6a1  mov     [rbx+0Ch], eax
0x18000a6a4  mov     ecx, edi; this
0x18000a6a6  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a6ab  jmp     short loc_18000A6BD
0x18000a6ad  mov     ecx, edi; this
0x18000a6af  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a6b4  jmp     short loc_18000A6BD
0x18000a6b6  mov     ecx, edi; this
0x18000a6b8  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a6bd  mov     esi, eax
0x18000a6bf  mov     [rbx], ebp
0x18000a6c1  mov     eax, [rsp+78h+arg_70]
0x18000a6c8  mov     [rbx+4], eax
0x18000a6cb  cmp     dword ptr [r15+8], 1
0x18000a6d0  jnz     short loc_18000A6D8
0x18000a6d2  or      eax, 8
0x18000a6d5  mov     [rbx+4], eax
0x18000a6d8  mov     eax, 1
0x18000a6dd  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a6e5  inc     eax
0x18000a6e7  mov     [rbx+10h], eax
0x18000a6ea  mov     rax, [rsp+78h+arg_40]
0x18000a6f2  xor     edi, edi
0x18000a6f4  test    rax, rax
0x18000a6f7  jz      short loc_18000A6FE
0x18000a6f9  cmp     [rax], di
0x18000a6fc  jnz     short loc_18000A701
0x18000a6fe  mov     rax, rdi
0x18000a701  mov     [rbx+18h], rax
0x18000a705  call    cs:__imp_GetCurrentThreadId
0x18000a70b  mov     [rbx+20h], eax
0x18000a70e  mov     [rbx+38h], r13
0x18000a712  mov     eax, [rsp+78h+arg_8]
0x18000a719  mov     [rbx+40h], eax
0x18000a71c  mov     [rbx+44h], esi
0x18000a71f  mov     rax, [rsp+78h+arg_20]
0x18000a727  mov     [rbx+28h], rax
0x18000a72b  mov     [rbx+30h], r12
0x18000a72f  mov     rax, [rsp+78h+arg_28]
0x18000a737  mov     [rbx+88h], rax
0x18000a73e  mov     rax, [rsp+78h+arg_0]
0x18000a746  mov     [rbx+90h], rax
0x18000a74d  mov     [rbx+48h], rdi
0x18000a751  xorps   xmm0, xmm0
0x18000a754  xor     eax, eax
0x18000a756  movups  xmmword ptr [rbx+68h], xmm0
0x18000a75a  mov     [rbx+78h], rax
0x18000a75e  movups  xmmword ptr [rbx+50h], xmm0
0x18000a762  mov     [rbx+60h], rax
0x18000a766  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a76d  test    rax, rax
0x18000a770  jz      short loc_18000A779
0x18000a772  call    _guard_dispatch_icall
0x18000a777  jmp     short loc_18000A77C
0x18000a779  mov     rax, rdi
0x18000a77c  mov     [rbx+80h], rax
0x18000a783  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a78a  test    rax, rax
0x18000a78d  jz      short loc_18000A797
0x18000a78f  mov     rcx, rbx
0x18000a792  call    _guard_dispatch_icall
0x18000a797  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a79e  test    rax, rax
0x18000a7a1  jz      short loc_18000A7B9
0x18000a7a3  mov     r8d, 400h
0x18000a7a9  mov     rdx, [rsp+78h+arg_60]
0x18000a7b1  mov     rcx, rbx
0x18000a7b4  call    _guard_dispatch_icall
0x18000a7b9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a7c0  test    rax, rax
0x18000a7c3  jz      short loc_18000A7CD
0x18000a7c5  mov     rcx, rbx
0x18000a7c8  call    _guard_dispatch_icall
0x18000a7cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a7d4  test    rax, rax
0x18000a7d7  jz      short loc_18000A7E7
0x18000a7d9  test    byte ptr [rbx+4], 2
0x18000a7dd  jnz     short loc_18000A7E7
0x18000a7df  mov     rcx, rbx
0x18000a7e2  call    _guard_dispatch_icall
0x18000a7e7  cmp     [rbx+8], edi
0x18000a7ea  jl      short loc_18000A805
0x18000a7ec  cmp     ebp, 3
0x18000a7ef  jnz     loc_18000A8DD
0x18000a7f5  mov     ecx, 8000FFFFh; this
0x18000a7fa  mov     [rbx+8], ecx
0x18000a7fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a802  mov     [rbx+0Ch], eax
0x18000a805  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a80c  jnz     short loc_18000A835
0x18000a80e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a815  test    rax, rax
0x18000a818  jz      short loc_18000A824
0x18000a81a  call    _guard_dispatch_icall
0x18000a81f  movzx   ecx, al
0x18000a822  jmp     short loc_18000A831
0x18000a824  call    cs:__imp_IsDebuggerPresent
0x18000a82a  mov     ecx, edi
0x18000a82c  test    eax, eax
0x18000a82e  setnz   cl
0x18000a831  test    ecx, ecx
0x18000a833  jz      short loc_18000A83B
0x18000a835  test    byte ptr [rbx+4], 2
0x18000a839  jz      short loc_18000A85F
0x18000a83b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a842  test    rax, rax
0x18000a845  jz      short loc_18000A8A4
0x18000a847  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a84e  jnz     short loc_18000A8A4
0x18000a850  xor     r8d, r8d
0x18000a853  xor     edx, edx
0x18000a855  mov     rcx, rbx
0x18000a858  call    _guard_dispatch_icall
0x18000a85d  jmp     short loc_18000A8A4
0x18000a85f  mov     esi, 800h
0x18000a864  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a86b  test    rax, rax
0x18000a86e  jz      short loc_18000A887
0x18000a870  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a877  jnz     short loc_18000A887
0x18000a879  mov     r8d, esi
0x18000a87c  mov     rdx, r14
0x18000a87f  mov     rcx, rbx
0x18000a882  call    _guard_dispatch_icall
0x18000a887  cmp     [r14], di
0x18000a88b  jnz     short loc_18000A89B
0x18000a88d  mov     r8, rbx; unsigned __int64
0x18000a890  mov     rdx, rsi; wchar_t *
0x18000a893  mov     rcx, r14; this
0x18000a896  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a89b  mov     rcx, r14; lpOutputString
0x18000a89e  call    cs:__imp_OutputDebugStringW
0x18000a8a4  test    byte ptr [rbx+4], 4
0x18000a8a8  jnz     short loc_18000A8B3
0x18000a8aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a8b1  jz      short loc_18000A8C5
0x18000a8b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a8ba  test    rax, rax
0x18000a8bd  jz      short loc_18000A8C5
0x18000a8bf  call    _guard_dispatch_icall
0x18000a8c4  nop
0x18000a8c5  mov     rbx, [rsp+78h+arg_10]
0x18000a8cd  add     rsp, 40h
0x18000a8d1  pop     r15
0x18000a8d3  pop     r14
0x18000a8d5  pop     r13
0x18000a8d7  pop     r12
0x18000a8d9  pop     rdi
0x18000a8da  pop     rsi
0x18000a8db  pop     rbp
0x18000a8dc  retn
0x18000a8dd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
