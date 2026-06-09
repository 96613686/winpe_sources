# CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_publisherPolicy(ushort,_SXS_NODE_INFO const *)

- ea: `0x180065d30`
- end: `0x180065f25`
- name: `?XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_publisherPolicy@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180027160`
- `0x1800515ec`
- `0x180065d30`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065df5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065e7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ede`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065df5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065e7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180065ede`

## string_xrefs

- `0x180065ea7`: `CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_publisherPolicy`
- `0x180065eb3`: `SXS.DLL: %s() app-level PublisherPolicy try to be set but there is no appcompat flags been set.\n`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_publisherPolicy(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned __int64 v3; // rdi
  __int64 v6; // rcx
  unsigned int v7; // ebx
  const struct _UNICODE_STRING *v9; // [rsp+30h] [rbp-110h]
  const struct _UNICODE_STRING *v10; // [rsp+38h] [rbp-108h]
  const struct _UNICODE_STRING *v11; // [rsp+40h] [rbp-100h]
  const struct _UNICODE_STRING *v12; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v13; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v14; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v15; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v16; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v17; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v18; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v19; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v20; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v21; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v22; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v23; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v24; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v25; // [rsp+B0h] [rbp-90h]
  char v26; // [rsp+C0h] [rbp-80h] BYREF
  _BYTE v27[3]; // [rsp+C1h] [rbp-7Fh] BYREF
  int v28; // [rsp+C4h] [rbp-7Ch] BYREF
  __int64 v29; // [rsp+C8h] [rbp-78h] BYREF
  int v30; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-68h]
  __int64 *v32; // [rsp+E0h] [rbp-60h]
  __int64 v33; // [rsp+E8h] [rbp-58h]
  int v34; // [rsp+F0h] [rbp-50h]
  unsigned int *v35; // [rsp+F8h] [rbp-48h]

  v3 = a2;
  v32 = &qword_180078EE8;
  v28 = 0;
  v35 = (unsigned int *)&v28;
  v30 = 1;
  v31 = 0;
  v33 = 544438355;
  v34 = 3020;
  CFrame::BaseEnter((CFrame *)&v30);
  v6 = *((_QWORD *)this + 157);
  if ( v6 )
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 1300LL) == 2 )
    {
      *(_BYTE *)(v6 + 40) = 0;
    }
    else
    {
      v26 = 0;
      v27[0] = 0;
      v29 = 0;
      SetLastError(0);
      if ( !(unsigned int)SxspGetAttributeValue(
                            0,
                            (WCHAR **)qword_180079E50,
                            (__int64)a3,
                            v3,
                            (__int64)this + 400,
                            &v26,
                            1,
                            (__int64)v27,
                            &v29,
                            (unsigned int (__fastcall *)(_QWORD, void ***, char *, __int64, __int64, _QWORD *))SxspValidateBoolAttribute) )
      {
        *v35 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078EC8);
        goto LABEL_14;
      }
      if ( !v26 )
      {
        SetLastError(0x54Fu);
        *v35 = 0;
        goto LABEL_14;
      }
      if ( !v27[0] && (*(_BYTE *)(*((_QWORD *)this + 2) + 1204LL) & 2) == 0 )
      {
        FusionpDbgPrintEx(
          0xC0000000,
          "SXS.DLL: %s() app-level PublisherPolicy try to be set but there is no appcompat flags been set.\n",
          "CNodeFactory::XMLParser_Element_doc_configuration_windows_assemblyBinding_dependentAssembly_publisherPolicy");
        SetLastError(0x36B5u);
        goto LABEL_14;
      }
      *(_BYTE *)(*((_QWORD *)this + 157) + 40LL) = v27[0];
    }
    SetLastError(0);
    *v35 = 1;
    goto LABEL_14;
  }
  CNodeFactory::LogParseError(
    this,
    0xC1010036,
    0x89u,
    0,
    0,
    0,
    v9,
    v10,
    v11,
    v12,
    v13,
    v14,
    v15,
    v16,
    v17,
    v18,
    v19,
    v20,
    v21,
    v22,
    v23,
    v24,
    v25);
LABEL_14:
  v7 = *v35;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v30);
  return v7;
}

```

## disassembly

```asm
0x180065d30  mov     [rsp-8+arg_8], rbx
0x180065d35  push    rbp
0x180065d36  push    rsi
0x180065d37  push    rdi
0x180065d38  lea     rbp, [rsp+30h]
0x180065d3d  sub     rsp, 110h
0x180065d44  mov     rax, cs:__security_cookie
0x180065d4b  xor     rax, rsp
0x180065d4e  mov     [rbp-20h+var_20], rax
0x180065d52  lea     rax, qword_180078EE8
0x180065d59  movzx   edi, dx
0x180065d5c  mov     [rbp-20h+var_40], rax
0x180065d60  mov     rbx, rcx
0x180065d63  lea     rax, [rbp-20h+var_5C]
0x180065d67  mov     [rbp-20h+var_5C], 0
0x180065d6e  lea     rcx, [rbp-20h+var_50]; this
0x180065d72  mov     [rbp-20h+var_28], rax
0x180065d76  mov     rsi, r8
0x180065d79  mov     [rbp-20h+var_50], 1
0x180065d80  mov     [rbp-20h+var_48], 0
0x180065d88  mov     [rbp-20h+var_38], 20737853h
0x180065d90  mov     [rbp-20h+var_30], 0BCCh
0x180065d97  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180065d9c  mov     rcx, [rbx+4E8h]
0x180065da3  test    rcx, rcx
0x180065da6  jnz     short loc_180065DCD
0x180065da8  mov     [rsp+120h+var_F8], rcx; struct _UNICODE_STRING *
0x180065dad  xor     r9d, r9d; struct _UNICODE_STRING *
0x180065db0  mov     [rsp+120h+var_100], rcx; struct _UNICODE_STRING *
0x180065db5  mov     edx, 0C1010036h; unsigned int
0x180065dba  mov     rcx, rbx; this
0x180065dbd  mov     r8d, 89h; unsigned int
0x180065dc3  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180065dc8  jmp     loc_180065EF4
0x180065dcd  mov     rax, [rbx+10h]
0x180065dd1  cmp     dword ptr [rax+514h], 2
0x180065dd8  jnz     short loc_180065DE3
0x180065dda  mov     byte ptr [rcx+28h], 0
0x180065dde  jmp     loc_180065EDC
0x180065de3  xor     ecx, ecx; dwErrCode
0x180065de5  mov     [rbp-20h+var_60], 0
0x180065de9  mov     [rbp-20h+var_5F], 0
0x180065ded  mov     [rbp-20h+var_58], 0
0x180065df5  call    cs:__imp_SetLastError
0x180065dfc  nop     dword ptr [rax+rax+00h]
0x180065e01  lea     rcx, ?SxspValidateBoolAttribute@@YAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@AEA_N_KPEAXAEA_K@Z; SxspValidateBoolAttribute(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &)
0x180065e08  mov     r9, rdi
0x180065e0b  mov     [rsp+120h+var_D8], rcx
0x180065e10  lea     rax, [rbx+190h]
0x180065e17  lea     rcx, [rbp-20h+var_58]
0x180065e1b  mov     r8, rsi
0x180065e1e  mov     [rsp+120h+var_E0], rcx
0x180065e23  lea     rdx, qword_180079E50
0x180065e2a  lea     rcx, [rbp-20h+var_5F]
0x180065e2e  mov     [rsp+120h+var_E8], rcx
0x180065e33  lea     rcx, [rbp-20h+var_60]
0x180065e37  mov     [rsp+120h+var_F0], 1
0x180065e40  mov     [rsp+120h+var_F8], rcx
0x180065e45  xor     ecx, ecx
0x180065e47  mov     [rsp+120h+var_100], rax
0x180065e4c  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180065e51  test    eax, eax
0x180065e53  jnz     short loc_180065E70
0x180065e55  mov     rax, [rbp-20h+var_28]
0x180065e59  lea     rcx, off_180078EC8; struct _CALL_SITE_INFO *
0x180065e60  mov     dword ptr [rax], 0
0x180065e66  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180065e6b  jmp     loc_180065EF4
0x180065e70  cmp     [rbp-20h+var_60], 0
0x180065e74  jnz     short loc_180065E93
0x180065e76  mov     ecx, 54Fh; dwErrCode
0x180065e7b  call    cs:__imp_SetLastError
0x180065e82  nop     dword ptr [rax+rax+00h]
0x180065e87  mov     rax, [rbp-20h+var_28]
0x180065e8b  mov     dword ptr [rax], 0
0x180065e91  jmp     short loc_180065EF4
0x180065e93  mov     cl, [rbp-20h+var_5F]
0x180065e96  test    cl, cl
0x180065e98  jnz     short loc_180065ED2
0x180065e9a  mov     rax, [rbx+10h]
0x180065e9e  test    byte ptr [rax+4B4h], 2
0x180065ea5  jnz     short loc_180065ED2
0x180065ea7  lea     r8, aCnodefactoryXm_2; "CNodeFactory::XMLParser_Element_doc_con"...
0x180065eae  mov     ecx, 0C0000000h; unsigned int
0x180065eb3  lea     rdx, aSxsDllSAppLeve; "SXS.DLL: %s() app-level PublisherPolicy"...
0x180065eba  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180065ebf  mov     ecx, 36B5h; dwErrCode
0x180065ec4  call    cs:__imp_SetLastError
0x180065ecb  nop     dword ptr [rax+rax+00h]
0x180065ed0  jmp     short loc_180065EF4
0x180065ed2  mov     rax, [rbx+4E8h]
0x180065ed9  mov     [rax+28h], cl
0x180065edc  xor     ecx, ecx; dwErrCode
0x180065ede  call    cs:__imp_SetLastError
0x180065ee5  nop     dword ptr [rax+rax+00h]
0x180065eea  mov     rax, [rbp-20h+var_28]
0x180065eee  mov     dword ptr [rax], 1
0x180065ef4  mov     rax, [rbp-20h+var_28]
0x180065ef8  lea     rcx, [rbp-20h+var_50]; this
0x180065efc  mov     ebx, [rax]
0x180065efe  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180065f03  mov     eax, ebx
0x180065f05  mov     rcx, [rbp-20h+var_20]
0x180065f09  xor     rcx, rsp; StackCookie
0x180065f0c  call    __security_check_cookie
0x180065f11  mov     rbx, [rsp+120h+arg_8]
0x180065f19  add     rsp, 110h
0x180065f20  pop     rdi
0x180065f21  pop     rsi
0x180065f22  pop     rbp
0x180065f23  retn
```
