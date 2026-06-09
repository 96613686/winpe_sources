# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14001880c`
- end: `0x140018b14`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x14000f030`
- `0x14001871c`
- `0x14002ebb8`
- `0x14002ec68`

## callees

- `0x14000db10`
- `0x140011ff4`
- `0x14001880c`
- `0x140018b20`
- `0x14001e174`
- `0x14001ff04`
- `0x14002eaec`
- `0x14002f2f4`
- `0x14002f7fc`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001892f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001892f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140018a56`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140018a56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140018ace`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140018ace`

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
0x14001880c  mov     [rsp+arg_10], rbx
0x140018811  mov     [rsp+arg_8], edx
0x140018815  mov     [rsp+arg_0], rcx
0x14001881a  push    rbp
0x14001881b  push    rsi
0x14001881c  push    rdi
0x14001881d  push    r12
0x14001881f  push    r13
0x140018821  push    r14
0x140018823  push    r15
0x140018825  sub     rsp, 40h
0x140018829  mov     r12, r9
0x14001882c  mov     r13, r8
0x14001882f  mov     r10, rcx
0x140018832  xor     eax, eax
0x140018834  mov     rsi, [rsp+78h+lpOutputString]
0x14001883c  mov     [rsi], ax
0x14001883f  mov     rax, [rsp+78h+arg_60]
0x140018847  mov     byte ptr [rax], 0
0x14001884a  mov     r14, [rsp+78h+arg_38]
0x140018852  mov     edi, [r14]
0x140018855  mov     rbx, [rsp+78h+arg_78]
0x14001885d  mov     [rbx+8], edi
0x140018860  mov     eax, [r14+4]
0x140018864  mov     [rbx+0Ch], eax
0x140018867  xor     ebp, ebp
0x140018869  mov     r15d, [rsp+78h+arg_30]
0x140018871  mov     ecx, r15d
0x140018874  test    r15d, r15d
0x140018877  jz      short loc_1400188DF
0x140018879  sub     ecx, 1
0x14001887c  jz      short loc_1400188D6
0x14001887e  sub     ecx, 1
0x140018881  jz      short loc_140018891
0x140018883  cmp     ecx, 1
0x140018886  jnz     short loc_1400188E8
0x140018888  mov     ecx, edi; this
0x14001888a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14001888f  jmp     short loc_1400188E6
0x140018891  test    edi, edi
0x140018893  js      short loc_1400188CD
0x140018895  mov     edi, 8007029Ch
0x14001889a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14001889e  mov     rax, [rsp+78h+arg_28]
0x1400188a6  mov     [rsp+78h+var_50], rax; __int64
0x1400188ab  mov     rax, [rsp+78h+arg_20]
0x1400188b3  mov     [rsp+78h+var_58], rax; __int64
0x1400188b8  mov     rcx, r10; int
0x1400188bb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400188c0  mov     [rbx+8], edi
0x1400188c3  mov     ecx, edi; this
0x1400188c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400188ca  mov     [rbx+0Ch], eax
0x1400188cd  mov     ecx, edi; this
0x1400188cf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400188d4  jmp     short loc_1400188E6
0x1400188d6  mov     ecx, edi; this
0x1400188d8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400188dd  jmp     short loc_1400188E6
0x1400188df  mov     ecx, edi; this
0x1400188e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400188e6  mov     ebp, eax
0x1400188e8  mov     [rbx], r15d
0x1400188eb  mov     eax, [rsp+78h+arg_70]
0x1400188f2  mov     [rbx+4], eax
0x1400188f5  cmp     dword ptr [r14+8], 1
0x1400188fa  jnz     short loc_140018902
0x1400188fc  or      eax, 8
0x1400188ff  mov     [rbx+4], eax
0x140018902  mov     eax, 1
0x140018907  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14001890f  inc     eax
0x140018911  mov     [rbx+10h], eax
0x140018914  mov     rax, [rsp+78h+arg_40]
0x14001891c  xor     edi, edi
0x14001891e  test    rax, rax
0x140018921  jz      short loc_140018928
0x140018923  cmp     [rax], di
0x140018926  jnz     short loc_14001892B
0x140018928  mov     rax, rdi
0x14001892b  mov     [rbx+18h], rax
0x14001892f  call    cs:__imp_GetCurrentThreadId
0x140018936  nop     dword ptr [rax+rax+00h]
0x14001893b  mov     [rbx+20h], eax
0x14001893e  mov     [rbx+38h], r13
0x140018942  mov     eax, [rsp+78h+arg_8]
0x140018949  mov     [rbx+40h], eax
0x14001894c  mov     [rbx+44h], ebp
0x14001894f  mov     rax, [rsp+78h+arg_20]
0x140018957  mov     [rbx+28h], rax
0x14001895b  mov     [rbx+30h], r12
0x14001895f  mov     rax, [rsp+78h+arg_28]
0x140018967  mov     [rbx+88h], rax
0x14001896e  mov     rax, [rsp+78h+arg_0]
0x140018976  mov     [rbx+90h], rax
0x14001897d  mov     [rbx+48h], rdi
0x140018981  xorps   xmm0, xmm0
0x140018984  xor     eax, eax
0x140018986  movups  xmmword ptr [rbx+68h], xmm0
0x14001898a  mov     [rbx+78h], rax
0x14001898e  movups  xmmword ptr [rbx+50h], xmm0
0x140018992  mov     [rbx+60h], rax
0x140018996  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001899d  test    rax, rax
0x1400189a0  jz      short loc_1400189A9
0x1400189a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400189a7  jmp     short loc_1400189AC
0x1400189a9  mov     rax, rdi
0x1400189ac  mov     [rbx+80h], rax
0x1400189b3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400189ba  test    rax, rax
0x1400189bd  jz      short loc_1400189C7
0x1400189bf  mov     rcx, rbx
0x1400189c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400189c7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400189ce  test    rax, rax
0x1400189d1  jz      short loc_1400189E9
0x1400189d3  mov     r8d, 400h
0x1400189d9  mov     rdx, [rsp+78h+arg_60]
0x1400189e1  mov     rcx, rbx
0x1400189e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400189e9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400189f0  test    rax, rax
0x1400189f3  jz      short loc_1400189FD
0x1400189f5  mov     rcx, rbx
0x1400189f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400189fd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140018a04  test    rax, rax
0x140018a07  jz      short loc_140018A17
0x140018a09  test    byte ptr [rbx+4], 2
0x140018a0d  jnz     short loc_140018A17
0x140018a0f  mov     rcx, rbx
0x140018a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018a17  cmp     [rbx+8], edi
0x140018a1a  jl      short loc_140018A38
0x140018a1c  cmp     r15d, 3
0x140018a20  jz      short loc_140018A28
0x140018a22  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140018a28  mov     ecx, 8000FFFFh; this
0x140018a2d  mov     [rbx+8], ecx
0x140018a30  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140018a35  mov     [rbx+0Ch], eax
0x140018a38  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140018a3f  jnz     short loc_140018A66
0x140018a41  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140018a48  test    rax, rax
0x140018a4b  jz      short loc_140018A56
0x140018a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018a52  test    al, al
0x140018a54  jmp     short loc_140018A64
0x140018a56  call    cs:__imp_IsDebuggerPresent
0x140018a5d  nop     dword ptr [rax+rax+00h]
0x140018a62  test    eax, eax
0x140018a64  jz      short loc_140018A6C
0x140018a66  test    byte ptr [rbx+4], 2
0x140018a6a  jz      short loc_140018A90
0x140018a6c  mov     rax, cs:g_pfnResultLoggingCallback
0x140018a73  test    rax, rax
0x140018a76  jz      short loc_140018ADA
0x140018a78  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140018a7f  jnz     short loc_140018ADA
0x140018a81  xor     r8d, r8d
0x140018a84  xor     edx, edx
0x140018a86  mov     rcx, rbx
0x140018a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018a8e  jmp     short loc_140018ADA
0x140018a90  mov     ebp, 800h
0x140018a95  mov     rax, cs:g_pfnResultLoggingCallback
0x140018a9c  test    rax, rax
0x140018a9f  jz      short loc_140018AB8
0x140018aa1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140018aa8  jnz     short loc_140018AB8
0x140018aaa  mov     r8d, ebp
0x140018aad  mov     rdx, rsi
0x140018ab0  mov     rcx, rbx
0x140018ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018ab8  cmp     [rsi], di
0x140018abb  jnz     short loc_140018ACB
0x140018abd  mov     r8, rbx; unsigned __int64
0x140018ac0  mov     rdx, rbp; unsigned __int16 *
0x140018ac3  mov     rcx, rsi; this
0x140018ac6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140018acb  mov     rcx, rsi; lpOutputString
0x140018ace  call    cs:__imp_OutputDebugStringW
0x140018ad5  nop     dword ptr [rax+rax+00h]
0x140018ada  test    byte ptr [rbx+4], 4
0x140018ade  jnz     short loc_140018AE9
0x140018ae0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140018ae7  jz      short loc_140018AFB
0x140018ae9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140018af0  test    rax, rax
0x140018af3  jz      short loc_140018AFB
0x140018af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018afa  nop
0x140018afb  mov     rbx, [rsp+78h+arg_10]
0x140018b03  add     rsp, 40h
0x140018b07  pop     r15
0x140018b09  pop     r14
0x140018b0b  pop     r13
0x140018b0d  pop     r12
0x140018b0f  pop     rdi
0x140018b10  pop     rsi
0x140018b11  pop     rbp
0x140018b12  retn
```
