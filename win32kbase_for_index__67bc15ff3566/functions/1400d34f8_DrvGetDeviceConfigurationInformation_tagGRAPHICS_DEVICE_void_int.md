# DrvGetDeviceConfigurationInformation(tagGRAPHICS_DEVICE *,void *,int)

- ea: `0x1400d34f8`
- end: `0x1400d417b`
- name: `?DrvGetDeviceConfigurationInformation@@YAXPEAUtagGRAPHICS_DEVICE@@PEAXH@Z`
- size: `3203`
- prototype: `void __fastcall(PVOID Context, PCWSTR Path, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400d27e0`
- `0x14018f010`

## callees

- `0x14000d76c`
- `0x14007b930`
- `0x1400d34f8`
- `0x1400d4e00`
- `0x1401b32d4`
- `0x1401c5560`
- `0x1401f16ac`
- `0x1402388e0`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d3ee3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d3ee3`
- `ntoskrnl!ZwQueryKey` at `0x1400d39f6`
- `ntoskrnl!ZwQueryKey` at `0x1400d3a49`
- `ntoskrnl!ZwQueryKey` at `0x1400d39f6`
- `ntoskrnl!ZwQueryKey` at `0x1400d3a49`
- `ntoskrnl!RtlCompareMemory` at `0x1400d4049`
- `ntoskrnl!RtlCompareMemory` at `0x1400d40cf`
- `ntoskrnl!RtlCompareMemory` at `0x1400d4049`
- `ntoskrnl!RtlCompareMemory` at `0x1400d40cf`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d37e6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d3b8e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d3c65`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d3eb1`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d37e6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d3b8e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d3c65`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400d3eb1`

## pseudocode

```c
void __fastcall DrvGetDeviceConfigurationInformation(unsigned int *Context, WCHAR *Path, int a3)
{
  int v3; // r14d
  WCHAR *v4; // rsi
  NTSTATUS RegistryValues; // edi
  bool v7; // zf
  struct _RTL_QUERY_REGISTRY_TABLE *p_QueryTable; // r8
  unsigned int v9; // r9d
  struct _DEVICE_OBJECT *v10; // rcx
  const wchar_t *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  WCHAR *v14; // rsi
  _DWORD *v15; // r14
  __int64 v16; // r15
  unsigned int v17; // edx
  unsigned int v18; // ecx
  unsigned int v19; // r13d
  WCHAR *v20; // rax
  int v21; // eax
  char v22; // r14
  size_t v23; // rdx
  struct _RTL_QUERY_REGISTRY_TABLE *v24; // r8
  __int64 v25; // rax
  __int64 v26; // r13
  __int64 v27; // rax
  WCHAR *v28; // r15
  const wchar_t *v29; // rsi
  int v30; // r12d
  __int64 i; // rax
  unsigned int v32; // r14d
  void *v33; // rax
  void *v34; // r15
  const void *v35; // rcx
  __int64 v36; // rsi
  void *v37; // rcx
  void *v38; // rax
  const void *v39; // rcx
  __int64 v40; // rsi
  void *v41; // rax
  int v42; // [rsp+58h] [rbp-B0h] BYREF
  int v43; // [rsp+5Ch] [rbp-ACh] BYREF
  int v44; // [rsp+60h] [rbp-A8h] BYREF
  int v45; // [rsp+64h] [rbp-A4h]
  unsigned __int64 v46; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE KeyHandle; // [rsp+70h] [rbp-98h]
  wchar_t ResultLength; // [rsp+78h] [rbp-90h]
  ULONG ResultLength_4; // [rsp+7Ch] [rbp-8Ch] BYREF
  ULONG ResultLength_8[4]; // [rsp+80h] [rbp-88h] BYREF
  void *Source2[2]; // [rsp+90h] [rbp-78h]
  SIZE_T Length[2]; // [rsp+A0h] [rbp-68h]
  size_t pcchLength[2]; // [rsp+B0h] [rbp-58h] BYREF
  ULONG v54; // [rsp+C0h] [rbp-48h] BYREF
  void *Src[2]; // [rsp+C8h] [rbp-40h] BYREF
  struct _RTL_QUERY_REGISTRY_TABLE v56; // [rsp+D8h] [rbp-30h] BYREF
  int (*v57)(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *); // [rsp+110h] [rbp+8h] BYREF
  int v58; // [rsp+118h] [rbp+10h]
  const wchar_t *v59; // [rsp+120h] [rbp+18h]
  void **v60; // [rsp+128h] [rbp+20h]
  int v61; // [rsp+130h] [rbp+28h]
  __int64 v62; // [rsp+138h] [rbp+30h]
  int v63; // [rsp+140h] [rbp+38h]
  __int64 v64; // [rsp+148h] [rbp+40h]
  int v65; // [rsp+150h] [rbp+48h]
  __int64 v66; // [rsp+158h] [rbp+50h]
  __int128 v67; // [rsp+160h] [rbp+58h]
  __int128 v68; // [rsp+170h] [rbp+68h]
  struct _RTL_QUERY_REGISTRY_TABLE QueryTable; // [rsp+188h] [rbp+80h] BYREF
  __int64 v70; // [rsp+1C0h] [rbp+B8h]
  int v71; // [rsp+1C8h] [rbp+C0h]
  const wchar_t *v72; // [rsp+1D0h] [rbp+C8h]
  __int64 v73; // [rsp+1D8h] [rbp+D0h]
  int v74; // [rsp+1E0h] [rbp+D8h]
  __int64 v75; // [rsp+1E8h] [rbp+E0h]
  int v76; // [rsp+1F0h] [rbp+E8h]
  __int64 v77; // [rsp+1F8h] [rbp+F0h] BYREF
  int v78; // [rsp+200h] [rbp+F8h]
  const wchar_t *v79; // [rsp+208h] [rbp+100h]
  char *v80; // [rsp+210h] [rbp+108h]
  int v81; // [rsp+218h] [rbp+110h]
  int *v82; // [rsp+220h] [rbp+118h]
  int v83; // [rsp+228h] [rbp+120h]
  __int64 v84; // [rsp+230h] [rbp+128h]
  int v85; // [rsp+238h] [rbp+130h]
  const wchar_t *v86; // [rsp+240h] [rbp+138h]
  int *v87; // [rsp+248h] [rbp+140h]
  int v88; // [rsp+250h] [rbp+148h]
  int *v89; // [rsp+258h] [rbp+150h]
  int v90; // [rsp+260h] [rbp+158h]
  __int64 v91; // [rsp+268h] [rbp+160h]
  int v92; // [rsp+270h] [rbp+168h]
  const wchar_t *v93; // [rsp+278h] [rbp+170h]
  int *v94; // [rsp+280h] [rbp+178h]
  int v95; // [rsp+288h] [rbp+180h]
  int *v96; // [rsp+290h] [rbp+188h]
  int v97; // [rsp+298h] [rbp+190h]
  int (*v98)(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *); // [rsp+2A0h] [rbp+198h]
  int v99; // [rsp+2A8h] [rbp+1A0h]
  const wchar_t *v100; // [rsp+2B0h] [rbp+1A8h]
  __int64 v101; // [rsp+2B8h] [rbp+1B0h]
  int v102; // [rsp+2C0h] [rbp+1B8h]
  __int64 v103; // [rsp+2C8h] [rbp+1C0h]
  int v104; // [rsp+2D0h] [rbp+1C8h]
  int (*v105)(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *); // [rsp+2D8h] [rbp+1D0h]
  int v106; // [rsp+2E0h] [rbp+1D8h]
  const wchar_t *v107; // [rsp+2E8h] [rbp+1E0h]
  __int64 v108; // [rsp+2F0h] [rbp+1E8h]
  int v109; // [rsp+2F8h] [rbp+1F0h]
  __int64 v110; // [rsp+300h] [rbp+1F8h]
  int v111; // [rsp+308h] [rbp+200h]
  int (*v112)(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *); // [rsp+310h] [rbp+208h]
  int v113; // [rsp+318h] [rbp+210h]
  const wchar_t *v114; // [rsp+320h] [rbp+218h]
  __int64 v115; // [rsp+328h] [rbp+220h]
  int v116; // [rsp+330h] [rbp+228h]
  __int64 v117; // [rsp+338h] [rbp+230h]
  int v118; // [rsp+340h] [rbp+238h]
  __int64 v119; // [rsp+348h] [rbp+240h]
  int v120; // [rsp+350h] [rbp+248h]
  const wchar_t *v121; // [rsp+358h] [rbp+250h]
  unsigned __int64 *v122; // [rsp+360h] [rbp+258h]
  int v123; // [rsp+368h] [rbp+260h]
  int *v124; // [rsp+370h] [rbp+268h]
  int v125; // [rsp+378h] [rbp+270h]
  __int64 v126; // [rsp+380h] [rbp+278h]
  int v127; // [rsp+388h] [rbp+280h]
  __int64 v128; // [rsp+390h] [rbp+288h]
  __int128 v129; // [rsp+398h] [rbp+290h]
  __int128 v130; // [rsp+3A8h] [rbp+2A0h]
  struct _RTL_QUERY_REGISTRY_TABLE v131; // [rsp+3B8h] [rbp+2B0h] BYREF
  int (*v132)(unsigned __int16 *, unsigned int, void *, unsigned int, void *, void *); // [rsp+3F0h] [rbp+2E8h]
  int v133; // [rsp+3F8h] [rbp+2F0h]
  const wchar_t *v134; // [rsp+400h] [rbp+2F8h]
  __int64 v135; // [rsp+408h] [rbp+300h]
  int v136; // [rsp+410h] [rbp+308h]
  __int64 v137; // [rsp+418h] [rbp+310h]
  int v138; // [rsp+420h] [rbp+318h]
  __int64 v139; // [rsp+428h] [rbp+320h]
  int v140; // [rsp+430h] [rbp+328h]
  const wchar_t *v141; // [rsp+438h] [rbp+330h]
  int *v142; // [rsp+440h] [rbp+338h]
  int v143; // [rsp+448h] [rbp+340h]
  int *v144; // [rsp+450h] [rbp+348h]
  int v145; // [rsp+458h] [rbp+350h]
  __int64 v146; // [rsp+460h] [rbp+358h]
  int v147; // [rsp+468h] [rbp+360h]
  const wchar_t *v148; // [rsp+470h] [rbp+368h]
  int *v149; // [rsp+478h] [rbp+370h]
  int v150; // [rsp+480h] [rbp+378h]
  int *v151; // [rsp+488h] [rbp+380h]
  int v152; // [rsp+490h] [rbp+388h]
  __int64 v153; // [rsp+498h] [rbp+390h]
  int v154; // [rsp+4A0h] [rbp+398h]
  const wchar_t *v155; // [rsp+4A8h] [rbp+3A0h]
  unsigned __int64 *v156; // [rsp+4B0h] [rbp+3A8h]
  int v157; // [rsp+4B8h] [rbp+3B0h]
  int *v158; // [rsp+4C0h] [rbp+3B8h]
  int v159; // [rsp+4C8h] [rbp+3C0h]
  __int64 v160; // [rsp+4D0h] [rbp+3C8h]
  int v161; // [rsp+4D8h] [rbp+3D0h]
  __int64 v162; // [rsp+4E0h] [rbp+3D8h]
  __int128 v163; // [rsp+4E8h] [rbp+3E0h]
  __int128 v164; // [rsp+4F8h] [rbp+3F0h]

  QueryTable.Name = L"DriverDesc";
  v79 = L"MultiDisplayDriver";
  v3 = a3;
  v45 = a3;
  v80 = (char *)&v46 + 4;
  KeyHandle = Path;
  v82 = &v44;
  v4 = Path;
  v86 = L"MirrorDriver";
  v44 = 0;
  v87 = &v42;
  RegistryValues = 0;
  v42 = 0;
  v89 = &v44;
  v93 = L"AccDriver";
  v94 = &v43;
  v96 = &v44;
  v100 = L"Device Description";
  v107 = L"HardwareInformation.AdapterString";
  v43 = 0;
  v46 = 0;
  QueryTable.QueryRoutine = __EnumDisplayQueryRoutine;
  QueryTable.Flags = 16;
  QueryTable.EntryContext = 0;
  QueryTable.DefaultType = 0;
  QueryTable.DefaultData = 0;
  QueryTable.DefaultLength = 0;
  v70 = 0;
  v71 = 1;
  v72 = L"Settings";
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 288;
  v81 = 67108868;
  v83 = 4;
  v84 = 0;
  v85 = 288;
  v88 = 67108868;
  v90 = 4;
  v91 = 0;
  v92 = 288;
  v95 = 67108868;
  v97 = 4;
  v98 = __EnumDisplayQueryRoutine;
  v99 = 16;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = __EnumDisplayQueryRoutine;
  v106 = 16;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = __EnumDisplayQueryRoutine;
  v113 = 16;
  v114 = L"HardwareInformation.ChipType";
  v7 = a3 == 0;
  v121 = L"TSCompatible";
  v125 = 4;
  v122 = &v46;
  p_QueryTable = (struct _RTL_QUERY_REGISTRY_TABLE *)&v77;
  v120 = 288;
  v124 = &v44;
  v123 = 67108868;
  if ( !v7 )
    p_QueryTable = &QueryTable;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v126 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  RtlQueryRegistryValues(0x40000000u, Path, p_QueryTable, Context, 0);
  if ( !v3 && !Context[65] )
  {
    ResultLength_4 = 0;
    RegistryValues = ZwQueryKey(v4, KeyNameInformation, 0, 0, &ResultLength_4);
    if ( RegistryValues == -1073741789 )
    {
      v14 = 0;
      v15 = (_DWORD *)PALLOCNOZ(ResultLength_4, 1936876615);
      if ( v15 )
      {
        v54 = 0;
        RegistryValues = ZwQueryKey(KeyHandle, KeyNameInformation, v15, ResultLength_4, &v54);
        if ( RegistryValues >= 0 )
        {
          LODWORD(v16) = 0;
          v17 = 0;
          if ( *v15 >> 1 )
          {
            do
            {
              v18 = v17;
              if ( *((_WORD *)v15 + v17 + 2) != 92 )
                v18 = v16;
              ++v17;
              v16 = v18;
            }
            while ( v17 < *v15 >> 1 );
            if ( v18 )
            {
              v19 = 2 * v18;
              LODWORD(pcchLength[0]) = *(_DWORD *)L"eo";
              ResultLength = aVideo[6];
              v20 = (WCHAR *)PALLOCNOZ(2 * v18 + 14, 1936876615);
              v14 = v20;
              if ( v20 )
              {
                memmove(v20, v15 + 1, v19);
                v21 = pcchLength[0];
                *(_QWORD *)&v14[v16] = *(_QWORD *)L"\\Video";
                *(_DWORD *)&v14[v16 + 4] = v21;
                v14[v16 + 6] = ResultLength;
              }
              else
              {
                RegistryValues = -1073741670;
              }
            }
          }
        }
        GreDeleteFastMutex(v15);
      }
      else
      {
        RegistryValues = -1073741670;
      }
      if ( v14 )
      {
        v56.QueryRoutine = __EnumDisplayQueryRoutine;
        v56.Flags = 16;
        v56.Name = L"DeviceDesc";
        v56.EntryContext = 0;
        v59 = L"Driver";
        v56.DefaultType = 0;
        v60 = Src;
        v56.DefaultData = 0;
        v22 = 0;
        v56.DefaultLength = 0;
        *(_OWORD *)Src = 0;
        v57 = 0;
        v58 = 304;
        v61 = 16777217;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        v65 = 0;
        v66 = 0;
        v67 = 0;
        v68 = 0;
        RegistryValues = RtlQueryRegistryValues(0, v14, &v56, Context, 0);
        if ( RegistryValues >= 0 )
        {
          v22 = 1;
          if ( LOWORD(Src[0]) )
          {
            v26 = (unsigned int)LOWORD(Src[0]) + 12;
            v27 = PALLOCNOZ((unsigned int)LOWORD(Src[0]) + 14, 1936876615);
            v28 = (WCHAR *)v27;
            if ( v27 )
            {
              *(_QWORD *)v27 = *(_QWORD *)L"Class\\";
              *(_DWORD *)(v27 + 8) = *(_DWORD *)L"s\\";
              memmove((void *)(v27 + 12), Src[1], LOWORD(Src[0]));
              v131.Flags = 1;
              *(WCHAR *)((char *)v28 + v26) = 0;
              v140 = 288;
              v147 = 288;
              v143 = 67108868;
              v131.Name = L"Settings";
              v150 = 67108868;
              v145 = 4;
              v132 = __DisplayDriverQueryRoutine;
              v134 = L"InstalledDisplayDrivers";
              v141 = L"MirrorDriver";
              v142 = &v42;
              v144 = &v44;
              v148 = L"AccDriver";
              v149 = &v43;
              v151 = &v44;
              v155 = L"TSCompatible";
              v156 = &v46;
              v152 = 4;
              v154 = 288;
              v157 = 67108868;
              v159 = 4;
              v158 = &v44;
              v131.QueryRoutine = 0;
              v131.EntryContext = 0;
              v131.DefaultType = 0;
              v131.DefaultData = 0;
              v131.DefaultLength = 0;
              v133 = 16;
              v135 = 0;
              v136 = 0;
              v137 = 0;
              v138 = 0;
              v139 = 0;
              v146 = 0;
              v153 = 0;
              v160 = 0;
              v161 = 0;
              v162 = 0;
              v163 = 0;
              v164 = 0;
              RtlQueryRegistryValues(2u, v28, &v131, Context, 0);
              GreDeleteFastMutex(v28);
            }
            else
            {
              RegistryValues = -1073741670;
            }
          }
        }
        if ( Src[1] )
        {
          ExFreePoolWithTag(Src[1], 0);
          Src[1] = 0;
        }
        GreDeleteFastMutex(v14);
        if ( v22 )
        {
          v29 = (const wchar_t *)*((_QWORD *)Context + 26);
          if ( v29 )
          {
            if ( Context[65] )
            {
              pcchLength[0] = 0;
              RegistryValues = RtlStringLengthWorkerW(v29, v23, pcchLength);
              if ( RegistryValues >= 0 )
              {
                v30 = 0;
                for ( i = 0;
                      (unsigned int)i < ((unsigned __int16)(2 * LOWORD(pcchLength[0])) >> 1) - 1;
                      i = (unsigned int)(i + 1) )
                {
                  if ( v29[i] == 59 )
                  {
                    v30 = i + 1;
                    break;
                  }
                }
                v32 = (unsigned __int16)(2 * LOWORD(pcchLength[0])) + 2 * (1 - v30);
                v33 = (void *)PALLOCNOZ(v32, 1936876615);
                v34 = v33;
                if ( v33 )
                {
                  memmove(v33, &v29[v30], v32);
                  GreDeleteFastMutex(*((PVOID *)Context + 26));
                  *((_QWORD *)Context + 26) = v34;
                  Context[65] = v32;
                }
                else
                {
                  RegistryValues = -1073741670;
                  Context[65] = 0;
                }
              }
            }
          }
        }
      }
      v3 = v45;
      v4 = (WCHAR *)KeyHandle;
    }
  }
  if ( (Context[40] & 0x800000) != 0 )
  {
    v25 = PALLOCNOZ(10, 1936876615);
    *((_QWORD *)Context + 25) = v25;
    if ( !v25 )
      goto LABEL_23;
    *(_QWORD *)v25 = *(_QWORD *)L"cdd";
    *(_WORD *)(v25 + 8) = 0;
    Context[64] = 10;
    RegistryValues = 0;
  }
  else
  {
    if ( !v43 && !v42 )
    {
      v24 = (struct _RTL_QUERY_REGISTRY_TABLE *)&v57;
      v59 = L"InstalledDisplayDrivers";
      v57 = __DisplayDriverQueryRoutine;
      v56.QueryRoutine = 0;
      if ( v3 )
        v24 = &v56;
      v56.Flags = 1;
      v56.Name = L"Settings";
      v56.EntryContext = 0;
      v56.DefaultType = 0;
      v56.DefaultData = 0;
      v56.DefaultLength = 0;
      v58 = 16;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      RegistryValues = RtlQueryRegistryValues(0x40000000u, v4, v24, Context, 0);
    }
    if ( RegistryValues < 0 )
      goto LABEL_23;
  }
  *(_OWORD *)ResultLength_8 = 0;
  *(_OWORD *)Source2 = 0;
  *(_OWORD *)Length = 0;
  if ( v43 )
    v42 = 1;
  GreDeviceIoControlImpl(
    *((PDEVICE_OBJECT *)Context + 17),
    0x23203Bu,
    0,
    0,
    ResultLength_8,
    0x30u,
    (unsigned int *)pcchLength,
    1u,
    1);
  v9 = (unsigned int)Source2[1];
  if ( !LODWORD(Source2[1]) || !Source2[0] )
  {
    ResultLength_8[0] = HIDWORD(v46);
    ResultLength_8[3] = v46;
    Source2[0] = *((void **)Context + 25);
    v10 = (struct _DEVICE_OBJECT *)*((_QWORD *)Context + 17);
    LODWORD(Source2[1]) = Context[64];
    Length[0] = *((_QWORD *)Context + 26);
    LODWORD(Length[1]) = Context[65];
    *(_QWORD *)&ResultLength_8[1] = (v43 != 0 ? 2 : 0) | (unsigned __int64)(v42 != 0);
    GreDeviceIoControlImpl(v10, 0x23203Fu, ResultLength_8, 0x30u, 0, 0, (unsigned int *)pcchLength, 1u, 1);
    goto LABEL_11;
  }
  if ( HIDWORD(v46) != ResultLength_8[0]
    || (v42 != 0) != (ResultLength_8[1] & 1)
    || (v43 != 0 ? 2 : 0) != (ResultLength_8[1] & 2)
    || (_DWORD)v46 != ResultLength_8[3] )
  {
    v42 = ResultLength_8[1] & 1;
    v43 = (ResultLength_8[1] >> 1) & 1;
    v46 = __PAIR64__(ResultLength_8[0], ResultLength_8[3]);
  }
  v35 = (const void *)*((_QWORD *)Context + 25);
  if ( !v35 )
    goto LABEL_79;
  v36 = Context[64];
  if ( LODWORD(Source2[1]) != (_DWORD)v36 )
    goto LABEL_79;
  if ( RtlCompareMemory(v35, Source2[0], LODWORD(Source2[1])) != v36 )
  {
    v9 = (unsigned int)Source2[1];
LABEL_79:
    v37 = (void *)*((_QWORD *)Context + 25);
    if ( v37 )
    {
      GreDeleteFastMutex(v37);
      v9 = (unsigned int)Source2[1];
    }
    v38 = (void *)PALLOCNOZ(v9, 1936876615);
    *((_QWORD *)Context + 25) = v38;
    if ( v38 )
      memmove(v38, Source2[0], LODWORD(Source2[1]));
    else
      RegistryValues = -1073741670;
  }
  v39 = (const void *)*((_QWORD *)Context + 26);
  if ( v39 )
  {
    if ( Length[0] )
    {
      v40 = Context[65];
      if ( LODWORD(Length[1]) != (_DWORD)v40
        || RtlCompareMemory(v39, (const void *)Length[0], LODWORD(Length[1])) != v40 )
      {
        GreDeleteFastMutex(*((PVOID *)Context + 26));
        v41 = (void *)PALLOCNOZ(LODWORD(Length[1]), 1936876615);
        *((_QWORD *)Context + 26) = v41;
        if ( v41 )
          memmove(v41, (const void *)Length[0], LODWORD(Length[1]));
        else
          RegistryValues = -1073741670;
      }
    }
  }
LABEL_11:
  if ( RegistryValues >= 0 )
  {
    if ( HIDWORD(v46) )
      Context[40] |= 2u;
    if ( v42 )
      Context[40] |= 8u;
    if ( v43 )
      Context[40] |= 0x48u;
    if ( (_DWORD)v46 )
      Context[40] |= 0x200000u;
    v11 = (const wchar_t *)*((_QWORD *)Context + 26);
    if ( v11 )
    {
      if ( !wcsicmp(v11, L"RDPUDD Chained DD") )
        Context[40] |= 0x1000000u;
    }
    return;
  }
LABEL_23:
  DrvLogDisplayDriverEvent(1);
  v12 = (void *)*((_QWORD *)Context + 25);
  if ( v12 )
  {
    GreDeleteFastMutex(v12);
    *((_QWORD *)Context + 25) = 0;
  }
  v13 = (void *)*((_QWORD *)Context + 26);
  if ( v13 )
  {
    GreDeleteFastMutex(v13);
    *((_QWORD *)Context + 26) = 0;
  }
}

```

## disassembly

```asm
0x1400d34f8  mov     rax, rsp
0x1400d34fb  mov     [rax+18h], rbx
0x1400d34ff  push    rbp
0x1400d3500  push    rsi
0x1400d3501  push    rdi
0x1400d3502  push    r12
0x1400d3504  push    r13
0x1400d3506  push    r14
0x1400d3508  push    r15
0x1400d350a  lea     rbp, [rax-458h]
0x1400d3511  sub     rsp, 520h
0x1400d3518  movaps  xmmword ptr [rax-48h], xmm6
0x1400d351c  mov     rax, cs:__security_cookie
0x1400d3523  xor     rax, rsp
0x1400d3526  mov     [rbp+450h+var_50], rax
0x1400d352d  mov     rax, cs:off_14023D0C0; "DriverDesc"
0x1400d3534  lea     r12, ?__EnumDisplayQueryRoutine@@YAJPEAGKPEAXK11@Z; __EnumDisplayQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x1400d353b  xor     r13d, r13d
0x1400d353e  mov     [rbp+450h+QueryTable.Name], rax
0x1400d3545  mov     rax, cs:off_14023D0D0; "MultiDisplayDriver"
0x1400d354c  lea     r15, aSettings; "Settings"
0x1400d3553  mov     [rbp+450h+var_350], rax
0x1400d355a  mov     r14d, r8d
0x1400d355d  lea     rax, [rsp+550h+var_4F0+4]
0x1400d3562  mov     [rsp+550h+var_4F4], r8d
0x1400d3567  mov     [rbp+450h+var_348], rax
0x1400d356e  lea     r8d, [r13+4]
0x1400d3572  lea     rax, [rsp+550h+var_4F8]
0x1400d3577  mov     [rsp+550h+KeyHandle], rdx
0x1400d357c  mov     [rbp+450h+var_338], rax
0x1400d3583  mov     rsi, rdx
0x1400d3586  mov     rax, cs:off_14023D0D8; "MirrorDriver"
0x1400d358d  mov     edx, 4000004h
0x1400d3592  mov     [rbp+450h+var_318], rax
0x1400d3599  mov     rbx, rcx
0x1400d359c  mov     ecx, 120h
0x1400d35a1  mov     [rsp+550h+var_4F8], r13d
0x1400d35a6  lea     rax, [rsp+550h+var_500]
0x1400d35ab  mov     dword ptr [rsp+550h+var_4F0+4], r13d
0x1400d35b0  mov     [rbp+450h+var_310], rax
0x1400d35b7  mov     edi, r13d
0x1400d35ba  lea     rax, [rsp+550h+var_4F8]
0x1400d35bf  mov     [rsp+550h+var_500], r13d
0x1400d35c4  mov     [rbp+450h+var_300], rax
0x1400d35cb  mov     rax, cs:off_14023D0E0; "AccDriver"
0x1400d35d2  mov     [rbp+450h+var_2E0], rax
0x1400d35d9  lea     rax, [rsp+550h+var_4FC]
0x1400d35de  mov     [rbp+450h+var_2D8], rax
0x1400d35e5  lea     rax, [rsp+550h+var_4F8]
0x1400d35ea  mov     [rbp+450h+var_2C8], rax
0x1400d35f1  mov     rax, cs:off_14023D0E8; "Device Description"
0x1400d35f8  mov     [rbp+450h+var_2A8], rax
0x1400d35ff  mov     rax, cs:off_14023D0F0; "HardwareInformation.AdapterString"
0x1400d3606  mov     [rbp+450h+var_270], rax
0x1400d360d  mov     rax, cs:off_14023D0F8; "HardwareInformation.ChipType"
0x1400d3614  mov     [rsp+550h+var_4FC], r13d
0x1400d3619  mov     dword ptr [rsp+550h+var_4F0], r13d
0x1400d361e  mov     [rbp+450h+QueryTable.QueryRoutine], r12
0x1400d3625  mov     [rbp+450h+QueryTable.Flags], 10h
0x1400d362f  mov     [rbp+450h+QueryTable.EntryContext], r13
0x1400d3636  mov     [rbp+450h+QueryTable.DefaultType], r13d
0x1400d363d  mov     [rbp+450h+QueryTable.DefaultData], r13
0x1400d3644  mov     [rbp+450h+QueryTable.DefaultLength], r13d
0x1400d364b  mov     [rbp+450h+var_398], r13
0x1400d3652  mov     [rbp+450h+var_390], 1
0x1400d365c  mov     [rbp+450h+var_388], r15
0x1400d3663  mov     [rbp+450h+var_380], r13
0x1400d366a  mov     [rbp+450h+var_378], r13d
0x1400d3671  mov     [rbp+450h+var_370], r13
0x1400d3678  mov     [rbp+450h+var_368], r13d
0x1400d367f  mov     [rbp+450h+var_360], r13
0x1400d3686  mov     [rbp+450h+var_358], ecx
0x1400d368c  mov     [rbp+450h+var_340], edx
0x1400d3692  mov     [rbp+450h+var_330], r8d
0x1400d3699  mov     [rbp+450h+var_328], r13
0x1400d36a0  mov     [rbp+450h+var_320], ecx
0x1400d36a6  mov     [rbp+450h+var_308], edx
0x1400d36ac  mov     [rbp+450h+var_2F8], r8d
0x1400d36b3  mov     [rbp+450h+var_2F0], r13
0x1400d36ba  mov     [rbp+450h+var_2E8], ecx
0x1400d36c0  mov     [rbp+450h+var_2D0], edx
0x1400d36c6  mov     [rbp+450h+var_2C0], r8d
0x1400d36cd  mov     [rbp+450h+var_2B8], r12
0x1400d36d4  mov     [rbp+450h+var_2B0], 10h
0x1400d36de  mov     [rbp+450h+var_2A0], r13
0x1400d36e5  mov     [rbp+450h+var_298], r13d
0x1400d36ec  mov     [rbp+450h+var_290], r13
0x1400d36f3  mov     [rbp+450h+var_288], r13d
0x1400d36fa  mov     [rbp+450h+var_280], r12
0x1400d3701  mov     [rbp+450h+var_278], 10h
0x1400d370b  mov     [rbp+450h+var_268], r13
0x1400d3712  mov     [rbp+450h+var_260], r13d
0x1400d3719  mov     [rbp+450h+var_258], r13
0x1400d3720  mov     [rbp+450h+var_250], r13d
0x1400d3727  mov     [rbp+450h+var_248], r12
0x1400d372e  mov     [rbp+450h+var_240], 10h
0x1400d3738  mov     [rbp+450h+var_238], rax
0x1400d373f  xorps   xmm0, xmm0
0x1400d3742  mov     rax, cs:off_14023D100; "TSCompatible"
0x1400d3749  test    r14d, r14d
0x1400d374c  mov     [rbp+450h+var_200], rax
0x1400d3753  mov     r9, rbx; Context
0x1400d3756  mov     [rbp+450h+var_1E0], r8d
0x1400d375d  lea     rax, [rsp+550h+var_4F0]
0x1400d3762  mov     [rbp+450h+var_1F8], rax
0x1400d3769  lea     r8, [rbp+450h+var_360]
0x1400d3770  lea     rax, [rsp+550h+var_4F8]
0x1400d3775  mov     [rbp+450h+var_208], ecx
0x1400d377b  mov     [rbp+450h+var_1E8], rax
0x1400d3782  mov     ecx, 40000000h; RelativeTo
0x1400d3787  lea     rax, [rbp+450h+QueryTable]
0x1400d378e  mov     [rbp+450h+var_1F0], edx
0x1400d3794  cmovnz  r8, rax; QueryTable
0x1400d3798  mov     [rbp+450h+var_230], r13
0x1400d379f  mov     rdx, rsi; Path
0x1400d37a2  mov     [rbp+450h+var_228], r13d
0x1400d37a9  mov     [rbp+450h+var_220], r13
0x1400d37b0  mov     [rbp+450h+var_218], r13d
0x1400d37b7  mov     [rbp+450h+var_210], r13
0x1400d37be  mov     [rbp+450h+var_1D8], r13
0x1400d37c5  mov     [rbp+450h+var_1D0], r13d
0x1400d37cc  mov     [rbp+450h+var_1C8], r13
0x1400d37d3  movups  [rbp+450h+var_1C0], xmm0
0x1400d37da  mov     [rsp+550h+Environment], r13; Environment
0x1400d37df  movups  [rbp+450h+var_1B0], xmm0
0x1400d37e6  call    cs:__imp_RtlQueryRegistryValues
0x1400d37ed  nop     dword ptr [rax+rax+00h]
0x1400d37f2  lea     rcx, ?__DisplayDriverQueryRoutine@@YAJPEAGKPEAXK11@Z; __DisplayDriverQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x1400d37f9  test    r14d, r14d
0x1400d37fc  jz      loc_1400D39CA
0x1400d3802  test    dword ptr [rbx+0A0h], 800000h
0x1400d380c  jnz     loc_1400D3C78
0x1400d3812  cmp     [rsp+550h+var_4FC], r13d
0x1400d3817  jz      loc_1400D3BDF
0x1400d381d  test    edi, edi
0x1400d381f  js      loc_1400D3970
0x1400d3825  xorps   xmm0, xmm0
0x1400d3828  mov     esi, 1
0x1400d382d  movups  xmmword ptr [rsp+550h+ResultLength+8], xmm0
0x1400d3832  movups  xmmword ptr [rbp+450h+Source2], xmm0
0x1400d3836  movups  xmmword ptr [rbp+450h+Length], xmm0
0x1400d383a  cmp     [rsp+550h+var_4FC], r13d
0x1400d383f  jz      short loc_1400D3845
0x1400d3841  mov     [rsp+550h+var_500], esi
0x1400d3845  mov     rcx, [rbx+88h]; DeviceObject
0x1400d384c  lea     rax, [rbp+450h+pcchLength]
0x1400d3850  mov     [rsp+550h+var_510], esi; int
0x1400d3854  mov     r14d, 30h ; '0'
0x1400d385a  mov     dword ptr [rsp+550h+var_518], esi; BOOLEAN
0x1400d385e  xor     r9d, r9d; InputBufferLength
0x1400d3861  mov     [rsp+550h+var_520], rax; unsigned int *
0x1400d3866  xor     r8d, r8d; InputBuffer
0x1400d3869  lea     rax, [rsp+550h+ResultLength+8]
0x1400d386e  mov     [rsp+550h+var_528], r14d; ULONG
0x1400d3873  mov     edx, 23203Bh; IoControlCode
0x1400d3878  mov     [rsp+550h+Environment], rax; PVOID
0x1400d387d  call    ?GreDeviceIoControlImpl@@YAJPEAXK0K0KPEAKHH@Z; GreDeviceIoControlImpl(void *,ulong,void *,ulong,void *,ulong,ulong *,int,int)
0x1400d3882  mov     r9d, dword ptr [rbp+450h+Source2+8]
0x1400d3886  test    r9d, r9d
0x1400d3889  jnz     loc_1400D3FBF
0x1400d388f  mov     eax, dword ptr [rsp+550h+var_4F0+4]
0x1400d3893  lea     r8, [rsp+550h+ResultLength+8]; InputBuffer
0x1400d3898  cmp     [rsp+550h+var_500], r13d
0x1400d389d  mov     edx, r13d
0x1400d38a0  mov     [rsp+550h+ResultLength+8], eax
0x1400d38a4  mov     r9d, r14d; InputBufferLength
0x1400d38a7  mov     eax, [rsp+550h+var_4FC]
0x1400d38ab  setnz   dl
0x1400d38ae  neg     eax
0x1400d38b0  mov     [rsp+550h+var_510], esi; int
0x1400d38b4  mov     eax, dword ptr [rsp+550h+var_4F0]
0x1400d38b8  mov     [rbp+450h+var_4CC], eax
0x1400d38bb  sbb     ecx, ecx
0x1400d38bd  mov     rax, [rbx+0C8h]
0x1400d38c4  and     ecx, 2
0x1400d38c7  mov     [rbp+450h+Source2], rax
0x1400d38cb  or      edx, ecx
0x1400d38cd  mov     eax, [rbx+100h]
0x1400d38d3  mov     rcx, [rbx+88h]; DeviceObject
0x1400d38da  mov     dword ptr [rbp+450h+Source2+8], eax
0x1400d38dd  mov     rax, [rbx+0D0h]
0x1400d38e4  mov     [rbp+450h+Length], rax
0x1400d38e8  mov     eax, [rbx+104h]
0x1400d38ee  mov     dword ptr [rsp+550h+var_518], esi; BOOLEAN
0x1400d38f2  mov     dword ptr [rbp+450h+Length+8], eax
0x1400d38f5  lea     rax, [rbp+450h+pcchLength]
0x1400d38f9  mov     [rsp+550h+var_520], rax; unsigned int *
0x1400d38fe  mov     [rsp+550h+ResultLength+0Ch], edx
0x1400d3902  mov     edx, 23203Fh; IoControlCode
0x1400d3907  mov     [rsp+550h+var_528], r13d; ULONG
0x1400d390c  mov     [rsp+550h+Environment], r13; PVOID
0x1400d3911  mov     [rbp+450h+var_4D0], r13d
0x1400d3915  call    ?GreDeviceIoControlImpl@@YAJPEAXK0K0KPEAKHH@Z; GreDeviceIoControlImpl(void *,ulong,void *,ulong,void *,ulong,ulong *,int,int)
0x1400d391a  test    edi, edi
0x1400d391c  js      short loc_1400D3970
0x1400d391e  cmp     dword ptr [rsp+550h+var_4F0+4], r13d
0x1400d3923  jnz     loc_1400D4128
0x1400d3929  cmp     [rsp+550h+var_500], r13d
0x1400d392e  jnz     loc_1400D4134
0x1400d3934  cmp     [rsp+550h+var_4FC], r13d
0x1400d3939  jnz     loc_1400D4140
0x1400d393f  cmp     dword ptr [rsp+550h+var_4F0], r13d
0x1400d3944  jnz     loc_1400D414C
0x1400d394a  mov     rcx, [rbx+0D0h]; Str1
0x1400d3951  test    rcx, rcx
0x1400d3954  jz      short loc_1400D399A
0x1400d3956  lea     rdx, aRdpuddChainedD; "RDPUDD Chained DD"
0x1400d395d  call    _wcsicmp
0x1400d3962  test    eax, eax
0x1400d3964  jnz     short loc_1400D399A
0x1400d3966  bts     dword ptr [rbx+0A0h], 18h
0x1400d396e  jmp     short loc_1400D399A
0x1400d3970  mov     ecx, 1
0x1400d3975  call    ?DrvLogDisplayDriverEvent@@YAXW4_DISP_DRIVER_LOG@@@Z; DrvLogDisplayDriverEvent(_DISP_DRIVER_LOG)
0x1400d397a  mov     rcx, [rbx+0C8h]; Buffer
0x1400d3981  test    rcx, rcx
0x1400d3984  jnz     loc_1400D4159
0x1400d398a  mov     rcx, [rbx+0D0h]; Buffer
0x1400d3991  test    rcx, rcx
0x1400d3994  jnz     loc_1400D416A
0x1400d399a  mov     rcx, [rbp+450h+var_50]
0x1400d39a1  xor     rcx, rsp; StackCookie
0x1400d39a4  call    __security_check_cookie
0x1400d39a9  lea     r11, [rsp+550h+var_30]
0x1400d39b1  mov     rbx, [r11+50h]
0x1400d39b5  movaps  xmm6, xmmword ptr [r11-10h]
0x1400d39ba  mov     rsp, r11
0x1400d39bd  pop     r15
0x1400d39bf  pop     r14
0x1400d39c1  pop     r13
0x1400d39c3  pop     r12
0x1400d39c5  pop     rdi
0x1400d39c6  pop     rsi
0x1400d39c7  pop     rbp
0x1400d39c8  retn
0x1400d39ca  cmp     [rbx+104h], r13d
0x1400d39d1  jnz     loc_1400D3802
0x1400d39d7  xor     r9d, r9d; Length
0x1400d39da  mov     [rsp+550h+ResultLength+4], r13d
0x1400d39df  lea     rax, [rsp+550h+ResultLength+4]
0x1400d39e4  xor     r8d, r8d; KeyInformation
0x1400d39e7  mov     rcx, rsi; KeyHandle
0x1400d39ea  mov     [rsp+550h+Environment], rax; ResultLength
0x1400d39ef  lea     r15d, [r9+3]
0x1400d39f3  mov     edx, r15d; KeyInformationClass
0x1400d39f6  call    cs:__imp_ZwQueryKey
0x1400d39fd  nop     dword ptr [rax+rax+00h]
0x1400d3a02  mov     edi, eax
0x1400d3a04  cmp     eax, 0C0000023h
0x1400d3a09  jnz     loc_1400D3BCC
0x1400d3a0f  mov     ecx, [rsp+550h+ResultLength+4]
0x1400d3a13  mov     edx, 73726447h
0x1400d3a18  mov     rsi, r13
0x1400d3a1b  call    PALLOCNOZ
0x1400d3a20  mov     r14, rax
0x1400d3a23  test    rax, rax
0x1400d3a26  jz      loc_1400D3CBE
0x1400d3a2c  mov     r9d, [rsp+550h+ResultLength+4]; Length
0x1400d3a31  lea     rax, [rbp+450h+var_498]
0x1400d3a35  mov     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x1400d3a3a  mov     r8, r14; KeyInformation
0x1400d3a3d  mov     edx, r15d; KeyInformationClass
0x1400d3a40  mov     [rsp+550h+Environment], rax; ResultLength
0x1400d3a45  mov     [rbp+450h+var_498], r13d
0x1400d3a49  call    cs:__imp_ZwQueryKey
0x1400d3a50  nop     dword ptr [rax+rax+00h]
0x1400d3a55  mov     edi, eax
0x1400d3a57  test    eax, eax
0x1400d3a59  js      loc_1400D3AFB
0x1400d3a5f  mov     r8d, [r14]
0x1400d3a62  mov     r15d, r13d
0x1400d3a65  shr     r8d, 1
0x1400d3a68  mov     edx, r13d
0x1400d3a6b  jz      loc_1400D3AF4
0x1400d3a71  mov     eax, edx
0x1400d3a73  mov     ecx, edx
0x1400d3a75  cmp     word ptr [r14+rax*2+4], 5Ch ; '\'
0x1400d3a7c  cmovnz  ecx, r15d
0x1400d3a80  inc     edx
0x1400d3a82  mov     r15d, ecx
0x1400d3a85  cmp     edx, r8d
0x1400d3a88  jb      short loc_1400D3A71
0x1400d3a8a  test    ecx, ecx
0x1400d3a8c  jz      short loc_1400D3AF4
0x1400d3a8e  mov     eax, dword ptr cs:aVideo+8; "eo"
0x1400d3a94  lea     r13d, [rcx+rcx]
0x1400d3a98  movsd   xmm6, qword ptr cs:aVideo; "\\Video"
0x1400d3aa0  lea     ecx, [r13+0Eh]
0x1400d3aa4  mov     dword ptr [rbp+450h+pcchLength], eax
0x1400d3aa7  mov     edx, 73726447h
0x1400d3aac  movzx   eax, word ptr cs:aVideo+0Ch; ""
0x1400d3ab3  mov     word ptr [rsp+550h+ResultLength], ax
0x1400d3ab8  call    PALLOCNOZ
0x1400d3abd  mov     rsi, rax
0x1400d3ac0  test    rax, rax
0x1400d3ac3  jz      loc_1400D3ED7
0x1400d3ac9  mov     r8d, r13d; Size
0x1400d3acc  lea     rdx, [r14+4]; Src
0x1400d3ad0  mov     rcx, rax; void *
0x1400d3ad3  call    memmove
  ... truncated ...
```
