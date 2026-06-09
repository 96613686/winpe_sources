# CNodeFactory::XMLParser_Element_doc_assembly_dependency(ushort,_SXS_NODE_INFO const *)

- ea: `0x180054be0`
- end: `0x180054d72`
- name: `?XMLParser_Element_doc_assembly_dependency@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180027160`
- `0x180054be0`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180054d02`
- `ntdll!RtlPopFrame` at `0x180054d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054d5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054c75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054cd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054c75`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054cd9`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_dependency(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned int v3; // edi
  unsigned int v6; // ebx
  DWORD LastError; // eax
  _BYTE v9[4]; // [rsp+60h] [rbp-19h] BYREF
  int v10; // [rsp+64h] [rbp-15h] BYREF
  __int64 v11; // [rsp+68h] [rbp-11h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+70h] [rbp-9h] BYREF
  __int64 v13; // [rsp+88h] [rbp+Fh]
  int v14; // [rsp+90h] [rbp+17h]
  unsigned int *v15; // [rsp+98h] [rbp+1Fh]

  v3 = a2;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_1800724F0;
  Frame.Flags = 1;
  v15 = (unsigned int *)&v10;
  v10 = 0;
  Frame.Previous = 0;
  v13 = 544438355;
  v14 = 2362;
  CFrame::BaseEnter((CFrame *)&Frame);
  v9[0] = 0;
  *((_BYTE *)this + 1834) = 0;
  v11 = 0;
  *((_BYTE *)this + 1835) = 0;
  *((_BYTE *)this + 1837) = 0;
  *((_BYTE *)this + 1840) = 0;
  SetLastError(0);
  if ( (unsigned int)SxspGetAttributeValue(
                       0,
                       (WCHAR **)qword_180072510,
                       (__int64)a3,
                       v3,
                       (__int64)this + 400,
                       v9,
                       1,
                       (__int64)this + 1834,
                       &v11,
                       (unsigned int (__fastcall *)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))SxspValidateBoolAttribute) )
  {
    if ( !v9[0] )
      *((_BYTE *)this + 1834) = 0;
    SetLastError(0);
    *v15 = 1;
  }
  else
  {
    *v15 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800792C8);
  }
  v6 = *v15;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v6 )
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
  return v6;
}

```

## disassembly

```asm
0x180054be0  mov     [rsp-8+arg_8], rbx
0x180054be5  push    rbp
0x180054be6  push    rsi
0x180054be7  push    rdi
0x180054be8  push    r14
0x180054bea  push    r15
0x180054bec  lea     rbp, [rsp-37h]
0x180054bf1  sub     rsp, 0B0h
0x180054bf8  mov     rax, cs:__security_cookie
0x180054bff  xor     rax, rsp
0x180054c02  mov     [rbp+57h+var_30], rax
0x180054c06  lea     rax, qword_1800724F0
0x180054c0d  movzx   edi, dx
0x180054c10  mov     [rbp+57h+Frame.Context], rax
0x180054c14  mov     rbx, rcx
0x180054c17  lea     rax, [rbp+57h+var_6C]
0x180054c1b  mov     [rbp+57h+Frame.Flags], 1
0x180054c22  xor     r15d, r15d
0x180054c25  mov     [rbp+57h+var_38], rax
0x180054c29  lea     rcx, [rbp+57h+Frame]; this
0x180054c2d  mov     [rbp+57h+var_6C], r15d
0x180054c31  mov     rsi, r8
0x180054c34  mov     [rbp+57h+Frame.Previous], r15
0x180054c38  mov     [rbp+57h+var_48], 20737853h
0x180054c40  mov     [rbp+57h+var_40], 93Ah
0x180054c47  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180054c4c  lea     r14, [rbx+72Ah]
0x180054c53  mov     [rbp+57h+var_70], r15b
0x180054c57  xor     ecx, ecx; dwErrCode
0x180054c59  mov     [r14], r15b
0x180054c5c  mov     [rbp+57h+var_68], r15
0x180054c60  mov     [rbx+72Bh], r15b
0x180054c67  mov     [rbx+72Dh], r15b
0x180054c6e  mov     [rbx+730h], r15b
0x180054c75  call    cs:__imp_SetLastError
0x180054c7c  nop     dword ptr [rax+rax+00h]
0x180054c81  lea     rcx, ?SxspValidateBoolAttribute@@YAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N_KPEAXAEA_K@Z; SxspValidateBoolAttribute(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &)
0x180054c88  mov     r9d, edi
0x180054c8b  mov     [rsp+0D0h+var_88], rcx
0x180054c90  lea     rax, [rbx+190h]
0x180054c97  lea     rcx, [rbp+57h+var_68]
0x180054c9b  mov     r8, rsi
0x180054c9e  mov     [rsp+0D0h+var_90], rcx
0x180054ca3  lea     rdx, qword_180072510
0x180054caa  mov     [rsp+0D0h+var_98], r14
0x180054caf  lea     rcx, [rbp+57h+var_70]
0x180054cb3  mov     [rsp+0D0h+var_A0], 1
0x180054cbc  mov     [rsp+0D0h+var_A8], rcx
0x180054cc1  xor     ecx, ecx
0x180054cc3  mov     [rsp+0D0h+var_B0], rax
0x180054cc8  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180054ccd  test    eax, eax
0x180054ccf  jz      short loc_180054D34
0x180054cd1  cmp     [rbp+57h+var_70], r15b
0x180054cd5  jz      short loc_180054D49
0x180054cd7  xor     ecx, ecx; dwErrCode
0x180054cd9  call    cs:__imp_SetLastError
0x180054ce0  nop     dword ptr [rax+rax+00h]
0x180054ce5  mov     rax, [rbp+57h+var_38]
0x180054ce9  mov     dword ptr [rax], 1
0x180054cef  cmp     cs:g_FusionEnterExitTracingEnabled, r15b
0x180054cf6  mov     rax, [rbp+57h+var_38]
0x180054cfa  mov     ebx, [rax]
0x180054cfc  jnz     short loc_180054D4E
0x180054cfe  lea     rcx, [rbp+57h+Frame]; Frame
0x180054d02  call    cs:__imp_RtlPopFrame
0x180054d09  nop     dword ptr [rax+rax+00h]
0x180054d0e  mov     eax, ebx
0x180054d10  mov     rcx, [rbp+57h+var_30]
0x180054d14  xor     rcx, rsp; StackCookie
0x180054d17  call    __security_check_cookie
0x180054d1c  mov     rbx, [rsp+0D0h+arg_8]
0x180054d24  add     rsp, 0B0h
0x180054d2b  pop     r15
0x180054d2d  pop     r14
0x180054d2f  pop     rdi
0x180054d30  pop     rsi
0x180054d31  pop     rbp
0x180054d32  retn
0x180054d34  mov     rax, [rbp+57h+var_38]
0x180054d38  lea     rcx, off_1800792C8; struct _CALL_SITE_INFO *
0x180054d3f  mov     [rax], r15d
0x180054d42  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180054d47  jmp     short loc_180054CEF
0x180054d49  mov     [r14], r15b
0x180054d4c  jmp     short loc_180054CD7
0x180054d4e  test    ebx, ebx
0x180054d50  jz      short loc_180054D5B
0x180054d52  xor     ecx, ecx; char *
0x180054d54  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180054d59  jmp     short loc_180054CFE
0x180054d5b  call    cs:__imp_GetLastError
0x180054d62  nop     dword ptr [rax+rax+00h]
0x180054d67  mov     ecx, eax; unsigned int
0x180054d69  xor     edx, edx; Format
0x180054d6b  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180054d70  jmp     short loc_180054CFE
```
