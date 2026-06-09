# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008858`
- end: `0x180008b64`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006ecc`
- `0x180007224`
- `0x18000a298`

## callees

- `0x180006e0c`
- `0x180007e04`
- `0x180008664`
- `0x180008858`
- `0x180008e94`
- `0x180008ec0`
- `0x180008ed4`
- `0x180008ef4`
- `0x180009c5c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000897b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000897b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008aa0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008aa0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b18`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b18`

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
0x180008858  mov     [rsp+arg_10], rbx
0x18000885d  mov     [rsp+arg_8], edx
0x180008861  mov     [rsp+arg_0], rcx
0x180008866  push    rbp
0x180008867  push    rsi
0x180008868  push    rdi
0x180008869  push    r12
0x18000886b  push    r13
0x18000886d  push    r14
0x18000886f  push    r15
0x180008871  sub     rsp, 40h
0x180008875  mov     r12, r9
0x180008878  mov     r13, r8
0x18000887b  mov     r10, rcx
0x18000887e  xor     eax, eax
0x180008880  mov     rsi, [rsp+78h+lpOutputString]
0x180008888  mov     [rsi], ax
0x18000888b  mov     rax, [rsp+78h+arg_60]
0x180008893  mov     byte ptr [rax], 0
0x180008896  mov     r14, [rsp+78h+arg_38]
0x18000889e  mov     edi, [r14]
0x1800088a1  mov     rbx, [rsp+78h+arg_78]
0x1800088a9  mov     [rbx+8], edi
0x1800088ac  mov     eax, [r14+4]
0x1800088b0  mov     [rbx+0Ch], eax
0x1800088b3  xor     ebp, ebp
0x1800088b5  mov     r15d, [rsp+78h+arg_30]
0x1800088bd  mov     ecx, r15d
0x1800088c0  test    r15d, r15d
0x1800088c3  jz      short loc_18000892B
0x1800088c5  sub     ecx, 1
0x1800088c8  jz      short loc_180008922
0x1800088ca  sub     ecx, 1
0x1800088cd  jz      short loc_1800088DD
0x1800088cf  cmp     ecx, 1
0x1800088d2  jnz     short loc_180008934
0x1800088d4  mov     ecx, edi; this
0x1800088d6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800088db  jmp     short loc_180008932
0x1800088dd  test    edi, edi
0x1800088df  js      short loc_180008919
0x1800088e1  mov     edi, 8007029Ch
0x1800088e6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800088ea  mov     rax, [rsp+78h+arg_28]
0x1800088f2  mov     [rsp+78h+var_50], rax; __int64
0x1800088f7  mov     rax, [rsp+78h+arg_20]
0x1800088ff  mov     [rsp+78h+var_58], rax; __int64
0x180008904  mov     rcx, r10; int
0x180008907  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000890c  mov     [rbx+8], edi
0x18000890f  mov     ecx, edi; this
0x180008911  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008916  mov     [rbx+0Ch], eax
0x180008919  mov     ecx, edi; this
0x18000891b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008920  jmp     short loc_180008932
0x180008922  mov     ecx, edi; this
0x180008924  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008929  jmp     short loc_180008932
0x18000892b  mov     ecx, edi; this
0x18000892d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008932  mov     ebp, eax
0x180008934  mov     [rbx], r15d
0x180008937  mov     eax, [rsp+78h+arg_70]
0x18000893e  mov     [rbx+4], eax
0x180008941  cmp     dword ptr [r14+8], 1
0x180008946  jnz     short loc_18000894E
0x180008948  or      eax, 8
0x18000894b  mov     [rbx+4], eax
0x18000894e  mov     eax, 1
0x180008953  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000895b  inc     eax
0x18000895d  mov     [rbx+10h], eax
0x180008960  mov     rax, [rsp+78h+arg_40]
0x180008968  xor     edi, edi
0x18000896a  test    rax, rax
0x18000896d  jz      short loc_180008974
0x18000896f  cmp     [rax], di
0x180008972  jnz     short loc_180008977
0x180008974  mov     rax, rdi
0x180008977  mov     [rbx+18h], rax
0x18000897b  call    cs:__imp_GetCurrentThreadId
0x180008982  nop     dword ptr [rax+rax+00h]
0x180008987  mov     [rbx+20h], eax
0x18000898a  mov     [rbx+38h], r13
0x18000898e  mov     eax, [rsp+78h+arg_8]
0x180008995  mov     [rbx+40h], eax
0x180008998  mov     [rbx+44h], ebp
0x18000899b  mov     rax, [rsp+78h+arg_20]
0x1800089a3  mov     [rbx+28h], rax
0x1800089a7  mov     [rbx+30h], r12
0x1800089ab  mov     rax, [rsp+78h+arg_28]
0x1800089b3  mov     [rbx+88h], rax
0x1800089ba  mov     rax, [rsp+78h+arg_0]
0x1800089c2  mov     [rbx+90h], rax
0x1800089c9  mov     [rbx+48h], rdi
0x1800089cd  xorps   xmm0, xmm0
0x1800089d0  xor     eax, eax
0x1800089d2  movups  xmmword ptr [rbx+68h], xmm0
0x1800089d6  mov     [rbx+78h], rax
0x1800089da  movups  xmmword ptr [rbx+50h], xmm0
0x1800089de  mov     [rbx+60h], rax
0x1800089e2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800089e9  test    rax, rax
0x1800089ec  jz      short loc_1800089F5
0x1800089ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089f3  jmp     short loc_1800089F8
0x1800089f5  mov     rax, rdi
0x1800089f8  mov     [rbx+80h], rax
0x1800089ff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008a06  test    rax, rax
0x180008a09  jz      short loc_180008A13
0x180008a0b  mov     rcx, rbx
0x180008a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a13  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008a1a  test    rax, rax
0x180008a1d  jz      short loc_180008A35
0x180008a1f  mov     r8d, 400h
0x180008a25  mov     rdx, [rsp+78h+arg_60]
0x180008a2d  mov     rcx, rbx
0x180008a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a35  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a3c  test    rax, rax
0x180008a3f  jz      short loc_180008A49
0x180008a41  mov     rcx, rbx
0x180008a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a49  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a50  test    rax, rax
0x180008a53  jz      short loc_180008A63
0x180008a55  test    byte ptr [rbx+4], 2
0x180008a59  jnz     short loc_180008A63
0x180008a5b  mov     rcx, rbx
0x180008a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a63  cmp     [rbx+8], edi
0x180008a66  jl      short loc_180008A82
0x180008a68  cmp     r15d, 3
0x180008a6c  jnz     loc_180008B5E
0x180008a72  mov     ecx, 8000FFFFh; this
0x180008a77  mov     [rbx+8], ecx
0x180008a7a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008a7f  mov     [rbx+0Ch], eax
0x180008a82  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008a89  jnz     short loc_180008AB0
0x180008a8b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008a92  test    rax, rax
0x180008a95  jz      short loc_180008AA0
0x180008a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a9c  test    al, al
0x180008a9e  jmp     short loc_180008AAE
0x180008aa0  call    cs:__imp_IsDebuggerPresent
0x180008aa7  nop     dword ptr [rax+rax+00h]
0x180008aac  test    eax, eax
0x180008aae  jz      short loc_180008AB6
0x180008ab0  test    byte ptr [rbx+4], 2
0x180008ab4  jz      short loc_180008ADA
0x180008ab6  mov     rax, cs:g_pfnResultLoggingCallback
0x180008abd  test    rax, rax
0x180008ac0  jz      short loc_180008B24
0x180008ac2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008ac9  jnz     short loc_180008B24
0x180008acb  xor     r8d, r8d
0x180008ace  xor     edx, edx
0x180008ad0  mov     rcx, rbx
0x180008ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ad8  jmp     short loc_180008B24
0x180008ada  mov     ebp, 800h
0x180008adf  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ae6  test    rax, rax
0x180008ae9  jz      short loc_180008B02
0x180008aeb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008af2  jnz     short loc_180008B02
0x180008af4  mov     r8d, ebp
0x180008af7  mov     rdx, rsi
0x180008afa  mov     rcx, rbx
0x180008afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b02  cmp     [rsi], di
0x180008b05  jnz     short loc_180008B15
0x180008b07  mov     r8, rbx; unsigned __int64
0x180008b0a  mov     rdx, rbp; unsigned __int16 *
0x180008b0d  mov     rcx, rsi; this
0x180008b10  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008b15  mov     rcx, rsi; lpOutputString
0x180008b18  call    cs:__imp_OutputDebugStringW
0x180008b1f  nop     dword ptr [rax+rax+00h]
0x180008b24  test    byte ptr [rbx+4], 4
0x180008b28  jnz     short loc_180008B33
0x180008b2a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008b31  jz      short loc_180008B45
0x180008b33  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008b3a  test    rax, rax
0x180008b3d  jz      short loc_180008B45
0x180008b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b44  nop
0x180008b45  mov     rbx, [rsp+78h+arg_10]
0x180008b4d  add     rsp, 40h
0x180008b51  pop     r15
0x180008b53  pop     r14
0x180008b55  pop     r13
0x180008b57  pop     r12
0x180008b59  pop     rdi
0x180008b5a  pop     rsi
0x180008b5b  pop     rbp
0x180008b5c  retn
0x180008b5e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
