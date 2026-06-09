# CNodeFactory::XMLParser_Element_doc_assembly_dependency_dependentAssembly(ushort,_SXS_NODE_INFO const *)

- ea: `0x18002e6d0`
- end: `0x18002e985`
- name: `?XMLParser_Element_doc_assembly_dependency_dependentAssembly@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180027160`
- `0x18002e4a0`
- `0x18002e6d0`
- `0x18002ed00`
- `0x18002fffc`
- `0x180030148`
- `0x18005d428`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18002e7f1`
- `ntdll!RtlPopFrame` at `0x18002e7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e96b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e96b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e768`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e89f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e8cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e92d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e768`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e89f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e8cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e92d`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_dependency_dependentAssembly(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned int v3; // edi
  char *v6; // rsi
  char **v7; // rcx
  unsigned int v8; // ebx
  DWORD v10; // ebx
  DWORD v11; // eax
  _BYTE *v12; // rbx
  DWORD LastError; // eax
  _BYTE v14[8]; // [rsp+D0h] [rbp-80h] BYREF
  int v15; // [rsp+D8h] [rbp-78h] BYREF
  int v16; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v17; // [rsp+E8h] [rbp-68h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v19; // [rsp+108h] [rbp-48h]
  int v20; // [rsp+110h] [rbp-40h]
  unsigned int *v21; // [rsp+118h] [rbp-38h]

  v3 = a2;
  v16 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006E128;
  Frame.Previous = 0;
  v19 = 544438355;
  Frame.Flags = 1;
  v20 = 2397;
  v21 = (unsigned int *)&v16;
  CFrame::BaseEnter((CFrame *)&Frame);
  v6 = (char *)this + 400;
  v14[0] = 0;
  v17 = 0;
  if ( *((_BYTE *)this + 1835) )
  {
    TraceActCtxGenManifestParseError(
      *(_DWORD *)(*((_QWORD *)this + 2) + 1304LL),
      *((unsigned int *)this + 118),
      0,
      0,
      0,
      0x8Eu);
    v15 = FusionpLogParseError(
            *(const unsigned __int16 **)(*((_QWORD *)this + 2) + 1312LL),
            *((const unsigned __int16 **)this + 56),
            *((_QWORD *)this + 57),
            *((_DWORD *)this + 118),
            0xC1010045,
            0,
            0,
            0);
    v10 = v15;
    FusionpConvertCOMFailure((unsigned int *)&v15);
    v11 = FusionpHRESULTToWin32(v15);
    SetLastError(v11);
    *v21 = 0;
    FusionpTraceCOMFailureOrigination((const struct _CALL_SITE_INFO *)off_18006FAB0, v10);
  }
  else
  {
    *(_WORD *)((char *)this + 1835) = 1;
    SetLastError(0);
    if ( !(unsigned int)SxspGetAttributeValue(
                          0,
                          (WCHAR **)qword_18006E148,
                          (__int64)a3,
                          v3,
                          (__int64)this + 400,
                          v14,
                          1,
                          (__int64)this + 1837,
                          &v17,
                          (unsigned int (__fastcall *)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))SxspValidateBoolAttribute) )
    {
      v7 = off_18006E168;
LABEL_4:
      *v21 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v7);
      goto LABEL_5;
    }
    if ( !v14[0] )
      *((_BYTE *)this + 1837) = 0;
    SetLastError(0);
    v12 = (char *)this + 1840;
    if ( !(unsigned int)SxspGetAttributeValue(
                          0,
                          (WCHAR **)qword_18006FBF0,
                          (__int64)a3,
                          v3,
                          (__int64)v6,
                          v14,
                          1,
                          (__int64)v12,
                          &v17,
                          (unsigned int (__fastcall *)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))SxspValidateBoolAttribute) )
    {
      v7 = off_1800792A8;
      goto LABEL_4;
    }
    if ( !v14[0] )
      *v12 = 0;
    SetLastError(0);
    *v21 = 1;
  }
LABEL_5:
  v8 = *v21;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v8 )
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
  return v8;
}

```

## disassembly

```asm
0x18002e6d0  mov     [rsp-8+arg_8], rbx
0x18002e6d5  push    rbp
0x18002e6d6  push    rsi
0x18002e6d7  push    rdi
0x18002e6d8  push    r12
0x18002e6da  push    r13
0x18002e6dc  push    r14
0x18002e6de  push    r15
0x18002e6e0  lea     rbp, [rsp+20h]
0x18002e6e5  sub     rsp, 130h
0x18002e6ec  mov     rax, cs:__security_cookie
0x18002e6f3  xor     rax, rsp
0x18002e6f6  mov     [rbp+10h+var_40], rax
0x18002e6fa  xor     r12d, r12d
0x18002e6fd  movzx   edi, dx
0x18002e700  lea     rax, qword_18006E128
0x18002e707  mov     [rbp+10h+var_80], r12d
0x18002e70b  mov     [rbp+10h+Frame.Context], rax
0x18002e70f  mov     rbx, rcx
0x18002e712  lea     rax, [rbp+10h+var_80]
0x18002e716  mov     [rbp+10h+Frame.Previous], r12
0x18002e71a  lea     r13d, [r12+1]
0x18002e71f  mov     [rbp+10h+var_58], 20737853h
0x18002e727  lea     rcx, [rbp+10h+Frame]; this
0x18002e72b  mov     [rbp+10h+Frame.Flags], r13d
0x18002e72f  mov     r14, r8
0x18002e732  mov     [rbp+10h+var_50], 95Dh
0x18002e739  mov     [rbp+10h+var_48], rax
0x18002e73d  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002e742  lea     rsi, [rbx+190h]
0x18002e749  mov     [rbp+10h+var_90], r12b
0x18002e74d  mov     [rbp+10h+var_78], r12
0x18002e751  cmp     [rbx+72Bh], r12b
0x18002e758  jnz     loc_18002E827
0x18002e75e  xor     ecx, ecx; dwErrCode
0x18002e760  mov     [rbx+72Bh], r13w
0x18002e768  call    cs:__imp_SetLastError
0x18002e76f  nop     dword ptr [rax+rax+00h]
0x18002e774  lea     rax, ?SxspValidateBoolAttribute@@YAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N_KPEAXAEA_K@Z; SxspValidateBoolAttribute(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &)
0x18002e77b  mov     r15d, edi
0x18002e77e  mov     [rsp+160h+var_118], rax
0x18002e783  lea     rdi, [rbx+72Dh]
0x18002e78a  lea     rax, [rbp+10h+var_78]
0x18002e78e  mov     r9d, r15d
0x18002e791  mov     [rsp+160h+var_120], rax
0x18002e796  lea     rdx, qword_18006E148
0x18002e79d  mov     [rsp+160h+var_128], rdi
0x18002e7a2  lea     rax, [rbp+10h+var_90]
0x18002e7a6  mov     [rsp+160h+var_130], r13
0x18002e7ab  mov     r8, r14
0x18002e7ae  mov     [rsp+160h+var_138], rax
0x18002e7b3  xor     ecx, ecx
0x18002e7b5  mov     qword ptr [rsp+160h+dwMessageId], rsi
0x18002e7ba  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x18002e7bf  test    eax, eax
0x18002e7c1  jnz     loc_18002E8C5
0x18002e7c7  lea     rcx, off_18006E168; struct _CALL_SITE_INFO *
0x18002e7ce  mov     rax, [rbp+10h+var_48]
0x18002e7d2  mov     [rax], r12d
0x18002e7d5  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002e7da  cmp     cs:g_FusionEnterExitTracingEnabled, r12b
0x18002e7e1  mov     rax, [rbp+10h+var_48]
0x18002e7e5  mov     ebx, [rax]
0x18002e7e7  jnz     loc_18002E95B
0x18002e7ed  lea     rcx, [rbp+10h+Frame]; Frame
0x18002e7f1  call    cs:__imp_RtlPopFrame
0x18002e7f8  nop     dword ptr [rax+rax+00h]
0x18002e7fd  mov     eax, ebx
0x18002e7ff  mov     rcx, [rbp+10h+var_40]
0x18002e803  xor     rcx, rsp; StackCookie
0x18002e806  call    __security_check_cookie
0x18002e80b  mov     rbx, [rsp+160h+arg_8]
0x18002e813  add     rsp, 130h
0x18002e81a  pop     r15
0x18002e81c  pop     r14
0x18002e81e  pop     r13
0x18002e820  pop     r12
0x18002e822  pop     rdi
0x18002e823  pop     rsi
0x18002e824  pop     rbp
0x18002e825  retn
0x18002e827  mov     rcx, [rbx+10h]
0x18002e82b  xor     r9d, r9d; unsigned __int16 *
0x18002e82e  mov     edx, [rsi+48h]; unsigned int
0x18002e831  xor     r8d, r8d; unsigned __int16 *
0x18002e834  mov     word ptr [rsp+160h+var_138], 8Eh; unsigned __int16
0x18002e83b  mov     qword ptr [rsp+160h+dwMessageId], r12; unsigned __int16 *
0x18002e840  mov     ecx, [rcx+518h]; int
0x18002e846  call    ?TraceActCtxGenManifestParseError@@YAKJKPEBG00G@Z; TraceActCtxGenManifestParseError(long,ulong,ushort const *,ushort const *,ushort const *,ushort)
0x18002e84b  mov     rcx, [rbx+10h]
0x18002e84f  mov     r9d, [rbx+1D8h]; unsigned int
0x18002e856  mov     r8, [rbx+1C8h]; unsigned __int64
0x18002e85d  mov     rdx, [rbx+1C0h]; unsigned __int16 *
0x18002e864  mov     rcx, [rcx+520h]; unsigned __int16 *
0x18002e86b  mov     [rsp+160h+var_128], r12; struct _UNICODE_STRING *
0x18002e870  mov     [rsp+160h+var_130], r12; struct _UNICODE_STRING *
0x18002e875  mov     [rsp+160h+var_138], r12; struct _UNICODE_STRING *
0x18002e87a  mov     [rsp+160h+dwMessageId], 0C1010045h; dwMessageId
0x18002e882  call    ?FusionpLogParseError@@YAJPEBG0_KKKPEBU_UNICODE_STRING@@2222222222222222222@Z; FusionpLogParseError(ushort const *,ushort const *,unsigned __int64,ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002e887  lea     rcx, [rbp+10h+var_88]; int *
0x18002e88b  mov     [rbp+10h+var_88], eax
0x18002e88e  mov     ebx, eax
0x18002e890  call    ?FusionpConvertCOMFailure@@YAXAEAJ@Z; FusionpConvertCOMFailure(long &)
0x18002e895  mov     ecx, [rbp+10h+var_88]; int
0x18002e898  call    ?FusionpHRESULTToWin32@@YAKJ@Z; FusionpHRESULTToWin32(long)
0x18002e89d  mov     ecx, eax; dwErrCode
0x18002e89f  call    cs:__imp_SetLastError
0x18002e8a6  nop     dword ptr [rax+rax+00h]
0x18002e8ab  mov     rcx, [rbp+10h+var_48]
0x18002e8af  mov     edx, ebx; int
0x18002e8b1  mov     [rcx], r12d
0x18002e8b4  lea     rcx, off_18006FAB0; struct _CALL_SITE_INFO *
0x18002e8bb  call    ?FusionpTraceCOMFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@J@Z; FusionpTraceCOMFailureOrigination(_CALL_SITE_INFO const &,long)
0x18002e8c0  jmp     loc_18002E7DA
0x18002e8c5  cmp     [rbp+10h+var_90], r12b
0x18002e8c9  jz      short loc_18002E945
0x18002e8cb  xor     ecx, ecx; dwErrCode
0x18002e8cd  call    cs:__imp_SetLastError
0x18002e8d4  nop     dword ptr [rax+rax+00h]
0x18002e8d9  lea     rax, ?SxspValidateBoolAttribute@@YAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N_KPEAXAEA_K@Z; SxspValidateBoolAttribute(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &)
0x18002e8e0  add     rbx, 730h
0x18002e8e7  mov     [rsp+160h+var_118], rax
0x18002e8ec  lea     rdx, qword_18006FBF0
0x18002e8f3  lea     rax, [rbp+10h+var_78]
0x18002e8f7  mov     r9, r15
0x18002e8fa  mov     [rsp+160h+var_120], rax
0x18002e8ff  mov     r8, r14
0x18002e902  mov     [rsp+160h+var_128], rbx
0x18002e907  lea     rax, [rbp+10h+var_90]
0x18002e90b  mov     [rsp+160h+var_130], r13
0x18002e910  xor     ecx, ecx
0x18002e912  mov     [rsp+160h+var_138], rax
0x18002e917  mov     qword ptr [rsp+160h+dwMessageId], rsi
0x18002e91c  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x18002e921  test    eax, eax
0x18002e923  jz      short loc_18002E94A
0x18002e925  cmp     [rbp+10h+var_90], r12b
0x18002e929  jz      short loc_18002E956
0x18002e92b  xor     ecx, ecx; dwErrCode
0x18002e92d  call    cs:__imp_SetLastError
0x18002e934  nop     dword ptr [rax+rax+00h]
0x18002e939  mov     rax, [rbp+10h+var_48]
0x18002e93d  mov     [rax], r13d
0x18002e940  jmp     loc_18002E7DA
0x18002e945  mov     [rdi], r12b
0x18002e948  jmp     short loc_18002E8CB
0x18002e94a  lea     rcx, off_1800792A8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x18002e951  jmp     loc_18002E7CE
0x18002e956  mov     [rbx], r12b
0x18002e959  jmp     short loc_18002E92B
0x18002e95b  test    ebx, ebx
0x18002e95d  jz      short loc_18002E96B
0x18002e95f  xor     ecx, ecx; char *
0x18002e961  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18002e966  jmp     loc_18002E7ED
0x18002e96b  call    cs:__imp_GetLastError
0x18002e972  nop     dword ptr [rax+rax+00h]
0x18002e977  mov     ecx, eax; unsigned int
0x18002e979  xor     edx, edx; Format
0x18002e97b  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18002e980  jmp     loc_18002E7ED
```
