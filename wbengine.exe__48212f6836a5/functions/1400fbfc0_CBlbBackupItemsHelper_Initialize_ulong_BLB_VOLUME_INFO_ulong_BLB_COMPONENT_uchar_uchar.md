# CBlbBackupItemsHelper::Initialize(ulong,_BLB_VOLUME_INFO *,ulong,_BLB_COMPONENT *,uchar,uchar)

- ea: `0x1400fbfc0`
- end: `0x1400fc87c`
- name: `?Initialize@CBlbBackupItemsHelper@@QEAAJKPEAU_BLB_VOLUME_INFO@@KPEAU_BLB_COMPONENT@@EE@Z`
- size: `2236`
- prototype: `__int64 __fastcall(CBlbBackupItemsHelper *__hidden this, unsigned int, struct _BLB_VOLUME_INFO *, unsigned int, struct _BLB_COMPONENT *, char, char)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400290e4`
- `0x14010e288`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000cbcc`
- `0x14001358c`
- `0x140014200`
- `0x140088d0c`
- `0x14008ba2c`
- `0x1400f7290`
- `0x1400fbedc`
- `0x1400fbfc0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400fc120`
- `ole32!CoTaskMemFree` at `0x1400fc132`
- `ole32!CoTaskMemFree` at `0x1400fc25e`
- `ole32!CoTaskMemFree` at `0x1400fc27d`
- `ole32!CoTaskMemFree` at `0x1400fc3bb`
- `ole32!CoTaskMemFree` at `0x1400fc3c9`
- `ole32!CoTaskMemFree` at `0x1400fc3d7`
- `ole32!CoTaskMemFree` at `0x1400fc3e5`
- `ole32!CoTaskMemFree` at `0x1400fc3f3`
- `ole32!CoTaskMemFree` at `0x1400fc405`
- `ole32!CoTaskMemFree` at `0x1400fc413`
- `ole32!CoTaskMemFree` at `0x1400fc421`
- `ole32!CoTaskMemFree` at `0x1400fc5d3`
- `ole32!CoTaskMemFree` at `0x1400fc120`
- `ole32!CoTaskMemFree` at `0x1400fc132`
- `ole32!CoTaskMemFree` at `0x1400fc25e`
- `ole32!CoTaskMemFree` at `0x1400fc27d`
- `ole32!CoTaskMemFree` at `0x1400fc3bb`
- `ole32!CoTaskMemFree` at `0x1400fc3c9`
- `ole32!CoTaskMemFree` at `0x1400fc3d7`
- `ole32!CoTaskMemFree` at `0x1400fc3e5`
- `ole32!CoTaskMemFree` at `0x1400fc3f3`
- `ole32!CoTaskMemFree` at `0x1400fc405`
- `ole32!CoTaskMemFree` at `0x1400fc413`
- `ole32!CoTaskMemFree` at `0x1400fc421`
- `ole32!CoTaskMemFree` at `0x1400fc5d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400fc460`
- `OLEAUT32!__imp_SysFreeString` at `0x1400fc460`

## string_xrefs

- `0x1400fc05b`: `m_wszSpecsXML == NULL`
- `0x1400fc209`: `<Volume Name="%ws" AccessPath="%ws" OriginalAccessPath="%ws" Label="%ws" OriginalLabel="%ws" >`
- `0x1400fc346`: `<FileSpec FilePath="%ws" FileName="%ws" IsRecursive="%ws" IsInclude="%ws" />`
- `0x1400fc59c`: `<ComponentSpecs>`
- `0x1400fc7d0`: `<ComponentSpec WriterId="{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}" InstanceId="{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}" ComponentName="%ws" LogicalPath="%ws" Caption="%ws" />`
- `0x1400fc806`: `</ComponentSpecs>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBlbBackupItemsHelper::Initialize(
        CBlbBackupItemsHelper *this,
        unsigned int a2,
        struct _BLB_VOLUME_INFO *a3,
        unsigned int a4,
        struct _BLB_COMPONENT *a5,
        char a6,
        char a7)
{
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // r13
  unsigned __int16 *v11; // r14
  unsigned __int16 *v12; // rdi
  void *v13; // r12
  int v14; // ebx
  unsigned int v15; // r13d
  unsigned int v16; // eax
  char *v17; // rdi
  unsigned __int16 *v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // esi
  const OLECHAR *v25; // rcx
  const OLECHAR *v26; // rax
  unsigned __int64 v27; // rdx
  unsigned int i; // r13d
  __int64 v29; // r12
  unsigned __int16 *v30; // r14
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // r14d
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rcx
  unsigned __int64 v36; // rdx
  const unsigned __int16 *v38; // r13
  const unsigned __int16 *v39; // r9
  unsigned __int16 *v40; // rdi
  const unsigned __int16 *v41; // r9
  __int64 v42; // rax
  struct _BLB_COMPONENT *v43; // r12
  __int64 v44; // r13
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // r8
  __int64 v50; // rcx
  const OLECHAR *v51; // rcx
  const OLECHAR *v52; // rax
  const OLECHAR *v53; // rcx
  int v54; // eax
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  int v58; // r10d
  int v59; // r11d
  int v60; // ebx
  int v61; // edi
  int v62; // esi
  int v63; // r14d
  __int64 v64; // [rsp+28h] [rbp-140h]
  __int64 v65; // [rsp+28h] [rbp-140h]
  __int64 v66; // [rsp+30h] [rbp-138h]
  __int64 v67; // [rsp+38h] [rbp-130h]
  __int64 v68; // [rsp+40h] [rbp-128h]
  __int64 v69; // [rsp+48h] [rbp-120h]
  __int64 v70; // [rsp+50h] [rbp-118h]
  __int64 v71; // [rsp+58h] [rbp-110h]
  __int64 v72; // [rsp+60h] [rbp-108h]
  __int64 v73; // [rsp+68h] [rbp-100h]
  __int64 v74; // [rsp+70h] [rbp-F8h]
  __int64 v75; // [rsp+78h] [rbp-F0h]
  __int64 v76; // [rsp+80h] [rbp-E8h]
  __int64 v77; // [rsp+88h] [rbp-E0h]
  __int64 v78; // [rsp+90h] [rbp-D8h]
  __int64 v79; // [rsp+98h] [rbp-D0h]
  __int64 v80; // [rsp+A0h] [rbp-C8h]
  __int64 v81; // [rsp+A8h] [rbp-C0h]
  __int64 v82; // [rsp+B0h] [rbp-B8h]
  __int64 v83; // [rsp+B8h] [rbp-B0h]
  __int64 v84; // [rsp+C0h] [rbp-A8h]
  __int64 v85; // [rsp+C8h] [rbp-A0h]
  unsigned __int16 *v86; // [rsp+E8h] [rbp-80h] BYREF
  unsigned __int16 *v87; // [rsp+F0h] [rbp-78h] BYREF
  unsigned __int16 *v88; // [rsp+F8h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+100h] [rbp-68h] BYREF
  unsigned __int16 *v90; // [rsp+108h] [rbp-60h] BYREF
  int v91; // [rsp+110h] [rbp-58h]
  unsigned __int16 *v92; // [rsp+118h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+120h] [rbp-48h] BYREF
  unsigned __int16 *v94; // [rsp+128h] [rbp-40h] BYREF
  unsigned int v95; // [rsp+130h] [rbp-38h]
  int v96; // [rsp+134h] [rbp-34h]
  unsigned __int16 *v97; // [rsp+140h] [rbp-28h] BYREF
  const OLECHAR *v98; // [rsp+148h] [rbp-20h]
  const OLECHAR *v99; // [rsp+150h] [rbp-18h]
  const OLECHAR *v100; // [rsp+158h] [rbp-10h]
  __int64 v101; // [rsp+160h] [rbp-8h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6073f0e2b9db3619c6870f43a06517b0_Traceguids);
  }
  v8 = 0;
  v92 = 0;
  v94 = 0;
  v9 = 0;
  v86 = 0;
  v97 = 0;
  v10 = 0;
  v90 = 0;
  v11 = 0;
  v87 = 0;
  v12 = 0;
  v88 = 0;
  v13 = 0;
  pv = 0;
  bstrString = 0;
  if ( *(_QWORD *)this )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbbackupitemsutils.cpp", 0xC0u, "m_wszSpecsXML == NULL");
  if ( *((_QWORD *)this + 1) )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbbackupitemsutils.cpp", 0xC1u, "m_spBackupItemsRoot == NULL");
  v14 = BlbutilMemalloc((void **)&v94, 0x1Cu, 2u);
  if ( v14 < 0 )
    goto LABEL_63;
  v14 = StringCchPrintfW(v94, 0x1Au, L"<BackupSpecs Version=\"%u\">");
  if ( v14 < 0 )
    goto LABEL_63;
  ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, v94);
  ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, L"<FileSpecs>");
  v15 = 0;
  v91 = 0;
  v16 = a2;
  while ( 1 )
  {
    if ( v15 >= v16 )
    {
      ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, L"</FileSpecs>");
      v14 = BlbutilMemalloc((void **)&v97, 41 - (unsigned int)(a6 != 0), 2u);
      if ( v14 < 0 )
        goto LABEL_61;
      v38 = L"true";
      v39 = L"true";
      if ( !a6 )
        v39 = L"false";
      v40 = v97;
      v14 = StringCchPrintfW(v97, 41 - (unsigned int)(a6 != 0), L"<SystemState IsPresent=\"%ws\" />", v39);
      if ( v14 < 0
        || (ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, v40),
            v14 = BlbutilMemalloc((void **)&v90, 41 - (unsigned int)(a7 != 0), 2u),
            v14 < 0) )
      {
LABEL_61:
        v12 = v88;
LABEL_62:
        v10 = v90;
        goto LABEL_63;
      }
      if ( !a7 )
        v38 = L"false";
      v41 = v38;
      v10 = v90;
      v14 = StringCchPrintfW(v90, 41 - (unsigned int)(a7 != 0), L"<AllCritical IsPresent=\"%ws\" />", v41);
      if ( v14 >= 0 )
      {
        ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, v10);
        ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, L"<ComponentSpecs>");
        v42 = 0;
        v43 = a5;
        v12 = v88;
        while ( 1 )
        {
          v91 = v42;
          if ( (unsigned int)v42 >= a4 )
            break;
          v44 = 9 * v42;
          v101 = 9 * v42;
          if ( v12 )
          {
            CoTaskMemFree(v12);
            v88 = 0;
          }
          v45 = *((_QWORD *)v43 + v44 + 1);
          if ( v45 )
          {
            v46 = -1;
            do
              ++v46;
            while ( *(_WORD *)(v45 + 2 * v46) );
          }
          else
          {
            LODWORD(v46) = 0;
          }
          v47 = *((_QWORD *)v43 + v44);
          if ( v47 )
          {
            v48 = -1;
            do
              ++v48;
            while ( *(_WORD *)(v47 + 2 * v48) );
          }
          else
          {
            LODWORD(v48) = 0;
          }
          v49 = *((_QWORD *)v43 + v44 + 6);
          if ( v49 )
          {
            v50 = -1;
            do
              ++v50;
            while ( *(_WORD *)(v49 + 2 * v50) );
          }
          else
          {
            LODWORD(v50) = 0;
          }
          v95 = v50 + 271 + v46 + v48;
          v14 = BlbutilMemalloc((void **)&v88, v95, 2u);
          if ( v14 < 0 )
          {
LABEL_86:
            v12 = v88;
            goto LABEL_87;
          }
          v51 = &String1;
          if ( *((_QWORD *)v43 + v44 + 6) )
            v51 = (const OLECHAR *)*((_QWORD *)v43 + v44 + 6);
          v98 = v51;
          v52 = &String1;
          if ( *((_QWORD *)v43 + v44) )
            v52 = (const OLECHAR *)*((_QWORD *)v43 + v44);
          v99 = v52;
          v53 = &String1;
          if ( *((_QWORD *)v43 + v44 + 1) )
            v53 = (const OLECHAR *)*((_QWORD *)v43 + v44 + 1);
          v100 = v53;
          v54 = *((unsigned __int8 *)v43 + 8 * v44 + 47);
          v55 = *((unsigned __int8 *)v43 + 8 * v44 + 46);
          v56 = *((unsigned __int8 *)v43 + 8 * v44 + 45);
          v57 = *((unsigned __int8 *)v43 + 8 * v44 + 44);
          v58 = *((unsigned __int8 *)v43 + 8 * v44 + 43);
          v59 = *((unsigned __int8 *)v43 + 8 * v44 + 42);
          v60 = *((unsigned __int8 *)v43 + 8 * v44 + 41);
          v61 = *((unsigned __int8 *)v43 + 8 * v44 + 40);
          v62 = *((unsigned __int16 *)v43 + 4 * v44 + 19);
          v63 = *((unsigned __int16 *)v43 + 4 * v44 + 18);
          v96 = *((unsigned __int8 *)v43 + 8 * v44 + 31);
          LODWORD(v85) = v54;
          LODWORD(v84) = v55;
          LODWORD(v83) = v56;
          LODWORD(v82) = v57;
          LODWORD(v81) = v58;
          LODWORD(v80) = v59;
          LODWORD(v79) = v60;
          LODWORD(v78) = v61;
          LODWORD(v77) = v62;
          LODWORD(v76) = v63;
          LODWORD(v75) = *((_DWORD *)a5 + 2 * v101 + 8);
          LODWORD(v74) = v96;
          LODWORD(v73) = *((unsigned __int8 *)v43 + 8 * v44 + 30);
          LODWORD(v72) = *((unsigned __int8 *)a5 + 8 * v44 + 29);
          v43 = a5;
          LODWORD(v71) = *((unsigned __int8 *)a5 + 8 * v101 + 28);
          LODWORD(v70) = *((unsigned __int8 *)a5 + 8 * v101 + 27);
          LODWORD(v69) = *((unsigned __int8 *)a5 + 8 * v101 + 26);
          LODWORD(v68) = *((unsigned __int8 *)a5 + 8 * v101 + 25);
          LODWORD(v67) = *((unsigned __int8 *)a5 + 8 * v101 + 24);
          LODWORD(v66) = *((unsigned __int16 *)a5 + 4 * v101 + 11);
          LODWORD(v64) = *((unsigned __int16 *)a5 + 4 * v101 + 10);
          v12 = v88;
          v14 = StringCchPrintfW(
                  v88,
                  v95,
                  L"<ComponentSpec WriterId=\"{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\" InstanceId=\"{%.8x-%.4x"
                   "-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\" ComponentName=\"%ws\" LogicalPath=\"%ws\" Caption=\"%ws\" />",
                  *((unsigned int *)a5 + 2 * v101 + 4),
                  v64,
                  v66,
                  v67,
                  v68,
                  v69,
                  v70,
                  v71,
                  v72,
                  v73,
                  v74,
                  v75,
                  v76,
                  v77,
                  v78,
                  v79,
                  v80,
                  v81,
                  v82,
                  v83,
                  v84,
                  v85,
                  v100,
                  v99,
                  v98);
          if ( v14 < 0 )
            goto LABEL_87;
          ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, v12);
          v42 = (unsigned int)(v91 + 1);
        }
        ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, L"</ComponentSpecs>");
        ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, L"</BackupSpecs>");
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6073f0e2b9db3619c6870f43a06517b0_Traceguids, bstrString);
        }
        v14 = CBlbBackupItemsHelper::Initialize((unsigned __int16 **)this, (struct ATL::CComBSTR *)&bstrString);
LABEL_87:
        v8 = v92;
        v13 = pv;
        goto LABEL_62;
      }
      v12 = v88;
LABEL_63:
      v30 = v87;
      goto LABEL_64;
    }
    v17 = (char *)a3 + 128 * (unsigned __int64)v15;
    if ( !v17[84] )
      goto LABEL_59;
    if ( v8 )
    {
      CoTaskMemFree(v8);
      v92 = 0;
    }
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v18 = 0;
      v86 = 0;
    }
    else
    {
      v18 = v86;
    }
    v14 = BlbutilQueryVolumeName((struct _GUID *)v17, *((_DWORD *)v17 + 22), &v92, 0);
    if ( v14 < 0 )
    {
      v30 = v87;
      v8 = v92;
      v12 = v88;
      v10 = v90;
      goto LABEL_65;
    }
    v19 = *((_QWORD *)v17 + 2);
    if ( v19 )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(v19 + 2 * v20) );
    }
    else
    {
      LODWORD(v20) = 0;
    }
    v21 = *((_QWORD *)v17 + 3);
    if ( v21 )
    {
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
    }
    else
    {
      LODWORD(v22) = 0;
    }
    v23 = -1;
    v8 = v92;
    do
      ++v23;
    while ( v92[v23] );
    v24 = v22 + 99 + v23 + v20;
    v14 = BlbutilMemalloc((void **)&v86, v24, 2u);
    if ( v14 < 0 )
      goto LABEL_61;
    v25 = &String1;
    if ( *((_QWORD *)v17 + 3) )
      v25 = (const OLECHAR *)*((_QWORD *)v17 + 3);
    v26 = &String1;
    if ( *((_QWORD *)v17 + 2) )
      v26 = (const OLECHAR *)*((_QWORD *)v17 + 2);
    v27 = v24;
    v9 = v86;
    v14 = StringCchPrintfW(
            v86,
            v27,
            L"<Volume Name=\"%ws\" AccessPath=\"%ws\" OriginalAccessPath=\"%ws\" Label=\"%ws\" OriginalLabel=\"%ws\" >",
            v8,
            v26,
            v25,
            &String1,
            &String1);
    if ( v14 < 0 )
      goto LABEL_61;
    ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, v9);
    if ( (v17[88] & 1) == 0 )
      break;
LABEL_58:
    ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, L"</Volume>");
    v16 = a2;
LABEL_59:
    v91 = ++v15;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)v17 + 26) )
    {
      v8 = v92;
      v15 = v91;
      goto LABEL_58;
    }
    v29 = *((_QWORD *)v17 + 14);
    if ( v11 )
    {
      CoTaskMemFree(v11);
      v30 = 0;
      v87 = 0;
    }
    else
    {
      v30 = v87;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v14 = BlbutilSlashTerminatePath(*(unsigned __int16 **)(v29 + 24LL * i), &pv);
    if ( v14 < 0 )
      break;
    v31 = -1;
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)pv + v32) );
    do
      ++v31;
    while ( *(_WORD *)(*(_QWORD *)(v29 + 24LL * i + 8) + 2 * v31) );
    v33 = 5 - (*(_BYTE *)(v29 + 24LL * i + 17) != 0) + v31 + v32 + 86 - (*(_BYTE *)(v29 + 24LL * i + 16) != 0);
    v14 = BlbutilMemalloc((void **)&v87, v33, 2u);
    if ( v14 < 0 )
      goto LABEL_86;
    v34 = L"true";
    v35 = L"true";
    if ( !*(_BYTE *)(v29 + 24LL * i + 17) )
      v35 = L"false";
    if ( !*(_BYTE *)(v29 + 24LL * i + 16) )
      v34 = L"false";
    v36 = v33;
    v65 = *(_QWORD *)(v29 + 24LL * i + 8);
    v13 = pv;
    v11 = v87;
    v14 = StringCchPrintfW(
            v87,
            v36,
            L"<FileSpec FilePath=\"%ws\" FileName=\"%ws\" IsRecursive=\"%ws\" IsInclude=\"%ws\" />",
            pv,
            v65,
            v34,
            v35);
    if ( v14 < 0 )
    {
      v8 = v92;
      goto LABEL_61;
    }
    ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, v11);
  }
  v8 = v92;
  v12 = v88;
  v13 = pv;
  v10 = v90;
LABEL_64:
  v18 = v86;
LABEL_65:
  if ( v94 )
    CoTaskMemFree(v94);
  if ( v18 )
    CoTaskMemFree(v18);
  if ( v30 )
    CoTaskMemFree(v30);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v13 )
    CoTaskMemFree(v13);
  if ( v97 )
    CoTaskMemFree(v97);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6073f0e2b9db3619c6870f43a06517b0_Traceguids);
  }
  SysFreeString(bstrString);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400fbfc0  mov     rax, rsp
0x1400fbfc3  mov     [rax+20h], r9d
0x1400fbfc7  mov     [rax+18h], r8
0x1400fbfcb  mov     [rax+10h], edx
0x1400fbfce  mov     [rax+8], rcx
0x1400fbfd2  push    rbp
0x1400fbfd3  push    rbx
0x1400fbfd4  push    rsi
0x1400fbfd5  push    rdi
0x1400fbfd6  push    r12
0x1400fbfd8  push    r13
0x1400fbfda  push    r14
0x1400fbfdc  push    r15
0x1400fbfde  lea     rbp, [rax-48h]
0x1400fbfe2  sub     rsp, 168h
0x1400fbfe9  mov     rbx, rcx
0x1400fbfec  lea     rax, WPP_GLOBAL_Control
0x1400fbff3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400fbffa  cmp     rcx, rax
0x1400fbffd  jz      short loc_1400FC020
0x1400fbfff  test    byte ptr [rcx+1Ch], 1
0x1400fc003  jz      short loc_1400FC020
0x1400fc005  cmp     byte ptr [rcx+19h], 4
0x1400fc009  jb      short loc_1400FC020
0x1400fc00b  mov     edx, 0Ah
0x1400fc010  lea     r8, WPP_6073f0e2b9db3619c6870f43a06517b0_Traceguids
0x1400fc017  mov     rcx, [rcx+10h]
0x1400fc01b  call    WPP_SF_
0x1400fc020  xor     eax, eax
0x1400fc022  mov     r15d, eax
0x1400fc025  mov     [rbp+40h+var_90], rax
0x1400fc029  mov     [rbp+40h+var_80], rax
0x1400fc02d  mov     esi, eax
0x1400fc02f  mov     [rbp+40h+var_C0], rax
0x1400fc033  mov     [rbp+40h+var_68], rax
0x1400fc037  mov     r13d, eax
0x1400fc03a  mov     [rbp+40h+var_A0], rax
0x1400fc03e  mov     r14d, eax
0x1400fc041  mov     [rbp+40h+var_B8], rax
0x1400fc045  mov     edi, eax
0x1400fc047  mov     [rbp+40h+var_B0], rax
0x1400fc04b  mov     r12d, eax
0x1400fc04e  mov     [rbp+40h+pv], rax
0x1400fc052  mov     [rbp+40h+bstrString], rax
0x1400fc056  cmp     [rbx], rax
0x1400fc059  jz      short loc_1400FC075
0x1400fc05b  lea     r8, aMWszspecsxmlNu; "m_wszSpecsXML == NULL"
0x1400fc062  mov     edx, 0C0h; unsigned int
0x1400fc067  lea     rcx, aBaseStorBlbEng_49; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400fc06e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400fc073  xor     eax, eax
0x1400fc075  cmp     [rbx+8], rax
0x1400fc079  jz      short loc_1400FC093
0x1400fc07b  lea     r8, aMSpbackupitems; "m_spBackupItemsRoot == NULL"
0x1400fc082  mov     edx, 0C1h; unsigned int
0x1400fc087  lea     rcx, aBaseStorBlbEng_49; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400fc08e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400fc093  mov     edx, 1Ch; unsigned int
0x1400fc098  lea     r8d, [rdx-1Ah]; unsigned int
0x1400fc09c  lea     rcx, [rbp+40h+var_80]; void **
0x1400fc0a0  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400fc0a5  mov     ebx, eax
0x1400fc0a7  test    eax, eax
0x1400fc0a9  js      loc_1400FC3A8
0x1400fc0af  mov     r9d, 1
0x1400fc0b5  lea     r8, aBackupspecsVer; "<BackupSpecs Version=\"%u\">"
0x1400fc0bc  lea     edx, [r9+19h]; unsigned __int64
0x1400fc0c0  mov     rcx, [rbp+40h+var_80]; unsigned __int16 *
0x1400fc0c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400fc0c9  mov     ebx, eax
0x1400fc0cb  test    eax, eax
0x1400fc0cd  js      loc_1400FC3A8
0x1400fc0d3  mov     rdx, [rbp+40h+var_80]
0x1400fc0d7  lea     rcx, [rbp+40h+bstrString]
0x1400fc0db  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1400fc0e0  lea     rdx, aFilespecs; "<FileSpecs>"
0x1400fc0e7  lea     rcx, [rbp+40h+bstrString]
0x1400fc0eb  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1400fc0f0  xor     ebx, ebx
0x1400fc0f2  mov     r13d, ebx
0x1400fc0f5  mov     [rbp+40h+var_98], ebx
0x1400fc0f8  mov     eax, [rbp+40h+arg_8]
0x1400fc0fb  cmp     r13d, eax
0x1400fc0fe  jnb     loc_1400FC4B7
0x1400fc104  mov     edi, r13d
0x1400fc107  shl     rdi, 7
0x1400fc10b  add     rdi, [rbp+40h+arg_10]
0x1400fc10f  cmp     [rdi+54h], bl
0x1400fc112  jz      loc_1400FC390
0x1400fc118  test    r15, r15
0x1400fc11b  jz      short loc_1400FC12A
0x1400fc11d  mov     rcx, r15; pv
0x1400fc120  call    cs:__imp_CoTaskMemFree
0x1400fc126  mov     [rbp+40h+var_90], rbx
0x1400fc12a  test    rsi, rsi
0x1400fc12d  jz      short loc_1400FC141
0x1400fc12f  mov     rcx, rsi; pv
0x1400fc132  call    cs:__imp_CoTaskMemFree
0x1400fc138  mov     rsi, rbx
0x1400fc13b  mov     [rbp+40h+var_C0], rbx
0x1400fc13f  jmp     short loc_1400FC145
0x1400fc141  mov     rsi, [rbp+40h+var_C0]
0x1400fc145  xor     r9d, r9d; unsigned __int8
0x1400fc148  lea     r8, [rbp+40h+var_90]; unsigned __int16 **
0x1400fc14c  mov     edx, [rdi+58h]; unsigned int
0x1400fc14f  mov     rcx, rdi; struct _GUID *
0x1400fc152  call    ?BlbutilQueryVolumeName@@YAJPEAU_GUID@@KPEAPEAGE@Z; BlbutilQueryVolumeName(_GUID *,ulong,ushort * *,uchar)
0x1400fc157  mov     ebx, eax
0x1400fc159  test    eax, eax
0x1400fc15b  js      loc_1400FC4A2
0x1400fc161  mov     rcx, [rdi+10h]
0x1400fc165  xor     ebx, ebx
0x1400fc167  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400fc16b  test    rcx, rcx
0x1400fc16e  jz      short loc_1400FC17E
0x1400fc170  mov     rax, r8
0x1400fc173  inc     rax
0x1400fc176  cmp     [rcx+rax*2], bx
0x1400fc17a  jnz     short loc_1400FC173
0x1400fc17c  jmp     short loc_1400FC181
0x1400fc17e  mov     rax, rbx
0x1400fc181  mov     rdx, [rdi+18h]
0x1400fc185  test    rdx, rdx
0x1400fc188  jz      short loc_1400FC198
0x1400fc18a  mov     rcx, r8
0x1400fc18d  inc     rcx
0x1400fc190  cmp     [rdx+rcx*2], bx
0x1400fc194  jnz     short loc_1400FC18D
0x1400fc196  jmp     short loc_1400FC19B
0x1400fc198  mov     rcx, rbx
0x1400fc19b  mov     rdx, r8
0x1400fc19e  mov     r15, [rbp+40h+var_90]
0x1400fc1a2  inc     rdx
0x1400fc1a5  cmp     [r15+rdx*2], bx
0x1400fc1aa  jnz     short loc_1400FC1A2
0x1400fc1ac  lea     esi, [rdx+rax]
0x1400fc1af  add     ecx, 63h ; 'c'
0x1400fc1b2  add     esi, ecx
0x1400fc1b4  mov     r8d, 2; unsigned int
0x1400fc1ba  mov     edx, esi; unsigned int
0x1400fc1bc  lea     rcx, [rbp+40h+var_C0]; void **
0x1400fc1c0  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400fc1c5  mov     ebx, eax
0x1400fc1c7  test    eax, eax
0x1400fc1c9  js      loc_1400FC3A0
0x1400fc1cf  lea     r8, String1
0x1400fc1d6  mov     rcx, r8
0x1400fc1d9  xor     ebx, ebx
0x1400fc1db  cmp     [rdi+18h], rbx
0x1400fc1df  cmovnz  rcx, [rdi+18h]
0x1400fc1e4  mov     rax, r8
0x1400fc1e7  cmp     [rdi+10h], rbx
0x1400fc1eb  cmovnz  rax, [rdi+10h]
0x1400fc1f0  mov     edx, esi; unsigned __int64
0x1400fc1f2  mov     [rsp+1A0h+var_168], r8
0x1400fc1f7  mov     [rsp+1A0h+var_170], r8
0x1400fc1fc  mov     [rsp+1A0h+var_178], rcx
0x1400fc201  mov     [rsp+1A0h+var_180], rax
0x1400fc206  mov     r9, r15
0x1400fc209  lea     r8, aVolumeNameWsAc; "<Volume Name=\"%ws\" AccessPath=\"%ws\""...
0x1400fc210  mov     rsi, [rbp+40h+var_C0]
0x1400fc214  mov     rcx, rsi; unsigned __int16 *
0x1400fc217  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400fc21c  mov     ebx, eax
0x1400fc21e  test    eax, eax
0x1400fc220  js      loc_1400FC3A0
0x1400fc226  mov     rdx, rsi
0x1400fc229  lea     rcx, [rbp+40h+bstrString]
0x1400fc22d  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1400fc232  xor     ebx, ebx
0x1400fc234  test    byte ptr [rdi+58h], 1
0x1400fc238  jnz     loc_1400FC37D
0x1400fc23e  mov     r13d, ebx
0x1400fc241  cmp     r13d, [rdi+68h]
0x1400fc245  jnb     loc_1400FC375
0x1400fc24b  mov     eax, r13d
0x1400fc24e  lea     r15, [rax+rax*2]
0x1400fc252  mov     r12, [rdi+70h]
0x1400fc256  test    r14, r14
0x1400fc259  jz      short loc_1400FC26D
0x1400fc25b  mov     rcx, r14; pv
0x1400fc25e  call    cs:__imp_CoTaskMemFree
0x1400fc264  mov     r14, rbx
0x1400fc267  mov     [rbp+40h+var_B8], rbx
0x1400fc26b  jmp     short loc_1400FC271
0x1400fc26d  mov     r14, [rbp+40h+var_B8]
0x1400fc271  mov     rax, [rbp+40h+pv]
0x1400fc275  test    rax, rax
0x1400fc278  jz      short loc_1400FC287
0x1400fc27a  mov     rcx, rax; pv
0x1400fc27d  call    cs:__imp_CoTaskMemFree
0x1400fc283  mov     [rbp+40h+pv], rbx
0x1400fc287  lea     rdx, [rbp+40h+pv]; unsigned __int16 **
0x1400fc28b  mov     rcx, [r12+r15*8]; unsigned __int16 *
0x1400fc28f  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x1400fc294  mov     ebx, eax
0x1400fc296  test    eax, eax
0x1400fc298  js      loc_1400FC48D
0x1400fc29e  mov     r9b, [r12+r15*8+10h]
0x1400fc2a3  mov     al, [r12+r15*8+11h]
0x1400fc2a8  neg     al
0x1400fc2aa  sbb     r8d, r8d
0x1400fc2ad  add     r8d, 5
0x1400fc2b1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400fc2b5  mov     rdx, rcx
0x1400fc2b8  mov     rax, [rbp+40h+pv]
0x1400fc2bc  xor     ebx, ebx
0x1400fc2be  inc     rdx
0x1400fc2c1  cmp     [rax+rdx*2], bx
0x1400fc2c5  jnz     short loc_1400FC2BE
0x1400fc2c7  mov     rax, [r12+r15*8+8]
0x1400fc2cc  inc     rcx
0x1400fc2cf  cmp     [rax+rcx*2], bx
0x1400fc2d3  jnz     short loc_1400FC2CC
0x1400fc2d5  neg     r9b
0x1400fc2d8  sbb     eax, eax
0x1400fc2da  lea     r14d, [rax+56h]
0x1400fc2de  add     r14d, edx
0x1400fc2e1  add     r14d, ecx
0x1400fc2e4  add     r14d, r8d
0x1400fc2e7  mov     r8d, 2; unsigned int
0x1400fc2ed  mov     edx, r14d; unsigned int
0x1400fc2f0  lea     rcx, [rbp+40h+var_B8]; void **
0x1400fc2f4  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400fc2f9  mov     ebx, eax
0x1400fc2fb  test    eax, eax
0x1400fc2fd  js      loc_1400FC47C
0x1400fc303  lea     rax, aTrue; "true"
0x1400fc30a  mov     rcx, rax
0x1400fc30d  xor     ebx, ebx
0x1400fc30f  cmp     [r12+r15*8+11h], bl
0x1400fc314  lea     rdx, aFalse_0; "false"
0x1400fc31b  cmovz   rcx, rdx
0x1400fc31f  cmp     [r12+r15*8+10h], bl
0x1400fc324  cmovz   rax, rdx
0x1400fc328  mov     edx, r14d; unsigned __int64
0x1400fc32b  mov     [rsp+1A0h+var_170], rcx
0x1400fc330  mov     [rsp+1A0h+var_178], rax
0x1400fc335  mov     rax, [r12+r15*8+8]
0x1400fc33a  mov     [rsp+1A0h+var_180], rax
0x1400fc33f  mov     r12, [rbp+40h+pv]
0x1400fc343  mov     r9, r12
0x1400fc346  lea     r8, aFilespecFilepa; "<FileSpec FilePath=\"%ws\" FileName=\"%"...
0x1400fc34d  mov     r14, [rbp+40h+var_B8]
0x1400fc351  mov     rcx, r14; unsigned __int16 *
0x1400fc354  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400fc359  mov     ebx, eax
0x1400fc35b  test    eax, eax
0x1400fc35d  js      short loc_1400FC39C
0x1400fc35f  mov     rdx, r14
0x1400fc362  lea     rcx, [rbp+40h+bstrString]
0x1400fc366  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1400fc36b  inc     r13d
0x1400fc36e  xor     ebx, ebx
0x1400fc370  jmp     loc_1400FC241
0x1400fc375  mov     r15, [rbp+40h+var_90]
0x1400fc379  mov     r13d, [rbp+40h+var_98]
0x1400fc37d  lea     rdx, aVolume_1; "</Volume>"
0x1400fc384  lea     rcx, [rbp+40h+bstrString]
0x1400fc388  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1400fc38d  mov     eax, [rbp+40h+arg_8]
0x1400fc390  inc     r13d
0x1400fc393  mov     [rbp+40h+var_98], r13d
0x1400fc397  jmp     loc_1400FC0FB
0x1400fc39c  mov     r15, [rbp+40h+var_90]
0x1400fc3a0  mov     rdi, [rbp+40h+var_B0]
0x1400fc3a4  mov     r13, [rbp+40h+var_A0]
0x1400fc3a8  mov     r14, [rbp+40h+var_B8]
0x1400fc3ac  mov     rsi, [rbp+40h+var_C0]
0x1400fc3b0  cmp     [rbp+40h+var_80], 0
0x1400fc3b5  jz      short loc_1400FC3C1
0x1400fc3b7  mov     rcx, [rbp+40h+var_80]; pv
0x1400fc3bb  call    cs:__imp_CoTaskMemFree
0x1400fc3c1  test    rsi, rsi
0x1400fc3c4  jz      short loc_1400FC3CF
0x1400fc3c6  mov     rcx, rsi; pv
0x1400fc3c9  call    cs:__imp_CoTaskMemFree
0x1400fc3cf  test    r14, r14
0x1400fc3d2  jz      short loc_1400FC3DD
0x1400fc3d4  mov     rcx, r14; pv
0x1400fc3d7  call    cs:__imp_CoTaskMemFree
0x1400fc3dd  test    rdi, rdi
0x1400fc3e0  jz      short loc_1400FC3EB
0x1400fc3e2  mov     rcx, rdi; pv
0x1400fc3e5  call    cs:__imp_CoTaskMemFree
0x1400fc3eb  test    r12, r12
0x1400fc3ee  jz      short loc_1400FC3F9
0x1400fc3f0  mov     rcx, r12; pv
0x1400fc3f3  call    cs:__imp_CoTaskMemFree
0x1400fc3f9  mov     rax, [rbp+40h+var_68]
0x1400fc3fd  test    rax, rax
0x1400fc400  jz      short loc_1400FC40B
0x1400fc402  mov     rcx, rax; pv
0x1400fc405  call    cs:__imp_CoTaskMemFree
0x1400fc40b  test    r13, r13
0x1400fc40e  jz      short loc_1400FC419
0x1400fc410  mov     rcx, r13; pv
0x1400fc413  call    cs:__imp_CoTaskMemFree
0x1400fc419  test    r15, r15
0x1400fc41c  jz      short loc_1400FC427
  ... truncated ...
```
