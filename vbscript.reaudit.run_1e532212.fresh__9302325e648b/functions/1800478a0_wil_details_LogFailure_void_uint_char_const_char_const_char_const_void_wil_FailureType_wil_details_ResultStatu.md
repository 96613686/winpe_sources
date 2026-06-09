# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800478a0`
- end: `0x180047b98`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800467a4`
- `0x180046af0`

## callees

- `0x18003e834`
- `0x1800466e4`
- `0x1800472b4`
- `0x1800478a0`
- `0x180048194`
- `0x1800481b0`
- `0x1800481c4`
- `0x1800481e0`
- `0x180048834`
- `0x180077010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180047ae2`
- `KERNEL32!IsDebuggerPresent` at `0x180047ae2`
- `KERNEL32!OutputDebugStringW` at `0x180047b54`
- `KERNEL32!OutputDebugStringW` at `0x180047b54`
- `KERNEL32!GetCurrentThreadId` at `0x1800479c3`
- `KERNEL32!GetCurrentThreadId` at `0x1800479c3`

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
0x1800478a0  mov     [rsp+arg_10], rbx
0x1800478a5  mov     [rsp+arg_8], edx
0x1800478a9  mov     [rsp+arg_0], rcx
0x1800478ae  push    rbp
0x1800478af  push    rsi
0x1800478b0  push    rdi
0x1800478b1  push    r12
0x1800478b3  push    r13
0x1800478b5  push    r14
0x1800478b7  push    r15
0x1800478b9  sub     rsp, 40h
0x1800478bd  mov     r14, [rsp+78h+arg_38]
0x1800478c5  xor     eax, eax
0x1800478c7  mov     rbx, [rsp+78h+arg_78]
0x1800478cf  xor     ebp, ebp
0x1800478d1  mov     r15d, [rsp+78h+arg_30]
0x1800478d9  mov     r10, rcx
0x1800478dc  mov     rsi, [rsp+78h+lpOutputString]
0x1800478e4  mov     r12, r9
0x1800478e7  mov     r13, r8
0x1800478ea  mov     ecx, r15d
0x1800478ed  mov     [rsi], ax
0x1800478f0  mov     rax, [rsp+78h+arg_60]
0x1800478f8  mov     byte ptr [rax], 0
0x1800478fb  mov     edi, [r14]
0x1800478fe  mov     [rbx+8], edi
0x180047901  mov     eax, [r14+4]
0x180047905  mov     [rbx+0Ch], eax
0x180047908  test    r15d, r15d
0x18004790b  jz      short loc_180047973
0x18004790d  sub     ecx, 1
0x180047910  jz      short loc_18004796A
0x180047912  sub     ecx, 1
0x180047915  jz      short loc_180047925
0x180047917  cmp     ecx, 1
0x18004791a  jnz     short loc_18004797C
0x18004791c  mov     ecx, edi; this
0x18004791e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180047923  jmp     short loc_18004797A
0x180047925  test    edi, edi
0x180047927  js      short loc_180047961
0x180047929  mov     rax, [rsp+78h+arg_28]
0x180047931  mov     edi, 8007029Ch
0x180047936  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18004793a  mov     rcx, r10; int
0x18004793d  mov     [rsp+78h+var_50], rax; __int64
0x180047942  mov     rax, [rsp+78h+arg_20]
0x18004794a  mov     [rsp+78h+var_58], rax; __int64
0x18004794f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180047954  mov     ecx, edi; this
0x180047956  mov     [rbx+8], edi
0x180047959  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004795e  mov     [rbx+0Ch], eax
0x180047961  mov     ecx, edi; this
0x180047963  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180047968  jmp     short loc_18004797A
0x18004796a  mov     ecx, edi; this
0x18004796c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180047971  jmp     short loc_18004797A
0x180047973  mov     ecx, edi; this
0x180047975  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004797a  mov     ebp, eax
0x18004797c  mov     eax, [rsp+78h+arg_70]
0x180047983  mov     [rbx+4], eax
0x180047986  mov     [rbx], r15d
0x180047989  cmp     dword ptr [r14+8], 1
0x18004798e  jnz     short loc_180047996
0x180047990  or      eax, 8
0x180047993  mov     [rbx+4], eax
0x180047996  mov     eax, 1
0x18004799b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800479a3  inc     eax
0x1800479a5  xor     edi, edi
0x1800479a7  mov     [rbx+10h], eax
0x1800479aa  mov     rax, [rsp+78h+arg_40]
0x1800479b2  test    rax, rax
0x1800479b5  jz      short loc_1800479BC
0x1800479b7  cmp     [rax], di
0x1800479ba  jnz     short loc_1800479BF
0x1800479bc  mov     rax, rdi
0x1800479bf  mov     [rbx+18h], rax
0x1800479c3  call    cs:__imp_GetCurrentThreadId
0x1800479c9  mov     [rbx+38h], r13
0x1800479cd  xorps   xmm0, xmm0
0x1800479d0  mov     [rbx+20h], eax
0x1800479d3  mov     eax, [rsp+78h+arg_8]
0x1800479da  mov     [rbx+40h], eax
0x1800479dd  mov     rax, [rsp+78h+arg_20]
0x1800479e5  mov     [rbx+28h], rax
0x1800479e9  mov     rax, [rsp+78h+arg_28]
0x1800479f1  mov     [rbx+88h], rax
0x1800479f8  mov     rax, [rsp+78h+arg_0]
0x180047a00  mov     [rbx+90h], rax
0x180047a07  xor     eax, eax
0x180047a09  mov     [rbx+44h], ebp
0x180047a0c  mov     [rbx+30h], r12
0x180047a10  mov     [rbx+48h], rdi
0x180047a14  movups  xmmword ptr [rbx+68h], xmm0
0x180047a18  mov     [rbx+78h], rax
0x180047a1c  movups  xmmword ptr [rbx+50h], xmm0
0x180047a20  mov     [rbx+60h], rax
0x180047a24  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180047a2b  test    rax, rax
0x180047a2e  jz      short loc_180047A37
0x180047a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a35  jmp     short loc_180047A3A
0x180047a37  mov     rax, rdi
0x180047a3a  mov     [rbx+80h], rax
0x180047a41  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180047a48  test    rax, rax
0x180047a4b  jz      short loc_180047A55
0x180047a4d  mov     rcx, rbx
0x180047a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a55  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180047a5c  test    rax, rax
0x180047a5f  jz      short loc_180047A77
0x180047a61  mov     rdx, [rsp+78h+arg_60]
0x180047a69  mov     r8d, 400h
0x180047a6f  mov     rcx, rbx
0x180047a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a77  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047a7e  test    rax, rax
0x180047a81  jz      short loc_180047A8B
0x180047a83  mov     rcx, rbx
0x180047a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a8b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047a92  test    rax, rax
0x180047a95  jz      short loc_180047AA5
0x180047a97  test    byte ptr [rbx+4], 2
0x180047a9b  jnz     short loc_180047AA5
0x180047a9d  mov     rcx, rbx
0x180047aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047aa5  cmp     [rbx+8], edi
0x180047aa8  jl      short loc_180047AC4
0x180047aaa  cmp     r15d, 3
0x180047aae  jnz     loc_180047B92
0x180047ab4  mov     ecx, 8000FFFFh; this
0x180047ab9  mov     [rbx+8], ecx
0x180047abc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180047ac1  mov     [rbx+0Ch], eax
0x180047ac4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180047acb  jnz     short loc_180047AEC
0x180047acd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180047ad4  test    rax, rax
0x180047ad7  jz      short loc_180047AE2
0x180047ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ade  test    al, al
0x180047ae0  jmp     short loc_180047AEA
0x180047ae2  call    cs:__imp_IsDebuggerPresent
0x180047ae8  test    eax, eax
0x180047aea  jz      short loc_180047AF2
0x180047aec  test    byte ptr [rbx+4], 2
0x180047af0  jz      short loc_180047B16
0x180047af2  mov     rax, cs:g_pfnResultLoggingCallback
0x180047af9  test    rax, rax
0x180047afc  jz      short loc_180047B5A
0x180047afe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180047b05  jnz     short loc_180047B5A
0x180047b07  xor     r8d, r8d
0x180047b0a  xor     edx, edx
0x180047b0c  mov     rcx, rbx
0x180047b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b14  jmp     short loc_180047B5A
0x180047b16  mov     rax, cs:g_pfnResultLoggingCallback
0x180047b1d  mov     ebp, 800h
0x180047b22  test    rax, rax
0x180047b25  jz      short loc_180047B3E
0x180047b27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180047b2e  jnz     short loc_180047B3E
0x180047b30  mov     r8d, ebp
0x180047b33  mov     rdx, rsi
0x180047b36  mov     rcx, rbx
0x180047b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b3e  cmp     [rsi], di
0x180047b41  jnz     short loc_180047B51
0x180047b43  mov     r8, rbx; unsigned __int64
0x180047b46  mov     rdx, rbp; unsigned __int16 *
0x180047b49  mov     rcx, rsi; this
0x180047b4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180047b51  mov     rcx, rsi; lpOutputString
0x180047b54  call    cs:__imp_OutputDebugStringW
0x180047b5a  test    byte ptr [rbx+4], 4
0x180047b5e  jnz     short loc_180047B69
0x180047b60  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180047b67  jz      short loc_180047B7A
0x180047b69  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180047b70  test    rax, rax
0x180047b73  jz      short loc_180047B7A
0x180047b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b7a  mov     rbx, [rsp+78h+arg_10]
0x180047b82  add     rsp, 40h
0x180047b86  pop     r15
0x180047b88  pop     r14
0x180047b8a  pop     r13
0x180047b8c  pop     r12
0x180047b8e  pop     rdi
0x180047b8f  pop     rsi
0x180047b90  pop     rbp
0x180047b91  retn
0x180047b92  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
