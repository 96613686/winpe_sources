# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800878e8`
- end: `0x180087bef`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180085c50`
- `0x180085d00`
- `0x180085df8`

## callees

- `0x180071ccc`
- `0x180085ba4`
- `0x180086ff4`
- `0x1800878e8`
- `0x1800885a4`
- `0x1800885d0`
- `0x18008869c`
- `0x1800886bc`
- `0x180089914`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087a0b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180087b32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180087b32`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180087baa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180087baa`

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
0x1800878e8  mov     [rsp+arg_10], rbx
0x1800878ed  mov     [rsp+arg_8], edx
0x1800878f1  mov     [rsp+arg_0], rcx
0x1800878f6  push    rbp
0x1800878f7  push    rsi
0x1800878f8  push    rdi
0x1800878f9  push    r12
0x1800878fb  push    r13
0x1800878fd  push    r14
0x1800878ff  push    r15
0x180087901  sub     rsp, 40h
0x180087905  mov     r14, [rsp+78h+arg_38]
0x18008790d  xor     eax, eax
0x18008790f  mov     rbx, [rsp+78h+arg_78]
0x180087917  xor     ebp, ebp
0x180087919  mov     r15d, [rsp+78h+arg_30]
0x180087921  mov     r10, rcx
0x180087924  mov     rsi, [rsp+78h+lpOutputString]
0x18008792c  mov     r12, r9
0x18008792f  mov     r13, r8
0x180087932  mov     ecx, r15d
0x180087935  mov     [rsi], ax
0x180087938  mov     rax, [rsp+78h+arg_60]
0x180087940  mov     byte ptr [rax], 0
0x180087943  mov     edi, [r14]
0x180087946  mov     [rbx+8], edi
0x180087949  mov     eax, [r14+4]
0x18008794d  mov     [rbx+0Ch], eax
0x180087950  test    r15d, r15d
0x180087953  jz      short loc_1800879BB
0x180087955  sub     ecx, 1
0x180087958  jz      short loc_1800879B2
0x18008795a  sub     ecx, 1
0x18008795d  jz      short loc_18008796D
0x18008795f  cmp     ecx, 1
0x180087962  jnz     short loc_1800879C4
0x180087964  mov     ecx, edi; this
0x180087966  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18008796b  jmp     short loc_1800879C2
0x18008796d  test    edi, edi
0x18008796f  js      short loc_1800879A9
0x180087971  mov     rax, [rsp+78h+arg_28]
0x180087979  mov     edi, 8007029Ch
0x18008797e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180087982  mov     rcx, r10; int
0x180087985  mov     [rsp+78h+var_50], rax; __int64
0x18008798a  mov     rax, [rsp+78h+arg_20]
0x180087992  mov     [rsp+78h+var_58], rax; __int64
0x180087997  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18008799c  mov     ecx, edi; this
0x18008799e  mov     [rbx+8], edi
0x1800879a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800879a6  mov     [rbx+0Ch], eax
0x1800879a9  mov     ecx, edi; this
0x1800879ab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800879b0  jmp     short loc_1800879C2
0x1800879b2  mov     ecx, edi; this
0x1800879b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800879b9  jmp     short loc_1800879C2
0x1800879bb  mov     ecx, edi; this
0x1800879bd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800879c2  mov     ebp, eax
0x1800879c4  mov     eax, [rsp+78h+arg_70]
0x1800879cb  mov     [rbx+4], eax
0x1800879ce  mov     [rbx], r15d
0x1800879d1  cmp     dword ptr [r14+8], 1
0x1800879d6  jnz     short loc_1800879DE
0x1800879d8  or      eax, 8
0x1800879db  mov     [rbx+4], eax
0x1800879de  mov     eax, 1
0x1800879e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800879eb  inc     eax
0x1800879ed  xor     edi, edi
0x1800879ef  mov     [rbx+10h], eax
0x1800879f2  mov     rax, [rsp+78h+arg_40]
0x1800879fa  test    rax, rax
0x1800879fd  jz      short loc_180087A04
0x1800879ff  cmp     [rax], di
0x180087a02  jnz     short loc_180087A07
0x180087a04  mov     rax, rdi
0x180087a07  mov     [rbx+18h], rax
0x180087a0b  call    cs:__imp_GetCurrentThreadId
0x180087a12  nop     dword ptr [rax+rax+00h]
0x180087a17  mov     [rbx+38h], r13
0x180087a1b  xorps   xmm0, xmm0
0x180087a1e  mov     [rbx+20h], eax
0x180087a21  mov     eax, [rsp+78h+arg_8]
0x180087a28  mov     [rbx+40h], eax
0x180087a2b  mov     rax, [rsp+78h+arg_20]
0x180087a33  mov     [rbx+28h], rax
0x180087a37  mov     rax, [rsp+78h+arg_28]
0x180087a3f  mov     [rbx+88h], rax
0x180087a46  mov     rax, [rsp+78h+arg_0]
0x180087a4e  mov     [rbx+90h], rax
0x180087a55  xor     eax, eax
0x180087a57  mov     [rbx+44h], ebp
0x180087a5a  mov     [rbx+30h], r12
0x180087a5e  mov     [rbx+48h], rdi
0x180087a62  movups  xmmword ptr [rbx+68h], xmm0
0x180087a66  mov     [rbx+78h], rax
0x180087a6a  movups  xmmword ptr [rbx+50h], xmm0
0x180087a6e  mov     [rbx+60h], rax
0x180087a72  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180087a79  test    rax, rax
0x180087a7c  jz      short loc_180087A85
0x180087a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087a83  jmp     short loc_180087A88
0x180087a85  mov     rax, rdi
0x180087a88  mov     [rbx+80h], rax
0x180087a8f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180087a96  test    rax, rax
0x180087a99  jz      short loc_180087AA3
0x180087a9b  mov     rcx, rbx
0x180087a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087aa3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180087aaa  test    rax, rax
0x180087aad  jz      short loc_180087AC5
0x180087aaf  mov     rdx, [rsp+78h+arg_60]
0x180087ab7  mov     r8d, 400h
0x180087abd  mov     rcx, rbx
0x180087ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ac5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180087acc  test    rax, rax
0x180087acf  jz      short loc_180087AD9
0x180087ad1  mov     rcx, rbx
0x180087ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ad9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180087ae0  test    rax, rax
0x180087ae3  jz      short loc_180087AF3
0x180087ae5  test    byte ptr [rbx+4], 2
0x180087ae9  jnz     short loc_180087AF3
0x180087aeb  mov     rcx, rbx
0x180087aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087af3  cmp     [rbx+8], edi
0x180087af6  jl      short loc_180087B14
0x180087af8  cmp     r15d, 3
0x180087afc  jz      short loc_180087B04
0x180087afe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180087b04  mov     ecx, 8000FFFFh; this
0x180087b09  mov     [rbx+8], ecx
0x180087b0c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180087b11  mov     [rbx+0Ch], eax
0x180087b14  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180087b1b  jnz     short loc_180087B42
0x180087b1d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180087b24  test    rax, rax
0x180087b27  jz      short loc_180087B32
0x180087b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b2e  test    al, al
0x180087b30  jmp     short loc_180087B40
0x180087b32  call    cs:__imp_IsDebuggerPresent
0x180087b39  nop     dword ptr [rax+rax+00h]
0x180087b3e  test    eax, eax
0x180087b40  jz      short loc_180087B48
0x180087b42  test    byte ptr [rbx+4], 2
0x180087b46  jz      short loc_180087B6C
0x180087b48  mov     rax, cs:g_pfnResultLoggingCallback
0x180087b4f  test    rax, rax
0x180087b52  jz      short loc_180087BB6
0x180087b54  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180087b5b  jnz     short loc_180087BB6
0x180087b5d  xor     r8d, r8d
0x180087b60  xor     edx, edx
0x180087b62  mov     rcx, rbx
0x180087b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b6a  jmp     short loc_180087BB6
0x180087b6c  mov     rax, cs:g_pfnResultLoggingCallback
0x180087b73  mov     ebp, 800h
0x180087b78  test    rax, rax
0x180087b7b  jz      short loc_180087B94
0x180087b7d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180087b84  jnz     short loc_180087B94
0x180087b86  mov     r8d, ebp
0x180087b89  mov     rdx, rsi
0x180087b8c  mov     rcx, rbx
0x180087b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b94  cmp     [rsi], di
0x180087b97  jnz     short loc_180087BA7
0x180087b99  mov     r8, rbx; unsigned __int64
0x180087b9c  mov     rdx, rbp; unsigned __int16 *
0x180087b9f  mov     rcx, rsi; this
0x180087ba2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180087ba7  mov     rcx, rsi; lpOutputString
0x180087baa  call    cs:__imp_OutputDebugStringW
0x180087bb1  nop     dword ptr [rax+rax+00h]
0x180087bb6  test    byte ptr [rbx+4], 4
0x180087bba  jnz     short loc_180087BC5
0x180087bbc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180087bc3  jz      short loc_180087BD6
0x180087bc5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180087bcc  test    rax, rax
0x180087bcf  jz      short loc_180087BD6
0x180087bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087bd6  mov     rbx, [rsp+78h+arg_10]
0x180087bde  add     rsp, 40h
0x180087be2  pop     r15
0x180087be4  pop     r14
0x180087be6  pop     r13
0x180087be8  pop     r12
0x180087bea  pop     rdi
0x180087beb  pop     rsi
0x180087bec  pop     rbp
0x180087bed  retn
```
