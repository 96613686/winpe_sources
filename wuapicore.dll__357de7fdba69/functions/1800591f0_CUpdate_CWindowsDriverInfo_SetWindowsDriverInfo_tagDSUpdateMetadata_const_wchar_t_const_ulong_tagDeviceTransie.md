# CUpdate::CWindowsDriverInfo::SetWindowsDriverInfo(tagDSUpdateMetadata const &,wchar_t * * const,ulong,tagDeviceTransientInfo const *,ulong,tagDSDeployment const &)

- ea: `0x1800591f0`
- end: `0x180059b1f`
- name: `?SetWindowsDriverInfo@CWindowsDriverInfo@CUpdate@@QEAAJAEBUtagDSUpdateMetadata@@QEAPEA_WKPEBUtagDeviceTransientInfo@@KAEBUtagDSDeployment@@@Z`
- size: `2351`
- prototype: `__int64 __fastcall(CUpdate::CWindowsDriverInfo *__hidden this, const struct tagDSUpdateMetadata *, wchar_t **const, unsigned int, const struct tagDeviceTransientInfo *, unsigned int, const struct tagDSDeployment *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800584b8`

## callees

- `0x180006ac4`
- `0x1800591f0`
- `0x18005d29c`
- `0x18005d778`
- `0x1800760a0`
- `0x180076434`
- `0x180091674`
- `0x180091c70`
- `0x1800967e4`
- `0x180096824`
- `0x180096b10`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800594ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800594ee`
- `OLEAUT32!__imp_SysAllocString` at `0x18005941c`
- `OLEAUT32!__imp_SysAllocString` at `0x180059454`
- `OLEAUT32!__imp_SysAllocString` at `0x18005948e`
- `OLEAUT32!__imp_SysAllocString` at `0x18005941c`
- `OLEAUT32!__imp_SysAllocString` at `0x180059454`
- `OLEAUT32!__imp_SysAllocString` at `0x18005948e`
- `OLEAUT32!__imp_SysFreeString` at `0x180059408`
- `OLEAUT32!__imp_SysFreeString` at `0x180059440`
- `OLEAUT32!__imp_SysFreeString` at `0x180059478`
- `OLEAUT32!__imp_SysFreeString` at `0x180059897`
- `OLEAUT32!__imp_SysFreeString` at `0x1800598a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800598ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18005992a`
- `OLEAUT32!__imp_SysFreeString` at `0x180059934`
- `OLEAUT32!__imp_SysFreeString` at `0x18005993e`
- `OLEAUT32!__imp_SysFreeString` at `0x180059a83`
- `OLEAUT32!__imp_SysFreeString` at `0x180059a8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180059a97`
- `OLEAUT32!__imp_SysFreeString` at `0x180059408`
- `OLEAUT32!__imp_SysFreeString` at `0x180059440`
- `OLEAUT32!__imp_SysFreeString` at `0x180059478`
- `OLEAUT32!__imp_SysFreeString` at `0x180059897`
- `OLEAUT32!__imp_SysFreeString` at `0x1800598a1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800598ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18005992a`
- `OLEAUT32!__imp_SysFreeString` at `0x180059934`
- `OLEAUT32!__imp_SysFreeString` at `0x18005993e`
- `OLEAUT32!__imp_SysFreeString` at `0x180059a83`
- `OLEAUT32!__imp_SysFreeString` at `0x180059a8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180059a97`

## string_xrefs

- `0x18005926e`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x180059a6c`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x180059ad6`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x180059aaf`: `C:\__w\1\s\src\Client\Engine\lib\updparse\exprdeserializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUpdate::CWindowsDriverInfo::SetWindowsDriverInfo(
        CUpdate::CWindowsDriverInfo *this,
        const struct tagDSUpdateMetadata *a2,
        wchar_t **const a3,
        unsigned int a4,
        const struct tagDeviceTransientInfo *a5,
        unsigned int a6,
        const struct tagDSDeployment *a7)
{
  unsigned int v7; // r13d
  const struct tagDSUpdateMetadata *v8; // rsi
  int v10; // ebx
  __int64 v11; // rdx
  CWindowsDriverUpdateEntryCollection *v13; // rbx
  int v14; // r14d
  unsigned int v15; // ebx
  __int64 v16; // rdx
  unsigned int v17; // r14d
  const struct tagDSDeployment *v18; // rcx
  int v19; // r12d
  __int64 v20; // r14
  __int64 v21; // rax
  _DWORD *v22; // r15
  _DWORD *v23; // rcx
  __int64 v24; // rax
  OLECHAR *v25; // rdi
  OLECHAR *v26; // rsi
  OLECHAR *v27; // rbx
  bool v28; // zf
  wchar_t **v29; // rcx
  const OLECHAR *v30; // r14
  const OLECHAR *v31; // r14
  const OLECHAR *v32; // r14
  const WCHAR *v33; // r8
  __int64 v34; // rax
  _DWORD *v35; // rcx
  __int64 v36; // rax
  _DWORD *v37; // rcx
  __int64 v38; // rax
  _DWORD *v39; // rcx
  __int64 v40; // rax
  _DWORD *v41; // rcx
  unsigned int v42; // ecx
  _DWORD *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // r9
  unsigned int v46; // ecx
  _DWORD *v47; // rax
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // r8
  __int64 v51; // r9
  int v52; // eax
  int v53; // eax
  unsigned int v54; // r12d
  unsigned int v55; // r13d
  CWindowsDriverUpdateEntry *v56; // r15
  int v57; // eax
  struct IWindowsDriverUpdateEntry *v58; // rdx
  int v59; // eax
  CUpdate::CWindowsDriverInfo *v60; // r15
  int v61; // eax
  int v62; // eax
  int v63; // eax
  int v64; // eax
  int v65; // eax
  __int64 v66; // rdx
  unsigned __int64 v67; // r9
  __int64 v68; // rdx
  int lpString2; // [rsp+20h] [rbp-E0h]
  char v70; // [rsp+50h] [rbp-B0h]
  unsigned int v71; // [rsp+54h] [rbp-ACh]
  int v72; // [rsp+58h] [rbp-A8h]
  int v73; // [rsp+5Ch] [rbp-A4h]
  __int64 v76; // [rsp+78h] [rbp-88h]
  wchar_t *v77; // [rsp+80h] [rbp-80h]
  wchar_t *v78; // [rsp+88h] [rbp-78h]
  wchar_t *v79; // [rsp+90h] [rbp-70h]
  _DWORD *v80; // [rsp+98h] [rbp-68h] BYREF
  __int128 v81; // [rsp+A0h] [rbp-60h]
  __int64 v82; // [rsp+B0h] [rbp-50h]
  CWindowsDriverUpdateEntryCollection *v83; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *strIn; // [rsp+C0h] [rbp-40h]
  wchar_t *v85; // [rsp+C8h] [rbp-38h]
  OLECHAR *v86; // [rsp+D0h] [rbp-30h]
  OLECHAR *v87; // [rsp+D8h] [rbp-28h]
  OLECHAR *v88; // [rsp+E0h] [rbp-20h]
  PCNZWCH v89; // [rsp+E8h] [rbp-18h]
  CWindowsDriverUpdateEntry *v90; // [rsp+F0h] [rbp-10h] BYREF
  const struct tagDSUpdateMetadata *v91; // [rsp+F8h] [rbp-8h]
  const struct tagDeviceTransientInfo *v92; // [rsp+100h] [rbp+0h]
  CUpdate::CWindowsDriverInfo *v93; // [rsp+108h] [rbp+8h]
  _DWORD v94[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v95; // [rsp+118h] [rbp+18h]
  double v96; // [rsp+120h] [rbp+20h] BYREF
  __int64 v97; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v7 = a4;
  v8 = a2;
  v91 = a2;
  v93 = this;
  v92 = a5;
  v83 = 0;
  v10 = ATL::CComObject<CWindowsDriverUpdateEntryCollection>::CreateInstance(&v83);
  if ( v10 < 0 )
  {
    v11 = 4301;
    goto LABEL_3;
  }
  v13 = v83;
  (*(void (__fastcall **)(char *))(*((_QWORD *)v83 + 1) + 8LL))((char *)v83 + 8);
  *((_QWORD *)this + 1) = v13;
  v14 = 0;
  v72 = 0;
  v15 = 0;
  v73 = 0;
  if ( !*((_DWORD *)v8 + 152) )
  {
LABEL_112:
    if ( v14 == v7 )
      return 0;
    v10 = -2145075196;
    v11 = 4468;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)v10,
      lpString2);
    return (unsigned int)v10;
  }
  while ( 1 )
  {
    v16 = *(_QWORD *)(*((_QWORD *)v8 + 77) + 16LL * v15 + 8);
    if ( !v16 || *(_DWORD *)(v16 + 8) != 2 )
      goto LABEL_111;
    v94[1] = 0;
    v94[0] = *(_DWORD *)(v16 + 4);
    v95 = v16 + 16;
    v80 = v94;
    v81 = 0;
    v82 = 0;
    v17 = CExprDeserializer::Initialize((CExprDeserializer *)&v80);
    if ( (v17 & 0x80000000) != 0 )
    {
      v68 = 4333;
      goto LABEL_145;
    }
    v18 = a7;
    if ( *((_QWORD *)a7 + 16) || (v70 = 0, *((_QWORD *)a7 + 17)) )
      v70 = 1;
    v19 = v82;
    if ( !(_DWORD)v82 || (v20 = v81) == 0 )
    {
      v17 = -2145067003;
LABEL_143:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E4,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\exprdeserializer.cpp",
        (const char *)v17,
        lpString2);
      v68 = 4340;
LABEL_145:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v68,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
        (const char *)v17,
        lpString2);
      goto LABEL_146;
    }
    v89 = 0;
    v21 = 0;
    v22 = (_DWORD *)*((_QWORD *)&v81 + 1);
    if ( *(_DWORD *)(v81 + 8) )
    {
      v23 = (_DWORD *)*((_QWORD *)&v81 + 1);
      while ( *v23 != 113 )
      {
        v21 = (unsigned int)(v21 + 1);
        v23 += 6;
        if ( (unsigned int)v21 >= *(_DWORD *)(v81 + 8) )
          goto LABEL_20;
      }
      if ( *(_DWORD *)(*((_QWORD *)&v81 + 1) + 24 * v21 + 8) != 8 )
      {
        v17 = -2147024809;
        goto LABEL_143;
      }
      v89 = *(PCNZWCH *)(*((_QWORD *)&v81 + 1) + 24 * v21 + 16);
LABEL_20:
      v18 = a7;
    }
    v71 = 0;
    if ( v7 )
      break;
LABEL_109:
    v14 = v72;
LABEL_110:
    CExprDeserializer::~CExprDeserializer((CExprDeserializer *)&v80);
    if ( v14 == v7 )
      return 0;
LABEL_111:
    v73 = ++v15;
    if ( v15 >= *((_DWORD *)v8 + 152) )
      goto LABEL_112;
  }
  v24 = 0;
  v76 = 0;
  while ( 1 )
  {
    v25 = 0;
    v86 = 0;
    v26 = 0;
    v87 = 0;
    v27 = 0;
    v88 = 0;
    if ( !*((_QWORD *)v18 + 16) )
      goto LABEL_33;
    v28 = *((_QWORD *)v18 + 17) == 0;
    v29 = a3;
    if ( !v28 && a3 )
    {
      v30 = a3[v24];
      SysFreeString(0);
      v25 = 0;
      v86 = 0;
      if ( v30 )
      {
        v25 = SysAllocString(v30);
        v86 = v25;
        if ( !v25 )
        {
          v66 = 4351;
LABEL_119:
          v17 = -2147024882;
          goto LABEL_140;
        }
      }
      v31 = (const OLECHAR *)*((_QWORD *)a7 + 16);
      SysFreeString(0);
      v26 = 0;
      v87 = 0;
      if ( v31 )
      {
        v26 = SysAllocString(v31);
        v87 = v26;
        if ( !v26 )
        {
          v66 = 4357;
          goto LABEL_119;
        }
      }
      v32 = (const OLECHAR *)*((_QWORD *)a7 + 17);
      SysFreeString(0);
      v27 = 0;
      v88 = 0;
      if ( v32 )
      {
        v27 = SysAllocString(v32);
        v88 = v27;
        if ( !v27 )
        {
          v66 = 4359;
          goto LABEL_119;
        }
      }
      v24 = v76;
      v20 = v81;
LABEL_33:
      v29 = a3;
    }
    if ( !v70 )
    {
      v33 = v29[v24];
      if ( v33 != v89 && (!v33 || !v89 || CompareStringW(0x7Fu, 1u, v33, -1, v89, -1) != 2) )
        goto LABEL_107;
    }
    v77 = v25;
    v78 = v27;
    v79 = v26;
    v96 = 0.0;
    v97 = 0;
    if ( !v70 )
      break;
LABEL_63:
    if ( !v19 || !v20 )
    {
      v17 = -2145067003;
      goto LABEL_139;
    }
    strIn = 0;
    v40 = 0;
    if ( *(_DWORD *)(v20 + 8) )
    {
      v41 = v22;
      while ( *v41 != 116 )
      {
        v40 = (unsigned int)(v40 + 1);
        v41 += 6;
        if ( (unsigned int)v40 >= *(_DWORD *)(v20 + 8) )
          goto LABEL_72;
      }
      if ( v22[6 * v40 + 2] != 8 )
      {
        v17 = -2147024809;
LABEL_139:
        v66 = 4395;
        goto LABEL_140;
      }
      strIn = *(wchar_t **)&v22[6 * v40 + 4];
    }
LABEL_72:
    v85 = 0;
    v42 = 0;
    if ( *(_DWORD *)(v20 + 8) )
    {
      v43 = v22;
      while ( *v43 != 118 )
      {
        ++v42;
        v43 += 6;
        if ( v42 >= *(_DWORD *)(v20 + 8) )
          goto LABEL_79;
      }
      v44 = 3LL * v42;
      if ( v22[2 * v44 + 2] != 8 )
      {
        v17 = -2147024809;
        v66 = 4397;
        goto LABEL_140;
      }
      v85 = *(wchar_t **)&v22[2 * v44 + 4];
    }
LABEL_79:
    v45 = 0;
    v46 = 0;
    if ( *(_DWORD *)(v20 + 8) )
    {
      v47 = v22;
      while ( *v47 != 114 )
      {
        ++v46;
        v47 += 6;
        if ( v46 >= *(_DWORD *)(v20 + 8) )
          goto LABEL_86;
      }
      v48 = 3LL * v46;
      if ( v22[2 * v48 + 2] != 8 )
      {
        v17 = -2147024809;
        v66 = 4399;
        goto LABEL_140;
      }
      v45 = *(_QWORD *)&v22[2 * v48 + 4];
    }
LABEL_86:
    v49 = StringToFileTime(v45, &v97, 1);
    v17 = v49;
    if ( v49 < 0 )
    {
      v67 = (unsigned int)v49;
      v66 = 4400;
      goto LABEL_141;
    }
    v52 = FileTimeToVariantTime(&v97, &v96, v50, v51);
    v17 = v52;
    if ( v52 < 0 )
    {
      v67 = (unsigned int)v52;
      v66 = 4402;
      goto LABEL_141;
    }
    v90 = 0;
    v53 = ATL::CComObject<CWindowsDriverUpdateEntry>::CreateInstance(&v90);
    v17 = v53;
    if ( v53 < 0 )
    {
      v67 = (unsigned int)v53;
      v66 = 4405;
      goto LABEL_141;
    }
    v54 = 0;
    v55 = 0;
    if ( v92 && v71 < a6 )
    {
      v54 = *((_DWORD *)v92 + 2 * v76 + 1);
      v55 = *((_DWORD *)v92 + 2 * v76);
    }
    v56 = v90;
    v57 = CWindowsDriverUpdateEntry::Initialize(v90, strIn, v77, v78, v79, v85, v96, v54, v55);
    v17 = v57;
    if ( v57 < 0 )
    {
      v67 = (unsigned int)v57;
      v66 = 4424;
      goto LABEL_141;
    }
    if ( v56 )
      v58 = (struct IWindowsDriverUpdateEntry *)((char *)v56 + 8);
    else
      v58 = 0;
    v59 = CWindowsDriverUpdateEntryCollection::AddInner(v83, v58);
    v17 = v59;
    if ( v59 < 0 )
    {
      v67 = (unsigned int)v59;
      v66 = 4426;
      goto LABEL_141;
    }
    if ( !v71 )
    {
      v60 = v93;
      v61 = SusCopyBSTR(strIn, (wchar_t **)v93 + 2);
      v17 = v61;
      if ( v61 < 0 )
      {
        v67 = (unsigned int)v61;
        v66 = 4434;
        goto LABEL_141;
      }
      v62 = SusCopyBSTR(v77, (wchar_t **)v60 + 3);
      v17 = v62;
      if ( v62 < 0 )
      {
        v67 = (unsigned int)v62;
        v66 = 4435;
        goto LABEL_141;
      }
      v63 = SusCopyBSTR(v78, (wchar_t **)v60 + 4);
      v17 = v63;
      if ( v63 < 0 )
      {
        v67 = (unsigned int)v63;
        v66 = 4436;
        goto LABEL_141;
      }
      v64 = SusCopyBSTR(v79, (wchar_t **)v60 + 5);
      v17 = v64;
      if ( v64 < 0 )
      {
        v67 = (unsigned int)v64;
        v66 = 4437;
        goto LABEL_141;
      }
      v65 = SusCopyBSTR(v85, (wchar_t **)v60 + 6);
      v17 = v65;
      if ( v65 < 0 )
      {
        v67 = (unsigned int)v65;
        v66 = 4438;
        goto LABEL_141;
      }
      *((double *)v60 + 7) = v96;
      *((_DWORD *)v60 + 16) = v54;
      *((_DWORD *)v60 + 17) = v55;
    }
    v14 = ++v72;
    v7 = a4;
    if ( !v70 || v14 == a4 )
    {
      SysFreeString(v27);
      SysFreeString(v26);
      SysFreeString(v25);
      v15 = v73;
      v8 = v91;
      goto LABEL_110;
    }
    v19 = v82;
LABEL_107:
    SysFreeString(v27);
    SysFreeString(v26);
    SysFreeString(v25);
    ++v71;
    v24 = ++v76;
    v22 = (_DWORD *)*((_QWORD *)&v81 + 1);
    v20 = v81;
    v18 = a7;
    if ( v71 >= v7 )
    {
      v15 = v73;
      v8 = v91;
      goto LABEL_109;
    }
  }
  if ( v19 && v20 )
  {
    v77 = 0;
    v34 = 0;
    if ( *(_DWORD *)(v20 + 8) )
    {
      v35 = v22;
      while ( *v35 != 113 )
      {
        v34 = (unsigned int)(v34 + 1);
        v35 += 6;
        if ( (unsigned int)v34 >= *(_DWORD *)(v20 + 8) )
          goto LABEL_49;
      }
      if ( v22[6 * v34 + 2] != 8 )
      {
        v17 = -2147024809;
        goto LABEL_124;
      }
      v77 = *(wchar_t **)&v22[6 * v34 + 4];
    }
LABEL_49:
    v78 = 0;
    v36 = 0;
    if ( *(_DWORD *)(v20 + 8) )
    {
      v37 = v22;
      while ( *v37 != 119 )
      {
        v36 = (unsigned int)(v36 + 1);
        v37 += 6;
        if ( (unsigned int)v36 >= *(_DWORD *)(v20 + 8) )
          goto LABEL_56;
      }
      if ( v22[6 * v36 + 2] != 8 )
      {
        v17 = -2147024809;
        v66 = 4389;
        goto LABEL_140;
      }
      v78 = *(wchar_t **)&v22[6 * v36 + 4];
    }
LABEL_56:
    v79 = 0;
    v38 = 0;
    if ( *(_DWORD *)(v20 + 8) )
    {
      v39 = v22;
      while ( *v39 != 120 )
      {
        v38 = (unsigned int)(v38 + 1);
        v39 += 6;
        if ( (unsigned int)v38 >= *(_DWORD *)(v20 + 8) )
          goto LABEL_63;
      }
      if ( v22[6 * v38 + 2] != 8 )
      {
        v17 = -2147024809;
        v66 = 4391;
        goto LABEL_140;
      }
      v79 = *(wchar_t **)&v22[6 * v38 + 4];
    }
    goto LABEL_63;
  }
  v17 = -2145067003;
LABEL_124:
  v66 = 4387;
LABEL_140:
  v67 = v17;
LABEL_141:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v66,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
    (const char *)v67,
    lpString2);
  SysFreeString(v27);
  SysFreeString(v26);
  SysFreeString(v25);
LABEL_146:
  CExprDeserializer::~CExprDeserializer((CExprDeserializer *)&v80);
  return v17;
}

```

## disassembly

```asm
0x1800591f0  mov     rax, rsp
0x1800591f3  mov     [rax+10h], rbx
0x1800591f7  push    rbp
0x1800591f8  push    rsi
0x1800591f9  push    rdi
0x1800591fa  push    r12
0x1800591fc  push    r13
0x1800591fe  push    r14
0x180059200  push    r15
0x180059202  lea     rbp, [rsp-50h]
0x180059207  sub     rsp, 150h
0x18005920e  movaps  xmmword ptr [rax-48h], xmm6
0x180059212  mov     rax, cs:__security_cookie
0x180059219  xor     rax, rsp
0x18005921c  mov     [rbp+80h+var_50], rax
0x180059220  mov     r13d, r9d
0x180059223  mov     [rsp+180h+var_118], r9d
0x180059228  mov     [rsp+180h+var_110], r8
0x18005922d  mov     rsi, rdx
0x180059230  mov     [rbp+80h+var_88], rdx
0x180059234  mov     rdi, rcx
0x180059237  mov     [rbp+80h+var_78], rcx
0x18005923b  mov     rax, [rbp+80h+arg_20]
0x180059242  mov     [rbp+80h+var_80], rax
0x180059246  mov     rax, [rbp+80h+arg_30]
0x18005924d  mov     [rsp+180h+var_120], rax
0x180059252  mov     [rbp+80h+var_C8], 0
0x18005925a  lea     rcx, [rbp+80h+var_C8]
0x18005925e  call    ?CreateInstance@?$CComObject@VCWindowsDriverUpdateEntryCollection@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWindowsDriverUpdateEntryCollection>::CreateInstance(ATL::CComObject<CWindowsDriverUpdateEntryCollection> * *)
0x180059263  mov     ebx, eax
0x180059265  test    eax, eax
0x180059267  jns     short loc_18005928B
0x180059269  mov     edx, 10CDh; void *
0x18005926e  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180059275  mov     r9d, ebx; char *
0x180059278  mov     rcx, [rbp+88h]; this
0x18005927f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059284  mov     eax, ebx
0x180059286  jmp     loc_180059AF3
0x18005928b  mov     rbx, [rbp+80h+var_C8]
0x18005928f  lea     rcx, [rbx+8]
0x180059293  mov     rax, [rcx]
0x180059296  mov     rax, [rax+8]
0x18005929a  call    _guard_dispatch_icall
0x18005929f  mov     [rdi+8], rbx
0x1800592a3  xor     r14d, r14d
0x1800592a6  mov     [rsp+180h+var_128], r14d
0x1800592ab  xor     ebx, ebx
0x1800592ad  mov     [rsp+180h+var_124], ebx
0x1800592b1  cmp     [rsi+260h], ebx
0x1800592b7  jbe     loc_18005990F
0x1800592bd  xorps   xmm6, xmm6
0x1800592c0  mov     ecx, ebx
0x1800592c2  add     rcx, rcx
0x1800592c5  mov     rax, [rsi+268h]
0x1800592cc  mov     rdx, [rax+rcx*8+8]
0x1800592d1  test    rdx, rdx
0x1800592d4  jz      loc_1800598FD
0x1800592da  cmp     dword ptr [rdx+8], 2
0x1800592de  jnz     loc_1800598FD
0x1800592e4  mov     [rbp+80h+var_6C], 0
0x1800592eb  mov     eax, [rdx+4]
0x1800592ee  mov     [rbp+80h+var_70], eax
0x1800592f1  lea     rax, [rdx+10h]
0x1800592f5  mov     [rbp+80h+var_68], rax
0x1800592f9  xorps   xmm0, xmm0
0x1800592fc  movups  [rbp+80h+var_E8], xmm0
0x180059300  movups  [rbp+80h+var_D8], xmm0
0x180059304  lea     rax, [rbp+80h+var_70]
0x180059308  mov     qword ptr [rbp+80h+var_E8], rax
0x18005930c  movdqu  [rbp+80h+var_E8+8], xmm0
0x180059311  mov     dword ptr [rbp+80h+var_D8+8], 0
0x180059318  lea     rcx, [rbp+80h+var_E8]; this
0x18005931c  call    ?Initialize@CExprDeserializer@@QEAAJXZ; CExprDeserializer::Initialize(void)
0x180059321  mov     r14d, eax
0x180059324  xor     edx, edx
0x180059326  test    eax, eax
0x180059328  js      loc_180059AC7
0x18005932e  mov     rcx, [rsp+180h+var_120]
0x180059333  cmp     [rcx+80h], rdx
0x18005933a  jnz     short loc_180059349
0x18005933c  cmp     [rcx+88h], rdx
0x180059343  mov     [rsp+180h+var_130], dl
0x180059347  jz      short loc_18005934E
0x180059349  mov     [rsp+180h+var_130], 1
0x18005934e  mov     r12d, dword ptr [rbp+80h+var_D8+8]
0x180059352  test    r12d, r12d
0x180059355  jz      loc_180059A9F
0x18005935b  mov     r14, qword ptr [rbp+80h+var_E8+8]
0x18005935f  test    r14, r14
0x180059362  jz      loc_180059A9F
0x180059368  mov     [rbp+80h+var_98], rdx
0x18005936c  mov     eax, edx
0x18005936e  mov     r15, qword ptr [rbp+80h+var_D8]
0x180059372  cmp     [r14+8], edx
0x180059376  jbe     short loc_1800593AC
0x180059378  mov     rcx, r15
0x18005937b  cmp     dword ptr [rcx], 71h ; 'q'
0x18005937e  jz      short loc_18005938E
0x180059380  inc     eax
0x180059382  add     rcx, 18h
0x180059386  cmp     eax, [r14+8]
0x18005938a  jb      short loc_18005937B
0x18005938c  jmp     short loc_1800593A7
0x18005938e  lea     rcx, [rax+rax*2]
0x180059392  cmp     dword ptr [r15+rcx*8+8], 8
0x180059398  jnz     loc_18005994E
0x18005939e  mov     rax, [r15+rcx*8+10h]
0x1800593a3  mov     [rbp+80h+var_98], rax
0x1800593a7  mov     rcx, [rsp+180h+var_120]
0x1800593ac  mov     [rsp+180h+var_12C], edx
0x1800593b0  test    r13d, r13d
0x1800593b3  jz      loc_1800598E6
0x1800593b9  mov     rax, rdx
0x1800593bc  mov     [rsp+180h+var_108], rdx
0x1800593c1  jmp     short loc_1800593C5
0x1800593c3  xor     edx, edx
0x1800593c5  mov     rdi, rdx
0x1800593c8  mov     [rbp+80h+var_B0], rdx
0x1800593cc  mov     rsi, rdx
0x1800593cf  mov     [rbp+80h+var_A8], rdx
0x1800593d3  mov     rbx, rdx
0x1800593d6  mov     [rbp+80h+var_A0], rdx
0x1800593da  cmp     [rcx+80h], rdx
0x1800593e1  jz      loc_1800594AF
0x1800593e7  cmp     [rcx+88h], rdx
0x1800593ee  mov     rcx, [rsp+180h+var_110]
0x1800593f3  jz      loc_1800594B4
0x1800593f9  test    rcx, rcx
0x1800593fc  jz      loc_1800594B4
0x180059402  mov     r14, [rcx+rax*8]
0x180059406  xor     ecx, ecx; bstrString
0x180059408  call    cs:__imp_SysFreeString
0x18005940e  xor     edi, edi
0x180059410  mov     [rbp+80h+var_B0], rdi
0x180059414  test    r14, r14
0x180059417  jz      short loc_180059432
0x180059419  mov     rcx, r14; psz
0x18005941c  call    cs:__imp_SysAllocString
0x180059422  mov     rdi, rax
0x180059425  mov     [rbp+80h+var_B0], rax
0x180059429  test    rax, rax
0x18005942c  jz      loc_180059959
0x180059432  mov     r14, [rsp+180h+var_120]
0x180059437  mov     r14, [r14+80h]
0x18005943e  xor     ecx, ecx; bstrString
0x180059440  call    cs:__imp_SysFreeString
0x180059446  xor     esi, esi
0x180059448  mov     [rbp+80h+var_A8], rsi
0x18005944c  test    r14, r14
0x18005944f  jz      short loc_18005946A
0x180059451  mov     rcx, r14; psz
0x180059454  call    cs:__imp_SysAllocString
0x18005945a  mov     rsi, rax
0x18005945d  mov     [rbp+80h+var_A8], rax
0x180059461  test    rax, rax
0x180059464  jz      loc_180059960
0x18005946a  mov     rax, [rsp+180h+var_120]
0x18005946f  mov     r14, [rax+88h]
0x180059476  xor     ecx, ecx; bstrString
0x180059478  call    cs:__imp_SysFreeString
0x18005947e  xor     edx, edx
0x180059480  mov     ebx, edx
0x180059482  mov     [rbp+80h+var_A0], rdx
0x180059486  test    r14, r14
0x180059489  jz      short loc_1800594A6
0x18005948b  mov     rcx, r14; psz
0x18005948e  call    cs:__imp_SysAllocString
0x180059494  mov     rbx, rax
0x180059497  mov     [rbp+80h+var_A0], rax
0x18005949b  xor     edx, edx
0x18005949d  test    rax, rax
0x1800594a0  jz      loc_180059967
0x1800594a6  mov     rax, [rsp+180h+var_108]
0x1800594ab  mov     r14, qword ptr [rbp+80h+var_E8+8]
0x1800594af  mov     rcx, [rsp+180h+var_110]
0x1800594b4  cmp     [rsp+180h+var_130], dl
0x1800594b8  jnz     short loc_1800594FF
0x1800594ba  mov     r8, [rcx+rax*8]; lpString1
0x1800594be  mov     rax, [rbp+80h+var_98]
0x1800594c2  cmp     r8, rax
0x1800594c5  jz      short loc_1800594FF
0x1800594c7  test    r8, r8
0x1800594ca  jz      loc_180059894
0x1800594d0  test    rax, rax
0x1800594d3  jz      loc_180059894
0x1800594d9  or      ecx, 0FFFFFFFFh
0x1800594dc  mov     [rsp+180h+cchCount2], ecx; cchCount2
0x1800594e0  mov     [rsp+180h+lpString2], rax; int
0x1800594e5  mov     r9d, ecx; cchCount1
0x1800594e8  lea     edx, [rcx+2]; dwCmpFlags
0x1800594eb  lea     ecx, [rdx+7Eh]; Locale
0x1800594ee  call    cs:__imp_CompareStringW
0x1800594f4  cmp     eax, 2
0x1800594f7  jnz     loc_180059894
0x1800594fd  xor     edx, edx
0x1800594ff  mov     [rbp+80h+var_100], rdi
0x180059503  mov     [rbp+80h+var_F8], rbx
0x180059507  mov     [rbp+80h+var_F0], rsi
0x18005950b  movsd   [rbp+80h+var_60], xmm6
0x180059510  mov     [rbp+80h+var_58], rdx
0x180059514  cmp     [rsp+180h+var_130], dl
0x180059518  jnz     loc_180059605
0x18005951e  test    r12d, r12d
0x180059521  jz      loc_1800599AF
0x180059527  test    r14, r14
0x18005952a  jz      loc_1800599AF
0x180059530  mov     [rbp+80h+var_100], rdx
0x180059534  mov     eax, edx
0x180059536  cmp     [r14+8], edx
0x18005953a  jbe     short loc_18005956B
0x18005953c  mov     rcx, r15
0x18005953f  cmp     dword ptr [rcx], 71h ; 'q'
0x180059542  jz      short loc_180059552
0x180059544  inc     eax
0x180059546  add     rcx, 18h
0x18005954a  cmp     eax, [r14+8]
0x18005954e  jb      short loc_18005953F
0x180059550  jmp     short loc_18005956B
0x180059552  lea     rcx, [rax+rax*2]
0x180059556  cmp     dword ptr [r15+rcx*8+8], 8
0x18005955c  jnz     loc_180059977
0x180059562  mov     rax, [r15+rcx*8+10h]
0x180059567  mov     [rbp+80h+var_100], rax
0x18005956b  test    r12d, r12d
0x18005956e  jz      loc_18005999F
0x180059574  test    r14, r14
0x180059577  jz      loc_18005999F
0x18005957d  mov     [rbp+80h+var_F8], rdx
0x180059581  mov     eax, edx
0x180059583  cmp     [r14+8], edx
0x180059587  jbe     short loc_1800595B8
0x180059589  mov     rcx, r15
0x18005958c  cmp     dword ptr [rcx], 77h ; 'w'
0x18005958f  jz      short loc_18005959F
0x180059591  inc     eax
0x180059593  add     rcx, 18h
0x180059597  cmp     eax, [r14+8]
0x18005959b  jb      short loc_18005958C
0x18005959d  jmp     short loc_1800595B8
0x18005959f  lea     rcx, [rax+rax*2]
0x1800595a3  cmp     dword ptr [r15+rcx*8+8], 8
0x1800595a9  jnz     loc_18005997F
0x1800595af  mov     rax, [r15+rcx*8+10h]
0x1800595b4  mov     [rbp+80h+var_F8], rax
0x1800595b8  test    r12d, r12d
0x1800595bb  jz      loc_18005998F
0x1800595c1  test    r14, r14
0x1800595c4  jz      loc_18005998F
0x1800595ca  mov     [rbp+80h+var_F0], rdx
0x1800595ce  mov     eax, edx
0x1800595d0  cmp     [r14+8], edx
0x1800595d4  jbe     short loc_180059605
0x1800595d6  mov     rcx, r15
0x1800595d9  cmp     dword ptr [rcx], 78h ; 'x'
0x1800595dc  jz      short loc_1800595EC
0x1800595de  inc     eax
0x1800595e0  add     rcx, 18h
0x1800595e4  cmp     eax, [r14+8]
0x1800595e8  jb      short loc_1800595D9
0x1800595ea  jmp     short loc_180059605
0x1800595ec  lea     rcx, [rax+rax*2]
0x1800595f0  cmp     dword ptr [r15+rcx*8+8], 8
0x1800595f6  jnz     loc_180059987
0x1800595fc  mov     rax, [r15+rcx*8+10h]
0x180059601  mov     [rbp+80h+var_F0], rax
0x180059605  test    r12d, r12d
0x180059608  jz      loc_180059A5E
0x18005960e  test    r14, r14
0x180059611  jz      loc_180059A5E
0x180059617  mov     [rbp+80h+strIn], rdx
0x18005961b  mov     eax, edx
0x18005961d  cmp     [r14+8], edx
0x180059621  jbe     short loc_180059652
0x180059623  mov     rcx, r15
0x180059626  cmp     dword ptr [rcx], 74h ; 't'
0x180059629  jz      short loc_180059639
0x18005962b  inc     eax
0x18005962d  add     rcx, 18h
0x180059631  cmp     eax, [r14+8]
0x180059635  jb      short loc_180059626
0x180059637  jmp     short loc_180059652
0x180059639  lea     rcx, [rax+rax*2]
0x18005963d  cmp     dword ptr [r15+rcx*8+8], 8
0x180059643  jnz     loc_1800599BF
0x180059649  mov     rax, [r15+rcx*8+10h]
0x18005964e  mov     [rbp+80h+strIn], rax
0x180059652  test    r12d, r12d
0x180059655  jz      loc_180059A51
0x18005965b  test    r14, r14
0x18005965e  jz      loc_180059A51
0x180059664  mov     [rbp+80h+var_B8], rdx
0x180059668  mov     ecx, edx
0x18005966a  cmp     [r14+8], edx
0x18005966e  jbe     short loc_1800596A1
0x180059670  mov     rax, r15
0x180059673  cmp     dword ptr [rax], 76h ; 'v'
0x180059676  jz      short loc_180059686
0x180059678  inc     ecx
0x18005967a  add     rax, 18h
  ... truncated ...
```
