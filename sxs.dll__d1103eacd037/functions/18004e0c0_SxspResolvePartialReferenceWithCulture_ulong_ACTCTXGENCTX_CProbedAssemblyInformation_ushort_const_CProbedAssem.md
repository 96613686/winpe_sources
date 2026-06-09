# SxspResolvePartialReferenceWithCulture(ulong,_ACTCTXGENCTX *,CProbedAssemblyInformation &,ushort const *,CProbedAssemblyInformation::LanguageProbeType,ulong,bool &)

- ea: `0x18004e0c0`
- end: `0x18004e35a`
- name: `?SxspResolvePartialReferenceWithCulture@@YAHKPEAU_ACTCTXGENCTX@@AEAVCProbedAssemblyInformation@@PEBGW4LanguageProbeType@2@KAEA_N@Z`
- size: `666`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180017dc0`

## callees

- `0x18000cd10`
- `0x18000df40`
- `0x18000dffc`
- `0x18004e0c0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18004e200`
- `ntdll!EtwEventWrite` at `0x18004e2c5`
- `ntdll!EtwEventWrite` at `0x18004e200`
- `ntdll!EtwEventWrite` at `0x18004e2c5`
- `ntdll!RtlPopFrame` at `0x18004e2df`
- `ntdll!RtlPopFrame` at `0x18004e2df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e343`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e20e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e20e`

## pseudocode

```c
__int64 __fastcall SxspResolvePartialReferenceWithCulture(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        _BYTE *a7)
{
  bool v11; // zf
  int v12; // edi
  __int64 v13; // r8
  __int64 v14; // rax
  unsigned int v15; // ebx
  DWORD LastError; // eax
  int v18; // [rsp+30h] [rbp-A1h] BYREF
  int v19; // [rsp+38h] [rbp-99h] BYREF
  int v20; // [rsp+40h] [rbp-91h] BYREF
  int v21; // [rsp+44h] [rbp-8Dh]
  __int64 v22; // [rsp+48h] [rbp-89h]
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+50h] [rbp-81h] BYREF
  __int64 v24; // [rsp+68h] [rbp-69h]
  int v25; // [rsp+70h] [rbp-61h]
  int *v26; // [rsp+78h] [rbp-59h]
  int *v27; // [rsp+80h] [rbp-51h] BYREF
  __int64 v28; // [rsp+88h] [rbp-49h]
  __int64 v29; // [rsp+90h] [rbp-41h]
  int v30; // [rsp+98h] [rbp-39h]
  int v31; // [rsp+9Ch] [rbp-35h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006CEA0;
  Frame.Flags = 1;
  v26 = &v18;
  v18 = 0;
  Frame.Previous = 0;
  v24 = 544438355;
  v25 = 792;
  CFrame::BaseEnter((CFrame *)&Frame);
  v11 = g_TraceEnabled == 0;
  *a7 = 0;
  v12 = *(_DWORD *)(a2 + 1304);
  v19 = v12;
  if ( !v11
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    v20 = 202;
    v27 = &v19;
    v13 = 1;
    v21 = 6750212;
    v22 = 256;
    v28 = 4;
    if ( a4 )
    {
      v29 = a4;
      v14 = -1;
      do
        v11 = *(_WORD *)(a4 + 2 * v14++ + 2) == 0;
      while ( !v11 );
      v31 = 0;
      v30 = 2 * v14 + 2;
      v13 = 2;
    }
    EtwEventWrite(g_hTraceHandle, &v20, v13, &v27);
  }
  SetLastError(0);
  if ( (unsigned int)CProbedAssemblyInformation::ProbeAssembly(a3, a1, a2, a5, a6, a7) )
  {
    v15 = 1;
    v18 = 1;
  }
  else
  {
    *v26 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180077C60);
    v15 = v18;
  }
  v19 = v12;
  if ( g_TraceEnabled
    && (unsigned __int8)(g_TraceLevel - 1) > 2u
    && (g_OrKeywordMask & 0x100) != 0
    && (g_AndKeywordMask & 0x100) == g_AndKeywordMask )
  {
    v27 = &v19;
    v20 = 203;
    v21 = 6750212;
    v22 = 256;
    v28 = 4;
    EtwEventWrite(g_hTraceHandle, &v20, 1, &v27);
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v26 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v15;
}

```

## disassembly

```asm
0x18004e0c0  mov     [rsp-8+arg_0], rbx
0x18004e0c5  push    rbp
0x18004e0c6  push    rsi
0x18004e0c7  push    rdi
0x18004e0c8  push    r12
0x18004e0ca  push    r13
0x18004e0cc  push    r14
0x18004e0ce  push    r15
0x18004e0d0  lea     rbp, [rsp-0Fh]
0x18004e0d5  sub     rsp, 0E0h
0x18004e0dc  mov     rax, cs:__security_cookie
0x18004e0e3  xor     rax, rsp
0x18004e0e6  mov     [rbp+3Fh+var_40], rax
0x18004e0ea  mov     r14, [rbp+3Fh+arg_30]
0x18004e0ee  lea     rax, qword_18006CEA0
0x18004e0f5  mov     [rbp+3Fh+Frame.Context], rax
0x18004e0f9  mov     r15d, ecx
0x18004e0fc  lea     rax, [rsp+110h+var_E0]
0x18004e101  mov     [rsp+110h+Frame.Flags], 1
0x18004e109  xor     r13d, r13d
0x18004e10c  mov     [rbp+3Fh+var_98], rax
0x18004e110  lea     rcx, [rsp+110h+Frame]; this
0x18004e115  mov     [rsp+110h+var_E0], r13d
0x18004e11a  mov     rbx, r9
0x18004e11d  mov     [rbp+3Fh+Frame.Previous], r13
0x18004e121  mov     r12, r8
0x18004e124  mov     [rbp+3Fh+var_A8], 20737853h
0x18004e12c  mov     rsi, rdx
0x18004e12f  mov     [rbp+3Fh+var_A0], 318h
0x18004e136  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18004e13b  cmp     cs:?g_TraceEnabled@@3KA, r13d; ulong g_TraceEnabled
0x18004e142  mov     [r14], r13b
0x18004e145  mov     edi, [rsi+518h]
0x18004e14b  mov     [rsp+110h+var_D8], edi
0x18004e14f  jz      loc_18004E20C
0x18004e155  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18004e15c  dec     al
0x18004e15e  cmp     al, 2
0x18004e160  jbe     loc_18004E20C
0x18004e166  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18004e171  jz      loc_18004E20C
0x18004e177  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18004e17e  and     eax, 100h
0x18004e183  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18004e18a  jnz     loc_18004E20C
0x18004e190  mov     [rsp+110h+var_D0], 0CAh
0x18004e198  lea     rax, [rsp+110h+var_D8]
0x18004e19d  mov     [rbp+3Fh+var_90], rax
0x18004e1a1  mov     r8d, 1
0x18004e1a7  mov     [rsp+110h+var_CC], 670004h
0x18004e1af  mov     [rsp+110h+var_C8], 100h
0x18004e1b8  mov     [rbp+3Fh+var_88], 4
0x18004e1c0  test    rbx, rbx
0x18004e1c3  jz      short loc_18004E1F0
0x18004e1c5  mov     [rbp+3Fh+var_80], rbx
0x18004e1c9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004e1d0  cmp     [rbx+rax*2+2], r13w
0x18004e1d6  lea     rax, [rax+1]
0x18004e1da  jnz     short loc_18004E1D0
0x18004e1dc  lea     eax, ds:2[rax*2]
0x18004e1e3  mov     [rbp+3Fh+var_74], r13d
0x18004e1e7  mov     [rbp+3Fh+var_78], eax
0x18004e1ea  mov     r8d, 2
0x18004e1f0  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18004e1f7  lea     r9, [rbp+3Fh+var_90]
0x18004e1fb  lea     rdx, [rsp+110h+var_D0]
0x18004e200  call    cs:__imp_EtwEventWrite
0x18004e207  nop     dword ptr [rax+rax+00h]
0x18004e20c  xor     ecx, ecx; dwErrCode
0x18004e20e  call    cs:__imp_SetLastError
0x18004e215  nop     dword ptr [rax+rax+00h]
0x18004e21a  mov     eax, [rbp+3Fh+arg_28]
0x18004e21d  mov     r8, rsi
0x18004e220  mov     r9d, [rbp+3Fh+arg_20]
0x18004e224  mov     edx, r15d
0x18004e227  mov     rcx, r12
0x18004e22a  mov     [rsp+110h+var_E8], r14
0x18004e22f  mov     [rsp+110h+var_F0], eax
0x18004e233  call    ?ProbeAssembly@CProbedAssemblyInformation@@QEAAHKPEAU_ACTCTXGENCTX@@W4LanguageProbeType@1@KAEA_N@Z; CProbedAssemblyInformation::ProbeAssembly(ulong,_ACTCTXGENCTX *,CProbedAssemblyInformation::LanguageProbeType,ulong,bool &)
0x18004e238  test    eax, eax
0x18004e23a  jz      loc_18004E315
0x18004e240  mov     ebx, 1
0x18004e245  mov     [rsp+110h+var_E0], ebx
0x18004e249  cmp     cs:?g_TraceEnabled@@3KA, r13d; ulong g_TraceEnabled
0x18004e250  mov     [rsp+110h+var_D8], edi
0x18004e254  jz      short loc_18004E2D1
0x18004e256  movzx   eax, cs:?g_TraceLevel@@3EA; uchar g_TraceLevel
0x18004e25d  dec     al
0x18004e25f  cmp     al, 2
0x18004e261  jbe     short loc_18004E2D1
0x18004e263  test    cs:?g_OrKeywordMask@@3_KA, 100h; unsigned __int64 g_OrKeywordMask
0x18004e26e  jz      short loc_18004E2D1
0x18004e270  mov     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18004e277  and     eax, 100h
0x18004e27c  cmp     rax, cs:?g_AndKeywordMask@@3_KA; unsigned __int64 g_AndKeywordMask
0x18004e283  jnz     short loc_18004E2D1
0x18004e285  mov     rcx, cs:?g_hTraceHandle@@3_KA; unsigned __int64 g_hTraceHandle
0x18004e28c  lea     rax, [rsp+110h+var_D8]
0x18004e291  lea     r9, [rbp+3Fh+var_90]
0x18004e295  mov     [rbp+3Fh+var_90], rax
0x18004e299  mov     r8d, 1
0x18004e29f  mov     [rsp+110h+var_D0], 0CBh
0x18004e2a7  lea     rdx, [rsp+110h+var_D0]
0x18004e2ac  mov     [rsp+110h+var_CC], 670004h
0x18004e2b4  mov     [rsp+110h+var_C8], 100h
0x18004e2bd  mov     [rbp+3Fh+var_88], 4
0x18004e2c5  call    cs:__imp_EtwEventWrite
0x18004e2cc  nop     dword ptr [rax+rax+00h]
0x18004e2d1  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x18004e2d8  jnz     short loc_18004E331
0x18004e2da  lea     rcx, [rsp+110h+Frame]; Frame
0x18004e2df  call    cs:__imp_RtlPopFrame
0x18004e2e6  nop     dword ptr [rax+rax+00h]
0x18004e2eb  mov     eax, ebx
0x18004e2ed  mov     rcx, [rbp+3Fh+var_40]
0x18004e2f1  xor     rcx, rsp; StackCookie
0x18004e2f4  call    __security_check_cookie
0x18004e2f9  mov     rbx, [rsp+110h+arg_0]
0x18004e301  add     rsp, 0E0h
0x18004e308  pop     r15
0x18004e30a  pop     r14
0x18004e30c  pop     r13
0x18004e30e  pop     r12
0x18004e310  pop     rdi
0x18004e311  pop     rsi
0x18004e312  pop     rbp
0x18004e313  retn
0x18004e315  mov     rax, [rbp+3Fh+var_98]
0x18004e319  lea     rcx, off_180077C60; struct _CALL_SITE_INFO *
0x18004e320  mov     [rax], r13d
0x18004e323  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004e328  mov     ebx, [rsp+110h+var_E0]
0x18004e32c  jmp     loc_18004E249
0x18004e331  mov     rax, [rbp+3Fh+var_98]
0x18004e335  cmp     [rax], r13d
0x18004e338  jz      short loc_18004E343
0x18004e33a  xor     ecx, ecx; char *
0x18004e33c  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18004e341  jmp     short loc_18004E2DA
0x18004e343  call    cs:__imp_GetLastError
0x18004e34a  nop     dword ptr [rax+rax+00h]
0x18004e34f  mov     ecx, eax; unsigned int
0x18004e351  xor     edx, edx; Format
0x18004e353  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18004e358  jmp     short loc_18004E2DA
```
