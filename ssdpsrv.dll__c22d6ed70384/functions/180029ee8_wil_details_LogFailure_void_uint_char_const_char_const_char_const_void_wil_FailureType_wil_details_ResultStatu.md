# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180029ee8`
- end: `0x18002a1dc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18002849c`
- `0x18002854c`
- `0x180028640`

## callees

- `0x180026200`
- `0x1800283f0`
- `0x180029604`
- `0x180029ee8`
- `0x18002ab18`
- `0x18002ab40`
- `0x18002acec`
- `0x18002ad08`
- `0x18002c348`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a00b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a00b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002a19e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002a19e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002a12c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002a12c`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180029ee8  mov     [rsp+arg_10], rbx
0x180029eed  mov     [rsp+arg_8], edx
0x180029ef1  mov     [rsp+arg_0], rcx
0x180029ef6  push    rbp
0x180029ef7  push    rsi
0x180029ef8  push    rdi
0x180029ef9  push    r12
0x180029efb  push    r13
0x180029efd  push    r14
0x180029eff  push    r15
0x180029f01  sub     rsp, 40h
0x180029f05  mov     r14, [rsp+78h+arg_38]
0x180029f0d  xor     eax, eax
0x180029f0f  mov     rbx, [rsp+78h+arg_78]
0x180029f17  xor     ebp, ebp
0x180029f19  mov     r15d, [rsp+78h+arg_30]
0x180029f21  mov     r10, rcx
0x180029f24  mov     rsi, [rsp+78h+lpOutputString]
0x180029f2c  mov     r12, r9
0x180029f2f  mov     r13, r8
0x180029f32  mov     ecx, r15d
0x180029f35  mov     [rsi], ax
0x180029f38  mov     rax, [rsp+78h+arg_60]
0x180029f40  mov     byte ptr [rax], 0
0x180029f43  mov     edi, [r14]
0x180029f46  mov     [rbx+8], edi
0x180029f49  mov     eax, [r14+4]
0x180029f4d  mov     [rbx+0Ch], eax
0x180029f50  test    r15d, r15d
0x180029f53  jz      short loc_180029FBB
0x180029f55  sub     ecx, 1
0x180029f58  jz      short loc_180029FB2
0x180029f5a  sub     ecx, 1
0x180029f5d  jz      short loc_180029F6D
0x180029f5f  cmp     ecx, 1
0x180029f62  jnz     short loc_180029FC4
0x180029f64  mov     ecx, edi; this
0x180029f66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180029f6b  jmp     short loc_180029FC2
0x180029f6d  test    edi, edi
0x180029f6f  js      short loc_180029FA9
0x180029f71  mov     rax, [rsp+78h+arg_28]
0x180029f79  mov     edi, 8007029Ch
0x180029f7e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180029f82  mov     rcx, r10; int
0x180029f85  mov     [rsp+78h+var_50], rax; __int64
0x180029f8a  mov     rax, [rsp+78h+arg_20]
0x180029f92  mov     [rsp+78h+var_58], rax; __int64
0x180029f97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180029f9c  mov     ecx, edi; this
0x180029f9e  mov     [rbx+8], edi
0x180029fa1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180029fa6  mov     [rbx+0Ch], eax
0x180029fa9  mov     ecx, edi; this
0x180029fab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180029fb0  jmp     short loc_180029FC2
0x180029fb2  mov     ecx, edi; this
0x180029fb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180029fb9  jmp     short loc_180029FC2
0x180029fbb  mov     ecx, edi; this
0x180029fbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180029fc2  mov     ebp, eax
0x180029fc4  mov     eax, [rsp+78h+arg_70]
0x180029fcb  mov     [rbx+4], eax
0x180029fce  mov     [rbx], r15d
0x180029fd1  cmp     dword ptr [r14+8], 1
0x180029fd6  jnz     short loc_180029FDE
0x180029fd8  or      eax, 8
0x180029fdb  mov     [rbx+4], eax
0x180029fde  mov     eax, 1
0x180029fe3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180029feb  inc     eax
0x180029fed  xor     edi, edi
0x180029fef  mov     [rbx+10h], eax
0x180029ff2  mov     rax, [rsp+78h+arg_40]
0x180029ffa  test    rax, rax
0x180029ffd  jz      short loc_18002A004
0x180029fff  cmp     [rax], di
0x18002a002  jnz     short loc_18002A007
0x18002a004  mov     rax, rdi
0x18002a007  mov     [rbx+18h], rax
0x18002a00b  call    cs:__imp_GetCurrentThreadId
0x18002a011  mov     [rbx+38h], r13
0x18002a015  xorps   xmm0, xmm0
0x18002a018  mov     [rbx+20h], eax
0x18002a01b  mov     eax, [rsp+78h+arg_8]
0x18002a022  mov     [rbx+40h], eax
0x18002a025  mov     rax, [rsp+78h+arg_20]
0x18002a02d  mov     [rbx+28h], rax
0x18002a031  mov     rax, [rsp+78h+arg_28]
0x18002a039  mov     [rbx+88h], rax
0x18002a040  mov     rax, [rsp+78h+arg_0]
0x18002a048  mov     [rbx+90h], rax
0x18002a04f  xor     eax, eax
0x18002a051  mov     [rbx+44h], ebp
0x18002a054  mov     [rbx+30h], r12
0x18002a058  mov     [rbx+48h], rdi
0x18002a05c  movups  xmmword ptr [rbx+68h], xmm0
0x18002a060  mov     [rbx+78h], rax
0x18002a064  movups  xmmword ptr [rbx+50h], xmm0
0x18002a068  mov     [rbx+60h], rax
0x18002a06c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002a073  test    rax, rax
0x18002a076  jz      short loc_18002A07F
0x18002a078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a07d  jmp     short loc_18002A082
0x18002a07f  mov     rax, rdi
0x18002a082  mov     [rbx+80h], rax
0x18002a089  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002a090  test    rax, rax
0x18002a093  jz      short loc_18002A09D
0x18002a095  mov     rcx, rbx
0x18002a098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a09d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002a0a4  test    rax, rax
0x18002a0a7  jz      short loc_18002A0BF
0x18002a0a9  mov     rdx, [rsp+78h+arg_60]
0x18002a0b1  mov     r8d, 400h
0x18002a0b7  mov     rcx, rbx
0x18002a0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002a0c6  test    rax, rax
0x18002a0c9  jz      short loc_18002A0D3
0x18002a0cb  mov     rcx, rbx
0x18002a0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002a0da  test    rax, rax
0x18002a0dd  jz      short loc_18002A0ED
0x18002a0df  test    byte ptr [rbx+4], 2
0x18002a0e3  jnz     short loc_18002A0ED
0x18002a0e5  mov     rcx, rbx
0x18002a0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0ed  cmp     [rbx+8], edi
0x18002a0f0  jl      short loc_18002A10E
0x18002a0f2  cmp     r15d, 3
0x18002a0f6  jz      short loc_18002A0FE
0x18002a0f8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002a0fe  mov     ecx, 8000FFFFh; this
0x18002a103  mov     [rbx+8], ecx
0x18002a106  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002a10b  mov     [rbx+0Ch], eax
0x18002a10e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002a115  jnz     short loc_18002A136
0x18002a117  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002a11e  test    rax, rax
0x18002a121  jz      short loc_18002A12C
0x18002a123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a128  test    al, al
0x18002a12a  jmp     short loc_18002A134
0x18002a12c  call    cs:__imp_IsDebuggerPresent
0x18002a132  test    eax, eax
0x18002a134  jz      short loc_18002A13C
0x18002a136  test    byte ptr [rbx+4], 2
0x18002a13a  jz      short loc_18002A160
0x18002a13c  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a143  test    rax, rax
0x18002a146  jz      short loc_18002A1A4
0x18002a148  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002a14f  jnz     short loc_18002A1A4
0x18002a151  xor     r8d, r8d
0x18002a154  xor     edx, edx
0x18002a156  mov     rcx, rbx
0x18002a159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a15e  jmp     short loc_18002A1A4
0x18002a160  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a167  mov     ebp, 800h
0x18002a16c  test    rax, rax
0x18002a16f  jz      short loc_18002A188
0x18002a171  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002a178  jnz     short loc_18002A188
0x18002a17a  mov     r8d, ebp
0x18002a17d  mov     rdx, rsi
0x18002a180  mov     rcx, rbx
0x18002a183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a188  cmp     [rsi], di
0x18002a18b  jnz     short loc_18002A19B
0x18002a18d  mov     r8, rbx; unsigned __int64
0x18002a190  mov     rdx, rbp; unsigned __int16 *
0x18002a193  mov     rcx, rsi; this
0x18002a196  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002a19b  mov     rcx, rsi; lpOutputString
0x18002a19e  call    cs:__imp_OutputDebugStringW
0x18002a1a4  test    byte ptr [rbx+4], 4
0x18002a1a8  jnz     short loc_18002A1B3
0x18002a1aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002a1b1  jz      short loc_18002A1C4
0x18002a1b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002a1ba  test    rax, rax
0x18002a1bd  jz      short loc_18002A1C4
0x18002a1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a1c4  mov     rbx, [rsp+78h+arg_10]
0x18002a1cc  add     rsp, 40h
0x18002a1d0  pop     r15
0x18002a1d2  pop     r14
0x18002a1d4  pop     r13
0x18002a1d6  pop     r12
0x18002a1d8  pop     rdi
0x18002a1d9  pop     rsi
0x18002a1da  pop     rbp
0x18002a1db  retn
```
