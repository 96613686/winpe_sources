# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400021b0`
- end: `0x14000243b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140001c88`

## callees

- `0x140001a63`
- `0x1400021b0`
- `0x1400030b4`
- `0x140003fb0`
- `0x140004860`
- `0x14000493c`
- `0x140014910`
- `0x1400149a0`
- `0x140015010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140002351`
- `KERNEL32!IsDebuggerPresent` at `0x140002351`
- `KERNEL32!OutputDebugStringW` at `0x1400023db`
- `KERNEL32!OutputDebugStringW` at `0x1400023db`
- `KERNEL32!GetCurrentThreadId` at `0x14000225d`
- `KERNEL32!GetCurrentThreadId` at `0x14000225d`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x1400021b0  push    rbp
0x1400021b2  push    rbx
0x1400021b3  push    rsi
0x1400021b4  push    rdi
0x1400021b5  push    r12
0x1400021b7  push    r14
0x1400021b9  push    r15
0x1400021bb  lea     rbp, [rsp-13D0h]
0x1400021c3  mov     eax, 14D0h
0x1400021c8  call    _alloca_probe
0x1400021cd  sub     rsp, rax
0x1400021d0  mov     rax, cs:__security_cookie
0x1400021d7  xor     rax, rsp
0x1400021da  mov     [rbp+1400h+var_40], rax
0x1400021e1  mov     rdi, [rbp+1400h+arg_28]
0x1400021e8  mov     r14, r8
0x1400021eb  mov     esi, edx
0x1400021ed  mov     r15, rcx
0x1400021f0  xor     edx, edx; Val
0x1400021f2  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400021f7  mov     r8d, 98h; Size
0x1400021fd  call    memset_0
0x140002202  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140002209  xor     r12d, r12d
0x14000220c  mov     [rbp+1400h+OutputString], r12w
0x140002214  mov     [rbp+1400h+var_1440], r12b
0x140002218  mov     ecx, [rdx]; this
0x14000221a  mov     eax, [rdx+4]
0x14000221d  mov     [rsp+1500h+var_14D8], ecx
0x140002221  mov     [rsp+1500h+var_14D4], eax
0x140002225  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000222a  cmp     dword ptr [rdx+8], 1
0x14000222e  mov     ebx, eax
0x140002230  lea     eax, [r12+8]
0x140002235  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000223d  mov     ecx, r12d
0x140002240  cmovz   ecx, eax
0x140002243  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002247  lea     ecx, [rax-7]
0x14000224a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002252  inc     ecx
0x140002254  mov     [rsp+1500h+var_14C8], r12
0x140002259  mov     [rsp+1500h+var_14D0], ecx
0x14000225d  call    cs:__imp_GetCurrentThreadId
0x140002263  xorps   xmm0, xmm0
0x140002266  mov     [rsp+1500h+var_14A8], r14
0x14000226b  mov     [rsp+1500h+var_14C0], eax
0x14000226f  xorps   xmm1, xmm1
0x140002272  xor     eax, eax
0x140002274  mov     [rsp+1500h+var_14A0], esi
0x140002278  mov     [rbp+1400h+var_1468], rax
0x14000227c  mov     [rbp+1400h+var_1480], rax
0x140002280  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002287  mov     [rsp+1500h+var_149C], ebx
0x14000228b  mov     [rsp+1500h+var_14B8], r12
0x140002290  mov     [rsp+1500h+var_14B0], r12
0x140002295  mov     [rbp+1400h+var_1458], rdi
0x140002299  mov     [rbp+1400h+var_1450], r15
0x14000229d  mov     [rsp+1500h+var_1498], r12
0x1400022a2  movups  [rbp+1400h+var_1478], xmm0
0x1400022a6  movups  [rsp+1500h+var_1490], xmm1
0x1400022ab  test    rax, rax
0x1400022ae  jz      short loc_1400022BB
0x1400022b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022b5  mov     [rbp+1400h+var_1460], rax
0x1400022b9  jmp     short loc_1400022BF
0x1400022bb  mov     [rbp+1400h+var_1460], r12
0x1400022bf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400022c6  test    rax, rax
0x1400022c9  jz      short loc_1400022D5
0x1400022cb  lea     rcx, [rsp+1500h+var_14E0]
0x1400022d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400022dc  test    rax, rax
0x1400022df  jz      short loc_1400022F5
0x1400022e1  mov     r8d, 400h
0x1400022e7  lea     rdx, [rbp+1400h+var_1440]
0x1400022eb  lea     rcx, [rsp+1500h+var_14E0]
0x1400022f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022f5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400022fc  test    rax, rax
0x1400022ff  jz      short loc_14000230B
0x140002301  lea     rcx, [rsp+1500h+var_14E0]
0x140002306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000230b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002312  test    rax, rax
0x140002315  jz      short loc_140002328
0x140002317  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000231c  jnz     short loc_140002328
0x14000231e  lea     rcx, [rsp+1500h+var_14E0]
0x140002323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002328  cmp     [rsp+1500h+var_14D8], r12d
0x14000232d  jge     loc_14000242A
0x140002333  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000233a  jnz     short loc_14000235B
0x14000233c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002343  test    rax, rax
0x140002346  jz      short loc_140002351
0x140002348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000234d  test    al, al
0x14000234f  jmp     short loc_140002359
0x140002351  call    cs:__imp_IsDebuggerPresent
0x140002357  test    eax, eax
0x140002359  jz      short loc_140002362
0x14000235b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002360  jz      short loc_140002388
0x140002362  mov     rax, cs:g_pfnResultLoggingCallback
0x140002369  test    rax, rax
0x14000236c  jz      short loc_1400023E1
0x14000236e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002375  jnz     short loc_1400023E1
0x140002377  xor     r8d, r8d
0x14000237a  lea     rcx, [rsp+1500h+var_14E0]
0x14000237f  xor     edx, edx
0x140002381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002386  jmp     short loc_1400023E1
0x140002388  mov     rax, cs:g_pfnResultLoggingCallback
0x14000238f  mov     ebx, 800h
0x140002394  test    rax, rax
0x140002397  jz      short loc_1400023B6
0x140002399  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400023a0  jnz     short loc_1400023B6
0x1400023a2  mov     r8d, ebx
0x1400023a5  lea     rdx, [rbp+1400h+OutputString]
0x1400023ac  lea     rcx, [rsp+1500h+var_14E0]
0x1400023b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023b6  cmp     [rbp+1400h+OutputString], r12w
0x1400023be  jnz     short loc_1400023D4
0x1400023c0  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400023c5  mov     rdx, rbx; unsigned __int16 *
0x1400023c8  lea     rcx, [rbp+1400h+OutputString]; this
0x1400023cf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400023d4  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400023db  call    cs:__imp_OutputDebugStringW
0x1400023e1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400023e6  jnz     short loc_1400023F1
0x1400023e8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400023ef  jz      short loc_140002402
0x1400023f1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400023f8  test    rax, rax
0x1400023fb  jz      short loc_140002402
0x1400023fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002402  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002407  jnz     short loc_140002430
0x140002409  mov     rcx, [rbp+1400h+var_40]
0x140002410  xor     rcx, rsp; StackCookie
0x140002413  call    __security_check_cookie
0x140002418  add     rsp, 14D0h
0x14000241f  pop     r15
0x140002421  pop     r14
0x140002423  pop     r12
0x140002425  pop     rdi
0x140002426  pop     rsi
0x140002427  pop     rbx
0x140002428  pop     rbp
0x140002429  retn
0x14000242a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002430  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002435  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
