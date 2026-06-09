# TransformSDPermissions(void *,_GENERIC_MAPPING *,ulong const * const,void *,bool,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)

- ea: `0x14003029c`
- end: `0x140030d0d`
- name: `?TransformSDPermissions@@YAKPEAXPEAU_GENERIC_MAPPING@@QEBK0_NAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z`
- size: `2673`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400151ec`

## callees

- `0x140002bd0`
- `0x140015878`
- `0x140015898`
- `0x140021b00`
- `0x140022cec`
- `0x14002f6c8`
- `0x1400301e0`
- `0x14003029c`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003036d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400303ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003049f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003052d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400305c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400306cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400307dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003086b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003036d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400303ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003049f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003052d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400305c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400306cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400307dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003086b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030c61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140030c31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140030c31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030c44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030c44`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140030363`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400303f5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140030363`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1400303f5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140030a93`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140030a93`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140030495`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140030523`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140030495`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140030523`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140030b19`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140030b19`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140030b9f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140030b9f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140030c25`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140030c57`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140030c25`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140030c57`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140030978`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x140030978`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x140030673`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x140030673`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400305b9`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400305b9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140030a06`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140030a06`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400306c2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140030861`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1400306c2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140030861`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1400308f7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1400308f7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140030655`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1400307d3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140030655`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1400307d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TransformSDPermissions(
        void *a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        char a5,
        PSECURITY_DESCRIPTOR *a6)
{
  unsigned int v7; // eax
  const char *v8; // r8
  unsigned int v9; // edi
  DWORD LastError; // edi
  const char *v11; // r8
  DWORD v12; // edi
  const char *v13; // r8
  DWORD v14; // edi
  const char *v15; // r8
  DWORD v16; // edi
  const char *v17; // r8
  DWORD v18; // r12d
  struct _ACL *v19; // r14
  DWORD v20; // edi
  const char *v21; // r8
  DWORD i; // edi
  _DWORD *v23; // r15
  int v24; // ecx
  int v25; // edx
  __int64 j; // rax
  DWORD v27; // edi
  const char *v28; // r8
  DWORD v29; // edi
  const char *v30; // r8
  DWORD v31; // edi
  const char *v32; // r8
  DWORD v33; // edi
  const char *v34; // r8
  DWORD v35; // edi
  const char *v36; // r8
  DWORD v37; // edi
  const char *v38; // r8
  DWORD v39; // edi
  const char *v40; // r8
  DWORD v41; // edi
  const char *v42; // r8
  DWORD v43; // edi
  const char *v44; // r8
  DWORD v45; // edi
  const char *v46; // r8
  HLOCAL v47; // rax
  PSECURITY_DESCRIPTOR v48; // rcx
  DWORD v49; // edi
  const char *v50; // r8
  DWORD v51; // ebx
  DWORD dwBufferLength; // [rsp+30h] [rbp-B9h] BYREF
  LPVOID pAce; // [rsp+38h] [rbp-B1h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+40h] [rbp-A9h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+68h] [rbp-81h] BYREF
  WINBOOL bDaclPresent; // [rsp+6Ch] [rbp-7Dh] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+70h] [rbp-79h] BYREF
  PACL pDacl; // [rsp+78h] [rbp-71h] BYREF
  PACL pAcl; // [rsp+80h] [rbp-69h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+88h] [rbp-61h] BYREF
  PSID pOwner; // [rsp+90h] [rbp-59h] BYREF
  PSID pGroup; // [rsp+98h] [rbp-51h] BYREF
  struct _ACL *v64; // [rsp+A0h] [rbp-49h] BYREF
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+A8h] [rbp-41h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-21h]
  __int64 v67; // [rsp+D0h] [rbp-19h] BYREF
  int v68; // [rsp+D8h] [rbp-11h]
  __int64 pAclInformation; // [rsp+E0h] [rbp-9h] BYREF
  int v70; // [rsp+E8h] [rbp-1h]

  pSecurityDescriptor = 0;
  v7 = CopySelfRelativeSD(a1);
  v9 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v7);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v9, v8, 67);
    throw (EvtException *)pExceptionObject;
  }
  pAcl = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, v11, 80);
    throw (EvtException *)pExceptionObject;
  }
  if ( a4 && !GetSecurityDescriptorDacl(a4, &bDaclPresent, &pAcl, &bDaclDefaulted) )
  {
    v12 = GetLastError();
    if ( !v12 )
      v12 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v12);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v12, v13, 87);
    throw (EvtException *)pExceptionObject;
  }
  v67 = 0;
  v68 = 0;
  pAclInformation = 0;
  v70 = 0;
  if ( pDacl && !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    v14 = GetLastError();
    if ( !v14 )
      v14 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v14, v15, 101);
    throw (EvtException *)pExceptionObject;
  }
  if ( pAcl && !GetAclInformation(pAcl, &v67, 0xCu, AclSizeInformation) )
  {
    v16 = GetLastError();
    if ( !v16 )
      v16 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v16);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v16, v17, 109);
    throw (EvtException *)pExceptionObject;
  }
  v18 = HIDWORD(v67) + HIDWORD(pAclInformation);
  v19 = (struct _ACL *)operator new((unsigned int)(HIDWORD(v67) + HIDWORD(pAclInformation)));
  v64 = v19;
  if ( !InitializeAcl(v19, v18, 2u) )
  {
    v20 = GetLastError();
    if ( !v20 )
      v20 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v20);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v20, v21, 124);
    throw (EvtException *)pExceptionObject;
  }
  for ( i = 0; i < (unsigned int)pAclInformation && !a5; ++i )
  {
    pAce = 0;
    if ( !GetAce(pDacl, i, &pAce) )
    {
      v29 = GetLastError();
      if ( !v29 )
        v29 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v29);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v29, v30, 135);
      throw (EvtException *)pExceptionObject;
    }
    v23 = pAce;
    MapGenericMask((PDWORD)pAce + 1, &GenericMapping);
    v24 = 0;
    v25 = 1;
    for ( j = 0; j != 32; ++j )
    {
      if ( (v25 & v23[1]) != 0 )
        v24 |= *((_DWORD *)qword_14003A270 + j);
      v25 *= 2;
    }
    if ( v24 )
    {
      v23[1] = v24;
      if ( !AddAce(v19, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
      {
        v27 = GetLastError();
        if ( !v27 )
          v27 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v27);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v27, v28, 173);
        throw (EvtException *)pExceptionObject;
      }
    }
  }
  if ( pAcl && HIDWORD(v67) > 8 )
  {
    pAce = 0;
    if ( !GetAce(pAcl, 0, &pAce) )
    {
      v31 = GetLastError();
      if ( !v31 )
        v31 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v31);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v31, v32, 186);
      throw (EvtException *)pExceptionObject;
    }
    if ( !AddAce(v19, 2u, 0xFFFFFFFF, pAce, HIDWORD(v67) - 8) )
    {
      v33 = GetLastError();
      if ( !v33 )
        v33 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v33);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v33, v34, 190);
      throw (EvtException *)pExceptionObject;
    }
  }
  bOwnerDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  if ( a4 )
  {
    if ( !GetSecurityDescriptorOwner(a4, &pOwner, &bOwnerDefaulted) )
    {
      v35 = GetLastError();
      if ( !v35 )
        v35 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v35);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v35, v36, 206);
      throw (EvtException *)pExceptionObject;
    }
    if ( !GetSecurityDescriptorGroup(a4, &pGroup, &bOwnerDefaulted) )
    {
      v37 = GetLastError();
      if ( !v37 )
        v37 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v37);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v37, v38, 211);
      throw (EvtException *)pExceptionObject;
    }
  }
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  v66 = 0;
  if ( !InitializeSecurityDescriptor(pAbsoluteSecurityDescriptor, 1u) )
  {
    v39 = GetLastError();
    if ( !v39 )
      v39 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v39);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v39, v40, 218);
    throw (EvtException *)pExceptionObject;
  }
  if ( v18 && !SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, 1, v19, 0) )
  {
    v41 = GetLastError();
    if ( !v41 )
      v41 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v41);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v41, v42, 225);
    throw (EvtException *)pExceptionObject;
  }
  if ( pOwner && !SetSecurityDescriptorOwner(pAbsoluteSecurityDescriptor, pOwner, 0) )
  {
    v43 = GetLastError();
    if ( !v43 )
      v43 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v43);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v43, v44, 233);
    throw (EvtException *)pExceptionObject;
  }
  if ( pGroup && !SetSecurityDescriptorGroup(pAbsoluteSecurityDescriptor, pGroup, 0) )
  {
    v45 = GetLastError();
    if ( !v45 )
      v45 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v45);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v45, v46, 241);
    throw (EvtException *)pExceptionObject;
  }
  dwBufferLength = 0;
  MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
  v47 = LocalAlloc(0, dwBufferLength);
  v48 = *a6;
  *a6 = v47;
  if ( v48 )
    LocalFree(v48);
  if ( !MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, *a6, &dwBufferLength) )
  {
    v49 = GetLastError();
    if ( !v49 )
      v49 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v49);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v49, v50, 253);
    throw (EvtException *)pExceptionObject;
  }
  v51 = dwBufferLength;
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v64);
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&pSecurityDescriptor);
  return v51;
}

```

## disassembly

```asm
0x14003029c  mov     [rsp-8+arg_8], rbx
0x1400302a1  push    rbp
0x1400302a2  push    rsi
0x1400302a3  push    rdi
0x1400302a4  push    r12
0x1400302a6  push    r13
0x1400302a8  push    r14
0x1400302aa  push    r15
0x1400302ac  lea     rbp, [rsp-17h]
0x1400302b1  sub     rsp, 100h
0x1400302b8  mov     rax, cs:__security_cookie
0x1400302bf  xor     rax, rsp
0x1400302c2  mov     [rbp+47h+var_40], rax
0x1400302c6  mov     rsi, r9
0x1400302c9  mov     r13, [rbp+47h+arg_28]
0x1400302cd  xor     r15d, r15d
0x1400302d0  mov     [rbp+47h+pSecurityDescriptor], r15
0x1400302d4  lea     rdx, [rbp+47h+pSecurityDescriptor]
0x1400302d8  call    ?CopySelfRelativeSD@@YAKPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z; CopySelfRelativeSD(void *,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x1400302dd  mov     edi, eax
0x1400302df  test    eax, eax
0x1400302e1  jz      short loc_140030341
0x1400302e3  lea     rcx, WPP_GLOBAL_Control
0x1400302ea  mov     r10, cs:WPP_GLOBAL_Control
0x1400302f1  cmp     r10, rcx
0x1400302f4  jz      short loc_14003031D
0x1400302f6  test    byte ptr [r10+1Ch], 4
0x1400302fb  jz      short loc_14003031D
0x1400302fd  lea     ebx, [r15+2]
0x140030301  cmp     [r10+19h], bl
0x140030305  jb      short loc_14003031D
0x140030307  lea     edx, [rbx+8]
0x14003030a  mov     r9d, eax
0x14003030d  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x140030314  mov     rcx, [r10+10h]
0x140030318  call    WPP_SF_d
0x14003031d  mov     r9d, 43h ; 'C'; int
0x140030323  mov     edx, edi; unsigned int
0x140030325  lea     rcx, [rsp+130h+pExceptionObject]; this
0x14003032a  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14003032f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140030336  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x14003033b  call    _CxxThrowException_0
0x140030341  mov     [rbp+47h+pAcl], r15
0x140030345  mov     [rbp+47h+pDacl], r15
0x140030349  mov     [rbp+47h+bDaclPresent], r15d
0x14003034d  mov     [rsp+130h+bDaclDefaulted], r15d
0x140030352  lea     r9, [rsp+130h+bDaclDefaulted]; lpbDaclDefaulted
0x140030357  lea     r8, [rbp+47h+pDacl]; pDacl
0x14003035b  lea     rdx, [rbp+47h+bDaclPresent]; lpbDaclPresent
0x14003035f  mov     rcx, [rbp+47h+pSecurityDescriptor]; pSecurityDescriptor
0x140030363  call    cs:__imp_GetSecurityDescriptorDacl
0x140030369  test    eax, eax
0x14003036b  jnz     short loc_1400303DC
0x14003036d  call    cs:__imp_GetLastError
0x140030373  mov     edi, eax
0x140030375  mov     eax, 507h
0x14003037a  test    edi, edi
0x14003037c  cmovz   edi, eax
0x14003037f  lea     rcx, WPP_GLOBAL_Control
0x140030386  mov     rax, cs:WPP_GLOBAL_Control
0x14003038d  cmp     rax, rcx
0x140030390  jz      short loc_1400303B8
0x140030392  test    byte ptr [rax+1Ch], 4
0x140030396  jz      short loc_1400303B8
0x140030398  mov     ebx, 2
0x14003039d  cmp     [rax+19h], bl
0x1400303a0  jb      short loc_1400303B8
0x1400303a2  lea     edx, [rbx+9]
0x1400303a5  mov     r9d, edi
0x1400303a8  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x1400303af  mov     rcx, [rax+10h]
0x1400303b3  call    WPP_SF_d
0x1400303b8  mov     r9d, 50h ; 'P'; int
0x1400303be  mov     edx, edi; unsigned int
0x1400303c0  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1400303c5  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400303ca  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400303d1  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x1400303d6  call    _CxxThrowException_0
0x1400303dc  test    rsi, rsi
0x1400303df  jz      loc_14003046E
0x1400303e5  lea     r9, [rsp+130h+bDaclDefaulted]; lpbDaclDefaulted
0x1400303ea  lea     r8, [rbp+47h+pAcl]; pDacl
0x1400303ee  lea     rdx, [rbp+47h+bDaclPresent]; lpbDaclPresent
0x1400303f2  mov     rcx, rsi; pSecurityDescriptor
0x1400303f5  call    cs:__imp_GetSecurityDescriptorDacl
0x1400303fb  test    eax, eax
0x1400303fd  jnz     short loc_14003046E
0x1400303ff  call    cs:__imp_GetLastError
0x140030405  mov     edi, eax
0x140030407  mov     eax, 507h
0x14003040c  test    edi, edi
0x14003040e  cmovz   edi, eax
0x140030411  lea     rcx, WPP_GLOBAL_Control
0x140030418  mov     rax, cs:WPP_GLOBAL_Control
0x14003041f  cmp     rax, rcx
0x140030422  jz      short loc_14003044A
0x140030424  test    byte ptr [rax+1Ch], 4
0x140030428  jz      short loc_14003044A
0x14003042a  mov     ebx, 2
0x14003042f  cmp     [rax+19h], bl
0x140030432  jb      short loc_14003044A
0x140030434  lea     edx, [rbx+0Ah]
0x140030437  mov     r9d, edi
0x14003043a  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x140030441  mov     rcx, [rax+10h]
0x140030445  call    WPP_SF_d
0x14003044a  mov     r9d, 57h ; 'W'; int
0x140030450  mov     edx, edi; unsigned int
0x140030452  lea     rcx, [rsp+130h+pExceptionObject]; this
0x140030457  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14003045c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140030463  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x140030468  call    _CxxThrowException_0
0x14003046e  xor     eax, eax
0x140030470  mov     [rbp+47h+var_60], rax
0x140030474  mov     [rbp+47h+var_58], eax
0x140030477  mov     [rbp+47h+pAclInformation], rax
0x14003047b  mov     [rbp+47h+var_48], eax
0x14003047e  lea     ebx, [rax+2]
0x140030481  mov     rcx, [rbp+47h+pDacl]; pAcl
0x140030485  test    rcx, rcx
0x140030488  jz      short loc_140030509
0x14003048a  mov     r9d, ebx; dwAclInformationClass
0x14003048d  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140030491  lea     rdx, [rbp+47h+pAclInformation]; pAclInformation
0x140030495  call    cs:__imp_GetAclInformation
0x14003049b  test    eax, eax
0x14003049d  jnz     short loc_140030509
0x14003049f  call    cs:__imp_GetLastError
0x1400304a5  mov     edi, eax
0x1400304a7  mov     eax, 507h
0x1400304ac  test    edi, edi
0x1400304ae  cmovz   edi, eax
0x1400304b1  lea     rcx, WPP_GLOBAL_Control
0x1400304b8  mov     rax, cs:WPP_GLOBAL_Control
0x1400304bf  cmp     rax, rcx
0x1400304c2  jz      short loc_1400304E5
0x1400304c4  test    byte ptr [rax+1Ch], 4
0x1400304c8  jz      short loc_1400304E5
0x1400304ca  cmp     [rax+19h], bl
0x1400304cd  jb      short loc_1400304E5
0x1400304cf  lea     edx, [rbx+0Bh]
0x1400304d2  mov     r9d, edi
0x1400304d5  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x1400304dc  mov     rcx, [rax+10h]
0x1400304e0  call    WPP_SF_d
0x1400304e5  mov     r9d, 65h ; 'e'; int
0x1400304eb  mov     edx, edi; unsigned int
0x1400304ed  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1400304f2  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400304f7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400304fe  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x140030503  call    _CxxThrowException_0
0x140030509  mov     rcx, [rbp+47h+pAcl]; pAcl
0x14003050d  test    rcx, rcx
0x140030510  jz      loc_140030599
0x140030516  mov     r9d, ebx; dwAclInformationClass
0x140030519  mov     r8d, 0Ch; nAclInformationLength
0x14003051f  lea     rdx, [rbp+47h+var_60]; pAclInformation
0x140030523  call    cs:__imp_GetAclInformation
0x140030529  test    eax, eax
0x14003052b  jnz     short loc_140030599
0x14003052d  call    cs:__imp_GetLastError
0x140030533  mov     edi, eax
0x140030535  mov     eax, 507h
0x14003053a  test    edi, edi
0x14003053c  cmovz   edi, eax
0x14003053f  lea     rcx, WPP_GLOBAL_Control
0x140030546  mov     rax, cs:WPP_GLOBAL_Control
0x14003054d  cmp     rax, rcx
0x140030550  jz      short loc_140030575
0x140030552  test    byte ptr [rax+1Ch], 4
0x140030556  jz      short loc_140030575
0x140030558  cmp     [rax+19h], bl
0x14003055b  jb      short loc_140030575
0x14003055d  mov     edx, 0Eh
0x140030562  mov     r9d, edi
0x140030565  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x14003056c  mov     rcx, [rax+10h]
0x140030570  call    WPP_SF_d
0x140030575  mov     r9d, 6Dh ; 'm'; int
0x14003057b  mov     edx, edi; unsigned int
0x14003057d  lea     rcx, [rsp+130h+pExceptionObject]; this
0x140030582  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140030587  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14003058e  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x140030593  call    _CxxThrowException_0
0x140030599  mov     r12d, dword ptr [rbp+47h+pAclInformation+4]
0x14003059d  add     r12d, dword ptr [rbp+47h+var_60+4]
0x1400305a1  mov     ecx, r12d; dwBytes
0x1400305a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400305a9  mov     r14, rax
0x1400305ac  mov     [rbp+47h+var_90], rax
0x1400305b0  mov     r8d, ebx; dwAclRevision
0x1400305b3  mov     edx, r12d; nAclLength
0x1400305b6  mov     rcx, rax; pAcl
0x1400305b9  call    cs:__imp_InitializeAcl
0x1400305bf  test    eax, eax
0x1400305c1  jnz     short loc_14003062F
0x1400305c3  call    cs:__imp_GetLastError
0x1400305c9  mov     edi, eax
0x1400305cb  mov     eax, 507h
0x1400305d0  test    edi, edi
0x1400305d2  cmovz   edi, eax
0x1400305d5  lea     rcx, WPP_GLOBAL_Control
0x1400305dc  mov     rax, cs:WPP_GLOBAL_Control
0x1400305e3  cmp     rax, rcx
0x1400305e6  jz      short loc_14003060B
0x1400305e8  test    byte ptr [rax+1Ch], 4
0x1400305ec  jz      short loc_14003060B
0x1400305ee  cmp     [rax+19h], bl
0x1400305f1  jb      short loc_14003060B
0x1400305f3  mov     edx, 0Fh
0x1400305f8  mov     r9d, edi
0x1400305fb  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x140030602  mov     rcx, [rax+10h]
0x140030606  call    WPP_SF_d
0x14003060b  mov     r9d, 7Ch ; '|'; int
0x140030611  mov     edx, edi; unsigned int
0x140030613  lea     rcx, [rsp+130h+pExceptionObject]; this
0x140030618  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14003061d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140030624  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x140030629  call    _CxxThrowException_0
0x14003062f  mov     edi, r15d
0x140030632  cmp     edi, dword ptr [rbp+47h+pAclInformation]
0x140030635  jnb     loc_1400307B0
0x14003063b  cmp     [rbp+47h+arg_20], r15b
0x14003063f  jnz     loc_1400307B0
0x140030645  mov     [rsp+130h+pAce], r15
0x14003064a  lea     r8, [rsp+130h+pAce]; pAce
0x14003064f  mov     edx, edi; dwAceIndex
0x140030651  mov     rcx, [rbp+47h+pDacl]; pAcl
0x140030655  call    cs:__imp_GetAce
0x14003065b  test    eax, eax
0x14003065d  jz      loc_140030744
0x140030663  mov     r15, [rsp+130h+pAce]
0x140030668  lea     rdx, GenericMapping; GenericMapping
0x14003066f  lea     rcx, [r15+4]; AccessMask
0x140030673  call    cs:__imp_MapGenericMask
0x140030679  xor     ecx, ecx
0x14003067b  lea     edx, [rcx+1]
0x14003067e  mov     r8d, [r15+4]
0x140030682  xor     eax, eax
0x140030684  test    r8d, edx
0x140030687  jz      short loc_140030694
0x140030689  lea     r9, qword_14003A270
0x140030690  or      ecx, [r9+rax*4]
0x140030694  add     edx, edx
0x140030696  inc     rax
0x140030699  cmp     rax, 20h ; ' '
0x14003069d  jnz     short loc_140030684
0x14003069f  test    ecx, ecx
0x1400306a1  jz      loc_14003073A
0x1400306a7  mov     [r15+4], ecx
0x1400306ab  mov     r9, [rsp+130h+pAce]; pAceList
0x1400306b0  movzx   eax, word ptr [r9+2]
0x1400306b5  mov     [rsp+130h+nAceListLength], eax; nAceListLength
0x1400306b9  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x1400306bd  mov     edx, ebx; dwAceRevision
0x1400306bf  mov     rcx, r14; pAcl
0x1400306c2  call    cs:__imp_AddAce
0x1400306c8  xor     r15d, r15d
0x1400306cb  test    eax, eax
0x1400306cd  jnz     short loc_14003073D
0x1400306cf  call    cs:__imp_GetLastError
0x1400306d5  mov     edi, eax
0x1400306d7  mov     eax, 507h
0x1400306dc  test    edi, edi
0x1400306de  cmovz   edi, eax
0x1400306e1  lea     rcx, WPP_GLOBAL_Control
0x1400306e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400306ef  cmp     rax, rcx
0x1400306f2  jz      short loc_140030716
0x1400306f4  test    byte ptr [rax+1Ch], 4
0x1400306f8  jz      short loc_140030716
0x1400306fa  cmp     [rax+19h], bl
0x1400306fd  jb      short loc_140030716
0x1400306ff  lea     edx, [r15+11h]
0x140030703  mov     r9d, edi
0x140030706  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x14003070d  mov     rcx, [rax+10h]
0x140030711  call    WPP_SF_d
0x140030716  mov     r9d, 0ADh; int
0x14003071c  mov     edx, edi; unsigned int
0x14003071e  lea     rcx, [rsp+130h+pExceptionObject]; this
0x140030723  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140030728  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14003072f  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x140030734  call    _CxxThrowException_0
0x14003073a  xor     r15d, r15d
0x14003073d  inc     edi
0x14003073f  jmp     loc_140030632
0x140030744  call    cs:__imp_GetLastError
0x14003074a  mov     edi, eax
0x14003074c  mov     eax, 507h
0x140030751  test    edi, edi
0x140030753  cmovz   edi, eax
  ... truncated ...
```
