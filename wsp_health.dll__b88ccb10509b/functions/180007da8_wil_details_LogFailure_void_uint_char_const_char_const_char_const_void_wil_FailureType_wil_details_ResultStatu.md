# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007da8`
- end: `0x1800080a1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005ba0`

## callees

- `0x1800055dc`
- `0x180007224`
- `0x180007aa4`
- `0x180007da8`
- `0x1800089ec`
- `0x180008a10`
- `0x180008b94`
- `0x180008bb0`
- `0x18000a4a8`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ecb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007fea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000805c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000805c`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180007da8  mov     [rsp+arg_10], rbx
0x180007dad  mov     [rsp+arg_8], edx
0x180007db1  mov     [rsp+arg_0], rcx
0x180007db6  push    rbp
0x180007db7  push    rsi
0x180007db8  push    rdi
0x180007db9  push    r12
0x180007dbb  push    r13
0x180007dbd  push    r14
0x180007dbf  push    r15
0x180007dc1  sub     rsp, 40h
0x180007dc5  mov     r12, r9
0x180007dc8  mov     r13, r8
0x180007dcb  mov     r10, rcx
0x180007dce  xor     eax, eax
0x180007dd0  mov     rsi, [rsp+78h+lpOutputString]
0x180007dd8  mov     [rsi], ax
0x180007ddb  mov     rax, [rsp+78h+arg_60]
0x180007de3  mov     byte ptr [rax], 0
0x180007de6  mov     r14, [rsp+78h+arg_38]
0x180007dee  mov     edi, [r14]
0x180007df1  mov     rbx, [rsp+78h+arg_78]
0x180007df9  mov     [rbx+8], edi
0x180007dfc  mov     eax, [r14+4]
0x180007e00  mov     [rbx+0Ch], eax
0x180007e03  xor     ebp, ebp
0x180007e05  mov     r15d, [rsp+78h+arg_30]
0x180007e0d  mov     ecx, r15d
0x180007e10  test    r15d, r15d
0x180007e13  jz      short loc_180007E7B
0x180007e15  sub     ecx, 1
0x180007e18  jz      short loc_180007E72
0x180007e1a  sub     ecx, 1
0x180007e1d  jz      short loc_180007E2D
0x180007e1f  cmp     ecx, 1
0x180007e22  jnz     short loc_180007E84
0x180007e24  mov     ecx, edi; this
0x180007e26  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007e2b  jmp     short loc_180007E82
0x180007e2d  test    edi, edi
0x180007e2f  js      short loc_180007E69
0x180007e31  mov     edi, 8007029Ch
0x180007e36  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007e3a  mov     rax, [rsp+78h+arg_28]
0x180007e42  mov     [rsp+78h+var_50], rax; __int64
0x180007e47  mov     rax, [rsp+78h+arg_20]
0x180007e4f  mov     [rsp+78h+var_58], rax; __int64
0x180007e54  mov     rcx, r10; int
0x180007e57  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007e5c  mov     [rbx+8], edi
0x180007e5f  mov     ecx, edi; this
0x180007e61  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007e66  mov     [rbx+0Ch], eax
0x180007e69  mov     ecx, edi; this
0x180007e6b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007e70  jmp     short loc_180007E82
0x180007e72  mov     ecx, edi; this
0x180007e74  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007e79  jmp     short loc_180007E82
0x180007e7b  mov     ecx, edi; this
0x180007e7d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007e82  mov     ebp, eax
0x180007e84  mov     [rbx], r15d
0x180007e87  mov     eax, [rsp+78h+arg_70]
0x180007e8e  mov     [rbx+4], eax
0x180007e91  cmp     dword ptr [r14+8], 1
0x180007e96  jnz     short loc_180007E9E
0x180007e98  or      eax, 8
0x180007e9b  mov     [rbx+4], eax
0x180007e9e  mov     eax, 1
0x180007ea3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007eab  inc     eax
0x180007ead  mov     [rbx+10h], eax
0x180007eb0  mov     rax, [rsp+78h+arg_40]
0x180007eb8  xor     edi, edi
0x180007eba  test    rax, rax
0x180007ebd  jz      short loc_180007EC4
0x180007ebf  cmp     [rax], di
0x180007ec2  jnz     short loc_180007EC7
0x180007ec4  mov     rax, rdi
0x180007ec7  mov     [rbx+18h], rax
0x180007ecb  call    cs:__imp_GetCurrentThreadId
0x180007ed1  mov     [rbx+20h], eax
0x180007ed4  mov     [rbx+38h], r13
0x180007ed8  mov     eax, [rsp+78h+arg_8]
0x180007edf  mov     [rbx+40h], eax
0x180007ee2  mov     [rbx+44h], ebp
0x180007ee5  mov     rax, [rsp+78h+arg_20]
0x180007eed  mov     [rbx+28h], rax
0x180007ef1  mov     [rbx+30h], r12
0x180007ef5  mov     rax, [rsp+78h+arg_28]
0x180007efd  mov     [rbx+88h], rax
0x180007f04  mov     rax, [rsp+78h+arg_0]
0x180007f0c  mov     [rbx+90h], rax
0x180007f13  mov     [rbx+48h], rdi
0x180007f17  xorps   xmm0, xmm0
0x180007f1a  xor     eax, eax
0x180007f1c  movups  xmmword ptr [rbx+68h], xmm0
0x180007f20  mov     [rbx+78h], rax
0x180007f24  movups  xmmword ptr [rbx+50h], xmm0
0x180007f28  mov     [rbx+60h], rax
0x180007f2c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007f33  test    rax, rax
0x180007f36  jz      short loc_180007F3F
0x180007f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f3d  jmp     short loc_180007F42
0x180007f3f  mov     rax, rdi
0x180007f42  mov     [rbx+80h], rax
0x180007f49  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007f50  test    rax, rax
0x180007f53  jz      short loc_180007F5D
0x180007f55  mov     rcx, rbx
0x180007f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f5d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007f64  test    rax, rax
0x180007f67  jz      short loc_180007F7F
0x180007f69  mov     r8d, 400h
0x180007f6f  mov     rdx, [rsp+78h+arg_60]
0x180007f77  mov     rcx, rbx
0x180007f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f7f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f86  test    rax, rax
0x180007f89  jz      short loc_180007F93
0x180007f8b  mov     rcx, rbx
0x180007f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f93  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007f9a  test    rax, rax
0x180007f9d  jz      short loc_180007FAD
0x180007f9f  test    byte ptr [rbx+4], 2
0x180007fa3  jnz     short loc_180007FAD
0x180007fa5  mov     rcx, rbx
0x180007fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fad  cmp     [rbx+8], edi
0x180007fb0  jl      short loc_180007FCC
0x180007fb2  cmp     r15d, 3
0x180007fb6  jnz     loc_18000809B
0x180007fbc  mov     ecx, 8000FFFFh; this
0x180007fc1  mov     [rbx+8], ecx
0x180007fc4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007fc9  mov     [rbx+0Ch], eax
0x180007fcc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007fd3  jnz     short loc_180007FF4
0x180007fd5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007fdc  test    rax, rax
0x180007fdf  jz      short loc_180007FEA
0x180007fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe6  test    al, al
0x180007fe8  jmp     short loc_180007FF2
0x180007fea  call    cs:__imp_IsDebuggerPresent
0x180007ff0  test    eax, eax
0x180007ff2  jz      short loc_180007FFA
0x180007ff4  test    byte ptr [rbx+4], 2
0x180007ff8  jz      short loc_18000801E
0x180007ffa  mov     rax, cs:g_pfnResultLoggingCallback
0x180008001  test    rax, rax
0x180008004  jz      short loc_180008062
0x180008006  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000800d  jnz     short loc_180008062
0x18000800f  xor     r8d, r8d
0x180008012  xor     edx, edx
0x180008014  mov     rcx, rbx
0x180008017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000801c  jmp     short loc_180008062
0x18000801e  mov     ebp, 800h
0x180008023  mov     rax, cs:g_pfnResultLoggingCallback
0x18000802a  test    rax, rax
0x18000802d  jz      short loc_180008046
0x18000802f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008036  jnz     short loc_180008046
0x180008038  mov     r8d, ebp
0x18000803b  mov     rdx, rsi
0x18000803e  mov     rcx, rbx
0x180008041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008046  cmp     [rsi], di
0x180008049  jnz     short loc_180008059
0x18000804b  mov     r8, rbx; unsigned __int64
0x18000804e  mov     rdx, rbp; wchar_t *
0x180008051  mov     rcx, rsi; pszDest
0x180008054  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008059  mov     rcx, rsi; lpOutputString
0x18000805c  call    cs:__imp_OutputDebugStringW
0x180008062  test    byte ptr [rbx+4], 4
0x180008066  jnz     short loc_180008071
0x180008068  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000806f  jz      short loc_180008083
0x180008071  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008078  test    rax, rax
0x18000807b  jz      short loc_180008083
0x18000807d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008082  nop
0x180008083  mov     rbx, [rsp+78h+arg_10]
0x18000808b  add     rsp, 40h
0x18000808f  pop     r15
0x180008091  pop     r14
0x180008093  pop     r13
0x180008095  pop     r12
0x180008097  pop     rdi
0x180008098  pop     rsi
0x180008099  pop     rbp
0x18000809a  retn
0x18000809b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
