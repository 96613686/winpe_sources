# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004638`
- end: `0x1800048de`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800040cc`

## callees

- `0x180001770`
- `0x1800021f4`
- `0x180002704`
- `0x180004638`
- `0x180009328`
- `0x18000b1bc`
- `0x18000b494`
- `0x18000d740`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000487d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000487d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047f3`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (__int64)&v18, v16);
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
0x180004638  push    rbp
0x18000463a  push    rbx
0x18000463b  push    rsi
0x18000463c  push    rdi
0x18000463d  push    r12
0x18000463f  push    r14
0x180004641  push    r15
0x180004643  lea     rbp, [rsp-13D0h]
0x18000464b  mov     eax, 14D0h
0x180004650  call    _alloca_probe
0x180004655  sub     rsp, rax
0x180004658  mov     rax, cs:__security_cookie
0x18000465f  xor     rax, rsp
0x180004662  mov     [rbp+1400h+var_40], rax
0x180004669  mov     rsi, r8
0x18000466c  mov     edi, edx
0x18000466e  mov     rbx, rcx
0x180004671  mov     r14, [rbp+1400h+arg_28]
0x180004678  xor     edx, edx; Val
0x18000467a  mov     r8d, 98h; Size
0x180004680  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004685  call    memset_0
0x18000468a  nop
0x18000468b  xor     r12d, r12d
0x18000468e  mov     [rbp+1400h+OutputString], r12w
0x180004696  mov     [rbp+1400h+var_1440], r12b
0x18000469a  mov     rdx, [rbp+1400h+arg_30]; int
0x1800046a1  mov     ecx, [rdx]; this
0x1800046a3  mov     [rsp+1500h+var_14D8], ecx
0x1800046a7  mov     eax, [rdx+4]
0x1800046aa  mov     [rsp+1500h+var_14D4], eax
0x1800046ae  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800046b3  mov     r15d, eax
0x1800046b6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800046be  mov     ecx, r12d
0x1800046c1  lea     eax, [r12+8]
0x1800046c6  cmp     dword ptr [rdx+8], 1
0x1800046ca  cmovz   ecx, eax
0x1800046cd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800046d1  lea     ecx, [rax-7]
0x1800046d4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800046dc  inc     ecx
0x1800046de  mov     [rsp+1500h+var_14D0], ecx
0x1800046e2  mov     rcx, [rbp+1400h+arg_38]
0x1800046e9  test    rcx, rcx
0x1800046ec  jz      short loc_1800046F9
0x1800046ee  cmp     [rcx], r12w
0x1800046f2  mov     [rsp+1500h+var_14C8], rcx
0x1800046f7  jnz     short loc_1800046FE
0x1800046f9  mov     [rsp+1500h+var_14C8], r12
0x1800046fe  call    cs:__imp_GetCurrentThreadId
0x180004704  mov     [rsp+1500h+var_14C0], eax
0x180004708  mov     [rsp+1500h+var_14A8], rsi
0x18000470d  mov     [rsp+1500h+var_14A0], edi
0x180004711  mov     [rsp+1500h+var_149C], r15d
0x180004716  mov     [rsp+1500h+var_14B8], r12
0x18000471b  mov     [rsp+1500h+var_14B0], r12
0x180004720  mov     [rbp+1400h+var_1458], r14
0x180004724  mov     [rbp+1400h+var_1450], rbx
0x180004728  mov     [rsp+1500h+var_1498], r12
0x18000472d  xorps   xmm0, xmm0
0x180004730  xor     eax, eax
0x180004732  movups  [rbp+1400h+var_1478], xmm0
0x180004736  mov     [rbp+1400h+var_1468], rax
0x18000473a  xorps   xmm1, xmm1
0x18000473d  movups  [rsp+1500h+var_1490], xmm1
0x180004742  mov     [rbp+1400h+var_1480], rax
0x180004746  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000474d  test    rax, rax
0x180004750  jz      short loc_18000475D
0x180004752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004757  mov     [rbp+1400h+var_1460], rax
0x18000475b  jmp     short loc_180004761
0x18000475d  mov     [rbp+1400h+var_1460], r12
0x180004761  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004768  test    rax, rax
0x18000476b  jz      short loc_180004777
0x18000476d  lea     rcx, [rsp+1500h+var_14E0]
0x180004772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004777  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000477e  test    rax, rax
0x180004781  jz      short loc_180004797
0x180004783  mov     r8d, 400h
0x180004789  lea     rdx, [rbp+1400h+var_1440]
0x18000478d  lea     rcx, [rsp+1500h+var_14E0]
0x180004792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004797  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000479e  test    rax, rax
0x1800047a1  jz      short loc_1800047AD
0x1800047a3  lea     rcx, [rsp+1500h+var_14E0]
0x1800047a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ad  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800047b4  test    rax, rax
0x1800047b7  jz      short loc_1800047CA
0x1800047b9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800047be  jnz     short loc_1800047CA
0x1800047c0  lea     rcx, [rsp+1500h+var_14E0]
0x1800047c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ca  cmp     [rsp+1500h+var_14D8], r12d
0x1800047cf  jge     loc_1800048D8
0x1800047d5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800047dc  jnz     short loc_1800047FD
0x1800047de  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800047e5  test    rax, rax
0x1800047e8  jz      short loc_1800047F3
0x1800047ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ef  test    al, al
0x1800047f1  jmp     short loc_1800047FB
0x1800047f3  call    cs:__imp_IsDebuggerPresent
0x1800047f9  test    eax, eax
0x1800047fb  jz      short loc_180004804
0x1800047fd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004802  jz      short loc_18000482A
0x180004804  mov     rax, cs:g_pfnResultLoggingCallback
0x18000480b  test    rax, rax
0x18000480e  jz      short loc_180004883
0x180004810  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004817  jnz     short loc_180004883
0x180004819  xor     r8d, r8d
0x18000481c  xor     edx, edx
0x18000481e  lea     rcx, [rsp+1500h+var_14E0]
0x180004823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004828  jmp     short loc_180004883
0x18000482a  mov     ebx, 800h
0x18000482f  mov     rax, cs:g_pfnResultLoggingCallback
0x180004836  test    rax, rax
0x180004839  jz      short loc_180004858
0x18000483b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004842  jnz     short loc_180004858
0x180004844  mov     r8d, ebx
0x180004847  lea     rdx, [rbp+1400h+OutputString]
0x18000484e  lea     rcx, [rsp+1500h+var_14E0]
0x180004853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004858  cmp     [rbp+1400h+OutputString], r12w
0x180004860  jnz     short loc_180004876
0x180004862  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004867  mov     rdx, rbx; wchar_t *
0x18000486a  lea     rcx, [rbp+1400h+OutputString]; this
0x180004871  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180004876  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000487d  call    cs:__imp_OutputDebugStringW
0x180004883  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004888  jnz     short loc_180004893
0x18000488a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004891  jz      short loc_1800048A5
0x180004893  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000489a  test    rax, rax
0x18000489d  jz      short loc_1800048A5
0x18000489f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a4  nop
0x1800048a5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800048aa  jnz     short loc_1800048CD
0x1800048ac  mov     rcx, [rbp+1400h+var_40]
0x1800048b3  xor     rcx, rsp; StackCookie
0x1800048b6  call    __security_check_cookie
0x1800048bb  add     rsp, 14D0h
0x1800048c2  pop     r15
0x1800048c4  pop     r14
0x1800048c6  pop     r12
0x1800048c8  pop     rdi
0x1800048c9  pop     rsi
0x1800048ca  pop     rbx
0x1800048cb  pop     rbp
0x1800048cc  retn
0x1800048cd  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800048d2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800048d8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
