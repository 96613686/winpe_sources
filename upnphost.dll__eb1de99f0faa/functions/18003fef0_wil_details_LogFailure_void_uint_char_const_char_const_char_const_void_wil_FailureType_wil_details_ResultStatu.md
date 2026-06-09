# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003fef0`
- end: `0x1800401e8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18003be40`
- `0x18003c18c`

## callees

- `0x180039e38`
- `0x18003bd80`
- `0x18003f374`
- `0x18003fef0`
- `0x18004117c`
- `0x1800411a0`
- `0x18004125c`
- `0x180041278`
- `0x180044340`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040013`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040013`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180040132`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180040132`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800401a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800401a4`

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
0x18003fef0  mov     [rsp+arg_10], rbx
0x18003fef5  mov     [rsp+arg_8], edx
0x18003fef9  mov     [rsp+arg_0], rcx
0x18003fefe  push    rbp
0x18003feff  push    rsi
0x18003ff00  push    rdi
0x18003ff01  push    r12
0x18003ff03  push    r13
0x18003ff05  push    r14
0x18003ff07  push    r15
0x18003ff09  sub     rsp, 40h
0x18003ff0d  mov     r14, [rsp+78h+arg_38]
0x18003ff15  xor     eax, eax
0x18003ff17  mov     rbx, [rsp+78h+arg_78]
0x18003ff1f  xor     ebp, ebp
0x18003ff21  mov     r15d, [rsp+78h+arg_30]
0x18003ff29  mov     r10, rcx
0x18003ff2c  mov     rsi, [rsp+78h+lpOutputString]
0x18003ff34  mov     r12, r9
0x18003ff37  mov     r13, r8
0x18003ff3a  mov     ecx, r15d
0x18003ff3d  mov     [rsi], ax
0x18003ff40  mov     rax, [rsp+78h+arg_60]
0x18003ff48  mov     byte ptr [rax], 0
0x18003ff4b  mov     edi, [r14]
0x18003ff4e  mov     [rbx+8], edi
0x18003ff51  mov     eax, [r14+4]
0x18003ff55  mov     [rbx+0Ch], eax
0x18003ff58  test    r15d, r15d
0x18003ff5b  jz      short loc_18003FFC3
0x18003ff5d  sub     ecx, 1
0x18003ff60  jz      short loc_18003FFBA
0x18003ff62  sub     ecx, 1
0x18003ff65  jz      short loc_18003FF75
0x18003ff67  cmp     ecx, 1
0x18003ff6a  jnz     short loc_18003FFCC
0x18003ff6c  mov     ecx, edi; this
0x18003ff6e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003ff73  jmp     short loc_18003FFCA
0x18003ff75  test    edi, edi
0x18003ff77  js      short loc_18003FFB1
0x18003ff79  mov     rax, [rsp+78h+arg_28]
0x18003ff81  mov     edi, 8007029Ch
0x18003ff86  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003ff8a  mov     rcx, r10; int
0x18003ff8d  mov     [rsp+78h+var_50], rax; __int64
0x18003ff92  mov     rax, [rsp+78h+arg_20]
0x18003ff9a  mov     [rsp+78h+var_58], rax; __int64
0x18003ff9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003ffa4  mov     ecx, edi; this
0x18003ffa6  mov     [rbx+8], edi
0x18003ffa9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003ffae  mov     [rbx+0Ch], eax
0x18003ffb1  mov     ecx, edi; this
0x18003ffb3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003ffb8  jmp     short loc_18003FFCA
0x18003ffba  mov     ecx, edi; this
0x18003ffbc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003ffc1  jmp     short loc_18003FFCA
0x18003ffc3  mov     ecx, edi; this
0x18003ffc5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003ffca  mov     ebp, eax
0x18003ffcc  mov     eax, [rsp+78h+arg_70]
0x18003ffd3  mov     [rbx+4], eax
0x18003ffd6  mov     [rbx], r15d
0x18003ffd9  cmp     dword ptr [r14+8], 1
0x18003ffde  jnz     short loc_18003FFE6
0x18003ffe0  or      eax, 8
0x18003ffe3  mov     [rbx+4], eax
0x18003ffe6  mov     eax, 1
0x18003ffeb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003fff3  inc     eax
0x18003fff5  xor     edi, edi
0x18003fff7  mov     [rbx+10h], eax
0x18003fffa  mov     rax, [rsp+78h+arg_40]
0x180040002  test    rax, rax
0x180040005  jz      short loc_18004000C
0x180040007  cmp     [rax], di
0x18004000a  jnz     short loc_18004000F
0x18004000c  mov     rax, rdi
0x18004000f  mov     [rbx+18h], rax
0x180040013  call    cs:__imp_GetCurrentThreadId
0x180040019  mov     [rbx+38h], r13
0x18004001d  xorps   xmm0, xmm0
0x180040020  mov     [rbx+20h], eax
0x180040023  mov     eax, [rsp+78h+arg_8]
0x18004002a  mov     [rbx+40h], eax
0x18004002d  mov     rax, [rsp+78h+arg_20]
0x180040035  mov     [rbx+28h], rax
0x180040039  mov     rax, [rsp+78h+arg_28]
0x180040041  mov     [rbx+88h], rax
0x180040048  mov     rax, [rsp+78h+arg_0]
0x180040050  mov     [rbx+90h], rax
0x180040057  xor     eax, eax
0x180040059  mov     [rbx+44h], ebp
0x18004005c  mov     [rbx+30h], r12
0x180040060  mov     [rbx+48h], rdi
0x180040064  movups  xmmword ptr [rbx+68h], xmm0
0x180040068  mov     [rbx+78h], rax
0x18004006c  movups  xmmword ptr [rbx+50h], xmm0
0x180040070  mov     [rbx+60h], rax
0x180040074  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004007b  test    rax, rax
0x18004007e  jz      short loc_180040087
0x180040080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040085  jmp     short loc_18004008A
0x180040087  mov     rax, rdi
0x18004008a  mov     [rbx+80h], rax
0x180040091  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180040098  test    rax, rax
0x18004009b  jz      short loc_1800400A5
0x18004009d  mov     rcx, rbx
0x1800400a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800400ac  test    rax, rax
0x1800400af  jz      short loc_1800400C7
0x1800400b1  mov     rdx, [rsp+78h+arg_60]
0x1800400b9  mov     r8d, 400h
0x1800400bf  mov     rcx, rbx
0x1800400c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800400ce  test    rax, rax
0x1800400d1  jz      short loc_1800400DB
0x1800400d3  mov     rcx, rbx
0x1800400d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800400e2  test    rax, rax
0x1800400e5  jz      short loc_1800400F5
0x1800400e7  test    byte ptr [rbx+4], 2
0x1800400eb  jnz     short loc_1800400F5
0x1800400ed  mov     rcx, rbx
0x1800400f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400f5  cmp     [rbx+8], edi
0x1800400f8  jl      short loc_180040114
0x1800400fa  cmp     r15d, 3
0x1800400fe  jnz     loc_1800401E2
0x180040104  mov     ecx, 8000FFFFh; this
0x180040109  mov     [rbx+8], ecx
0x18004010c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180040111  mov     [rbx+0Ch], eax
0x180040114  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004011b  jnz     short loc_18004013C
0x18004011d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180040124  test    rax, rax
0x180040127  jz      short loc_180040132
0x180040129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004012e  test    al, al
0x180040130  jmp     short loc_18004013A
0x180040132  call    cs:__imp_IsDebuggerPresent
0x180040138  test    eax, eax
0x18004013a  jz      short loc_180040142
0x18004013c  test    byte ptr [rbx+4], 2
0x180040140  jz      short loc_180040166
0x180040142  mov     rax, cs:g_pfnResultLoggingCallback
0x180040149  test    rax, rax
0x18004014c  jz      short loc_1800401AA
0x18004014e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180040155  jnz     short loc_1800401AA
0x180040157  xor     r8d, r8d
0x18004015a  xor     edx, edx
0x18004015c  mov     rcx, rbx
0x18004015f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040164  jmp     short loc_1800401AA
0x180040166  mov     rax, cs:g_pfnResultLoggingCallback
0x18004016d  mov     ebp, 800h
0x180040172  test    rax, rax
0x180040175  jz      short loc_18004018E
0x180040177  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004017e  jnz     short loc_18004018E
0x180040180  mov     r8d, ebp
0x180040183  mov     rdx, rsi
0x180040186  mov     rcx, rbx
0x180040189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004018e  cmp     [rsi], di
0x180040191  jnz     short loc_1800401A1
0x180040193  mov     r8, rbx; unsigned __int64
0x180040196  mov     rdx, rbp; unsigned __int16 *
0x180040199  mov     rcx, rsi; this
0x18004019c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800401a1  mov     rcx, rsi; lpOutputString
0x1800401a4  call    cs:__imp_OutputDebugStringW
0x1800401aa  test    byte ptr [rbx+4], 4
0x1800401ae  jnz     short loc_1800401B9
0x1800401b0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800401b7  jz      short loc_1800401CA
0x1800401b9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800401c0  test    rax, rax
0x1800401c3  jz      short loc_1800401CA
0x1800401c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401ca  mov     rbx, [rsp+78h+arg_10]
0x1800401d2  add     rsp, 40h
0x1800401d6  pop     r15
0x1800401d8  pop     r14
0x1800401da  pop     r13
0x1800401dc  pop     r12
0x1800401de  pop     rdi
0x1800401df  pop     rsi
0x1800401e0  pop     rbp
0x1800401e1  retn
0x1800401e2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
