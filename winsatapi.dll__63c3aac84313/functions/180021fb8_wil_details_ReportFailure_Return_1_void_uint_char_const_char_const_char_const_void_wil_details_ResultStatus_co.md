# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180021fb8`
- end: `0x18002225a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180012440`

## callees

- `0x1800151bb`
- `0x180021fb8`
- `0x1800243c4`
- `0x180025adc`
- `0x180026e88`
- `0x180027338`
- `0x18002dec0`
- `0x18002df80`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002206f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002206f`
- `KERNEL32!IsDebuggerPresent` at `0x18002216a`
- `KERNEL32!IsDebuggerPresent` at `0x18002216a`
- `KERNEL32!OutputDebugStringW` at `0x1800221f4`
- `KERNEL32!OutputDebugStringW` at `0x1800221f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180021fb8  push    rbp
0x180021fba  push    rsi
0x180021fbb  push    rdi
0x180021fbc  push    r14
0x180021fbe  push    r15
0x180021fc0  lea     rbp, [rsp-13E0h]
0x180021fc8  mov     eax, 14E0h
0x180021fcd  call    _alloca_probe
0x180021fd2  sub     rsp, rax
0x180021fd5  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x180021fdd  mov     [rsp+1500h+arg_10], rbx
0x180021fe5  mov     rax, cs:__security_cookie
0x180021fec  xor     rax, rsp
0x180021fef  mov     [rbp+1400h+var_30], rax
0x180021ff6  mov     esi, edx
0x180021ff8  mov     r14, rcx
0x180021ffb  mov     rdi, [rbp+1400h+arg_28]
0x180022002  xor     edx, edx; Val
0x180022004  mov     r8d, 98h; Size
0x18002200a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18002200f  call    memset_0
0x180022014  nop
0x180022015  xor     r15d, r15d
0x180022018  mov     [rbp+1400h+OutputString], r15w
0x180022020  mov     [rbp+1400h+var_1430], r15b
0x180022024  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18002202b  mov     ecx, [rdx]; this
0x18002202d  mov     [rsp+1500h+var_14D8], ecx
0x180022031  mov     eax, [rdx+4]
0x180022034  mov     [rsp+1500h+var_14D4], eax
0x180022038  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002203d  mov     ebx, eax
0x18002203f  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180022047  mov     ecx, r15d
0x18002204a  lea     eax, [r15+8]
0x18002204e  cmp     dword ptr [rdx+8], 1
0x180022052  cmovz   ecx, eax
0x180022055  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180022059  lea     ecx, [rax-7]
0x18002205c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180022064  inc     ecx
0x180022066  mov     [rsp+1500h+var_14D0], ecx
0x18002206a  mov     [rsp+1500h+var_14C8], r15
0x18002206f  call    cs:__imp_GetCurrentThreadId
0x180022075  mov     [rsp+1500h+var_14C0], eax
0x180022079  lea     rax, aWil; "wil"
0x180022080  mov     [rsp+1500h+var_14A8], rax
0x180022085  mov     [rsp+1500h+var_14A0], esi
0x180022089  mov     [rsp+1500h+var_149C], ebx
0x18002208d  mov     [rsp+1500h+var_14B8], r15
0x180022092  mov     [rsp+1500h+var_14B0], r15
0x180022097  mov     [rbp+1400h+var_1458], rdi
0x18002209b  mov     [rbp+1400h+var_1450], r14
0x18002209f  mov     [rsp+1500h+var_1498], r15
0x1800220a4  xorps   xmm0, xmm0
0x1800220a7  xor     eax, eax
0x1800220a9  movups  [rbp+1400h+var_1478], xmm0
0x1800220ad  mov     [rbp+1400h+var_1468], rax
0x1800220b1  xorps   xmm1, xmm1
0x1800220b4  movups  [rsp+1500h+var_1490], xmm1
0x1800220b9  mov     [rbp+1400h+var_1480], rax
0x1800220bd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800220c4  test    rax, rax
0x1800220c7  jz      short loc_1800220D4
0x1800220c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ce  mov     [rbp+1400h+var_1460], rax
0x1800220d2  jmp     short loc_1800220D8
0x1800220d4  mov     [rbp+1400h+var_1460], r15
0x1800220d8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800220df  test    rax, rax
0x1800220e2  jz      short loc_1800220EE
0x1800220e4  lea     rcx, [rsp+1500h+var_14E0]
0x1800220e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ee  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800220f5  test    rax, rax
0x1800220f8  jz      short loc_18002210E
0x1800220fa  mov     r8d, 400h
0x180022100  lea     rdx, [rbp+1400h+var_1430]
0x180022104  lea     rcx, [rsp+1500h+var_14E0]
0x180022109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002210e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022115  test    rax, rax
0x180022118  jz      short loc_180022124
0x18002211a  lea     rcx, [rsp+1500h+var_14E0]
0x18002211f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022124  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002212b  test    rax, rax
0x18002212e  jz      short loc_180022141
0x180022130  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180022135  jnz     short loc_180022141
0x180022137  lea     rcx, [rsp+1500h+var_14E0]
0x18002213c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022141  cmp     [rsp+1500h+var_14D8], r15d
0x180022146  jge     loc_180022254
0x18002214c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180022153  jnz     short loc_180022174
0x180022155  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002215c  test    rax, rax
0x18002215f  jz      short loc_18002216A
0x180022161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022166  test    al, al
0x180022168  jmp     short loc_180022172
0x18002216a  call    cs:__imp_IsDebuggerPresent
0x180022170  test    eax, eax
0x180022172  jz      short loc_18002217B
0x180022174  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180022179  jz      short loc_1800221A1
0x18002217b  mov     rax, cs:g_pfnResultLoggingCallback
0x180022182  test    rax, rax
0x180022185  jz      short loc_1800221FA
0x180022187  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002218e  jnz     short loc_1800221FA
0x180022190  xor     r8d, r8d
0x180022193  xor     edx, edx
0x180022195  lea     rcx, [rsp+1500h+var_14E0]
0x18002219a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002219f  jmp     short loc_1800221FA
0x1800221a1  mov     ebx, 800h
0x1800221a6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800221ad  test    rax, rax
0x1800221b0  jz      short loc_1800221CF
0x1800221b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800221b9  jnz     short loc_1800221CF
0x1800221bb  mov     r8d, ebx
0x1800221be  lea     rdx, [rbp+1400h+OutputString]
0x1800221c5  lea     rcx, [rsp+1500h+var_14E0]
0x1800221ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221cf  cmp     [rbp+1400h+OutputString], r15w
0x1800221d7  jnz     short loc_1800221ED
0x1800221d9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800221de  mov     rdx, rbx; unsigned __int16 *
0x1800221e1  lea     rcx, [rbp+1400h+OutputString]; this
0x1800221e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800221ed  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800221f4  call    cs:__imp_OutputDebugStringW
0x1800221fa  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800221ff  jnz     short loc_18002220A
0x180022201  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180022208  jz      short loc_18002221C
0x18002220a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180022211  test    rax, rax
0x180022214  jz      short loc_18002221C
0x180022216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002221b  nop
0x18002221c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180022221  jnz     short loc_180022249
0x180022223  mov     rcx, [rbp+1400h+var_30]
0x18002222a  xor     rcx, rsp; StackCookie
0x18002222d  call    __security_check_cookie
0x180022232  mov     rbx, [rsp+1500h+arg_10]
0x18002223a  add     rsp, 14E0h
0x180022241  pop     r15
0x180022243  pop     r14
0x180022245  pop     rdi
0x180022246  pop     rsi
0x180022247  pop     rbp
0x180022248  retn
0x180022249  lea     rcx, [rsp+1500h+var_14E0]; this
0x18002224e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180022254  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
