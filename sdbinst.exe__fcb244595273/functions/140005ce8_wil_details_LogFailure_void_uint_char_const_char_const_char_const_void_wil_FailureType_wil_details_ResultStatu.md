# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005ce8`
- end: `0x140005fe1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002de0`

## callees

- `0x140002824`
- `0x140004324`
- `0x1400054a4`
- `0x140005ce8`
- `0x14000660c`
- `0x140006630`
- `0x140006644`
- `0x140006660`
- `0x140007d54`
- `0x14002f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005e0b`
- `KERNEL32!GetCurrentThreadId` at `0x140005e0b`
- `KERNEL32!OutputDebugStringW` at `0x140005f9c`
- `KERNEL32!OutputDebugStringW` at `0x140005f9c`
- `KERNEL32!IsDebuggerPresent` at `0x140005f2a`
- `KERNEL32!IsDebuggerPresent` at `0x140005f2a`

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
0x140005ce8  mov     [rsp+arg_10], rbx
0x140005ced  mov     [rsp+arg_8], edx
0x140005cf1  mov     [rsp+arg_0], rcx
0x140005cf6  push    rbp
0x140005cf7  push    rsi
0x140005cf8  push    rdi
0x140005cf9  push    r12
0x140005cfb  push    r13
0x140005cfd  push    r14
0x140005cff  push    r15
0x140005d01  sub     rsp, 40h
0x140005d05  mov     r12, r9
0x140005d08  mov     r13, r8
0x140005d0b  mov     r10, rcx
0x140005d0e  xor     eax, eax
0x140005d10  mov     rsi, [rsp+78h+lpOutputString]
0x140005d18  mov     [rsi], ax
0x140005d1b  mov     rax, [rsp+78h+arg_60]
0x140005d23  mov     byte ptr [rax], 0
0x140005d26  mov     r14, [rsp+78h+arg_38]
0x140005d2e  mov     edi, [r14]
0x140005d31  mov     rbx, [rsp+78h+arg_78]
0x140005d39  mov     [rbx+8], edi
0x140005d3c  mov     eax, [r14+4]
0x140005d40  mov     [rbx+0Ch], eax
0x140005d43  xor     ebp, ebp
0x140005d45  mov     r15d, [rsp+78h+arg_30]
0x140005d4d  mov     ecx, r15d
0x140005d50  test    r15d, r15d
0x140005d53  jz      short loc_140005DBB
0x140005d55  sub     ecx, 1
0x140005d58  jz      short loc_140005DB2
0x140005d5a  sub     ecx, 1
0x140005d5d  jz      short loc_140005D6D
0x140005d5f  cmp     ecx, 1
0x140005d62  jnz     short loc_140005DC4
0x140005d64  mov     ecx, edi; this
0x140005d66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005d6b  jmp     short loc_140005DC2
0x140005d6d  test    edi, edi
0x140005d6f  js      short loc_140005DA9
0x140005d71  mov     edi, 8007029Ch
0x140005d76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140005d7a  mov     rax, [rsp+78h+arg_28]
0x140005d82  mov     [rsp+78h+var_50], rax; __int64
0x140005d87  mov     rax, [rsp+78h+arg_20]
0x140005d8f  mov     [rsp+78h+var_58], rax; __int64
0x140005d94  mov     rcx, r10; int
0x140005d97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005d9c  mov     [rbx+8], edi
0x140005d9f  mov     ecx, edi; this
0x140005da1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005da6  mov     [rbx+0Ch], eax
0x140005da9  mov     ecx, edi; this
0x140005dab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140005db0  jmp     short loc_140005DC2
0x140005db2  mov     ecx, edi; this
0x140005db4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005db9  jmp     short loc_140005DC2
0x140005dbb  mov     ecx, edi; this
0x140005dbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005dc2  mov     ebp, eax
0x140005dc4  mov     [rbx], r15d
0x140005dc7  mov     eax, [rsp+78h+arg_70]
0x140005dce  mov     [rbx+4], eax
0x140005dd1  cmp     dword ptr [r14+8], 1
0x140005dd6  jnz     short loc_140005DDE
0x140005dd8  or      eax, 8
0x140005ddb  mov     [rbx+4], eax
0x140005dde  mov     eax, 1
0x140005de3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005deb  inc     eax
0x140005ded  mov     [rbx+10h], eax
0x140005df0  mov     rax, [rsp+78h+arg_40]
0x140005df8  xor     edi, edi
0x140005dfa  test    rax, rax
0x140005dfd  jz      short loc_140005E04
0x140005dff  cmp     [rax], di
0x140005e02  jnz     short loc_140005E07
0x140005e04  mov     rax, rdi
0x140005e07  mov     [rbx+18h], rax
0x140005e0b  call    cs:__imp_GetCurrentThreadId
0x140005e11  mov     [rbx+20h], eax
0x140005e14  mov     [rbx+38h], r13
0x140005e18  mov     eax, [rsp+78h+arg_8]
0x140005e1f  mov     [rbx+40h], eax
0x140005e22  mov     [rbx+44h], ebp
0x140005e25  mov     rax, [rsp+78h+arg_20]
0x140005e2d  mov     [rbx+28h], rax
0x140005e31  mov     [rbx+30h], r12
0x140005e35  mov     rax, [rsp+78h+arg_28]
0x140005e3d  mov     [rbx+88h], rax
0x140005e44  mov     rax, [rsp+78h+arg_0]
0x140005e4c  mov     [rbx+90h], rax
0x140005e53  mov     [rbx+48h], rdi
0x140005e57  xorps   xmm0, xmm0
0x140005e5a  xor     eax, eax
0x140005e5c  movups  xmmword ptr [rbx+68h], xmm0
0x140005e60  mov     [rbx+78h], rax
0x140005e64  movups  xmmword ptr [rbx+50h], xmm0
0x140005e68  mov     [rbx+60h], rax
0x140005e6c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005e73  test    rax, rax
0x140005e76  jz      short loc_140005E7F
0x140005e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e7d  jmp     short loc_140005E82
0x140005e7f  mov     rax, rdi
0x140005e82  mov     [rbx+80h], rax
0x140005e89  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005e90  test    rax, rax
0x140005e93  jz      short loc_140005E9D
0x140005e95  mov     rcx, rbx
0x140005e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e9d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005ea4  test    rax, rax
0x140005ea7  jz      short loc_140005EBF
0x140005ea9  mov     r8d, 400h
0x140005eaf  mov     rdx, [rsp+78h+arg_60]
0x140005eb7  mov     rcx, rbx
0x140005eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ebf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005ec6  test    rax, rax
0x140005ec9  jz      short loc_140005ED3
0x140005ecb  mov     rcx, rbx
0x140005ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ed3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005eda  test    rax, rax
0x140005edd  jz      short loc_140005EED
0x140005edf  test    byte ptr [rbx+4], 2
0x140005ee3  jnz     short loc_140005EED
0x140005ee5  mov     rcx, rbx
0x140005ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eed  cmp     [rbx+8], edi
0x140005ef0  jl      short loc_140005F0C
0x140005ef2  cmp     r15d, 3
0x140005ef6  jnz     loc_140005FDB
0x140005efc  mov     ecx, 8000FFFFh; this
0x140005f01  mov     [rbx+8], ecx
0x140005f04  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005f09  mov     [rbx+0Ch], eax
0x140005f0c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005f13  jnz     short loc_140005F34
0x140005f15  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005f1c  test    rax, rax
0x140005f1f  jz      short loc_140005F2A
0x140005f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f26  test    al, al
0x140005f28  jmp     short loc_140005F32
0x140005f2a  call    cs:__imp_IsDebuggerPresent
0x140005f30  test    eax, eax
0x140005f32  jz      short loc_140005F3A
0x140005f34  test    byte ptr [rbx+4], 2
0x140005f38  jz      short loc_140005F5E
0x140005f3a  mov     rax, cs:g_pfnResultLoggingCallback
0x140005f41  test    rax, rax
0x140005f44  jz      short loc_140005FA2
0x140005f46  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005f4d  jnz     short loc_140005FA2
0x140005f4f  xor     r8d, r8d
0x140005f52  xor     edx, edx
0x140005f54  mov     rcx, rbx
0x140005f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f5c  jmp     short loc_140005FA2
0x140005f5e  mov     ebp, 800h
0x140005f63  mov     rax, cs:g_pfnResultLoggingCallback
0x140005f6a  test    rax, rax
0x140005f6d  jz      short loc_140005F86
0x140005f6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005f76  jnz     short loc_140005F86
0x140005f78  mov     r8d, ebp
0x140005f7b  mov     rdx, rsi
0x140005f7e  mov     rcx, rbx
0x140005f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f86  cmp     [rsi], di
0x140005f89  jnz     short loc_140005F99
0x140005f8b  mov     r8, rbx; unsigned __int64
0x140005f8e  mov     rdx, rbp; unsigned __int16 *
0x140005f91  mov     rcx, rsi; this
0x140005f94  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005f99  mov     rcx, rsi; lpOutputString
0x140005f9c  call    cs:__imp_OutputDebugStringW
0x140005fa2  test    byte ptr [rbx+4], 4
0x140005fa6  jnz     short loc_140005FB1
0x140005fa8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005faf  jz      short loc_140005FC3
0x140005fb1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005fb8  test    rax, rax
0x140005fbb  jz      short loc_140005FC3
0x140005fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fc2  nop
0x140005fc3  mov     rbx, [rsp+78h+arg_10]
0x140005fcb  add     rsp, 40h
0x140005fcf  pop     r15
0x140005fd1  pop     r14
0x140005fd3  pop     r13
0x140005fd5  pop     r12
0x140005fd7  pop     rdi
0x140005fd8  pop     rsi
0x140005fd9  pop     rbp
0x140005fda  retn
0x140005fdb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
