# CNodeFactory::ValidateIdentity(ulong,ulong,_ASSEMBLY_IDENTITY const *)

- ea: `0x1800419e4`
- end: `0x180041f01`
- name: `?ValidateIdentity@CNodeFactory@@QEAAHKKPEBU_ASSEMBLY_IDENTITY@@@Z`
- size: `1309`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned int, unsigned int, const struct _ASSEMBLY_IDENTITY *)`
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180040a30`
- `0x1800434a0`
- `0x180065520`
- `0x180065700`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x180011910`
- `0x180019740`
- `0x180022f90`
- `0x1800419e4`
- `0x1800515ec`
- `0x18005d2b0`
- `0x18005d38c`
- `0x18005d428`
- `0x180067548`
- `0x180067680`
- `0x180069df4`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x180041c03`
- `ntdll!RtlPopFrame` at `0x180041c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ee7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041a9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041ac9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041bd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041c81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041a9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041ac9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041b7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041bd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041c81`

## string_xrefs

- `0x180041cfb`: `SXS.DLL: Manifest "%ls" (line %d) has invalid type attribute "%wZ"; report to owner of "%ls"\n`
- `0x180041d39`: `SXS.DLL: Manifest "%ls" (line %d) is missing name attribute; report to owner of "%ls"\n`
- `0x180041e1e`: `SXS.DLL: Manifest "%ls" (line %d) has a version attribute where it may not appear; report to owner of "%ls"\n`
- `0x180041c45`: `SXS.DLL: Manifest "%ls" (line %d) is missing version attribute; report to owner of "%ls"\n`
- `0x180041e96`: `SXS.DLL: Manifest "%ls" is missing required attribute or contains disallowed attribute; report to owner of "%ls"\n`

## pseudocode

```c
__int64 __fastcall CNodeFactory::ValidateIdentity(
        CNodeFactory *this,
        int a2,
        int a3,
        const struct _ASSEMBLY_IDENTITY *a4)
{
  const char *v8; // rcx
  char v9; // r15
  unsigned __int64 v10; // rdi
  const unsigned __int16 *v11; // r12
  unsigned int v12; // ebx
  unsigned int v14; // edx
  unsigned int v15; // r8d
  char **v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  char **v19; // rcx
  __int16 v20; // ax
  DWORD LastError; // eax
  const struct _UNICODE_STRING *v22; // [rsp+30h] [rbp-110h]
  const struct _UNICODE_STRING *v23; // [rsp+38h] [rbp-108h]
  const struct _UNICODE_STRING *v24; // [rsp+40h] [rbp-100h]
  const struct _UNICODE_STRING *v25; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v26; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v27; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v28; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v29; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v30; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v31; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v32; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v33; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v34; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v35; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v36; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v37; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v38; // [rsp+B0h] [rbp-90h]
  bool v39; // [rsp+C0h] [rbp-80h] BYREF
  __int16 v40[4]; // [rsp+C8h] [rbp-78h] BYREF
  struct _UNICODE_STRING v41; // [rsp+D0h] [rbp-70h] BYREF
  int v42; // [rsp+E0h] [rbp-60h] BYREF
  struct _UNICODE_STRING v43; // [rsp+E8h] [rbp-58h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v45; // [rsp+110h] [rbp-30h]
  int v46; // [rsp+118h] [rbp-28h]
  unsigned int *v47; // [rsp+120h] [rbp-20h]
  int v48; // [rsp+128h] [rbp-18h] BYREF

  v45 = 544438355;
  v48 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_180071090;
  Frame.Previous = 0;
  v46 = 3709;
  Frame.Flags = 1;
  v47 = (unsigned int *)&v48;
  CFrame::BaseEnter((CFrame *)&Frame);
  *(_QWORD *)&v41.Length = 0;
  *(_QWORD *)v40 = 0;
  v39 = 0;
  v42 = 0;
  if ( (a2 & 0xFFFFFFF4) != 0 )
  {
    v46 = 3719;
    goto LABEL_25;
  }
  if ( (unsigned int)(a3 - 1) > 1 )
  {
    v46 = 3720;
    goto LABEL_25;
  }
  if ( !a4 )
  {
    v46 = 3721;
    goto LABEL_25;
  }
  if ( (a2 & 9) == 9 )
  {
    v46 = 3728;
LABEL_25:
    FusionpTraceParameterCheck(v8);
    SetLastError(0x57u);
    *v47 = 0;
    goto LABEL_20;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspDetermineAssemblyType(a4, &v42) )
  {
    v16 = off_180078B68;
    goto LABEL_27;
  }
  v9 = 0;
  if ( v42 )
  {
    **((_DWORD **)this + 49) |= 0x10u;
    if ( (a2 & 2) != 0 )
    {
      v17 = *((_QWORD *)this + 56);
      v18 = *((unsigned int *)this + 118);
      v9 = 1;
      v43.Buffer = 0;
      *(_DWORD *)&v43.Length = 0;
      FusionpDbgPrintEx(
        0xC0000000,
        "SXS.DLL: Manifest \"%ls\" (line %d) has invalid type attribute \"%wZ\"; report to owner of \"%ls\"\n",
        v17,
        v18,
        &v43,
        v17);
    }
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                        1u,
                        a4,
                        (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                        (const unsigned __int16 **)&v41,
                        (unsigned __int64 *)v40) )
  {
    v16 = off_180078B48;
    goto LABEL_27;
  }
  if ( !*(_QWORD *)v40 )
  {
    FusionpDbgPrintEx(
      0xC0000000,
      "SXS.DLL: Manifest \"%ls\" (line %d) is missing name attribute; report to owner of \"%ls\"\n",
      *((const wchar_t **)this + 56),
      *((_DWORD *)this + 118),
      *((const wchar_t **)this + 56));
    v9 = 1;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                        1u,
                        a4,
                        (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_processorArchitecture,
                        (const unsigned __int16 **)&v41,
                        (unsigned __int64 *)v40) )
  {
    v16 = off_180071230;
LABEL_27:
    *v47 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v16);
    goto LABEL_20;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                        1u,
                        a4,
                        (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_version,
                        (const unsigned __int16 **)&v41,
                        (unsigned __int64 *)v40) )
  {
    v16 = off_180078B28;
    goto LABEL_27;
  }
  v10 = *(_QWORD *)v40;
  if ( !*(_QWORD *)v40 )
    goto LABEL_15;
  *(_QWORD *)v40 = 0;
  SetLastError(0);
  v11 = *(const unsigned __int16 **)&v41.Length;
  if ( !(unsigned int)CFusionParser::ParseVersion(
                        (union _ASSEMBLY_VERSION *)v40,
                        *(const unsigned __int16 **)&v41.Length,
                        v10,
                        &v39) )
  {
    v16 = off_180078B08;
    goto LABEL_27;
  }
  if ( v39 )
  {
LABEL_15:
    if ( (a2 & 9) != 0 )
    {
      if ( (a2 & 8) != 0 && v10 )
      {
        FusionpDbgPrintEx(
          0xC0000000,
          "SXS.DLL: Manifest \"%ls\" (line %d) has a version attribute where it may not appear; report to owner of \"%ls\"\n",
          *((const wchar_t **)this + 56),
          *((_DWORD *)this + 118),
          *((const wchar_t **)this + 56));
        v14 = -1056899008;
        v15 = 122;
        goto LABEL_38;
      }
      if ( (a2 & 1) != 0 && !v10 )
      {
        FusionpDbgPrintEx(
          0xC0000000,
          "SXS.DLL: Manifest \"%ls\" (line %d) is missing version attribute; report to owner of \"%ls\"\n",
          *((const wchar_t **)this + 56),
          *((_DWORD *)this + 118),
          *((const wchar_t **)this + 56));
        v14 = -1056899010;
        v15 = 120;
LABEL_38:
        v43.Buffer = L"version";
        v41.Buffer = (PWSTR)*((_QWORD *)this + 52);
        v20 = *((_WORD *)this + 212);
        *(_DWORD *)&v43.Length = 917518;
        v41.Length = 2 * v20;
        v41.MaximumLength = 2 * v20;
        CNodeFactory::LogParseError(
          this,
          v14,
          v15,
          &v41,
          &v43,
          0,
          v22,
          v23,
          v24,
          v25,
          v26,
          v27,
          v28,
          v29,
          v30,
          v31,
          v32,
          v33,
          v34,
          v35,
          v36,
          v37,
          v38);
LABEL_39:
        FusionpDbgPrintEx(
          0xC0000000,
          "SXS.DLL: Manifest \"%ls\" is missing required attribute or contains disallowed attribute; report to owner of \"%ls\"\n",
          *((const wchar_t **)this + 56),
          *((const wchar_t **)this + 56));
        CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&Frame, 0x36B5u);
        v19 = off_180078AC8;
        goto LABEL_40;
      }
    }
    if ( !v9 )
    {
      SetLastError(0);
      *v47 = 1;
      goto LABEL_20;
    }
    goto LABEL_39;
  }
  FusionpLogInvalidAttributeValueParseError(
    *(const unsigned __int16 **)(*((_QWORD *)this + 2) + 1312LL),
    *((const unsigned __int16 **)this + 56),
    *((_QWORD *)this + 57),
    *((_DWORD *)this + 118),
    *((const unsigned __int16 **)this + 52),
    *((_QWORD *)this + 53),
    L"version",
    7,
    v11,
    v10);
  TraceActCtxGenManifestParseError(
    *(_DWORD *)(*((_QWORD *)this + 2) + 1304LL),
    *((unsigned int *)this + 118),
    *((const unsigned __int16 **)this + 52),
    L"version",
    v11,
    0x79u);
  CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&Frame, 0x36B5u);
  v19 = off_180078AE8;
LABEL_40:
  FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v19);
LABEL_20:
  v12 = *v47;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( v12 )
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
  return v12;
}

```

## disassembly

```asm
0x1800419e4  mov     [rsp-38h+arg_8], rbx
0x1800419e9  push    rbp
0x1800419ea  push    rsi
0x1800419eb  push    rdi
0x1800419ec  push    r12
0x1800419ee  push    r13
0x1800419f0  push    r14
0x1800419f2  push    r15
0x1800419f4  mov     rbp, rsp
0x1800419f7  sub     rsp, 140h
0x1800419fe  mov     rax, cs:__security_cookie
0x180041a05  xor     rax, rsp
0x180041a08  mov     [rbp+var_10], rax
0x180041a0c  xor     r13d, r13d
0x180041a0f  mov     [rbp+var_30], 20737853h
0x180041a17  lea     rax, qword_180071090
0x180041a1e  mov     [rbp+var_18], r13d
0x180041a22  mov     [rbp+Frame.Context], rax
0x180041a26  mov     rbx, rcx
0x180041a29  lea     rax, [rbp+var_18]
0x180041a2d  mov     [rbp+Frame.Previous], r13
0x180041a31  lea     r12d, [r13+1]
0x180041a35  mov     [rbp+var_28], 0E7Dh
0x180041a3c  lea     rcx, [rbp+Frame]; this
0x180041a40  mov     [rbp+Frame.Flags], r12d
0x180041a44  mov     rdi, r9
0x180041a47  mov     [rbp+var_20], rax
0x180041a4b  mov     r14d, r8d
0x180041a4e  mov     esi, edx
0x180041a50  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180041a55  mov     qword ptr [rbp+var_70.Length], r13
0x180041a59  mov     qword ptr [rbp+var_78], r13
0x180041a5d  mov     [rbp+var_80], r13b
0x180041a61  mov     [rbp+var_60], r13d
0x180041a65  test    esi, 0FFFFFFF4h
0x180041a6b  jnz     loc_180041CB1
0x180041a71  lea     eax, [r14-1]
0x180041a75  cmp     eax, r12d
0x180041a78  ja      loc_180041CBA
0x180041a7e  test    rdi, rdi
0x180041a81  jz      loc_180041CC3
0x180041a87  mov     r14d, esi
0x180041a8a  and     r14d, 9
0x180041a8e  cmp     r14d, 9
0x180041a92  jz      loc_180041C70
0x180041a98  xor     ecx, ecx; dwErrCode
0x180041a9a  call    cs:__imp_SetLastError
0x180041aa1  nop     dword ptr [rax+rax+00h]
0x180041aa6  lea     rdx, [rbp+var_60]; int *
0x180041aaa  mov     rcx, rdi; struct _ASSEMBLY_IDENTITY *
0x180041aad  call    ?SxspDetermineAssemblyType@@YAHPEBU_ASSEMBLY_IDENTITY@@AEAH@Z; SxspDetermineAssemblyType(_ASSEMBLY_IDENTITY const *,int &)
0x180041ab2  test    eax, eax
0x180041ab4  jz      loc_180041CCC
0x180041aba  mov     r15b, r13b
0x180041abd  cmp     [rbp+var_60], r13d
0x180041ac1  jnz     loc_180041CD5
0x180041ac7  xor     ecx, ecx; dwErrCode
0x180041ac9  call    cs:__imp_SetLastError
0x180041ad0  nop     dword ptr [rax+rax+00h]
0x180041ad5  lea     rax, [rbp+var_78]
0x180041ad9  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x180041adc  lea     r9, [rbp+var_70]; unsigned __int16 **
0x180041ae0  mov     [rsp+140h+var_120], rax; unsigned __int64 *
0x180041ae5  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180041aec  mov     ecx, r12d; unsigned int
0x180041aef  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180041af4  test    eax, eax
0x180041af6  jz      loc_180041D26
0x180041afc  cmp     qword ptr [rbp+var_78], r13
0x180041b00  jz      loc_180041D32
0x180041b06  xor     ecx, ecx; dwErrCode
0x180041b08  call    cs:__imp_SetLastError
0x180041b0f  nop     dword ptr [rax+rax+00h]
0x180041b14  lea     rax, [rbp+var_78]
0x180041b18  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x180041b1b  lea     r9, [rbp+var_70]; unsigned __int16 **
0x180041b1f  mov     [rsp+140h+var_120], rax; unsigned __int64 *
0x180041b24  lea     r8, s_IdentityAttribute_processorArchitecture; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180041b2b  mov     ecx, r12d; unsigned int
0x180041b2e  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180041b33  test    eax, eax
0x180041b35  jz      loc_180041C99
0x180041b3b  xor     ecx, ecx; dwErrCode
0x180041b3d  call    cs:__imp_SetLastError
0x180041b44  nop     dword ptr [rax+rax+00h]
0x180041b49  lea     rax, [rbp+var_78]
0x180041b4d  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x180041b50  lea     r9, [rbp+var_70]; unsigned __int16 **
0x180041b54  mov     [rsp+140h+var_120], rax; unsigned __int64 *
0x180041b59  lea     r8, s_IdentityAttribute_version; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180041b60  mov     ecx, r12d; unsigned int
0x180041b63  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180041b68  test    eax, eax
0x180041b6a  jz      loc_180041D5E
0x180041b70  mov     rdi, qword ptr [rbp+var_78]
0x180041b74  test    rdi, rdi
0x180041b77  jz      short loc_180041BBA
0x180041b79  xor     ecx, ecx; dwErrCode
0x180041b7b  mov     qword ptr [rbp+var_78], r13
0x180041b7f  call    cs:__imp_SetLastError
0x180041b86  nop     dword ptr [rax+rax+00h]
0x180041b8b  mov     r12, qword ptr [rbp+var_70.Length]
0x180041b8f  lea     r9, [rbp+var_80]; bool *
0x180041b93  mov     rdx, r12; unsigned __int16 *
0x180041b96  lea     rcx, [rbp+var_78]; union _ASSEMBLY_VERSION *
0x180041b9a  mov     r8, rdi; unsigned __int64
0x180041b9d  call    ?ParseVersion@CFusionParser@@SAHAEAT_ASSEMBLY_VERSION@@PEBG_KAEA_N@Z; CFusionParser::ParseVersion(_ASSEMBLY_VERSION &,ushort const *,unsigned __int64,bool &)
0x180041ba2  test    eax, eax
0x180041ba4  jz      loc_180041D6A
0x180041baa  cmp     [rbp+var_80], r13b
0x180041bae  jz      loc_180041D76
0x180041bb4  mov     r12d, 1
0x180041bba  test    r14d, r14d
0x180041bbd  jz      short loc_180041BCE
0x180041bbf  test    sil, 8
0x180041bc3  jnz     loc_180041EC9
0x180041bc9  test    r12b, sil
0x180041bcc  jnz     short loc_180041C39
0x180041bce  test    r15b, r15b
0x180041bd1  jnz     loc_180041E8F
0x180041bd7  xor     ecx, ecx; dwErrCode
0x180041bd9  call    cs:__imp_SetLastError
0x180041be0  nop     dword ptr [rax+rax+00h]
0x180041be5  mov     rax, [rbp+var_20]
0x180041be9  mov     [rax], r12d
0x180041bec  cmp     cs:g_FusionEnterExitTracingEnabled, r13b
0x180041bf3  mov     rax, [rbp+var_20]
0x180041bf7  mov     ebx, [rax]
0x180041bf9  jnz     loc_180041ED7
0x180041bff  lea     rcx, [rbp+Frame]; Frame
0x180041c03  call    cs:__imp_RtlPopFrame
0x180041c0a  nop     dword ptr [rax+rax+00h]
0x180041c0f  mov     eax, ebx
0x180041c11  mov     rcx, [rbp+var_10]
0x180041c15  xor     rcx, rsp; StackCookie
0x180041c18  call    __security_check_cookie
0x180041c1d  mov     rbx, [rsp+140h+arg_8]
0x180041c25  add     rsp, 140h
0x180041c2c  pop     r15
0x180041c2e  pop     r14
0x180041c30  pop     r13
0x180041c32  pop     r12
0x180041c34  pop     rdi
0x180041c35  pop     rsi
0x180041c36  pop     rbp
0x180041c37  retn
0x180041c39  test    rdi, rdi
0x180041c3c  jnz     short loc_180041BCE
0x180041c3e  mov     r8, [rbx+1C0h]
0x180041c45  lea     rdx, aSxsDllManifest_1; "SXS.DLL: Manifest \"%ls\" (line %d) is "...
0x180041c4c  mov     r9d, [rbx+1D8h]
0x180041c53  mov     ecx, 0C0000000h; unsigned int
0x180041c58  mov     [rsp+140h+var_120], r8
0x180041c5d  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180041c62  mov     edx, 0C101003Eh
0x180041c67  lea     r8d, [rdi+78h]
0x180041c6b  jmp     loc_180041E46
0x180041c70  mov     [rbp+var_28], 0E90h
0x180041c77  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180041c7c  mov     ecx, 57h ; 'W'; dwErrCode
0x180041c81  call    cs:__imp_SetLastError
0x180041c88  nop     dword ptr [rax+rax+00h]
0x180041c8d  mov     rax, [rbp+var_20]
0x180041c91  mov     [rax], r13d
0x180041c94  jmp     loc_180041BEC
0x180041c99  lea     rcx, off_180071230; struct _CALL_SITE_INFO *
0x180041ca0  mov     rax, [rbp+var_20]
0x180041ca4  mov     [rax], r13d
0x180041ca7  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180041cac  jmp     loc_180041BEC
0x180041cb1  mov     [rbp+var_28], 0E87h
0x180041cb8  jmp     short loc_180041C77
0x180041cba  mov     [rbp+var_28], 0E88h
0x180041cc1  jmp     short loc_180041C77
0x180041cc3  mov     [rbp+var_28], 0E89h
0x180041cca  jmp     short loc_180041C77
0x180041ccc  lea     rcx, off_180078B68; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180041cd3  jmp     short loc_180041CA0
0x180041cd5  mov     rax, [rbx+188h]
0x180041cdc  or      dword ptr [rax], 10h
0x180041cdf  test    sil, 2
0x180041ce3  jz      loc_180041AC7
0x180041ce9  mov     r8, [rbx+1C0h]
0x180041cf0  lea     rax, [rbp+var_58]
0x180041cf4  mov     r9d, [rbx+1D8h]
0x180041cfb  lea     rdx, aSxsDllManifest_4; "SXS.DLL: Manifest \"%ls\" (line %d) has"...
0x180041d02  mov     [rsp+140h+var_118], r8
0x180041d07  mov     ecx, 0C0000000h; unsigned int
0x180041d0c  mov     [rsp+140h+var_120], rax
0x180041d11  mov     r15b, r12b
0x180041d14  mov     [rbp+var_58.Buffer], r13
0x180041d18  mov     dword ptr [rbp+var_58.Length], r13d
0x180041d1c  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180041d21  jmp     loc_180041AC7
0x180041d26  lea     rcx, off_180078B48; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180041d2d  jmp     loc_180041CA0
0x180041d32  mov     r8, [rbx+1C0h]
0x180041d39  lea     rdx, aSxsDllManifest; "SXS.DLL: Manifest \"%ls\" (line %d) is "...
0x180041d40  mov     r9d, [rbx+1D8h]
0x180041d47  mov     ecx, 0C0000000h; unsigned int
0x180041d4c  mov     [rsp+140h+var_120], r8
0x180041d51  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180041d56  mov     r15b, r12b
0x180041d59  jmp     loc_180041B06
0x180041d5e  lea     rcx, off_180078B28; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180041d65  jmp     loc_180041CA0
0x180041d6a  lea     rcx, off_180078B08; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180041d71  jmp     loc_180041CA0
0x180041d76  mov     rax, [rbx+1A8h]
0x180041d7d  mov     rcx, [rbx+10h]
0x180041d81  mov     r9d, [rbx+1D8h]; unsigned int
0x180041d88  mov     r8, [rbx+1C8h]; unsigned __int64
0x180041d8f  mov     rdx, [rbx+1C0h]; unsigned __int16 *
0x180041d96  mov     rcx, [rcx+520h]; unsigned __int16 *
0x180041d9d  mov     qword ptr [rsp+140h+var_F8], rdi; __int16
0x180041da2  lea     rdi, aVersion; "version"
0x180041da9  mov     [rsp+140h+var_100], r12; unsigned __int16 *
0x180041dae  mov     qword ptr [rsp+140h+var_108], 7; __int16
0x180041db7  mov     [rsp+140h+var_110], rdi; unsigned __int16 *
0x180041dbc  mov     [rsp+140h+var_118], rax; __int16
0x180041dc1  mov     rax, [rbx+1A0h]
0x180041dc8  mov     [rsp+140h+var_120], rax; unsigned __int16 *
0x180041dcd  call    ?FusionpLogInvalidAttributeValueParseError@@YAXPEBG0_KK010101@Z; FusionpLogInvalidAttributeValueParseError(ushort const *,ushort const *,unsigned __int64,ulong,ushort const *,unsigned __int64,ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180041dd2  mov     rcx, [rbx+10h]
0x180041dd6  mov     r9, rdi; unsigned __int16 *
0x180041dd9  mov     r8, [rbx+1A0h]; unsigned __int16 *
0x180041de0  mov     edx, [rbx+1D8h]; unsigned int
0x180041de6  mov     word ptr [rsp+140h+var_118], 79h ; 'y'; unsigned __int16
0x180041ded  mov     ecx, [rcx+518h]; int
0x180041df3  mov     [rsp+140h+var_120], r12; unsigned __int16 *
0x180041df8  call    ?TraceActCtxGenManifestParseError@@YAKJKPEBG00G@Z; TraceActCtxGenManifestParseError(long,ulong,ushort const *,ushort const *,ushort const *,ushort)
0x180041dfd  mov     edx, 36B5h; unsigned int
0x180041e02  lea     rcx, [rbp+Frame]; this
0x180041e06  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180041e0b  lea     rcx, off_180078AE8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180041e12  jmp     loc_180041EBF
0x180041e17  mov     r8, [rbx+1C0h]
0x180041e1e  lea     rdx, aSxsDllManifest_0; "SXS.DLL: Manifest \"%ls\" (line %d) has"...
0x180041e25  mov     r9d, [rbx+1D8h]
0x180041e2c  mov     ecx, 0C0000000h; unsigned int
0x180041e31  mov     [rsp+140h+var_120], r8
0x180041e36  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180041e3b  mov     edx, 0C1010040h; unsigned int
0x180041e40  mov     r8d, 7Ah ; 'z'; unsigned int
0x180041e46  lea     rax, aVersion_0; "version"
0x180041e4d  mov     [rsp+140h+var_118], r13; struct _UNICODE_STRING *
0x180041e52  mov     [rbp+var_58.Buffer], rax
0x180041e56  lea     r9, [rbp+var_70]; struct _UNICODE_STRING *
0x180041e5a  mov     rax, [rbx+1A0h]
0x180041e61  mov     rcx, rbx; this
0x180041e64  mov     [rbp+var_70.Buffer], rax
0x180041e68  movzx   eax, word ptr [rbx+1A8h]
0x180041e6f  add     ax, ax
0x180041e72  mov     dword ptr [rbp+var_58.Length], 0E000Eh
0x180041e79  mov     [rbp+var_70.Length], ax
0x180041e7d  mov     [rbp+var_70.MaximumLength], ax
0x180041e81  lea     rax, [rbp+var_58]
0x180041e85  mov     [rsp+140h+var_120], rax; struct _UNICODE_STRING *
0x180041e8a  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180041e8f  mov     r8, [rbx+1C0h]
0x180041e96  lea     rdx, aSxsDllManifest_2; "SXS.DLL: Manifest \"%ls\" is missing re"...
0x180041e9d  mov     r9, r8
0x180041ea0  mov     ecx, 0C0000000h; unsigned int
0x180041ea5  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180041eaa  mov     edx, 36B5h; unsigned int
0x180041eaf  lea     rcx, [rbp+Frame]; this
0x180041eb3  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180041eb8  lea     rcx, off_180078AC8; struct _CALL_SITE_INFO *
0x180041ebf  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180041ec4  jmp     loc_180041BEC
0x180041ec9  test    rdi, rdi
0x180041ecc  jz      loc_180041BC9
0x180041ed2  jmp     loc_180041E17
0x180041ed7  test    ebx, ebx
0x180041ed9  jz      short loc_180041EE7
0x180041edb  xor     ecx, ecx; char *
0x180041edd  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x180041ee2  jmp     loc_180041BFF
0x180041ee7  call    cs:__imp_GetLastError
0x180041eee  nop     dword ptr [rax+rax+00h]
0x180041ef3  mov     ecx, eax; unsigned int
0x180041ef5  xor     edx, edx; Format
0x180041ef7  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x180041efc  jmp     loc_180041BFF
```
