# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000796c`
- end: `0x180007c73`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003070`

## callees

- `0x180002a8c`
- `0x1800062d4`
- `0x180006bdc`
- `0x18000796c`
- `0x1800089f4`
- `0x180008a20`
- `0x180008b7c`
- `0x180008b9c`
- `0x18000b818`
- `0x18000e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180007baf`
- `KERNEL32!IsDebuggerPresent` at `0x180007baf`
- `KERNEL32!GetCurrentThreadId` at `0x180007a8b`
- `KERNEL32!GetCurrentThreadId` at `0x180007a8b`
- `KERNEL32!OutputDebugStringW` at `0x180007c28`
- `KERNEL32!OutputDebugStringW` at `0x180007c28`

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
0x18000796c  mov     [rsp+arg_10], rbx
0x180007971  mov     [rsp+arg_8], edx
0x180007975  mov     [rsp+arg_0], rcx
0x18000797a  push    rbp
0x18000797b  push    rsi
0x18000797c  push    rdi
0x18000797d  push    r12
0x18000797f  push    r13
0x180007981  push    r14
0x180007983  push    r15
0x180007985  sub     rsp, 40h
0x180007989  mov     rax, [rsp+78h+arg_60]
0x180007991  mov     r13, r8
0x180007994  mov     r15, [rsp+78h+arg_38]
0x18000799c  xor     r8d, r8d
0x18000799f  mov     rbx, [rsp+78h+arg_70]
0x1800079a7  mov     r10, rcx
0x1800079aa  mov     ebp, [rsp+78h+arg_30]
0x1800079b1  mov     r12, r9
0x1800079b4  mov     r14, [rsp+78h+lpOutputString]
0x1800079bc  mov     esi, r8d
0x1800079bf  mov     ecx, ebp
0x1800079c1  mov     [r14], r8w
0x1800079c5  mov     [rax], r8b
0x1800079c8  mov     edi, [r15]
0x1800079cb  mov     [rbx+8], edi
0x1800079ce  mov     eax, [r15+4]
0x1800079d2  mov     [rbx+0Ch], eax
0x1800079d5  test    ebp, ebp
0x1800079d7  jz      short loc_180007A42
0x1800079d9  sub     ecx, 1
0x1800079dc  jz      short loc_180007A39
0x1800079de  sub     ecx, 1
0x1800079e1  jz      short loc_1800079F1
0x1800079e3  cmp     ecx, 1
0x1800079e6  jnz     short loc_180007A4B
0x1800079e8  mov     ecx, edi; this
0x1800079ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800079ef  jmp     short loc_180007A49
0x1800079f1  test    edi, edi
0x1800079f3  js      short loc_180007A30
0x1800079f5  mov     rax, [rsp+78h+arg_28]
0x1800079fd  mov     edi, 8007029Ch
0x180007a02  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007a06  mov     r8, r13; int
0x180007a09  mov     [rsp+78h+var_50], rax; __int64
0x180007a0e  mov     rcx, r10; int
0x180007a11  mov     rax, [rsp+78h+arg_20]
0x180007a19  mov     [rsp+78h+var_58], rax; __int64
0x180007a1e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180007a23  mov     ecx, edi; this
0x180007a25  mov     [rbx+8], edi
0x180007a28  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007a2d  mov     [rbx+0Ch], eax
0x180007a30  mov     ecx, edi; this
0x180007a32  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007a37  jmp     short loc_180007A49
0x180007a39  mov     ecx, edi; this
0x180007a3b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007a40  jmp     short loc_180007A49
0x180007a42  mov     ecx, edi; this
0x180007a44  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007a49  mov     esi, eax
0x180007a4b  xor     edi, edi
0x180007a4d  mov     [rbx], ebp
0x180007a4f  mov     [rbx+4], edi
0x180007a52  cmp     dword ptr [r15+8], 1
0x180007a57  jnz     short loc_180007A60
0x180007a59  mov     dword ptr [rbx+4], 8
0x180007a60  mov     eax, 1
0x180007a65  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180007a6d  inc     eax
0x180007a6f  mov     [rbx+10h], eax
0x180007a72  mov     rax, [rsp+78h+arg_40]
0x180007a7a  test    rax, rax
0x180007a7d  jz      short loc_180007A84
0x180007a7f  cmp     [rax], di
0x180007a82  jnz     short loc_180007A87
0x180007a84  mov     rax, rdi
0x180007a87  mov     [rbx+18h], rax
0x180007a8b  call    cs:__imp_GetCurrentThreadId
0x180007a92  nop     dword ptr [rax+rax+00h]
0x180007a97  mov     [rbx+38h], r13
0x180007a9b  xorps   xmm0, xmm0
0x180007a9e  mov     [rbx+20h], eax
0x180007aa1  mov     eax, [rsp+78h+arg_8]
0x180007aa8  mov     [rbx+40h], eax
0x180007aab  mov     rax, [rsp+78h+arg_20]
0x180007ab3  mov     [rbx+28h], rax
0x180007ab7  mov     rax, [rsp+78h+arg_28]
0x180007abf  mov     [rbx+88h], rax
0x180007ac6  mov     rax, [rsp+78h+arg_0]
0x180007ace  mov     [rbx+90h], rax
0x180007ad5  xor     eax, eax
0x180007ad7  mov     [rbx+44h], esi
0x180007ada  mov     [rbx+30h], r12
0x180007ade  mov     [rbx+48h], rdi
0x180007ae2  movups  xmmword ptr [rbx+68h], xmm0
0x180007ae6  mov     [rbx+78h], rax
0x180007aea  movups  xmmword ptr [rbx+50h], xmm0
0x180007aee  mov     [rbx+60h], rax
0x180007af2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007af9  test    rax, rax
0x180007afc  jz      short loc_180007B05
0x180007afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b03  jmp     short loc_180007B08
0x180007b05  mov     rax, rdi
0x180007b08  mov     [rbx+80h], rax
0x180007b0f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007b16  test    rax, rax
0x180007b19  jz      short loc_180007B23
0x180007b1b  mov     rcx, rbx
0x180007b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b23  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007b2a  test    rax, rax
0x180007b2d  jz      short loc_180007B45
0x180007b2f  mov     rdx, [rsp+78h+arg_60]
0x180007b37  mov     r8d, 400h
0x180007b3d  mov     rcx, rbx
0x180007b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b45  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b4c  test    rax, rax
0x180007b4f  jz      short loc_180007B59
0x180007b51  mov     rcx, rbx
0x180007b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b59  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b60  test    rax, rax
0x180007b63  jz      short loc_180007B73
0x180007b65  test    byte ptr [rbx+4], 2
0x180007b69  jnz     short loc_180007B73
0x180007b6b  mov     rcx, rbx
0x180007b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b73  cmp     [rbx+8], edi
0x180007b76  jl      short loc_180007B91
0x180007b78  cmp     ebp, 3
0x180007b7b  jnz     loc_180007C6D
0x180007b81  mov     ecx, 8000FFFFh; this
0x180007b86  mov     [rbx+8], ecx
0x180007b89  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007b8e  mov     [rbx+0Ch], eax
0x180007b91  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007b98  jnz     short loc_180007BBF
0x180007b9a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007ba1  test    rax, rax
0x180007ba4  jz      short loc_180007BAF
0x180007ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bab  test    al, al
0x180007bad  jmp     short loc_180007BBD
0x180007baf  call    cs:__imp_IsDebuggerPresent
0x180007bb6  nop     dword ptr [rax+rax+00h]
0x180007bbb  test    eax, eax
0x180007bbd  jz      short loc_180007BC5
0x180007bbf  test    byte ptr [rbx+4], 2
0x180007bc3  jz      short loc_180007BE9
0x180007bc5  mov     rax, cs:g_pfnResultLoggingCallback
0x180007bcc  test    rax, rax
0x180007bcf  jz      short loc_180007C34
0x180007bd1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007bd8  jnz     short loc_180007C34
0x180007bda  xor     r8d, r8d
0x180007bdd  xor     edx, edx
0x180007bdf  mov     rcx, rbx
0x180007be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be7  jmp     short loc_180007C34
0x180007be9  mov     rax, cs:g_pfnResultLoggingCallback
0x180007bf0  mov     esi, 800h
0x180007bf5  test    rax, rax
0x180007bf8  jz      short loc_180007C11
0x180007bfa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007c01  jnz     short loc_180007C11
0x180007c03  mov     r8d, esi
0x180007c06  mov     rdx, r14
0x180007c09  mov     rcx, rbx
0x180007c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c11  cmp     [r14], di
0x180007c15  jnz     short loc_180007C25
0x180007c17  mov     r8, rbx; unsigned __int64
0x180007c1a  mov     rdx, rsi; unsigned __int16 *
0x180007c1d  mov     rcx, r14; this
0x180007c20  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007c25  mov     rcx, r14; lpOutputString
0x180007c28  call    cs:__imp_OutputDebugStringW
0x180007c2f  nop     dword ptr [rax+rax+00h]
0x180007c34  test    byte ptr [rbx+4], 4
0x180007c38  jnz     short loc_180007C43
0x180007c3a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007c41  jz      short loc_180007C54
0x180007c43  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007c4a  test    rax, rax
0x180007c4d  jz      short loc_180007C54
0x180007c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c54  mov     rbx, [rsp+78h+arg_10]
0x180007c5c  add     rsp, 40h
0x180007c60  pop     r15
0x180007c62  pop     r14
0x180007c64  pop     r13
0x180007c66  pop     r12
0x180007c68  pop     rdi
0x180007c69  pop     rsi
0x180007c6a  pop     rbp
0x180007c6b  retn
0x180007c6d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
