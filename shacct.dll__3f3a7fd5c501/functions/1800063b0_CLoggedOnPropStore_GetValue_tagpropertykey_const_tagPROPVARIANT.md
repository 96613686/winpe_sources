# CLoggedOnPropStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x1800063b0`
- end: `0x180006b8e`
- name: `?GetValue@CLoggedOnPropStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `2014`
- prototype: `__int64 __fastcall(struct IPropertyStore *this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180004bf0`
- `0x1800063b0`
- `0x180008230`
- `0x180008890`
- `0x18000b410`
- `0x18000b960`
- `0x18000cb6c`
- `0x180010a3c`
- `0x180011ca4`
- `0x180014030`
- `0x1800140ec`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000678d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000678d`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180006b6f`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180006b6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006692`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000682a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000682a`

## pseudocode

```c
__int64 __fastcall CLoggedOnPropStore::GetValue(
        struct IPropertyStore *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  int inited; // ebp
  unsigned int i; // r9d
  __int64 v8; // rax
  unsigned int j; // edx
  __int64 v10; // rax
  DWORD pid; // r8d
  __int64 v12; // rax
  __int64 v13; // rax
  HRESULT (__stdcall **p_SetValue)(IPropertyStore *, const PROPERTYKEY *const, const PROPVARIANT *const); // rcx
  __int64 v15; // rax
  LONG QueryInterface; // ecx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  LONG lpVtbl; // eax
  __int64 v26; // rax
  struct IPropertyStoreVtbl *v27; // rcx
  BYTE *v28; // rbx
  void *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  struct IPropertyStoreVtbl *v32; // rbx
  __int64 v33; // rax
  __int64 v35; // rsi
  void *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int16 *v48; // rbx
  __int64 v49; // rdx
  __int16 *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rcx
  bool v53; // al
  int v54; // r8d
  _QWORD *v55; // r10
  __int64 v56; // rax
  struct IPropertyStoreVtbl *v57; // rcx
  __int64 v58; // rax
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  inited = -2147024809;
  if ( !a3 )
    return (unsigned int)inited;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xA )
    {
      for ( j = 0; j < 0x12; ++j )
      {
        if ( a2->pid == dword_18001F780[9 * j] )
        {
          v10 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)((char *)&xmmword_18001F770 + 36 * (int)j);
          if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)((char *)&xmmword_18001F770 + 36 * (int)j) )
            v10 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)((char *)&xmmword_18001F770 + 36 * (int)j + 8);
          if ( !v10 )
            goto LABEL_16;
        }
      }
      return (unsigned int)inited;
    }
    if ( a2->pid == dword_18001F610[9 * i] )
    {
      v8 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)((char *)&xmmword_18001F600 + 36 * (int)i);
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)((char *)&xmmword_18001F600 + 36 * (int)i) )
        v8 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)((char *)&xmmword_18001F600 + 36 * (int)i + 8);
      if ( !v8 )
        break;
    }
  }
LABEL_16:
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  pid = a2->pid;
  if ( pid == 200 )
  {
    v12 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_LUID;
    if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_LUID )
      v12 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_LUID + 1);
    if ( !v12 )
    {
      inited = CLoggedOnPropStore::_InitLogonSessionData((CLoggedOnPropStore *)this);
      if ( inited >= 0 )
      {
        inited = 0;
        a3->hVal.QuadPart = *(LONGLONG *)((char *)&this[4].lpVtbl->QueryInterface + 4);
        a3->vt = 21;
      }
      return (unsigned int)inited;
    }
  }
  if ( pid == 201 )
  {
    v13 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_AuthenticationPackage;
    if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_AuthenticationPackage )
      v13 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_AuthenticationPackage + 1);
    if ( !v13 )
    {
      inited = CLoggedOnPropStore::_InitLogonSessionData((CLoggedOnPropStore *)this);
      if ( inited < 0 )
        return (unsigned int)inited;
      p_SetValue = &this[4].lpVtbl->SetValue;
      goto LABEL_57;
    }
  }
  if ( pid == 202 )
  {
    v15 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_TSSession;
    if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_TSSession )
      v15 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_TSSession + 1);
    if ( !v15 )
    {
      QueryInterface = (LONG)this[3].lpVtbl->QueryInterface;
      a3->vt = 19;
      a3->lVal = QueryInterface;
      return 0;
    }
  }
  if ( pid == 203 )
  {
    v17 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_LogonTime;
    if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_LogonTime )
      v17 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_LogonTime + 1);
    if ( !v17 )
    {
      inited = CLoggedOnPropStore::_InitLogonSessionData((CLoggedOnPropStore *)this);
      if ( inited < 0 )
        return (unsigned int)inited;
      a3->hVal.QuadPart = (LONGLONG)this[4].lpVtbl[1].Release;
      a3->vt = 21;
      return 0;
    }
  }
  if ( pid == 204 )
  {
    v18 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_LogonServer;
    if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_LogonServer )
      v18 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_LogonServer + 1);
    if ( !v18 )
    {
      inited = CLoggedOnPropStore::_InitLogonSessionData((CLoggedOnPropStore *)this);
      if ( inited < 0 )
        return (unsigned int)inited;
      p_SetValue = (HRESULT (__stdcall **)(IPropertyStore *, const PROPERTYKEY *const, const PROPVARIANT *const))&this[4].lpVtbl[1].GetCount;
      goto LABEL_57;
    }
  }
  if ( pid == 205 )
  {
    v19 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_DnsDomainName;
    if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_DnsDomainName )
      v19 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_DnsDomainName + 1);
    if ( !v19 )
    {
      inited = CLoggedOnPropStore::_InitLogonSessionData((CLoggedOnPropStore *)this);
      if ( inited < 0 )
        return (unsigned int)inited;
      p_SetValue = (HRESULT (__stdcall **)(IPropertyStore *, const PROPERTYKEY *const, const PROPVARIANT *const))&this[4].lpVtbl[1].GetValue;
      goto LABEL_57;
    }
  }
  if ( pid != 206 )
    goto LABEL_62;
  v20 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_UPN;
  if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_UPN )
    v20 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_UPN + 1);
  if ( v20 )
  {
LABEL_62:
    if ( pid == 207 )
    {
      v21 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_ClientName;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_ClientName )
        v21 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_ClientName + 1);
      if ( !v21 )
        return (unsigned int)InitPropVariantFromString((const unsigned __int16 *)this[5].lpVtbl, a3);
    }
    if ( pid == 208 )
    {
      v23 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_WinStationName;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_WinStationName )
        v23 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_WinStationName + 1);
      if ( !v23 )
        return (unsigned int)InitPropVariantFromString((const unsigned __int16 *)this[6].lpVtbl, a3);
    }
    if ( pid == 209 )
    {
      v24 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_LOGON_Status;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_LOGON_Status )
        v24 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_LOGON_Status + 1);
      if ( !v24 )
      {
        lpVtbl = (LONG)this[7].lpVtbl;
        a3->vt = 19;
        a3->lVal = lpVtbl;
        return 0;
      }
    }
    if ( pid == 18 )
    {
      v26 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_SecurityID;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_SecurityID )
        v26 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_SecurityID + 1);
      if ( !v26 )
      {
        v27 = this[9].lpVtbl;
        pv = 0;
        inited = DupSID(v27, &pv);
        if ( inited >= 0 )
        {
          v28 = (BYTE *)pv;
          v29 = pv;
          a3->vt = 65;
          a3->lVal = GetLengthSid(v29);
          a3->bstrblobVal.pData = v28;
        }
        return (unsigned int)inited;
      }
    }
    if ( pid == 103 )
    {
      v30 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_ResidualID;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_ResidualID )
        v30 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_ResidualID + 1);
      if ( !v30 )
      {
        a3->lVal = RIDFromSID(this[9].lpVtbl);
        a3->vt = 19;
        return 0;
      }
    }
    if ( pid == 2 )
    {
      v31 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_Name;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_Name )
        v31 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_Name + 1);
      if ( !v31 )
      {
        v32 = this[10].lpVtbl;
        if ( v32 )
        {
          v33 = -1;
          while ( *((_WORD *)&v32->QueryInterface + ++v33) != 0 )
            ;
          v35 = 2 * v33 + 2;
          v36 = CoTaskMemAlloc(v35);
          a3->hVal.QuadPart = (LONGLONG)v36;
          if ( v36 )
          {
            inited = 0;
            memcpy_s(v36, v35, v32, v35);
            a3->vt = 31;
            return (unsigned int)inited;
          }
          inited = -2147024882;
        }
        *(_OWORD *)&a3->vt = 0;
        a3->bstrblobVal.pData = 0;
        return (unsigned int)inited;
      }
    }
    if ( pid == 26 )
    {
      v37 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_Domain;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_Domain )
        v37 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_Domain + 1);
      if ( !v37 )
        return (unsigned int)InitPropVariantFromString((const unsigned __int16 *)this[11].lpVtbl, a3);
    }
    if ( pid == 36 )
    {
      v38 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_InteractiveLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_InteractiveLogin )
        v38 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_InteractiveLogin + 1);
      if ( !v38 )
        goto LABEL_141;
    }
    if ( pid == 37 )
    {
      v39 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_NetworkLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_NetworkLogin )
        v39 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_NetworkLogin + 1);
      if ( !v39 )
        goto LABEL_141;
    }
    if ( pid == 38 )
    {
      v40 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_BatchLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_BatchLogin )
        v40 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_BatchLogin + 1);
      if ( !v40 )
        goto LABEL_141;
    }
    if ( pid == 39 )
    {
      v41 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_ServiceLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_ServiceLogin )
        v41 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_ServiceLogin + 1);
      if ( !v41 )
        goto LABEL_141;
    }
    if ( pid == 40 )
    {
      v42 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_RemoteInteractiveLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_RemoteInteractiveLogin )
        v42 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_RemoteInteractiveLogin + 1);
      if ( !v42 )
        goto LABEL_141;
    }
    if ( pid == 41 )
    {
      v43 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyInteractiveLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyInteractiveLogin )
        v43 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyInteractiveLogin + 1);
      if ( !v43 )
        goto LABEL_141;
    }
    if ( pid == 42 )
    {
      v44 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyNetworkLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyNetworkLogin )
        v44 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyNetworkLogin + 1);
      if ( !v44 )
        goto LABEL_141;
    }
    if ( pid == 43 )
    {
      v45 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyBatchLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyBatchLogin )
        v45 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyBatchLogin + 1);
      if ( !v45 )
        goto LABEL_141;
    }
    if ( pid == 44 )
    {
      v46 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyServiceLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyServiceLogin )
        v46 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyServiceLogin + 1);
      if ( !v46 )
        goto LABEL_141;
    }
    if ( pid == 45 )
    {
      v47 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DenyRemoteInteractiveLogin;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DenyRemoteInteractiveLogin )
        v47 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DenyRemoteInteractiveLogin + 1);
      if ( !v47 )
      {
LABEL_141:
        v48 = 0;
        v49 = 0;
        do
        {
          if ( v48 )
            break;
          if ( pid == dword_18001F780[9 * v49] )
          {
            v50 = &_ImageBase[18 * v49 + 64440];
            v51 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v50;
            if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v50 )
              v51 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)&word_180000008[18 * v49 + 64440];
            if ( !v51 )
              v48 = &_ImageBase[18 * v49 + 64440];
          }
          v49 = (unsigned int)(v49 + 1);
        }
        while ( (unsigned int)v49 < 0x12 );
        inited = 0;
        if ( HIDWORD(this[15].lpVtbl) || (inited = CSGetAccountRights(this[9].lpVtbl, &this[15]), inited < 0) )
        {
          if ( inited < 0 )
            return (unsigned int)inited;
        }
        else
        {
          HIDWORD(this[15].lpVtbl) = 1;
        }
        a3->vt = v48[10];
        a3->iVal = -(((__int64)this[15].lpVtbl & *((_DWORD *)v48 + 7)) != 0);
        return (unsigned int)inited;
      }
    }
    if ( (unsigned int)operator==(a2, &PKEY_SAM_AllowedLogon) )
    {
      v53 = IsUserAllowedLogon(this);
    }
    else
    {
      if ( !(unsigned int)operator==(v52, &PKEY_SAM_DontEnumerateForLogon) )
      {
        if ( v54 != PKEY_Identity_DisplayName.pid )
          goto LABEL_176;
        v56 = *v55 - *(_QWORD *)&PKEY_Identity_DisplayName.fmtid.Data1;
        if ( *v55 == *(_QWORD *)&PKEY_Identity_DisplayName.fmtid.Data1 )
          v56 = v55[1] - *(_QWORD *)PKEY_Identity_DisplayName.fmtid.Data4;
        if ( v56 )
        {
LABEL_176:
          if ( v54 != PKEY_Identity_ProviderID.pid )
            return (unsigned int)inited;
          v58 = *v55 - *(_QWORD *)&PKEY_Identity_ProviderID.fmtid.Data1;
          if ( *v55 == *(_QWORD *)&PKEY_Identity_ProviderID.fmtid.Data1 )
            v58 = v55[1] - *(_QWORD *)PKEY_Identity_ProviderID.fmtid.Data4;
          if ( v58 || !this[12].lpVtbl )
            return (unsigned int)inited;
          return (unsigned int)InitPropVariantFromCLSID((const IID *const)&this[13], (PROPVARIANT *)a3);
        }
        else
        {
          v57 = this[12].lpVtbl;
          if ( !v57 )
            return (unsigned int)inited;
          return (unsigned int)InitPropVariantFromString((const unsigned __int16 *)v57, a3);
        }
      }
      v53 = DontEnumerateForLogon(this);
    }
    a3->vt = 11;
    a3->iVal = !v53 - 1;
    return 0;
  }
  inited = CLoggedOnPropStore::_InitLogonSessionData((CLoggedOnPropStore *)this);
  if ( inited < 0 )
    return (unsigned int)inited;
  p_SetValue = (HRESULT (__stdcall **)(IPropertyStore *, const PROPERTYKEY *const, const PROPVARIANT *const))&this[4].lpVtbl[1].Commit;
LABEL_57:
  pv = 0;
  inited = _CreatePWSTRFromUSTRAlloc((const struct _UNICODE_STRING *)p_SetValue, (unsigned __int16 **)&pv);
  if ( inited >= 0 )
  {
    inited = InitPropVariantFromString((const unsigned __int16 *)pv, a3);
    CoTaskMemFree(pv);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800063b0  mov     [rsp+arg_8], rbp
0x1800063b5  mov     [rsp+arg_18], rsi
0x1800063ba  push    rdi
0x1800063bb  sub     rsp, 20h
0x1800063bf  mov     rdi, r8
0x1800063c2  mov     r10, rdx
0x1800063c5  mov     rsi, rcx
0x1800063c8  mov     ebp, 80070057h
0x1800063cd  test    r8, r8
0x1800063d0  jz      loc_180006B7C
0x1800063d6  xor     r9d, r9d
0x1800063d9  lea     r11, __ImageBase
0x1800063e0  cmp     r9d, 0Ah
0x1800063e4  jnb     short loc_18000641D
0x1800063e6  movsxd  rax, r9d
0x1800063e9  lea     rcx, [rax+rax*8]
0x1800063ed  mov     eax, rva dword_18001F610[r11+rcx*4]
0x1800063f5  cmp     [rdx+10h], eax
0x1800063f8  jnz     short loc_180006418
0x1800063fa  mov     rax, [rdx]
0x1800063fd  sub     rax, qword ptr rva xmmword_18001F600[r11+rcx*4]
0x180006405  jnz     short loc_180006413
0x180006407  mov     rax, [rdx+8]
0x18000640b  sub     rax, qword ptr (rva xmmword_18001F600+8)[r11+rcx*4]
0x180006413  test    rax, rax
0x180006416  jz      short loc_180006460
0x180006418  inc     r9d
0x18000641b  jmp     short loc_1800063E0
0x18000641d  xor     edx, edx
0x18000641f  nop
0x180006420  cmp     edx, 12h
0x180006423  jnb     loc_180006B7C
0x180006429  movsxd  rax, edx
0x18000642c  lea     rcx, [rax+rax*8]
0x180006430  mov     eax, rva dword_18001F780[r11+rcx*4]
0x180006438  cmp     [r10+10h], eax
0x18000643c  jnz     short loc_18000645C
0x18000643e  mov     rax, [r10]
0x180006441  sub     rax, qword ptr rva xmmword_18001F770[r11+rcx*4]
0x180006449  jnz     short loc_180006457
0x18000644b  mov     rax, [r10+8]
0x18000644f  sub     rax, qword ptr (rva xmmword_18001F770+8)[r11+rcx*4]
0x180006457  test    rax, rax
0x18000645a  jz      short loc_180006460
0x18000645c  inc     edx
0x18000645e  jmp     short loc_180006420
0x180006460  xor     eax, eax
0x180006462  xorps   xmm0, xmm0
0x180006465  movups  xmmword ptr [r8], xmm0
0x180006469  mov     [r8+10h], rax
0x18000646d  mov     r8d, [r10+10h]
0x180006471  cmp     r8d, cs:dword_18001A858
0x180006478  jnz     short loc_1800064CF
0x18000647a  mov     rax, [r10]
0x18000647d  sub     rax, qword ptr cs:PKEY_LOGON_LUID
0x180006484  jnz     short loc_180006491
0x180006486  mov     rax, [r10+8]
0x18000648a  sub     rax, qword ptr cs:PKEY_LOGON_LUID+8
0x180006491  test    rax, rax
0x180006494  jnz     short loc_1800064CF
0x180006496  mov     rcx, rsi; this
0x180006499  call    ?_InitLogonSessionData@CLoggedOnPropStore@@AEAAJXZ; CLoggedOnPropStore::_InitLogonSessionData(void)
0x18000649e  mov     ebp, eax
0x1800064a0  test    eax, eax
0x1800064a2  js      loc_180006B7C
0x1800064a8  mov     rcx, [rsi+20h]
0x1800064ac  xor     ebp, ebp
0x1800064ae  mov     eax, [rcx+4]
0x1800064b1  mov     dword ptr [rsp+28h+pv], eax
0x1800064b5  mov     eax, [rcx+8]
0x1800064b8  mov     dword ptr [rsp+28h+pv+4], eax
0x1800064bc  mov     rax, [rsp+28h+pv]
0x1800064c1  mov     [rdi+8], rax
0x1800064c5  mov     word ptr [rdi], 15h
0x1800064ca  jmp     loc_180006B7C
0x1800064cf  cmp     r8d, cs:dword_18001A7E0
0x1800064d6  mov     [rsp+28h+arg_0], rbx
0x1800064db  jnz     short loc_180006518
0x1800064dd  mov     rax, [r10]
0x1800064e0  sub     rax, qword ptr cs:PKEY_LOGON_AuthenticationPackage
0x1800064e7  jnz     short loc_1800064F4
0x1800064e9  mov     rax, [r10+8]
0x1800064ed  sub     rax, qword ptr cs:PKEY_LOGON_AuthenticationPackage+8
0x1800064f4  test    rax, rax
0x1800064f7  jnz     short loc_180006518
0x1800064f9  mov     rcx, rsi; this
0x1800064fc  call    ?_InitLogonSessionData@CLoggedOnPropStore@@AEAAJXZ; CLoggedOnPropStore::_InitLogonSessionData(void)
0x180006501  mov     ebp, eax
0x180006503  test    eax, eax
0x180006505  js      loc_180006B77
0x18000650b  mov     rcx, [rsi+20h]
0x18000650f  add     rcx, 30h ; '0'
0x180006513  jmp     loc_180006661
0x180006518  cmp     r8d, cs:dword_18001A888
0x18000651f  jnz     short loc_180006550
0x180006521  mov     rax, [r10]
0x180006524  sub     rax, qword ptr cs:PKEY_LOGON_TSSession
0x18000652b  jnz     short loc_180006538
0x18000652d  mov     rax, [r10+8]
0x180006531  sub     rax, qword ptr cs:PKEY_LOGON_TSSession+8
0x180006538  test    rax, rax
0x18000653b  jnz     short loc_180006550
0x18000653d  mov     rax, [rsi+18h]
0x180006541  mov     ecx, [rax]
0x180006543  mov     word ptr [rdi], 13h
0x180006548  mov     [rdi+8], ecx
0x18000654b  jmp     loc_180006B01
0x180006550  cmp     r8d, cs:dword_18001A840
0x180006557  jnz     short loc_18000659D
0x180006559  mov     rax, [r10]
0x18000655c  sub     rax, qword ptr cs:PKEY_LOGON_LogonTime
0x180006563  jnz     short loc_180006570
0x180006565  mov     rax, [r10+8]
0x180006569  sub     rax, qword ptr cs:PKEY_LOGON_LogonTime+8
0x180006570  test    rax, rax
0x180006573  jnz     short loc_18000659D
0x180006575  mov     rcx, rsi; this
0x180006578  call    ?_InitLogonSessionData@CLoggedOnPropStore@@AEAAJXZ; CLoggedOnPropStore::_InitLogonSessionData(void)
0x18000657d  mov     ebp, eax
0x18000657f  test    eax, eax
0x180006581  js      loc_180006B77
0x180006587  mov     rax, [rsi+20h]
0x18000658b  mov     rcx, [rax+50h]
0x18000658f  mov     [rdi+8], rcx
0x180006593  mov     word ptr [rdi], 15h
0x180006598  jmp     loc_180006B01
0x18000659d  cmp     r8d, cs:dword_18001A828
0x1800065a4  jnz     short loc_1800065E1
0x1800065a6  mov     rax, [r10]
0x1800065a9  sub     rax, qword ptr cs:PKEY_LOGON_LogonServer
0x1800065b0  jnz     short loc_1800065BD
0x1800065b2  mov     rax, [r10+8]
0x1800065b6  sub     rax, qword ptr cs:PKEY_LOGON_LogonServer+8
0x1800065bd  test    rax, rax
0x1800065c0  jnz     short loc_1800065E1
0x1800065c2  mov     rcx, rsi; this
0x1800065c5  call    ?_InitLogonSessionData@CLoggedOnPropStore@@AEAAJXZ; CLoggedOnPropStore::_InitLogonSessionData(void)
0x1800065ca  mov     ebp, eax
0x1800065cc  test    eax, eax
0x1800065ce  js      loc_180006B77
0x1800065d4  mov     rcx, [rsi+20h]
0x1800065d8  add     rcx, 58h ; 'X'
0x1800065dc  jmp     loc_180006661
0x1800065e1  cmp     r8d, cs:dword_18001A810
0x1800065e8  jnz     short loc_180006622
0x1800065ea  mov     rax, [r10]
0x1800065ed  sub     rax, qword ptr cs:PKEY_LOGON_DnsDomainName
0x1800065f4  jnz     short loc_180006601
0x1800065f6  mov     rax, [r10+8]
0x1800065fa  sub     rax, qword ptr cs:PKEY_LOGON_DnsDomainName+8
0x180006601  test    rax, rax
0x180006604  jnz     short loc_180006622
0x180006606  mov     rcx, rsi; this
0x180006609  call    ?_InitLogonSessionData@CLoggedOnPropStore@@AEAAJXZ; CLoggedOnPropStore::_InitLogonSessionData(void)
0x18000660e  mov     ebp, eax
0x180006610  test    eax, eax
0x180006612  js      loc_180006B77
0x180006618  mov     rcx, [rsi+20h]
0x18000661c  add     rcx, 68h ; 'h'
0x180006620  jmp     short loc_180006661
0x180006622  cmp     r8d, cs:dword_18001A8A0
0x180006629  jnz     short loc_18000669D
0x18000662b  mov     rax, [r10]
0x18000662e  sub     rax, qword ptr cs:PKEY_LOGON_UPN
0x180006635  jnz     short loc_180006642
0x180006637  mov     rax, [r10+8]
0x18000663b  sub     rax, qword ptr cs:PKEY_LOGON_UPN+8
0x180006642  test    rax, rax
0x180006645  jnz     short loc_18000669D
0x180006647  mov     rcx, rsi; this
0x18000664a  call    ?_InitLogonSessionData@CLoggedOnPropStore@@AEAAJXZ; CLoggedOnPropStore::_InitLogonSessionData(void)
0x18000664f  mov     ebp, eax
0x180006651  test    eax, eax
0x180006653  js      loc_180006B77
0x180006659  mov     rcx, [rsi+20h]
0x18000665d  add     rcx, 78h ; 'x'; struct _UNICODE_STRING *
0x180006661  lea     rdx, [rsp+28h+pv]; unsigned __int16 **
0x180006666  mov     [rsp+28h+pv], 0
0x18000666f  call    ?_CreatePWSTRFromUSTRAlloc@@YAJPEBU_UNICODE_STRING@@PEAPEAG@Z; _CreatePWSTRFromUSTRAlloc(_UNICODE_STRING const *,ushort * *)
0x180006674  mov     ebp, eax
0x180006676  test    eax, eax
0x180006678  js      loc_180006B77
0x18000667e  mov     rcx, [rsp+28h+pv]; Source
0x180006683  mov     rdx, rdi; struct tagPROPVARIANT *
0x180006686  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18000668b  mov     rcx, [rsp+28h+pv]; pv
0x180006690  mov     ebp, eax
0x180006692  call    cs:__imp_CoTaskMemFree
0x180006698  jmp     loc_180006B77
0x18000669d  cmp     r8d, cs:dword_18001A7F8
0x1800066a4  jnz     short loc_1800066D3
0x1800066a6  mov     rax, [r10]
0x1800066a9  sub     rax, qword ptr cs:PKEY_LOGON_ClientName
0x1800066b0  jnz     short loc_1800066BD
0x1800066b2  mov     rax, [r10+8]
0x1800066b6  sub     rax, qword ptr cs:PKEY_LOGON_ClientName+8
0x1800066bd  test    rax, rax
0x1800066c0  jnz     short loc_1800066D3
0x1800066c2  mov     rcx, [rsi+28h]; Source
0x1800066c6  mov     rdx, rdi; struct tagPROPVARIANT *
0x1800066c9  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x1800066ce  jmp     loc_180006B75
0x1800066d3  cmp     r8d, cs:dword_18001A8B8
0x1800066da  jnz     short loc_180006709
0x1800066dc  mov     rax, [r10]
0x1800066df  sub     rax, qword ptr cs:PKEY_LOGON_WinStationName
0x1800066e6  jnz     short loc_1800066F3
0x1800066e8  mov     rax, [r10+8]
0x1800066ec  sub     rax, qword ptr cs:PKEY_LOGON_WinStationName+8
0x1800066f3  test    rax, rax
0x1800066f6  jnz     short loc_180006709
0x1800066f8  mov     rcx, [rsi+30h]; Source
0x1800066fc  mov     rdx, rdi; struct tagPROPVARIANT *
0x1800066ff  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180006704  jmp     loc_180006B75
0x180006709  cmp     r8d, cs:dword_18001A870
0x180006710  jnz     short loc_18000673E
0x180006712  mov     rax, [r10]
0x180006715  sub     rax, qword ptr cs:PKEY_LOGON_Status
0x18000671c  jnz     short loc_180006729
0x18000671e  mov     rax, [r10+8]
0x180006722  sub     rax, qword ptr cs:PKEY_LOGON_Status+8
0x180006729  test    rax, rax
0x18000672c  jnz     short loc_18000673E
0x18000672e  mov     eax, [rsi+38h]
0x180006731  mov     word ptr [rdi], 13h
0x180006736  mov     [rdi+8], eax
0x180006739  jmp     loc_180006B01
0x18000673e  cmp     r8d, cs:dword_18001AC60
0x180006745  jnz     short loc_18000679F
0x180006747  mov     rax, [r10]
0x18000674a  sub     rax, qword ptr cs:PKEY_SAM_SecurityID
0x180006751  jnz     short loc_18000675E
0x180006753  mov     rax, [r10+8]
0x180006757  sub     rax, qword ptr cs:PKEY_SAM_SecurityID+8
0x18000675e  test    rax, rax
0x180006761  jnz     short loc_18000679F
0x180006763  mov     rcx, [rsi+48h]; pSourceSid
0x180006767  lea     rdx, [rsp+28h+pv]; void **
0x18000676c  mov     [rsp+28h+pv], rax
0x180006771  call    ?DupSID@@YAJPEAXPEAPEAX@Z; DupSID(void *,void * *)
0x180006776  mov     ebp, eax
0x180006778  test    eax, eax
0x18000677a  js      loc_180006B77
0x180006780  mov     rbx, [rsp+28h+pv]
0x180006785  mov     rcx, rbx; pSid
0x180006788  mov     word ptr [rdi], 41h ; 'A'
0x18000678d  call    cs:__imp_GetLengthSid
0x180006793  mov     [rdi+8], eax
0x180006796  mov     [rdi+10h], rbx
0x18000679a  jmp     loc_180006B77
0x18000679f  cmp     r8d, cs:dword_18001AC30
0x1800067a6  jnz     short loc_1800067DA
0x1800067a8  mov     rax, [r10]
0x1800067ab  sub     rax, qword ptr cs:PKEY_SAM_ResidualID
0x1800067b2  jnz     short loc_1800067BF
0x1800067b4  mov     rax, [r10+8]
0x1800067b8  sub     rax, qword ptr cs:PKEY_SAM_ResidualID+8
0x1800067bf  test    rax, rax
0x1800067c2  jnz     short loc_1800067DA
0x1800067c4  mov     rcx, [rsi+48h]; pSid
0x1800067c8  call    ?RIDFromSID@@YAKQEAX@Z; RIDFromSID(void * const)
0x1800067cd  mov     [rdi+8], eax
0x1800067d0  mov     word ptr [rdi], 13h
0x1800067d5  jmp     loc_180006B01
0x1800067da  cmp     r8d, cs:dword_18001AB28
0x1800067e1  jnz     loc_18000686C
0x1800067e7  mov     rax, [r10]
0x1800067ea  sub     rax, qword ptr cs:PKEY_SAM_Name
0x1800067f1  jnz     short loc_1800067FE
0x1800067f3  mov     rax, [r10+8]
0x1800067f7  sub     rax, qword ptr cs:PKEY_SAM_Name+8
0x1800067fe  test    rax, rax
0x180006801  jnz     short loc_18000686C
0x180006803  mov     rbx, [rsi+50h]
0x180006807  test    rbx, rbx
0x18000680a  jz      short loc_18000685B
0x18000680c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006813  cmp     word ptr [rbx+rax*2+2], 0
0x180006819  lea     rax, [rax+1]
0x18000681d  jnz     short loc_180006813
0x18000681f  lea     rsi, ds:2[rax*2]
0x180006827  mov     rcx, rsi; cb
0x18000682a  call    cs:__imp_CoTaskMemAlloc
0x180006830  mov     [rdi+8], rax
0x180006834  test    rax, rax
0x180006837  jz      short loc_180006856
0x180006839  xor     ebp, ebp
0x18000683b  mov     r9, rsi; SourceSize
0x18000683e  mov     r8, rbx; Source
0x180006841  mov     rdx, rsi; DestinationSize
0x180006844  mov     rcx, rax; Destination
0x180006847  call    memcpy_s
0x18000684c  mov     word ptr [rdi], 1Fh
0x180006851  jmp     loc_180006B77
0x180006856  mov     ebp, 8007000Eh
0x18000685b  xorps   xmm0, xmm0
0x18000685e  xor     eax, eax
0x180006860  movups  xmmword ptr [rdi], xmm0
0x180006863  mov     [rdi+10h], rax
  ... truncated ...
```
