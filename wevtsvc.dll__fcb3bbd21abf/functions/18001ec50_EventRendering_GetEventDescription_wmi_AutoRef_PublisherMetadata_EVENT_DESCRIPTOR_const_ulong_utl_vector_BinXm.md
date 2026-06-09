# EventRendering::GetEventDescription(wmi::AutoRef<PublisherMetadata> &,_EVENT_DESCRIPTOR const &,ulong,utl::vector<BinXmlVariantHolder,utl::allocator<BinXmlVariantHolder>> &,ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,tag_RpcInfo &)

- ea: `0x18001ec50`
- end: `0x18001fe75`
- name: `?GetEventDescription@EventRendering@@YAXAEAV?$AutoRef@VPublisherMetadata@@@wmi@@AEBU_EVENT_DESCRIPTOR@@KAEAV?$vector@VBinXmlVariantHolder@@V?$allocator@VBinXmlVariantHolder@@@utl@@@utl@@KAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@6@AEAUtag_RpcInfo@@@Z`
- size: `4645`
- prototype: `void __fastcall(PublisherMetadata **, __int64, int, _QWORD *, unsigned int, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `26`
- tags: `file_ops, registry_config`

## callers

- `0x18001ea14`
- `0x18008e3b8`
- `0x1800b0f88`

## callees

- `0x18000bf10`
- `0x18000c540`
- `0x180014bd0`
- `0x180016a64`
- `0x180017b60`
- `0x18001c320`
- `0x18001cdb0`
- `0x18001ec50`
- `0x1800204d8`
- `0x180020d88`
- `0x1800210c0`
- `0x18002afa8`
- `0x18002d408`
- `0x18002d6dc`
- `0x18003068c`
- `0x180031098`
- `0x180031140`
- `0x1800660ac`
- `0x180083004`
- `0x180092008`
- `0x18009aee0`
- `0x18009b590`
- `0x18009bb88`
- `0x1800a7b60`
- `0x1800a7cd8`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ecd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ecd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001edf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001edf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f63c`
- `api-ms-win-core-localization-l1-2-4!SetThreadPreferredUILanguages2` at `0x18001efaf`
- `api-ms-win-core-localization-l1-2-4!SetThreadPreferredUILanguages2` at `0x18001efaf`
- `api-ms-win-core-localization-l1-2-4!RestoreThreadPreferredUILanguages` at `0x18001edea`
- `api-ms-win-core-localization-l1-2-4!RestoreThreadPreferredUILanguages` at `0x18001edea`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18001ef6b`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18001ef6b`

## pseudocode

```c
void __fastcall EventRendering::GetEventDescription(
        PublisherMetadata **a1,
        __int64 a2,
        int a3,
        _QWORD *a4,
        unsigned int a5,
        _QWORD *a6,
        __int64 a7)
{
  RTL_SRWLOCK *v8; // rax
  unsigned int v9; // r12d
  PublisherMetadata *v10; // r13
  unsigned int v11; // eax
  unsigned int v12; // r13d
  int v13; // eax
  struct _EVENT_DESCRIPTOR *v14; // r13
  PublisherMetadata *v15; // rcx
  unsigned int MessageStringForResourceType; // eax
  int v17; // esi
  void *v18; // rcx
  unsigned __int16 v19; // r12
  unsigned int MessageStringFromSystem; // eax
  int v21; // esi
  _QWORD *v22; // rsi
  __int64 v23; // rax
  _DWORD *v24; // rsi
  int v25; // eax
  unsigned __int64 v26; // rax
  unsigned int v27; // esi
  unsigned __int16 v28; // r13
  unsigned int v29; // ecx
  __int64 v30; // rax
  PublisherMetadata *v31; // rax
  unsigned int v32; // r15d
  unsigned __int16 v33; // r13
  unsigned int v34; // eax
  int v35; // esi
  PublisherMetadata *v36; // rcx
  unsigned int v37; // eax
  int v38; // esi
  __int64 v39; // rax
  DWORD LastError; // esi
  PVOID *v41; // rcx
  DWORD v42; // esi
  PVOID *v43; // r10
  _QWORD *v44; // rsi
  __int64 v45; // rax
  int v46; // [rsp+50h] [rbp-B0h] BYREF
  void *v47[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h]
  int v49; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+74h] [rbp-8Ch]
  char v51; // [rsp+7Ch] [rbp-84h]
  __int128 pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  int v54; // [rsp+98h] [rbp-68h]
  int v55; // [rsp+9Ch] [rbp-64h]
  int v56; // [rsp+A0h] [rbp-60h]
  _DWORD v57[2]; // [rsp+A8h] [rbp-58h] BYREF
  void *v58; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v59; // [rsp+B8h] [rbp-48h]
  __int64 v60; // [rsp+C8h] [rbp-38h] BYREF
  struct _EVENT_DESCRIPTOR v61; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v62; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v63; // [rsp+E8h] [rbp-18h]
  PSRWLOCK SRWLock; // [rsp+F0h] [rbp-10h] BYREF
  char v65; // [rsp+F8h] [rbp-8h]
  __int64 *v66; // [rsp+100h] [rbp+0h] BYREF
  char v67; // [rsp+108h] [rbp+8h]
  void *v68[2]; // [rsp+110h] [rbp+10h] BYREF
  char v69; // [rsp+120h] [rbp+20h] BYREF
  WCHAR Name[88]; // [rsp+130h] [rbp+30h] BYREF

  v62 = a4;
  v57[0] = a3;
  *(_QWORD *)&v61.Id = a2;
  if ( a3 == -1 )
  {
    if ( a5 != 8 )
      goto LABEL_3;
LABEL_105:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 87);
    }
    *(_OWORD *)v47 = 0;
    v48 = 0;
    v49 = 87;
    v50 = 0x553FFFFFFFFLL;
    throw (EvtException *)v47;
  }
  if ( a5 != 8 )
    goto LABEL_105;
LABEL_3:
  v8 = (RTL_SRWLOCK *)*a1;
  if ( !*a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 15002);
    }
    *(_OWORD *)v47 = 0;
    v48 = 0;
    v49 = 15002;
    v50 = 0x558FFFFFFFFLL;
    throw (EvtException *)v47;
  }
  SRWLock = v8 + 42;
  AcquireSRWLockExclusive(v8 + 42);
  v9 = 1;
  v65 = 1;
  v60 = 0;
  v66 = &v60;
  v67 = 1;
  v10 = *a1;
  if ( *((_BYTE *)*a1 + 371) )
  {
    LOWORD(v46) = *((_WORD *)v10 + 184);
    if ( !(_WORD)v46 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 87);
      }
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v49 = 87;
      v50 = 0x590FFFFFFFFLL;
      throw (EvtException *)v47;
    }
  }
  else
  {
    memset_0(Name, 0, 0xACu);
    v25 = LCIDToLocaleName(*((unsigned __int16 *)v10 + 184), Name, 85, 0x8000000u);
    if ( !v25 )
    {
      LastError = GetLastError();
      v41 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids,
          *((unsigned __int16 *)*a1 + 184),
          LastError);
        v41 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !LastError )
        LastError = 1287;
      if ( v41 != &WPP_GLOBAL_Control && (*((_DWORD *)v41 + 7) & 0x800000) != 0 && *((_BYTE *)v41 + 25) >= 2u )
        WPP_SF_d(v41[2], 53, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, LastError);
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v49 = LastError;
      v50 = 0x56CFFFFFFFFLL;
      throw (EvtException *)v47;
    }
    if ( (unsigned __int64)v25 >= 0x56 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 111);
      }
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v49 = 111;
      v50 = 0x571FFFFFFFFLL;
      throw (EvtException *)v47;
    }
    v26 = v25;
    if ( v26 >= 86 )
      _report_rangecheckfailure();
    Name[v26] = 0;
    v46 = 0;
    if ( !(unsigned int)SetThreadPreferredUILanguages2(8, Name, &v46, &v60) )
    {
      v42 = GetLastError();
      if ( !v42 )
        v42 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, v42);
      }
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v49 = v42;
      v50 = 0x57AFFFFFFFFLL;
      throw (EvtException *)v47;
    }
    if ( v46 != 1 )
    {
      v43 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dDS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)&WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids,
            v46,
            *((_WORD *)*a1 + 184),
            (__int64)Name);
          v43 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v43 != &WPP_GLOBAL_Control && (*((_DWORD *)v43 + 7) & 0x800000) != 0 && *((_BYTE *)v43 + 25) >= 2u )
          WPP_SF_d(v43[2], 57, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 87);
      }
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v49 = 87;
      v50 = 0x580FFFFFFFFLL;
      throw (EvtException *)v47;
    }
    LOWORD(v46) = 0;
  }
  v11 = PublisherMetadata::EnsureResourceFilesAreLoaded(*a1);
  v12 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, v11);
    }
    v47[0] = (void *)&byte_1800EC961;
    v47[1] = 0;
    v48 = 0;
    v49 = v12;
    v50 = -1;
    v51 = 0;
    throw (EvtException *)v47;
  }
  utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(&v58);
  v13 = v57[0];
  if ( v57[0] == -1 )
  {
    v14 = *(struct _EVENT_DESCRIPTOR **)&v61.Id;
    IsReserved(*(_QWORD *)&v61.Id, a5);
    v61 = *v14;
    if ( !(unsigned __int8)GetMessageId(&v61, (__int64)&v58, a7) )
      goto LABEL_164;
  }
  else
  {
    v57[0] = 0;
    v57[1] = v13;
    LOBYTE(v57[0]) = *((_BYTE *)*a1 + 373);
    if ( !(unsigned __int8)utl::vector<MessageIdType,utl::allocator<MessageIdType>>::_PushBackOne<MessageIdType const &>(
                             &v58,
                             v57) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
      }
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v49 = 14;
      v50 = 0x5A3FFFFFFFFLL;
      throw (EvtException *)v47;
    }
    v14 = *(struct _EVENT_DESCRIPTOR **)&v61.Id;
  }
  if ( a5 == 1 )
  {
    v19 = v46;
    if ( *((_BYTE *)*a1 + 373) )
      MessageStringFromSystem = GetMessageStringFromSystem(*((unsigned int *)v58 + 1), (unsigned __int16)v46, a6);
    else
      MessageStringFromSystem = PublisherMetadata::GetMessageStringForResourceType(
                                  (unsigned int)*a1,
                                  0,
                                  *((_DWORD *)v58 + 1),
                                  (unsigned __int16)v46,
                                  (__int64)a6);
    v21 = MessageStringFromSystem;
    if ( MessageStringFromSystem == -2147024579 )
      goto LABEL_16;
    if ( MessageStringFromSystem == -2147009791 )
      goto LABEL_214;
    if ( MessageStringFromSystem )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids,
          MessageStringFromSystem);
      }
      pExceptionObject = 0;
      v53 = 0;
      v54 = v21;
      v55 = -1;
      v56 = 1484;
      throw (EvtException *)&pExceptionObject;
    }
    v22 = v62;
    if ( !*((_BYTE *)*a1 + 370) && (v14->Keyword & 0x80000000000000LL) == 0 )
      SubstituteInsertsWithOutTypeOrMap(a1, v14, v19, v62);
    *(_QWORD *)&v61.Id = 0;
    v57[0] = 0;
    utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v47);
    LOBYTE(v46) = 0;
    if ( !(unsigned __int8)utl::vector<bool,utl::allocator<bool>>::_Resize<bool,0>(
                             v47,
                             (__int64)(v22[1] - *v22) >> 4,
                             &v46) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
      }
      pExceptionObject = 0;
      v53 = 0;
      v54 = 14;
      v55 = -1;
      v56 = 1507;
      throw (EvtException *)&pExceptionObject;
    }
    v62 = (_QWORD *)*v22;
    v63 = (__int64)(v22[1] - (_QWORD)v62) >> 4;
    ResolveInserts(
      (unsigned int)*a1,
      v19,
      (unsigned int)&v62,
      (_DWORD)a6,
      (__int64)&v61,
      3,
      (__int64)v57,
      a7,
      (__int64)v47);
    v23 = a6[1] - *a6;
    if ( v23
      && *(_WORD *)(*a6 + 2 * (v23 >> 1) - 2)
      && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a6,
                             0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
      }
      pExceptionObject = 0;
      v53 = 0;
      v54 = 14;
      v55 = -1;
      v56 = 1525;
      throw (EvtException *)&pExceptionObject;
    }
    if ( v47[0] != (void *)-1LL )
    {
      v47[1] = v47[0];
      operator delete(v47[0]);
    }
  }
  else
  {
    if ( a5 != 2 )
    {
      if ( a5 == 3 )
      {
        LODWORD(v15) = (_DWORD)g_winmetaPublisherMetadata;
        if ( !*(_BYTE *)v58 )
          v15 = *a1;
        MessageStringForResourceType = PublisherMetadata::GetMessageStringForResourceType(
                                         (_DWORD)v15,
                                         3,
                                         *((_DWORD *)v58 + 1),
                                         (unsigned __int16)v46,
                                         (__int64)a6);
        v17 = MessageStringForResourceType;
        if ( MessageStringForResourceType == -2147024579 )
          goto LABEL_16;
        if ( MessageStringForResourceType != -2147009791 )
        {
          if ( MessageStringForResourceType )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                66,
                &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids,
                MessageStringForResourceType);
            }
            pExceptionObject = 0;
            v53 = 0;
            v54 = v17;
            v55 = -1;
            v56 = 1592;
            throw (EvtException *)&pExceptionObject;
          }
          v39 = a6[1] - *a6;
          if ( v39
            && *(_WORD *)(*a6 + 2 * (v39 >> 1) - 2)
            && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                   a6,
                                   0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
            }
            pExceptionObject = 0;
            v53 = 0;
            v54 = 14;
            v55 = -1;
            v56 = 1599;
            throw (EvtException *)&pExceptionObject;
          }
          goto LABEL_33;
        }
        goto LABEL_214;
      }
      if ( a5 == 4 || a5 == 5 )
      {
        v24 = v58;
        v31 = g_winmetaPublisherMetadata;
        if ( !*(_BYTE *)v58 )
          v31 = *a1;
        *(_QWORD *)&v61.Id = v31;
        v32 = 0;
        v33 = v46;
        while ( v32 < (unsigned __int64)((v59 - (_BYTE *)v24) >> 3) )
        {
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v68);
          v34 = PublisherMetadata::GetMessageStringForResourceType(
                  *(_DWORD *)&v61.Id,
                  2,
                  v24[2 * v32 + 1],
                  v33,
                  (__int64)v68);
          v35 = v34;
          if ( v34 == -2147024579 )
          {
            *(_QWORD *)a7 = 15027;
            *(_DWORD *)(a7 + 8) = 0;
            if ( v68[0] != &v69 )
              operator delete(v68[0]);
            goto LABEL_17;
          }
          if ( v34 == -2147009791 )
          {
            *(_QWORD *)a7 = 15033;
            *(_DWORD *)(a7 + 8) = 0;
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v68);
            goto LABEL_164;
          }
          if ( v34 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, v34);
            }
            pExceptionObject = 0;
            v53 = 0;
            v54 = v35;
            v55 = -1;
            v56 = 1634;
            throw (EvtException *)&pExceptionObject;
          }
          if ( v68[0] != v68[1]
            && (!(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(a6)
             || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                    a6,
                                    0)) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
            }
            pExceptionObject = 0;
            v53 = 0;
            v54 = 14;
            v55 = -1;
            v56 = 1642;
            throw (EvtException *)&pExceptionObject;
          }
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v68);
          ++v32;
          v24 = v58;
        }
        if ( a6[1] == *a6 )
          goto LABEL_34;
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 a6,
                                 0) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
          }
          pExceptionObject = 0;
          v53 = 0;
          v54 = 14;
          v55 = -1;
          v56 = 1651;
          throw (EvtException *)&pExceptionObject;
        }
        goto LABEL_33;
      }
      if ( a5 != 6 && a5 != 7 )
      {
        if ( a5 != 8 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 87);
          }
          *(_OWORD *)v47 = 0;
          v48 = 0;
          v49 = 87;
          v50 = 0x6C2FFFFFFFFLL;
          throw (EvtException *)v47;
        }
        v27 = 0;
        v28 = v46;
        do
        {
          if ( !v9 )
            break;
          v9 = PublisherMetadata::GetMessageStringForResourceType(
                 (unsigned int)*a1,
                 v27,
                 *((_DWORD *)v58 + 1),
                 v28,
                 (__int64)a6);
          v29 = v27 + 1;
          if ( !v9 )
            v29 = v27;
          v27 = v29;
        }
        while ( v29 < 4 );
        if ( v9 != -2147024579 )
        {
          if ( v9 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, v9);
            }
            *(_OWORD *)v47 = 0;
            v48 = 0;
            v49 = v9;
            v50 = 0x698FFFFFFFFLL;
            throw (EvtException *)v47;
          }
          if ( !v27 )
          {
            *(_QWORD *)&v61.Id = 0;
            v57[0] = 0;
            utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(v47);
            LOBYTE(v46) = 0;
            v44 = v62;
            if ( !(unsigned __int8)utl::vector<bool,utl::allocator<bool>>::_Resize<bool,0>(
                                     v47,
                                     (__int64)(v62[1] - *v62) >> 4,
                                     &v46) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
              }
              pExceptionObject = 0;
              v53 = 0;
              v54 = 14;
              v55 = -1;
              v56 = 1704;
              throw (EvtException *)&pExceptionObject;
            }
            v62 = (_QWORD *)*v44;
            v63 = (__int64)(v44[1] - (_QWORD)v62) >> 4;
            ResolveInserts(
              (unsigned int)*a1,
              v28,
              (unsigned int)&v62,
              (_DWORD)a6,
              (__int64)&v61,
              3,
              (__int64)v57,
              a7,
              (__int64)v47);
            utl::vector<MessageIdType,utl::allocator<MessageIdType>>::_Uninit(v47);
          }
          v30 = a6[1] - *a6;
          if ( v30
            && *(_WORD *)(*a6 + 2 * (v30 >> 1) - 2)
            && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                   a6,
                                   0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
            }
            pExceptionObject = 0;
            v53 = 0;
            v54 = 14;
            v55 = -1;
            v56 = 1723;
            throw (EvtException *)&pExceptionObject;
          }
          goto LABEL_33;
        }
LABEL_214:
        *(_QWORD *)a7 = 15033;
        *(_DWORD *)(a7 + 8) = 0;
LABEL_164:
        utl::vector<MessageIdType,utl::allocator<MessageIdType>>::_Uninit(&v58);
        tlx::_UndoSolo__EventRendering::GetEventDescription_::_2_::_lambda_1___::__UndoSolo__EventRendering::GetEventDescription_::_2_::_lambda_1___(&v66);
        utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&SRWLock);
        return;
      }
    }
    LODWORD(v36) = (_DWORD)g_winmetaPublisherMetadata;
    if ( !*(_BYTE *)v58 )
      v36 = *a1;
    v37 = PublisherMetadata::GetMessageStringForResourceType(
            (_DWORD)v36,
            2,
            *((_DWORD *)v58 + 1),
            (unsigned __int16)v46,
            (__int64)a6);
    v38 = v37;
    if ( v37 == -2147024579 )
    {
LABEL_16:
      *(_QWORD *)a7 = 15027;
      *(_DWORD *)(a7 + 8) = 0;
LABEL_17:
      v18 = v58;
      if ( v58 == (void *)-1LL )
        goto LABEL_20;
      v59 = v58;
      goto LABEL_19;
    }
    if ( v37 == -2147009791 )
      goto LABEL_214;
    if ( v37 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, v37);
      }
      pExceptionObject = 0;
      v53 = 0;
      v54 = v38;
      v55 = -1;
      v56 = 1556;
      throw (EvtException *)&pExceptionObject;
    }
    v45 = a6[1] - *a6;
    if ( v45
      && *(_WORD *)(*a6 + 2 * (v45 >> 1) - 2)
      && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a6,
                             0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids, 14);
      }
      pExceptionObject = 0;
      v53 = 0;
      v54 = 14;
      v55 = -1;
      v56 = 1563;
      throw (EvtException *)&pExceptionObject;
    }
  }
LABEL_33:
  v24 = v58;
LABEL_34:
  if ( v24 == (_DWORD *)-1LL )
    goto LABEL_20;
  v59 = v24;
  v18 = v24;
LABEL_19:
  operator delete(v18);
LABEL_20:
  if ( v60 )
    RestoreThreadPreferredUILanguages();
  ReleaseSRWLockExclusive(SRWLock);
}

```

## disassembly

```asm
0x18001ec50  push    rbp
0x18001ec52  push    rbx
0x18001ec53  push    rsi
0x18001ec54  push    rdi
0x18001ec55  push    r12
0x18001ec57  push    r13
0x18001ec59  push    r14
0x18001ec5b  push    r15
0x18001ec5d  lea     rbp, [rsp-0F8h]
0x18001ec65  sub     rsp, 1F8h
0x18001ec6c  mov     rax, cs:__security_cookie
0x18001ec73  xor     rax, rsp
0x18001ec76  mov     [rbp+130h+var_50], rax
0x18001ec7d  mov     [rbp+130h+var_150], r9
0x18001ec81  mov     dword ptr [rbp+130h+var_188], r8d
0x18001ec85  mov     qword ptr [rbp+130h+var_160.Id], rdx
0x18001ec89  mov     r15, rcx
0x18001ec8c  mov     r14, [rbp+130h+arg_28]
0x18001ec93  mov     rdi, [rbp+130h+arg_30]
0x18001ec9a  or      r12d, 0FFFFFFFFh
0x18001ec9e  mov     esi, [rbp+130h+arg_20]
0x18001eca4  cmp     r8d, r12d
0x18001eca7  jnz     loc_18001F423
0x18001ecad  cmp     esi, 8
0x18001ecb0  jz      loc_18001F42C
0x18001ecb6  mov     rax, [rcx]
0x18001ecb9  xor     ebx, ebx
0x18001ecbb  test    rax, rax
0x18001ecbe  jz      loc_18001F49C
0x18001ecc4  add     rax, 150h
0x18001ecca  mov     [rbp+130h+SRWLock], rax
0x18001ecce  mov     rcx, rax; SRWLock
0x18001ecd1  call    cs:__imp_AcquireSRWLockExclusive
0x18001ecd7  lea     r12d, [rbx+1]
0x18001ecdb  mov     [rbp+130h+var_138], r12b
0x18001ecdf  mov     [rbp+130h+var_168], rbx
0x18001ece3  lea     rax, [rbp+130h+var_168]
0x18001ece7  mov     [rbp+130h+var_130], rax
0x18001eceb  mov     [rbp+130h+var_128], r12b
0x18001ecef  mov     r13, [r15]
0x18001ecf2  cmp     [r13+173h], bl
0x18001ecf9  jz      loc_18001EF42
0x18001ecff  movzx   eax, word ptr [r13+170h]
0x18001ed07  mov     word ptr [rsp+230h+var_1E0], ax
0x18001ed0c  test    ax, ax
0x18001ed0f  jz      loc_18001F77E
0x18001ed15  mov     rcx, [r15]; this
0x18001ed18  call    ?EnsureResourceFilesAreLoaded@PublisherMetadata@@QEAAKXZ; PublisherMetadata::EnsureResourceFilesAreLoaded(void)
0x18001ed1d  mov     r13d, eax
0x18001ed20  test    eax, eax
0x18001ed22  jnz     loc_18001F7EF
0x18001ed28  lea     rcx, [rbp+130h+var_180]; void *
0x18001ed2c  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18001ed31  nop
0x18001ed32  mov     eax, dword ptr [rbp+130h+var_188]
0x18001ed35  or      r13d, 0FFFFFFFFh
0x18001ed39  cmp     eax, r13d
0x18001ed3c  jz      loc_18001F0F5
0x18001ed42  mov     [rbp+130h+var_188], rbx
0x18001ed46  mov     dword ptr [rbp+130h+var_188+4], eax
0x18001ed49  mov     rax, [r15]
0x18001ed4c  mov     cl, [rax+175h]
0x18001ed52  mov     byte ptr [rbp+130h+var_188], cl
0x18001ed55  lea     rdx, [rbp+130h+var_188]
0x18001ed59  lea     rcx, [rbp+130h+var_180]
0x18001ed5d  call    ??$_PushBackOne@AEBUMessageIdType@@@?$vector@UMessageIdType@@V?$allocator@UMessageIdType@@@utl@@@utl@@AEAA_NAEBUMessageIdType@@@Z; utl::vector<MessageIdType,utl::allocator<MessageIdType>>::_PushBackOne<MessageIdType const &>(MessageIdType const &)
0x18001ed62  test    al, al
0x18001ed64  jz      loc_18001F863
0x18001ed6a  mov     r13, qword ptr [rbp+130h+var_160.Id]
0x18001ed6e  sub     esi, 1
0x18001ed71  jz      loc_18001EE1E
0x18001ed77  sub     esi, 1
0x18001ed7a  jz      loc_18001F1EB
0x18001ed80  sub     esi, 1
0x18001ed83  jnz     loc_18001EFD5
0x18001ed89  mov     r8, [rbp+130h+var_180]
0x18001ed8d  cmp     [r8], bl
0x18001ed90  mov     rcx, cs:?g_winmetaPublisherMetadata@@3V?$AutoRef@VPublisherMetadata@@@wmi@@A; wmi::AutoRef<PublisherMetadata> g_winmetaPublisherMetadata
0x18001ed97  jz      loc_18001FC5D
0x18001ed9d  mov     [rsp+230h+var_210], r14
0x18001eda2  movzx   r9d, word ptr [rsp+230h+var_1E0]
0x18001eda8  mov     r8d, [r8+4]
0x18001edac  mov     edx, 3
0x18001edb1  call    ?GetMessageStringForResourceType@PublisherMetadata@@QEBAJW4PUB_MSG_RESOURCE_TYPE@1@KGAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PublisherMetadata::GetMessageStringForResourceType(PublisherMetadata::PUB_MSG_RESOURCE_TYPE,ulong,ushort,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001edb6  mov     esi, eax
0x18001edb8  cmp     eax, 8007013Dh
0x18001edbd  jnz     loc_18001F32A
0x18001edc3  mov     qword ptr [rdi], 3AB3h
0x18001edca  mov     [rdi+8], ebx
0x18001edcd  mov     rcx, [rbp+130h+var_180]; void *
0x18001edd1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001edd5  jz      short loc_18001EDE1
0x18001edd7  mov     [rbp+130h+var_178], rcx
0x18001eddb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ede0  nop
0x18001ede1  mov     rcx, [rbp+130h+var_168]
0x18001ede5  test    rcx, rcx
0x18001ede8  jz      short loc_18001EDF1
0x18001edea  call    cs:__imp_RestoreThreadPreferredUILanguages
0x18001edf0  nop
0x18001edf1  mov     rcx, [rbp+130h+SRWLock]; SRWLock
0x18001edf5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001edfb  mov     rcx, [rbp+130h+var_50]
0x18001ee02  xor     rcx, rsp; StackCookie
0x18001ee05  call    __security_check_cookie
0x18001ee0a  add     rsp, 1F8h
0x18001ee11  pop     r15
0x18001ee13  pop     r14
0x18001ee15  pop     r13
0x18001ee17  pop     r12
0x18001ee19  pop     rdi
0x18001ee1a  pop     rsi
0x18001ee1b  pop     rbx
0x18001ee1c  pop     rbp
0x18001ee1d  retn
0x18001ee1e  mov     rcx, [r15]
0x18001ee21  movzx   r12d, word ptr [rsp+230h+var_1E0]
0x18001ee27  cmp     [rcx+175h], bl
0x18001ee2d  jz      loc_18001F139
0x18001ee33  mov     rcx, [rbp+130h+var_180]
0x18001ee37  mov     r8, r14
0x18001ee3a  movzx   edx, r12w
0x18001ee3e  mov     ecx, [rcx+4]
0x18001ee41  call    GetMessageStringFromSystem
0x18001ee46  mov     esi, eax
0x18001ee48  cmp     eax, 8007013Dh
0x18001ee4d  jz      loc_18001EDC3
0x18001ee53  cmp     eax, 80073B01h
0x18001ee58  jz      loc_18001FD68
0x18001ee5e  test    eax, eax
0x18001ee60  jnz     loc_18001FD77
0x18001ee66  mov     rax, [r15]
0x18001ee69  mov     rsi, [rbp+130h+var_150]
0x18001ee6d  cmp     [rax+172h], bl
0x18001ee73  jz      loc_18001FDDF
0x18001ee79  mov     qword ptr [rbp+130h+var_160.Id], rbx
0x18001ee7d  mov     dword ptr [rbp+130h+var_188], ebx
0x18001ee80  lea     rcx, [rsp+230h+var_1D8]; void *
0x18001ee85  call    ??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ; utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)
0x18001ee8a  nop
0x18001ee8b  mov     byte ptr [rsp+230h+var_1E0], bl
0x18001ee8f  mov     rdx, [rsi+8]
0x18001ee93  sub     rdx, [rsi]
0x18001ee96  sar     rdx, 4
0x18001ee9a  lea     r8, [rsp+230h+var_1E0]
0x18001ee9f  lea     rcx, [rsp+230h+var_1D8]
0x18001eea4  call    ??$_Resize@_N$0A@@?$vector@_NV?$allocator@_N@utl@@@utl@@AEAA_N_KAEB_N@Z; utl::vector<bool,utl::allocator<bool>>::_Resize<bool,0>(unsigned __int64,bool const &)
0x18001eea9  test    al, al
0x18001eeab  jz      loc_18001FE0A
0x18001eeb1  mov     rax, [rsi]
0x18001eeb4  mov     [rbp+130h+var_150], rax
0x18001eeb8  mov     rcx, [rsi+8]
0x18001eebc  sub     rcx, rax
0x18001eebf  sar     rcx, 4
0x18001eec3  mov     [rbp+130h+var_148], rcx
0x18001eec7  lea     rax, [rsp+230h+var_1D8]
0x18001eecc  mov     [rsp+230h+var_1F0], rax
0x18001eed1  mov     [rsp+230h+var_1F8], rdi
0x18001eed6  lea     rax, [rbp+130h+var_188]
0x18001eeda  mov     [rsp+230h+var_200], rax
0x18001eedf  mov     dword ptr [rsp+230h+var_208], 3
0x18001eee7  lea     rax, [rbp+130h+var_160]
0x18001eeeb  mov     [rsp+230h+var_210], rax
0x18001eef0  mov     r9, r14
0x18001eef3  lea     r8, [rbp+130h+var_150]
0x18001eef7  movzx   edx, r12w
0x18001eefb  mov     rcx, [r15]
0x18001eefe  call    ?ResolveInserts@@YAXPEBVPublisherMetadata@@GV?$span@$$CBVBinXmlVariantHolder@@$0?0@utl@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@3@AEA_KKAEAKAEAUtag_RpcInfo@@AEAV?$vector@_NV?$allocator@_N@utl@@@3@@Z; ResolveInserts(PublisherMetadata const *,ushort,utl::span<BinXmlVariantHolder const,-1>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,unsigned __int64 &,ulong,ulong &,tag_RpcInfo &,utl::vector<bool,utl::allocator<bool>> &)
0x18001ef03  mov     rcx, [r14]
0x18001ef06  mov     rax, [r14+8]
0x18001ef0a  sub     rax, rcx
0x18001ef0d  jnz     loc_18001F29F
0x18001ef13  mov     rcx, [rsp+230h+var_1D8]; void *
0x18001ef18  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ef1c  jz      short loc_18001EF28
0x18001ef1e  mov     [rsp+230h+var_1D8+8], rcx
0x18001ef23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ef28  mov     rsi, [rbp+130h+var_180]
0x18001ef2c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001ef30  jz      loc_18001EDE1
0x18001ef36  mov     [rbp+130h+var_178], rsi
0x18001ef3a  mov     rcx, rsi
0x18001ef3d  jmp     loc_18001EDDB
0x18001ef42  xor     edx, edx; Val
0x18001ef44  mov     r8d, 0ACh; Size
0x18001ef4a  lea     rcx, [rbp+130h+Name]; void *
0x18001ef4e  call    memset_0
0x18001ef53  movzx   ecx, word ptr [r13+170h]; Locale
0x18001ef5b  mov     r9d, 8000000h; dwFlags
0x18001ef61  mov     r8d, 55h ; 'U'; cchName
0x18001ef67  lea     rdx, [rbp+130h+Name]; lpName
0x18001ef6b  call    cs:__imp_LCIDToLocaleName
0x18001ef71  test    eax, eax
0x18001ef73  jz      loc_18001F50C
0x18001ef79  cdqe
0x18001ef7b  cmp     rax, 56h ; 'V'
0x18001ef7f  jnb     loc_18001F5CB
0x18001ef85  add     rax, rax
0x18001ef88  cmp     rax, 0ACh
0x18001ef8e  jnb     loc_18001F778
0x18001ef94  mov     [rbp+rax+130h+Name], bx
0x18001ef99  mov     [rsp+230h+var_1E0], ebx
0x18001ef9d  lea     r9, [rbp+130h+var_168]
0x18001efa1  lea     r8, [rsp+230h+var_1E0]
0x18001efa6  lea     rdx, [rbp+130h+Name]
0x18001efaa  mov     ecx, 8
0x18001efaf  call    cs:__imp_SetThreadPreferredUILanguages2
0x18001efb5  test    eax, eax
0x18001efb7  jz      loc_18001F63C
0x18001efbd  mov     r9d, [rsp+230h+var_1E0]
0x18001efc2  cmp     r9d, r12d
0x18001efc5  jnz     loc_18001F6BC
0x18001efcb  mov     word ptr [rsp+230h+var_1E0], bx
0x18001efd0  jmp     loc_18001ED15
0x18001efd5  sub     esi, 1
0x18001efd8  jz      loc_18001F156
0x18001efde  sub     esi, 1
0x18001efe1  jz      loc_18001F156
0x18001efe7  sub     esi, 1
0x18001efea  jz      loc_18001F1EB
0x18001eff0  sub     esi, 1
0x18001eff3  jz      loc_18001F1EB
0x18001eff9  cmp     esi, 1
0x18001effc  jnz     loc_18001F907
0x18001f002  mov     esi, ebx
0x18001f004  movzx   r13d, word ptr [rsp+230h+var_1E0]
0x18001f00a  test    r12d, r12d
0x18001f00d  jz      short loc_18001F03C
0x18001f00f  mov     [rsp+230h+var_210], r14
0x18001f014  movzx   r9d, r13w
0x18001f018  mov     r8, [rbp+130h+var_180]
0x18001f01c  mov     r8d, [r8+4]
0x18001f020  mov     edx, esi
0x18001f022  mov     rcx, [r15]
0x18001f025  call    ?GetMessageStringForResourceType@PublisherMetadata@@QEBAJW4PUB_MSG_RESOURCE_TYPE@1@KGAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PublisherMetadata::GetMessageStringForResourceType(PublisherMetadata::PUB_MSG_RESOURCE_TYPE,ulong,ushort,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18001f02a  mov     r12d, eax
0x18001f02d  lea     ecx, [rsi+1]
0x18001f030  test    eax, eax
0x18001f032  cmovz   ecx, esi
0x18001f035  mov     esi, ecx
0x18001f037  cmp     ecx, 4
0x18001f03a  jb      short loc_18001F00A
0x18001f03c  cmp     r12d, 8007013Dh
0x18001f043  jz      loc_18001FD68
0x18001f049  test    r12d, r12d
0x18001f04c  jnz     loc_18001F978
0x18001f052  test    esi, esi
0x18001f054  jz      loc_18001F9E7
0x18001f05a  mov     rcx, [r14]
0x18001f05d  mov     rax, [r14+8]
0x18001f061  sub     rax, rcx
0x18001f064  jz      loc_18001EF28
0x18001f06a  sar     rax, 1
0x18001f06d  cmp     [rcx+rax*2-2], bx
0x18001f072  jz      loc_18001EF28
0x18001f078  xor     edx, edx
0x18001f07a  mov     rcx, r14
0x18001f07d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18001f082  test    al, al
0x18001f084  jnz     loc_18001EF28
0x18001f08a  lea     rdi, WPP_GLOBAL_Control
0x18001f091  mov     esi, 0Eh
0x18001f096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f09d  cmp     rcx, rdi
0x18001f0a0  jz      short loc_18001F0C7
0x18001f0a2  test    dword ptr [rcx+1Ch], 800000h
0x18001f0a9  jz      short loc_18001F0C7
0x18001f0ab  cmp     byte ptr [rcx+19h], 2
0x18001f0af  jb      short loc_18001F0C7
0x18001f0b1  lea     edx, [rsi+3Bh]
0x18001f0b4  mov     r9d, esi
0x18001f0b7  lea     r8, WPP_9af7b4fdf9643c34d429c258a20cedef_Traceguids
0x18001f0be  mov     rcx, [rcx+10h]
0x18001f0c2  call    WPP_SF_d
0x18001f0c7  xorps   xmm0, xmm0
0x18001f0ca  movdqu  [rbp+130h+pExceptionObject], xmm0
0x18001f0cf  mov     [rbp+130h+var_1A0], rbx
0x18001f0d3  mov     [rbp+130h+var_198], esi
0x18001f0d6  mov     [rbp+130h+var_194], 0FFFFFFFFh
0x18001f0dd  mov     [rbp+130h+var_190], 6BBh
0x18001f0e4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001f0eb  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x18001f0ef  call    _CxxThrowException_0
0x18001f0f5  mov     edx, esi
0x18001f0f7  mov     r13, qword ptr [rbp+130h+var_160.Id]
0x18001f0fb  mov     rcx, r13
0x18001f0fe  call    IsReserved
0x18001f103  movups  xmm0, xmmword ptr [r13+0]
0x18001f108  movdqu  xmmword ptr [rbp+130h+var_160.Id], xmm0
0x18001f10d  mov     [rsp+230h+var_208], rdi; __int64
0x18001f112  lea     rcx, [rbp+130h+var_180]
0x18001f116  mov     [rsp+230h+var_210], rcx; __int64
0x18001f11b  mov     r9d, esi
0x18001f11e  mov     r8, r15
0x18001f121  mov     dl, al
0x18001f123  lea     rcx, [rbp+130h+var_160]; struct _EVENT_DESCRIPTOR *
0x18001f127  call    GetMessageId
0x18001f12c  test    al, al
0x18001f12e  jnz     loc_18001ED6E
0x18001f134  jmp     loc_18001F8E5
  ... truncated ...
```
