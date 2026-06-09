# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180021efc`
- end: `0x1800221b1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800219b4`

## callees

- `0x180021efc`
- `0x180025564`
- `0x180027084`
- `0x1800282a8`
- `0x180028814`
- `0x1800319ae`
- `0x1800319f0`
- `0x180031ab0`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180021fb3`
- `KERNEL32!GetCurrentThreadId` at `0x180021fb3`
- `KERNEL32!OutputDebugStringW` at `0x180022144`
- `KERNEL32!OutputDebugStringW` at `0x180022144`
- `KERNEL32!IsDebuggerPresent` at `0x1800220b4`
- `KERNEL32!IsDebuggerPresent` at `0x1800220b4`

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
0x180021efc  push    rbp
0x180021efe  push    rsi
0x180021eff  push    rdi
0x180021f00  push    r14
0x180021f02  push    r15
0x180021f04  lea     rbp, [rsp-13E0h]
0x180021f0c  mov     eax, 14E0h
0x180021f11  call    _alloca_probe
0x180021f16  sub     rsp, rax
0x180021f19  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x180021f21  mov     [rsp+1500h+arg_10], rbx
0x180021f29  mov     rax, cs:__security_cookie
0x180021f30  xor     rax, rsp
0x180021f33  mov     [rbp+1400h+var_30], rax
0x180021f3a  mov     esi, edx
0x180021f3c  mov     r14, rcx
0x180021f3f  mov     rdi, [rbp+1400h+arg_28]
0x180021f46  xor     edx, edx; Val
0x180021f48  mov     r8d, 98h; Size
0x180021f4e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180021f53  call    memset_0
0x180021f58  nop
0x180021f59  xor     r15d, r15d
0x180021f5c  mov     [rbp+1400h+OutputString], r15w
0x180021f64  mov     [rbp+1400h+var_1430], r15b
0x180021f68  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180021f6f  mov     ecx, [rdx]; this
0x180021f71  mov     [rsp+1500h+var_14D8], ecx
0x180021f75  mov     eax, [rdx+4]
0x180021f78  mov     [rsp+1500h+var_14D4], eax
0x180021f7c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180021f81  mov     ebx, eax
0x180021f83  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180021f8b  mov     ecx, r15d
0x180021f8e  lea     eax, [r15+8]
0x180021f92  cmp     dword ptr [rdx+8], 1
0x180021f96  cmovz   ecx, eax
0x180021f99  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180021f9d  lea     ecx, [rax-7]
0x180021fa0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180021fa8  inc     ecx
0x180021faa  mov     [rsp+1500h+var_14D0], ecx
0x180021fae  mov     [rsp+1500h+var_14C8], r15
0x180021fb3  call    cs:__imp_GetCurrentThreadId
0x180021fba  nop     dword ptr [rax+rax+00h]
0x180021fbf  mov     [rsp+1500h+var_14C0], eax
0x180021fc3  lea     rax, aWil; "wil"
0x180021fca  mov     [rsp+1500h+var_14A8], rax
0x180021fcf  mov     [rsp+1500h+var_14A0], esi
0x180021fd3  mov     [rsp+1500h+var_149C], ebx
0x180021fd7  mov     [rsp+1500h+var_14B8], r15
0x180021fdc  mov     [rsp+1500h+var_14B0], r15
0x180021fe1  mov     [rbp+1400h+var_1458], rdi
0x180021fe5  mov     [rbp+1400h+var_1450], r14
0x180021fe9  mov     [rsp+1500h+var_1498], r15
0x180021fee  xorps   xmm0, xmm0
0x180021ff1  xor     eax, eax
0x180021ff3  movups  [rbp+1400h+var_1478], xmm0
0x180021ff7  mov     [rbp+1400h+var_1468], rax
0x180021ffb  xorps   xmm1, xmm1
0x180021ffe  movups  [rsp+1500h+var_1490], xmm1
0x180022003  mov     [rbp+1400h+var_1480], rax
0x180022007  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002200e  test    rax, rax
0x180022011  jz      short loc_18002201E
0x180022013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022018  mov     [rbp+1400h+var_1460], rax
0x18002201c  jmp     short loc_180022022
0x18002201e  mov     [rbp+1400h+var_1460], r15
0x180022022  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180022029  test    rax, rax
0x18002202c  jz      short loc_180022038
0x18002202e  lea     rcx, [rsp+1500h+var_14E0]
0x180022033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022038  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002203f  test    rax, rax
0x180022042  jz      short loc_180022058
0x180022044  mov     r8d, 400h
0x18002204a  lea     rdx, [rbp+1400h+var_1430]
0x18002204e  lea     rcx, [rsp+1500h+var_14E0]
0x180022053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022058  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002205f  test    rax, rax
0x180022062  jz      short loc_18002206E
0x180022064  lea     rcx, [rsp+1500h+var_14E0]
0x180022069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002206e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022075  test    rax, rax
0x180022078  jz      short loc_18002208B
0x18002207a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18002207f  jnz     short loc_18002208B
0x180022081  lea     rcx, [rsp+1500h+var_14E0]
0x180022086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002208b  cmp     [rsp+1500h+var_14D8], r15d
0x180022090  jge     loc_1800221AB
0x180022096  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18002209d  jnz     short loc_1800220C4
0x18002209f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800220a6  test    rax, rax
0x1800220a9  jz      short loc_1800220B4
0x1800220ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b0  test    al, al
0x1800220b2  jmp     short loc_1800220C2
0x1800220b4  call    cs:__imp_IsDebuggerPresent
0x1800220bb  nop     dword ptr [rax+rax+00h]
0x1800220c0  test    eax, eax
0x1800220c2  jz      short loc_1800220CB
0x1800220c4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800220c9  jz      short loc_1800220F1
0x1800220cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800220d2  test    rax, rax
0x1800220d5  jz      short loc_180022150
0x1800220d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800220de  jnz     short loc_180022150
0x1800220e0  xor     r8d, r8d
0x1800220e3  xor     edx, edx
0x1800220e5  lea     rcx, [rsp+1500h+var_14E0]
0x1800220ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ef  jmp     short loc_180022150
0x1800220f1  mov     ebx, 800h
0x1800220f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800220fd  test    rax, rax
0x180022100  jz      short loc_18002211F
0x180022102  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180022109  jnz     short loc_18002211F
0x18002210b  mov     r8d, ebx
0x18002210e  lea     rdx, [rbp+1400h+OutputString]
0x180022115  lea     rcx, [rsp+1500h+var_14E0]
0x18002211a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002211f  cmp     [rbp+1400h+OutputString], r15w
0x180022127  jnz     short loc_18002213D
0x180022129  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18002212e  mov     rdx, rbx; unsigned __int16 *
0x180022131  lea     rcx, [rbp+1400h+OutputString]; this
0x180022138  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002213d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180022144  call    cs:__imp_OutputDebugStringW
0x18002214b  nop     dword ptr [rax+rax+00h]
0x180022150  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180022155  jnz     short loc_180022160
0x180022157  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18002215e  jz      short loc_180022172
0x180022160  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180022167  test    rax, rax
0x18002216a  jz      short loc_180022172
0x18002216c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022171  nop
0x180022172  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180022177  jnz     short loc_1800221A0
0x180022179  mov     rcx, [rbp+1400h+var_30]
0x180022180  xor     rcx, rsp; StackCookie
0x180022183  call    __security_check_cookie
0x180022188  mov     rbx, [rsp+1500h+arg_10]
0x180022190  add     rsp, 14E0h
0x180022197  pop     r15
0x180022199  pop     r14
0x18002219b  pop     rdi
0x18002219c  pop     rsi
0x18002219d  pop     rbp
0x18002219e  retn
0x1800221a0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800221a5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800221ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
