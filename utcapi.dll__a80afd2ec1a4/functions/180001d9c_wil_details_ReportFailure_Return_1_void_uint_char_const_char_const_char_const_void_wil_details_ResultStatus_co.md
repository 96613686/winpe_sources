# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180001d9c`
- end: `0x180002051`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180001d44`

## callees

- `0x180001400`
- `0x180001ca2`
- `0x180001d9c`
- `0x180002058`
- `0x180002570`
- `0x180002654`
- `0x180002730`
- `0x180002fe0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001e53`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001fe4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180001fe4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001f54`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180001f54`

## string_xrefs

- `0x180001e63`: `onecore\base\telemetry\utc\service\api\client\current_dll\utcrpcapiwrapperexport.cpp`

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
  v25 = "onecore\\base\\telemetry\\utc\\service\\api\\client\\current_dll\\utcrpcapiwrapperexport.cpp";
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x180001d9c  push    rbp
0x180001d9e  push    rsi
0x180001d9f  push    rdi
0x180001da0  push    r14
0x180001da2  push    r15
0x180001da4  lea     rbp, [rsp-13E0h]
0x180001dac  mov     eax, 14E0h
0x180001db1  call    _alloca_probe
0x180001db6  sub     rsp, rax
0x180001db9  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x180001dc1  mov     [rsp+1500h+arg_10], rbx
0x180001dc9  mov     rax, cs:__security_cookie
0x180001dd0  xor     rax, rsp
0x180001dd3  mov     [rbp+1400h+var_30], rax
0x180001dda  mov     esi, edx
0x180001ddc  mov     r14, rcx
0x180001ddf  mov     rdi, [rbp+1400h+arg_28]
0x180001de6  xor     edx, edx; Val
0x180001de8  mov     r8d, 98h; Size
0x180001dee  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180001df3  call    memset_0
0x180001df8  nop
0x180001df9  xor     r15d, r15d
0x180001dfc  mov     [rbp+1400h+OutputString], r15w
0x180001e04  mov     [rbp+1400h+var_1430], r15b
0x180001e08  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180001e0f  mov     ecx, [rdx]; this
0x180001e11  mov     [rsp+1500h+var_14D8], ecx
0x180001e15  mov     eax, [rdx+4]
0x180001e18  mov     [rsp+1500h+var_14D4], eax
0x180001e1c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180001e21  mov     ebx, eax
0x180001e23  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180001e2b  mov     ecx, r15d
0x180001e2e  lea     eax, [r15+8]
0x180001e32  cmp     dword ptr [rdx+8], 1
0x180001e36  cmovz   ecx, eax
0x180001e39  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180001e3d  lea     ecx, [rax-7]
0x180001e40  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180001e48  inc     ecx
0x180001e4a  mov     [rsp+1500h+var_14D0], ecx
0x180001e4e  mov     [rsp+1500h+var_14C8], r15
0x180001e53  call    cs:__imp_GetCurrentThreadId
0x180001e5a  nop     dword ptr [rax+rax+00h]
0x180001e5f  mov     [rsp+1500h+var_14C0], eax
0x180001e63  lea     rax, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\service"...
0x180001e6a  mov     [rsp+1500h+var_14A8], rax
0x180001e6f  mov     [rsp+1500h+var_14A0], esi
0x180001e73  mov     [rsp+1500h+var_149C], ebx
0x180001e77  mov     [rsp+1500h+var_14B8], r15
0x180001e7c  mov     [rsp+1500h+var_14B0], r15
0x180001e81  mov     [rbp+1400h+var_1458], rdi
0x180001e85  mov     [rbp+1400h+var_1450], r14
0x180001e89  mov     [rsp+1500h+var_1498], r15
0x180001e8e  xorps   xmm0, xmm0
0x180001e91  xor     eax, eax
0x180001e93  movups  [rbp+1400h+var_1478], xmm0
0x180001e97  mov     [rbp+1400h+var_1468], rax
0x180001e9b  xorps   xmm1, xmm1
0x180001e9e  movups  [rsp+1500h+var_1490], xmm1
0x180001ea3  mov     [rbp+1400h+var_1480], rax
0x180001ea7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180001eae  test    rax, rax
0x180001eb1  jz      short loc_180001EBE
0x180001eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eb8  mov     [rbp+1400h+var_1460], rax
0x180001ebc  jmp     short loc_180001EC2
0x180001ebe  mov     [rbp+1400h+var_1460], r15
0x180001ec2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180001ec9  test    rax, rax
0x180001ecc  jz      short loc_180001ED8
0x180001ece  lea     rcx, [rsp+1500h+var_14E0]
0x180001ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ed8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180001edf  test    rax, rax
0x180001ee2  jz      short loc_180001EF8
0x180001ee4  mov     r8d, 400h
0x180001eea  lea     rdx, [rbp+1400h+var_1430]
0x180001eee  lea     rcx, [rsp+1500h+var_14E0]
0x180001ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001eff  test    rax, rax
0x180001f02  jz      short loc_180001F0E
0x180001f04  lea     rcx, [rsp+1500h+var_14E0]
0x180001f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f0e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180001f15  test    rax, rax
0x180001f18  jz      short loc_180001F2B
0x180001f1a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180001f1f  jnz     short loc_180001F2B
0x180001f21  lea     rcx, [rsp+1500h+var_14E0]
0x180001f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f2b  cmp     [rsp+1500h+var_14D8], r15d
0x180001f30  jge     loc_18000204B
0x180001f36  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180001f3d  jnz     short loc_180001F64
0x180001f3f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180001f46  test    rax, rax
0x180001f49  jz      short loc_180001F54
0x180001f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f50  test    al, al
0x180001f52  jmp     short loc_180001F62
0x180001f54  call    cs:__imp_IsDebuggerPresent
0x180001f5b  nop     dword ptr [rax+rax+00h]
0x180001f60  test    eax, eax
0x180001f62  jz      short loc_180001F6B
0x180001f64  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180001f69  jz      short loc_180001F91
0x180001f6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f72  test    rax, rax
0x180001f75  jz      short loc_180001FF0
0x180001f77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180001f7e  jnz     short loc_180001FF0
0x180001f80  xor     r8d, r8d
0x180001f83  xor     edx, edx
0x180001f85  lea     rcx, [rsp+1500h+var_14E0]
0x180001f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f8f  jmp     short loc_180001FF0
0x180001f91  mov     ebx, 800h
0x180001f96  mov     rax, cs:g_pfnResultLoggingCallback
0x180001f9d  test    rax, rax
0x180001fa0  jz      short loc_180001FBF
0x180001fa2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180001fa9  jnz     short loc_180001FBF
0x180001fab  mov     r8d, ebx
0x180001fae  lea     rdx, [rbp+1400h+OutputString]
0x180001fb5  lea     rcx, [rsp+1500h+var_14E0]
0x180001fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fbf  cmp     [rbp+1400h+OutputString], r15w
0x180001fc7  jnz     short loc_180001FDD
0x180001fc9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180001fce  mov     rdx, rbx; wchar_t *
0x180001fd1  lea     rcx, [rbp+1400h+OutputString]; this
0x180001fd8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180001fdd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180001fe4  call    cs:__imp_OutputDebugStringW
0x180001feb  nop     dword ptr [rax+rax+00h]
0x180001ff0  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180001ff5  jnz     short loc_180002000
0x180001ff7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180001ffe  jz      short loc_180002012
0x180002000  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002007  test    rax, rax
0x18000200a  jz      short loc_180002012
0x18000200c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002011  nop
0x180002012  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002017  jnz     short loc_180002040
0x180002019  mov     rcx, [rbp+1400h+var_30]
0x180002020  xor     rcx, rsp; StackCookie
0x180002023  call    __security_check_cookie
0x180002028  mov     rbx, [rsp+1500h+arg_10]
0x180002030  add     rsp, 14E0h
0x180002037  pop     r15
0x180002039  pop     r14
0x18000203b  pop     rdi
0x18000203c  pop     rsi
0x18000203d  pop     rbp
0x18000203e  retn
0x180002040  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002045  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000204b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
