# VmVssWriterHelper::ParseBackupMetadataXML(IVssComponent *,_BackupMetadataFormatInfo *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &,int &,int &)

- ea: `0x140163208`
- end: `0x140163a76`
- name: `?ParseBackupMetadataXML@VmVssWriterHelper@@SAHPEAVIVssComponent@@PEAU_BackupMetadataFormatInfo@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@5@AEAH4@Z`
- size: `2158`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1406a9998`

## callees

- `0x14001a000`
- `0x140022640`
- `0x140034404`
- `0x140041f88`
- `0x14004fd60`
- `0x14005c630`
- `0x1400634f4`
- `0x140064a48`
- `0x1400826e0`
- `0x1400db298`
- `0x1400e62ec`
- `0x14014e39c`
- `0x140163208`
- `0x14016404c`
- `0x14017902c`
- `0x140188e18`
- `0x140252220`
- `0x1404828e0`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140163587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401637f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401638b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140163a2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140163587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401637f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401638b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1401639fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140163a2e`

## string_xrefs

- `0x140163599`: `/configuration/hot_backup`
- `0x1401637ff`: `/configuration/renamed_files/file%llu/renamed_file_name`
- `0x1401632de`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x14016332c`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x140163410`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x140163474`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x1401634d8`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x14016353c`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x1401635e1`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x14016364e`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x1401636b2`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x1401637b5`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x14016387a`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x14016398d`: `onecore\vm\vmms\vss\vmvsswriterhelper.cpp`
- `0x140163606`: `/configuration/consistent_image_in_snapshot`
- `0x14016342c`: `/configuration/store_root`
- `0x1401633c8`: `/configuration/version`
- `0x14016366a`: `/configuration/renamed_files/count`
- `0x14016373a`: `/configuration/renamed_files/file%llu/original_file_name`
- `0x1401634f4`: `/configuration/vm_id`
- `0x140163490`: `/configuration/type`
- `0x140163558`: `/configuration/extension`
- `0x14016379c`: `ERROR VmVssWriterHelper::GetStringValue of original_file_name fails with (HRESULT = 0x%08lX)\n`
- `0x140163861`: `ERROR VmVssWriterHelper::GetStringValue of renamed_file_name fails with (HRESULT = 0x%08lX)\n`
- `0x140163635`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	Could not read CONFIGURATION_CONSISTENT_IMAGE_IN_SNAPSHOT_XPATH hr = %x\n`
- `0x140163699`: `ERROR VmVssWriterHelper::GetStringValue of renamed_files_count fails with (HRESULT = 0x%08lX)\n`
- `0x140163523`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	Could not read CONFIGURATION_VM_ID_XPATH hr = %x\n`
- `0x1401635c8`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	Could not read CONFIGURATION_HOT_BACKUP_XPATH hr = %x\n`
- `0x14016345b`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	Could not read CONFIGURATION_STORE_ROOT_XPATH hr = %x\n`
- `0x1401634bf`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	Could not read CONFIGURATION_TYPE_XPATH hr = %x\n`
- `0x140163310`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	Metadata is empty\n`
- `0x1401633f7`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	Could not read CONFIGURATION_VERSION_XPATH hr = %x\n`
- `0x14016326c`: `VmVssWriterHelper::ParseBackupMetadataXML\n`
- `0x1401632c5`: `ERROR VmVssWriterHelper::ParseBackupMetadataXML\n	GetBackupMetadata failed with HRESULT = 0x%X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_BOOL8 __fastcall VmVssWriterHelper::ParseBackupMetadataXML(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // r12d
  int v9; // esi
  __int64 v10; // rbx
  int v11; // esi
  int v12; // esi
  int v13; // esi
  int v14; // esi
  HLOCAL v15; // rcx
  int v16; // esi
  int v17; // esi
  int v18; // esi
  unsigned int v19; // r14d
  BOOL v20; // esi
  __m128i si128; // xmm6
  __int64 v22; // r13
  __int128 *p_Src; // rdx
  int v24; // r15d
  HLOCAL v25; // rcx
  __int128 *v26; // rdx
  int v27; // r15d
  HLOCAL v28; // rcx
  const WCHAR *v29; // rbx
  int v30; // eax
  const char *v31; // r9
  unsigned int v33; // [rsp+20h] [rbp-188h]
  int v34; // [rsp+20h] [rbp-188h]
  __int64 v35; // [rsp+30h] [rbp-178h] BYREF
  _QWORD v36[2]; // [rsp+38h] [rbp-170h] BYREF
  int v37[2]; // [rsp+48h] [rbp-160h]
  _BYTE v38[64]; // [rsp+50h] [rbp-158h] BYREF
  HLOCAL v39[2]; // [rsp+90h] [rbp-118h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-108h] BYREF
  HLOCAL hMem[2]; // [rsp+A8h] [rbp-100h] BYREF
  __int64 v42; // [rsp+B8h] [rbp-F0h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-E8h] BYREF
  __int128 Src; // [rsp+C8h] [rbp-E0h] BYREF
  __m128i v45; // [rsp+D8h] [rbp-D0h]
  HLOCAL v46[2]; // [rsp+E8h] [rbp-C0h] BYREF
  HLOCAL v47[2]; // [rsp+F8h] [rbp-B0h] BYREF
  HLOCAL v48[2]; // [rsp+108h] [rbp-A0h] BYREF
  _OWORD v49[2]; // [rsp+118h] [rbp-90h] BYREF
  _OWORD v50[2]; // [rsp+138h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  v36[0] = a4;
  *(_QWORD *)v37 = a3;
  v8 = 0;
  LODWORD(v35) = 0;
  if ( (unsigned int)VmlIsDebugTraceEnabled(49250) )
    VmlDebugTrace(49250, L"VmVssWriterHelper::ParseBackupMetadataXML\n");
  try
  {
    v40 = 0;
    v39[1] = 0;
    v39[0] = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 80LL))(a1, &v40);
    if ( v9 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n\tGetBackupMetadata failed with HRESULT = 0x%X\n",
          (unsigned int)v9);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1677,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v9,
        v33);
    }
    if ( Vml::VmBstr::Empty((Vml::VmBstr *)&v40) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(16482, L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n\tMetadata is empty\n");
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x167F,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)0xD,
        v33);
    }
    v35 = 0;
    v48[1] = 0;
    v48[0] = 0;
    v47[1] = 0;
    v47[0] = 0;
    v46[1] = 0;
    v46[0] = 0;
    v43 = 0;
    hMem[1] = 0;
    hMem[0] = 0;
    Vml::VmComPtr<IVmVirtualSwitch>::Reset(&v35, *(_QWORD *)(a2 + 8));
    Vml::VmComPtr<IVmVirtualSwitch>::Reset(a2, 0);
    Vml::VmComPtr<IVmVirtualSwitch>::Reset(a2 + 8, 0);
    v42 = 0;
    v10 = v35;
    v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v35 + 216LL))(
            v35,
            L"/configuration/version",
            &v42);
    if ( v11 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n\tCould not read CONFIGURATION_VERSION_XPATH hr = %x\n",
          (unsigned int)v11);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16A1,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v11,
        v33);
    }
    v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, HLOCAL *))(*(_QWORD *)v10 + 232LL))(
            v10,
            L"/configuration/store_root",
            v48);
    if ( v12 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n\tCould not read CONFIGURATION_STORE_ROOT_XPATH hr = %x\n",
          (unsigned int)v12);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16B1,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v12,
        v33);
    }
    v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, HLOCAL *))(*(_QWORD *)v10 + 232LL))(
            v10,
            L"/configuration/type",
            v47);
    if ( v13 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n\tCould not read CONFIGURATION_TYPE_XPATH hr = %x\n",
          (unsigned int)v13);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16BC,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v13,
        v33);
    }
    v14 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, HLOCAL *))(*(_QWORD *)v10 + 232LL))(
            v10,
            L"/configuration/vm_id",
            v46);
    if ( v14 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n\tCould not read CONFIGURATION_VM_ID_XPATH hr = %x\n",
          (unsigned int)v14);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16C9,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v14,
        v33);
    }
    if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, HLOCAL *))(*(_QWORD *)v10 + 232LL))(
           v10,
           L"/configuration/extension",
           hMem) < 0 )
    {
      v15 = hMem[0];
      hMem[0] = 0;
      if ( v15 )
        LocalFree(v15);
    }
    v16 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v10 + 208LL))(
            v10,
            L"/configuration/hot_backup",
            a5);
    if ( v16 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n\tCould not read CONFIGURATION_HOT_BACKUP_XPATH hr = %x\n",
          (unsigned int)v16);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16DE,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v16,
        v33);
    }
    if ( v42 >= 1280 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v10 + 208LL))(
              v10,
              L"/configuration/consistent_image_in_snapshot",
              a6);
      if ( v17 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
          VmlDebugTrace(
            16482,
            L"ERROR VmVssWriterHelper::ParseBackupMetadataXML\n"
             "\tCould not read CONFIGURATION_CONSISTENT_IMAGE_IN_SNAPSHOT_XPATH hr = %x\n",
            (unsigned int)v17);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16EE,
          (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
          (const char *)(unsigned int)v17,
          v33);
      }
    }
    v18 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v10 + 216LL))(
            v10,
            L"/configuration/renamed_files/count",
            &v43);
    if ( v18 < 0 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
        VmlDebugTrace(
          16482,
          L"ERROR VmVssWriterHelper::GetStringValue of renamed_files_count fails with (HRESULT = 0x%08lX)\n",
          (unsigned int)v18);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16FA,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v18,
        v33);
    }
    v19 = 0;
    v20 = 1;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v22 = v36[0];
    while ( v19 < v43 )
    {
      Src = 0;
      v45 = si128;
      LOWORD(Src) = 0;
      v50[0] = 0;
      v50[1] = si128;
      LOWORD(v50[0]) = 0;
      v49[0] = 0;
      v49[1] = si128;
      LOWORD(v49[0]) = 0;
      Vml::FormatString(&Src, (wchar_t *)L"/configuration/renamed_files/file%llu/original_file_name");
      p_Src = &Src;
      if ( v45.m128i_i64[1] > 7uLL )
        p_Src = (__int128 *)Src;
      v24 = (*(__int64 (__fastcall **)(__int64, __int128 *, HLOCAL *))(*(_QWORD *)v10 + 232LL))(v10, p_Src, v39);
      if ( v24 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
          VmlDebugTrace(
            16482,
            L"ERROR VmVssWriterHelper::GetStringValue of original_file_name fails with (HRESULT = 0x%08lX)\n",
            (unsigned int)v24);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x170B,
          (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
          (const char *)(unsigned int)v24,
          v33);
      }
      std::wstring::assign(v50, v39[0]);
      v25 = v39[0];
      v39[0] = 0;
      if ( v25 )
        LocalFree(v25);
      Vml::FormatString(&Src, (wchar_t *)L"/configuration/renamed_files/file%llu/renamed_file_name");
      v26 = &Src;
      if ( v45.m128i_i64[1] > 7uLL )
        v26 = (__int128 *)Src;
      v27 = (*(__int64 (__fastcall **)(__int64, __int128 *, HLOCAL *))(*(_QWORD *)v10 + 232LL))(v10, v26, v39);
      if ( v27 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16482) )
          VmlDebugTrace(
            16482,
            L"ERROR VmVssWriterHelper::GetStringValue of renamed_file_name fails with (HRESULT = 0x%08lX)\n",
            (unsigned int)v27);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x171B,
          (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
          (const char *)(unsigned int)v27,
          v33);
      }
      std::wstring::assign(v49, v39[0]);
      v28 = v39[0];
      v39[0] = 0;
      if ( v28 )
        LocalFree(v28);
      std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v38, v49, v50);
      v8 |= 1u;
      std::map<std::wstring,std::wstring>::insert<std::pair<std::wstring,std::wstring>,0>(v22, v36, v38);
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v38);
      std::wstring::_Tidy_deallocate(v49);
      std::wstring::_Tidy_deallocate(v50);
      std::wstring::_Tidy_deallocate(&Src);
      ++v19;
    }
    v29 = L".xml";
    if ( hMem[0] )
      LODWORD(v29) = hMem[0];
    Vml::VmGuid::Assign((Vml::VmGuid *)v36, (const unsigned __int16 *const)v46[0]);
    v30 = ConfigRepository::BuildConfigFilePath(v48[0], v47[0], (unsigned int)v36, (_DWORD)v29, *(__int64 *)v37);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x172A,
        (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
        (const char *)(unsigned int)v30,
        v34);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    if ( v46[0] )
      LocalFree(v46[0]);
    if ( v47[0] )
      LocalFree(v47[0]);
    if ( v48[0] )
      LocalFree(v48[0]);
    Vml::VmComPtr<IVssAsync>::~VmComPtr<IVssAsync>(&v35);
  }
  catch ( ... )
  {
    LODWORD(v35) = wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0x172E,
                     (unsigned int)"onecore\\vm\\vmms\\vss\\vmvsswriterhelper.cpp",
                     v31);
    v20 = (int)v35 >= 0;
  }
  if ( v39[0] )
    LocalFree(v39[0]);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v40);
  return v20;
}

```

## disassembly

```asm
0x140163208  mov     rax, rsp
0x14016320b  push    rbx
0x14016320c  push    rsi
0x14016320d  push    rdi
0x14016320e  push    r12
0x140163210  push    r13
0x140163212  push    r14
0x140163214  push    r15
0x140163216  sub     rsp, 170h
0x14016321d  movaps  xmmword ptr [rax-48h], xmm6
0x140163221  mov     rax, cs:__security_cookie
0x140163228  xor     rax, rsp
0x14016322b  mov     [rsp+1A8h+var_50], rax
0x140163233  mov     [rsp+1A8h+var_170], r9
0x140163238  mov     qword ptr [rsp+1A8h+var_160], r8
0x14016323d  mov     r14, rdx
0x140163240  mov     rbx, rcx
0x140163243  mov     r15, [rsp+1A8h+arg_20]
0x14016324b  mov     r13, [rsp+1A8h+arg_28]
0x140163253  xor     edi, edi
0x140163255  mov     r12d, edi
0x140163258  mov     dword ptr [rsp+1A8h+var_178], edi
0x14016325c  mov     esi, 0C062h
0x140163261  mov     ecx, esi
0x140163263  call    VmlIsDebugTraceEnabled
0x140163268  test    eax, eax
0x14016326a  jz      short loc_14016327A
0x14016326c  lea     rdx, aVmvsswriterhel_17; "VmVssWriterHelper::ParseBackupMetadataX"...
0x140163273  mov     ecx, esi
0x140163275  call    VmlDebugTrace
0x14016327a  mov     [rsp+1A8h+var_108], rdi
0x140163282  xorps   xmm0, xmm0
0x140163285  movups  xmmword ptr [rsp+1A8h+var_118], xmm0
0x14016328d  mov     [rsp+1A8h+var_118], rdi
0x140163295  mov     rax, [rbx]
0x140163298  lea     rdx, [rsp+1A8h+var_108]
0x1401632a0  mov     rcx, rbx
0x1401632a3  mov     rax, [rax+50h]
0x1401632a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401632ac  mov     esi, eax
0x1401632ae  test    eax, eax
0x1401632b0  jns     short loc_1401632EF
0x1401632b2  mov     ebx, 4062h
0x1401632b7  mov     ecx, ebx
0x1401632b9  call    VmlIsDebugTraceEnabled
0x1401632be  test    eax, eax
0x1401632c0  jz      short loc_1401632D3
0x1401632c2  mov     r8d, esi
0x1401632c5  lea     rdx, aErrorVmvsswrit_69; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x1401632cc  mov     ecx, ebx
0x1401632ce  call    VmlDebugTrace
0x1401632d3  mov     rcx, [rsp+1A8h]; this
0x1401632db  mov     r9d, esi; char *
0x1401632de  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x1401632e5  mov     edx, 1677h; void *
0x1401632ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401632ef  lea     rcx, [rsp+1A8h+var_108]; this
0x1401632f7  call    ?Empty@VmBstr@Vml@@QEBA_NXZ; Vml::VmBstr::Empty(void)
0x1401632fc  test    al, al
0x1401632fe  jz      short loc_14016333D
0x140163300  mov     ebx, 4062h
0x140163305  mov     ecx, ebx
0x140163307  call    VmlIsDebugTraceEnabled
0x14016330c  test    eax, eax
0x14016330e  jz      short loc_14016331E
0x140163310  lea     rdx, aErrorVmvsswrit_127; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x140163317  mov     ecx, ebx
0x140163319  call    VmlDebugTrace
0x14016331e  mov     rcx, [rsp+1A8h]; this
0x140163326  mov     r9d, 0Dh; char *
0x14016332c  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x140163333  mov     edx, 167Fh; void *
0x140163338  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14016333d  mov     [rsp+1A8h+var_178], rdi
0x140163342  xorps   xmm0, xmm0
0x140163345  movups  xmmword ptr [rsp+1A8h+var_A0], xmm0
0x14016334d  mov     [rsp+1A8h+var_A0], rdi
0x140163355  movups  xmmword ptr [rsp+1A8h+var_B0], xmm0
0x14016335d  mov     [rsp+1A8h+var_B0], rdi
0x140163365  movups  xmmword ptr [rsp+1A8h+var_C0], xmm0
0x14016336d  mov     [rsp+1A8h+var_C0], rdi
0x140163375  mov     [rsp+1A8h+var_E8], rdi
0x14016337d  movups  xmmword ptr [rsp+1A8h+hMem], xmm0
0x140163385  mov     [rsp+1A8h+hMem], rdi
0x14016338d  mov     rdx, [r14+8]
0x140163391  lea     rcx, [rsp+1A8h+var_178]
0x140163396  call    ?Reset@?$VmComPtr@UIVmVirtualSwitch@@@Vml@@QEAAXPEAUIVmVirtualSwitch@@@Z; Vml::VmComPtr<IVmVirtualSwitch>::Reset(IVmVirtualSwitch *)
0x14016339b  xor     edx, edx
0x14016339d  mov     rcx, r14
0x1401633a0  call    ?Reset@?$VmComPtr@UIVmVirtualSwitch@@@Vml@@QEAAXPEAUIVmVirtualSwitch@@@Z; Vml::VmComPtr<IVmVirtualSwitch>::Reset(IVmVirtualSwitch *)
0x1401633a5  xor     edx, edx
0x1401633a7  lea     rcx, [r14+8]
0x1401633ab  call    ?Reset@?$VmComPtr@UIVmVirtualSwitch@@@Vml@@QEAAXPEAUIVmVirtualSwitch@@@Z; Vml::VmComPtr<IVmVirtualSwitch>::Reset(IVmVirtualSwitch *)
0x1401633b0  mov     [rsp+1A8h+var_F0], rdi
0x1401633b8  mov     rbx, [rsp+1A8h+var_178]
0x1401633bd  mov     rax, [rbx]
0x1401633c0  lea     r8, [rsp+1A8h+var_F0]
0x1401633c8  lea     rdx, ?CONFIGURATION_VERSION_XPATH@@3QBGB; "/configuration/version"
0x1401633cf  mov     rcx, rbx
0x1401633d2  mov     rax, [rax+0D8h]
0x1401633d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401633de  mov     esi, eax
0x1401633e0  test    eax, eax
0x1401633e2  jns     short loc_140163421
0x1401633e4  mov     ebx, 4062h
0x1401633e9  mov     ecx, ebx
0x1401633eb  call    VmlIsDebugTraceEnabled
0x1401633f0  test    eax, eax
0x1401633f2  jz      short loc_140163405
0x1401633f4  mov     r8d, esi
0x1401633f7  lea     rdx, aErrorVmvsswrit_136; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x1401633fe  mov     ecx, ebx
0x140163400  call    VmlDebugTrace
0x140163405  mov     rcx, [rsp+1A8h]; this
0x14016340d  mov     r9d, esi; char *
0x140163410  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x140163417  mov     edx, 16A1h; void *
0x14016341c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140163421  mov     rax, [rbx]
0x140163424  lea     r8, [rsp+1A8h+var_A0]
0x14016342c  lea     rdx, ?CONFIGURATION_STORE_ROOT_XPATH@@3QBGB; "/configuration/store_root"
0x140163433  mov     rcx, rbx
0x140163436  mov     rax, [rax+0E8h]
0x14016343d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140163442  mov     esi, eax
0x140163444  test    eax, eax
0x140163446  jns     short loc_140163485
0x140163448  mov     ebx, 4062h
0x14016344d  mov     ecx, ebx
0x14016344f  call    VmlIsDebugTraceEnabled
0x140163454  test    eax, eax
0x140163456  jz      short loc_140163469
0x140163458  mov     r8d, esi
0x14016345b  lea     rdx, aErrorVmvsswrit_57; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x140163462  mov     ecx, ebx
0x140163464  call    VmlDebugTrace
0x140163469  mov     rcx, [rsp+1A8h]; this
0x140163471  mov     r9d, esi; char *
0x140163474  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x14016347b  mov     edx, 16B1h; void *
0x140163480  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140163485  mov     rax, [rbx]
0x140163488  lea     r8, [rsp+1A8h+var_B0]
0x140163490  lea     rdx, ?CONFIGURATION_TYPE_XPATH@@3QBGB; "/configuration/type"
0x140163497  mov     rcx, rbx
0x14016349a  mov     rax, [rax+0E8h]
0x1401634a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401634a6  mov     esi, eax
0x1401634a8  test    eax, eax
0x1401634aa  jns     short loc_1401634E9
0x1401634ac  mov     ebx, 4062h
0x1401634b1  mov     ecx, ebx
0x1401634b3  call    VmlIsDebugTraceEnabled
0x1401634b8  test    eax, eax
0x1401634ba  jz      short loc_1401634CD
0x1401634bc  mov     r8d, esi
0x1401634bf  lea     rdx, aErrorVmvsswrit_73; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x1401634c6  mov     ecx, ebx
0x1401634c8  call    VmlDebugTrace
0x1401634cd  mov     rcx, [rsp+1A8h]; this
0x1401634d5  mov     r9d, esi; char *
0x1401634d8  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x1401634df  mov     edx, 16BCh; void *
0x1401634e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401634e9  mov     rax, [rbx]
0x1401634ec  lea     r8, [rsp+1A8h+var_C0]
0x1401634f4  lea     rdx, ?CONFIGURATION_VM_ID_XPATH@@3QBGB; "/configuration/vm_id"
0x1401634fb  mov     rcx, rbx
0x1401634fe  mov     rax, [rax+0E8h]
0x140163505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14016350a  mov     esi, eax
0x14016350c  test    eax, eax
0x14016350e  jns     short loc_14016354D
0x140163510  mov     ebx, 4062h
0x140163515  mov     ecx, ebx
0x140163517  call    VmlIsDebugTraceEnabled
0x14016351c  test    eax, eax
0x14016351e  jz      short loc_140163531
0x140163520  mov     r8d, esi
0x140163523  lea     rdx, aErrorVmvsswrit_58; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x14016352a  mov     ecx, ebx
0x14016352c  call    VmlDebugTrace
0x140163531  mov     rcx, [rsp+1A8h]; this
0x140163539  mov     r9d, esi; char *
0x14016353c  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x140163543  mov     edx, 16C9h; void *
0x140163548  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14016354d  mov     rax, [rbx]
0x140163550  lea     r8, [rsp+1A8h+hMem]
0x140163558  lea     rdx, ?CONFIGURATION_EXTENSION_XPATH@@3QBGB; "/configuration/extension"
0x14016355f  mov     rcx, rbx
0x140163562  mov     rax, [rax+0E8h]
0x140163569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14016356e  test    eax, eax
0x140163570  jns     short loc_140163593
0x140163572  mov     rcx, [rsp+1A8h+hMem]; hMem
0x14016357a  mov     [rsp+1A8h+hMem], rdi
0x140163582  test    rcx, rcx
0x140163585  jz      short loc_140163593
0x140163587  call    cs:__imp_LocalFree
0x14016358e  nop     dword ptr [rax+rax+00h]
0x140163593  mov     rax, [rbx]
0x140163596  mov     r8, r15
0x140163599  lea     rdx, ?CONFIGURATION_HOT_BACKUP_XPATH@@3QBGB; "/configuration/hot_backup"
0x1401635a0  mov     rcx, rbx
0x1401635a3  mov     rax, [rax+0D0h]
0x1401635aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401635af  mov     esi, eax
0x1401635b1  test    eax, eax
0x1401635b3  jns     short loc_1401635F2
0x1401635b5  mov     ebx, 4062h
0x1401635ba  mov     ecx, ebx
0x1401635bc  call    VmlIsDebugTraceEnabled
0x1401635c1  test    eax, eax
0x1401635c3  jz      short loc_1401635D6
0x1401635c5  mov     r8d, esi
0x1401635c8  lea     rdx, aErrorVmvsswrit_22; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x1401635cf  mov     ecx, ebx
0x1401635d1  call    VmlDebugTrace
0x1401635d6  mov     rcx, [rsp+1A8h]; this
0x1401635de  mov     r9d, esi; char *
0x1401635e1  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x1401635e8  mov     edx, 16DEh; void *
0x1401635ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401635f2  cmp     [rsp+1A8h+var_F0], 500h
0x1401635fe  jl      short loc_14016365F
0x140163600  mov     rax, [rbx]
0x140163603  mov     r8, r13
0x140163606  lea     rdx, ?CONFIGURATION_CONSISTENT_IMAGE_IN_SNAPSHOT_XPATH@@3QBGB; "/configuration/consistent_image_in_snap"...
0x14016360d  mov     rcx, rbx
0x140163610  mov     rax, [rax+0D0h]
0x140163617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14016361c  mov     esi, eax
0x14016361e  test    eax, eax
0x140163620  jns     short loc_14016365F
0x140163622  mov     ebx, 4062h
0x140163627  mov     ecx, ebx
0x140163629  call    VmlIsDebugTraceEnabled
0x14016362e  test    eax, eax
0x140163630  jz      short loc_140163643
0x140163632  mov     r8d, esi
0x140163635  lea     rdx, aErrorVmvsswrit_72; "ERROR VmVssWriterHelper::ParseBackupMet"...
0x14016363c  mov     ecx, ebx
0x14016363e  call    VmlDebugTrace
0x140163643  mov     rcx, [rsp+1A8h]; this
0x14016364b  mov     r9d, esi; char *
0x14016364e  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x140163655  mov     edx, 16EEh; void *
0x14016365a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14016365f  mov     rax, [rbx]
0x140163662  lea     r8, [rsp+1A8h+var_E8]
0x14016366a  lea     rdx, ?CONFIGURATION_RENAMED_FILES_COUNT_XPATH@@3QBGB; "/configuration/renamed_files/count"
0x140163671  mov     rcx, rbx
0x140163674  mov     rax, [rax+0D8h]
0x14016367b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140163680  mov     esi, eax
0x140163682  test    eax, eax
0x140163684  jns     short loc_1401636C3
0x140163686  mov     ebx, 4062h
0x14016368b  mov     ecx, ebx
0x14016368d  call    VmlIsDebugTraceEnabled
0x140163692  test    eax, eax
0x140163694  jz      short loc_1401636A7
0x140163696  mov     r8d, esi
0x140163699  lea     rdx, aErrorVmvsswrit_34; "ERROR VmVssWriterHelper::GetStringValue"...
0x1401636a0  mov     ecx, ebx
0x1401636a2  call    VmlDebugTrace
0x1401636a7  mov     rcx, [rsp+1A8h]; this
0x1401636af  mov     r9d, esi; char *
0x1401636b2  lea     r8, aOnecoreVmVmmsV_89; "onecore\\vm\\vmms\\vss\\vmvsswriterhelp"...
0x1401636b9  mov     edx, 16FAh; void *
0x1401636be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401636c3  mov     r14d, edi
0x1401636c6  mov     esi, 1
0x1401636cb  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1401636d3  mov     r13, [rsp+1A8h+var_170]
0x1401636d8  mov     eax, r14d
0x1401636db  cmp     rax, [rsp+1A8h+var_E8]
0x1401636e3  jge     loc_14016392D
0x1401636e9  xorps   xmm0, xmm0
0x1401636ec  movups  [rsp+1A8h+Src], xmm0
0x1401636f4  movdqu  [rsp+1A8h+var_D0], xmm6
0x1401636fd  mov     word ptr [rsp+1A8h+Src], di
0x140163705  movups  [rsp+1A8h+var_70], xmm0
0x14016370d  movdqu  [rsp+1A8h+var_60], xmm6
0x140163716  mov     word ptr [rsp+1A8h+var_70], di
0x14016371e  movups  [rsp+1A8h+var_90], xmm0
0x140163726  movdqu  [rsp+1A8h+var_80], xmm6
0x14016372f  mov     word ptr [rsp+1A8h+var_90], di
0x140163737  mov     r8d, r14d
0x14016373a  lea     rdx, ?CONFIGURATION_RENAMED_FILES_ORIGINAL_FILE_NAME_XPATH_TEMPLATE@@3QBGB; "/configuration/renamed_files/file%llu/o"...
0x140163741  lea     rcx, [rsp+1A8h+Src]; Src
0x140163749  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14016374e  mov     rax, [rbx]
0x140163751  lea     rdx, [rsp+1A8h+Src]
0x140163759  cmp     qword ptr [rsp+1A8h+var_D0+8], 7
0x140163762  cmova   rdx, qword ptr [rsp+1A8h+Src]
0x14016376b  lea     r8, [rsp+1A8h+var_118]
0x140163773  mov     rcx, rbx
0x140163776  mov     rax, [rax+0E8h]
  ... truncated ...
```
