# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001f370`
- end: `0x18001f668`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001cff0`

## callees

- `0x18001a1f8`
- `0x18001ca34`
- `0x18001e7a4`
- `0x18001f370`
- `0x1800201d0`
- `0x1800201f0`
- `0x180020374`
- `0x180020390`
- `0x1800220dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f493`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f493`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f624`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f624`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f5b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f5b2`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18001f370  mov     [rsp+arg_10], rbx
0x18001f375  mov     [rsp+arg_8], edx
0x18001f379  mov     [rsp+arg_0], rcx
0x18001f37e  push    rbp
0x18001f37f  push    rsi
0x18001f380  push    rdi
0x18001f381  push    r12
0x18001f383  push    r13
0x18001f385  push    r14
0x18001f387  push    r15
0x18001f389  sub     rsp, 40h
0x18001f38d  mov     r14, [rsp+78h+arg_38]
0x18001f395  xor     eax, eax
0x18001f397  mov     rbx, [rsp+78h+arg_78]
0x18001f39f  xor     ebp, ebp
0x18001f3a1  mov     r15d, [rsp+78h+arg_30]
0x18001f3a9  mov     r10, rcx
0x18001f3ac  mov     rsi, [rsp+78h+lpOutputString]
0x18001f3b4  mov     r12, r9
0x18001f3b7  mov     r13, r8
0x18001f3ba  mov     ecx, r15d
0x18001f3bd  mov     [rsi], ax
0x18001f3c0  mov     rax, [rsp+78h+arg_60]
0x18001f3c8  mov     byte ptr [rax], 0
0x18001f3cb  mov     edi, [r14]
0x18001f3ce  mov     [rbx+8], edi
0x18001f3d1  mov     eax, [r14+4]
0x18001f3d5  mov     [rbx+0Ch], eax
0x18001f3d8  test    r15d, r15d
0x18001f3db  jz      short loc_18001F443
0x18001f3dd  sub     ecx, 1
0x18001f3e0  jz      short loc_18001F43A
0x18001f3e2  sub     ecx, 1
0x18001f3e5  jz      short loc_18001F3F5
0x18001f3e7  cmp     ecx, 1
0x18001f3ea  jnz     short loc_18001F44C
0x18001f3ec  mov     ecx, edi; this
0x18001f3ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001f3f3  jmp     short loc_18001F44A
0x18001f3f5  test    edi, edi
0x18001f3f7  js      short loc_18001F431
0x18001f3f9  mov     rax, [rsp+78h+arg_28]
0x18001f401  mov     edi, 8007029Ch
0x18001f406  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001f40a  mov     rcx, r10; int
0x18001f40d  mov     [rsp+78h+var_50], rax; __int64
0x18001f412  mov     rax, [rsp+78h+arg_20]
0x18001f41a  mov     [rsp+78h+var_58], rax; __int64
0x18001f41f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001f424  mov     ecx, edi; this
0x18001f426  mov     [rbx+8], edi
0x18001f429  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f42e  mov     [rbx+0Ch], eax
0x18001f431  mov     ecx, edi; this
0x18001f433  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001f438  jmp     short loc_18001F44A
0x18001f43a  mov     ecx, edi; this
0x18001f43c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001f441  jmp     short loc_18001F44A
0x18001f443  mov     ecx, edi; this
0x18001f445  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001f44a  mov     ebp, eax
0x18001f44c  mov     eax, [rsp+78h+arg_70]
0x18001f453  mov     [rbx+4], eax
0x18001f456  mov     [rbx], r15d
0x18001f459  cmp     dword ptr [r14+8], 1
0x18001f45e  jnz     short loc_18001F466
0x18001f460  or      eax, 8
0x18001f463  mov     [rbx+4], eax
0x18001f466  mov     eax, 1
0x18001f46b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001f473  inc     eax
0x18001f475  xor     edi, edi
0x18001f477  mov     [rbx+10h], eax
0x18001f47a  mov     rax, [rsp+78h+arg_40]
0x18001f482  test    rax, rax
0x18001f485  jz      short loc_18001F48C
0x18001f487  cmp     [rax], di
0x18001f48a  jnz     short loc_18001F48F
0x18001f48c  mov     rax, rdi
0x18001f48f  mov     [rbx+18h], rax
0x18001f493  call    cs:__imp_GetCurrentThreadId
0x18001f499  mov     [rbx+38h], r13
0x18001f49d  xorps   xmm0, xmm0
0x18001f4a0  mov     [rbx+20h], eax
0x18001f4a3  mov     eax, [rsp+78h+arg_8]
0x18001f4aa  mov     [rbx+40h], eax
0x18001f4ad  mov     rax, [rsp+78h+arg_20]
0x18001f4b5  mov     [rbx+28h], rax
0x18001f4b9  mov     rax, [rsp+78h+arg_28]
0x18001f4c1  mov     [rbx+88h], rax
0x18001f4c8  mov     rax, [rsp+78h+arg_0]
0x18001f4d0  mov     [rbx+90h], rax
0x18001f4d7  xor     eax, eax
0x18001f4d9  mov     [rbx+44h], ebp
0x18001f4dc  mov     [rbx+30h], r12
0x18001f4e0  mov     [rbx+48h], rdi
0x18001f4e4  movups  xmmword ptr [rbx+68h], xmm0
0x18001f4e8  mov     [rbx+78h], rax
0x18001f4ec  movups  xmmword ptr [rbx+50h], xmm0
0x18001f4f0  mov     [rbx+60h], rax
0x18001f4f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001f4fb  test    rax, rax
0x18001f4fe  jz      short loc_18001F507
0x18001f500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f505  jmp     short loc_18001F50A
0x18001f507  mov     rax, rdi
0x18001f50a  mov     [rbx+80h], rax
0x18001f511  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001f518  test    rax, rax
0x18001f51b  jz      short loc_18001F525
0x18001f51d  mov     rcx, rbx
0x18001f520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f525  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001f52c  test    rax, rax
0x18001f52f  jz      short loc_18001F547
0x18001f531  mov     rdx, [rsp+78h+arg_60]
0x18001f539  mov     r8d, 400h
0x18001f53f  mov     rcx, rbx
0x18001f542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f547  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f54e  test    rax, rax
0x18001f551  jz      short loc_18001F55B
0x18001f553  mov     rcx, rbx
0x18001f556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f55b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f562  test    rax, rax
0x18001f565  jz      short loc_18001F575
0x18001f567  test    byte ptr [rbx+4], 2
0x18001f56b  jnz     short loc_18001F575
0x18001f56d  mov     rcx, rbx
0x18001f570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f575  cmp     [rbx+8], edi
0x18001f578  jl      short loc_18001F594
0x18001f57a  cmp     r15d, 3
0x18001f57e  jnz     loc_18001F662
0x18001f584  mov     ecx, 8000FFFFh; this
0x18001f589  mov     [rbx+8], ecx
0x18001f58c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f591  mov     [rbx+0Ch], eax
0x18001f594  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001f59b  jnz     short loc_18001F5BC
0x18001f59d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001f5a4  test    rax, rax
0x18001f5a7  jz      short loc_18001F5B2
0x18001f5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5ae  test    al, al
0x18001f5b0  jmp     short loc_18001F5BA
0x18001f5b2  call    cs:__imp_IsDebuggerPresent
0x18001f5b8  test    eax, eax
0x18001f5ba  jz      short loc_18001F5C2
0x18001f5bc  test    byte ptr [rbx+4], 2
0x18001f5c0  jz      short loc_18001F5E6
0x18001f5c2  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f5c9  test    rax, rax
0x18001f5cc  jz      short loc_18001F62A
0x18001f5ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f5d5  jnz     short loc_18001F62A
0x18001f5d7  xor     r8d, r8d
0x18001f5da  xor     edx, edx
0x18001f5dc  mov     rcx, rbx
0x18001f5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5e4  jmp     short loc_18001F62A
0x18001f5e6  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f5ed  mov     ebp, 800h
0x18001f5f2  test    rax, rax
0x18001f5f5  jz      short loc_18001F60E
0x18001f5f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f5fe  jnz     short loc_18001F60E
0x18001f600  mov     r8d, ebp
0x18001f603  mov     rdx, rsi
0x18001f606  mov     rcx, rbx
0x18001f609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f60e  cmp     [rsi], di
0x18001f611  jnz     short loc_18001F621
0x18001f613  mov     r8, rbx; unsigned __int64
0x18001f616  mov     rdx, rbp; unsigned __int16 *
0x18001f619  mov     rcx, rsi; this
0x18001f61c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001f621  mov     rcx, rsi; lpOutputString
0x18001f624  call    cs:__imp_OutputDebugStringW
0x18001f62a  test    byte ptr [rbx+4], 4
0x18001f62e  jnz     short loc_18001F639
0x18001f630  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001f637  jz      short loc_18001F64A
0x18001f639  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001f640  test    rax, rax
0x18001f643  jz      short loc_18001F64A
0x18001f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f64a  mov     rbx, [rsp+78h+arg_10]
0x18001f652  add     rsp, 40h
0x18001f656  pop     r15
0x18001f658  pop     r14
0x18001f65a  pop     r13
0x18001f65c  pop     r12
0x18001f65e  pop     rdi
0x18001f65f  pop     rsi
0x18001f660  pop     rbp
0x18001f661  retn
0x18001f662  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
