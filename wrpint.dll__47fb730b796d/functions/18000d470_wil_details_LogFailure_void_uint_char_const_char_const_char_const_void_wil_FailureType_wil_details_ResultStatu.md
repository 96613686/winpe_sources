# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000d470`
- end: `0x18000d768`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000af30`

## callees

- `0x18000a974`
- `0x18000caf4`
- `0x18000d2ac`
- `0x18000d470`
- `0x18000dec4`
- `0x18000dee0`
- `0x18000e010`
- `0x18000e02c`
- `0x18000ff0c`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d593`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d724`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d724`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d6b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d6b2`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v24);
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
0x18000d470  mov     [rsp+arg_10], rbx
0x18000d475  mov     [rsp+arg_8], edx
0x18000d479  mov     [rsp+arg_0], rcx
0x18000d47e  push    rbp
0x18000d47f  push    rsi
0x18000d480  push    rdi
0x18000d481  push    r12
0x18000d483  push    r13
0x18000d485  push    r14
0x18000d487  push    r15
0x18000d489  sub     rsp, 40h
0x18000d48d  mov     r14, [rsp+78h+arg_38]
0x18000d495  xor     eax, eax
0x18000d497  mov     rbx, [rsp+78h+arg_78]
0x18000d49f  xor     ebp, ebp
0x18000d4a1  mov     r15d, [rsp+78h+arg_30]
0x18000d4a9  mov     r10, rcx
0x18000d4ac  mov     rsi, [rsp+78h+lpOutputString]
0x18000d4b4  mov     r12, r9
0x18000d4b7  mov     r13, r8
0x18000d4ba  mov     ecx, r15d
0x18000d4bd  mov     [rsi], ax
0x18000d4c0  mov     rax, [rsp+78h+arg_60]
0x18000d4c8  mov     byte ptr [rax], 0
0x18000d4cb  mov     edi, [r14]
0x18000d4ce  mov     [rbx+8], edi
0x18000d4d1  mov     eax, [r14+4]
0x18000d4d5  mov     [rbx+0Ch], eax
0x18000d4d8  test    r15d, r15d
0x18000d4db  jz      short loc_18000D543
0x18000d4dd  sub     ecx, 1
0x18000d4e0  jz      short loc_18000D53A
0x18000d4e2  sub     ecx, 1
0x18000d4e5  jz      short loc_18000D4F5
0x18000d4e7  cmp     ecx, 1
0x18000d4ea  jnz     short loc_18000D54C
0x18000d4ec  mov     ecx, edi; this
0x18000d4ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000d4f3  jmp     short loc_18000D54A
0x18000d4f5  test    edi, edi
0x18000d4f7  js      short loc_18000D531
0x18000d4f9  mov     rax, [rsp+78h+arg_28]
0x18000d501  mov     edi, 8007029Ch
0x18000d506  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000d50a  mov     rcx, r10; int
0x18000d50d  mov     [rsp+78h+var_50], rax; __int64
0x18000d512  mov     rax, [rsp+78h+arg_20]
0x18000d51a  mov     [rsp+78h+var_58], rax; __int64
0x18000d51f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d524  mov     ecx, edi; this
0x18000d526  mov     [rbx+8], edi
0x18000d529  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d52e  mov     [rbx+0Ch], eax
0x18000d531  mov     ecx, edi; this
0x18000d533  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000d538  jmp     short loc_18000D54A
0x18000d53a  mov     ecx, edi; this
0x18000d53c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d541  jmp     short loc_18000D54A
0x18000d543  mov     ecx, edi; this
0x18000d545  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d54a  mov     ebp, eax
0x18000d54c  mov     eax, [rsp+78h+arg_70]
0x18000d553  mov     [rbx+4], eax
0x18000d556  mov     [rbx], r15d
0x18000d559  cmp     dword ptr [r14+8], 1
0x18000d55e  jnz     short loc_18000D566
0x18000d560  or      eax, 8
0x18000d563  mov     [rbx+4], eax
0x18000d566  mov     eax, 1
0x18000d56b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d573  inc     eax
0x18000d575  xor     edi, edi
0x18000d577  mov     [rbx+10h], eax
0x18000d57a  mov     rax, [rsp+78h+arg_40]
0x18000d582  test    rax, rax
0x18000d585  jz      short loc_18000D58C
0x18000d587  cmp     [rax], di
0x18000d58a  jnz     short loc_18000D58F
0x18000d58c  mov     rax, rdi
0x18000d58f  mov     [rbx+18h], rax
0x18000d593  call    cs:__imp_GetCurrentThreadId
0x18000d599  mov     [rbx+38h], r13
0x18000d59d  xorps   xmm0, xmm0
0x18000d5a0  mov     [rbx+20h], eax
0x18000d5a3  mov     eax, [rsp+78h+arg_8]
0x18000d5aa  mov     [rbx+40h], eax
0x18000d5ad  mov     rax, [rsp+78h+arg_20]
0x18000d5b5  mov     [rbx+28h], rax
0x18000d5b9  mov     rax, [rsp+78h+arg_28]
0x18000d5c1  mov     [rbx+88h], rax
0x18000d5c8  mov     rax, [rsp+78h+arg_0]
0x18000d5d0  mov     [rbx+90h], rax
0x18000d5d7  xor     eax, eax
0x18000d5d9  mov     [rbx+44h], ebp
0x18000d5dc  mov     [rbx+30h], r12
0x18000d5e0  mov     [rbx+48h], rdi
0x18000d5e4  movups  xmmword ptr [rbx+68h], xmm0
0x18000d5e8  mov     [rbx+78h], rax
0x18000d5ec  movups  xmmword ptr [rbx+50h], xmm0
0x18000d5f0  mov     [rbx+60h], rax
0x18000d5f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d5fb  test    rax, rax
0x18000d5fe  jz      short loc_18000D607
0x18000d600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d605  jmp     short loc_18000D60A
0x18000d607  mov     rax, rdi
0x18000d60a  mov     [rbx+80h], rax
0x18000d611  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d618  test    rax, rax
0x18000d61b  jz      short loc_18000D625
0x18000d61d  mov     rcx, rbx
0x18000d620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d625  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d62c  test    rax, rax
0x18000d62f  jz      short loc_18000D647
0x18000d631  mov     rdx, [rsp+78h+arg_60]
0x18000d639  mov     r8d, 400h
0x18000d63f  mov     rcx, rbx
0x18000d642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d647  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d64e  test    rax, rax
0x18000d651  jz      short loc_18000D65B
0x18000d653  mov     rcx, rbx
0x18000d656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d65b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d662  test    rax, rax
0x18000d665  jz      short loc_18000D675
0x18000d667  test    byte ptr [rbx+4], 2
0x18000d66b  jnz     short loc_18000D675
0x18000d66d  mov     rcx, rbx
0x18000d670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d675  cmp     [rbx+8], edi
0x18000d678  jl      short loc_18000D694
0x18000d67a  cmp     r15d, 3
0x18000d67e  jnz     loc_18000D762
0x18000d684  mov     ecx, 8000FFFFh; this
0x18000d689  mov     [rbx+8], ecx
0x18000d68c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d691  mov     [rbx+0Ch], eax
0x18000d694  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000d69b  jnz     short loc_18000D6BC
0x18000d69d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d6a4  test    rax, rax
0x18000d6a7  jz      short loc_18000D6B2
0x18000d6a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ae  test    al, al
0x18000d6b0  jmp     short loc_18000D6BA
0x18000d6b2  call    cs:__imp_IsDebuggerPresent
0x18000d6b8  test    eax, eax
0x18000d6ba  jz      short loc_18000D6C2
0x18000d6bc  test    byte ptr [rbx+4], 2
0x18000d6c0  jz      short loc_18000D6E6
0x18000d6c2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d6c9  test    rax, rax
0x18000d6cc  jz      short loc_18000D72A
0x18000d6ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d6d5  jnz     short loc_18000D72A
0x18000d6d7  xor     r8d, r8d
0x18000d6da  xor     edx, edx
0x18000d6dc  mov     rcx, rbx
0x18000d6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6e4  jmp     short loc_18000D72A
0x18000d6e6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d6ed  mov     ebp, 800h
0x18000d6f2  test    rax, rax
0x18000d6f5  jz      short loc_18000D70E
0x18000d6f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000d6fe  jnz     short loc_18000D70E
0x18000d700  mov     r8d, ebp
0x18000d703  mov     rdx, rsi
0x18000d706  mov     rcx, rbx
0x18000d709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d70e  cmp     [rsi], di
0x18000d711  jnz     short loc_18000D721
0x18000d713  mov     r8, rbx; unsigned __int64
0x18000d716  mov     rdx, rbp; wchar_t *
0x18000d719  mov     rcx, rsi; this
0x18000d71c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000d721  mov     rcx, rsi; lpOutputString
0x18000d724  call    cs:__imp_OutputDebugStringW
0x18000d72a  test    byte ptr [rbx+4], 4
0x18000d72e  jnz     short loc_18000D739
0x18000d730  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000d737  jz      short loc_18000D74A
0x18000d739  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d740  test    rax, rax
0x18000d743  jz      short loc_18000D74A
0x18000d745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d74a  mov     rbx, [rsp+78h+arg_10]
0x18000d752  add     rsp, 40h
0x18000d756  pop     r15
0x18000d758  pop     r14
0x18000d75a  pop     r13
0x18000d75c  pop     r12
0x18000d75e  pop     rdi
0x18000d75f  pop     rsi
0x18000d760  pop     rbp
0x18000d761  retn
0x18000d762  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
