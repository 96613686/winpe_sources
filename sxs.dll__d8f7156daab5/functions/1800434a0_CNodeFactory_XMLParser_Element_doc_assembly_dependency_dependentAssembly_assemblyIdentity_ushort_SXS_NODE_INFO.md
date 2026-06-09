# CNodeFactory::XMLParser_Element_doc_assembly_dependency_dependentAssembly_assemblyIdentity(ushort,_SXS_NODE_INFO const *)

- ea: `0x1800434a0`
- end: `0x180043bb8`
- name: `?XMLParser_Element_doc_assembly_dependency_dependentAssembly_assemblyIdentity@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `1816`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800075a0`
- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x180019740`
- `0x18001c270`
- `0x180020820`
- `0x180027160`
- `0x18002977c`
- `0x18002b580`
- `0x1800419e4`
- `0x180041f10`
- `0x1800434a0`
- `0x180043bc0`
- `0x18004d2d0`
- `0x1800515ec`
- `0x1800526cc`
- `0x18005d38c`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043583`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043683`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043704`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800437df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004381c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043860`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800438dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800439c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043a07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043a46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043a96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043af1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043583`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043683`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800436f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043704`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800437df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004381c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043860`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800438dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800439c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043a07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043a46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043a96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043af1`

## string_xrefs

- `0x180043933`: `SXS.DLL: unexpected assemblyidentity within dependency tag in component policy "%ls"\n`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_dependency_dependentAssembly_assemblyIdentity(
        CNodeFactory *this,
        unsigned __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  unsigned __int64 v3; // r14
  int v6; // edi
  int v7; // ecx
  int v8; // ecx
  char **v9; // rcx
  __int16 v10; // ax
  char **v11; // rcx
  __int16 v12; // ax
  int v13; // edi
  unsigned int v14; // edx
  unsigned int v15; // r8d
  const struct _ACTCTXCTB_PARSE_CONTEXT *v16; // rdx
  __int64 v17; // rcx
  struct _ASSEMBLY_IDENTITY *v18; // rdi
  WCHAR *v19; // rcx
  const struct _ACTCTXCTB_PARSE_CONTEXT *v20; // rdx
  __int64 v21; // rcx
  const struct _ASSEMBLY_IDENTITY *v22; // r8
  struct _ASSEMBLY_IDENTITY *v23; // rdi
  unsigned __int64 v24; // rdi
  unsigned int v25; // ebx
  unsigned __int8 v27; // [rsp+20h] [rbp-120h]
  struct _UNICODE_STRING *v28; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v29; // [rsp+30h] [rbp-110h]
  struct _UNICODE_STRING *v30; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v31; // [rsp+38h] [rbp-108h]
  struct _UNICODE_STRING *v32; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v33; // [rsp+40h] [rbp-100h]
  struct _UNICODE_STRING *v34; // [rsp+48h] [rbp-F8h]
  struct _UNICODE_STRING *v35; // [rsp+48h] [rbp-F8h]
  const struct _UNICODE_STRING *v36; // [rsp+50h] [rbp-F0h]
  const struct _UNICODE_STRING *v37; // [rsp+58h] [rbp-E8h]
  const struct _UNICODE_STRING *v38; // [rsp+60h] [rbp-E0h]
  const struct _UNICODE_STRING *v39; // [rsp+68h] [rbp-D8h]
  const struct _UNICODE_STRING *v40; // [rsp+70h] [rbp-D0h]
  const struct _UNICODE_STRING *v41; // [rsp+78h] [rbp-C8h]
  const struct _UNICODE_STRING *v42; // [rsp+80h] [rbp-C0h]
  const struct _UNICODE_STRING *v43; // [rsp+88h] [rbp-B8h]
  const struct _UNICODE_STRING *v44; // [rsp+90h] [rbp-B0h]
  const struct _UNICODE_STRING *v45; // [rsp+98h] [rbp-A8h]
  const struct _UNICODE_STRING *v46; // [rsp+A0h] [rbp-A0h]
  const struct _UNICODE_STRING *v47; // [rsp+A8h] [rbp-98h]
  const struct _UNICODE_STRING *v48; // [rsp+B0h] [rbp-90h]
  bool v49[8]; // [rsp+C0h] [rbp-80h] BYREF
  struct _UNICODE_STRING Str; // [rsp+C8h] [rbp-78h] BYREF
  struct _UNICODE_STRING v51; // [rsp+D8h] [rbp-68h] BYREF
  struct _ASSEMBLY_IDENTITY *v52; // [rsp+E8h] [rbp-58h] BYREF
  char v53; // [rsp+F0h] [rbp-50h]
  unsigned __int64 v54; // [rsp+F8h] [rbp-48h] BYREF
  unsigned __int64 v55; // [rsp+100h] [rbp-40h] BYREF
  int v56; // [rsp+108h] [rbp-38h] BYREF
  __int64 v57; // [rsp+110h] [rbp-30h]
  __int64 *v58; // [rsp+118h] [rbp-28h]
  __int64 v59; // [rsp+120h] [rbp-20h]
  int v60; // [rsp+128h] [rbp-18h]
  unsigned int *v61; // [rsp+130h] [rbp-10h]
  int v62; // [rsp+138h] [rbp-8h] BYREF
  struct _UNICODE_STRING v63; // [rsp+140h] [rbp+0h] BYREF
  struct _UNICODE_STRING v64; // [rsp+150h] [rbp+10h] BYREF
  char *v65; // [rsp+160h] [rbp+20h]
  __int64 v66; // [rsp+168h] [rbp+28h]
  char v67; // [rsp+178h] [rbp+38h] BYREF
  struct _UNICODE_STRING v68; // [rsp+200h] [rbp+C0h] BYREF
  char *v69; // [rsp+210h] [rbp+D0h]
  __int64 v70; // [rsp+218h] [rbp+D8h]
  char v71; // [rsp+228h] [rbp+E8h] BYREF

  v3 = a2;
  v62 = 0;
  v58 = &qword_1800711F0;
  v57 = 0;
  v59 = 544438355;
  v56 = 1;
  v60 = 2522;
  v61 = (unsigned int *)&v62;
  CFrame::BaseEnter((CFrame *)&v56);
  v52 = 0;
  v53 = 0;
  v49[0] = 0;
  *(_QWORD *)&v63.Length = 0;
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(&v68);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(&v64);
  v6 = *((_DWORD *)this + 94);
  if ( (unsigned int)(v6 - 1) > 2 )
    goto LABEL_60;
  if ( *((_BYTE *)this + 1836) )
  {
    v14 = -1056899002;
    v15 = 140;
    goto LABEL_26;
  }
  v7 = *((_DWORD *)this + 2);
  *((_BYTE *)this + 1836) = 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
        goto LABEL_60;
      v6 = 2;
    }
    else
    {
      v6 = 1;
    }
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        0,
                        (WCHAR **)qword_1800711D0,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        v49,
                        168,
                        (__int64)&v68,
                        &v63,
                        0) )
  {
    v9 = off_180079248;
LABEL_10:
    *v61 = 0;
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v9);
    goto LABEL_61;
  }
  if ( v49[0] )
  {
    if ( *((_DWORD *)this + 94) != 1 )
    {
      v51.Buffer = L"versionScope";
      Str.Buffer = (PWSTR)*((_QWORD *)this + 52);
      v10 = *((_WORD *)this + 212);
      *(_DWORD *)&v51.Length = 1572888;
      Str.Length = 2 * v10;
      Str.MaximumLength = 2 * v10;
      CNodeFactory::LogParseError(
        this,
        0xC1010040,
        0x7Au,
        &Str,
        &v51,
        0,
        v29,
        v31,
        v33,
        v35,
        v36,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v45,
        v46,
        v47,
        v48);
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v56, 0x36C1u);
      v11 = off_180079228;
LABEL_14:
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v11);
      goto LABEL_61;
    }
LABEL_19:
    SetLastError(0);
LABEL_20:
    SetLastError(0);
    *v61 = 1;
    goto LABEL_61;
  }
  SetLastError(0);
  if ( !(unsigned int)SxspGetAttributeValue(
                        0,
                        (WCHAR **)qword_1800711B0,
                        (__int64)a3,
                        v3,
                        (__int64)this + 400,
                        v49,
                        168,
                        (__int64)&v64,
                        &v63,
                        0) )
  {
    v9 = off_180079208;
    goto LABEL_10;
  }
  if ( v49[0] )
  {
    if ( *((_DWORD *)this + 94) != 1 )
    {
      v51.Buffer = L"buildType";
      Str.Buffer = (PWSTR)*((_QWORD *)this + 52);
      v12 = *((_WORD *)this + 212);
      *(_DWORD *)&v51.Length = 1179666;
      Str.Length = 2 * v12;
      Str.MaximumLength = 2 * v12;
      CNodeFactory::LogParseError(
        this,
        0xC1010040,
        0x7Au,
        &Str,
        &v51,
        0,
        v28,
        v30,
        v32,
        v34,
        v36,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v45,
        v46,
        v47,
        v48);
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v56, 0x36C1u);
      v11 = off_1800791E8;
      goto LABEL_14;
    }
    goto LABEL_19;
  }
  v13 = v6 - 1;
  if ( !v13 )
  {
    *(_QWORD *)&Str.Length = 0;
    *(_QWORD *)&v51.Length = 0;
    SetLastError(0);
    v53 = 1;
    if ( !(unsigned int)SxspCreateAssemblyIdentityFromIdentityElement(v21, v20, 2u, &v52, v3, a3) )
    {
      v9 = off_1800791C8;
      goto LABEL_10;
    }
    v23 = v52;
    if ( *(_DWORD *)(*((_QWORD *)this + 3) + 868LL) )
      TraceActCtxGenIdentity(*(_DWORD *)(*((_QWORD *)this + 2) + 1304LL), v52, v22, 114, v27, 0x68u);
    SetLastError(0);
    if ( !(unsigned int)CNodeFactory::ValidateIdentity(this, 3, 2, v23) )
    {
      v9 = off_180071210;
      goto LABEL_10;
    }
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 1208LL) == 1 && !*((_BYTE *)this + 1840) )
    {
      SetLastError(0);
      if ( !SxspEnqueueAssemblyReference(
              *((struct _ACTCTXGENCTX **)this + 2),
              *((struct _ASSEMBLY **)this + 3),
              v23,
              *((_BYTE *)this + 1834),
              *((_BYTE *)this + 1837)) )
      {
        v9 = off_1800712D0;
        goto LABEL_10;
      }
    }
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          v23,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                          (const unsigned __int16 **)&Str,
                          (unsigned __int64 *)&v51.Length) )
    {
      v9 = off_1800791A8;
      goto LABEL_10;
    }
    v24 = *(_QWORD *)&v51.Length;
    if ( *(_QWORD *)&v51.Length )
    {
      v49[0] = 0;
      SetLastError(0);
      if ( !(unsigned int)SxspIsAssemblyIdentityNameValidForManifest(*(wchar_t **)&Str.Length, v24, v49) )
      {
        v9 = off_180079188;
        goto LABEL_10;
      }
      if ( !v49[0] )
        *(_BYTE *)(*((_QWORD *)this + 2) + 1321LL) = 1;
    }
    goto LABEL_20;
  }
  if ( v13 == 1 )
  {
    *(_QWORD *)&Str.Length = 0;
    *(_QWORD *)&v51.Length = 0;
    v54 = 0;
    v55 = 0;
    if ( *((_QWORD *)this + 156) )
    {
      v14 = -1056899020;
      v15 = 139;
LABEL_26:
      CNodeFactory::LogParseError(
        this,
        v14,
        v15,
        0,
        0,
        0,
        v28,
        v30,
        v32,
        v34,
        v36,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v45,
        v46,
        v47,
        v48);
      goto LABEL_61;
    }
    SetLastError(0);
    v53 = 1;
    if ( !(unsigned int)SxspCreateAssemblyIdentityFromIdentityElement(v17, v16, 2u, &v52, v3, a3) )
    {
      v9 = off_180079168;
      goto LABEL_10;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          *(const struct _ASSEMBLY_IDENTITY **)(*((_QWORD *)this + 3) + 32LL),
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                          (const unsigned __int16 **)&Str,
                          &v54) )
    {
      v9 = off_180079148;
      goto LABEL_10;
    }
    SetLastError(0);
    v18 = v52;
    if ( !(unsigned int)SxspGetAssemblyIdentityAttributeValue(
                          1u,
                          v52,
                          (const struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *)s_IdentityAttribute_name,
                          (const unsigned __int16 **)&v51,
                          &v55) )
    {
      v9 = off_180079128;
      goto LABEL_10;
    }
    if ( v54 <= v55
      || !v55
      || (v19 = (WCHAR *)(*(_QWORD *)&Str.Length + 2 * (v54 - v55)), *(v19 - 1) != 46)
      || !FusionpEqualStrings(v19, v55, *(WCHAR **)&v51.Length, v55, 0) )
    {
      FusionpDbgPrintEx(
        0x80010002,
        "SXS.DLL: unexpected assemblyidentity within dependency tag in component policy \"%ls\"\n",
        *((const wchar_t **)this + 88));
      goto LABEL_20;
    }
    SetLastError(0);
    if ( !(unsigned int)CNodeFactory::ValidateIdentity(this, 10, 2, v18) )
    {
      v9 = off_180079108;
      goto LABEL_10;
    }
    if ( !*((_QWORD *)this + 156) )
    {
      v52 = 0;
      v53 = 0;
      *((_QWORD *)this + 156) = v18;
      goto LABEL_20;
    }
  }
LABEL_60:
  SetLastError(0x54Fu);
  *v61 = 0;
LABEL_61:
  v25 = *v61;
  *(_QWORD *)&v64.Length = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v65 != &v67 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v64);
  v65 = 0;
  v66 = 0;
  *(_QWORD *)&v64.Length = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  *(_QWORD *)&v68.Length = &CGenericStringBuffer<64,CUnicodeCharTraits>::`vftable';
  if ( v69 != &v71 )
    CGenericStringBuffer<64,CUnicodeCharTraits>::DeallocateBuffer(&v68);
  v69 = 0;
  v70 = 0;
  *(_QWORD *)&v68.Length = &CGenericBaseStringBuffer<CUnicodeCharTraits>::`vftable';
  CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>::~CSmartPtrWithNamedDestructor<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *),CSmartPtrWithNamedDestructorHelper<_ASSEMBLY_IDENTITY,&void SxsDestroyAssemblyIdentity(_ASSEMBLY_IDENTITY *)>>(&v52);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v56);
  return v25;
}

```

## disassembly

```asm
0x1800434a0  mov     [rsp-8+arg_8], rbx
0x1800434a5  push    rbp
0x1800434a6  push    rsi
0x1800434a7  push    rdi
0x1800434a8  push    r12
0x1800434aa  push    r13
0x1800434ac  push    r14
0x1800434ae  push    r15
0x1800434b0  lea     rbp, [rsp-180h]
0x1800434b8  sub     rsp, 2C0h
0x1800434bf  mov     rax, cs:__security_cookie
0x1800434c6  xor     rax, rsp
0x1800434c9  mov     [rbp+1B0h+var_40], rax
0x1800434d0  xor     r13d, r13d
0x1800434d3  movzx   r14d, dx
0x1800434d7  lea     rax, qword_1800711F0
0x1800434de  mov     [rbp+1B0h+var_1B8], r13d
0x1800434e2  mov     [rbp+1B0h+var_1D8], rax
0x1800434e6  mov     rbx, rcx
0x1800434e9  lea     rax, [rbp+1B0h+var_1B8]
0x1800434ed  mov     [rbp+1B0h+var_1E0], r13
0x1800434f1  lea     r15d, [r13+1]
0x1800434f5  mov     [rbp+1B0h+var_1D0], 20737853h
0x1800434fd  lea     rcx, [rbp+1B0h+var_1E8]; this
0x180043501  mov     [rbp+1B0h+var_1E8], r15d
0x180043505  mov     rsi, r8
0x180043508  mov     [rbp+1B0h+var_1C8], 9DAh
0x18004350f  mov     [rbp+1B0h+var_1C0], rax
0x180043513  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180043518  lea     rcx, [rbp+1B0h+var_F0]
0x18004351f  mov     [rbp+1B0h+var_208], r13
0x180043523  mov     [rbp+1B0h+var_200], r13b
0x180043527  mov     [rbp+1B0h+var_230], r13b
0x18004352b  mov     qword ptr [rbp+1B0h+var_1B0.Length], r13
0x18004352f  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180043534  lea     rcx, [rbp+1B0h+var_1A0]
0x180043538  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x18004353d  mov     edi, [rbx+178h]
0x180043543  lea     eax, [rdi-1]
0x180043546  cmp     eax, 2
0x180043549  ja      loc_180043AEC
0x18004354f  cmp     [rbx+72Ch], r13b
0x180043556  jnz     loc_180043ADC
0x18004355c  mov     ecx, [rbx+8]
0x18004355f  mov     [rbx+72Ch], r15b
0x180043566  test    ecx, ecx
0x180043568  jz      short loc_180043581
0x18004356a  sub     ecx, r15d
0x18004356d  jz      short loc_18004357E
0x18004356f  cmp     ecx, r15d
0x180043572  jnz     loc_180043AEC
0x180043578  lea     edi, [r13+2]
0x18004357c  jmp     short loc_180043581
0x18004357e  mov     edi, r15d
0x180043581  xor     ecx, ecx; dwErrCode
0x180043583  call    cs:__imp_SetLastError
0x18004358a  nop     dword ptr [rax+rax+00h]
0x18004358f  mov     [rsp+2F0h+var_2A8], r13; struct _UNICODE_STRING *
0x180043594  lea     rax, [rbp+1B0h+var_1B0]
0x180043598  mov     [rsp+2F0h+var_2B0], rax; struct _UNICODE_STRING *
0x18004359d  lea     r15, [rbx+190h]
0x1800435a4  lea     rax, [rbp+1B0h+var_F0]
0x1800435ab  mov     r9, r14
0x1800435ae  mov     [rsp+2F0h+var_2B8], rax; struct _UNICODE_STRING *
0x1800435b3  lea     rdx, qword_1800711D0
0x1800435ba  lea     rax, [rbp+1B0h+var_230]
0x1800435be  mov     [rsp+2F0h+var_2C0], 0A8h; struct _UNICODE_STRING *
0x1800435c7  mov     [rsp+2F0h+var_2C8], rax
0x1800435cc  mov     r8, rsi
0x1800435cf  xor     ecx, ecx
0x1800435d1  mov     [rsp+2F0h+var_2D0], r15
0x1800435d6  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x1800435db  test    eax, eax
0x1800435dd  jnz     short loc_1800435F7
0x1800435df  lea     rcx, off_180079248; struct _CALL_SITE_INFO *
0x1800435e6  mov     rax, [rbp+1B0h+var_1C0]
0x1800435ea  mov     [rax], r13d
0x1800435ed  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800435f2  jmp     loc_180043B04
0x1800435f7  cmp     [rbp+1B0h+var_230], r13b
0x1800435fb  jz      loc_180043681
0x180043601  cmp     dword ptr [rbx+178h], 1
0x180043608  jz      loc_1800436F4
0x18004360e  lea     rax, aVersionscope_0; "versionScope"
0x180043615  mov     [rsp+2F0h+var_2C8], r13; struct _UNICODE_STRING *
0x18004361a  mov     [rbp+1B0h+var_218.Buffer], rax
0x18004361e  lea     r9, [rbp+1B0h+Str]; struct _UNICODE_STRING *
0x180043622  mov     rax, [rbx+1A0h]
0x180043629  mov     edx, 0C1010040h; unsigned int
0x18004362e  mov     [rbp+1B0h+var_220], rax
0x180043632  mov     r8d, 7Ah ; 'z'; unsigned int
0x180043638  movzx   eax, word ptr [rbx+1A8h]
0x18004363f  mov     rcx, rbx; this
0x180043642  add     ax, ax
0x180043645  mov     dword ptr [rbp+1B0h+var_218.Length], 180018h
0x18004364c  mov     word ptr [rbp+1B0h+Str], ax
0x180043650  mov     word ptr [rbp+1B0h+Str+2], ax
0x180043654  lea     rax, [rbp+1B0h+var_218]
0x180043658  mov     [rsp+2F0h+var_2D0], rax; struct _UNICODE_STRING *
0x18004365d  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180043662  mov     edx, 36C1h; unsigned int
0x180043667  lea     rcx, [rbp+1B0h+var_1E8]; this
0x18004366b  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180043670  lea     rcx, off_180079228; struct _CALL_SITE_INFO *
0x180043677  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18004367c  jmp     loc_180043B04
0x180043681  xor     ecx, ecx; dwErrCode
0x180043683  call    cs:__imp_SetLastError
0x18004368a  nop     dword ptr [rax+rax+00h]
0x18004368f  mov     [rsp+2F0h+var_2A8], r13; struct _UNICODE_STRING *
0x180043694  lea     rax, [rbp+1B0h+var_1B0]
0x180043698  mov     [rsp+2F0h+var_2B0], rax; struct _UNICODE_STRING *
0x18004369d  lea     rdx, qword_1800711B0
0x1800436a4  lea     rax, [rbp+1B0h+var_1A0]
0x1800436a8  mov     r9, r14
0x1800436ab  mov     [rsp+2F0h+var_2B8], rax; struct _UNICODE_STRING *
0x1800436b0  mov     r8, rsi
0x1800436b3  lea     rax, [rbp+1B0h+var_230]
0x1800436b7  mov     [rsp+2F0h+var_2C0], 0A8h; struct _UNICODE_STRING *
0x1800436c0  mov     [rsp+2F0h+var_2C8], rax
0x1800436c5  xor     ecx, ecx
0x1800436c7  mov     [rsp+2F0h+var_2D0], r15
0x1800436cc  call    ?SxspGetAttributeValue@@YAHKPEBU_ATTRIBUTE_NAME_DESCRIPTOR@@PEBU_SXS_NODE_INFO@@_KPEBU_ACTCTXCTB_PARSE_CONTEXT@@AEA_N2PEAXAEA_KP6AHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@4256@ZK@Z; SxspGetAttributeValue(ulong,_ATTRIBUTE_NAME_DESCRIPTOR const *,_SXS_NODE_INFO const *,unsigned __int64,_ACTCTXCTB_PARSE_CONTEXT const *,bool &,unsigned __int64,void *,unsigned __int64 &,int (*)(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &,bool &,unsigned __int64,void *,unsigned __int64 &),ulong)
0x1800436d1  test    eax, eax
0x1800436d3  jnz     short loc_1800436E1
0x1800436d5  lea     rcx, off_180079208; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x1800436dc  jmp     loc_1800435E6
0x1800436e1  cmp     [rbp+1B0h+var_230], r13b
0x1800436e5  jz      loc_18004378D
0x1800436eb  cmp     dword ptr [rbx+178h], 1
0x1800436f2  jnz     short loc_18004371F
0x1800436f4  xor     ecx, ecx; dwErrCode
0x1800436f6  call    cs:__imp_SetLastError
0x1800436fd  nop     dword ptr [rax+rax+00h]
0x180043702  xor     ecx, ecx; dwErrCode
0x180043704  call    cs:__imp_SetLastError
0x18004370b  nop     dword ptr [rax+rax+00h]
0x180043710  mov     rax, [rbp+1B0h+var_1C0]
0x180043714  mov     dword ptr [rax], 1
0x18004371a  jmp     loc_180043B04
0x18004371f  lea     rax, aBuildtype_0; "buildType"
0x180043726  mov     [rsp+2F0h+var_2C8], r13; struct _UNICODE_STRING *
0x18004372b  mov     [rbp+1B0h+var_218.Buffer], rax
0x18004372f  lea     r9, [rbp+1B0h+Str]; struct _UNICODE_STRING *
0x180043733  mov     rax, [rbx+1A0h]
0x18004373a  mov     edx, 0C1010040h; unsigned int
0x18004373f  mov     [rbp+1B0h+var_220], rax
0x180043743  mov     r8d, 7Ah ; 'z'; unsigned int
0x180043749  movzx   eax, word ptr [rbx+1A8h]
0x180043750  mov     rcx, rbx; this
0x180043753  add     ax, ax
0x180043756  mov     dword ptr [rbp+1B0h+var_218.Length], 120012h
0x18004375d  mov     word ptr [rbp+1B0h+Str], ax
0x180043761  mov     word ptr [rbp+1B0h+Str+2], ax
0x180043765  lea     rax, [rbp+1B0h+var_218]
0x180043769  mov     [rsp+2F0h+var_2D0], rax; struct _UNICODE_STRING *
0x18004376e  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180043773  mov     edx, 36C1h; unsigned int
0x180043778  lea     rcx, [rbp+1B0h+var_1E8]; this
0x18004377c  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180043781  lea     rcx, off_1800791E8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180043788  jmp     loc_180043677
0x18004378d  sub     edi, 1
0x180043790  jz      loc_180043949
0x180043796  cmp     edi, 1
0x180043799  jnz     loc_180043AEC
0x18004379f  mov     [rbp+1B0h+Str], r13
0x1800437a3  mov     qword ptr [rbp+1B0h+var_218.Length], r13
0x1800437a7  mov     [rbp+1B0h+var_1F8], r13
0x1800437ab  mov     [rbp+1B0h+var_1F0], r13
0x1800437af  cmp     [rbx+4E0h], r13
0x1800437b6  jz      short loc_1800437DD
0x1800437b8  mov     edx, 0C1010034h; unsigned int
0x1800437bd  mov     r8d, 8Bh; unsigned int
0x1800437c3  mov     [rsp+2F0h+var_2C8], r13; struct _UNICODE_STRING *
0x1800437c8  xor     r9d, r9d; struct _UNICODE_STRING *
0x1800437cb  mov     rcx, rbx; this
0x1800437ce  mov     [rsp+2F0h+var_2D0], r13; struct _UNICODE_STRING *
0x1800437d3  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800437d8  jmp     loc_180043B04
0x1800437dd  xor     ecx, ecx; dwErrCode
0x1800437df  call    cs:__imp_SetLastError
0x1800437e6  nop     dword ptr [rax+rax+00h]
0x1800437eb  mov     [rsp+2F0h+var_2C8], rsi; struct _SXS_NODE_INFO *
0x1800437f0  lea     r9, [rbp+1B0h+var_208]; struct _ASSEMBLY_IDENTITY **
0x1800437f4  mov     esi, 2
0x1800437f9  mov     [rbp+1B0h+var_200], 1
0x1800437fd  mov     r8d, esi; unsigned int
0x180043800  mov     dword ptr [rsp+2F0h+var_2D0], r14d; unsigned int
0x180043805  call    ?SxspCreateAssemblyIdentityFromIdentityElement@@YAHKPEBU_ACTCTXCTB_PARSE_CONTEXT@@KPEAPEAU_ASSEMBLY_IDENTITY@@KPEBU_SXS_NODE_INFO@@@Z; SxspCreateAssemblyIdentityFromIdentityElement(ulong,_ACTCTXCTB_PARSE_CONTEXT const *,ulong,_ASSEMBLY_IDENTITY * *,ulong,_SXS_NODE_INFO const *)
0x18004380a  test    eax, eax
0x18004380c  jnz     short loc_18004381A
0x18004380e  lea     rcx, off_180079168; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180043815  jmp     loc_1800435E6
0x18004381a  xor     ecx, ecx; dwErrCode
0x18004381c  call    cs:__imp_SetLastError
0x180043823  nop     dword ptr [rax+rax+00h]
0x180043828  mov     rdx, [rbx+18h]
0x18004382c  lea     rax, [rbp+1B0h+var_1F8]
0x180043830  lea     r9, [rbp+1B0h+Str]; unsigned __int16 **
0x180043834  mov     [rsp+2F0h+var_2D0], rax; unsigned __int64 *
0x180043839  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x180043840  mov     ecx, 1; unsigned int
0x180043845  mov     rdx, [rdx+20h]; struct _ASSEMBLY_IDENTITY *
0x180043849  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x18004384e  test    eax, eax
0x180043850  jnz     short loc_18004385E
0x180043852  lea     rcx, off_180079148; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180043859  jmp     loc_1800435E6
0x18004385e  xor     ecx, ecx; dwErrCode
0x180043860  call    cs:__imp_SetLastError
0x180043867  nop     dword ptr [rax+rax+00h]
0x18004386c  mov     rdi, [rbp+1B0h+var_208]
0x180043870  lea     rax, [rbp+1B0h+var_1F0]
0x180043874  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x180043877  mov     [rsp+2F0h+var_2D0], rax; unsigned __int64 *
0x18004387c  lea     r9, [rbp+1B0h+var_218]; unsigned __int16 **
0x180043880  mov     ecx, 1; unsigned int
0x180043885  lea     r8, s_IdentityAttribute_name; struct _SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE *
0x18004388c  call    ?SxspGetAssemblyIdentityAttributeValue@@YAHKPEBU_ASSEMBLY_IDENTITY@@PEBU_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE@@PEAPEBGPEA_K@Z; SxspGetAssemblyIdentityAttributeValue(ulong,_ASSEMBLY_IDENTITY const *,_SXS_ASSEMBLY_IDENTITY_ATTRIBUTE_REFERENCE const *,ushort const * *,unsigned __int64 *)
0x180043891  test    eax, eax
0x180043893  jnz     short loc_1800438A1
0x180043895  lea     rcx, off_180079128; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x18004389c  jmp     loc_1800435E6
0x1800438a1  mov     rcx, [rbp+1B0h+var_1F8]
0x1800438a5  mov     rdx, [rbp+1B0h+var_1F0]; unsigned __int64
0x1800438a9  cmp     rcx, rdx
0x1800438ac  jbe     short loc_18004392C
0x1800438ae  test    rdx, rdx
0x1800438b1  jz      short loc_18004392C
0x1800438b3  mov     rax, [rbp+1B0h+Str]
0x1800438b7  sub     rcx, rdx
0x1800438ba  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x1800438be  cmp     word ptr [rcx-2], 2Eh ; '.'
0x1800438c3  jnz     short loc_18004392C
0x1800438c5  mov     r8, qword ptr [rbp+1B0h+var_218.Length]; unsigned __int16 *
0x1800438c9  mov     r9, rdx; unsigned __int64
0x1800438cc  mov     byte ptr [rsp+2F0h+var_2D0], r13b; bool
0x1800438d1  call    ?FusionpEqualStrings@@YA_NPEBG_K01_N@Z; FusionpEqualStrings(ushort const *,unsigned __int64,ushort const *,unsigned __int64,bool)
0x1800438d6  test    al, al
0x1800438d8  jz      short loc_18004392C
0x1800438da  xor     ecx, ecx; dwErrCode
0x1800438dc  call    cs:__imp_SetLastError
0x1800438e3  nop     dword ptr [rax+rax+00h]
0x1800438e8  mov     r9, rdi; struct _ASSEMBLY_IDENTITY *
0x1800438eb  mov     r8d, esi; unsigned int
0x1800438ee  mov     edx, 0Ah; unsigned int
0x1800438f3  mov     rcx, rbx; this
0x1800438f6  call    ?ValidateIdentity@CNodeFactory@@QEAAHKKPEBU_ASSEMBLY_IDENTITY@@@Z; CNodeFactory::ValidateIdentity(ulong,ulong,_ASSEMBLY_IDENTITY const *)
0x1800438fb  test    eax, eax
0x1800438fd  jnz     short loc_18004390B
0x1800438ff  lea     rcx, off_180079108; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180043906  jmp     loc_1800435E6
0x18004390b  cmp     [rbx+4E0h], r13
0x180043912  jnz     loc_180043AEC
0x180043918  mov     [rbp+1B0h+var_208], r13
0x18004391c  mov     [rbp+1B0h+var_200], r13b
0x180043920  mov     [rbx+4E0h], rdi
0x180043927  jmp     loc_180043702
0x18004392c  mov     r8, [rbx+2C0h]
0x180043933  lea     rdx, aSxsDllUnexpect; "SXS.DLL: unexpected assemblyidentity wi"...
0x18004393a  mov     ecx, 80010002h; unsigned int
0x18004393f  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180043944  jmp     loc_180043702
0x180043949  xor     ecx, ecx; dwErrCode
0x18004394b  mov     [rbp+1B0h+Str], r13
0x18004394f  mov     qword ptr [rbp+1B0h+var_218.Length], r13
0x180043953  call    cs:__imp_SetLastError
0x18004395a  nop     dword ptr [rax+rax+00h]
0x18004395f  mov     [rsp+2F0h+var_2C8], rsi; struct _SXS_NODE_INFO *
0x180043964  lea     r9, [rbp+1B0h+var_208]; struct _ASSEMBLY_IDENTITY **
0x180043968  mov     esi, 2
0x18004396d  mov     [rbp+1B0h+var_200], 1
0x180043971  mov     r8d, esi; unsigned int
0x180043974  mov     dword ptr [rsp+2F0h+var_2D0], r14d; unsigned __int8
0x180043979  call    ?SxspCreateAssemblyIdentityFromIdentityElement@@YAHKPEBU_ACTCTXCTB_PARSE_CONTEXT@@KPEAPEAU_ASSEMBLY_IDENTITY@@KPEBU_SXS_NODE_INFO@@@Z; SxspCreateAssemblyIdentityFromIdentityElement(ulong,_ACTCTXCTB_PARSE_CONTEXT const *,ulong,_ASSEMBLY_IDENTITY * *,ulong,_SXS_NODE_INFO const *)
0x18004397e  test    eax, eax
0x180043980  jnz     short loc_18004398E
0x180043982  lea     rcx, off_1800791C8; "clientcore\\base\\win32\\fusion\\sxs\\n"...
0x180043989  jmp     loc_1800435E6
0x18004398e  mov     rax, [rbx+18h]
0x180043992  mov     rdi, [rbp+1B0h+var_208]
0x180043996  cmp     [rax+364h], r13d
0x18004399d  jz      short loc_1800439BE
0x18004399f  mov     rcx, [rbx+10h]
0x1800439a3  mov     r9d, 72h ; 'r'; unsigned __int16
0x1800439a9  mov     rdx, rdi; struct _ASSEMBLY_IDENTITY *
0x1800439ac  mov     word ptr [rsp+2F0h+var_2C8], 68h ; 'h'; unsigned __int16
0x1800439b3  mov     ecx, [rcx+518h]; int
0x1800439b9  call    ?TraceActCtxGenIdentity@@YAKJPEBU_ASSEMBLY_IDENTITY@@0GEG@Z; TraceActCtxGenIdentity(long,_ASSEMBLY_IDENTITY const *,_ASSEMBLY_IDENTITY const *,ushort,uchar,ushort)
0x1800439be  xor     ecx, ecx; dwErrCode
0x1800439c0  call    cs:__imp_SetLastError
0x1800439c7  nop     dword ptr [rax+rax+00h]
0x1800439cc  mov     r9, rdi; struct _ASSEMBLY_IDENTITY *
0x1800439cf  mov     r8d, esi; unsigned int
0x1800439d2  mov     edx, 3; unsigned int
0x1800439d7  mov     rcx, rbx; this
0x1800439da  call    ?ValidateIdentity@CNodeFactory@@QEAAHKKPEBU_ASSEMBLY_IDENTITY@@@Z; CNodeFactory::ValidateIdentity(ulong,ulong,_ASSEMBLY_IDENTITY const *)
0x1800439df  test    eax, eax
0x1800439e1  jnz     short loc_1800439EF
  ... truncated ...
```
