# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180018d94`
- end: `0x18001908c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180016ea0`

## callees

- `0x1800168dc`
- `0x180018224`
- `0x180018a90`
- `0x180018d94`
- `0x1800199b8`
- `0x1800199e0`
- `0x180019b64`
- `0x180019b80`
- `0x18001b1ec`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018eb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018eb7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019048`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018fd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018fd6`

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
0x180018d94  mov     [rsp+arg_10], rbx
0x180018d99  mov     [rsp+arg_8], edx
0x180018d9d  mov     [rsp+arg_0], rcx
0x180018da2  push    rbp
0x180018da3  push    rsi
0x180018da4  push    rdi
0x180018da5  push    r12
0x180018da7  push    r13
0x180018da9  push    r14
0x180018dab  push    r15
0x180018dad  sub     rsp, 40h
0x180018db1  mov     r14, [rsp+78h+arg_38]
0x180018db9  xor     eax, eax
0x180018dbb  mov     rbx, [rsp+78h+arg_78]
0x180018dc3  xor     ebp, ebp
0x180018dc5  mov     r15d, [rsp+78h+arg_30]
0x180018dcd  mov     r10, rcx
0x180018dd0  mov     rsi, [rsp+78h+lpOutputString]
0x180018dd8  mov     r12, r9
0x180018ddb  mov     r13, r8
0x180018dde  mov     ecx, r15d
0x180018de1  mov     [rsi], ax
0x180018de4  mov     rax, [rsp+78h+arg_60]
0x180018dec  mov     byte ptr [rax], 0
0x180018def  mov     edi, [r14]
0x180018df2  mov     [rbx+8], edi
0x180018df5  mov     eax, [r14+4]
0x180018df9  mov     [rbx+0Ch], eax
0x180018dfc  test    r15d, r15d
0x180018dff  jz      short loc_180018E67
0x180018e01  sub     ecx, 1
0x180018e04  jz      short loc_180018E5E
0x180018e06  sub     ecx, 1
0x180018e09  jz      short loc_180018E19
0x180018e0b  cmp     ecx, 1
0x180018e0e  jnz     short loc_180018E70
0x180018e10  mov     ecx, edi; this
0x180018e12  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180018e17  jmp     short loc_180018E6E
0x180018e19  test    edi, edi
0x180018e1b  js      short loc_180018E55
0x180018e1d  mov     rax, [rsp+78h+arg_28]
0x180018e25  mov     edi, 8007029Ch
0x180018e2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180018e2e  mov     rcx, r10; int
0x180018e31  mov     [rsp+78h+var_50], rax; __int64
0x180018e36  mov     rax, [rsp+78h+arg_20]
0x180018e3e  mov     [rsp+78h+var_58], rax; __int64
0x180018e43  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180018e48  mov     ecx, edi; this
0x180018e4a  mov     [rbx+8], edi
0x180018e4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180018e52  mov     [rbx+0Ch], eax
0x180018e55  mov     ecx, edi; this
0x180018e57  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180018e5c  jmp     short loc_180018E6E
0x180018e5e  mov     ecx, edi; this
0x180018e60  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180018e65  jmp     short loc_180018E6E
0x180018e67  mov     ecx, edi; this
0x180018e69  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180018e6e  mov     ebp, eax
0x180018e70  mov     eax, [rsp+78h+arg_70]
0x180018e77  mov     [rbx+4], eax
0x180018e7a  mov     [rbx], r15d
0x180018e7d  cmp     dword ptr [r14+8], 1
0x180018e82  jnz     short loc_180018E8A
0x180018e84  or      eax, 8
0x180018e87  mov     [rbx+4], eax
0x180018e8a  mov     eax, 1
0x180018e8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180018e97  inc     eax
0x180018e99  xor     edi, edi
0x180018e9b  mov     [rbx+10h], eax
0x180018e9e  mov     rax, [rsp+78h+arg_40]
0x180018ea6  test    rax, rax
0x180018ea9  jz      short loc_180018EB0
0x180018eab  cmp     [rax], di
0x180018eae  jnz     short loc_180018EB3
0x180018eb0  mov     rax, rdi
0x180018eb3  mov     [rbx+18h], rax
0x180018eb7  call    cs:__imp_GetCurrentThreadId
0x180018ebd  mov     [rbx+38h], r13
0x180018ec1  xorps   xmm0, xmm0
0x180018ec4  mov     [rbx+20h], eax
0x180018ec7  mov     eax, [rsp+78h+arg_8]
0x180018ece  mov     [rbx+40h], eax
0x180018ed1  mov     rax, [rsp+78h+arg_20]
0x180018ed9  mov     [rbx+28h], rax
0x180018edd  mov     rax, [rsp+78h+arg_28]
0x180018ee5  mov     [rbx+88h], rax
0x180018eec  mov     rax, [rsp+78h+arg_0]
0x180018ef4  mov     [rbx+90h], rax
0x180018efb  xor     eax, eax
0x180018efd  mov     [rbx+44h], ebp
0x180018f00  mov     [rbx+30h], r12
0x180018f04  mov     [rbx+48h], rdi
0x180018f08  movups  xmmword ptr [rbx+68h], xmm0
0x180018f0c  mov     [rbx+78h], rax
0x180018f10  movups  xmmword ptr [rbx+50h], xmm0
0x180018f14  mov     [rbx+60h], rax
0x180018f18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180018f1f  test    rax, rax
0x180018f22  jz      short loc_180018F2B
0x180018f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f29  jmp     short loc_180018F2E
0x180018f2b  mov     rax, rdi
0x180018f2e  mov     [rbx+80h], rax
0x180018f35  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180018f3c  test    rax, rax
0x180018f3f  jz      short loc_180018F49
0x180018f41  mov     rcx, rbx
0x180018f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180018f50  test    rax, rax
0x180018f53  jz      short loc_180018F6B
0x180018f55  mov     rdx, [rsp+78h+arg_60]
0x180018f5d  mov     r8d, 400h
0x180018f63  mov     rcx, rbx
0x180018f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f6b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018f72  test    rax, rax
0x180018f75  jz      short loc_180018F7F
0x180018f77  mov     rcx, rbx
0x180018f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018f86  test    rax, rax
0x180018f89  jz      short loc_180018F99
0x180018f8b  test    byte ptr [rbx+4], 2
0x180018f8f  jnz     short loc_180018F99
0x180018f91  mov     rcx, rbx
0x180018f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f99  cmp     [rbx+8], edi
0x180018f9c  jl      short loc_180018FB8
0x180018f9e  cmp     r15d, 3
0x180018fa2  jnz     loc_180019086
0x180018fa8  mov     ecx, 8000FFFFh; this
0x180018fad  mov     [rbx+8], ecx
0x180018fb0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180018fb5  mov     [rbx+0Ch], eax
0x180018fb8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180018fbf  jnz     short loc_180018FE0
0x180018fc1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180018fc8  test    rax, rax
0x180018fcb  jz      short loc_180018FD6
0x180018fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fd2  test    al, al
0x180018fd4  jmp     short loc_180018FDE
0x180018fd6  call    cs:__imp_IsDebuggerPresent
0x180018fdc  test    eax, eax
0x180018fde  jz      short loc_180018FE6
0x180018fe0  test    byte ptr [rbx+4], 2
0x180018fe4  jz      short loc_18001900A
0x180018fe6  mov     rax, cs:g_pfnResultLoggingCallback
0x180018fed  test    rax, rax
0x180018ff0  jz      short loc_18001904E
0x180018ff2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180018ff9  jnz     short loc_18001904E
0x180018ffb  xor     r8d, r8d
0x180018ffe  xor     edx, edx
0x180019000  mov     rcx, rbx
0x180019003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019008  jmp     short loc_18001904E
0x18001900a  mov     rax, cs:g_pfnResultLoggingCallback
0x180019011  mov     ebp, 800h
0x180019016  test    rax, rax
0x180019019  jz      short loc_180019032
0x18001901b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180019022  jnz     short loc_180019032
0x180019024  mov     r8d, ebp
0x180019027  mov     rdx, rsi
0x18001902a  mov     rcx, rbx
0x18001902d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019032  cmp     [rsi], di
0x180019035  jnz     short loc_180019045
0x180019037  mov     r8, rbx; unsigned __int64
0x18001903a  mov     rdx, rbp; unsigned __int16 *
0x18001903d  mov     rcx, rsi; this
0x180019040  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180019045  mov     rcx, rsi; lpOutputString
0x180019048  call    cs:__imp_OutputDebugStringW
0x18001904e  test    byte ptr [rbx+4], 4
0x180019052  jnz     short loc_18001905D
0x180019054  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001905b  jz      short loc_18001906E
0x18001905d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180019064  test    rax, rax
0x180019067  jz      short loc_18001906E
0x180019069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001906e  mov     rbx, [rsp+78h+arg_10]
0x180019076  add     rsp, 40h
0x18001907a  pop     r15
0x18001907c  pop     r14
0x18001907e  pop     r13
0x180019080  pop     r12
0x180019082  pop     rdi
0x180019083  pop     rsi
0x180019084  pop     rbp
0x180019085  retn
0x180019086  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
