# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009b98`
- end: `0x180009e9b`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800095a0`

## callees

- `0x180008940`
- `0x180009568`
- `0x180009584`
- `0x18000971c`
- `0x180009780`
- `0x1800097a0`
- `0x1800098dc`
- `0x180009b98`
- `0x18000a184`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009e56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009e56`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009ddc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009ddc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009cbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009cbd`

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
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x180009b98  mov     [rsp+arg_10], rbx
0x180009b9d  mov     [rsp+arg_8], edx
0x180009ba1  mov     [rsp+arg_0], rcx
0x180009ba6  push    rbp
0x180009ba7  push    rsi
0x180009ba8  push    rdi
0x180009ba9  push    r12
0x180009bab  push    r13
0x180009bad  push    r14
0x180009baf  push    r15
0x180009bb1  sub     rsp, 40h
0x180009bb5  mov     r12, r9
0x180009bb8  mov     r13, r8
0x180009bbb  mov     r10, rcx
0x180009bbe  xor     r8d, r8d
0x180009bc1  mov     r14, [rsp+78h+lpOutputString]
0x180009bc9  mov     [r14], r8w
0x180009bcd  mov     rax, [rsp+78h+arg_60]
0x180009bd5  mov     [rax], r8b
0x180009bd8  mov     r15, [rsp+78h+arg_38]
0x180009be0  mov     edi, [r15]
0x180009be3  mov     rbx, [rsp+78h+arg_78]
0x180009beb  mov     [rbx+8], edi
0x180009bee  mov     eax, [r15+4]
0x180009bf2  mov     [rbx+0Ch], eax
0x180009bf5  mov     esi, r8d
0x180009bf8  mov     ebp, [rsp+78h+arg_30]
0x180009bff  mov     ecx, ebp
0x180009c01  test    ebp, ebp
0x180009c03  jz      short loc_180009C6E
0x180009c05  sub     ecx, 1
0x180009c08  jz      short loc_180009C65
0x180009c0a  sub     ecx, 1
0x180009c0d  jz      short loc_180009C1D
0x180009c0f  cmp     ecx, 1
0x180009c12  jnz     short loc_180009C77
0x180009c14  mov     ecx, edi; this
0x180009c16  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009c1b  jmp     short loc_180009C75
0x180009c1d  test    edi, edi
0x180009c1f  js      short loc_180009C5C
0x180009c21  mov     edi, 8007029Ch
0x180009c26  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009c2a  mov     rax, [rsp+78h+arg_28]
0x180009c32  mov     [rsp+78h+var_50], rax; __int64
0x180009c37  mov     rax, [rsp+78h+arg_20]
0x180009c3f  mov     [rsp+78h+var_58], rax; __int64
0x180009c44  mov     r8, r13; int
0x180009c47  mov     rcx, r10; int
0x180009c4a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009c4f  mov     [rbx+8], edi
0x180009c52  mov     ecx, edi; this
0x180009c54  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009c59  mov     [rbx+0Ch], eax
0x180009c5c  mov     ecx, edi; this
0x180009c5e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009c63  jmp     short loc_180009C75
0x180009c65  mov     ecx, edi; this
0x180009c67  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009c6c  jmp     short loc_180009C75
0x180009c6e  mov     ecx, edi; this
0x180009c70  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009c75  mov     esi, eax
0x180009c77  mov     [rbx], ebp
0x180009c79  mov     eax, [rsp+78h+arg_70]
0x180009c80  mov     [rbx+4], eax
0x180009c83  cmp     dword ptr [r15+8], 1
0x180009c88  jnz     short loc_180009C90
0x180009c8a  or      eax, 8
0x180009c8d  mov     [rbx+4], eax
0x180009c90  mov     eax, 1
0x180009c95  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009c9d  inc     eax
0x180009c9f  mov     [rbx+10h], eax
0x180009ca2  mov     rax, [rsp+78h+arg_40]
0x180009caa  xor     edi, edi
0x180009cac  test    rax, rax
0x180009caf  jz      short loc_180009CB6
0x180009cb1  cmp     [rax], di
0x180009cb4  jnz     short loc_180009CB9
0x180009cb6  mov     rax, rdi
0x180009cb9  mov     [rbx+18h], rax
0x180009cbd  call    cs:__imp_GetCurrentThreadId
0x180009cc3  mov     [rbx+20h], eax
0x180009cc6  mov     [rbx+38h], r13
0x180009cca  mov     eax, [rsp+78h+arg_8]
0x180009cd1  mov     [rbx+40h], eax
0x180009cd4  mov     [rbx+44h], esi
0x180009cd7  mov     rax, [rsp+78h+arg_20]
0x180009cdf  mov     [rbx+28h], rax
0x180009ce3  mov     [rbx+30h], r12
0x180009ce7  mov     rax, [rsp+78h+arg_28]
0x180009cef  mov     [rbx+88h], rax
0x180009cf6  mov     rax, [rsp+78h+arg_0]
0x180009cfe  mov     [rbx+90h], rax
0x180009d05  mov     [rbx+48h], rdi
0x180009d09  xorps   xmm0, xmm0
0x180009d0c  xor     eax, eax
0x180009d0e  movups  xmmword ptr [rbx+68h], xmm0
0x180009d12  mov     [rbx+78h], rax
0x180009d16  movups  xmmword ptr [rbx+50h], xmm0
0x180009d1a  mov     [rbx+60h], rax
0x180009d1e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009d25  test    rax, rax
0x180009d28  jz      short loc_180009D31
0x180009d2a  call    _guard_dispatch_icall
0x180009d2f  jmp     short loc_180009D34
0x180009d31  mov     rax, rdi
0x180009d34  mov     [rbx+80h], rax
0x180009d3b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009d42  test    rax, rax
0x180009d45  jz      short loc_180009D4F
0x180009d47  mov     rcx, rbx
0x180009d4a  call    _guard_dispatch_icall
0x180009d4f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009d56  test    rax, rax
0x180009d59  jz      short loc_180009D71
0x180009d5b  mov     r8d, 400h
0x180009d61  mov     rdx, [rsp+78h+arg_60]
0x180009d69  mov     rcx, rbx
0x180009d6c  call    _guard_dispatch_icall
0x180009d71  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009d78  test    rax, rax
0x180009d7b  jz      short loc_180009D85
0x180009d7d  mov     rcx, rbx
0x180009d80  call    _guard_dispatch_icall
0x180009d85  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009d8c  test    rax, rax
0x180009d8f  jz      short loc_180009D9F
0x180009d91  test    byte ptr [rbx+4], 2
0x180009d95  jnz     short loc_180009D9F
0x180009d97  mov     rcx, rbx
0x180009d9a  call    _guard_dispatch_icall
0x180009d9f  cmp     [rbx+8], edi
0x180009da2  jl      short loc_180009DBD
0x180009da4  cmp     ebp, 3
0x180009da7  jnz     loc_180009E95
0x180009dad  mov     ecx, 8000FFFFh; this
0x180009db2  mov     [rbx+8], ecx
0x180009db5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009dba  mov     [rbx+0Ch], eax
0x180009dbd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009dc4  jnz     short loc_180009DED
0x180009dc6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009dcd  test    rax, rax
0x180009dd0  jz      short loc_180009DDC
0x180009dd2  call    _guard_dispatch_icall
0x180009dd7  movzx   ecx, al
0x180009dda  jmp     short loc_180009DE9
0x180009ddc  call    cs:__imp_IsDebuggerPresent
0x180009de2  mov     ecx, edi
0x180009de4  test    eax, eax
0x180009de6  setnz   cl
0x180009de9  test    ecx, ecx
0x180009deb  jz      short loc_180009DF3
0x180009ded  test    byte ptr [rbx+4], 2
0x180009df1  jz      short loc_180009E17
0x180009df3  mov     rax, cs:g_pfnResultLoggingCallback
0x180009dfa  test    rax, rax
0x180009dfd  jz      short loc_180009E5C
0x180009dff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009e06  jnz     short loc_180009E5C
0x180009e08  xor     r8d, r8d
0x180009e0b  xor     edx, edx
0x180009e0d  mov     rcx, rbx
0x180009e10  call    _guard_dispatch_icall
0x180009e15  jmp     short loc_180009E5C
0x180009e17  mov     esi, 800h
0x180009e1c  mov     rax, cs:g_pfnResultLoggingCallback
0x180009e23  test    rax, rax
0x180009e26  jz      short loc_180009E3F
0x180009e28  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009e2f  jnz     short loc_180009E3F
0x180009e31  mov     r8d, esi
0x180009e34  mov     rdx, r14
0x180009e37  mov     rcx, rbx
0x180009e3a  call    _guard_dispatch_icall
0x180009e3f  cmp     [r14], di
0x180009e43  jnz     short loc_180009E53
0x180009e45  mov     r8, rbx; unsigned __int64
0x180009e48  mov     rdx, rsi; wchar_t *
0x180009e4b  mov     rcx, r14; this
0x180009e4e  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180009e53  mov     rcx, r14; lpOutputString
0x180009e56  call    cs:__imp_OutputDebugStringW
0x180009e5c  test    byte ptr [rbx+4], 4
0x180009e60  jnz     short loc_180009E6B
0x180009e62  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009e69  jz      short loc_180009E7D
0x180009e6b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009e72  test    rax, rax
0x180009e75  jz      short loc_180009E7D
0x180009e77  call    _guard_dispatch_icall
0x180009e7c  nop
0x180009e7d  mov     rbx, [rsp+78h+arg_10]
0x180009e85  add     rsp, 40h
0x180009e89  pop     r15
0x180009e8b  pop     r14
0x180009e8d  pop     r13
0x180009e8f  pop     r12
0x180009e91  pop     rdi
0x180009e92  pop     rsi
0x180009e93  pop     rbp
0x180009e94  retn
0x180009e95  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
