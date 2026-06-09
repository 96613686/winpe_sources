# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005a50`
- end: `0x180005d53`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007274`

## callees

- `0x180004724`
- `0x180004aec`
- `0x180004b08`
- `0x180004b24`
- `0x180004b40`
- `0x180004d50`
- `0x180005a50`
- `0x180005f00`
- `0x180006bb4`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005d0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005d0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c94`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c94`

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
  int v19; // esi
  int v20; // eax
  _WORD *v21; // rax
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  wil::details *v25; // [rsp+30h] [rbp-48h]

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
          LODWORD(v25) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v25);
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
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
}

```

## disassembly

```asm
0x180005a50  mov     [rsp+arg_10], rbx
0x180005a55  mov     [rsp+arg_8], edx
0x180005a59  mov     [rsp+arg_0], rcx
0x180005a5e  push    rbp
0x180005a5f  push    rsi
0x180005a60  push    rdi
0x180005a61  push    r12
0x180005a63  push    r13
0x180005a65  push    r14
0x180005a67  push    r15
0x180005a69  sub     rsp, 40h
0x180005a6d  mov     r12, r9
0x180005a70  mov     r13, r8
0x180005a73  mov     r10, rcx
0x180005a76  xor     r8d, r8d
0x180005a79  mov     r14, [rsp+78h+lpOutputString]
0x180005a81  mov     [r14], r8w
0x180005a85  mov     rax, [rsp+78h+arg_60]
0x180005a8d  mov     [rax], r8b
0x180005a90  mov     r15, [rsp+78h+arg_38]
0x180005a98  mov     edi, [r15]
0x180005a9b  mov     rbx, [rsp+78h+arg_78]
0x180005aa3  mov     [rbx+8], edi
0x180005aa6  mov     eax, [r15+4]
0x180005aaa  mov     [rbx+0Ch], eax
0x180005aad  mov     esi, r8d
0x180005ab0  mov     ebp, [rsp+78h+arg_30]
0x180005ab7  mov     ecx, ebp
0x180005ab9  test    ebp, ebp
0x180005abb  jz      short loc_180005B26
0x180005abd  sub     ecx, 1
0x180005ac0  jz      short loc_180005B1D
0x180005ac2  sub     ecx, 1
0x180005ac5  jz      short loc_180005AD5
0x180005ac7  cmp     ecx, 1
0x180005aca  jnz     short loc_180005B2F
0x180005acc  mov     ecx, edi; this
0x180005ace  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005ad3  jmp     short loc_180005B2D
0x180005ad5  test    edi, edi
0x180005ad7  js      short loc_180005B14
0x180005ad9  mov     edi, 8007029Ch
0x180005ade  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005ae2  mov     rax, [rsp+78h+arg_28]
0x180005aea  mov     [rsp+78h+var_50], rax; __int64
0x180005aef  mov     rax, [rsp+78h+arg_20]
0x180005af7  mov     [rsp+78h+var_58], rax; __int64
0x180005afc  mov     r8, r13; int
0x180005aff  mov     rcx, r10; int
0x180005b02  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005b07  mov     [rbx+8], edi
0x180005b0a  mov     ecx, edi; this
0x180005b0c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005b11  mov     [rbx+0Ch], eax
0x180005b14  mov     ecx, edi; this
0x180005b16  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005b1b  jmp     short loc_180005B2D
0x180005b1d  mov     ecx, edi; this
0x180005b1f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005b24  jmp     short loc_180005B2D
0x180005b26  mov     ecx, edi; this
0x180005b28  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005b2d  mov     esi, eax
0x180005b2f  mov     [rbx], ebp
0x180005b31  mov     eax, [rsp+78h+arg_70]
0x180005b38  mov     [rbx+4], eax
0x180005b3b  cmp     dword ptr [r15+8], 1
0x180005b40  jnz     short loc_180005B48
0x180005b42  or      eax, 8
0x180005b45  mov     [rbx+4], eax
0x180005b48  mov     eax, 1
0x180005b4d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005b55  inc     eax
0x180005b57  mov     [rbx+10h], eax
0x180005b5a  mov     rax, [rsp+78h+arg_40]
0x180005b62  xor     edi, edi
0x180005b64  test    rax, rax
0x180005b67  jz      short loc_180005B6E
0x180005b69  cmp     [rax], di
0x180005b6c  jnz     short loc_180005B71
0x180005b6e  mov     rax, rdi
0x180005b71  mov     [rbx+18h], rax
0x180005b75  call    cs:__imp_GetCurrentThreadId
0x180005b7b  mov     [rbx+20h], eax
0x180005b7e  mov     [rbx+38h], r13
0x180005b82  mov     eax, [rsp+78h+arg_8]
0x180005b89  mov     [rbx+40h], eax
0x180005b8c  mov     [rbx+44h], esi
0x180005b8f  mov     rax, [rsp+78h+arg_20]
0x180005b97  mov     [rbx+28h], rax
0x180005b9b  mov     [rbx+30h], r12
0x180005b9f  mov     rax, [rsp+78h+arg_28]
0x180005ba7  mov     [rbx+88h], rax
0x180005bae  mov     rax, [rsp+78h+arg_0]
0x180005bb6  mov     [rbx+90h], rax
0x180005bbd  mov     [rbx+48h], rdi
0x180005bc1  xorps   xmm0, xmm0
0x180005bc4  xor     eax, eax
0x180005bc6  movups  xmmword ptr [rbx+68h], xmm0
0x180005bca  mov     [rbx+78h], rax
0x180005bce  movups  xmmword ptr [rbx+50h], xmm0
0x180005bd2  mov     [rbx+60h], rax
0x180005bd6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005bdd  test    rax, rax
0x180005be0  jz      short loc_180005BE9
0x180005be2  call    _guard_dispatch_icall
0x180005be7  jmp     short loc_180005BEC
0x180005be9  mov     rax, rdi
0x180005bec  mov     [rbx+80h], rax
0x180005bf3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005bfa  test    rax, rax
0x180005bfd  jz      short loc_180005C07
0x180005bff  mov     rcx, rbx
0x180005c02  call    _guard_dispatch_icall
0x180005c07  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005c0e  test    rax, rax
0x180005c11  jz      short loc_180005C29
0x180005c13  mov     r8d, 400h
0x180005c19  mov     rdx, [rsp+78h+arg_60]
0x180005c21  mov     rcx, rbx
0x180005c24  call    _guard_dispatch_icall
0x180005c29  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c30  test    rax, rax
0x180005c33  jz      short loc_180005C3D
0x180005c35  mov     rcx, rbx
0x180005c38  call    _guard_dispatch_icall
0x180005c3d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005c44  test    rax, rax
0x180005c47  jz      short loc_180005C57
0x180005c49  test    byte ptr [rbx+4], 2
0x180005c4d  jnz     short loc_180005C57
0x180005c4f  mov     rcx, rbx
0x180005c52  call    _guard_dispatch_icall
0x180005c57  cmp     [rbx+8], edi
0x180005c5a  jl      short loc_180005C75
0x180005c5c  cmp     ebp, 3
0x180005c5f  jnz     loc_180005D4D
0x180005c65  mov     ecx, 8000FFFFh; this
0x180005c6a  mov     [rbx+8], ecx
0x180005c6d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005c72  mov     [rbx+0Ch], eax
0x180005c75  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005c7c  jnz     short loc_180005CA5
0x180005c7e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005c85  test    rax, rax
0x180005c88  jz      short loc_180005C94
0x180005c8a  call    _guard_dispatch_icall
0x180005c8f  movzx   ecx, al
0x180005c92  jmp     short loc_180005CA1
0x180005c94  call    cs:__imp_IsDebuggerPresent
0x180005c9a  mov     ecx, edi
0x180005c9c  test    eax, eax
0x180005c9e  setnz   cl
0x180005ca1  test    ecx, ecx
0x180005ca3  jz      short loc_180005CAB
0x180005ca5  test    byte ptr [rbx+4], 2
0x180005ca9  jz      short loc_180005CCF
0x180005cab  mov     rax, cs:g_pfnResultLoggingCallback
0x180005cb2  test    rax, rax
0x180005cb5  jz      short loc_180005D14
0x180005cb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005cbe  jnz     short loc_180005D14
0x180005cc0  xor     r8d, r8d
0x180005cc3  xor     edx, edx
0x180005cc5  mov     rcx, rbx
0x180005cc8  call    _guard_dispatch_icall
0x180005ccd  jmp     short loc_180005D14
0x180005ccf  mov     esi, 800h
0x180005cd4  mov     rax, cs:g_pfnResultLoggingCallback
0x180005cdb  test    rax, rax
0x180005cde  jz      short loc_180005CF7
0x180005ce0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ce7  jnz     short loc_180005CF7
0x180005ce9  mov     r8d, esi
0x180005cec  mov     rdx, r14
0x180005cef  mov     rcx, rbx
0x180005cf2  call    _guard_dispatch_icall
0x180005cf7  cmp     [r14], di
0x180005cfb  jnz     short loc_180005D0B
0x180005cfd  mov     r8, rbx; unsigned __int64
0x180005d00  mov     rdx, rsi; wchar_t *
0x180005d03  mov     rcx, r14; this
0x180005d06  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005d0b  mov     rcx, r14; lpOutputString
0x180005d0e  call    cs:__imp_OutputDebugStringW
0x180005d14  test    byte ptr [rbx+4], 4
0x180005d18  jnz     short loc_180005D23
0x180005d1a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005d21  jz      short loc_180005D35
0x180005d23  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005d2a  test    rax, rax
0x180005d2d  jz      short loc_180005D35
0x180005d2f  call    _guard_dispatch_icall
0x180005d34  nop
0x180005d35  mov     rbx, [rsp+78h+arg_10]
0x180005d3d  add     rsp, 40h
0x180005d41  pop     r15
0x180005d43  pop     r14
0x180005d45  pop     r13
0x180005d47  pop     r12
0x180005d49  pop     rdi
0x180005d4a  pop     rsi
0x180005d4b  pop     rbp
0x180005d4c  retn
0x180005d4d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
