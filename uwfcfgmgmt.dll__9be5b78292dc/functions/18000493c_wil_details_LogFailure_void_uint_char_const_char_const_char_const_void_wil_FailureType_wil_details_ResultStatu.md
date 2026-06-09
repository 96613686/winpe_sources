# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000493c`
- end: `0x180004c34`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003360`

## callees

- `0x180002d9c`
- `0x180003fd4`
- `0x18000476c`
- `0x18000493c`
- `0x180004e7c`
- `0x180004ea0`
- `0x180004eb4`
- `0x180004ed0`
- `0x180005924`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a5f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b7e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bf0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bf0`

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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
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
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x18000493c  mov     [rsp+arg_10], rbx
0x180004941  mov     [rsp+arg_8], edx
0x180004945  mov     [rsp+arg_0], rcx
0x18000494a  push    rbp
0x18000494b  push    rsi
0x18000494c  push    rdi
0x18000494d  push    r12
0x18000494f  push    r13
0x180004951  push    r14
0x180004953  push    r15
0x180004955  sub     rsp, 40h
0x180004959  mov     r14, [rsp+78h+arg_38]
0x180004961  xor     eax, eax
0x180004963  mov     rbx, [rsp+78h+arg_78]
0x18000496b  xor     ebp, ebp
0x18000496d  mov     r15d, [rsp+78h+arg_30]
0x180004975  mov     r10, rcx
0x180004978  mov     rsi, [rsp+78h+lpOutputString]
0x180004980  mov     r12, r9
0x180004983  mov     r13, r8
0x180004986  mov     ecx, r15d
0x180004989  mov     [rsi], ax
0x18000498c  mov     rax, [rsp+78h+arg_60]
0x180004994  mov     byte ptr [rax], 0
0x180004997  mov     edi, [r14]
0x18000499a  mov     [rbx+8], edi
0x18000499d  mov     eax, [r14+4]
0x1800049a1  mov     [rbx+0Ch], eax
0x1800049a4  test    r15d, r15d
0x1800049a7  jz      short loc_180004A0F
0x1800049a9  sub     ecx, 1
0x1800049ac  jz      short loc_180004A06
0x1800049ae  sub     ecx, 1
0x1800049b1  jz      short loc_1800049C1
0x1800049b3  cmp     ecx, 1
0x1800049b6  jnz     short loc_180004A18
0x1800049b8  mov     ecx, edi; this
0x1800049ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800049bf  jmp     short loc_180004A16
0x1800049c1  test    edi, edi
0x1800049c3  js      short loc_1800049FD
0x1800049c5  mov     rax, [rsp+78h+arg_28]
0x1800049cd  mov     edi, 8007029Ch
0x1800049d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800049d6  mov     rcx, r10; int
0x1800049d9  mov     [rsp+78h+var_50], rax; __int64
0x1800049de  mov     rax, [rsp+78h+arg_20]
0x1800049e6  mov     [rsp+78h+var_58], rax; __int64
0x1800049eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800049f0  mov     ecx, edi; this
0x1800049f2  mov     [rbx+8], edi
0x1800049f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800049fa  mov     [rbx+0Ch], eax
0x1800049fd  mov     ecx, edi; this
0x1800049ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004a04  jmp     short loc_180004A16
0x180004a06  mov     ecx, edi; this
0x180004a08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004a0d  jmp     short loc_180004A16
0x180004a0f  mov     ecx, edi; this
0x180004a11  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004a16  mov     ebp, eax
0x180004a18  mov     eax, [rsp+78h+arg_70]
0x180004a1f  mov     [rbx+4], eax
0x180004a22  mov     [rbx], r15d
0x180004a25  cmp     dword ptr [r14+8], 1
0x180004a2a  jnz     short loc_180004A32
0x180004a2c  or      eax, 8
0x180004a2f  mov     [rbx+4], eax
0x180004a32  mov     eax, 1
0x180004a37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004a3f  inc     eax
0x180004a41  xor     edi, edi
0x180004a43  mov     [rbx+10h], eax
0x180004a46  mov     rax, [rsp+78h+arg_40]
0x180004a4e  test    rax, rax
0x180004a51  jz      short loc_180004A58
0x180004a53  cmp     [rax], di
0x180004a56  jnz     short loc_180004A5B
0x180004a58  mov     rax, rdi
0x180004a5b  mov     [rbx+18h], rax
0x180004a5f  call    cs:__imp_GetCurrentThreadId
0x180004a65  mov     [rbx+38h], r13
0x180004a69  xorps   xmm0, xmm0
0x180004a6c  mov     [rbx+20h], eax
0x180004a6f  mov     eax, [rsp+78h+arg_8]
0x180004a76  mov     [rbx+40h], eax
0x180004a79  mov     rax, [rsp+78h+arg_20]
0x180004a81  mov     [rbx+28h], rax
0x180004a85  mov     rax, [rsp+78h+arg_28]
0x180004a8d  mov     [rbx+88h], rax
0x180004a94  mov     rax, [rsp+78h+arg_0]
0x180004a9c  mov     [rbx+90h], rax
0x180004aa3  xor     eax, eax
0x180004aa5  mov     [rbx+44h], ebp
0x180004aa8  mov     [rbx+30h], r12
0x180004aac  mov     [rbx+48h], rdi
0x180004ab0  movups  xmmword ptr [rbx+68h], xmm0
0x180004ab4  mov     [rbx+78h], rax
0x180004ab8  movups  xmmword ptr [rbx+50h], xmm0
0x180004abc  mov     [rbx+60h], rax
0x180004ac0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ac7  test    rax, rax
0x180004aca  jz      short loc_180004AD3
0x180004acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad1  jmp     short loc_180004AD6
0x180004ad3  mov     rax, rdi
0x180004ad6  mov     [rbx+80h], rax
0x180004add  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004ae4  test    rax, rax
0x180004ae7  jz      short loc_180004AF1
0x180004ae9  mov     rcx, rbx
0x180004aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004af1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004af8  test    rax, rax
0x180004afb  jz      short loc_180004B13
0x180004afd  mov     rdx, [rsp+78h+arg_60]
0x180004b05  mov     r8d, 400h
0x180004b0b  mov     rcx, rbx
0x180004b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b13  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b1a  test    rax, rax
0x180004b1d  jz      short loc_180004B27
0x180004b1f  mov     rcx, rbx
0x180004b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b27  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b2e  test    rax, rax
0x180004b31  jz      short loc_180004B41
0x180004b33  test    byte ptr [rbx+4], 2
0x180004b37  jnz     short loc_180004B41
0x180004b39  mov     rcx, rbx
0x180004b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b41  cmp     [rbx+8], edi
0x180004b44  jl      short loc_180004B60
0x180004b46  cmp     r15d, 3
0x180004b4a  jnz     loc_180004C2E
0x180004b50  mov     ecx, 8000FFFFh; this
0x180004b55  mov     [rbx+8], ecx
0x180004b58  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004b5d  mov     [rbx+0Ch], eax
0x180004b60  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004b67  jnz     short loc_180004B88
0x180004b69  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004b70  test    rax, rax
0x180004b73  jz      short loc_180004B7E
0x180004b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7a  test    al, al
0x180004b7c  jmp     short loc_180004B86
0x180004b7e  call    cs:__imp_IsDebuggerPresent
0x180004b84  test    eax, eax
0x180004b86  jz      short loc_180004B8E
0x180004b88  test    byte ptr [rbx+4], 2
0x180004b8c  jz      short loc_180004BB2
0x180004b8e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b95  test    rax, rax
0x180004b98  jz      short loc_180004BF6
0x180004b9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004ba1  jnz     short loc_180004BF6
0x180004ba3  xor     r8d, r8d
0x180004ba6  xor     edx, edx
0x180004ba8  mov     rcx, rbx
0x180004bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bb0  jmp     short loc_180004BF6
0x180004bb2  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bb9  mov     ebp, 800h
0x180004bbe  test    rax, rax
0x180004bc1  jz      short loc_180004BDA
0x180004bc3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004bca  jnz     short loc_180004BDA
0x180004bcc  mov     r8d, ebp
0x180004bcf  mov     rdx, rsi
0x180004bd2  mov     rcx, rbx
0x180004bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bda  cmp     [rsi], di
0x180004bdd  jnz     short loc_180004BED
0x180004bdf  mov     r8, rbx; unsigned __int64
0x180004be2  mov     rdx, rbp; unsigned __int16 *
0x180004be5  mov     rcx, rsi; this
0x180004be8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004bed  mov     rcx, rsi; lpOutputString
0x180004bf0  call    cs:__imp_OutputDebugStringW
0x180004bf6  test    byte ptr [rbx+4], 4
0x180004bfa  jnz     short loc_180004C05
0x180004bfc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004c03  jz      short loc_180004C16
0x180004c05  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c0c  test    rax, rax
0x180004c0f  jz      short loc_180004C16
0x180004c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c16  mov     rbx, [rsp+78h+arg_10]
0x180004c1e  add     rsp, 40h
0x180004c22  pop     r15
0x180004c24  pop     r14
0x180004c26  pop     r13
0x180004c28  pop     r12
0x180004c2a  pop     rdi
0x180004c2b  pop     rsi
0x180004c2c  pop     rbp
0x180004c2d  retn
0x180004c2e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
