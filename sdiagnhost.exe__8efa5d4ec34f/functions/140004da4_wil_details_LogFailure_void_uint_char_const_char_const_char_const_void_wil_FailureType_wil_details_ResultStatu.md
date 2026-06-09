# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004da4`
- end: `0x1400050a5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003610`

## callees

- `0x140003030`
- `0x140004424`
- `0x140004be0`
- `0x140004da4`
- `0x140005304`
- `0x140005320`
- `0x140005334`
- `0x140005350`
- `0x140006e2c`
- `0x140008010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140004fee`
- `KERNEL32!IsDebuggerPresent` at `0x140004fee`
- `KERNEL32!OutputDebugStringW` at `0x140005060`
- `KERNEL32!OutputDebugStringW` at `0x140005060`
- `KERNEL32!GetCurrentThreadId` at `0x140004ecf`
- `KERNEL32!GetCurrentThreadId` at `0x140004ecf`

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
  wil::details *v26; // [rsp+30h] [rbp-58h]

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
0x140004da4  mov     rax, rsp
0x140004da7  mov     [rax+10h], edx
0x140004daa  mov     [rax+8], rcx
0x140004dae  push    rbp
0x140004daf  push    rsi
0x140004db0  push    rdi
0x140004db1  push    r12
0x140004db3  push    r13
0x140004db5  push    r14
0x140004db7  push    r15
0x140004db9  sub     rsp, 50h
0x140004dbd  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x140004dc5  mov     [rax+18h], rbx
0x140004dc9  mov     r12, r9
0x140004dcc  mov     r13, r8
0x140004dcf  mov     r10, rcx
0x140004dd2  xor     eax, eax
0x140004dd4  mov     rsi, [rsp+88h+lpOutputString]
0x140004ddc  mov     [rsi], ax
0x140004ddf  mov     rax, [rsp+88h+arg_60]
0x140004de7  mov     byte ptr [rax], 0
0x140004dea  mov     r14, [rsp+88h+arg_38]
0x140004df2  mov     edi, [r14]
0x140004df5  mov     rbx, [rsp+88h+arg_78]
0x140004dfd  mov     [rbx+8], edi
0x140004e00  mov     eax, [r14+4]
0x140004e04  mov     [rbx+0Ch], eax
0x140004e07  xor     ebp, ebp
0x140004e09  mov     r15d, [rsp+88h+arg_30]
0x140004e11  mov     ecx, r15d
0x140004e14  test    r15d, r15d
0x140004e17  jz      short loc_140004E7F
0x140004e19  sub     ecx, 1
0x140004e1c  jz      short loc_140004E76
0x140004e1e  sub     ecx, 1
0x140004e21  jz      short loc_140004E31
0x140004e23  cmp     ecx, 1
0x140004e26  jnz     short loc_140004E88
0x140004e28  mov     ecx, edi; this
0x140004e2a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004e2f  jmp     short loc_140004E86
0x140004e31  test    edi, edi
0x140004e33  js      short loc_140004E6D
0x140004e35  mov     edi, 8007029Ch
0x140004e3a  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x140004e3e  mov     rax, [rsp+88h+arg_28]
0x140004e46  mov     [rsp+88h+var_60], rax; __int64
0x140004e4b  mov     rax, [rsp+88h+arg_20]
0x140004e53  mov     [rsp+88h+var_68], rax; __int64
0x140004e58  mov     rcx, r10; int
0x140004e5b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004e60  mov     [rbx+8], edi
0x140004e63  mov     ecx, edi; this
0x140004e65  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004e6a  mov     [rbx+0Ch], eax
0x140004e6d  mov     ecx, edi; this
0x140004e6f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004e74  jmp     short loc_140004E86
0x140004e76  mov     ecx, edi; this
0x140004e78  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004e7d  jmp     short loc_140004E86
0x140004e7f  mov     ecx, edi; this
0x140004e81  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004e86  mov     ebp, eax
0x140004e88  mov     [rbx], r15d
0x140004e8b  mov     eax, [rsp+88h+arg_70]
0x140004e92  mov     [rbx+4], eax
0x140004e95  cmp     dword ptr [r14+8], 1
0x140004e9a  jnz     short loc_140004EA2
0x140004e9c  or      eax, 8
0x140004e9f  mov     [rbx+4], eax
0x140004ea2  mov     eax, 1
0x140004ea7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004eaf  inc     eax
0x140004eb1  mov     [rbx+10h], eax
0x140004eb4  mov     rax, [rsp+88h+arg_40]
0x140004ebc  xor     edi, edi
0x140004ebe  test    rax, rax
0x140004ec1  jz      short loc_140004EC8
0x140004ec3  cmp     [rax], di
0x140004ec6  jnz     short loc_140004ECB
0x140004ec8  mov     rax, rdi
0x140004ecb  mov     [rbx+18h], rax
0x140004ecf  call    cs:__imp_GetCurrentThreadId
0x140004ed5  mov     [rbx+20h], eax
0x140004ed8  mov     [rbx+38h], r13
0x140004edc  mov     eax, [rsp+88h+arg_8]
0x140004ee3  mov     [rbx+40h], eax
0x140004ee6  mov     [rbx+44h], ebp
0x140004ee9  mov     rax, [rsp+88h+arg_20]
0x140004ef1  mov     [rbx+28h], rax
0x140004ef5  mov     [rbx+30h], r12
0x140004ef9  mov     rax, [rsp+88h+arg_28]
0x140004f01  mov     [rbx+88h], rax
0x140004f08  mov     rax, [rsp+88h+arg_0]
0x140004f10  mov     [rbx+90h], rax
0x140004f17  mov     [rbx+48h], rdi
0x140004f1b  xorps   xmm0, xmm0
0x140004f1e  xor     eax, eax
0x140004f20  movups  xmmword ptr [rbx+68h], xmm0
0x140004f24  mov     [rbx+78h], rax
0x140004f28  movups  xmmword ptr [rbx+50h], xmm0
0x140004f2c  mov     [rbx+60h], rax
0x140004f30  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004f37  test    rax, rax
0x140004f3a  jz      short loc_140004F43
0x140004f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f41  jmp     short loc_140004F46
0x140004f43  mov     rax, rdi
0x140004f46  mov     [rbx+80h], rax
0x140004f4d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004f54  test    rax, rax
0x140004f57  jz      short loc_140004F61
0x140004f59  mov     rcx, rbx
0x140004f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f61  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004f68  test    rax, rax
0x140004f6b  jz      short loc_140004F83
0x140004f6d  mov     r8d, 400h
0x140004f73  mov     rdx, [rsp+88h+arg_60]
0x140004f7b  mov     rcx, rbx
0x140004f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f83  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004f8a  test    rax, rax
0x140004f8d  jz      short loc_140004F97
0x140004f8f  mov     rcx, rbx
0x140004f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f97  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004f9e  test    rax, rax
0x140004fa1  jz      short loc_140004FB1
0x140004fa3  test    byte ptr [rbx+4], 2
0x140004fa7  jnz     short loc_140004FB1
0x140004fa9  mov     rcx, rbx
0x140004fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fb1  cmp     [rbx+8], edi
0x140004fb4  jl      short loc_140004FD0
0x140004fb6  cmp     r15d, 3
0x140004fba  jnz     loc_14000509F
0x140004fc0  mov     ecx, 8000FFFFh; this
0x140004fc5  mov     [rbx+8], ecx
0x140004fc8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004fcd  mov     [rbx+0Ch], eax
0x140004fd0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004fd7  jnz     short loc_140004FF8
0x140004fd9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004fe0  test    rax, rax
0x140004fe3  jz      short loc_140004FEE
0x140004fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fea  test    al, al
0x140004fec  jmp     short loc_140004FF6
0x140004fee  call    cs:__imp_IsDebuggerPresent
0x140004ff4  test    eax, eax
0x140004ff6  jz      short loc_140004FFE
0x140004ff8  test    byte ptr [rbx+4], 2
0x140004ffc  jz      short loc_140005022
0x140004ffe  mov     rax, cs:g_pfnResultLoggingCallback
0x140005005  test    rax, rax
0x140005008  jz      short loc_140005066
0x14000500a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005011  jnz     short loc_140005066
0x140005013  xor     r8d, r8d
0x140005016  xor     edx, edx
0x140005018  mov     rcx, rbx
0x14000501b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005020  jmp     short loc_140005066
0x140005022  mov     ebp, 800h
0x140005027  mov     rax, cs:g_pfnResultLoggingCallback
0x14000502e  test    rax, rax
0x140005031  jz      short loc_14000504A
0x140005033  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000503a  jnz     short loc_14000504A
0x14000503c  mov     r8d, ebp
0x14000503f  mov     rdx, rsi
0x140005042  mov     rcx, rbx
0x140005045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000504a  cmp     [rsi], di
0x14000504d  jnz     short loc_14000505D
0x14000504f  mov     r8, rbx; unsigned __int64
0x140005052  mov     rdx, rbp; unsigned __int16 *
0x140005055  mov     rcx, rsi; this
0x140005058  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000505d  mov     rcx, rsi; lpOutputString
0x140005060  call    cs:__imp_OutputDebugStringW
0x140005066  test    byte ptr [rbx+4], 4
0x14000506a  jnz     short loc_140005075
0x14000506c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005073  jz      short loc_140005087
0x140005075  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000507c  test    rax, rax
0x14000507f  jz      short loc_140005087
0x140005081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005086  nop
0x140005087  mov     rbx, [rsp+88h+arg_10]
0x14000508f  add     rsp, 50h
0x140005093  pop     r15
0x140005095  pop     r14
0x140005097  pop     r13
0x140005099  pop     r12
0x14000509b  pop     rdi
0x14000509c  pop     rsi
0x14000509d  pop     rbp
0x14000509e  retn
0x14000509f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
