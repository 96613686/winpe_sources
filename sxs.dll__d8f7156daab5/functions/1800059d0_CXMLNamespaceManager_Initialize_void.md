# CXMLNamespaceManager::Initialize(void)

- ea: `0x1800059d0`
- end: `0x180005ad6`
- name: `?Initialize@CXMLNamespaceManager@@QEAAHXZ`
- size: `262`
- prototype: `__int64 __fastcall(CXMLNamespaceManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800057e0`

## callees

- `0x1800059d0`
- `0x180005adc`
- `0x18000df40`
- `0x18000dffc`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180005a74`
- `ntdll!RtlPopFrame` at `0x180005a74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005abf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a4b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a4b`

## pseudocode

```c
__int64 __fastcall CXMLNamespaceManager::Initialize(CXMLNamespaceManager *this)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  int v5; // [rsp+20h] [rbp-40h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+28h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-20h]
  int v8; // [rsp+48h] [rbp-18h]
  unsigned int *v9; // [rsp+50h] [rbp-10h]

  v5 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006C240;
  Frame.Flags = 1;
  v9 = (unsigned int *)&v5;
  Frame.Previous = 0;
  v7 = 544438355;
  v8 = 42;
  CFrame::BaseEnter((CFrame *)&Frame);
  SetLastError(0);
  if ( (unsigned int)CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Initialize(this) )
  {
    SetLastError(0);
    *v9 = 1;
  }
  else
  {
    *v9 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_18007CBC0);
  }
  v2 = *v9;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v2 )
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
  return v2;
}

```

## disassembly

```asm
0x1800059d0  mov     [rsp-8+arg_8], rbx
0x1800059d5  push    rbp
0x1800059d6  mov     rbp, rsp
0x1800059d9  sub     rsp, 60h
0x1800059dd  mov     rax, cs:__security_cookie
0x1800059e4  xor     rax, rsp
0x1800059e7  mov     [rbp+var_8], rax
0x1800059eb  lea     rax, qword_18006C240
0x1800059f2  mov     [rbp+var_40], 0
0x1800059f9  mov     [rbp+Frame.Context], rax
0x1800059fd  mov     rbx, rcx
0x180005a00  lea     rax, [rbp+var_40]
0x180005a04  mov     [rbp+Frame.Flags], 1
0x180005a0b  lea     rcx, [rbp+Frame]; this
0x180005a0f  mov     [rbp+var_10], rax
0x180005a13  mov     [rbp+Frame.Previous], 0
0x180005a1b  mov     [rbp+var_20], 20737853h
0x180005a23  mov     [rbp+var_18], 2Ah ; '*'
0x180005a2a  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180005a2f  xor     ecx, ecx; dwErrCode
0x180005a31  call    cs:__imp_SetLastError
0x180005a38  nop     dword ptr [rax+rax+00h]
0x180005a3d  mov     rcx, rbx
0x180005a40  call    ?Initialize@?$CHashTable@AEBV?$CCountedStringHolder@VCUnicodeCharTraits@@@@V?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@PEAVCNamespacePrefix@CXMLNamespaceManager@@PEAV34@V?$CStringPtrTableHelper@VCNamespacePrefix@CXMLNamespaceManager@@VCUnicodeCharTraits@@$0A@@@$06$0A@@@QEAAHK@Z; CHashTable<CCountedStringHolder<CUnicodeCharTraits> const &,CGenericStringBuffer<260,CUnicodeCharTraits>,CXMLNamespaceManager::CNamespacePrefix *,CXMLNamespaceManager::CNamespacePrefix *,CStringPtrTableHelper<CXMLNamespaceManager::CNamespacePrefix,CUnicodeCharTraits,0>,7,0>::Initialize(ulong)
0x180005a45  test    eax, eax
0x180005a47  jz      short loc_180005A9A
0x180005a49  xor     ecx, ecx; dwErrCode
0x180005a4b  call    cs:__imp_SetLastError
0x180005a52  nop     dword ptr [rax+rax+00h]
0x180005a57  mov     rax, [rbp+var_10]
0x180005a5b  mov     dword ptr [rax], 1
0x180005a61  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180005a68  mov     rax, [rbp+var_10]
0x180005a6c  mov     ebx, [rax]
0x180005a6e  jnz     short loc_180005AB2
0x180005a70  lea     rcx, [rbp+Frame]; Frame
0x180005a74  call    cs:__imp_RtlPopFrame
0x180005a7b  nop     dword ptr [rax+rax+00h]
0x180005a80  mov     eax, ebx
0x180005a82  mov     rcx, [rbp+var_8]
0x180005a86  xor     rcx, rsp; StackCookie
0x180005a89  call    __security_check_cookie
0x180005a8e  mov     rbx, [rsp+60h+arg_8]
0x180005a93  add     rsp, 60h
0x180005a97  pop     rbp
0x180005a98  retn
0x180005a9a  mov     rax, [rbp+var_10]
0x180005a9e  lea     rcx, off_18007CBC0; struct _CALL_SITE_INFO *
0x180005aa5  mov     dword ptr [rax], 0
0x180005aab  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180005ab0  jmp     short loc_180005A61
0x180005ab2  test    ebx, ebx
0x180005ab4  jz      short loc_180005ABF
0x180005ab6  xor     ecx, ecx; char *
0x180005ab8  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180005abd  jmp     short loc_180005A70
0x180005abf  call    cs:__imp_GetLastError
0x180005ac6  nop     dword ptr [rax+rax+00h]
0x180005acb  mov     ecx, eax; unsigned int
0x180005acd  xor     edx, edx; Format
0x180005acf  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180005ad4  jmp     short loc_180005A70
```
