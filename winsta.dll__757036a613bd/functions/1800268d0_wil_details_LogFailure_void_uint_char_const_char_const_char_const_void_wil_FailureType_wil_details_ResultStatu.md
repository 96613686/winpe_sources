# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800268d0`
- end: `0x180026bc8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180024938`
- `0x180024c80`

## callees

- `0x180013bb8`
- `0x180024880`
- `0x180026314`
- `0x1800268d0`
- `0x180026ebc`
- `0x180026ee0`
- `0x180026ef4`
- `0x180026f10`
- `0x180027864`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800269f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800269f3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026b84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026b84`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026b12`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026b12`

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
0x1800268d0  mov     [rsp+arg_10], rbx
0x1800268d5  mov     [rsp+arg_8], edx
0x1800268d9  mov     [rsp+arg_0], rcx
0x1800268de  push    rbp
0x1800268df  push    rsi
0x1800268e0  push    rdi
0x1800268e1  push    r12
0x1800268e3  push    r13
0x1800268e5  push    r14
0x1800268e7  push    r15
0x1800268e9  sub     rsp, 40h
0x1800268ed  mov     r14, [rsp+78h+arg_38]
0x1800268f5  xor     eax, eax
0x1800268f7  mov     rbx, [rsp+78h+arg_78]
0x1800268ff  xor     ebp, ebp
0x180026901  mov     r15d, [rsp+78h+arg_30]
0x180026909  mov     r10, rcx
0x18002690c  mov     rsi, [rsp+78h+lpOutputString]
0x180026914  mov     r12, r9
0x180026917  mov     r13, r8
0x18002691a  mov     ecx, r15d
0x18002691d  mov     [rsi], ax
0x180026920  mov     rax, [rsp+78h+arg_60]
0x180026928  mov     byte ptr [rax], 0
0x18002692b  mov     edi, [r14]
0x18002692e  mov     [rbx+8], edi
0x180026931  mov     eax, [r14+4]
0x180026935  mov     [rbx+0Ch], eax
0x180026938  test    r15d, r15d
0x18002693b  jz      short loc_1800269A3
0x18002693d  sub     ecx, 1
0x180026940  jz      short loc_18002699A
0x180026942  sub     ecx, 1
0x180026945  jz      short loc_180026955
0x180026947  cmp     ecx, 1
0x18002694a  jnz     short loc_1800269AC
0x18002694c  mov     ecx, edi; this
0x18002694e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180026953  jmp     short loc_1800269AA
0x180026955  test    edi, edi
0x180026957  js      short loc_180026991
0x180026959  mov     rax, [rsp+78h+arg_28]
0x180026961  mov     edi, 8007029Ch
0x180026966  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002696a  mov     rcx, r10; int
0x18002696d  mov     [rsp+78h+var_50], rax; __int64
0x180026972  mov     rax, [rsp+78h+arg_20]
0x18002697a  mov     [rsp+78h+var_58], rax; __int64
0x18002697f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180026984  mov     ecx, edi; this
0x180026986  mov     [rbx+8], edi
0x180026989  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002698e  mov     [rbx+0Ch], eax
0x180026991  mov     ecx, edi; this
0x180026993  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180026998  jmp     short loc_1800269AA
0x18002699a  mov     ecx, edi; this
0x18002699c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800269a1  jmp     short loc_1800269AA
0x1800269a3  mov     ecx, edi; this
0x1800269a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800269aa  mov     ebp, eax
0x1800269ac  mov     eax, [rsp+78h+arg_70]
0x1800269b3  mov     [rbx+4], eax
0x1800269b6  mov     [rbx], r15d
0x1800269b9  cmp     dword ptr [r14+8], 1
0x1800269be  jnz     short loc_1800269C6
0x1800269c0  or      eax, 8
0x1800269c3  mov     [rbx+4], eax
0x1800269c6  mov     eax, 1
0x1800269cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800269d3  inc     eax
0x1800269d5  xor     edi, edi
0x1800269d7  mov     [rbx+10h], eax
0x1800269da  mov     rax, [rsp+78h+arg_40]
0x1800269e2  test    rax, rax
0x1800269e5  jz      short loc_1800269EC
0x1800269e7  cmp     [rax], di
0x1800269ea  jnz     short loc_1800269EF
0x1800269ec  mov     rax, rdi
0x1800269ef  mov     [rbx+18h], rax
0x1800269f3  call    cs:__imp_GetCurrentThreadId
0x1800269f9  mov     [rbx+38h], r13
0x1800269fd  xorps   xmm0, xmm0
0x180026a00  mov     [rbx+20h], eax
0x180026a03  mov     eax, [rsp+78h+arg_8]
0x180026a0a  mov     [rbx+40h], eax
0x180026a0d  mov     rax, [rsp+78h+arg_20]
0x180026a15  mov     [rbx+28h], rax
0x180026a19  mov     rax, [rsp+78h+arg_28]
0x180026a21  mov     [rbx+88h], rax
0x180026a28  mov     rax, [rsp+78h+arg_0]
0x180026a30  mov     [rbx+90h], rax
0x180026a37  xor     eax, eax
0x180026a39  mov     [rbx+44h], ebp
0x180026a3c  mov     [rbx+30h], r12
0x180026a40  mov     [rbx+48h], rdi
0x180026a44  movups  xmmword ptr [rbx+68h], xmm0
0x180026a48  mov     [rbx+78h], rax
0x180026a4c  movups  xmmword ptr [rbx+50h], xmm0
0x180026a50  mov     [rbx+60h], rax
0x180026a54  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180026a5b  test    rax, rax
0x180026a5e  jz      short loc_180026A67
0x180026a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a65  jmp     short loc_180026A6A
0x180026a67  mov     rax, rdi
0x180026a6a  mov     [rbx+80h], rax
0x180026a71  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180026a78  test    rax, rax
0x180026a7b  jz      short loc_180026A85
0x180026a7d  mov     rcx, rbx
0x180026a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a85  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180026a8c  test    rax, rax
0x180026a8f  jz      short loc_180026AA7
0x180026a91  mov     rdx, [rsp+78h+arg_60]
0x180026a99  mov     r8d, 400h
0x180026a9f  mov     rcx, rbx
0x180026aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aa7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026aae  test    rax, rax
0x180026ab1  jz      short loc_180026ABB
0x180026ab3  mov     rcx, rbx
0x180026ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026abb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026ac2  test    rax, rax
0x180026ac5  jz      short loc_180026AD5
0x180026ac7  test    byte ptr [rbx+4], 2
0x180026acb  jnz     short loc_180026AD5
0x180026acd  mov     rcx, rbx
0x180026ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ad5  cmp     [rbx+8], edi
0x180026ad8  jl      short loc_180026AF4
0x180026ada  cmp     r15d, 3
0x180026ade  jnz     loc_180026BC2
0x180026ae4  mov     ecx, 8000FFFFh; this
0x180026ae9  mov     [rbx+8], ecx
0x180026aec  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180026af1  mov     [rbx+0Ch], eax
0x180026af4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180026afb  jnz     short loc_180026B1C
0x180026afd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180026b04  test    rax, rax
0x180026b07  jz      short loc_180026B12
0x180026b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b0e  test    al, al
0x180026b10  jmp     short loc_180026B1A
0x180026b12  call    cs:__imp_IsDebuggerPresent
0x180026b18  test    eax, eax
0x180026b1a  jz      short loc_180026B22
0x180026b1c  test    byte ptr [rbx+4], 2
0x180026b20  jz      short loc_180026B46
0x180026b22  mov     rax, cs:g_pfnResultLoggingCallback
0x180026b29  test    rax, rax
0x180026b2c  jz      short loc_180026B8A
0x180026b2e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180026b35  jnz     short loc_180026B8A
0x180026b37  xor     r8d, r8d
0x180026b3a  xor     edx, edx
0x180026b3c  mov     rcx, rbx
0x180026b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b44  jmp     short loc_180026B8A
0x180026b46  mov     rax, cs:g_pfnResultLoggingCallback
0x180026b4d  mov     ebp, 800h
0x180026b52  test    rax, rax
0x180026b55  jz      short loc_180026B6E
0x180026b57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180026b5e  jnz     short loc_180026B6E
0x180026b60  mov     r8d, ebp
0x180026b63  mov     rdx, rsi
0x180026b66  mov     rcx, rbx
0x180026b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b6e  cmp     [rsi], di
0x180026b71  jnz     short loc_180026B81
0x180026b73  mov     r8, rbx; unsigned __int64
0x180026b76  mov     rdx, rbp; unsigned __int16 *
0x180026b79  mov     rcx, rsi; this
0x180026b7c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180026b81  mov     rcx, rsi; lpOutputString
0x180026b84  call    cs:__imp_OutputDebugStringW
0x180026b8a  test    byte ptr [rbx+4], 4
0x180026b8e  jnz     short loc_180026B99
0x180026b90  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180026b97  jz      short loc_180026BAA
0x180026b99  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180026ba0  test    rax, rax
0x180026ba3  jz      short loc_180026BAA
0x180026ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026baa  mov     rbx, [rsp+78h+arg_10]
0x180026bb2  add     rsp, 40h
0x180026bb6  pop     r15
0x180026bb8  pop     r14
0x180026bba  pop     r13
0x180026bbc  pop     r12
0x180026bbe  pop     rdi
0x180026bbf  pop     rsi
0x180026bc0  pop     rbp
0x180026bc1  retn
0x180026bc2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
