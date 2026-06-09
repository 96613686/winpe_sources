# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000af78`
- end: `0x18000b26d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180009c24`
- `0x180009ce4`
- `0x180009de0`
- `0x1800132dc`

## callees

- `0x1800076ac`
- `0x180009b70`
- `0x18000a8d4`
- `0x18000af78`
- `0x18000b63c`
- `0x18000b660`
- `0x18000b674`
- `0x18000b690`
- `0x18000c45c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b09b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b09b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b1bc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b1bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b22e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b22e`

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
0x18000af78  mov     [rsp+arg_10], rbx
0x18000af7d  mov     [rsp+arg_8], edx
0x18000af81  mov     [rsp+arg_0], rcx
0x18000af86  push    rbp
0x18000af87  push    rsi
0x18000af88  push    rdi
0x18000af89  push    r12
0x18000af8b  push    r13
0x18000af8d  push    r14
0x18000af8f  push    r15
0x18000af91  sub     rsp, 40h
0x18000af95  mov     r12, r9
0x18000af98  mov     r13, r8
0x18000af9b  mov     r10, rcx
0x18000af9e  xor     eax, eax
0x18000afa0  mov     rsi, [rsp+78h+lpOutputString]
0x18000afa8  mov     [rsi], ax
0x18000afab  mov     rax, [rsp+78h+arg_60]
0x18000afb3  mov     byte ptr [rax], 0
0x18000afb6  mov     r14, [rsp+78h+arg_38]
0x18000afbe  mov     edi, [r14]
0x18000afc1  mov     rbx, [rsp+78h+arg_78]
0x18000afc9  mov     [rbx+8], edi
0x18000afcc  mov     eax, [r14+4]
0x18000afd0  mov     [rbx+0Ch], eax
0x18000afd3  xor     ebp, ebp
0x18000afd5  mov     r15d, [rsp+78h+arg_30]
0x18000afdd  mov     ecx, r15d
0x18000afe0  test    r15d, r15d
0x18000afe3  jz      short loc_18000B04B
0x18000afe5  sub     ecx, 1
0x18000afe8  jz      short loc_18000B042
0x18000afea  sub     ecx, 1
0x18000afed  jz      short loc_18000AFFD
0x18000afef  cmp     ecx, 1
0x18000aff2  jnz     short loc_18000B054
0x18000aff4  mov     ecx, edi; this
0x18000aff6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000affb  jmp     short loc_18000B052
0x18000affd  test    edi, edi
0x18000afff  js      short loc_18000B039
0x18000b001  mov     edi, 8007029Ch
0x18000b006  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000b00a  mov     rax, [rsp+78h+arg_28]
0x18000b012  mov     [rsp+78h+var_50], rax; __int64
0x18000b017  mov     rax, [rsp+78h+arg_20]
0x18000b01f  mov     [rsp+78h+var_58], rax; __int64
0x18000b024  mov     rcx, r10; int
0x18000b027  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b02c  mov     [rbx+8], edi
0x18000b02f  mov     ecx, edi; this
0x18000b031  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b036  mov     [rbx+0Ch], eax
0x18000b039  mov     ecx, edi; this
0x18000b03b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000b040  jmp     short loc_18000B052
0x18000b042  mov     ecx, edi; this
0x18000b044  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b049  jmp     short loc_18000B052
0x18000b04b  mov     ecx, edi; this
0x18000b04d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b052  mov     ebp, eax
0x18000b054  mov     [rbx], r15d
0x18000b057  mov     eax, [rsp+78h+arg_70]
0x18000b05e  mov     [rbx+4], eax
0x18000b061  cmp     dword ptr [r14+8], 1
0x18000b066  jnz     short loc_18000B06E
0x18000b068  or      eax, 8
0x18000b06b  mov     [rbx+4], eax
0x18000b06e  mov     eax, 1
0x18000b073  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b07b  inc     eax
0x18000b07d  mov     [rbx+10h], eax
0x18000b080  mov     rax, [rsp+78h+arg_40]
0x18000b088  xor     edi, edi
0x18000b08a  test    rax, rax
0x18000b08d  jz      short loc_18000B094
0x18000b08f  cmp     [rax], di
0x18000b092  jnz     short loc_18000B097
0x18000b094  mov     rax, rdi
0x18000b097  mov     [rbx+18h], rax
0x18000b09b  call    cs:__imp_GetCurrentThreadId
0x18000b0a1  mov     [rbx+20h], eax
0x18000b0a4  mov     [rbx+38h], r13
0x18000b0a8  mov     eax, [rsp+78h+arg_8]
0x18000b0af  mov     [rbx+40h], eax
0x18000b0b2  mov     [rbx+44h], ebp
0x18000b0b5  mov     rax, [rsp+78h+arg_20]
0x18000b0bd  mov     [rbx+28h], rax
0x18000b0c1  mov     [rbx+30h], r12
0x18000b0c5  mov     rax, [rsp+78h+arg_28]
0x18000b0cd  mov     [rbx+88h], rax
0x18000b0d4  mov     rax, [rsp+78h+arg_0]
0x18000b0dc  mov     [rbx+90h], rax
0x18000b0e3  mov     [rbx+48h], rdi
0x18000b0e7  xorps   xmm0, xmm0
0x18000b0ea  xor     eax, eax
0x18000b0ec  movups  xmmword ptr [rbx+68h], xmm0
0x18000b0f0  mov     [rbx+78h], rax
0x18000b0f4  movups  xmmword ptr [rbx+50h], xmm0
0x18000b0f8  mov     [rbx+60h], rax
0x18000b0fc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b103  test    rax, rax
0x18000b106  jz      short loc_18000B10F
0x18000b108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b10d  jmp     short loc_18000B112
0x18000b10f  mov     rax, rdi
0x18000b112  mov     [rbx+80h], rax
0x18000b119  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b120  test    rax, rax
0x18000b123  jz      short loc_18000B12D
0x18000b125  mov     rcx, rbx
0x18000b128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b12d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b134  test    rax, rax
0x18000b137  jz      short loc_18000B14F
0x18000b139  mov     r8d, 400h
0x18000b13f  mov     rdx, [rsp+78h+arg_60]
0x18000b147  mov     rcx, rbx
0x18000b14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b14f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b156  test    rax, rax
0x18000b159  jz      short loc_18000B163
0x18000b15b  mov     rcx, rbx
0x18000b15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b163  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b16a  test    rax, rax
0x18000b16d  jz      short loc_18000B17D
0x18000b16f  test    byte ptr [rbx+4], 2
0x18000b173  jnz     short loc_18000B17D
0x18000b175  mov     rcx, rbx
0x18000b178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b17d  cmp     [rbx+8], edi
0x18000b180  jl      short loc_18000B19E
0x18000b182  cmp     r15d, 3
0x18000b186  jz      short loc_18000B18E
0x18000b188  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b18e  mov     ecx, 8000FFFFh; this
0x18000b193  mov     [rbx+8], ecx
0x18000b196  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b19b  mov     [rbx+0Ch], eax
0x18000b19e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000b1a5  jnz     short loc_18000B1C6
0x18000b1a7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b1ae  test    rax, rax
0x18000b1b1  jz      short loc_18000B1BC
0x18000b1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b8  test    al, al
0x18000b1ba  jmp     short loc_18000B1C4
0x18000b1bc  call    cs:__imp_IsDebuggerPresent
0x18000b1c2  test    eax, eax
0x18000b1c4  jz      short loc_18000B1CC
0x18000b1c6  test    byte ptr [rbx+4], 2
0x18000b1ca  jz      short loc_18000B1F0
0x18000b1cc  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b1d3  test    rax, rax
0x18000b1d6  jz      short loc_18000B234
0x18000b1d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b1df  jnz     short loc_18000B234
0x18000b1e1  xor     r8d, r8d
0x18000b1e4  xor     edx, edx
0x18000b1e6  mov     rcx, rbx
0x18000b1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1ee  jmp     short loc_18000B234
0x18000b1f0  mov     ebp, 800h
0x18000b1f5  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b1fc  test    rax, rax
0x18000b1ff  jz      short loc_18000B218
0x18000b201  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b208  jnz     short loc_18000B218
0x18000b20a  mov     r8d, ebp
0x18000b20d  mov     rdx, rsi
0x18000b210  mov     rcx, rbx
0x18000b213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b218  cmp     [rsi], di
0x18000b21b  jnz     short loc_18000B22B
0x18000b21d  mov     r8, rbx; unsigned __int64
0x18000b220  mov     rdx, rbp; unsigned __int16 *
0x18000b223  mov     rcx, rsi; this
0x18000b226  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b22b  mov     rcx, rsi; lpOutputString
0x18000b22e  call    cs:__imp_OutputDebugStringW
0x18000b234  test    byte ptr [rbx+4], 4
0x18000b238  jnz     short loc_18000B243
0x18000b23a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000b241  jz      short loc_18000B255
0x18000b243  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b24a  test    rax, rax
0x18000b24d  jz      short loc_18000B255
0x18000b24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b254  nop
0x18000b255  mov     rbx, [rsp+78h+arg_10]
0x18000b25d  add     rsp, 40h
0x18000b261  pop     r15
0x18000b263  pop     r14
0x18000b265  pop     r13
0x18000b267  pop     r12
0x18000b269  pop     rdi
0x18000b26a  pop     rsi
0x18000b26b  pop     rbp
0x18000b26c  retn
```
