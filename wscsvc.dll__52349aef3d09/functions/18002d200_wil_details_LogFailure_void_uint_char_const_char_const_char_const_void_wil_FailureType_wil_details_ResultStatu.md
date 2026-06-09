# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002d200`
- end: `0x18002d4f9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002babc`
- `0x18002be00`

## callees

- `0x180022e1c`
- `0x18002b9fc`
- `0x18002cb24`
- `0x18002d200`
- `0x18002d89c`
- `0x18002d8c0`
- `0x18002d930`
- `0x18002d94c`
- `0x18002eae4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d323`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d323`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d442`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002d442`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002d4b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002d4b4`

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
0x18002d200  mov     [rsp+arg_10], rbx
0x18002d205  mov     [rsp+arg_8], edx
0x18002d209  mov     [rsp+arg_0], rcx
0x18002d20e  push    rbp
0x18002d20f  push    rsi
0x18002d210  push    rdi
0x18002d211  push    r12
0x18002d213  push    r13
0x18002d215  push    r14
0x18002d217  push    r15
0x18002d219  sub     rsp, 40h
0x18002d21d  mov     r12, r9
0x18002d220  mov     r13, r8
0x18002d223  mov     r10, rcx
0x18002d226  xor     eax, eax
0x18002d228  mov     rsi, [rsp+78h+lpOutputString]
0x18002d230  mov     [rsi], ax
0x18002d233  mov     rax, [rsp+78h+arg_60]
0x18002d23b  mov     byte ptr [rax], 0
0x18002d23e  mov     r14, [rsp+78h+arg_38]
0x18002d246  mov     edi, [r14]
0x18002d249  mov     rbx, [rsp+78h+arg_78]
0x18002d251  mov     [rbx+8], edi
0x18002d254  mov     eax, [r14+4]
0x18002d258  mov     [rbx+0Ch], eax
0x18002d25b  xor     ebp, ebp
0x18002d25d  mov     r15d, [rsp+78h+arg_30]
0x18002d265  mov     ecx, r15d
0x18002d268  test    r15d, r15d
0x18002d26b  jz      short loc_18002D2D3
0x18002d26d  sub     ecx, 1
0x18002d270  jz      short loc_18002D2CA
0x18002d272  sub     ecx, 1
0x18002d275  jz      short loc_18002D285
0x18002d277  cmp     ecx, 1
0x18002d27a  jnz     short loc_18002D2DC
0x18002d27c  mov     ecx, edi; this
0x18002d27e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002d283  jmp     short loc_18002D2DA
0x18002d285  test    edi, edi
0x18002d287  js      short loc_18002D2C1
0x18002d289  mov     edi, 8007029Ch
0x18002d28e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002d292  mov     rax, [rsp+78h+arg_28]
0x18002d29a  mov     [rsp+78h+var_50], rax; __int64
0x18002d29f  mov     rax, [rsp+78h+arg_20]
0x18002d2a7  mov     [rsp+78h+var_58], rax; __int64
0x18002d2ac  mov     rcx, r10; int
0x18002d2af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002d2b4  mov     [rbx+8], edi
0x18002d2b7  mov     ecx, edi; this
0x18002d2b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002d2be  mov     [rbx+0Ch], eax
0x18002d2c1  mov     ecx, edi; this
0x18002d2c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002d2c8  jmp     short loc_18002D2DA
0x18002d2ca  mov     ecx, edi; this
0x18002d2cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002d2d1  jmp     short loc_18002D2DA
0x18002d2d3  mov     ecx, edi; this
0x18002d2d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002d2da  mov     ebp, eax
0x18002d2dc  mov     [rbx], r15d
0x18002d2df  mov     eax, [rsp+78h+arg_70]
0x18002d2e6  mov     [rbx+4], eax
0x18002d2e9  cmp     dword ptr [r14+8], 1
0x18002d2ee  jnz     short loc_18002D2F6
0x18002d2f0  or      eax, 8
0x18002d2f3  mov     [rbx+4], eax
0x18002d2f6  mov     eax, 1
0x18002d2fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002d303  inc     eax
0x18002d305  mov     [rbx+10h], eax
0x18002d308  mov     rax, [rsp+78h+arg_40]
0x18002d310  xor     edi, edi
0x18002d312  test    rax, rax
0x18002d315  jz      short loc_18002D31C
0x18002d317  cmp     [rax], di
0x18002d31a  jnz     short loc_18002D31F
0x18002d31c  mov     rax, rdi
0x18002d31f  mov     [rbx+18h], rax
0x18002d323  call    cs:__imp_GetCurrentThreadId
0x18002d329  mov     [rbx+20h], eax
0x18002d32c  mov     [rbx+38h], r13
0x18002d330  mov     eax, [rsp+78h+arg_8]
0x18002d337  mov     [rbx+40h], eax
0x18002d33a  mov     [rbx+44h], ebp
0x18002d33d  mov     rax, [rsp+78h+arg_20]
0x18002d345  mov     [rbx+28h], rax
0x18002d349  mov     [rbx+30h], r12
0x18002d34d  mov     rax, [rsp+78h+arg_28]
0x18002d355  mov     [rbx+88h], rax
0x18002d35c  mov     rax, [rsp+78h+arg_0]
0x18002d364  mov     [rbx+90h], rax
0x18002d36b  mov     [rbx+48h], rdi
0x18002d36f  xorps   xmm0, xmm0
0x18002d372  xor     eax, eax
0x18002d374  movups  xmmword ptr [rbx+68h], xmm0
0x18002d378  mov     [rbx+78h], rax
0x18002d37c  movups  xmmword ptr [rbx+50h], xmm0
0x18002d380  mov     [rbx+60h], rax
0x18002d384  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002d38b  test    rax, rax
0x18002d38e  jz      short loc_18002D397
0x18002d390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d395  jmp     short loc_18002D39A
0x18002d397  mov     rax, rdi
0x18002d39a  mov     [rbx+80h], rax
0x18002d3a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002d3a8  test    rax, rax
0x18002d3ab  jz      short loc_18002D3B5
0x18002d3ad  mov     rcx, rbx
0x18002d3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002d3bc  test    rax, rax
0x18002d3bf  jz      short loc_18002D3D7
0x18002d3c1  mov     r8d, 400h
0x18002d3c7  mov     rdx, [rsp+78h+arg_60]
0x18002d3cf  mov     rcx, rbx
0x18002d3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002d3de  test    rax, rax
0x18002d3e1  jz      short loc_18002D3EB
0x18002d3e3  mov     rcx, rbx
0x18002d3e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002d3f2  test    rax, rax
0x18002d3f5  jz      short loc_18002D405
0x18002d3f7  test    byte ptr [rbx+4], 2
0x18002d3fb  jnz     short loc_18002D405
0x18002d3fd  mov     rcx, rbx
0x18002d400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d405  cmp     [rbx+8], edi
0x18002d408  jl      short loc_18002D424
0x18002d40a  cmp     r15d, 3
0x18002d40e  jnz     loc_18002D4F3
0x18002d414  mov     ecx, 8000FFFFh; this
0x18002d419  mov     [rbx+8], ecx
0x18002d41c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002d421  mov     [rbx+0Ch], eax
0x18002d424  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002d42b  jnz     short loc_18002D44C
0x18002d42d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002d434  test    rax, rax
0x18002d437  jz      short loc_18002D442
0x18002d439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d43e  test    al, al
0x18002d440  jmp     short loc_18002D44A
0x18002d442  call    cs:__imp_IsDebuggerPresent
0x18002d448  test    eax, eax
0x18002d44a  jz      short loc_18002D452
0x18002d44c  test    byte ptr [rbx+4], 2
0x18002d450  jz      short loc_18002D476
0x18002d452  mov     rax, cs:g_pfnResultLoggingCallback
0x18002d459  test    rax, rax
0x18002d45c  jz      short loc_18002D4BA
0x18002d45e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002d465  jnz     short loc_18002D4BA
0x18002d467  xor     r8d, r8d
0x18002d46a  xor     edx, edx
0x18002d46c  mov     rcx, rbx
0x18002d46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d474  jmp     short loc_18002D4BA
0x18002d476  mov     ebp, 800h
0x18002d47b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002d482  test    rax, rax
0x18002d485  jz      short loc_18002D49E
0x18002d487  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002d48e  jnz     short loc_18002D49E
0x18002d490  mov     r8d, ebp
0x18002d493  mov     rdx, rsi
0x18002d496  mov     rcx, rbx
0x18002d499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d49e  cmp     [rsi], di
0x18002d4a1  jnz     short loc_18002D4B1
0x18002d4a3  mov     r8, rbx; unsigned __int64
0x18002d4a6  mov     rdx, rbp; unsigned __int16 *
0x18002d4a9  mov     rcx, rsi; this
0x18002d4ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002d4b1  mov     rcx, rsi; lpOutputString
0x18002d4b4  call    cs:__imp_OutputDebugStringW
0x18002d4ba  test    byte ptr [rbx+4], 4
0x18002d4be  jnz     short loc_18002D4C9
0x18002d4c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002d4c7  jz      short loc_18002D4DB
0x18002d4c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002d4d0  test    rax, rax
0x18002d4d3  jz      short loc_18002D4DB
0x18002d4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4da  nop
0x18002d4db  mov     rbx, [rsp+78h+arg_10]
0x18002d4e3  add     rsp, 40h
0x18002d4e7  pop     r15
0x18002d4e9  pop     r14
0x18002d4eb  pop     r13
0x18002d4ed  pop     r12
0x18002d4ef  pop     rdi
0x18002d4f0  pop     rsi
0x18002d4f1  pop     rbp
0x18002d4f2  retn
0x18002d4f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
