# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180024f64`
- end: `0x180025265`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180021f08`
- `0x180022260`

## callees

- `0x18001244c`
- `0x180021e48`
- `0x1800243c4`
- `0x180024f64`
- `0x180025954`
- `0x180025970`
- `0x180025ac0`
- `0x180025adc`
- `0x180027338`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002508f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002508f`
- `KERNEL32!IsDebuggerPresent` at `0x1800251ae`
- `KERNEL32!IsDebuggerPresent` at `0x1800251ae`
- `KERNEL32!OutputDebugStringW` at `0x180025220`
- `KERNEL32!OutputDebugStringW` at `0x180025220`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180024f64  mov     rax, rsp
0x180024f67  mov     [rax+10h], edx
0x180024f6a  mov     [rax+8], rcx
0x180024f6e  push    rbp
0x180024f6f  push    rsi
0x180024f70  push    rdi
0x180024f71  push    r12
0x180024f73  push    r13
0x180024f75  push    r14
0x180024f77  push    r15
0x180024f79  sub     rsp, 50h
0x180024f7d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180024f85  mov     [rax+18h], rbx
0x180024f89  mov     r12, r9
0x180024f8c  mov     r13, r8
0x180024f8f  mov     r10, rcx
0x180024f92  xor     eax, eax
0x180024f94  mov     rsi, [rsp+88h+lpOutputString]
0x180024f9c  mov     [rsi], ax
0x180024f9f  mov     rax, [rsp+88h+arg_60]
0x180024fa7  mov     byte ptr [rax], 0
0x180024faa  mov     r14, [rsp+88h+arg_38]
0x180024fb2  mov     edi, [r14]
0x180024fb5  mov     rbx, [rsp+88h+arg_78]
0x180024fbd  mov     [rbx+8], edi
0x180024fc0  mov     eax, [r14+4]
0x180024fc4  mov     [rbx+0Ch], eax
0x180024fc7  xor     ebp, ebp
0x180024fc9  mov     r15d, [rsp+88h+arg_30]
0x180024fd1  mov     ecx, r15d
0x180024fd4  test    r15d, r15d
0x180024fd7  jz      short loc_18002503F
0x180024fd9  sub     ecx, 1
0x180024fdc  jz      short loc_180025036
0x180024fde  sub     ecx, 1
0x180024fe1  jz      short loc_180024FF1
0x180024fe3  cmp     ecx, 1
0x180024fe6  jnz     short loc_180025048
0x180024fe8  mov     ecx, edi; this
0x180024fea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180024fef  jmp     short loc_180025046
0x180024ff1  test    edi, edi
0x180024ff3  js      short loc_18002502D
0x180024ff5  mov     edi, 8007029Ch
0x180024ffa  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180024ffe  mov     rax, [rsp+88h+arg_28]
0x180025006  mov     [rsp+88h+var_60], rax; __int64
0x18002500b  mov     rax, [rsp+88h+arg_20]
0x180025013  mov     [rsp+88h+var_68], rax; __int64
0x180025018  mov     rcx, r10; int
0x18002501b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025020  mov     [rbx+8], edi
0x180025023  mov     ecx, edi; this
0x180025025  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002502a  mov     [rbx+0Ch], eax
0x18002502d  mov     ecx, edi; this
0x18002502f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180025034  jmp     short loc_180025046
0x180025036  mov     ecx, edi; this
0x180025038  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002503d  jmp     short loc_180025046
0x18002503f  mov     ecx, edi; this
0x180025041  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180025046  mov     ebp, eax
0x180025048  mov     [rbx], r15d
0x18002504b  mov     eax, [rsp+88h+arg_70]
0x180025052  mov     [rbx+4], eax
0x180025055  cmp     dword ptr [r14+8], 1
0x18002505a  jnz     short loc_180025062
0x18002505c  or      eax, 8
0x18002505f  mov     [rbx+4], eax
0x180025062  mov     eax, 1
0x180025067  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002506f  inc     eax
0x180025071  mov     [rbx+10h], eax
0x180025074  mov     rax, [rsp+88h+arg_40]
0x18002507c  xor     edi, edi
0x18002507e  test    rax, rax
0x180025081  jz      short loc_180025088
0x180025083  cmp     [rax], di
0x180025086  jnz     short loc_18002508B
0x180025088  mov     rax, rdi
0x18002508b  mov     [rbx+18h], rax
0x18002508f  call    cs:__imp_GetCurrentThreadId
0x180025095  mov     [rbx+20h], eax
0x180025098  mov     [rbx+38h], r13
0x18002509c  mov     eax, [rsp+88h+arg_8]
0x1800250a3  mov     [rbx+40h], eax
0x1800250a6  mov     [rbx+44h], ebp
0x1800250a9  mov     rax, [rsp+88h+arg_20]
0x1800250b1  mov     [rbx+28h], rax
0x1800250b5  mov     [rbx+30h], r12
0x1800250b9  mov     rax, [rsp+88h+arg_28]
0x1800250c1  mov     [rbx+88h], rax
0x1800250c8  mov     rax, [rsp+88h+arg_0]
0x1800250d0  mov     [rbx+90h], rax
0x1800250d7  mov     [rbx+48h], rdi
0x1800250db  xorps   xmm0, xmm0
0x1800250de  xor     eax, eax
0x1800250e0  movups  xmmword ptr [rbx+68h], xmm0
0x1800250e4  mov     [rbx+78h], rax
0x1800250e8  movups  xmmword ptr [rbx+50h], xmm0
0x1800250ec  mov     [rbx+60h], rax
0x1800250f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800250f7  test    rax, rax
0x1800250fa  jz      short loc_180025103
0x1800250fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025101  jmp     short loc_180025106
0x180025103  mov     rax, rdi
0x180025106  mov     [rbx+80h], rax
0x18002510d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025114  test    rax, rax
0x180025117  jz      short loc_180025121
0x180025119  mov     rcx, rbx
0x18002511c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025121  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025128  test    rax, rax
0x18002512b  jz      short loc_180025143
0x18002512d  mov     r8d, 400h
0x180025133  mov     rdx, [rsp+88h+arg_60]
0x18002513b  mov     rcx, rbx
0x18002513e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025143  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002514a  test    rax, rax
0x18002514d  jz      short loc_180025157
0x18002514f  mov     rcx, rbx
0x180025152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025157  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002515e  test    rax, rax
0x180025161  jz      short loc_180025171
0x180025163  test    byte ptr [rbx+4], 2
0x180025167  jnz     short loc_180025171
0x180025169  mov     rcx, rbx
0x18002516c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025171  cmp     [rbx+8], edi
0x180025174  jl      short loc_180025190
0x180025176  cmp     r15d, 3
0x18002517a  jnz     loc_18002525F
0x180025180  mov     ecx, 8000FFFFh; this
0x180025185  mov     [rbx+8], ecx
0x180025188  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002518d  mov     [rbx+0Ch], eax
0x180025190  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180025197  jnz     short loc_1800251B8
0x180025199  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800251a0  test    rax, rax
0x1800251a3  jz      short loc_1800251AE
0x1800251a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251aa  test    al, al
0x1800251ac  jmp     short loc_1800251B6
0x1800251ae  call    cs:__imp_IsDebuggerPresent
0x1800251b4  test    eax, eax
0x1800251b6  jz      short loc_1800251BE
0x1800251b8  test    byte ptr [rbx+4], 2
0x1800251bc  jz      short loc_1800251E2
0x1800251be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800251c5  test    rax, rax
0x1800251c8  jz      short loc_180025226
0x1800251ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800251d1  jnz     short loc_180025226
0x1800251d3  xor     r8d, r8d
0x1800251d6  xor     edx, edx
0x1800251d8  mov     rcx, rbx
0x1800251db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251e0  jmp     short loc_180025226
0x1800251e2  mov     ebp, 800h
0x1800251e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800251ee  test    rax, rax
0x1800251f1  jz      short loc_18002520A
0x1800251f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800251fa  jnz     short loc_18002520A
0x1800251fc  mov     r8d, ebp
0x1800251ff  mov     rdx, rsi
0x180025202  mov     rcx, rbx
0x180025205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002520a  cmp     [rsi], di
0x18002520d  jnz     short loc_18002521D
0x18002520f  mov     r8, rbx; unsigned __int64
0x180025212  mov     rdx, rbp; unsigned __int16 *
0x180025215  mov     rcx, rsi; this
0x180025218  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002521d  mov     rcx, rsi; lpOutputString
0x180025220  call    cs:__imp_OutputDebugStringW
0x180025226  test    byte ptr [rbx+4], 4
0x18002522a  jnz     short loc_180025235
0x18002522c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180025233  jz      short loc_180025247
0x180025235  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002523c  test    rax, rax
0x18002523f  jz      short loc_180025247
0x180025241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025246  nop
0x180025247  mov     rbx, [rsp+88h+arg_10]
0x18002524f  add     rsp, 50h
0x180025253  pop     r15
0x180025255  pop     r14
0x180025257  pop     r13
0x180025259  pop     r12
0x18002525b  pop     rdi
0x18002525c  pop     rsi
0x18002525d  pop     rbp
0x18002525e  retn
0x18002525f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
