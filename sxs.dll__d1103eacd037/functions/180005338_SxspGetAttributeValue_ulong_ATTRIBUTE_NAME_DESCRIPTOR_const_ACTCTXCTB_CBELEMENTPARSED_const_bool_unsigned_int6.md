# SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_ACTCTXCTB_CBELEMENTPARSED const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)

- ea: `0x180005338`
- end: `0x1800054c8`
- name: `?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_ACTCTXCTB_CBELEMENTPARSED@@AEA_N_KPEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@2345@ZK@Z`
- size: `400`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180002a70`
- `0x1800345b0`
- `0x1800358d0`
- `0x18003731c`

## callees

- `0x180005338`
- `0x18000df40`
- `0x18000dffc`
- `0x180027160`
- `0x18005d2b0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18000542b`
- `ntdll!RtlPopFrame` at `0x18000542b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005469`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005469`

## pseudocode

```c
__int64 __fastcall SxspGetAttributeValue(
        int a1,
        WCHAR **a2,
        __int64 a3,
        _BYTE *a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        unsigned int (__fastcall *a8)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))
{
  const char *v12; // rcx
  unsigned int v13; // ebx
  DWORD LastError; // eax
  int v16; // [rsp+60h] [rbp-39h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+68h] [rbp-31h] BYREF
  __int64 v18; // [rsp+80h] [rbp-19h]
  int v19; // [rsp+88h] [rbp-11h]
  int *v20; // [rsp+90h] [rbp-9h]

  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006D2E0;
  v16 = 0;
  v20 = &v16;
  Frame.Flags = 1;
  Frame.Previous = 0;
  v18 = 544438355;
  v19 = 2077;
  CFrame::BaseEnter((CFrame *)&Frame);
  *a4 = 0;
  *a7 = 0;
  if ( a3 )
  {
    SetLastError(0);
    if ( (unsigned int)SxspGetAttributeValue(
                         a1,
                         a2,
                         *(_QWORD *)(a3 + 104),
                         *(unsigned int *)(a3 + 96),
                         *(_QWORD *)(a3 + 88),
                         a4,
                         a5,
                         a6,
                         a7,
                         a8) )
    {
      v16 = 1;
    }
    else
    {
      *v20 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800756B0);
    }
  }
  else
  {
    v19 = 2083;
    FusionpTraceParameterCheck(v12);
    SetLastError(0x57u);
    *v20 = 0;
  }
  v13 = v16;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v20 )
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
  return v13;
}

```

## disassembly

```asm
0x180005338  push    rbp
0x18000533a  push    rbx
0x18000533b  push    rsi
0x18000533c  push    rdi
0x18000533d  push    r12
0x18000533f  push    r14
0x180005341  push    r15
0x180005343  lea     rbp, [rsp-7]
0x180005348  sub     rsp, 0A0h
0x18000534f  mov     rax, cs:__security_cookie
0x180005356  xor     rax, rsp
0x180005359  mov     [rbp+37h+var_38], rax
0x18000535d  mov     r12, [rbp+37h+arg_28]
0x180005361  lea     rax, qword_18006D2E0
0x180005368  mov     rsi, [rbp+37h+arg_30]
0x18000536c  mov     r14d, ecx
0x18000536f  mov     [rbp+37h+Frame.Context], rax
0x180005373  lea     rcx, [rbp+37h+Frame]; this
0x180005377  lea     rax, [rbp+37h+var_70]
0x18000537b  mov     [rbp+37h+var_70], 0
0x180005382  mov     [rbp+37h+var_40], rax
0x180005386  mov     rdi, r9
0x180005389  mov     rbx, r8
0x18000538c  mov     [rbp+37h+Frame.Flags], 1
0x180005393  mov     r15, rdx
0x180005396  mov     [rbp+37h+Frame.Previous], 0
0x18000539e  mov     [rbp+37h+var_50], 20737853h
0x1800053a6  mov     [rbp+37h+var_48], 81Dh
0x1800053ad  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800053b2  mov     byte ptr [rdi], 0
0x1800053b5  mov     qword ptr [rsi], 0
0x1800053bc  test    rbx, rbx
0x1800053bf  jz      loc_180005458
0x1800053c5  xor     ecx, ecx; dwErrCode
0x1800053c7  call    cs:__imp_SetLastError
0x1800053ce  nop     dword ptr [rax+rax+00h]
0x1800053d3  mov     rax, [rbp+37h+arg_38]
0x1800053d7  mov     rdx, r15
0x1800053da  mov     r9d, [rbx+60h]
0x1800053de  mov     ecx, r14d
0x1800053e1  mov     r8, [rbx+68h]
0x1800053e5  mov     [rsp+0D0h+var_88], rax
0x1800053ea  mov     rax, [rbp+37h+arg_20]
0x1800053ee  mov     [rsp+0D0h+var_90], rsi
0x1800053f3  mov     [rsp+0D0h+var_98], r12
0x1800053f8  mov     [rsp+0D0h+var_A0], rax
0x1800053fd  mov     rax, [rbx+58h]
0x180005401  mov     [rsp+0D0h+var_A8], rdi
0x180005406  mov     [rsp+0D0h+var_B0], rax
0x18000540b  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180005410  test    eax, eax
0x180005412  jz      short loc_180005481
0x180005414  mov     [rbp+37h+var_70], 1
0x18000541b  cmp     cs:g_FusionEnterExitTracingEnabled, 0
0x180005422  mov     ebx, [rbp+37h+var_70]
0x180005425  jnz     short loc_180005499
0x180005427  lea     rcx, [rbp+37h+Frame]; Frame
0x18000542b  call    cs:__imp_RtlPopFrame
0x180005432  nop     dword ptr [rax+rax+00h]
0x180005437  mov     eax, ebx
0x180005439  mov     rcx, [rbp+37h+var_38]
0x18000543d  xor     rcx, rsp; StackCookie
0x180005440  call    __security_check_cookie
0x180005445  add     rsp, 0A0h
0x18000544c  pop     r15
0x18000544e  pop     r14
0x180005450  pop     r12
0x180005452  pop     rdi
0x180005453  pop     rsi
0x180005454  pop     rbx
0x180005455  pop     rbp
0x180005456  retn
0x180005458  mov     [rbp+37h+var_48], 823h
0x18000545f  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180005464  mov     ecx, 57h ; 'W'; dwErrCode
0x180005469  call    cs:__imp_SetLastError
0x180005470  nop     dword ptr [rax+rax+00h]
0x180005475  mov     rax, [rbp+37h+var_40]
0x180005479  mov     dword ptr [rax], 0
0x18000547f  jmp     short loc_18000541B
0x180005481  mov     rax, [rbp+37h+var_40]
0x180005485  lea     rcx, off_1800756B0; struct _CALL_SITE_INFO *
0x18000548c  mov     dword ptr [rax], 0
0x180005492  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180005497  jmp     short loc_18000541B
0x180005499  mov     rax, [rbp+37h+var_40]
0x18000549d  cmp     dword ptr [rax], 0
0x1800054a0  jz      short loc_1800054AE
0x1800054a2  xor     ecx, ecx; char *
0x1800054a4  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x1800054a9  jmp     loc_180005427
0x1800054ae  call    cs:__imp_GetLastError
0x1800054b5  nop     dword ptr [rax+rax+00h]
0x1800054ba  mov     ecx, eax; unsigned int
0x1800054bc  xor     edx, edx; Format
0x1800054be  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x1800054c3  jmp     loc_180005427
```
