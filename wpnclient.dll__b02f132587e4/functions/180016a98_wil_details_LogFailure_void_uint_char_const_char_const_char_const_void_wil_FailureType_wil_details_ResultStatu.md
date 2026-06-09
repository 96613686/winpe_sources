# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180016a98`
- end: `0x180016d8d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800167e4`
- `0x1800168e0`
- `0x1800213b4`
- `0x180021474`

## callees

- `0x180016a98`
- `0x1800173a4`
- `0x180017448`
- `0x1800212fc`
- `0x180021c08`
- `0x180022238`
- `0x180022260`
- `0x180022274`
- `0x180022a80`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016bbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016d4e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016d4e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016cdc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016cdc`

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
0x180016a98  mov     [rsp+arg_10], rbx
0x180016a9d  mov     [rsp+arg_8], edx
0x180016aa1  mov     [rsp+arg_0], rcx
0x180016aa6  push    rbp
0x180016aa7  push    rsi
0x180016aa8  push    rdi
0x180016aa9  push    r12
0x180016aab  push    r13
0x180016aad  push    r14
0x180016aaf  push    r15
0x180016ab1  sub     rsp, 40h
0x180016ab5  mov     r12, r9
0x180016ab8  mov     r13, r8
0x180016abb  mov     r10, rcx
0x180016abe  xor     eax, eax
0x180016ac0  mov     rsi, [rsp+78h+lpOutputString]
0x180016ac8  mov     [rsi], ax
0x180016acb  mov     rax, [rsp+78h+arg_60]
0x180016ad3  mov     byte ptr [rax], 0
0x180016ad6  mov     r14, [rsp+78h+arg_38]
0x180016ade  mov     edi, [r14]
0x180016ae1  mov     rbx, [rsp+78h+arg_78]
0x180016ae9  mov     [rbx+8], edi
0x180016aec  mov     eax, [r14+4]
0x180016af0  mov     [rbx+0Ch], eax
0x180016af3  xor     ebp, ebp
0x180016af5  mov     r15d, [rsp+78h+arg_30]
0x180016afd  mov     ecx, r15d
0x180016b00  test    r15d, r15d
0x180016b03  jz      short loc_180016B6B
0x180016b05  sub     ecx, 1
0x180016b08  jz      short loc_180016B62
0x180016b0a  sub     ecx, 1
0x180016b0d  jz      short loc_180016B1D
0x180016b0f  cmp     ecx, 1
0x180016b12  jnz     short loc_180016B74
0x180016b14  mov     ecx, edi; this
0x180016b16  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180016b1b  jmp     short loc_180016B72
0x180016b1d  test    edi, edi
0x180016b1f  js      short loc_180016B59
0x180016b21  mov     edi, 8007029Ch
0x180016b26  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180016b2a  mov     rax, [rsp+78h+arg_28]
0x180016b32  mov     [rsp+78h+var_50], rax; __int64
0x180016b37  mov     rax, [rsp+78h+arg_20]
0x180016b3f  mov     [rsp+78h+var_58], rax; __int64
0x180016b44  mov     rcx, r10; int
0x180016b47  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016b4c  mov     [rbx+8], edi
0x180016b4f  mov     ecx, edi; this
0x180016b51  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016b56  mov     [rbx+0Ch], eax
0x180016b59  mov     ecx, edi; this
0x180016b5b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180016b60  jmp     short loc_180016B72
0x180016b62  mov     ecx, edi; this
0x180016b64  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016b69  jmp     short loc_180016B72
0x180016b6b  mov     ecx, edi; this
0x180016b6d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180016b72  mov     ebp, eax
0x180016b74  mov     [rbx], r15d
0x180016b77  mov     eax, [rsp+78h+arg_70]
0x180016b7e  mov     [rbx+4], eax
0x180016b81  cmp     dword ptr [r14+8], 1
0x180016b86  jnz     short loc_180016B8E
0x180016b88  or      eax, 8
0x180016b8b  mov     [rbx+4], eax
0x180016b8e  mov     eax, 1
0x180016b93  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016b9b  inc     eax
0x180016b9d  mov     [rbx+10h], eax
0x180016ba0  mov     rax, [rsp+78h+arg_40]
0x180016ba8  xor     edi, edi
0x180016baa  test    rax, rax
0x180016bad  jz      short loc_180016BB4
0x180016baf  cmp     [rax], di
0x180016bb2  jnz     short loc_180016BB7
0x180016bb4  mov     rax, rdi
0x180016bb7  mov     [rbx+18h], rax
0x180016bbb  call    cs:__imp_GetCurrentThreadId
0x180016bc1  mov     [rbx+20h], eax
0x180016bc4  mov     [rbx+38h], r13
0x180016bc8  mov     eax, [rsp+78h+arg_8]
0x180016bcf  mov     [rbx+40h], eax
0x180016bd2  mov     [rbx+44h], ebp
0x180016bd5  mov     rax, [rsp+78h+arg_20]
0x180016bdd  mov     [rbx+28h], rax
0x180016be1  mov     [rbx+30h], r12
0x180016be5  mov     rax, [rsp+78h+arg_28]
0x180016bed  mov     [rbx+88h], rax
0x180016bf4  mov     rax, [rsp+78h+arg_0]
0x180016bfc  mov     [rbx+90h], rax
0x180016c03  mov     [rbx+48h], rdi
0x180016c07  xorps   xmm0, xmm0
0x180016c0a  xor     eax, eax
0x180016c0c  movups  xmmword ptr [rbx+68h], xmm0
0x180016c10  mov     [rbx+78h], rax
0x180016c14  movups  xmmword ptr [rbx+50h], xmm0
0x180016c18  mov     [rbx+60h], rax
0x180016c1c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180016c23  test    rax, rax
0x180016c26  jz      short loc_180016C2F
0x180016c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c2d  jmp     short loc_180016C32
0x180016c2f  mov     rax, rdi
0x180016c32  mov     [rbx+80h], rax
0x180016c39  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016c40  test    rax, rax
0x180016c43  jz      short loc_180016C4D
0x180016c45  mov     rcx, rbx
0x180016c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c4d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180016c54  test    rax, rax
0x180016c57  jz      short loc_180016C6F
0x180016c59  mov     r8d, 400h
0x180016c5f  mov     rdx, [rsp+78h+arg_60]
0x180016c67  mov     rcx, rbx
0x180016c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c6f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016c76  test    rax, rax
0x180016c79  jz      short loc_180016C83
0x180016c7b  mov     rcx, rbx
0x180016c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c83  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016c8a  test    rax, rax
0x180016c8d  jz      short loc_180016C9D
0x180016c8f  test    byte ptr [rbx+4], 2
0x180016c93  jnz     short loc_180016C9D
0x180016c95  mov     rcx, rbx
0x180016c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c9d  cmp     [rbx+8], edi
0x180016ca0  jl      short loc_180016CBE
0x180016ca2  cmp     r15d, 3
0x180016ca6  jz      short loc_180016CAE
0x180016ca8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180016cae  mov     ecx, 8000FFFFh; this
0x180016cb3  mov     [rbx+8], ecx
0x180016cb6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016cbb  mov     [rbx+0Ch], eax
0x180016cbe  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180016cc5  jnz     short loc_180016CE6
0x180016cc7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016cce  test    rax, rax
0x180016cd1  jz      short loc_180016CDC
0x180016cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cd8  test    al, al
0x180016cda  jmp     short loc_180016CE4
0x180016cdc  call    cs:__imp_IsDebuggerPresent
0x180016ce2  test    eax, eax
0x180016ce4  jz      short loc_180016CEC
0x180016ce6  test    byte ptr [rbx+4], 2
0x180016cea  jz      short loc_180016D10
0x180016cec  mov     rax, cs:g_pfnResultLoggingCallback
0x180016cf3  test    rax, rax
0x180016cf6  jz      short loc_180016D54
0x180016cf8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180016cff  jnz     short loc_180016D54
0x180016d01  xor     r8d, r8d
0x180016d04  xor     edx, edx
0x180016d06  mov     rcx, rbx
0x180016d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d0e  jmp     short loc_180016D54
0x180016d10  mov     ebp, 800h
0x180016d15  mov     rax, cs:g_pfnResultLoggingCallback
0x180016d1c  test    rax, rax
0x180016d1f  jz      short loc_180016D38
0x180016d21  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180016d28  jnz     short loc_180016D38
0x180016d2a  mov     r8d, ebp
0x180016d2d  mov     rdx, rsi
0x180016d30  mov     rcx, rbx
0x180016d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d38  cmp     [rsi], di
0x180016d3b  jnz     short loc_180016D4B
0x180016d3d  mov     r8, rbx; unsigned __int64
0x180016d40  mov     rdx, rbp; unsigned __int16 *
0x180016d43  mov     rcx, rsi; this
0x180016d46  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016d4b  mov     rcx, rsi; lpOutputString
0x180016d4e  call    cs:__imp_OutputDebugStringW
0x180016d54  test    byte ptr [rbx+4], 4
0x180016d58  jnz     short loc_180016D63
0x180016d5a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180016d61  jz      short loc_180016D75
0x180016d63  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016d6a  test    rax, rax
0x180016d6d  jz      short loc_180016D75
0x180016d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d74  nop
0x180016d75  mov     rbx, [rsp+78h+arg_10]
0x180016d7d  add     rsp, 40h
0x180016d81  pop     r15
0x180016d83  pop     r14
0x180016d85  pop     r13
0x180016d87  pop     r12
0x180016d89  pop     rdi
0x180016d8a  pop     rsi
0x180016d8b  pop     rbp
0x180016d8c  retn
```
