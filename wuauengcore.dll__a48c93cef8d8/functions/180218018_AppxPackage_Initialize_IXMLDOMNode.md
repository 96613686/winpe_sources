# AppxPackage::Initialize(IXMLDOMNode *)

- ea: `0x180218018`
- end: `0x1802182bc`
- name: `?Initialize@AppxPackage@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `676`
- prototype: `int(AppxPackage *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180217f50`

## callees

- `0x180113c50`
- `0x18012b618`
- `0x18013a280`
- `0x180218018`
- `0x18021be3c`
- `0x18021c058`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021808e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802180a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802180d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021813c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021817e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802181a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802181d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021821e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021808e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802180a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802180d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021813c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021817e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802181a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802181d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021821e`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1802180ed`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x1802180ed`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180218120`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18021815e`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x180218120`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18021815e`

## pseudocode

```c
__int64 __fastcall AppxPackage::Initialize(AppxPackage *this, struct IUnknown *a2)
{
  signed int LegacyPackageFamilyNameFromApplicabilityData; // edi
  wchar_t **v4; // r8
  void *v5; // rcx
  __int64 v6; // rbx
  void *v7; // rcx
  __int64 v8; // rbx
  bool v9; // zf
  int v10; // eax
  void *v11; // rcx
  const WCHAR *v12; // r14
  WCHAR *v13; // rax
  WCHAR *v14; // rbx
  LONG v15; // eax
  wchar_t **v16; // r8
  WCHAR *v17; // rdi
  bool v18; // sf
  void *v19; // rcx
  wchar_t **v20; // r8
  void *v21; // rcx
  _WORD *v22; // rax
  void *v23; // rcx
  int v24; // eax
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int8 v27[16]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v28; // [rsp+58h] [rbp-1h]
  _OWORD v29[2]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v30; // [rsp+80h] [rbp+27h]

  v30 = 0;
  v28 = 0;
  memset(v29, 0, sizeof(v29));
  *(_OWORD *)v27 = 0;
  LegacyPackageFamilyNameFromApplicabilityData = DspParseElementSet(
                                                   a2,
                                                   v27,
                                                   (struct SusXmlNode *)&qword_180337690,
                                                   (struct tagSusXmlState *)v29);
  if ( LegacyPackageFamilyNameFromApplicabilityData < 0 )
    goto LABEL_40;
  v5 = (void *)*((_QWORD *)this + 1);
  v6 = *(_QWORD *)v27;
  if ( v5 )
    CoTaskMemFree(v5);
  *((_QWORD *)this + 1) = v6;
  v7 = (void *)*((_QWORD *)this + 6);
  v8 = v28;
  if ( v7 )
    CoTaskMemFree(v7);
  v9 = *(_DWORD *)&v27[8] == 0;
  *((_QWORD *)this + 6) = v8;
  *((_BYTE *)this + 40) = !v9;
  v10 = *(_DWORD *)&v27[12];
  *(_DWORD *)this = *(_DWORD *)&v27[12];
  if ( *((_QWORD *)this + 1) )
  {
    v11 = (void *)*((_QWORD *)this + 2);
    if ( v11 )
      CoTaskMemFree(v11);
    v12 = (const WCHAR *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 2) = 0;
    packageFamilyNameLength = 128;
    if ( !IsApiSetImplemented("api-ms-win-appmodel-runtime-l1-1-0") )
    {
      LegacyPackageFamilyNameFromApplicabilityData = -2145124266;
LABEL_40:
      WUTrace("AppxPackage::Initialize", 234, 4096, 2, LegacyPackageFamilyNameFromApplicabilityData, L"Method failed");
      return (unsigned int)LegacyPackageFamilyNameFromApplicabilityData;
    }
    v13 = (WCHAR *)SafeSusComAllocArray(packageFamilyNameLength, 2u);
    v14 = v13;
    if ( !v13 )
    {
LABEL_14:
      LegacyPackageFamilyNameFromApplicabilityData = -2147024882;
      goto LABEL_40;
    }
    v15 = PackageFamilyNameFromFullName(v12, &packageFamilyNameLength, v13);
    if ( v15 == 122 )
    {
      v17 = (WCHAR *)SafeSusComAllocArray(packageFamilyNameLength, 2u);
      CoTaskMemFree(v14);
      v14 = v17;
      if ( !v17 )
        goto LABEL_14;
      v15 = PackageFamilyNameFromFullName(v12, &packageFamilyNameLength, v17);
    }
    if ( !v15 )
    {
      *((_QWORD *)this + 2) = v14;
      LegacyPackageFamilyNameFromApplicabilityData = 0;
      goto LABEL_31;
    }
    LegacyPackageFamilyNameFromApplicabilityData = (unsigned __int16)v15 | 0x80070000;
    if ( v15 <= 0 )
      LegacyPackageFamilyNameFromApplicabilityData = v15;
    if ( v14 )
      CoTaskMemFree(v14);
    v18 = LegacyPackageFamilyNameFromApplicabilityData < 0;
  }
  else
  {
    if ( v10 != 3 )
    {
      LegacyPackageFamilyNameFromApplicabilityData = -2145116154;
      goto LABEL_40;
    }
    v19 = (void *)*((_QWORD *)this + 2);
    if ( v19 )
    {
      CoTaskMemFree(v19);
      *((_QWORD *)this + 2) = 0;
    }
    LegacyPackageFamilyNameFromApplicabilityData = AppXUtil::GetLegacyPackageFamilyNameFromApplicabilityData(
                                                     *((AppXUtil **)this + 6),
                                                     (const wchar_t *const)this + 8,
                                                     v4);
    if ( LegacyPackageFamilyNameFromApplicabilityData < 0 )
      goto LABEL_40;
    v21 = (void *)*((_QWORD *)this + 3);
    if ( v21 )
    {
      CoTaskMemFree(v21);
      *((_QWORD *)this + 3) = 0;
    }
    LegacyPackageFamilyNameFromApplicabilityData = AppXUtil::GetLegacyPackageFullNameFromApplicabilityData(
                                                     *((AppXUtil **)this + 6),
                                                     (const wchar_t *)this + 12,
                                                     v20);
    v18 = LegacyPackageFamilyNameFromApplicabilityData < 0;
  }
  if ( v18 )
    goto LABEL_40;
LABEL_31:
  if ( *(_DWORD *)this != 3 || *((_QWORD *)this + 1) )
  {
    v22 = (_WORD *)*((_QWORD *)this + 6);
    if ( v22 )
    {
      if ( *v22 )
      {
        v23 = (void *)*((_QWORD *)this + 4);
        if ( v23 )
        {
          CoTaskMemFree(v23);
          *((_QWORD *)this + 4) = 0;
        }
        v24 = AppXUtil::GetLegacyPackageFamilyNameFromApplicabilityData(
                *((AppXUtil **)this + 6),
                (const wchar_t *const)this + 16,
                v16);
        if ( v24 < 0 )
          WUTrace(0, 0, 4096, 3, v24, L"Retrieving package legacy family name for '%ws'", *((_QWORD *)this + 6));
      }
    }
  }
  return (unsigned int)LegacyPackageFamilyNameFromApplicabilityData;
}

```

## disassembly

```asm
0x180218018  mov     [rsp-8+arg_10], rbx
0x18021801d  push    rbp
0x18021801e  push    rsi
0x18021801f  push    rdi
0x180218020  push    r14
0x180218022  push    r15
0x180218024  lea     rbp, [rsp-37h]
0x180218029  sub     rsp, 90h
0x180218030  mov     rax, cs:__security_cookie
0x180218037  xor     rax, rsp
0x18021803a  mov     [rbp+57h+var_28], rax
0x18021803e  xorps   xmm0, xmm0
0x180218041  lea     r9, [rbp+57h+var_50]; struct tagSusXmlState *
0x180218045  mov     rsi, rcx
0x180218048  lea     r8, qword_180337690; struct SusXmlNode *
0x18021804f  xor     ecx, ecx
0x180218051  mov     rax, rdx
0x180218054  mov     [rbp+57h+var_30], rcx
0x180218058  lea     rdx, [rbp+57h+var_68]; unsigned __int8 *
0x18021805c  mov     [rbp+57h+var_58], rcx
0x180218060  mov     rcx, rax; struct IUnknown *
0x180218063  movups  [rbp+57h+var_50], xmm0
0x180218067  movups  [rbp+57h+var_40], xmm0
0x18021806b  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18021806f  call    ?DspParseElementSet@@YAJPEAUIUnknown@@PEAEPEAUSusXmlNode@@AEAUtagSusXmlState@@@Z; DspParseElementSet(IUnknown *,uchar *,SusXmlNode *,tagSusXmlState &)
0x180218074  xor     r15d, r15d
0x180218077  mov     edi, eax
0x180218079  test    eax, eax
0x18021807b  js      loc_18021826A
0x180218081  mov     rcx, [rsi+8]; pv
0x180218085  mov     rbx, qword ptr [rbp+57h+var_68]
0x180218089  test    rcx, rcx
0x18021808c  jz      short loc_180218094
0x18021808e  call    cs:__imp_CoTaskMemFree
0x180218094  mov     [rsi+8], rbx
0x180218098  mov     rcx, [rsi+30h]; pv
0x18021809c  mov     rbx, [rbp+57h+var_58]
0x1802180a0  test    rcx, rcx
0x1802180a3  jz      short loc_1802180AB
0x1802180a5  call    cs:__imp_CoTaskMemFree
0x1802180ab  cmp     dword ptr [rbp+57h+var_68+8], r15d
0x1802180af  mov     [rsi+30h], rbx
0x1802180b3  setnz   al
0x1802180b6  mov     [rsi+28h], al
0x1802180b9  mov     eax, dword ptr [rbp+57h+var_68+0Ch]
0x1802180bc  mov     [rsi], eax
0x1802180be  cmp     [rsi+8], r15
0x1802180c2  jz      loc_180218191
0x1802180c8  mov     rcx, [rsi+10h]; pv
0x1802180cc  test    rcx, rcx
0x1802180cf  jz      short loc_1802180D7
0x1802180d1  call    cs:__imp_CoTaskMemFree
0x1802180d7  mov     r14, [rsi+8]
0x1802180db  lea     rcx, aApiMsWinAppmod_0; "api-ms-win-appmodel-runtime-l1-1-0"
0x1802180e2  mov     [rsi+10h], r15
0x1802180e6  mov     [rbp+57h+packageFamilyNameLength], 80h
0x1802180ed  call    cs:__imp_IsApiSetImplemented
0x1802180f3  test    eax, eax
0x1802180f5  jnz     short loc_180218101
0x1802180f7  mov     edi, 80240056h
0x1802180fc  jmp     loc_18021826A
0x180218101  mov     ecx, [rbp+57h+packageFamilyNameLength]; unsigned __int64
0x180218104  mov     edx, 2; unsigned __int64
0x180218109  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x18021810e  mov     rbx, rax
0x180218111  test    rax, rax
0x180218114  jz      short loc_18021814A
0x180218116  mov     r8, rax; packageFamilyName
0x180218119  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18021811d  mov     rcx, r14; packageFullName
0x180218120  call    cs:__imp_PackageFamilyNameFromFullName
0x180218126  cmp     eax, 7Ah ; 'z'
0x180218129  jnz     short loc_180218164
0x18021812b  mov     ecx, [rbp+57h+packageFamilyNameLength]; unsigned __int64
0x18021812e  lea     edx, [rax-78h]; unsigned __int64
0x180218131  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x180218136  mov     rcx, rbx; pv
0x180218139  mov     rdi, rax
0x18021813c  call    cs:__imp_CoTaskMemFree
0x180218142  mov     rbx, rdi
0x180218145  test    rdi, rdi
0x180218148  jnz     short loc_180218154
0x18021814a  mov     edi, 8007000Eh
0x18021814f  jmp     loc_18021826A
0x180218154  mov     r8, rdi; packageFamilyName
0x180218157  lea     rdx, [rbp+57h+packageFamilyNameLength]; packageFamilyNameLength
0x18021815b  mov     rcx, r14; packageFullName
0x18021815e  call    cs:__imp_PackageFamilyNameFromFullName
0x180218164  test    eax, eax
0x180218166  jz      short loc_180218188
0x180218168  movzx   edi, ax
0x18021816b  or      edi, 80070000h
0x180218171  test    eax, eax
0x180218173  cmovle  edi, eax
0x180218176  test    rbx, rbx
0x180218179  jz      short loc_180218184
0x18021817b  mov     rcx, rbx; pv
0x18021817e  call    cs:__imp_CoTaskMemFree
0x180218184  test    edi, edi
0x180218186  jmp     short loc_1802181EA
0x180218188  mov     [rsi+10h], rbx
0x18021818c  mov     edi, r15d
0x18021818f  jmp     short loc_1802181EC
0x180218191  cmp     eax, 3
0x180218194  jnz     loc_180218265
0x18021819a  lea     rbx, [rsi+10h]
0x18021819e  mov     rcx, [rbx]; pv
0x1802181a1  test    rcx, rcx
0x1802181a4  jz      short loc_1802181AF
0x1802181a6  call    cs:__imp_CoTaskMemFree
0x1802181ac  mov     [rbx], r15
0x1802181af  mov     rcx, [rsi+30h]; this
0x1802181b3  mov     rdx, rbx; wchar_t *
0x1802181b6  call    ?GetLegacyPackageFamilyNameFromApplicabilityData@AppXUtil@@YAJQEB_WPEAPEA_W@Z; AppXUtil::GetLegacyPackageFamilyNameFromApplicabilityData(wchar_t const * const,wchar_t * *)
0x1802181bb  mov     edi, eax
0x1802181bd  test    eax, eax
0x1802181bf  js      loc_18021826A
0x1802181c5  lea     rbx, [rsi+18h]
0x1802181c9  mov     rcx, [rbx]; pv
0x1802181cc  test    rcx, rcx
0x1802181cf  jz      short loc_1802181DA
0x1802181d1  call    cs:__imp_CoTaskMemFree
0x1802181d7  mov     [rbx], r15
0x1802181da  mov     rcx, [rsi+30h]; this
0x1802181de  mov     rdx, rbx; wchar_t *
0x1802181e1  call    ?GetLegacyPackageFullNameFromApplicabilityData@AppXUtil@@YAJPEB_WPEAPEA_W@Z; AppXUtil::GetLegacyPackageFullNameFromApplicabilityData(wchar_t const *,wchar_t * *)
0x1802181e6  mov     edi, eax
0x1802181e8  test    eax, eax
0x1802181ea  js      short loc_18021826A
0x1802181ec  cmp     dword ptr [rsi], 3
0x1802181ef  jnz     short loc_1802181FB
0x1802181f1  cmp     [rsi+8], r15
0x1802181f5  jz      loc_180218297
0x1802181fb  mov     rax, [rsi+30h]
0x1802181ff  test    rax, rax
0x180218202  jz      loc_180218297
0x180218208  cmp     [rax], r15w
0x18021820c  jz      loc_180218297
0x180218212  lea     rbx, [rsi+20h]
0x180218216  mov     rcx, [rbx]; pv
0x180218219  test    rcx, rcx
0x18021821c  jz      short loc_180218227
0x18021821e  call    cs:__imp_CoTaskMemFree
0x180218224  mov     [rbx], r15
0x180218227  mov     rcx, [rsi+30h]; this
0x18021822b  mov     rdx, rbx; wchar_t *
0x18021822e  call    ?GetLegacyPackageFamilyNameFromApplicabilityData@AppXUtil@@YAJQEB_WPEAPEA_W@Z; AppXUtil::GetLegacyPackageFamilyNameFromApplicabilityData(wchar_t const * const,wchar_t * *)
0x180218233  test    eax, eax
0x180218235  jns     short loc_180218297
0x180218237  mov     rcx, [rsi+30h]
0x18021823b  xor     edx, edx
0x18021823d  mov     [rsp+0B0h+var_80], rcx
0x180218242  mov     r8d, 1000h
0x180218248  lea     rcx, aRetrievingPack; "Retrieving package legacy family name f"...
0x18021824f  mov     [rsp+0B0h+var_88], rcx
0x180218254  xor     ecx, ecx
0x180218256  lea     r9d, [rdx+3]
0x18021825a  mov     [rsp+0B0h+var_90], eax
0x18021825e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180218263  jmp     short loc_180218297
0x180218265  mov     edi, 80242006h
0x18021826a  lea     rax, aMethodFailed; "Method failed"
0x180218271  mov     edx, 0EAh
0x180218276  mov     [rsp+0B0h+var_88], rax
0x18021827b  lea     rcx, aAppxpackageIni; "AppxPackage::Initialize"
0x180218282  mov     r9d, 2
0x180218288  mov     [rsp+0B0h+var_90], edi
0x18021828c  mov     r8d, 1000h
0x180218292  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180218297  mov     eax, edi
0x180218299  mov     rcx, [rbp+57h+var_28]
0x18021829d  xor     rcx, rsp; StackCookie
0x1802182a0  call    __security_check_cookie
0x1802182a5  mov     rbx, [rsp+0B0h+arg_10]
0x1802182ad  add     rsp, 90h
0x1802182b4  pop     r15
0x1802182b6  pop     r14
0x1802182b8  pop     rdi
0x1802182b9  pop     rsi
0x1802182ba  pop     rbp
0x1802182bb  retn
```
