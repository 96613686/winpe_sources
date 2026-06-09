# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800080a8`
- end: `0x1800083a0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000514c`
- `0x180005490`

## callees

- `0x18000508c`
- `0x180007204`
- `0x180007bd0`
- `0x1800080a8`
- `0x180008d4c`
- `0x180008d70`
- `0x180008d84`
- `0x180008da0`
- `0x18000b068`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000835c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000835c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800082ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800082ea`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x1800080a8  mov     [rsp+arg_10], rbx
0x1800080ad  mov     [rsp+arg_8], edx
0x1800080b1  mov     [rsp+arg_0], rcx
0x1800080b6  push    rbp
0x1800080b7  push    rsi
0x1800080b8  push    rdi
0x1800080b9  push    r12
0x1800080bb  push    r13
0x1800080bd  push    r14
0x1800080bf  push    r15
0x1800080c1  sub     rsp, 40h
0x1800080c5  mov     r14, [rsp+78h+arg_38]
0x1800080cd  xor     eax, eax
0x1800080cf  mov     rbx, [rsp+78h+arg_78]
0x1800080d7  xor     ebp, ebp
0x1800080d9  mov     r15d, [rsp+78h+arg_30]
0x1800080e1  mov     r10, rcx
0x1800080e4  mov     rsi, [rsp+78h+lpOutputString]
0x1800080ec  mov     r12, r9
0x1800080ef  mov     r13, r8
0x1800080f2  mov     ecx, r15d
0x1800080f5  mov     [rsi], ax
0x1800080f8  mov     rax, [rsp+78h+arg_60]
0x180008100  mov     byte ptr [rax], 0
0x180008103  mov     edi, [r14]
0x180008106  mov     [rbx+8], edi
0x180008109  mov     eax, [r14+4]
0x18000810d  mov     [rbx+0Ch], eax
0x180008110  test    r15d, r15d
0x180008113  jz      short loc_18000817B
0x180008115  sub     ecx, 1
0x180008118  jz      short loc_180008172
0x18000811a  sub     ecx, 1
0x18000811d  jz      short loc_18000812D
0x18000811f  cmp     ecx, 1
0x180008122  jnz     short loc_180008184
0x180008124  mov     ecx, edi; this
0x180008126  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000812b  jmp     short loc_180008182
0x18000812d  test    edi, edi
0x18000812f  js      short loc_180008169
0x180008131  mov     rax, [rsp+78h+arg_28]
0x180008139  mov     edi, 8007029Ch
0x18000813e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008142  mov     rcx, r10; int
0x180008145  mov     [rsp+78h+var_50], rax; __int64
0x18000814a  mov     rax, [rsp+78h+arg_20]
0x180008152  mov     [rsp+78h+var_58], rax; __int64
0x180008157  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000815c  mov     ecx, edi; this
0x18000815e  mov     [rbx+8], edi
0x180008161  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008166  mov     [rbx+0Ch], eax
0x180008169  mov     ecx, edi; this
0x18000816b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008170  jmp     short loc_180008182
0x180008172  mov     ecx, edi; this
0x180008174  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008179  jmp     short loc_180008182
0x18000817b  mov     ecx, edi; this
0x18000817d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008182  mov     ebp, eax
0x180008184  mov     eax, [rsp+78h+arg_70]
0x18000818b  mov     [rbx+4], eax
0x18000818e  mov     [rbx], r15d
0x180008191  cmp     dword ptr [r14+8], 1
0x180008196  jnz     short loc_18000819E
0x180008198  or      eax, 8
0x18000819b  mov     [rbx+4], eax
0x18000819e  mov     eax, 1
0x1800081a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800081ab  inc     eax
0x1800081ad  xor     edi, edi
0x1800081af  mov     [rbx+10h], eax
0x1800081b2  mov     rax, [rsp+78h+arg_40]
0x1800081ba  test    rax, rax
0x1800081bd  jz      short loc_1800081C4
0x1800081bf  cmp     [rax], di
0x1800081c2  jnz     short loc_1800081C7
0x1800081c4  mov     rax, rdi
0x1800081c7  mov     [rbx+18h], rax
0x1800081cb  call    cs:__imp_GetCurrentThreadId
0x1800081d1  mov     [rbx+38h], r13
0x1800081d5  xorps   xmm0, xmm0
0x1800081d8  mov     [rbx+20h], eax
0x1800081db  mov     eax, [rsp+78h+arg_8]
0x1800081e2  mov     [rbx+40h], eax
0x1800081e5  mov     rax, [rsp+78h+arg_20]
0x1800081ed  mov     [rbx+28h], rax
0x1800081f1  mov     rax, [rsp+78h+arg_28]
0x1800081f9  mov     [rbx+88h], rax
0x180008200  mov     rax, [rsp+78h+arg_0]
0x180008208  mov     [rbx+90h], rax
0x18000820f  xor     eax, eax
0x180008211  mov     [rbx+44h], ebp
0x180008214  mov     [rbx+30h], r12
0x180008218  mov     [rbx+48h], rdi
0x18000821c  movups  xmmword ptr [rbx+68h], xmm0
0x180008220  mov     [rbx+78h], rax
0x180008224  movups  xmmword ptr [rbx+50h], xmm0
0x180008228  mov     [rbx+60h], rax
0x18000822c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008233  test    rax, rax
0x180008236  jz      short loc_18000823F
0x180008238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000823d  jmp     short loc_180008242
0x18000823f  mov     rax, rdi
0x180008242  mov     [rbx+80h], rax
0x180008249  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008250  test    rax, rax
0x180008253  jz      short loc_18000825D
0x180008255  mov     rcx, rbx
0x180008258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008264  test    rax, rax
0x180008267  jz      short loc_18000827F
0x180008269  mov     rdx, [rsp+78h+arg_60]
0x180008271  mov     r8d, 400h
0x180008277  mov     rcx, rbx
0x18000827a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008286  test    rax, rax
0x180008289  jz      short loc_180008293
0x18000828b  mov     rcx, rbx
0x18000828e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008293  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000829a  test    rax, rax
0x18000829d  jz      short loc_1800082AD
0x18000829f  test    byte ptr [rbx+4], 2
0x1800082a3  jnz     short loc_1800082AD
0x1800082a5  mov     rcx, rbx
0x1800082a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082ad  cmp     [rbx+8], edi
0x1800082b0  jl      short loc_1800082CC
0x1800082b2  cmp     r15d, 3
0x1800082b6  jnz     loc_18000839A
0x1800082bc  mov     ecx, 8000FFFFh; this
0x1800082c1  mov     [rbx+8], ecx
0x1800082c4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800082c9  mov     [rbx+0Ch], eax
0x1800082cc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800082d3  jnz     short loc_1800082F4
0x1800082d5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800082dc  test    rax, rax
0x1800082df  jz      short loc_1800082EA
0x1800082e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e6  test    al, al
0x1800082e8  jmp     short loc_1800082F2
0x1800082ea  call    cs:__imp_IsDebuggerPresent
0x1800082f0  test    eax, eax
0x1800082f2  jz      short loc_1800082FA
0x1800082f4  test    byte ptr [rbx+4], 2
0x1800082f8  jz      short loc_18000831E
0x1800082fa  mov     rax, cs:g_pfnResultLoggingCallback
0x180008301  test    rax, rax
0x180008304  jz      short loc_180008362
0x180008306  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000830d  jnz     short loc_180008362
0x18000830f  xor     r8d, r8d
0x180008312  xor     edx, edx
0x180008314  mov     rcx, rbx
0x180008317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000831c  jmp     short loc_180008362
0x18000831e  mov     rax, cs:g_pfnResultLoggingCallback
0x180008325  mov     ebp, 800h
0x18000832a  test    rax, rax
0x18000832d  jz      short loc_180008346
0x18000832f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008336  jnz     short loc_180008346
0x180008338  mov     r8d, ebp
0x18000833b  mov     rdx, rsi
0x18000833e  mov     rcx, rbx
0x180008341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008346  cmp     [rsi], di
0x180008349  jnz     short loc_180008359
0x18000834b  mov     r8, rbx; unsigned __int64
0x18000834e  mov     rdx, rbp; unsigned __int16 *
0x180008351  mov     rcx, rsi; this
0x180008354  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008359  mov     rcx, rsi; lpOutputString
0x18000835c  call    cs:__imp_OutputDebugStringW
0x180008362  test    byte ptr [rbx+4], 4
0x180008366  jnz     short loc_180008371
0x180008368  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000836f  jz      short loc_180008382
0x180008371  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008378  test    rax, rax
0x18000837b  jz      short loc_180008382
0x18000837d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008382  mov     rbx, [rsp+78h+arg_10]
0x18000838a  add     rsp, 40h
0x18000838e  pop     r15
0x180008390  pop     r14
0x180008392  pop     r13
0x180008394  pop     r12
0x180008396  pop     rdi
0x180008397  pop     rsi
0x180008398  pop     rbp
0x180008399  retn
0x18000839a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
