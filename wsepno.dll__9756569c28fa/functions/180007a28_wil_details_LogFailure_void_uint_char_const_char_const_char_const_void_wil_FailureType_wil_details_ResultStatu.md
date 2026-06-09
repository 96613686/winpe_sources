# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007a28`
- end: `0x180007d21`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800048e4`

## callees

- `0x180002704`
- `0x180002aec`
- `0x180002e90`
- `0x1800042f0`
- `0x180007a28`
- `0x1800091d8`
- `0x18000930c`
- `0x180009328`
- `0x18000b494`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007cdc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007cdc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007c6a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007c6a`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180007a28  mov     [rsp+arg_10], rbx
0x180007a2d  mov     [rsp+arg_8], edx
0x180007a31  mov     [rsp+arg_0], rcx
0x180007a36  push    rbp
0x180007a37  push    rsi
0x180007a38  push    rdi
0x180007a39  push    r12
0x180007a3b  push    r13
0x180007a3d  push    r14
0x180007a3f  push    r15
0x180007a41  sub     rsp, 40h
0x180007a45  mov     r12, r9
0x180007a48  mov     r13, r8
0x180007a4b  mov     r10, rcx
0x180007a4e  xor     eax, eax
0x180007a50  mov     rsi, [rsp+78h+lpOutputString]
0x180007a58  mov     [rsi], ax
0x180007a5b  mov     rax, [rsp+78h+arg_60]
0x180007a63  mov     byte ptr [rax], 0
0x180007a66  mov     r14, [rsp+78h+arg_38]
0x180007a6e  mov     edi, [r14]
0x180007a71  mov     rbx, [rsp+78h+arg_78]
0x180007a79  mov     [rbx+8], edi
0x180007a7c  mov     eax, [r14+4]
0x180007a80  mov     [rbx+0Ch], eax
0x180007a83  xor     ebp, ebp
0x180007a85  mov     r15d, [rsp+78h+arg_30]
0x180007a8d  mov     ecx, r15d
0x180007a90  test    r15d, r15d
0x180007a93  jz      short loc_180007AFB
0x180007a95  sub     ecx, 1
0x180007a98  jz      short loc_180007AF2
0x180007a9a  sub     ecx, 1
0x180007a9d  jz      short loc_180007AAD
0x180007a9f  cmp     ecx, 1
0x180007aa2  jnz     short loc_180007B04
0x180007aa4  mov     ecx, edi; this
0x180007aa6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007aab  jmp     short loc_180007B02
0x180007aad  test    edi, edi
0x180007aaf  js      short loc_180007AE9
0x180007ab1  mov     edi, 8007029Ch
0x180007ab6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007aba  mov     rax, [rsp+78h+arg_28]
0x180007ac2  mov     [rsp+78h+var_50], rax; __int64
0x180007ac7  mov     rax, [rsp+78h+arg_20]
0x180007acf  mov     [rsp+78h+var_58], rax; __int64
0x180007ad4  mov     rcx, r10; int
0x180007ad7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007adc  mov     [rbx+8], edi
0x180007adf  mov     ecx, edi; this
0x180007ae1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007ae6  mov     [rbx+0Ch], eax
0x180007ae9  mov     ecx, edi; this
0x180007aeb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007af0  jmp     short loc_180007B02
0x180007af2  mov     ecx, edi; this
0x180007af4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007af9  jmp     short loc_180007B02
0x180007afb  mov     ecx, edi; this
0x180007afd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007b02  mov     ebp, eax
0x180007b04  mov     [rbx], r15d
0x180007b07  mov     eax, [rsp+78h+arg_70]
0x180007b0e  mov     [rbx+4], eax
0x180007b11  cmp     dword ptr [r14+8], 1
0x180007b16  jnz     short loc_180007B1E
0x180007b18  or      eax, 8
0x180007b1b  mov     [rbx+4], eax
0x180007b1e  mov     eax, 1
0x180007b23  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007b2b  inc     eax
0x180007b2d  mov     [rbx+10h], eax
0x180007b30  mov     rax, [rsp+78h+arg_40]
0x180007b38  xor     edi, edi
0x180007b3a  test    rax, rax
0x180007b3d  jz      short loc_180007B44
0x180007b3f  cmp     [rax], di
0x180007b42  jnz     short loc_180007B47
0x180007b44  mov     rax, rdi
0x180007b47  mov     [rbx+18h], rax
0x180007b4b  call    cs:__imp_GetCurrentThreadId
0x180007b51  mov     [rbx+20h], eax
0x180007b54  mov     [rbx+38h], r13
0x180007b58  mov     eax, [rsp+78h+arg_8]
0x180007b5f  mov     [rbx+40h], eax
0x180007b62  mov     [rbx+44h], ebp
0x180007b65  mov     rax, [rsp+78h+arg_20]
0x180007b6d  mov     [rbx+28h], rax
0x180007b71  mov     [rbx+30h], r12
0x180007b75  mov     rax, [rsp+78h+arg_28]
0x180007b7d  mov     [rbx+88h], rax
0x180007b84  mov     rax, [rsp+78h+arg_0]
0x180007b8c  mov     [rbx+90h], rax
0x180007b93  mov     [rbx+48h], rdi
0x180007b97  xorps   xmm0, xmm0
0x180007b9a  xor     eax, eax
0x180007b9c  movups  xmmword ptr [rbx+68h], xmm0
0x180007ba0  mov     [rbx+78h], rax
0x180007ba4  movups  xmmword ptr [rbx+50h], xmm0
0x180007ba8  mov     [rbx+60h], rax
0x180007bac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007bb3  test    rax, rax
0x180007bb6  jz      short loc_180007BBF
0x180007bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bbd  jmp     short loc_180007BC2
0x180007bbf  mov     rax, rdi
0x180007bc2  mov     [rbx+80h], rax
0x180007bc9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007bd0  test    rax, rax
0x180007bd3  jz      short loc_180007BDD
0x180007bd5  mov     rcx, rbx
0x180007bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bdd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007be4  test    rax, rax
0x180007be7  jz      short loc_180007BFF
0x180007be9  mov     r8d, 400h
0x180007bef  mov     rdx, [rsp+78h+arg_60]
0x180007bf7  mov     rcx, rbx
0x180007bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c06  test    rax, rax
0x180007c09  jz      short loc_180007C13
0x180007c0b  mov     rcx, rbx
0x180007c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c13  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c1a  test    rax, rax
0x180007c1d  jz      short loc_180007C2D
0x180007c1f  test    byte ptr [rbx+4], 2
0x180007c23  jnz     short loc_180007C2D
0x180007c25  mov     rcx, rbx
0x180007c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c2d  cmp     [rbx+8], edi
0x180007c30  jl      short loc_180007C4C
0x180007c32  cmp     r15d, 3
0x180007c36  jnz     loc_180007D1B
0x180007c3c  mov     ecx, 8000FFFFh; this
0x180007c41  mov     [rbx+8], ecx
0x180007c44  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007c49  mov     [rbx+0Ch], eax
0x180007c4c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007c53  jnz     short loc_180007C74
0x180007c55  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007c5c  test    rax, rax
0x180007c5f  jz      short loc_180007C6A
0x180007c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c66  test    al, al
0x180007c68  jmp     short loc_180007C72
0x180007c6a  call    cs:__imp_IsDebuggerPresent
0x180007c70  test    eax, eax
0x180007c72  jz      short loc_180007C7A
0x180007c74  test    byte ptr [rbx+4], 2
0x180007c78  jz      short loc_180007C9E
0x180007c7a  mov     rax, cs:g_pfnResultLoggingCallback
0x180007c81  test    rax, rax
0x180007c84  jz      short loc_180007CE2
0x180007c86  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007c8d  jnz     short loc_180007CE2
0x180007c8f  xor     r8d, r8d
0x180007c92  xor     edx, edx
0x180007c94  mov     rcx, rbx
0x180007c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9c  jmp     short loc_180007CE2
0x180007c9e  mov     ebp, 800h
0x180007ca3  mov     rax, cs:g_pfnResultLoggingCallback
0x180007caa  test    rax, rax
0x180007cad  jz      short loc_180007CC6
0x180007caf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007cb6  jnz     short loc_180007CC6
0x180007cb8  mov     r8d, ebp
0x180007cbb  mov     rdx, rsi
0x180007cbe  mov     rcx, rbx
0x180007cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc6  cmp     [rsi], di
0x180007cc9  jnz     short loc_180007CD9
0x180007ccb  mov     r8, rbx; unsigned __int64
0x180007cce  mov     rdx, rbp; wchar_t *
0x180007cd1  mov     rcx, rsi; this
0x180007cd4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007cd9  mov     rcx, rsi; lpOutputString
0x180007cdc  call    cs:__imp_OutputDebugStringW
0x180007ce2  test    byte ptr [rbx+4], 4
0x180007ce6  jnz     short loc_180007CF1
0x180007ce8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007cef  jz      short loc_180007D03
0x180007cf1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007cf8  test    rax, rax
0x180007cfb  jz      short loc_180007D03
0x180007cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d02  nop
0x180007d03  mov     rbx, [rsp+78h+arg_10]
0x180007d0b  add     rsp, 40h
0x180007d0f  pop     r15
0x180007d11  pop     r14
0x180007d13  pop     r13
0x180007d15  pop     r12
0x180007d17  pop     rdi
0x180007d18  pop     rsi
0x180007d19  pop     rbp
0x180007d1a  retn
0x180007d1b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
