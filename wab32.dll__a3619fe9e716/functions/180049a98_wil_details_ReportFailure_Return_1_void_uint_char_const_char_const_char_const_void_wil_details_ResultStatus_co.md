# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180049a98`
- end: `0x180049d2c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180049760`

## callees

- `0x180049a98`
- `0x18004e688`
- `0x18005129c`
- `0x180054cb8`
- `0x180054ec8`
- `0x180091eaa`
- `0x180091ef0`
- `0x180091f80`
- `0x180093010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180049cc7`
- `KERNEL32!OutputDebugStringW` at `0x180049cc7`
- `KERNEL32!IsDebuggerPresent` at `0x180049c3d`
- `KERNEL32!IsDebuggerPresent` at `0x180049c3d`
- `KERNEL32!GetCurrentThreadId` at `0x180049b42`
- `KERNEL32!GetCurrentThreadId` at `0x180049b42`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180049a98  mov     [rsp-8+arg_10], rbx
0x180049a9d  push    rbp
0x180049a9e  push    rsi
0x180049a9f  push    rdi
0x180049aa0  push    r14
0x180049aa2  push    r15
0x180049aa4  lea     rbp, [rsp-13D0h]
0x180049aac  mov     eax, 14D0h
0x180049ab1  call    _alloca_probe
0x180049ab6  sub     rsp, rax
0x180049ab9  mov     rax, cs:__security_cookie
0x180049ac0  xor     rax, rsp
0x180049ac3  mov     [rbp+13F0h+var_30], rax
0x180049aca  mov     rdi, [rbp+13F0h+arg_28]
0x180049ad1  mov     esi, edx
0x180049ad3  mov     r14, rcx
0x180049ad6  xor     edx, edx; Val
0x180049ad8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180049add  mov     r8d, 98h; Size
0x180049ae3  call    memset_0
0x180049ae8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180049aef  xor     r15d, r15d
0x180049af2  mov     [rbp+13F0h+OutputString], r15w
0x180049afa  mov     [rbp+13F0h+var_1430], r15b
0x180049afe  mov     ecx, [rdx]; this
0x180049b00  mov     eax, [rdx+4]
0x180049b03  mov     [rsp+14F0h+var_14C8], ecx
0x180049b07  mov     [rsp+14F0h+var_14C4], eax
0x180049b0b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180049b10  cmp     dword ptr [rdx+8], 1
0x180049b14  mov     ebx, eax
0x180049b16  lea     eax, [r15+8]
0x180049b1a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180049b22  mov     ecx, r15d
0x180049b25  cmovz   ecx, eax
0x180049b28  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180049b2c  lea     ecx, [rax-7]
0x180049b2f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180049b37  inc     ecx
0x180049b39  mov     [rsp+14F0h+var_14B8], r15
0x180049b3e  mov     [rsp+14F0h+var_14C0], ecx
0x180049b42  call    cs:__imp_GetCurrentThreadId
0x180049b48  xorps   xmm0, xmm0
0x180049b4b  mov     [rsp+14F0h+var_1490], esi
0x180049b4f  mov     [rsp+14F0h+var_14B0], eax
0x180049b53  xorps   xmm1, xmm1
0x180049b56  lea     rax, aWil; "wil"
0x180049b5d  mov     [rsp+14F0h+var_148C], ebx
0x180049b61  mov     [rsp+14F0h+var_1498], rax
0x180049b66  xor     eax, eax
0x180049b68  mov     [rbp+13F0h+var_1458], rax
0x180049b6c  mov     [rbp+13F0h+var_1470], rax
0x180049b70  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180049b77  mov     [rsp+14F0h+var_14A8], r15
0x180049b7c  mov     [rsp+14F0h+var_14A0], r15
0x180049b81  mov     [rbp+13F0h+var_1448], rdi
0x180049b85  mov     [rbp+13F0h+var_1440], r14
0x180049b89  mov     [rsp+14F0h+var_1488], r15
0x180049b8e  movups  [rbp+13F0h+var_1468], xmm0
0x180049b92  movups  [rsp+14F0h+var_1480], xmm1
0x180049b97  test    rax, rax
0x180049b9a  jz      short loc_180049BA7
0x180049b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ba1  mov     [rbp+13F0h+var_1450], rax
0x180049ba5  jmp     short loc_180049BAB
0x180049ba7  mov     [rbp+13F0h+var_1450], r15
0x180049bab  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180049bb2  test    rax, rax
0x180049bb5  jz      short loc_180049BC1
0x180049bb7  lea     rcx, [rsp+14F0h+var_14D0]
0x180049bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bc1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180049bc8  test    rax, rax
0x180049bcb  jz      short loc_180049BE1
0x180049bcd  mov     r8d, 400h
0x180049bd3  lea     rdx, [rbp+13F0h+var_1430]
0x180049bd7  lea     rcx, [rsp+14F0h+var_14D0]
0x180049bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049be1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180049be8  test    rax, rax
0x180049beb  jz      short loc_180049BF7
0x180049bed  lea     rcx, [rsp+14F0h+var_14D0]
0x180049bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bf7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180049bfe  test    rax, rax
0x180049c01  jz      short loc_180049C14
0x180049c03  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180049c08  jnz     short loc_180049C14
0x180049c0a  lea     rcx, [rsp+14F0h+var_14D0]
0x180049c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c14  cmp     [rsp+14F0h+var_14C8], r15d
0x180049c19  jge     loc_180049D1B
0x180049c1f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180049c26  jnz     short loc_180049C47
0x180049c28  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180049c2f  test    rax, rax
0x180049c32  jz      short loc_180049C3D
0x180049c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c39  test    al, al
0x180049c3b  jmp     short loc_180049C45
0x180049c3d  call    cs:__imp_IsDebuggerPresent
0x180049c43  test    eax, eax
0x180049c45  jz      short loc_180049C4E
0x180049c47  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180049c4c  jz      short loc_180049C74
0x180049c4e  mov     rax, cs:g_pfnResultLoggingCallback
0x180049c55  test    rax, rax
0x180049c58  jz      short loc_180049CCD
0x180049c5a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180049c61  jnz     short loc_180049CCD
0x180049c63  xor     r8d, r8d
0x180049c66  lea     rcx, [rsp+14F0h+var_14D0]
0x180049c6b  xor     edx, edx
0x180049c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c72  jmp     short loc_180049CCD
0x180049c74  mov     rax, cs:g_pfnResultLoggingCallback
0x180049c7b  mov     ebx, 800h
0x180049c80  test    rax, rax
0x180049c83  jz      short loc_180049CA2
0x180049c85  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180049c8c  jnz     short loc_180049CA2
0x180049c8e  mov     r8d, ebx
0x180049c91  lea     rdx, [rbp+13F0h+OutputString]
0x180049c98  lea     rcx, [rsp+14F0h+var_14D0]
0x180049c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ca2  cmp     [rbp+13F0h+OutputString], r15w
0x180049caa  jnz     short loc_180049CC0
0x180049cac  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180049cb1  mov     rdx, rbx; unsigned __int16 *
0x180049cb4  lea     rcx, [rbp+13F0h+OutputString]; this
0x180049cbb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180049cc0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180049cc7  call    cs:__imp_OutputDebugStringW
0x180049ccd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180049cd2  jnz     short loc_180049CDD
0x180049cd4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180049cdb  jz      short loc_180049CEE
0x180049cdd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180049ce4  test    rax, rax
0x180049ce7  jz      short loc_180049CEE
0x180049ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cee  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180049cf3  jnz     short loc_180049D21
0x180049cf5  mov     rcx, [rbp+13F0h+var_30]
0x180049cfc  xor     rcx, rsp; StackCookie
0x180049cff  call    __security_check_cookie
0x180049d04  mov     rbx, [rsp+14F0h+arg_10]
0x180049d0c  add     rsp, 14D0h
0x180049d13  pop     r15
0x180049d15  pop     r14
0x180049d17  pop     rdi
0x180049d18  pop     rsi
0x180049d19  pop     rbp
0x180049d1a  retn
0x180049d1b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180049d21  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180049d26  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
