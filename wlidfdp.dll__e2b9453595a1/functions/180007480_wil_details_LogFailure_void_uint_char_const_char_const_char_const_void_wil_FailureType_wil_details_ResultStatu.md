# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007480`
- end: `0x180007779`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004b04`
- `0x180004e4c`

## callees

- `0x180004a4c`
- `0x1800067d4`
- `0x180006ed0`
- `0x180007480`
- `0x18000826c`
- `0x180008290`
- `0x1800082a4`
- `0x1800082c0`
- `0x1800095c4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007734`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007734`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180007480  mov     [rsp+arg_10], rbx
0x180007485  mov     [rsp+arg_8], edx
0x180007489  mov     [rsp+arg_0], rcx
0x18000748e  push    rbp
0x18000748f  push    rsi
0x180007490  push    rdi
0x180007491  push    r12
0x180007493  push    r13
0x180007495  push    r14
0x180007497  push    r15
0x180007499  sub     rsp, 40h
0x18000749d  mov     r12, r9
0x1800074a0  mov     r13, r8
0x1800074a3  mov     r10, rcx
0x1800074a6  xor     eax, eax
0x1800074a8  mov     rsi, [rsp+78h+lpOutputString]
0x1800074b0  mov     [rsi], ax
0x1800074b3  mov     rax, [rsp+78h+arg_60]
0x1800074bb  mov     byte ptr [rax], 0
0x1800074be  mov     r14, [rsp+78h+arg_38]
0x1800074c6  mov     edi, [r14]
0x1800074c9  mov     rbx, [rsp+78h+arg_78]
0x1800074d1  mov     [rbx+8], edi
0x1800074d4  mov     eax, [r14+4]
0x1800074d8  mov     [rbx+0Ch], eax
0x1800074db  xor     ebp, ebp
0x1800074dd  mov     r15d, [rsp+78h+arg_30]
0x1800074e5  mov     ecx, r15d
0x1800074e8  test    r15d, r15d
0x1800074eb  jz      short loc_180007553
0x1800074ed  sub     ecx, 1
0x1800074f0  jz      short loc_18000754A
0x1800074f2  sub     ecx, 1
0x1800074f5  jz      short loc_180007505
0x1800074f7  cmp     ecx, 1
0x1800074fa  jnz     short loc_18000755C
0x1800074fc  mov     ecx, edi; this
0x1800074fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007503  jmp     short loc_18000755A
0x180007505  test    edi, edi
0x180007507  js      short loc_180007541
0x180007509  mov     edi, 8007029Ch
0x18000750e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007512  mov     rax, [rsp+78h+arg_28]
0x18000751a  mov     [rsp+78h+var_50], rax; __int64
0x18000751f  mov     rax, [rsp+78h+arg_20]
0x180007527  mov     [rsp+78h+var_58], rax; __int64
0x18000752c  mov     rcx, r10; int
0x18000752f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007534  mov     [rbx+8], edi
0x180007537  mov     ecx, edi; this
0x180007539  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000753e  mov     [rbx+0Ch], eax
0x180007541  mov     ecx, edi; this
0x180007543  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007548  jmp     short loc_18000755A
0x18000754a  mov     ecx, edi; this
0x18000754c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007551  jmp     short loc_18000755A
0x180007553  mov     ecx, edi; this
0x180007555  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000755a  mov     ebp, eax
0x18000755c  mov     [rbx], r15d
0x18000755f  mov     eax, [rsp+78h+arg_70]
0x180007566  mov     [rbx+4], eax
0x180007569  cmp     dword ptr [r14+8], 1
0x18000756e  jnz     short loc_180007576
0x180007570  or      eax, 8
0x180007573  mov     [rbx+4], eax
0x180007576  mov     eax, 1
0x18000757b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007583  inc     eax
0x180007585  mov     [rbx+10h], eax
0x180007588  mov     rax, [rsp+78h+arg_40]
0x180007590  xor     edi, edi
0x180007592  test    rax, rax
0x180007595  jz      short loc_18000759C
0x180007597  cmp     [rax], di
0x18000759a  jnz     short loc_18000759F
0x18000759c  mov     rax, rdi
0x18000759f  mov     [rbx+18h], rax
0x1800075a3  call    cs:__imp_GetCurrentThreadId
0x1800075a9  mov     [rbx+20h], eax
0x1800075ac  mov     [rbx+38h], r13
0x1800075b0  mov     eax, [rsp+78h+arg_8]
0x1800075b7  mov     [rbx+40h], eax
0x1800075ba  mov     [rbx+44h], ebp
0x1800075bd  mov     rax, [rsp+78h+arg_20]
0x1800075c5  mov     [rbx+28h], rax
0x1800075c9  mov     [rbx+30h], r12
0x1800075cd  mov     rax, [rsp+78h+arg_28]
0x1800075d5  mov     [rbx+88h], rax
0x1800075dc  mov     rax, [rsp+78h+arg_0]
0x1800075e4  mov     [rbx+90h], rax
0x1800075eb  mov     [rbx+48h], rdi
0x1800075ef  xorps   xmm0, xmm0
0x1800075f2  xor     eax, eax
0x1800075f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800075f8  mov     [rbx+78h], rax
0x1800075fc  movups  xmmword ptr [rbx+50h], xmm0
0x180007600  mov     [rbx+60h], rax
0x180007604  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000760b  test    rax, rax
0x18000760e  jz      short loc_180007617
0x180007610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007615  jmp     short loc_18000761A
0x180007617  mov     rax, rdi
0x18000761a  mov     [rbx+80h], rax
0x180007621  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007628  test    rax, rax
0x18000762b  jz      short loc_180007635
0x18000762d  mov     rcx, rbx
0x180007630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007635  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000763c  test    rax, rax
0x18000763f  jz      short loc_180007657
0x180007641  mov     r8d, 400h
0x180007647  mov     rdx, [rsp+78h+arg_60]
0x18000764f  mov     rcx, rbx
0x180007652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007657  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000765e  test    rax, rax
0x180007661  jz      short loc_18000766B
0x180007663  mov     rcx, rbx
0x180007666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007672  test    rax, rax
0x180007675  jz      short loc_180007685
0x180007677  test    byte ptr [rbx+4], 2
0x18000767b  jnz     short loc_180007685
0x18000767d  mov     rcx, rbx
0x180007680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007685  cmp     [rbx+8], edi
0x180007688  jl      short loc_1800076A4
0x18000768a  cmp     r15d, 3
0x18000768e  jnz     loc_180007773
0x180007694  mov     ecx, 8000FFFFh; this
0x180007699  mov     [rbx+8], ecx
0x18000769c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800076a1  mov     [rbx+0Ch], eax
0x1800076a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800076ab  jnz     short loc_1800076CC
0x1800076ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800076b4  test    rax, rax
0x1800076b7  jz      short loc_1800076C2
0x1800076b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076be  test    al, al
0x1800076c0  jmp     short loc_1800076CA
0x1800076c2  call    cs:__imp_IsDebuggerPresent
0x1800076c8  test    eax, eax
0x1800076ca  jz      short loc_1800076D2
0x1800076cc  test    byte ptr [rbx+4], 2
0x1800076d0  jz      short loc_1800076F6
0x1800076d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076d9  test    rax, rax
0x1800076dc  jz      short loc_18000773A
0x1800076de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800076e5  jnz     short loc_18000773A
0x1800076e7  xor     r8d, r8d
0x1800076ea  xor     edx, edx
0x1800076ec  mov     rcx, rbx
0x1800076ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f4  jmp     short loc_18000773A
0x1800076f6  mov     ebp, 800h
0x1800076fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180007702  test    rax, rax
0x180007705  jz      short loc_18000771E
0x180007707  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000770e  jnz     short loc_18000771E
0x180007710  mov     r8d, ebp
0x180007713  mov     rdx, rsi
0x180007716  mov     rcx, rbx
0x180007719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771e  cmp     [rsi], di
0x180007721  jnz     short loc_180007731
0x180007723  mov     r8, rbx; unsigned __int64
0x180007726  mov     rdx, rbp; unsigned __int16 *
0x180007729  mov     rcx, rsi; this
0x18000772c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007731  mov     rcx, rsi; lpOutputString
0x180007734  call    cs:__imp_OutputDebugStringW
0x18000773a  test    byte ptr [rbx+4], 4
0x18000773e  jnz     short loc_180007749
0x180007740  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007747  jz      short loc_18000775B
0x180007749  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007750  test    rax, rax
0x180007753  jz      short loc_18000775B
0x180007755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000775a  nop
0x18000775b  mov     rbx, [rsp+78h+arg_10]
0x180007763  add     rsp, 40h
0x180007767  pop     r15
0x180007769  pop     r14
0x18000776b  pop     r13
0x18000776d  pop     r12
0x18000776f  pop     rdi
0x180007770  pop     rsi
0x180007771  pop     rbp
0x180007772  retn
0x180007773  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
