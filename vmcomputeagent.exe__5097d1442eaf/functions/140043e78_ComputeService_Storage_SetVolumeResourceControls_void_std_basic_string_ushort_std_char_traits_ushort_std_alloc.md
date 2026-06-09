# ComputeService::Storage::SetVolumeResourceControls(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,vmstd::optional<unsigned __int64> const &,vmstd::optional<unsigned __int64> const &,std::vector<Config::Containers::MappedDirectory,std::allocator<Config::Containers::MappedDirectory>> const &)

- ea: `0x140043e78`
- end: `0x140044877`
- name: `?SetVolumeResourceControls@Storage@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBU?$optional@_K@vmstd@@2AEBV?$vector@UMappedDirectory@Containers@Config@@V?$allocator@UMappedDirectory@Containers@Config@@@std@@@4@@Z`
- size: `2559`
- prototype: `__int64 __usercall@<rax>(HANDLE JobHandle@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140087d00`

## callees

- `0x140005360`
- `0x1400056fc`
- `0x140006098`
- `0x1400083bc`
- `0x140008760`
- `0x14001e4f4`
- `0x14002c0a8`
- `0x14002dd18`
- `0x1400392a8`
- `0x14003a9ac`
- `0x14003fc00`
- `0x140040048`
- `0x1400425cc`
- `0x1400427a4`
- `0x14004283c`
- `0x140042a60`
- `0x1400437d4`
- `0x140043e50`
- `0x140043e78`
- `0x1400448ac`
- `0x140044adc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004427e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400442ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140044317`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004443b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004427e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400442ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140044317`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004443b`
- `ntdll!NtSetInformationJobObject` at `0x140043f14`
- `ntdll!NtSetInformationJobObject` at `0x1400445be`
- `ntdll!NtSetInformationJobObject` at `0x140044663`
- `ntdll!NtSetInformationJobObject` at `0x140043f14`
- `ntdll!NtSetInformationJobObject` at `0x1400445be`
- `ntdll!NtSetInformationJobObject` at `0x140044663`
- `ntdll!NtQuerySystemInformation` at `0x14004406f`
- `ntdll!NtQuerySystemInformation` at `0x14004406f`
- `ntdll!RtlNtStatusToDosError` at `0x140044813`
- `ntdll!RtlNtStatusToDosError` at `0x14004484b`
- `ntdll!RtlNtStatusToDosError` at `0x140044813`
- `ntdll!RtlNtStatusToDosError` at `0x14004484b`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14004476a`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14004476a`

## string_xrefs

- `0x1400447c8`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x1400447dd`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x1400447fe`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x140044837`: `onecore\vm\compute\shared\storage\storageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ComputeService::Storage::SetVolumeResourceControls(
        HANDLE JobHandle,
        unsigned __int16 *a2,
        void *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  NTSTATUS v8; // eax
  bool v9; // r13
  __int64 v10; // rax
  unsigned __int64 v11; // r12
  __int64 VolumeDevicePathForFilePath; // rax
  NTSTATUS v13; // eax
  unsigned __int64 v14; // r8
  const void *v15; // rdx
  __int64 v16; // rax
  const char *v17; // r9
  unsigned __int64 v18; // rbx
  _QWORD *v19; // rax
  PVOID *v20; // rsi
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rax
  __int128 *v23; // rdx
  struct _EVENT_DATA_DESCRIPTOR *Ptr; // rcx
  __int128 *v25; // rdx
  struct _EVENT_DATA_DESCRIPTOR *v26; // rcx
  __int64 v27; // rbx
  _QWORD *v28; // rdx
  struct _EVENT_DATA_DESCRIPTOR *v29; // rcx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rdx
  __int64 v32; // rax
  __int128 v33; // xmm6
  __int64 v34; // rdx
  _QWORD *v35; // rdx
  struct _EVENT_DATA_DESCRIPTOR *p_JobInformation; // rcx
  ULONGLONG v37; // rbx
  struct _EVENT_DATA_DESCRIPTOR *v38; // rax
  HANDLE v39; // r13
  NTSTATUS v40; // eax
  __int64 *v41; // rbx
  __int64 *v42; // rax
  int v43; // eax
  NTSTATUS v44; // r12d
  __int64 **v45; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned __int16 *v48; // rsi
  struct _VML_ETW_TRACE *v49; // rbx
  signed int v50; // eax
  __int64 v51; // rdx
  unsigned int v52; // eax
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  int v56; // [rsp+20h] [rbp-1D8h]
  __int64 v57; // [rsp+28h] [rbp-1D0h]
  __int64 v58; // [rsp+30h] [rbp-1C8h]
  PVOID SystemInformation[2]; // [rsp+40h] [rbp-1B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-1A8h]
  unsigned __int16 *v61; // [rsp+60h] [rbp-198h]
  unsigned int v62[2]; // [rsp+68h] [rbp-190h] BYREF
  unsigned int v63; // [rsp+70h] [rbp-188h] BYREF
  __int64 v64; // [rsp+78h] [rbp-180h] BYREF
  __int64 v65; // [rsp+80h] [rbp-178h]
  __int64 v66; // [rsp+88h] [rbp-170h]
  HANDLE JobHandlea; // [rsp+90h] [rbp-168h]
  __int128 *v68; // [rsp+98h] [rbp-160h]
  __int64 v69; // [rsp+A0h] [rbp-158h]
  __int128 v70; // [rsp+A8h] [rbp-150h] BYREF
  __int128 v71; // [rsp+B8h] [rbp-140h]
  __int128 v72; // [rsp+C8h] [rbp-130h]
  ULONG ReturnLength[2]; // [rsp+D8h] [rbp-120h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v74; // [rsp+E0h] [rbp-118h] BYREF
  ULONG *v75; // [rsp+F0h] [rbp-108h]
  unsigned __int64 v76; // [rsp+F8h] [rbp-100h]
  __int128 v77; // [rsp+100h] [rbp-F8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR JobInformation; // [rsp+110h] [rbp-E8h] BYREF
  ULONG *v79; // [rsp+120h] [rbp-D8h]
  unsigned __int64 v80; // [rsp+128h] [rbp-D0h]
  struct _EVENT_DATA_DESCRIPTOR v81; // [rsp+130h] [rbp-C8h] BYREF
  PVOID v82; // [rsp+140h] [rbp-B8h]
  __int128 v83; // [rsp+160h] [rbp-98h] BYREF
  __int64 v84; // [rsp+170h] [rbp-88h]
  unsigned __int64 v85; // [rsp+178h] [rbp-80h]
  __int128 v86; // [rsp+180h] [rbp-78h] BYREF
  __int64 v87; // [rsp+190h] [rbp-68h]
  unsigned __int64 v88; // [rsp+198h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  SystemInformation[0] = a3;
  v61 = a2;
  JobHandlea = JobHandle;
  v68 = (__int128 *)JobHandle;
  *(_QWORD *)v62 = a2;
  memset_0(&JobInformation, 0, 0x48u);
  LODWORD(JobInformation.Ptr) = 1;
  v8 = NtSetInformationJobObject(JobHandle, JobObjectJobSetInformation|0x20, &JobInformation, 0x48u);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
      (const char *)(unsigned int)v8,
      v56);
  v9 = *(_BYTE *)(a4 + 8) && *(_QWORD *)a4 || *(_BYTE *)(a5 + 8) && *(_QWORD *)a5;
  LOBYTE(v56) = v9;
  if ( !*(_BYTE *)(a4 + 8) || (v10 = *(_QWORD *)a4, (v58 = *(_QWORD *)a4) == 0) )
  {
    v10 = 0x1000000000000LL;
    v58 = 0x1000000000000LL;
  }
  v64 = v10;
  if ( *(_BYTE *)(a5 + 8) && (v11 = *(_QWORD *)a5) != 0 )
  {
    v65 = *(_QWORD *)a5;
  }
  else
  {
    v11 = 0x1000000000000LL;
    v65 = 0x1000000000000LL;
  }
  try
  {
    v66 = 0;
    v86 = 0;
    v87 = 0;
    v88 = 7;
    LOWORD(v86) = 0;
    v83 = 0;
    v84 = 0;
    v85 = 7;
    LOWORD(v83) = 0;
    if ( *((_QWORD *)SystemInformation[0] + 2) )
    {
      VolumeDevicePathForFilePath = ComputeService::Storage::GetVolumeDevicePathForFilePath(&v74, SystemInformation[0]);
      std::wstring::operator=(&v86, VolumeDevicePathForFilePath);
      std::wstring::~wstring(&v74);
    }
    *(_OWORD *)SystemInformation = 0;
    v60 = 0;
    std::vector<unsigned char>::vector<unsigned char>(SystemInformation, 4096);
    ReturnLength[0] = 0;
    v13 = NtQuerySystemInformation(
            SystemPageFileInformation,
            SystemInformation[0],
            LODWORD(SystemInformation[1]) - LODWORD(SystemInformation[0]),
            ReturnLength);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x349,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
        (const char *)(unsigned int)v13,
        v56);
    v14 = (unsigned __int64)*((unsigned __int16 *)SystemInformation[0] + 8) >> 1;
    v15 = (const void *)*((_QWORD *)SystemInformation[0] + 3);
    v74 = 0;
    v75 = 0;
    v76 = 0;
    std::wstring::_Construct<1,unsigned short const *>((__int64)&v74, v15, v14);
    std::vector<unsigned char>::~vector<unsigned char>(SystemInformation);
    v16 = ComputeService::Storage::GetVolumeDevicePathForFilePath(&JobInformation, &v74);
    std::wstring::operator=(&v83, v16);
    std::wstring::~wstring(&JobInformation);
    std::wstring::~wstring(&v74);
    v18 = v58;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3C1,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
      v17);
    v11 = v65;
    v18 = v64;
    v58 = v64;
    JobHandlea = v68;
    v61 = *(unsigned __int16 **)v62;
  }
  v77 = 0u;
  v19 = operator new(0x58u);
  *v19 = v19;
  v19[1] = v19;
  v19[2] = v19;
  *((_WORD *)v19 + 12) = 257;
  *(_QWORD *)&v77 = v19;
  LOBYTE(v56) = 0;
  v20 = *(PVOID **)a6;
  *(_QWORD *)v62 = *(_QWORD *)(a6 + 8);
  if ( v20 != *(PVOID **)v62 )
  {
    while ( 1 )
    {
      ComputeService::Storage::GetVolumeDevicePathForFilePath(&v74, v20);
      SystemInformation[0] = (unsigned __int64)v20[3] <= 7 ? v20 : *v20;
      if ( *((_BYTE *)v20 + 80) && (v21 = (unsigned __int64)v20[9], (*(_QWORD *)ReturnLength = v21) != 0) )
      {
        v9 = 1;
        if ( !*((_BYTE *)v20 + 80) )
          __fastfail(5u);
      }
      else
      {
        v21 = 0x1000000000000LL;
        *(_QWORD *)ReturnLength = 0x1000000000000LL;
      }
      if ( *((_BYTE *)v20 + 96) && (v22 = (unsigned __int64)v20[11], (v57 = v22) != 0) )
      {
        v9 = 1;
        if ( !*((_BYTE *)v20 + 96) )
          __fastfail(5u);
      }
      else
      {
        v22 = 0x1000000000000LL;
        v57 = 0x1000000000000LL;
      }
      if ( v18 < 0x1000000000000LL || v11 < 0x1000000000000LL || v21 < 0x1000000000000LL || v22 < 0x1000000000000LL )
      {
        v23 = &v86;
        if ( v88 > 7 )
          v23 = (__int128 *)v86;
        Ptr = &v74;
        if ( v76 > 7 )
          Ptr = (struct _EVENT_DATA_DESCRIPTOR *)v74.Ptr;
        if ( !(unsigned int)_o__wcsicmp(Ptr, v23) )
          goto LABEL_47;
        v25 = &v83;
        if ( v85 > 7 )
          v25 = (__int128 *)v83;
        v26 = &v74;
        if ( v76 > 7 )
          v26 = (struct _EVENT_DATA_DESCRIPTOR *)v74.Ptr;
        if ( !(unsigned int)_o__wcsicmp(v26, v25) )
LABEL_47:
          LOBYTE(v56) = 1;
      }
      std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters_Vml::CaseInsensitiveLess_std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters____0___::_Find_lower_bound_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____(
        &v77,
        &v64,
        &v74);
      v27 = v66;
      if ( *(_BYTE *)(v66 + 25) )
        goto LABEL_58;
      v28 = (_QWORD *)(v66 + 32);
      if ( *(_QWORD *)(v66 + 56) > 7u )
        v28 = (_QWORD *)*v28;
      v29 = &v74;
      if ( v76 > 7 )
        v29 = (struct _EVENT_DATA_DESCRIPTOR *)v74.Ptr;
      if ( (int)_o__wcsicmp(v29, v28) < 0 || v27 == (_QWORD)v77 )
      {
LABEL_58:
        JobInformation = v74;
        v79 = v75;
        v80 = v76;
        v75 = 0;
        v76 = 7;
        LOWORD(v74.Ptr) = 0;
        v81.Ptr = *(_QWORD *)ReturnLength;
        *(_QWORD *)&v81.Size = v57;
        v82 = SystemInformation[0];
        v32 = std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters_Vml::CaseInsensitiveLess_std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters____0___::_Find_lower_bound_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____(
                &v77,
                &v64,
                &JobInformation);
        v33 = *(_OWORD *)v32;
        v34 = *(_QWORD *)(v32 + 16);
        if ( *(_BYTE *)(v34 + 25) )
          goto LABEL_64;
        v35 = (_QWORD *)(v34 + 32);
        if ( v35[3] > 7u )
          v35 = (_QWORD *)*v35;
        p_JobInformation = &JobInformation;
        if ( v80 > 7 )
          p_JobInformation = (struct _EVENT_DATA_DESCRIPTOR *)JobInformation.Ptr;
        if ( (int)_o__wcsicmp(p_JobInformation, v35) < 0 )
        {
LABEL_64:
          if ( *((_QWORD *)&v77 + 1) == 0x2E8BA2E8BA2E8BALL )
            std::_Throw_tree_length_error();
          v37 = v77;
          v68 = &v77;
          v69 = 0;
          v38 = (struct _EVENT_DATA_DESCRIPTOR *)operator new(0x58u);
          v38[2] = JobInformation;
          v38[3].Ptr = (ULONGLONG)v79;
          *(_QWORD *)&v38[3].Size = v80;
          v79 = 0;
          v80 = 7;
          LOWORD(JobInformation.Ptr) = 0;
          v38[4] = v81;
          v38[5].Ptr = (ULONGLONG)v82;
          v38->Ptr = v37;
          *(_QWORD *)&v38->Size = v37;
          v38[1].Ptr = v37;
          LOWORD(v38[1].Size) = 0;
          v69 = 0;
          *(_OWORD *)SystemInformation = v33;
          std::_Tree_val_std::_Tree_simple_types_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters_____::_Insert_node(
            &v77,
            SystemInformation);
        }
        std::wstring::~wstring(&JobInformation);
      }
      else
      {
        v30 = *(_QWORD *)(v27 + 64) + *(_QWORD *)ReturnLength;
        if ( v30 < *(_QWORD *)(v27 + 64)
          || (*(_QWORD *)(v27 + 64) = v30, v31 = *(_QWORD *)(v27 + 72) + v57, v31 < *(_QWORD *)(v27 + 72)) )
        {
          msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
        }
        *(_QWORD *)(v27 + 72) = v31;
      }
      std::wstring::~wstring(&v74);
      v20 += 14;
      if ( v20 == *(PVOID **)v62 )
        break;
      v18 = v58;
    }
  }
  if ( v9 )
  {
    v71 = 0;
    v72 = 0x100000000uLL;
    *(_QWORD *)&v70 = v58;
    *((_QWORD *)&v70 + 1) = v11;
    v39 = JobHandlea;
    v40 = NtSetInformationJobObject(JobHandlea, MaxJobObjectInfoClass|JobObjectBasicProcessIdList|0x10, &v70, 0x30u);
    if ( v40 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
        (const char *)(unsigned int)v40,
        v56);
    v41 = *(__int64 **)v77;
    while ( !*((_BYTE *)v41 + 25) )
    {
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v70 = *((_OWORD *)v41 + 4);
      DWORD1(v72) = 3;
      if ( (unsigned __int64)v41[7] <= 7 )
        v42 = v41 + 4;
      else
        v42 = (__int64 *)v41[4];
      *((_QWORD *)&v71 + 1) = v42;
      WORD4(v72) = 2 * *((_WORD *)v41 + 24);
      v43 = NtSetInformationJobObject(v39, MaxJobObjectInfoClass|JobObjectBasicProcessIdList|0x10, &v70, 0x30u);
      v44 = v43;
      if ( v43 < 0 && ((unsigned __int64)v70 < 0x1000000000000LL || *((_QWORD *)&v70 + 1) < 0x1000000000000uLL) )
      {
        v50 = RtlNtStatusToDosError(v43);
        if ( v50 > 0 )
          v50 = (unsigned __int16)v50 | 0x80070000;
        v52 = wil::verify_hresult<long>((unsigned int)v50, v51);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x452,
          (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
          (const char *)v52,
          v56);
        RtlNtStatusToDosError(v44);
        v53 = std::wstring::c_str(v61);
        ComputeService::Reporting::LogAndThrowComputeSystemError<unsigned short const * const &>(
          v53,
          v54,
          v55,
          v41 + 10);
      }
      v45 = (__int64 **)v41[2];
      if ( *((_BYTE *)v45 + 25) )
      {
        for ( i = (__int64 *)v41[1]; !*((_BYTE *)i + 25) && v41 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v41 = i;
        v41 = i;
      }
      else
      {
        v41 = (__int64 *)v41[2];
        for ( j = *v45; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v41 = j;
      }
    }
    if ( (_BYTE)v56 )
    {
      ReturnLength[0] = 0;
      v48 = v61;
      if ( *((_QWORD *)v61 + 3) > 7u )
        v48 = *(unsigned __int16 **)v61;
      v49 = g_VmlEtwTrace;
      if ( g_VmlEtwTrace )
      {
        VmCreateDataDescriptor(&v81, &v63, &szPassword);
        v79 = ReturnLength;
        v80 = 4;
        VmCreateDataDescriptor(&JobInformation, v62, v48);
        EventWrite(*((_QWORD *)v49 + 2), &MSVCOMP_STORAGE_QOS_CONFIGURATION_CONFLICT, 3u, &JobInformation);
      }
    }
  }
  std::_Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters_Vml::CaseInsensitiveLess_std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters____0___::__Tree_std::_Tmap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters_Vml::CaseInsensitiveLess_std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___ComputeService::Storage::SetVolumeResourceControls_::_2_::QoSParameters____0___(&v77);
  std::wstring::~wstring(&v83);
  std::wstring::~wstring(&v86);
}

```

## disassembly

```asm
0x140043e78  mov     rax, rsp
0x140043e7b  push    rbx
0x140043e7c  push    rsi
0x140043e7d  push    rdi
0x140043e7e  push    r12
0x140043e80  push    r13
0x140043e82  push    r14
0x140043e84  push    r15
0x140043e86  sub     rsp, 1C0h
0x140043e8d  movaps  xmmword ptr [rax-48h], xmm6
0x140043e91  mov     rax, cs:__security_cookie
0x140043e98  xor     rax, rsp
0x140043e9b  mov     [rsp+1F8h+var_58], rax
0x140043ea3  mov     rsi, r9
0x140043ea6  mov     [rsp+1F8h+SystemInformation], r8
0x140043eab  mov     rax, rdx
0x140043eae  mov     [rsp+1F8h+var_198], rdx
0x140043eb3  mov     r14, rcx
0x140043eb6  mov     [rsp+1F8h+JobHandle], rcx
0x140043ebe  mov     [rsp+1F8h+var_160], rcx
0x140043ec6  mov     qword ptr [rsp+1F8h+var_190], rdx
0x140043ecb  mov     rbx, [rsp+1F8h+arg_20]
0x140043ed3  mov     rax, [rsp+1F8h+arg_28]
0x140043edb  mov     [rsp+1F8h+var_1D0], rax
0x140043ee0  xor     edi, edi
0x140043ee2  lea     r15d, [rdi+48h]
0x140043ee6  mov     r8d, r15d; Size
0x140043ee9  xor     edx, edx; Val
0x140043eeb  lea     rcx, [rsp+1F8h+JobInformation]; void *
0x140043ef3  call    memset_0
0x140043ef8  mov     dword ptr [rsp+1F8h+JobInformation], 1
0x140043f03  mov     r9d, r15d; JobInformationLength
0x140043f06  lea     r8, [rsp+1F8h+JobInformation]; JobInformation
0x140043f0e  lea     edx, [rdi+2Ah]; JobInformationClass
0x140043f11  mov     rcx, r14; JobHandle
0x140043f14  call    cs:__imp_NtSetInformationJobObject
0x140043f1a  mov     rcx, [rsp+1F8h]; this
0x140043f22  test    eax, eax
0x140043f24  js      loc_1400447C5
0x140043f2a  cmp     [rsi+8], dil
0x140043f2e  jz      short loc_140043F35
0x140043f30  cmp     [rsi], rdi
0x140043f33  ja      short loc_140043F40
0x140043f35  cmp     [rbx+8], dil
0x140043f39  jz      short loc_140043F45
0x140043f3b  cmp     [rbx], rdi
0x140043f3e  jbe     short loc_140043F45
0x140043f40  mov     r13b, 1
0x140043f43  jmp     short loc_140043F48
0x140043f45  mov     r13b, dil
0x140043f48  mov     byte ptr [rsp+1F8h+var_1D8], r13b; int
0x140043f4d  cmp     [rsi+8], dil
0x140043f51  jz      short loc_140043F6C
0x140043f53  mov     rax, [rsi]
0x140043f56  mov     [rsp+1F8h+var_1C8], rax
0x140043f5b  test    rax, rax
0x140043f5e  jz      short loc_140043F6C
0x140043f60  mov     r15, 1000000000000h
0x140043f6a  jmp     short loc_140043F7E
0x140043f6c  mov     r15, 1000000000000h
0x140043f76  mov     rax, r15
0x140043f79  mov     [rsp+1F8h+var_1C8], rax
0x140043f7e  mov     [rsp+1F8h+var_180], rax
0x140043f83  cmp     [rbx+8], dil
0x140043f87  jz      short loc_140043F9B
0x140043f89  mov     r12, [rbx]
0x140043f8c  test    r12, r12
0x140043f8f  jz      short loc_140043F9B
0x140043f91  mov     [rsp+1F8h+var_178], r12
0x140043f99  jmp     short loc_140043FA6
0x140043f9b  mov     r12, r15
0x140043f9e  mov     [rsp+1F8h+var_178], r15
0x140043fa6  xor     eax, eax
0x140043fa8  mov     [rsp+1F8h+var_170], rax
0x140043fb0  xorps   xmm0, xmm0
0x140043fb3  movups  [rsp+1F8h+var_78], xmm0
0x140043fbb  mov     [rsp+1F8h+var_68], rdi
0x140043fc3  lea     r14d, [rax+7]
0x140043fc7  mov     [rsp+1F8h+var_60], r14
0x140043fcf  mov     word ptr [rsp+1F8h+var_78], di
0x140043fd7  movups  [rsp+1F8h+var_98], xmm0
0x140043fdf  mov     [rsp+1F8h+var_88], rdi
0x140043fe7  mov     [rsp+1F8h+var_80], r14
0x140043fef  mov     word ptr [rsp+1F8h+var_98], di
0x140043ff7  mov     rax, [rsp+1F8h+SystemInformation]
0x140043ffc  cmp     [rax+10h], rdi
0x140044000  jz      short loc_14004402F
0x140044002  mov     rdx, rax
0x140044005  lea     rcx, [rsp+1F8h+var_118]
0x14004400d  call    ?GetVolumeDevicePathForFilePath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::Storage::GetVolumeDevicePathForFilePath(std::wstring const &)
0x140044012  mov     rdx, rax
0x140044015  lea     rcx, [rsp+1F8h+var_78]
0x14004401d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140044022  lea     rcx, [rsp+1F8h+var_118]; void *
0x14004402a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004402f  xorps   xmm0, xmm0
0x140044032  xor     eax, eax
0x140044034  movups  xmmword ptr [rsp+1F8h+SystemInformation], xmm0
0x140044039  mov     [rsp+1F8h+var_1A8], rax
0x14004403e  mov     edx, 1000h
0x140044043  lea     rcx, [rsp+1F8h+SystemInformation]
0x140044048  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x14004404d  nop
0x14004404e  mov     [rsp+1F8h+ReturnLength], edi
0x140044055  mov     rdx, [rsp+1F8h+SystemInformation]; SystemInformation
0x14004405a  mov     r8d, dword ptr [rsp+1F8h+SystemInformation+8]
0x14004405f  sub     r8d, edx; SystemInformationLength
0x140044062  lea     r9, [rsp+1F8h+ReturnLength]; ReturnLength
0x14004406a  mov     ecx, 12h; SystemInformationClass
0x14004406f  call    cs:__imp_NtQuerySystemInformation
0x140044075  mov     rcx, [rsp+1F8h]; this
0x14004407d  test    eax, eax
0x14004407f  js      loc_1400447DA
0x140044085  mov     rax, [rsp+1F8h+SystemInformation]
0x14004408a  movzx   r8d, word ptr [rax+10h]
0x14004408f  shr     r8, 1
0x140044092  mov     rdx, [rax+18h]
0x140044096  xorps   xmm0, xmm0
0x140044099  movups  [rsp+1F8h+var_118], xmm0
0x1400440a1  mov     [rsp+1F8h+var_108], rdi
0x1400440a9  mov     [rsp+1F8h+var_100], rdi
0x1400440b1  lea     rcx, [rsp+1F8h+var_118]
0x1400440b9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400440be  nop
0x1400440bf  lea     rcx, [rsp+1F8h+SystemInformation]
0x1400440c4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1400440c9  nop
0x1400440ca  lea     rdx, [rsp+1F8h+var_118]
0x1400440d2  lea     rcx, [rsp+1F8h+JobInformation]
0x1400440da  call    ?GetVolumeDevicePathForFilePath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::Storage::GetVolumeDevicePathForFilePath(std::wstring const &)
0x1400440df  mov     rdx, rax
0x1400440e2  lea     rcx, [rsp+1F8h+var_98]
0x1400440ea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400440ef  lea     rcx, [rsp+1F8h+JobInformation]; void *
0x1400440f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400440fc  nop
0x1400440fd  lea     rcx, [rsp+1F8h+var_118]; void *
0x140044105  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004410a  nop
0x14004410b  mov     rbx, [rsp+1F8h+var_1C8]
0x140044110  jmp     short loc_140044153
0x140044112  xor     edi, edi
0x140044114  mov     r15, 1000000000000h
0x14004411e  lea     r14d, [rdi+7]
0x140044122  mov     r13b, byte ptr [rsp+1F8h+var_1D8]
0x140044127  mov     r12, [rsp+1F8h+var_178]
0x14004412f  mov     rbx, [rsp+1F8h+var_180]
0x140044134  mov     [rsp+1F8h+var_1C8], rbx
0x140044139  mov     rax, [rsp+1F8h+var_160]
0x140044141  mov     [rsp+1F8h+JobHandle], rax
0x140044149  mov     rax, qword ptr [rsp+1F8h+var_190]
0x14004414e  mov     [rsp+1F8h+var_198], rax
0x140044153  xorps   xmm0, xmm0
0x140044156  movups  [rsp+1F8h+var_F8], xmm0
0x14004415e  mov     qword ptr [rsp+1F8h+var_F8], rdi
0x140044166  mov     qword ptr [rsp+1F8h+var_F8+8], rdi
0x14004416e  mov     ecx, 58h ; 'X'; Size
0x140044173  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140044178  mov     [rax], rax
0x14004417b  mov     [rax+8], rax
0x14004417f  mov     [rax+10h], rax
0x140044183  mov     word ptr [rax+18h], 101h
0x140044189  mov     qword ptr [rsp+1F8h+var_F8], rax
0x140044191  mov     byte ptr [rsp+1F8h+var_1D8], dil; int
0x140044196  mov     rax, [rsp+1F8h+var_1D0]
0x14004419b  mov     rsi, [rax]
0x14004419e  mov     rax, [rax+8]
0x1400441a2  mov     qword ptr [rsp+1F8h+var_190], rax
0x1400441a7  cmp     rsi, rax
0x1400441aa  jz      loc_14004455D
0x1400441b0  mov     rdx, rsi
0x1400441b3  lea     rcx, [rsp+1F8h+var_118]
0x1400441bb  call    ?GetVolumeDevicePathForFilePath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::Storage::GetVolumeDevicePathForFilePath(std::wstring const &)
0x1400441c0  nop
0x1400441c1  cmp     [rsi+18h], r14
0x1400441c5  jbe     short loc_1400441D1
0x1400441c7  mov     rax, [rsi]
0x1400441ca  mov     [rsp+1F8h+SystemInformation], rax
0x1400441cf  jmp     short loc_1400441D6
0x1400441d1  mov     [rsp+1F8h+SystemInformation], rsi
0x1400441d6  cmp     [rsi+50h], dil
0x1400441da  jz      short loc_1400441FF
0x1400441dc  mov     rdx, [rsi+48h]
0x1400441e0  mov     qword ptr [rsp+1F8h+ReturnLength], rdx
0x1400441e8  test    rdx, rdx
0x1400441eb  jz      short loc_1400441FF
0x1400441ed  mov     r13b, 1
0x1400441f0  cmp     [rsi+50h], dil
0x1400441f4  jnz     short loc_14004420A
0x1400441f6  mov     ecx, 5
0x1400441fb  int     29h; Win8: RtlFailFast(ecx)
0x1400441fd  jmp     short loc_14004420A
0x1400441ff  mov     rdx, r15
0x140044202  mov     qword ptr [rsp+1F8h+ReturnLength], rdx
0x14004420a  cmp     [rsi+60h], dil
0x14004420e  jz      short loc_140044230
0x140044210  mov     rax, [rsi+58h]
0x140044214  mov     [rsp+1F8h+var_1D0], rax
0x140044219  test    rax, rax
0x14004421c  jz      short loc_140044230
0x14004421e  mov     r13b, 1
0x140044221  cmp     [rsi+60h], dil
0x140044225  jnz     short loc_140044238
0x140044227  mov     ecx, 5
0x14004422c  int     29h; Win8: RtlFailFast(ecx)
0x14004422e  jmp     short loc_140044238
0x140044230  mov     rax, r15
0x140044233  mov     [rsp+1F8h+var_1D0], rax
0x140044238  cmp     rbx, r15
0x14004423b  jb      short loc_14004424C
0x14004423d  cmp     r12, r15
0x140044240  jb      short loc_14004424C
0x140044242  cmp     rdx, r15
0x140044245  jb      short loc_14004424C
0x140044247  cmp     rax, r15
0x14004424a  jnb     short loc_1400442C9
0x14004424c  lea     rdx, [rsp+1F8h+var_78]
0x140044254  cmp     [rsp+1F8h+var_60], r14
0x14004425c  cmova   rdx, qword ptr [rsp+1F8h+var_78]
0x140044265  lea     rcx, [rsp+1F8h+var_118]
0x14004426d  cmp     [rsp+1F8h+var_100], r14
0x140044275  cmova   rcx, qword ptr [rsp+1F8h+var_118]
0x14004427e  call    cs:__imp__o__wcsicmp
0x140044284  test    eax, eax
0x140044286  jz      short loc_1400442C4
0x140044288  lea     rdx, [rsp+1F8h+var_98]
0x140044290  cmp     [rsp+1F8h+var_80], r14
0x140044298  cmova   rdx, qword ptr [rsp+1F8h+var_98]
0x1400442a1  lea     rcx, [rsp+1F8h+var_118]
0x1400442a9  cmp     [rsp+1F8h+var_100], r14
0x1400442b1  cmova   rcx, qword ptr [rsp+1F8h+var_118]
0x1400442ba  call    cs:__imp__o__wcsicmp
0x1400442c0  test    eax, eax
0x1400442c2  jnz     short loc_1400442C9
0x1400442c4  mov     byte ptr [rsp+1F8h+var_1D8], 1
0x1400442c9  lea     r8, [rsp+1F8h+var_118]
0x1400442d1  lea     rdx, [rsp+1F8h+var_180]
0x1400442d6  lea     rcx, [rsp+1F8h+var_F8]
0x1400442de  call    std___Tree_std___Tmap_traits_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____ComputeService__Storage__SetVolumeResourceControls____2___QoSParameters_Vml__CaseInsensitiveLess_std__allocator_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____const___ComputeService__Storage__SetVolumeResourceControls____2___QoSParameters____0______Find_lower_bound_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____
0x1400442e3  mov     rbx, [rsp+1F8h+var_170]
0x1400442eb  cmp     [rbx+19h], dil
0x1400442ef  jnz     short loc_140044361
0x1400442f1  lea     rdx, [rbx+20h]
0x1400442f5  cmp     [rdx+18h], r14
0x1400442f9  jbe     short loc_1400442FE
0x1400442fb  mov     rdx, [rdx]
0x1400442fe  lea     rcx, [rsp+1F8h+var_118]
0x140044306  cmp     [rsp+1F8h+var_100], r14
0x14004430e  cmova   rcx, qword ptr [rsp+1F8h+var_118]
0x140044317  call    cs:__imp__o__wcsicmp
0x14004431d  test    eax, eax
0x14004431f  js      short loc_140044361
0x140044321  cmp     rbx, qword ptr [rsp+1F8h+var_F8]
0x140044329  jz      short loc_140044361
0x14004432b  mov     rcx, qword ptr [rsp+1F8h+ReturnLength]
0x140044333  add     rcx, [rbx+40h]
0x140044337  cmp     rcx, [rbx+40h]
0x14004433b  jb      loc_1400447EF
0x140044341  mov     [rbx+40h], rcx
0x140044345  mov     rdx, [rsp+1F8h+var_1D0]
0x14004434a  add     rdx, [rbx+48h]
0x14004434e  cmp     rdx, [rbx+48h]
0x140044352  jb      loc_1400447EF
0x140044358  mov     [rbx+48h], rdx
0x14004435c  jmp     loc_14004453B
0x140044361  xorps   xmm0, xmm0
0x140044364  movups  [rsp+1F8h+JobInformation], xmm0
0x14004436c  mov     rax, qword ptr [rsp+1F8h+var_118]
0x140044374  mov     qword ptr [rsp+1F8h+JobInformation], rax
0x14004437c  mov     rax, qword ptr [rsp+1F8h+var_118+8]
0x140044384  mov     qword ptr [rsp+1F8h+JobInformation+8], rax
0x14004438c  mov     rax, [rsp+1F8h+var_108]
0x140044394  mov     [rsp+1F8h+var_D8], rax
0x14004439c  mov     rax, [rsp+1F8h+var_100]
0x1400443a4  mov     [rsp+1F8h+var_D0], rax
0x1400443ac  mov     [rsp+1F8h+var_108], rdi
0x1400443b4  mov     [rsp+1F8h+var_100], r14
0x1400443bc  mov     word ptr [rsp+1F8h+var_118], di
0x1400443c4  mov     rcx, qword ptr [rsp+1F8h+ReturnLength]
0x1400443cc  mov     [rsp+1F8h+var_C8.Ptr], rcx
0x1400443d4  mov     rcx, [rsp+1F8h+var_1D0]
0x1400443d9  mov     qword ptr [rsp+1F8h+var_C8.Size], rcx
0x1400443e1  mov     rax, [rsp+1F8h+SystemInformation]
0x1400443e6  mov     [rsp+1F8h+var_B8], rax
0x1400443ee  lea     r8, [rsp+1F8h+JobInformation]
0x1400443f6  lea     rdx, [rsp+1F8h+var_180]
0x1400443fb  lea     rcx, [rsp+1F8h+var_F8]
0x140044403  call    std___Tree_std___Tmap_traits_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____ComputeService__Storage__SetVolumeResourceControls____2___QoSParameters_Vml__CaseInsensitiveLess_std__allocator_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____const___ComputeService__Storage__SetVolumeResourceControls____2___QoSParameters____0______Find_lower_bound_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____
0x140044408  movups  xmm6, xmmword ptr [rax]
0x14004440b  mov     rdx, [rax+10h]
0x14004440f  cmp     [rdx+19h], dil
0x140044413  jnz     short loc_140044449
0x140044415  add     rdx, 20h ; ' '
0x140044419  cmp     [rdx+18h], r14
0x14004441d  jbe     short loc_140044422
0x14004441f  mov     rdx, [rdx]
0x140044422  lea     rcx, [rsp+1F8h+JobInformation]
0x14004442a  cmp     [rsp+1F8h+var_D0], r14
0x140044432  cmova   rcx, qword ptr [rsp+1F8h+JobInformation]
0x14004443b  call    cs:__imp__o__wcsicmp
  ... truncated ...
```
