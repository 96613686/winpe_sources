# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005e360`
- end: `0x18005e659`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18005bb40`
- `0x18005be8c`

## callees

- `0x1800568c4`
- `0x18005ba80`
- `0x18005d550`
- `0x18005e360`
- `0x18005ee4c`
- `0x18005ee70`
- `0x18005efa8`
- `0x18005efc4`
- `0x1800616e8`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e483`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e483`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005e614`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005e614`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005e5a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005e5a2`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x18005e360  mov     [rsp+arg_10], rbx
0x18005e365  mov     [rsp+arg_8], edx
0x18005e369  mov     [rsp+arg_0], rcx
0x18005e36e  push    rbp
0x18005e36f  push    rsi
0x18005e370  push    rdi
0x18005e371  push    r12
0x18005e373  push    r13
0x18005e375  push    r14
0x18005e377  push    r15
0x18005e379  sub     rsp, 40h
0x18005e37d  mov     r12, r9
0x18005e380  mov     r13, r8
0x18005e383  mov     r10, rcx
0x18005e386  xor     eax, eax
0x18005e388  mov     rsi, [rsp+78h+lpOutputString]
0x18005e390  mov     [rsi], ax
0x18005e393  mov     rax, [rsp+78h+arg_60]
0x18005e39b  mov     byte ptr [rax], 0
0x18005e39e  mov     r14, [rsp+78h+arg_38]
0x18005e3a6  mov     edi, [r14]
0x18005e3a9  mov     rbx, [rsp+78h+arg_78]
0x18005e3b1  mov     [rbx+8], edi
0x18005e3b4  mov     eax, [r14+4]
0x18005e3b8  mov     [rbx+0Ch], eax
0x18005e3bb  xor     ebp, ebp
0x18005e3bd  mov     r15d, [rsp+78h+arg_30]
0x18005e3c5  mov     ecx, r15d
0x18005e3c8  test    r15d, r15d
0x18005e3cb  jz      short loc_18005E433
0x18005e3cd  sub     ecx, 1
0x18005e3d0  jz      short loc_18005E42A
0x18005e3d2  sub     ecx, 1
0x18005e3d5  jz      short loc_18005E3E5
0x18005e3d7  cmp     ecx, 1
0x18005e3da  jnz     short loc_18005E43C
0x18005e3dc  mov     ecx, edi; this
0x18005e3de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18005e3e3  jmp     short loc_18005E43A
0x18005e3e5  test    edi, edi
0x18005e3e7  js      short loc_18005E421
0x18005e3e9  mov     edi, 8007029Ch
0x18005e3ee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18005e3f2  mov     rax, [rsp+78h+arg_28]
0x18005e3fa  mov     [rsp+78h+var_50], rax; __int64
0x18005e3ff  mov     rax, [rsp+78h+arg_20]
0x18005e407  mov     [rsp+78h+var_58], rax; __int64
0x18005e40c  mov     rcx, r10; int
0x18005e40f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18005e414  mov     [rbx+8], edi
0x18005e417  mov     ecx, edi; this
0x18005e419  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005e41e  mov     [rbx+0Ch], eax
0x18005e421  mov     ecx, edi; this
0x18005e423  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18005e428  jmp     short loc_18005E43A
0x18005e42a  mov     ecx, edi; this
0x18005e42c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005e431  jmp     short loc_18005E43A
0x18005e433  mov     ecx, edi; this
0x18005e435  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005e43a  mov     ebp, eax
0x18005e43c  mov     [rbx], r15d
0x18005e43f  mov     eax, [rsp+78h+arg_70]
0x18005e446  mov     [rbx+4], eax
0x18005e449  cmp     dword ptr [r14+8], 1
0x18005e44e  jnz     short loc_18005E456
0x18005e450  or      eax, 8
0x18005e453  mov     [rbx+4], eax
0x18005e456  mov     eax, 1
0x18005e45b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005e463  inc     eax
0x18005e465  mov     [rbx+10h], eax
0x18005e468  mov     rax, [rsp+78h+arg_40]
0x18005e470  xor     edi, edi
0x18005e472  test    rax, rax
0x18005e475  jz      short loc_18005E47C
0x18005e477  cmp     [rax], di
0x18005e47a  jnz     short loc_18005E47F
0x18005e47c  mov     rax, rdi
0x18005e47f  mov     [rbx+18h], rax
0x18005e483  call    cs:__imp_GetCurrentThreadId
0x18005e489  mov     [rbx+20h], eax
0x18005e48c  mov     [rbx+38h], r13
0x18005e490  mov     eax, [rsp+78h+arg_8]
0x18005e497  mov     [rbx+40h], eax
0x18005e49a  mov     [rbx+44h], ebp
0x18005e49d  mov     rax, [rsp+78h+arg_20]
0x18005e4a5  mov     [rbx+28h], rax
0x18005e4a9  mov     [rbx+30h], r12
0x18005e4ad  mov     rax, [rsp+78h+arg_28]
0x18005e4b5  mov     [rbx+88h], rax
0x18005e4bc  mov     rax, [rsp+78h+arg_0]
0x18005e4c4  mov     [rbx+90h], rax
0x18005e4cb  mov     [rbx+48h], rdi
0x18005e4cf  xorps   xmm0, xmm0
0x18005e4d2  xor     eax, eax
0x18005e4d4  movups  xmmword ptr [rbx+68h], xmm0
0x18005e4d8  mov     [rbx+78h], rax
0x18005e4dc  movups  xmmword ptr [rbx+50h], xmm0
0x18005e4e0  mov     [rbx+60h], rax
0x18005e4e4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005e4eb  test    rax, rax
0x18005e4ee  jz      short loc_18005E4F7
0x18005e4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4f5  jmp     short loc_18005E4FA
0x18005e4f7  mov     rax, rdi
0x18005e4fa  mov     [rbx+80h], rax
0x18005e501  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005e508  test    rax, rax
0x18005e50b  jz      short loc_18005E515
0x18005e50d  mov     rcx, rbx
0x18005e510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e515  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005e51c  test    rax, rax
0x18005e51f  jz      short loc_18005E537
0x18005e521  mov     r8d, 400h
0x18005e527  mov     rdx, [rsp+78h+arg_60]
0x18005e52f  mov     rcx, rbx
0x18005e532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e537  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005e53e  test    rax, rax
0x18005e541  jz      short loc_18005E54B
0x18005e543  mov     rcx, rbx
0x18005e546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e54b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005e552  test    rax, rax
0x18005e555  jz      short loc_18005E565
0x18005e557  test    byte ptr [rbx+4], 2
0x18005e55b  jnz     short loc_18005E565
0x18005e55d  mov     rcx, rbx
0x18005e560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e565  cmp     [rbx+8], edi
0x18005e568  jl      short loc_18005E584
0x18005e56a  cmp     r15d, 3
0x18005e56e  jnz     loc_18005E653
0x18005e574  mov     ecx, 8000FFFFh; this
0x18005e579  mov     [rbx+8], ecx
0x18005e57c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005e581  mov     [rbx+0Ch], eax
0x18005e584  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005e58b  jnz     short loc_18005E5AC
0x18005e58d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005e594  test    rax, rax
0x18005e597  jz      short loc_18005E5A2
0x18005e599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e59e  test    al, al
0x18005e5a0  jmp     short loc_18005E5AA
0x18005e5a2  call    cs:__imp_IsDebuggerPresent
0x18005e5a8  test    eax, eax
0x18005e5aa  jz      short loc_18005E5B2
0x18005e5ac  test    byte ptr [rbx+4], 2
0x18005e5b0  jz      short loc_18005E5D6
0x18005e5b2  mov     rax, cs:g_pfnResultLoggingCallback
0x18005e5b9  test    rax, rax
0x18005e5bc  jz      short loc_18005E61A
0x18005e5be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005e5c5  jnz     short loc_18005E61A
0x18005e5c7  xor     r8d, r8d
0x18005e5ca  xor     edx, edx
0x18005e5cc  mov     rcx, rbx
0x18005e5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5d4  jmp     short loc_18005E61A
0x18005e5d6  mov     ebp, 800h
0x18005e5db  mov     rax, cs:g_pfnResultLoggingCallback
0x18005e5e2  test    rax, rax
0x18005e5e5  jz      short loc_18005E5FE
0x18005e5e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005e5ee  jnz     short loc_18005E5FE
0x18005e5f0  mov     r8d, ebp
0x18005e5f3  mov     rdx, rsi
0x18005e5f6  mov     rcx, rbx
0x18005e5f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5fe  cmp     [rsi], di
0x18005e601  jnz     short loc_18005E611
0x18005e603  mov     r8, rbx; unsigned __int64
0x18005e606  mov     rdx, rbp; unsigned __int16 *
0x18005e609  mov     rcx, rsi; this
0x18005e60c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005e611  mov     rcx, rsi; lpOutputString
0x18005e614  call    cs:__imp_OutputDebugStringW
0x18005e61a  test    byte ptr [rbx+4], 4
0x18005e61e  jnz     short loc_18005E629
0x18005e620  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005e627  jz      short loc_18005E63B
0x18005e629  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005e630  test    rax, rax
0x18005e633  jz      short loc_18005E63B
0x18005e635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e63a  nop
0x18005e63b  mov     rbx, [rsp+78h+arg_10]
0x18005e643  add     rsp, 40h
0x18005e647  pop     r15
0x18005e649  pop     r14
0x18005e64b  pop     r13
0x18005e64d  pop     r12
0x18005e64f  pop     rdi
0x18005e650  pop     rsi
0x18005e651  pop     rbp
0x18005e652  retn
0x18005e653  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
