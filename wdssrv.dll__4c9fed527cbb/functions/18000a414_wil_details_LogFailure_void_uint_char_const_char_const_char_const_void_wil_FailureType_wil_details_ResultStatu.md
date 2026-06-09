# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000a414`
- end: `0x18000a71b`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180006df8`

## callees

- `0x180006814`
- `0x1800091d4`
- `0x180009b0c`
- `0x18000a414`
- `0x18000b7c8`
- `0x18000b7f0`
- `0x18000b94c`
- `0x18000b96c`
- `0x18000eab4`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000a533`
- `KERNEL32!GetCurrentThreadId` at `0x18000a533`
- `KERNEL32!IsDebuggerPresent` at `0x18000a657`
- `KERNEL32!IsDebuggerPresent` at `0x18000a657`
- `KERNEL32!OutputDebugStringW` at `0x18000a6d0`
- `KERNEL32!OutputDebugStringW` at `0x18000a6d0`

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
        unsigned __int64 a15)
{
  int v17; // esi
  unsigned int v18; // edi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  v17 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v17 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 32) = CurrentThreadId;
  *(_DWORD *)(a15 + 64) = a2;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_DWORD *)(a15 + 68) = v17;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000a414  mov     [rsp+arg_10], rbx
0x18000a419  mov     [rsp+arg_8], edx
0x18000a41d  mov     [rsp+arg_0], rcx
0x18000a422  push    rbp
0x18000a423  push    rsi
0x18000a424  push    rdi
0x18000a425  push    r12
0x18000a427  push    r13
0x18000a429  push    r14
0x18000a42b  push    r15
0x18000a42d  sub     rsp, 40h
0x18000a431  mov     rax, [rsp+78h+arg_60]
0x18000a439  mov     r13, r8
0x18000a43c  mov     r15, [rsp+78h+arg_38]
0x18000a444  xor     r8d, r8d
0x18000a447  mov     rbx, [rsp+78h+arg_70]
0x18000a44f  mov     r10, rcx
0x18000a452  mov     ebp, [rsp+78h+arg_30]
0x18000a459  mov     r12, r9
0x18000a45c  mov     r14, [rsp+78h+lpOutputString]
0x18000a464  mov     esi, r8d
0x18000a467  mov     ecx, ebp
0x18000a469  mov     [r14], r8w
0x18000a46d  mov     [rax], r8b
0x18000a470  mov     edi, [r15]
0x18000a473  mov     [rbx+8], edi
0x18000a476  mov     eax, [r15+4]
0x18000a47a  mov     [rbx+0Ch], eax
0x18000a47d  test    ebp, ebp
0x18000a47f  jz      short loc_18000A4EA
0x18000a481  sub     ecx, 1
0x18000a484  jz      short loc_18000A4E1
0x18000a486  sub     ecx, 1
0x18000a489  jz      short loc_18000A499
0x18000a48b  cmp     ecx, 1
0x18000a48e  jnz     short loc_18000A4F3
0x18000a490  mov     ecx, edi; this
0x18000a492  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a497  jmp     short loc_18000A4F1
0x18000a499  test    edi, edi
0x18000a49b  js      short loc_18000A4D8
0x18000a49d  mov     rax, [rsp+78h+arg_28]
0x18000a4a5  mov     edi, 8007029Ch
0x18000a4aa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a4ae  mov     r8, r13; int
0x18000a4b1  mov     [rsp+78h+var_50], rax; __int64
0x18000a4b6  mov     rcx, r10; int
0x18000a4b9  mov     rax, [rsp+78h+arg_20]
0x18000a4c1  mov     [rsp+78h+var_58], rax; __int64
0x18000a4c6  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000a4cb  mov     ecx, edi; this
0x18000a4cd  mov     [rbx+8], edi
0x18000a4d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a4d5  mov     [rbx+0Ch], eax
0x18000a4d8  mov     ecx, edi; this
0x18000a4da  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a4df  jmp     short loc_18000A4F1
0x18000a4e1  mov     ecx, edi; this
0x18000a4e3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a4e8  jmp     short loc_18000A4F1
0x18000a4ea  mov     ecx, edi; this
0x18000a4ec  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a4f1  mov     esi, eax
0x18000a4f3  xor     edi, edi
0x18000a4f5  mov     [rbx], ebp
0x18000a4f7  mov     [rbx+4], edi
0x18000a4fa  cmp     dword ptr [r15+8], 1
0x18000a4ff  jnz     short loc_18000A508
0x18000a501  mov     dword ptr [rbx+4], 8
0x18000a508  mov     eax, 1
0x18000a50d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000a515  inc     eax
0x18000a517  mov     [rbx+10h], eax
0x18000a51a  mov     rax, [rsp+78h+arg_40]
0x18000a522  test    rax, rax
0x18000a525  jz      short loc_18000A52C
0x18000a527  cmp     [rax], di
0x18000a52a  jnz     short loc_18000A52F
0x18000a52c  mov     rax, rdi
0x18000a52f  mov     [rbx+18h], rax
0x18000a533  call    cs:__imp_GetCurrentThreadId
0x18000a53a  nop     dword ptr [rax+rax+00h]
0x18000a53f  mov     [rbx+38h], r13
0x18000a543  xorps   xmm0, xmm0
0x18000a546  mov     [rbx+20h], eax
0x18000a549  mov     eax, [rsp+78h+arg_8]
0x18000a550  mov     [rbx+40h], eax
0x18000a553  mov     rax, [rsp+78h+arg_20]
0x18000a55b  mov     [rbx+28h], rax
0x18000a55f  mov     rax, [rsp+78h+arg_28]
0x18000a567  mov     [rbx+88h], rax
0x18000a56e  mov     rax, [rsp+78h+arg_0]
0x18000a576  mov     [rbx+90h], rax
0x18000a57d  xor     eax, eax
0x18000a57f  mov     [rbx+44h], esi
0x18000a582  mov     [rbx+30h], r12
0x18000a586  mov     [rbx+48h], rdi
0x18000a58a  movups  xmmword ptr [rbx+68h], xmm0
0x18000a58e  mov     [rbx+78h], rax
0x18000a592  movups  xmmword ptr [rbx+50h], xmm0
0x18000a596  mov     [rbx+60h], rax
0x18000a59a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a5a1  test    rax, rax
0x18000a5a4  jz      short loc_18000A5AD
0x18000a5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ab  jmp     short loc_18000A5B0
0x18000a5ad  mov     rax, rdi
0x18000a5b0  mov     [rbx+80h], rax
0x18000a5b7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a5be  test    rax, rax
0x18000a5c1  jz      short loc_18000A5CB
0x18000a5c3  mov     rcx, rbx
0x18000a5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5cb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a5d2  test    rax, rax
0x18000a5d5  jz      short loc_18000A5ED
0x18000a5d7  mov     rdx, [rsp+78h+arg_60]
0x18000a5df  mov     r8d, 400h
0x18000a5e5  mov     rcx, rbx
0x18000a5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ed  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a5f4  test    rax, rax
0x18000a5f7  jz      short loc_18000A601
0x18000a5f9  mov     rcx, rbx
0x18000a5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a601  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a608  test    rax, rax
0x18000a60b  jz      short loc_18000A61B
0x18000a60d  test    byte ptr [rbx+4], 2
0x18000a611  jnz     short loc_18000A61B
0x18000a613  mov     rcx, rbx
0x18000a616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a61b  cmp     [rbx+8], edi
0x18000a61e  jl      short loc_18000A639
0x18000a620  cmp     ebp, 3
0x18000a623  jnz     loc_18000A715
0x18000a629  mov     ecx, 8000FFFFh; this
0x18000a62e  mov     [rbx+8], ecx
0x18000a631  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a636  mov     [rbx+0Ch], eax
0x18000a639  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a640  jnz     short loc_18000A667
0x18000a642  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a649  test    rax, rax
0x18000a64c  jz      short loc_18000A657
0x18000a64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a653  test    al, al
0x18000a655  jmp     short loc_18000A665
0x18000a657  call    cs:__imp_IsDebuggerPresent
0x18000a65e  nop     dword ptr [rax+rax+00h]
0x18000a663  test    eax, eax
0x18000a665  jz      short loc_18000A66D
0x18000a667  test    byte ptr [rbx+4], 2
0x18000a66b  jz      short loc_18000A691
0x18000a66d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a674  test    rax, rax
0x18000a677  jz      short loc_18000A6DC
0x18000a679  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a680  jnz     short loc_18000A6DC
0x18000a682  xor     r8d, r8d
0x18000a685  xor     edx, edx
0x18000a687  mov     rcx, rbx
0x18000a68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a68f  jmp     short loc_18000A6DC
0x18000a691  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a698  mov     esi, 800h
0x18000a69d  test    rax, rax
0x18000a6a0  jz      short loc_18000A6B9
0x18000a6a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a6a9  jnz     short loc_18000A6B9
0x18000a6ab  mov     r8d, esi
0x18000a6ae  mov     rdx, r14
0x18000a6b1  mov     rcx, rbx
0x18000a6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b9  cmp     [r14], di
0x18000a6bd  jnz     short loc_18000A6CD
0x18000a6bf  mov     r8, rbx; unsigned __int64
0x18000a6c2  mov     rdx, rsi; unsigned __int16 *
0x18000a6c5  mov     rcx, r14; this
0x18000a6c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a6cd  mov     rcx, r14; lpOutputString
0x18000a6d0  call    cs:__imp_OutputDebugStringW
0x18000a6d7  nop     dword ptr [rax+rax+00h]
0x18000a6dc  test    byte ptr [rbx+4], 4
0x18000a6e0  jnz     short loc_18000A6EB
0x18000a6e2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a6e9  jz      short loc_18000A6FC
0x18000a6eb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a6f2  test    rax, rax
0x18000a6f5  jz      short loc_18000A6FC
0x18000a6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fc  mov     rbx, [rsp+78h+arg_10]
0x18000a704  add     rsp, 40h
0x18000a708  pop     r15
0x18000a70a  pop     r14
0x18000a70c  pop     r13
0x18000a70e  pop     r12
0x18000a710  pop     rdi
0x18000a711  pop     rsi
0x18000a712  pop     rbp
0x18000a713  retn
0x18000a715  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
