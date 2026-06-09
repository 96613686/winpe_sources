# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008b20`
- end: `0x180008e2b`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002818`

## callees

- `0x180002230`
- `0x180005798`
- `0x180007fbc`
- `0x180008b20`
- `0x18000b188`
- `0x18000b1b0`
- `0x18000b1c4`
- `0x18000b1e4`
- `0x18000d7b4`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008c43`
- `KERNEL32!GetCurrentThreadId` at `0x180008c43`
- `KERNEL32!IsDebuggerPresent` at `0x180008d68`
- `KERNEL32!IsDebuggerPresent` at `0x180008d68`
- `KERNEL32!OutputDebugStringW` at `0x180008de0`
- `KERNEL32!OutputDebugStringW` at `0x180008de0`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x180008b20  mov     [rsp+arg_10], rbx
0x180008b25  mov     [rsp+arg_8], edx
0x180008b29  mov     [rsp+arg_0], rcx
0x180008b2e  push    rbp
0x180008b2f  push    rsi
0x180008b30  push    rdi
0x180008b31  push    r12
0x180008b33  push    r13
0x180008b35  push    r14
0x180008b37  push    r15
0x180008b39  sub     rsp, 40h
0x180008b3d  mov     r14, [rsp+78h+arg_38]
0x180008b45  xor     eax, eax
0x180008b47  mov     rbx, [rsp+78h+arg_78]
0x180008b4f  xor     ebp, ebp
0x180008b51  mov     r15d, [rsp+78h+arg_30]
0x180008b59  mov     r10, rcx
0x180008b5c  mov     rsi, [rsp+78h+lpOutputString]
0x180008b64  mov     r12, r9
0x180008b67  mov     r13, r8
0x180008b6a  mov     ecx, r15d
0x180008b6d  mov     [rsi], ax
0x180008b70  mov     rax, [rsp+78h+arg_60]
0x180008b78  mov     byte ptr [rax], 0
0x180008b7b  mov     edi, [r14]
0x180008b7e  mov     [rbx+8], edi
0x180008b81  mov     eax, [r14+4]
0x180008b85  mov     [rbx+0Ch], eax
0x180008b88  test    r15d, r15d
0x180008b8b  jz      short loc_180008BF3
0x180008b8d  sub     ecx, 1
0x180008b90  jz      short loc_180008BEA
0x180008b92  sub     ecx, 1
0x180008b95  jz      short loc_180008BA5
0x180008b97  cmp     ecx, 1
0x180008b9a  jnz     short loc_180008BFC
0x180008b9c  mov     ecx, edi; this
0x180008b9e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008ba3  jmp     short loc_180008BFA
0x180008ba5  test    edi, edi
0x180008ba7  js      short loc_180008BE1
0x180008ba9  mov     rax, [rsp+78h+arg_28]
0x180008bb1  mov     edi, 8007029Ch
0x180008bb6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008bba  mov     rcx, r10; int
0x180008bbd  mov     [rsp+78h+var_50], rax; __int64
0x180008bc2  mov     rax, [rsp+78h+arg_20]
0x180008bca  mov     [rsp+78h+var_58], rax; __int64
0x180008bcf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008bd4  mov     ecx, edi; this
0x180008bd6  mov     [rbx+8], edi
0x180008bd9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008bde  mov     [rbx+0Ch], eax
0x180008be1  mov     ecx, edi; this
0x180008be3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008be8  jmp     short loc_180008BFA
0x180008bea  mov     ecx, edi; this
0x180008bec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008bf1  jmp     short loc_180008BFA
0x180008bf3  mov     ecx, edi; this
0x180008bf5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008bfa  mov     ebp, eax
0x180008bfc  mov     eax, [rsp+78h+arg_70]
0x180008c03  mov     [rbx+4], eax
0x180008c06  mov     [rbx], r15d
0x180008c09  cmp     dword ptr [r14+8], 1
0x180008c0e  jnz     short loc_180008C16
0x180008c10  or      eax, 8
0x180008c13  mov     [rbx+4], eax
0x180008c16  mov     eax, 1
0x180008c1b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008c23  inc     eax
0x180008c25  xor     edi, edi
0x180008c27  mov     [rbx+10h], eax
0x180008c2a  mov     rax, [rsp+78h+arg_40]
0x180008c32  test    rax, rax
0x180008c35  jz      short loc_180008C3C
0x180008c37  cmp     [rax], di
0x180008c3a  jnz     short loc_180008C3F
0x180008c3c  mov     rax, rdi
0x180008c3f  mov     [rbx+18h], rax
0x180008c43  call    cs:__imp_GetCurrentThreadId
0x180008c4a  nop     dword ptr [rax+rax+00h]
0x180008c4f  mov     [rbx+38h], r13
0x180008c53  xorps   xmm0, xmm0
0x180008c56  mov     [rbx+20h], eax
0x180008c59  mov     eax, [rsp+78h+arg_8]
0x180008c60  mov     [rbx+40h], eax
0x180008c63  mov     rax, [rsp+78h+arg_20]
0x180008c6b  mov     [rbx+28h], rax
0x180008c6f  mov     rax, [rsp+78h+arg_28]
0x180008c77  mov     [rbx+88h], rax
0x180008c7e  mov     rax, [rsp+78h+arg_0]
0x180008c86  mov     [rbx+90h], rax
0x180008c8d  xor     eax, eax
0x180008c8f  mov     [rbx+44h], ebp
0x180008c92  mov     [rbx+30h], r12
0x180008c96  mov     [rbx+48h], rdi
0x180008c9a  movups  xmmword ptr [rbx+68h], xmm0
0x180008c9e  mov     [rbx+78h], rax
0x180008ca2  movups  xmmword ptr [rbx+50h], xmm0
0x180008ca6  mov     [rbx+60h], rax
0x180008caa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008cb1  test    rax, rax
0x180008cb4  jz      short loc_180008CBD
0x180008cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cbb  jmp     short loc_180008CC0
0x180008cbd  mov     rax, rdi
0x180008cc0  mov     [rbx+80h], rax
0x180008cc7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008cce  test    rax, rax
0x180008cd1  jz      short loc_180008CDB
0x180008cd3  mov     rcx, rbx
0x180008cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008ce2  test    rax, rax
0x180008ce5  jz      short loc_180008CFD
0x180008ce7  mov     rdx, [rsp+78h+arg_60]
0x180008cef  mov     r8d, 400h
0x180008cf5  mov     rcx, rbx
0x180008cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008d04  test    rax, rax
0x180008d07  jz      short loc_180008D11
0x180008d09  mov     rcx, rbx
0x180008d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d11  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008d18  test    rax, rax
0x180008d1b  jz      short loc_180008D2B
0x180008d1d  test    byte ptr [rbx+4], 2
0x180008d21  jnz     short loc_180008D2B
0x180008d23  mov     rcx, rbx
0x180008d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d2b  cmp     [rbx+8], edi
0x180008d2e  jl      short loc_180008D4A
0x180008d30  cmp     r15d, 3
0x180008d34  jnz     loc_180008E25
0x180008d3a  mov     ecx, 8000FFFFh; this
0x180008d3f  mov     [rbx+8], ecx
0x180008d42  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008d47  mov     [rbx+0Ch], eax
0x180008d4a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008d51  jnz     short loc_180008D78
0x180008d53  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008d5a  test    rax, rax
0x180008d5d  jz      short loc_180008D68
0x180008d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d64  test    al, al
0x180008d66  jmp     short loc_180008D76
0x180008d68  call    cs:__imp_IsDebuggerPresent
0x180008d6f  nop     dword ptr [rax+rax+00h]
0x180008d74  test    eax, eax
0x180008d76  jz      short loc_180008D7E
0x180008d78  test    byte ptr [rbx+4], 2
0x180008d7c  jz      short loc_180008DA2
0x180008d7e  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d85  test    rax, rax
0x180008d88  jz      short loc_180008DEC
0x180008d8a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008d91  jnz     short loc_180008DEC
0x180008d93  xor     r8d, r8d
0x180008d96  xor     edx, edx
0x180008d98  mov     rcx, rbx
0x180008d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da0  jmp     short loc_180008DEC
0x180008da2  mov     rax, cs:g_pfnResultLoggingCallback
0x180008da9  mov     ebp, 800h
0x180008dae  test    rax, rax
0x180008db1  jz      short loc_180008DCA
0x180008db3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008dba  jnz     short loc_180008DCA
0x180008dbc  mov     r8d, ebp
0x180008dbf  mov     rdx, rsi
0x180008dc2  mov     rcx, rbx
0x180008dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dca  cmp     [rsi], di
0x180008dcd  jnz     short loc_180008DDD
0x180008dcf  mov     r8, rbx; unsigned __int64
0x180008dd2  mov     rdx, rbp; unsigned __int16 *
0x180008dd5  mov     rcx, rsi; this
0x180008dd8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008ddd  mov     rcx, rsi; lpOutputString
0x180008de0  call    cs:__imp_OutputDebugStringW
0x180008de7  nop     dword ptr [rax+rax+00h]
0x180008dec  test    byte ptr [rbx+4], 4
0x180008df0  jnz     short loc_180008DFB
0x180008df2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008df9  jz      short loc_180008E0C
0x180008dfb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008e02  test    rax, rax
0x180008e05  jz      short loc_180008E0C
0x180008e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0c  mov     rbx, [rsp+78h+arg_10]
0x180008e14  add     rsp, 40h
0x180008e18  pop     r15
0x180008e1a  pop     r14
0x180008e1c  pop     r13
0x180008e1e  pop     r12
0x180008e20  pop     rdi
0x180008e21  pop     rsi
0x180008e22  pop     rbp
0x180008e23  retn
0x180008e25  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
