# SamrSetInformationUser

- ea: `0x1800291c0`
- end: `0x18002b808`
- name: `SamrSetInformationUser`
- size: `9800`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, int, int *)`
- caller_count: `4`
- callee_count: `67`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180070e00`
- `0x180073370`
- `0x180073870`
- `0x1800a7630`

## callees

- `0x1800028e0`
- `0x180007ba0`
- `0x180008590`
- `0x1800096c0`
- `0x18000ae10`
- `0x18000e7f0`
- `0x180012a28`
- `0x1800198a0`
- `0x18001c1d0`
- `0x18001e430`
- `0x180020aa0`
- `0x1800213d0`
- `0x180022188`
- `0x180022678`
- `0x180024e74`
- `0x1800270e0`
- `0x180027250`
- `0x180027e24`
- `0x180027ef8`
- `0x180028040`
- `0x180028370`
- `0x1800290f0`
- `0x1800291c0`
- `0x18002c450`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x1800372ec`
- `0x180037394`
- `0x18003cd20`
- `0x180051930`
- `0x1800556ac`
- `0x1800616ec`
- `0x1800655e4`
- `0x180065b60`
- `0x180068fb0`
- `0x180074b5c`
- `0x180075490`
- `0x180075570`
- `0x180076bbc`
- `0x180076c04`
- `0x180076e8c`
- `0x180077738`
- `0x18007780c`
- `0x180077dc4`
- `0x18008ba3c`
- `0x18008e130`
- `0x18009eab8`
- `0x18009f0ec`
- `0x1800a008c`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18002b37c`
- `ntdll!RtlCompareUnicodeString` at `0x18002b37c`
- `ntdll!RtlInitializeBitMap` at `0x1800294ef`
- `ntdll!RtlInitializeBitMap` at `0x1800294ef`
- `ntdll!RtlFreeUnicodeString` at `0x18002b6b1`
- `ntdll!RtlFreeUnicodeString` at `0x18002b6b1`
- `ntdll!NtQuerySystemTime` at `0x180029fec`
- `ntdll!NtQuerySystemTime` at `0x18002a0bb`
- `ntdll!NtQuerySystemTime` at `0x18002a11f`
- `ntdll!NtQuerySystemTime` at `0x18002a1bc`
- `ntdll!NtQuerySystemTime` at `0x180029fec`
- `ntdll!NtQuerySystemTime` at `0x18002a0bb`
- `ntdll!NtQuerySystemTime` at `0x18002a11f`
- `ntdll!NtQuerySystemTime` at `0x18002a1bc`
- `ntdll!RtlFreeHeap` at `0x180029e3e`
- `ntdll!RtlFreeHeap` at `0x18002a452`
- `ntdll!RtlFreeHeap` at `0x180029e3e`
- `ntdll!RtlFreeHeap` at `0x18002a452`
- `ntdll!RtlClearAllBits` at `0x1800294f9`
- `ntdll!RtlClearAllBits` at `0x1800294f9`
- `ntdll!RtlLengthSid` at `0x18002a384`
- `ntdll!RtlLengthSid` at `0x18002a384`
- `ntdll!RtlInitUnicodeString` at `0x180029456`
- `ntdll!RtlInitUnicodeString` at `0x1800294b4`
- `ntdll!RtlInitUnicodeString` at `0x180029505`
- `ntdll!RtlInitUnicodeString` at `0x180029511`
- `ntdll!RtlInitUnicodeString` at `0x18002951d`
- `ntdll!RtlInitUnicodeString` at `0x180029529`
- `ntdll!RtlInitUnicodeString` at `0x18002b4cb`
- `ntdll!RtlInitUnicodeString` at `0x18002b4da`
- `ntdll!RtlInitUnicodeString` at `0x180029456`
- `ntdll!RtlInitUnicodeString` at `0x1800294b4`
- `ntdll!RtlInitUnicodeString` at `0x180029505`
- `ntdll!RtlInitUnicodeString` at `0x180029511`
- `ntdll!RtlInitUnicodeString` at `0x18002951d`
- `ntdll!RtlInitUnicodeString` at `0x180029529`
- `ntdll!RtlInitUnicodeString` at `0x18002b4cb`
- `ntdll!RtlInitUnicodeString` at `0x18002b4da`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002ac4b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18002ac4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b72f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b6dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b72f`
- `CRYPTBASE!SystemFunction029` at `0x18002a881`
- `CRYPTBASE!SystemFunction029` at `0x18002b083`
- `CRYPTBASE!SystemFunction029` at `0x18002a881`
- `CRYPTBASE!SystemFunction029` at `0x18002b083`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaintainPrimaryGroupIdChange` at `0x18002b33b`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtMaintainPrimaryGroupIdChange` at `0x18002b33b`
- `CRYPTSP!SystemFunction021` at `0x18002a8b6`
- `CRYPTSP!SystemFunction021` at `0x18002b0b3`
- `CRYPTSP!SystemFunction021` at `0x18002a8b6`
- `CRYPTSP!SystemFunction021` at `0x18002b0b3`
- `CRYPTSP!SystemFunction023` at `0x18002a90b`
- `CRYPTSP!SystemFunction023` at `0x18002b0e1`
- `CRYPTSP!SystemFunction023` at `0x18002a90b`
- `CRYPTSP!SystemFunction023` at `0x18002b0e1`

## pseudocode

```c
__int64 __fastcall SamrSetInformationUser(struct _SAMP_OBJECT *a1, int a2, int *a3)
{
  int v4; // r15d
  int v6; // ebx
  PUNICODE_STRING v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int IsLapsAutoManagedAccount; // eax
  HLOCAL v11; // rsi
  int UnicodeStringAttribute; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  HLOCAL *v15; // rax
  int *v16; // r14
  int v17; // ecx
  unsigned int v18; // esi
  int v19; // edx
  __int64 v20; // rdx
  char v21; // r13
  unsigned __int8 v22; // si
  char v23; // r12
  __int64 v24; // rdx
  unsigned int v25; // r14d
  int UserV1aFixed; // eax
  unsigned __int64 Buffer; // rcx
  __int64 v28; // r8
  char v29; // cl
  __int64 v30; // rdx
  unsigned int v31; // edx
  char v32; // al
  int v33; // eax
  __int64 v34; // r8
  bool v35; // zf
  unsigned __int8 v36; // r13
  char v37; // si
  char v38; // r14
  __int128 v39; // xmm1
  char v40; // bl
  unsigned __int8 v41; // dl
  char *v42; // rax
  __int64 v43; // rcx
  PUNICODE_STRING v44; // rcx
  char *v45; // rax
  __int64 v46; // rcx
  struct _UNICODE_STRING *v47; // r8
  unsigned __int8 v48; // al
  int v49; // r15d
  unsigned int v50; // edx
  int v51; // eax
  void *v52; // rcx
  int *v53; // rsi
  int v54; // eax
  bool v55; // sf
  char v56; // al
  int v57; // eax
  char v58; // al
  int v59; // esi
  __int64 v60; // rcx
  int *v61; // r15
  char v62; // al
  __int128 *v63; // r9
  char v64; // r14
  __int128 *v65; // rsi
  char v66; // dl
  char v67; // al
  int *v68; // r8
  _BYTE *v69; // r15
  int v70; // eax
  int *v71; // rcx
  int IsPwdSettingAttemptGranted; // eax
  struct _GUID *v73; // r9
  int v74; // eax
  PSECURITY_DESCRIPTOR v75; // rcx
  DWORD SecurityDescriptorLength; // eax
  int v77; // eax
  int *v78; // r15
  int v79; // ecx
  int v80; // eax
  unsigned int v81; // eax
  int v82; // ecx
  PUNICODE_STRING v83; // rcx
  __int64 v84; // rax
  struct _SAMP_ATTRIBUTES_INFORMATION near **v85; // r8
  unsigned int v86; // edx
  char v87; // r12
  char v88; // al
  int v89; // eax
  int v90; // ecx
  unsigned int v91; // esi
  unsigned int v92; // r14d
  int v93; // eax
  __int64 v94; // r9
  unsigned int v95; // ecx
  unsigned int v96; // esi
  char v97; // r14
  __int64 v98; // rcx
  struct _PSAMP_DEFINED_DOMAINS *v99; // rax
  unsigned int v100; // r12d
  unsigned int v101; // r14d
  __int64 v102; // rcx
  int v103; // eax
  UNICODE_STRING *p_String2; // rdx
  int v105; // ecx
  bool v106; // cf
  PWSTR v107; // rax
  __int64 Length; // rcx
  _BYTE *v109; // rcx
  __int64 v110; // rax
  __int64 v111; // rdx
  __int128 *v112; // rax
  __int64 v113; // rcx
  __int128 *v114; // rax
  int v116; // [rsp+20h] [rbp-E0h]
  int *v117; // [rsp+48h] [rbp-B8h]
  char v118; // [rsp+70h] [rbp-90h]
  int UserAccountSettings; // [rsp+74h] [rbp-8Ch] BYREF
  char v120; // [rsp+78h] [rbp-88h]
  char v121; // [rsp+79h] [rbp-87h]
  unsigned __int8 v122; // [rsp+7Ah] [rbp-86h]
  _BYTE v123[9]; // [rsp+7Bh] [rbp-85h] BYREF
  char v124; // [rsp+84h] [rbp-7Ch] BYREF
  char v125; // [rsp+85h] [rbp-7Bh]
  unsigned __int8 v126; // [rsp+86h] [rbp-7Ah] BYREF
  char v127; // [rsp+87h] [rbp-79h]
  unsigned int v128; // [rsp+88h] [rbp-78h]
  int *v129; // [rsp+90h] [rbp-70h]
  int v130; // [rsp+98h] [rbp-68h]
  int v131; // [rsp+9Ch] [rbp-64h] BYREF
  HLOCAL v132; // [rsp+A0h] [rbp-60h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v135; // [rsp+C0h] [rbp-40h]
  unsigned int v136; // [rsp+C4h] [rbp-3Ch]
  int *v137; // [rsp+C8h] [rbp-38h]
  UNICODE_STRING String2; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v140; // [rsp+F0h] [rbp-10h]
  int v141; // [rsp+F4h] [rbp-Ch] BYREF
  PVOID P[2]; // [rsp+F8h] [rbp-8h] BYREF
  HLOCAL hMem[2]; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v144; // [rsp+118h] [rbp+18h]
  unsigned int v145; // [rsp+11Ch] [rbp+1Ch]
  __int128 v146; // [rsp+120h] [rbp+20h] BYREF
  struct _UNICODE_STRING v147; // [rsp+130h] [rbp+30h] BYREF
  _RTL_BITMAP BitMapHeader; // [rsp+140h] [rbp+40h] BYREF
  struct _UNICODE_STRING v149; // [rsp+150h] [rbp+50h] BYREF
  struct _UNICODE_STRING v150; // [rsp+160h] [rbp+60h] BYREF
  __int128 v151; // [rsp+170h] [rbp+70h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+180h] [rbp+80h] BYREF
  __int128 Buf2; // [rsp+190h] [rbp+90h] BYREF
  _DWORD v154[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  UNICODE_STRING v155; // [rsp+1A8h] [rbp+A8h]
  struct _UNICODE_STRING v156; // [rsp+1B8h] [rbp+B8h]
  struct _UNICODE_STRING v157; // [rsp+1C8h] [rbp+C8h]
  _DWORD v158[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  UNICODE_STRING v159; // [rsp+1E8h] [rbp+E8h]
  struct _UNICODE_STRING v160; // [rsp+1F8h] [rbp+F8h] BYREF
  struct _UNICODE_STRING v161; // [rsp+208h] [rbp+108h] BYREF
  char v162[8]; // [rsp+220h] [rbp+120h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+228h] [rbp+128h] BYREF
  union _LARGE_INTEGER v164; // [rsp+230h] [rbp+130h] BYREF
  __int64 v165; // [rsp+238h] [rbp+138h] BYREF
  __int64 v166; // [rsp+240h] [rbp+140h]
  __int64 v167; // [rsp+248h] [rbp+148h]
  unsigned int v168; // [rsp+250h] [rbp+150h]
  unsigned int v169; // [rsp+254h] [rbp+154h]
  unsigned int v170; // [rsp+258h] [rbp+158h]
  __int16 v171; // [rsp+25Ch] [rbp+15Ch]
  __int16 v172; // [rsp+25Eh] [rbp+15Eh]
  __int16 v173; // [rsp+260h] [rbp+160h]
  __int16 v174; // [rsp+262h] [rbp+162h]
  __int128 v175; // [rsp+270h] [rbp+170h] BYREF
  __int128 v176; // [rsp+280h] [rbp+180h] BYREF
  __int128 v177; // [rsp+290h] [rbp+190h] BYREF
  struct _DOMAIN_PASSWORD_INFORMATION v178[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v179; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v180; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 Buf1; // [rsp+2F0h] [rbp+1F0h] BYREF
  ULONG BitMapBuffer[6]; // [rsp+300h] [rbp+200h] BYREF

  *(_DWORD *)&v123[5] = a2;
  v141 = 0;
  v4 = a2;
  memset_0(v162, 0, 0x50u);
  v123[2] = 0;
  *(_WORD *)v123 = 0;
  String1 = 0;
  v123[4] = 0;
  *(_OWORD *)P = 0;
  v126 = 0;
  v150 = 0;
  v131 = 0;
  String2 = 0;
  v132 = 0;
  v149 = 0;
  v177 = 0;
  v176 = 0;
  v175 = 0;
  UnicodeString = 0;
  v146 = 0;
  memset(v178, 0, sizeof(v178));
  *(_OWORD *)hMem = 0;
  Buf1 = 0;
  Buf2 = 0;
  BitMapHeader = 0;
  v147 = 0;
  DestinationString = 0;
  v144 = SampClientRevisionFromHandle(a1);
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
    WPP_SF_qD(WPP_GLOBAL_Control[3].Buffer, 81, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, a1, v4);
  v6 = SampAcquireWriteLock(a1);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v8 = 82;
LABEL_611:
      v9 = (unsigned int)v6;
      goto LABEL_612;
    }
    return (unsigned int)v6;
  }
  UserAccountSettings = SampLookupContextEx(a1, 0, 0, 4, &v141);
  v6 = UserAccountSettings;
  if ( UserAccountSettings < 0 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control[3].Buffer, 83, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, a1);
    SampReleaseWriteLock(0);
    v7 = WPP_GLOBAL_Control;
    v6 = -1073741816;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v8 = 84;
      v9 = 3221225480LL;
LABEL_612:
      WPP_SF_Dd(v7[3].Buffer, v8, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v9, v6);
      return (unsigned int)v6;
    }
    return (unsigned int)v6;
  }
  SampDeReferenceContext(a1, 0);
  SampReleaseWriteLock(0);
  SampTraceEvent(1);
  if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
    goto LABEL_25;
  IsLapsAutoManagedAccount = SampIsLapsAutoManagedAccount(a1, &v131);
  UserAccountSettings = IsLapsAutoManagedAccount;
  v6 = IsLapsAutoManagedAccount;
  if ( IsLapsAutoManagedAccount < 0 )
  {
    if ( IsLapsAutoManagedAccount != -1073741724 )
    {
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control[3].Buffer,
          86,
          WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
          (unsigned int)IsLapsAutoManagedAccount);
      goto LABEL_603;
    }
    v6 = 0;
    UserAccountSettings = 0;
LABEL_25:
    if ( (unsigned int)(v4 - 23) <= 3 )
    {
      RtlInitUnicodeString(&DestinationString, L"SamrSetInformationUser");
      v147 = 0;
      UnicodeStringAttribute = SampGetUnicodeStringAttribute(a1);
      UserAccountSettings = UnicodeStringAttribute;
      v6 = UnicodeStringAttribute;
      if ( UnicodeStringAttribute < 0 )
      {
        if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control[3].Buffer,
            87,
            WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
            a1,
            UnicodeStringAttribute);
        }
        RtlInitUnicodeString(&v147, L"Could not get account name");
        v6 = 0;
        UserAccountSettings = 0;
      }
      SampLogLegacyRpcMethodAuditEvent(&DestinationString, &v147);
    }
    UnicodeString.Buffer = 0;
    UnicodeString.Length = 0;
    *((_QWORD *)&v146 + 1) = 0;
    RtlInitializeBitMap(&BitMapHeader, BitMapBuffer, 0x8Cu);
    RtlClearAllBits(&BitMapHeader);
    RtlInitUnicodeString(&String1, 0);
    RtlInitUnicodeString(&String2, 0);
    RtlInitUnicodeString(&v149, 0);
    RtlInitUnicodeString(&v150, 0);
    v14 = 16;
    v15 = hMem;
    do
    {
      *(_BYTE *)v15 = 0;
      v15 = (HLOCAL *)((char *)v15 + 1);
      --v14;
    }
    while ( v14 );
    if ( a3 )
    {
      v129 = 0;
      v16 = 0;
      v128 = 7;
      if ( v4 <= 17 )
      {
        if ( v4 == 17 )
          goto LABEL_46;
        if ( v4 <= 9 )
        {
          if ( v4 == 9 )
            goto LABEL_46;
          if ( v4 == 1 )
            goto LABEL_58;
          if ( v4 != 2 )
          {
            if ( v4 != 3 )
            {
              if ( v4 == 4 )
                goto LABEL_46;
              if ( v4 != 5 )
              {
                if ( v4 == 6 )
                  goto LABEL_46;
                v17 = v4 - 7;
                if ( v4 == 7 )
                  goto LABEL_46;
                goto LABEL_57;
              }
            }
LABEL_58:
            v6 = -1073741821;
            goto LABEL_603;
          }
          v18 = 4;
LABEL_68:
          v136 = *((_DWORD *)a1 + 62);
          if ( v4 == 21 && *((_BYTE *)a1 + 326) )
          {
            v16[71] &= 0xB000000u;
            v18 = 128;
          }
          if ( (*((_BYTE *)a1 + 28) & 1) != 0 && (*((_BYTE *)a1 + 192) & 2) != 0 && v4 == 19 )
          {
            v127 = 0;
            _InterlockedAdd((volatile signed __int32 *)a1 + 36, 1u);
            goto LABEL_104;
          }
          v6 = SampAcquireWriteLock(a1);
          if ( v6 >= 0 )
          {
            v127 = 1;
            if ( v16 )
              v20 = (unsigned int)v16[71];
            else
              v20 = 0;
            SampGetRequestedAttributesForUser((unsigned int)v4, v20, &BitMapHeader);
            v6 = SampLookupContextEx(
                   a1,
                   v18,
                   (unsigned __int64)&BitMapHeader & -(__int64)((*((_DWORD *)a1 + 48) & 2) != 0),
                   4,
                   &v141);
            UserAccountSettings = v6;
LABEL_104:
            v137 = 0;
            v122 = 0;
            v21 = 1;
            v135 = 0;
            v118 = 0;
            LOBYTE(v130) = 0;
            v120 = 1;
            v123[3] = 0;
            v121 = 0;
            v131 = 0;
            if ( v6 < 0 )
            {
              v22 = 0;
              v23 = 0;
              goto LABEL_552;
            }
            LOBYTE(v13) = (*((_BYTE *)a1 + 20) & 0x20) != 0;
            UserAccountSettings = SampValidateUserInfoBuffer(a3, (unsigned int)v4, v13);
            v6 = UserAccountSettings;
            if ( UserAccountSettings < 0 )
            {
              SampDeReferenceContext(a1, 0);
              v22 = v122;
              v23 = v122;
              goto LABEL_552;
            }
            v24 = 1360LL * *((unsigned int *)a1 + 50);
            v131 = *((_DWORD *)a1 + 62);
            if ( ((unsigned int)(v4 - 23) <= 3 || (unsigned int)(v4 - 31) <= 1)
              && (*((_BYTE *)SampDefinedDomains + v24 + 572) & 4) != 0 )
            {
              v6 = -1073610718;
              v23 = 0;
              UserAccountSettings = -1073610718;
LABEL_154:
              SampDeReferenceContext(a1, 0);
              v4 = *(_DWORD *)&v123[5];
              v22 = v122;
              goto LABEL_552;
            }
            if ( v4 > 21 )
            {
              if ( v4 != 22 && v4 != 23 && v4 != 25 && v4 != 32 )
              {
LABEL_125:
                if ( v4 > 22 )
                {
                  if ( v4 != 23 )
                  {
                    if ( v4 == 24 )
                      goto LABEL_148;
                    if ( v4 != 25 )
                    {
                      if ( v4 == 26 || v4 == 28 || v4 == 30 || v4 == 31 )
                        goto LABEL_148;
                      if ( v4 != 32 )
                        goto LABEL_149;
                    }
                  }
                }
                else if ( v4 != 22 )
                {
LABEL_127:
                  if ( v4 == 2 || v4 == 9 || v4 == 15 || v4 == 16 || v4 == 17 || v4 == 18 || v4 == 19 )
                    goto LABEL_148;
                  if ( v4 != 21 )
                    goto LABEL_149;
                }
                if ( !v18 )
                {
                  if ( (*((_BYTE *)a1 + 20) & 0x20) == 0 )
                    v6 = -1073741790;
                  UserAccountSettings = v6;
                }
LABEL_148:
                if ( v6 < 0 )
                {
LABEL_153:
                  v23 = v118;
                  goto LABEL_154;
                }
LABEL_149:
                v25 = *(_DWORD *)((char *)SampDefinedDomains + v24 + 1304);
                v145 = v25;
                UserV1aFixed = SampRetrieveUserV1aFixed(a1, v162, SampDefinedDomains, 0);
                v28 = 0;
                UserAccountSettings = UserV1aFixed;
                v6 = UserV1aFixed;
                if ( UserV1aFixed < 0 )
                {
                  v140 = 0;
                }
                else
                {
                  v29 = *((_BYTE *)a1 + 20) >> 5;
                  v135 = v170;
                  if ( (((v170 & 0x40) != 0) & (unsigned __int8)~v29) != 0 )
                  {
                    v6 = -1073741790;
LABEL_152:
                    UserAccountSettings = v6;
                    goto LABEL_153;
                  }
                  v140 = v169;
                }
                v30 = (unsigned int)UserV1aFixed;
                if ( UserV1aFixed < 0 )
                  goto LABEL_153;
                v125 = 0;
                if ( v4 <= 18 )
                {
                  if ( v4 != 18 )
                  {
                    if ( v4 <= 11 )
                    {
                      if ( v4 == 11 )
                      {
                        v31 = 8;
                        goto LABEL_199;
                      }
                      if ( v4 == 2 )
                      {
                        v171 = *((_WORD *)a3 + 16);
                        v172 = *((_WORD *)a3 + 17);
                        UserAccountSettings = SampReplaceUserV1aFixed(a1, v162);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_527;
                        v31 = 4;
                        goto LABEL_199;
                      }
                      if ( v4 == 4 )
                      {
                        v33 = SampReplaceUserLogonHours(a1, a3);
LABEL_502:
                        v6 = v33;
                        UserAccountSettings = v33;
                        goto LABEL_527;
                      }
                      if ( v4 == 6 )
                      {
                        UserAccountSettings = SampSetUnicodeStringAttribute(a1, 2u);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_527;
                      }
                      else if ( v4 != 7 )
                      {
                        if ( v4 == 8 )
                        {
                          v31 = 2;
                          goto LABEL_199;
                        }
                        if ( v4 != 9 )
                        {
                          if ( v4 == 10 )
                          {
                            UserAccountSettings = SampSetUnicodeStringAttribute(a1, 6u);
                            v6 = UserAccountSettings;
                            if ( UserAccountSettings >= 0 )
                            {
                              v31 = 7;
LABEL_199:
                              v33 = SampSetUnicodeStringAttribute(a1, v31);
                              goto LABEL_502;
                            }
                          }
LABEL_527:
                          if ( v6 >= 0 )
                            goto LABEL_528;
LABEL_409:
                          v23 = v118;
                          goto LABEL_410;
                        }
                        if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                        {
                          if ( (v170 & 0x100000) != 0 && v169 == 521 )
                          {
                            v6 = *a3 != 521 ? 0xC00002D0 : 0;
                            goto LABEL_319;
                          }
                          if ( (v170 & 0x100) != 0 && v169 == 516 )
                          {
                            if ( (*((char *)a1 + 20) < 0 || *a3 != 513) && *a3 != 516 )
                            {
                              v6 = -1073741104;
                              goto LABEL_152;
                            }
LABEL_528:
                            v6 = SampGetUnicodeStringAttribute(a1);
                            UserAccountSettings = v6;
                            if ( v6 < 0 || String1.Buffer )
                            {
                              v89 = v6;
                              v90 = v6;
                            }
                            else
                            {
                              v89 = SampDuplicateUnicodeString(&String1, &String2);
                              v6 = v89;
                              UserAccountSettings = v89;
                              v90 = v89;
                            }
                            v23 = v118;
                            if ( v118 && v90 >= 0 )
                            {
                              UserAccountSettings = SampGetUnicodeStringAttribute(a1);
                              v6 = UserAccountSettings;
                              if ( UserAccountSettings < 0 )
                                goto LABEL_410;
                              v89 = SampGetUnicodeStringAttribute(a1);
                              v6 = v89;
                              UserAccountSettings = v89;
                            }
                            if ( v89 >= 0 )
                            {
                              v91 = v169;
                              v92 = v140;
                              if ( v169 == v140 || (*((_BYTE *)a1 + 192) & 2) == 0 )
                                goto LABEL_545;
                              v93 = SampShouldCallNtdsaApiSet();
                              v6 = v93;
                              if ( v93 == -1073741637 )
                              {
                                v6 = 0;
                              }
                              else if ( v93 >= 0 )
                              {
                                LOBYTE(v94) = v123[0];
                                v6 = NtdsaExtMaintainPrimaryGroupIdChange(a1, v91, v92, v94);
                              }
                              UserAccountSettings = v6;
                              if ( v6 >= 0 )
                              {
LABEL_545:
                                if ( SampSuccessAccountAuditingEnabled == 1 && v21 )
                                {
                                  if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
                                    SampAuditAccountNameChange(a1, &String2, &String1);
                                  v95 = v170;
                                  v96 = v135;
                                  if ( (((unsigned __int8)v135 ^ (unsigned __int8)v170) & 1) != 0 )
                                  {
                                    SampAuditAccountEnableDisableChange(a1, v170, v135, &String2);
                                    v95 = v170;
                                  }
                                  SampAuditUserChange(a1, (unsigned int)v4, &String2, (char *)a1 + 248, v96, v95, 0, 0);
                                }
                              }
                            }
LABEL_410:
                            if ( !v125 )
                              goto LABEL_416;
                            goto LABEL_411;
                          }
                          if ( (v170 & 0x40) != 0 && (*((_BYTE *)a1 + 20) & 0x20) != 0 )
                          {
                            if ( *a3 != 513 && (unsigned int)(*a3 - 528) >= 2 )
                            {
                              v6 = -1073741720;
                              goto LABEL_152;
                            }
                            v169 = *a3;
                            UserAccountSettings = SampReplaceUserV1aFixed(a1, v162);
                            v6 = UserAccountSettings;
                            if ( UserAccountSettings < 0 )
                              goto LABEL_153;
                            goto LABEL_527;
                          }
                        }
                        v6 = SampAssignPrimaryGroup(a1);
                        UserAccountSettings = v6;
                        if ( v6 < 0 )
                        {
                          if ( *a3 != 513 || (v170 & 0x1C0) == 0 )
                            goto LABEL_527;
                          v6 = 0;
LABEL_319:
                          UserAccountSettings = v6;
                          goto LABEL_527;
                        }
                        v169 = *a3;
                        v123[0] = 1;
LABEL_215:
                        v33 = SampReplaceUserV1aFixed(a1, v162);
                        goto LABEL_502;
                      }
                      v6 = SampChangeUserAccountName(a1);
                      UserAccountSettings = v6;
                      v32 = *((_BYTE *)a1 + 28);
                      v137 = a3;
                      v123[3] = (v32 & 2) != 0;
                      *((_BYTE *)a1 + 28) = v32 & 0xFD;
                      goto LABEL_527;
                    }
                    switch ( v4 )
                    {
                      case 12:
                        v31 = 9;
                        goto LABEL_199;
                      case 13:
                        v31 = 3;
                        goto LABEL_199;
                      case 14:
                        if ( !*(_WORD *)a3 || *((_QWORD *)a3 + 1) )
                        {
                          UserAccountSettings = SampConvertUiListToApiList(a3, P);
                          v6 = UserAccountSettings;
                          if ( UserAccountSettings < 0 )
                            goto LABEL_153;
                          v6 = SampSetUnicodeStringAttribute(a1, 0xAu);
                          UserAccountSettings = v6;
                          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
                        }
                        else
                        {
                          v6 = -1073741811;
                          UserAccountSettings = -1073741811;
                        }
                        goto LABEL_527;
                    }
                    if ( v4 != 15 )
                    {
                      if ( v4 == 16 )
                      {
                        UserAccountSettings = SampGetUserAccountSettings(a1, v178);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_527;
                        SampUpdateComputedUserAccountControlBits(a1);
                        UserAccountSettings = SampSetUserAccountControl(
                                                a1,
                                                v178,
                                                (__int64)&v123[4],
                                                (__int64)&v123[2],
                                                (__int64)v123);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_527;
                        if ( v123[2] )
                          SampGetUnicodeStringAttribute(a1);
                      }
                      else
                      {
                        if ( (*((_BYTE *)a1 + 20) & 0x20) == 0 && *((_DWORD *)a1 + 62) == 500 )
                        {
                          pSecurityDescriptor = (PSECURITY_DESCRIPTOR)*((_QWORD *)v129 + 3);
                          if ( pSecurityDescriptor )
                          {
                            v6 = -1073741532;
                            goto LABEL_152;
                          }
                        }
                        v166 = *(_QWORD *)a3;
                      }
                      goto LABEL_215;
                    }
LABEL_216:
                    v6 = -1073741821;
                    goto LABEL_152;
                  }
                  goto LABEL_231;
                }
                if ( v4 <= 25 )
                {
                  if ( v4 == 25 )
                    goto LABEL_320;
                  if ( v4 != 19 )
                  {
                    if ( v4 == 20 )
                    {
                      v31 = 5;
                      goto LABEL_199;
                    }
                    Buffer = (unsigned int)(v4 - 21);
                    if ( v4 != 21 )
                    {
                      Buffer = (unsigned int)(v4 - 22);
                      if ( v4 != 22 )
                      {
                        Buffer = (unsigned int)(v4 - 23);
                        if ( v4 != 23 )
                          goto LABEL_231;
                      }
                    }
LABEL_320:
                    v53 = v129;
                    if ( (v129[71] & 0x400) != 0 )
                    {
                      if ( *((_WORD *)v129 + 80) )
                      {
                        if ( !*((_QWORD *)v129 + 21) )
                          v6 = -1073741811;
                        UserAccountSettings = v6;
                      }
                      if ( v6 < 0 )
                        goto LABEL_153;
                      if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
                      {
                        *(_OWORD *)P = *((_OWORD *)v129 + 10);
                      }
                      else
                      {
                        v6 = SampConvertUiListToApiList(v129 + 40, P);
                        UserAccountSettings = v6;
                      }
                      if ( v6 < 0 )
                        goto LABEL_153;
                      v6 = SampSetUnicodeStringAttribute(a1, 0xAu);
                      UserAccountSettings = v6;
                      if ( P[1] != *((PVOID *)v129 + 21) )
                        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
                      v30 = (unsigned int)v6;
                      if ( v6 < 0 )
                        goto LABEL_153;
                    }
                    if ( (v129[71] & 1) != 0 )
                    {
                      v137 = v129 + 12;
                      v54 = SampChangeUserAccountName(a1);
                      Buffer = (unsigned __int64)String1.Buffer;
                      v55 = v54 < 0;
                      v6 = v54;
                      UserAccountSettings = v54;
                      v56 = *((_BYTE *)a1 + 28);
                      if ( v55 )
                        Buffer = 0;
                      String1.Buffer = (PWSTR)Buffer;
                      v30 = (unsigned int)v6;
                      *((_BYTE *)a1 + 28) = v56 & 0xFD;
                      v123[3] = (v56 & 2) != 0;
                      if ( v6 < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 2) != 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 2u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 0x40) != 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 6u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( *((char *)v53 + 284) < 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 7u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 0x100) != 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 8u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 0x200) != 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 9u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 0x10) != 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 3u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 0x20) != 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 4u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 0x200000) != 0 )
                    {
                      UserAccountSettings = SampSetUnicodeStringAttribute(a1, 5u);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    if ( (v53[71] & 0x2000) != 0 )
                    {
                      UserAccountSettings = SampReplaceUserLogonHours(a1, v53 + 72);
                      v6 = UserAccountSettings;
                      v30 = (unsigned int)UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_153;
                    }
                    v57 = v53[71];
                    if ( (v57 & 0x1000000) == 0 && (v57 & 0x2000000) == 0 )
                      goto LABEL_402;
                    v125 = 1;
                    v124 = 0;
                    v123[1] = 0;
                    v179 = 0;
                    v180 = 0;
                    UserAccountSettings = SampIsInternetAccount(a1);
                    v6 = UserAccountSettings;
                    if ( UserAccountSettings < 0 )
                      goto LABEL_498;
                    UserAccountSettings = SampGetUserAccountSettings(a1, v178);
                    v6 = UserAccountSettings;
                    if ( UserAccountSettings < 0 )
                      goto LABEL_498;
                    UserAccountSettings = SampGetUnicodeStringAttribute(a1);
                    v6 = UserAccountSettings;
                    if ( UserAccountSettings < 0 )
                      goto LABEL_498;
                    if ( *(_DWORD *)&v123[5] == 22
                      || *(_DWORD *)&v123[5] == 21 && (v58 = *((_BYTE *)a1 + 20), (v58 & 0x20) == 0) && v58 >= 0 )
                    {
                      if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
                      {
                        v70 = v53[71];
                        if ( (v70 & 0x2000000) != 0 )
                        {
                          v65 = (__int128 *)*((_QWORD *)v53 + 27);
                          v64 = *((_BYTE *)v129 + 312);
                        }
                        else
                        {
                          v65 = 0;
                          v64 = 0;
                        }
                        v35 = (v70 & 0x1000000) == 0;
                        v61 = v129;
                        v67 = v121;
                        if ( v35 )
                        {
                          v63 = 0;
                          v66 = 0;
                        }
                        else
                        {
                          v63 = (__int128 *)*((_QWORD *)v129 + 29);
                          v66 = *((_BYTE *)v129 + 313);
                        }
                      }
                      else
                      {
                        v175 = 0;
                        UserAccountSettings = SystemFunction029(a1, &v175);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_498;
                        if ( (v53[71] & 0x2000000) != 0 )
                        {
                          UserAccountSettings = SystemFunction021(*((_QWORD *)v53 + 27), &v175, &v180);
                          v6 = UserAccountSettings;
                          if ( UserAccountSettings < 0 )
                            goto LABEL_498;
                          v71 = v129;
                          v65 = &v180;
                          v64 = *((_BYTE *)v129 + 312);
                        }
                        else
                        {
                          v71 = v129;
                          v65 = 0;
                          v64 = 0;
                        }
                        if ( (v71[71] & 0x1000000) != 0 )
                        {
                          v61 = v129;
                          UserAccountSettings = SystemFunction023(*((_QWORD *)v129 + 29), &v175, &v179);
                          v6 = UserAccountSettings;
                          if ( UserAccountSettings < 0 )
                            goto LABEL_498;
                          v66 = *((_BYTE *)v129 + 313);
                          v63 = &v179;
                          v67 = v121;
                        }
                        else
                        {
                          v66 = 0;
                          v63 = 0;
                          v61 = v129;
                          v67 = 0;
                        }
                      }
                    }
                    else
                    {
                      v4 = *(_DWORD *)&v123[5];
                      v59 = v53[71];
                      if ( *(_DWORD *)&v123[5] <= 0x20u
                        && (v60 = 0x102800000LL, _bittest64(&v60, *(unsigned int *)&v123[5])) )
                      {
                        UserAccountSettings = SampDecryptPasswordWithSessionKey(
                                                a1,
                                                *(unsigned int *)&v123[5],
                                                a3,
                                                &UnicodeString);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_526;
                        v61 = v129;
                      }
                      else
                      {
                        v62 = *((_BYTE *)a1 + 20);
                        if ( (v62 & 0x20) == 0 && v62 >= 0 )
                        {
                          v23 = v118;
                          v6 = -1073741790;
                          UserAccountSettings = -1073741790;
                          goto LABEL_411;
                        }
                        v61 = v129;
                        UserAccountSettings = SampDuplicateUnicodeString(&UnicodeString, (PCUNICODE_STRING)v129 + 14);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_498;
                      }
                      UserAccountSettings = SampCalculateLmAndNtOwfPasswords(&UnicodeString, &v124, &v180, &v179);
                      v6 = UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_498;
                      v35 = (v59 & 0x100000) == 0;
                      v63 = &v179;
                      v64 = v124;
                      v65 = &v180;
                      v66 = 1;
                      v67 = 1;
                      v121 = 1;
                      if ( !v35 )
                      {
                        v68 = v61 + 70;
                        v69 = v61 + 70;
LABEL_394:
                        v117 = v68;
                        LOBYTE(v68) = v64;
                        LOBYTE(v116) = v66;
                        IsPwdSettingAttemptGranted = SampStoreUserPasswords(
                                                       a1,
                                                       v65,
                                                       v68,
                                                       v63,
                                                       v116,
                                                       1,
                                                       2,
                                                       v178,
                                                       (unsigned __int64)&UnicodeString & -(__int64)(v67 != 0),
                                                       v117,
                                                       hMem,
                                                       0);
                        UserAccountSettings = IsPwdSettingAttemptGranted;
                        v6 = IsPwdSettingAttemptGranted;
                        if ( IsPwdSettingAttemptGranted >= 0 )
                        {
                          IsPwdSettingAttemptGranted = SampIsPwdSettingAttemptGranted(a1, 0, v170, v73, &v126);
                          UserAccountSettings = IsPwdSettingAttemptGranted;
                          v6 = IsPwdSettingAttemptGranted;
                          if ( IsPwdSettingAttemptGranted >= 0 )
                          {
                            LOBYTE(Buffer) = v126 == 0;
                            IsPwdSettingAttemptGranted = SampComputePasswordExpired(Buffer, &v165);
                            v6 = IsPwdSettingAttemptGranted;
                            UserAccountSettings = IsPwdSettingAttemptGranted;
                          }
                        }
                        v30 = (unsigned int)IsPwdSettingAttemptGranted;
                        v53 = v129;
                        if ( (v170 & 0x40) != 0 || (v129[71] & 0x100000) != 0 && (*v69 & 0x40) != 0 )
                          LOBYTE(v130) = 1;
                        v128 = 8;
                        if ( IsPwdSettingAttemptGranted < 0 )
                          goto LABEL_409;
LABEL_402:
                        if ( (v53[71] & 0x8000000) == 0 )
                          goto LABEL_427;
                        if ( !*((_BYTE *)v53 + 314) )
                        {
                          UserAccountSettings = SampValidatePwdSettingAttempt(
                                                  (__int64)a1,
                                                  0,
                                                  v170,
                                                  &GUID_CONTROL_UnexpirePassword);
                          v6 = UserAccountSettings;
                          v30 = (unsigned int)UserAccountSettings;
                          if ( UserAccountSettings < 0 )
                            goto LABEL_409;
                        }
                        LOBYTE(Buffer) = *((_BYTE *)v53 + 314);
                        if ( (_BYTE)Buffer )
                        {
                          if ( *((_DWORD *)a1 + 212) )
                          {
                            v6 = -1073700725;
LABEL_408:
                            UserAccountSettings = v6;
                            goto LABEL_409;
                          }
                        }
                        else if ( SampHasNeverTime.QuadPart != v165 )
                        {
                          goto LABEL_426;
                        }
                        v6 = SampComputePasswordExpired(Buffer, &v165);
                        UserAccountSettings = v6;
                        v30 = (unsigned int)v6;
LABEL_426:
                        v122 = *((_BYTE *)v53 + 314);
                        if ( (int)v30 < 0 )
                          goto LABEL_409;
LABEL_427:
                        if ( (v53[71] & 0x4000000) != 0 )
                        {
                          UserAccountSettings = SampSetPrivateUserData(
                                                  a1,
                                                  *((unsigned __int16 *)v53 + 120),
                                                  *((void **)v53 + 31));
                          v6 = UserAccountSettings;
                          if ( UserAccountSettings < 0 )
                            goto LABEL_409;
                        }
                        if ( (v53[71] & 0x10000000) != 0 )
                        {
                          UserAccountSettings = SampValidatePassedSD(v53[64], *((PSECURITY_DESCRIPTOR *)v53 + 33));
                          v6 = UserAccountSettings;
                          if ( UserAccountSettings >= 0 )
                          {
                            if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                            {
                              v35 = (*((_BYTE *)a1 + 20) & 0x20) == 0;
                              pSecurityDescriptor = 0;
                              if ( v35 )
                                goto LABEL_438;
                              UserAccountSettings = SampExtConvertNt4SdToNt5SdDs(
                                                      *((_QWORD *)v53 + 33),
                                                      *((unsigned int *)a1 + 4),
                                                      a1,
                                                      &pSecurityDescriptor);
                              v6 = UserAccountSettings;
                              if ( UserAccountSettings < 0 )
                                goto LABEL_409;
                              v75 = pSecurityDescriptor;
                              if ( *((__int16 *)pSecurityDescriptor + 1) < 0 )
                              {
                                SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
                                v77 = SampSetAccessAttribute(
                                        a1,
                                        0,
                                        (unsigned __int8 *)pSecurityDescriptor,
                                        SecurityDescriptorLength);
                                v75 = pSecurityDescriptor;
                                v6 = v77;
                              }
                              else
                              {
                                v6 = -1073741811;
                              }
                              UserAccountSettings = v6;
                              LocalFree(v75);
                            }
                            else
                            {
                              v6 = SampSetAccessAttribute(a1, 0, *((unsigned __int8 **)v53 + 33), v53[64]);
                              UserAccountSettings = v6;
                            }
                          }
                        }
                        if ( v6 < 0 )
                          goto LABEL_409;
                        if ( (v53[71] & 0x100000) != 0
                          && (UserAccountSettings = SampGetUserAccountSettings(a1, v178),
                              v6 = UserAccountSettings,
                              UserAccountSettings >= 0) )
                        {
                          SampUpdateComputedUserAccountControlBits(a1);
                          v78 = v129;
                          UserAccountSettings = SampSetUserAccountControl(
                                                  a1,
                                                  v178,
                                                  (__int64)&v123[4],
                                                  (__int64)&v123[2],
                                                  (__int64)v123);
                          v6 = UserAccountSettings;
                          if ( UserAccountSettings >= 0 && v123[2] )
                            SampGetUnicodeStringAttribute(a1);
                        }
                        else
                        {
                          v78 = v129;
                        }
                        if ( v6 < 0 )
                          goto LABEL_409;
                        if ( (v78[71] & 0x800) != 0 )
                        {
                          if ( (*((_BYTE *)a1 + 20) & 0x20) == 0 )
                            goto LABEL_438;
                          SystemTime = *(union _LARGE_INTEGER *)v78;
                          UserAccountSettings = SampDsUpdateLastLogonTimeStamp(a1, SystemTime, v145);
                          v6 = UserAccountSettings;
                          if ( UserAccountSettings < 0 )
                            goto LABEL_498;
                        }
                        v79 = v78[71];
                        if ( (v79 & 0x1000) == 0 )
                        {
LABEL_454:
                          if ( (v79 & 0x40000) != 0 )
                          {
                            if ( *((_QWORD *)v78 + 2) )
                            {
                              UserAccountSettings = SampValidatePwdSettingAttempt(
                                                      (__int64)a1,
                                                      0,
                                                      v170,
                                                      &GUID_CONTROL_UnexpirePassword);
                              v6 = UserAccountSettings;
                              if ( UserAccountSettings < 0 )
                                goto LABEL_498;
                              v79 = v78[71];
                            }
                            v165 = *((_QWORD *)v78 + 2);
                          }
                          if ( (v79 & 0x80000) != 0 )
                            v166 = *((_QWORD *)v78 + 3);
                          if ( (v79 & 8) == 0 )
                            goto LABEL_483;
                          if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                          {
                            if ( (v170 & 0x100000) != 0 )
                            {
                              v80 = 521;
                              if ( v169 == 521 )
                              {
LABEL_465:
                                if ( v78[69] != v80 )
                                {
                                  v6 = -1073741104;
                                  goto LABEL_408;
                                }
                                goto LABEL_483;
                              }
                            }
                            if ( (v170 & 0x100) != 0 )
                            {
                              v80 = 516;
                              if ( v169 == 516 )
                              {
                                if ( *((char *)a1 + 20) < 0 || v78[69] != 513 )
                                  goto LABEL_465;
LABEL_483:
                                v82 = v78[71];
                                if ( (v82 & 0x400000) != 0 )
                                  v171 = *((_WORD *)v78 + 154);
                                if ( (v82 & 0x800000) != 0 )
                                  v172 = *((_WORD *)v78 + 155);
                                if ( (v82 & 0x4000) != 0 )
                                {
                                  v83 = WPP_GLOBAL_Control;
                                  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x800) != 0
                                    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
                                  {
                                    WPP_SF_Dd(
                                      WPP_GLOBAL_Control[3].Buffer,
                                      88,
                                      WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                                      v168,
                                      *((unsigned __int16 *)v78 + 152));
                                    v83 = WPP_GLOBAL_Control;
                                  }
                                  v173 = *((_WORD *)v78 + 152);
                                  if ( *(_DWORD *)&v123[5] == 22 )
                                  {
                                    v84 = *(_QWORD *)(a3 + 79);
                                    v167 = v84;
                                    if ( (*(_DWORD *)(&v83[4].MaximumLength + 1) & 0x800) != 0
                                      && HIBYTE(v83[4].Length) >= 4u )
                                    {
                                      WPP_SF_Di(v83[3].Buffer, 89, v28, v168, v84);
                                    }
                                  }
                                }
                                if ( (v78[71] & 0x8000) != 0 )
                                  v174 = *((_WORD *)v78 + 153);
                                v6 = SampReplaceUserV1aFixed(a1, v162);
                                UserAccountSettings = v6;
                                goto LABEL_498;
                              }
                            }
                            if ( (v170 & 0x40) != 0 && (*((_BYTE *)a1 + 20) & 0x20) != 0 )
                            {
                              if ( v78[69] != 513 && (unsigned int)(v78[69] - 528) >= 2 )
                              {
                                v6 = -1073741720;
                                goto LABEL_408;
                              }
                              v169 = v78[69];
                              UserAccountSettings = SampReplaceUserV1aFixed(a1, v162);
                              v6 = UserAccountSettings;
                              if ( UserAccountSettings < 0 )
                                goto LABEL_409;
                              goto LABEL_483;
                            }
                          }
                          v6 = SampAssignPrimaryGroup(a1);
                          UserAccountSettings = v6;
                          v81 = v78[69];
                          if ( v6 >= 0 )
                          {
                            v123[0] = 1;
                            v169 = v81;
                            goto LABEL_483;
                          }
                          if ( v81 == 513 && (v170 & 0x1C0) != 0 )
                            goto LABEL_483;
LABEL_498:
                          v4 = *(_DWORD *)&v123[5];
                          goto LABEL_526;
                        }
                        if ( (*((_BYTE *)a1 + 20) & 0x20) != 0 )
                        {
                          v164 = *(union _LARGE_INTEGER *)(v78 + 2);
                          goto LABEL_454;
                        }
LABEL_438:
                        v6 = -1073741790;
                        goto LABEL_408;
                      }
                    }
                    v68 = 0;
                    v69 = v61 + 70;
                    goto LABEL_394;
                  }
                  if ( (*((_BYTE *)a1 + 20) & 0x20) == 0 )
                    goto LABEL_216;
                  v120 = 0;
                  v21 = 0;
                  UserAccountSettings = SampGetUserAccountSettings(a1, v178);
                  v6 = UserAccountSettings;
                  if ( UserAccountSettings < 0 )
                    goto LABEL_527;
                  v40 = 0;
                  if ( (*a3 & 0x1000000) == 0 )
                  {
                    v44 = WPP_GLOBAL_Control;
LABEL_257:
                    if ( (*a3 & 0x20000000) != 0 )
                    {
                      if ( (*a3 & 0xDFFFFFFF) != 0 )
                      {
LABEL_259:
                        v6 = -1073741811;
                        goto LABEL_152;
                      }
                      if ( v174 )
                        --v174;
                      NtQuerySystemTime(&v164);
                      v44 = WPP_GLOBAL_Control;
                      v40 = 1;
                    }
                    if ( (*a3 & 0x40000000) == 0 )
                      goto LABEL_278;
                    if ( v173 && (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x800) != 0 && HIBYTE(v44[4].Length) >= 4u )
                      WPP_SF_d(v44[3].Buffer, 92, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v168);
                    v173 = 0;
                    NtQuerySystemTime(&SystemTime);
                    if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                    {
                      v45 = (char *)a1 + 272;
                      if ( *((_QWORD *)a1 + 34) )
                      {
                        v46 = 8;
                        do
                        {
                          *v45++ = 0;
                          --v46;
                        }
                        while ( v46 );
                        UserAccountSettings = SampExtUpdateLockoutTimeExDs(a1, 1u);
                        v6 = UserAccountSettings;
                        if ( UserAccountSettings < 0 )
                          goto LABEL_307;
                        v44 = WPP_GLOBAL_Control;
                        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x800) == 0
                          || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
                        {
                          goto LABEL_277;
                        }
                        WPP_SF_d(
                          WPP_GLOBAL_Control[3].Buffer,
                          93,
                          WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                          v168);
                      }
                    }
                    v44 = WPP_GLOBAL_Control;
LABEL_277:
                    v40 = 1;
LABEL_278:
                    if ( *a3 < 0 )
                    {
                      if ( (*a3 & 0x7FFFFFFF) != 0 )
                        goto LABEL_259;
                      NtQuerySystemTime(&v164);
                      v44 = WPP_GLOBAL_Control;
                      v40 = 1;
                    }
                    if ( (*a3 & 0x8000000) != 0 )
                    {
                      v47 = 0;
                      if ( (*a3 & 0x10000000) != 0 )
                        v47 = (struct _UNICODE_STRING *)(a3 + 6);
                      v48 = SampIncrementBadPasswordCount(
                              a1,
                              (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)v162,
                              v47,
                              (struct _SAMP_USER_ACCOUNT_SETTINGS *)v178);
                      v44 = WPP_GLOBAL_Control;
                      v49 = (unsigned __int8)v130;
                      if ( v48 )
                        v49 = 1;
                      v130 = v49;
                    }
                    else
                    {
                      LOBYTE(v49) = v130;
                    }
                    v50 = *a3;
                    if ( (*a3 & 2) != 0 )
                      SystemTime = *(union _LARGE_INTEGER *)(a3 + 1);
                    if ( (v50 & 1) != 0 )
                      v164 = *(union _LARGE_INTEGER *)(a3 + 3);
                    if ( (v50 & 4) != 0 )
                    {
                      if ( (*(_DWORD *)(&v44[4].MaximumLength + 1) & 0x800) != 0 && HIBYTE(v44[4].Length) >= 4u )
                      {
                        WPP_SF_Dd(
                          v44[3].Buffer,
                          94,
                          WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids,
                          v168,
                          *((unsigned __int16 *)a3 + 10));
                        v50 = *a3;
                      }
                      v173 = *((_WORD *)a3 + 10);
                    }
                    if ( (v50 & 8) != 0 )
                      v174 = *((_WORD *)a3 + 11);
                    if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                    {
                      if ( (v50 & 0x100000) != 0 )
                        Buf1 = *(_OWORD *)(*((_QWORD *)a1 + 22) + 8LL);
                      if ( v40 )
                        v51 = SampExtSuccessfulLogonSetDs(a1, v50, v25, (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)v162, 0);
                      else
                        v51 = SampExtFailedLogonSetDs(a1, v50, (struct _SAMP_V1_0A_FIXED_LENGTH_USER *)v162);
                    }
                    else
                    {
                      v51 = SampReplaceUserV1aFixed(a1, v162);
                    }
                    v6 = v51;
                    UserAccountSettings = v51;
                    v21 = v49;
                    v120 = v49;
LABEL_307:
                    v4 = *(_DWORD *)&v123[5];
                    goto LABEL_527;
                  }
                  if ( v173
                    && (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x800) != 0
                    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 90, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v168);
                  }
                  v173 = 0;
                  if ( v174 != -1 )
                    ++v174;
                  NtQuerySystemTime(&SystemTime);
                  if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                  {
                    v42 = (char *)a1 + 272;
                    if ( *((_QWORD *)a1 + 34) )
                    {
                      v43 = 8;
                      do
                      {
                        *v42++ = 0;
                        --v43;
                      }
                      while ( v43 );
                      UserAccountSettings = SampExtUpdateLockoutTimeExDs(a1, v41);
                      v6 = UserAccountSettings;
                      if ( UserAccountSettings < 0 )
                        goto LABEL_307;
                      v44 = WPP_GLOBAL_Control;
                      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x800) == 0
                        || HIBYTE(WPP_GLOBAL_Control[4].Length) < 4u )
                      {
                        goto LABEL_255;
                      }
                      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 91, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, v168);
                    }
                  }
                  v44 = WPP_GLOBAL_Control;
LABEL_255:
                  v40 = 1;
                  goto LABEL_257;
                }
                if ( v4 != 26 )
                {
                  switch ( v4 )
                  {
                    case 28:
                      v85 = &UserExtendedAttributesInformation;
                      v86 = 11;
                      break;
                    case 30:
                      *a3 = 0x4000000;
                      v85 = &UserExtendedAttributesResetData;
                      v86 = 1;
                      break;
                    case 31:
                      goto LABEL_231;
                    default:
                      Buffer = (unsigned int)(v4 - 32);
                      if ( v4 != 32 )
                      {
                        if ( v4 != 34 )
                          goto LABEL_527;
                        v151 = 0;
                        if ( (*((_BYTE *)a1 + 192) & 2) != 0 )
                        {
                          v6 = -1073741811;
                        }
                        else
                        {
                          v52 = *(void **)a3;
                          if ( *(_QWORD *)a3 )
                          {
                            *((_QWORD *)&v151 + 1) = *(_QWORD *)a3;
                            LODWORD(v151) = RtlLengthSid(v52);
                          }
                          v6 = SampSetExtendedAttribute(a1, 0x28u, &v151);
                        }
                        goto LABEL_319;
                      }
                      goto LABEL_320;
                  }
                  v33 = SampSetObjectExtendedAttributes(a1, v86, (struct _SAMP_ATTRIBUTES_INFORMATION *)v85, a3);
                  goto LABEL_502;
                }
LABEL_231:
                v125 = 1;
                UserAccountSettings = SampGetUserAccountSettings(a1, v178);
                v6 = UserAccountSettings;
                if ( UserAccountSettings < 0 )
                  goto LABEL_527;
                UserAccountSettings = SampGetUnicodeStringAttribute(a1);
                v6 = UserAccountSettings;
                if ( UserAccountSettings < 0 )
                  goto LABEL_527;
                if ( v4 != 18 )
                {
                  UserAccountSettings = SampDecryptPasswordWithSessionKey(a1, (unsigned int)v4, a3, &UnicodeString);
                  v6 = UserAccountSettings;
                  if ( UserAccountSettings < 0 )
                    goto LABEL_527;
                  UserAccountSettings = SampCalculateLmAndNtOwfPasswords(&UnicodeString, &v123[1], &v176, &v177);
                  v6 = UserAccountSettings;
                  if ( UserAccountSettings < 0 )
                    goto LABEL_527;
                  UserAccountSettings = SampGetUserAccountSettings(a1, v178);
                  v6 = UserAccountSettings;
                  if ( UserAccountSettings < 0 )
                    goto LABEL_527;
                  v38 = 1;
                  if ( v4 == 24 )
                  {
                    v36 = *((_BYTE *)a3 + 516);
                  }
                  else if ( v4 == 26 )
                  {
                    v36 = *((_BYTE *)a3 + 532);
                  }
                  else
                  {
                    v36 = *((_BYTE *)a3 + 104);
                  }
                  v87 = 1;
                  v121 = 1;
                  v37 = v123[1];
                  v122 = v36;
                  goto LABEL_518;
                }
                v35 = (*((_BYTE *)a1 + 20) & 0x20) == 0;
                v36 = *((_BYTE *)a3 + 34);
                v37 = *((_BYTE *)a3 + 33);
                v38 = *((_BYTE *)a3 + 32);
                v122 = v36;
                if ( !v35 )
                {
                  v39 = *(_OWORD *)a3;
                  v176 = *((_OWORD *)a3 + 1);
                  v177 = v39;
LABEL_508:
                  v87 = v121;
LABEL_518:
                  if ( !v36 )
                  {
                    v6 = SampValidatePwdSettingAttempt((__int64)a1, 0, v170, &GUID_CONTROL_UnexpirePassword);
                    UserAccountSettings = v6;
                  }
                  if ( v6 >= 0 )
                  {
                    LOBYTE(v34) = v37;
                    LOBYTE(v116) = v38;
                    UserAccountSettings = SampStoreUserPasswords(
                                            a1,
                                            &v176,
                                            v34,
                                            &v177,
                                            v116,
                                            1,
                                            2,
                                            v178,
                                            (unsigned __int64)&UnicodeString & -(__int64)(v87 != 0),
                                            0,
                                            hMem,
                                            0);
                    v6 = UserAccountSettings;
                    if ( UserAccountSettings >= 0 )
                    {
                      v6 = SampStorePasswordExpired(a1, v36);
                      UserAccountSettings = v6;
                    }
                    v88 = v130;
                    if ( (v170 & 0x40) != 0 )
                      v88 = 1;
                    LOBYTE(v130) = v88;
                    goto LABEL_526;
                  }
                  v23 = v118;
LABEL_411:
                  if ( SampFailureAccountAuditingEnabled == 1 && v6 < 0 )
                  {
LABEL_415:
                    SampAuditAnyEvent(
                      a1,
                      (unsigned int)v6,
                      628,
                      0,
                      *((_QWORD *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50) + 1),
                      0,
                      0,
                      0,
                      &String2,
                      (char *)SampDefinedDomains + 1360 * *((unsigned int *)a1 + 50) + 16,
                      (char *)a1 + 248,
                      0,
                      0,
                      0);
                    goto LABEL_416;
                  }
                  if ( SampSuccessAccountAuditingEnabled == 1 )
                  {
                    if ( v6 < 0 )
                      goto LABEL_154;
                    goto LABEL_415;
                  }
LABEL_416:
                  if ( v6 < 0 )
                    goto LABEL_154;
                  v22 = v122;
                  if ( (*((_BYTE *)a1 + 192) & 2) != 0 && (v170 & 0x1C0) == 0 && (v122 || v123[4]) )
                    *((_BYTE *)a1 + 28) |= 0x20u;
                  LOBYTE(v30) = 1;
                  v74 = SampDeReferenceContext(a1, v30);
                  v4 = *(_DWORD *)&v123[5];
                  v6 = v74;
                  UserAccountSettings = v74;
LABEL_552:
                  if ( !v127 )
                  {
                    v102 = 3;
                    if ( v6 < 0 )
                      v102 = 2;
                    SampExtMaybeEndDsTransactionDs(v102);
                    v101 = v128;
                    goto LABEL_576;
                  }
                  if ( v6 >= 0 )
                  {
                    v97 = v120;
                    if ( !v120 && (*((_BYTE *)a1 + 192) & 2) == 0 )
                    {
                      v98 = 1360LL * SampTransactionDomainIndexGlobal;
                      v99 = SampDefinedDomains;
                      if ( *(_DWORD *)((char *)SampDefinedDomains + v98 + 220) != 2 )
                      {
                        --*(_QWORD *)((char *)SampDefinedDomains + v98 + 144);
                        --*(_QWORD *)((char *)v99 + v98 + 872);
                      }
                    }
                    UserAccountSettings = SampCommitAndRetainWriteLock();
                    v6 = UserAccountSettings;
                    if ( UserAccountSettings >= 0 )
                    {
                      if ( !v23 || (*((_BYTE *)a1 + 192) & 2) != 0 )
                      {
                        v100 = v136;
                      }
                      else
                      {
                        memset_0(v158, 0, 0x40u);
                        memset_0(v154, 0, 0x40u);
                        v100 = v136;
                        v159 = String1;
                        v158[1] = v135;
                        v158[0] = v136;
                        RtlInitUnicodeString(&v160, 0);
                        RtlInitUnicodeString(&v161, 0);
                        v155 = String2;
                        v154[1] = v170;
                        v154[0] = v100;
                        v156 = v150;
                        v157 = v149;
                        SampUpdateDisplayInformation(v158, v154, 4);
                      }
                      if ( (unsigned int)(v4 - 6) > 1 && (v4 != 21 || (v129[71] & 1) == 0) )
                      {
                        v35 = v97 == 0;
                        v101 = v128;
                        if ( !v35 )
                        {
                          pSecurityDescriptor = (PSECURITY_DESCRIPTOR)v170;
                          SampNotifyNetlogonOfDelta(v128, 2, v100, 0, (unsigned __int8)v130, &pSecurityDescriptor);
                        }
                        goto LABEL_570;
                      }
                      SampNotifyNetlogonOfDelta(2, 2, v100, &String1, (unsigned __int8)v130, 0);
                    }
                  }
                  v101 = v128;
LABEL_570:
                  if ( v123[3] )
                    SampExtDeleteElementFromAccountNameTableDs(v137, 4);
                  SampReleaseWriteLock(0);
LABEL_576:
                  if ( v6 >= 0 )
                  {
                    v103 = v22 != 0;
                    if ( v123[4] )
                      v103 |= 2u;
                    if ( v101 == 8 && (v170 & 0x40) == 0 )
                      v103 |= 4u;
                    if ( v103 )
                    {
                      p_String2 = &String2;
                      v105 = v103 | 8;
                      if ( (v170 & 0x1C0) == 0 )
                        v105 = v103;
                      if ( !String2.Buffer )
                        p_String2 = (UNICODE_STRING *)&v146;
                      v106 = v121 != 0;
                      v121 = -v121;
                      SampPasswordChangeNotify(
                        v105,
                        (_DWORD)p_String2,
                        v131,
                        (unsigned __int64)hMem & -(__int64)v106,
                        0);
                    }
                  }
                  SampFreeUnicodeString(&String1);
                  SampFreeUnicodeString(&String2);
                  SampFreeUnicodeString(&v149);
                  SampFreeUnicodeString(&v150);
                  SampFreeUnicodeString(&v146);
                  v107 = UnicodeString.Buffer;
                  if ( UnicodeString.Buffer )
                  {
                    Length = UnicodeString.Length;
                    if ( UnicodeString.Length )
                    {
                      do
                      {
                        *(_BYTE *)v107 = 0;
                        v107 = (PWSTR)((char *)v107 + 1);
                        --Length;
                      }
                      while ( Length );
                    }
                    RtlFreeUnicodeString(&UnicodeString);
                  }
                  v109 = hMem[1];
                  if ( hMem[1] )
                  {
                    v110 = LOWORD(hMem[0]);
                    if ( LOWORD(hMem[0]) )
                    {
                      do
                      {
                        *v109++ = 0;
                        --v110;
                      }
                      while ( v110 );
                      v109 = hMem[1];
                    }
                    LocalFree(v109);
                  }
                  v111 = 16;
                  v112 = &v176;
                  v113 = 16;
                  do
                  {
                    *(_BYTE *)v112 = 0;
                    v112 = (__int128 *)((char *)v112 + 1);
                    --v113;
                  }
                  while ( v113 );
                  v114 = &v177;
                  do
                  {
                    *(_BYTE *)v114 = 0;
                    v114 = (__int128 *)((char *)v114 + 1);
                    --v111;
                  }
                  while ( v111 );
                  SampMapNtStatusToClientRevision(v144, &UserAccountSettings);
                  v6 = UserAccountSettings;
                  goto LABEL_603;
                }
                v175 = 0;
                v6 = SystemFunction029(a1, &v175);
                UserAccountSettings = v6;
                if ( v6 >= 0 )
                {
                  if ( !*((_BYTE *)a3 + 33)
                    || (v6 = SystemFunction021(a3 + 4, &v175, &v176), UserAccountSettings = v6, v6 >= 0) )
                  {
                    if ( !*((_BYTE *)a3 + 32) )
                      goto LABEL_508;
                    UserAccountSettings = SystemFunction023(a3, &v175, &v177);
                    v6 = UserAccountSettings;
                    if ( UserAccountSettings >= 0 )
                      goto LABEL_508;
                  }
                }
LABEL_526:
                v21 = v120;
                goto LABEL_527;
              }
            }
            else if ( v4 != 21 )
            {
              if ( v4 != 6 && v4 != 7 && v4 != 8 && v4 != 13 && v4 != 16 )
                goto LABEL_127;
LABEL_124:
              v118 = 1;
              goto LABEL_125;
            }
            if ( (v16[71] & 0x100013) == 0 )
              goto LABEL_125;
            goto LABEL_124;
          }
LABEL_603:
          v11 = v132;
          goto LABEL_604;
        }
        if ( v4 == 10 || v4 == 11 || v4 == 12 || v4 == 13 || v4 == 14 )
          goto LABEL_46;
        v17 = v4 - 15;
        if ( v4 != 15 )
          goto LABEL_57;
        goto LABEL_67;
      }
      if ( v4 > 25 )
      {
        switch ( v4 )
        {
          case 26:
            goto LABEL_67;
          case 28:
            UserAccountSettings = SampCheckAccessToExtendedInformation(a1, 1u, *a3);
            v6 = UserAccountSettings;
            if ( UserAccountSettings < 0 )
              goto LABEL_603;
            v18 = ((*a3 & 0xDFC000) != 0 ? 0x20 : 0) | 4;
            if ( (*a3 & 0x3000) == 0 )
              v18 = (*a3 & 0xDFC000) != 0 ? 0x20 : 0;
            goto LABEL_68;
          case 30:
            v18 = 64;
            goto LABEL_68;
          case 31:
LABEL_67:
            v128 = 8;
            v18 = 128;
            goto LABEL_68;
        }
        if ( v4 != 32 )
        {
          v17 = v4 - 33;
          if ( v4 == 33 )
            goto LABEL_58;
LABEL_57:
          if ( v17 != 1 )
            goto LABEL_58;
LABEL_46:
          v18 = 32;
          goto LABEL_68;
        }
      }
      else if ( v4 != 25 )
      {
        switch ( v4 )
        {
          case 18:
            goto LABEL_67;
          case 19:
            v18 = 0;
            goto LABEL_68;
          case 20:
            goto LABEL_46;
        }
        if ( v4 != 21 && v4 != 22 && v4 != 23 )
          goto LABEL_67;
      }
      v19 = a3[71];
      if ( v19 && (v19 & 0xC0030004) == 0 )
      {
        if ( (((v19 & 0x80000) != 0) & (unsigned __int8)~(*((_BYTE *)a1 + 20) >> 5)) != 0 && *((_DWORD *)a1 + 62) == 500 )
        {
          v137 = (int *)*((_QWORD *)a3 + 3);
          if ( v137 )
          {
            v6 = -1073741532;
            goto LABEL_603;
          }
        }
        v129 = a3;
        v16 = a3;
        v18 = 0;
        if ( (v19 & 0x1404D800) == 0 )
        {
          v18 = ((v19 & 0x3827DB) != 0 ? 0x20 : 0) | 4;
          if ( (v19 & 0xC00020) == 0 )
            v18 = (v19 & 0x3827DB) != 0 ? 0x20 : 0;
          if ( (v19 & 0xB000000) != 0 )
            v18 |= 0x80u;
        }
        goto LABEL_68;
      }
    }
    v6 = -1073741811;
    goto LABEL_603;
  }
  if ( !v131 )
    goto LABEL_25;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 85, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, (unsigned int)v4);
  if ( (int)SampCreateAccountSid(a1, &v132) < 0 )
  {
    v11 = v132;
  }
  else
  {
    v11 = v132;
    SamLAPSNotifyBlockedOperation(v132, 1u);
  }
  v6 = -1073700725;
LABEL_604:
  LocalFree(v11);
  if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
    SampExtQueueReplicationRequestDs(&Buf1, *((_QWORD *)a1 + 22) + 56LL, 1);
  SampTraceEvent(2);
  v7 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 95, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids, (unsigned int)v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v7[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v8 = 96;
    goto LABEL_611;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800291c0  mov     [rsp-8+arg_18], rbx
0x1800291c5  push    rbp
0x1800291c6  push    rsi
0x1800291c7  push    rdi
0x1800291c8  push    r12
0x1800291ca  push    r13
0x1800291cc  push    r14
0x1800291ce  push    r15
0x1800291d0  lea     rbp, [rsp-220h]
0x1800291d8  sub     rsp, 320h
0x1800291df  mov     rax, cs:__security_cookie
0x1800291e6  xor     rax, rsp
0x1800291e9  mov     [rbp+250h+var_38], rax
0x1800291f0  xor     r13d, r13d
0x1800291f3  mov     dword ptr [rbp+250h+var_2D5+5], edx
0x1800291f6  mov     r12, r8
0x1800291f9  mov     [rbp+250h+var_25C], r13d
0x1800291fd  mov     r15d, edx
0x180029200  mov     rdi, rcx
0x180029203  xor     edx, edx; Val
0x180029205  lea     rcx, [rbp+250h+var_130]; void *
0x18002920c  lea     r8d, [r13+50h]; Size
0x180029210  call    memset_0
0x180029215  xorps   xmm0, xmm0
0x180029218  mov     [rsp+350h+var_2D5+1], r13b
0x18002921d  xorps   xmm1, xmm1
0x180029220  mov     [rsp+350h+var_2D5+2], r13b
0x180029225  mov     rcx, rdi; void *
0x180029228  mov     [rsp+350h+var_2D5], r13b
0x18002922d  movups  xmmword ptr [rbp+250h+String1.Length], xmm0
0x180029231  mov     [rsp+350h+var_2D5+4], r13b
0x180029236  movups  xmmword ptr [rbp+250h+P], xmm1
0x18002923a  mov     [rbp+250h+var_2CA], r13b
0x18002923e  movups  xmmword ptr [rbp+250h+var_1F0.Length], xmm0
0x180029242  mov     [rbp+250h+var_2B4], r13d
0x180029246  movups  xmmword ptr [rbp+250h+String2.Length], xmm1
0x18002924a  mov     [rbp+250h+var_2B0], r13
0x18002924e  movups  xmmword ptr [rbp+250h+var_200.Length], xmm0
0x180029252  movups  [rbp+250h+var_C0], xmm1
0x180029259  movups  [rbp+250h+var_D0], xmm0
0x180029260  movups  [rbp+250h+var_E0], xmm1
0x180029267  movups  xmmword ptr [rbp+250h+UnicodeString.Length], xmm0
0x18002926b  movups  [rbp+250h+var_230], xmm1
0x18002926f  movups  xmmword ptr [rbp+250h+var_B0.MinPasswordLength], xmm0
0x180029276  movups  xmmword ptr [rbp+250h+var_B0.MinPasswordAge], xmm0
0x18002927d  movups  [rbp+250h+var_90], xmm0
0x180029284  movups  xmmword ptr [rbp+250h+hMem], xmm0
0x180029288  movups  [rbp+250h+Buf1], xmm1
0x18002928f  movups  [rbp+250h+Buf2], xmm0
0x180029296  movups  xmmword ptr [rbp+250h+BitMapHeader.SizeOfBitMap], xmm0
0x18002929a  movups  xmmword ptr [rbp+250h+var_220.Length], xmm1
0x18002929e  movups  xmmword ptr [rbp+250h+DestinationString.Length], xmm0
0x1800292a5  call    ?SampClientRevisionFromHandle@@YAKPEAX@Z; SampClientRevisionFromHandle(void *)
0x1800292aa  mov     [rbp+250h+var_238], eax
0x1800292ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292b4  lea     r14, WPP_4df1d4a5aeb03bdf81176d8d5f1c5427_Traceguids
0x1800292bb  test    byte ptr [rcx+44h], 8
0x1800292bf  jz      short loc_1800292DF
0x1800292c1  cmp     byte ptr [rcx+41h], 4
0x1800292c5  jb      short loc_1800292DF
0x1800292c7  mov     rcx, [rcx+38h]
0x1800292cb  lea     edx, [r13+51h]
0x1800292cf  mov     r9, rdi
0x1800292d2  mov     dword ptr [rsp+350h+var_330], r15d
0x1800292d7  mov     r8, r14
0x1800292da  call    WPP_SF_qD
0x1800292df  mov     rcx, rdi
0x1800292e2  call    SampAcquireWriteLock
0x1800292e7  mov     ebx, eax
0x1800292e9  test    eax, eax
0x1800292eb  jns     short loc_18002930E
0x1800292ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292f4  test    dword ptr [rcx+44h], 20000h
0x1800292fb  jz      loc_18002B7DC
0x180029301  mov     edx, 52h ; 'R'
0x180029306  mov     r8, r14
0x180029309  jmp     loc_18002B7CC
0x18002930e  lea     rax, [rbp+250h+var_25C]
0x180029312  mov     r9d, 4
0x180029318  xor     r8d, r8d
0x18002931b  mov     [rsp+350h+var_330], rax
0x180029320  xor     edx, edx
0x180029322  mov     rcx, rdi
0x180029325  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x18002932a  mov     [rsp+350h+var_2DC], eax
0x18002932e  mov     ebx, eax
0x180029330  test    eax, eax
0x180029332  jns     short loc_18002938E
0x180029334  mov     rcx, cs:WPP_GLOBAL_Control
0x18002933b  test    byte ptr [rcx+44h], 8
0x18002933f  jz      short loc_18002935B
0x180029341  cmp     byte ptr [rcx+41h], 4
0x180029345  jb      short loc_18002935B
0x180029347  mov     rcx, [rcx+38h]
0x18002934b  mov     edx, 53h ; 'S'
0x180029350  mov     r9, rdi
0x180029353  mov     r8, r14
0x180029356  call    WPP_SF_q
0x18002935b  xor     ecx, ecx
0x18002935d  call    SampReleaseWriteLock
0x180029362  mov     rcx, cs:WPP_GLOBAL_Control
0x180029369  mov     ebx, 0C0000008h
0x18002936e  test    dword ptr [rcx+44h], 20000h
0x180029375  jz      loc_18002B7DC
0x18002937b  mov     edx, 54h ; 'T'
0x180029380  mov     r9d, 0C0000008h
0x180029386  mov     r8, r14
0x180029389  jmp     loc_18002B7CF
0x18002938e  xor     edx, edx
0x180029390  mov     rcx, rdi
0x180029393  call    SampDeReferenceContext
0x180029398  xor     ecx, ecx
0x18002939a  call    SampReleaseWriteLock
0x18002939f  xor     r8d, r8d
0x1800293a2  lea     edx, [r8+26h]
0x1800293a6  lea     esi, [rdx-25h]
0x1800293a9  mov     ecx, esi
0x1800293ab  call    SampTraceEvent
0x1800293b0  test    byte ptr [rdi+14h], 20h
0x1800293b4  jnz     loc_18002943B
0x1800293ba  lea     rdx, [rbp+250h+var_2B4]; int *
0x1800293be  mov     rcx, rdi; struct _SAMP_OBJECT *
0x1800293c1  call    ?SampIsLapsAutoManagedAccount@@YAJPEAU_SAMP_OBJECT@@PEAH@Z; SampIsLapsAutoManagedAccount(_SAMP_OBJECT *,int *)
0x1800293c6  mov     [rsp+350h+var_2DC], eax
0x1800293ca  mov     ebx, eax
0x1800293cc  test    eax, eax
0x1800293ce  js      short loc_180029429
0x1800293d0  cmp     [rbp+250h+var_2B4], r13d
0x1800293d4  jz      short loc_18002943B
0x1800293d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293dd  test    byte ptr [rcx+44h], 8
0x1800293e1  jz      short loc_1800293FB
0x1800293e3  cmp     byte ptr [rcx+41h], 2
0x1800293e7  jb      short loc_1800293FB
0x1800293e9  mov     rcx, [rcx+38h]
0x1800293ed  lea     edx, [rsi+54h]
0x1800293f0  mov     r9d, r15d
0x1800293f3  mov     r8, r14
0x1800293f6  call    WPP_SF_d
0x1800293fb  lea     rdx, [rbp+250h+var_2B0]; void **
0x1800293ff  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180029402  call    ?SampCreateAccountSid@@YAJPEAU_SAMP_OBJECT@@PEAPEAX@Z; SampCreateAccountSid(_SAMP_OBJECT *,void * *)
0x180029407  test    eax, eax
0x180029409  js      short loc_18002941B
0x18002940b  mov     edx, esi; unsigned int
0x18002940d  mov     rsi, [rbp+250h+var_2B0]
0x180029411  mov     rcx, rsi; void *
0x180029414  call    ?SamLAPSNotifyBlockedOperation@@YAXPEAXK@Z; SamLAPSNotifyBlockedOperation(void *,ulong)
0x180029419  jmp     short loc_18002941F
0x18002941b  mov     rsi, [rbp+250h+var_2B0]
0x18002941f  mov     ebx, 0C000A08Bh
0x180029424  jmp     loc_18002B72C
0x180029429  cmp     eax, 0C0000064h
0x18002942e  jnz     loc_180029597
0x180029434  mov     ebx, r13d
0x180029437  mov     [rsp+350h+var_2DC], ebx
0x18002943b  lea     eax, [r15-17h]
0x18002943f  cmp     eax, 3
0x180029442  ja      loc_1800294D1
0x180029448  lea     rdx, aSamrsetinforma_3; "SamrSetInformationUser"
0x18002944f  lea     rcx, [rbp+250h+DestinationString]; DestinationString
0x180029456  call    cs:__imp_RtlInitUnicodeString
0x18002945c  xorps   xmm0, xmm0
0x18002945f  lea     r9, [rbp+250h+var_220]
0x180029463  xor     r8d, r8d
0x180029466  mov     edx, esi
0x180029468  mov     rcx, rdi; struct _SAMP_OBJECT *
0x18002946b  movups  xmmword ptr [rbp+250h+var_220.Length], xmm0
0x18002946f  call    SampGetUnicodeStringAttribute
0x180029474  mov     [rsp+350h+var_2DC], eax
0x180029478  mov     ebx, eax
0x18002947a  test    eax, eax
0x18002947c  jns     short loc_1800294C1
0x18002947e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029485  test    byte ptr [rcx+44h], 20h
0x180029489  jz      short loc_1800294A9
0x18002948b  cmp     byte ptr [rcx+41h], 2
0x18002948f  jb      short loc_1800294A9
0x180029491  mov     rcx, [rcx+38h]
0x180029495  mov     edx, 57h ; 'W'
0x18002949a  mov     r9, rdi
0x18002949d  mov     dword ptr [rsp+350h+var_330], eax
0x1800294a1  mov     r8, r14
0x1800294a4  call    WPP_SF_qD
0x1800294a9  lea     rdx, aCouldNotGetAcc; "Could not get account name"
0x1800294b0  lea     rcx, [rbp+250h+var_220]; DestinationString
0x1800294b4  call    cs:__imp_RtlInitUnicodeString
0x1800294ba  mov     ebx, r13d
0x1800294bd  mov     [rsp+350h+var_2DC], ebx
0x1800294c1  lea     rdx, [rbp+250h+var_220]; struct _UNICODE_STRING *
0x1800294c5  lea     rcx, [rbp+250h+DestinationString]; struct _UNICODE_STRING *
0x1800294cc  call    ?SampLogLegacyRpcMethodAuditEvent@@YAXPEAU_UNICODE_STRING@@0@Z; SampLogLegacyRpcMethodAuditEvent(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800294d1  mov     r8d, 8Ch; SizeOfBitMap
0x1800294d7  mov     [rbp+250h+UnicodeString.Buffer], r13
0x1800294db  lea     rdx, [rbp+250h+BitMapBuffer]; BitMapBuffer
0x1800294e2  mov     [rbp+250h+UnicodeString.Length], r13w
0x1800294e7  lea     rcx, [rbp+250h+BitMapHeader]; BitMapHeader
0x1800294eb  mov     qword ptr [rbp+250h+var_230+8], r13
0x1800294ef  call    cs:__imp_RtlInitializeBitMap
0x1800294f5  lea     rcx, [rbp+250h+BitMapHeader]; BitMapHeader
0x1800294f9  call    cs:__imp_RtlClearAllBits
0x1800294ff  xor     edx, edx; SourceString
0x180029501  lea     rcx, [rbp+250h+String1]; DestinationString
0x180029505  call    cs:__imp_RtlInitUnicodeString
0x18002950b  xor     edx, edx; SourceString
0x18002950d  lea     rcx, [rbp+250h+String2]; DestinationString
0x180029511  call    cs:__imp_RtlInitUnicodeString
0x180029517  xor     edx, edx; SourceString
0x180029519  lea     rcx, [rbp+250h+var_200]; DestinationString
0x18002951d  call    cs:__imp_RtlInitUnicodeString
0x180029523  xor     edx, edx; SourceString
0x180029525  lea     rcx, [rbp+250h+var_1F0]; DestinationString
0x180029529  call    cs:__imp_RtlInitUnicodeString
0x18002952f  mov     ecx, 10h
0x180029534  lea     rax, [rbp+250h+hMem]
0x180029538  mov     [rax], r13b
0x18002953b  add     rax, rsi
0x18002953e  sub     rcx, rsi
0x180029541  jnz     short loc_180029538
0x180029543  test    r12, r12
0x180029546  jz      loc_18002B723
0x18002954c  mov     [rbp+250h+var_2C0], r13
0x180029550  mov     r14, r13
0x180029553  mov     [rbp+250h+var_2C8], 7
0x18002955a  cmp     r15d, 11h
0x18002955e  jg      loc_1800295FC
0x180029564  jz      short loc_18002958D
0x180029566  cmp     r15d, 9
0x18002956a  jg      short loc_1800295D2
0x18002956c  jz      short loc_18002958D
0x18002956e  mov     ecx, r15d
0x180029571  sub     ecx, esi
0x180029573  jz      short loc_1800295F2
0x180029575  sub     ecx, esi
0x180029577  jz      short loc_1800295CB
0x180029579  sub     ecx, esi
0x18002957b  jz      short loc_1800295F2
0x18002957d  sub     ecx, esi
0x18002957f  jz      short loc_18002958D
0x180029581  sub     ecx, esi
0x180029583  jz      short loc_1800295F2
0x180029585  sub     ecx, esi
0x180029587  jz      short loc_18002958D
0x180029589  sub     ecx, esi
0x18002958b  jnz     short loc_1800295EE
0x18002958d  mov     esi, 20h ; ' '
0x180029592  jmp     loc_18002964C
0x180029597  mov     rcx, cs:WPP_GLOBAL_Control
0x18002959e  test    byte ptr [rcx+44h], 8
0x1800295a2  jz      loc_18002B728
0x1800295a8  cmp     byte ptr [rcx+41h], 2
0x1800295ac  jb      loc_18002B728
0x1800295b2  mov     rcx, [rcx+38h]
0x1800295b6  mov     edx, 56h ; 'V'
0x1800295bb  mov     r9d, eax
0x1800295be  mov     r8, r14
0x1800295c1  call    WPP_SF_d
0x1800295c6  jmp     loc_18002B728
0x1800295cb  mov     esi, 4
0x1800295d0  jmp     short loc_18002964C
0x1800295d2  mov     ecx, r15d
0x1800295d5  sub     ecx, 0Ah
0x1800295d8  jz      short loc_18002958D
0x1800295da  sub     ecx, esi
0x1800295dc  jz      short loc_18002958D
0x1800295de  sub     ecx, esi
0x1800295e0  jz      short loc_18002958D
0x1800295e2  sub     ecx, esi
0x1800295e4  jz      short loc_18002958D
0x1800295e6  sub     ecx, esi
0x1800295e8  jz      short loc_18002958D
0x1800295ea  sub     ecx, esi
0x1800295ec  jz      short loc_180029640
0x1800295ee  cmp     ecx, esi
0x1800295f0  jz      short loc_18002958D
0x1800295f2  mov     ebx, 0C0000003h
0x1800295f7  jmp     loc_18002B728
0x1800295fc  cmp     r15d, 19h
0x180029600  jg      loc_1800296AD
0x180029606  jz      loc_1800296E0
0x18002960c  mov     ecx, r15d
0x18002960f  sub     ecx, 12h
0x180029612  jz      short loc_180029640
0x180029614  sub     ecx, esi
0x180029616  jz      loc_1800296A8
0x18002961c  sub     ecx, esi
0x18002961e  jz      loc_18002958D
0x180029624  sub     ecx, esi
0x180029626  jz      loc_1800296E0
0x18002962c  sub     ecx, esi
0x18002962e  jz      loc_1800296E0
0x180029634  sub     ecx, esi
0x180029636  jz      loc_1800296E0
0x18002963c  cmp     ecx, esi
0x18002963e  jnz     short loc_1800295F2
0x180029640  mov     [rbp+250h+var_2C8], 8
0x180029647  mov     esi, 80h
0x18002964c  mov     eax, [rdi+0F8h]
0x180029652  mov     [rbp+250h+var_28C], eax
0x180029655  cmp     r15d, 15h
  ... truncated ...
```
