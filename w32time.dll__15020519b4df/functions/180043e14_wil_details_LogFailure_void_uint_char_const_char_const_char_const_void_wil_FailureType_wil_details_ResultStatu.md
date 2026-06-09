# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180043e14`
- end: `0x18004411c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18003f9f4`
- `0x18003fab4`
- `0x18003fbb4`
- `0x180051654`

## callees

- `0x18003c464`
- `0x18003f940`
- `0x180042be4`
- `0x180043e14`
- `0x180044e34`
- `0x180044e60`
- `0x180044f20`
- `0x180044f40`
- `0x1800488c4`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043f37`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800440d6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800440d6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004405e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004405e`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180043e14  mov     [rsp+arg_10], rbx
0x180043e19  mov     [rsp+arg_8], edx
0x180043e1d  mov     [rsp+arg_0], rcx
0x180043e22  push    rbp
0x180043e23  push    rsi
0x180043e24  push    rdi
0x180043e25  push    r12
0x180043e27  push    r13
0x180043e29  push    r14
0x180043e2b  push    r15
0x180043e2d  sub     rsp, 40h
0x180043e31  mov     r12, r9
0x180043e34  mov     r13, r8
0x180043e37  mov     r10, rcx
0x180043e3a  xor     eax, eax
0x180043e3c  mov     rsi, [rsp+78h+lpOutputString]
0x180043e44  mov     [rsi], ax
0x180043e47  mov     rax, [rsp+78h+arg_60]
0x180043e4f  mov     byte ptr [rax], 0
0x180043e52  mov     r14, [rsp+78h+arg_38]
0x180043e5a  mov     edi, [r14]
0x180043e5d  mov     rbx, [rsp+78h+arg_78]
0x180043e65  mov     [rbx+8], edi
0x180043e68  mov     eax, [r14+4]
0x180043e6c  mov     [rbx+0Ch], eax
0x180043e6f  xor     ebp, ebp
0x180043e71  mov     r15d, [rsp+78h+arg_30]
0x180043e79  mov     ecx, r15d
0x180043e7c  test    r15d, r15d
0x180043e7f  jz      short loc_180043EE7
0x180043e81  sub     ecx, 1
0x180043e84  jz      short loc_180043EDE
0x180043e86  sub     ecx, 1
0x180043e89  jz      short loc_180043E99
0x180043e8b  cmp     ecx, 1
0x180043e8e  jnz     short loc_180043EF0
0x180043e90  mov     ecx, edi; this
0x180043e92  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180043e97  jmp     short loc_180043EEE
0x180043e99  test    edi, edi
0x180043e9b  js      short loc_180043ED5
0x180043e9d  mov     edi, 8007029Ch
0x180043ea2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180043ea6  mov     rax, [rsp+78h+arg_28]
0x180043eae  mov     [rsp+78h+var_50], rax; __int64
0x180043eb3  mov     rax, [rsp+78h+arg_20]
0x180043ebb  mov     [rsp+78h+var_58], rax; __int64
0x180043ec0  mov     rcx, r10; int
0x180043ec3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180043ec8  mov     [rbx+8], edi
0x180043ecb  mov     ecx, edi; this
0x180043ecd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180043ed2  mov     [rbx+0Ch], eax
0x180043ed5  mov     ecx, edi; this
0x180043ed7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180043edc  jmp     short loc_180043EEE
0x180043ede  mov     ecx, edi; this
0x180043ee0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180043ee5  jmp     short loc_180043EEE
0x180043ee7  mov     ecx, edi; this
0x180043ee9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180043eee  mov     ebp, eax
0x180043ef0  mov     [rbx], r15d
0x180043ef3  mov     eax, [rsp+78h+arg_70]
0x180043efa  mov     [rbx+4], eax
0x180043efd  cmp     dword ptr [r14+8], 1
0x180043f02  jnz     short loc_180043F0A
0x180043f04  or      eax, 8
0x180043f07  mov     [rbx+4], eax
0x180043f0a  mov     eax, 1
0x180043f0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180043f17  inc     eax
0x180043f19  mov     [rbx+10h], eax
0x180043f1c  mov     rax, [rsp+78h+arg_40]
0x180043f24  xor     edi, edi
0x180043f26  test    rax, rax
0x180043f29  jz      short loc_180043F30
0x180043f2b  cmp     [rax], di
0x180043f2e  jnz     short loc_180043F33
0x180043f30  mov     rax, rdi
0x180043f33  mov     [rbx+18h], rax
0x180043f37  call    cs:__imp_GetCurrentThreadId
0x180043f3e  nop     dword ptr [rax+rax+00h]
0x180043f43  mov     [rbx+20h], eax
0x180043f46  mov     [rbx+38h], r13
0x180043f4a  mov     eax, [rsp+78h+arg_8]
0x180043f51  mov     [rbx+40h], eax
0x180043f54  mov     [rbx+44h], ebp
0x180043f57  mov     rax, [rsp+78h+arg_20]
0x180043f5f  mov     [rbx+28h], rax
0x180043f63  mov     [rbx+30h], r12
0x180043f67  mov     rax, [rsp+78h+arg_28]
0x180043f6f  mov     [rbx+88h], rax
0x180043f76  mov     rax, [rsp+78h+arg_0]
0x180043f7e  mov     [rbx+90h], rax
0x180043f85  mov     [rbx+48h], rdi
0x180043f89  xorps   xmm0, xmm0
0x180043f8c  xor     eax, eax
0x180043f8e  movups  xmmword ptr [rbx+68h], xmm0
0x180043f92  mov     [rbx+78h], rax
0x180043f96  movups  xmmword ptr [rbx+50h], xmm0
0x180043f9a  mov     [rbx+60h], rax
0x180043f9e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180043fa5  test    rax, rax
0x180043fa8  jz      short loc_180043FB1
0x180043faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043faf  jmp     short loc_180043FB4
0x180043fb1  mov     rax, rdi
0x180043fb4  mov     [rbx+80h], rax
0x180043fbb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180043fc2  test    rax, rax
0x180043fc5  jz      short loc_180043FCF
0x180043fc7  mov     rcx, rbx
0x180043fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fcf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180043fd6  test    rax, rax
0x180043fd9  jz      short loc_180043FF1
0x180043fdb  mov     r8d, 400h
0x180043fe1  mov     rdx, [rsp+78h+arg_60]
0x180043fe9  mov     rcx, rbx
0x180043fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ff1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043ff8  test    rax, rax
0x180043ffb  jz      short loc_180044005
0x180043ffd  mov     rcx, rbx
0x180044000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044005  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004400c  test    rax, rax
0x18004400f  jz      short loc_18004401F
0x180044011  test    byte ptr [rbx+4], 2
0x180044015  jnz     short loc_18004401F
0x180044017  mov     rcx, rbx
0x18004401a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004401f  cmp     [rbx+8], edi
0x180044022  jl      short loc_180044040
0x180044024  cmp     r15d, 3
0x180044028  jz      short loc_180044030
0x18004402a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180044030  mov     ecx, 8000FFFFh; this
0x180044035  mov     [rbx+8], ecx
0x180044038  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004403d  mov     [rbx+0Ch], eax
0x180044040  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180044047  jnz     short loc_18004406E
0x180044049  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180044050  test    rax, rax
0x180044053  jz      short loc_18004405E
0x180044055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004405a  test    al, al
0x18004405c  jmp     short loc_18004406C
0x18004405e  call    cs:__imp_IsDebuggerPresent
0x180044065  nop     dword ptr [rax+rax+00h]
0x18004406a  test    eax, eax
0x18004406c  jz      short loc_180044074
0x18004406e  test    byte ptr [rbx+4], 2
0x180044072  jz      short loc_180044098
0x180044074  mov     rax, cs:g_pfnResultLoggingCallback
0x18004407b  test    rax, rax
0x18004407e  jz      short loc_1800440E2
0x180044080  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180044087  jnz     short loc_1800440E2
0x180044089  xor     r8d, r8d
0x18004408c  xor     edx, edx
0x18004408e  mov     rcx, rbx
0x180044091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044096  jmp     short loc_1800440E2
0x180044098  mov     ebp, 800h
0x18004409d  mov     rax, cs:g_pfnResultLoggingCallback
0x1800440a4  test    rax, rax
0x1800440a7  jz      short loc_1800440C0
0x1800440a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800440b0  jnz     short loc_1800440C0
0x1800440b2  mov     r8d, ebp
0x1800440b5  mov     rdx, rsi
0x1800440b8  mov     rcx, rbx
0x1800440bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440c0  cmp     [rsi], di
0x1800440c3  jnz     short loc_1800440D3
0x1800440c5  mov     r8, rbx; unsigned __int64
0x1800440c8  mov     rdx, rbp; unsigned __int16 *
0x1800440cb  mov     rcx, rsi; this
0x1800440ce  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800440d3  mov     rcx, rsi; lpOutputString
0x1800440d6  call    cs:__imp_OutputDebugStringW
0x1800440dd  nop     dword ptr [rax+rax+00h]
0x1800440e2  test    byte ptr [rbx+4], 4
0x1800440e6  jnz     short loc_1800440F1
0x1800440e8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800440ef  jz      short loc_180044103
0x1800440f1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800440f8  test    rax, rax
0x1800440fb  jz      short loc_180044103
0x1800440fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044102  nop
0x180044103  mov     rbx, [rsp+78h+arg_10]
0x18004410b  add     rsp, 40h
0x18004410f  pop     r15
0x180044111  pop     r14
0x180044113  pop     r13
0x180044115  pop     r12
0x180044117  pop     rdi
0x180044118  pop     rsi
0x180044119  pop     rbp
0x18004411a  retn
```
