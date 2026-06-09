# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006ad8`
- end: `0x180006dd1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800037b8`
- `0x180003afc`

## callees

- `0x1800036f8`
- `0x180005de4`
- `0x180006650`
- `0x180006ad8`
- `0x180007a7c`
- `0x180007aa0`
- `0x180007c24`
- `0x180007c40`
- `0x18000ad50`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d8c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d1a`

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
0x180006ad8  mov     [rsp+arg_10], rbx
0x180006add  mov     [rsp+arg_8], edx
0x180006ae1  mov     [rsp+arg_0], rcx
0x180006ae6  push    rbp
0x180006ae7  push    rsi
0x180006ae8  push    rdi
0x180006ae9  push    r12
0x180006aeb  push    r13
0x180006aed  push    r14
0x180006aef  push    r15
0x180006af1  sub     rsp, 40h
0x180006af5  mov     r12, r9
0x180006af8  mov     r13, r8
0x180006afb  mov     r10, rcx
0x180006afe  xor     eax, eax
0x180006b00  mov     rsi, [rsp+78h+lpOutputString]
0x180006b08  mov     [rsi], ax
0x180006b0b  mov     rax, [rsp+78h+arg_60]
0x180006b13  mov     byte ptr [rax], 0
0x180006b16  mov     r14, [rsp+78h+arg_38]
0x180006b1e  mov     edi, [r14]
0x180006b21  mov     rbx, [rsp+78h+arg_78]
0x180006b29  mov     [rbx+8], edi
0x180006b2c  mov     eax, [r14+4]
0x180006b30  mov     [rbx+0Ch], eax
0x180006b33  xor     ebp, ebp
0x180006b35  mov     r15d, [rsp+78h+arg_30]
0x180006b3d  mov     ecx, r15d
0x180006b40  test    r15d, r15d
0x180006b43  jz      short loc_180006BAB
0x180006b45  sub     ecx, 1
0x180006b48  jz      short loc_180006BA2
0x180006b4a  sub     ecx, 1
0x180006b4d  jz      short loc_180006B5D
0x180006b4f  cmp     ecx, 1
0x180006b52  jnz     short loc_180006BB4
0x180006b54  mov     ecx, edi; this
0x180006b56  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006b5b  jmp     short loc_180006BB2
0x180006b5d  test    edi, edi
0x180006b5f  js      short loc_180006B99
0x180006b61  mov     edi, 8007029Ch
0x180006b66  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006b6a  mov     rax, [rsp+78h+arg_28]
0x180006b72  mov     [rsp+78h+var_50], rax; __int64
0x180006b77  mov     rax, [rsp+78h+arg_20]
0x180006b7f  mov     [rsp+78h+var_58], rax; __int64
0x180006b84  mov     rcx, r10; int
0x180006b87  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006b8c  mov     [rbx+8], edi
0x180006b8f  mov     ecx, edi; this
0x180006b91  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006b96  mov     [rbx+0Ch], eax
0x180006b99  mov     ecx, edi; this
0x180006b9b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006ba0  jmp     short loc_180006BB2
0x180006ba2  mov     ecx, edi; this
0x180006ba4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ba9  jmp     short loc_180006BB2
0x180006bab  mov     ecx, edi; this
0x180006bad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006bb2  mov     ebp, eax
0x180006bb4  mov     [rbx], r15d
0x180006bb7  mov     eax, [rsp+78h+arg_70]
0x180006bbe  mov     [rbx+4], eax
0x180006bc1  cmp     dword ptr [r14+8], 1
0x180006bc6  jnz     short loc_180006BCE
0x180006bc8  or      eax, 8
0x180006bcb  mov     [rbx+4], eax
0x180006bce  mov     eax, 1
0x180006bd3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006bdb  inc     eax
0x180006bdd  mov     [rbx+10h], eax
0x180006be0  mov     rax, [rsp+78h+arg_40]
0x180006be8  xor     edi, edi
0x180006bea  test    rax, rax
0x180006bed  jz      short loc_180006BF4
0x180006bef  cmp     [rax], di
0x180006bf2  jnz     short loc_180006BF7
0x180006bf4  mov     rax, rdi
0x180006bf7  mov     [rbx+18h], rax
0x180006bfb  call    cs:__imp_GetCurrentThreadId
0x180006c01  mov     [rbx+20h], eax
0x180006c04  mov     [rbx+38h], r13
0x180006c08  mov     eax, [rsp+78h+arg_8]
0x180006c0f  mov     [rbx+40h], eax
0x180006c12  mov     [rbx+44h], ebp
0x180006c15  mov     rax, [rsp+78h+arg_20]
0x180006c1d  mov     [rbx+28h], rax
0x180006c21  mov     [rbx+30h], r12
0x180006c25  mov     rax, [rsp+78h+arg_28]
0x180006c2d  mov     [rbx+88h], rax
0x180006c34  mov     rax, [rsp+78h+arg_0]
0x180006c3c  mov     [rbx+90h], rax
0x180006c43  mov     [rbx+48h], rdi
0x180006c47  xorps   xmm0, xmm0
0x180006c4a  xor     eax, eax
0x180006c4c  movups  xmmword ptr [rbx+68h], xmm0
0x180006c50  mov     [rbx+78h], rax
0x180006c54  movups  xmmword ptr [rbx+50h], xmm0
0x180006c58  mov     [rbx+60h], rax
0x180006c5c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006c63  test    rax, rax
0x180006c66  jz      short loc_180006C6F
0x180006c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c6d  jmp     short loc_180006C72
0x180006c6f  mov     rax, rdi
0x180006c72  mov     [rbx+80h], rax
0x180006c79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c80  test    rax, rax
0x180006c83  jz      short loc_180006C8D
0x180006c85  mov     rcx, rbx
0x180006c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c94  test    rax, rax
0x180006c97  jz      short loc_180006CAF
0x180006c99  mov     r8d, 400h
0x180006c9f  mov     rdx, [rsp+78h+arg_60]
0x180006ca7  mov     rcx, rbx
0x180006caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006caf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cb6  test    rax, rax
0x180006cb9  jz      short loc_180006CC3
0x180006cbb  mov     rcx, rbx
0x180006cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cca  test    rax, rax
0x180006ccd  jz      short loc_180006CDD
0x180006ccf  test    byte ptr [rbx+4], 2
0x180006cd3  jnz     short loc_180006CDD
0x180006cd5  mov     rcx, rbx
0x180006cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdd  cmp     [rbx+8], edi
0x180006ce0  jl      short loc_180006CFC
0x180006ce2  cmp     r15d, 3
0x180006ce6  jnz     loc_180006DCB
0x180006cec  mov     ecx, 8000FFFFh; this
0x180006cf1  mov     [rbx+8], ecx
0x180006cf4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006cf9  mov     [rbx+0Ch], eax
0x180006cfc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006d03  jnz     short loc_180006D24
0x180006d05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006d0c  test    rax, rax
0x180006d0f  jz      short loc_180006D1A
0x180006d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d16  test    al, al
0x180006d18  jmp     short loc_180006D22
0x180006d1a  call    cs:__imp_IsDebuggerPresent
0x180006d20  test    eax, eax
0x180006d22  jz      short loc_180006D2A
0x180006d24  test    byte ptr [rbx+4], 2
0x180006d28  jz      short loc_180006D4E
0x180006d2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d31  test    rax, rax
0x180006d34  jz      short loc_180006D92
0x180006d36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d3d  jnz     short loc_180006D92
0x180006d3f  xor     r8d, r8d
0x180006d42  xor     edx, edx
0x180006d44  mov     rcx, rbx
0x180006d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4c  jmp     short loc_180006D92
0x180006d4e  mov     ebp, 800h
0x180006d53  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d5a  test    rax, rax
0x180006d5d  jz      short loc_180006D76
0x180006d5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d66  jnz     short loc_180006D76
0x180006d68  mov     r8d, ebp
0x180006d6b  mov     rdx, rsi
0x180006d6e  mov     rcx, rbx
0x180006d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d76  cmp     [rsi], di
0x180006d79  jnz     short loc_180006D89
0x180006d7b  mov     r8, rbx; unsigned __int64
0x180006d7e  mov     rdx, rbp; unsigned __int16 *
0x180006d81  mov     rcx, rsi; this
0x180006d84  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d89  mov     rcx, rsi; lpOutputString
0x180006d8c  call    cs:__imp_OutputDebugStringW
0x180006d92  test    byte ptr [rbx+4], 4
0x180006d96  jnz     short loc_180006DA1
0x180006d98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006d9f  jz      short loc_180006DB3
0x180006da1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006da8  test    rax, rax
0x180006dab  jz      short loc_180006DB3
0x180006dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db2  nop
0x180006db3  mov     rbx, [rsp+78h+arg_10]
0x180006dbb  add     rsp, 40h
0x180006dbf  pop     r15
0x180006dc1  pop     r14
0x180006dc3  pop     r13
0x180006dc5  pop     r12
0x180006dc7  pop     rdi
0x180006dc8  pop     rsi
0x180006dc9  pop     rbp
0x180006dca  retn
0x180006dcb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
