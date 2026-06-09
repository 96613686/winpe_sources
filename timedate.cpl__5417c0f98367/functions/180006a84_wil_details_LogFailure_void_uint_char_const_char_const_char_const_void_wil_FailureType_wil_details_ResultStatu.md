# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006a84`
- end: `0x180006d80`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `764`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800047fc`
- `0x180004b48`

## callees

- `0x18000473c`
- `0x180005e14`
- `0x180006630`
- `0x180006a84`
- `0x180007928`
- `0x180007950`
- `0x180007964`
- `0x180007980`
- `0x1800091b4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d3c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d3c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006cca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006cca`

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
0x180006a84  mov     [rsp+arg_10], rbx
0x180006a89  mov     [rsp+arg_8], edx
0x180006a8d  mov     [rsp+arg_0], rcx
0x180006a92  push    rbp
0x180006a93  push    rsi
0x180006a94  push    rdi
0x180006a95  push    r12
0x180006a97  push    r13
0x180006a99  push    r14
0x180006a9b  push    r15
0x180006a9d  sub     rsp, 40h
0x180006aa1  mov     r14, [rsp+78h+arg_38]
0x180006aa9  xor     eax, eax
0x180006aab  mov     rbx, [rsp+78h+arg_78]
0x180006ab3  xor     ebp, ebp
0x180006ab5  mov     r15d, [rsp+78h+arg_30]
0x180006abd  mov     r10, rcx
0x180006ac0  mov     rsi, [rsp+78h+lpOutputString]
0x180006ac8  mov     r12, r9
0x180006acb  mov     r13, r8
0x180006ace  mov     ecx, r15d
0x180006ad1  mov     [rsi], ax
0x180006ad4  mov     rax, [rsp+78h+arg_60]
0x180006adc  mov     byte ptr [rax], 0
0x180006adf  mov     edi, [r14]
0x180006ae2  mov     [rbx+8], edi
0x180006ae5  mov     eax, [r14+4]
0x180006ae9  mov     [rbx+0Ch], eax
0x180006aec  test    r15d, r15d
0x180006aef  jz      short loc_180006B5B
0x180006af1  sub     ecx, 1
0x180006af4  jz      short loc_180006B52
0x180006af6  sub     ecx, 1
0x180006af9  jz      short loc_180006B09
0x180006afb  cmp     ecx, 1
0x180006afe  jnz     short loc_180006B64
0x180006b00  mov     ecx, edi; this
0x180006b02  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006b07  jmp     short loc_180006B62
0x180006b09  test    edi, edi
0x180006b0b  js      short loc_180006B49
0x180006b0d  mov     rax, [rsp+78h+arg_28]
0x180006b15  mov     edi, 8007029Ch
0x180006b1a  mov     [rsp+78h+var_40], ebp
0x180006b1e  mov     rcx, r10; int
0x180006b21  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006b25  mov     [rsp+78h+var_50], rax; __int64
0x180006b2a  mov     rax, [rsp+78h+arg_20]
0x180006b32  mov     [rsp+78h+var_58], rax; __int64
0x180006b37  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006b3c  mov     ecx, edi; this
0x180006b3e  mov     [rbx+8], edi
0x180006b41  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006b46  mov     [rbx+0Ch], eax
0x180006b49  mov     ecx, edi; this
0x180006b4b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006b50  jmp     short loc_180006B62
0x180006b52  mov     ecx, edi; this
0x180006b54  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006b59  jmp     short loc_180006B62
0x180006b5b  mov     ecx, edi; this
0x180006b5d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006b62  mov     ebp, eax
0x180006b64  mov     eax, [rsp+78h+arg_70]
0x180006b6b  mov     [rbx+4], eax
0x180006b6e  mov     [rbx], r15d
0x180006b71  cmp     dword ptr [r14+8], 1
0x180006b76  jnz     short loc_180006B7E
0x180006b78  or      eax, 8
0x180006b7b  mov     [rbx+4], eax
0x180006b7e  mov     eax, 1
0x180006b83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006b8b  inc     eax
0x180006b8d  xor     edi, edi
0x180006b8f  mov     [rbx+10h], eax
0x180006b92  mov     rax, [rsp+78h+arg_40]
0x180006b9a  test    rax, rax
0x180006b9d  jz      short loc_180006BA4
0x180006b9f  cmp     [rax], di
0x180006ba2  jnz     short loc_180006BA7
0x180006ba4  mov     rax, rdi
0x180006ba7  mov     [rbx+18h], rax
0x180006bab  call    cs:__imp_GetCurrentThreadId
0x180006bb1  mov     [rbx+38h], r13
0x180006bb5  xorps   xmm0, xmm0
0x180006bb8  mov     [rbx+20h], eax
0x180006bbb  mov     eax, [rsp+78h+arg_8]
0x180006bc2  mov     [rbx+40h], eax
0x180006bc5  mov     rax, [rsp+78h+arg_20]
0x180006bcd  mov     [rbx+28h], rax
0x180006bd1  mov     rax, [rsp+78h+arg_28]
0x180006bd9  mov     [rbx+88h], rax
0x180006be0  mov     rax, [rsp+78h+arg_0]
0x180006be8  mov     [rbx+90h], rax
0x180006bef  xor     eax, eax
0x180006bf1  mov     [rbx+44h], ebp
0x180006bf4  mov     [rbx+30h], r12
0x180006bf8  mov     [rbx+48h], rdi
0x180006bfc  movups  xmmword ptr [rbx+68h], xmm0
0x180006c00  mov     [rbx+78h], rax
0x180006c04  movups  xmmword ptr [rbx+50h], xmm0
0x180006c08  mov     [rbx+60h], rax
0x180006c0c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006c13  test    rax, rax
0x180006c16  jz      short loc_180006C1F
0x180006c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c1d  jmp     short loc_180006C22
0x180006c1f  mov     rax, rdi
0x180006c22  mov     [rbx+80h], rax
0x180006c29  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c30  test    rax, rax
0x180006c33  jz      short loc_180006C3D
0x180006c35  mov     rcx, rbx
0x180006c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c3d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c44  test    rax, rax
0x180006c47  jz      short loc_180006C5F
0x180006c49  mov     rdx, [rsp+78h+arg_60]
0x180006c51  mov     r8d, 400h
0x180006c57  mov     rcx, rbx
0x180006c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c5f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c66  test    rax, rax
0x180006c69  jz      short loc_180006C73
0x180006c6b  mov     rcx, rbx
0x180006c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c73  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c7a  test    rax, rax
0x180006c7d  jz      short loc_180006C8D
0x180006c7f  test    byte ptr [rbx+4], 2
0x180006c83  jnz     short loc_180006C8D
0x180006c85  mov     rcx, rbx
0x180006c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8d  cmp     [rbx+8], edi
0x180006c90  jl      short loc_180006CAC
0x180006c92  cmp     r15d, 3
0x180006c96  jnz     loc_180006D7A
0x180006c9c  mov     ecx, 8000FFFFh; this
0x180006ca1  mov     [rbx+8], ecx
0x180006ca4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006ca9  mov     [rbx+0Ch], eax
0x180006cac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006cb3  jnz     short loc_180006CD4
0x180006cb5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006cbc  test    rax, rax
0x180006cbf  jz      short loc_180006CCA
0x180006cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc6  test    al, al
0x180006cc8  jmp     short loc_180006CD2
0x180006cca  call    cs:__imp_IsDebuggerPresent
0x180006cd0  test    eax, eax
0x180006cd2  jz      short loc_180006CDA
0x180006cd4  test    byte ptr [rbx+4], 2
0x180006cd8  jz      short loc_180006CFE
0x180006cda  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ce1  test    rax, rax
0x180006ce4  jz      short loc_180006D42
0x180006ce6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006ced  jnz     short loc_180006D42
0x180006cef  xor     r8d, r8d
0x180006cf2  xor     edx, edx
0x180006cf4  mov     rcx, rbx
0x180006cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cfc  jmp     short loc_180006D42
0x180006cfe  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d05  mov     ebp, 800h
0x180006d0a  test    rax, rax
0x180006d0d  jz      short loc_180006D26
0x180006d0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d16  jnz     short loc_180006D26
0x180006d18  mov     r8d, ebp
0x180006d1b  mov     rdx, rsi
0x180006d1e  mov     rcx, rbx
0x180006d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d26  cmp     [rsi], di
0x180006d29  jnz     short loc_180006D39
0x180006d2b  mov     r8, rbx; unsigned __int64
0x180006d2e  mov     rdx, rbp; unsigned __int16 *
0x180006d31  mov     rcx, rsi; this
0x180006d34  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d39  mov     rcx, rsi; lpOutputString
0x180006d3c  call    cs:__imp_OutputDebugStringW
0x180006d42  test    byte ptr [rbx+4], 4
0x180006d46  jnz     short loc_180006D51
0x180006d48  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006d4f  jz      short loc_180006D62
0x180006d51  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006d58  test    rax, rax
0x180006d5b  jz      short loc_180006D62
0x180006d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d62  mov     rbx, [rsp+78h+arg_10]
0x180006d6a  add     rsp, 40h
0x180006d6e  pop     r15
0x180006d70  pop     r14
0x180006d72  pop     r13
0x180006d74  pop     r12
0x180006d76  pop     rdi
0x180006d77  pop     rsi
0x180006d78  pop     rbp
0x180006d79  retn
0x180006d7a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
