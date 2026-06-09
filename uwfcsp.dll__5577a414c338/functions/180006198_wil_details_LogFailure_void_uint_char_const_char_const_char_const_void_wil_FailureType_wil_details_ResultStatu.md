# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006198`
- end: `0x180006490`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004c28`

## callees

- `0x18000466c`
- `0x180005794`
- `0x180005fd4`
- `0x180006198`
- `0x1800066dc`
- `0x180006700`
- `0x180006714`
- `0x180006730`
- `0x180007228`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062bb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800063da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800063da`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000644c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000644c`

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
0x180006198  mov     [rsp+arg_10], rbx
0x18000619d  mov     [rsp+arg_8], edx
0x1800061a1  mov     [rsp+arg_0], rcx
0x1800061a6  push    rbp
0x1800061a7  push    rsi
0x1800061a8  push    rdi
0x1800061a9  push    r12
0x1800061ab  push    r13
0x1800061ad  push    r14
0x1800061af  push    r15
0x1800061b1  sub     rsp, 40h
0x1800061b5  mov     r14, [rsp+78h+arg_38]
0x1800061bd  xor     eax, eax
0x1800061bf  mov     rbx, [rsp+78h+arg_78]
0x1800061c7  xor     ebp, ebp
0x1800061c9  mov     r15d, [rsp+78h+arg_30]
0x1800061d1  mov     r10, rcx
0x1800061d4  mov     rsi, [rsp+78h+lpOutputString]
0x1800061dc  mov     r12, r9
0x1800061df  mov     r13, r8
0x1800061e2  mov     ecx, r15d
0x1800061e5  mov     [rsi], ax
0x1800061e8  mov     rax, [rsp+78h+arg_60]
0x1800061f0  mov     byte ptr [rax], 0
0x1800061f3  mov     edi, [r14]
0x1800061f6  mov     [rbx+8], edi
0x1800061f9  mov     eax, [r14+4]
0x1800061fd  mov     [rbx+0Ch], eax
0x180006200  test    r15d, r15d
0x180006203  jz      short loc_18000626B
0x180006205  sub     ecx, 1
0x180006208  jz      short loc_180006262
0x18000620a  sub     ecx, 1
0x18000620d  jz      short loc_18000621D
0x18000620f  cmp     ecx, 1
0x180006212  jnz     short loc_180006274
0x180006214  mov     ecx, edi; this
0x180006216  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000621b  jmp     short loc_180006272
0x18000621d  test    edi, edi
0x18000621f  js      short loc_180006259
0x180006221  mov     rax, [rsp+78h+arg_28]
0x180006229  mov     edi, 8007029Ch
0x18000622e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006232  mov     rcx, r10; int
0x180006235  mov     [rsp+78h+var_50], rax; __int64
0x18000623a  mov     rax, [rsp+78h+arg_20]
0x180006242  mov     [rsp+78h+var_58], rax; __int64
0x180006247  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000624c  mov     ecx, edi; this
0x18000624e  mov     [rbx+8], edi
0x180006251  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006256  mov     [rbx+0Ch], eax
0x180006259  mov     ecx, edi; this
0x18000625b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006260  jmp     short loc_180006272
0x180006262  mov     ecx, edi; this
0x180006264  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006269  jmp     short loc_180006272
0x18000626b  mov     ecx, edi; this
0x18000626d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006272  mov     ebp, eax
0x180006274  mov     eax, [rsp+78h+arg_70]
0x18000627b  mov     [rbx+4], eax
0x18000627e  mov     [rbx], r15d
0x180006281  cmp     dword ptr [r14+8], 1
0x180006286  jnz     short loc_18000628E
0x180006288  or      eax, 8
0x18000628b  mov     [rbx+4], eax
0x18000628e  mov     eax, 1
0x180006293  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000629b  inc     eax
0x18000629d  xor     edi, edi
0x18000629f  mov     [rbx+10h], eax
0x1800062a2  mov     rax, [rsp+78h+arg_40]
0x1800062aa  test    rax, rax
0x1800062ad  jz      short loc_1800062B4
0x1800062af  cmp     [rax], di
0x1800062b2  jnz     short loc_1800062B7
0x1800062b4  mov     rax, rdi
0x1800062b7  mov     [rbx+18h], rax
0x1800062bb  call    cs:__imp_GetCurrentThreadId
0x1800062c1  mov     [rbx+38h], r13
0x1800062c5  xorps   xmm0, xmm0
0x1800062c8  mov     [rbx+20h], eax
0x1800062cb  mov     eax, [rsp+78h+arg_8]
0x1800062d2  mov     [rbx+40h], eax
0x1800062d5  mov     rax, [rsp+78h+arg_20]
0x1800062dd  mov     [rbx+28h], rax
0x1800062e1  mov     rax, [rsp+78h+arg_28]
0x1800062e9  mov     [rbx+88h], rax
0x1800062f0  mov     rax, [rsp+78h+arg_0]
0x1800062f8  mov     [rbx+90h], rax
0x1800062ff  xor     eax, eax
0x180006301  mov     [rbx+44h], ebp
0x180006304  mov     [rbx+30h], r12
0x180006308  mov     [rbx+48h], rdi
0x18000630c  movups  xmmword ptr [rbx+68h], xmm0
0x180006310  mov     [rbx+78h], rax
0x180006314  movups  xmmword ptr [rbx+50h], xmm0
0x180006318  mov     [rbx+60h], rax
0x18000631c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006323  test    rax, rax
0x180006326  jz      short loc_18000632F
0x180006328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632d  jmp     short loc_180006332
0x18000632f  mov     rax, rdi
0x180006332  mov     [rbx+80h], rax
0x180006339  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006340  test    rax, rax
0x180006343  jz      short loc_18000634D
0x180006345  mov     rcx, rbx
0x180006348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006354  test    rax, rax
0x180006357  jz      short loc_18000636F
0x180006359  mov     rdx, [rsp+78h+arg_60]
0x180006361  mov     r8d, 400h
0x180006367  mov     rcx, rbx
0x18000636a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006376  test    rax, rax
0x180006379  jz      short loc_180006383
0x18000637b  mov     rcx, rbx
0x18000637e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006383  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000638a  test    rax, rax
0x18000638d  jz      short loc_18000639D
0x18000638f  test    byte ptr [rbx+4], 2
0x180006393  jnz     short loc_18000639D
0x180006395  mov     rcx, rbx
0x180006398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639d  cmp     [rbx+8], edi
0x1800063a0  jl      short loc_1800063BC
0x1800063a2  cmp     r15d, 3
0x1800063a6  jnz     loc_18000648A
0x1800063ac  mov     ecx, 8000FFFFh; this
0x1800063b1  mov     [rbx+8], ecx
0x1800063b4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800063b9  mov     [rbx+0Ch], eax
0x1800063bc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800063c3  jnz     short loc_1800063E4
0x1800063c5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800063cc  test    rax, rax
0x1800063cf  jz      short loc_1800063DA
0x1800063d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d6  test    al, al
0x1800063d8  jmp     short loc_1800063E2
0x1800063da  call    cs:__imp_IsDebuggerPresent
0x1800063e0  test    eax, eax
0x1800063e2  jz      short loc_1800063EA
0x1800063e4  test    byte ptr [rbx+4], 2
0x1800063e8  jz      short loc_18000640E
0x1800063ea  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063f1  test    rax, rax
0x1800063f4  jz      short loc_180006452
0x1800063f6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800063fd  jnz     short loc_180006452
0x1800063ff  xor     r8d, r8d
0x180006402  xor     edx, edx
0x180006404  mov     rcx, rbx
0x180006407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000640c  jmp     short loc_180006452
0x18000640e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006415  mov     ebp, 800h
0x18000641a  test    rax, rax
0x18000641d  jz      short loc_180006436
0x18000641f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006426  jnz     short loc_180006436
0x180006428  mov     r8d, ebp
0x18000642b  mov     rdx, rsi
0x18000642e  mov     rcx, rbx
0x180006431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006436  cmp     [rsi], di
0x180006439  jnz     short loc_180006449
0x18000643b  mov     r8, rbx; unsigned __int64
0x18000643e  mov     rdx, rbp; unsigned __int16 *
0x180006441  mov     rcx, rsi; this
0x180006444  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006449  mov     rcx, rsi; lpOutputString
0x18000644c  call    cs:__imp_OutputDebugStringW
0x180006452  test    byte ptr [rbx+4], 4
0x180006456  jnz     short loc_180006461
0x180006458  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000645f  jz      short loc_180006472
0x180006461  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006468  test    rax, rax
0x18000646b  jz      short loc_180006472
0x18000646d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006472  mov     rbx, [rsp+78h+arg_10]
0x18000647a  add     rsp, 40h
0x18000647e  pop     r15
0x180006480  pop     r14
0x180006482  pop     r13
0x180006484  pop     r12
0x180006486  pop     rdi
0x180006487  pop     rsi
0x180006488  pop     rbp
0x180006489  retn
0x18000648a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
