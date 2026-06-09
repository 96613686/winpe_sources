# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002166c`
- end: `0x180021965`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001ff1c`
- `0x180020288`
- `0x1800307ac`

## callees

- `0x18001383c`
- `0x18001fe54`
- `0x180020e64`
- `0x18002166c`
- `0x180021bbc`
- `0x180021be0`
- `0x180021bf4`
- `0x180021c10`
- `0x180022894`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800218ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800218ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021920`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180021920`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002178f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002178f`

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
0x18002166c  mov     [rsp+arg_10], rbx
0x180021671  mov     [rsp+arg_8], edx
0x180021675  mov     [rsp+arg_0], rcx
0x18002167a  push    rbp
0x18002167b  push    rsi
0x18002167c  push    rdi
0x18002167d  push    r12
0x18002167f  push    r13
0x180021681  push    r14
0x180021683  push    r15
0x180021685  sub     rsp, 40h
0x180021689  mov     r12, r9
0x18002168c  mov     r13, r8
0x18002168f  mov     r10, rcx
0x180021692  xor     eax, eax
0x180021694  mov     rsi, [rsp+78h+lpOutputString]
0x18002169c  mov     [rsi], ax
0x18002169f  mov     rax, [rsp+78h+arg_60]
0x1800216a7  mov     byte ptr [rax], 0
0x1800216aa  mov     r14, [rsp+78h+arg_38]
0x1800216b2  mov     edi, [r14]
0x1800216b5  mov     rbx, [rsp+78h+arg_78]
0x1800216bd  mov     [rbx+8], edi
0x1800216c0  mov     eax, [r14+4]
0x1800216c4  mov     [rbx+0Ch], eax
0x1800216c7  xor     ebp, ebp
0x1800216c9  mov     r15d, [rsp+78h+arg_30]
0x1800216d1  mov     ecx, r15d
0x1800216d4  test    r15d, r15d
0x1800216d7  jz      short loc_18002173F
0x1800216d9  sub     ecx, 1
0x1800216dc  jz      short loc_180021736
0x1800216de  sub     ecx, 1
0x1800216e1  jz      short loc_1800216F1
0x1800216e3  cmp     ecx, 1
0x1800216e6  jnz     short loc_180021748
0x1800216e8  mov     ecx, edi; this
0x1800216ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800216ef  jmp     short loc_180021746
0x1800216f1  test    edi, edi
0x1800216f3  js      short loc_18002172D
0x1800216f5  mov     edi, 8007029Ch
0x1800216fa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800216fe  mov     rax, [rsp+78h+arg_28]
0x180021706  mov     [rsp+78h+var_50], rax; __int64
0x18002170b  mov     rax, [rsp+78h+arg_20]
0x180021713  mov     [rsp+78h+var_58], rax; __int64
0x180021718  mov     rcx, r10; int
0x18002171b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180021720  mov     [rbx+8], edi
0x180021723  mov     ecx, edi; this
0x180021725  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002172a  mov     [rbx+0Ch], eax
0x18002172d  mov     ecx, edi; this
0x18002172f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180021734  jmp     short loc_180021746
0x180021736  mov     ecx, edi; this
0x180021738  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002173d  jmp     short loc_180021746
0x18002173f  mov     ecx, edi; this
0x180021741  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180021746  mov     ebp, eax
0x180021748  mov     [rbx], r15d
0x18002174b  mov     eax, [rsp+78h+arg_70]
0x180021752  mov     [rbx+4], eax
0x180021755  cmp     dword ptr [r14+8], 1
0x18002175a  jnz     short loc_180021762
0x18002175c  or      eax, 8
0x18002175f  mov     [rbx+4], eax
0x180021762  mov     eax, 1
0x180021767  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002176f  inc     eax
0x180021771  mov     [rbx+10h], eax
0x180021774  mov     rax, [rsp+78h+arg_40]
0x18002177c  xor     edi, edi
0x18002177e  test    rax, rax
0x180021781  jz      short loc_180021788
0x180021783  cmp     [rax], di
0x180021786  jnz     short loc_18002178B
0x180021788  mov     rax, rdi
0x18002178b  mov     [rbx+18h], rax
0x18002178f  call    cs:__imp_GetCurrentThreadId
0x180021795  mov     [rbx+20h], eax
0x180021798  mov     [rbx+38h], r13
0x18002179c  mov     eax, [rsp+78h+arg_8]
0x1800217a3  mov     [rbx+40h], eax
0x1800217a6  mov     [rbx+44h], ebp
0x1800217a9  mov     rax, [rsp+78h+arg_20]
0x1800217b1  mov     [rbx+28h], rax
0x1800217b5  mov     [rbx+30h], r12
0x1800217b9  mov     rax, [rsp+78h+arg_28]
0x1800217c1  mov     [rbx+88h], rax
0x1800217c8  mov     rax, [rsp+78h+arg_0]
0x1800217d0  mov     [rbx+90h], rax
0x1800217d7  mov     [rbx+48h], rdi
0x1800217db  xorps   xmm0, xmm0
0x1800217de  xor     eax, eax
0x1800217e0  movups  xmmword ptr [rbx+68h], xmm0
0x1800217e4  mov     [rbx+78h], rax
0x1800217e8  movups  xmmword ptr [rbx+50h], xmm0
0x1800217ec  mov     [rbx+60h], rax
0x1800217f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800217f7  test    rax, rax
0x1800217fa  jz      short loc_180021803
0x1800217fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021801  jmp     short loc_180021806
0x180021803  mov     rax, rdi
0x180021806  mov     [rbx+80h], rax
0x18002180d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180021814  test    rax, rax
0x180021817  jz      short loc_180021821
0x180021819  mov     rcx, rbx
0x18002181c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021821  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180021828  test    rax, rax
0x18002182b  jz      short loc_180021843
0x18002182d  mov     r8d, 400h
0x180021833  mov     rdx, [rsp+78h+arg_60]
0x18002183b  mov     rcx, rbx
0x18002183e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021843  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002184a  test    rax, rax
0x18002184d  jz      short loc_180021857
0x18002184f  mov     rcx, rbx
0x180021852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021857  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002185e  test    rax, rax
0x180021861  jz      short loc_180021871
0x180021863  test    byte ptr [rbx+4], 2
0x180021867  jnz     short loc_180021871
0x180021869  mov     rcx, rbx
0x18002186c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021871  cmp     [rbx+8], edi
0x180021874  jl      short loc_180021890
0x180021876  cmp     r15d, 3
0x18002187a  jnz     loc_18002195F
0x180021880  mov     ecx, 8000FFFFh; this
0x180021885  mov     [rbx+8], ecx
0x180021888  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002188d  mov     [rbx+0Ch], eax
0x180021890  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180021897  jnz     short loc_1800218B8
0x180021899  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800218a0  test    rax, rax
0x1800218a3  jz      short loc_1800218AE
0x1800218a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218aa  test    al, al
0x1800218ac  jmp     short loc_1800218B6
0x1800218ae  call    cs:__imp_IsDebuggerPresent
0x1800218b4  test    eax, eax
0x1800218b6  jz      short loc_1800218BE
0x1800218b8  test    byte ptr [rbx+4], 2
0x1800218bc  jz      short loc_1800218E2
0x1800218be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800218c5  test    rax, rax
0x1800218c8  jz      short loc_180021926
0x1800218ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800218d1  jnz     short loc_180021926
0x1800218d3  xor     r8d, r8d
0x1800218d6  xor     edx, edx
0x1800218d8  mov     rcx, rbx
0x1800218db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218e0  jmp     short loc_180021926
0x1800218e2  mov     ebp, 800h
0x1800218e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800218ee  test    rax, rax
0x1800218f1  jz      short loc_18002190A
0x1800218f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800218fa  jnz     short loc_18002190A
0x1800218fc  mov     r8d, ebp
0x1800218ff  mov     rdx, rsi
0x180021902  mov     rcx, rbx
0x180021905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002190a  cmp     [rsi], di
0x18002190d  jnz     short loc_18002191D
0x18002190f  mov     r8, rbx; unsigned __int64
0x180021912  mov     rdx, rbp; unsigned __int16 *
0x180021915  mov     rcx, rsi; this
0x180021918  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002191d  mov     rcx, rsi; lpOutputString
0x180021920  call    cs:__imp_OutputDebugStringW
0x180021926  test    byte ptr [rbx+4], 4
0x18002192a  jnz     short loc_180021935
0x18002192c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180021933  jz      short loc_180021947
0x180021935  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002193c  test    rax, rax
0x18002193f  jz      short loc_180021947
0x180021941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021946  nop
0x180021947  mov     rbx, [rsp+78h+arg_10]
0x18002194f  add     rsp, 40h
0x180021953  pop     r15
0x180021955  pop     r14
0x180021957  pop     r13
0x180021959  pop     r12
0x18002195b  pop     rdi
0x18002195c  pop     rsi
0x18002195d  pop     rbp
0x18002195e  retn
0x18002195f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
