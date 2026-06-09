# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004cc0`
- end: `0x140004fb9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000347c`

## callees

- `0x140002ec0`
- `0x140004354`
- `0x140004afc`
- `0x140004cc0`
- `0x1400051fc`
- `0x140005220`
- `0x140005234`
- `0x140005250`
- `0x14000627c`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004de3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f74`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f74`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f02`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f02`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x140004cc0  mov     [rsp+arg_10], rbx
0x140004cc5  mov     [rsp+arg_8], edx
0x140004cc9  mov     [rsp+arg_0], rcx
0x140004cce  push    rbp
0x140004ccf  push    rsi
0x140004cd0  push    rdi
0x140004cd1  push    r12
0x140004cd3  push    r13
0x140004cd5  push    r14
0x140004cd7  push    r15
0x140004cd9  sub     rsp, 40h
0x140004cdd  mov     r12, r9
0x140004ce0  mov     r13, r8
0x140004ce3  mov     r10, rcx
0x140004ce6  xor     eax, eax
0x140004ce8  mov     rsi, [rsp+78h+lpOutputString]
0x140004cf0  mov     [rsi], ax
0x140004cf3  mov     rax, [rsp+78h+arg_60]
0x140004cfb  mov     byte ptr [rax], 0
0x140004cfe  mov     r14, [rsp+78h+arg_38]
0x140004d06  mov     edi, [r14]
0x140004d09  mov     rbx, [rsp+78h+arg_78]
0x140004d11  mov     [rbx+8], edi
0x140004d14  mov     eax, [r14+4]
0x140004d18  mov     [rbx+0Ch], eax
0x140004d1b  xor     ebp, ebp
0x140004d1d  mov     r15d, [rsp+78h+arg_30]
0x140004d25  mov     ecx, r15d
0x140004d28  test    r15d, r15d
0x140004d2b  jz      short loc_140004D93
0x140004d2d  sub     ecx, 1
0x140004d30  jz      short loc_140004D8A
0x140004d32  sub     ecx, 1
0x140004d35  jz      short loc_140004D45
0x140004d37  cmp     ecx, 1
0x140004d3a  jnz     short loc_140004D9C
0x140004d3c  mov     ecx, edi; this
0x140004d3e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004d43  jmp     short loc_140004D9A
0x140004d45  test    edi, edi
0x140004d47  js      short loc_140004D81
0x140004d49  mov     edi, 8007029Ch
0x140004d4e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004d52  mov     rax, [rsp+78h+arg_28]
0x140004d5a  mov     [rsp+78h+var_50], rax; __int64
0x140004d5f  mov     rax, [rsp+78h+arg_20]
0x140004d67  mov     [rsp+78h+var_58], rax; __int64
0x140004d6c  mov     rcx, r10; int
0x140004d6f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004d74  mov     [rbx+8], edi
0x140004d77  mov     ecx, edi; this
0x140004d79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004d7e  mov     [rbx+0Ch], eax
0x140004d81  mov     ecx, edi; this
0x140004d83  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004d88  jmp     short loc_140004D9A
0x140004d8a  mov     ecx, edi; this
0x140004d8c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004d91  jmp     short loc_140004D9A
0x140004d93  mov     ecx, edi; this
0x140004d95  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004d9a  mov     ebp, eax
0x140004d9c  mov     [rbx], r15d
0x140004d9f  mov     eax, [rsp+78h+arg_70]
0x140004da6  mov     [rbx+4], eax
0x140004da9  cmp     dword ptr [r14+8], 1
0x140004dae  jnz     short loc_140004DB6
0x140004db0  or      eax, 8
0x140004db3  mov     [rbx+4], eax
0x140004db6  mov     eax, 1
0x140004dbb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004dc3  inc     eax
0x140004dc5  mov     [rbx+10h], eax
0x140004dc8  mov     rax, [rsp+78h+arg_40]
0x140004dd0  xor     edi, edi
0x140004dd2  test    rax, rax
0x140004dd5  jz      short loc_140004DDC
0x140004dd7  cmp     [rax], di
0x140004dda  jnz     short loc_140004DDF
0x140004ddc  mov     rax, rdi
0x140004ddf  mov     [rbx+18h], rax
0x140004de3  call    cs:__imp_GetCurrentThreadId
0x140004de9  mov     [rbx+20h], eax
0x140004dec  mov     [rbx+38h], r13
0x140004df0  mov     eax, [rsp+78h+arg_8]
0x140004df7  mov     [rbx+40h], eax
0x140004dfa  mov     [rbx+44h], ebp
0x140004dfd  mov     rax, [rsp+78h+arg_20]
0x140004e05  mov     [rbx+28h], rax
0x140004e09  mov     [rbx+30h], r12
0x140004e0d  mov     rax, [rsp+78h+arg_28]
0x140004e15  mov     [rbx+88h], rax
0x140004e1c  mov     rax, [rsp+78h+arg_0]
0x140004e24  mov     [rbx+90h], rax
0x140004e2b  mov     [rbx+48h], rdi
0x140004e2f  xorps   xmm0, xmm0
0x140004e32  xor     eax, eax
0x140004e34  movups  xmmword ptr [rbx+68h], xmm0
0x140004e38  mov     [rbx+78h], rax
0x140004e3c  movups  xmmword ptr [rbx+50h], xmm0
0x140004e40  mov     [rbx+60h], rax
0x140004e44  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004e4b  test    rax, rax
0x140004e4e  jz      short loc_140004E57
0x140004e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e55  jmp     short loc_140004E5A
0x140004e57  mov     rax, rdi
0x140004e5a  mov     [rbx+80h], rax
0x140004e61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004e68  test    rax, rax
0x140004e6b  jz      short loc_140004E75
0x140004e6d  mov     rcx, rbx
0x140004e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e75  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004e7c  test    rax, rax
0x140004e7f  jz      short loc_140004E97
0x140004e81  mov     r8d, 400h
0x140004e87  mov     rdx, [rsp+78h+arg_60]
0x140004e8f  mov     rcx, rbx
0x140004e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004e9e  test    rax, rax
0x140004ea1  jz      short loc_140004EAB
0x140004ea3  mov     rcx, rbx
0x140004ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004eab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004eb2  test    rax, rax
0x140004eb5  jz      short loc_140004EC5
0x140004eb7  test    byte ptr [rbx+4], 2
0x140004ebb  jnz     short loc_140004EC5
0x140004ebd  mov     rcx, rbx
0x140004ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec5  cmp     [rbx+8], edi
0x140004ec8  jl      short loc_140004EE4
0x140004eca  cmp     r15d, 3
0x140004ece  jnz     loc_140004FB3
0x140004ed4  mov     ecx, 8000FFFFh; this
0x140004ed9  mov     [rbx+8], ecx
0x140004edc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004ee1  mov     [rbx+0Ch], eax
0x140004ee4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004eeb  jnz     short loc_140004F0C
0x140004eed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004ef4  test    rax, rax
0x140004ef7  jz      short loc_140004F02
0x140004ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004efe  test    al, al
0x140004f00  jmp     short loc_140004F0A
0x140004f02  call    cs:__imp_IsDebuggerPresent
0x140004f08  test    eax, eax
0x140004f0a  jz      short loc_140004F12
0x140004f0c  test    byte ptr [rbx+4], 2
0x140004f10  jz      short loc_140004F36
0x140004f12  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f19  test    rax, rax
0x140004f1c  jz      short loc_140004F7A
0x140004f1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004f25  jnz     short loc_140004F7A
0x140004f27  xor     r8d, r8d
0x140004f2a  xor     edx, edx
0x140004f2c  mov     rcx, rbx
0x140004f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f34  jmp     short loc_140004F7A
0x140004f36  mov     ebp, 800h
0x140004f3b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f42  test    rax, rax
0x140004f45  jz      short loc_140004F5E
0x140004f47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004f4e  jnz     short loc_140004F5E
0x140004f50  mov     r8d, ebp
0x140004f53  mov     rdx, rsi
0x140004f56  mov     rcx, rbx
0x140004f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f5e  cmp     [rsi], di
0x140004f61  jnz     short loc_140004F71
0x140004f63  mov     r8, rbx; unsigned __int64
0x140004f66  mov     rdx, rbp; unsigned __int16 *
0x140004f69  mov     rcx, rsi; this
0x140004f6c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004f71  mov     rcx, rsi; lpOutputString
0x140004f74  call    cs:__imp_OutputDebugStringW
0x140004f7a  test    byte ptr [rbx+4], 4
0x140004f7e  jnz     short loc_140004F89
0x140004f80  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004f87  jz      short loc_140004F9B
0x140004f89  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004f90  test    rax, rax
0x140004f93  jz      short loc_140004F9B
0x140004f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f9a  nop
0x140004f9b  mov     rbx, [rsp+78h+arg_10]
0x140004fa3  add     rsp, 40h
0x140004fa7  pop     r15
0x140004fa9  pop     r14
0x140004fab  pop     r13
0x140004fad  pop     r12
0x140004faf  pop     rdi
0x140004fb0  pop     rsi
0x140004fb1  pop     rbp
0x140004fb2  retn
0x140004fb3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
