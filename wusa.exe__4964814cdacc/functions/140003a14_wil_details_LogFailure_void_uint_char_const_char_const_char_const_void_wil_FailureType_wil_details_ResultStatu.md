# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140003a14`
- end: `0x140003d0c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002444`

## callees

- `0x140001e88`
- `0x1400030b4`
- `0x140003850`
- `0x140003a14`
- `0x140003f5c`
- `0x140003f80`
- `0x140003f94`
- `0x140003fb0`
- `0x14000493c`
- `0x140015010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140003c56`
- `KERNEL32!IsDebuggerPresent` at `0x140003c56`
- `KERNEL32!OutputDebugStringW` at `0x140003cc8`
- `KERNEL32!OutputDebugStringW` at `0x140003cc8`
- `KERNEL32!GetCurrentThreadId` at `0x140003b37`
- `KERNEL32!GetCurrentThreadId` at `0x140003b37`

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
0x140003a14  mov     [rsp+arg_10], rbx
0x140003a19  mov     [rsp+arg_8], edx
0x140003a1d  mov     [rsp+arg_0], rcx
0x140003a22  push    rbp
0x140003a23  push    rsi
0x140003a24  push    rdi
0x140003a25  push    r12
0x140003a27  push    r13
0x140003a29  push    r14
0x140003a2b  push    r15
0x140003a2d  sub     rsp, 40h
0x140003a31  mov     r14, [rsp+78h+arg_38]
0x140003a39  xor     eax, eax
0x140003a3b  mov     rbx, [rsp+78h+arg_78]
0x140003a43  xor     ebp, ebp
0x140003a45  mov     r15d, [rsp+78h+arg_30]
0x140003a4d  mov     r10, rcx
0x140003a50  mov     rsi, [rsp+78h+lpOutputString]
0x140003a58  mov     r12, r9
0x140003a5b  mov     r13, r8
0x140003a5e  mov     ecx, r15d
0x140003a61  mov     [rsi], ax
0x140003a64  mov     rax, [rsp+78h+arg_60]
0x140003a6c  mov     byte ptr [rax], 0
0x140003a6f  mov     edi, [r14]
0x140003a72  mov     [rbx+8], edi
0x140003a75  mov     eax, [r14+4]
0x140003a79  mov     [rbx+0Ch], eax
0x140003a7c  test    r15d, r15d
0x140003a7f  jz      short loc_140003AE7
0x140003a81  sub     ecx, 1
0x140003a84  jz      short loc_140003ADE
0x140003a86  sub     ecx, 1
0x140003a89  jz      short loc_140003A99
0x140003a8b  cmp     ecx, 1
0x140003a8e  jnz     short loc_140003AF0
0x140003a90  mov     ecx, edi; this
0x140003a92  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003a97  jmp     short loc_140003AEE
0x140003a99  test    edi, edi
0x140003a9b  js      short loc_140003AD5
0x140003a9d  mov     rax, [rsp+78h+arg_28]
0x140003aa5  mov     edi, 8007029Ch
0x140003aaa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140003aae  mov     rcx, r10; int
0x140003ab1  mov     [rsp+78h+var_50], rax; __int64
0x140003ab6  mov     rax, [rsp+78h+arg_20]
0x140003abe  mov     [rsp+78h+var_58], rax; __int64
0x140003ac3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140003ac8  mov     ecx, edi; this
0x140003aca  mov     [rbx+8], edi
0x140003acd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003ad2  mov     [rbx+0Ch], eax
0x140003ad5  mov     ecx, edi; this
0x140003ad7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140003adc  jmp     short loc_140003AEE
0x140003ade  mov     ecx, edi; this
0x140003ae0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003ae5  jmp     short loc_140003AEE
0x140003ae7  mov     ecx, edi; this
0x140003ae9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140003aee  mov     ebp, eax
0x140003af0  mov     eax, [rsp+78h+arg_70]
0x140003af7  mov     [rbx+4], eax
0x140003afa  mov     [rbx], r15d
0x140003afd  cmp     dword ptr [r14+8], 1
0x140003b02  jnz     short loc_140003B0A
0x140003b04  or      eax, 8
0x140003b07  mov     [rbx+4], eax
0x140003b0a  mov     eax, 1
0x140003b0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003b17  inc     eax
0x140003b19  xor     edi, edi
0x140003b1b  mov     [rbx+10h], eax
0x140003b1e  mov     rax, [rsp+78h+arg_40]
0x140003b26  test    rax, rax
0x140003b29  jz      short loc_140003B30
0x140003b2b  cmp     [rax], di
0x140003b2e  jnz     short loc_140003B33
0x140003b30  mov     rax, rdi
0x140003b33  mov     [rbx+18h], rax
0x140003b37  call    cs:__imp_GetCurrentThreadId
0x140003b3d  mov     [rbx+38h], r13
0x140003b41  xorps   xmm0, xmm0
0x140003b44  mov     [rbx+20h], eax
0x140003b47  mov     eax, [rsp+78h+arg_8]
0x140003b4e  mov     [rbx+40h], eax
0x140003b51  mov     rax, [rsp+78h+arg_20]
0x140003b59  mov     [rbx+28h], rax
0x140003b5d  mov     rax, [rsp+78h+arg_28]
0x140003b65  mov     [rbx+88h], rax
0x140003b6c  mov     rax, [rsp+78h+arg_0]
0x140003b74  mov     [rbx+90h], rax
0x140003b7b  xor     eax, eax
0x140003b7d  mov     [rbx+44h], ebp
0x140003b80  mov     [rbx+30h], r12
0x140003b84  mov     [rbx+48h], rdi
0x140003b88  movups  xmmword ptr [rbx+68h], xmm0
0x140003b8c  mov     [rbx+78h], rax
0x140003b90  movups  xmmword ptr [rbx+50h], xmm0
0x140003b94  mov     [rbx+60h], rax
0x140003b98  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003b9f  test    rax, rax
0x140003ba2  jz      short loc_140003BAB
0x140003ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ba9  jmp     short loc_140003BAE
0x140003bab  mov     rax, rdi
0x140003bae  mov     [rbx+80h], rax
0x140003bb5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003bbc  test    rax, rax
0x140003bbf  jz      short loc_140003BC9
0x140003bc1  mov     rcx, rbx
0x140003bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bc9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003bd0  test    rax, rax
0x140003bd3  jz      short loc_140003BEB
0x140003bd5  mov     rdx, [rsp+78h+arg_60]
0x140003bdd  mov     r8d, 400h
0x140003be3  mov     rcx, rbx
0x140003be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003beb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003bf2  test    rax, rax
0x140003bf5  jz      short loc_140003BFF
0x140003bf7  mov     rcx, rbx
0x140003bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003c06  test    rax, rax
0x140003c09  jz      short loc_140003C19
0x140003c0b  test    byte ptr [rbx+4], 2
0x140003c0f  jnz     short loc_140003C19
0x140003c11  mov     rcx, rbx
0x140003c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c19  cmp     [rbx+8], edi
0x140003c1c  jl      short loc_140003C38
0x140003c1e  cmp     r15d, 3
0x140003c22  jnz     loc_140003D06
0x140003c28  mov     ecx, 8000FFFFh; this
0x140003c2d  mov     [rbx+8], ecx
0x140003c30  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003c35  mov     [rbx+0Ch], eax
0x140003c38  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140003c3f  jnz     short loc_140003C60
0x140003c41  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003c48  test    rax, rax
0x140003c4b  jz      short loc_140003C56
0x140003c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c52  test    al, al
0x140003c54  jmp     short loc_140003C5E
0x140003c56  call    cs:__imp_IsDebuggerPresent
0x140003c5c  test    eax, eax
0x140003c5e  jz      short loc_140003C66
0x140003c60  test    byte ptr [rbx+4], 2
0x140003c64  jz      short loc_140003C8A
0x140003c66  mov     rax, cs:g_pfnResultLoggingCallback
0x140003c6d  test    rax, rax
0x140003c70  jz      short loc_140003CCE
0x140003c72  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140003c79  jnz     short loc_140003CCE
0x140003c7b  xor     r8d, r8d
0x140003c7e  xor     edx, edx
0x140003c80  mov     rcx, rbx
0x140003c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c88  jmp     short loc_140003CCE
0x140003c8a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003c91  mov     ebp, 800h
0x140003c96  test    rax, rax
0x140003c99  jz      short loc_140003CB2
0x140003c9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140003ca2  jnz     short loc_140003CB2
0x140003ca4  mov     r8d, ebp
0x140003ca7  mov     rdx, rsi
0x140003caa  mov     rcx, rbx
0x140003cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cb2  cmp     [rsi], di
0x140003cb5  jnz     short loc_140003CC5
0x140003cb7  mov     r8, rbx; unsigned __int64
0x140003cba  mov     rdx, rbp; unsigned __int16 *
0x140003cbd  mov     rcx, rsi; this
0x140003cc0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003cc5  mov     rcx, rsi; lpOutputString
0x140003cc8  call    cs:__imp_OutputDebugStringW
0x140003cce  test    byte ptr [rbx+4], 4
0x140003cd2  jnz     short loc_140003CDD
0x140003cd4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140003cdb  jz      short loc_140003CEE
0x140003cdd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003ce4  test    rax, rax
0x140003ce7  jz      short loc_140003CEE
0x140003ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cee  mov     rbx, [rsp+78h+arg_10]
0x140003cf6  add     rsp, 40h
0x140003cfa  pop     r15
0x140003cfc  pop     r14
0x140003cfe  pop     r13
0x140003d00  pop     r12
0x140003d02  pop     rdi
0x140003d03  pop     rsi
0x140003d04  pop     rbp
0x140003d05  retn
0x140003d06  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
