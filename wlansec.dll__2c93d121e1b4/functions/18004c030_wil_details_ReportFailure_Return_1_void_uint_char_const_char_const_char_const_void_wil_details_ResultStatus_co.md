# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18004c030`
- end: `0x18004c2e9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180042e44`

## callees

- `0x18003d18c`
- `0x180041120`
- `0x180042614`
- `0x180043a30`
- `0x18004456c`
- `0x18004c030`
- `0x18004fc98`
- `0x180094810`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c0f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c0f6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004c1f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004c1f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004c281`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004c281`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18004c030  push    rbp
0x18004c032  push    rbx
0x18004c033  push    rsi
0x18004c034  push    rdi
0x18004c035  push    r12
0x18004c037  push    r14
0x18004c039  push    r15
0x18004c03b  lea     rbp, [rsp-13D0h]
0x18004c043  mov     eax, 14D0h
0x18004c048  call    _alloca_probe
0x18004c04d  sub     rsp, rax
0x18004c050  mov     rax, cs:__security_cookie
0x18004c057  xor     rax, rsp
0x18004c05a  mov     [rbp+1400h+var_40], rax
0x18004c061  mov     rsi, r8
0x18004c064  mov     edi, edx
0x18004c066  mov     rbx, rcx
0x18004c069  mov     r14, [rbp+1400h+arg_28]
0x18004c070  xor     edx, edx; Val
0x18004c072  mov     r8d, 98h; Size
0x18004c078  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18004c07d  call    memset_0
0x18004c082  nop
0x18004c083  xor     r12d, r12d
0x18004c086  mov     [rbp+1400h+OutputString], r12w
0x18004c08e  mov     [rbp+1400h+var_1440], r12b
0x18004c092  mov     rdx, [rbp+1400h+arg_30]; int
0x18004c099  mov     ecx, [rdx]; this
0x18004c09b  mov     [rsp+1500h+var_14D8], ecx
0x18004c09f  mov     eax, [rdx+4]
0x18004c0a2  mov     [rsp+1500h+var_14D4], eax
0x18004c0a6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004c0ab  mov     r15d, eax
0x18004c0ae  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18004c0b6  mov     ecx, r12d
0x18004c0b9  lea     eax, [r12+8]
0x18004c0be  cmp     dword ptr [rdx+8], 1
0x18004c0c2  cmovz   ecx, eax
0x18004c0c5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18004c0c9  lea     ecx, [rax-7]
0x18004c0cc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004c0d4  inc     ecx
0x18004c0d6  mov     [rsp+1500h+var_14D0], ecx
0x18004c0da  mov     rcx, [rbp+1400h+arg_38]
0x18004c0e1  test    rcx, rcx
0x18004c0e4  jz      short loc_18004C0F1
0x18004c0e6  cmp     [rcx], r12w
0x18004c0ea  mov     [rsp+1500h+var_14C8], rcx
0x18004c0ef  jnz     short loc_18004C0F6
0x18004c0f1  mov     [rsp+1500h+var_14C8], r12
0x18004c0f6  call    cs:__imp_GetCurrentThreadId
0x18004c0fd  nop     dword ptr [rax+rax+00h]
0x18004c102  mov     [rsp+1500h+var_14C0], eax
0x18004c106  mov     [rsp+1500h+var_14A8], rsi
0x18004c10b  mov     [rsp+1500h+var_14A0], edi
0x18004c10f  mov     [rsp+1500h+var_149C], r15d
0x18004c114  mov     [rsp+1500h+var_14B8], r12
0x18004c119  mov     [rsp+1500h+var_14B0], r12
0x18004c11e  mov     [rbp+1400h+var_1458], r14
0x18004c122  mov     [rbp+1400h+var_1450], rbx
0x18004c126  mov     [rsp+1500h+var_1498], r12
0x18004c12b  xorps   xmm0, xmm0
0x18004c12e  xor     eax, eax
0x18004c130  movups  [rbp+1400h+var_1478], xmm0
0x18004c134  mov     [rbp+1400h+var_1468], rax
0x18004c138  xorps   xmm1, xmm1
0x18004c13b  movups  [rsp+1500h+var_1490], xmm1
0x18004c140  mov     [rbp+1400h+var_1480], rax
0x18004c144  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004c14b  test    rax, rax
0x18004c14e  jz      short loc_18004C15B
0x18004c150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c155  mov     [rbp+1400h+var_1460], rax
0x18004c159  jmp     short loc_18004C15F
0x18004c15b  mov     [rbp+1400h+var_1460], r12
0x18004c15f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004c166  test    rax, rax
0x18004c169  jz      short loc_18004C175
0x18004c16b  lea     rcx, [rsp+1500h+var_14E0]
0x18004c170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c175  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004c17c  test    rax, rax
0x18004c17f  jz      short loc_18004C195
0x18004c181  mov     r8d, 400h
0x18004c187  lea     rdx, [rbp+1400h+var_1440]
0x18004c18b  lea     rcx, [rsp+1500h+var_14E0]
0x18004c190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c195  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004c19c  test    rax, rax
0x18004c19f  jz      short loc_18004C1AB
0x18004c1a1  lea     rcx, [rsp+1500h+var_14E0]
0x18004c1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004c1b2  test    rax, rax
0x18004c1b5  jz      short loc_18004C1C8
0x18004c1b7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004c1bc  jnz     short loc_18004C1C8
0x18004c1be  lea     rcx, [rsp+1500h+var_14E0]
0x18004c1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1c8  cmp     [rsp+1500h+var_14D8], r12d
0x18004c1cd  jge     loc_18004C2E3
0x18004c1d3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18004c1da  jnz     short loc_18004C201
0x18004c1dc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004c1e3  test    rax, rax
0x18004c1e6  jz      short loc_18004C1F1
0x18004c1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1ed  test    al, al
0x18004c1ef  jmp     short loc_18004C1FF
0x18004c1f1  call    cs:__imp_IsDebuggerPresent
0x18004c1f8  nop     dword ptr [rax+rax+00h]
0x18004c1fd  test    eax, eax
0x18004c1ff  jz      short loc_18004C208
0x18004c201  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18004c206  jz      short loc_18004C22E
0x18004c208  mov     rax, cs:g_pfnResultLoggingCallback
0x18004c20f  test    rax, rax
0x18004c212  jz      short loc_18004C28D
0x18004c214  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18004c21b  jnz     short loc_18004C28D
0x18004c21d  xor     r8d, r8d
0x18004c220  xor     edx, edx
0x18004c222  lea     rcx, [rsp+1500h+var_14E0]
0x18004c227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c22c  jmp     short loc_18004C28D
0x18004c22e  mov     ebx, 800h
0x18004c233  mov     rax, cs:g_pfnResultLoggingCallback
0x18004c23a  test    rax, rax
0x18004c23d  jz      short loc_18004C25C
0x18004c23f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18004c246  jnz     short loc_18004C25C
0x18004c248  mov     r8d, ebx
0x18004c24b  lea     rdx, [rbp+1400h+OutputString]
0x18004c252  lea     rcx, [rsp+1500h+var_14E0]
0x18004c257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c25c  cmp     [rbp+1400h+OutputString], r12w
0x18004c264  jnz     short loc_18004C27A
0x18004c266  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18004c26b  mov     rdx, rbx; unsigned __int16 *
0x18004c26e  lea     rcx, [rbp+1400h+OutputString]; this
0x18004c275  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004c27a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18004c281  call    cs:__imp_OutputDebugStringW
0x18004c288  nop     dword ptr [rax+rax+00h]
0x18004c28d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18004c292  jnz     short loc_18004C29D
0x18004c294  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18004c29b  jz      short loc_18004C2AF
0x18004c29d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004c2a4  test    rax, rax
0x18004c2a7  jz      short loc_18004C2AF
0x18004c2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2ae  nop
0x18004c2af  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18004c2b4  jnz     short loc_18004C2D8
0x18004c2b6  mov     rcx, [rbp+1400h+var_40]
0x18004c2bd  xor     rcx, rsp; StackCookie
0x18004c2c0  call    __security_check_cookie
0x18004c2c5  add     rsp, 14D0h
0x18004c2cc  pop     r15
0x18004c2ce  pop     r14
0x18004c2d0  pop     r12
0x18004c2d2  pop     rdi
0x18004c2d3  pop     rsi
0x18004c2d4  pop     rbx
0x18004c2d5  pop     rbp
0x18004c2d6  retn
0x18004c2d8  lea     rcx, [rsp+1500h+var_14E0]; this
0x18004c2dd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18004c2e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
