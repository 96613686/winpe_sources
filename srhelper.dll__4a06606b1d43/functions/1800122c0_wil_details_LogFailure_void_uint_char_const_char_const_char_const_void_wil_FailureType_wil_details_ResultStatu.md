# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800122c0`
- end: `0x1800125b8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000ff54`

## callees

- `0x18000f990`
- `0x180011964`
- `0x1800120fc`
- `0x1800122c0`
- `0x180012ca8`
- `0x180012cd0`
- `0x180012df8`
- `0x180012e14`
- `0x18001498c`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800123e3`
- `KERNEL32!GetCurrentThreadId` at `0x1800123e3`
- `KERNEL32!OutputDebugStringW` at `0x180012574`
- `KERNEL32!OutputDebugStringW` at `0x180012574`
- `KERNEL32!IsDebuggerPresent` at `0x180012502`
- `KERNEL32!IsDebuggerPresent` at `0x180012502`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
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
0x1800122c0  mov     [rsp+arg_10], rbx
0x1800122c5  mov     [rsp+arg_8], edx
0x1800122c9  mov     [rsp+arg_0], rcx
0x1800122ce  push    rbp
0x1800122cf  push    rsi
0x1800122d0  push    rdi
0x1800122d1  push    r12
0x1800122d3  push    r13
0x1800122d5  push    r14
0x1800122d7  push    r15
0x1800122d9  sub     rsp, 40h
0x1800122dd  mov     r14, [rsp+78h+arg_38]
0x1800122e5  xor     eax, eax
0x1800122e7  mov     rbx, [rsp+78h+arg_78]
0x1800122ef  xor     ebp, ebp
0x1800122f1  mov     r15d, [rsp+78h+arg_30]
0x1800122f9  mov     r10, rcx
0x1800122fc  mov     rsi, [rsp+78h+lpOutputString]
0x180012304  mov     r12, r9
0x180012307  mov     r13, r8
0x18001230a  mov     ecx, r15d
0x18001230d  mov     [rsi], ax
0x180012310  mov     rax, [rsp+78h+arg_60]
0x180012318  mov     byte ptr [rax], 0
0x18001231b  mov     edi, [r14]
0x18001231e  mov     [rbx+8], edi
0x180012321  mov     eax, [r14+4]
0x180012325  mov     [rbx+0Ch], eax
0x180012328  test    r15d, r15d
0x18001232b  jz      short loc_180012393
0x18001232d  sub     ecx, 1
0x180012330  jz      short loc_18001238A
0x180012332  sub     ecx, 1
0x180012335  jz      short loc_180012345
0x180012337  cmp     ecx, 1
0x18001233a  jnz     short loc_18001239C
0x18001233c  mov     ecx, edi; this
0x18001233e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180012343  jmp     short loc_18001239A
0x180012345  test    edi, edi
0x180012347  js      short loc_180012381
0x180012349  mov     rax, [rsp+78h+arg_28]
0x180012351  mov     edi, 8007029Ch
0x180012356  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001235a  mov     rcx, r10; int
0x18001235d  mov     [rsp+78h+var_50], rax; __int64
0x180012362  mov     rax, [rsp+78h+arg_20]
0x18001236a  mov     [rsp+78h+var_58], rax; __int64
0x18001236f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180012374  mov     ecx, edi; this
0x180012376  mov     [rbx+8], edi
0x180012379  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001237e  mov     [rbx+0Ch], eax
0x180012381  mov     ecx, edi; this
0x180012383  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180012388  jmp     short loc_18001239A
0x18001238a  mov     ecx, edi; this
0x18001238c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180012391  jmp     short loc_18001239A
0x180012393  mov     ecx, edi; this
0x180012395  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001239a  mov     ebp, eax
0x18001239c  mov     eax, [rsp+78h+arg_70]
0x1800123a3  mov     [rbx+4], eax
0x1800123a6  mov     [rbx], r15d
0x1800123a9  cmp     dword ptr [r14+8], 1
0x1800123ae  jnz     short loc_1800123B6
0x1800123b0  or      eax, 8
0x1800123b3  mov     [rbx+4], eax
0x1800123b6  mov     eax, 1
0x1800123bb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800123c3  inc     eax
0x1800123c5  xor     edi, edi
0x1800123c7  mov     [rbx+10h], eax
0x1800123ca  mov     rax, [rsp+78h+arg_40]
0x1800123d2  test    rax, rax
0x1800123d5  jz      short loc_1800123DC
0x1800123d7  cmp     [rax], di
0x1800123da  jnz     short loc_1800123DF
0x1800123dc  mov     rax, rdi
0x1800123df  mov     [rbx+18h], rax
0x1800123e3  call    cs:__imp_GetCurrentThreadId
0x1800123e9  mov     [rbx+38h], r13
0x1800123ed  xorps   xmm0, xmm0
0x1800123f0  mov     [rbx+20h], eax
0x1800123f3  mov     eax, [rsp+78h+arg_8]
0x1800123fa  mov     [rbx+40h], eax
0x1800123fd  mov     rax, [rsp+78h+arg_20]
0x180012405  mov     [rbx+28h], rax
0x180012409  mov     rax, [rsp+78h+arg_28]
0x180012411  mov     [rbx+88h], rax
0x180012418  mov     rax, [rsp+78h+arg_0]
0x180012420  mov     [rbx+90h], rax
0x180012427  xor     eax, eax
0x180012429  mov     [rbx+44h], ebp
0x18001242c  mov     [rbx+30h], r12
0x180012430  mov     [rbx+48h], rdi
0x180012434  movups  xmmword ptr [rbx+68h], xmm0
0x180012438  mov     [rbx+78h], rax
0x18001243c  movups  xmmword ptr [rbx+50h], xmm0
0x180012440  mov     [rbx+60h], rax
0x180012444  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001244b  test    rax, rax
0x18001244e  jz      short loc_180012457
0x180012450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012455  jmp     short loc_18001245A
0x180012457  mov     rax, rdi
0x18001245a  mov     [rbx+80h], rax
0x180012461  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012468  test    rax, rax
0x18001246b  jz      short loc_180012475
0x18001246d  mov     rcx, rbx
0x180012470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012475  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001247c  test    rax, rax
0x18001247f  jz      short loc_180012497
0x180012481  mov     rdx, [rsp+78h+arg_60]
0x180012489  mov     r8d, 400h
0x18001248f  mov     rcx, rbx
0x180012492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012497  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001249e  test    rax, rax
0x1800124a1  jz      short loc_1800124AB
0x1800124a3  mov     rcx, rbx
0x1800124a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800124b2  test    rax, rax
0x1800124b5  jz      short loc_1800124C5
0x1800124b7  test    byte ptr [rbx+4], 2
0x1800124bb  jnz     short loc_1800124C5
0x1800124bd  mov     rcx, rbx
0x1800124c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124c5  cmp     [rbx+8], edi
0x1800124c8  jl      short loc_1800124E4
0x1800124ca  cmp     r15d, 3
0x1800124ce  jnz     loc_1800125B2
0x1800124d4  mov     ecx, 8000FFFFh; this
0x1800124d9  mov     [rbx+8], ecx
0x1800124dc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800124e1  mov     [rbx+0Ch], eax
0x1800124e4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800124eb  jnz     short loc_18001250C
0x1800124ed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800124f4  test    rax, rax
0x1800124f7  jz      short loc_180012502
0x1800124f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124fe  test    al, al
0x180012500  jmp     short loc_18001250A
0x180012502  call    cs:__imp_IsDebuggerPresent
0x180012508  test    eax, eax
0x18001250a  jz      short loc_180012512
0x18001250c  test    byte ptr [rbx+4], 2
0x180012510  jz      short loc_180012536
0x180012512  mov     rax, cs:g_pfnResultLoggingCallback
0x180012519  test    rax, rax
0x18001251c  jz      short loc_18001257A
0x18001251e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012525  jnz     short loc_18001257A
0x180012527  xor     r8d, r8d
0x18001252a  xor     edx, edx
0x18001252c  mov     rcx, rbx
0x18001252f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012534  jmp     short loc_18001257A
0x180012536  mov     rax, cs:g_pfnResultLoggingCallback
0x18001253d  mov     ebp, 800h
0x180012542  test    rax, rax
0x180012545  jz      short loc_18001255E
0x180012547  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001254e  jnz     short loc_18001255E
0x180012550  mov     r8d, ebp
0x180012553  mov     rdx, rsi
0x180012556  mov     rcx, rbx
0x180012559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001255e  cmp     [rsi], di
0x180012561  jnz     short loc_180012571
0x180012563  mov     r8, rbx; unsigned __int64
0x180012566  mov     rdx, rbp; unsigned __int16 *
0x180012569  mov     rcx, rsi; this
0x18001256c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180012571  mov     rcx, rsi; lpOutputString
0x180012574  call    cs:__imp_OutputDebugStringW
0x18001257a  test    byte ptr [rbx+4], 4
0x18001257e  jnz     short loc_180012589
0x180012580  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180012587  jz      short loc_18001259A
0x180012589  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012590  test    rax, rax
0x180012593  jz      short loc_18001259A
0x180012595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001259a  mov     rbx, [rsp+78h+arg_10]
0x1800125a2  add     rsp, 40h
0x1800125a6  pop     r15
0x1800125a8  pop     r14
0x1800125aa  pop     r13
0x1800125ac  pop     r12
0x1800125ae  pop     rdi
0x1800125af  pop     rsi
0x1800125b0  pop     rbp
0x1800125b1  retn
0x1800125b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
