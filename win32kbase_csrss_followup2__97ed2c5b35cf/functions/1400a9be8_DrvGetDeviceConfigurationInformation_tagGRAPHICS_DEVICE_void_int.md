# DrvGetDeviceConfigurationInformation(tagGRAPHICS_DEVICE *,void *,int)

- ea: `0x1400a9be8`
- end: `0x1400aa86b`
- name: `?DrvGetDeviceConfigurationInformation@@YAXPEAUtagGRAPHICS_DEVICE@@PEAXH@Z`
- size: `3203`
- prototype: `void __fastcall(PVOID Context, PCWSTR Path, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14005d990`
- `0x1400a8ed0`

## callees

- `0x14000dc4c`
- `0x14004a0d0`
- `0x1400a9be8`
- `0x1400ab4f0`
- `0x1401b20c4`
- `0x1401c4430`
- `0x1401f0e4c`
- `0x140238160`
- `0x140238800`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa5d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aa5d3`
- `ntoskrnl!ZwQueryKey` at `0x1400aa0e6`
- `ntoskrnl!ZwQueryKey` at `0x1400aa139`
- `ntoskrnl!ZwQueryKey` at `0x1400aa0e6`
- `ntoskrnl!ZwQueryKey` at `0x1400aa139`
- `ntoskrnl!RtlCompareMemory` at `0x1400aa739`
- `ntoskrnl!RtlCompareMemory` at `0x1400aa7bf`
- `ntoskrnl!RtlCompareMemory` at `0x1400aa739`
- `ntoskrnl!RtlCompareMemory` at `0x1400aa7bf`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400a9ed6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400aa27e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400aa355`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400aa5a1`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400a9ed6`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400aa27e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400aa355`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400aa5a1`

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
0x1400a9be8  mov     rax, rsp
0x1400a9beb  mov     [rax+18h], rbx
0x1400a9bef  push    rbp
0x1400a9bf0  push    rsi
0x1400a9bf1  push    rdi
0x1400a9bf2  push    r12
0x1400a9bf4  push    r13
0x1400a9bf6  push    r14
0x1400a9bf8  push    r15
0x1400a9bfa  lea     rbp, [rax-458h]
0x1400a9c01  sub     rsp, 520h
0x1400a9c08  movaps  xmmword ptr [rax-48h], xmm6
0x1400a9c0c  mov     rax, cs:__security_cookie
0x1400a9c13  xor     rax, rsp
0x1400a9c16  mov     [rbp+450h+var_50], rax
0x1400a9c1d  mov     rax, cs:off_14023C230; "DriverDesc"
0x1400a9c24  lea     r12, ?__EnumDisplayQueryRoutine@@YAJPEAGKPEAXK11@Z; __EnumDisplayQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x1400a9c2b  xor     r13d, r13d
0x1400a9c2e  mov     [rbp+450h+QueryTable.Name], rax
0x1400a9c35  mov     rax, cs:off_14023C240; "MultiDisplayDriver"
0x1400a9c3c  lea     r15, aSettings; "Settings"
0x1400a9c43  mov     [rbp+450h+var_350], rax
0x1400a9c4a  mov     r14d, r8d
0x1400a9c4d  lea     rax, [rsp+550h+var_4F0+4]
0x1400a9c52  mov     [rsp+550h+var_4F4], r8d
0x1400a9c57  mov     [rbp+450h+var_348], rax
0x1400a9c5e  lea     r8d, [r13+4]
0x1400a9c62  lea     rax, [rsp+550h+var_4F8]
0x1400a9c67  mov     [rsp+550h+KeyHandle], rdx
0x1400a9c6c  mov     [rbp+450h+var_338], rax
0x1400a9c73  mov     rsi, rdx
0x1400a9c76  mov     rax, cs:off_14023C248; "MirrorDriver"
0x1400a9c7d  mov     edx, 4000004h
0x1400a9c82  mov     [rbp+450h+var_318], rax
0x1400a9c89  mov     rbx, rcx
0x1400a9c8c  mov     ecx, 120h
0x1400a9c91  mov     [rsp+550h+var_4F8], r13d
0x1400a9c96  lea     rax, [rsp+550h+var_500]
0x1400a9c9b  mov     dword ptr [rsp+550h+var_4F0+4], r13d
0x1400a9ca0  mov     [rbp+450h+var_310], rax
0x1400a9ca7  mov     edi, r13d
0x1400a9caa  lea     rax, [rsp+550h+var_4F8]
0x1400a9caf  mov     [rsp+550h+var_500], r13d
0x1400a9cb4  mov     [rbp+450h+var_300], rax
0x1400a9cbb  mov     rax, cs:off_14023C250; "AccDriver"
0x1400a9cc2  mov     [rbp+450h+var_2E0], rax
0x1400a9cc9  lea     rax, [rsp+550h+var_4FC]
0x1400a9cce  mov     [rbp+450h+var_2D8], rax
0x1400a9cd5  lea     rax, [rsp+550h+var_4F8]
0x1400a9cda  mov     [rbp+450h+var_2C8], rax
0x1400a9ce1  mov     rax, cs:off_14023C258; "Device Description"
0x1400a9ce8  mov     [rbp+450h+var_2A8], rax
0x1400a9cef  mov     rax, cs:off_14023C260; "HardwareInformation.AdapterString"
0x1400a9cf6  mov     [rbp+450h+var_270], rax
0x1400a9cfd  mov     rax, cs:off_14023C268; "HardwareInformation.ChipType"
0x1400a9d04  mov     [rsp+550h+var_4FC], r13d
0x1400a9d09  mov     dword ptr [rsp+550h+var_4F0], r13d
0x1400a9d0e  mov     [rbp+450h+QueryTable.QueryRoutine], r12
0x1400a9d15  mov     [rbp+450h+QueryTable.Flags], 10h
0x1400a9d1f  mov     [rbp+450h+QueryTable.EntryContext], r13
0x1400a9d26  mov     [rbp+450h+QueryTable.DefaultType], r13d
0x1400a9d2d  mov     [rbp+450h+QueryTable.DefaultData], r13
0x1400a9d34  mov     [rbp+450h+QueryTable.DefaultLength], r13d
0x1400a9d3b  mov     [rbp+450h+var_398], r13
0x1400a9d42  mov     [rbp+450h+var_390], 1
0x1400a9d4c  mov     [rbp+450h+var_388], r15
0x1400a9d53  mov     [rbp+450h+var_380], r13
0x1400a9d5a  mov     [rbp+450h+var_378], r13d
0x1400a9d61  mov     [rbp+450h+var_370], r13
0x1400a9d68  mov     [rbp+450h+var_368], r13d
0x1400a9d6f  mov     [rbp+450h+var_360], r13
0x1400a9d76  mov     [rbp+450h+var_358], ecx
0x1400a9d7c  mov     [rbp+450h+var_340], edx
0x1400a9d82  mov     [rbp+450h+var_330], r8d
0x1400a9d89  mov     [rbp+450h+var_328], r13
0x1400a9d90  mov     [rbp+450h+var_320], ecx
0x1400a9d96  mov     [rbp+450h+var_308], edx
0x1400a9d9c  mov     [rbp+450h+var_2F8], r8d
0x1400a9da3  mov     [rbp+450h+var_2F0], r13
0x1400a9daa  mov     [rbp+450h+var_2E8], ecx
0x1400a9db0  mov     [rbp+450h+var_2D0], edx
0x1400a9db6  mov     [rbp+450h+var_2C0], r8d
0x1400a9dbd  mov     [rbp+450h+var_2B8], r12
0x1400a9dc4  mov     [rbp+450h+var_2B0], 10h
0x1400a9dce  mov     [rbp+450h+var_2A0], r13
0x1400a9dd5  mov     [rbp+450h+var_298], r13d
0x1400a9ddc  mov     [rbp+450h+var_290], r13
0x1400a9de3  mov     [rbp+450h+var_288], r13d
0x1400a9dea  mov     [rbp+450h+var_280], r12
0x1400a9df1  mov     [rbp+450h+var_278], 10h
0x1400a9dfb  mov     [rbp+450h+var_268], r13
0x1400a9e02  mov     [rbp+450h+var_260], r13d
0x1400a9e09  mov     [rbp+450h+var_258], r13
0x1400a9e10  mov     [rbp+450h+var_250], r13d
0x1400a9e17  mov     [rbp+450h+var_248], r12
0x1400a9e1e  mov     [rbp+450h+var_240], 10h
0x1400a9e28  mov     [rbp+450h+var_238], rax
0x1400a9e2f  xorps   xmm0, xmm0
0x1400a9e32  mov     rax, cs:off_14023C270; "TSCompatible"
0x1400a9e39  test    r14d, r14d
0x1400a9e3c  mov     [rbp+450h+var_200], rax
0x1400a9e43  mov     r9, rbx; Context
0x1400a9e46  mov     [rbp+450h+var_1E0], r8d
0x1400a9e4d  lea     rax, [rsp+550h+var_4F0]
0x1400a9e52  mov     [rbp+450h+var_1F8], rax
0x1400a9e59  lea     r8, [rbp+450h+var_360]
0x1400a9e60  lea     rax, [rsp+550h+var_4F8]
0x1400a9e65  mov     [rbp+450h+var_208], ecx
0x1400a9e6b  mov     [rbp+450h+var_1E8], rax
0x1400a9e72  mov     ecx, 40000000h; RelativeTo
0x1400a9e77  lea     rax, [rbp+450h+QueryTable]
0x1400a9e7e  mov     [rbp+450h+var_1F0], edx
0x1400a9e84  cmovnz  r8, rax; QueryTable
0x1400a9e88  mov     [rbp+450h+var_230], r13
0x1400a9e8f  mov     rdx, rsi; Path
0x1400a9e92  mov     [rbp+450h+var_228], r13d
0x1400a9e99  mov     [rbp+450h+var_220], r13
0x1400a9ea0  mov     [rbp+450h+var_218], r13d
0x1400a9ea7  mov     [rbp+450h+var_210], r13
0x1400a9eae  mov     [rbp+450h+var_1D8], r13
0x1400a9eb5  mov     [rbp+450h+var_1D0], r13d
0x1400a9ebc  mov     [rbp+450h+var_1C8], r13
0x1400a9ec3  movups  [rbp+450h+var_1C0], xmm0
0x1400a9eca  mov     [rsp+550h+Environment], r13; Environment
0x1400a9ecf  movups  [rbp+450h+var_1B0], xmm0
0x1400a9ed6  call    cs:__imp_RtlQueryRegistryValues
0x1400a9edd  nop     dword ptr [rax+rax+00h]
0x1400a9ee2  lea     rcx, ?__DisplayDriverQueryRoutine@@YAJPEAGKPEAXK11@Z; __DisplayDriverQueryRoutine(ushort *,ulong,void *,ulong,void *,void *)
0x1400a9ee9  test    r14d, r14d
0x1400a9eec  jz      loc_1400AA0BA
0x1400a9ef2  test    dword ptr [rbx+0A0h], 800000h
0x1400a9efc  jnz     loc_1400AA368
0x1400a9f02  cmp     [rsp+550h+var_4FC], r13d
0x1400a9f07  jz      loc_1400AA2CF
0x1400a9f0d  test    edi, edi
0x1400a9f0f  js      loc_1400AA060
0x1400a9f15  xorps   xmm0, xmm0
0x1400a9f18  mov     esi, 1
0x1400a9f1d  movups  xmmword ptr [rsp+550h+ResultLength+8], xmm0
0x1400a9f22  movups  xmmword ptr [rbp+450h+Source2], xmm0
0x1400a9f26  movups  xmmword ptr [rbp+450h+Length], xmm0
0x1400a9f2a  cmp     [rsp+550h+var_4FC], r13d
0x1400a9f2f  jz      short loc_1400A9F35
0x1400a9f31  mov     [rsp+550h+var_500], esi
0x1400a9f35  mov     rcx, [rbx+88h]; DeviceObject
0x1400a9f3c  lea     rax, [rbp+450h+pcchLength]
0x1400a9f40  mov     [rsp+550h+var_510], esi; int
0x1400a9f44  mov     r14d, 30h ; '0'
0x1400a9f4a  mov     dword ptr [rsp+550h+var_518], esi; BOOLEAN
0x1400a9f4e  xor     r9d, r9d; InputBufferLength
0x1400a9f51  mov     [rsp+550h+var_520], rax; unsigned int *
0x1400a9f56  xor     r8d, r8d; InputBuffer
0x1400a9f59  lea     rax, [rsp+550h+ResultLength+8]
0x1400a9f5e  mov     [rsp+550h+var_528], r14d; ULONG
0x1400a9f63  mov     edx, 23203Bh; IoControlCode
0x1400a9f68  mov     [rsp+550h+Environment], rax; PVOID
0x1400a9f6d  call    ?GreDeviceIoControlImpl@@YAJPEAXK0K0KPEAKHH@Z; GreDeviceIoControlImpl(void *,ulong,void *,ulong,void *,ulong,ulong *,int,int)
0x1400a9f72  mov     r9d, dword ptr [rbp+450h+Source2+8]
0x1400a9f76  test    r9d, r9d
0x1400a9f79  jnz     loc_1400AA6AF
0x1400a9f7f  mov     eax, dword ptr [rsp+550h+var_4F0+4]
0x1400a9f83  lea     r8, [rsp+550h+ResultLength+8]; InputBuffer
0x1400a9f88  cmp     [rsp+550h+var_500], r13d
0x1400a9f8d  mov     edx, r13d
0x1400a9f90  mov     [rsp+550h+ResultLength+8], eax
0x1400a9f94  mov     r9d, r14d; InputBufferLength
0x1400a9f97  mov     eax, [rsp+550h+var_4FC]
0x1400a9f9b  setnz   dl
0x1400a9f9e  neg     eax
0x1400a9fa0  mov     [rsp+550h+var_510], esi; int
0x1400a9fa4  mov     eax, dword ptr [rsp+550h+var_4F0]
0x1400a9fa8  mov     [rbp+450h+var_4CC], eax
0x1400a9fab  sbb     ecx, ecx
0x1400a9fad  mov     rax, [rbx+0C8h]
0x1400a9fb4  and     ecx, 2
0x1400a9fb7  mov     [rbp+450h+Source2], rax
0x1400a9fbb  or      edx, ecx
0x1400a9fbd  mov     eax, [rbx+100h]
0x1400a9fc3  mov     rcx, [rbx+88h]; DeviceObject
0x1400a9fca  mov     dword ptr [rbp+450h+Source2+8], eax
0x1400a9fcd  mov     rax, [rbx+0D0h]
0x1400a9fd4  mov     [rbp+450h+Length], rax
0x1400a9fd8  mov     eax, [rbx+104h]
0x1400a9fde  mov     dword ptr [rsp+550h+var_518], esi; BOOLEAN
0x1400a9fe2  mov     dword ptr [rbp+450h+Length+8], eax
0x1400a9fe5  lea     rax, [rbp+450h+pcchLength]
0x1400a9fe9  mov     [rsp+550h+var_520], rax; unsigned int *
0x1400a9fee  mov     [rsp+550h+ResultLength+0Ch], edx
0x1400a9ff2  mov     edx, 23203Fh; IoControlCode
0x1400a9ff7  mov     [rsp+550h+var_528], r13d; ULONG
0x1400a9ffc  mov     [rsp+550h+Environment], r13; PVOID
0x1400aa001  mov     [rbp+450h+var_4D0], r13d
0x1400aa005  call    ?GreDeviceIoControlImpl@@YAJPEAXK0K0KPEAKHH@Z; GreDeviceIoControlImpl(void *,ulong,void *,ulong,void *,ulong,ulong *,int,int)
0x1400aa00a  test    edi, edi
0x1400aa00c  js      short loc_1400AA060
0x1400aa00e  cmp     dword ptr [rsp+550h+var_4F0+4], r13d
0x1400aa013  jnz     loc_1400AA818
0x1400aa019  cmp     [rsp+550h+var_500], r13d
0x1400aa01e  jnz     loc_1400AA824
0x1400aa024  cmp     [rsp+550h+var_4FC], r13d
0x1400aa029  jnz     loc_1400AA830
0x1400aa02f  cmp     dword ptr [rsp+550h+var_4F0], r13d
0x1400aa034  jnz     loc_1400AA83C
0x1400aa03a  mov     rcx, [rbx+0D0h]; Str1
0x1400aa041  test    rcx, rcx
0x1400aa044  jz      short loc_1400AA08A
0x1400aa046  lea     rdx, aRdpuddChainedD; "RDPUDD Chained DD"
0x1400aa04d  call    _wcsicmp
0x1400aa052  test    eax, eax
0x1400aa054  jnz     short loc_1400AA08A
0x1400aa056  bts     dword ptr [rbx+0A0h], 18h
0x1400aa05e  jmp     short loc_1400AA08A
0x1400aa060  mov     ecx, 1
0x1400aa065  call    ?DrvLogDisplayDriverEvent@@YAXW4_DISP_DRIVER_LOG@@@Z; DrvLogDisplayDriverEvent(_DISP_DRIVER_LOG)
0x1400aa06a  mov     rcx, [rbx+0C8h]; Buffer
0x1400aa071  test    rcx, rcx
0x1400aa074  jnz     loc_1400AA849
0x1400aa07a  mov     rcx, [rbx+0D0h]; Buffer
0x1400aa081  test    rcx, rcx
0x1400aa084  jnz     loc_1400AA85A
0x1400aa08a  mov     rcx, [rbp+450h+var_50]
0x1400aa091  xor     rcx, rsp; StackCookie
0x1400aa094  call    __security_check_cookie
0x1400aa099  lea     r11, [rsp+550h+var_30]
0x1400aa0a1  mov     rbx, [r11+50h]
0x1400aa0a5  movaps  xmm6, xmmword ptr [r11-10h]
0x1400aa0aa  mov     rsp, r11
0x1400aa0ad  pop     r15
0x1400aa0af  pop     r14
0x1400aa0b1  pop     r13
0x1400aa0b3  pop     r12
0x1400aa0b5  pop     rdi
0x1400aa0b6  pop     rsi
0x1400aa0b7  pop     rbp
0x1400aa0b8  retn
0x1400aa0ba  cmp     [rbx+104h], r13d
0x1400aa0c1  jnz     loc_1400A9EF2
0x1400aa0c7  xor     r9d, r9d; Length
0x1400aa0ca  mov     [rsp+550h+ResultLength+4], r13d
0x1400aa0cf  lea     rax, [rsp+550h+ResultLength+4]
0x1400aa0d4  xor     r8d, r8d; KeyInformation
0x1400aa0d7  mov     rcx, rsi; KeyHandle
0x1400aa0da  mov     [rsp+550h+Environment], rax; ResultLength
0x1400aa0df  lea     r15d, [r9+3]
0x1400aa0e3  mov     edx, r15d; KeyInformationClass
0x1400aa0e6  call    cs:__imp_ZwQueryKey
0x1400aa0ed  nop     dword ptr [rax+rax+00h]
0x1400aa0f2  mov     edi, eax
0x1400aa0f4  cmp     eax, 0C0000023h
0x1400aa0f9  jnz     loc_1400AA2BC
0x1400aa0ff  mov     ecx, [rsp+550h+ResultLength+4]
0x1400aa103  mov     edx, 73726447h
0x1400aa108  mov     rsi, r13
0x1400aa10b  call    PALLOCNOZ
0x1400aa110  mov     r14, rax
0x1400aa113  test    rax, rax
0x1400aa116  jz      loc_1400AA3AE
0x1400aa11c  mov     r9d, [rsp+550h+ResultLength+4]; Length
0x1400aa121  lea     rax, [rbp+450h+var_498]
0x1400aa125  mov     rcx, [rsp+550h+KeyHandle]; KeyHandle
0x1400aa12a  mov     r8, r14; KeyInformation
0x1400aa12d  mov     edx, r15d; KeyInformationClass
0x1400aa130  mov     [rsp+550h+Environment], rax; ResultLength
0x1400aa135  mov     [rbp+450h+var_498], r13d
0x1400aa139  call    cs:__imp_ZwQueryKey
0x1400aa140  nop     dword ptr [rax+rax+00h]
0x1400aa145  mov     edi, eax
0x1400aa147  test    eax, eax
0x1400aa149  js      loc_1400AA1EB
0x1400aa14f  mov     r8d, [r14]
0x1400aa152  mov     r15d, r13d
0x1400aa155  shr     r8d, 1
0x1400aa158  mov     edx, r13d
0x1400aa15b  jz      loc_1400AA1E4
0x1400aa161  mov     eax, edx
0x1400aa163  mov     ecx, edx
0x1400aa165  cmp     word ptr [r14+rax*2+4], 5Ch ; '\'
0x1400aa16c  cmovnz  ecx, r15d
0x1400aa170  inc     edx
0x1400aa172  mov     r15d, ecx
0x1400aa175  cmp     edx, r8d
0x1400aa178  jb      short loc_1400AA161
0x1400aa17a  test    ecx, ecx
0x1400aa17c  jz      short loc_1400AA1E4
0x1400aa17e  mov     eax, dword ptr cs:aVideo+8; "eo"
0x1400aa184  lea     r13d, [rcx+rcx]
0x1400aa188  movsd   xmm6, qword ptr cs:aVideo; "\\Video"
0x1400aa190  lea     ecx, [r13+0Eh]
0x1400aa194  mov     dword ptr [rbp+450h+pcchLength], eax
0x1400aa197  mov     edx, 73726447h
0x1400aa19c  movzx   eax, word ptr cs:aVideo+0Ch; ""
0x1400aa1a3  mov     word ptr [rsp+550h+ResultLength], ax
0x1400aa1a8  call    PALLOCNOZ
0x1400aa1ad  mov     rsi, rax
0x1400aa1b0  test    rax, rax
0x1400aa1b3  jz      loc_1400AA5C7
0x1400aa1b9  mov     r8d, r13d; Size
0x1400aa1bc  lea     rdx, [r14+4]; Src
0x1400aa1c0  mov     rcx, rax; void *
0x1400aa1c3  call    memmove
  ... truncated ...
```
