# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002be78`
- end: `0x18002c17f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18002a2c0`
- `0x18002a370`
- `0x18002a468`

## callees

- `0x180027f9c`
- `0x18002a214`
- `0x18002b4d4`
- `0x18002be78`
- `0x18002caf8`
- `0x18002cb20`
- `0x18002ccdc`
- `0x18002ccfc`
- `0x18002e2e8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bf9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002bf9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002c13a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002c13a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c0c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002c0c2`

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
0x18002be78  mov     [rsp+arg_10], rbx
0x18002be7d  mov     [rsp+arg_8], edx
0x18002be81  mov     [rsp+arg_0], rcx
0x18002be86  push    rbp
0x18002be87  push    rsi
0x18002be88  push    rdi
0x18002be89  push    r12
0x18002be8b  push    r13
0x18002be8d  push    r14
0x18002be8f  push    r15
0x18002be91  sub     rsp, 40h
0x18002be95  mov     r14, [rsp+78h+arg_38]
0x18002be9d  xor     eax, eax
0x18002be9f  mov     rbx, [rsp+78h+arg_78]
0x18002bea7  xor     ebp, ebp
0x18002bea9  mov     r15d, [rsp+78h+arg_30]
0x18002beb1  mov     r10, rcx
0x18002beb4  mov     rsi, [rsp+78h+lpOutputString]
0x18002bebc  mov     r12, r9
0x18002bebf  mov     r13, r8
0x18002bec2  mov     ecx, r15d
0x18002bec5  mov     [rsi], ax
0x18002bec8  mov     rax, [rsp+78h+arg_60]
0x18002bed0  mov     byte ptr [rax], 0
0x18002bed3  mov     edi, [r14]
0x18002bed6  mov     [rbx+8], edi
0x18002bed9  mov     eax, [r14+4]
0x18002bedd  mov     [rbx+0Ch], eax
0x18002bee0  test    r15d, r15d
0x18002bee3  jz      short loc_18002BF4B
0x18002bee5  sub     ecx, 1
0x18002bee8  jz      short loc_18002BF42
0x18002beea  sub     ecx, 1
0x18002beed  jz      short loc_18002BEFD
0x18002beef  cmp     ecx, 1
0x18002bef2  jnz     short loc_18002BF54
0x18002bef4  mov     ecx, edi; this
0x18002bef6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002befb  jmp     short loc_18002BF52
0x18002befd  test    edi, edi
0x18002beff  js      short loc_18002BF39
0x18002bf01  mov     rax, [rsp+78h+arg_28]
0x18002bf09  mov     edi, 8007029Ch
0x18002bf0e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002bf12  mov     rcx, r10; int
0x18002bf15  mov     [rsp+78h+var_50], rax; __int64
0x18002bf1a  mov     rax, [rsp+78h+arg_20]
0x18002bf22  mov     [rsp+78h+var_58], rax; __int64
0x18002bf27  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002bf2c  mov     ecx, edi; this
0x18002bf2e  mov     [rbx+8], edi
0x18002bf31  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002bf36  mov     [rbx+0Ch], eax
0x18002bf39  mov     ecx, edi; this
0x18002bf3b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002bf40  jmp     short loc_18002BF52
0x18002bf42  mov     ecx, edi; this
0x18002bf44  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002bf49  jmp     short loc_18002BF52
0x18002bf4b  mov     ecx, edi; this
0x18002bf4d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002bf52  mov     ebp, eax
0x18002bf54  mov     eax, [rsp+78h+arg_70]
0x18002bf5b  mov     [rbx+4], eax
0x18002bf5e  mov     [rbx], r15d
0x18002bf61  cmp     dword ptr [r14+8], 1
0x18002bf66  jnz     short loc_18002BF6E
0x18002bf68  or      eax, 8
0x18002bf6b  mov     [rbx+4], eax
0x18002bf6e  mov     eax, 1
0x18002bf73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002bf7b  inc     eax
0x18002bf7d  xor     edi, edi
0x18002bf7f  mov     [rbx+10h], eax
0x18002bf82  mov     rax, [rsp+78h+arg_40]
0x18002bf8a  test    rax, rax
0x18002bf8d  jz      short loc_18002BF94
0x18002bf8f  cmp     [rax], di
0x18002bf92  jnz     short loc_18002BF97
0x18002bf94  mov     rax, rdi
0x18002bf97  mov     [rbx+18h], rax
0x18002bf9b  call    cs:__imp_GetCurrentThreadId
0x18002bfa2  nop     dword ptr [rax+rax+00h]
0x18002bfa7  mov     [rbx+38h], r13
0x18002bfab  xorps   xmm0, xmm0
0x18002bfae  mov     [rbx+20h], eax
0x18002bfb1  mov     eax, [rsp+78h+arg_8]
0x18002bfb8  mov     [rbx+40h], eax
0x18002bfbb  mov     rax, [rsp+78h+arg_20]
0x18002bfc3  mov     [rbx+28h], rax
0x18002bfc7  mov     rax, [rsp+78h+arg_28]
0x18002bfcf  mov     [rbx+88h], rax
0x18002bfd6  mov     rax, [rsp+78h+arg_0]
0x18002bfde  mov     [rbx+90h], rax
0x18002bfe5  xor     eax, eax
0x18002bfe7  mov     [rbx+44h], ebp
0x18002bfea  mov     [rbx+30h], r12
0x18002bfee  mov     [rbx+48h], rdi
0x18002bff2  movups  xmmword ptr [rbx+68h], xmm0
0x18002bff6  mov     [rbx+78h], rax
0x18002bffa  movups  xmmword ptr [rbx+50h], xmm0
0x18002bffe  mov     [rbx+60h], rax
0x18002c002  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002c009  test    rax, rax
0x18002c00c  jz      short loc_18002C015
0x18002c00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c013  jmp     short loc_18002C018
0x18002c015  mov     rax, rdi
0x18002c018  mov     [rbx+80h], rax
0x18002c01f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002c026  test    rax, rax
0x18002c029  jz      short loc_18002C033
0x18002c02b  mov     rcx, rbx
0x18002c02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c033  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002c03a  test    rax, rax
0x18002c03d  jz      short loc_18002C055
0x18002c03f  mov     rdx, [rsp+78h+arg_60]
0x18002c047  mov     r8d, 400h
0x18002c04d  mov     rcx, rbx
0x18002c050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c055  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002c05c  test    rax, rax
0x18002c05f  jz      short loc_18002C069
0x18002c061  mov     rcx, rbx
0x18002c064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c069  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002c070  test    rax, rax
0x18002c073  jz      short loc_18002C083
0x18002c075  test    byte ptr [rbx+4], 2
0x18002c079  jnz     short loc_18002C083
0x18002c07b  mov     rcx, rbx
0x18002c07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c083  cmp     [rbx+8], edi
0x18002c086  jl      short loc_18002C0A4
0x18002c088  cmp     r15d, 3
0x18002c08c  jz      short loc_18002C094
0x18002c08e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002c094  mov     ecx, 8000FFFFh; this
0x18002c099  mov     [rbx+8], ecx
0x18002c09c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002c0a1  mov     [rbx+0Ch], eax
0x18002c0a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002c0ab  jnz     short loc_18002C0D2
0x18002c0ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002c0b4  test    rax, rax
0x18002c0b7  jz      short loc_18002C0C2
0x18002c0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0be  test    al, al
0x18002c0c0  jmp     short loc_18002C0D0
0x18002c0c2  call    cs:__imp_IsDebuggerPresent
0x18002c0c9  nop     dword ptr [rax+rax+00h]
0x18002c0ce  test    eax, eax
0x18002c0d0  jz      short loc_18002C0D8
0x18002c0d2  test    byte ptr [rbx+4], 2
0x18002c0d6  jz      short loc_18002C0FC
0x18002c0d8  mov     rax, cs:g_pfnResultLoggingCallback
0x18002c0df  test    rax, rax
0x18002c0e2  jz      short loc_18002C146
0x18002c0e4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002c0eb  jnz     short loc_18002C146
0x18002c0ed  xor     r8d, r8d
0x18002c0f0  xor     edx, edx
0x18002c0f2  mov     rcx, rbx
0x18002c0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0fa  jmp     short loc_18002C146
0x18002c0fc  mov     rax, cs:g_pfnResultLoggingCallback
0x18002c103  mov     ebp, 800h
0x18002c108  test    rax, rax
0x18002c10b  jz      short loc_18002C124
0x18002c10d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002c114  jnz     short loc_18002C124
0x18002c116  mov     r8d, ebp
0x18002c119  mov     rdx, rsi
0x18002c11c  mov     rcx, rbx
0x18002c11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c124  cmp     [rsi], di
0x18002c127  jnz     short loc_18002C137
0x18002c129  mov     r8, rbx; unsigned __int64
0x18002c12c  mov     rdx, rbp; unsigned __int16 *
0x18002c12f  mov     rcx, rsi; this
0x18002c132  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002c137  mov     rcx, rsi; lpOutputString
0x18002c13a  call    cs:__imp_OutputDebugStringW
0x18002c141  nop     dword ptr [rax+rax+00h]
0x18002c146  test    byte ptr [rbx+4], 4
0x18002c14a  jnz     short loc_18002C155
0x18002c14c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002c153  jz      short loc_18002C166
0x18002c155  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002c15c  test    rax, rax
0x18002c15f  jz      short loc_18002C166
0x18002c161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c166  mov     rbx, [rsp+78h+arg_10]
0x18002c16e  add     rsp, 40h
0x18002c172  pop     r15
0x18002c174  pop     r14
0x18002c176  pop     r13
0x18002c178  pop     r12
0x18002c17a  pop     rdi
0x18002c17b  pop     rsi
0x18002c17c  pop     rbp
0x18002c17d  retn
```
