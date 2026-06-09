# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001d4e4`
- end: `0x18001d7dc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180014bd8`

## callees

- `0x180014614`
- `0x18001c244`
- `0x18001ccd8`
- `0x18001d4e4`
- `0x18001fa74`
- `0x18001fa90`
- `0x18001faa4`
- `0x18001fac0`
- `0x180026f7c`
- `0x18002b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18001d798`
- `KERNEL32!OutputDebugStringW` at `0x18001d798`
- `KERNEL32!IsDebuggerPresent` at `0x18001d726`
- `KERNEL32!IsDebuggerPresent` at `0x18001d726`
- `KERNEL32!GetCurrentThreadId` at `0x18001d607`
- `KERNEL32!GetCurrentThreadId` at `0x18001d607`

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
0x18001d4e4  mov     [rsp+arg_10], rbx
0x18001d4e9  mov     [rsp+arg_8], edx
0x18001d4ed  mov     [rsp+arg_0], rcx
0x18001d4f2  push    rbp
0x18001d4f3  push    rsi
0x18001d4f4  push    rdi
0x18001d4f5  push    r12
0x18001d4f7  push    r13
0x18001d4f9  push    r14
0x18001d4fb  push    r15
0x18001d4fd  sub     rsp, 40h
0x18001d501  mov     r14, [rsp+78h+arg_38]
0x18001d509  xor     eax, eax
0x18001d50b  mov     rbx, [rsp+78h+arg_78]
0x18001d513  xor     ebp, ebp
0x18001d515  mov     r15d, [rsp+78h+arg_30]
0x18001d51d  mov     r10, rcx
0x18001d520  mov     rsi, [rsp+78h+lpOutputString]
0x18001d528  mov     r12, r9
0x18001d52b  mov     r13, r8
0x18001d52e  mov     ecx, r15d
0x18001d531  mov     [rsi], ax
0x18001d534  mov     rax, [rsp+78h+arg_60]
0x18001d53c  mov     byte ptr [rax], 0
0x18001d53f  mov     edi, [r14]
0x18001d542  mov     [rbx+8], edi
0x18001d545  mov     eax, [r14+4]
0x18001d549  mov     [rbx+0Ch], eax
0x18001d54c  test    r15d, r15d
0x18001d54f  jz      short loc_18001D5B7
0x18001d551  sub     ecx, 1
0x18001d554  jz      short loc_18001D5AE
0x18001d556  sub     ecx, 1
0x18001d559  jz      short loc_18001D569
0x18001d55b  cmp     ecx, 1
0x18001d55e  jnz     short loc_18001D5C0
0x18001d560  mov     ecx, edi; this
0x18001d562  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001d567  jmp     short loc_18001D5BE
0x18001d569  test    edi, edi
0x18001d56b  js      short loc_18001D5A5
0x18001d56d  mov     rax, [rsp+78h+arg_28]
0x18001d575  mov     edi, 8007029Ch
0x18001d57a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001d57e  mov     rcx, r10; int
0x18001d581  mov     [rsp+78h+var_50], rax; __int64
0x18001d586  mov     rax, [rsp+78h+arg_20]
0x18001d58e  mov     [rsp+78h+var_58], rax; __int64
0x18001d593  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001d598  mov     ecx, edi; this
0x18001d59a  mov     [rbx+8], edi
0x18001d59d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d5a2  mov     [rbx+0Ch], eax
0x18001d5a5  mov     ecx, edi; this
0x18001d5a7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001d5ac  jmp     short loc_18001D5BE
0x18001d5ae  mov     ecx, edi; this
0x18001d5b0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001d5b5  jmp     short loc_18001D5BE
0x18001d5b7  mov     ecx, edi; this
0x18001d5b9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001d5be  mov     ebp, eax
0x18001d5c0  mov     eax, [rsp+78h+arg_70]
0x18001d5c7  mov     [rbx+4], eax
0x18001d5ca  mov     [rbx], r15d
0x18001d5cd  cmp     dword ptr [r14+8], 1
0x18001d5d2  jnz     short loc_18001D5DA
0x18001d5d4  or      eax, 8
0x18001d5d7  mov     [rbx+4], eax
0x18001d5da  mov     eax, 1
0x18001d5df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d5e7  inc     eax
0x18001d5e9  xor     edi, edi
0x18001d5eb  mov     [rbx+10h], eax
0x18001d5ee  mov     rax, [rsp+78h+arg_40]
0x18001d5f6  test    rax, rax
0x18001d5f9  jz      short loc_18001D600
0x18001d5fb  cmp     [rax], di
0x18001d5fe  jnz     short loc_18001D603
0x18001d600  mov     rax, rdi
0x18001d603  mov     [rbx+18h], rax
0x18001d607  call    cs:__imp_GetCurrentThreadId
0x18001d60d  mov     [rbx+38h], r13
0x18001d611  xorps   xmm0, xmm0
0x18001d614  mov     [rbx+20h], eax
0x18001d617  mov     eax, [rsp+78h+arg_8]
0x18001d61e  mov     [rbx+40h], eax
0x18001d621  mov     rax, [rsp+78h+arg_20]
0x18001d629  mov     [rbx+28h], rax
0x18001d62d  mov     rax, [rsp+78h+arg_28]
0x18001d635  mov     [rbx+88h], rax
0x18001d63c  mov     rax, [rsp+78h+arg_0]
0x18001d644  mov     [rbx+90h], rax
0x18001d64b  xor     eax, eax
0x18001d64d  mov     [rbx+44h], ebp
0x18001d650  mov     [rbx+30h], r12
0x18001d654  mov     [rbx+48h], rdi
0x18001d658  movups  xmmword ptr [rbx+68h], xmm0
0x18001d65c  mov     [rbx+78h], rax
0x18001d660  movups  xmmword ptr [rbx+50h], xmm0
0x18001d664  mov     [rbx+60h], rax
0x18001d668  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d66f  test    rax, rax
0x18001d672  jz      short loc_18001D67B
0x18001d674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d679  jmp     short loc_18001D67E
0x18001d67b  mov     rax, rdi
0x18001d67e  mov     [rbx+80h], rax
0x18001d685  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d68c  test    rax, rax
0x18001d68f  jz      short loc_18001D699
0x18001d691  mov     rcx, rbx
0x18001d694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d699  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d6a0  test    rax, rax
0x18001d6a3  jz      short loc_18001D6BB
0x18001d6a5  mov     rdx, [rsp+78h+arg_60]
0x18001d6ad  mov     r8d, 400h
0x18001d6b3  mov     rcx, rbx
0x18001d6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6bb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d6c2  test    rax, rax
0x18001d6c5  jz      short loc_18001D6CF
0x18001d6c7  mov     rcx, rbx
0x18001d6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d6d6  test    rax, rax
0x18001d6d9  jz      short loc_18001D6E9
0x18001d6db  test    byte ptr [rbx+4], 2
0x18001d6df  jnz     short loc_18001D6E9
0x18001d6e1  mov     rcx, rbx
0x18001d6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6e9  cmp     [rbx+8], edi
0x18001d6ec  jl      short loc_18001D708
0x18001d6ee  cmp     r15d, 3
0x18001d6f2  jnz     loc_18001D7D6
0x18001d6f8  mov     ecx, 8000FFFFh; this
0x18001d6fd  mov     [rbx+8], ecx
0x18001d700  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d705  mov     [rbx+0Ch], eax
0x18001d708  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001d70f  jnz     short loc_18001D730
0x18001d711  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d718  test    rax, rax
0x18001d71b  jz      short loc_18001D726
0x18001d71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d722  test    al, al
0x18001d724  jmp     short loc_18001D72E
0x18001d726  call    cs:__imp_IsDebuggerPresent
0x18001d72c  test    eax, eax
0x18001d72e  jz      short loc_18001D736
0x18001d730  test    byte ptr [rbx+4], 2
0x18001d734  jz      short loc_18001D75A
0x18001d736  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d73d  test    rax, rax
0x18001d740  jz      short loc_18001D79E
0x18001d742  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d749  jnz     short loc_18001D79E
0x18001d74b  xor     r8d, r8d
0x18001d74e  xor     edx, edx
0x18001d750  mov     rcx, rbx
0x18001d753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d758  jmp     short loc_18001D79E
0x18001d75a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d761  mov     ebp, 800h
0x18001d766  test    rax, rax
0x18001d769  jz      short loc_18001D782
0x18001d76b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d772  jnz     short loc_18001D782
0x18001d774  mov     r8d, ebp
0x18001d777  mov     rdx, rsi
0x18001d77a  mov     rcx, rbx
0x18001d77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d782  cmp     [rsi], di
0x18001d785  jnz     short loc_18001D795
0x18001d787  mov     r8, rbx; unsigned __int64
0x18001d78a  mov     rdx, rbp; unsigned __int16 *
0x18001d78d  mov     rcx, rsi; this
0x18001d790  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d795  mov     rcx, rsi; lpOutputString
0x18001d798  call    cs:__imp_OutputDebugStringW
0x18001d79e  test    byte ptr [rbx+4], 4
0x18001d7a2  jnz     short loc_18001D7AD
0x18001d7a4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001d7ab  jz      short loc_18001D7BE
0x18001d7ad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d7b4  test    rax, rax
0x18001d7b7  jz      short loc_18001D7BE
0x18001d7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7be  mov     rbx, [rsp+78h+arg_10]
0x18001d7c6  add     rsp, 40h
0x18001d7ca  pop     r15
0x18001d7cc  pop     r14
0x18001d7ce  pop     r13
0x18001d7d0  pop     r12
0x18001d7d2  pop     rdi
0x18001d7d3  pop     rsi
0x18001d7d4  pop     rbp
0x18001d7d5  retn
0x18001d7d6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
