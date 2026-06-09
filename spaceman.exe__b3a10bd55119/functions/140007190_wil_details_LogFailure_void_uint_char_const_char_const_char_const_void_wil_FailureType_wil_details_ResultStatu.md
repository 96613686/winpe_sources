# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140007190`
- end: `0x140007488`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004bf4`

## callees

- `0x140004630`
- `0x140006834`
- `0x140006fcc`
- `0x140007190`
- `0x140007b78`
- `0x140007ba0`
- `0x140007cc8`
- `0x140007ce4`
- `0x14000a00c`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400072b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400072b3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007444`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007444`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400073d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400073d2`

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
0x140007190  mov     [rsp+arg_10], rbx
0x140007195  mov     [rsp+arg_8], edx
0x140007199  mov     [rsp+arg_0], rcx
0x14000719e  push    rbp
0x14000719f  push    rsi
0x1400071a0  push    rdi
0x1400071a1  push    r12
0x1400071a3  push    r13
0x1400071a5  push    r14
0x1400071a7  push    r15
0x1400071a9  sub     rsp, 40h
0x1400071ad  mov     r14, [rsp+78h+arg_38]
0x1400071b5  xor     eax, eax
0x1400071b7  mov     rbx, [rsp+78h+arg_78]
0x1400071bf  xor     ebp, ebp
0x1400071c1  mov     r15d, [rsp+78h+arg_30]
0x1400071c9  mov     r10, rcx
0x1400071cc  mov     rsi, [rsp+78h+lpOutputString]
0x1400071d4  mov     r12, r9
0x1400071d7  mov     r13, r8
0x1400071da  mov     ecx, r15d
0x1400071dd  mov     [rsi], ax
0x1400071e0  mov     rax, [rsp+78h+arg_60]
0x1400071e8  mov     byte ptr [rax], 0
0x1400071eb  mov     edi, [r14]
0x1400071ee  mov     [rbx+8], edi
0x1400071f1  mov     eax, [r14+4]
0x1400071f5  mov     [rbx+0Ch], eax
0x1400071f8  test    r15d, r15d
0x1400071fb  jz      short loc_140007263
0x1400071fd  sub     ecx, 1
0x140007200  jz      short loc_14000725A
0x140007202  sub     ecx, 1
0x140007205  jz      short loc_140007215
0x140007207  cmp     ecx, 1
0x14000720a  jnz     short loc_14000726C
0x14000720c  mov     ecx, edi; this
0x14000720e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140007213  jmp     short loc_14000726A
0x140007215  test    edi, edi
0x140007217  js      short loc_140007251
0x140007219  mov     rax, [rsp+78h+arg_28]
0x140007221  mov     edi, 8007029Ch
0x140007226  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000722a  mov     rcx, r10; int
0x14000722d  mov     [rsp+78h+var_50], rax; __int64
0x140007232  mov     rax, [rsp+78h+arg_20]
0x14000723a  mov     [rsp+78h+var_58], rax; __int64
0x14000723f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007244  mov     ecx, edi; this
0x140007246  mov     [rbx+8], edi
0x140007249  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000724e  mov     [rbx+0Ch], eax
0x140007251  mov     ecx, edi; this
0x140007253  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007258  jmp     short loc_14000726A
0x14000725a  mov     ecx, edi; this
0x14000725c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007261  jmp     short loc_14000726A
0x140007263  mov     ecx, edi; this
0x140007265  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000726a  mov     ebp, eax
0x14000726c  mov     eax, [rsp+78h+arg_70]
0x140007273  mov     [rbx+4], eax
0x140007276  mov     [rbx], r15d
0x140007279  cmp     dword ptr [r14+8], 1
0x14000727e  jnz     short loc_140007286
0x140007280  or      eax, 8
0x140007283  mov     [rbx+4], eax
0x140007286  mov     eax, 1
0x14000728b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007293  inc     eax
0x140007295  xor     edi, edi
0x140007297  mov     [rbx+10h], eax
0x14000729a  mov     rax, [rsp+78h+arg_40]
0x1400072a2  test    rax, rax
0x1400072a5  jz      short loc_1400072AC
0x1400072a7  cmp     [rax], di
0x1400072aa  jnz     short loc_1400072AF
0x1400072ac  mov     rax, rdi
0x1400072af  mov     [rbx+18h], rax
0x1400072b3  call    cs:__imp_GetCurrentThreadId
0x1400072b9  mov     [rbx+38h], r13
0x1400072bd  xorps   xmm0, xmm0
0x1400072c0  mov     [rbx+20h], eax
0x1400072c3  mov     eax, [rsp+78h+arg_8]
0x1400072ca  mov     [rbx+40h], eax
0x1400072cd  mov     rax, [rsp+78h+arg_20]
0x1400072d5  mov     [rbx+28h], rax
0x1400072d9  mov     rax, [rsp+78h+arg_28]
0x1400072e1  mov     [rbx+88h], rax
0x1400072e8  mov     rax, [rsp+78h+arg_0]
0x1400072f0  mov     [rbx+90h], rax
0x1400072f7  xor     eax, eax
0x1400072f9  mov     [rbx+44h], ebp
0x1400072fc  mov     [rbx+30h], r12
0x140007300  mov     [rbx+48h], rdi
0x140007304  movups  xmmword ptr [rbx+68h], xmm0
0x140007308  mov     [rbx+78h], rax
0x14000730c  movups  xmmword ptr [rbx+50h], xmm0
0x140007310  mov     [rbx+60h], rax
0x140007314  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000731b  test    rax, rax
0x14000731e  jz      short loc_140007327
0x140007320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007325  jmp     short loc_14000732A
0x140007327  mov     rax, rdi
0x14000732a  mov     [rbx+80h], rax
0x140007331  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007338  test    rax, rax
0x14000733b  jz      short loc_140007345
0x14000733d  mov     rcx, rbx
0x140007340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007345  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000734c  test    rax, rax
0x14000734f  jz      short loc_140007367
0x140007351  mov     rdx, [rsp+78h+arg_60]
0x140007359  mov     r8d, 400h
0x14000735f  mov     rcx, rbx
0x140007362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007367  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000736e  test    rax, rax
0x140007371  jz      short loc_14000737B
0x140007373  mov     rcx, rbx
0x140007376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000737b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007382  test    rax, rax
0x140007385  jz      short loc_140007395
0x140007387  test    byte ptr [rbx+4], 2
0x14000738b  jnz     short loc_140007395
0x14000738d  mov     rcx, rbx
0x140007390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007395  cmp     [rbx+8], edi
0x140007398  jl      short loc_1400073B4
0x14000739a  cmp     r15d, 3
0x14000739e  jnz     loc_140007482
0x1400073a4  mov     ecx, 8000FFFFh; this
0x1400073a9  mov     [rbx+8], ecx
0x1400073ac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400073b1  mov     [rbx+0Ch], eax
0x1400073b4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400073bb  jnz     short loc_1400073DC
0x1400073bd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400073c4  test    rax, rax
0x1400073c7  jz      short loc_1400073D2
0x1400073c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073ce  test    al, al
0x1400073d0  jmp     short loc_1400073DA
0x1400073d2  call    cs:__imp_IsDebuggerPresent
0x1400073d8  test    eax, eax
0x1400073da  jz      short loc_1400073E2
0x1400073dc  test    byte ptr [rbx+4], 2
0x1400073e0  jz      short loc_140007406
0x1400073e2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400073e9  test    rax, rax
0x1400073ec  jz      short loc_14000744A
0x1400073ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400073f5  jnz     short loc_14000744A
0x1400073f7  xor     r8d, r8d
0x1400073fa  xor     edx, edx
0x1400073fc  mov     rcx, rbx
0x1400073ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007404  jmp     short loc_14000744A
0x140007406  mov     rax, cs:g_pfnResultLoggingCallback
0x14000740d  mov     ebp, 800h
0x140007412  test    rax, rax
0x140007415  jz      short loc_14000742E
0x140007417  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000741e  jnz     short loc_14000742E
0x140007420  mov     r8d, ebp
0x140007423  mov     rdx, rsi
0x140007426  mov     rcx, rbx
0x140007429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000742e  cmp     [rsi], di
0x140007431  jnz     short loc_140007441
0x140007433  mov     r8, rbx; unsigned __int64
0x140007436  mov     rdx, rbp; unsigned __int16 *
0x140007439  mov     rcx, rsi; this
0x14000743c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007441  mov     rcx, rsi; lpOutputString
0x140007444  call    cs:__imp_OutputDebugStringW
0x14000744a  test    byte ptr [rbx+4], 4
0x14000744e  jnz     short loc_140007459
0x140007450  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007457  jz      short loc_14000746A
0x140007459  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007460  test    rax, rax
0x140007463  jz      short loc_14000746A
0x140007465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000746a  mov     rbx, [rsp+78h+arg_10]
0x140007472  add     rsp, 40h
0x140007476  pop     r15
0x140007478  pop     r14
0x14000747a  pop     r13
0x14000747c  pop     r12
0x14000747e  pop     rdi
0x14000747f  pop     rsi
0x140007480  pop     rbp
0x140007481  retn
0x140007482  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
