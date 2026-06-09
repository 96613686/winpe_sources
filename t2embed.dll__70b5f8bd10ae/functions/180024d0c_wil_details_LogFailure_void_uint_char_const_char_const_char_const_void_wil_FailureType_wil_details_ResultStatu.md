# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180024d0c`
- end: `0x180025000`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18002379c`
- `0x180023850`
- `0x180023944`

## callees

- `0x1800236ec`
- `0x1800243c4`
- `0x180024b3c`
- `0x180024d0c`
- `0x1800255c0`
- `0x1800255e0`
- `0x1800255f4`
- `0x180025610`
- `0x180026fc4`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180024e2f`
- `KERNEL32!GetCurrentThreadId` at `0x180024e2f`
- `KERNEL32!OutputDebugStringW` at `0x180024fc2`
- `KERNEL32!OutputDebugStringW` at `0x180024fc2`
- `KERNEL32!IsDebuggerPresent` at `0x180024f50`
- `KERNEL32!IsDebuggerPresent` at `0x180024f50`

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
0x180024d0c  mov     [rsp+arg_10], rbx
0x180024d11  mov     [rsp+arg_8], edx
0x180024d15  mov     [rsp+arg_0], rcx
0x180024d1a  push    rbp
0x180024d1b  push    rsi
0x180024d1c  push    rdi
0x180024d1d  push    r12
0x180024d1f  push    r13
0x180024d21  push    r14
0x180024d23  push    r15
0x180024d25  sub     rsp, 40h
0x180024d29  mov     r14, [rsp+78h+arg_38]
0x180024d31  xor     eax, eax
0x180024d33  mov     rbx, [rsp+78h+arg_78]
0x180024d3b  xor     ebp, ebp
0x180024d3d  mov     r15d, [rsp+78h+arg_30]
0x180024d45  mov     r10, rcx
0x180024d48  mov     rsi, [rsp+78h+lpOutputString]
0x180024d50  mov     r12, r9
0x180024d53  mov     r13, r8
0x180024d56  mov     ecx, r15d
0x180024d59  mov     [rsi], ax
0x180024d5c  mov     rax, [rsp+78h+arg_60]
0x180024d64  mov     byte ptr [rax], 0
0x180024d67  mov     edi, [r14]
0x180024d6a  mov     [rbx+8], edi
0x180024d6d  mov     eax, [r14+4]
0x180024d71  mov     [rbx+0Ch], eax
0x180024d74  test    r15d, r15d
0x180024d77  jz      short loc_180024DDF
0x180024d79  sub     ecx, 1
0x180024d7c  jz      short loc_180024DD6
0x180024d7e  sub     ecx, 1
0x180024d81  jz      short loc_180024D91
0x180024d83  cmp     ecx, 1
0x180024d86  jnz     short loc_180024DE8
0x180024d88  mov     ecx, edi; this
0x180024d8a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180024d8f  jmp     short loc_180024DE6
0x180024d91  test    edi, edi
0x180024d93  js      short loc_180024DCD
0x180024d95  mov     rax, [rsp+78h+arg_28]
0x180024d9d  mov     edi, 8007029Ch
0x180024da2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180024da6  mov     rcx, r10; int
0x180024da9  mov     [rsp+78h+var_50], rax; __int64
0x180024dae  mov     rax, [rsp+78h+arg_20]
0x180024db6  mov     [rsp+78h+var_58], rax; __int64
0x180024dbb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180024dc0  mov     ecx, edi; this
0x180024dc2  mov     [rbx+8], edi
0x180024dc5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180024dca  mov     [rbx+0Ch], eax
0x180024dcd  mov     ecx, edi; this
0x180024dcf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180024dd4  jmp     short loc_180024DE6
0x180024dd6  mov     ecx, edi; this
0x180024dd8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180024ddd  jmp     short loc_180024DE6
0x180024ddf  mov     ecx, edi; this
0x180024de1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180024de6  mov     ebp, eax
0x180024de8  mov     eax, [rsp+78h+arg_70]
0x180024def  mov     [rbx+4], eax
0x180024df2  mov     [rbx], r15d
0x180024df5  cmp     dword ptr [r14+8], 1
0x180024dfa  jnz     short loc_180024E02
0x180024dfc  or      eax, 8
0x180024dff  mov     [rbx+4], eax
0x180024e02  mov     eax, 1
0x180024e07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180024e0f  inc     eax
0x180024e11  xor     edi, edi
0x180024e13  mov     [rbx+10h], eax
0x180024e16  mov     rax, [rsp+78h+arg_40]
0x180024e1e  test    rax, rax
0x180024e21  jz      short loc_180024E28
0x180024e23  cmp     [rax], di
0x180024e26  jnz     short loc_180024E2B
0x180024e28  mov     rax, rdi
0x180024e2b  mov     [rbx+18h], rax
0x180024e2f  call    cs:__imp_GetCurrentThreadId
0x180024e35  mov     [rbx+38h], r13
0x180024e39  xorps   xmm0, xmm0
0x180024e3c  mov     [rbx+20h], eax
0x180024e3f  mov     eax, [rsp+78h+arg_8]
0x180024e46  mov     [rbx+40h], eax
0x180024e49  mov     rax, [rsp+78h+arg_20]
0x180024e51  mov     [rbx+28h], rax
0x180024e55  mov     rax, [rsp+78h+arg_28]
0x180024e5d  mov     [rbx+88h], rax
0x180024e64  mov     rax, [rsp+78h+arg_0]
0x180024e6c  mov     [rbx+90h], rax
0x180024e73  xor     eax, eax
0x180024e75  mov     [rbx+44h], ebp
0x180024e78  mov     [rbx+30h], r12
0x180024e7c  mov     [rbx+48h], rdi
0x180024e80  movups  xmmword ptr [rbx+68h], xmm0
0x180024e84  mov     [rbx+78h], rax
0x180024e88  movups  xmmword ptr [rbx+50h], xmm0
0x180024e8c  mov     [rbx+60h], rax
0x180024e90  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180024e97  test    rax, rax
0x180024e9a  jz      short loc_180024EA3
0x180024e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ea1  jmp     short loc_180024EA6
0x180024ea3  mov     rax, rdi
0x180024ea6  mov     [rbx+80h], rax
0x180024ead  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180024eb4  test    rax, rax
0x180024eb7  jz      short loc_180024EC1
0x180024eb9  mov     rcx, rbx
0x180024ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ec1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180024ec8  test    rax, rax
0x180024ecb  jz      short loc_180024EE3
0x180024ecd  mov     rdx, [rsp+78h+arg_60]
0x180024ed5  mov     r8d, 400h
0x180024edb  mov     rcx, rbx
0x180024ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ee3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024eea  test    rax, rax
0x180024eed  jz      short loc_180024EF7
0x180024eef  mov     rcx, rbx
0x180024ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ef7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024efe  test    rax, rax
0x180024f01  jz      short loc_180024F11
0x180024f03  test    byte ptr [rbx+4], 2
0x180024f07  jnz     short loc_180024F11
0x180024f09  mov     rcx, rbx
0x180024f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f11  cmp     [rbx+8], edi
0x180024f14  jl      short loc_180024F32
0x180024f16  cmp     r15d, 3
0x180024f1a  jz      short loc_180024F22
0x180024f1c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180024f22  mov     ecx, 8000FFFFh; this
0x180024f27  mov     [rbx+8], ecx
0x180024f2a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180024f2f  mov     [rbx+0Ch], eax
0x180024f32  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180024f39  jnz     short loc_180024F5A
0x180024f3b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180024f42  test    rax, rax
0x180024f45  jz      short loc_180024F50
0x180024f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f4c  test    al, al
0x180024f4e  jmp     short loc_180024F58
0x180024f50  call    cs:__imp_IsDebuggerPresent
0x180024f56  test    eax, eax
0x180024f58  jz      short loc_180024F60
0x180024f5a  test    byte ptr [rbx+4], 2
0x180024f5e  jz      short loc_180024F84
0x180024f60  mov     rax, cs:g_pfnResultLoggingCallback
0x180024f67  test    rax, rax
0x180024f6a  jz      short loc_180024FC8
0x180024f6c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180024f73  jnz     short loc_180024FC8
0x180024f75  xor     r8d, r8d
0x180024f78  xor     edx, edx
0x180024f7a  mov     rcx, rbx
0x180024f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f82  jmp     short loc_180024FC8
0x180024f84  mov     rax, cs:g_pfnResultLoggingCallback
0x180024f8b  mov     ebp, 800h
0x180024f90  test    rax, rax
0x180024f93  jz      short loc_180024FAC
0x180024f95  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180024f9c  jnz     short loc_180024FAC
0x180024f9e  mov     r8d, ebp
0x180024fa1  mov     rdx, rsi
0x180024fa4  mov     rcx, rbx
0x180024fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fac  cmp     [rsi], di
0x180024faf  jnz     short loc_180024FBF
0x180024fb1  mov     r8, rbx; unsigned __int64
0x180024fb4  mov     rdx, rbp; unsigned __int16 *
0x180024fb7  mov     rcx, rsi; this
0x180024fba  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180024fbf  mov     rcx, rsi; lpOutputString
0x180024fc2  call    cs:__imp_OutputDebugStringW
0x180024fc8  test    byte ptr [rbx+4], 4
0x180024fcc  jnz     short loc_180024FD7
0x180024fce  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180024fd5  jz      short loc_180024FE8
0x180024fd7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180024fde  test    rax, rax
0x180024fe1  jz      short loc_180024FE8
0x180024fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fe8  mov     rbx, [rsp+78h+arg_10]
0x180024ff0  add     rsp, 40h
0x180024ff4  pop     r15
0x180024ff6  pop     r14
0x180024ff8  pop     r13
0x180024ffa  pop     r12
0x180024ffc  pop     rdi
0x180024ffd  pop     rsi
0x180024ffe  pop     rbp
0x180024fff  retn
```
