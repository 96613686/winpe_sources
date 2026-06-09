# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180031d64`
- end: `0x18003205c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002ffa0`

## callees

- `0x18002f9dc`
- `0x1800311f4`
- `0x180031a60`
- `0x180031d64`
- `0x1800328b0`
- `0x1800328d0`
- `0x180032a54`
- `0x180032a70`
- `0x180033ffc`
- `0x180037010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180031fa6`
- `KERNEL32!IsDebuggerPresent` at `0x180031fa6`
- `KERNEL32!OutputDebugStringW` at `0x180032018`
- `KERNEL32!OutputDebugStringW` at `0x180032018`
- `KERNEL32!GetCurrentThreadId` at `0x180031e87`
- `KERNEL32!GetCurrentThreadId` at `0x180031e87`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x180031d64  mov     [rsp+arg_10], rbx
0x180031d69  mov     [rsp+arg_8], edx
0x180031d6d  mov     [rsp+arg_0], rcx
0x180031d72  push    rbp
0x180031d73  push    rsi
0x180031d74  push    rdi
0x180031d75  push    r12
0x180031d77  push    r13
0x180031d79  push    r14
0x180031d7b  push    r15
0x180031d7d  sub     rsp, 40h
0x180031d81  mov     r14, [rsp+78h+arg_38]
0x180031d89  xor     eax, eax
0x180031d8b  mov     rbx, [rsp+78h+arg_78]
0x180031d93  xor     ebp, ebp
0x180031d95  mov     r15d, [rsp+78h+arg_30]
0x180031d9d  mov     r10, rcx
0x180031da0  mov     rsi, [rsp+78h+lpOutputString]
0x180031da8  mov     r12, r9
0x180031dab  mov     r13, r8
0x180031dae  mov     ecx, r15d
0x180031db1  mov     [rsi], ax
0x180031db4  mov     rax, [rsp+78h+arg_60]
0x180031dbc  mov     byte ptr [rax], 0
0x180031dbf  mov     edi, [r14]
0x180031dc2  mov     [rbx+8], edi
0x180031dc5  mov     eax, [r14+4]
0x180031dc9  mov     [rbx+0Ch], eax
0x180031dcc  test    r15d, r15d
0x180031dcf  jz      short loc_180031E37
0x180031dd1  sub     ecx, 1
0x180031dd4  jz      short loc_180031E2E
0x180031dd6  sub     ecx, 1
0x180031dd9  jz      short loc_180031DE9
0x180031ddb  cmp     ecx, 1
0x180031dde  jnz     short loc_180031E40
0x180031de0  mov     ecx, edi; this
0x180031de2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180031de7  jmp     short loc_180031E3E
0x180031de9  test    edi, edi
0x180031deb  js      short loc_180031E25
0x180031ded  mov     rax, [rsp+78h+arg_28]
0x180031df5  mov     edi, 8007029Ch
0x180031dfa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180031dfe  mov     rcx, r10; int
0x180031e01  mov     [rsp+78h+var_50], rax; __int64
0x180031e06  mov     rax, [rsp+78h+arg_20]
0x180031e0e  mov     [rsp+78h+var_58], rax; __int64
0x180031e13  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180031e18  mov     ecx, edi; this
0x180031e1a  mov     [rbx+8], edi
0x180031e1d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180031e22  mov     [rbx+0Ch], eax
0x180031e25  mov     ecx, edi; this
0x180031e27  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180031e2c  jmp     short loc_180031E3E
0x180031e2e  mov     ecx, edi; this
0x180031e30  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180031e35  jmp     short loc_180031E3E
0x180031e37  mov     ecx, edi; this
0x180031e39  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180031e3e  mov     ebp, eax
0x180031e40  mov     eax, [rsp+78h+arg_70]
0x180031e47  mov     [rbx+4], eax
0x180031e4a  mov     [rbx], r15d
0x180031e4d  cmp     dword ptr [r14+8], 1
0x180031e52  jnz     short loc_180031E5A
0x180031e54  or      eax, 8
0x180031e57  mov     [rbx+4], eax
0x180031e5a  mov     eax, 1
0x180031e5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180031e67  inc     eax
0x180031e69  xor     edi, edi
0x180031e6b  mov     [rbx+10h], eax
0x180031e6e  mov     rax, [rsp+78h+arg_40]
0x180031e76  test    rax, rax
0x180031e79  jz      short loc_180031E80
0x180031e7b  cmp     [rax], di
0x180031e7e  jnz     short loc_180031E83
0x180031e80  mov     rax, rdi
0x180031e83  mov     [rbx+18h], rax
0x180031e87  call    cs:__imp_GetCurrentThreadId
0x180031e8d  mov     [rbx+38h], r13
0x180031e91  xorps   xmm0, xmm0
0x180031e94  mov     [rbx+20h], eax
0x180031e97  mov     eax, [rsp+78h+arg_8]
0x180031e9e  mov     [rbx+40h], eax
0x180031ea1  mov     rax, [rsp+78h+arg_20]
0x180031ea9  mov     [rbx+28h], rax
0x180031ead  mov     rax, [rsp+78h+arg_28]
0x180031eb5  mov     [rbx+88h], rax
0x180031ebc  mov     rax, [rsp+78h+arg_0]
0x180031ec4  mov     [rbx+90h], rax
0x180031ecb  xor     eax, eax
0x180031ecd  mov     [rbx+44h], ebp
0x180031ed0  mov     [rbx+30h], r12
0x180031ed4  mov     [rbx+48h], rdi
0x180031ed8  movups  xmmword ptr [rbx+68h], xmm0
0x180031edc  mov     [rbx+78h], rax
0x180031ee0  movups  xmmword ptr [rbx+50h], xmm0
0x180031ee4  mov     [rbx+60h], rax
0x180031ee8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180031eef  test    rax, rax
0x180031ef2  jz      short loc_180031EFB
0x180031ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ef9  jmp     short loc_180031EFE
0x180031efb  mov     rax, rdi
0x180031efe  mov     [rbx+80h], rax
0x180031f05  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180031f0c  test    rax, rax
0x180031f0f  jz      short loc_180031F19
0x180031f11  mov     rcx, rbx
0x180031f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f19  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180031f20  test    rax, rax
0x180031f23  jz      short loc_180031F3B
0x180031f25  mov     rdx, [rsp+78h+arg_60]
0x180031f2d  mov     r8d, 400h
0x180031f33  mov     rcx, rbx
0x180031f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f3b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180031f42  test    rax, rax
0x180031f45  jz      short loc_180031F4F
0x180031f47  mov     rcx, rbx
0x180031f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f4f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180031f56  test    rax, rax
0x180031f59  jz      short loc_180031F69
0x180031f5b  test    byte ptr [rbx+4], 2
0x180031f5f  jnz     short loc_180031F69
0x180031f61  mov     rcx, rbx
0x180031f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f69  cmp     [rbx+8], edi
0x180031f6c  jl      short loc_180031F88
0x180031f6e  cmp     r15d, 3
0x180031f72  jnz     loc_180032056
0x180031f78  mov     ecx, 8000FFFFh; this
0x180031f7d  mov     [rbx+8], ecx
0x180031f80  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180031f85  mov     [rbx+0Ch], eax
0x180031f88  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180031f8f  jnz     short loc_180031FB0
0x180031f91  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180031f98  test    rax, rax
0x180031f9b  jz      short loc_180031FA6
0x180031f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fa2  test    al, al
0x180031fa4  jmp     short loc_180031FAE
0x180031fa6  call    cs:__imp_IsDebuggerPresent
0x180031fac  test    eax, eax
0x180031fae  jz      short loc_180031FB6
0x180031fb0  test    byte ptr [rbx+4], 2
0x180031fb4  jz      short loc_180031FDA
0x180031fb6  mov     rax, cs:g_pfnResultLoggingCallback
0x180031fbd  test    rax, rax
0x180031fc0  jz      short loc_18003201E
0x180031fc2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180031fc9  jnz     short loc_18003201E
0x180031fcb  xor     r8d, r8d
0x180031fce  xor     edx, edx
0x180031fd0  mov     rcx, rbx
0x180031fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fd8  jmp     short loc_18003201E
0x180031fda  mov     rax, cs:g_pfnResultLoggingCallback
0x180031fe1  mov     ebp, 800h
0x180031fe6  test    rax, rax
0x180031fe9  jz      short loc_180032002
0x180031feb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180031ff2  jnz     short loc_180032002
0x180031ff4  mov     r8d, ebp
0x180031ff7  mov     rdx, rsi
0x180031ffa  mov     rcx, rbx
0x180031ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032002  cmp     [rsi], di
0x180032005  jnz     short loc_180032015
0x180032007  mov     r8, rbx; unsigned __int64
0x18003200a  mov     rdx, rbp; unsigned __int16 *
0x18003200d  mov     rcx, rsi; this
0x180032010  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180032015  mov     rcx, rsi; lpOutputString
0x180032018  call    cs:__imp_OutputDebugStringW
0x18003201e  test    byte ptr [rbx+4], 4
0x180032022  jnz     short loc_18003202D
0x180032024  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003202b  jz      short loc_18003203E
0x18003202d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180032034  test    rax, rax
0x180032037  jz      short loc_18003203E
0x180032039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003203e  mov     rbx, [rsp+78h+arg_10]
0x180032046  add     rsp, 40h
0x18003204a  pop     r15
0x18003204c  pop     r14
0x18003204e  pop     r13
0x180032050  pop     r12
0x180032052  pop     rdi
0x180032053  pop     rsi
0x180032054  pop     rbp
0x180032055  retn
0x180032056  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
