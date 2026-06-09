# CNodeFactory::XMLParser_Element_doc_assembly_msix(ushort,_SXS_NODE_INFO const *)

- ea: `0x180055cf0`
- end: `0x180056285`
- name: `?XMLParser_Element_doc_assembly_msix@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `1429`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180020820`
- `0x180027160`
- `0x180029380`
- `0x1800515ec`
- `0x180055cf0`
- `0x18005d38c`
- `0x18005d5cc`
- `0x18006a0f5`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055e3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055ec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055fa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055fef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005617e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055e3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055ec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055f3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055fa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055fef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005617e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055fbd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055fbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056005`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056005`
- `KERNEL32!FormatApplicationUserModelId` at `0x1800560ef`
- `KERNEL32!FormatApplicationUserModelId` at `0x1800560ef`
- `KERNEL32!PackageFamilyNameFromId` at `0x18005608a`
- `KERNEL32!PackageFamilyNameFromId` at `0x18005608a`

## string_xrefs

- `0x180055fb4`: `KernelBase.dll`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_msix(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned __int64 v3; // rsi
  _BYTE *v6; // rax
  char **v7; // rcx
  char **v8; // rcx
  HMODULE Library; // rax
  HMODULE v10; // rdi
  FARPROC ProcAddress; // rax
  WCHAR *v12; // r9
  unsigned int v13; // ebx
  struct _UNICODE_STRING *v15; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v16; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v17; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v18; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v19; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v20; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v21; // [rsp+48h] [rbp-F8h]
  struct _UNICODE_STRING *v22; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v23; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v24; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v25; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v26; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v27; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v28; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v29; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v30; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v31; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v32; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v33; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v34; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v35; // [rsp+B0h] [rbp-90h]
  _BYTE v36[8]; // [rsp+C0h] [rbp-80h] BYREF
  HMODULE v37; // [rsp+C8h] [rbp-78h] BYREF
  PACKAGE_ID packageId; // [rsp+D0h] [rbp-70h] BYREF
  int v39; // [rsp+100h] [rbp-40h] BYREF
  struct _UNICODE_STRING v40; // [rsp+108h] [rbp-38h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+118h] [rbp-28h] BYREF
  int v42; // [rsp+120h] [rbp-20h] BYREF
  __int64 v43; // [rsp+128h] [rbp-18h]
  __int64 *v44; // [rsp+130h] [rbp-10h]
  __int64 v45; // [rsp+138h] [rbp-8h]
  int v46; // [rsp+140h] [rbp+0h]
  int *v47; // [rsp+148h] [rbp+8h]
  struct _UNICODE_STRING v48; // [rsp+150h] [rbp+10h] BYREF
  PCWSTR packageRelativeApplicationId; // [rsp+160h] [rbp+20h]
  __int64 v50; // [rsp+168h] [rbp+28h]
  char v51; // [rsp+178h] [rbp+38h] BYREF
  _QWORD v52[2]; // [rsp+200h] [rbp+C0h] BYREF
  WCHAR *v53; // [rsp+210h] [rbp+D0h]
  __int64 v54; // [rsp+218h] [rbp+D8h]
  char v55; // [rsp+228h] [rbp+E8h] BYREF
  _QWORD v56[2]; // [rsp+2B0h] [rbp+170h] BYREF
  WCHAR *v57; // [rsp+2C0h] [rbp+180h]
  __int64 v58; // [rsp+2C8h] [rbp+188h]
  char v59; // [rsp+2D8h] [rbp+198h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+4E0h] [rbp+3A0h] BYREF

  v3 = a2;
  v39 = 0;
  v44 = &qword_180072728;
  v43 = 0;
  v45 = 544438355;
  v42 = 1;
  v46 = 3390;
  v47 = &v39;
  CFrame::BaseEnter((CFrame *)&v42);
  *(_QWORD *)&v40.Length = 0;
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v56);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v52);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(&v48);
  v6 = (_BYTE *)*((_QWORD *)this + 49);
  memset(&packageId, 0, sizeof(packageId));
  v37 = 0;
  if ( (*v6 & 4) == 0 )
  {
    CNodeFactory::LogParseError(
      this,
      0xC1010055,
      0x9Du,
      0,
      0,
      0,
      v15,
      v17,
      v19,
      v21,
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
      v35);
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v42, 0x36B5u);
    v7 = off_180078C88;
LABEL_3:
    FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v7);
    goto LABEL_29;
  }
  if ( *(_WORD *)(*((_QWORD *)this + 2) + 4320LL) )
  {
    CNodeFactory::LogParseError(
      this,
      0xC1010056,
      0x9Eu,
      0,
      0,
      0,
      v15,
      v17,
      v19,
      v21,
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
      v35);
    CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v42, 0x36B5u);
    v7 = off_180078C68;
    goto LABEL_3;
  }
  *(_QWORD *)&v40.Length = 0;
  v36[0] = 0;
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (WCHAR **)qword_180072768,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        v36,
                        560,
                        (__int64)v56,
                        &v40,
                        0) )
  {
    v8 = off_180078C48;
LABEL_8:
    *v47 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v8);
    goto LABEL_29;
  }
  if ( !v36[0] )
    goto LABEL_28;
  *(_QWORD *)&v40.Length = 0;
  v36[0] = 0;
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (WCHAR **)qword_180072748,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        v36,
                        168,
                        (__int64)v52,
                        &v40,
                        0) )
  {
    v8 = off_180078C28;
    goto LABEL_8;
  }
  if ( !v36[0] )
    goto LABEL_28;
  *(_QWORD *)&v40.Length = 0;
  v36[0] = 0;
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        1,
                        (WCHAR **)qword_180072788,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        v36,
                        168,
                        (__int64)&v48,
                        &v40,
                        0) )
  {
    v8 = off_180078C08;
    goto LABEL_8;
  }
  if ( v36[0] )
  {
    SetLastError(0);
    Library = LoadLibraryExW(L"KernelBase.dll", 0, 0);
    v10 = Library;
    if ( !Library )
    {
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)`CDynamicLinkLibrary::Win32LoadLibrary'::`7'::__callsite);
      v8 = off_180078BE8;
      goto LABEL_8;
    }
    v37 = Library;
    SetLastError(0);
    ProcAddress = GetProcAddress(v10, "VerifyPackagePublisher");
    if ( !ProcAddress )
    {
      v8 = off_1800727A8;
      goto LABEL_8;
    }
    LODWORD(v40.Buffer) = 0;
    if ( ((unsigned int (__fastcall *)(WCHAR *, PWSTR *))ProcAddress)(v57, &v40.Buffer) || LODWORD(v40.Buffer) != 1 )
    {
      CNodeFactory::LogParseError(
        this,
        0xC1010057,
        0x9Fu,
        0,
        0,
        0,
        v16,
        v18,
        v20,
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
        v35);
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v42, 0x36B5u);
      v7 = off_180078BC8;
      goto LABEL_3;
    }
    packageId.publisher = v57;
    packageId.name = v53;
    memset_0(packageFamilyName, 0, 0x82u);
    HIDWORD(v40.Buffer) = 65;
    if ( PackageFamilyNameFromId(&packageId, (UINT32 *)&v40.Buffer + 1, packageFamilyName) )
    {
      CNodeFactory::LogParseError(
        this,
        0xC1010058,
        0xA0u,
        0,
        0,
        0,
        v16,
        v18,
        v20,
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
        v35);
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v42, 0x36B5u);
      v7 = off_180078BA8;
      goto LABEL_3;
    }
    v12 = (WCHAR *)(*((_QWORD *)this + 2) + 4320LL);
    applicationUserModelIdLength = 130;
    if ( FormatApplicationUserModelId(
           packageFamilyName,
           packageRelativeApplicationId,
           &applicationUserModelIdLength,
           v12) )
    {
      CNodeFactory::LogParseError(
        this,
        0xC1010059,
        0xA1u,
        0,
        0,
        0,
        v16,
        v18,
        v20,
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
        v35);
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v42, 0x36B5u);
      v7 = off_180078B88;
      goto LABEL_3;
    }
    v39 = 1;
  }
  else
  {
LABEL_28:
    SetLastError(0x54Fu);
    *v47 = 0;
  }
LABEL_29:
  v13 = v39;
  CHandleTemplate<&void * hNull,COperatorFreeLibrary>::~CHandleTemplate<&void * hNull,COperatorFreeLibrary>(&v37);
  *(_QWORD *)&v48.Length = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( packageRelativeApplicationId != (PCWSTR)&v51 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v48);
  packageRelativeApplicationId = 0;
  v50 = 0;
  *(_QWORD *)&v48.Length = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  v52[0] = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v53 != (WCHAR *)&v55 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v52);
  v56[0] = &CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable';
  v53 = 0;
  v54 = 0;
  v52[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  if ( v57 != (WCHAR *)&v59 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(v56);
  v57 = 0;
  v58 = 0;
  v56[0] = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v42);
  return v13;
}

```

## disassembly

```asm
0x180055cf0  mov     [rsp-8+arg_8], rbx
0x180055cf5  mov     [rsp-8+arg_18], rsi
0x180055cfa  push    rbp
0x180055cfb  push    rdi
0x180055cfc  push    r12
0x180055cfe  push    r14
0x180055d00  push    r15
0x180055d02  lea     rbp, [rsp-440h]
0x180055d0a  sub     rsp, 580h
0x180055d11  mov     rax, cs:__security_cookie
0x180055d18  xor     rax, rsp
0x180055d1b  mov     [rbp+460h+var_30], rax
0x180055d22  xor     r15d, r15d
0x180055d25  movzx   esi, dx
0x180055d28  lea     rax, qword_180072728
0x180055d2f  mov     [rbp+460h+var_4A0], r15d
0x180055d33  mov     [rbp+460h+var_470], rax
0x180055d37  mov     rbx, rcx
0x180055d3a  lea     rax, [rbp+460h+var_4A0]
0x180055d3e  mov     [rbp+460h+var_478], r15
0x180055d42  lea     r12d, [r15+1]
0x180055d46  mov     [rbp+460h+var_468], 20737853h
0x180055d4e  lea     rcx, [rbp+460h+var_480]; this
0x180055d52  mov     [rbp+460h+var_480], r12d
0x180055d56  mov     r14, r8
0x180055d59  mov     [rbp+460h+var_460], 0D3Eh
0x180055d60  mov     [rbp+460h+var_458], rax
0x180055d64  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180055d69  lea     rcx, [rbp+460h+var_2F0]; void *
0x180055d70  mov     qword ptr [rbp+460h+var_498.Length], r15
0x180055d74  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180055d79  lea     rcx, [rbp+460h+var_3A0]
0x180055d80  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180055d85  lea     rcx, [rbp+460h+var_450]
0x180055d89  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180055d8e  mov     rax, [rbx+188h]
0x180055d95  xorps   xmm0, xmm0
0x180055d98  movups  xmmword ptr [rbp+460h+packageId.reserved], xmm0
0x180055d9c  mov     [rbp+460h+var_4D8], r15
0x180055da0  movups  xmmword ptr [rbp+460h+packageId.name], xmm0
0x180055da4  movups  xmmword ptr [rbp+460h+packageId.resourceId], xmm0
0x180055da8  test    byte ptr [rax], 4
0x180055dab  jnz     short loc_180055DEC
0x180055dad  mov     [rsp+5A0h+var_578], r15; struct _UNICODE_STRING *
0x180055db2  xor     r9d, r9d; struct _UNICODE_STRING *
0x180055db5  mov     edx, 0C1010055h; unsigned int
0x180055dba  mov     [rsp+5A0h+var_580], r15; struct _UNICODE_STRING *
0x180055dbf  mov     r8d, 9Dh; unsigned int
0x180055dc5  mov     rcx, rbx; this
0x180055dc8  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180055dcd  mov     edx, 36B5h; unsigned int
0x180055dd2  lea     rcx, [rbp+460h+var_480]; this
0x180055dd6  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180055ddb  lea     rcx, off_180078C88; struct _CALL_SITE_INFO *
0x180055de2  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180055de7  jmp     loc_180056191
0x180055dec  mov     rax, [rbx+10h]
0x180055df0  cmp     [rax+10E0h], r15w
0x180055df8  jz      short loc_180055E31
0x180055dfa  mov     [rsp+5A0h+var_578], r15; struct _UNICODE_STRING *
0x180055dff  xor     r9d, r9d; struct _UNICODE_STRING *
0x180055e02  mov     edx, 0C1010056h; unsigned int
0x180055e07  mov     [rsp+5A0h+var_580], r15; struct _UNICODE_STRING *
0x180055e0c  mov     r8d, 9Eh; unsigned int
0x180055e12  mov     rcx, rbx; this
0x180055e15  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180055e1a  mov     edx, 36B5h; unsigned int
0x180055e1f  lea     rcx, [rbp+460h+var_480]; this
0x180055e23  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180055e28  lea     rcx, off_180078C68; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180055e2f  jmp     short loc_180055DE2
0x180055e31  xor     ecx, ecx; dwErrCode
0x180055e33  mov     qword ptr [rbp+460h+var_498.Length], r15
0x180055e37  mov     [rbp+460h+var_4E0], r15b
0x180055e3b  call    cs:__imp_SetLastError
0x180055e42  nop     dword ptr [rax+rax+00h]
0x180055e47  mov     [rsp+5A0h+var_558], r15
0x180055e4c  lea     rax, [rbp+460h+var_498]
0x180055e50  mov     [rsp+5A0h+var_560], rax
0x180055e55  lea     rdi, [rbx+190h]
0x180055e5c  lea     rax, [rbp+460h+var_2F0]
0x180055e63  mov     r9, rsi
0x180055e66  mov     [rsp+5A0h+var_568], rax
0x180055e6b  lea     rdx, qword_180072768
0x180055e72  lea     rax, [rbp+460h+var_4E0]
0x180055e76  mov     [rsp+5A0h+var_570], 230h
0x180055e7f  mov     [rsp+5A0h+var_578], rax
0x180055e84  mov     r8, r14
0x180055e87  mov     ecx, r12d
0x180055e8a  mov     [rsp+5A0h+var_580], rdi
0x180055e8f  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180055e94  test    eax, eax
0x180055e96  jnz     short loc_180055EB0
0x180055e98  lea     rcx, off_180078C48; struct _CALL_SITE_INFO *
0x180055e9f  mov     rax, [rbp+460h+var_458]
0x180055ea3  mov     [rax], r15d
0x180055ea6  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180055eab  jmp     loc_180056191
0x180055eb0  cmp     [rbp+460h+var_4E0], r15b
0x180055eb4  jz      loc_180056179
0x180055eba  xor     ecx, ecx; dwErrCode
0x180055ebc  mov     qword ptr [rbp+460h+var_498.Length], r15
0x180055ec0  mov     [rbp+460h+var_4E0], r15b
0x180055ec4  call    cs:__imp_SetLastError
0x180055ecb  nop     dword ptr [rax+rax+00h]
0x180055ed0  mov     [rsp+5A0h+var_558], r15
0x180055ed5  lea     rax, [rbp+460h+var_498]
0x180055ed9  mov     [rsp+5A0h+var_560], rax
0x180055ede  lea     rdx, qword_180072748
0x180055ee5  lea     rax, [rbp+460h+var_3A0]
0x180055eec  mov     r9, rsi
0x180055eef  mov     [rsp+5A0h+var_568], rax
0x180055ef4  mov     r8, r14
0x180055ef7  lea     rax, [rbp+460h+var_4E0]
0x180055efb  mov     [rsp+5A0h+var_570], 0A8h
0x180055f04  mov     [rsp+5A0h+var_578], rax
0x180055f09  mov     ecx, r12d
0x180055f0c  mov     [rsp+5A0h+var_580], rdi
0x180055f11  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180055f16  test    eax, eax
0x180055f18  jnz     short loc_180055F26
0x180055f1a  lea     rcx, off_180078C28; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180055f21  jmp     loc_180055E9F
0x180055f26  cmp     [rbp+460h+var_4E0], r15b
0x180055f2a  jz      loc_180056179
0x180055f30  xor     ecx, ecx; dwErrCode
0x180055f32  mov     qword ptr [rbp+460h+var_498.Length], r15
0x180055f36  mov     [rbp+460h+var_4E0], r15b
0x180055f3a  call    cs:__imp_SetLastError
0x180055f41  nop     dword ptr [rax+rax+00h]
0x180055f46  mov     [rsp+5A0h+var_558], r15; struct _UNICODE_STRING *
0x180055f4b  lea     rax, [rbp+460h+var_498]
0x180055f4f  mov     [rsp+5A0h+var_560], rax; struct _UNICODE_STRING *
0x180055f54  lea     rdx, qword_180072788
0x180055f5b  lea     rax, [rbp+460h+var_450]
0x180055f5f  mov     r9, rsi
0x180055f62  mov     [rsp+5A0h+var_568], rax; struct _UNICODE_STRING *
0x180055f67  mov     r8, r14
0x180055f6a  lea     rax, [rbp+460h+var_4E0]
0x180055f6e  mov     [rsp+5A0h+var_570], 0A8h; struct _UNICODE_STRING *
0x180055f77  mov     [rsp+5A0h+var_578], rax
0x180055f7c  mov     ecx, r12d
0x180055f7f  mov     [rsp+5A0h+var_580], rdi
0x180055f84  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x180055f89  test    eax, eax
0x180055f8b  jnz     short loc_180055F99
0x180055f8d  lea     rcx, off_180078C08; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180055f94  jmp     loc_180055E9F
0x180055f99  cmp     [rbp+460h+var_4E0], r15b
0x180055f9d  jz      loc_180056179
0x180055fa3  xor     ecx, ecx; dwErrCode
0x180055fa5  call    cs:__imp_SetLastError
0x180055fac  nop     dword ptr [rax+rax+00h]
0x180055fb1  xor     r8d, r8d; dwFlags
0x180055fb4  lea     rcx, LibFileName; "KernelBase.dll"
0x180055fbb  xor     edx, edx; hFile
0x180055fbd  call    cs:__imp_LoadLibraryExW
0x180055fc4  nop     dword ptr [rax+rax+00h]
0x180055fc9  mov     rdi, rax
0x180055fcc  test    rax, rax
0x180055fcf  jnz     short loc_180055FE9
0x180055fd1  lea     rcx, ?__callsite@?6??Win32LoadLibrary@CDynamicLinkLibrary@@QEAAHPEBGK@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x180055fd8  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180055fdd  lea     rcx, off_180078BE8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180055fe4  jmp     loc_180055E9F
0x180055fe9  xor     ecx, ecx; dwErrCode
0x180055feb  mov     [rbp+460h+var_4D8], rdi
0x180055fef  call    cs:__imp_SetLastError
0x180055ff6  nop     dword ptr [rax+rax+00h]
0x180055ffb  lea     rdx, aVerifypackagep; "VerifyPackagePublisher"
0x180056002  mov     rcx, rdi; hModule
0x180056005  call    cs:__imp_GetProcAddress
0x18005600c  nop     dword ptr [rax+rax+00h]
0x180056011  test    rax, rax
0x180056014  jnz     short loc_180056022
0x180056016  lea     rcx, off_1800727A8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x18005601d  jmp     loc_180055E9F
0x180056022  mov     rcx, [rbp+460h+var_2E0]
0x180056029  lea     rdx, [rbp+460h+var_498.Buffer]
0x18005602d  mov     dword ptr [rbp+460h+var_498.Buffer], r15d
0x180056031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056036  test    eax, eax
0x180056038  jnz     loc_18005613F
0x18005603e  cmp     dword ptr [rbp+460h+var_498.Buffer], r12d
0x180056042  jnz     loc_18005613F
0x180056048  mov     rax, [rbp+460h+var_2E0]
0x18005604f  lea     rcx, [rbp+460h+packageFamilyName]; void *
0x180056056  mov     [rbp+460h+packageId.publisher], rax
0x18005605a  mov     edi, 82h
0x18005605f  mov     rax, [rbp+460h+var_390]
0x180056066  mov     r8d, edi; Size
0x180056069  xor     edx, edx; Val
0x18005606b  mov     [rbp+460h+packageId.name], rax
0x18005606f  call    memset_0
0x180056074  lea     r8, [rbp+460h+packageFamilyName]; packageFamilyName
0x18005607b  mov     dword ptr [rbp+460h+var_498.Buffer+4], 41h ; 'A'
0x180056082  lea     rdx, [rbp+460h+var_498.Buffer+4]; packageFamilyNameLength
0x180056086  lea     rcx, [rbp+460h+packageId]; packageId
0x18005608a  call    cs:__imp_PackageFamilyNameFromId
0x180056091  nop     dword ptr [rax+rax+00h]
0x180056096  test    eax, eax
0x180056098  jz      short loc_1800560D2
0x18005609a  mov     [rsp+5A0h+var_578], r15; struct _UNICODE_STRING *
0x18005609f  lea     r8d, [rdi+1Eh]; unsigned int
0x1800560a3  xor     r9d, r9d; struct _UNICODE_STRING *
0x1800560a6  mov     [rsp+5A0h+var_580], r15; struct _UNICODE_STRING *
0x1800560ab  mov     edx, 0C1010058h; unsigned int
0x1800560b0  mov     rcx, rbx; this
0x1800560b3  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800560b8  mov     edx, 36B5h; unsigned int
0x1800560bd  lea     rcx, [rbp+460h+var_480]; this
0x1800560c1  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x1800560c6  lea     rcx, off_180078BA8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x1800560cd  jmp     loc_180055DE2
0x1800560d2  mov     r9, [rbx+10h]
0x1800560d6  lea     r8, [rbp+460h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800560da  mov     rdx, [rbp+460h+packageRelativeApplicationId]; packageRelativeApplicationId
0x1800560de  lea     rcx, [rbp+460h+packageFamilyName]; packageFamilyName
0x1800560e5  add     r9, 10E0h; applicationUserModelId
0x1800560ec  mov     [rbp+460h+applicationUserModelIdLength], edi
0x1800560ef  call    cs:__imp_FormatApplicationUserModelId
0x1800560f6  nop     dword ptr [rax+rax+00h]
0x1800560fb  test    eax, eax
0x1800560fd  jz      short loc_180056139
0x1800560ff  mov     [rsp+5A0h+var_578], r15; struct _UNICODE_STRING *
0x180056104  xor     r9d, r9d; struct _UNICODE_STRING *
0x180056107  mov     edx, 0C1010059h; unsigned int
0x18005610c  mov     [rsp+5A0h+var_580], r15; struct _UNICODE_STRING *
0x180056111  mov     r8d, 0A1h; unsigned int
0x180056117  mov     rcx, rbx; this
0x18005611a  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18005611f  mov     edx, 36B5h; unsigned int
0x180056124  lea     rcx, [rbp+460h+var_480]; this
0x180056128  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18005612d  lea     rcx, off_180078B88; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180056134  jmp     loc_180055DE2
0x180056139  mov     [rbp+460h+var_4A0], r12d
0x18005613d  jmp     short loc_180056191
0x18005613f  mov     [rsp+5A0h+var_578], r15; struct _UNICODE_STRING *
0x180056144  xor     r9d, r9d; struct _UNICODE_STRING *
0x180056147  mov     edx, 0C1010057h; unsigned int
0x18005614c  mov     [rsp+5A0h+var_580], r15; struct _UNICODE_STRING *
0x180056151  mov     r8d, 9Fh; unsigned int
0x180056157  mov     rcx, rbx; this
0x18005615a  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18005615f  mov     edx, 36B5h; unsigned int
0x180056164  lea     rcx, [rbp+460h+var_480]; this
0x180056168  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x18005616d  lea     rcx, off_180078BC8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180056174  jmp     loc_180055DE2
0x180056179  mov     ecx, 54Fh; dwErrCode
0x18005617e  call    cs:__imp_SetLastError
0x180056185  nop     dword ptr [rax+rax+00h]
0x18005618a  mov     rax, [rbp+460h+var_458]
0x18005618e  mov     [rax], r15d
0x180056191  mov     ebx, [rbp+460h+var_4A0]
0x180056194  lea     rcx, [rbp+460h+var_4D8]
0x180056198  call    ??1?$CHandleTemplate@$1?hNull@@3QEAXEAVCOperatorFreeLibrary@@@@QEAA@XZ; CHandleTemplate<&void * hNull,COperatorFreeLibrary>::~CHandleTemplate<&void * hNull,COperatorFreeLibrary>(void)
0x18005619d  mov     rdx, [rbp+460h+packageRelativeApplicationId]
0x1800561a1  lea     rax, [rbp+460h+var_428]
0x1800561a5  lea     rsi, ??_7?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable'
0x1800561ac  mov     qword ptr [rbp+460h+var_450.Length], rsi
0x1800561b0  cmp     rdx, rax
0x1800561b3  jz      short loc_1800561BE
0x1800561b5  lea     rcx, [rbp+460h+var_450]
0x1800561b9  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x1800561be  mov     rdx, [rbp+460h+var_390]
0x1800561c5  lea     rax, [rbp+460h+var_378]
0x1800561cc  mov     [rbp+460h+packageRelativeApplicationId], r15
0x1800561d0  lea     rdi, ??_7?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@6B@; const CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable'
0x1800561d7  mov     [rbp+460h+var_438], r15
0x1800561db  mov     qword ptr [rbp+460h+var_450.Length], rdi
0x1800561df  mov     [rbp+460h+var_3A0], rsi
0x1800561e6  cmp     rdx, rax
0x1800561e9  jz      short loc_1800561F7
0x1800561eb  lea     rcx, [rbp+460h+var_3A0]
0x1800561f2  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x1800561f7  mov     rdx, [rbp+460h+var_2E0]
0x1800561fe  lea     rax, ??_7?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@6B@; const CGenericStringBuffer<260,CUnicodeCharTraits>::`vftable'
0x180056205  mov     [rbp+460h+var_2F0], rax
0x18005620c  lea     rax, [rbp+460h+var_2C8]
0x180056213  mov     [rbp+460h+var_390], r15
0x18005621a  mov     [rbp+460h+var_388], r15
0x180056221  mov     [rbp+460h+var_3A0], rdi
0x180056228  cmp     rdx, rax
0x18005622b  jz      short loc_180056239
0x18005622d  lea     rcx, [rbp+460h+var_2F0]
0x180056234  call    ?DeallocateBuffer@?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@MEBAXPEAG@Z; CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(ushort *)
0x180056239  lea     rcx, [rbp+460h+var_480]; this
0x18005623d  mov     [rbp+460h+var_2E0], r15
0x180056244  mov     [rbp+460h+var_2D8], r15
0x18005624b  mov     [rbp+460h+var_2F0], rdi
0x180056252  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180056257  mov     eax, ebx
0x180056259  mov     rcx, [rbp+460h+var_30]
0x180056260  xor     rcx, rsp; StackCookie
0x180056263  call    __security_check_cookie
0x180056268  lea     r11, [rsp+5A0h+var_20]
0x180056270  mov     rbx, [r11+38h]
0x180056274  mov     rsi, [r11+48h]
  ... truncated ...
```
