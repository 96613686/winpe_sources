# SampConfigurePackage(ushort const *,ulong,void *,ulong,void *,void *,uchar)

- ea: `0x18006681c`
- end: `0x180067130`
- name: `?SampConfigurePackage@@YAJPEBGKPEAXK11E@Z`
- size: `2324`
- prototype: `__int64 __fastcall(PCWSTR SourceString, __int64, WCHAR *, int, void *, void *, unsigned __int8)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180067140`
- `0x180067304`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x180037284`
- `0x18004e2d4`
- `0x180052e48`
- `0x180059a74`
- `0x18006681c`
- `0x180069728`
- `0x1800b03d0`
- `0x1800bc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066b28`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180066b28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b3a`
- `ntdll!LdrUnloadDll` at `0x1800670d1`
- `ntdll!LdrUnloadDll` at `0x1800670d1`
- `ntdll!RtlCompareString` at `0x180066dbb`
- `ntdll!RtlCompareString` at `0x180066e02`
- `ntdll!RtlCompareString` at `0x180066dbb`
- `ntdll!RtlCompareString` at `0x180066e02`
- `ntdll!LdrGetProcedureAddress` at `0x180066bc2`
- `ntdll!LdrGetProcedureAddress` at `0x180066c07`
- `ntdll!LdrGetProcedureAddress` at `0x180066d50`
- `ntdll!LdrGetProcedureAddress` at `0x180066bc2`
- `ntdll!LdrGetProcedureAddress` at `0x180066c07`
- `ntdll!LdrGetProcedureAddress` at `0x180066d50`
- `ntdll!RtlFreeHeap` at `0x1800670ab`
- `ntdll!RtlFreeHeap` at `0x1800670c3`
- `ntdll!RtlFreeHeap` at `0x1800670ab`
- `ntdll!RtlFreeHeap` at `0x1800670c3`
- `ntdll!RtlAllocateHeap` at `0x180066a9c`
- `ntdll!RtlAllocateHeap` at `0x180066c8c`
- `ntdll!RtlAllocateHeap` at `0x180066a9c`
- `ntdll!RtlAllocateHeap` at `0x180066c8c`
- `ntdll!RtlCopyUnicodeString` at `0x180066b0e`
- `ntdll!RtlCopyUnicodeString` at `0x180066b0e`
- `ntdll!RtlInitUnicodeString` at `0x180066a0e`
- `ntdll!RtlInitUnicodeString` at `0x180066b60`
- `ntdll!RtlInitUnicodeString` at `0x180066b6d`
- `ntdll!RtlInitUnicodeString` at `0x180066cde`
- `ntdll!RtlInitUnicodeString` at `0x180066a0e`
- `ntdll!RtlInitUnicodeString` at `0x180066b60`
- `ntdll!RtlInitUnicodeString` at `0x180066b6d`
- `ntdll!RtlInitUnicodeString` at `0x180066cde`
- `ntdll!RtlInitString` at `0x180066a42`
- `ntdll!RtlInitString` at `0x180066bad`
- `ntdll!RtlInitString` at `0x180066bf2`
- `ntdll!RtlInitString` at `0x180066d23`
- `ntdll!RtlInitString` at `0x180066d3b`
- `ntdll!RtlInitString` at `0x180066df0`
- `ntdll!RtlInitString` at `0x180066a42`
- `ntdll!RtlInitString` at `0x180066bad`
- `ntdll!RtlInitString` at `0x180066bf2`
- `ntdll!RtlInitString` at `0x180066d23`
- `ntdll!RtlInitString` at `0x180066d3b`
- `ntdll!RtlInitString` at `0x180066df0`
- `LSASRV!LsaIAuditNotifyPackageLoad` at `0x18006708b`
- `LSASRV!LsaIAuditNotifyPackageLoad` at `0x18006708b`

## string_xrefs

- `0x180066889`: `CredentialUpdateNotify`
- `0x1800668c2`: `CredentialUpdateFree`
- `0x180066898`: `CredentialUpdateRegister`

## pseudocode

```c
__int64 __fastcall SampConfigurePackage(
        PCWSTR SourceString,
        __int64 a2,
        WCHAR *a3,
        int a4,
        void *a5,
        void *a6,
        unsigned __int8 a7)
{
  unsigned int v7; // r12d
  SIZE_T v11; // r8
  SIZE_T v12; // rbx
  _BYTE *Heap; // rax
  _QWORD *v14; // rsi
  void *v16; // r13
  int v17; // edi
  int v18; // r14d
  unsigned int v19; // r14d
  SIZE_T v20; // rbx
  _BYTE *v21; // rax
  __int128 *v22; // r15
  unsigned int v23; // r8d
  __int64 v24; // rbx
  __int64 v25; // r12
  __int64 v26; // rbx
  __int64 v27; // rdi
  __int64 v28; // rdx
  int v29; // edx
  int v30; // r8d
  PUNICODE_STRING v31; // r10
  __int64 v32; // rdi
  __int64 i; // r15
  __int64 v34; // rcx
  unsigned int v35; // r8d
  __int64 v36; // rbx
  char v37; // al
  __int64 v38; // rax
  __int64 v39; // rdx
  __int128 *v40; // rax
  __int128 *v41; // rcx
  int v42; // edx
  void *v43; // r8
  unsigned int v44; // [rsp+40h] [rbp-C0h]
  UNICODE_STRING SourceStringa; // [rsp+48h] [rbp-B8h] BYREF
  PVOID v46; // [rsp+58h] [rbp-A8h] BYREF
  int v47; // [rsp+60h] [rbp-A0h]
  int v48; // [rsp+64h] [rbp-9Ch]
  unsigned int v49; // [rsp+68h] [rbp-98h]
  struct _STRING Name; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v51; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  PVOID ProcedureAddress; // [rsp+98h] [rbp-68h] BYREF
  PVOID v54; // [rsp+A0h] [rbp-60h] BYREF
  STRING v55; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall *v56)(struct _UNICODE_STRING *); // [rsp+B8h] [rbp-48h]
  struct _UNICODE_STRING v57; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v58; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING v59; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v60; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v61[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 *v62; // [rsp+108h] [rbp+8h]
  struct _STRING v63; // [rsp+110h] [rbp+10h] BYREF
  PCSZ v64; // [rsp+120h] [rbp+20h]
  int v65; // [rsp+128h] [rbp+28h]
  int v66; // [rsp+12Ch] [rbp+2Ch]
  const char *v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  const char *v69; // [rsp+140h] [rbp+40h]
  int v70; // [rsp+148h] [rbp+48h]
  int v71; // [rsp+14Ch] [rbp+4Ch]
  const char *v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+158h] [rbp+58h]
  const char *v74; // [rsp+160h] [rbp+60h]
  __int64 v75; // [rsp+168h] [rbp+68h]
  const char *v76; // [rsp+170h] [rbp+70h]
  int v77; // [rsp+178h] [rbp+78h]
  int v78; // [rsp+17Ch] [rbp+7Ch]
  const char *v79; // [rsp+180h] [rbp+80h]
  __int64 v80; // [rsp+188h] [rbp+88h]
  _STRING String1; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v82[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v83; // [rsp+1B0h] [rbp+B0h]
  const char *v84; // [rsp+1B8h] [rbp+B8h]
  const char *v85; // [rsp+1C0h] [rbp+C0h]
  char v86; // [rsp+1C8h] [rbp+C8h]
  const char *v87; // [rsp+1D0h] [rbp+D0h]
  const char *v88; // [rsp+1D8h] [rbp+D8h]
  char v89; // [rsp+1E0h] [rbp+E0h]
  const char *v90; // [rsp+1E8h] [rbp+E8h]
  const char *v91; // [rsp+1F0h] [rbp+F0h]
  char v92; // [rsp+1F8h] [rbp+F8h]
  const char *v93; // [rsp+200h] [rbp+100h]
  const char *v94; // [rsp+208h] [rbp+108h]
  char v95; // [rsp+210h] [rbp+110h]
  const char *v96; // [rsp+218h] [rbp+118h]
  const char *v97; // [rsp+220h] [rbp+120h]
  char v98; // [rsp+228h] [rbp+128h]
  const char *v99; // [rsp+230h] [rbp+130h]
  const char *v100; // [rsp+238h] [rbp+138h]
  char v101; // [rsp+240h] [rbp+140h]
  const char *v102; // [rsp+248h] [rbp+148h]
  const char *v103; // [rsp+250h] [rbp+150h]
  char v104; // [rsp+258h] [rbp+158h]

  v7 = 0;
  v65 = 16;
  v46 = 0;
  ProcedureAddress = 0;
  v54 = 0;
  v64 = "PasswordChangeNotify";
  v66 = 24;
  v68 = 32;
  v69 = "PasswordFilter";
  v70 = 40;
  v71 = 48;
  v67 = "DeltaNotify";
  v84 = "DeltaNotify";
  v79 = "CredentialUpdateFree";
  v85 = "DeltaNotify";
  v72 = "UserParmsConvert";
  v90 = "UserParmsConvert";
  v91 = "UserParmsConvert";
  v102 = "CredentialUpdateFree";
  v103 = "CredentialUpdateFree";
  SourceStringa = 0;
  v73 = 56;
  Name = 0;
  v74 = "UserParmsFree";
  v63 = 0;
  v75 = 64;
  String1 = 0;
  v76 = "CredentialUpdateNotify";
  DestinationString = 0;
  v77 = 72;
  v78 = 80;
  v80 = 88;
  v82[0] = "PasswordChangeNotify";
  v82[1] = "PasswordChangeNotify";
  v83 = 1;
  v86 = 1;
  v87 = "PasswordFilter";
  v88 = "PasswordFilter";
  v89 = 0;
  v92 = 0;
  v93 = "UserParmsFree";
  v94 = "UserParmsFree";
  v95 = 1;
  v96 = "CredentialUpdateRegister";
  v97 = "CredentialUpdateRegister";
  v98 = 1;
  v99 = "CredentialUpdateNotify";
  v100 = "CredentialUpdateNotify";
  v101 = 1;
  v104 = 1;
  v60 = 0;
  v61[1] = 0;
  v58 = 0;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x100) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 10, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids);
  }
  RtlInitUnicodeString(&DestinationString, 0);
  v61[0] = 1;
  *((_QWORD *)&v60 + 1) = v82;
  v62 = &v60;
  LODWORD(v60) = 8;
  RtlInitString(&String1, "CredentialUpdateRegister");
  SourceStringa.Buffer = a3;
  SourceStringa.Length = a4 - 2;
  SourceStringa.MaximumLength = a4;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x100) != 0
    && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control[3].Buffer, 11, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids, &SourceStringa);
  }
  v11 = (unsigned int)(a4 + 40);
  v12 = v11;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  v14 = Heap;
  if ( !Heap )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        12,
        WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids,
        3221225626LL,
        -1073741670);
    return 3221225626LL;
  }
  for ( ; v12; --v12 )
    *Heap++ = 0;
  *(UNICODE_STRING *)(v14 + 1) = SourceStringa;
  v14[2] = v14 + 5;
  RtlCopyUnicodeString((PUNICODE_STRING)(v14 + 1), &SourceStringa);
  *((_DWORD *)v14 + 6) = a7;
  *(_QWORD *)&v59.Length = LoadLibraryExW(SourceStringa.Buffer, 0, 8u);
  v16 = *(void **)&v59.Length;
  if ( *(_QWORD *)&v59.Length )
  {
    RtlInitString(&Name, "InitializeChangeNotify");
    if ( LdrGetProcedureAddress(v16, &Name, 0, &ProcedureAddress) < 0 || ((unsigned __int8 (*)(void))ProcedureAddress)() )
    {
      v18 = 0;
      RtlInitString(&Name, "RegisterMappedEntrypoints");
      if ( LdrGetProcedureAddress(v16, &Name, 0, &v54) < 0 )
      {
        v17 = 0;
        v48 = 0;
      }
      else
      {
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x100) != 0
          && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
        {
          WPP_SF_Z(WPP_GLOBAL_Control[3].Buffer, 13, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids, &SourceStringa);
        }
        v48 = ((__int64 (__fastcall *)(__int128 *))v54)(&v58);
        v17 = v48;
        if ( v48 < 0 )
          goto LABEL_80;
        v18 = v58;
      }
      v19 = v18 + 1;
      v51 = v19;
      v20 = 96 * v19;
      v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      v14[4] = v21;
      if ( v21 )
      {
        v56 = 0;
        v22 = (__int128 *)v61;
        *(_QWORD *)&v57.Length = v61;
        v23 = 0;
        v44 = 0;
        v49 = 0;
        if ( 96 * v19 )
        {
          do
          {
            *v21++ = 0;
            --v20;
          }
          while ( v20 );
        }
        while ( 1 )
        {
          if ( v23 >= v19 )
          {
            *((_DWORD *)v14 + 7) = v19;
            goto LABEL_80;
          }
          RtlInitUnicodeString(&DestinationString, 0);
          v24 = v7;
          v25 = *((_QWORD *)v22 + 1);
          v26 = 2 * v24;
          if ( *(_DWORD *)(v25 + 8 * v26) )
          {
            v27 = 0;
            v47 = 0;
            do
            {
              v46 = 0;
              v28 = *(_QWORD *)(v25 + 8 * v26 + 8);
              *(_QWORD *)&v55.Length = 3 * v27;
              RtlInitString(&Name, *(PCSZ *)(v28 + 24 * v27));
              RtlInitString(&v63, *(PCSZ *)(*(_QWORD *)(v25 + 8 * v26 + 8) + 8LL * *(_QWORD *)&v55.Length + 8));
              LdrGetProcedureAddress(v16, &v63, 0, &v46);
              v31 = WPP_GLOBAL_Control;
              if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x100) != 0
                && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
              {
                WPP_SF_aZaZZq(
                  WPP_GLOBAL_Control[3].Buffer,
                  v29,
                  v30,
                  (unsigned int)&Name,
                  (__int64)&v63,
                  (__int64)&SourceStringa,
                  (char)v46);
                v31 = WPP_GLOBAL_Control;
              }
              if ( v46 )
              {
                if ( RtlCompareString(&String1, &Name, 1u) )
                {
                  v32 = *(_QWORD *)&v55.Length;
                  for ( i = 0; i != 7; ++i )
                  {
                    v55 = 0;
                    RtlInitString(&v55, (&v64)[2 * i]);
                    if ( !RtlCompareString(&v55, &Name, 1u) )
                    {
                      *(_QWORD *)(v14[4] + (unsigned int)*(&v65 + 4 * i) + 96LL * v44) = v46;
                      v34 = (unsigned int)*(&v66 + 4 * i);
                      if ( (_DWORD)v34 )
                        *(_BYTE *)(v14[4] + v34 + 96LL * v44) = *(_BYTE *)(*(_QWORD *)(v25 + 8 * v26 + 8) + 8 * v32 + 16);
                    }
                  }
                  LODWORD(v27) = v47;
                  v22 = *(__int128 **)&v57.Length;
                  v16 = *(void **)&v59.Length;
                }
                else
                {
                  v56 = (__int64 (__fastcall *)(struct _UNICODE_STRING *))v46;
                }
                v31 = WPP_GLOBAL_Control;
              }
              v25 = *((_QWORD *)v22 + 1);
              v27 = (unsigned int)(v27 + 1);
              v47 = v27;
            }
            while ( (unsigned int)v27 < *(_DWORD *)(v25 + 8 * v26) );
            v17 = v48;
            v19 = v51;
          }
          else
          {
            v31 = WPP_GLOBAL_Control;
          }
          v35 = v44;
          v7 = 0;
          v36 = 96LL * v44;
          if ( *(_QWORD *)(v14[4] + v36 + 72) )
          {
            if ( v56 )
            {
              v37 = v56(&DestinationString);
              v31 = WPP_GLOBAL_Control;
              if ( !v37 )
              {
                v17 = -1073741595;
                goto LABEL_81;
              }
            }
            if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x100) != 0 && HIBYTE(v31[4].Length) >= 4u )
            {
              WPP_SF_ZZ(
                v31[3].Buffer,
                15,
                (unsigned int)WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids,
                (unsigned int)&DestinationString,
                (__int64)&SourceStringa);
              v31 = WPP_GLOBAL_Control;
            }
            if ( !DestinationString.Buffer || !DestinationString.Length || (v38 = v14[4], !*(_QWORD *)(v38 + v36 + 88)) )
            {
              v17 = -1073741595;
              if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x100) == 0 )
                goto LABEL_84;
              if ( HIBYTE(v31[4].Length) >= 2u )
              {
                v42 = 16;
LABEL_72:
                WPP_SF_ZD(
                  v31[3].Buffer,
                  v42,
                  (unsigned int)WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids,
                  (unsigned int)&SourceStringa,
                  229);
                goto LABEL_80;
              }
              goto LABEL_81;
            }
            v35 = v44;
            *(struct _UNICODE_STRING *)(v38 + 96LL * v44) = DestinationString;
            v31 = WPP_GLOBAL_Control;
          }
          v39 = v14[4];
          if ( (*(_QWORD *)(v39 + v36 + 56) != 0) != (*(_QWORD *)(v39 + v36 + 64) != 0) )
            break;
          if ( !*(_QWORD *)(v39 + v36 + 16)
            && !*(_QWORD *)(v39 + v36 + 32)
            && !*(_QWORD *)(v39 + v36 + 72)
            && !*(_QWORD *)(v39 + v36 + 40) )
          {
            v17 = -1073741595;
            if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x100) == 0 )
              goto LABEL_84;
            if ( HIBYTE(v31[4].Length) >= 2u )
            {
              v42 = 18;
              goto LABEL_72;
            }
            goto LABEL_81;
          }
          v40 = &v58;
          v41 = v22;
          if ( v22 == &v58 )
            v40 = v22;
          v23 = v35 + 1;
          v22 = v40;
          *(_QWORD *)&v57.Length = v40;
          v44 = v23;
          if ( v41 == &v58 )
            v7 = v49 + 1;
          v49 = v7;
        }
        v17 = -1073741595;
        if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x100) == 0 )
          goto LABEL_84;
        if ( HIBYTE(v31[4].Length) >= 2u )
        {
          v42 = 17;
          goto LABEL_72;
        }
        goto LABEL_81;
      }
      v17 = -1073741670;
    }
    else
    {
      v17 = -1073741595;
    }
  }
  else
  {
    GetLastError();
    v57 = 0;
    v17 = -1073741515;
    v59 = 0;
    RtlInitUnicodeString(&v57, L"HKLM\\System\\CurrentControlSet\\Control\\Lsa\\");
    RtlInitUnicodeString(&v59, SourceString);
    SampWriteEventLog(SAMMSG_NOTIFICATION_PACKAGE_REGISTRATION_FAILED, L"uuud", &SourceStringa, &v57);
  }
LABEL_80:
  v31 = WPP_GLOBAL_Control;
LABEL_81:
  if ( (*(_DWORD *)(&v31[4].MaximumLength + 1) & 0x100) != 0 && HIBYTE(v31[4].Length) >= 4u )
    WPP_SF_ZD(
      v31[3].Buffer,
      19,
      (unsigned int)WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids,
      (unsigned int)&SourceStringa,
      v17);
LABEL_84:
  if ( v17 < 0 )
  {
    v43 = (void *)v14[4];
    if ( v43 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v43);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    if ( v16 )
      LdrUnloadDll(v16);
  }
  else
  {
    *v14 = SampNotificationPackages;
    SampNotificationPackages = (struct _SAMP_NOTIFICATION_PACKAGE *)v14;
    LsaIAuditNotifyPackageLoad(&SourceStringa);
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 20, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18006681c  mov     [rsp-8+arg_8], rbx
0x180066821  push    rbp
0x180066822  push    rsi
0x180066823  push    rdi
0x180066824  push    r12
0x180066826  push    r13
0x180066828  push    r14
0x18006682a  push    r15
0x18006682c  lea     rbp, [rsp-170h]
0x180066834  sub     rsp, 270h
0x18006683b  mov     rax, cs:__security_cookie
0x180066842  xor     rax, rsp
0x180066845  mov     [rbp+1A0h+var_40], rax
0x18006684c  xor     r12d, r12d
0x18006684f  mov     [rbp+1A0h+var_178], 10h
0x180066856  xorps   xmm0, xmm0
0x180066859  mov     [rsp+2A0h+var_248], r12
0x18006685e  xorps   xmm1, xmm1
0x180066861  mov     [rbp+1A0h+ProcedureAddress], r12
0x180066865  lea     r11, aPasswordchange; "PasswordChangeNotify"
0x18006686c  mov     [rbp+1A0h+var_200], r12
0x180066870  lea     rdx, aPasswordfilter; "PasswordFilter"
0x180066877  mov     [rbp+1A0h+var_180], r11
0x18006687b  lea     rax, aUserparmsfree; "UserParmsFree"
0x180066882  mov     [rbp+1A0h+var_174], 18h
0x180066889  lea     r10, aCredentialupda_0; "CredentialUpdateNotify"
0x180066890  mov     [rbp+1A0h+var_168], 20h ; ' '
0x180066898  lea     r13, aCredentialupda_1; "CredentialUpdateRegister"
0x18006689f  mov     [rbp+1A0h+var_160], rdx
0x1800668a3  mov     ebx, r9d
0x1800668a6  mov     [rbp+1A0h+var_158], 28h ; '('
0x1800668ad  lea     r9, aDeltanotify; "DeltaNotify"
0x1800668b4  mov     [rbp+1A0h+var_154], 30h ; '0'
0x1800668bb  mov     rdi, r8
0x1800668be  mov     [rbp+1A0h+var_170], r9
0x1800668c2  lea     r8, aCredentialupda; "CredentialUpdateFree"
0x1800668c9  mov     [rbp+1A0h+var_E8], r9
0x1800668d0  mov     r14, rcx
0x1800668d3  mov     [rbp+1A0h+var_120], r8
0x1800668da  lea     rcx, aUserparmsconve; "UserParmsConvert"
0x1800668e1  mov     [rbp+1A0h+var_E0], r9
0x1800668e8  mov     [rbp+1A0h+var_150], rcx
0x1800668ec  mov     [rbp+1A0h+var_B8], rcx
0x1800668f3  mov     [rbp+1A0h+var_B0], rcx
0x1800668fa  mov     [rbp+1A0h+var_58], r8
0x180066901  mov     [rbp+1A0h+var_50], r8
0x180066908  movups  xmmword ptr [rsp+2A0h+SourceString.Length], xmm0
0x18006690d  mov     [rbp+1A0h+var_148], 38h ; '8'
0x180066915  movups  xmmword ptr [rsp+2A0h+Name.Length], xmm1
0x18006691a  mov     [rbp+1A0h+var_140], rax
0x18006691e  movups  xmmword ptr [rbp+1A0h+var_190.Length], xmm0
0x180066922  mov     [rbp+1A0h+var_138], 40h ; '@'
0x18006692a  movups  xmmword ptr [rbp+1A0h+String1.Length], xmm1
0x180066931  mov     [rbp+1A0h+var_130], r10
0x180066935  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm0
0x180066939  mov     [rbp+1A0h+var_128], 48h ; 'H'
0x180066940  mov     [rbp+1A0h+var_124], 50h ; 'P'
0x180066947  mov     [rbp+1A0h+var_118], 58h ; 'X'
0x180066952  mov     [rbp+1A0h+var_100], r11
0x180066959  mov     [rbp+1A0h+var_F8], r11
0x180066960  mov     [rbp+1A0h+var_F0], 1
0x180066967  mov     [rbp+1A0h+var_D8], 1
0x18006696e  mov     [rbp+1A0h+var_D0], rdx
0x180066975  mov     [rbp+1A0h+var_C8], rdx
0x18006697c  mov     [rbp+1A0h+var_C0], r12b
0x180066983  mov     [rbp+1A0h+var_A8], r12b
0x18006698a  mov     [rbp+1A0h+var_A0], rax
0x180066991  mov     [rbp+1A0h+var_98], rax
0x180066998  mov     [rbp+1A0h+var_90], 1
0x18006699f  mov     [rbp+1A0h+var_88], r13
0x1800669a6  mov     [rbp+1A0h+var_80], r13
0x1800669ad  mov     [rbp+1A0h+var_78], 1
0x1800669b4  mov     [rbp+1A0h+var_70], r10
0x1800669bb  mov     [rbp+1A0h+var_68], r10
0x1800669c2  mov     [rbp+1A0h+var_60], 1
0x1800669c9  mov     [rbp+1A0h+var_48], 1
0x1800669d0  movups  [rbp+1A0h+var_1B0], xmm0
0x1800669d4  mov     [rbp+1A0h+var_19C], r12d
0x1800669d8  movups  [rbp+1A0h+var_1D0], xmm1
0x1800669dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800669e3  mov     esi, 100h
0x1800669e8  test    [rcx+44h], esi
0x1800669eb  jz      short loc_180066A08
0x1800669ed  cmp     byte ptr [rcx+41h], 4
0x1800669f1  jb      short loc_180066A08
0x1800669f3  mov     rcx, [rcx+38h]
0x1800669f7  lea     edx, [r12+0Ah]
0x1800669fc  lea     r8, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids
0x180066a03  call    WPP_SF_
0x180066a08  xor     edx, edx; SourceString
0x180066a0a  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x180066a0e  call    cs:__imp_RtlInitUnicodeString
0x180066a14  lea     rax, [rbp+1A0h+var_100]
0x180066a1b  mov     [rbp+1A0h+var_1A0], 1
0x180066a22  mov     qword ptr [rbp+1A0h+var_1B0+8], rax
0x180066a26  lea     rcx, [rbp+1A0h+String1]; DestinationString
0x180066a2d  lea     rax, [rbp+1A0h+var_1B0]
0x180066a31  mov     r15d, 8
0x180066a37  mov     rdx, r13; SourceString
0x180066a3a  mov     [rbp+1A0h+var_198], rax
0x180066a3e  mov     dword ptr [rbp+1A0h+var_1B0], r15d
0x180066a42  call    cs:__imp_RtlInitString
0x180066a48  lea     eax, [rbx-2]
0x180066a4b  mov     [rsp+2A0h+SourceString.Buffer], rdi
0x180066a50  mov     [rsp+2A0h+SourceString.Length], ax
0x180066a55  mov     [rsp+2A0h+SourceString.MaximumLength], bx
0x180066a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a61  test    [rcx+44h], esi
0x180066a64  jz      short loc_180066A85
0x180066a66  cmp     byte ptr [rcx+41h], 4
0x180066a6a  jb      short loc_180066A85
0x180066a6c  mov     rcx, [rcx+38h]
0x180066a70  lea     edx, [r15+3]
0x180066a74  lea     r9, [rsp+2A0h+SourceString]
0x180066a79  lea     r8, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids
0x180066a80  call    WPP_SF_Z
0x180066a85  mov     rcx, gs:60h
0x180066a8e  lea     eax, [rbx+28h]
0x180066a91  mov     r8d, eax; Size
0x180066a94  xor     edx, edx; Flags
0x180066a96  mov     ebx, eax
0x180066a98  mov     rcx, [rcx+30h]; HeapHandle
0x180066a9c  call    cs:__imp_RtlAllocateHeap
0x180066aa2  mov     rsi, rax
0x180066aa5  test    rax, rax
0x180066aa8  jnz     short loc_180066AE3
0x180066aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180066ab1  mov     edi, 0C000009Ah
0x180066ab6  test    dword ptr [rcx+44h], 20000h
0x180066abd  jz      short loc_180066ADC
0x180066abf  mov     rcx, [rcx+38h]
0x180066ac3  lea     edx, [rax+0Ch]
0x180066ac6  mov     r9d, 0C000009Ah
0x180066acc  mov     dword ptr [rsp+2A0h+var_280], edi
0x180066ad0  lea     r8, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids
0x180066ad7  call    WPP_SF_Dd
0x180066adc  mov     eax, edi
0x180066ade  jmp     loc_180067106
0x180066ae3  test    rbx, rbx
0x180066ae6  jz      short loc_180066AF4
0x180066ae8  mov     [rax], r12b
0x180066aeb  inc     rax
0x180066aee  sub     rbx, 1
0x180066af2  jnz     short loc_180066AE8
0x180066af4  movups  xmm0, xmmword ptr [rsp+2A0h+SourceString.Length]
0x180066af9  lea     rcx, [rsi+8]; DestinationString
0x180066afd  lea     rax, [rsi+28h]
0x180066b01  movdqu  xmmword ptr [rcx], xmm0
0x180066b05  lea     rdx, [rsp+2A0h+SourceString]; SourceString
0x180066b0a  mov     [rsi+10h], rax
0x180066b0e  call    cs:__imp_RtlCopyUnicodeString
0x180066b14  movzx   eax, [rbp+1A0h+arg_30]
0x180066b1b  mov     r8d, r15d; dwFlags
0x180066b1e  mov     [rsi+18h], eax
0x180066b21  xor     edx, edx; hFile
0x180066b23  mov     rcx, [rsp+2A0h+SourceString.Buffer]; lpLibFileName
0x180066b28  call    cs:__imp_LoadLibraryExW
0x180066b2e  mov     qword ptr [rbp+1A0h+var_1C0.Length], rax
0x180066b32  mov     r13, rax
0x180066b35  test    rax, rax
0x180066b38  jnz     short loc_180066BA1
0x180066b3a  call    cs:__imp_GetLastError
0x180066b40  xorps   xmm0, xmm0
0x180066b43  lea     rdx, aHklmSystemCurr; "HKLM\\System\\CurrentControlSet\\Contro"...
0x180066b4a  xorps   xmm1, xmm1
0x180066b4d  lea     rcx, [rbp+1A0h+var_1E0]; DestinationString
0x180066b51  movups  xmmword ptr [rbp+1A0h+var_1E0.Length], xmm0
0x180066b55  mov     ebx, eax
0x180066b57  mov     edi, 0C0000135h
0x180066b5c  movups  xmmword ptr [rbp+1A0h+var_1C0.Length], xmm1
0x180066b60  call    cs:__imp_RtlInitUnicodeString
0x180066b66  mov     rdx, r14; SourceString
0x180066b69  lea     rcx, [rbp+1A0h+var_1C0]; DestinationString
0x180066b6d  call    cs:__imp_RtlInitUnicodeString
0x180066b73  lea     rax, [rbp+1A0h+var_1C0]
0x180066b77  mov     dword ptr [rsp+2A0h+var_278], ebx
0x180066b7b  lea     r9, [rbp+1A0h+var_1E0]
0x180066b7f  mov     [rsp+2A0h+var_280], rax
0x180066b84  lea     r8, [rsp+2A0h+SourceString]
0x180066b89  lea     rdx, aUuud; "uuud"
0x180066b90  lea     rcx, SAMMSG_NOTIFICATION_PACKAGE_REGISTRATION_FAILED
0x180066b97  call    SampWriteEventLog
0x180066b9c  jmp     loc_18006703B
0x180066ba1  lea     rdx, aInitializechan; "InitializeChangeNotify"
0x180066ba8  lea     rcx, [rsp+2A0h+Name]; DestinationString
0x180066bad  call    cs:__imp_RtlInitString
0x180066bb3  lea     r9, [rbp+1A0h+ProcedureAddress]; ProcedureAddress
0x180066bb7  xor     r8d, r8d; Ordinal
0x180066bba  lea     rdx, [rsp+2A0h+Name]; Name
0x180066bbf  mov     rcx, r13; BaseAddress
0x180066bc2  call    cs:__imp_LdrGetProcedureAddress
0x180066bc8  test    eax, eax
0x180066bca  js      short loc_180066BE3
0x180066bcc  mov     rax, [rbp+1A0h+ProcedureAddress]
0x180066bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066bd5  test    al, al
0x180066bd7  jnz     short loc_180066BE3
0x180066bd9  mov     edi, 0C00000E5h
0x180066bde  jmp     loc_18006703B
0x180066be3  lea     rdx, aRegistermapped; "RegisterMappedEntrypoints"
0x180066bea  mov     r14d, r12d
0x180066bed  lea     rcx, [rsp+2A0h+Name]; DestinationString
0x180066bf2  call    cs:__imp_RtlInitString
0x180066bf8  lea     r9, [rbp+1A0h+var_200]; ProcedureAddress
0x180066bfc  xor     r8d, r8d; Ordinal
0x180066bff  lea     rdx, [rsp+2A0h+Name]; Name
0x180066c04  mov     rcx, r13; BaseAddress
0x180066c07  call    cs:__imp_LdrGetProcedureAddress
0x180066c0d  test    eax, eax
0x180066c0f  js      short loc_180066C62
0x180066c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180066c18  test    dword ptr [rcx+44h], 100h
0x180066c1f  jz      short loc_180066C41
0x180066c21  cmp     byte ptr [rcx+41h], 4
0x180066c25  jb      short loc_180066C41
0x180066c27  mov     rcx, [rcx+38h]
0x180066c2b  lea     r9, [rsp+2A0h+SourceString]
0x180066c30  mov     edx, 0Dh
0x180066c35  lea     r8, WPP_01b93c307ff23203b183c101fc7fd89a_Traceguids
0x180066c3c  call    WPP_SF_Z
0x180066c41  mov     rax, [rbp+1A0h+var_200]
0x180066c45  lea     rcx, [rbp+1A0h+var_1D0]
0x180066c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066c4e  mov     [rsp+2A0h+var_23C], eax
0x180066c52  mov     edi, eax
0x180066c54  test    eax, eax
0x180066c56  js      loc_18006703B
0x180066c5c  mov     r14d, dword ptr [rbp+1A0h+var_1D0]
0x180066c60  jmp     short loc_180066C6A
0x180066c62  mov     edi, r12d
0x180066c65  mov     [rsp+2A0h+var_23C], r12d
0x180066c6a  mov     rcx, gs:60h
0x180066c73  inc     r14d
0x180066c76  xor     edx, edx; Flags
0x180066c78  mov     [rbp+1A0h+var_220], r14d
0x180066c7c  mov     rcx, [rcx+30h]; HeapHandle
0x180066c80  lea     eax, [r14+r14*2]
0x180066c84  shl     eax, 5
0x180066c87  mov     r8d, eax; Size
0x180066c8a  mov     ebx, eax
0x180066c8c  call    cs:__imp_RtlAllocateHeap
0x180066c92  mov     [rsi+20h], rax
0x180066c96  test    rax, rax
0x180066c99  jnz     short loc_180066CA5
0x180066c9b  mov     edi, 0C000009Ah
0x180066ca0  jmp     loc_18006703B
0x180066ca5  mov     [rbp+1A0h+var_1E8], r12
0x180066ca9  lea     r15, [rbp+1A0h+var_1A0]
0x180066cad  mov     qword ptr [rbp+1A0h+var_1E0.Length], r15
0x180066cb1  mov     r8d, r12d
0x180066cb4  mov     [rsp+2A0h+var_260], r12d
0x180066cb9  mov     [rsp+2A0h+var_238], r12d
0x180066cbe  test    rbx, rbx
0x180066cc1  jz      short loc_180066CCF
0x180066cc3  mov     [rax], r8b
0x180066cc6  inc     rax
0x180066cc9  sub     rbx, 1
0x180066ccd  jnz     short loc_180066CC3
0x180066ccf  cmp     r8d, r14d
0x180066cd2  jnb     loc_180067034
0x180066cd8  xor     edx, edx; SourceString
0x180066cda  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x180066cde  call    cs:__imp_RtlInitUnicodeString
0x180066ce4  mov     ebx, r12d
0x180066ce7  mov     r12, [r15+8]
0x180066ceb  add     rbx, rbx
0x180066cee  cmp     dword ptr [r12+rbx*8], 0
0x180066cf3  jbe     loc_180066E79
0x180066cf9  mov     r14d, [rsp+2A0h+var_260]
0x180066cfe  xor     edi, edi
0x180066d00  mov     [rsp+2A0h+var_240], edi
0x180066d04  mov     [rsp+2A0h+var_248], 0
0x180066d0d  lea     rax, [rdi+rdi*2]
0x180066d11  mov     rdx, [r12+rbx*8+8]
0x180066d16  lea     rcx, [rsp+2A0h+Name]; DestinationString
0x180066d1b  mov     qword ptr [rbp+1A0h+var_1F8.Length], rax
0x180066d1f  mov     rdx, [rdx+rax*8]; SourceString
0x180066d23  call    cs:__imp_RtlInitString
0x180066d29  mov     rdx, [r12+rbx*8+8]
0x180066d2e  lea     rcx, [rbp+1A0h+var_190]; DestinationString
0x180066d32  mov     rax, qword ptr [rbp+1A0h+var_1F8.Length]
0x180066d36  mov     rdx, [rdx+rax*8+8]; SourceString
0x180066d3b  call    cs:__imp_RtlInitString
0x180066d41  lea     r9, [rsp+2A0h+var_248]; ProcedureAddress
0x180066d46  xor     r8d, r8d; Ordinal
0x180066d49  lea     rdx, [rbp+1A0h+var_190]; Name
0x180066d4d  mov     rcx, r13; BaseAddress
0x180066d50  call    cs:__imp_LdrGetProcedureAddress
0x180066d56  mov     r10, cs:WPP_GLOBAL_Control
0x180066d5d  test    dword ptr [r10+44h], 100h
0x180066d65  jz      short loc_180066DA0
0x180066d67  cmp     byte ptr [r10+41h], 4
0x180066d6c  jb      short loc_180066DA0
0x180066d6e  mov     rax, [rsp+2A0h+var_248]
0x180066d73  lea     r9, [rsp+2A0h+Name]
0x180066d78  mov     rcx, [r10+38h]
0x180066d7c  mov     [rsp+2A0h+var_270], rax
0x180066d81  lea     rax, [rsp+2A0h+SourceString]
0x180066d86  mov     [rsp+2A0h+var_278], rax
0x180066d8b  lea     rax, [rbp+1A0h+var_190]
  ... truncated ...
```
