# CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::InitializeKey(CCountedStringHolder<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> &)

- ea: `0x1800293fc`
- end: `0x180029501`
- name: `?InitializeKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180020904`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x1800293fc`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180029492`
- `ntdll!RtlPopFrame` at `0x180029492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800294ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029463`

## pseudocode

```c
__int64 __fastcall CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::InitializeKey(
        __int64 a1,
        __int64 a2)
{
  unsigned int v3; // esi
  DWORD LastError; // eax
  int v7; // [rsp+20h] [rbp-40h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-38h] BYREF
  __int64 v9; // [rsp+40h] [rbp-20h]
  int v10; // [rsp+48h] [rbp-18h]
  int *v11; // [rsp+50h] [rbp-10h]

  v7 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::InitializeKey'::`2'::__stc;
  Frame.Previous = 0;
  v3 = 1;
  v11 = &v7;
  Frame.Flags = 1;
  v9 = 544438355;
  v10 = 1288;
  CFrame::BaseEnter((CFrame *)&Frame);
  SetLastError(0);
  if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(
                       a2,
                       *(const void **)a1,
                       *(_QWORD *)(a1 + 8)) )
  {
    v7 = 1;
  }
  else
  {
    *v11 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::InitializeKey'::`15'::__callsite);
    v3 = v7;
  }
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v11 )
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
  return v3;
}

```

## disassembly

```asm
0x1800293fc  mov     [rsp-18h+arg_10], rbx
0x180029401  push    rbp
0x180029402  push    rsi
0x180029403  push    rdi
0x180029404  mov     rbp, rsp
0x180029407  sub     rsp, 60h
0x18002940b  mov     rax, cs:__security_cookie
0x180029412  xor     rax, rsp
0x180029415  mov     [rbp+var_8], rax
0x180029419  lea     rax, ?__stc@?1??InitializeKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::InitializeKey(CCountedStringHolder<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> &)'::`2'::__stc
0x180029420  mov     [rbp+var_40], 0
0x180029427  mov     [rbp+Frame.Context], rax
0x18002942b  mov     rbx, rcx
0x18002942e  lea     rax, [rbp+var_40]
0x180029432  mov     [rbp+Frame.Previous], 0
0x18002943a  mov     esi, 1
0x18002943f  mov     [rbp+var_10], rax
0x180029443  lea     rcx, [rbp+Frame]; this
0x180029447  mov     [rbp+Frame.Flags], esi
0x18002944a  mov     rdi, rdx
0x18002944d  mov     [rbp+var_20], 20737853h
0x180029455  mov     [rbp+var_18], 508h
0x18002945c  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180029461  xor     ecx, ecx; dwErrCode
0x180029463  call    cs:__imp_SetLastError
0x18002946a  nop     dword ptr [rax+rax+00h]
0x18002946f  mov     r8, [rbx+8]
0x180029473  mov     rcx, rdi
0x180029476  mov     rdx, [rbx]
0x180029479  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002947e  test    eax, eax
0x180029480  jz      short loc_1800294BD
0x180029482  mov     [rbp+var_40], esi
0x180029485  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18002948c  jnz     short loc_1800294D8
0x18002948e  lea     rcx, [rbp+Frame]; Frame
0x180029492  call    cs:__imp_RtlPopFrame
0x180029499  nop     dword ptr [rax+rax+00h]
0x18002949e  mov     eax, esi
0x1800294a0  mov     rcx, [rbp+var_8]
0x1800294a4  xor     rcx, rsp; StackCookie
0x1800294a7  call    __security_check_cookie
0x1800294ac  mov     rbx, [rsp+60h+arg_10]
0x1800294b4  add     rsp, 60h
0x1800294b8  pop     rdi
0x1800294b9  pop     rsi
0x1800294ba  pop     rbp
0x1800294bb  retn
0x1800294bd  mov     rax, [rbp+var_10]
0x1800294c1  lea     rcx, ?__callsite@?P@??InitializeKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x1800294c8  mov     dword ptr [rax], 0
0x1800294ce  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800294d3  mov     esi, [rbp+var_40]
0x1800294d6  jmp     short loc_180029485
0x1800294d8  mov     rax, [rbp+var_10]
0x1800294dc  cmp     dword ptr [rax], 0
0x1800294df  jz      short loc_1800294EA
0x1800294e1  xor     ecx, ecx; char *
0x1800294e3  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800294e8  jmp     short loc_18002948E
0x1800294ea  call    cs:__imp_GetLastError
0x1800294f1  nop     dword ptr [rax+rax+00h]
0x1800294f6  mov     ecx, eax; unsigned int
0x1800294f8  xor     edx, edx; Format
0x1800294fa  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x1800294ff  jmp     short loc_18002948E
```
