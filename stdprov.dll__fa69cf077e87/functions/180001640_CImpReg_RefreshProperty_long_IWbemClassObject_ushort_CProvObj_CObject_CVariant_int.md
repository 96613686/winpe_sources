# CImpReg::RefreshProperty(long,IWbemClassObject *,ushort *,CProvObj &,CObject *,CVariant *,int)

- ea: `0x180001640`
- end: `0x1800020b5`
- name: `?RefreshProperty@CImpReg@@UEAAJJPEAUIWbemClassObject@@PEAGAEAVCProvObj@@PEAVCObject@@PEAVCVariant@@H@Z`
- size: `2677`
- prototype: `__int64 __fastcall(CImpReg *this, unsigned int, struct IWbemClassObject *, unsigned __int16 *, struct CProvObj *, struct CObject *Dst, struct CVariant *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001640`
- `0x1800020c0`
- `0x180002770`
- `0x180002e10`
- `0x180002e90`
- `0x180003f40`
- `0x1800087c0`
- `0x180008c30`
- `0x1800094b0`
- `0x180011aa8`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180001a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180001a60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001ad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001ad3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800019fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800019fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001821`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001821`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001e7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001ee8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001a46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001e7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001ee8`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180001e45`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180001ec6`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180001e45`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180001ec6`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001c3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002031`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001c3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180002031`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x180001b22`
- `wbemcomn!?Empty@CFlexArray@@QEAAXXZ` at `0x180001b22`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x1800016db`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x1800016db`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800016a3`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000177f`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800017f7`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001854`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001af6`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001b6d`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800016a3`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000177f`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800017f7`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001854`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001af6`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180001b6d`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180001736`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x1800019c3`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x180001736`
- `wbemcomn!?InsertAt@CFlexArray@@QEAAHHPEAX@Z` at `0x1800019c3`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x180001b2d`
- `wbemcomn!??1CFlexArray@@QEAA@XZ` at `0x180001b2d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800018b6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001939`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800019a6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002052`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800018b6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180001939`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800019a6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180002052`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800016fa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000186c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001918`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001980`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001c60`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800016fa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000186c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001918`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001980`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001c60`
- `OLEAUT32!__imp_VariantInit` at `0x180001c09`
- `OLEAUT32!__imp_VariantInit` at `0x180001c09`
- `OLEAUT32!__imp_VariantClear` at `0x180001cb7`
- `OLEAUT32!__imp_VariantClear` at `0x180001cb7`

## pseudocode

```c
__int64 __fastcall CImpReg::RefreshProperty(
        CImpReg *this,
        unsigned int a2,
        struct IWbemClassObject *a3,
        unsigned __int16 *a4,
        struct CProvObj *a5,
        struct CObject *Dst,
        struct CVariant *a7)
{
  const WCHAR *v8; // r14
  CFlexArray *v9; // r12
  void *v10; // rax
  const unsigned __int16 *v11; // rbx
  CToken *v12; // rax
  int *v13; // rdi
  __int64 v14; // rax
  void *v15; // rax
  const unsigned __int16 *v16; // r9
  struct CObject *v17; // rdi
  unsigned int Root; // ebx
  int v19; // r15d
  void *v20; // rax
  const WCHAR *v21; // rdx
  LSTATUS v22; // eax
  HKEY v23; // r14
  void *v24; // rax
  const unsigned __int16 *v25; // rbx
  char *v26; // rax
  _QWORD *v27; // rdi
  char *v28; // rsi
  char *v29; // rcx
  __int64 v30; // rax
  int v31; // esi
  unsigned __int16 *v32; // rax
  char *v33; // rcx
  unsigned __int16 *v34; // rbx
  __int64 v35; // rax
  int v36; // esi
  unsigned __int16 *v37; // rax
  BYTE *v38; // rsi
  HKEY v39; // r15
  BYTE *v40; // rax
  BYTE *v41; // rbx
  int v42; // r12d
  LSTATUS v43; // eax
  unsigned int v44; // edi
  BYTE *v45; // rdi
  LSTATUS v46; // eax
  int i; // ebx
  void (__fastcall ***v48)(void *, __int64); // rax
  void *v50; // rax
  int DataFromDesc; // eax
  CImpReg *v52; // rcx
  signed int v53; // edi
  WCHAR *v54; // rax
  WCHAR *v55; // rbx
  unsigned __int16 *v56; // r15
  struct IWbemClassObject *v57; // r14
  __int64 (__fastcall *v58)(HKEY, const unsigned __int16 *, _QWORD, _QWORD); // rbx
  const unsigned __int16 *Token; // rax
  LSTATUS v60; // eax
  DWORD v61; // ebx
  unsigned __int16 v62; // r8
  struct CVariant *v63; // rbx
  __int16 v64; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  int v68; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v70; // [rsp+58h] [rbp-A8h]
  _WORD v71[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v72; // [rsp+64h] [rbp-9Ch]
  void **v73; // [rsp+68h] [rbp-98h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  HKEY v75; // [rsp+88h] [rbp-78h] BYREF
  void **v76; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v77[22]; // [rsp+98h] [rbp-68h] BYREF
  int v78; // [rsp+F0h] [rbp-10h]
  __int16 v79; // [rsp+F4h] [rbp-Ch]
  char v80; // [rsp+F6h] [rbp-Ah]
  CToken *v81; // [rsp+100h] [rbp+0h]

  v8 = 0;
  v68 = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  v75 = 0;
  v9 = (struct CProvObj *)((char *)a5 + 8);
  if ( *((int *)a5 + 2) > 1 && (v10 = CFlexArray::GetAt((struct CProvObj *)((char *)a5 + 8), 1)) != 0 )
    v11 = (const unsigned __int16 *)*((_QWORD *)v10 + 4);
  else
    v11 = 0;
  v76 = &CProvObj::`vftable';
  CFlexArray::CFlexArray((CFlexArray *)v77, 8, 100);
  v80 = 1;
  v79 = 92;
  while ( 1 )
  {
    if ( !*v11 )
    {
      v78 = 0;
      goto LABEL_13;
    }
    v12 = (CToken *)CWin32DefaultArena::WbemMemAlloc(0x88u);
    v81 = v12;
    v13 = v12 ? (int *)CToken::CToken(v12, v11, 92, v80) : 0LL;
    if ( !v13 )
      break;
    if ( CFlexArray::InsertAt((CFlexArray *)v77, v77[0], v13) )
    {
      (**(void (__fastcall ***)(int *, __int64))v13)(v13, 1);
      break;
    }
    v14 = v13[2];
    if ( (_DWORD)v14 == -1 )
    {
      v78 = -2147217400;
      goto LABEL_13;
    }
    v11 += v14;
  }
  v78 = -2147217402;
LABEL_13:
  if ( v78 || v77[0] < 1 )
  {
    CProvObj::~CProvObj((CProvObj *)&v76);
    return 2147749896LL;
  }
  if ( *(int *)v9 > 0 && (v15 = CFlexArray::GetAt(v9, 0)) != 0 )
    v16 = (const unsigned __int16 *)*((_QWORD *)v15 + 4);
  else
    v16 = 0;
  v17 = Dst;
  Root = CImpReg::GetRoot(this, &hKey, (struct CProvObj *)&v76, v16, Dst, &v68);
  if ( Root )
  {
LABEL_93:
    CProvObj::~CProvObj((CProvObj *)&v76);
    return Root;
  }
  v19 = v68;
  while ( ++v19 < v77[0] )
  {
    if ( !*((_QWORD *)this + 16) || *((_DWORD *)v17 + 24) )
    {
      if ( v19 >= 0 && (v20 = CFlexArray::GetAt((CFlexArray *)v77, v19)) != 0 )
        v21 = (const WCHAR *)*((_QWORD *)v20 + 2);
      else
        v21 = 0;
      v22 = RegOpenKeyExW(hKey, v21, 0, 0x20019u, &v75);
    }
    else
    {
      v58 = (__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 17);
      Token = CProvObj::sGetToken((CProvObj *)&v76, v19);
      LODWORD(phkResult) = 1;
      v22 = v58(hKey, Token, 0, 0);
    }
    Root = v22;
    if ( v22 )
      goto LABEL_93;
    v23 = v75;
    hKey = v75;
    if ( v19 < v77[0] && v19 >= 0 && (v24 = CFlexArray::GetAt((CFlexArray *)v77, v19)) != 0 )
      v25 = (const unsigned __int16 *)*((_QWORD *)v24 + 2);
    else
      v25 = 0;
    v26 = (char *)CWin32DefaultArena::WbemMemAlloc(0x20u);
    v27 = v26;
    v81 = (CToken *)v26;
    if ( v26 )
    {
      *(_QWORD *)v26 = &CObject::`vftable';
      *(_QWORD *)v26 = &CEntry::`vftable';
      v28 = v26 + 16;
      *((_WORD *)v26 + 8) = 0;
      *((_QWORD *)v26 + 1) = v26 + 16;
      *((_DWORD *)v26 + 5) = 0;
      *((_QWORD *)v26 + 3) = 0;
      *((_DWORD *)v26 + 5) = 0;
      v29 = (char *)*((_QWORD *)v26 + 1);
      if ( v29 != v26 + 16 )
        CWin32DefaultArena::WbemMemFree(v29);
      v27[1] = v28;
    }
    else
    {
      v27 = 0;
    }
    if ( !v27 )
      goto LABEL_100;
    v27[3] = v23;
    v71[0] = 0;
    v70 = v71;
    v72 = 0;
    if ( v25 )
    {
      v30 = -1;
      do
        ++v30;
      while ( v25[v30] );
      v31 = v30 + 1;
      v32 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v30 + 1, 2u));
      if ( v32 )
      {
        v70 = v32;
        v72 = v31;
        StringCchCopyW(v32, v31, v25);
      }
    }
    *((_DWORD *)v27 + 5) = 0;
    v33 = (char *)v27[1];
    if ( v33 != (char *)(v27 + 2) )
      CWin32DefaultArena::WbemMemFree(v33);
    v27[1] = v27 + 2;
    v34 = v70;
    if ( v70 )
    {
      v35 = -1;
      do
        ++v35;
      while ( v70[v35] );
      v36 = v35 + 1;
      v37 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((int)v35 + 1, 2u));
      if ( v37 )
      {
        v27[1] = v37;
        *((_DWORD *)v27 + 5) = v36;
        StringCchCopyW(v37, v36, v34);
      }
    }
    v8 = 0;
    v72 = 0;
    if ( v70 != v71 )
      CWin32DefaultArena::WbemMemFree(v70);
    v70 = v71;
    if ( CFlexArray::InsertAt((struct CObject *)((char *)Dst + 8), *((_DWORD *)Dst + 2), v27) )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))*v27)(v27, 1);
LABEL_100:
      CProvObj::~CProvObj((CProvObj *)&v76);
      return 2147749894LL;
    }
    v17 = Dst;
  }
  v38 = 0;
  if ( *(int *)v9 > 2 )
  {
    v50 = CFlexArray::GetAt(v9, 2);
    if ( v50 )
      v8 = (const WCHAR *)*((_QWORD *)v50 + 2);
  }
  v39 = hKey;
  cbData = 20;
  v40 = (BYTE *)CoTaskMemAlloc(0x14u);
  v41 = v40;
  if ( !v40 )
    goto LABEL_110;
  v42 = 0;
  if ( *((_QWORD *)this + 16) && !*((_DWORD *)v17 + 24) )
  {
    phkResult = (PHKEY)v40;
    v43 = (*((__int64 (__fastcall **)(HKEY, const WCHAR *, _QWORD, DWORD *))this + 19))(v39, v8, 0, &Type);
    goto LABEL_57;
  }
  if ( (a2 & 0x20000) == 0 || RegQueryValueExW(v39, v8, 0, &Type, 0, 0) || Type - 1 > 1 && Type != 7 )
  {
    v43 = RegQueryValueExW(v39, v8, 0, &Type, v41, &cbData);
LABEL_57:
    v44 = v43;
    goto LABEL_58;
  }
  v42 = 1;
  v60 = RegLoadMUIStringW(v39, v8, (LPWSTR)v41, cbData, &cbData, 0, 0);
  v44 = v60;
  if ( v60 )
  {
    if ( v60 == 234 )
      goto LABEL_59;
    v43 = RegQueryValueExW(v39, v8, 0, &Type, v41, &cbData);
    v42 = 0;
    goto LABEL_57;
  }
LABEL_58:
  if ( v44 != 234 )
    goto LABEL_64;
LABEL_59:
  v45 = v41;
  v41 = (BYTE *)CoTaskMemRealloc(v41, cbData);
  if ( !v41 )
  {
    CoTaskMemFree(v45);
LABEL_110:
    v44 = -2147217402;
    goto LABEL_77;
  }
  if ( !*((_QWORD *)this + 16) || *((_DWORD *)Dst + 24) )
  {
    if ( v42 )
      v46 = RegLoadMUIStringW(v39, v8, (LPWSTR)v41, cbData, &cbData, 0, 0);
    else
      v46 = RegQueryValueExW(v39, v8, 0, &Type, v41, &cbData);
  }
  else
  {
    phkResult = (PHKEY)v41;
    v46 = (*((__int64 (__fastcall **)(HKEY, const WCHAR *, _QWORD, DWORD *))this + 19))(v39, v8, 0, &Type);
  }
  v44 = v46;
LABEL_64:
  v38 = v41;
  if ( !v44 )
  {
    if ( !cbData )
    {
      v44 = 2;
      goto LABEL_65;
    }
LABEL_77:
    if ( v44 )
      goto LABEL_65;
    v73 = &CVariant::`vftable';
    VariantInit(&pvarg);
    pvarg.llVal = 0;
    if ( Type - 8 <= 1 )
    {
      DataFromDesc = CImpReg::ConvertGetDataFromDesc(
                       v52,
                       (struct CVariant *)&v73,
                       v38,
                       Type,
                       (unsigned int)phkResult,
                       a5);
      goto LABEL_133;
    }
    LODWORD(a5) = 0;
    if ( Type == 2 )
    {
      v53 = ExpandEnvironmentStringsW((LPCWSTR)v38, (LPWSTR)&Dst, 1u) + 2;
      v54 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v53, 2u));
      v55 = v54;
      if ( v54 )
      {
        ExpandEnvironmentStringsW((LPCWSTR)v38, v54, v53);
        v44 = CVariant::SetData((CVariant *)&v73, v55, 8u, v53);
        CWin32DefaultArena::WbemMemFree(v55);
      }
      else
      {
        v44 = -2147217402;
      }
      goto LABEL_82;
    }
    if ( Type == 4 )
    {
      DataFromDesc = CVariant::SetData((CVariant *)&v73, v38, 3u, -1);
LABEL_133:
      v44 = DataFromDesc;
      goto LABEL_82;
    }
    v61 = cbData;
    switch ( Type )
    {
      case 1u:
        DataFromDesc = CVariant::SetData((CVariant *)&v73, v38, 8u, cbData);
        goto LABEL_133;
      case 3u:
        v57 = a3;
        v56 = a4;
        if ( a3 )
        {
          v44 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, _QWORD, struct CProvObj **, _QWORD))a3->lpVtbl->Get)(
                  a3,
                  a4,
                  0,
                  0,
                  &a5,
                  0);
          if ( v44 )
            goto LABEL_83;
          v62 = (unsigned __int16)a5;
        }
        else
        {
          v62 = 8209;
          LODWORD(a5) = 8209;
        }
        if ( (v62 & 0x2000) != 0 )
          v44 = CVariant::SetData((CVariant *)&v73, v38, v62, v61);
        else
          v44 = -2147217407;
        goto LABEL_83;
      case 5u:
        v44 = CVariant::SetData((CVariant *)&v73, v38, 3u, -1);
        pvarg.bVal = v38[3];
        BYTE1(pvarg.decVal.Lo32) = v38[2];
        BYTE2(pvarg.decVal.Lo64) = v38[1];
        BYTE3(pvarg.decVal.Lo64) = *v38;
        break;
      case 7u:
        DataFromDesc = CVariant::SetData((CVariant *)&v73, v38, 0x2008u, cbData);
        goto LABEL_133;
      default:
        v44 = -2147217403;
        break;
    }
LABEL_82:
    v56 = a4;
    v57 = a3;
LABEL_83:
    if ( !v44 )
    {
      if ( v57 )
      {
        LODWORD(phkResult) = 0;
        v44 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, VARIANTARG *, PHKEY))v57->lpVtbl->Put)(
                v57,
                v56,
                a2,
                &pvarg,
                phkResult);
      }
      else
      {
        v63 = a7;
        if ( a7 )
        {
          OMSVariantClear((struct tagVARIANT *)((char *)a7 + 8));
          v44 = OMSVariantChangeType((VARIANTARG *)((char *)v63 + 8), &pvarg, v64, pvarg.vt);
        }
        else
        {
          v44 = -2147217407;
        }
      }
    }
    v73 = &CVariant::`vftable';
    VariantClear(&pvarg);
    pvarg.llVal = 0;
    v73 = &CObject::`vftable';
  }
LABEL_65:
  if ( v38 )
    CoTaskMemFree(v38);
  v76 = &CProvObj::`vftable';
  for ( i = 0; i < v77[0]; ++i )
  {
    v48 = (void (__fastcall ***)(void *, __int64))CFlexArray::GetAt((CFlexArray *)v77, i);
    if ( v48 )
      (**v48)(v48, 1);
  }
  CFlexArray::Empty((CFlexArray *)v77);
  CFlexArray::~CFlexArray((CFlexArray *)v77);
  v76 = &CObject::`vftable';
  return v44;
}

```

## disassembly

```asm
0x180001640  mov     [rsp-8+arg_0], rbx
0x180001645  mov     [rsp-8+arg_18], r9
0x18000164a  mov     [rsp-8+arg_10], r8
0x18000164f  mov     [rsp-8+arg_8], edx
0x180001653  push    rbp
0x180001654  push    rsi
0x180001655  push    rdi
0x180001656  push    r12
0x180001658  push    r13
0x18000165a  push    r14
0x18000165c  push    r15
0x18000165e  lea     rbp, [rsp-10h]
0x180001663  sub     rsp, 110h
0x18000166a  mov     r13, rcx
0x18000166d  xor     r14d, r14d
0x180001670  mov     [rsp+140h+var_F8], r14d
0x180001675  mov     [rsp+140h+Type], r14d
0x18000167a  mov     [rsp+140h+cbData], r14d
0x18000167f  mov     [rsp+140h+hKey], r14
0x180001684  mov     [rbp+40h+var_B8], r14
0x180001688  mov     r12, [rbp+40h+arg_20]
0x18000168c  add     r12, 8
0x180001690  cmp     dword ptr [r12], 1
0x180001695  jle     loc_180001CCE
0x18000169b  mov     edx, 1
0x1800016a0  mov     rcx, r12
0x1800016a3  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800016a9  test    rax, rax
0x1800016ac  jz      loc_180001CCE
0x1800016b2  mov     rbx, [rax+20h]
0x1800016b6  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x1800016bd  mov     [rbp+40h+var_B0], rax
0x1800016c1  lea     rax, ??_7CProvObj@@6B@; const CProvObj::`vftable'
0x1800016c8  mov     [rbp+40h+var_B0], rax
0x1800016cc  mov     edx, 8
0x1800016d1  mov     r8d, 64h ; 'd'
0x1800016d7  lea     rcx, [rbp+40h+var_A8]
0x1800016db  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x1800016e1  nop
0x1800016e2  mov     [rbp+40h+var_4A], 1
0x1800016e6  mov     esi, 5Ch ; '\'
0x1800016eb  mov     [rbp+40h+var_4C], si
0x1800016ef  cmp     word ptr [rbx], 0
0x1800016f3  jz      short loc_180001757
0x1800016f5  mov     ecx, 88h
0x1800016fa  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180001700  mov     [rbp+40h+var_40], rax
0x180001704  test    rax, rax
0x180001707  jz      loc_180001CD6
0x18000170d  mov     r8d, esi; unsigned __int16
0x180001710  movzx   r9d, [rbp+40h+var_4A]; bool
0x180001715  mov     rdx, rbx; unsigned __int16 *
0x180001718  mov     rcx, rax; this
0x18000171b  call    ??0CToken@@QEAA@PEBGG_N@Z; CToken::CToken(ushort const *,ushort,bool)
0x180001720  mov     rdi, rax
0x180001723  test    rdi, rdi
0x180001726  jz      loc_180001CFD
0x18000172c  mov     r8, rdi
0x18000172f  mov     edx, [rbp+40h+var_A8]
0x180001732  lea     rcx, [rbp+40h+var_A8]
0x180001736  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x18000173c  test    eax, eax
0x18000173e  jnz     loc_180001CEA
0x180001744  movsxd  rax, dword ptr [rdi+8]
0x180001748  cmp     eax, 0FFFFFFFFh
0x18000174b  jz      loc_180001CDE
0x180001751  lea     rbx, [rbx+rax*2]
0x180001755  jmp     short loc_1800016EF
0x180001757  mov     [rbp+40h+var_50], r14d
0x18000175b  mov     eax, [rbp+40h+var_50]
0x18000175e  test    eax, eax
0x180001760  jnz     loc_180001B55
0x180001766  cmp     [rbp+40h+var_A8], 1
0x18000176a  jl      loc_180001B55
0x180001770  cmp     [r12], eax
0x180001774  jle     loc_180001D09
0x18000177a  xor     edx, edx
0x18000177c  mov     rcx, r12
0x18000177f  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180001785  test    rax, rax
0x180001788  jz      loc_180001D09
0x18000178e  mov     r9, [rax+20h]; unsigned __int16 *
0x180001792  lea     rax, [rsp+140h+var_F8]
0x180001797  mov     [rsp+140h+lpcbData], rax; int *
0x18000179c  mov     rdi, [rbp+40h+Dst]
0x1800017a0  mov     [rsp+140h+phkResult], rdi; struct CHandleCache *
0x1800017a5  lea     r8, [rbp+40h+var_B0]; struct CProvObj *
0x1800017a9  lea     rdx, [rsp+140h+hKey]; HKEY *
0x1800017ae  mov     rcx, r13; this
0x1800017b1  call    ?GetRoot@CImpReg@@QEAAHPEAPEAUHKEY__@@AEAVCProvObj@@PEBGPEAVCHandleCache@@AEAH@Z; CImpReg::GetRoot(HKEY__ * *,CProvObj &,ushort const *,CHandleCache *,int &)
0x1800017b6  mov     ebx, eax
0x1800017b8  test    eax, eax
0x1800017ba  jnz     loc_180001D11
0x1800017c0  mov     r15d, [rsp+140h+var_F8]
0x1800017c5  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800017cc  inc     r15d
0x1800017cf  cmp     r15d, [rbp+40h+var_A8]
0x1800017d3  jge     loc_1800019DA
0x1800017d9  cmp     qword ptr [r13+80h], 0
0x1800017e1  jnz     loc_180001D21
0x1800017e7  test    r15d, r15d
0x1800017ea  js      loc_180001D6A
0x1800017f0  mov     edx, r15d
0x1800017f3  lea     rcx, [rbp+40h+var_A8]
0x1800017f7  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800017fd  test    rax, rax
0x180001800  jz      loc_180001D6A
0x180001806  mov     rdx, [rax+10h]; lpSubKey
0x18000180a  lea     rax, [rbp+40h+var_B8]
0x18000180e  mov     [rsp+140h+phkResult], rax; phkResult
0x180001813  mov     r9d, 20019h; samDesired
0x180001819  xor     r8d, r8d; ulOptions
0x18000181c  mov     rcx, [rsp+140h+hKey]; hKey
0x180001821  call    cs:__imp_RegOpenKeyExW
0x180001827  mov     ebx, eax
0x180001829  test    eax, eax
0x18000182b  jnz     loc_180001D11
0x180001831  mov     r14, [rbp+40h+var_B8]
0x180001835  mov     [rsp+140h+hKey], r14
0x18000183a  cmp     r15d, [rbp+40h+var_A8]
0x18000183e  jge     loc_180001D72
0x180001844  test    r15d, r15d
0x180001847  js      loc_180001D72
0x18000184d  mov     edx, r15d
0x180001850  lea     rcx, [rbp+40h+var_A8]
0x180001854  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000185a  test    rax, rax
0x18000185d  jz      loc_180001D72
0x180001863  mov     rbx, [rax+10h]
0x180001867  mov     ecx, 20h ; ' '
0x18000186c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180001872  mov     rdi, rax
0x180001875  mov     [rbp+40h+var_40], rax
0x180001879  test    rax, rax
0x18000187c  jz      loc_180001D79
0x180001882  lea     rax, ??_7CObject@@6B@; const CObject::`vftable'
0x180001889  mov     [rdi], rax
0x18000188c  lea     rax, ??_7CEntry@@6B@; const CEntry::`vftable'
0x180001893  mov     [rdi], rax
0x180001896  lea     rsi, [rdi+10h]
0x18000189a  xor     edx, edx
0x18000189c  mov     [rsi], dx
0x18000189f  mov     [rdi+8], rsi
0x1800018a3  mov     [rdi+14h], edx
0x1800018a6  mov     [rdi+18h], rdx
0x1800018aa  mov     [rdi+14h], edx
0x1800018ad  mov     rcx, [rdi+8]
0x1800018b1  cmp     rcx, rsi
0x1800018b4  jz      short loc_1800018BE
0x1800018b6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800018bc  xor     edx, edx
0x1800018be  mov     [rdi+8], rsi
0x1800018c2  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800018c9  test    rdi, rdi
0x1800018cc  jz      loc_180001D96
0x1800018d2  mov     [rdi+18h], r14
0x1800018d6  mov     [rsp+140h+var_E0], dx
0x1800018db  lea     rax, [rsp+140h+var_E0]
0x1800018e0  mov     [rsp+140h+var_E8], rax
0x1800018e5  mov     [rsp+140h+var_DC], edx
0x1800018e9  test    rbx, rbx
0x1800018ec  jz      short loc_180001929
0x1800018ee  mov     rax, rsi
0x1800018f1  lea     rax, [rax+1]
0x1800018f5  cmp     word ptr [rbx+rax*2], 0
0x1800018fa  jnz     short loc_1800018F1
0x1800018fc  lea     esi, [rax+1]
0x1800018ff  movsxd  r14, esi
0x180001902  mov     eax, 2
0x180001907  mul     r14
0x18000190a  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180001911  cmovb   rax, r9
0x180001915  mov     rcx, rax
0x180001918  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000191e  test    rax, rax
0x180001921  jnz     loc_180001B85
0x180001927  xor     edx, edx
0x180001929  mov     [rdi+14h], edx
0x18000192c  lea     rbx, [rdi+10h]
0x180001930  mov     rcx, [rdi+8]
0x180001934  cmp     rcx, rbx
0x180001937  jz      short loc_18000193F
0x180001939  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000193f  mov     [rdi+8], rbx
0x180001943  mov     rbx, [rsp+140h+var_E8]
0x180001948  test    rbx, rbx
0x18000194b  jz      short loc_18000198F
0x18000194d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180001954  mov     rax, rcx
0x180001957  nop     word ptr [rax+rax+00000000h]
0x180001960  lea     rax, [rax+1]
0x180001964  cmp     word ptr [rbx+rax*2], 0
0x180001969  jnz     short loc_180001960
0x18000196b  lea     esi, [rax+1]
0x18000196e  movsxd  r14, esi
0x180001971  mov     eax, 2
0x180001976  mul     r14
0x180001979  cmovb   rax, rcx
0x18000197d  mov     rcx, rax
0x180001980  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180001986  test    rax, rax
0x180001989  jnz     loc_180001BA1
0x18000198f  xor     r14d, r14d
0x180001992  mov     [rsp+140h+var_DC], r14d
0x180001997  lea     rax, [rsp+140h+var_E0]
0x18000199c  mov     rcx, [rsp+140h+var_E8]
0x1800019a1  cmp     rcx, rax
0x1800019a4  jz      short loc_1800019AC
0x1800019a6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800019ac  lea     rax, [rsp+140h+var_E0]
0x1800019b1  mov     [rsp+140h+var_E8], rax
0x1800019b6  mov     rcx, [rbp+40h+Dst]
0x1800019ba  add     rcx, 8
0x1800019be  mov     r8, rdi
0x1800019c1  mov     edx, [rcx]
0x1800019c3  call    cs:__imp_?InsertAt@CFlexArray@@QEAAHHPEAX@Z; CFlexArray::InsertAt(int,void *)
0x1800019c9  test    eax, eax
0x1800019cb  jnz     loc_180001D82
0x1800019d1  mov     rdi, [rbp+40h+Dst]
0x1800019d5  jmp     loc_1800017C5
0x1800019da  mov     rsi, r14
0x1800019dd  cmp     dword ptr [r12], 2
0x1800019e2  jg      loc_180001B65
0x1800019e8  mov     r15, [rsp+140h+hKey]
0x1800019ed  mov     [rsp+140h+cbData], 14h
0x1800019f5  mov     ecx, 14h; cb
0x1800019fa  call    cs:__imp_CoTaskMemAlloc
0x180001a00  mov     rbx, rax
0x180001a03  test    rax, rax
0x180001a06  jz      loc_180001E94
0x180001a0c  xor     r12d, r12d
0x180001a0f  cmp     [r13+80h], r12
0x180001a16  jnz     loc_180001DA9
0x180001a1c  test    [rbp+40h+arg_8], 20000h
0x180001a23  jnz     loc_180001DE1
0x180001a29  lea     rax, [rsp+140h+cbData]
0x180001a2e  mov     [rsp+140h+lpcbData], rax; lpcbData
0x180001a33  mov     [rsp+140h+phkResult], rbx; unsigned int
0x180001a38  lea     r9, [rsp+140h+Type]; lpType
0x180001a3d  xor     r8d, r8d; lpReserved
0x180001a40  mov     rdx, r14; lpValueName
0x180001a43  mov     rcx, r15; hKey
0x180001a46  call    cs:__imp_RegQueryValueExW
0x180001a4c  mov     edi, eax
0x180001a4e  cmp     edi, 0EAh
0x180001a54  jnz     short loc_180001AB9
0x180001a56  mov     rdi, rbx
0x180001a59  mov     edx, [rsp+140h+cbData]; cb
0x180001a5d  mov     rcx, rbx; pv
0x180001a60  call    cs:__imp_CoTaskMemRealloc
0x180001a66  mov     rbx, rax
0x180001a69  test    rax, rax
0x180001a6c  jz      loc_180001E8B
0x180001a72  cmp     qword ptr [r13+80h], 0
0x180001a7a  jz      loc_180001E9E
0x180001a80  mov     rax, [rbp+40h+Dst]
0x180001a84  cmp     dword ptr [rax+60h], 0
0x180001a88  jnz     loc_180001E9E
0x180001a8e  lea     rax, [rsp+140h+cbData]
0x180001a93  mov     [rsp+140h+lpcbData], rax
0x180001a98  mov     [rsp+140h+phkResult], rbx
0x180001a9d  lea     r9, [rsp+140h+Type]
0x180001aa2  xor     r8d, r8d
0x180001aa5  mov     rdx, r14
0x180001aa8  mov     rcx, r15
0x180001aab  mov     rax, [r13+98h]
0x180001ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ab7  mov     edi, eax
0x180001ab9  mov     rsi, rbx
0x180001abc  test    edi, edi
0x180001abe  jz      loc_180001EF3
0x180001ac4  lea     r13, ??_7CObject@@6B@; const CObject::`vftable'
0x180001acb  test    rsi, rsi
0x180001ace  jz      short loc_180001ADA
0x180001ad0  mov     rcx, rsi; pv
0x180001ad3  call    cs:__imp_CoTaskMemFree
0x180001ad9  nop
0x180001ada  lea     rax, ??_7CProvObj@@6B@; const CProvObj::`vftable'
0x180001ae1  mov     [rbp+40h+var_B0], rax
0x180001ae5  xor     ebx, ebx
0x180001ae7  cmp     [rbp+40h+var_A8], ebx
0x180001aea  jle     short loc_180001B1E
0x180001aec  nop     dword ptr [rax+00h]
0x180001af0  mov     edx, ebx
0x180001af2  lea     rcx, [rbp+40h+var_A8]
0x180001af6  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180001afc  mov     r8, rax
0x180001aff  test    rax, rax
0x180001b02  jz      short loc_180001B17
0x180001b04  mov     rcx, [rax]
0x180001b07  mov     rax, [rcx]
0x180001b0a  mov     edx, 1
0x180001b0f  mov     rcx, r8
0x180001b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b17  inc     ebx
0x180001b19  cmp     ebx, [rbp+40h+var_A8]
0x180001b1c  jl      short loc_180001AF0
0x180001b1e  lea     rcx, [rbp+40h+var_A8]
0x180001b22  call    cs:__imp_?Empty@CFlexArray@@QEAAXXZ; CFlexArray::Empty(void)
0x180001b28  nop
  ... truncated ...
```
