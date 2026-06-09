# UnionFs::Utils::AccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,ulong,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)

- ea: `0x140068770`
- end: `0x140069340`
- name: `?AccessCheck@Utils@UnionFs@@YAJUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@KAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z`
- size: `3024`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400414c8`
- `0x14006dfb0`

## callees

- `0x140001008`
- `0x140001c08`
- `0x140003a4c`
- `0x140003d00`
- `0x1400055d0`
- `0x140006168`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140068770`
- `0x14006ff9c`
- `0x14007498c`
- `0x140079c48`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x1400689d5`
- `ntoskrnl!SeShouldCheckForAccessRightsFromParent` at `0x1400689d5`
- `ntoskrnl!SeAppendPrivileges` at `0x1400688e7`
- `ntoskrnl!SeAppendPrivileges` at `0x140068ca4`
- `ntoskrnl!SeAppendPrivileges` at `0x1400688e7`
- `ntoskrnl!SeAppendPrivileges` at `0x140068ca4`
- `ntoskrnl!SeFreePrivileges` at `0x1400688f7`
- `ntoskrnl!SeFreePrivileges` at `0x140068aa7`
- `ntoskrnl!SeFreePrivileges` at `0x140068bc2`
- `ntoskrnl!SeFreePrivileges` at `0x140068cb4`
- `ntoskrnl!SeFreePrivileges` at `0x1400688f7`
- `ntoskrnl!SeFreePrivileges` at `0x140068aa7`
- `ntoskrnl!SeFreePrivileges` at `0x140068bc2`
- `ntoskrnl!SeFreePrivileges` at `0x140068cb4`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140068f7e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400690e7`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140068f7e`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x1400690e7`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14006887f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068a3a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068b55`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068c35`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14006887f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068a3a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068b55`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140068c35`
- `ntoskrnl!RtlGetAce` at `0x140069098`
- `ntoskrnl!RtlGetAce` at `0x140069098`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140068f5f`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140068f5f`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x140068812`
- `ntoskrnl!SeAdjustAccessStateForAccessConstraints` at `0x140068812`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140069047`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140069047`
- `ntoskrnl!IoFileObjectType` at `0x140068801`
- `ntoskrnl!IoFileObjectType` at `0x1400689c4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140068d1c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069307`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140068d1c`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140069307`
- `ntoskrnl!SeLockSubjectContext` at `0x140068865`
- `ntoskrnl!SeLockSubjectContext` at `0x140068865`

## string_xrefs

- `0x1400687dd`: `UnionFs::Utils::AccessCheck`
- `0x140068967`: `UnionFs::Utils::AccessCheck`
- `0x140068ae5`: `UnionFs::Utils::AccessCheck`
- `0x140068bf9`: `UnionFs::Utils::AccessCheck`
- `0x140068cf2`: `UnionFs::Utils::AccessCheck`
- `0x140068e4a`: `UnionFs::Utils::AccessCheck`
- `0x140068f1c`: `UnionFs::Utils::AccessCheck`
- `0x1400687ca`: `ORIGIN: Need SubjectSecurityContext in Cbd`
- `0x140068ada`: `PUSH: Requsting FILE_DELETE_CHILD`
- `0x14006895c`: `API: Check access of target`
- `0x140068ce7`: `PUSH: Re-check access of target`
- `0x140068bee`: `PUSH: Requsting FILE_LIST_DIRECTORY`
- `0x140068e7c`: `Access granted`
- `0x140069249`: `NULL DACL`
- `0x140069294`: `NO DACL`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::AccessCheck(__int128 *a1, void *a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rax
  bool v9; // zf
  struct _ACCESS_STATE *v11; // rdi
  int v12; // ebx
  __int64 v13; // rcx
  char v14; // si
  __int64 v15; // rax
  PSECURITY_SUBJECT_CONTEXT v16; // r13
  __int128 v17; // xmm1
  ACCESS_MASK PreviouslyGrantedAccess; // eax
  int v19; // edx
  char v20; // r8
  ACCESS_MASK v21; // ecx
  int v22; // r12d
  char v23; // si
  unsigned int v24; // r14d
  char v25; // r15
  unsigned int v26; // r13d
  int v27; // eax
  int v28; // eax
  int v29; // eax
  PSECURITY_SUBJECT_CONTEXT v30; // rsi
  __int64 v31; // rdx
  int v32; // r15d
  unsigned int v33; // ebx
  int v34; // eax
  __int64 v35; // rdx
  unsigned __int8 v36; // al
  int v37; // ecx
  __int128 v38; // xmm1
  __int64 v39; // xmm0_8
  char v40; // si
  unsigned int v41; // eax
  int v42; // ebx
  int v43; // eax
  __int64 v44; // rcx
  int v45; // r9d
  struct _ACL *v46; // rcx
  struct _UNICODE_STRING *v47; // rax
  int *v48; // r13
  int v49; // edi
  int v50; // esi
  PSECURITY_DESCRIPTOR v51; // rbx
  int v52; // r8d
  int v53; // r9d
  struct _UNICODE_STRING *p_UnicodeString; // rax
  __int64 v55; // rdx
  int v56; // r8d
  int v57; // r9d
  struct _ACL *v58; // rcx
  signed int v59; // ebx
  int v60; // r14d
  int v61; // r8d
  int v62; // r9d
  struct _UNICODE_STRING *v63; // rax
  int AceCount; // ecx
  int v65; // ecx
  __int64 *v66; // rdx
  const char *v67; // rax
  struct _UNICODE_STRING *v68; // rdx
  char *v69; // [rsp+28h] [rbp-E8h]
  unsigned __int8 DaclPresent; // [rsp+90h] [rbp-80h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+91h] [rbp-7Fh] BYREF
  _BYTE v72[6]; // [rsp+92h] [rbp-7Eh] BYREF
  int v73[2]; // [rsp+98h] [rbp-78h] BYREF
  int OriginalDesiredAccess; // [rsp+A0h] [rbp-70h] BYREF
  PSID Owner; // [rsp+A8h] [rbp-68h] BYREF
  PVOID Ace; // [rsp+B0h] [rbp-60h] BYREF
  const char *v77; // [rsp+B8h] [rbp-58h] BYREF
  const char *v78; // [rsp+C0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v79; // [rsp+C8h] [rbp-48h] BYREF
  PPRIVILEGE_SET v80; // [rsp+D8h] [rbp-38h]
  int RemainingDesiredAccess; // [rsp+E0h] [rbp-30h] BYREF
  ULONG Flags; // [rsp+E4h] [rbp-2Ch] BYREF
  int v83; // [rsp+E8h] [rbp-28h] BYREF
  int *v84; // [rsp+F0h] [rbp-20h]
  PSECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+F8h] [rbp-18h]
  PACL Dacl; // [rsp+100h] [rbp-10h] BYREF
  const char *v87; // [rsp+108h] [rbp-8h] BYREF
  const char *v88; // [rsp+110h] [rbp+0h] BYREF
  UnionFs *v89; // [rsp+118h] [rbp+8h]
  struct UnionFs::StackEventTracer *v90; // [rsp+120h] [rbp+10h]
  PPRIVILEGE_SET Privileges; // [rsp+128h] [rbp+18h]
  __int128 v92; // [rsp+130h] [rbp+20h] BYREF
  _OWORD v93[2]; // [rsp+140h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+160h] [rbp+50h]
  struct _UNICODE_STRING UnicodeString; // [rsp+168h] [rbp+58h] BYREF
  __int128 v96; // [rsp+180h] [rbp+70h] BYREF
  __int128 v97; // [rsp+190h] [rbp+80h]
  __int64 v98; // [rsp+1A0h] [rbp+90h]
  _BYTE v99[752]; // [rsp+1B0h] [rbp+A0h] BYREF

  v5 = *(_QWORD *)(a4 + 16);
  Ace = (PVOID)a4;
  SecurityDescriptor = a2;
  v9 = *(_BYTE *)(v5 + 4) == 0;
  v84 = (int *)a1;
  *(_QWORD *)v73 = a5;
  if ( !v9 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      a5,
      (struct UnionFs::StackEventTracer *)0x23200211621LL,
      (unsigned __int64)"UnionFs::Utils::AccessCheck",
      "ORIGIN: Need SubjectSecurityContext in Cbd",
      v69);
    return 3221225485LL;
  }
  v11 = *(struct _ACCESS_STATE **)(*(_QWORD *)(v5 + 24) + 8LL);
  SeAdjustAccessStateForAccessConstraints(IoFileObjectType, a2, v11);
  v12 = a3 & ~v11->PreviouslyGrantedAccess;
  if ( !v12 )
    return 0;
  v13 = *(_QWORD *)(a4 + 16);
  v14 = 1;
  LODWORD(Owner) = v12 & 0x2000000;
  v72[0] = (v12 & 0x2000000) != 0;
  if ( (*(_BYTE *)(v13 + 6) & 1) == 0 )
    v14 = *(_BYTE *)(a4 + 80);
  v15 = *(_QWORD *)(v13 + 24);
  v72[1] = v14;
  SubjectContext = (PSECURITY_SUBJECT_CONTEXT)(*(_QWORD *)(v15 + 8) + 32LL);
  v16 = SubjectContext;
  SeLockSubjectContext(SubjectContext);
  v89 = 0;
  v90 = 0;
  Privileges = 0;
  IoGetFileObjectGenericMapping();
  v17 = a1[1];
  PreviouslyGrantedAccess = v11->PreviouslyGrantedAccess;
  v92 = *a1;
  LODWORD(v69) = PreviouslyGrantedAccess;
  *(_QWORD *)&v93[1] = *((_QWORD *)a1 + 4);
  v93[0] = v17;
  OwnerDefaulted = UnionFs::Utils::PerformSeAccessCheck(&v92, SecurityDescriptor, SubjectContext);
  if ( OwnerDefaulted )
  {
    v19 = (int)v89;
    v20 = 0;
    v11->PreviouslyGrantedAccess |= (unsigned int)v89;
    v21 = v11->PreviouslyGrantedAccess;
    DaclPresent = 0;
    OriginalDesiredAccess = v19;
    v22 = v12 & ~(v19 | 0x2000000);
    v23 = 0;
    v24 = 0;
    if ( (v12 & 0x2000000) != 0 )
    {
      v23 = BYTE2(v21) & 1;
      if ( (v21 & 0x80u) != 0 )
      {
        v20 = 1;
        DaclPresent = 1;
      }
    }
    v11->RemainingDesiredAccess &= ~(v19 | 0x2000000);
    v25 = 0;
LABEL_12:
    if ( !(_DWORD)Owner || v23 && v20 )
      goto LABEL_69;
    goto LABEL_15;
  }
  v24 = HIDWORD(v89);
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)HIDWORD(v89),
    a5,
    v90,
    (unsigned __int64)"UnionFs::Utils::AccessCheck",
    "API: Check access of target",
    v69);
  v20 = 0;
  OriginalDesiredAccess = 0;
  v23 = 0;
  DaclPresent = 0;
  v25 = 0;
  v22 = v12;
  if ( (v12 & 0x10080) == 0 )
    goto LABEL_12;
LABEL_15:
  if ( *((_QWORD *)v84 + 1) )
  {
    if ( (unsigned __int8)SeShouldCheckForAccessRightsFromParent(IoFileObjectType, SecurityDescriptor, v11) )
    {
      v26 = 0;
      if ( (v22 & 0x10000) != 0 || (v27 = (int)Owner) != 0 && !v23 )
      {
        v28 = *v84;
        v92 = 0u;
        memset(v93, 0, 24);
        if ( (v28 & 2) != 0 )
        {
          v29 = v84[4];
          LODWORD(v92) = 1;
          DWORD1(v92) = v29;
        }
        *(_QWORD *)&v79.Length = 0;
        v79.Buffer = 0;
        v80 = 0;
        IoGetFileObjectGenericMapping();
        v30 = SubjectContext;
        v31 = *((_QWORD *)v84 + 1);
        v96 = v92;
        LODWORD(v69) = 0;
        v97 = v93[0];
        v98 = *(_QWORD *)&v93[1];
        v32 = v73[0];
        if ( (unsigned __int8)UnionFs::Utils::PerformSeAccessCheck(&v96, v31, SubjectContext) )
        {
          v26 = *(_DWORD *)&v79.Length & 0xFFFEFFBF | 0x10000;
          v22 &= ~0x10000u;
        }
        else
        {
          v24 = *(_DWORD *)(&v79.MaximumLength + 1);
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)*(unsigned int *)(&v79.MaximumLength + 1),
            v73[0],
            (struct UnionFs::StackEventTracer *)v79.Buffer,
            (unsigned __int64)"UnionFs::Utils::AccessCheck",
            "PUSH: Requsting FILE_DELETE_CHILD",
            v69);
        }
        v27 = (int)Owner;
      }
      else
      {
        v32 = v73[0];
        v30 = SubjectContext;
      }
      v33 = 0;
      if ( (v22 & 0x80u) != 0 || v27 && !DaclPresent )
      {
        v92 = 0u;
        memset(v93, 0, 24);
        if ( (*v84 & 2) != 0 )
        {
          v34 = v84[4];
          LODWORD(v92) = 1;
          DWORD1(v92) = v34;
        }
        *(_QWORD *)&v79.Length = 0;
        v79.Buffer = 0;
        v80 = 0;
        IoGetFileObjectGenericMapping();
        v35 = *((_QWORD *)v84 + 1);
        v96 = v92;
        LODWORD(v69) = 0;
        v97 = v93[0];
        v98 = *(_QWORD *)&v93[1];
        DaclPresent = UnionFs::Utils::PerformSeAccessCheck(&v96, v35, v30);
        if ( DaclPresent )
        {
          v33 = *(_DWORD *)&v79.Length & 0xFFFFFF7E | 0x80;
          v22 &= ~0x80u;
        }
        else
        {
          v24 = *(_DWORD *)(&v79.MaximumLength + 1);
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)*(unsigned int *)(&v79.MaximumLength + 1),
            v32,
            (struct UnionFs::StackEventTracer *)v79.Buffer,
            (unsigned __int64)"UnionFs::Utils::AccessCheck",
            "PUSH: Requsting FILE_LIST_DIRECTORY",
            v69);
        }
      }
      if ( v22 )
      {
        IoGetFileObjectGenericMapping();
        v38 = *((_OWORD *)v84 + 1);
        v96 = *(_OWORD *)v84;
        v39 = *((_QWORD *)v84 + 4);
        LODWORD(v69) = v11->PreviouslyGrantedAccess;
        v97 = v38;
        v98 = v39;
        v40 = UnionFs::Utils::PerformSeAccessCheck(&v96, SecurityDescriptor, v30);
        if ( Privileges )
        {
          SeAppendPrivileges(v11, Privileges);
          SeFreePrivileges(Privileges);
          Privileges = 0;
        }
        if ( v40 )
        {
          v37 = (int)v89;
          goto LABEL_56;
        }
        if ( v22 == 0x2000000 && (v33 || v26) )
        {
          v37 = 0;
          goto LABEL_56;
        }
        v24 = HIDWORD(v89);
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)HIDWORD(v89),
          v32,
          v90,
          (unsigned __int64)"UnionFs::Utils::AccessCheck",
          "PUSH: Re-check access of target",
          v69);
      }
      else
      {
        if ( v33 || v26 )
          v36 = 1;
        else
          v36 = OwnerDefaulted;
        if ( v36 )
        {
          v37 = OriginalDesiredAccess;
LABEL_56:
          v41 = v33;
          v25 = 1;
          v42 = v26 | v33;
          v43 = v26 | v41;
          v16 = SubjectContext;
          v11->PreviouslyGrantedAccess |= v37 | v43;
          v11->RemainingDesiredAccess &= ~(v37 | v42 | 0x2000000);
          goto LABEL_57;
        }
      }
      v16 = SubjectContext;
LABEL_51:
      if ( v16 && v16->PrimaryToken )
        SeUnlockSubjectContext(v16);
      return v24;
    }
    v25 = 0;
  }
LABEL_69:
  if ( !OwnerDefaulted )
    goto LABEL_51;
LABEL_57:
  v44 = *(_QWORD *)v73;
  **(_DWORD **)v73 = 0;
  *(_WORD *)(v44 + 548) = 0;
  if ( (unsigned int)dword_14009E178 <= 5
    || (qword_14009E188 & 0x10000) == 0
    || (qword_14009E190 & 0x10000) != qword_14009E190 )
  {
    goto LABEL_109;
  }
  v79 = 0;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v99, 0x680021175EuLL);
  UnionFs::Utils::GetUserSidString(Ace, &v79, v99);
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x10000) != 0
    && (qword_14009E190 & 0x10000) == qword_14009E190 )
  {
    v46 = (struct _ACL *)&FsTlEmptyUnicodeString;
    OriginalDesiredAccess = v11->OriginalDesiredAccess;
    LODWORD(Owner) = v11->PreviouslyGrantedAccess;
    RemainingDesiredAccess = v11->RemainingDesiredAccess;
    Flags = v11->Flags;
    v47 = &v79;
    if ( !v79.Buffer )
      v47 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
    v83 = v22;
    Ace = v47;
    v87 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
    OwnerDefaulted = 1;
    v73[0] = 5998;
    v77 = "UnionFs::Utils::AccessCheck";
    if ( *((_QWORD *)v84 + 4) )
      v46 = (struct _ACL *)(v84 + 6);
    v78 = "Access granted";
    Dacl = v46;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v46,
      (unsigned int)&word_14009A0D6,
      (unsigned int)&FsTlEmptyUnicodeString,
      v45,
      (__int64)&v78,
      (__int64)&v77,
      (__int64)&v87,
      (__int64)v73,
      (__int64)&Dacl,
      (__int64)&Ace,
      (__int64)&OwnerDefaulted,
      (__int64)v72,
      (__int64)&v83,
      (__int64)&Flags,
      (__int64)&RemainingDesiredAccess,
      (__int64)&Owner,
      (__int64)&OriginalDesiredAccess);
  }
  v48 = v84;
  v49 = (v25 != 0) + 1;
  OriginalDesiredAccess = v49;
  v50 = 0;
  do
  {
    v51 = SecurityDescriptor;
    if ( v50 )
      v51 = (PSECURITY_DESCRIPTOR)*((_QWORD *)v48 + 1);
    OwnerDefaulted = 0;
    Owner = 0;
    UnicodeString = 0;
    if ( RtlGetOwnerSecurityDescriptor(v51, &Owner, &OwnerDefaulted) >= 0
      && RtlConvertSidToUnicodeString(&UnicodeString, Owner, 1u) >= 0
      && (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x10000) != 0
      && (qword_14009E190 & 0x10000) == qword_14009E190 )
    {
      p_UnicodeString = &UnicodeString;
      v73[0] = 6026;
      if ( !UnicodeString.Buffer )
        p_UnicodeString = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
      v87 = "UnionFs::Utils::AccessCheck";
      v78 = (const char *)p_UnicodeString;
      v77 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
      Ace = "Owner";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (unsigned int)&FsTlEmptyUnicodeString,
        (unsigned int)byte_14009A001,
        v52,
        v53,
        (__int64)&Ace,
        (__int64)&v87,
        (__int64)&v77,
        (__int64)v73,
        (__int64)&v78);
    }
    Dacl = 0;
    DaclPresent = 0;
    if ( RtlGetDaclSecurityDescriptor(v51, &DaclPresent, &Dacl, &OwnerDefaulted) >= 0 )
    {
      if ( DaclPresent )
      {
        v58 = Dacl;
        if ( Dacl )
        {
          v59 = 0;
          if ( Dacl->AceCount )
          {
            do
            {
              Ace = 0;
              if ( RtlGetAce(v58, v59, &Ace) >= 0 )
              {
                v55 = *(unsigned __int8 *)Ace;
                if ( !*(_BYTE *)Ace || (_DWORD)v55 == 1 )
                {
                  v60 = *((_DWORD *)Ace + 1);
                  Owner = (char *)Ace + 8;
                  FsFltWil::Details::FreeUnicodeString(&UnicodeString, (struct _UNICODE_STRING *)v55);
                  UnicodeString = 0;
                  if ( RtlConvertSidToUnicodeString(&UnicodeString, Owner, 1u) >= 0 && (unsigned int)dword_14009E178 > 5 )
                  {
                    v55 = 0x10000;
                    if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
                    {
                      v63 = &UnicodeString;
                      v73[0] = v60;
                      if ( !UnicodeString.Buffer )
                        v63 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
                      v77 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
                      v78 = (const char *)v63;
                      v87 = "UnionFs::Utils::AccessCheck";
                      v72[0] = *(_BYTE *)Ace;
                      AceCount = Dacl->AceCount;
                      v88 = "DACL";
                      v83 = AceCount;
                      Flags = v59;
                      RemainingDesiredAccess = 6081;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
                        AceCount,
                        (unsigned int)&word_140099BCE,
                        v61,
                        v62,
                        (__int64)&v88,
                        (__int64)&v87,
                        (__int64)&v77,
                        (__int64)&RemainingDesiredAccess,
                        (__int64)&Flags,
                        (__int64)&v83,
                        (__int64)v72,
                        (__int64)v73,
                        (__int64)&v78);
                    }
                  }
                }
              }
              v58 = Dacl;
              ++v59;
            }
            while ( v59 < Dacl->AceCount );
            v49 = OriginalDesiredAccess;
            v48 = v84;
          }
        }
        else if ( (unsigned int)dword_14009E178 > 5 )
        {
          v65 = qword_14009E190;
          if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
          {
            v73[0] = 6091;
            v88 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
            v66 = qword_140099FC0;
            v67 = "NULL DACL";
LABEL_106:
            v77 = v67;
            v78 = "UnionFs::Utils::AccessCheck";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v65,
              (_DWORD)v66,
              v56,
              v57,
              (__int64)&v77,
              (__int64)&v78,
              (__int64)&v88,
              (__int64)v73);
          }
        }
      }
      else if ( (unsigned int)dword_14009E178 > 5 )
      {
        v65 = qword_14009E190;
        if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
        {
          v73[0] = 6097;
          v88 = "onecore\\base\\fs\\unionfs\\sys\\unionfsproc.cpp";
          v66 = (__int64 *)byte_140099B43;
          v67 = "NO DACL";
          goto LABEL_106;
        }
      }
    }
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, (struct _UNICODE_STRING *)v55);
    ++v50;
  }
  while ( v50 < v49 );
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v99);
  FsFltWil::Details::FreeUnicodeString(&v79, v68);
  v16 = SubjectContext;
LABEL_109:
  if ( v16 )
  {
    if ( v16->PrimaryToken )
      SeUnlockSubjectContext(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x140068770  mov     [rsp-8+arg_10], rbx
0x140068775  push    rbp
0x140068776  push    rsi
0x140068777  push    rdi
0x140068778  push    r12
0x14006877a  push    r13
0x14006877c  push    r14
0x14006877e  push    r15
0x140068780  lea     rbp, [rsp-3A0h]
0x140068788  sub     rsp, 4B0h
0x14006878f  mov     rax, cs:__security_cookie
0x140068796  xor     rax, rsp
0x140068799  mov     [rbp+3D0h+var_40], rax
0x1400687a0  mov     rax, [r9+10h]
0x1400687a4  mov     r13, r9
0x1400687a7  mov     r12, qword ptr [rbp+3D0h+arg_20]
0x1400687ae  mov     esi, r8d
0x1400687b1  mov     [rbp+3D0h+Ace], r9
0x1400687b5  mov     r14, rcx
0x1400687b8  mov     [rbp+3D0h+SecurityDescriptor], rdx
0x1400687bc  cmp     byte ptr [rax+4], 0
0x1400687c0  mov     [rbp+3D0h+var_3F0], rcx
0x1400687c4  mov     qword ptr [rbp+3D0h+var_448], r12
0x1400687c8  jz      short loc_1400687FD
0x1400687ca  lea     rax, aOriginNeedSubj; "ORIGIN: Need SubjectSecurityContext in "...
0x1400687d1  mov     ebx, 0C000000Dh
0x1400687d6  mov     ecx, ebx; this
0x1400687d8  mov     [rsp+4E0h+var_4C0], rax; char *
0x1400687dd  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x1400687e4  mov     r8, 23200211621h; struct UnionFs::StackEventTracer *
0x1400687ee  mov     rdx, r12; int
0x1400687f1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400687f6  mov     eax, ebx
0x1400687f8  jmp     loc_140069315
0x1400687fd  mov     rax, [rax+18h]
0x140068801  mov     rcx, cs:__imp_IoFileObjectType
0x140068808  mov     rdi, [rax+8]
0x14006880c  mov     rcx, [rcx]
0x14006880f  mov     r8, rdi
0x140068812  call    cs:__imp_SeAdjustAccessStateForAccessConstraints
0x140068819  nop     dword ptr [rax+rax+00h]
0x14006881e  mov     ebx, [rdi+14h]
0x140068821  not     ebx
0x140068823  and     ebx, esi
0x140068825  jz      loc_140069313
0x14006882b  mov     rcx, [r13+10h]
0x14006882f  mov     r15d, ebx
0x140068832  and     r15d, 2000000h
0x140068839  mov     sil, 1
0x14006883c  mov     dword ptr [rbp+3D0h+Owner], r15d
0x140068840  setnz   [rbp+3D0h+var_44E]
0x140068844  test    byte ptr [rcx+6], 1
0x140068848  jnz     short loc_14006884E
0x14006884a  mov     sil, [r13+50h]
0x14006884e  mov     rax, [rcx+18h]
0x140068852  mov     [rbp+3D0h+var_44D], sil
0x140068856  mov     r13, [rax+8]
0x14006885a  add     r13, 20h ; ' '
0x14006885e  mov     rcx, r13; SubjectContext
0x140068861  mov     [rbp+3D0h+SubjectContext], r13
0x140068865  call    cs:__imp_SeLockSubjectContext
0x14006886c  nop     dword ptr [rax+rax+00h]
0x140068871  xor     eax, eax
0x140068873  mov     [rbp+3D0h+var_3C8], rax
0x140068877  mov     [rbp+3D0h+var_3C0], rax
0x14006887b  mov     [rbp+3D0h+Privileges], rax
0x14006887f  call    cs:__imp_IoGetFileObjectGenericMapping
0x140068886  nop     dword ptr [rax+rax+00h]
0x14006888b  movups  xmm0, xmmword ptr [r14]
0x14006888f  mov     rdx, [rbp+3D0h+SecurityDescriptor]
0x140068893  lea     rcx, [rbp+3D0h+var_3C8]
0x140068897  movups  xmm1, xmmword ptr [r14+10h]
0x14006889c  mov     [rsp+4E0h+var_4A0], rcx
0x1400688a1  mov     r8, r13
0x1400688a4  mov     byte ptr [rsp+4E0h+var_4A8], sil
0x1400688a9  lea     rcx, [rbp+3D0h+var_3B0]
0x1400688ad  mov     [rsp+4E0h+var_4B0], rax
0x1400688b2  mov     eax, [rdi+14h]
0x1400688b5  movaps  [rbp+3D0h+var_3B0], xmm0
0x1400688b9  movsd   xmm0, qword ptr [r14+20h]
0x1400688bf  mov     dword ptr [rsp+4E0h+var_4B8], eax; char *
0x1400688c3  movsd   [rbp+3D0h+var_390], xmm0
0x1400688c8  mov     dword ptr [rsp+4E0h+var_4C0], ebx
0x1400688cc  movaps  [rbp+3D0h+var_3A0], xmm1
0x1400688d0  call    ?PerformSeAccessCheck@Utils@UnionFs@@YA_NUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@AEBU_SECURITY_SUBJECT_CONTEXT@@_NKKAEBU_GENERIC_MAPPING@@DAEAUPerformSeAccessCheckResults@12@@Z; UnionFs::Utils::PerformSeAccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,_SECURITY_SUBJECT_CONTEXT const &,bool,ulong,ulong,_GENERIC_MAPPING const &,char,UnionFs::Utils::PerformSeAccessCheckResults &)
0x1400688d5  mov     rdx, [rbp+3D0h+Privileges]; Privileges
0x1400688d9  mov     sil, al
0x1400688dc  mov     [rbp+3D0h+OwnerDefaulted], al
0x1400688df  test    rdx, rdx
0x1400688e2  jz      short loc_14006890B
0x1400688e4  mov     rcx, rdi; AccessState
0x1400688e7  call    cs:__imp_SeAppendPrivileges
0x1400688ee  nop     dword ptr [rax+rax+00h]
0x1400688f3  mov     rcx, [rbp+3D0h+Privileges]; Privileges
0x1400688f7  call    cs:__imp_SeFreePrivileges
0x1400688fe  nop     dword ptr [rax+rax+00h]
0x140068903  mov     [rbp+3D0h+Privileges], 0
0x14006890b  test    sil, sil
0x14006890e  jz      short loc_140068958
0x140068910  mov     edx, dword ptr [rbp+3D0h+var_3C8]
0x140068913  xor     r8b, r8b
0x140068916  or      [rdi+14h], edx
0x140068919  mov     eax, edx
0x14006891b  mov     ecx, [rdi+14h]
0x14006891e  bts     eax, 19h
0x140068922  not     eax
0x140068924  mov     [rbp+3D0h+DaclPresent], r8b
0x140068928  mov     r12d, eax
0x14006892b  mov     [rbp+3D0h+var_440], edx
0x14006892e  and     r12d, ebx
0x140068931  xor     sil, sil
0x140068934  xor     r14d, r14d
0x140068937  test    r15d, r15d
0x14006893a  jz      short loc_140068950
0x14006893c  mov     esi, ecx
0x14006893e  shr     esi, 10h
0x140068941  and     sil, 1
0x140068945  test    cl, cl
0x140068947  jns     short loc_140068950
0x140068949  mov     r8b, 1
0x14006894c  mov     [rbp+3D0h+DaclPresent], r8b
0x140068950  and     [rdi+10h], eax
0x140068953  xor     r15b, r15b
0x140068956  jmp     short loc_14006899D
0x140068958  mov     r14d, dword ptr [rbp+3D0h+var_3C8+4]
0x14006895c  lea     rax, aApiCheckAccess; "API: Check access of target"
0x140068963  mov     r8, [rbp+3D0h+var_3C0]; struct UnionFs::StackEventTracer *
0x140068967  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x14006896e  mov     ecx, r14d; this
0x140068971  mov     [rsp+4E0h+var_4C0], rax; char *
0x140068976  mov     rdx, r12; int
0x140068979  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006897e  xor     r8b, r8b
0x140068981  mov     [rbp+3D0h+var_440], 0
0x140068988  xor     sil, sil
0x14006898b  mov     [rbp+3D0h+DaclPresent], r8b
0x14006898f  xor     r15b, r15b
0x140068992  mov     r12d, ebx
0x140068995  test    ebx, 10080h
0x14006899b  jnz     short loc_1400689B5
0x14006899d  cmp     dword ptr [rbp+3D0h+Owner], 0
0x1400689a1  jz      loc_140068F0D
0x1400689a7  test    sil, sil
0x1400689aa  jz      short loc_1400689B5
0x1400689ac  test    r8b, r8b
0x1400689af  jnz     loc_140068F0D
0x1400689b5  mov     rbx, [rbp+3D0h+var_3F0]
0x1400689b9  cmp     qword ptr [rbx+8], 0
0x1400689be  jz      loc_140068F0D
0x1400689c4  mov     rcx, cs:__imp_IoFileObjectType
0x1400689cb  mov     r8, rdi
0x1400689ce  mov     rdx, [rbp+3D0h+SecurityDescriptor]
0x1400689d2  mov     rcx, [rcx]
0x1400689d5  call    cs:__imp_SeShouldCheckForAccessRightsFromParent
0x1400689dc  nop     dword ptr [rax+rax+00h]
0x1400689e1  test    al, al
0x1400689e3  jz      loc_140068F0A
0x1400689e9  xor     r13d, r13d
0x1400689ec  bt      r12d, 10h
0x1400689f1  jb      short loc_140068A07
0x1400689f3  mov     eax, dword ptr [rbp+3D0h+Owner]
0x1400689f6  test    eax, eax
0x1400689f8  jz      loc_140068AFE
0x1400689fe  test    sil, sil
0x140068a01  jnz     loc_140068AFE
0x140068a07  mov     eax, [rbx]
0x140068a09  xor     ecx, ecx
0x140068a0b  mov     qword ptr [rbp+3D0h+var_3B0], rcx
0x140068a0f  xorps   xmm0, xmm0
0x140068a12  mov     qword ptr [rbp+3D0h+var_3B0+8], rcx
0x140068a16  mov     qword ptr [rbp+3D0h+var_3A0], rcx
0x140068a1a  movups  [rbp+3D0h+var_3A0+8], xmm0
0x140068a1e  test    al, 2
0x140068a20  jz      short loc_140068A2E
0x140068a22  mov     eax, [rbx+10h]
0x140068a25  or      ecx, 1
0x140068a28  mov     dword ptr [rbp+3D0h+var_3B0], ecx
0x140068a2b  mov     dword ptr [rbp+3D0h+var_3B0+4], eax
0x140068a2e  mov     qword ptr [rbp+3D0h+var_418.Length], r13
0x140068a32  mov     [rbp+3D0h+var_418.Buffer], r13
0x140068a36  mov     [rbp+3D0h+var_408], r13
0x140068a3a  call    cs:__imp_IoGetFileObjectGenericMapping
0x140068a41  nop     dword ptr [rax+rax+00h]
0x140068a46  movups  xmm0, [rbp+3D0h+var_3B0]
0x140068a4a  mov     rsi, [rbp+3D0h+SubjectContext]
0x140068a4e  lea     rcx, [rbp+3D0h+var_418]
0x140068a52  movups  xmm1, [rbp+3D0h+var_3A0]
0x140068a56  mov     rdx, [rbx+8]
0x140068a5a  mov     r8, rsi
0x140068a5d  mov     [rsp+4E0h+var_4A0], rcx
0x140068a62  mov     cl, [rbp+3D0h+var_44D]
0x140068a65  mov     byte ptr [rsp+4E0h+var_4A8], cl
0x140068a69  lea     rcx, [rbp+3D0h+var_360]
0x140068a6d  mov     [rsp+4E0h+var_4B0], rax
0x140068a72  movaps  [rbp+3D0h+var_360], xmm0
0x140068a76  movsd   xmm0, [rbp+3D0h+var_390]
0x140068a7b  mov     dword ptr [rsp+4E0h+var_4B8], r13d; char *
0x140068a80  mov     dword ptr [rsp+4E0h+var_4C0], 40h ; '@'
0x140068a88  movaps  [rbp+3D0h+var_350], xmm1
0x140068a8f  movsd   [rbp+3D0h+var_340], xmm0
0x140068a97  call    ?PerformSeAccessCheck@Utils@UnionFs@@YA_NUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@AEBU_SECURITY_SUBJECT_CONTEXT@@_NKKAEBU_GENERIC_MAPPING@@DAEAUPerformSeAccessCheckResults@12@@Z; UnionFs::Utils::PerformSeAccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,_SECURITY_SUBJECT_CONTEXT const &,bool,ulong,ulong,_GENERIC_MAPPING const &,char,UnionFs::Utils::PerformSeAccessCheckResults &)
0x140068a9c  mov     rcx, [rbp+3D0h+var_408]; Privileges
0x140068aa0  mov     bl, al
0x140068aa2  test    rcx, rcx
0x140068aa5  jz      short loc_140068AB7
0x140068aa7  call    cs:__imp_SeFreePrivileges
0x140068aae  nop     dword ptr [rax+rax+00h]
0x140068ab3  mov     [rbp+3D0h+var_408], r13
0x140068ab7  mov     r15, qword ptr [rbp+3D0h+var_448]
0x140068abb  test    bl, bl
0x140068abd  jz      short loc_140068AD6
0x140068abf  mov     r13d, dword ptr [rbp+3D0h+var_418.Length]
0x140068ac3  and     r13d, 0FFFFFFBFh
0x140068ac7  bts     r13d, 10h
0x140068acc  btr     r12d, 10h
0x140068ad1  mov     eax, dword ptr [rbp+3D0h+Owner]
0x140068ad4  jmp     short loc_140068B06
0x140068ad6  mov     r14d, dword ptr [rbp+3D0h+var_418+4]
0x140068ada  lea     rax, aPushRequstingF_0; "PUSH: Requsting FILE_DELETE_CHILD"
0x140068ae1  mov     r8, [rbp+3D0h+var_418.Buffer]; struct UnionFs::StackEventTracer *
0x140068ae5  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x140068aec  mov     ecx, r14d; this
0x140068aef  mov     [rsp+4E0h+var_4C0], rax; char *
0x140068af4  mov     rdx, r15; int
0x140068af7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068afc  jmp     short loc_140068AD1
0x140068afe  mov     r15, qword ptr [rbp+3D0h+var_448]
0x140068b02  mov     rsi, [rbp+3D0h+SubjectContext]
0x140068b06  xor     ebx, ebx
0x140068b08  test    r12b, r12b
0x140068b0b  js      short loc_140068B1E
0x140068b0d  test    eax, eax
0x140068b0f  jz      loc_140068C10
0x140068b15  cmp     [rbp+3D0h+DaclPresent], bl
0x140068b18  jnz     loc_140068C10
0x140068b1e  mov     rdx, [rbp+3D0h+var_3F0]
0x140068b22  xor     ecx, ecx
0x140068b24  xorps   xmm0, xmm0
0x140068b27  mov     qword ptr [rbp+3D0h+var_3B0], rcx
0x140068b2b  mov     qword ptr [rbp+3D0h+var_3B0+8], rcx
0x140068b2f  mov     qword ptr [rbp+3D0h+var_3A0], rcx
0x140068b33  mov     eax, [rdx]
0x140068b35  movups  [rbp+3D0h+var_3A0+8], xmm0
0x140068b39  test    al, 2
0x140068b3b  jz      short loc_140068B49
0x140068b3d  mov     eax, [rdx+10h]
0x140068b40  or      ecx, 1
0x140068b43  mov     dword ptr [rbp+3D0h+var_3B0], ecx
0x140068b46  mov     dword ptr [rbp+3D0h+var_3B0+4], eax
0x140068b49  mov     qword ptr [rbp+3D0h+var_418.Length], rbx
0x140068b4d  mov     [rbp+3D0h+var_418.Buffer], rbx
0x140068b51  mov     [rbp+3D0h+var_408], rbx
0x140068b55  call    cs:__imp_IoGetFileObjectGenericMapping
0x140068b5c  nop     dword ptr [rax+rax+00h]
0x140068b61  movups  xmm0, [rbp+3D0h+var_3B0]
0x140068b65  mov     rdx, [rbp+3D0h+var_3F0]
0x140068b69  lea     rcx, [rbp+3D0h+var_418]
0x140068b6d  movups  xmm1, [rbp+3D0h+var_3A0]
0x140068b71  mov     [rsp+4E0h+var_4A0], rcx
0x140068b76  mov     r8, rsi
0x140068b79  mov     cl, [rbp+3D0h+var_44D]
0x140068b7c  mov     rdx, [rdx+8]
0x140068b80  mov     byte ptr [rsp+4E0h+var_4A8], cl
0x140068b84  lea     rcx, [rbp+3D0h+var_360]
0x140068b88  mov     [rsp+4E0h+var_4B0], rax
0x140068b8d  movaps  [rbp+3D0h+var_360], xmm0
0x140068b91  movsd   xmm0, [rbp+3D0h+var_390]
0x140068b96  mov     dword ptr [rsp+4E0h+var_4B8], ebx; char *
0x140068b9a  mov     dword ptr [rsp+4E0h+var_4C0], 1
0x140068ba2  movaps  [rbp+3D0h+var_350], xmm1
0x140068ba9  movsd   [rbp+3D0h+var_340], xmm0
0x140068bb1  call    ?PerformSeAccessCheck@Utils@UnionFs@@YA_NUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@AEBU_SECURITY_SUBJECT_CONTEXT@@_NKKAEBU_GENERIC_MAPPING@@DAEAUPerformSeAccessCheckResults@12@@Z; UnionFs::Utils::PerformSeAccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,_SECURITY_SUBJECT_CONTEXT const &,bool,ulong,ulong,_GENERIC_MAPPING const &,char,UnionFs::Utils::PerformSeAccessCheckResults &)
0x140068bb6  mov     rcx, [rbp+3D0h+var_408]; Privileges
0x140068bba  mov     [rbp+3D0h+DaclPresent], al
0x140068bbd  test    rcx, rcx
0x140068bc0  jz      short loc_140068BD5
0x140068bc2  call    cs:__imp_SeFreePrivileges
0x140068bc9  nop     dword ptr [rax+rax+00h]
0x140068bce  mov     al, [rbp+3D0h+DaclPresent]
0x140068bd1  mov     [rbp+3D0h+var_408], rbx
0x140068bd5  test    al, al
0x140068bd7  jz      short loc_140068BEA
0x140068bd9  mov     ebx, dword ptr [rbp+3D0h+var_418.Length]
0x140068bdc  and     ebx, 0FFFFFFFEh
0x140068bdf  bts     ebx, 7
0x140068be3  btr     r12d, 7
0x140068be8  jmp     short loc_140068C10
0x140068bea  mov     r14d, dword ptr [rbp+3D0h+var_418+4]
0x140068bee  lea     rax, aPushRequstingF; "PUSH: Requsting FILE_LIST_DIRECTORY"
0x140068bf5  mov     r8, [rbp+3D0h+var_418.Buffer]; struct UnionFs::StackEventTracer *
0x140068bf9  lea     r9, aUnionfsUtilsAc; "UnionFs::Utils::AccessCheck"
0x140068c00  mov     ecx, r14d; this
0x140068c03  mov     [rsp+4E0h+var_4C0], rax; char *
0x140068c08  mov     rdx, r15; int
0x140068c0b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140068c10  test    r12d, r12d
0x140068c13  jnz     short loc_140068C35
0x140068c15  test    ebx, ebx
0x140068c17  jnz     short loc_140068C1E
0x140068c19  test    r13d, r13d
  ... truncated ...
```
