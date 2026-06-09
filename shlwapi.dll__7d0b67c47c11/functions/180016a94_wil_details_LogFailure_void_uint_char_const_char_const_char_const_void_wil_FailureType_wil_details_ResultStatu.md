# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180016a94`
- end: `0x180016d8c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800157d0`
- `0x180015b14`

## callees

- `0x180011194`
- `0x180015710`
- `0x180016394`
- `0x180016a94`
- `0x180016f34`
- `0x180016f50`
- `0x180016f64`
- `0x180016f80`
- `0x1800177c8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bb7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016cd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016cd6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016d48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016d48`

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
0x180016a94  mov     [rsp+arg_10], rbx
0x180016a99  mov     [rsp+arg_8], edx
0x180016a9d  mov     [rsp+arg_0], rcx
0x180016aa2  push    rbp
0x180016aa3  push    rsi
0x180016aa4  push    rdi
0x180016aa5  push    r12
0x180016aa7  push    r13
0x180016aa9  push    r14
0x180016aab  push    r15
0x180016aad  sub     rsp, 40h
0x180016ab1  mov     r14, [rsp+78h+arg_38]
0x180016ab9  xor     eax, eax
0x180016abb  mov     rbx, [rsp+78h+arg_78]
0x180016ac3  xor     ebp, ebp
0x180016ac5  mov     r15d, [rsp+78h+arg_30]
0x180016acd  mov     r10, rcx
0x180016ad0  mov     rsi, [rsp+78h+lpOutputString]
0x180016ad8  mov     r12, r9
0x180016adb  mov     r13, r8
0x180016ade  mov     ecx, r15d
0x180016ae1  mov     [rsi], ax
0x180016ae4  mov     rax, [rsp+78h+arg_60]
0x180016aec  mov     byte ptr [rax], 0
0x180016aef  mov     edi, [r14]
0x180016af2  mov     [rbx+8], edi
0x180016af5  mov     eax, [r14+4]
0x180016af9  mov     [rbx+0Ch], eax
0x180016afc  test    r15d, r15d
0x180016aff  jz      short loc_180016B67
0x180016b01  sub     ecx, 1
0x180016b04  jz      short loc_180016B5E
0x180016b06  sub     ecx, 1
0x180016b09  jz      short loc_180016B19
0x180016b0b  cmp     ecx, 1
0x180016b0e  jnz     short loc_180016B70
0x180016b10  mov     ecx, edi; this
0x180016b12  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180016b17  jmp     short loc_180016B6E
0x180016b19  test    edi, edi
0x180016b1b  js      short loc_180016B55
0x180016b1d  mov     rax, [rsp+78h+arg_28]
0x180016b25  mov     edi, 8007029Ch
0x180016b2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180016b2e  mov     rcx, r10; int
0x180016b31  mov     [rsp+78h+var_50], rax; __int64
0x180016b36  mov     rax, [rsp+78h+arg_20]
0x180016b3e  mov     [rsp+78h+var_58], rax; __int64
0x180016b43  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016b48  mov     ecx, edi; this
0x180016b4a  mov     [rbx+8], edi
0x180016b4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016b52  mov     [rbx+0Ch], eax
0x180016b55  mov     ecx, edi; this
0x180016b57  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180016b5c  jmp     short loc_180016B6E
0x180016b5e  mov     ecx, edi; this
0x180016b60  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016b65  jmp     short loc_180016B6E
0x180016b67  mov     ecx, edi; this
0x180016b69  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180016b6e  mov     ebp, eax
0x180016b70  mov     eax, [rsp+78h+arg_70]
0x180016b77  mov     [rbx+4], eax
0x180016b7a  mov     [rbx], r15d
0x180016b7d  cmp     dword ptr [r14+8], 1
0x180016b82  jnz     short loc_180016B8A
0x180016b84  or      eax, 8
0x180016b87  mov     [rbx+4], eax
0x180016b8a  mov     eax, 1
0x180016b8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016b97  inc     eax
0x180016b99  xor     edi, edi
0x180016b9b  mov     [rbx+10h], eax
0x180016b9e  mov     rax, [rsp+78h+arg_40]
0x180016ba6  test    rax, rax
0x180016ba9  jz      short loc_180016BB0
0x180016bab  cmp     [rax], di
0x180016bae  jnz     short loc_180016BB3
0x180016bb0  mov     rax, rdi
0x180016bb3  mov     [rbx+18h], rax
0x180016bb7  call    cs:__imp_GetCurrentThreadId
0x180016bbd  mov     [rbx+38h], r13
0x180016bc1  xorps   xmm0, xmm0
0x180016bc4  mov     [rbx+20h], eax
0x180016bc7  mov     eax, [rsp+78h+arg_8]
0x180016bce  mov     [rbx+40h], eax
0x180016bd1  mov     rax, [rsp+78h+arg_20]
0x180016bd9  mov     [rbx+28h], rax
0x180016bdd  mov     rax, [rsp+78h+arg_28]
0x180016be5  mov     [rbx+88h], rax
0x180016bec  mov     rax, [rsp+78h+arg_0]
0x180016bf4  mov     [rbx+90h], rax
0x180016bfb  xor     eax, eax
0x180016bfd  mov     [rbx+44h], ebp
0x180016c00  mov     [rbx+30h], r12
0x180016c04  mov     [rbx+48h], rdi
0x180016c08  movups  xmmword ptr [rbx+68h], xmm0
0x180016c0c  mov     [rbx+78h], rax
0x180016c10  movups  xmmword ptr [rbx+50h], xmm0
0x180016c14  mov     [rbx+60h], rax
0x180016c18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180016c1f  test    rax, rax
0x180016c22  jz      short loc_180016C2B
0x180016c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c29  jmp     short loc_180016C2E
0x180016c2b  mov     rax, rdi
0x180016c2e  mov     [rbx+80h], rax
0x180016c35  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016c3c  test    rax, rax
0x180016c3f  jz      short loc_180016C49
0x180016c41  mov     rcx, rbx
0x180016c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180016c50  test    rax, rax
0x180016c53  jz      short loc_180016C6B
0x180016c55  mov     rdx, [rsp+78h+arg_60]
0x180016c5d  mov     r8d, 400h
0x180016c63  mov     rcx, rbx
0x180016c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c6b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016c72  test    rax, rax
0x180016c75  jz      short loc_180016C7F
0x180016c77  mov     rcx, rbx
0x180016c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016c86  test    rax, rax
0x180016c89  jz      short loc_180016C99
0x180016c8b  test    byte ptr [rbx+4], 2
0x180016c8f  jnz     short loc_180016C99
0x180016c91  mov     rcx, rbx
0x180016c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c99  cmp     [rbx+8], edi
0x180016c9c  jl      short loc_180016CB8
0x180016c9e  cmp     r15d, 3
0x180016ca2  jnz     loc_180016D86
0x180016ca8  mov     ecx, 8000FFFFh; this
0x180016cad  mov     [rbx+8], ecx
0x180016cb0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016cb5  mov     [rbx+0Ch], eax
0x180016cb8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180016cbf  jnz     short loc_180016CE0
0x180016cc1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016cc8  test    rax, rax
0x180016ccb  jz      short loc_180016CD6
0x180016ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cd2  test    al, al
0x180016cd4  jmp     short loc_180016CDE
0x180016cd6  call    cs:__imp_IsDebuggerPresent
0x180016cdc  test    eax, eax
0x180016cde  jz      short loc_180016CE6
0x180016ce0  test    byte ptr [rbx+4], 2
0x180016ce4  jz      short loc_180016D0A
0x180016ce6  mov     rax, cs:g_pfnResultLoggingCallback
0x180016ced  test    rax, rax
0x180016cf0  jz      short loc_180016D4E
0x180016cf2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180016cf9  jnz     short loc_180016D4E
0x180016cfb  xor     r8d, r8d
0x180016cfe  xor     edx, edx
0x180016d00  mov     rcx, rbx
0x180016d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d08  jmp     short loc_180016D4E
0x180016d0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180016d11  mov     ebp, 800h
0x180016d16  test    rax, rax
0x180016d19  jz      short loc_180016D32
0x180016d1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180016d22  jnz     short loc_180016D32
0x180016d24  mov     r8d, ebp
0x180016d27  mov     rdx, rsi
0x180016d2a  mov     rcx, rbx
0x180016d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d32  cmp     [rsi], di
0x180016d35  jnz     short loc_180016D45
0x180016d37  mov     r8, rbx; unsigned __int64
0x180016d3a  mov     rdx, rbp; unsigned __int16 *
0x180016d3d  mov     rcx, rsi; this
0x180016d40  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016d45  mov     rcx, rsi; lpOutputString
0x180016d48  call    cs:__imp_OutputDebugStringW
0x180016d4e  test    byte ptr [rbx+4], 4
0x180016d52  jnz     short loc_180016D5D
0x180016d54  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180016d5b  jz      short loc_180016D6E
0x180016d5d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016d64  test    rax, rax
0x180016d67  jz      short loc_180016D6E
0x180016d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d6e  mov     rbx, [rsp+78h+arg_10]
0x180016d76  add     rsp, 40h
0x180016d7a  pop     r15
0x180016d7c  pop     r14
0x180016d7e  pop     r13
0x180016d80  pop     r12
0x180016d82  pop     rdi
0x180016d83  pop     rsi
0x180016d84  pop     rbp
0x180016d85  retn
0x180016d86  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
