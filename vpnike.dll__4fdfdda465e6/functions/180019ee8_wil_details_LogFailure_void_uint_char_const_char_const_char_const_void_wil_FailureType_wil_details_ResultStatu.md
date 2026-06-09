# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180019ee8`
- end: `0x18001a1e1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180015670`

## callees

- `0x1800150ac`
- `0x1800185f4`
- `0x180019050`
- `0x180019ee8`
- `0x18001d3ec`
- `0x18001d410`
- `0x18001d594`
- `0x18001d5b0`
- `0x18002028c`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a00b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a00b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a12a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001a12a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a19c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001a19c`

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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
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
0x180019ee8  mov     [rsp+arg_10], rbx
0x180019eed  mov     [rsp+arg_8], edx
0x180019ef1  mov     [rsp+arg_0], rcx
0x180019ef6  push    rbp
0x180019ef7  push    rsi
0x180019ef8  push    rdi
0x180019ef9  push    r12
0x180019efb  push    r13
0x180019efd  push    r14
0x180019eff  push    r15
0x180019f01  sub     rsp, 40h
0x180019f05  mov     r12, r9
0x180019f08  mov     r13, r8
0x180019f0b  mov     r10, rcx
0x180019f0e  xor     eax, eax
0x180019f10  mov     rsi, [rsp+78h+lpOutputString]
0x180019f18  mov     [rsi], ax
0x180019f1b  mov     rax, [rsp+78h+arg_60]
0x180019f23  mov     byte ptr [rax], 0
0x180019f26  mov     r14, [rsp+78h+arg_38]
0x180019f2e  mov     edi, [r14]
0x180019f31  mov     rbx, [rsp+78h+arg_78]
0x180019f39  mov     [rbx+8], edi
0x180019f3c  mov     eax, [r14+4]
0x180019f40  mov     [rbx+0Ch], eax
0x180019f43  xor     ebp, ebp
0x180019f45  mov     r15d, [rsp+78h+arg_30]
0x180019f4d  mov     ecx, r15d
0x180019f50  test    r15d, r15d
0x180019f53  jz      short loc_180019FBB
0x180019f55  sub     ecx, 1
0x180019f58  jz      short loc_180019FB2
0x180019f5a  sub     ecx, 1
0x180019f5d  jz      short loc_180019F6D
0x180019f5f  cmp     ecx, 1
0x180019f62  jnz     short loc_180019FC4
0x180019f64  mov     ecx, edi; this
0x180019f66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180019f6b  jmp     short loc_180019FC2
0x180019f6d  test    edi, edi
0x180019f6f  js      short loc_180019FA9
0x180019f71  mov     edi, 8007029Ch
0x180019f76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180019f7a  mov     rax, [rsp+78h+arg_28]
0x180019f82  mov     [rsp+78h+var_50], rax; __int64
0x180019f87  mov     rax, [rsp+78h+arg_20]
0x180019f8f  mov     [rsp+78h+var_58], rax; __int64
0x180019f94  mov     rcx, r10; int
0x180019f97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180019f9c  mov     [rbx+8], edi
0x180019f9f  mov     ecx, edi; this
0x180019fa1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180019fa6  mov     [rbx+0Ch], eax
0x180019fa9  mov     ecx, edi; this
0x180019fab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180019fb0  jmp     short loc_180019FC2
0x180019fb2  mov     ecx, edi; this
0x180019fb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180019fb9  jmp     short loc_180019FC2
0x180019fbb  mov     ecx, edi; this
0x180019fbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180019fc2  mov     ebp, eax
0x180019fc4  mov     [rbx], r15d
0x180019fc7  mov     eax, [rsp+78h+arg_70]
0x180019fce  mov     [rbx+4], eax
0x180019fd1  cmp     dword ptr [r14+8], 1
0x180019fd6  jnz     short loc_180019FDE
0x180019fd8  or      eax, 8
0x180019fdb  mov     [rbx+4], eax
0x180019fde  mov     eax, 1
0x180019fe3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180019feb  inc     eax
0x180019fed  mov     [rbx+10h], eax
0x180019ff0  mov     rax, [rsp+78h+arg_40]
0x180019ff8  xor     edi, edi
0x180019ffa  test    rax, rax
0x180019ffd  jz      short loc_18001A004
0x180019fff  cmp     [rax], di
0x18001a002  jnz     short loc_18001A007
0x18001a004  mov     rax, rdi
0x18001a007  mov     [rbx+18h], rax
0x18001a00b  call    cs:__imp_GetCurrentThreadId
0x18001a011  mov     [rbx+20h], eax
0x18001a014  mov     [rbx+38h], r13
0x18001a018  mov     eax, [rsp+78h+arg_8]
0x18001a01f  mov     [rbx+40h], eax
0x18001a022  mov     [rbx+44h], ebp
0x18001a025  mov     rax, [rsp+78h+arg_20]
0x18001a02d  mov     [rbx+28h], rax
0x18001a031  mov     [rbx+30h], r12
0x18001a035  mov     rax, [rsp+78h+arg_28]
0x18001a03d  mov     [rbx+88h], rax
0x18001a044  mov     rax, [rsp+78h+arg_0]
0x18001a04c  mov     [rbx+90h], rax
0x18001a053  mov     [rbx+48h], rdi
0x18001a057  xorps   xmm0, xmm0
0x18001a05a  xor     eax, eax
0x18001a05c  movups  xmmword ptr [rbx+68h], xmm0
0x18001a060  mov     [rbx+78h], rax
0x18001a064  movups  xmmword ptr [rbx+50h], xmm0
0x18001a068  mov     [rbx+60h], rax
0x18001a06c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001a073  test    rax, rax
0x18001a076  jz      short loc_18001A07F
0x18001a078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a07d  jmp     short loc_18001A082
0x18001a07f  mov     rax, rdi
0x18001a082  mov     [rbx+80h], rax
0x18001a089  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001a090  test    rax, rax
0x18001a093  jz      short loc_18001A09D
0x18001a095  mov     rcx, rbx
0x18001a098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a09d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001a0a4  test    rax, rax
0x18001a0a7  jz      short loc_18001A0BF
0x18001a0a9  mov     r8d, 400h
0x18001a0af  mov     rdx, [rsp+78h+arg_60]
0x18001a0b7  mov     rcx, rbx
0x18001a0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a0c6  test    rax, rax
0x18001a0c9  jz      short loc_18001A0D3
0x18001a0cb  mov     rcx, rbx
0x18001a0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001a0da  test    rax, rax
0x18001a0dd  jz      short loc_18001A0ED
0x18001a0df  test    byte ptr [rbx+4], 2
0x18001a0e3  jnz     short loc_18001A0ED
0x18001a0e5  mov     rcx, rbx
0x18001a0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0ed  cmp     [rbx+8], edi
0x18001a0f0  jl      short loc_18001A10C
0x18001a0f2  cmp     r15d, 3
0x18001a0f6  jnz     loc_18001A1DB
0x18001a0fc  mov     ecx, 8000FFFFh; this
0x18001a101  mov     [rbx+8], ecx
0x18001a104  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001a109  mov     [rbx+0Ch], eax
0x18001a10c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001a113  jnz     short loc_18001A134
0x18001a115  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001a11c  test    rax, rax
0x18001a11f  jz      short loc_18001A12A
0x18001a121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a126  test    al, al
0x18001a128  jmp     short loc_18001A132
0x18001a12a  call    cs:__imp_IsDebuggerPresent
0x18001a130  test    eax, eax
0x18001a132  jz      short loc_18001A13A
0x18001a134  test    byte ptr [rbx+4], 2
0x18001a138  jz      short loc_18001A15E
0x18001a13a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a141  test    rax, rax
0x18001a144  jz      short loc_18001A1A2
0x18001a146  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a14d  jnz     short loc_18001A1A2
0x18001a14f  xor     r8d, r8d
0x18001a152  xor     edx, edx
0x18001a154  mov     rcx, rbx
0x18001a157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a15c  jmp     short loc_18001A1A2
0x18001a15e  mov     ebp, 800h
0x18001a163  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a16a  test    rax, rax
0x18001a16d  jz      short loc_18001A186
0x18001a16f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001a176  jnz     short loc_18001A186
0x18001a178  mov     r8d, ebp
0x18001a17b  mov     rdx, rsi
0x18001a17e  mov     rcx, rbx
0x18001a181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a186  cmp     [rsi], di
0x18001a189  jnz     short loc_18001A199
0x18001a18b  mov     r8, rbx; unsigned __int64
0x18001a18e  mov     rdx, rbp; unsigned __int16 *
0x18001a191  mov     rcx, rsi; this
0x18001a194  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001a199  mov     rcx, rsi; lpOutputString
0x18001a19c  call    cs:__imp_OutputDebugStringW
0x18001a1a2  test    byte ptr [rbx+4], 4
0x18001a1a6  jnz     short loc_18001A1B1
0x18001a1a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001a1af  jz      short loc_18001A1C3
0x18001a1b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001a1b8  test    rax, rax
0x18001a1bb  jz      short loc_18001A1C3
0x18001a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1c2  nop
0x18001a1c3  mov     rbx, [rsp+78h+arg_10]
0x18001a1cb  add     rsp, 40h
0x18001a1cf  pop     r15
0x18001a1d1  pop     r14
0x18001a1d3  pop     r13
0x18001a1d5  pop     r12
0x18001a1d7  pop     rdi
0x18001a1d8  pop     rsi
0x18001a1d9  pop     rbp
0x18001a1da  retn
0x18001a1db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
