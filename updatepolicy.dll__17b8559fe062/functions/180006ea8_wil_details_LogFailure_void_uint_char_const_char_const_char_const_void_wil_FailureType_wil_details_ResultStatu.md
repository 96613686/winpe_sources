# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006ea8`
- end: `0x1800071ab`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800068b4`

## callees

- `0x180005734`
- `0x18000687c`
- `0x180006898`
- `0x180006a30`
- `0x180006a94`
- `0x180006ab0`
- `0x180006bec`
- `0x180006ea8`
- `0x180007570`
- `0x180015430`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800070ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800070ec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007166`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007166`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fcd`

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
0x180006ea8  mov     [rsp+arg_10], rbx
0x180006ead  mov     [rsp+arg_8], edx
0x180006eb1  mov     [rsp+arg_0], rcx
0x180006eb6  push    rbp
0x180006eb7  push    rsi
0x180006eb8  push    rdi
0x180006eb9  push    r12
0x180006ebb  push    r13
0x180006ebd  push    r14
0x180006ebf  push    r15
0x180006ec1  sub     rsp, 40h
0x180006ec5  mov     r12, r9
0x180006ec8  mov     r13, r8
0x180006ecb  mov     r10, rcx
0x180006ece  xor     r8d, r8d
0x180006ed1  mov     r14, [rsp+78h+lpOutputString]
0x180006ed9  mov     [r14], r8w
0x180006edd  mov     rax, [rsp+78h+arg_60]
0x180006ee5  mov     [rax], r8b
0x180006ee8  mov     r15, [rsp+78h+arg_38]
0x180006ef0  mov     edi, [r15]
0x180006ef3  mov     rbx, [rsp+78h+arg_78]
0x180006efb  mov     [rbx+8], edi
0x180006efe  mov     eax, [r15+4]
0x180006f02  mov     [rbx+0Ch], eax
0x180006f05  mov     esi, r8d
0x180006f08  mov     ebp, [rsp+78h+arg_30]
0x180006f0f  mov     ecx, ebp
0x180006f11  test    ebp, ebp
0x180006f13  jz      short loc_180006F7E
0x180006f15  sub     ecx, 1
0x180006f18  jz      short loc_180006F75
0x180006f1a  sub     ecx, 1
0x180006f1d  jz      short loc_180006F2D
0x180006f1f  cmp     ecx, 1
0x180006f22  jnz     short loc_180006F87
0x180006f24  mov     ecx, edi; this
0x180006f26  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006f2b  jmp     short loc_180006F85
0x180006f2d  test    edi, edi
0x180006f2f  js      short loc_180006F6C
0x180006f31  mov     edi, 8007029Ch
0x180006f36  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006f3a  mov     rax, [rsp+78h+arg_28]
0x180006f42  mov     [rsp+78h+var_50], rax; __int64
0x180006f47  mov     rax, [rsp+78h+arg_20]
0x180006f4f  mov     [rsp+78h+var_58], rax; __int64
0x180006f54  mov     r8, r13; int
0x180006f57  mov     rcx, r10; int
0x180006f5a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006f5f  mov     [rbx+8], edi
0x180006f62  mov     ecx, edi; this
0x180006f64  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006f69  mov     [rbx+0Ch], eax
0x180006f6c  mov     ecx, edi; this
0x180006f6e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006f73  jmp     short loc_180006F85
0x180006f75  mov     ecx, edi; this
0x180006f77  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006f7c  jmp     short loc_180006F85
0x180006f7e  mov     ecx, edi; this
0x180006f80  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006f85  mov     esi, eax
0x180006f87  mov     [rbx], ebp
0x180006f89  mov     eax, [rsp+78h+arg_70]
0x180006f90  mov     [rbx+4], eax
0x180006f93  cmp     dword ptr [r15+8], 1
0x180006f98  jnz     short loc_180006FA0
0x180006f9a  or      eax, 8
0x180006f9d  mov     [rbx+4], eax
0x180006fa0  mov     eax, 1
0x180006fa5  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006fad  inc     eax
0x180006faf  mov     [rbx+10h], eax
0x180006fb2  mov     rax, [rsp+78h+arg_40]
0x180006fba  xor     edi, edi
0x180006fbc  test    rax, rax
0x180006fbf  jz      short loc_180006FC6
0x180006fc1  cmp     [rax], di
0x180006fc4  jnz     short loc_180006FC9
0x180006fc6  mov     rax, rdi
0x180006fc9  mov     [rbx+18h], rax
0x180006fcd  call    cs:__imp_GetCurrentThreadId
0x180006fd3  mov     [rbx+20h], eax
0x180006fd6  mov     [rbx+38h], r13
0x180006fda  mov     eax, [rsp+78h+arg_8]
0x180006fe1  mov     [rbx+40h], eax
0x180006fe4  mov     [rbx+44h], esi
0x180006fe7  mov     rax, [rsp+78h+arg_20]
0x180006fef  mov     [rbx+28h], rax
0x180006ff3  mov     [rbx+30h], r12
0x180006ff7  mov     rax, [rsp+78h+arg_28]
0x180006fff  mov     [rbx+88h], rax
0x180007006  mov     rax, [rsp+78h+arg_0]
0x18000700e  mov     [rbx+90h], rax
0x180007015  mov     [rbx+48h], rdi
0x180007019  xorps   xmm0, xmm0
0x18000701c  xor     eax, eax
0x18000701e  movups  xmmword ptr [rbx+68h], xmm0
0x180007022  mov     [rbx+78h], rax
0x180007026  movups  xmmword ptr [rbx+50h], xmm0
0x18000702a  mov     [rbx+60h], rax
0x18000702e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007035  test    rax, rax
0x180007038  jz      short loc_180007041
0x18000703a  call    _guard_dispatch_icall
0x18000703f  jmp     short loc_180007044
0x180007041  mov     rax, rdi
0x180007044  mov     [rbx+80h], rax
0x18000704b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007052  test    rax, rax
0x180007055  jz      short loc_18000705F
0x180007057  mov     rcx, rbx
0x18000705a  call    _guard_dispatch_icall
0x18000705f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007066  test    rax, rax
0x180007069  jz      short loc_180007081
0x18000706b  mov     r8d, 400h
0x180007071  mov     rdx, [rsp+78h+arg_60]
0x180007079  mov     rcx, rbx
0x18000707c  call    _guard_dispatch_icall
0x180007081  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007088  test    rax, rax
0x18000708b  jz      short loc_180007095
0x18000708d  mov     rcx, rbx
0x180007090  call    _guard_dispatch_icall
0x180007095  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000709c  test    rax, rax
0x18000709f  jz      short loc_1800070AF
0x1800070a1  test    byte ptr [rbx+4], 2
0x1800070a5  jnz     short loc_1800070AF
0x1800070a7  mov     rcx, rbx
0x1800070aa  call    _guard_dispatch_icall
0x1800070af  cmp     [rbx+8], edi
0x1800070b2  jl      short loc_1800070CD
0x1800070b4  cmp     ebp, 3
0x1800070b7  jnz     loc_1800071A5
0x1800070bd  mov     ecx, 8000FFFFh; this
0x1800070c2  mov     [rbx+8], ecx
0x1800070c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800070ca  mov     [rbx+0Ch], eax
0x1800070cd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800070d4  jnz     short loc_1800070FD
0x1800070d6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800070dd  test    rax, rax
0x1800070e0  jz      short loc_1800070EC
0x1800070e2  call    _guard_dispatch_icall
0x1800070e7  movzx   ecx, al
0x1800070ea  jmp     short loc_1800070F9
0x1800070ec  call    cs:__imp_IsDebuggerPresent
0x1800070f2  mov     ecx, edi
0x1800070f4  test    eax, eax
0x1800070f6  setnz   cl
0x1800070f9  test    ecx, ecx
0x1800070fb  jz      short loc_180007103
0x1800070fd  test    byte ptr [rbx+4], 2
0x180007101  jz      short loc_180007127
0x180007103  mov     rax, cs:g_pfnResultLoggingCallback
0x18000710a  test    rax, rax
0x18000710d  jz      short loc_18000716C
0x18000710f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007116  jnz     short loc_18000716C
0x180007118  xor     r8d, r8d
0x18000711b  xor     edx, edx
0x18000711d  mov     rcx, rbx
0x180007120  call    _guard_dispatch_icall
0x180007125  jmp     short loc_18000716C
0x180007127  mov     esi, 800h
0x18000712c  mov     rax, cs:g_pfnResultLoggingCallback
0x180007133  test    rax, rax
0x180007136  jz      short loc_18000714F
0x180007138  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000713f  jnz     short loc_18000714F
0x180007141  mov     r8d, esi
0x180007144  mov     rdx, r14
0x180007147  mov     rcx, rbx
0x18000714a  call    _guard_dispatch_icall
0x18000714f  cmp     [r14], di
0x180007153  jnz     short loc_180007163
0x180007155  mov     r8, rbx; unsigned __int64
0x180007158  mov     rdx, rsi; wchar_t *
0x18000715b  mov     rcx, r14; this
0x18000715e  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180007163  mov     rcx, r14; lpOutputString
0x180007166  call    cs:__imp_OutputDebugStringW
0x18000716c  test    byte ptr [rbx+4], 4
0x180007170  jnz     short loc_18000717B
0x180007172  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007179  jz      short loc_18000718D
0x18000717b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007182  test    rax, rax
0x180007185  jz      short loc_18000718D
0x180007187  call    _guard_dispatch_icall
0x18000718c  nop
0x18000718d  mov     rbx, [rsp+78h+arg_10]
0x180007195  add     rsp, 40h
0x180007199  pop     r15
0x18000719b  pop     r14
0x18000719d  pop     r13
0x18000719f  pop     r12
0x1800071a1  pop     rdi
0x1800071a2  pop     rsi
0x1800071a3  pop     rbp
0x1800071a4  retn
0x1800071a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
