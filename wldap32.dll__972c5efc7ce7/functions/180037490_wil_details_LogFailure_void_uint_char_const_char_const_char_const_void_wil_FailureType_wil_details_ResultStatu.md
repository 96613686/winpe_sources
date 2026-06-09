# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180037490`
- end: `0x180037797`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800359a8`
- `0x180035a58`
- `0x180035b50`

## callees

- `0x180033ab0`
- `0x1800358fc`
- `0x180036b94`
- `0x180037490`
- `0x180037fd8`
- `0x180038000`
- `0x1800380c4`
- `0x1800380e4`
- `0x1800395f8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800375b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800375b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800376da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800376da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180037752`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180037752`

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
0x180037490  mov     [rsp+arg_10], rbx
0x180037495  mov     [rsp+arg_8], edx
0x180037499  mov     [rsp+arg_0], rcx
0x18003749e  push    rbp
0x18003749f  push    rsi
0x1800374a0  push    rdi
0x1800374a1  push    r12
0x1800374a3  push    r13
0x1800374a5  push    r14
0x1800374a7  push    r15
0x1800374a9  sub     rsp, 40h
0x1800374ad  mov     r14, [rsp+78h+arg_38]
0x1800374b5  xor     eax, eax
0x1800374b7  mov     rbx, [rsp+78h+arg_78]
0x1800374bf  xor     ebp, ebp
0x1800374c1  mov     r15d, [rsp+78h+arg_30]
0x1800374c9  mov     r10, rcx
0x1800374cc  mov     rsi, [rsp+78h+lpOutputString]
0x1800374d4  mov     r12, r9
0x1800374d7  mov     r13, r8
0x1800374da  mov     ecx, r15d
0x1800374dd  mov     [rsi], ax
0x1800374e0  mov     rax, [rsp+78h+arg_60]
0x1800374e8  mov     byte ptr [rax], 0
0x1800374eb  mov     edi, [r14]
0x1800374ee  mov     [rbx+8], edi
0x1800374f1  mov     eax, [r14+4]
0x1800374f5  mov     [rbx+0Ch], eax
0x1800374f8  test    r15d, r15d
0x1800374fb  jz      short loc_180037563
0x1800374fd  sub     ecx, 1
0x180037500  jz      short loc_18003755A
0x180037502  sub     ecx, 1
0x180037505  jz      short loc_180037515
0x180037507  cmp     ecx, 1
0x18003750a  jnz     short loc_18003756C
0x18003750c  mov     ecx, edi; this
0x18003750e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180037513  jmp     short loc_18003756A
0x180037515  test    edi, edi
0x180037517  js      short loc_180037551
0x180037519  mov     rax, [rsp+78h+arg_28]
0x180037521  mov     edi, 8007029Ch
0x180037526  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003752a  mov     rcx, r10; int
0x18003752d  mov     [rsp+78h+var_50], rax; __int64
0x180037532  mov     rax, [rsp+78h+arg_20]
0x18003753a  mov     [rsp+78h+var_58], rax; __int64
0x18003753f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180037544  mov     ecx, edi; this
0x180037546  mov     [rbx+8], edi
0x180037549  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003754e  mov     [rbx+0Ch], eax
0x180037551  mov     ecx, edi; this
0x180037553  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180037558  jmp     short loc_18003756A
0x18003755a  mov     ecx, edi; this
0x18003755c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180037561  jmp     short loc_18003756A
0x180037563  mov     ecx, edi; this
0x180037565  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003756a  mov     ebp, eax
0x18003756c  mov     eax, [rsp+78h+arg_70]
0x180037573  mov     [rbx+4], eax
0x180037576  mov     [rbx], r15d
0x180037579  cmp     dword ptr [r14+8], 1
0x18003757e  jnz     short loc_180037586
0x180037580  or      eax, 8
0x180037583  mov     [rbx+4], eax
0x180037586  mov     eax, 1
0x18003758b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180037593  inc     eax
0x180037595  xor     edi, edi
0x180037597  mov     [rbx+10h], eax
0x18003759a  mov     rax, [rsp+78h+arg_40]
0x1800375a2  test    rax, rax
0x1800375a5  jz      short loc_1800375AC
0x1800375a7  cmp     [rax], di
0x1800375aa  jnz     short loc_1800375AF
0x1800375ac  mov     rax, rdi
0x1800375af  mov     [rbx+18h], rax
0x1800375b3  call    cs:__imp_GetCurrentThreadId
0x1800375ba  nop     dword ptr [rax+rax+00h]
0x1800375bf  mov     [rbx+38h], r13
0x1800375c3  xorps   xmm0, xmm0
0x1800375c6  mov     [rbx+20h], eax
0x1800375c9  mov     eax, [rsp+78h+arg_8]
0x1800375d0  mov     [rbx+40h], eax
0x1800375d3  mov     rax, [rsp+78h+arg_20]
0x1800375db  mov     [rbx+28h], rax
0x1800375df  mov     rax, [rsp+78h+arg_28]
0x1800375e7  mov     [rbx+88h], rax
0x1800375ee  mov     rax, [rsp+78h+arg_0]
0x1800375f6  mov     [rbx+90h], rax
0x1800375fd  xor     eax, eax
0x1800375ff  mov     [rbx+44h], ebp
0x180037602  mov     [rbx+30h], r12
0x180037606  mov     [rbx+48h], rdi
0x18003760a  movups  xmmword ptr [rbx+68h], xmm0
0x18003760e  mov     [rbx+78h], rax
0x180037612  movups  xmmword ptr [rbx+50h], xmm0
0x180037616  mov     [rbx+60h], rax
0x18003761a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180037621  test    rax, rax
0x180037624  jz      short loc_18003762D
0x180037626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003762b  jmp     short loc_180037630
0x18003762d  mov     rax, rdi
0x180037630  mov     [rbx+80h], rax
0x180037637  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003763e  test    rax, rax
0x180037641  jz      short loc_18003764B
0x180037643  mov     rcx, rbx
0x180037646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003764b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180037652  test    rax, rax
0x180037655  jz      short loc_18003766D
0x180037657  mov     rdx, [rsp+78h+arg_60]
0x18003765f  mov     r8d, 400h
0x180037665  mov     rcx, rbx
0x180037668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003766d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180037674  test    rax, rax
0x180037677  jz      short loc_180037681
0x180037679  mov     rcx, rbx
0x18003767c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037681  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180037688  test    rax, rax
0x18003768b  jz      short loc_18003769B
0x18003768d  test    byte ptr [rbx+4], 2
0x180037691  jnz     short loc_18003769B
0x180037693  mov     rcx, rbx
0x180037696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003769b  cmp     [rbx+8], edi
0x18003769e  jl      short loc_1800376BC
0x1800376a0  cmp     r15d, 3
0x1800376a4  jz      short loc_1800376AC
0x1800376a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800376ac  mov     ecx, 8000FFFFh; this
0x1800376b1  mov     [rbx+8], ecx
0x1800376b4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800376b9  mov     [rbx+0Ch], eax
0x1800376bc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800376c3  jnz     short loc_1800376EA
0x1800376c5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800376cc  test    rax, rax
0x1800376cf  jz      short loc_1800376DA
0x1800376d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376d6  test    al, al
0x1800376d8  jmp     short loc_1800376E8
0x1800376da  call    cs:__imp_IsDebuggerPresent
0x1800376e1  nop     dword ptr [rax+rax+00h]
0x1800376e6  test    eax, eax
0x1800376e8  jz      short loc_1800376F0
0x1800376ea  test    byte ptr [rbx+4], 2
0x1800376ee  jz      short loc_180037714
0x1800376f0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800376f7  test    rax, rax
0x1800376fa  jz      short loc_18003775E
0x1800376fc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180037703  jnz     short loc_18003775E
0x180037705  xor     r8d, r8d
0x180037708  xor     edx, edx
0x18003770a  mov     rcx, rbx
0x18003770d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037712  jmp     short loc_18003775E
0x180037714  mov     rax, cs:g_pfnResultLoggingCallback
0x18003771b  mov     ebp, 800h
0x180037720  test    rax, rax
0x180037723  jz      short loc_18003773C
0x180037725  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003772c  jnz     short loc_18003773C
0x18003772e  mov     r8d, ebp
0x180037731  mov     rdx, rsi
0x180037734  mov     rcx, rbx
0x180037737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003773c  cmp     [rsi], di
0x18003773f  jnz     short loc_18003774F
0x180037741  mov     r8, rbx; unsigned __int64
0x180037744  mov     rdx, rbp; unsigned __int16 *
0x180037747  mov     rcx, rsi; this
0x18003774a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003774f  mov     rcx, rsi; lpOutputString
0x180037752  call    cs:__imp_OutputDebugStringW
0x180037759  nop     dword ptr [rax+rax+00h]
0x18003775e  test    byte ptr [rbx+4], 4
0x180037762  jnz     short loc_18003776D
0x180037764  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003776b  jz      short loc_18003777E
0x18003776d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180037774  test    rax, rax
0x180037777  jz      short loc_18003777E
0x180037779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003777e  mov     rbx, [rsp+78h+arg_10]
0x180037786  add     rsp, 40h
0x18003778a  pop     r15
0x18003778c  pop     r14
0x18003778e  pop     r13
0x180037790  pop     r12
0x180037792  pop     rdi
0x180037793  pop     rsi
0x180037794  pop     rbp
0x180037795  retn
```
