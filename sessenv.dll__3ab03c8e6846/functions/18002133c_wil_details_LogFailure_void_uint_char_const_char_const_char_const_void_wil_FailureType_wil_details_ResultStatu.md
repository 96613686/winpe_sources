# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002133c`
- end: `0x180021634`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f048`
- `0x18001f398`

## callees

- `0x180016f40`
- `0x18001ef90`
- `0x1800203c4`
- `0x18002133c`
- `0x18002184c`
- `0x180021870`
- `0x180021884`
- `0x1800218a0`
- `0x180022184`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002145f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002145f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800215f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800215f0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002157e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002157e`

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
0x18002133c  mov     [rsp+arg_10], rbx
0x180021341  mov     [rsp+arg_8], edx
0x180021345  mov     [rsp+arg_0], rcx
0x18002134a  push    rbp
0x18002134b  push    rsi
0x18002134c  push    rdi
0x18002134d  push    r12
0x18002134f  push    r13
0x180021351  push    r14
0x180021353  push    r15
0x180021355  sub     rsp, 40h
0x180021359  mov     r14, [rsp+78h+arg_38]
0x180021361  xor     eax, eax
0x180021363  mov     rbx, [rsp+78h+arg_78]
0x18002136b  xor     ebp, ebp
0x18002136d  mov     r15d, [rsp+78h+arg_30]
0x180021375  mov     r10, rcx
0x180021378  mov     rsi, [rsp+78h+lpOutputString]
0x180021380  mov     r12, r9
0x180021383  mov     r13, r8
0x180021386  mov     ecx, r15d
0x180021389  mov     [rsi], ax
0x18002138c  mov     rax, [rsp+78h+arg_60]
0x180021394  mov     byte ptr [rax], 0
0x180021397  mov     edi, [r14]
0x18002139a  mov     [rbx+8], edi
0x18002139d  mov     eax, [r14+4]
0x1800213a1  mov     [rbx+0Ch], eax
0x1800213a4  test    r15d, r15d
0x1800213a7  jz      short loc_18002140F
0x1800213a9  sub     ecx, 1
0x1800213ac  jz      short loc_180021406
0x1800213ae  sub     ecx, 1
0x1800213b1  jz      short loc_1800213C1
0x1800213b3  cmp     ecx, 1
0x1800213b6  jnz     short loc_180021418
0x1800213b8  mov     ecx, edi; this
0x1800213ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800213bf  jmp     short loc_180021416
0x1800213c1  test    edi, edi
0x1800213c3  js      short loc_1800213FD
0x1800213c5  mov     rax, [rsp+78h+arg_28]
0x1800213cd  mov     edi, 8007029Ch
0x1800213d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800213d6  mov     rcx, r10; int
0x1800213d9  mov     [rsp+78h+var_50], rax; __int64
0x1800213de  mov     rax, [rsp+78h+arg_20]
0x1800213e6  mov     [rsp+78h+var_58], rax; __int64
0x1800213eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800213f0  mov     ecx, edi; this
0x1800213f2  mov     [rbx+8], edi
0x1800213f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800213fa  mov     [rbx+0Ch], eax
0x1800213fd  mov     ecx, edi; this
0x1800213ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180021404  jmp     short loc_180021416
0x180021406  mov     ecx, edi; this
0x180021408  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002140d  jmp     short loc_180021416
0x18002140f  mov     ecx, edi; this
0x180021411  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180021416  mov     ebp, eax
0x180021418  mov     eax, [rsp+78h+arg_70]
0x18002141f  mov     [rbx+4], eax
0x180021422  mov     [rbx], r15d
0x180021425  cmp     dword ptr [r14+8], 1
0x18002142a  jnz     short loc_180021432
0x18002142c  or      eax, 8
0x18002142f  mov     [rbx+4], eax
0x180021432  mov     eax, 1
0x180021437  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002143f  inc     eax
0x180021441  xor     edi, edi
0x180021443  mov     [rbx+10h], eax
0x180021446  mov     rax, [rsp+78h+arg_40]
0x18002144e  test    rax, rax
0x180021451  jz      short loc_180021458
0x180021453  cmp     [rax], di
0x180021456  jnz     short loc_18002145B
0x180021458  mov     rax, rdi
0x18002145b  mov     [rbx+18h], rax
0x18002145f  call    cs:__imp_GetCurrentThreadId
0x180021465  mov     [rbx+38h], r13
0x180021469  xorps   xmm0, xmm0
0x18002146c  mov     [rbx+20h], eax
0x18002146f  mov     eax, [rsp+78h+arg_8]
0x180021476  mov     [rbx+40h], eax
0x180021479  mov     rax, [rsp+78h+arg_20]
0x180021481  mov     [rbx+28h], rax
0x180021485  mov     rax, [rsp+78h+arg_28]
0x18002148d  mov     [rbx+88h], rax
0x180021494  mov     rax, [rsp+78h+arg_0]
0x18002149c  mov     [rbx+90h], rax
0x1800214a3  xor     eax, eax
0x1800214a5  mov     [rbx+44h], ebp
0x1800214a8  mov     [rbx+30h], r12
0x1800214ac  mov     [rbx+48h], rdi
0x1800214b0  movups  xmmword ptr [rbx+68h], xmm0
0x1800214b4  mov     [rbx+78h], rax
0x1800214b8  movups  xmmword ptr [rbx+50h], xmm0
0x1800214bc  mov     [rbx+60h], rax
0x1800214c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800214c7  test    rax, rax
0x1800214ca  jz      short loc_1800214D3
0x1800214cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214d1  jmp     short loc_1800214D6
0x1800214d3  mov     rax, rdi
0x1800214d6  mov     [rbx+80h], rax
0x1800214dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800214e4  test    rax, rax
0x1800214e7  jz      short loc_1800214F1
0x1800214e9  mov     rcx, rbx
0x1800214ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800214f8  test    rax, rax
0x1800214fb  jz      short loc_180021513
0x1800214fd  mov     rdx, [rsp+78h+arg_60]
0x180021505  mov     r8d, 400h
0x18002150b  mov     rcx, rbx
0x18002150e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021513  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002151a  test    rax, rax
0x18002151d  jz      short loc_180021527
0x18002151f  mov     rcx, rbx
0x180021522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021527  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002152e  test    rax, rax
0x180021531  jz      short loc_180021541
0x180021533  test    byte ptr [rbx+4], 2
0x180021537  jnz     short loc_180021541
0x180021539  mov     rcx, rbx
0x18002153c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021541  cmp     [rbx+8], edi
0x180021544  jl      short loc_180021560
0x180021546  cmp     r15d, 3
0x18002154a  jnz     loc_18002162E
0x180021550  mov     ecx, 8000FFFFh; this
0x180021555  mov     [rbx+8], ecx
0x180021558  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002155d  mov     [rbx+0Ch], eax
0x180021560  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180021567  jnz     short loc_180021588
0x180021569  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180021570  test    rax, rax
0x180021573  jz      short loc_18002157E
0x180021575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002157a  test    al, al
0x18002157c  jmp     short loc_180021586
0x18002157e  call    cs:__imp_IsDebuggerPresent
0x180021584  test    eax, eax
0x180021586  jz      short loc_18002158E
0x180021588  test    byte ptr [rbx+4], 2
0x18002158c  jz      short loc_1800215B2
0x18002158e  mov     rax, cs:g_pfnResultLoggingCallback
0x180021595  test    rax, rax
0x180021598  jz      short loc_1800215F6
0x18002159a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800215a1  jnz     short loc_1800215F6
0x1800215a3  xor     r8d, r8d
0x1800215a6  xor     edx, edx
0x1800215a8  mov     rcx, rbx
0x1800215ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215b0  jmp     short loc_1800215F6
0x1800215b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800215b9  mov     ebp, 800h
0x1800215be  test    rax, rax
0x1800215c1  jz      short loc_1800215DA
0x1800215c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800215ca  jnz     short loc_1800215DA
0x1800215cc  mov     r8d, ebp
0x1800215cf  mov     rdx, rsi
0x1800215d2  mov     rcx, rbx
0x1800215d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215da  cmp     [rsi], di
0x1800215dd  jnz     short loc_1800215ED
0x1800215df  mov     r8, rbx; unsigned __int64
0x1800215e2  mov     rdx, rbp; unsigned __int16 *
0x1800215e5  mov     rcx, rsi; this
0x1800215e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800215ed  mov     rcx, rsi; lpOutputString
0x1800215f0  call    cs:__imp_OutputDebugStringW
0x1800215f6  test    byte ptr [rbx+4], 4
0x1800215fa  jnz     short loc_180021605
0x1800215fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180021603  jz      short loc_180021616
0x180021605  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002160c  test    rax, rax
0x18002160f  jz      short loc_180021616
0x180021611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021616  mov     rbx, [rsp+78h+arg_10]
0x18002161e  add     rsp, 40h
0x180021622  pop     r15
0x180021624  pop     r14
0x180021626  pop     r13
0x180021628  pop     r12
0x18002162a  pop     rdi
0x18002162b  pop     rsi
0x18002162c  pop     rbp
0x18002162d  retn
0x18002162e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
