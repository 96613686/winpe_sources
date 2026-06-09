# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800a5528`
- end: `0x1800a581d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800a091c`
- `0x1800a09cc`
- `0x1800a0ac0`

## callees

- `0x18009a5ec`
- `0x1800a0870`
- `0x1800a321c`
- `0x1800a5528`
- `0x1800a602c`
- `0x1800a6050`
- `0x1800a6064`
- `0x1800a6080`
- `0x1800a6e24`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a564b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a564b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a576c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a576c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a57de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a57de`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x1800a5528  mov     [rsp+arg_10], rbx
0x1800a552d  mov     [rsp+arg_8], edx
0x1800a5531  mov     [rsp+arg_0], rcx
0x1800a5536  push    rbp
0x1800a5537  push    rsi
0x1800a5538  push    rdi
0x1800a5539  push    r12
0x1800a553b  push    r13
0x1800a553d  push    r14
0x1800a553f  push    r15
0x1800a5541  sub     rsp, 40h
0x1800a5545  mov     r12, r9
0x1800a5548  mov     r13, r8
0x1800a554b  mov     r10, rcx
0x1800a554e  xor     eax, eax
0x1800a5550  mov     rsi, [rsp+78h+lpOutputString]
0x1800a5558  mov     [rsi], ax
0x1800a555b  mov     rax, [rsp+78h+arg_60]
0x1800a5563  mov     byte ptr [rax], 0
0x1800a5566  mov     r14, [rsp+78h+arg_38]
0x1800a556e  mov     edi, [r14]
0x1800a5571  mov     rbx, [rsp+78h+arg_78]
0x1800a5579  mov     [rbx+8], edi
0x1800a557c  mov     eax, [r14+4]
0x1800a5580  mov     [rbx+0Ch], eax
0x1800a5583  xor     ebp, ebp
0x1800a5585  mov     r15d, [rsp+78h+arg_30]
0x1800a558d  mov     ecx, r15d
0x1800a5590  test    r15d, r15d
0x1800a5593  jz      short loc_1800A55FB
0x1800a5595  sub     ecx, 1
0x1800a5598  jz      short loc_1800A55F2
0x1800a559a  sub     ecx, 1
0x1800a559d  jz      short loc_1800A55AD
0x1800a559f  cmp     ecx, 1
0x1800a55a2  jnz     short loc_1800A5604
0x1800a55a4  mov     ecx, edi; this
0x1800a55a6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800a55ab  jmp     short loc_1800A5602
0x1800a55ad  test    edi, edi
0x1800a55af  js      short loc_1800A55E9
0x1800a55b1  mov     edi, 8007029Ch
0x1800a55b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800a55ba  mov     rax, [rsp+78h+arg_28]
0x1800a55c2  mov     [rsp+78h+var_50], rax; __int64
0x1800a55c7  mov     rax, [rsp+78h+arg_20]
0x1800a55cf  mov     [rsp+78h+var_58], rax; __int64
0x1800a55d4  mov     rcx, r10; int
0x1800a55d7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800a55dc  mov     [rbx+8], edi
0x1800a55df  mov     ecx, edi; this
0x1800a55e1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a55e6  mov     [rbx+0Ch], eax
0x1800a55e9  mov     ecx, edi; this
0x1800a55eb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800a55f0  jmp     short loc_1800A5602
0x1800a55f2  mov     ecx, edi; this
0x1800a55f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800a55f9  jmp     short loc_1800A5602
0x1800a55fb  mov     ecx, edi; this
0x1800a55fd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800a5602  mov     ebp, eax
0x1800a5604  mov     [rbx], r15d
0x1800a5607  mov     eax, [rsp+78h+arg_70]
0x1800a560e  mov     [rbx+4], eax
0x1800a5611  cmp     dword ptr [r14+8], 1
0x1800a5616  jnz     short loc_1800A561E
0x1800a5618  or      eax, 8
0x1800a561b  mov     [rbx+4], eax
0x1800a561e  mov     eax, 1
0x1800a5623  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a562b  inc     eax
0x1800a562d  mov     [rbx+10h], eax
0x1800a5630  mov     rax, [rsp+78h+arg_40]
0x1800a5638  xor     edi, edi
0x1800a563a  test    rax, rax
0x1800a563d  jz      short loc_1800A5644
0x1800a563f  cmp     [rax], di
0x1800a5642  jnz     short loc_1800A5647
0x1800a5644  mov     rax, rdi
0x1800a5647  mov     [rbx+18h], rax
0x1800a564b  call    cs:__imp_GetCurrentThreadId
0x1800a5651  mov     [rbx+20h], eax
0x1800a5654  mov     [rbx+38h], r13
0x1800a5658  mov     eax, [rsp+78h+arg_8]
0x1800a565f  mov     [rbx+40h], eax
0x1800a5662  mov     [rbx+44h], ebp
0x1800a5665  mov     rax, [rsp+78h+arg_20]
0x1800a566d  mov     [rbx+28h], rax
0x1800a5671  mov     [rbx+30h], r12
0x1800a5675  mov     rax, [rsp+78h+arg_28]
0x1800a567d  mov     [rbx+88h], rax
0x1800a5684  mov     rax, [rsp+78h+arg_0]
0x1800a568c  mov     [rbx+90h], rax
0x1800a5693  mov     [rbx+48h], rdi
0x1800a5697  xorps   xmm0, xmm0
0x1800a569a  xor     eax, eax
0x1800a569c  movups  xmmword ptr [rbx+68h], xmm0
0x1800a56a0  mov     [rbx+78h], rax
0x1800a56a4  movups  xmmword ptr [rbx+50h], xmm0
0x1800a56a8  mov     [rbx+60h], rax
0x1800a56ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a56b3  test    rax, rax
0x1800a56b6  jz      short loc_1800A56BF
0x1800a56b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56bd  jmp     short loc_1800A56C2
0x1800a56bf  mov     rax, rdi
0x1800a56c2  mov     [rbx+80h], rax
0x1800a56c9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a56d0  test    rax, rax
0x1800a56d3  jz      short loc_1800A56DD
0x1800a56d5  mov     rcx, rbx
0x1800a56d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56dd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a56e4  test    rax, rax
0x1800a56e7  jz      short loc_1800A56FF
0x1800a56e9  mov     r8d, 400h
0x1800a56ef  mov     rdx, [rsp+78h+arg_60]
0x1800a56f7  mov     rcx, rbx
0x1800a56fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56ff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a5706  test    rax, rax
0x1800a5709  jz      short loc_1800A5713
0x1800a570b  mov     rcx, rbx
0x1800a570e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5713  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a571a  test    rax, rax
0x1800a571d  jz      short loc_1800A572D
0x1800a571f  test    byte ptr [rbx+4], 2
0x1800a5723  jnz     short loc_1800A572D
0x1800a5725  mov     rcx, rbx
0x1800a5728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a572d  cmp     [rbx+8], edi
0x1800a5730  jl      short loc_1800A574E
0x1800a5732  cmp     r15d, 3
0x1800a5736  jz      short loc_1800A573E
0x1800a5738  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800a573e  mov     ecx, 8000FFFFh; this
0x1800a5743  mov     [rbx+8], ecx
0x1800a5746  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a574b  mov     [rbx+0Ch], eax
0x1800a574e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800a5755  jnz     short loc_1800A5776
0x1800a5757  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a575e  test    rax, rax
0x1800a5761  jz      short loc_1800A576C
0x1800a5763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5768  test    al, al
0x1800a576a  jmp     short loc_1800A5774
0x1800a576c  call    cs:__imp_IsDebuggerPresent
0x1800a5772  test    eax, eax
0x1800a5774  jz      short loc_1800A577C
0x1800a5776  test    byte ptr [rbx+4], 2
0x1800a577a  jz      short loc_1800A57A0
0x1800a577c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a5783  test    rax, rax
0x1800a5786  jz      short loc_1800A57E4
0x1800a5788  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a578f  jnz     short loc_1800A57E4
0x1800a5791  xor     r8d, r8d
0x1800a5794  xor     edx, edx
0x1800a5796  mov     rcx, rbx
0x1800a5799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a579e  jmp     short loc_1800A57E4
0x1800a57a0  mov     ebp, 800h
0x1800a57a5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a57ac  test    rax, rax
0x1800a57af  jz      short loc_1800A57C8
0x1800a57b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a57b8  jnz     short loc_1800A57C8
0x1800a57ba  mov     r8d, ebp
0x1800a57bd  mov     rdx, rsi
0x1800a57c0  mov     rcx, rbx
0x1800a57c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a57c8  cmp     [rsi], di
0x1800a57cb  jnz     short loc_1800A57DB
0x1800a57cd  mov     r8, rbx; unsigned __int64
0x1800a57d0  mov     rdx, rbp; wchar_t *
0x1800a57d3  mov     rcx, rsi; this
0x1800a57d6  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800a57db  mov     rcx, rsi; lpOutputString
0x1800a57de  call    cs:__imp_OutputDebugStringW
0x1800a57e4  test    byte ptr [rbx+4], 4
0x1800a57e8  jnz     short loc_1800A57F3
0x1800a57ea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800a57f1  jz      short loc_1800A5805
0x1800a57f3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a57fa  test    rax, rax
0x1800a57fd  jz      short loc_1800A5805
0x1800a57ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5804  nop
0x1800a5805  mov     rbx, [rsp+78h+arg_10]
0x1800a580d  add     rsp, 40h
0x1800a5811  pop     r15
0x1800a5813  pop     r14
0x1800a5815  pop     r13
0x1800a5817  pop     r12
0x1800a5819  pop     rdi
0x1800a581a  pop     rsi
0x1800a581b  pop     rbp
0x1800a581c  retn
```
