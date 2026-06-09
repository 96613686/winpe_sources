# CWbemNamespace::CommonValidateAndSetSD(CNtSecurityDescriptor *,bool)

- ea: `0x18007ebf4`
- end: `0x18007f401`
- name: `?CommonValidateAndSetSD@CWbemNamespace@@QEAAJPEAVCNtSecurityDescriptor@@_N@Z`
- size: `2061`
- prototype: `__int64 __fastcall(CWbemNamespace *__hidden this, struct CNtSecurityDescriptor *, bool)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180049d34`
- `0x1800bf004`
- `0x1800bf154`

## callees

- `0x18000b140`
- `0x180024098`
- `0x1800251a4`
- `0x18005d9a8`
- `0x180060ba4`
- `0x18007bac8`
- `0x18007ebf4`
- `0x180080f48`
- `0x1800be2d0`
- `0x1800bed4c`
- `0x1800bf2d8`
- `0x1800bf548`
- `0x1800bf788`

## import_xrefs

- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x18007ec10`
- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x18007f360`
- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x18007ec10`
- `wbemcomn!?GetStatus@CNtSecurityDescriptor@@QEAAKXZ` at `0x18007f360`
- `wbemcomn!?OrderAces@CNtAcl@@QEAAPEAV1@XZ` at `0x18007eeb7`
- `wbemcomn!?OrderAces@CNtAcl@@QEAAPEAV1@XZ` at `0x18007f07e`
- `wbemcomn!?OrderAces@CNtAcl@@QEAAPEAV1@XZ` at `0x18007eeb7`
- `wbemcomn!?OrderAces@CNtAcl@@QEAAPEAV1@XZ` at `0x18007f07e`
- `wbemcomn!??4CNtSecurityDescriptor@@QEAAAEAV0@AEAV0@@Z` at `0x18007f357`
- `wbemcomn!??4CNtSecurityDescriptor@@QEAAAEAV0@AEAV0@@Z` at `0x18007f357`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007ec8a`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007ee50`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007ec8a`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007ee50`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007ef99`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007f152`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007ef99`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z` at `0x18007f152`
- `wbemcomn!?SetSacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x18007f0d5`
- `wbemcomn!?SetSacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x18007f0d5`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x18007ef1d`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x18007ef1d`
- `wbemcomn!GetMemLogObject` at `0x18007ec1a`
- `wbemcomn!GetMemLogObject` at `0x18007ec96`
- `wbemcomn!GetMemLogObject` at `0x18007ece5`
- `wbemcomn!GetMemLogObject` at `0x18007ed53`
- `wbemcomn!GetMemLogObject` at `0x18007eda7`
- `wbemcomn!GetMemLogObject` at `0x18007edfb`
- `wbemcomn!GetMemLogObject` at `0x18007ee5c`
- `wbemcomn!GetMemLogObject` at `0x18007eec2`
- `wbemcomn!GetMemLogObject` at `0x18007ef27`
- `wbemcomn!GetMemLogObject` at `0x18007efa5`
- `wbemcomn!GetMemLogObject` at `0x18007f023`
- `wbemcomn!GetMemLogObject` at `0x18007f089`
- `wbemcomn!GetMemLogObject` at `0x18007f0df`
- `wbemcomn!GetMemLogObject` at `0x18007f15e`
- `wbemcomn!GetMemLogObject` at `0x18007f1c9`
- `wbemcomn!GetMemLogObject` at `0x18007f23e`
- `wbemcomn!GetMemLogObject` at `0x18007f2af`
- `wbemcomn!GetMemLogObject` at `0x18007f30b`
- `wbemcomn!GetMemLogObject` at `0x18007f398`
- `wbemcomn!GetMemLogObject` at `0x18007ec1a`
- `wbemcomn!GetMemLogObject` at `0x18007ec96`
- `wbemcomn!GetMemLogObject` at `0x18007ece5`
- `wbemcomn!GetMemLogObject` at `0x18007ed53`
- `wbemcomn!GetMemLogObject` at `0x18007eda7`
- `wbemcomn!GetMemLogObject` at `0x18007edfb`
- `wbemcomn!GetMemLogObject` at `0x18007ee5c`
- `wbemcomn!GetMemLogObject` at `0x18007eec2`
- `wbemcomn!GetMemLogObject` at `0x18007ef27`
- `wbemcomn!GetMemLogObject` at `0x18007efa5`
- `wbemcomn!GetMemLogObject` at `0x18007f023`
- `wbemcomn!GetMemLogObject` at `0x18007f089`
- `wbemcomn!GetMemLogObject` at `0x18007f0df`
- `wbemcomn!GetMemLogObject` at `0x18007f15e`
- `wbemcomn!GetMemLogObject` at `0x18007f1c9`
- `wbemcomn!GetMemLogObject` at `0x18007f23e`
- `wbemcomn!GetMemLogObject` at `0x18007f2af`
- `wbemcomn!GetMemLogObject` at `0x18007f30b`
- `wbemcomn!GetMemLogObject` at `0x18007f398`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ec2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007eca1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ecf5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ed5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007edb2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ee06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ee67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007eed2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ef37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007efb0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f02e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f099`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f0ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f169`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f1d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f249`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f2ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f316`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f3a3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ec2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007eca1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ecf5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ed5e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007edb2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ee06`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ee67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007eed2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007ef37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007efb0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f02e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f099`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f0ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f169`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f1d4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f249`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f2ba`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f316`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18007f3a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWbemNamespace::CommonValidateAndSetSD(
        struct IWmiDbSession **this,
        struct CNtSecurityDescriptor *a2,
        char a3)
{
  CMemoryLog *v6; // rax
  signed int Dacl; // ebx
  CClientCnt *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CNtAcl *v17; // rax
  CMemoryLog *v18; // rax
  CClientCnt *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CMemoryLog *v22; // rax
  CNtAcl **v23; // rcx
  CMemoryLog *v24; // rax
  CNtAcl *v25; // rcx
  CMemoryLog *v26; // rax
  CClientCnt *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  CNtAcl *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax
  bool v40; // [rsp+20h] [rbp-48h] BYREF
  bool v41; // [rsp+21h] [rbp-47h] BYREF
  bool v42; // [rsp+22h] [rbp-46h] BYREF
  CNtAcl *v43; // [rsp+28h] [rbp-40h] BYREF
  struct CNtAcl *v44; // [rsp+30h] [rbp-38h] BYREF
  struct CNtAcl *v45; // [rsp+38h] [rbp-30h] BYREF
  struct CNtAcl *v46; // [rsp+40h] [rbp-28h] BYREF
  CNtAcl *v47; // [rsp+48h] [rbp-20h] BYREF
  CNtAcl *v48; // [rsp+50h] [rbp-18h] BYREF
  CNtAcl *v49; // [rsp+B8h] [rbp+50h] BYREF

  if ( !CNtSecurityDescriptor::GetStatus(a2) )
  {
    v47 = 0;
    Dacl = CNtSecurityDescriptor::GetDacl(a2, &v47);
    if ( Dacl < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, Dacl);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Dacl;
      }
      v9 = 136;
      goto LABEL_12;
    }
    if ( !v47 )
    {
      v12 = GetMemLogObject();
      Dacl = -2147217400;
      CMemoryLog::Write(v12, -2147217400);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v9 = 137;
        v10 = 2147749896LL;
        goto LABEL_6;
      }
      return (unsigned int)Dacl;
    }
    CNtAcl::`scalar deleting destructor'(v47);
    Dacl = CheckOwnerAndReplace(a2, (struct CNtSecurityDescriptor *)(this + 27));
    if ( Dacl < 0 )
    {
      v13 = GetMemLogObject();
      CMemoryLog::Write(v13, Dacl);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Dacl;
      }
      v9 = 138;
      goto LABEL_12;
    }
    Dacl = StripOutInheritedAcesForDACL(a2);
    if ( Dacl < 0 )
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, Dacl);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Dacl;
      }
      v9 = 139;
      goto LABEL_12;
    }
    Dacl = StripOutInheritedAcesForSACL(a2);
    if ( Dacl < 0 )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, Dacl);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Dacl;
      }
      v9 = 140;
      goto LABEL_12;
    }
    v45 = 0;
    Dacl = CNtSecurityDescriptor::GetDacl(a2, &v45);
    if ( Dacl < 0 )
    {
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, Dacl);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)Dacl;
      }
      v9 = 141;
LABEL_12:
      v10 = (unsigned int)Dacl;
      goto LABEL_6;
    }
    v48 = v45;
    if ( v45 )
    {
      v17 = CNtAcl::OrderAces(v45);
      if ( !v17 )
      {
        v18 = GetMemLogObject();
        Dacl = -2147217407;
        CMemoryLog::Write(v18, -2147217407);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_120;
        }
        v20 = 142;
        v21 = 2147749889LL;
        goto LABEL_56;
      }
      v49 = v17;
      if ( !CNtSecurityDescriptor::SetDacl(a2, v17) )
      {
        v22 = GetMemLogObject();
        Dacl = -2147217407;
        CMemoryLog::Write(v22, -2147217407);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            143,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            2147749889LL);
        }
        v23 = &v49;
        goto LABEL_67;
      }
      CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v49);
    }
    v44 = 0;
    Dacl = CNtSecurityDescriptor::GetSacl(a2, &v44);
    if ( Dacl < 0 )
    {
      v24 = GetMemLogObject();
      CMemoryLog::Write(v24, Dacl);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_120;
      }
      v20 = 144;
      v21 = (unsigned int)Dacl;
LABEL_56:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v21);
LABEL_120:
      CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v48);
      return (unsigned int)Dacl;
    }
    v43 = v44;
    v25 = v44;
    if ( v44 )
    {
      if ( a3 )
      {
        Dacl = CheckForSaclPriv();
        if ( Dacl < 0 )
        {
          v26 = GetMemLogObject();
          CMemoryLog::Write(v26, Dacl);
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_66;
          }
          v28 = 145;
          goto LABEL_64;
        }
        v25 = v44;
      }
      v30 = CNtAcl::OrderAces(v25);
      if ( !v30 )
      {
        v31 = GetMemLogObject();
        Dacl = -2147217407;
        CMemoryLog::Write(v31, -2147217407);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_66;
        }
        v28 = 146;
        v29 = 2147749889LL;
        goto LABEL_65;
      }
      v49 = v30;
      if ( !CNtSecurityDescriptor::SetSacl(a2, v30) )
      {
        v32 = GetMemLogObject();
        Dacl = -2147217407;
        CMemoryLog::Write(v32, -2147217407);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            147,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            2147749889LL);
        }
LABEL_79:
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v49);
        goto LABEL_66;
      }
    }
    else
    {
      v46 = 0;
      Dacl = CNtSecurityDescriptor::GetSacl((CNtSecurityDescriptor *)(this + 27), &v46);
      if ( Dacl < 0 )
      {
        v33 = GetMemLogObject();
        CMemoryLog::Write(v33, Dacl);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_66;
        }
        v28 = 148;
LABEL_64:
        v29 = (unsigned int)Dacl;
LABEL_65:
        WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v29);
LABEL_66:
        v23 = &v43;
LABEL_67:
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(v23);
        goto LABEL_120;
      }
      if ( !v46 )
      {
LABEL_95:
        v40 = 0;
        LOBYTE(v49) = 0;
        Dacl = _IsSDProtected(a2, &v40, (bool *)&v49);
        if ( Dacl >= 0 )
        {
          if ( v40 && (_BYTE)v49
            || (Dacl = CWbemNamespace::GetParentInheritableAces((CWbemNamespace *)this, a2, !v40, (_BYTE)v49 == 0),
                Dacl >= 0) )
          {
            Dacl = StoreSDIntoNamespace(this[5], this[7], a2);
            if ( Dacl >= 0 )
            {
              CNtSecurityDescriptor::operator=(this + 27, a2);
              if ( CNtSecurityDescriptor::GetStatus((CNtSecurityDescriptor *)(this + 27)) )
              {
                CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v43);
                Dacl = -2147217398;
                goto LABEL_120;
              }
              v42 = 1;
              v41 = 1;
              Dacl = CWbemNamespace::RecursiveSDMerge((CWbemNamespace *)this, &v42, &v41);
              if ( Dacl >= 0 )
              {
                CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v43);
                Dacl = 0;
                goto LABEL_120;
              }
              v38 = GetMemLogObject();
              CMemoryLog::Write(v38, Dacl);
              v27 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_66;
              }
              v28 = 153;
            }
            else
            {
              v37 = GetMemLogObject();
              CMemoryLog::Write(v37, Dacl);
              v27 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_66;
              }
              v28 = 152;
            }
          }
          else
          {
            v36 = GetMemLogObject();
            CMemoryLog::Write(v36, Dacl);
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_66;
            }
            v28 = 151;
          }
        }
        else
        {
          v35 = GetMemLogObject();
          CMemoryLog::Write(v35, Dacl);
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_66;
          }
          v28 = 150;
        }
        goto LABEL_64;
      }
      v49 = v46;
      if ( !IsSaclAllInherited(v46) )
      {
        Dacl = CheckForSaclPriv();
        if ( Dacl < 0 )
        {
          v34 = GetMemLogObject();
          CMemoryLog::Write(v34, Dacl);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              149,
              WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
              (unsigned int)Dacl);
          }
          goto LABEL_79;
        }
      }
    }
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v49);
    goto LABEL_95;
  }
  v6 = GetMemLogObject();
  Dacl = -2147217393;
  CMemoryLog::Write(v6, -2147217393);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 135;
    v10 = 2147749903LL;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v10);
  }
  return (unsigned int)Dacl;
}

```

## disassembly

```asm
0x18007ebf4  push    rbp
0x18007ebf6  push    rbx
0x18007ebf7  push    rsi
0x18007ebf8  push    rdi
0x18007ebf9  push    r14
0x18007ebfb  push    r15
0x18007ebfd  mov     rbp, rsp
0x18007ec00  sub     rsp, 68h
0x18007ec04  mov     r15b, r8b
0x18007ec07  mov     rdi, rdx
0x18007ec0a  mov     rsi, rcx
0x18007ec0d  mov     rcx, rdx
0x18007ec10  call    cs:__imp_?GetStatus@CNtSecurityDescriptor@@QEAAKXZ; CNtSecurityDescriptor::GetStatus(void)
0x18007ec16  test    eax, eax
0x18007ec18  jz      short loc_18007EC7B
0x18007ec1a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ec20  mov     ebx, 8004100Fh
0x18007ec25  mov     edx, ebx
0x18007ec27  mov     rcx, rax
0x18007ec2a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ec30  lea     rax, WPP_GLOBAL_Control
0x18007ec37  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ec3e  cmp     rcx, rax
0x18007ec41  jz      loc_18007F3F2
0x18007ec47  test    byte ptr [rcx+1Ch], 1
0x18007ec4b  jz      loc_18007F3F2
0x18007ec51  cmp     byte ptr [rcx+19h], 2
0x18007ec55  jb      loc_18007F3F2
0x18007ec5b  mov     edx, 87h
0x18007ec60  mov     r9d, 8004100Fh
0x18007ec66  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18007ec6d  mov     rcx, [rcx+10h]
0x18007ec71  call    WPP_SF_d
0x18007ec76  jmp     loc_18007F3F2
0x18007ec7b  mov     [rbp+var_20], 0
0x18007ec83  lea     rdx, [rbp+var_20]
0x18007ec87  mov     rcx, rdi
0x18007ec8a  call    cs:__imp_?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z; CNtSecurityDescriptor::GetDacl(CNtAcl * *)
0x18007ec90  mov     ebx, eax
0x18007ec92  test    eax, eax
0x18007ec94  jns     short loc_18007ECDC
0x18007ec96  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ec9c  mov     edx, ebx
0x18007ec9e  mov     rcx, rax
0x18007eca1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007eca7  lea     rax, WPP_GLOBAL_Control
0x18007ecae  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ecb5  cmp     rcx, rax
0x18007ecb8  jz      loc_18007F3F2
0x18007ecbe  test    byte ptr [rcx+1Ch], 1
0x18007ecc2  jz      loc_18007F3F2
0x18007ecc8  cmp     byte ptr [rcx+19h], 2
0x18007eccc  jb      loc_18007F3F2
0x18007ecd2  mov     edx, 88h
0x18007ecd7  mov     r9d, ebx
0x18007ecda  jmp     short loc_18007EC66
0x18007ecdc  mov     rcx, [rbp+var_20]; this
0x18007ece0  test    rcx, rcx
0x18007ece3  jnz     short loc_18007ED36
0x18007ece5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007eceb  mov     ebx, 80041008h
0x18007ecf0  mov     edx, ebx
0x18007ecf2  mov     rcx, rax
0x18007ecf5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ecfb  lea     rax, WPP_GLOBAL_Control
0x18007ed02  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed09  cmp     rcx, rax
0x18007ed0c  jz      loc_18007F3F2
0x18007ed12  test    byte ptr [rcx+1Ch], 1
0x18007ed16  jz      loc_18007F3F2
0x18007ed1c  cmp     byte ptr [rcx+19h], 2
0x18007ed20  jb      loc_18007F3F2
0x18007ed26  mov     edx, 89h
0x18007ed2b  mov     r9d, 80041008h
0x18007ed31  jmp     loc_18007EC66
0x18007ed36  call    ??_GCNtAcl@@QEAAPEAXI@Z; CNtAcl::`scalar deleting destructor'(uint)
0x18007ed3b  lea     r14, [rsi+0D8h]
0x18007ed42  mov     rdx, r14; struct CNtSecurityDescriptor *
0x18007ed45  mov     rcx, rdi; struct CNtSecurityDescriptor *
0x18007ed48  call    ?CheckOwnerAndReplace@@YAJPEAVCNtSecurityDescriptor@@0@Z; CheckOwnerAndReplace(CNtSecurityDescriptor *,CNtSecurityDescriptor *)
0x18007ed4d  mov     ebx, eax
0x18007ed4f  test    eax, eax
0x18007ed51  jns     short loc_18007ED99
0x18007ed53  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ed59  mov     edx, ebx
0x18007ed5b  mov     rcx, rax
0x18007ed5e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ed64  lea     rax, WPP_GLOBAL_Control
0x18007ed6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed72  cmp     rcx, rax
0x18007ed75  jz      loc_18007F3F2
0x18007ed7b  test    byte ptr [rcx+1Ch], 1
0x18007ed7f  jz      loc_18007F3F2
0x18007ed85  cmp     byte ptr [rcx+19h], 2
0x18007ed89  jb      loc_18007F3F2
0x18007ed8f  mov     edx, 8Ah
0x18007ed94  jmp     loc_18007ECD7
0x18007ed99  mov     rcx, rdi; struct CNtSecurityDescriptor *
0x18007ed9c  call    ?StripOutInheritedAcesForDACL@@YAJAEAVCNtSecurityDescriptor@@@Z; StripOutInheritedAcesForDACL(CNtSecurityDescriptor &)
0x18007eda1  mov     ebx, eax
0x18007eda3  test    eax, eax
0x18007eda5  jns     short loc_18007EDED
0x18007eda7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007edad  mov     edx, ebx
0x18007edaf  mov     rcx, rax
0x18007edb2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007edb8  lea     rax, WPP_GLOBAL_Control
0x18007edbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007edc6  cmp     rcx, rax
0x18007edc9  jz      loc_18007F3F2
0x18007edcf  test    byte ptr [rcx+1Ch], 1
0x18007edd3  jz      loc_18007F3F2
0x18007edd9  cmp     byte ptr [rcx+19h], 2
0x18007eddd  jb      loc_18007F3F2
0x18007ede3  mov     edx, 8Bh
0x18007ede8  jmp     loc_18007ECD7
0x18007eded  mov     rcx, rdi; struct CNtSecurityDescriptor *
0x18007edf0  call    ?StripOutInheritedAcesForSACL@@YAJAEAVCNtSecurityDescriptor@@@Z; StripOutInheritedAcesForSACL(CNtSecurityDescriptor &)
0x18007edf5  mov     ebx, eax
0x18007edf7  test    eax, eax
0x18007edf9  jns     short loc_18007EE41
0x18007edfb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ee01  mov     edx, ebx
0x18007ee03  mov     rcx, rax
0x18007ee06  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ee0c  lea     rax, WPP_GLOBAL_Control
0x18007ee13  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ee1a  cmp     rcx, rax
0x18007ee1d  jz      loc_18007F3F2
0x18007ee23  test    byte ptr [rcx+1Ch], 1
0x18007ee27  jz      loc_18007F3F2
0x18007ee2d  cmp     byte ptr [rcx+19h], 2
0x18007ee31  jb      loc_18007F3F2
0x18007ee37  mov     edx, 8Ch
0x18007ee3c  jmp     loc_18007ECD7
0x18007ee41  mov     [rbp+var_30], 0
0x18007ee49  lea     rdx, [rbp+var_30]
0x18007ee4d  mov     rcx, rdi
0x18007ee50  call    cs:__imp_?GetDacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z; CNtSecurityDescriptor::GetDacl(CNtAcl * *)
0x18007ee56  mov     ebx, eax
0x18007ee58  test    eax, eax
0x18007ee5a  jns     short loc_18007EEA2
0x18007ee5c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ee62  mov     edx, ebx
0x18007ee64  mov     rcx, rax
0x18007ee67  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ee6d  lea     rax, WPP_GLOBAL_Control
0x18007ee74  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ee7b  cmp     rcx, rax
0x18007ee7e  jz      loc_18007F3F2
0x18007ee84  test    byte ptr [rcx+1Ch], 1
0x18007ee88  jz      loc_18007F3F2
0x18007ee8e  cmp     byte ptr [rcx+19h], 2
0x18007ee92  jb      loc_18007F3F2
0x18007ee98  mov     edx, 8Dh
0x18007ee9d  jmp     loc_18007ECD7
0x18007eea2  mov     rax, [rbp+var_30]
0x18007eea6  mov     [rbp+var_18], rax
0x18007eeaa  mov     rcx, [rbp+var_30]
0x18007eeae  test    rcx, rcx
0x18007eeb1  jz      loc_18007EF8A
0x18007eeb7  call    cs:__imp_?OrderAces@CNtAcl@@QEAAPEAV1@XZ; CNtAcl::OrderAces(void)
0x18007eebd  test    rax, rax
0x18007eec0  jnz     short loc_18007EF13
0x18007eec2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007eec8  mov     ebx, 80041001h
0x18007eecd  mov     edx, ebx
0x18007eecf  mov     rcx, rax
0x18007eed2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007eed8  lea     rax, WPP_GLOBAL_Control
0x18007eedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eee6  cmp     rcx, rax
0x18007eee9  jz      loc_18007F3E9
0x18007eeef  test    byte ptr [rcx+1Ch], 1
0x18007eef3  jz      loc_18007F3E9
0x18007eef9  cmp     byte ptr [rcx+19h], 2
0x18007eefd  jb      loc_18007F3E9
0x18007ef03  mov     edx, 8Eh
0x18007ef08  mov     r9d, 80041001h
0x18007ef0e  jmp     loc_18007EFE9
0x18007ef13  mov     [rbp+arg_18], rax
0x18007ef17  mov     rdx, rax
0x18007ef1a  mov     rcx, rdi
0x18007ef1d  call    cs:__imp_?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x18007ef23  test    eax, eax
0x18007ef25  jnz     short loc_18007EF81
0x18007ef27  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007ef2d  mov     ebx, 80041001h
0x18007ef32  mov     edx, ebx
0x18007ef34  mov     rcx, rax
0x18007ef37  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007ef3d  lea     rax, WPP_GLOBAL_Control
0x18007ef44  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ef4b  cmp     rcx, rax
0x18007ef4e  jz      short loc_18007EF78
0x18007ef50  test    byte ptr [rcx+1Ch], 1
0x18007ef54  jz      short loc_18007EF78
0x18007ef56  cmp     byte ptr [rcx+19h], 2
0x18007ef5a  jb      short loc_18007EF78
0x18007ef5c  mov     edx, 8Fh
0x18007ef61  mov     r9d, 80041001h
0x18007ef67  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18007ef6e  mov     rcx, [rcx+10h]
0x18007ef72  call    WPP_SF_d
0x18007ef77  nop
0x18007ef78  lea     rcx, [rbp+arg_18]
0x18007ef7c  jmp     loc_18007F070
0x18007ef81  lea     rcx, [rbp+arg_18]
0x18007ef85  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x18007ef8a  mov     [rbp+var_38], 0
0x18007ef92  lea     rdx, [rbp+var_38]
0x18007ef96  mov     rcx, rdi
0x18007ef99  call    cs:__imp_?GetSacl@CNtSecurityDescriptor@@QEAAJPEAPEAVCNtAcl@@@Z; CNtSecurityDescriptor::GetSacl(CNtAcl * *)
0x18007ef9f  mov     ebx, eax
0x18007efa1  test    eax, eax
0x18007efa3  jns     short loc_18007EFFE
0x18007efa5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007efab  mov     edx, ebx
0x18007efad  mov     rcx, rax
0x18007efb0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007efb6  lea     rax, WPP_GLOBAL_Control
0x18007efbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007efc4  cmp     rcx, rax
0x18007efc7  jz      loc_18007F3E9
0x18007efcd  test    byte ptr [rcx+1Ch], 1
0x18007efd1  jz      loc_18007F3E9
0x18007efd7  cmp     byte ptr [rcx+19h], 2
0x18007efdb  jb      loc_18007F3E9
0x18007efe1  mov     edx, 90h
0x18007efe6  mov     r9d, ebx
0x18007efe9  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18007eff0  mov     rcx, [rcx+10h]
0x18007eff4  call    WPP_SF_d
0x18007eff9  jmp     loc_18007F3E9
0x18007effe  mov     rax, [rbp+var_38]
0x18007f002  mov     [rbp+var_40], rax
0x18007f006  mov     rcx, [rbp+var_38]
0x18007f00a  test    rcx, rcx
0x18007f00d  jz      loc_18007F143
0x18007f013  test    r15b, r15b
0x18007f016  jz      short loc_18007F07E
0x18007f018  call    ?CheckForSaclPriv@@YAJXZ; CheckForSaclPriv(void)
0x18007f01d  mov     ebx, eax
0x18007f01f  test    eax, eax
0x18007f021  jns     short loc_18007F07A
0x18007f023  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f029  mov     edx, ebx
0x18007f02b  mov     rcx, rax
0x18007f02e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f034  lea     rax, WPP_GLOBAL_Control
0x18007f03b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f042  cmp     rcx, rax
0x18007f045  jz      short loc_18007F06C
0x18007f047  test    byte ptr [rcx+1Ch], 1
0x18007f04b  jz      short loc_18007F06C
0x18007f04d  cmp     byte ptr [rcx+19h], 2
0x18007f051  jb      short loc_18007F06C
0x18007f053  mov     edx, 91h
0x18007f058  mov     r9d, ebx
0x18007f05b  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18007f062  mov     rcx, [rcx+10h]
0x18007f066  call    WPP_SF_d
0x18007f06b  nop
0x18007f06c  lea     rcx, [rbp+var_40]
0x18007f070  call    ??1?$CDeleteMe@VCNtAcl@@@@QEAA@XZ; CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(void)
0x18007f075  jmp     loc_18007F3E9
0x18007f07a  mov     rcx, [rbp+var_38]
0x18007f07e  call    cs:__imp_?OrderAces@CNtAcl@@QEAAPEAV1@XZ; CNtAcl::OrderAces(void)
0x18007f084  test    rax, rax
0x18007f087  jnz     short loc_18007F0CB
0x18007f089  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f08f  mov     ebx, 80041001h
0x18007f094  mov     edx, ebx
0x18007f096  mov     rcx, rax
0x18007f099  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f09f  lea     rax, WPP_GLOBAL_Control
0x18007f0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f0ad  cmp     rcx, rax
0x18007f0b0  jz      short loc_18007F06C
0x18007f0b2  test    byte ptr [rcx+1Ch], 1
0x18007f0b6  jz      short loc_18007F06C
0x18007f0b8  cmp     byte ptr [rcx+19h], 2
0x18007f0bc  jb      short loc_18007F06C
0x18007f0be  mov     edx, 92h
0x18007f0c3  mov     r9d, 80041001h
0x18007f0c9  jmp     short loc_18007F05B
0x18007f0cb  mov     [rbp+arg_18], rax
0x18007f0cf  mov     rdx, rax
0x18007f0d2  mov     rcx, rdi
0x18007f0d5  call    cs:__imp_?SetSacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetSacl(CNtAcl *)
0x18007f0db  test    eax, eax
0x18007f0dd  jnz     short loc_18007F13E
0x18007f0df  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18007f0e5  mov     ebx, 80041001h
0x18007f0ea  mov     edx, ebx
0x18007f0ec  mov     rcx, rax
0x18007f0ef  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18007f0f5  lea     rax, WPP_GLOBAL_Control
0x18007f0fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f103  cmp     rcx, rax
  ... truncated ...
```
