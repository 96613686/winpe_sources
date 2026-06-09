# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140012c74`
- end: `0x140012f6d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140009600`

## callees

- `0x14000900c`
- `0x140011cc8`
- `0x140012910`
- `0x140012c74`
- `0x140014f34`
- `0x140014f50`
- `0x14001507c`
- `0x140015098`
- `0x14001b500`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140012eb6`
- `KERNEL32!IsDebuggerPresent` at `0x140012eb6`
- `KERNEL32!OutputDebugStringW` at `0x140012f28`
- `KERNEL32!OutputDebugStringW` at `0x140012f28`
- `KERNEL32!GetCurrentThreadId` at `0x140012d97`
- `KERNEL32!GetCurrentThreadId` at `0x140012d97`

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
0x140012c74  mov     [rsp+arg_10], rbx
0x140012c79  mov     [rsp+arg_8], edx
0x140012c7d  mov     [rsp+arg_0], rcx
0x140012c82  push    rbp
0x140012c83  push    rsi
0x140012c84  push    rdi
0x140012c85  push    r12
0x140012c87  push    r13
0x140012c89  push    r14
0x140012c8b  push    r15
0x140012c8d  sub     rsp, 40h
0x140012c91  mov     r12, r9
0x140012c94  mov     r13, r8
0x140012c97  mov     r10, rcx
0x140012c9a  xor     eax, eax
0x140012c9c  mov     rsi, [rsp+78h+lpOutputString]
0x140012ca4  mov     [rsi], ax
0x140012ca7  mov     rax, [rsp+78h+arg_60]
0x140012caf  mov     byte ptr [rax], 0
0x140012cb2  mov     r14, [rsp+78h+arg_38]
0x140012cba  mov     edi, [r14]
0x140012cbd  mov     rbx, [rsp+78h+arg_78]
0x140012cc5  mov     [rbx+8], edi
0x140012cc8  mov     eax, [r14+4]
0x140012ccc  mov     [rbx+0Ch], eax
0x140012ccf  xor     ebp, ebp
0x140012cd1  mov     r15d, [rsp+78h+arg_30]
0x140012cd9  mov     ecx, r15d
0x140012cdc  test    r15d, r15d
0x140012cdf  jz      short loc_140012D47
0x140012ce1  sub     ecx, 1
0x140012ce4  jz      short loc_140012D3E
0x140012ce6  sub     ecx, 1
0x140012ce9  jz      short loc_140012CF9
0x140012ceb  cmp     ecx, 1
0x140012cee  jnz     short loc_140012D50
0x140012cf0  mov     ecx, edi; this
0x140012cf2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140012cf7  jmp     short loc_140012D4E
0x140012cf9  test    edi, edi
0x140012cfb  js      short loc_140012D35
0x140012cfd  mov     edi, 8007029Ch
0x140012d02  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140012d06  mov     rax, [rsp+78h+arg_28]
0x140012d0e  mov     [rsp+78h+var_50], rax; __int64
0x140012d13  mov     rax, [rsp+78h+arg_20]
0x140012d1b  mov     [rsp+78h+var_58], rax; __int64
0x140012d20  mov     rcx, r10; int
0x140012d23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140012d28  mov     [rbx+8], edi
0x140012d2b  mov     ecx, edi; this
0x140012d2d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140012d32  mov     [rbx+0Ch], eax
0x140012d35  mov     ecx, edi; this
0x140012d37  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140012d3c  jmp     short loc_140012D4E
0x140012d3e  mov     ecx, edi; this
0x140012d40  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140012d45  jmp     short loc_140012D4E
0x140012d47  mov     ecx, edi; this
0x140012d49  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140012d4e  mov     ebp, eax
0x140012d50  mov     [rbx], r15d
0x140012d53  mov     eax, [rsp+78h+arg_70]
0x140012d5a  mov     [rbx+4], eax
0x140012d5d  cmp     dword ptr [r14+8], 1
0x140012d62  jnz     short loc_140012D6A
0x140012d64  or      eax, 8
0x140012d67  mov     [rbx+4], eax
0x140012d6a  mov     eax, 1
0x140012d6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140012d77  inc     eax
0x140012d79  mov     [rbx+10h], eax
0x140012d7c  mov     rax, [rsp+78h+arg_40]
0x140012d84  xor     edi, edi
0x140012d86  test    rax, rax
0x140012d89  jz      short loc_140012D90
0x140012d8b  cmp     [rax], di
0x140012d8e  jnz     short loc_140012D93
0x140012d90  mov     rax, rdi
0x140012d93  mov     [rbx+18h], rax
0x140012d97  call    cs:__imp_GetCurrentThreadId
0x140012d9d  mov     [rbx+20h], eax
0x140012da0  mov     [rbx+38h], r13
0x140012da4  mov     eax, [rsp+78h+arg_8]
0x140012dab  mov     [rbx+40h], eax
0x140012dae  mov     [rbx+44h], ebp
0x140012db1  mov     rax, [rsp+78h+arg_20]
0x140012db9  mov     [rbx+28h], rax
0x140012dbd  mov     [rbx+30h], r12
0x140012dc1  mov     rax, [rsp+78h+arg_28]
0x140012dc9  mov     [rbx+88h], rax
0x140012dd0  mov     rax, [rsp+78h+arg_0]
0x140012dd8  mov     [rbx+90h], rax
0x140012ddf  mov     [rbx+48h], rdi
0x140012de3  xorps   xmm0, xmm0
0x140012de6  xor     eax, eax
0x140012de8  movups  xmmword ptr [rbx+68h], xmm0
0x140012dec  mov     [rbx+78h], rax
0x140012df0  movups  xmmword ptr [rbx+50h], xmm0
0x140012df4  mov     [rbx+60h], rax
0x140012df8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140012dff  test    rax, rax
0x140012e02  jz      short loc_140012E0B
0x140012e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e09  jmp     short loc_140012E0E
0x140012e0b  mov     rax, rdi
0x140012e0e  mov     [rbx+80h], rax
0x140012e15  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140012e1c  test    rax, rax
0x140012e1f  jz      short loc_140012E29
0x140012e21  mov     rcx, rbx
0x140012e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e29  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140012e30  test    rax, rax
0x140012e33  jz      short loc_140012E4B
0x140012e35  mov     r8d, 400h
0x140012e3b  mov     rdx, [rsp+78h+arg_60]
0x140012e43  mov     rcx, rbx
0x140012e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e4b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140012e52  test    rax, rax
0x140012e55  jz      short loc_140012E5F
0x140012e57  mov     rcx, rbx
0x140012e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e5f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140012e66  test    rax, rax
0x140012e69  jz      short loc_140012E79
0x140012e6b  test    byte ptr [rbx+4], 2
0x140012e6f  jnz     short loc_140012E79
0x140012e71  mov     rcx, rbx
0x140012e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e79  cmp     [rbx+8], edi
0x140012e7c  jl      short loc_140012E98
0x140012e7e  cmp     r15d, 3
0x140012e82  jnz     loc_140012F67
0x140012e88  mov     ecx, 8000FFFFh; this
0x140012e8d  mov     [rbx+8], ecx
0x140012e90  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140012e95  mov     [rbx+0Ch], eax
0x140012e98  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140012e9f  jnz     short loc_140012EC0
0x140012ea1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140012ea8  test    rax, rax
0x140012eab  jz      short loc_140012EB6
0x140012ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012eb2  test    al, al
0x140012eb4  jmp     short loc_140012EBE
0x140012eb6  call    cs:__imp_IsDebuggerPresent
0x140012ebc  test    eax, eax
0x140012ebe  jz      short loc_140012EC6
0x140012ec0  test    byte ptr [rbx+4], 2
0x140012ec4  jz      short loc_140012EEA
0x140012ec6  mov     rax, cs:g_pfnResultLoggingCallback
0x140012ecd  test    rax, rax
0x140012ed0  jz      short loc_140012F2E
0x140012ed2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140012ed9  jnz     short loc_140012F2E
0x140012edb  xor     r8d, r8d
0x140012ede  xor     edx, edx
0x140012ee0  mov     rcx, rbx
0x140012ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ee8  jmp     short loc_140012F2E
0x140012eea  mov     ebp, 800h
0x140012eef  mov     rax, cs:g_pfnResultLoggingCallback
0x140012ef6  test    rax, rax
0x140012ef9  jz      short loc_140012F12
0x140012efb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140012f02  jnz     short loc_140012F12
0x140012f04  mov     r8d, ebp
0x140012f07  mov     rdx, rsi
0x140012f0a  mov     rcx, rbx
0x140012f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f12  cmp     [rsi], di
0x140012f15  jnz     short loc_140012F25
0x140012f17  mov     r8, rbx; unsigned __int64
0x140012f1a  mov     rdx, rbp; unsigned __int16 *
0x140012f1d  mov     rcx, rsi; this
0x140012f20  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140012f25  mov     rcx, rsi; lpOutputString
0x140012f28  call    cs:__imp_OutputDebugStringW
0x140012f2e  test    byte ptr [rbx+4], 4
0x140012f32  jnz     short loc_140012F3D
0x140012f34  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140012f3b  jz      short loc_140012F4F
0x140012f3d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140012f44  test    rax, rax
0x140012f47  jz      short loc_140012F4F
0x140012f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f4e  nop
0x140012f4f  mov     rbx, [rsp+78h+arg_10]
0x140012f57  add     rsp, 40h
0x140012f5b  pop     r15
0x140012f5d  pop     r14
0x140012f5f  pop     r13
0x140012f61  pop     r12
0x140012f63  pop     rdi
0x140012f64  pop     rsi
0x140012f65  pop     rbp
0x140012f66  retn
0x140012f67  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
