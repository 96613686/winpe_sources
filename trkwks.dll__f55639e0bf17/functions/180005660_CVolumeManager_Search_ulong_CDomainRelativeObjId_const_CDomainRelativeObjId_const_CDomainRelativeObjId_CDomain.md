# CVolumeManager::Search(ulong,CDomainRelativeObjId const &,CDomainRelativeObjId const &,CDomainRelativeObjId *,CDomainRelativeObjId *,CMachineId *,ushort *,unsigned __int64)

- ea: `0x180005660`
- end: `0x1800065eb`
- name: `?Search@CVolumeManager@@QEAAJKAEBUCDomainRelativeObjId@@0PEAU2@1PEAUCMachineId@@PEAG_K@Z`
- size: `3979`
- prototype: `__int64 __fastcall(CVolumeManager *this, char, const struct CDomainRelativeObjId *, const struct CDomainRelativeObjId *, struct CDomainRelativeObjId *, struct CDomainRelativeObjId *, struct CMachineId *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800053b0`

## callees

- `0x180003180`
- `0x180003b50`
- `0x180005590`
- `0x180005660`
- `0x180006600`
- `0x1800066c0`
- `0x180006700`
- `0x180006a80`
- `0x18000b520`
- `0x18000c548`
- `0x18000d038`
- `0x18000f8bc`
- `0x18000fc9c`
- `0x180010fb2`
- `0x180010fca`
- `0x180011000`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800062e9`
- `msvcrt!_wcsnicmp` at `0x1800062e9`
- `ntdll!NtCreateFile` at `0x180005fd8`
- `ntdll!NtCreateFile` at `0x180005fd8`
- `ntdll!RtlFreeHeap` at `0x180005cd0`
- `ntdll!RtlFreeHeap` at `0x180005cd0`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180005f1d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180005f1d`
- `ntdll!NtClose` at `0x1800062c9`
- `ntdll!NtClose` at `0x1800062c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800061a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800061a3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006033`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000608c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006033`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000608c`

## pseudocode

```c
__int64 __fastcall CVolumeManager::Search(
        CVolumeManager *this,
        char a2,
        const struct CDomainRelativeObjId *a3,
        const struct CDomainRelativeObjId *a4,
        struct CDomainRelativeObjId *a5,
        struct CDomainRelativeObjId *a6,
        struct CMachineId *a7,
        unsigned __int16 *a8)
{
  int v12; // r15d
  struct CVolume *v13; // rdi
  __int128 v14; // xmm7
  __int128 v15; // xmm6
  char *v16; // rax
  char *v17; // rcx
  unsigned int v18; // ebx
  struct CVolume *NextVolume; // rax
  __m128i v20; // xmm0
  unsigned __int64 v21; // rax
  unsigned int v22; // r9d
  PWSTR Buffer; // r12
  __int64 v24; // rdx
  unsigned __int16 *v25; // r8
  __int64 v26; // rcx
  WCHAR *v27; // r9
  int v28; // r11d
  __int64 v29; // r10
  unsigned __int16 v30; // ax
  __int64 v31; // rcx
  WCHAR *v32; // rax
  int v33; // r11d
  __int64 v34; // rdx
  const unsigned __int16 *v35; // r8
  __int64 v36; // rcx
  WCHAR *v37; // r9
  int v38; // r11d
  __int64 v39; // r10
  unsigned __int16 v40; // ax
  __int64 v41; // rax
  WCHAR *v42; // rcx
  int v43; // r11d
  __int64 v44; // rdx
  const wchar_t *v45; // r8
  __int64 v46; // rcx
  WCHAR *v47; // r9
  int v48; // r11d
  __int64 v49; // r10
  wchar_t v50; // ax
  int BirthId; // ebx
  void *v52; // rcx
  int v53; // r12d
  char *v54; // rax
  char *v55; // rcx
  struct CVolume *v56; // rax
  __m128i v57; // xmm0
  unsigned __int64 v58; // rax
  unsigned __int64 v59; // rcx
  unsigned __int64 v60; // rcx
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int64 v63; // rcx
  unsigned __int16 v64; // ax
  unsigned __int16 v65; // ax
  PLogFileNotify *Volume; // rax
  __int64 v67; // rax
  struct CDomainRelativeObjId *v68; // rdx
  struct CDomainRelativeObjId *v69; // rax
  int v71; // [rsp+60h] [rbp-9F8h]
  void *FileHandle; // [rsp+80h] [rbp-9D8h] BYREF
  int v73; // [rsp+88h] [rbp-9D0h]
  int v74; // [rsp+8Ch] [rbp-9CCh]
  int v75; // [rsp+90h] [rbp-9C8h]
  __int64 v76; // [rsp+98h] [rbp-9C0h]
  __int128 Buf1; // [rsp+A0h] [rbp-9B8h] BYREF
  unsigned int v78; // [rsp+B0h] [rbp-9A8h]
  int v79; // [rsp+B4h] [rbp-9A4h]
  unsigned int v80; // [rsp+B8h] [rbp-9A0h]
  const struct CDomainRelativeObjId *v81; // [rsp+C0h] [rbp-998h]
  __int128 v82; // [rsp+C8h] [rbp-990h] BYREF
  __int64 v83; // [rsp+D8h] [rbp-980h]
  __int128 v84; // [rsp+E0h] [rbp-978h] BYREF
  __int128 v85; // [rsp+F0h] [rbp-968h]
  __int128 v86; // [rsp+100h] [rbp-958h] BYREF
  __int128 v87; // [rsp+110h] [rbp-948h]
  WCHAR *v88; // [rsp+120h] [rbp-938h]
  __int64 v89; // [rsp+128h] [rbp-930h]
  __int64 v90; // [rsp+130h] [rbp-928h]
  WCHAR *v91; // [rsp+138h] [rbp-920h]
  __int64 v92; // [rsp+140h] [rbp-918h]
  __int64 v93; // [rsp+148h] [rbp-910h]
  WCHAR *v94; // [rsp+150h] [rbp-908h]
  __int64 v95; // [rsp+158h] [rbp-900h]
  struct _UNICODE_STRING NtPathName; // [rsp+160h] [rbp-8F8h] BYREF
  WCHAR *v97; // [rsp+170h] [rbp-8E8h]
  __int64 v98; // [rsp+178h] [rbp-8E0h]
  const unsigned __int16 *v99; // [rsp+180h] [rbp-8D8h]
  __int64 v100; // [rsp+188h] [rbp-8D0h]
  __int64 v101; // [rsp+190h] [rbp-8C8h]
  WCHAR *v102; // [rsp+198h] [rbp-8C0h]
  __int64 v103; // [rsp+1A0h] [rbp-8B8h]
  const wchar_t *v104; // [rsp+1A8h] [rbp-8B0h]
  __int64 v105; // [rsp+1B0h] [rbp-8A8h]
  __int64 v106; // [rsp+1B8h] [rbp-8A0h]
  PWSTR v107; // [rsp+1C0h] [rbp-898h]
  struct CDomainRelativeObjId *v108; // [rsp+1C8h] [rbp-890h]
  struct CMachineId *v109; // [rsp+1D0h] [rbp-888h]
  struct CDomainRelativeObjId *v110; // [rsp+1D8h] [rbp-880h]
  __int64 v111; // [rsp+1E0h] [rbp-878h]
  __int128 v112; // [rsp+1F0h] [rbp-868h]
  unsigned __int16 *v113; // [rsp+208h] [rbp-850h]
  __int128 v114; // [rsp+210h] [rbp-848h] BYREF
  __int64 v115; // [rsp+220h] [rbp-838h]
  __int128 v116; // [rsp+228h] [rbp-830h] BYREF
  __int64 v117; // [rsp+238h] [rbp-820h]
  __int64 v118; // [rsp+240h] [rbp-818h]
  __int128 v119; // [rsp+248h] [rbp-810h] BYREF
  __int128 v120; // [rsp+258h] [rbp-800h]
  __int128 v121; // [rsp+278h] [rbp-7E0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+288h] [rbp-7D0h] BYREF
  __int128 v123; // [rsp+2B8h] [rbp-7A0h]
  __int64 v124; // [rsp+2C8h] [rbp-790h]
  __int128 v125; // [rsp+2D0h] [rbp-788h]
  __int64 v126; // [rsp+2E0h] [rbp-778h]
  __int128 v127; // [rsp+2E8h] [rbp-770h]
  __int64 v128; // [rsp+2F8h] [rbp-760h]
  __int128 v129; // [rsp+300h] [rbp-758h]
  __int64 v130; // [rsp+310h] [rbp-748h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+318h] [rbp-740h] BYREF
  char *v132; // [rsp+328h] [rbp-730h]
  char *v133; // [rsp+330h] [rbp-728h]
  __int64 v134; // [rsp+338h] [rbp-720h]
  __m128i v135; // [rsp+340h] [rbp-718h]
  _OWORD v136[6]; // [rsp+350h] [rbp-708h] BYREF
  __int128 Buf2; // [rsp+3B0h] [rbp-6A8h] BYREF
  unsigned __int16 v138[264]; // [rsp+3C0h] [rbp-698h] BYREF
  wchar_t String2[264]; // [rsp+5D0h] [rbp-488h] BYREF
  WCHAR DosPathName[264]; // [rsp+7E0h] [rbp-278h] BYREF

  v81 = a3;
  v110 = a6;
  v108 = a5;
  v109 = a7;
  *(_QWORD *)&Buf1 = a8;
  *a8 = 0;
  v12 = -1913991141;
  v82 = 0;
  v83 = 0;
  v13 = 0;
  CMachineId::CMachineId((CMachineId *)&Buf2);
  v71 = 0;
  v86 = 0;
  v87 = 0;
  v85 = 0;
  v84 = *(_OWORD *)a3;
  v85 = *((_OWORD *)a3 + 1);
  v14 = *(_OWORD *)a4;
  v76 = *((_QWORD *)a4 + 2);
  *((_QWORD *)&v121 + 1) = *((_QWORD *)a4 + 3);
  v15 = Buf2;
  if ( CSvcCtrlInterface::_fStoppedOrStopping )
  {
    RaiseException(0x8DEAD012, 0, 0, 0);
    __debugbreak();
  }
  v74 = a2 & 0x10;
  if ( (a2 & 0x10) == 0 )
  {
    v123 = 0;
    v124 = 0;
    if ( (*((_BYTE *)this + 20) & 2) != 0 )
    {
      v16 = (char *)this + 200;
      v132 = (char *)this + 200;
      v17 = (char *)this + 208;
      v133 = (char *)this + 208;
      v134 = 0;
    }
    else
    {
      v17 = (char *)*((_QWORD *)&v123 + 1);
      v16 = (char *)v123;
    }
    *(_QWORD *)&v82 = v16;
    *((_QWORD *)&v82 + 1) = v17;
  }
  v79 = a2 & 0x20;
  if ( (a2 & 0x20) != 0 )
  {
    v18 = 0;
  }
  else
  {
    v116 = 0;
    v18 = 0;
    v117 = 0;
    if ( (*((_BYTE *)this + 20) & 2) != 0 )
    {
      *(_QWORD *)&v125 = (char *)this + 200;
      *((_QWORD *)&v125 + 1) = (char *)this + 208;
      v126 = 0;
      v116 = v125;
      v117 = 0;
    }
    NextVolume = CVolumeEnumerator::GetNextVolume((LPCRITICAL_SECTION *)&v116);
    while ( 1 )
    {
      v13 = NextVolume;
      if ( !NextVolume )
        break;
      v78 = 0;
      while ( 1 )
      {
        v20 = *(__m128i *)((char *)v13 + 264);
        v135 = v20;
        if ( (*((_BYTE *)v13 + 568) & 1) == 0 )
          break;
        v78 = ++v18;
        if ( v18 > 0xBB8 )
          TrkRaiseWin32Error(258);
        Sleep(0xAu);
      }
      v21 = v20.m128i_i64[0] - *(_QWORD *)a4;
      if ( v20.m128i_i64[0] == *(_QWORD *)a4 )
        v21 = _mm_srli_si128(v20, 8).m128i_u64[0] - *((_QWORD *)a4 + 1);
      if ( !v21 )
      {
        v18 = 0;
        break;
      }
      PLogFileNotify::Release(v13);
      NextVolume = CVolumeEnumerator::GetNextVolume((LPCRITICAL_SECTION *)&v116);
      v18 = 0;
    }
  }
  if ( !v13 )
    goto LABEL_62;
  do
  {
    v22 = *((unsigned __int16 *)v13 + 24);
    if ( v22 < 0x1A )
    {
      StringCchPrintfW(v138, 0x104u, L"\\\\.\\%c:", v22 + 65);
      FileHandle = 0;
      memset_0(DosPathName, 0, 0x20Au);
      memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
      IoStatusBlock = 0;
      NtPathName = 0;
      Buffer = 0;
      v107 = 0;
      v73 = 0;
      v24 = 2147483646;
      v118 = 2147483646;
      v25 = v138;
      v113 = v138;
      v26 = 261;
      v103 = 261;
      v27 = DosPathName;
      v88 = DosPathName;
      v28 = 0;
      v29 = 0;
      v89 = 0;
      while ( v26 )
      {
        if ( !v24 )
          goto LABEL_24;
        v30 = *v25;
        if ( !*v25 )
          goto LABEL_24;
        v113 = ++v25;
        *v27++ = v30;
        v88 = v27;
        v103 = --v26;
        v118 = --v24;
        v89 = ++v29;
      }
      v88 = --v27;
      v89 = v29 - 1;
      v28 = -2147024774;
LABEL_24:
      *v27 = 0;
      v73 = v28;
      if ( v28 < 0 )
        goto LABEL_51;
      v90 = 0;
      v31 = 261;
      v98 = 261;
      v32 = DosPathName;
      v97 = DosPathName;
      v33 = 0;
      while ( v31 )
      {
        if ( !*v32 )
          goto LABEL_29;
        v97 = ++v32;
        v98 = --v31;
      }
      v33 = -2147024809;
LABEL_29:
      v90 = v33 < 0 ? 0LL : 261 - v31;
      if ( v33 < 0 )
        goto LABEL_51;
      v34 = 2147483646;
      v101 = 2147483646;
      v35 = L"\\";
      v99 = L"\\";
      v36 = 261 - v90;
      v100 = 261 - v90;
      v37 = &DosPathName[v90];
      v91 = v37;
      v38 = 0;
      v39 = 0;
      v92 = 0;
      while ( v36 )
      {
        if ( !v34 )
          goto LABEL_37;
        v40 = *v35;
        if ( !*v35 )
          goto LABEL_37;
        v99 = ++v35;
        *v37++ = v40;
        v91 = v37;
        v100 = --v36;
        v101 = --v34;
        v92 = ++v39;
      }
      v91 = --v37;
      v92 = v39 - 1;
      v38 = -2147024774;
LABEL_37:
      *v37 = 0;
      if ( v38 < 0 )
        goto LABEL_51;
      v93 = 0;
      v41 = 261;
      v111 = 261;
      v42 = DosPathName;
      v102 = DosPathName;
      v43 = 0;
      while ( v41 )
      {
        if ( !*v42 )
          goto LABEL_42;
        v102 = ++v42;
        v111 = --v41;
      }
      v43 = -2147024809;
LABEL_42:
      v93 = v43 < 0 ? 0LL : 261 - v41;
      if ( v43 < 0 )
        goto LABEL_51;
      v44 = 2147483646;
      v106 = 2147483646;
      v45 = L"12345678";
      v104 = L"12345678";
      v46 = 261 - v93;
      v105 = 261 - v93;
      v47 = &DosPathName[v93];
      v94 = v47;
      v48 = 0;
      v49 = 0;
      v95 = 0;
      while ( v46 )
      {
        if ( !v44 )
          goto LABEL_50;
        v50 = *v45;
        if ( !*v45 )
          goto LABEL_50;
        v104 = ++v45;
        *v47++ = v50;
        v94 = v47;
        v105 = --v46;
        v106 = --v44;
        v95 = ++v49;
      }
      v94 = --v47;
      v95 = v49 - 1;
      v48 = -2147024774;
LABEL_50:
      *v47 = 0;
      if ( v48 >= 0 )
      {
        if ( RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
        {
          Buffer = NtPathName.Buffer;
          v107 = NtPathName.Buffer;
          *(_OWORD *)&NtPathName.Buffer[(unsigned __int64)((unsigned int)NtPathName.Length - 16) >> 1] = *((_OWORD *)a4 + 1);
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 64;
          ObjectAttributes.ObjectName = &NtPathName;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          BirthId = NtCreateFile(
                      &FileHandle,
                      0x100080u,
                      &ObjectAttributes,
                      &IoStatusBlock,
                      0,
                      0x80u,
                      7u,
                      1u,
                      0x402020u,
                      0,
                      0);
          if ( BirthId < 0 )
            FileHandle = 0;
        }
        else
        {
          BirthId = -1073741773;
        }
      }
      else
      {
LABEL_51:
        BirthId = -2147483643;
      }
      if ( Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      if ( BirthId >= 0 )
      {
        BirthId = GetBirthId(FileHandle, (struct CDomainRelativeObjId *)&v84);
        if ( BirthId >= 0 )
        {
          BirthId = QueryVolRelativePath(FileHandle, String2);
          if ( BirthId >= 0 && !String2[0] )
            wcscpy(String2, L"\\");
        }
        v52 = FileHandle;
      }
      else
      {
        v52 = 0;
        FileHandle = 0;
      }
      if ( v52 )
        NtClose(v52);
      if ( BirthId >= 0 && _wcsnicmp(L"System Volume Information", String2, 0xCu) )
      {
        if ( (unsigned int)CDomainRelativeObjId::operator==(v81, &v84)
          || (unsigned int)CDomainRelativeObjId::operator==(v63, &v86) )
        {
          v65 = VolChar(*((unsigned __int16 *)v13 + 24));
          StringCchPrintfW((unsigned __int16 *)Buf1, 0x209u, L"%c:%s", v65, String2);
          v14 = *CVolume::GetVolumeId((__int64)v13, &Buf1);
          v136[4] = v14;
          v136[5] = *((_OWORD *)a4 + 1);
          v62 = *((_OWORD *)a4 + 1);
          v15 = Buf2;
          v112 = Buf2;
          v12 = 0;
          v75 = 0;
          v71 = 0;
LABEL_100:
          v121 = v62;
          v76 = v62;
          goto LABEL_134;
        }
        if ( !v71 )
        {
          v64 = VolChar(*((unsigned __int16 *)v13 + 24));
          StringCchPrintfW((unsigned __int16 *)Buf1, 0x209u, L"%c:%s", v64, String2);
          v14 = *CVolume::GetVolumeId((__int64)v13, v136);
          v136[2] = v14;
          v136[3] = *((_OWORD *)a4 + 1);
          v121 = *((_OWORD *)a4 + 1);
          v15 = Buf2;
          v112 = Buf2;
          v71 = 1;
          v76 = v121;
        }
      }
    }
    if ( !_InterlockedDecrement((volatile signed __int32 *)v13 + 2) )
      (**(void (__fastcall ***)(struct CVolume *, __int64))v13)(v13, 1);
    v18 = 0;
LABEL_62:
    v13 = CVolumeEnumerator::GetNextVolume((LPCRITICAL_SECTION *)&v82);
  }
  while ( v13 );
  v82 = 0;
  if ( (a2 & 2) == 0 )
  {
    v53 = v74;
    if ( !v74 )
    {
      v127 = 0;
      v128 = 0;
      if ( (*((_BYTE *)this + 20) & 2) != 0 )
      {
        v54 = (char *)this + 200;
        *(_QWORD *)&v119 = (char *)this + 200;
        v55 = (char *)this + 208;
        *((_QWORD *)&v119 + 1) = (char *)this + 208;
        *(_QWORD *)&v120 = 0;
      }
      else
      {
        v55 = (char *)*((_QWORD *)&v127 + 1);
        v54 = (char *)v127;
      }
      *(_QWORD *)&v82 = v54;
      *((_QWORD *)&v82 + 1) = v55;
      v83 = 0;
    }
    if ( !v79 )
    {
      v114 = 0;
      v115 = 0;
      if ( (*((_BYTE *)this + 20) & 2) != 0 )
      {
        *(_QWORD *)&v129 = (char *)this + 200;
        *((_QWORD *)&v129 + 1) = (char *)this + 208;
        v130 = 0;
        v114 = v129;
        v115 = 0;
      }
      v56 = CVolumeEnumerator::GetNextVolume((LPCRITICAL_SECTION *)&v114);
      while ( 1 )
      {
        v13 = v56;
        if ( !v56 )
          break;
        v80 = 0;
        while ( 1 )
        {
          v57 = *(__m128i *)((char *)v13 + 264);
          v136[1] = v57;
          if ( (*((_BYTE *)v13 + 568) & 1) == 0 )
            break;
          v80 = ++v18;
          if ( v18 > 0xBB8 )
            TrkRaiseWin32Error(258);
          Sleep(0xAu);
        }
        v58 = v57.m128i_i64[0] - *(_QWORD *)a4;
        if ( v57.m128i_i64[0] == *(_QWORD *)a4 )
          v58 = _mm_srli_si128(v57, 8).m128i_u64[0] - *((_QWORD *)a4 + 1);
        if ( !v58 )
          break;
        PLogFileNotify::Release(v13);
        v56 = CVolumeEnumerator::GetNextVolume((LPCRITICAL_SECTION *)&v114);
        v18 = 0;
      }
    }
    if ( v13 )
      goto LABEL_80;
    while ( 1 )
    {
      v13 = CVolumeEnumerator::GetNextVolume((LPCRITICAL_SECTION *)&v82);
      if ( !v13 )
        break;
LABEL_80:
      v86 = 0;
      v87 = 0;
      v119 = 0;
      v120 = 0;
      Buf1 = 0;
      if ( (unsigned int)CVolume::Search(
                           v13,
                           a4,
                           (struct CDomainRelativeObjId *)&v86,
                           (struct CMachineId *)&Buf1,
                           (struct CDomainRelativeObjId *)&v119) )
      {
        v59 = v86;
        if ( !(_QWORD)v86 )
          v59 = *((_QWORD *)&v86 + 1) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v59 )
        {
          Volume = CVolumeManager::FindVolume(this, (const struct CVolumeId *)&v86);
          if ( !Volume )
            goto LABEL_131;
          PLogFileNotify::Release(Volume);
          v67 = *((_QWORD *)a4 + 2) - v87;
          if ( !v67 )
            v67 = *((_QWORD *)a4 + 3) - *((_QWORD *)&v87 + 1);
          if ( v67 || v53 )
          {
LABEL_131:
            v12 = -1913990911;
            v75 = -1913990911;
            v84 = *(_OWORD *)v81;
            v61 = *((_OWORD *)v81 + 1);
            v14 = v86;
            v62 = v87;
            v15 = Buf1;
            v112 = Buf1;
            goto LABEL_99;
          }
        }
        v60 = Buf1;
        if ( !(_QWORD)Buf1 )
          v60 = *((_QWORD *)&Buf1 + 1) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v60 && (memcmp_0(&Buf1, &Buf2, 0x10u) || v53) )
        {
          v12 = -1913990911;
          v75 = -1913990911;
          v84 = *(_OWORD *)v81;
          v61 = *((_OWORD *)v81 + 1);
          v15 = Buf1;
          v112 = Buf1;
          v14 = v86;
          v62 = v87;
LABEL_99:
          v71 = 0;
          v85 = v61;
          goto LABEL_100;
        }
      }
      PLogFileNotify::Release(v13);
    }
  }
LABEL_134:
  if ( v13 )
    PLogFileNotify::Release(v13);
  if ( v12 == -1913991141 && v71 )
  {
    v12 = -1913990906;
  }
  else if ( v12 >= 0 )
  {
LABEL_138:
    v68 = v108;
    *(_OWORD *)v108 = v84;
    *((_OWORD *)v68 + 1) = v85;
    *(_OWORD *)v109 = v15;
    v69 = v110;
    *(_OWORD *)v110 = v14;
    *((_QWORD *)v69 + 2) = v76;
    *((_QWORD *)v69 + 3) = *((_QWORD *)&v121 + 1);
    return (unsigned int)v12;
  }
  if ( v12 == -1913990911 || v12 == -1913990906 )
    goto LABEL_138;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180005660  mov     rax, rsp
0x180005663  push    rbx
0x180005664  push    rsi
0x180005665  push    rdi
0x180005666  push    r12
0x180005668  push    r13
0x18000566a  push    r14
0x18000566c  push    r15
0x18000566e  sub     rsp, 0A20h
0x180005675  movaps  xmmword ptr [rax-48h], xmm6
0x180005679  movaps  xmmword ptr [rax-58h], xmm7
0x18000567d  mov     rax, cs:__security_cookie
0x180005684  xor     rax, rsp
0x180005687  mov     [rsp+0A58h+var_68], rax
0x18000568f  mov     r14, r9
0x180005692  mov     rbx, r8
0x180005695  mov     [rsp+0A58h+var_998], rbx
0x18000569d  mov     r13d, edx
0x1800056a0  mov     rsi, rcx
0x1800056a3  mov     rax, [rsp+0A58h+arg_28]
0x1800056ab  mov     [rsp+0A58h+var_880], rax
0x1800056b3  mov     rax, [rsp+0A58h+arg_20]
0x1800056bb  mov     [rsp+0A58h+var_890], rax
0x1800056c3  mov     rax, [rsp+0A58h+arg_30]
0x1800056cb  mov     [rsp+0A58h+var_888], rax
0x1800056d3  mov     rcx, [rsp+0A58h+arg_38]
0x1800056db  mov     qword ptr [rsp+0A58h+Buf1], rcx
0x1800056e3  xor     r12d, r12d
0x1800056e6  mov     [rcx], r12w
0x1800056ea  mov     r15d, 8DEAD01Bh
0x1800056f0  xorps   xmm0, xmm0
0x1800056f3  movdqu  [rsp+0A58h+var_990], xmm0
0x1800056fc  mov     [rsp+0A58h+var_980], r12
0x180005704  mov     edi, r12d
0x180005707  mov     [rsp+0A58h+var_9F0], r12
0x18000570c  lea     rcx, [rsp+0A58h+Buf2]
0x180005714  call    ??0CMachineId@@QEAA@W4MCID_CREATE_TYPE@@@Z; CMachineId::CMachineId(MCID_CREATE_TYPE)
0x180005719  mov     [rsp+0A58h+var_9F8], r12d
0x18000571e  xorps   xmm0, xmm0
0x180005721  movups  [rsp+0A58h+var_958], xmm0
0x180005729  xorps   xmm1, xmm1
0x18000572c  movups  [rsp+0A58h+var_948], xmm1
0x180005734  movups  [rsp+0A58h+var_968], xmm1
0x18000573c  movups  xmm0, xmmword ptr [rbx]
0x18000573f  movups  [rsp+0A58h+var_978], xmm0
0x180005747  mov     rax, [rbx+10h]
0x18000574b  mov     qword ptr [rsp+0A58h+var_968], rax
0x180005753  mov     rax, [rbx+18h]
0x180005757  mov     qword ptr [rsp+0A58h+var_968+8], rax
0x18000575f  movups  xmm7, xmmword ptr [r14]
0x180005763  mov     rax, [r14+10h]
0x180005767  mov     [rsp+0A58h+var_9C0], rax
0x18000576f  mov     rax, [r14+18h]
0x180005773  mov     [rsp+0A58h+var_7D8], rax
0x18000577b  movaps  xmm6, [rsp+0A58h+Buf2]
0x180005783  cmp     cs:?_fStoppedOrStopping@CSvcCtrlInterface@@0HA, r12d; int CSvcCtrlInterface::_fStoppedOrStopping
0x18000578a  jnz     loc_180006196
0x180005790  mov     r12d, r13d
0x180005793  and     r12d, 10h
0x180005797  mov     [rsp+0A58h+var_9CC], r12d
0x18000579f  jnz     short loc_1800057F7
0x1800057a1  xorps   xmm0, xmm0
0x1800057a4  movdqu  [rsp+0A58h+var_7A0], xmm0
0x1800057ad  xor     edx, edx
0x1800057af  mov     [rsp+0A58h+var_790], rdx
0x1800057b7  test    byte ptr [rsi+14h], 2
0x1800057bb  jz      loc_1800061AA
0x1800057c1  lea     rax, [rsi+0C8h]
0x1800057c8  mov     [rsp+0A58h+var_730], rax
0x1800057d0  lea     rcx, [rsi+0D0h]
0x1800057d7  mov     [rsp+0A58h+var_728], rcx
0x1800057df  mov     [rsp+0A58h+var_720], rdx
0x1800057e7  mov     qword ptr [rsp+0A58h+var_990], rax
0x1800057ef  mov     qword ptr [rsp+0A58h+var_990+8], rcx
0x1800057f7  mov     ebx, r13d
0x1800057fa  and     ebx, 20h
0x1800057fd  mov     [rsp+0A58h+var_9A4], ebx
0x180005804  jnz     loc_1800061CA
0x18000580a  xorps   xmm0, xmm0
0x18000580d  movdqu  [rsp+0A58h+var_830], xmm0
0x180005816  xor     ebx, ebx
0x180005818  mov     [rsp+0A58h+var_820], rbx
0x180005820  test    byte ptr [rsi+14h], 2
0x180005824  jz      short loc_180005864
0x180005826  lea     rax, [rsi+0C8h]
0x18000582d  mov     qword ptr [rsp+0A58h+var_788], rax
0x180005835  lea     rax, [rsi+0D0h]
0x18000583c  mov     qword ptr [rsp+0A58h+var_788+8], rax
0x180005844  mov     [rsp+0A58h+var_778], rbx
0x18000584c  movups  xmm0, [rsp+0A58h+var_788]
0x180005854  movups  [rsp+0A58h+var_830], xmm0
0x18000585c  mov     [rsp+0A58h+var_820], rbx
0x180005864  lea     rcx, [rsp+0A58h+var_830]; this
0x18000586c  call    ?GetNextVolume@CVolumeEnumerator@@QEAAPEAVCVolume@@XZ; CVolumeEnumerator::GetNextVolume(void)
0x180005871  mov     rdi, rax
0x180005874  test    rax, rax
0x180005877  jz      short loc_1800058BF
0x180005879  mov     [rsp+0A58h+var_9A8], ebx
0x180005880  movups  xmm0, xmmword ptr [rdi+108h]
0x180005887  movups  [rsp+0A58h+var_718], xmm0
0x18000588f  test    byte ptr [rdi+238h], 1
0x180005896  jnz     loc_180006072
0x18000589c  movq    rax, xmm0
0x1800058a1  sub     rax, [r14]
0x1800058a4  jnz     short loc_1800058B4
0x1800058a6  psrldq  xmm0, 8
0x1800058ab  movq    rax, xmm0
0x1800058b0  sub     rax, [r14+8]
0x1800058b4  test    rax, rax
0x1800058b7  jnz     loc_180006056
0x1800058bd  xor     ebx, ebx
0x1800058bf  mov     [rsp+0A58h+var_9F0], rdi
0x1800058c4  test    rdi, rdi
0x1800058c7  jz      loc_180005D17
0x1800058cd  movzx   r9d, word ptr [rdi+30h]
0x1800058d2  cmp     r9d, 1Ah
0x1800058d6  jnb     loc_180005CFD
0x1800058dc  add     r9d, 41h ; 'A'
0x1800058e0  lea     r8, aC_0; "\\\\.\\%c:"
0x1800058e7  mov     edx, 104h; unsigned __int64
0x1800058ec  lea     rcx, [rsp+0A58h+var_698]; unsigned __int16 *
0x1800058f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800058f9  mov     [rsp+0A58h+var_9E4], ebx
0x1800058fd  mov     [rsp+0A58h+FileHandle], rbx
0x180005905  mov     [rsp+0A58h+var_9E8], ebx
0x180005909  xor     edx, edx; Val
0x18000590b  mov     r8d, 20Ah; Size
0x180005911  lea     rcx, [rsp+0A58h+DosPathName]; void *
0x180005919  call    memset_0
0x18000591e  xorps   xmm0, xmm0
0x180005921  movups  xmmword ptr [rsp+0A58h+ObjectAttributes.Length], xmm0
0x180005929  movups  xmmword ptr [rsp+0A58h+ObjectAttributes.ObjectName], xmm0
0x180005931  movups  xmmword ptr [rsp+0A58h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005939  movups  xmmword ptr [rsp+0A58h+IoStatusBlock], xmm0
0x180005941  xorps   xmm1, xmm1
0x180005944  movups  xmmword ptr [rsp+0A58h+NtPathName.Length], xmm1
0x18000594c  mov     r12, rbx
0x18000594f  mov     [rsp+0A58h+var_898], rbx
0x180005957  mov     [rsp+0A58h+var_9D0], ebx
0x18000595e  mov     [rsp+0A58h+var_9D0], ebx
0x180005965  mov     edx, 7FFFFFFEh
0x18000596a  mov     [rsp+0A58h+var_818], rdx
0x180005972  lea     r8, [rsp+0A58h+var_698]
0x18000597a  mov     [rsp+0A58h+var_850], r8
0x180005982  mov     ecx, 105h
0x180005987  mov     [rsp+0A58h+var_8B8], rcx
0x18000598f  lea     r9, [rsp+0A58h+DosPathName]
0x180005997  mov     [rsp+0A58h+var_938], r9
0x18000599f  mov     r11d, ebx
0x1800059a2  mov     r10, rbx
0x1800059a5  mov     [rsp+0A58h+var_930], rbx
0x1800059ad  nop     dword ptr [rax]
0x1800059b0  test    rcx, rcx
0x1800059b3  jz      loc_1800061D1
0x1800059b9  test    rdx, rdx
0x1800059bc  jz      short loc_180005A06
0x1800059be  movzx   eax, word ptr [r8]
0x1800059c2  test    ax, ax
0x1800059c5  jz      short loc_180005A06
0x1800059c7  add     r8, 2
0x1800059cb  mov     [rsp+0A58h+var_850], r8
0x1800059d3  mov     [r9], ax
0x1800059d7  add     r9, 2
0x1800059db  mov     [rsp+0A58h+var_938], r9
0x1800059e3  dec     rcx
0x1800059e6  mov     [rsp+0A58h+var_8B8], rcx
0x1800059ee  dec     rdx
0x1800059f1  mov     [rsp+0A58h+var_818], rdx
0x1800059f9  inc     r10
0x1800059fc  mov     [rsp+0A58h+var_930], r10
0x180005a04  jmp     short loc_1800059B0
0x180005a06  test    rcx, rcx
0x180005a09  jz      loc_1800061D1
0x180005a0f  mov     [r9], bx
0x180005a13  mov     [rsp+0A58h+var_9D0], r11d
0x180005a1b  test    r11d, r11d
0x180005a1e  js      loc_180005CB0
0x180005a24  mov     [rsp+0A58h+var_928], rbx
0x180005a2c  lea     rdx, [rsp+0A58h+var_928]
0x180005a34  mov     ecx, 105h
0x180005a39  mov     [rsp+0A58h+var_8E0], rcx
0x180005a41  lea     rax, [rsp+0A58h+DosPathName]
0x180005a49  mov     [rsp+0A58h+var_8E8], rax
0x180005a51  mov     r11d, ebx
0x180005a54  test    rcx, rcx
0x180005a57  jz      loc_1800061F3
0x180005a5d  cmp     word ptr [rax], 0
0x180005a61  jz      short loc_180005A7C
0x180005a63  add     rax, 2
0x180005a67  mov     [rsp+0A58h+var_8E8], rax
0x180005a6f  dec     rcx
0x180005a72  mov     [rsp+0A58h+var_8E0], rcx
0x180005a7a  jmp     short loc_180005A54
0x180005a7c  test    rcx, rcx
0x180005a7f  jz      loc_1800061F3
0x180005a85  test    r11d, r11d
0x180005a88  js      loc_1800061FE
0x180005a8e  mov     eax, 105h
0x180005a93  sub     rax, rcx
0x180005a96  mov     [rdx], rax
0x180005a99  test    r11d, r11d
0x180005a9c  js      loc_180005CB0
0x180005aa2  mov     edx, 7FFFFFFEh
0x180005aa7  mov     [rsp+0A58h+var_8C8], rdx
0x180005aaf  lea     r8, asc_180015BC8; "\\"
0x180005ab6  mov     [rsp+0A58h+var_8D8], r8
0x180005abe  mov     ecx, 105h
0x180005ac3  mov     rax, [rsp+0A58h+var_928]
0x180005acb  sub     rcx, rax
0x180005ace  mov     [rsp+0A58h+var_8D0], rcx
0x180005ad6  lea     r9, [rsp+0A58h+DosPathName]
0x180005ade  lea     r9, [r9+rax*2]
0x180005ae2  mov     [rsp+0A58h+var_920], r9
0x180005aea  mov     r11d, ebx
0x180005aed  mov     r10, rbx
0x180005af0  mov     [rsp+0A58h+var_918], rbx
0x180005af8  nop     dword ptr [rax+rax+00000000h]
0x180005b00  test    rcx, rcx
0x180005b03  jz      loc_180006206
0x180005b09  test    rdx, rdx
0x180005b0c  jz      short loc_180005B56
0x180005b0e  movzx   eax, word ptr [r8]
0x180005b12  test    ax, ax
0x180005b15  jz      short loc_180005B56
0x180005b17  add     r8, 2
0x180005b1b  mov     [rsp+0A58h+var_8D8], r8
0x180005b23  mov     [r9], ax
0x180005b27  add     r9, 2
0x180005b2b  mov     [rsp+0A58h+var_920], r9
0x180005b33  dec     rcx
0x180005b36  mov     [rsp+0A58h+var_8D0], rcx
0x180005b3e  dec     rdx
0x180005b41  mov     [rsp+0A58h+var_8C8], rdx
0x180005b49  inc     r10
0x180005b4c  mov     [rsp+0A58h+var_918], r10
0x180005b54  jmp     short loc_180005B00
0x180005b56  test    rcx, rcx
0x180005b59  jz      loc_180006206
0x180005b5f  mov     [r9], bx
0x180005b63  test    r11d, r11d
0x180005b66  js      loc_180005CB0
0x180005b6c  mov     [rsp+0A58h+var_910], rbx
0x180005b74  lea     rdx, [rsp+0A58h+var_910]
0x180005b7c  mov     eax, 105h
0x180005b81  mov     [rsp+0A58h+var_878], rax
0x180005b89  lea     rcx, [rsp+0A58h+DosPathName]
0x180005b91  mov     [rsp+0A58h+var_8C0], rcx
0x180005b99  mov     r11d, ebx
0x180005b9c  nop     dword ptr [rax+00h]
0x180005ba0  test    rax, rax
0x180005ba3  jz      loc_180006228
0x180005ba9  cmp     word ptr [rcx], 0
0x180005bad  jz      short loc_180005BC8
0x180005baf  add     rcx, 2
0x180005bb3  mov     [rsp+0A58h+var_8C0], rcx
0x180005bbb  dec     rax
0x180005bbe  mov     [rsp+0A58h+var_878], rax
0x180005bc6  jmp     short loc_180005BA0
0x180005bc8  test    rax, rax
0x180005bcb  jz      loc_180006228
0x180005bd1  test    r11d, r11d
0x180005bd4  js      loc_180006233
0x180005bda  mov     ecx, 105h
0x180005bdf  sub     rcx, rax
0x180005be2  mov     [rdx], rcx
0x180005be5  test    r11d, r11d
0x180005be8  js      loc_180005CB0
0x180005bee  mov     edx, 7FFFFFFEh
0x180005bf3  mov     [rsp+0A58h+var_8A0], rdx
0x180005bfb  lea     r8, a12345678; "12345678"
0x180005c02  mov     [rsp+0A58h+var_8B0], r8
0x180005c0a  mov     ecx, 105h
0x180005c0f  mov     rax, [rsp+0A58h+var_910]
0x180005c17  sub     rcx, rax
0x180005c1a  mov     [rsp+0A58h+var_8A8], rcx
0x180005c22  lea     r9, [rsp+0A58h+DosPathName]
0x180005c2a  lea     r9, [r9+rax*2]
0x180005c2e  mov     [rsp+0A58h+var_908], r9
0x180005c36  mov     r11d, ebx
0x180005c39  mov     r10, rbx
0x180005c3c  mov     [rsp+0A58h+var_900], rbx
0x180005c44  test    rcx, rcx
0x180005c47  jz      loc_18000623B
0x180005c4d  test    rdx, rdx
0x180005c50  jz      short loc_180005C9A
0x180005c52  movzx   eax, word ptr [r8]
0x180005c56  test    ax, ax
0x180005c59  jz      short loc_180005C9A
0x180005c5b  add     r8, 2
0x180005c5f  mov     [rsp+0A58h+var_8B0], r8
0x180005c67  mov     [r9], ax
0x180005c6b  add     r9, 2
0x180005c6f  mov     [rsp+0A58h+var_908], r9
0x180005c77  dec     rcx
0x180005c7a  mov     [rsp+0A58h+var_8A8], rcx
0x180005c82  dec     rdx
0x180005c85  mov     [rsp+0A58h+var_8A0], rdx
0x180005c8d  inc     r10
0x180005c90  mov     [rsp+0A58h+var_900], r10
0x180005c98  jmp     short loc_180005C44
  ... truncated ...
```
