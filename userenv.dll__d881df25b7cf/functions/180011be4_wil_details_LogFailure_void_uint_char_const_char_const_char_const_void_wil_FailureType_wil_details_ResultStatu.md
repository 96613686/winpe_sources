# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011be4`
- end: `0x180011ef4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `784`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180010ef4`
- `0x180011264`

## callees

- `0x180009b7c`
- `0x18000dc88`
- `0x1800100d4`
- `0x180010530`
- `0x180011be4`
- `0x180012090`
- `0x1800120b0`
- `0x1800120d0`
- `0x180012780`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011d0b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011e30`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011e30`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011ea8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011ea8`

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
0x180011be4  mov     [rsp+arg_10], rbx
0x180011be9  mov     [rsp+arg_8], edx
0x180011bed  mov     [rsp+arg_0], rcx
0x180011bf2  push    rbp
0x180011bf3  push    rsi
0x180011bf4  push    rdi
0x180011bf5  push    r12
0x180011bf7  push    r13
0x180011bf9  push    r14
0x180011bfb  push    r15
0x180011bfd  sub     rsp, 40h
0x180011c01  mov     r12, r9
0x180011c04  mov     r13, r8
0x180011c07  mov     r10, rcx
0x180011c0a  xor     eax, eax
0x180011c0c  mov     rsi, [rsp+78h+lpOutputString]
0x180011c14  mov     [rsi], ax
0x180011c17  mov     rax, [rsp+78h+arg_60]
0x180011c1f  mov     byte ptr [rax], 0
0x180011c22  mov     r14, [rsp+78h+arg_38]
0x180011c2a  mov     edi, [r14]
0x180011c2d  mov     rbx, [rsp+78h+arg_78]
0x180011c35  mov     [rbx+8], edi
0x180011c38  mov     eax, [r14+4]
0x180011c3c  mov     [rbx+0Ch], eax
0x180011c3f  xor     ebp, ebp
0x180011c41  mov     r15d, [rsp+78h+arg_30]
0x180011c49  mov     ecx, r15d
0x180011c4c  test    r15d, r15d
0x180011c4f  jz      short loc_180011CBB
0x180011c51  sub     ecx, 1
0x180011c54  jz      short loc_180011CB2
0x180011c56  sub     ecx, 1
0x180011c59  jz      short loc_180011C69
0x180011c5b  cmp     ecx, 1
0x180011c5e  jnz     short loc_180011CC4
0x180011c60  mov     ecx, edi; this
0x180011c62  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011c67  jmp     short loc_180011CC2
0x180011c69  test    edi, edi
0x180011c6b  js      short loc_180011CA9
0x180011c6d  mov     [rsp+78h+var_40], ebp
0x180011c71  mov     edi, 8007029Ch
0x180011c76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011c7a  mov     rax, [rsp+78h+arg_28]
0x180011c82  mov     [rsp+78h+var_50], rax; __int64
0x180011c87  mov     rax, [rsp+78h+arg_20]
0x180011c8f  mov     [rsp+78h+var_58], rax; __int64
0x180011c94  mov     rcx, r10; int
0x180011c97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011c9c  mov     [rbx+8], edi
0x180011c9f  mov     ecx, edi; this
0x180011ca1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011ca6  mov     [rbx+0Ch], eax
0x180011ca9  mov     ecx, edi; this
0x180011cab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011cb0  jmp     short loc_180011CC2
0x180011cb2  mov     ecx, edi; this
0x180011cb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011cb9  jmp     short loc_180011CC2
0x180011cbb  mov     ecx, edi; this
0x180011cbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011cc2  mov     ebp, eax
0x180011cc4  mov     [rbx], r15d
0x180011cc7  mov     eax, [rsp+78h+arg_70]
0x180011cce  mov     [rbx+4], eax
0x180011cd1  cmp     dword ptr [r14+8], 1
0x180011cd6  jnz     short loc_180011CDE
0x180011cd8  or      eax, 8
0x180011cdb  mov     [rbx+4], eax
0x180011cde  mov     eax, 1
0x180011ce3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011ceb  inc     eax
0x180011ced  mov     [rbx+10h], eax
0x180011cf0  mov     rax, [rsp+78h+arg_40]
0x180011cf8  xor     edi, edi
0x180011cfa  test    rax, rax
0x180011cfd  jz      short loc_180011D04
0x180011cff  cmp     [rax], di
0x180011d02  jnz     short loc_180011D07
0x180011d04  mov     rax, rdi
0x180011d07  mov     [rbx+18h], rax
0x180011d0b  call    cs:__imp_GetCurrentThreadId
0x180011d12  nop     dword ptr [rax+rax+00h]
0x180011d17  mov     [rbx+20h], eax
0x180011d1a  mov     [rbx+38h], r13
0x180011d1e  mov     eax, [rsp+78h+arg_8]
0x180011d25  mov     [rbx+40h], eax
0x180011d28  mov     [rbx+44h], ebp
0x180011d2b  mov     rax, [rsp+78h+arg_20]
0x180011d33  mov     [rbx+28h], rax
0x180011d37  mov     [rbx+30h], r12
0x180011d3b  mov     rax, [rsp+78h+arg_28]
0x180011d43  mov     [rbx+88h], rax
0x180011d4a  mov     rax, [rsp+78h+arg_0]
0x180011d52  mov     [rbx+90h], rax
0x180011d59  mov     [rbx+48h], rdi
0x180011d5d  xorps   xmm0, xmm0
0x180011d60  xor     eax, eax
0x180011d62  movups  xmmword ptr [rbx+68h], xmm0
0x180011d66  mov     [rbx+78h], rax
0x180011d6a  movups  xmmword ptr [rbx+50h], xmm0
0x180011d6e  mov     [rbx+60h], rax
0x180011d72  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011d79  test    rax, rax
0x180011d7c  jz      short loc_180011D85
0x180011d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d83  jmp     short loc_180011D88
0x180011d85  mov     rax, rdi
0x180011d88  mov     [rbx+80h], rax
0x180011d8f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011d96  test    rax, rax
0x180011d99  jz      short loc_180011DA3
0x180011d9b  mov     rcx, rbx
0x180011d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011daa  test    rax, rax
0x180011dad  jz      short loc_180011DC5
0x180011daf  mov     r8d, 400h
0x180011db5  mov     rdx, [rsp+78h+arg_60]
0x180011dbd  mov     rcx, rbx
0x180011dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011dcc  test    rax, rax
0x180011dcf  jz      short loc_180011DD9
0x180011dd1  mov     rcx, rbx
0x180011dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dd9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011de0  test    rax, rax
0x180011de3  jz      short loc_180011DF3
0x180011de5  test    byte ptr [rbx+4], 2
0x180011de9  jnz     short loc_180011DF3
0x180011deb  mov     rcx, rbx
0x180011dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011df3  cmp     [rbx+8], edi
0x180011df6  jl      short loc_180011E12
0x180011df8  cmp     r15d, 3
0x180011dfc  jnz     loc_180011EEE
0x180011e02  mov     ecx, 8000FFFFh; this
0x180011e07  mov     [rbx+8], ecx
0x180011e0a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011e0f  mov     [rbx+0Ch], eax
0x180011e12  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180011e19  jnz     short loc_180011E40
0x180011e1b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011e22  test    rax, rax
0x180011e25  jz      short loc_180011E30
0x180011e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e2c  test    al, al
0x180011e2e  jmp     short loc_180011E3E
0x180011e30  call    cs:__imp_IsDebuggerPresent
0x180011e37  nop     dword ptr [rax+rax+00h]
0x180011e3c  test    eax, eax
0x180011e3e  jz      short loc_180011E46
0x180011e40  test    byte ptr [rbx+4], 2
0x180011e44  jz      short loc_180011E6A
0x180011e46  mov     rax, cs:g_pfnResultLoggingCallback
0x180011e4d  test    rax, rax
0x180011e50  jz      short loc_180011EB4
0x180011e52  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011e59  jnz     short loc_180011EB4
0x180011e5b  xor     r8d, r8d
0x180011e5e  xor     edx, edx
0x180011e60  mov     rcx, rbx
0x180011e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e68  jmp     short loc_180011EB4
0x180011e6a  mov     ebp, 800h
0x180011e6f  mov     rax, cs:g_pfnResultLoggingCallback
0x180011e76  test    rax, rax
0x180011e79  jz      short loc_180011E92
0x180011e7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011e82  jnz     short loc_180011E92
0x180011e84  mov     r8d, ebp
0x180011e87  mov     rdx, rsi
0x180011e8a  mov     rcx, rbx
0x180011e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e92  cmp     [rsi], di
0x180011e95  jnz     short loc_180011EA5
0x180011e97  mov     r8, rbx; unsigned __int64
0x180011e9a  mov     rdx, rbp; unsigned __int16 *
0x180011e9d  mov     rcx, rsi; this
0x180011ea0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011ea5  mov     rcx, rsi; lpOutputString
0x180011ea8  call    cs:__imp_OutputDebugStringW
0x180011eaf  nop     dword ptr [rax+rax+00h]
0x180011eb4  test    byte ptr [rbx+4], 4
0x180011eb8  jnz     short loc_180011EC3
0x180011eba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011ec1  jz      short loc_180011ED5
0x180011ec3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011eca  test    rax, rax
0x180011ecd  jz      short loc_180011ED5
0x180011ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed4  nop
0x180011ed5  mov     rbx, [rsp+78h+arg_10]
0x180011edd  add     rsp, 40h
0x180011ee1  pop     r15
0x180011ee3  pop     r14
0x180011ee5  pop     r13
0x180011ee7  pop     r12
0x180011ee9  pop     rdi
0x180011eea  pop     rsi
0x180011eeb  pop     rbp
0x180011eec  retn
0x180011eee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
