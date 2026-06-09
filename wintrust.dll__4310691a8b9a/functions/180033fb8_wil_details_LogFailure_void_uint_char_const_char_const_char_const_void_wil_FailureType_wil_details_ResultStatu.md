# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180033fb8`
- end: `0x1800342b1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180032d0c`
- `0x180033050`

## callees

- `0x1800281d4`
- `0x180031f04`
- `0x1800323e0`
- `0x180032c4c`
- `0x180033fb8`
- `0x1800346a0`
- `0x180034764`
- `0x180034780`
- `0x1800354a8`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800340db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800340db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003426c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003426c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800341fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800341fa`

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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180033fb8  mov     [rsp+arg_10], rbx
0x180033fbd  mov     [rsp+arg_8], edx
0x180033fc1  mov     [rsp+arg_0], rcx
0x180033fc6  push    rbp
0x180033fc7  push    rsi
0x180033fc8  push    rdi
0x180033fc9  push    r12
0x180033fcb  push    r13
0x180033fcd  push    r14
0x180033fcf  push    r15
0x180033fd1  sub     rsp, 40h
0x180033fd5  mov     r12, r9
0x180033fd8  mov     r13, r8
0x180033fdb  mov     r10, rcx
0x180033fde  xor     eax, eax
0x180033fe0  mov     rsi, [rsp+78h+lpOutputString]
0x180033fe8  mov     [rsi], ax
0x180033feb  mov     rax, [rsp+78h+arg_60]
0x180033ff3  mov     byte ptr [rax], 0
0x180033ff6  mov     r14, [rsp+78h+arg_38]
0x180033ffe  mov     edi, [r14]
0x180034001  mov     rbx, [rsp+78h+arg_78]
0x180034009  mov     [rbx+8], edi
0x18003400c  mov     eax, [r14+4]
0x180034010  mov     [rbx+0Ch], eax
0x180034013  xor     ebp, ebp
0x180034015  mov     r15d, [rsp+78h+arg_30]
0x18003401d  mov     ecx, r15d
0x180034020  test    r15d, r15d
0x180034023  jz      short loc_18003408B
0x180034025  sub     ecx, 1
0x180034028  jz      short loc_180034082
0x18003402a  sub     ecx, 1
0x18003402d  jz      short loc_18003403D
0x18003402f  cmp     ecx, 1
0x180034032  jnz     short loc_180034094
0x180034034  mov     ecx, edi; this
0x180034036  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003403b  jmp     short loc_180034092
0x18003403d  test    edi, edi
0x18003403f  js      short loc_180034079
0x180034041  mov     edi, 8007029Ch
0x180034046  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003404a  mov     rax, [rsp+78h+arg_28]
0x180034052  mov     [rsp+78h+var_50], rax; __int64
0x180034057  mov     rax, [rsp+78h+arg_20]
0x18003405f  mov     [rsp+78h+var_58], rax; __int64
0x180034064  mov     rcx, r10; int
0x180034067  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003406c  mov     [rbx+8], edi
0x18003406f  mov     ecx, edi; this
0x180034071  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180034076  mov     [rbx+0Ch], eax
0x180034079  mov     ecx, edi; this
0x18003407b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180034080  jmp     short loc_180034092
0x180034082  mov     ecx, edi; this
0x180034084  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180034089  jmp     short loc_180034092
0x18003408b  mov     ecx, edi; this
0x18003408d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180034092  mov     ebp, eax
0x180034094  mov     [rbx], r15d
0x180034097  mov     eax, [rsp+78h+arg_70]
0x18003409e  mov     [rbx+4], eax
0x1800340a1  cmp     dword ptr [r14+8], 1
0x1800340a6  jnz     short loc_1800340AE
0x1800340a8  or      eax, 8
0x1800340ab  mov     [rbx+4], eax
0x1800340ae  mov     eax, 1
0x1800340b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800340bb  inc     eax
0x1800340bd  mov     [rbx+10h], eax
0x1800340c0  mov     rax, [rsp+78h+arg_40]
0x1800340c8  xor     edi, edi
0x1800340ca  test    rax, rax
0x1800340cd  jz      short loc_1800340D4
0x1800340cf  cmp     [rax], di
0x1800340d2  jnz     short loc_1800340D7
0x1800340d4  mov     rax, rdi
0x1800340d7  mov     [rbx+18h], rax
0x1800340db  call    cs:__imp_GetCurrentThreadId
0x1800340e1  mov     [rbx+20h], eax
0x1800340e4  mov     [rbx+38h], r13
0x1800340e8  mov     eax, [rsp+78h+arg_8]
0x1800340ef  mov     [rbx+40h], eax
0x1800340f2  mov     [rbx+44h], ebp
0x1800340f5  mov     rax, [rsp+78h+arg_20]
0x1800340fd  mov     [rbx+28h], rax
0x180034101  mov     [rbx+30h], r12
0x180034105  mov     rax, [rsp+78h+arg_28]
0x18003410d  mov     [rbx+88h], rax
0x180034114  mov     rax, [rsp+78h+arg_0]
0x18003411c  mov     [rbx+90h], rax
0x180034123  mov     [rbx+48h], rdi
0x180034127  xorps   xmm0, xmm0
0x18003412a  xor     eax, eax
0x18003412c  movups  xmmword ptr [rbx+68h], xmm0
0x180034130  mov     [rbx+78h], rax
0x180034134  movups  xmmword ptr [rbx+50h], xmm0
0x180034138  mov     [rbx+60h], rax
0x18003413c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180034143  test    rax, rax
0x180034146  jz      short loc_18003414F
0x180034148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003414d  jmp     short loc_180034152
0x18003414f  mov     rax, rdi
0x180034152  mov     [rbx+80h], rax
0x180034159  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180034160  test    rax, rax
0x180034163  jz      short loc_18003416D
0x180034165  mov     rcx, rbx
0x180034168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003416d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180034174  test    rax, rax
0x180034177  jz      short loc_18003418F
0x180034179  mov     r8d, 400h
0x18003417f  mov     rdx, [rsp+78h+arg_60]
0x180034187  mov     rcx, rbx
0x18003418a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003418f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180034196  test    rax, rax
0x180034199  jz      short loc_1800341A3
0x18003419b  mov     rcx, rbx
0x18003419e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800341aa  test    rax, rax
0x1800341ad  jz      short loc_1800341BD
0x1800341af  test    byte ptr [rbx+4], 2
0x1800341b3  jnz     short loc_1800341BD
0x1800341b5  mov     rcx, rbx
0x1800341b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341bd  cmp     [rbx+8], edi
0x1800341c0  jl      short loc_1800341DC
0x1800341c2  cmp     r15d, 3
0x1800341c6  jnz     loc_1800342AB
0x1800341cc  mov     ecx, 8000FFFFh; this
0x1800341d1  mov     [rbx+8], ecx
0x1800341d4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800341d9  mov     [rbx+0Ch], eax
0x1800341dc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800341e3  jnz     short loc_180034204
0x1800341e5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800341ec  test    rax, rax
0x1800341ef  jz      short loc_1800341FA
0x1800341f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800341f6  test    al, al
0x1800341f8  jmp     short loc_180034202
0x1800341fa  call    cs:__imp_IsDebuggerPresent
0x180034200  test    eax, eax
0x180034202  jz      short loc_18003420A
0x180034204  test    byte ptr [rbx+4], 2
0x180034208  jz      short loc_18003422E
0x18003420a  mov     rax, cs:g_pfnResultLoggingCallback
0x180034211  test    rax, rax
0x180034214  jz      short loc_180034272
0x180034216  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003421d  jnz     short loc_180034272
0x18003421f  xor     r8d, r8d
0x180034222  xor     edx, edx
0x180034224  mov     rcx, rbx
0x180034227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003422c  jmp     short loc_180034272
0x18003422e  mov     ebp, 800h
0x180034233  mov     rax, cs:g_pfnResultLoggingCallback
0x18003423a  test    rax, rax
0x18003423d  jz      short loc_180034256
0x18003423f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180034246  jnz     short loc_180034256
0x180034248  mov     r8d, ebp
0x18003424b  mov     rdx, rsi
0x18003424e  mov     rcx, rbx
0x180034251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034256  cmp     [rsi], di
0x180034259  jnz     short loc_180034269
0x18003425b  mov     r8, rbx; unsigned __int64
0x18003425e  mov     rdx, rbp; unsigned __int16 *
0x180034261  mov     rcx, rsi; this
0x180034264  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180034269  mov     rcx, rsi; lpOutputString
0x18003426c  call    cs:__imp_OutputDebugStringW
0x180034272  test    byte ptr [rbx+4], 4
0x180034276  jnz     short loc_180034281
0x180034278  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003427f  jz      short loc_180034293
0x180034281  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180034288  test    rax, rax
0x18003428b  jz      short loc_180034293
0x18003428d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034292  nop
0x180034293  mov     rbx, [rsp+78h+arg_10]
0x18003429b  add     rsp, 40h
0x18003429f  pop     r15
0x1800342a1  pop     r14
0x1800342a3  pop     r13
0x1800342a5  pop     r12
0x1800342a7  pop     rdi
0x1800342a8  pop     rsi
0x1800342a9  pop     rbp
0x1800342aa  retn
0x1800342ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
