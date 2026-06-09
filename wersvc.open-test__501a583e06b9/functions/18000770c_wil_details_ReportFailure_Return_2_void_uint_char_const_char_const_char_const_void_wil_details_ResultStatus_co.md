# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000770c`
- end: `0x180007a0c`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180006f58`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180004fe4`
- `0x1800053cc`
- `0x180006250`
- `0x180007150`
- `0x18000770c`
- `0x18000b7b8`
- `0x18001140c`
- `0x1800344f0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000782d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000782d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800079a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800079a9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007920`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007920`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x18000770c  push    rbp
0x18000770e  push    rbx
0x18000770f  push    rsi
0x180007710  push    rdi
0x180007711  push    r12
0x180007713  push    r13
0x180007715  push    r14
0x180007717  push    r15
0x180007719  lea     rbp, [rsp-1408h]
0x180007721  mov     eax, 1508h
0x180007726  call    _alloca_probe
0x18000772b  sub     rsp, rax
0x18000772e  mov     rax, cs:__security_cookie
0x180007735  xor     rax, rsp
0x180007738  mov     [rbp+1440h+var_50], rax
0x18000773f  mov     r12, r9
0x180007742  mov     r15, r8
0x180007745  mov     r14d, edx
0x180007748  mov     rsi, rcx
0x18000774b  mov     r13, [rbp+1440h+arg_20]
0x180007752  mov     rax, [rbp+1440h+arg_28]
0x180007759  mov     [rsp+1540h+var_1500], rax
0x18000775e  xor     edx, edx; Val
0x180007760  mov     r8d, 98h; Size
0x180007766  lea     rcx, [rsp+1540h+var_14F0]; void *
0x18000776b  call    memset_0
0x180007770  nop
0x180007771  xor     eax, eax
0x180007773  mov     [rbp+1440h+OutputString], ax
0x18000777a  mov     [rbp+1440h+var_1450], al
0x18000777d  mov     rdi, [rbp+1440h+arg_30]
0x180007784  mov     ebx, [rdi]
0x180007786  mov     [rsp+1540h+var_14E8], ebx
0x18000778a  mov     eax, [rdi+4]
0x18000778d  mov     [rsp+1540h+var_14E4], eax
0x180007791  test    ebx, ebx
0x180007793  js      short loc_1800077D5
0x180007795  mov     [rsp+1540h+var_1508], 0
0x18000779d  mov     ebx, 8007029Ch
0x1800077a2  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x1800077a6  mov     rax, [rsp+1540h+var_1500]
0x1800077ab  mov     [rsp+1540h+var_1518], rax; __int64
0x1800077b0  mov     [rsp+1540h+var_1520], r13; __int64
0x1800077b5  mov     r9, r12; int
0x1800077b8  mov     r8, r15; int
0x1800077bb  mov     edx, r14d; int
0x1800077be  mov     rcx, rsi; int
0x1800077c1  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800077c6  mov     [rsp+1540h+var_14E8], ebx
0x1800077ca  mov     ecx, ebx; this
0x1800077cc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800077d1  mov     [rsp+1540h+var_14E4], eax
0x1800077d5  mov     ecx, ebx; this
0x1800077d7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800077dc  mov     ebx, eax
0x1800077de  mov     dword ptr [rsp+1540h+var_14F0], 2
0x1800077e6  mov     ecx, [rbp+1440h+arg_48]
0x1800077ec  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800077f0  cmp     dword ptr [rdi+8], 1
0x1800077f4  jnz     short loc_1800077FD
0x1800077f6  or      ecx, 8
0x1800077f9  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800077fd  mov     ecx, 1
0x180007802  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000780a  inc     ecx
0x18000780c  mov     [rsp+1540h+var_14E0], ecx
0x180007810  mov     rax, [rbp+1440h+arg_38]
0x180007817  xor     edi, edi
0x180007819  test    rax, rax
0x18000781c  jz      short loc_180007828
0x18000781e  cmp     [rax], di
0x180007821  mov     [rsp+1540h+var_14D8], rax
0x180007826  jnz     short loc_18000782D
0x180007828  mov     [rsp+1540h+var_14D8], rdi
0x18000782d  call    cs:__imp_GetCurrentThreadId
0x180007833  mov     [rsp+1540h+var_14D0], eax
0x180007837  mov     [rbp+1440h+var_14B8], r15
0x18000783b  mov     [rbp+1440h+var_14B0], r14d
0x18000783f  mov     [rbp+1440h+var_14AC], ebx
0x180007842  mov     [rsp+1540h+var_14C8], r13
0x180007847  mov     [rbp+1440h+var_14C0], r12
0x18000784b  mov     rax, [rsp+1540h+var_1500]
0x180007850  mov     [rbp+1440h+var_1468], rax
0x180007854  mov     [rbp+1440h+var_1460], rsi
0x180007858  mov     [rbp+1440h+var_14A8], rdi
0x18000785c  xorps   xmm0, xmm0
0x18000785f  xor     eax, eax
0x180007861  movups  [rbp+1440h+var_1488], xmm0
0x180007865  mov     [rbp+1440h+var_1478], rax
0x180007869  xorps   xmm1, xmm1
0x18000786c  movups  [rbp+1440h+var_14A0], xmm1
0x180007870  mov     [rbp+1440h+var_1490], rax
0x180007874  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000787b  test    rax, rax
0x18000787e  jz      short loc_18000788B
0x180007880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007885  mov     [rbp+1440h+var_1470], rax
0x180007889  jmp     short loc_18000788F
0x18000788b  mov     [rbp+1440h+var_1470], rdi
0x18000788f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007896  test    rax, rax
0x180007899  jz      short loc_1800078A5
0x18000789b  lea     rcx, [rsp+1540h+var_14F0]
0x1800078a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800078ac  test    rax, rax
0x1800078af  jz      short loc_1800078C5
0x1800078b1  mov     r8d, 400h
0x1800078b7  lea     rdx, [rbp+1440h+var_1450]
0x1800078bb  lea     rcx, [rsp+1540h+var_14F0]
0x1800078c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800078cc  test    rax, rax
0x1800078cf  jz      short loc_1800078DB
0x1800078d1  lea     rcx, [rsp+1540h+var_14F0]
0x1800078d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800078e2  test    rax, rax
0x1800078e5  jz      short loc_1800078F8
0x1800078e7  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800078ec  jnz     short loc_1800078F8
0x1800078ee  lea     rcx, [rsp+1540h+var_14F0]
0x1800078f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078f8  cmp     [rsp+1540h+var_14E8], edi
0x1800078fc  jge     loc_180007A06
0x180007902  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007909  jnz     short loc_18000792A
0x18000790b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007912  test    rax, rax
0x180007915  jz      short loc_180007920
0x180007917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000791c  test    al, al
0x18000791e  jmp     short loc_180007928
0x180007920  call    cs:__imp_IsDebuggerPresent
0x180007926  test    eax, eax
0x180007928  jz      short loc_180007931
0x18000792a  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x18000792f  jz      short loc_180007957
0x180007931  mov     rax, cs:g_pfnResultLoggingCallback
0x180007938  test    rax, rax
0x18000793b  jz      short loc_1800079AF
0x18000793d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007944  jnz     short loc_1800079AF
0x180007946  xor     r8d, r8d
0x180007949  xor     edx, edx
0x18000794b  lea     rcx, [rsp+1540h+var_14F0]
0x180007950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007955  jmp     short loc_1800079AF
0x180007957  mov     ebx, 800h
0x18000795c  mov     rax, cs:g_pfnResultLoggingCallback
0x180007963  test    rax, rax
0x180007966  jz      short loc_180007985
0x180007968  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000796f  jnz     short loc_180007985
0x180007971  mov     r8d, ebx
0x180007974  lea     rdx, [rbp+1440h+OutputString]
0x18000797b  lea     rcx, [rsp+1540h+var_14F0]
0x180007980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007985  cmp     [rbp+1440h+OutputString], di
0x18000798c  jnz     short loc_1800079A2
0x18000798e  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180007993  mov     rdx, rbx; wchar_t *
0x180007996  lea     rcx, [rbp+1440h+OutputString]; this
0x18000799d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800079a2  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x1800079a9  call    cs:__imp_OutputDebugStringW
0x1800079af  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x1800079b4  jnz     short loc_1800079BF
0x1800079b6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800079bd  jz      short loc_1800079D1
0x1800079bf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800079c6  test    rax, rax
0x1800079c9  jz      short loc_1800079D1
0x1800079cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d0  nop
0x1800079d1  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x1800079d6  jnz     short loc_1800079FB
0x1800079d8  mov     rcx, [rbp+1440h+var_50]
0x1800079df  xor     rcx, rsp; StackCookie
0x1800079e2  call    __security_check_cookie
0x1800079e7  add     rsp, 1508h
0x1800079ee  pop     r15
0x1800079f0  pop     r14
0x1800079f2  pop     r13
0x1800079f4  pop     r12
0x1800079f6  pop     rdi
0x1800079f7  pop     rsi
0x1800079f8  pop     rbx
0x1800079f9  pop     rbp
0x1800079fa  retn
0x1800079fb  lea     rcx, [rsp+1540h+var_14F0]; this
0x180007a00  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007a06  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
