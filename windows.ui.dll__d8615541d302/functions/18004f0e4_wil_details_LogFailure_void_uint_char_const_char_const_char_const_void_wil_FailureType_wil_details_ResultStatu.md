# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18004f0e4`
- end: `0x18004f3d9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18004c5f0`
- `0x18004ee5c`
- `0x18004efe8`
- `0x180073324`

## callees

- `0x1800491b0`
- `0x18004a420`
- `0x18004eda8`
- `0x18004f0e4`
- `0x18004f3e0`
- `0x18006829c`
- `0x18006ab6c`
- `0x18006ab88`
- `0x18006c4f8`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f207`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004f39a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004f39a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004f328`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004f328`

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
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

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
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x18004f0e4  mov     [rsp+arg_10], rbx
0x18004f0e9  mov     [rsp+arg_8], edx
0x18004f0ed  mov     [rsp+arg_0], rcx
0x18004f0f2  push    rbp
0x18004f0f3  push    rsi
0x18004f0f4  push    rdi
0x18004f0f5  push    r12
0x18004f0f7  push    r13
0x18004f0f9  push    r14
0x18004f0fb  push    r15
0x18004f0fd  sub     rsp, 40h
0x18004f101  mov     r12, r9
0x18004f104  mov     r13, r8
0x18004f107  mov     r10, rcx
0x18004f10a  xor     eax, eax
0x18004f10c  mov     rsi, [rsp+78h+lpOutputString]
0x18004f114  mov     [rsi], ax
0x18004f117  mov     rax, [rsp+78h+arg_60]
0x18004f11f  mov     byte ptr [rax], 0
0x18004f122  mov     r14, [rsp+78h+arg_38]
0x18004f12a  mov     edi, [r14]
0x18004f12d  mov     rbx, [rsp+78h+arg_78]
0x18004f135  mov     [rbx+8], edi
0x18004f138  mov     eax, [r14+4]
0x18004f13c  mov     [rbx+0Ch], eax
0x18004f13f  xor     ebp, ebp
0x18004f141  mov     r15d, [rsp+78h+arg_30]
0x18004f149  mov     ecx, r15d
0x18004f14c  test    r15d, r15d
0x18004f14f  jz      short loc_18004F1B7
0x18004f151  sub     ecx, 1
0x18004f154  jz      short loc_18004F1AE
0x18004f156  sub     ecx, 1
0x18004f159  jz      short loc_18004F169
0x18004f15b  cmp     ecx, 1
0x18004f15e  jnz     short loc_18004F1C0
0x18004f160  mov     ecx, edi; this
0x18004f162  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004f167  jmp     short loc_18004F1BE
0x18004f169  test    edi, edi
0x18004f16b  js      short loc_18004F1A5
0x18004f16d  mov     edi, 8007029Ch
0x18004f172  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004f176  mov     rax, [rsp+78h+arg_28]
0x18004f17e  mov     [rsp+78h+var_50], rax; __int64
0x18004f183  mov     rax, [rsp+78h+arg_20]
0x18004f18b  mov     [rsp+78h+var_58], rax; __int64
0x18004f190  mov     rcx, r10; int
0x18004f193  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18004f198  mov     [rbx+8], edi
0x18004f19b  mov     ecx, edi; this
0x18004f19d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004f1a2  mov     [rbx+0Ch], eax
0x18004f1a5  mov     ecx, edi; this
0x18004f1a7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004f1ac  jmp     short loc_18004F1BE
0x18004f1ae  mov     ecx, edi; this
0x18004f1b0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004f1b5  jmp     short loc_18004F1BE
0x18004f1b7  mov     ecx, edi; this
0x18004f1b9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004f1be  mov     ebp, eax
0x18004f1c0  mov     [rbx], r15d
0x18004f1c3  mov     eax, [rsp+78h+arg_70]
0x18004f1ca  mov     [rbx+4], eax
0x18004f1cd  cmp     dword ptr [r14+8], 1
0x18004f1d2  jnz     short loc_18004F1DA
0x18004f1d4  or      eax, 8
0x18004f1d7  mov     [rbx+4], eax
0x18004f1da  mov     eax, 1
0x18004f1df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004f1e7  inc     eax
0x18004f1e9  mov     [rbx+10h], eax
0x18004f1ec  mov     rax, [rsp+78h+arg_40]
0x18004f1f4  xor     edi, edi
0x18004f1f6  test    rax, rax
0x18004f1f9  jz      short loc_18004F200
0x18004f1fb  cmp     [rax], di
0x18004f1fe  jnz     short loc_18004F203
0x18004f200  mov     rax, rdi
0x18004f203  mov     [rbx+18h], rax
0x18004f207  call    cs:__imp_GetCurrentThreadId
0x18004f20d  mov     [rbx+20h], eax
0x18004f210  mov     [rbx+38h], r13
0x18004f214  mov     eax, [rsp+78h+arg_8]
0x18004f21b  mov     [rbx+40h], eax
0x18004f21e  mov     [rbx+44h], ebp
0x18004f221  mov     rax, [rsp+78h+arg_20]
0x18004f229  mov     [rbx+28h], rax
0x18004f22d  mov     [rbx+30h], r12
0x18004f231  mov     rax, [rsp+78h+arg_28]
0x18004f239  mov     [rbx+88h], rax
0x18004f240  mov     rax, [rsp+78h+arg_0]
0x18004f248  mov     [rbx+90h], rax
0x18004f24f  mov     [rbx+48h], rdi
0x18004f253  xorps   xmm0, xmm0
0x18004f256  xor     eax, eax
0x18004f258  movups  xmmword ptr [rbx+68h], xmm0
0x18004f25c  mov     [rbx+78h], rax
0x18004f260  movups  xmmword ptr [rbx+50h], xmm0
0x18004f264  mov     [rbx+60h], rax
0x18004f268  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004f26f  test    rax, rax
0x18004f272  jz      short loc_18004F27B
0x18004f274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f279  jmp     short loc_18004F27E
0x18004f27b  mov     rax, rdi
0x18004f27e  mov     [rbx+80h], rax
0x18004f285  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004f28c  test    rax, rax
0x18004f28f  jz      short loc_18004F299
0x18004f291  mov     rcx, rbx
0x18004f294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f299  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004f2a0  test    rax, rax
0x18004f2a3  jz      short loc_18004F2BB
0x18004f2a5  mov     r8d, 400h
0x18004f2ab  mov     rdx, [rsp+78h+arg_60]
0x18004f2b3  mov     rcx, rbx
0x18004f2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2bb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004f2c2  test    rax, rax
0x18004f2c5  jz      short loc_18004F2CF
0x18004f2c7  mov     rcx, rbx
0x18004f2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004f2d6  test    rax, rax
0x18004f2d9  jz      short loc_18004F2E9
0x18004f2db  test    byte ptr [rbx+4], 2
0x18004f2df  jnz     short loc_18004F2E9
0x18004f2e1  mov     rcx, rbx
0x18004f2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2e9  cmp     [rbx+8], edi
0x18004f2ec  jl      short loc_18004F30A
0x18004f2ee  cmp     r15d, 3
0x18004f2f2  jz      short loc_18004F2FA
0x18004f2f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18004f2fa  mov     ecx, 8000FFFFh; this
0x18004f2ff  mov     [rbx+8], ecx
0x18004f302  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004f307  mov     [rbx+0Ch], eax
0x18004f30a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004f311  jnz     short loc_18004F332
0x18004f313  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004f31a  test    rax, rax
0x18004f31d  jz      short loc_18004F328
0x18004f31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f324  test    al, al
0x18004f326  jmp     short loc_18004F330
0x18004f328  call    cs:__imp_IsDebuggerPresent
0x18004f32e  test    eax, eax
0x18004f330  jz      short loc_18004F338
0x18004f332  test    byte ptr [rbx+4], 2
0x18004f336  jz      short loc_18004F35C
0x18004f338  mov     rax, cs:g_pfnResultLoggingCallback
0x18004f33f  test    rax, rax
0x18004f342  jz      short loc_18004F3A0
0x18004f344  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004f34b  jnz     short loc_18004F3A0
0x18004f34d  xor     r8d, r8d
0x18004f350  xor     edx, edx
0x18004f352  mov     rcx, rbx
0x18004f355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f35a  jmp     short loc_18004F3A0
0x18004f35c  mov     ebp, 800h
0x18004f361  mov     rax, cs:g_pfnResultLoggingCallback
0x18004f368  test    rax, rax
0x18004f36b  jz      short loc_18004F384
0x18004f36d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004f374  jnz     short loc_18004F384
0x18004f376  mov     r8d, ebp
0x18004f379  mov     rdx, rsi
0x18004f37c  mov     rcx, rbx
0x18004f37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f384  cmp     [rsi], di
0x18004f387  jnz     short loc_18004F397
0x18004f389  mov     r8, rbx; unsigned __int64
0x18004f38c  mov     rdx, rbp; unsigned __int16 *
0x18004f38f  mov     rcx, rsi; this
0x18004f392  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004f397  mov     rcx, rsi; lpOutputString
0x18004f39a  call    cs:__imp_OutputDebugStringW
0x18004f3a0  test    byte ptr [rbx+4], 4
0x18004f3a4  jnz     short loc_18004F3AF
0x18004f3a6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004f3ad  jz      short loc_18004F3C1
0x18004f3af  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004f3b6  test    rax, rax
0x18004f3b9  jz      short loc_18004F3C1
0x18004f3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3c0  nop
0x18004f3c1  mov     rbx, [rsp+78h+arg_10]
0x18004f3c9  add     rsp, 40h
0x18004f3cd  pop     r15
0x18004f3cf  pop     r14
0x18004f3d1  pop     r13
0x18004f3d3  pop     r12
0x18004f3d5  pop     rdi
0x18004f3d6  pop     rsi
0x18004f3d7  pop     rbp
0x18004f3d8  retn
```
