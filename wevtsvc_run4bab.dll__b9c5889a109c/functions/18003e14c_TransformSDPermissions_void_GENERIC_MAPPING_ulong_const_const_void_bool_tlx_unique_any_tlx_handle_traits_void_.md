# TransformSDPermissions(void *,_GENERIC_MAPPING *,ulong const * const,void *,bool,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)

- ea: `0x18003e14c`
- end: `0x18003ed43`
- name: `?TransformSDPermissions@@YAKPEAXPEAU_GENERIC_MAPPING@@QEBK0_NAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z`
- size: `3063`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000349c`
- `0x1800bff1c`

## callees

- `0x180016250`
- `0x18001c320`
- `0x18003e14c`
- `0x18003ed4c`
- `0x18003edf8`
- `0x180092008`
- `0x18009aee0`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e88c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ea5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e6f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e88c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ea5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e348`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e348`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e38d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e38d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003e1c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003e785`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003e1c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18003e785`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18003e50f`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18003e50f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003e28f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003e28f`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003e5ff`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003e9bb`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003e5ff`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18003e9bb`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18003ea51`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18003ea51`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18003eae3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18003eae3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003e4eb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003e91e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003e4eb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18003e91e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18003e2c5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18003e2c5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003ec88`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18003ec88`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003e233`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003e233`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18003e33c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18003e369`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18003e33c`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18003e369`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003e446`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003e55b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003e446`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18003e55b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003ebf7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18003ebf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TransformSDPermissions(
        void *a1,
        struct _GENERIC_MAPPING *a2,
        __int64 a3,
        void *a4,
        char a5,
        PSECURITY_DESCRIPTOR *a6)
{
  DWORD v7; // eax
  DWORD v8; // edi
  PSECURITY_DESCRIPTOR v9; // r13
  DWORD v10; // r12d
  struct _ACL *v11; // rsi
  DWORD i; // r15d
  DWORD v13; // esi
  HLOCAL v14; // rax
  PSECURITY_DESCRIPTOR *v15; // r14
  DWORD v16; // ebx
  DWORD v18; // esi
  DWORD v19; // edi
  _DWORD *v20; // r12
  int v21; // ecx
  int v22; // edx
  __int64 j; // rax
  DWORD v24; // edi
  DWORD v25; // esi
  DWORD LastError; // edi
  DWORD v27; // edi
  DWORD v28; // edi
  DWORD v29; // esi
  DWORD v30; // esi
  DWORD v31; // esi
  DWORD v32; // esi
  DWORD v33; // esi
  DWORD v34; // esi
  DWORD v35; // esi
  DWORD v36; // esi
  __int128 pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C0h]
  DWORD v39; // [rsp+48h] [rbp-B8h]
  int v40; // [rsp+4Ch] [rbp-B4h]
  int v41; // [rsp+50h] [rbp-B0h]
  DWORD dwBufferLength; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pAce; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL bDaclPresent; // [rsp+6Ch] [rbp-94h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+70h] [rbp-90h] BYREF
  int v47; // [rsp+74h] [rbp-8Ch]
  PACL pDacl; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp-80h]
  PACL pAcl; // [rsp+88h] [rbp-78h] BYREF
  PSID pOwner; // [rsp+90h] [rbp-70h] BYREF
  PSID pGroup; // [rsp+98h] [rbp-68h] BYREF
  PGENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+A8h] [rbp-58h]
  PSECURITY_DESCRIPTOR *v55; // [rsp+B0h] [rbp-50h]
  _OWORD pAbsoluteSecurityDescriptor[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-28h]
  struct _ACL *v58; // [rsp+E0h] [rbp-20h]
  __int64 pAclInformation; // [rsp+E8h] [rbp-18h] BYREF
  int v60; // [rsp+F0h] [rbp-10h]
  __int64 v61; // [rsp+F8h] [rbp-8h] BYREF
  int v62; // [rsp+100h] [rbp+0h]

  v54 = a3;
  GenericMapping = a2;
  v55 = a6;
  pSecurityDescriptor = 0;
  v7 = CopySelfRelativeSD(a1);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v7);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v8;
    v40 = -1;
    v41 = 67;
    throw (EvtException *)&pExceptionObject;
  }
  pAcl = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  v9 = pSecurityDescriptor;
  if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = LastError;
    v40 = -1;
    v41 = 80;
    throw (EvtException *)&pExceptionObject;
  }
  if ( a4 && !GetSecurityDescriptorDacl(a4, &bDaclPresent, &pAcl, &bDaclDefaulted) )
  {
    v27 = GetLastError();
    if ( !v27 )
      v27 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v27);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v27;
    v40 = -1;
    v41 = 87;
    throw (EvtException *)&pExceptionObject;
  }
  pAclInformation = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  if ( pDacl && !GetAclInformation(pDacl, &v61, 0xCu, AclSizeInformation) )
  {
    v24 = GetLastError();
    if ( !v24 )
      v24 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v24);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v24;
    v40 = -1;
    v41 = 101;
    throw (EvtException *)&pExceptionObject;
  }
  if ( pAcl && !GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    v19 = GetLastError();
    if ( !v19 )
      v19 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v19);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v19;
    v40 = -1;
    v41 = 109;
    throw (EvtException *)&pExceptionObject;
  }
  v10 = HIDWORD(pAclInformation) + HIDWORD(v61);
  v47 = HIDWORD(pAclInformation) + HIDWORD(v61);
  v11 = (struct _ACL *)operator new((unsigned int)(HIDWORD(pAclInformation) + HIDWORD(v61)));
  v58 = v11;
  if ( !InitializeAcl(v11, v10, 2u) )
  {
    v28 = GetLastError();
    if ( !v28 )
      v28 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v28);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v28;
    v40 = -1;
    v41 = 124;
    throw (EvtException *)&pExceptionObject;
  }
  for ( i = 0; i < (unsigned int)v61 && !a5; ++i )
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v29);
      }
      pExceptionObject = 0;
      v38 = 0;
      v39 = v29;
      v40 = -1;
      v41 = 135;
      throw (EvtException *)&pExceptionObject;
    }
    v20 = pAce;
    if ( GenericMapping )
      MapGenericMask((PDWORD)pAce + 1, GenericMapping);
    v21 = 0;
    v22 = 1;
    for ( j = 0; j != 32; ++j )
    {
      if ( (v22 & v20[1]) != 0 )
        v21 |= *(_DWORD *)(v54 + 4 * j);
      v22 *= 2;
    }
    v9 = pSecurityDescriptor;
    if ( v21 )
    {
      v20[1] = v21;
      if ( !AddAce(v11, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
      {
        v25 = GetLastError();
        if ( !v25 )
          v25 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v25);
        }
        pExceptionObject = 0;
        v38 = 0;
        v39 = v25;
        v40 = -1;
        v41 = 173;
        throw (EvtException *)&pExceptionObject;
      }
    }
  }
  if ( pAcl && HIDWORD(pAclInformation) > 8 )
  {
    pAce = 0;
    if ( !GetAce(pAcl, 0, &pAce) )
    {
      v30 = GetLastError();
      if ( !v30 )
        v30 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v30);
      }
      pExceptionObject = 0;
      v38 = 0;
      v39 = v30;
      v40 = -1;
      v41 = 186;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !AddAce(v11, 2u, 0xFFFFFFFF, pAce, HIDWORD(pAclInformation) - 8) )
    {
      v31 = GetLastError();
      if ( !v31 )
        v31 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v31);
      }
      pExceptionObject = 0;
      v38 = 0;
      v39 = v31;
      v40 = -1;
      v41 = 190;
      throw (EvtException *)&pExceptionObject;
    }
  }
  bOwnerDefaulted = 0;
  pOwner = 0;
  pGroup = 0;
  if ( a4 )
  {
    if ( !GetSecurityDescriptorOwner(a4, &pOwner, &bOwnerDefaulted) )
    {
      v32 = GetLastError();
      if ( !v32 )
        v32 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v32);
      }
      pExceptionObject = 0;
      v38 = 0;
      v39 = v32;
      v40 = -1;
      v41 = 206;
      throw (EvtException *)&pExceptionObject;
    }
    if ( !GetSecurityDescriptorGroup(a4, &pGroup, &bOwnerDefaulted) )
    {
      v33 = GetLastError();
      if ( !v33 )
        v33 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v33);
      }
      pExceptionObject = 0;
      v38 = 0;
      v39 = v33;
      v40 = -1;
      v41 = 211;
      throw (EvtException *)&pExceptionObject;
    }
  }
  memset(pAbsoluteSecurityDescriptor, 0, sizeof(pAbsoluteSecurityDescriptor));
  v57 = 0;
  if ( !InitializeSecurityDescriptor(pAbsoluteSecurityDescriptor, 1u) )
  {
    v34 = GetLastError();
    if ( !v34 )
      v34 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v34);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v34;
    v40 = -1;
    v41 = 218;
    throw (EvtException *)&pExceptionObject;
  }
  if ( v47 && !SetSecurityDescriptorDacl(pAbsoluteSecurityDescriptor, 1, v11, 0) )
  {
    v35 = GetLastError();
    if ( !v35 )
      v35 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v35);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v35;
    v40 = -1;
    v41 = 225;
    throw (EvtException *)&pExceptionObject;
  }
  if ( pOwner && !SetSecurityDescriptorOwner(pAbsoluteSecurityDescriptor, pOwner, 0) )
  {
    v36 = GetLastError();
    if ( !v36 )
      v36 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v36);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v36;
    v40 = -1;
    v41 = 233;
    throw (EvtException *)&pExceptionObject;
  }
  if ( pGroup && !SetSecurityDescriptorGroup(pAbsoluteSecurityDescriptor, pGroup, 0) )
  {
    v13 = GetLastError();
    if ( !v13 )
      v13 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v13);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v13;
    v40 = -1;
    v41 = 241;
    throw (EvtException *)&pExceptionObject;
  }
  dwBufferLength = 0;
  MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
  v14 = LocalAlloc(0, dwBufferLength);
  v15 = v55;
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::reset(v55, v14);
  if ( !MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, *v15, &dwBufferLength) )
  {
    v18 = GetLastError();
    if ( !v18 )
      v18 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids, v18);
    }
    pExceptionObject = 0;
    v38 = 0;
    v39 = v18;
    v40 = -1;
    v41 = 253;
    throw (EvtException *)&pExceptionObject;
  }
  v16 = dwBufferLength;
  if ( v11 )
    operator delete(v11);
  if ( v9 )
    LocalFree(v9);
  return v16;
}

```

## disassembly

```asm
0x18003e14c  mov     [rsp-8+arg_10], rbx
0x18003e151  push    rbp
0x18003e152  push    rsi
0x18003e153  push    rdi
0x18003e154  push    r12
0x18003e156  push    r13
0x18003e158  push    r14
0x18003e15a  push    r15
0x18003e15c  lea     rbp, [rsp-10h]
0x18003e161  sub     rsp, 110h
0x18003e168  mov     rax, cs:__security_cookie
0x18003e16f  xor     rax, rsp
0x18003e172  mov     [rbp+40h+var_38], rax
0x18003e176  mov     r14, r9
0x18003e179  mov     [rbp+40h+var_98], r8
0x18003e17d  mov     [rbp+40h+GenericMapping], rdx
0x18003e181  mov     rax, [rbp+40h+arg_28]
0x18003e185  mov     [rbp+40h+var_90], rax
0x18003e189  xor     esi, esi
0x18003e18b  mov     [rbp+40h+pSecurityDescriptor], rsi
0x18003e18f  lea     rdx, [rbp+40h+pSecurityDescriptor]
0x18003e193  call    ?CopySelfRelativeSD@@YAKPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z; CopySelfRelativeSD(void *,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x18003e198  mov     edi, eax
0x18003e19a  test    eax, eax
0x18003e19c  jnz     loc_18003E688
0x18003e1a2  mov     [rbp+40h+pAcl], rsi
0x18003e1a6  mov     [rsp+140h+pDacl], rsi
0x18003e1ab  mov     [rsp+140h+bDaclPresent], esi
0x18003e1af  mov     [rsp+140h+bDaclDefaulted], esi
0x18003e1b3  lea     r9, [rsp+140h+bDaclDefaulted]; lpbDaclDefaulted
0x18003e1b8  lea     r8, [rsp+140h+pDacl]; pDacl
0x18003e1bd  lea     rdx, [rsp+140h+bDaclPresent]; lpbDaclPresent
0x18003e1c2  mov     r13, [rbp+40h+pSecurityDescriptor]
0x18003e1c6  mov     rcx, r13; pSecurityDescriptor
0x18003e1c9  call    cs:__imp_GetSecurityDescriptorDacl
0x18003e1cf  test    eax, eax
0x18003e1d1  jz      loc_18003E6F6
0x18003e1d7  test    r14, r14
0x18003e1da  jnz     loc_18003E774
0x18003e1e0  xor     eax, eax
0x18003e1e2  mov     [rbp+40h+pAclInformation], rax
0x18003e1e6  mov     [rbp+40h+var_50], eax
0x18003e1e9  mov     [rbp+40h+var_48], rax
0x18003e1ed  mov     [rbp+40h+var_40], eax
0x18003e1f0  lea     ebx, [rax+2]
0x18003e1f3  mov     rcx, [rsp+140h+pDacl]; pAcl
0x18003e1f8  test    rcx, rcx
0x18003e1fb  jnz     loc_18003E54E
0x18003e201  mov     rcx, [rbp+40h+pAcl]; pAcl
0x18003e205  test    rcx, rcx
0x18003e208  jnz     loc_18003E439
0x18003e20e  mov     r12d, dword ptr [rbp+40h+var_48+4]
0x18003e212  add     r12d, dword ptr [rbp+40h+pAclInformation+4]
0x18003e216  mov     [rsp+140h+var_CC], r12d
0x18003e21b  mov     ecx, r12d; dwBytes
0x18003e21e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e223  mov     rsi, rax
0x18003e226  mov     [rbp+40h+var_60], rax
0x18003e22a  mov     r8d, ebx; dwAclRevision
0x18003e22d  mov     edx, r12d; nAclLength
0x18003e230  mov     rcx, rax; pAcl
0x18003e233  call    cs:__imp_InitializeAcl
0x18003e239  xor     r12d, r12d
0x18003e23c  test    eax, eax
0x18003e23e  jz      loc_18003E811
0x18003e244  mov     r15d, r12d
0x18003e247  or      edi, 0FFFFFFFFh
0x18003e24a  cmp     r15d, dword ptr [rbp+40h+var_48]
0x18003e24e  jb      loc_18003E4CF
0x18003e254  mov     rcx, [rbp+40h+pAcl]; pAcl
0x18003e258  test    rcx, rcx
0x18003e25b  jnz     loc_18003E908
0x18003e261  mov     [rsp+140h+bOwnerDefaulted], r12d
0x18003e266  mov     [rbp+40h+pOwner], r12
0x18003e26a  mov     [rbp+40h+pGroup], r12
0x18003e26e  test    r14, r14
0x18003e271  jnz     loc_18003EA45
0x18003e277  xorps   xmm0, xmm0
0x18003e27a  xor     eax, eax
0x18003e27c  movups  [rbp+40h+pAbsoluteSecurityDescriptor], xmm0
0x18003e280  movups  [rbp+40h+var_78], xmm0
0x18003e284  mov     [rbp+40h+var_68], rax
0x18003e288  lea     edx, [rax+1]; dwRevision
0x18003e28b  lea     rcx, [rbp+40h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x18003e28f  call    cs:__imp_InitializeSecurityDescriptor
0x18003e295  test    eax, eax
0x18003e297  jz      loc_18003EB6D
0x18003e29d  cmp     [rsp+140h+var_CC], r12d
0x18003e2a2  ja      loc_18003EBE9
0x18003e2a8  mov     rdx, [rbp+40h+pOwner]; pOwner
0x18003e2ac  test    rdx, rdx
0x18003e2af  jnz     loc_18003EC81
0x18003e2b5  mov     rdx, [rbp+40h+pGroup]; pGroup
0x18003e2b9  test    rdx, rdx
0x18003e2bc  jz      short loc_18003E32C
0x18003e2be  xor     r8d, r8d; bGroupDefaulted
0x18003e2c1  lea     rcx, [rbp+40h+pAbsoluteSecurityDescriptor]; pSecurityDescriptor
0x18003e2c5  call    cs:__imp_SetSecurityDescriptorGroup
0x18003e2cb  test    eax, eax
0x18003e2cd  jnz     short loc_18003E32C
0x18003e2cf  call    cs:__imp_GetLastError
0x18003e2d5  mov     esi, eax
0x18003e2d7  mov     ecx, 507h
0x18003e2dc  test    eax, eax
0x18003e2de  cmovz   esi, ecx
0x18003e2e1  lea     rcx, WPP_GLOBAL_Control
0x18003e2e8  mov     rax, cs:WPP_GLOBAL_Control
0x18003e2ef  cmp     rax, rcx
0x18003e2f2  jnz     loc_18003ED12
0x18003e2f8  xorps   xmm0, xmm0
0x18003e2fb  movdqu  [rsp+140h+pExceptionObject], xmm0
0x18003e301  mov     [rsp+140h+var_100], 0
0x18003e30a  mov     [rsp+140h+var_F8], esi
0x18003e30e  mov     [rsp+140h+var_F4], edi
0x18003e312  mov     [rsp+140h+var_F0], 0F1h
0x18003e31a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003e321  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18003e326  call    _CxxThrowException_0
0x18003e32c  mov     [rsp+140h+dwBufferLength], r12d
0x18003e331  lea     r8, [rsp+140h+dwBufferLength]; lpdwBufferLength
0x18003e336  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18003e338  lea     rcx, [rbp+40h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18003e33c  call    cs:__imp_MakeSelfRelativeSD
0x18003e342  mov     edx, [rsp+140h+dwBufferLength]; uBytes
0x18003e346  xor     ecx, ecx; uFlags
0x18003e348  call    cs:__imp_LocalAlloc
0x18003e34e  mov     rdx, rax
0x18003e351  mov     r14, [rbp+40h+var_90]
0x18003e355  mov     rcx, r14
0x18003e358  call    ?reset@?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::reset(void *)
0x18003e35d  lea     r8, [rsp+140h+dwBufferLength]; lpdwBufferLength
0x18003e362  mov     rdx, [r14]; pSelfRelativeSecurityDescriptor
0x18003e365  lea     rcx, [rbp+40h+pAbsoluteSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18003e369  call    cs:__imp_MakeSelfRelativeSD
0x18003e36f  test    eax, eax
0x18003e371  jz      short loc_18003E3BC
0x18003e373  mov     ebx, [rsp+140h+dwBufferLength]
0x18003e377  test    rsi, rsi
0x18003e37a  jz      short loc_18003E385
0x18003e37c  mov     rcx, rsi; void *
0x18003e37f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e384  nop
0x18003e385  test    r13, r13
0x18003e388  jz      short loc_18003E393
0x18003e38a  mov     rcx, r13; hMem
0x18003e38d  call    cs:__imp_LocalFree
0x18003e393  mov     eax, ebx
0x18003e395  mov     rcx, [rbp+40h+var_38]
0x18003e399  xor     rcx, rsp; StackCookie
0x18003e39c  call    __security_check_cookie
0x18003e3a1  mov     rbx, [rsp+140h+arg_10]
0x18003e3a9  add     rsp, 110h
0x18003e3b0  pop     r15
0x18003e3b2  pop     r14
0x18003e3b4  pop     r13
0x18003e3b6  pop     r12
0x18003e3b8  pop     rdi
0x18003e3b9  pop     rsi
0x18003e3ba  pop     rbp
0x18003e3bb  retn
0x18003e3bc  call    cs:__imp_GetLastError
0x18003e3c2  nop
0x18003e3c3  mov     esi, eax
0x18003e3c5  mov     ecx, 507h
0x18003e3ca  test    eax, eax
0x18003e3cc  cmovz   esi, ecx
0x18003e3cf  lea     rcx, WPP_GLOBAL_Control
0x18003e3d6  mov     rax, cs:WPP_GLOBAL_Control
0x18003e3dd  cmp     rax, rcx
0x18003e3e0  jz      short loc_18003E405
0x18003e3e2  test    byte ptr [rax+1Ch], 4
0x18003e3e6  jz      short loc_18003E405
0x18003e3e8  cmp     [rax+19h], bl
0x18003e3eb  jb      short loc_18003E405
0x18003e3ed  mov     edx, 1Ah
0x18003e3f2  mov     r9d, esi
0x18003e3f5  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x18003e3fc  mov     rcx, [rax+10h]
0x18003e400  call    WPP_SF_d
0x18003e405  xorps   xmm0, xmm0
0x18003e408  movdqu  [rsp+140h+pExceptionObject], xmm0
0x18003e40e  mov     [rsp+140h+var_100], 0
0x18003e417  mov     [rsp+140h+var_F8], esi
0x18003e41b  mov     [rsp+140h+var_F4], edi
0x18003e41f  mov     [rsp+140h+var_F0], 0FDh
0x18003e427  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003e42e  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18003e433  call    _CxxThrowException_0
0x18003e439  mov     r9d, ebx; dwAclInformationClass
0x18003e43c  mov     r8d, 0Ch; nAclInformationLength
0x18003e442  lea     rdx, [rbp+40h+pAclInformation]; pAclInformation
0x18003e446  call    cs:__imp_GetAclInformation
0x18003e44c  test    eax, eax
0x18003e44e  jnz     loc_18003E20E
0x18003e454  call    cs:__imp_GetLastError
0x18003e45a  mov     edi, eax
0x18003e45c  mov     ecx, 507h
0x18003e461  test    eax, eax
0x18003e463  cmovz   edi, ecx
0x18003e466  lea     rcx, WPP_GLOBAL_Control
0x18003e46d  mov     rax, cs:WPP_GLOBAL_Control
0x18003e474  cmp     rax, rcx
0x18003e477  jz      short loc_18003E49C
0x18003e479  test    byte ptr [rax+1Ch], 4
0x18003e47d  jz      short loc_18003E49C
0x18003e47f  cmp     [rax+19h], bl
0x18003e482  jb      short loc_18003E49C
0x18003e484  mov     edx, 0Eh
0x18003e489  mov     r9d, edi
0x18003e48c  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x18003e493  mov     rcx, [rax+10h]
0x18003e497  call    WPP_SF_d
0x18003e49c  xorps   xmm0, xmm0
0x18003e49f  movdqu  [rsp+140h+pExceptionObject], xmm0
0x18003e4a5  mov     [rsp+140h+var_100], rsi
0x18003e4aa  mov     [rsp+140h+var_F8], edi
0x18003e4ae  or      edi, 0FFFFFFFFh
0x18003e4b1  mov     [rsp+140h+var_F4], edi
0x18003e4b5  mov     [rsp+140h+var_F0], 6Dh ; 'm'
0x18003e4bd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003e4c4  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18003e4c9  call    _CxxThrowException_0
0x18003e4cf  cmp     [rbp+40h+arg_20], r12b
0x18003e4d3  jnz     loc_18003E254
0x18003e4d9  mov     [rsp+140h+pAce], r12
0x18003e4de  lea     r8, [rsp+140h+pAce]; pAce
0x18003e4e3  mov     edx, r15d; dwAceIndex
0x18003e4e6  mov     rcx, [rsp+140h+pDacl]; pAcl
0x18003e4eb  call    cs:__imp_GetAce
0x18003e4f1  test    eax, eax
0x18003e4f3  jz      loc_18003E88C
0x18003e4f9  mov     r12, [rsp+140h+pAce]
0x18003e4fe  mov     rax, [rbp+40h+GenericMapping]
0x18003e502  test    rax, rax
0x18003e505  jz      short loc_18003E515
0x18003e507  mov     rdx, rax; GenericMapping
0x18003e50a  lea     rcx, [r12+4]; AccessMask
0x18003e50f  call    cs:__imp_MapGenericMask
0x18003e515  xor     ecx, ecx
0x18003e517  lea     edx, [rcx+1]
0x18003e51a  xor     eax, eax
0x18003e51c  mov     r13, [rbp+40h+var_98]
0x18003e520  test    [r12+4], edx
0x18003e525  jz      short loc_18003E52C
0x18003e527  or      ecx, [r13+rax*4+0]
0x18003e52c  add     edx, edx
0x18003e52e  inc     rax
0x18003e531  cmp     rax, 20h ; ' '
0x18003e535  jnz     short loc_18003E520
0x18003e537  mov     r13, [rbp+40h+pSecurityDescriptor]
0x18003e53b  test    ecx, ecx
0x18003e53d  jnz     loc_18003E5E4
0x18003e543  xor     r12d, r12d
0x18003e546  inc     r15d
0x18003e549  jmp     loc_18003E24A
0x18003e54e  mov     r9d, ebx; dwAclInformationClass
0x18003e551  mov     r8d, 0Ch; nAclInformationLength
0x18003e557  lea     rdx, [rbp+40h+var_48]; pAclInformation
0x18003e55b  call    cs:__imp_GetAclInformation
0x18003e561  test    eax, eax
0x18003e563  jnz     loc_18003E201
0x18003e569  call    cs:__imp_GetLastError
0x18003e56f  mov     edi, eax
0x18003e571  mov     ecx, 507h
0x18003e576  test    eax, eax
0x18003e578  cmovz   edi, ecx
0x18003e57b  lea     rcx, WPP_GLOBAL_Control
0x18003e582  mov     rax, cs:WPP_GLOBAL_Control
0x18003e589  cmp     rax, rcx
0x18003e58c  jz      short loc_18003E5B1
0x18003e58e  test    byte ptr [rax+1Ch], 4
0x18003e592  jz      short loc_18003E5B1
0x18003e594  cmp     [rax+19h], bl
0x18003e597  jb      short loc_18003E5B1
0x18003e599  mov     edx, 0Dh
0x18003e59e  mov     r9d, edi
0x18003e5a1  lea     r8, WPP_41fe612362a23b47d3c4e1e38e5a1c24_Traceguids
0x18003e5a8  mov     rcx, [rax+10h]
0x18003e5ac  call    WPP_SF_d
0x18003e5b1  xorps   xmm0, xmm0
0x18003e5b4  movdqu  [rsp+140h+pExceptionObject], xmm0
0x18003e5ba  mov     [rsp+140h+var_100], rsi
0x18003e5bf  mov     [rsp+140h+var_F8], edi
0x18003e5c3  or      edi, 0FFFFFFFFh
0x18003e5c6  mov     [rsp+140h+var_F4], edi
0x18003e5ca  mov     [rsp+140h+var_F0], 65h ; 'e'
0x18003e5d2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003e5d9  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18003e5de  call    _CxxThrowException_0
0x18003e5e4  mov     [r12+4], ecx
0x18003e5e9  mov     r9, [rsp+140h+pAce]; pAceList
0x18003e5ee  movzx   eax, word ptr [r9+2]
0x18003e5f3  mov     [rsp+140h+nAceListLength], eax; nAceListLength
0x18003e5f7  mov     r8d, edi; dwStartingAceIndex
0x18003e5fa  mov     edx, ebx; dwAceRevision
0x18003e5fc  mov     rcx, rsi; pAcl
0x18003e5ff  call    cs:__imp_AddAce
0x18003e605  xor     r12d, r12d
0x18003e608  test    eax, eax
0x18003e60a  jnz     loc_18003E546
  ... truncated ...
```
