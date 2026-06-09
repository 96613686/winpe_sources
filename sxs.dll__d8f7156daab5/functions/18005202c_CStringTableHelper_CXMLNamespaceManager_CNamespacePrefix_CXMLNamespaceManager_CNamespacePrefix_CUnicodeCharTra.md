# CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::CompareKey(CCountedStringHolder<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &)

- ea: `0x18005202c`
- end: `0x1800521f7`
- name: `?CompareKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020904`

## callees

- `0x18000df40`
- `0x18005202c`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18005213f`
- `ntdll!RtlCompareUnicodeString` at `0x18005213f`
- `ntdll!RtlPopFrame` at `0x180052175`
- `ntdll!RtlPopFrame` at `0x180052192`
- `ntdll!RtlPopFrame` at `0x180052175`
- `ntdll!RtlPopFrame` at `0x180052192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800521e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800520a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800520f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052155`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800520a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800520f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052155`

## pseudocode

```c
__int64 __fastcall CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::CompareKey(
        __int64 a1,
        __int64 a2,
        bool *a3)
{
  __int64 v6; // rdi
  WCHAR *v7; // rbx
  WCHAR *v8; // rax
  DWORD LastError; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-59h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-49h] BYREF
  int v13; // [rsp+40h] [rbp-39h] BYREF
  int v14; // [rsp+44h] [rbp-35h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+48h] [rbp-31h] BYREF
  __int64 v16; // [rsp+60h] [rbp-19h]
  int v17; // [rsp+68h] [rbp-11h]
  int *v18; // [rsp+70h] [rbp-9h]
  struct _TEB_ACTIVE_FRAME v19; // [rsp+78h] [rbp-1h] BYREF
  __int64 v20; // [rsp+90h] [rbp+17h]
  int v21; // [rsp+98h] [rbp+1Fh]
  int *v22; // [rsp+A0h] [rbp+27h]

  v13 = 0;
  v19.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::CompareKey'::`2'::__stc;
  v19.Previous = 0;
  v22 = &v13;
  v19.Flags = 1;
  v20 = 544438355;
  v21 = 1289;
  CFrame::BaseEnter((CFrame *)&v19);
  SetLastError(0);
  v6 = *(_QWORD *)(a1 + 8);
  v7 = *(WCHAR **)a1;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals'::`2'::__stc;
  v18 = &v14;
  v14 = 0;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v16 = 544438355;
  v17 = 654;
  CFrame::BaseEnter((CFrame *)&Frame);
  SetLastError(0);
  v8 = *(WCHAR **)(a2 + 16);
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = v8;
  LOWORD(v8) = *(_WORD *)(a2 + 32);
  *(&String2.MaximumLength + 2) = 0;
  String2.Buffer = v7;
  *(_QWORD *)&String1.Length = (unsigned __int16)(2 * (_WORD)v8);
  *(_DWORD *)&String1.MaximumLength = (unsigned __int16)(2 * (_WORD)v8);
  String2.Length = 2 * v6;
  *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(2 * v6);
  *a3 = RtlCompareUnicodeString(&String1, &String2, 0) == 0;
  SetLastError(0);
  *v18 = 1;
  if ( g_FusionEnterExitTracingEnabled )
    FusionpTraceCallSuccessfulExit(0);
  RtlPopFrame(&Frame);
  v13 = 1;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v22 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&v19);
  return 1;
}

```

## disassembly

```asm
0x18005202c  mov     [rsp-8+arg_18], rbx
0x180052031  push    rbp
0x180052032  push    rsi
0x180052033  push    rdi
0x180052034  push    r13
0x180052036  push    r14
0x180052038  lea     rbp, [rsp-37h]
0x18005203d  sub     rsp, 0B0h
0x180052044  mov     rax, cs:__security_cookie
0x18005204b  xor     rax, rsp
0x18005204e  mov     [rbp+57h+var_28], rax
0x180052052  lea     rax, ?__stc@?1??CompareKey@?$CStringTableHelper@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV12@VCUnicodeCharTraits@@$0A@@@SAHAEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@AEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CStringTableHelper<CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CUnicodeCharTraits,0>::CompareKey(CCountedStringHolder<CUnicodeCharTraits> const &,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &)'::`2'::__stc
0x180052059  mov     [rbp+57h+var_90], 0
0x180052060  mov     [rbp+57h+var_58.Context], rax
0x180052064  mov     rbx, rcx
0x180052067  lea     rax, [rbp+57h+var_90]
0x18005206b  mov     [rbp+57h+var_58.Previous], 0
0x180052073  mov     r13d, 1
0x180052079  mov     [rbp+57h+var_30], rax
0x18005207d  lea     rcx, [rbp+57h+var_58]; this
0x180052081  mov     [rbp+57h+var_58.Flags], r13d
0x180052085  mov     r14, r8
0x180052088  mov     [rbp+57h+var_40], 20737853h
0x180052090  mov     rsi, rdx
0x180052093  mov     [rbp+57h+var_38], 509h
0x18005209a  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18005209f  xor     ecx, ecx; dwErrCode
0x1800520a1  call    cs:__imp_SetLastError
0x1800520a8  nop     dword ptr [rax+rax+00h]
0x1800520ad  mov     rdi, [rbx+8]
0x1800520b1  lea     rax, ?__stc@?1??Win32Equals@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEBG_KAEA_N_N@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Equals(ushort const *,unsigned __int64,bool &,bool)'::`2'::__stc
0x1800520b8  mov     rbx, [rbx]
0x1800520bb  lea     rcx, [rbp+57h+Frame]; this
0x1800520bf  mov     [rbp+57h+Frame.Context], rax
0x1800520c3  lea     rax, [rbp+57h+var_8C]
0x1800520c7  mov     [rbp+57h+var_60], rax
0x1800520cb  mov     [rbp+57h+var_8C], 0
0x1800520d2  mov     [rbp+57h+Frame.Flags], r13d
0x1800520d6  mov     [rbp+57h+Frame.Previous], 0
0x1800520de  mov     [rbp+57h+var_70], 20737853h
0x1800520e6  mov     [rbp+57h+var_68], 28Eh
0x1800520ed  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800520f2  xor     ecx, ecx; dwErrCode
0x1800520f4  call    cs:__imp_SetLastError
0x1800520fb  nop     dword ptr [rax+rax+00h]
0x180052100  mov     rax, [rsi+10h]
0x180052104  lea     rdx, [rbp+57h+String2]; String2
0x180052108  xorps   xmm0, xmm0
0x18005210b  lea     rcx, [rbp+57h+String1]; String1
0x18005210f  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x180052113  mov     [rbp+57h+String1.Buffer], rax
0x180052117  add     di, di
0x18005211a  movzx   eax, word ptr [rsi+20h]
0x18005211e  xorps   xmm1, xmm1
0x180052121  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x180052125  add     ax, ax
0x180052128  mov     [rbp+57h+String2.Buffer], rbx
0x18005212c  xor     r8d, r8d; CaseInsensitive
0x18005212f  mov     [rbp+57h+String1.Length], ax
0x180052133  mov     [rbp+57h+String1.MaximumLength], ax
0x180052137  mov     [rbp+57h+String2.Length], di
0x18005213b  mov     [rbp+57h+String2.MaximumLength], di
0x18005213f  call    cs:__imp_RtlCompareUnicodeString
0x180052146  nop     dword ptr [rax+rax+00h]
0x18005214b  test    eax, eax
0x18005214d  setz    al
0x180052150  xor     ecx, ecx; dwErrCode
0x180052152  mov     [r14], al
0x180052155  call    cs:__imp_SetLastError
0x18005215c  nop     dword ptr [rax+rax+00h]
0x180052161  mov     rax, [rbp+57h+var_60]
0x180052165  mov     [rax], r13d
0x180052168  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18005216f  jnz     short loc_1800521C5
0x180052171  lea     rcx, [rbp+57h+Frame]; Frame
0x180052175  call    cs:__imp_RtlPopFrame
0x18005217c  nop     dword ptr [rax+rax+00h]
0x180052181  mov     [rbp+57h+var_90], r13d
0x180052185  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x18005218c  jnz     short loc_1800521CE
0x18005218e  lea     rcx, [rbp+57h+var_58]; Frame
0x180052192  call    cs:__imp_RtlPopFrame
0x180052199  nop     dword ptr [rax+rax+00h]
0x18005219e  mov     eax, r13d
0x1800521a1  mov     rcx, [rbp+57h+var_28]
0x1800521a5  xor     rcx, rsp; StackCookie
0x1800521a8  call    __security_check_cookie
0x1800521ad  mov     rbx, [rsp+0D0h+arg_18]
0x1800521b5  add     rsp, 0B0h
0x1800521bc  pop     r14
0x1800521be  pop     r13
0x1800521c0  pop     rdi
0x1800521c1  pop     rsi
0x1800521c2  pop     rbp
0x1800521c3  retn
0x1800521c5  xor     ecx, ecx; char *
0x1800521c7  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800521cc  jmp     short loc_180052171
0x1800521ce  mov     rax, [rbp+57h+var_30]
0x1800521d2  cmp     dword ptr [rax], 0
0x1800521d5  jz      short loc_1800521E0
0x1800521d7  xor     ecx, ecx; char *
0x1800521d9  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800521de  jmp     short loc_18005218E
0x1800521e0  call    cs:__imp_GetLastError
0x1800521e7  nop     dword ptr [rax+rax+00h]
0x1800521ec  mov     ecx, eax; unsigned int
0x1800521ee  xor     edx, edx; Format
0x1800521f0  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x1800521f5  jmp     short loc_18005218E
```
