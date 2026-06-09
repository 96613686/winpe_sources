# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800362d0`
- end: `0x1800365c9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800338cc`

## callees

- `0x180033310`
- `0x180035884`
- `0x180036024`
- `0x1800362d0`
- `0x180036f38`
- `0x180036f60`
- `0x18003708c`
- `0x1800370a8`
- `0x1800396ec`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800363f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800363f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036512`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180036512`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180036584`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180036584`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x1800362d0  mov     [rsp+arg_10], rbx
0x1800362d5  mov     [rsp+arg_8], edx
0x1800362d9  mov     [rsp+arg_0], rcx
0x1800362de  push    rbp
0x1800362df  push    rsi
0x1800362e0  push    rdi
0x1800362e1  push    r12
0x1800362e3  push    r13
0x1800362e5  push    r14
0x1800362e7  push    r15
0x1800362e9  sub     rsp, 40h
0x1800362ed  mov     r12, r9
0x1800362f0  mov     r13, r8
0x1800362f3  mov     r10, rcx
0x1800362f6  xor     eax, eax
0x1800362f8  mov     rsi, [rsp+78h+lpOutputString]
0x180036300  mov     [rsi], ax
0x180036303  mov     rax, [rsp+78h+arg_60]
0x18003630b  mov     byte ptr [rax], 0
0x18003630e  mov     r14, [rsp+78h+arg_38]
0x180036316  mov     edi, [r14]
0x180036319  mov     rbx, [rsp+78h+arg_78]
0x180036321  mov     [rbx+8], edi
0x180036324  mov     eax, [r14+4]
0x180036328  mov     [rbx+0Ch], eax
0x18003632b  xor     ebp, ebp
0x18003632d  mov     r15d, [rsp+78h+arg_30]
0x180036335  mov     ecx, r15d
0x180036338  test    r15d, r15d
0x18003633b  jz      short loc_1800363A3
0x18003633d  sub     ecx, 1
0x180036340  jz      short loc_18003639A
0x180036342  sub     ecx, 1
0x180036345  jz      short loc_180036355
0x180036347  cmp     ecx, 1
0x18003634a  jnz     short loc_1800363AC
0x18003634c  mov     ecx, edi; this
0x18003634e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180036353  jmp     short loc_1800363AA
0x180036355  test    edi, edi
0x180036357  js      short loc_180036391
0x180036359  mov     edi, 8007029Ch
0x18003635e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180036362  mov     rax, [rsp+78h+arg_28]
0x18003636a  mov     [rsp+78h+var_50], rax; __int64
0x18003636f  mov     rax, [rsp+78h+arg_20]
0x180036377  mov     [rsp+78h+var_58], rax; __int64
0x18003637c  mov     rcx, r10; int
0x18003637f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180036384  mov     [rbx+8], edi
0x180036387  mov     ecx, edi; this
0x180036389  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003638e  mov     [rbx+0Ch], eax
0x180036391  mov     ecx, edi; this
0x180036393  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180036398  jmp     short loc_1800363AA
0x18003639a  mov     ecx, edi; this
0x18003639c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800363a1  jmp     short loc_1800363AA
0x1800363a3  mov     ecx, edi; this
0x1800363a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800363aa  mov     ebp, eax
0x1800363ac  mov     [rbx], r15d
0x1800363af  mov     eax, [rsp+78h+arg_70]
0x1800363b6  mov     [rbx+4], eax
0x1800363b9  cmp     dword ptr [r14+8], 1
0x1800363be  jnz     short loc_1800363C6
0x1800363c0  or      eax, 8
0x1800363c3  mov     [rbx+4], eax
0x1800363c6  mov     eax, 1
0x1800363cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800363d3  inc     eax
0x1800363d5  mov     [rbx+10h], eax
0x1800363d8  mov     rax, [rsp+78h+arg_40]
0x1800363e0  xor     edi, edi
0x1800363e2  test    rax, rax
0x1800363e5  jz      short loc_1800363EC
0x1800363e7  cmp     [rax], di
0x1800363ea  jnz     short loc_1800363EF
0x1800363ec  mov     rax, rdi
0x1800363ef  mov     [rbx+18h], rax
0x1800363f3  call    cs:__imp_GetCurrentThreadId
0x1800363f9  mov     [rbx+20h], eax
0x1800363fc  mov     [rbx+38h], r13
0x180036400  mov     eax, [rsp+78h+arg_8]
0x180036407  mov     [rbx+40h], eax
0x18003640a  mov     [rbx+44h], ebp
0x18003640d  mov     rax, [rsp+78h+arg_20]
0x180036415  mov     [rbx+28h], rax
0x180036419  mov     [rbx+30h], r12
0x18003641d  mov     rax, [rsp+78h+arg_28]
0x180036425  mov     [rbx+88h], rax
0x18003642c  mov     rax, [rsp+78h+arg_0]
0x180036434  mov     [rbx+90h], rax
0x18003643b  mov     [rbx+48h], rdi
0x18003643f  xorps   xmm0, xmm0
0x180036442  xor     eax, eax
0x180036444  movups  xmmword ptr [rbx+68h], xmm0
0x180036448  mov     [rbx+78h], rax
0x18003644c  movups  xmmword ptr [rbx+50h], xmm0
0x180036450  mov     [rbx+60h], rax
0x180036454  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003645b  test    rax, rax
0x18003645e  jz      short loc_180036467
0x180036460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036465  jmp     short loc_18003646A
0x180036467  mov     rax, rdi
0x18003646a  mov     [rbx+80h], rax
0x180036471  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180036478  test    rax, rax
0x18003647b  jz      short loc_180036485
0x18003647d  mov     rcx, rbx
0x180036480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036485  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003648c  test    rax, rax
0x18003648f  jz      short loc_1800364A7
0x180036491  mov     r8d, 400h
0x180036497  mov     rdx, [rsp+78h+arg_60]
0x18003649f  mov     rcx, rbx
0x1800364a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800364ae  test    rax, rax
0x1800364b1  jz      short loc_1800364BB
0x1800364b3  mov     rcx, rbx
0x1800364b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800364c2  test    rax, rax
0x1800364c5  jz      short loc_1800364D5
0x1800364c7  test    byte ptr [rbx+4], 2
0x1800364cb  jnz     short loc_1800364D5
0x1800364cd  mov     rcx, rbx
0x1800364d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364d5  cmp     [rbx+8], edi
0x1800364d8  jl      short loc_1800364F4
0x1800364da  cmp     r15d, 3
0x1800364de  jnz     loc_1800365C3
0x1800364e4  mov     ecx, 8000FFFFh; this
0x1800364e9  mov     [rbx+8], ecx
0x1800364ec  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800364f1  mov     [rbx+0Ch], eax
0x1800364f4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800364fb  jnz     short loc_18003651C
0x1800364fd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180036504  test    rax, rax
0x180036507  jz      short loc_180036512
0x180036509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003650e  test    al, al
0x180036510  jmp     short loc_18003651A
0x180036512  call    cs:__imp_IsDebuggerPresent
0x180036518  test    eax, eax
0x18003651a  jz      short loc_180036522
0x18003651c  test    byte ptr [rbx+4], 2
0x180036520  jz      short loc_180036546
0x180036522  mov     rax, cs:g_pfnResultLoggingCallback
0x180036529  test    rax, rax
0x18003652c  jz      short loc_18003658A
0x18003652e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180036535  jnz     short loc_18003658A
0x180036537  xor     r8d, r8d
0x18003653a  xor     edx, edx
0x18003653c  mov     rcx, rbx
0x18003653f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036544  jmp     short loc_18003658A
0x180036546  mov     ebp, 800h
0x18003654b  mov     rax, cs:g_pfnResultLoggingCallback
0x180036552  test    rax, rax
0x180036555  jz      short loc_18003656E
0x180036557  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003655e  jnz     short loc_18003656E
0x180036560  mov     r8d, ebp
0x180036563  mov     rdx, rsi
0x180036566  mov     rcx, rbx
0x180036569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003656e  cmp     [rsi], di
0x180036571  jnz     short loc_180036581
0x180036573  mov     r8, rbx; unsigned __int64
0x180036576  mov     rdx, rbp; unsigned __int16 *
0x180036579  mov     rcx, rsi; this
0x18003657c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180036581  mov     rcx, rsi; lpOutputString
0x180036584  call    cs:__imp_OutputDebugStringW
0x18003658a  test    byte ptr [rbx+4], 4
0x18003658e  jnz     short loc_180036599
0x180036590  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180036597  jz      short loc_1800365AB
0x180036599  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800365a0  test    rax, rax
0x1800365a3  jz      short loc_1800365AB
0x1800365a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365aa  nop
0x1800365ab  mov     rbx, [rsp+78h+arg_10]
0x1800365b3  add     rsp, 40h
0x1800365b7  pop     r15
0x1800365b9  pop     r14
0x1800365bb  pop     r13
0x1800365bd  pop     r12
0x1800365bf  pop     rdi
0x1800365c0  pop     rsi
0x1800365c1  pop     rbp
0x1800365c2  retn
0x1800365c3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
