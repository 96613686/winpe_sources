# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18004daa4`
- end: `0x18004ddb0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180035104`
- `0x18004bf70`
- `0x18004c2f0`

## callees

- `0x1800312a4`
- `0x18003821c`
- `0x18003d18c`
- `0x180042614`
- `0x18004bea8`
- `0x18004daa4`
- `0x18004e6e0`
- `0x18004e7a4`
- `0x18004fc98`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004dbc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004dbc7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004dcec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004dcec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004dd64`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004dd64`

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
0x18004daa4  mov     [rsp+arg_10], rbx
0x18004daa9  mov     [rsp+arg_8], edx
0x18004daad  mov     [rsp+arg_0], rcx
0x18004dab2  push    rbp
0x18004dab3  push    rsi
0x18004dab4  push    rdi
0x18004dab5  push    r12
0x18004dab7  push    r13
0x18004dab9  push    r14
0x18004dabb  push    r15
0x18004dabd  sub     rsp, 40h
0x18004dac1  mov     r12, r9
0x18004dac4  mov     r13, r8
0x18004dac7  mov     r10, rcx
0x18004daca  xor     eax, eax
0x18004dacc  mov     rsi, [rsp+78h+lpOutputString]
0x18004dad4  mov     [rsi], ax
0x18004dad7  mov     rax, [rsp+78h+arg_60]
0x18004dadf  mov     byte ptr [rax], 0
0x18004dae2  mov     r14, [rsp+78h+arg_38]
0x18004daea  mov     edi, [r14]
0x18004daed  mov     rbx, [rsp+78h+arg_78]
0x18004daf5  mov     [rbx+8], edi
0x18004daf8  mov     eax, [r14+4]
0x18004dafc  mov     [rbx+0Ch], eax
0x18004daff  xor     ebp, ebp
0x18004db01  mov     r15d, [rsp+78h+arg_30]
0x18004db09  mov     ecx, r15d
0x18004db0c  test    r15d, r15d
0x18004db0f  jz      short loc_18004DB77
0x18004db11  sub     ecx, 1
0x18004db14  jz      short loc_18004DB6E
0x18004db16  sub     ecx, 1
0x18004db19  jz      short loc_18004DB29
0x18004db1b  cmp     ecx, 1
0x18004db1e  jnz     short loc_18004DB80
0x18004db20  mov     ecx, edi; this
0x18004db22  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004db27  jmp     short loc_18004DB7E
0x18004db29  test    edi, edi
0x18004db2b  js      short loc_18004DB65
0x18004db2d  mov     edi, 8007029Ch
0x18004db32  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004db36  mov     rax, [rsp+78h+arg_28]
0x18004db3e  mov     [rsp+78h+var_50], rax; __int64
0x18004db43  mov     rax, [rsp+78h+arg_20]
0x18004db4b  mov     [rsp+78h+var_58], rax; __int64
0x18004db50  mov     rcx, r10; int
0x18004db53  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18004db58  mov     [rbx+8], edi
0x18004db5b  mov     ecx, edi; this
0x18004db5d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004db62  mov     [rbx+0Ch], eax
0x18004db65  mov     ecx, edi; this
0x18004db67  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004db6c  jmp     short loc_18004DB7E
0x18004db6e  mov     ecx, edi; this
0x18004db70  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004db75  jmp     short loc_18004DB7E
0x18004db77  mov     ecx, edi; this
0x18004db79  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004db7e  mov     ebp, eax
0x18004db80  mov     [rbx], r15d
0x18004db83  mov     eax, [rsp+78h+arg_70]
0x18004db8a  mov     [rbx+4], eax
0x18004db8d  cmp     dword ptr [r14+8], 1
0x18004db92  jnz     short loc_18004DB9A
0x18004db94  or      eax, 8
0x18004db97  mov     [rbx+4], eax
0x18004db9a  mov     eax, 1
0x18004db9f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004dba7  inc     eax
0x18004dba9  mov     [rbx+10h], eax
0x18004dbac  mov     rax, [rsp+78h+arg_40]
0x18004dbb4  xor     edi, edi
0x18004dbb6  test    rax, rax
0x18004dbb9  jz      short loc_18004DBC0
0x18004dbbb  cmp     [rax], di
0x18004dbbe  jnz     short loc_18004DBC3
0x18004dbc0  mov     rax, rdi
0x18004dbc3  mov     [rbx+18h], rax
0x18004dbc7  call    cs:__imp_GetCurrentThreadId
0x18004dbce  nop     dword ptr [rax+rax+00h]
0x18004dbd3  mov     [rbx+20h], eax
0x18004dbd6  mov     [rbx+38h], r13
0x18004dbda  mov     eax, [rsp+78h+arg_8]
0x18004dbe1  mov     [rbx+40h], eax
0x18004dbe4  mov     [rbx+44h], ebp
0x18004dbe7  mov     rax, [rsp+78h+arg_20]
0x18004dbef  mov     [rbx+28h], rax
0x18004dbf3  mov     [rbx+30h], r12
0x18004dbf7  mov     rax, [rsp+78h+arg_28]
0x18004dbff  mov     [rbx+88h], rax
0x18004dc06  mov     rax, [rsp+78h+arg_0]
0x18004dc0e  mov     [rbx+90h], rax
0x18004dc15  mov     [rbx+48h], rdi
0x18004dc19  xorps   xmm0, xmm0
0x18004dc1c  xor     eax, eax
0x18004dc1e  movups  xmmword ptr [rbx+68h], xmm0
0x18004dc22  mov     [rbx+78h], rax
0x18004dc26  movups  xmmword ptr [rbx+50h], xmm0
0x18004dc2a  mov     [rbx+60h], rax
0x18004dc2e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004dc35  test    rax, rax
0x18004dc38  jz      short loc_18004DC41
0x18004dc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc3f  jmp     short loc_18004DC44
0x18004dc41  mov     rax, rdi
0x18004dc44  mov     [rbx+80h], rax
0x18004dc4b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004dc52  test    rax, rax
0x18004dc55  jz      short loc_18004DC5F
0x18004dc57  mov     rcx, rbx
0x18004dc5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc5f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004dc66  test    rax, rax
0x18004dc69  jz      short loc_18004DC81
0x18004dc6b  mov     r8d, 400h
0x18004dc71  mov     rdx, [rsp+78h+arg_60]
0x18004dc79  mov     rcx, rbx
0x18004dc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc81  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004dc88  test    rax, rax
0x18004dc8b  jz      short loc_18004DC95
0x18004dc8d  mov     rcx, rbx
0x18004dc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dc95  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004dc9c  test    rax, rax
0x18004dc9f  jz      short loc_18004DCAF
0x18004dca1  test    byte ptr [rbx+4], 2
0x18004dca5  jnz     short loc_18004DCAF
0x18004dca7  mov     rcx, rbx
0x18004dcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dcaf  cmp     [rbx+8], edi
0x18004dcb2  jl      short loc_18004DCCE
0x18004dcb4  cmp     r15d, 3
0x18004dcb8  jnz     loc_18004DDAA
0x18004dcbe  mov     ecx, 8000FFFFh; this
0x18004dcc3  mov     [rbx+8], ecx
0x18004dcc6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004dccb  mov     [rbx+0Ch], eax
0x18004dcce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004dcd5  jnz     short loc_18004DCFC
0x18004dcd7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004dcde  test    rax, rax
0x18004dce1  jz      short loc_18004DCEC
0x18004dce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dce8  test    al, al
0x18004dcea  jmp     short loc_18004DCFA
0x18004dcec  call    cs:__imp_IsDebuggerPresent
0x18004dcf3  nop     dword ptr [rax+rax+00h]
0x18004dcf8  test    eax, eax
0x18004dcfa  jz      short loc_18004DD02
0x18004dcfc  test    byte ptr [rbx+4], 2
0x18004dd00  jz      short loc_18004DD26
0x18004dd02  mov     rax, cs:g_pfnResultLoggingCallback
0x18004dd09  test    rax, rax
0x18004dd0c  jz      short loc_18004DD70
0x18004dd0e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004dd15  jnz     short loc_18004DD70
0x18004dd17  xor     r8d, r8d
0x18004dd1a  xor     edx, edx
0x18004dd1c  mov     rcx, rbx
0x18004dd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd24  jmp     short loc_18004DD70
0x18004dd26  mov     ebp, 800h
0x18004dd2b  mov     rax, cs:g_pfnResultLoggingCallback
0x18004dd32  test    rax, rax
0x18004dd35  jz      short loc_18004DD4E
0x18004dd37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004dd3e  jnz     short loc_18004DD4E
0x18004dd40  mov     r8d, ebp
0x18004dd43  mov     rdx, rsi
0x18004dd46  mov     rcx, rbx
0x18004dd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd4e  cmp     [rsi], di
0x18004dd51  jnz     short loc_18004DD61
0x18004dd53  mov     r8, rbx; unsigned __int64
0x18004dd56  mov     rdx, rbp; unsigned __int16 *
0x18004dd59  mov     rcx, rsi; this
0x18004dd5c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004dd61  mov     rcx, rsi; lpOutputString
0x18004dd64  call    cs:__imp_OutputDebugStringW
0x18004dd6b  nop     dword ptr [rax+rax+00h]
0x18004dd70  test    byte ptr [rbx+4], 4
0x18004dd74  jnz     short loc_18004DD7F
0x18004dd76  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004dd7d  jz      short loc_18004DD91
0x18004dd7f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004dd86  test    rax, rax
0x18004dd89  jz      short loc_18004DD91
0x18004dd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dd90  nop
0x18004dd91  mov     rbx, [rsp+78h+arg_10]
0x18004dd99  add     rsp, 40h
0x18004dd9d  pop     r15
0x18004dd9f  pop     r14
0x18004dda1  pop     r13
0x18004dda3  pop     r12
0x18004dda5  pop     rdi
0x18004dda6  pop     rsi
0x18004dda7  pop     rbp
0x18004dda8  retn
0x18004ddaa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
