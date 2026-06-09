# CustomizedCalendarPropMapping_PoomToUdm(PoomOperationContext *,ulong,Udm::Vector<_SQLCEPROPVAL> const &,Udm::Vector<_SQLCEPROPVAL> const &,UdmObjectId const &,UdmPropertyValue *)

- ea: `0x18004a000`
- end: `0x18004add7`
- name: `?CustomizedCalendarPropMapping_PoomToUdm@@YAJPEAVPoomOperationContext@@KAEBV?$Vector@U_SQLCEPROPVAL@@@Udm@@1AEBUUdmObjectId@@PEAUUdmPropertyValue@@@Z`
- size: `3543`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPVOID Context)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800054c0`
- `0x18000ae80`
- `0x1800267b0`
- `0x18004a000`
- `0x18004ade0`
- `0x18004aff0`
- `0x18004b018`
- `0x18004b04c`
- `0x180072ccc`
- `0x1800810f8`
- `0x18008421c`

## import_xrefs

- `PIMSTORE!PimBinaryBodyToString` at `0x18004a3b1`
- `PIMSTORE!PimBinaryBodyToString` at `0x18004a3b1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004a84c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004a93e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004a84c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004a93e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004a801`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004a8f3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004a801`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18004a8f3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004a823`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004a915`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004a823`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004a915`
- `UserDataTypeHelperUtil!DupString` at `0x18004a53b`
- `UserDataTypeHelperUtil!DupString` at `0x18004aa4b`
- `UserDataTypeHelperUtil!DupString` at `0x18004ab71`
- `UserDataTypeHelperUtil!DupString` at `0x18004a53b`
- `UserDataTypeHelperUtil!DupString` at `0x18004aa4b`
- `UserDataTypeHelperUtil!DupString` at `0x18004ab71`

## pseudocode

```c
__int64 __fastcall CustomizedCalendarPropMapping_PoomToUdm(
        __int64 a1,
        unsigned int a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4,
        int a5,
        _DWORD *Context)
{
  _DWORD *v6; // r15
  unsigned int i; // ecx
  unsigned __int64 v10; // rax
  __int64 v11; // r8
  unsigned __int64 j; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  const struct _USPROPVAL *v15; // rsi
  unsigned __int64 v16; // r9
  unsigned __int64 k; // rcx
  int v18; // ebx
  char *v19; // rdx
  int v20; // eax
  int v22; // r11d
  unsigned __int64 m; // rdx
  char *v24; // rcx
  __int64 v25; // r8
  unsigned __int64 i4; // r14
  __int64 v27; // rax
  unsigned __int64 i2; // rcx
  __int64 v29; // rbx
  unsigned __int64 v30; // r8
  unsigned __int64 mm; // rcx
  unsigned __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // r8
  unsigned int v35; // edi
  unsigned __int64 v36; // r9
  unsigned __int64 v37; // r14
  unsigned __int64 v38; // rdx
  unsigned __int64 n; // rcx
  unsigned __int64 kk; // r14
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // r8
  unsigned int v44; // edi
  unsigned __int64 i3; // r14
  __int64 v46; // rcx
  int v47; // eax
  __int64 v48; // r8
  unsigned int v49; // edi
  int v50; // eax
  __int64 v51; // r8
  unsigned int v52; // edi
  unsigned int nn; // ecx
  const struct UdmPoomPropIdMap near *const *v54; // rdx
  unsigned __int64 ii; // rcx
  unsigned __int64 jj; // rcx
  const struct _USPROPVAL *v57; // rax
  __int64 v58; // r11
  unsigned __int16 *v59; // rax
  __int64 v60; // r8
  int v61; // ecx
  int v62; // edx
  BOOL v63; // r14d
  unsigned __int64 v64; // r11
  unsigned __int64 i1; // r8
  unsigned __int64 v66; // rcx
  __int64 v67; // r8
  int v68; // eax
  __int64 v69; // r8
  unsigned int v70; // edi
  __int64 v71; // rdx
  __int64 v72; // rdx
  int v73; // eax
  __int64 v74; // r8
  unsigned int v75; // edi
  const struct _USPROPVAL *v76; // rax
  const struct _USPROPVAL *v77; // rbx
  StorePropertyCache *v78; // rdi
  int v79; // eax
  __int64 v80; // r8
  unsigned int v81; // edi
  StorePropertyCache *v82; // rdi
  int PropertiesForStore; // eax
  __int64 v84; // r8
  unsigned int v85; // edi
  const struct _USPROPVAL *v86; // rax
  struct StorePropertySet *v87; // rax
  __int64 v88; // rdx
  int v89; // eax
  __int64 v90; // r8
  unsigned int v91; // edi
  const struct _USPROPVAL *v92; // rax
  const struct _USPROPVAL *v93; // rax
  unsigned int v94; // r11d
  const struct _USPROPVAL *v95; // rax
  int v96; // eax
  __int64 v97; // r8
  unsigned int v98; // edi
  __int64 v99; // rdx
  int v100; // eax
  __int64 v101; // r8
  unsigned int v102; // edi
  __int64 v103; // rdx
  int v104; // eax
  __int64 v105; // r8
  unsigned int v106; // edi
  __int64 v107; // rdx
  int v108; // eax
  __int64 v109; // r8
  unsigned int v110; // edi
  __int64 v111; // rax
  __int64 v112; // rdx
  int v113; // eax
  __int64 v114; // r8
  unsigned int v115; // edi
  const struct _USPROPVAL *v116; // rax
  int v117; // r11d
  const struct _USPROPVAL *PropByUnistorePropId; // rax
  int v119; // r11d
  struct StorePropertySet *v120; // [rsp+30h] [rbp-28h] BYREF
  __int64 v121; // [rsp+38h] [rbp-20h] BYREF
  const struct PoomEnumToUdmStringMap near *const *v122; // [rsp+40h] [rbp-18h]
  WINBOOL fPending; // [rsp+98h] [rbp+40h] BYREF

  v6 = Context;
  Context[1] = a2;
  if ( a2 == 36569089 )
  {
LABEL_2:
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x17uLL )
      {
        v11 = 4294901762LL;
        goto LABEL_7;
      }
      v10 = (unsigned __int64)i << 6;
      if ( *(_DWORD *)((char *)&s_Calendar_PropMap + v10) == a2 )
        break;
    }
    v11 = *(unsigned int *)((char *)&s_Calendar_PropMap + v10 + 4);
LABEL_7:
    for ( j = 0; ; ++j )
    {
      if ( j >= *a3 )
        goto LABEL_11;
      v13 = a3[1] + 24 * j;
      if ( *(_DWORD *)v13 == (_DWORD)v11 )
        break;
    }
    if ( (*(_WORD *)(v13 + 6) & 0x300) == 0 )
    {
      *v6 &= ~0x100u;
      v6[2] = *(__int16 *)(v13 + 8);
      return 0;
    }
LABEL_11:
    *v6 &= ~0x100u;
    v14 = 0;
    v6[2] = 0;
    v15 = (const struct _USPROPVAL *)a4[1];
    v16 = *a4;
    while ( 1 )
    {
      if ( v14 >= v16 )
        return 0;
      if ( *((_DWORD *)v15 + 6 * v14) == 873922625 )
        break;
      ++v14;
    }
    if ( (*((_WORD *)v15 + 12 * v14 + 3) & 0x300) != 0 )
      return 0;
    for ( k = 0; ; ++k )
    {
      v18 = 1;
      if ( k >= v16 )
        goto LABEL_27;
      v19 = (char *)v15 + 24 * k;
      if ( *(_DWORD *)v19 == 924123155 )
        break;
    }
    if ( (*((_WORD *)v19 + 3) & 0x300) != 0 || (v19[8] & 2) == 0 )
    {
LABEL_27:
      v22 = 0;
      goto LABEL_28;
    }
    v22 = 1;
LABEL_28:
    for ( m = 0; ; ++m )
    {
      if ( m >= v16 )
        goto LABEL_19;
      v24 = (char *)v15 + 24 * m;
      if ( *(_DWORD *)v24 == 1161101330 )
        break;
    }
    if ( (*((_WORD *)v24 + 3) & 0x300) != 0 || (v20 = 1, !*((_DWORD *)v24 + 2)) )
LABEL_19:
      v20 = 0;
    if ( a2 == 36700161 )
    {
      v18 = v20;
      goto LABEL_22;
    }
    if ( a2 > 0x22D0001 )
    {
      if ( a2 != 36569089 )
      {
        if ( a2 != 36634625 )
          goto LABEL_43;
        v18 = v22 | v20;
      }
      goto LABEL_22;
    }
    switch ( a2 )
    {
      case 0x22D0001u:
        PropByUnistorePropId = FindPropByUnistorePropId(v16, v15, 0x45060012u);
        if ( v119 && PropByUnistorePropId && (*((_WORD *)PropByUnistorePropId + 3) & 0x300) == 0 )
        {
          if ( !*((_WORD *)PropByUnistorePropId + 4) )
            v18 = 0;
          goto LABEL_22;
        }
        break;
      case 0x22A0001u:
      case 0x22B0001u:
        goto LABEL_22;
      case 0x22C0001u:
        v116 = FindPropByUnistorePropId(v16, v15, 0x45000012u);
        if ( v117 )
        {
          if ( v116 && (*((_WORD *)v116 + 3) & 0x300) == 0 && *((_WORD *)v116 + 4) )
            goto LABEL_22;
        }
        break;
      default:
LABEL_43:
        Log_HREvent_18(2147942487LL, 0, v11, 324);
        Log_HREvent_18(2147942487LL, 1, v25, 427);
        return 2147942487LL;
    }
    v18 = 0;
LABEL_22:
    v6[2] = v18;
    return 0;
  }
  if ( a2 > 0x2470002 )
  {
    if ( a2 > 0x2560005 )
    {
      if ( a2 == 41287682 )
      {
        *v6 &= ~0x100u;
        v36 = a3[1];
        LODWORD(v37) = 0;
        v38 = *a3;
        for ( n = 0; n < v38; ++n )
        {
          if ( *(_DWORD *)(v36 + 24 * n) == 2228235 )
          {
            if ( *(_DWORD *)(v36 + 24 * n + 8) )
            {
              for ( ii = 0; ii < v38; ++ii )
              {
                if ( *(_DWORD *)(v36 + 24 * ii) == 279576587 )
                {
                  if ( *(_DWORD *)(v36 + 24 * ii + 8) )
                  {
                    v6[2] = 2;
                    return 0;
                  }
                  break;
                }
              }
              for ( jj = 0; jj < v38; ++jj )
              {
                if ( *(_DWORD *)(v36 + 24 * jj) == 279707659 )
                {
                  if ( !*(_DWORD *)(v36 + 24 * jj + 8) )
                    goto LABEL_87;
                  v6[2] = 1;
                  return 0;
                }
              }
            }
            break;
          }
        }
LABEL_87:
        v6[2] = v37;
        return 0;
      }
      if ( a2 == 39256070 )
      {
        for ( kk = 0; kk < *a3; ++kk )
        {
          v41 = a3[1] + 24 * kk;
          if ( *(_DWORD *)v41 == 29491300 )
          {
            if ( (*(_WORD *)(v41 + 6) & 0x300) == 0 )
            {
              *v6 &= ~0x100u;
              v42 = PoomToUdmAttendeesBlob((const struct _SQLCEBLOB *)(v41 + 8), (struct UDMBLOB *)(v6 + 2));
              v44 = v42;
              if ( v42 < 0 )
              {
                Log_HREvent_18((unsigned int)v42, 1, v43, 576);
                return v44;
              }
            }
            return 0;
          }
        }
        return 0;
      }
      if ( a2 != 41549829 && a2 != 40632322 && a2 != 41156610 )
        goto LABEL_197;
    }
    else
    {
      if ( a2 == 39190533 )
      {
        v95 = FindPropByUnistorePropId(*a3, (const struct _USPROPVAL *)a3[1], dword_18015C804);
        if ( !v95 || (*((_WORD *)v95 + 3) & 0x300) != 0 )
          return 0;
        v96 = DupString(v6 + 2, *((_QWORD *)v95 + 1));
        v98 = v96;
        if ( v96 >= 0 )
        {
LABEL_105:
          *v6 &= ~0x100u;
          return 0;
        }
        else
        {
          Log_HREvent_18((unsigned int)v96, 1, v97, 451);
          return v98;
        }
      }
      if ( a2 > 0x24E0002 )
      {
        if ( a2 == 38731777 )
        {
          v93 = FindPropByUnistorePropId(*a3, (const struct _USPROPVAL *)a3[1], 0x1C20064u);
          if ( v93 )
          {
            if ( (*((_WORD *)v93 + 3) & 0x300) != 0 )
            {
              *v6 &= ~0x100u;
              v18 = 0;
              goto LABEL_22;
            }
            if ( *((_DWORD *)v93 + 2) > v94 )
              v94 = **((_DWORD **)v93 + 2);
          }
          *v6 &= ~0x100u;
          v18 = v94 != 0;
          goto LABEL_22;
        }
        if ( a2 == 39059463 )
        {
          v92 = FindPropByUnistorePropId(*a3, (const struct _USPROPVAL *)a3[1], 0xE090013u);
          if ( v92 )
          {
            *v6 &= ~0x100u;
            v6[3] = 11;
            v6[2] = 0;
            v6[4] = *((_DWORD *)v92 + 2);
          }
          return 0;
        }
        goto LABEL_197;
      }
      if ( a2 != 38666242 && a2 != 38273025 && a2 != 38338561 )
      {
        if ( a2 == 38469637 )
        {
          v30 = a3[1];
          for ( mm = 0; mm < *a3; ++mm )
          {
            v32 = v30 + 24 * mm;
            if ( *(_DWORD *)v32 == 1966180 )
            {
              if ( (*(_WORD *)(v32 + 6) & 0x300) != 0 )
                return 0;
              Context = 0;
              v33 = PimBinaryBodyToString(v32 + 8, &Context);
              v35 = v33;
              if ( v33 < 0 )
              {
                Log_HREvent_18((unsigned int)v33, 1, v34, 587);
                return v35;
              }
              v50 = DupString(v6 + 2, Context);
              v52 = v50;
              if ( v50 < 0 )
              {
                Log_HREvent_18((unsigned int)v50, 1, v51, 589);
                return v52;
              }
              goto LABEL_105;
            }
          }
          return 0;
        }
        goto LABEL_197;
      }
    }
LABEL_107:
    v37 = 0;
    for ( nn = 0; nn < 0x36uLL; ++nn )
    {
      v54 = &s_Appointment_PropMap + 8 * (unsigned __int64)nn;
      if ( *(_DWORD *)v54 == a2 )
      {
        v64 = a3[1];
        for ( i1 = 0; i1 < *a3; ++i1 )
        {
          v66 = v64 + 24 * i1;
          if ( *(_DWORD *)v66 == *((_DWORD *)v54 + 1) )
          {
            if ( (*(_WORD *)(v66 + 6) & 0x300) != 0 )
              return 0;
            *v6 &= ~0x100u;
            if ( a2 == 41156610 )
            {
              v6[2] = *(_DWORD *)(v66 + 8);
              while ( v37 < *a3 )
              {
                v71 = a3[1] + 24 * v37;
                if ( *(_DWORD *)v71 == 1191378963 )
                {
                  if ( (*(_WORD *)(v71 + 6) & 0x300) == 0 )
                  {
                    v111 = *(_QWORD *)(v71 + 8);
                    if ( v111 == 3 || v111 == 6 )
                    {
                      v112 = *(unsigned int *)(v66 + 8);
                      v122 = &s_PoomWeekOfMonthToAppointmentWeekOfMonth;
                      v121 = 5;
                      v113 = UnistoreEnumToUdmEnum(&v121, v112, v6 + 2);
                      v115 = v113;
                      if ( v113 < 0 )
                      {
                        Log_HREvent_18((unsigned int)v113, 1, v114, 510);
                        return v115;
                      }
                    }
                  }
                  return 0;
                }
                ++v37;
              }
              return 0;
            }
            if ( a2 == 38141954 )
            {
              v72 = *(unsigned int *)(v66 + 8);
              v122 = &s_BusyStatusToAppointmentBusyStatusMap;
              v121 = 5;
              v73 = UnistoreEnumToUdmEnum(&v121, v72, v6 + 2);
              v75 = v73;
              if ( v73 >= 0 )
                return 0;
              Log_HREvent_18((unsigned int)v73, 1, v74, 481);
              return v75;
            }
            if ( a2 <= 0x24E0002 )
            {
              if ( a2 != 38666242 )
              {
                if ( a2 != 38207490 )
                {
                  LOBYTE(v37) = *(_DWORD *)(v66 + 8) == 0;
                  goto LABEL_87;
                }
                v99 = *(unsigned int *)(v66 + 8);
                v122 = &s_SensitivityToAppointmentSensitivityMap;
                v121 = 4;
                v100 = UnistoreEnumToUdmEnum(&v121, v99, v6 + 2);
                v102 = v100;
                if ( v100 < 0 )
                {
                  Log_HREvent_18((unsigned int)v100, 1, v101, 484);
                  return v102;
                }
                return 0;
              }
              v103 = *(unsigned int *)(v66 + 8);
              v122 = &s_RecipientStatusToAppointmentParticipantResponseMap;
              v121 = 5;
              v104 = UnistoreEnumToUdmEnum(&v121, v103, v6 + 2);
              v106 = v104;
              if ( v104 >= 0 )
                return 0;
              Log_HREvent_18((unsigned int)v104, 1, v105, 487);
              return v106;
            }
            else if ( a2 == 41549829 )
            {
              v67 = *(unsigned int *)(v66 + 8);
              v122 = &s_PoomCalendarTypeToAppointmentCalendarIdentifier;
              v121 = 15;
              v68 = PoomEnumToUdmString(&v121, v54, v67, v6 + 2);
              v70 = v68;
              if ( v68 >= 0 )
                return 0;
              Log_HREvent_18((unsigned int)v68, 1, v69, 493);
              return v70;
            }
            else
            {
              v107 = *(unsigned int *)(v66 + 8);
              v122 = &s_RecurrenceTypeToAppointmentRecurrenceUnit;
              v121 = 7;
              v108 = UnistoreEnumToUdmEnum(&v121, v107, v6 + 2);
              v110 = v108;
              if ( v108 >= 0 )
                return 0;
              Log_HREvent_18((unsigned int)v108, 1, v109, 490);
              return v110;
            }
          }
        }
        return 0;
      }
    }
    return 0;
  }
  if ( a2 == 38207490 )
    goto LABEL_107;
  if ( a2 > 0x22C0001 )
  {
    if ( a2 <= 0x2310005 )
    {
      if ( a2 == 36765701 )
      {
        for ( i2 = 0; i2 < *a3; ++i2 )
        {
          v29 = a3[1] + 24 * i2;
          if ( *(_DWORD *)v29 == 131075 )
          {
            if ( (*(_WORD *)(v29 + 6) & 0x300) != 0 )
              return 0;
            v120 = 0;
            fPending = 0;
            Context = 0;
            InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, (LPVOID *)&Context);
            v82 = (StorePropertyCache *)Context;
            if ( !Context )
            {
              qword_18015EA70 = 0;
              InitializeCriticalSectionEx(&stru_18015EA78, 0, 0);
              utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(qword_18015EAA0);
              v82 = (StorePropertyCache *)&qword_18015EA70;
              v121 = 0;
              InitOnceComplete(&stru_18015EA68, 0, &qword_18015EA70);
              tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v121);
            }
            PropertiesForStore = StorePropertyCache::GetPropertiesForStore(v82, *(_DWORD *)(v29 + 8), &v120);
            v85 = PropertiesForStore;
            if ( PropertiesForStore < 0 )
            {
              Log_HREvent_18((unsigned int)PropertiesForStore, 1, v84, 617);
              return v85;
            }
            v88 = *((_QWORD *)v120 + 1);
            if ( !v88 )
              return 0;
            v89 = DupString(v6 + 2, v88);
            v91 = v89;
            if ( v89 >= 0 )
              goto LABEL_105;
            Log_HREvent_18((unsigned int)v89, 1, v90, 621);
            return v91;
          }
        }
        return 0;
      }
      if ( a2 == 36503553 || a2 == 36634625 || a2 == 36700161 )
        goto LABEL_2;
      goto LABEL_197;
    }
    if ( a2 == 37945348 )
    {
      for ( i3 = 0; i3 < *a3; ++i3 )
      {
        v46 = a3[1] + 24 * i3;
        if ( *(_DWORD *)v46 == 4784192 )
        {
          if ( (*(_WORD *)(v46 + 6) & 0x300) == 0 )
          {
            v47 = UnistorePropToUdmProp((const struct _USPROPVAL *)v46, (struct UdmPropertyValue *)v6);
            v49 = v47;
            if ( v47 < 0 )
            {
              Log_HREvent_18((unsigned int)v47, 1, v48, 441);
              return v49;
            }
          }
          return 0;
        }
      }
      return 0;
    }
    if ( a2 == 38141954 )
      goto LABEL_107;
LABEL_197:
    Log_HREvent_18(2147942487LL, 0, a3, 629);
    return 2147942487LL;
  }
  if ( a2 == 36438017 )
    goto LABEL_2;
  if ( a2 == 36241415 )
  {
    v76 = FindPropByUnistorePropId(*a3, (const struct _USPROPVAL *)a3[1], 0x20003u);
    v77 = v76;
    if ( !v76 || (*((_WORD *)v76 + 3) & 0x300) != 0 )
      return 0;
    *v6 &= ~0x100u;
    v120 = 0;
    fPending = 0;
    Context = 0;
    InitOnceBeginInitialize(&stru_18015EA68, 0, &fPending, (LPVOID *)&Context);
    v78 = (StorePropertyCache *)Context;
    if ( !Context )
    {
      qword_18015EA70 = 0;
      InitializeCriticalSectionEx(&stru_18015EA78, 0, 0);
      utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(qword_18015EAA0);
      v78 = (StorePropertyCache *)&qword_18015EA70;
      v121 = 0;
      InitOnceComplete(&stru_18015EA68, 0, &qword_18015EA70);
      tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v121);
    }
    v79 = StorePropertyCache::GetPropertiesForStore(v78, *((_DWORD *)v77 + 2), &v120);
    v81 = v79;
    if ( v79 >= 0 )
    {
      v87 = v120;
      v6[2] = 0;
      v6[3] = 41;
      v6[4] = *(_DWORD *)v87;
      return 0;
    }
    Log_HREvent_18((unsigned int)v79, 1, v80, 398);
    return v81;
  }
  else
  {
    if ( a2 > 0x2290007 )
    {
      if ( a2 == 36306945 || a2 == 36372481 )
        goto LABEL_2;
      goto LABEL_197;
    }
    if ( a2 != 33751041 )
    {
      if ( a2 == 33685511 )
      {
        v86 = FindPropByUnistorePropId(*a3, (const struct _USPROPVAL *)a3[1], 0x10003u);
        if ( v86 )
        {
          *v6 &= ~0x100u;
          v6[2] = *((_DWORD *)v86 + 2);
          v6[3] = 10;
          v6[4] = *((_DWORD *)v86 + 2);
        }
        return 0;
      }
      if ( a2 == 36110338 )
      {
        for ( i4 = 0; i4 < *a3; ++i4 )
        {
          v27 = a3[1] + 24 * i4;
          if ( *(_DWORD *)v27 == dword_18015C800 )
          {
            if ( (*(_WORD *)(v27 + 6) & 0x300) != 0 )
              return 0;
            *v6 &= ~0x100u;
            v6[2] = *(_DWORD *)(v27 + 8);
            return 0;
          }
        }
        return 0;
      }
      goto LABEL_197;
    }
    v57 = FindPropByUnistorePropId(*a3, (const struct _USPROPVAL *)a3[1], 0x10B1001Fu);
    *v6 &= ~0x100u;
    if ( v57 && (*((_WORD *)v57 + 3) & 0x300) == 0 && *(_QWORD *)(v58 + 8) )
    {
      v59 = (unsigned __int16 *)*((_QWORD *)v57 + 1);
      v60 = *(_QWORD *)(v58 + 16) - (_QWORD)v59;
      do
      {
        v61 = *(unsigned __int16 *)((char *)v59 + v60);
        v62 = *v59 - v61;
        if ( v62 )
          break;
        ++v59;
      }
      while ( v61 );
      v63 = v62 == 0;
    }
    else
    {
      v63 = 0;
    }
    v6[2] = v63;
    return 0;
  }
}

```

## disassembly

```asm
0x18004a000  push    rbp
0x18004a002  push    rbx
0x18004a003  push    rsi
0x18004a004  push    rdi
0x18004a005  push    r14
0x18004a007  push    r15
0x18004a009  mov     rbp, rsp
0x18004a00c  sub     rsp, 58h
0x18004a010  mov     r15, [rbp+Context]
0x18004a014  mov     rbx, r9
0x18004a017  mov     rsi, r8
0x18004a01a  mov     r10d, edx
0x18004a01d  mov     r11, rcx
0x18004a020  mov     [r15+4], edx
0x18004a024  cmp     edx, 22E0001h
0x18004a02a  jnz     loc_18004A1F7
0x18004a030  xor     r14d, r14d
0x18004a033  lea     r8, __ImageBase
0x18004a03a  mov     ecx, r14d
0x18004a03d  nop     dword ptr [rax]
0x18004a040  mov     eax, ecx
0x18004a042  cmp     rax, 17h
0x18004a046  jnb     short loc_18004A05E
0x18004a048  shl     rax, 6
0x18004a04c  cmp     [rax+r8+159CC0h], r10d
0x18004a054  jz      loc_18004A2D3
0x18004a05a  inc     ecx
0x18004a05c  jmp     short loc_18004A040
0x18004a05e  mov     r8d, 0FFFF0002h
0x18004a064  mov     r9, [rsi+8]
0x18004a068  mov     rcx, r14
0x18004a06b  cmp     rcx, [rsi]
0x18004a06e  jnb     short loc_18004A087
0x18004a070  lea     rax, [rcx+rcx*2]
0x18004a074  cmp     [r9+rax*8], r8d
0x18004a078  lea     rdx, [r9+rax*8]
0x18004a07c  jz      loc_18004A109
0x18004a082  inc     rcx
0x18004a085  jmp     short loc_18004A06B
0x18004a087  mov     edi, 300h
0x18004a08c  and     dword ptr [r15], 0FFFFFEFFh
0x18004a093  mov     rcx, r14
0x18004a096  mov     [r15+8], r14d
0x18004a09a  mov     rsi, [rbx+8]
0x18004a09e  mov     r9, [rbx]
0x18004a0a1  cmp     rcx, r9
0x18004a0a4  jnb     short loc_18004A0FA
0x18004a0a6  lea     rax, [rcx+rcx*2]
0x18004a0aa  cmp     dword ptr [rsi+rax*8], 34170041h
0x18004a0b1  lea     rdx, [rsi+rax*8]
0x18004a0b5  jnz     short loc_18004A136
0x18004a0b7  test    [rdx+6], di
0x18004a0bb  jnz     short loc_18004A0FA
0x18004a0bd  mov     rcx, r14
0x18004a0c0  mov     ebx, 1
0x18004a0c5  cmp     rcx, r9
0x18004a0c8  jnb     short loc_18004A13E
0x18004a0ca  lea     rax, [rcx+rcx*2]
0x18004a0ce  cmp     dword ptr [rsi+rax*8], 37150013h
0x18004a0d5  lea     rdx, [rsi+rax*8]
0x18004a0d9  jz      loc_18004A176
0x18004a0df  inc     rcx
0x18004a0e2  jmp     short loc_18004A0C0
0x18004a0e4  mov     eax, r14d
0x18004a0e7  cmp     r10d, 2300001h
0x18004a0ee  jnz     loc_18004A187
0x18004a0f4  mov     ebx, eax
0x18004a0f6  mov     [r15+8], ebx
0x18004a0fa  xor     eax, eax
0x18004a0fc  add     rsp, 58h
0x18004a100  pop     r15
0x18004a102  pop     r14
0x18004a104  pop     rdi
0x18004a105  pop     rsi
0x18004a106  pop     rbx
0x18004a107  pop     rbp
0x18004a108  retn
0x18004a109  mov     edi, 300h
0x18004a10e  test    [rdx+6], di
0x18004a112  jnz     loc_18004A08C
0x18004a118  and     dword ptr [r15], 0FFFFFEFFh
0x18004a11f  movsx   eax, word ptr [rdx+8]
0x18004a123  mov     [r15+8], eax
0x18004a127  xor     eax, eax
0x18004a129  add     rsp, 58h
0x18004a12d  pop     r15
0x18004a12f  pop     r14
0x18004a131  pop     rdi
0x18004a132  pop     rsi
0x18004a133  pop     rbx
0x18004a134  pop     rbp
0x18004a135  retn
0x18004a136  inc     rcx
0x18004a139  jmp     loc_18004A0A1
0x18004a13e  mov     r11d, r14d
0x18004a141  mov     rdx, r14
0x18004a144  cmp     rdx, r9
0x18004a147  jnb     short loc_18004A0E4
0x18004a149  lea     rax, [rdx+rdx*2]
0x18004a14d  cmp     dword ptr [rsi+rax*8], 45350012h
0x18004a154  lea     rcx, [rsi+rax*8]
0x18004a158  jnz     short loc_18004A171
0x18004a15a  test    [rcx+6], di
0x18004a15e  jnz     short loc_18004A0E4
0x18004a160  mov     eax, ebx
0x18004a162  cmp     [rcx+8], r14d
0x18004a166  jnz     loc_18004A0E7
0x18004a16c  jmp     loc_18004A0E4
0x18004a171  inc     rdx
0x18004a174  jmp     short loc_18004A144
0x18004a176  test    [rdx+6], di
0x18004a17a  jnz     short loc_18004A13E
0x18004a17c  test    byte ptr [rdx+8], 2
0x18004a180  jz      short loc_18004A13E
0x18004a182  mov     r11d, ebx
0x18004a185  jmp     short loc_18004A141
0x18004a187  cmp     r10d, 22D0001h
0x18004a18e  ja      loc_18004A2AF
0x18004a194  jz      loc_18004ADAF
0x18004a19a  cmp     r10d, 22A0001h
0x18004a1a1  jz      loc_18004A0F6
0x18004a1a7  cmp     r10d, 22B0001h
0x18004a1ae  jz      loc_18004A0F6
0x18004a1b4  cmp     r10d, 22C0001h
0x18004a1bb  jz      loc_18004AD77
0x18004a1c1  xor     edx, edx
0x18004a1c3  mov     ecx, 80070057h
0x18004a1c8  mov     r9d, 144h
0x18004a1ce  call    Log_HREvent_18
0x18004a1d3  mov     r9d, 1ABh
0x18004a1d9  mov     edx, ebx
0x18004a1db  mov     ecx, 80070057h
0x18004a1e0  call    Log_HREvent_18
0x18004a1e5  mov     eax, 80070057h
0x18004a1ea  add     rsp, 58h
0x18004a1ee  pop     r15
0x18004a1f0  pop     r14
0x18004a1f2  pop     rdi
0x18004a1f3  pop     rsi
0x18004a1f4  pop     rbx
0x18004a1f5  pop     rbp
0x18004a1f6  retn
0x18004a1f7  cmp     r10d, 2470002h
0x18004a1fe  ja      loc_18004A320
0x18004a204  jz      loc_18004A56E
0x18004a20a  cmp     r10d, 22C0001h
0x18004a211  ja      loc_18004A2E0
0x18004a217  jz      loc_18004A030
0x18004a21d  cmp     r10d, 2290007h
0x18004a224  jz      loc_18004A7AD
0x18004a22a  ja      loc_18004A9D7
0x18004a230  cmp     r10d, 2030001h
0x18004a237  jz      loc_18004A601
0x18004a23d  cmp     r10d, 2020007h
0x18004a244  jz      loc_18004A97F
0x18004a24a  cmp     r10d, 2270002h
0x18004a251  jnz     loc_18004ABB4
0x18004a257  mov     rdx, [r8+8]
0x18004a25b  xor     r14d, r14d
0x18004a25e  mov     rcx, [r8]
0x18004a261  mov     r8d, cs:dword_18015C800
0x18004a268  cmp     r14, rcx
0x18004a26b  jnb     loc_18004A0FA
0x18004a271  lea     rax, [r14+r14*2]
0x18004a275  cmp     [rdx+rax*8], r8d
0x18004a279  lea     rax, [rdx+rax*8]
0x18004a27d  jnz     loc_18004A3E2
0x18004a283  mov     edi, 300h
0x18004a288  test    [rax+6], di
0x18004a28c  jnz     loc_18004A0FA
0x18004a292  and     dword ptr [r15], 0FFFFFEFFh
0x18004a299  mov     eax, [rax+8]
0x18004a29c  mov     [r15+8], eax
0x18004a2a0  xor     eax, eax
0x18004a2a2  add     rsp, 58h
0x18004a2a6  pop     r15
0x18004a2a8  pop     r14
0x18004a2aa  pop     rdi
0x18004a2ab  pop     rsi
0x18004a2ac  pop     rbx
0x18004a2ad  pop     rbp
0x18004a2ae  retn
0x18004a2af  cmp     r10d, 22E0001h
0x18004a2b6  jz      loc_18004A0F6
0x18004a2bc  cmp     r10d, 22F0001h
0x18004a2c3  jnz     loc_18004A1C1
0x18004a2c9  mov     ebx, eax
0x18004a2cb  or      ebx, r11d
0x18004a2ce  jmp     loc_18004A0F6
0x18004a2d3  mov     r8d, [rax+r8+159CC4h]
0x18004a2db  jmp     loc_18004A064
0x18004a2e0  cmp     r10d, 2310005h
0x18004a2e7  ja      loc_18004A4C7
0x18004a2ed  jnz     loc_18004A9F6
0x18004a2f3  mov     rdx, [r8+8]
0x18004a2f7  xor     r14d, r14d
0x18004a2fa  mov     ecx, r14d
0x18004a2fd  cmp     rcx, [r8]
0x18004a300  jnb     loc_18004A0FA
0x18004a306  lea     rax, [rcx+rcx*2]
0x18004a30a  cmp     dword ptr [rdx+rax*8], 20003h
0x18004a311  lea     rbx, [rdx+rax*8]
0x18004a315  jz      loc_18004AA22
0x18004a31b  inc     rcx
0x18004a31e  jmp     short loc_18004A2FD
0x18004a320  cmp     r10d, 2560005h
0x18004a327  ja      loc_18004A3EA
0x18004a32d  jz      loc_18004AB3E
0x18004a333  cmp     r10d, 24E0002h
0x18004a33a  ja      loc_18004AA9F
0x18004a340  jz      loc_18004A56E
0x18004a346  cmp     r10d, 2480001h
0x18004a34d  jz      loc_18004A56E
0x18004a353  cmp     r10d, 2490001h
0x18004a35a  jz      loc_18004A56E
0x18004a360  cmp     r10d, 24B0005h
0x18004a367  jnz     loc_18004ABB4
0x18004a36d  mov     r8, [r8+8]
0x18004a371  xor     r14d, r14d
0x18004a374  mov     ecx, r14d
0x18004a377  cmp     rcx, [rsi]
0x18004a37a  jnb     loc_18004A0FA
0x18004a380  lea     rax, [rcx+rcx*2]
0x18004a384  cmp     dword ptr [r8+rax*8], 1E0064h
0x18004a38c  lea     rdx, [r8+rax*8]
0x18004a390  jnz     loc_18004A43F
0x18004a396  mov     edi, 300h
0x18004a39b  test    [rdx+6], di
0x18004a39f  jnz     loc_18004A0FA
0x18004a3a5  lea     rcx, [rdx+8]
0x18004a3a9  mov     [rbp+Context], r14
0x18004a3ad  lea     rdx, [rbp+Context]
0x18004a3b1  call    cs:__imp_PimBinaryBodyToString
0x18004a3b7  mov     edi, eax
0x18004a3b9  test    eax, eax
0x18004a3bb  jns     loc_18004A533
0x18004a3c1  mov     edx, 1
0x18004a3c6  mov     r9d, 24Bh
0x18004a3cc  mov     ecx, eax
0x18004a3ce  call    Log_HREvent_18
0x18004a3d3  mov     eax, edi
0x18004a3d5  add     rsp, 58h
0x18004a3d9  pop     r15
0x18004a3db  pop     r14
0x18004a3dd  pop     rdi
0x18004a3de  pop     rsi
0x18004a3df  pop     rbx
0x18004a3e0  pop     rbp
0x18004a3e1  retn
0x18004a3e2  inc     r14
0x18004a3e5  jmp     loc_18004A268
0x18004a3ea  cmp     r10d, 2760002h
0x18004a3f1  jnz     short loc_18004A447
0x18004a3f3  and     dword ptr [r15], 0FFFFFEFFh
0x18004a3fa  mov     r9, [r8+8]
0x18004a3fe  xor     r14d, r14d
0x18004a401  mov     rdx, [r8]
0x18004a404  mov     ecx, r14d
0x18004a407  cmp     rcx, rdx
0x18004a40a  jnb     short loc_18004A42C
0x18004a40c  lea     rax, [rcx+rcx*2]
0x18004a410  cmp     dword ptr [r9+rax*8], 22000Bh
0x18004a418  lea     r8, [r9+rax*8]
0x18004a41c  jnz     loc_18004A4BF
0x18004a422  cmp     [r8+8], r14d
0x18004a426  jnz     loc_18004A5B7
0x18004a42c  mov     [r15+8], r14d
0x18004a430  xor     eax, eax
0x18004a432  add     rsp, 58h
0x18004a436  pop     r15
0x18004a438  pop     r14
0x18004a43a  pop     rdi
0x18004a43b  pop     rsi
0x18004a43c  pop     rbx
0x18004a43d  pop     rbp
0x18004a43e  retn
0x18004a43f  inc     rcx
0x18004a442  jmp     loc_18004A377
0x18004a447  cmp     r10d, 2570006h
0x18004a44e  jnz     loc_18004A561
0x18004a454  mov     rdx, [r8+8]
0x18004a458  xor     r14d, r14d
0x18004a45b  cmp     r14, [r8]
0x18004a45e  jnb     loc_18004A0FA
0x18004a464  lea     rax, [r14+r14*2]
0x18004a468  cmp     dword ptr [rdx+rax*8], 1C20064h
0x18004a46f  lea     rcx, [rdx+rax*8]
0x18004a473  jnz     loc_18004A5A7
0x18004a479  mov     edi, 300h
0x18004a47e  test    [rcx+6], di
0x18004a482  jnz     loc_18004A0FA
0x18004a488  and     dword ptr [r15], 0FFFFFEFFh
0x18004a48f  lea     rdx, [r15+8]; struct UDMBLOB *
0x18004a493  add     rcx, 8; struct _SQLCEBLOB *
0x18004a497  call    ?PoomToUdmAttendeesBlob@@YAJAEBU_SQLCEBLOB@@PEAUUDMBLOB@@@Z; PoomToUdmAttendeesBlob(_SQLCEBLOB const &,UDMBLOB *)
0x18004a49c  mov     edi, eax
0x18004a49e  test    eax, eax
0x18004a4a0  jns     loc_18004A0FA
0x18004a4a6  mov     edx, 1
0x18004a4ab  mov     r9d, 240h
  ... truncated ...
```
