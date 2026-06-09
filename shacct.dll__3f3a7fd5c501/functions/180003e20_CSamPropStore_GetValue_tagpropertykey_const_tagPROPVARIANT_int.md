# CSamPropStore::_GetValue(_tagpropertykey const &,tagPROPVARIANT *,int)

- ea: `0x180003e20`
- end: `0x180004bdd`
- name: `?_GetValue@CSamPropStore@@AEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@H@Z`
- size: `3517`
- prototype: `__int64 __fastcall(struct IPropertyStore *this, const struct _tagpropertykey *, struct tagPROPVARIANT *, int)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000bbb0`
- `0x180015660`

## callees

- `0x1800037e0`
- `0x180003e20`
- `0x180004bf0`
- `0x180004fd0`
- `0x180005d80`
- `0x180006f80`
- `0x1800087b0`
- `0x180008890`
- `0x18000b290`
- `0x18000b410`
- `0x18000c240`
- `0x180010a3c`
- `0x180012f18`
- `0x180013534`
- `0x18001645c`
- `0x180016698`
- `0x180016834`
- `0x180016ce9`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800044e7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000458f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800044e7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000458f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800042c6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800042c6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000429b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004370`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000429b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180004370`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004b90`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180004b90`
- `PROPSYS!VariantToPropVariant` at `0x180004aab`
- `PROPSYS!VariantToPropVariant` at `0x180004aab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000426a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000426a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800042d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800049e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800040ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800042a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000440e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800049b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004b0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800040ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800042a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000440e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800049b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004a49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004b0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000461e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000461e`
- `OLEAUT32!__imp_VariantClear` at `0x180004ab8`
- `OLEAUT32!__imp_VariantClear` at `0x180004ab8`
- `SAMLIB!SamRidToSid` at `0x18000428c`
- `SAMLIB!SamRidToSid` at `0x18000428c`
- `SAMLIB!SamOpenDomain` at `0x1800041e4`
- `SAMLIB!SamOpenDomain` at `0x1800041e4`
- `SAMLIB!SamConnect` at `0x1800041c1`
- `SAMLIB!SamConnect` at `0x1800041c1`
- `SAMLIB!SamCloseHandle` at `0x180004203`
- `SAMLIB!SamCloseHandle` at `0x180004343`
- `SAMLIB!SamCloseHandle` at `0x18000434c`
- `SAMLIB!SamCloseHandle` at `0x180004203`
- `SAMLIB!SamCloseHandle` at `0x180004343`
- `SAMLIB!SamCloseHandle` at `0x18000434c`
- `SAMLIB!SamFreeMemory` at `0x1800042f8`
- `SAMLIB!SamFreeMemory` at `0x1800042f8`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180004838`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180004838`

## pseudocode

```c
__int64 __fastcall CSamPropStore::_GetValue(
        struct IPropertyStore *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3,
        int a4)
{
  int v7; // ebx
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int128 *v11; // rbx
  __int128 *v12; // r9
  int lpVtbl_high; // r10d
  unsigned int v14; // r11d
  unsigned int v15; // r8d
  __int64 i; // rdx
  DWORD pid; // eax
  char *v18; // rsi
  __int64 v19; // rcx
  __int64 j; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  struct IPropertyStoreVtbl *lpVtbl; // rax
  unsigned int v29; // eax
  unsigned int v30; // edi
  BYTE *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  void *v34; // rdi
  LPVOID v35; // r12
  unsigned int v36; // r13d
  FILETIME v37; // r14
  int v38; // eax
  int v39; // r15d
  int v40; // ebx
  int v41; // ebx
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  int v44; // eax
  SIZE_T LengthSid; // r15
  void *v46; // rax
  void *v47; // rdi
  signed int LastError; // eax
  VARTYPE v49; // ax
  struct tagPROPVARIANT *v50; // rsi
  __int64 v51; // rcx
  LONG v52; // eax
  __int64 v53; // rcx
  struct IPropertyStoreVtbl *v54; // r15
  __int64 QueryInterface_low; // r15
  BYTE *v56; // r12
  VARTYPE v57; // ax
  unsigned int v58; // esi
  __int64 v59; // rdi
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rcx
  struct IPropertyStoreVtbl *v63; // rdi
  const wchar_t *GetValue; // rdi
  unsigned int v65; // r12d
  wchar_t *v66; // rax
  void *v67; // rcx
  void **v68; // r9
  HRESULT (__stdcall *k)(IPropertyStore *, const PROPERTYKEY *const, PROPVARIANT *); // rdi
  wchar_t *v70; // rax
  wchar_t *v71; // rsi
  __int64 v72; // r8
  __int64 v73; // rax
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  struct IPropertyStoreVtbl *v85; // rcx
  __int64 v86; // rcx
  bool v87; // cf
  __int64 v88; // rcx
  int v89; // ecx
  int v90; // ecx
  __int64 v91; // rcx
  bool v92; // al
  __int64 v93; // rax
  bool v94; // al
  VARTYPE v95; // ax
  HRESULT inited; // esi
  struct _UNICODE_STRING *v97; // r15
  unsigned __int16 *v98; // rax
  unsigned __int16 *v99; // rbx
  BYTE *v100; // rax
  __int64 v101; // rax
  unsigned int v102; // esi
  unsigned __int16 *v103; // rax
  unsigned __int16 *v104; // rdi
  __int64 v105; // rdx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchName[2]; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime2; // [rsp+40h] [rbp-C0h] BYREF
  PSID pSid; // [rsp+48h] [rbp-B8h] BYREF
  struct tagPROPVARIANT *v110; // [rsp+50h] [rbp-B0h]
  VARIANTARG ReferencedDomainName; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v112; // [rsp+70h] [rbp-90h]
  __int128 v113; // [rsp+78h] [rbp-88h]
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  v110 = a3;
  if ( !a3 )
    return (unsigned int)-2147467261;
  if ( !a4 || !this[12].lpVtbl || (unsigned int)CSamPropStore::_FindSamPropKey((CSamPropStore *)this, a2, 0) )
  {
LABEL_11:
    v11 = &xmmword_18001FEE0;
    *(_OWORD *)&a3->vt = 0;
    a3->bstrblobVal.pData = 0;
    v12 = &xmmword_18001FAC0;
    lpVtbl_high = HIDWORD(this[10].lpVtbl);
    v14 = 13;
    v15 = 29;
    if ( lpVtbl_high != 1 )
    {
      v14 = 10;
      v15 = 9;
      v11 = &xmmword_180020210;
      v12 = &xmmword_1800200C0;
    }
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= v15 )
      {
        for ( j = 0; (unsigned int)j < v14; j = (unsigned int)(j + 1) )
        {
          pid = a2->pid;
          v18 = (char *)v11 + 36 * j;
          if ( pid == *((_DWORD *)v18 + 4) )
          {
            v21 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v18;
            if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v18 )
              v21 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)v18 + 1);
            if ( !v21 )
              goto LABEL_27;
          }
        }
        return (unsigned int)-2147024809;
      }
      pid = a2->pid;
      v18 = (char *)v12 + 36 * i;
      if ( pid == *((_DWORD *)v18 + 4) )
      {
        v19 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v18;
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v18 )
          v19 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)v18 + 1);
        if ( !v19 )
          break;
      }
    }
LABEL_27:
    v7 = 0;
    if ( pid != *((_DWORD *)v18 + 4) )
      return (unsigned int)v7;
    v22 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v18;
    if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v18 )
      v22 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)v18 + 1);
    if ( v22 )
      return (unsigned int)v7;
    v23 = *((_DWORD *)v18 + 8);
    if ( lpVtbl_high == 1 )
    {
      v24 = 4;
      if ( !v23 )
        v24 = 3;
    }
    else
    {
      v24 = 5;
      if ( v23 )
        v24 = 6;
    }
    v25 = *((unsigned int *)v18 + 6);
    if ( (_DWORD)v25 == -1 )
    {
      if ( pid == 32 )
      {
        v26 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_Type;
        if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_Type )
          v26 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_Type + 1);
        if ( !v26 )
        {
          if ( lpVtbl_high == 1 )
          {
            a3->vt = 19;
            a3->lVal = 1;
            return (unsigned int)v7;
          }
          if ( lpVtbl_high == 2 )
          {
            a3->vt = 19;
            a3->lVal = 2;
            return (unsigned int)v7;
          }
          return (unsigned int)-2147024809;
        }
      }
      if ( pid == 20 )
      {
        v27 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_LogonHours;
        if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_LogonHours )
          v27 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_LogonHours + 1);
        if ( !v27 )
        {
          lpVtbl = this[3].lpVtbl;
          if ( !lpVtbl[4].GetValue )
            return (unsigned int)v7;
          v29 = LOWORD(lpVtbl[4].GetAt) >> 3 != 0;
          a3->lVal = v29;
          v30 = v29;
          v31 = (BYTE *)CoTaskMemAlloc(v29);
          a3->bstrblobVal.pData = v31;
          if ( v31 )
          {
            memcpy_0(v31, this[3].lpVtbl[4].GetValue, v30);
            a3->vt = *((_WORD *)v18 + 10);
            return (unsigned int)v7;
          }
          return (unsigned int)-2147024882;
        }
      }
      if ( pid == 31 )
      {
        v32 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_Groups;
        if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_Groups )
          v32 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_Groups + 1);
        if ( !v32 )
          return (unsigned int)InitPropVariantFromString(L"Need to implement Groups", a3);
      }
      if ( pid != 18 )
        goto LABEL_98;
      v33 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_SecurityID;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_SecurityID )
        v33 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_SecurityID + 1);
      if ( v33 )
      {
LABEL_98:
        if ( pid == 103 )
        {
          v51 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_ResidualID;
          if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_ResidualID )
            v51 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_ResidualID + 1);
          if ( !v51 )
          {
            v52 = (LONG)this[10].lpVtbl;
            a3->vt = 19;
            a3->lVal = v52;
            return (unsigned int)v7;
          }
        }
        if ( pid != 102 )
          goto LABEL_118;
        v53 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_GroupMembers;
        if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_GroupMembers )
          v53 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_GroupMembers + 1);
        if ( v53 )
        {
LABEL_118:
          if ( pid == 15 )
          {
            v62 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_Workstations;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_Workstations )
              v62 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_Workstations + 1);
            if ( !v62 )
            {
              v63 = this[3].lpVtbl;
              if ( v63 && LOWORD(v63[2].GetAt) )
              {
                GetValue = (const wchar_t *)v63[2].GetValue;
                v65 = 0;
                while ( *GetValue )
                {
                  v66 = wcschr(GetValue, 0x2Cu);
                  if ( !v66 )
                  {
                    ++v65;
                    break;
                  }
                  if ( (char *)v66 - (char *)GetValue >= 0
                    && (((char *)v66 - (char *)GetValue) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
                  {
                    ++v65;
                  }
                  GetValue = v66 + 1;
                }
                if ( v65 )
                {
                  a3->vt = *((_WORD *)v18 + 10);
                  a3->lVal = 0;
                  a3->bstrblobVal.pData = 0;
                  FileTime2 = 0;
                  v7 = ULongLongMult(v65, 8u, (unsigned __int64 *)&FileTime2);
                  if ( v7 >= 0 )
                    v7 = CTCoAllocPolicy::Alloc(v67, 1u, *(_QWORD *)&FileTime2, v68);
                  if ( v7 >= 0 )
                  {
                    for ( k = this[3].lpVtbl[2].GetValue;
                          *(_WORD *)k && a3->lVal < v65;
                          k = (HRESULT (__stdcall *)(IPropertyStore *, const PROPERTYKEY *const, PROPVARIANT *))(v71 + 1) )
                    {
                      if ( v7 < 0 )
                        goto LABEL_146;
                      v70 = wcschr((const wchar_t *)k, 0x2Cu);
                      v71 = v70;
                      if ( !v70 )
                      {
                        v73 = -1;
                        do
                          ++v73;
                        while ( *((_WORD *)k + v73) );
                        v7 = _AllocStringWorker<CTCoAllocPolicy>(
                               a3->ulVal,
                               &a3->bstrblobVal.pData[8 * a3->ulVal],
                               k,
                               v73);
                        if ( v7 >= 0 )
                        {
                          ++a3->lVal;
                          return (unsigned int)v7;
                        }
                        goto LABEL_146;
                      }
                      v72 = ((char *)v70 - (char *)k) >> 1;
                      if ( v72 > 0 )
                      {
                        v7 = _AllocStringWorker<CTCoAllocPolicy>(a3->bstrblobVal.pData, a3->ulVal, k, (unsigned int)v72);
                        if ( v7 >= 0 )
                          ++a3->lVal;
                      }
                    }
                    if ( v7 >= 0 )
                      return (unsigned int)v7;
                  }
LABEL_146:
                  PropVariantClear((PROPVARIANT *)a3);
                }
              }
              return (unsigned int)v7;
            }
          }
          if ( pid == 36 )
          {
            v74 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_InteractiveLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_InteractiveLogin )
              v74 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_InteractiveLogin + 1);
            if ( !v74 )
              goto LABEL_187;
          }
          if ( pid == 37 )
          {
            v75 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_NetworkLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_NetworkLogin )
              v75 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_NetworkLogin + 1);
            if ( !v75 )
              goto LABEL_187;
          }
          if ( pid == 38 )
          {
            v76 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_BatchLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_BatchLogin )
              v76 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_BatchLogin + 1);
            if ( !v76 )
              goto LABEL_187;
          }
          if ( pid == 39 )
          {
            v77 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_ServiceLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_ServiceLogin )
              v77 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_ServiceLogin + 1);
            if ( !v77 )
              goto LABEL_187;
          }
          if ( pid == 40 )
          {
            v78 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_RemoteInteractiveLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_RemoteInteractiveLogin )
              v78 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_RemoteInteractiveLogin + 1);
            if ( !v78 )
              goto LABEL_187;
          }
          if ( pid == 41 )
          {
            v79 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyInteractiveLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyInteractiveLogin )
              v79 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyInteractiveLogin + 1);
            if ( !v79 )
              goto LABEL_187;
          }
          if ( pid == 42 )
          {
            v80 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyNetworkLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyNetworkLogin )
              v80 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyNetworkLogin + 1);
            if ( !v80 )
              goto LABEL_187;
          }
          if ( pid == 43 )
          {
            v81 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyBatchLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyBatchLogin )
              v81 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyBatchLogin + 1);
            if ( !v81 )
              goto LABEL_187;
          }
          if ( pid == 44 )
          {
            v82 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyServiceLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyServiceLogin )
              v82 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyServiceLogin + 1);
            if ( !v82 )
              goto LABEL_187;
          }
          if ( pid == 45 )
          {
            v83 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyRemoteInteractiveLogin;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyRemoteInteractiveLogin )
              v83 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyRemoteInteractiveLogin + 1);
            if ( !v83 )
            {
LABEL_187:
              v7 = CSamPropStore::_PopulateAccountRights((CSamPropStore *)this);
              if ( v7 >= 0 )
              {
                a3->vt = *((_WORD *)v18 + 10);
                a3->iVal = -((*((_DWORD *)v18 + 7) & (__int64)this[8].lpVtbl) != 0);
              }
              return (unsigned int)v7;
            }
          }
          if ( pid == 26 )
          {
            v84 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_Domain;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_Domain )
              v84 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_Domain + 1);
            if ( !v84 )
            {
              v85 = this[11].lpVtbl;
              cchName[0] = 257;
              LODWORD(pv) = 16;
              LODWORD(pSid) = 0;
              if ( LookupAccountSidLocalW(
                     v85,
                     Name,
                     cchName,
                     &ReferencedDomainName.vt,
                     (LPDWORD)&pv,
                     (PSID_NAME_USE)&pSid) )
              {
                return (unsigned int)InitPropVariantFromString(&ReferencedDomainName.vt, a3);
              }
              else
              {
                return 1;
              }
            }
          }
          if ( pid != 50 )
            goto LABEL_204;
          v86 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_PasswordIsEmpty;
          if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_PasswordIsEmpty )
            v86 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_PasswordIsEmpty + 1);
          if ( v86 )
          {
LABEL_204:
            if ( pid != 51 )
              goto LABEL_214;
            v88 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_AccountIsDisabledForLogonUI;
            if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_AccountIsDisabledForLogonUI )
              v88 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_AccountIsDisabledForLogonUI + 1);
            if ( v88 )
            {
LABEL_214:
              if ( pid != 2 )
                goto LABEL_216;
              v91 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_AllowedLogon;
              if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_AllowedLogon )
                v91 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_AllowedLogon + 1);
              if ( v91 )
              {
LABEL_216:
                if ( pid == 3 )
                {
                  v93 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DontEnumerateForLogon;
                  if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DontEnumerateForLogon )
                    v93 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DontEnumerateForLogon + 1);
                  if ( !v93 )
                  {
                    v94 = DontEnumerateForLogon(this);
                    a3->vt = 11;
                    a3->iVal = !v94 - 1;
                  }
                }
              }
              else
              {
                v92 = IsUserAllowedLogon(this);
                a3->vt = 11;
                a3->iVal = !v92 - 1;
              }
              return (unsigned int)v7;
            }
            v89 = HIDWORD(this[9].lpVtbl);
            if ( !v89 )
              return (unsigned int)-2147467259;
            v90 = v89 - 1;
            if ( !v90 )
            {
              a3->vt = 11;
              a3->iVal = -1;
              return (unsigned int)v7;
            }
            if ( v90 != 1 )
              return (unsigned int)-2147467259;
            a3->vt = 11;
          }
          else
          {
            v87 = LODWORD(this[9].lpVtbl) != 0;
            a3->vt = 11;
            a3->iVal = -v87;
          }
          return (unsigned int)v7;
        }
        v54 = this[7].lpVtbl;
        if ( !v54 )
          return (unsigned int)v7;
        QueryInterface_low = LODWORD(v54->QueryInterface);
        if ( (int)QueryInterface_low <= 0 )
          return (unsigned int)v7;
        if ( (unsigned __int64)(24 * QueryInterface_low) > 0xFFFFFFFF )
          return (unsigned int)-2147024362;
        v56 = (BYTE *)CoTaskMemAlloc((unsigned int)(24 * QueryInterface_low));
        if ( v56 )
        {
          v57 = *((_WORD *)v18 + 10);
          v58 = 0;
          a3->vt = v57;
          a3->lVal = QueryInterface_low;
          a3->bstrblobVal.pData = v56;
          v59 = 0;
          do
          {
            v60 = *((_QWORD *)this[7].lpVtbl->AddRef + v59);
            if ( v60 )
            {
              v61 = 3 * v59;
              *(_WORD *)&v56[8 * v61] = 13;
              *(_QWORD *)&v56[8 * v61 + 8] = v60;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 8LL))(v60);
            }
            ++v58;
            ++v59;
          }
          while ( v58 < (unsigned int)QueryInterface_low );
          return (unsigned int)v7;
        }
        return (unsigned int)-2147024882;
      }
      v34 = this[11].lpVtbl;
      v35 = 0;
      v36 = (unsigned int)this[10].lpVtbl;
      v37 = 0;
      *(_QWORD *)cchName = 0;
      pv = v34;
      if ( v34 )
      {
        v39 = 0;
      }
      else
      {
        v38 = CSGetAccountDomainSid(&pv, v24 * 8);
        v34 = pv;
        v7 = v38;
        v39 = 1;
        if ( v38 < 0 )
        {
LABEL_77:
          CoTaskMemFree(v34);
LABEL_78:
          if ( v7 < 0 )
          {
            v47 = *(void **)cchName;
LABEL_93:
            if ( v7 >= 0 )
            {
              v49 = *((_WORD *)v18 + 10);
              v50 = v110;
              v110->vt = v49;
              v50->lVal = GetLengthSid(v47);
              v50->bstrblobVal.pData = (BYTE *)v47;
            }
            return (unsigned int)v7;
          }
          pSid = 0;
          v44 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))SamRidToSid)(v37, v36, &pSid);
          if ( v44 < 0 )
          {
            v7 = v44 | 0x10000000;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_dD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                68,
                WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
                v36,
                v7);
            v47 = *(void **)cchName;
            goto LABEL_91;
          }
          LengthSid = GetLengthSid(pSid);
          v46 = CoTaskMemAlloc(LengthSid);
          v47 = v46;
          if ( v46 )
          {
            if ( CopySid(LengthSid, v46, pSid) )
            {
LABEL_86:
              SamFreeMemory(pSid);
LABEL_91:
              ((void (__fastcall *)(_QWORD))SamCloseHandle)(v37);
              SamCloseHandle(v35);
              goto LABEL_93;
            }
            CoTaskMemFree(v47);
            LastError = GetLastError();
            v7 = LastError;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v7 = -2147024882;
          }
          v47 = *(void **)cchName;
          goto LABEL_86;
        }
      }
      *(_OWORD *)&ReferencedDomainName.vt = 0x30u;
      v112 = 0;
      pv = 0;
      ReferencedDomainName.pRecInfo = 0;
      v113 = 0;
      v40 = SamConnect(0, &pv, 131121, &ReferencedDomainName);
      if ( v40 < 0 )
      {
        v7 = v40 | 0x10000000;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v43 = 35;
          goto LABEL_75;
        }
      }
      else
      {
        FileTime2 = 0;
        v41 = SamOpenDomain(pv, 131973, v34, &FileTime2);
        if ( v41 >= 0 )
        {
          v37 = FileTime2;
          v7 = 0;
          v35 = pv;
          goto LABEL_76;
        }
        SamCloseHandle(pv);
        v7 = v41 | 0x10000000;
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v43 = 34;
LABEL_75:
          WPP_SF_d(v42[2], v43, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v7);
        }
      }
LABEL_76:
      if ( !v39 )
        goto LABEL_78;
      goto LABEL_77;
    }
    v95 = *((_WORD *)v18 + 10);
    v7 = -2147467259;
    inited = -2147467259;
    v97 = (struct _UNICODE_STRING *)((char *)this[v24].lpVtbl + v25);
    switch ( v95 )
    {
      case 0x1Fu:
        if ( v97 )
        {
          v98 = (unsigned __int16 *)CoTaskMemAlloc(v97->Length + 2LL);
          v99 = v98;
          if ( v98 )
          {
            CopyUstrToPstr(v97, v98, v97->Length + 2);
            inited = InitPropVariantFromString(v99, a3);
            CoTaskMemFree(v99);
          }
          else
          {
            inited = -2147024882;
          }
        }
        break;
      case 0x40u:
        a3->hVal.QuadPart = *(_QWORD *)&v97->Length;
        a3->vt = 64;
        return (unsigned int)v7;
      case 0x41u:
        if ( v97 )
        {
          if ( !*(_DWORD *)&v97->Length )
          {
            v7 = 0;
            goto LABEL_238;
          }
          a3->vt = 65;
          inited = -2147024882;
          a3->lVal = *(_DWORD *)&v97->Length;
          v100 = (BYTE *)CoTaskMemAlloc(*(unsigned int *)&v97->Length);
          a3->bstrblobVal.pData = v100;
          if ( v100 )
          {
            memcpy_0(v100, v97->Buffer, *(unsigned int *)&v97->Length);
            inited = 0;
          }
        }
        break;
      case 0xBu:
        a3->vt = 11;
        a3->iVal = -(*(_DWORD *)&v97->Length != 0);
        v7 = 0;
        goto LABEL_238;
      default:
        *(_OWORD *)&ReferencedDomainName.vt = 0;
        ReferencedDomainName.vt = v95;
        *(_OWORD *)&ReferencedDomainName.decVal.Lo32 = *(unsigned __int64 *)&v97->Length;
        inited = VariantToPropVariant(&ReferencedDomainName, (PROPVARIANT *)a3);
        VariantClear(&ReferencedDomainName);
        break;
    }
    v7 = inited;
    if ( inited < 0 )
      return (unsigned int)v7;
LABEL_238:
    if ( a2->pid != 46 )
      goto LABEL_256;
    v101 = PKEY_SAM_DontShowInLogonUI - *(_QWORD *)&a2->fmtid.Data1;
    if ( (_QWORD)PKEY_SAM_DontShowInLogonUI == *(_QWORD *)&a2->fmtid.Data1 )
      v101 = *((_QWORD *)&PKEY_SAM_DontShowInLogonUI + 1) - *(_QWORD *)a2->fmtid.Data4;
    if ( v101 )
    {
LABEL_256:
      if ( (unsigned int)operator==(&PKEY_SAM_DateAccountExpires, a2)
        || (unsigned int)operator==(&PKEY_SAM_PasswordMustChange, v105) )
      {
        FileTime2.dwLowDateTime = -1;
        FileTime2.dwHighDateTime = 0x7FFFFFFF;
        if ( !CompareFileTime(&a3->filetime, &FileTime2) )
        {
          a3->lVal = -1487503360;
          a3->hVal.HighPart = 617109909;
        }
      }
    }
    else if ( !a3->iVal )
    {
      v102 = LOWORD(this[3].lpVtbl->SetValue) + 2;
      v103 = (unsigned __int16 *)CoTaskMemAlloc(v102);
      v104 = v103;
      if ( v103 )
      {
        v7 = CopyUstrToPstr((struct _UNICODE_STRING *const)&this[3].lpVtbl->SetValue, v103, v102);
        if ( v7 >= 0 )
        {
          v7 = CSShowUserInLogonUI(v104);
          if ( v7 >= 1 )
            a3->iVal = -1;
        }
        CoTaskMemFree(v104);
      }
    }
    return (unsigned int)v7;
  }
  result = (*((__int64 (__fastcall **)(struct IPropertyStoreVtbl *, const struct _tagpropertykey *, struct tagPROPVARIANT *))this[12].lpVtbl->QueryInterface
            + 5))(
             this[12].lpVtbl,
             a2,
             a3);
  if ( (int)result < 0 || !a3->vt )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF__guid_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a2, a2->pid, result);
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x180003e20  push    rbp
0x180003e22  push    rbx
0x180003e23  push    rdi
0x180003e24  push    r12
0x180003e26  push    r13
0x180003e28  push    r14
0x180003e2a  push    r15
0x180003e2c  lea     rbp, [rsp-1B0h]
0x180003e34  sub     rsp, 2B0h
0x180003e3b  mov     rax, cs:__security_cookie
0x180003e42  xor     rax, rsp
0x180003e45  mov     [rbp+1E0h+var_40], rax
0x180003e4c  mov     [rsp+2E0h+var_290], r8
0x180003e51  mov     r13, r8
0x180003e54  mov     rdi, rdx
0x180003e57  mov     r14, rcx
0x180003e5a  test    r8, r8
0x180003e5d  jnz     short loc_180003E69
0x180003e5f  mov     ebx, 80004003h
0x180003e64  jmp     loc_180004BB9
0x180003e69  lea     rbx, WPP_GLOBAL_Control
0x180003e70  test    r9d, r9d
0x180003e73  jz      short loc_180003ED7
0x180003e75  cmp     qword ptr [rcx+60h], 0
0x180003e7a  jz      short loc_180003ED7
0x180003e7c  xor     r8d, r8d; struct _PROPMAP **
0x180003e7f  call    ?_FindSamPropKey@CSamPropStore@@AEAAJAEBU_tagpropertykey@@PEAPEAU_PROPMAP@@@Z; CSamPropStore::_FindSamPropKey(_tagpropertykey const &,_PROPMAP * *)
0x180003e84  test    eax, eax
0x180003e86  jnz     short loc_180003ED7
0x180003e88  mov     rcx, [r14+60h]
0x180003e8c  mov     r8, r13
0x180003e8f  mov     rdx, rdi
0x180003e92  mov     rax, [rcx]
0x180003e95  mov     rax, [rax+28h]
0x180003e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e9e  test    eax, eax
0x180003ea0  js      short loc_180003EAE
0x180003ea2  cmp     word ptr [r13+0], 0
0x180003ea8  jnz     loc_180004BBB
0x180003eae  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eb5  cmp     rcx, rbx
0x180003eb8  jz      short loc_180003ED7
0x180003eba  test    byte ptr [rcx+1Ch], 2
0x180003ebe  jz      short loc_180003ED7
0x180003ec0  mov     rcx, [rcx+10h]
0x180003ec4  mov     r9, rdi
0x180003ec7  mov     dword ptr [rsp+2E0h+peUse], eax
0x180003ecb  mov     eax, [rdi+10h]
0x180003ece  mov     dword ptr [rsp+2E0h+cchReferencedDomainName], eax
0x180003ed2  call    WPP_SF__guid_dD
0x180003ed7  xor     eax, eax
0x180003ed9  mov     [rsp+2E0h+arg_18], rsi
0x180003ee1  xorps   xmm0, xmm0
0x180003ee4  lea     rbx, xmmword_18001FEE0
0x180003eeb  movups  xmmword ptr [r13+0], xmm0
0x180003ef0  mov     [r13+10h], rax
0x180003ef4  lea     r9, xmmword_18001FAC0
0x180003efb  mov     r10d, [r14+54h]
0x180003eff  mov     eax, 0Ah
0x180003f04  cmp     r10d, 1
0x180003f08  mov     r11d, 0Dh
0x180003f0e  mov     r8d, 1Dh
0x180003f14  cmovnz  r11d, eax
0x180003f18  mov     eax, 9
0x180003f1d  cmovnz  r8d, eax
0x180003f21  lea     rax, xmmword_180020210
0x180003f28  cmovnz  rbx, rax
0x180003f2c  lea     rax, xmmword_1800200C0
0x180003f33  cmovnz  r9, rax
0x180003f37  xor     edx, edx
0x180003f39  cmp     edx, r8d
0x180003f3c  jnb     short loc_180003F69
0x180003f3e  mov     eax, [rdi+10h]
0x180003f41  lea     rcx, [rdx+rdx*8]
0x180003f45  cmp     eax, [r9+rcx*4+10h]
0x180003f4a  lea     rsi, [r9+rcx*4]
0x180003f4e  jnz     short loc_180003F65
0x180003f50  mov     rcx, [rdi]
0x180003f53  sub     rcx, [rsi]
0x180003f56  jnz     short loc_180003F60
0x180003f58  mov     rcx, [rdi+8]
0x180003f5c  sub     rcx, [rsi+8]
0x180003f60  test    rcx, rcx
0x180003f63  jz      short loc_180003F9E
0x180003f65  inc     edx
0x180003f67  jmp     short loc_180003F39
0x180003f69  xor     edx, edx
0x180003f6b  cmp     edx, r11d
0x180003f6e  jnb     loc_180004BAC
0x180003f74  mov     eax, [rdi+10h]
0x180003f77  lea     rcx, [rdx+rdx*8]
0x180003f7b  cmp     eax, [rbx+rcx*4+10h]
0x180003f7f  lea     rsi, [rbx+rcx*4]
0x180003f83  jnz     short loc_180003F9A
0x180003f85  mov     rcx, [rdi]
0x180003f88  sub     rcx, [rsi]
0x180003f8b  jnz     short loc_180003F95
0x180003f8d  mov     rcx, [rdi+8]
0x180003f91  sub     rcx, [rsi+8]
0x180003f95  test    rcx, rcx
0x180003f98  jz      short loc_180003F9E
0x180003f9a  inc     edx
0x180003f9c  jmp     short loc_180003F6B
0x180003f9e  xor     ebx, ebx
0x180003fa0  cmp     eax, [rsi+10h]
0x180003fa3  jnz     loc_180004BB1
0x180003fa9  mov     rcx, [rdi]
0x180003fac  sub     rcx, [rsi]
0x180003faf  jnz     short loc_180003FB9
0x180003fb1  mov     rcx, [rdi+8]
0x180003fb5  sub     rcx, [rsi+8]
0x180003fb9  test    rcx, rcx
0x180003fbc  jnz     loc_180004BB1
0x180003fc2  mov     ecx, [rsi+20h]
0x180003fc5  mov     r8d, 30h ; '0'
0x180003fcb  cmp     r10d, 1
0x180003fcf  jnz     short loc_180003FE4
0x180003fd1  test    ecx, ecx
0x180003fd3  mov     edx, 20h ; ' '
0x180003fd8  mov     r8d, 18h
0x180003fde  cmovz   edx, r8d
0x180003fe2  jmp     short loc_180003FEF
0x180003fe4  test    ecx, ecx
0x180003fe6  mov     edx, 28h ; '('
0x180003feb  cmovnz  rdx, r8
0x180003fef  mov     ecx, [rsi+18h]
0x180003ff2  mov     r12d, 0FFFFFFFFh
0x180003ff8  cmp     ecx, r12d
0x180003ffb  jnz     loc_18000498F
0x180004001  cmp     eax, cs:dword_18001ACA8
0x180004007  jnz     short loc_180004055
0x180004009  mov     rcx, [rdi]
0x18000400c  sub     rcx, qword ptr cs:PKEY_SAM_Type
0x180004013  jnz     short loc_180004020
0x180004015  mov     rcx, [rdi+8]
0x180004019  sub     rcx, qword ptr cs:PKEY_SAM_Type+8
0x180004020  test    rcx, rcx
0x180004023  jnz     short loc_180004055
0x180004025  cmp     r10d, 1
0x180004029  jnz     short loc_18000403B
0x18000402b  mov     word ptr [r13+0], 13h
0x180004032  mov     [r13+8], r10d
0x180004036  jmp     loc_180004BB1
0x18000403b  cmp     r10d, 2
0x18000403f  jnz     loc_180004BAC
0x180004045  mov     word ptr [r13+0], 13h
0x18000404c  mov     [r13+8], r10d
0x180004050  jmp     loc_180004BB1
0x180004055  cmp     eax, cs:dword_18001AB10
0x18000405b  jnz     loc_1800040E3
0x180004061  mov     rcx, [rdi]
0x180004064  sub     rcx, qword ptr cs:PKEY_SAM_LogonHours
0x18000406b  jnz     short loc_180004078
0x18000406d  mov     rcx, [rdi+8]
0x180004071  sub     rcx, qword ptr cs:PKEY_SAM_LogonHours+8
0x180004078  test    rcx, rcx
0x18000407b  jnz     short loc_1800040E3
0x18000407d  mov     rax, [r14+18h]
0x180004081  cmp     [rax+128h], rbx
0x180004088  jz      loc_180004BB1
0x18000408e  movzx   eax, word ptr [rax+120h]
0x180004095  mov     r15d, 1
0x18000409b  shr     eax, 3
0x18000409e  test    eax, eax
0x1800040a0  cmovnz  eax, r15d
0x1800040a4  mov     ecx, eax; cb
0x1800040a6  mov     [r13+8], eax
0x1800040aa  mov     edi, eax
0x1800040ac  call    cs:__imp_CoTaskMemAlloc
0x1800040b2  mov     [r13+10h], rax
0x1800040b6  test    rax, rax
0x1800040b9  jz      loc_18000441C
0x1800040bf  mov     rdx, [r14+18h]
0x1800040c3  mov     r8d, edi; Size
0x1800040c6  mov     rcx, rax; void *
0x1800040c9  mov     rdx, [rdx+128h]; Src
0x1800040d0  call    memcpy_0
0x1800040d5  movzx   eax, word ptr [rsi+14h]
0x1800040d9  mov     [r13+0], ax
0x1800040de  jmp     loc_180004BB1
0x1800040e3  cmp     eax, cs:dword_18001AAB0
0x1800040e9  jnz     short loc_18000411D
0x1800040eb  mov     rcx, [rdi]
0x1800040ee  sub     rcx, qword ptr cs:PKEY_SAM_Groups
0x1800040f5  jnz     short loc_180004102
0x1800040f7  mov     rcx, [rdi+8]
0x1800040fb  sub     rcx, qword ptr cs:PKEY_SAM_Groups+8
0x180004102  test    rcx, rcx
0x180004105  jnz     short loc_18000411D
0x180004107  mov     rdx, r13; struct tagPROPVARIANT *
0x18000410a  lea     rcx, Source; "Need to implement Groups"
0x180004111  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180004116  mov     ebx, eax
0x180004118  jmp     loc_180004BB1
0x18000411d  cmp     eax, cs:dword_18001AC60
0x180004123  jnz     loc_180004382
0x180004129  mov     rcx, [rdi]
0x18000412c  sub     rcx, qword ptr cs:PKEY_SAM_SecurityID
0x180004133  jnz     short loc_180004140
0x180004135  mov     rcx, [rdi+8]
0x180004139  sub     rcx, qword ptr cs:PKEY_SAM_SecurityID+8
0x180004140  test    rcx, rcx
0x180004143  jnz     loc_180004382
0x180004149  mov     rdi, [r14+58h]
0x18000414d  xor     r12d, r12d
0x180004150  mov     r13d, [r14+50h]
0x180004154  xor     r14d, r14d
0x180004157  mov     qword ptr [rsp+2E0h+cchName], rbx
0x18000415c  mov     [rsp+2E0h+pv], rdi
0x180004161  test    rdi, rdi
0x180004164  jnz     short loc_180004186
0x180004166  lea     rcx, [rsp+2E0h+pv]
0x18000416b  call    CSGetAccountDomainSid
0x180004170  mov     rdi, [rsp+2E0h+pv]
0x180004175  mov     ebx, eax
0x180004177  mov     r15d, 1
0x18000417d  test    eax, eax
0x18000417f  jns     short loc_180004189
0x180004181  jmp     loc_180004267
0x180004186  xor     r15d, r15d
0x180004189  xorps   xmm0, xmm0
0x18000418c  mov     qword ptr [rsp+2E0h+ReferencedDomainName], 30h ; '0'
0x180004195  lea     r9, [rsp+2E0h+ReferencedDomainName]
0x18000419a  mov     [rsp+2E0h+var_270], r12
0x18000419f  mov     r8d, 20031h
0x1800041a5  mov     [rsp+2E0h+pv], r12
0x1800041aa  lea     rdx, [rsp+2E0h+pv]
0x1800041af  mov     qword ptr [rsp+2E0h+ReferencedDomainName+8], r12
0x1800041b4  xor     ecx, ecx
0x1800041b6  mov     [rsp+2E0h+var_278], r12
0x1800041bb  movdqu  [rsp+2E0h+var_268], xmm0
0x1800041c1  call    cs:__imp_SamConnect
0x1800041c7  mov     ebx, eax
0x1800041c9  test    eax, eax
0x1800041cb  js      short loc_18000422D
0x1800041cd  mov     rcx, [rsp+2E0h+pv]
0x1800041d2  lea     r9, [rsp+2E0h+FileTime2]
0x1800041d7  mov     r8, rdi
0x1800041da  mov     qword ptr [rsp+2E0h+FileTime2.dwLowDateTime], r12
0x1800041df  mov     edx, 20385h
0x1800041e4  call    cs:__imp_SamOpenDomain
0x1800041ea  mov     ebx, eax
0x1800041ec  test    eax, eax
0x1800041ee  js      short loc_1800041FE
0x1800041f0  mov     r14, qword ptr [rsp+2E0h+FileTime2.dwLowDateTime]
0x1800041f5  xor     ebx, ebx
0x1800041f7  mov     r12, [rsp+2E0h+pv]
0x1800041fc  jmp     short loc_180004262
0x1800041fe  mov     rcx, [rsp+2E0h+pv]
0x180004203  call    cs:__imp_SamCloseHandle
0x180004209  bts     ebx, 1Ch
0x18000420d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004214  lea     rax, WPP_GLOBAL_Control
0x18000421b  cmp     rcx, rax
0x18000421e  jz      short loc_180004262
0x180004220  test    byte ptr [rcx+1Ch], 2
0x180004224  jz      short loc_180004262
0x180004226  mov     edx, 22h ; '"'
0x18000422b  jmp     short loc_18000424F
0x18000422d  bts     ebx, 1Ch
0x180004231  mov     rcx, cs:WPP_GLOBAL_Control
0x180004238  lea     rax, WPP_GLOBAL_Control
0x18000423f  cmp     rcx, rax
0x180004242  jz      short loc_180004262
0x180004244  test    byte ptr [rcx+1Ch], 2
0x180004248  jz      short loc_180004262
0x18000424a  mov     edx, 23h ; '#'
0x18000424f  mov     rcx, [rcx+10h]
0x180004253  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18000425a  mov     r9d, ebx
0x18000425d  call    WPP_SF_d
0x180004262  test    r15d, r15d
0x180004265  jz      short loc_180004270
0x180004267  mov     rcx, rdi; pv
0x18000426a  call    cs:__imp_CoTaskMemFree
0x180004270  test    ebx, ebx
0x180004272  js      loc_180004354
0x180004278  lea     r8, [rsp+2E0h+pSid]
0x18000427d  mov     [rsp+2E0h+pSid], 0
0x180004286  mov     edx, r13d
0x180004289  mov     rcx, r14
0x18000428c  call    cs:__imp_SamRidToSid
0x180004292  test    eax, eax
0x180004294  js      short loc_180004300
0x180004296  mov     rcx, [rsp+2E0h+pSid]; pSid
0x18000429b  call    cs:__imp_GetLengthSid
0x1800042a1  mov     ecx, eax; cb
0x1800042a3  mov     r15d, eax
0x1800042a6  call    cs:__imp_CoTaskMemAlloc
0x1800042ac  mov     rdi, rax
0x1800042af  test    rax, rax
0x1800042b2  jnz     short loc_1800042BB
0x1800042b4  mov     ebx, 8007000Eh
0x1800042b9  jmp     short loc_1800042EE
0x1800042bb  mov     r8, [rsp+2E0h+pSid]; pSourceSid
0x1800042c0  mov     rdx, rdi; pDestinationSid
0x1800042c3  mov     ecx, r15d; nDestinationSidLength
0x1800042c6  call    cs:__imp_CopySid
0x1800042cc  test    eax, eax
0x1800042ce  jnz     short loc_1800042F3
  ... truncated ...
```
