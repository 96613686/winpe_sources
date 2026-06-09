# CSpp::_DiscoverTornComponents(CWriterEntryArray *,CVolumeEntryMap *,ulong,_SPP_WRITER_COMPONENT_INFO *,int,ulong,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x180016258`
- end: `0x180016b0e`
- name: `?_DiscoverTornComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@PEAVCVolumeEntryMap@@KPEAU_SPP_WRITER_COMPONENT_INFO@@HKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z`
- size: `2230`
- prototype: `__int64 __fastcall(CSpp *this, struct CWriterEntryArray *, struct CVolumeEntryMap *, unsigned int, struct _SPP_WRITER_COMPONENT_INFO *, int, unsigned int, struct _SPP_ONDISK_SNAPSHOT_PROP *)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010e68`

## callees

- `0x180007650`
- `0x180008c74`
- `0x18000907c`
- `0x18000cc50`
- `0x18000e080`
- `0x18000e308`
- `0x18000e48c`
- `0x18000e54c`
- `0x180010800`
- `0x1800113b0`
- `0x18001212c`
- `0x1800123e4`
- `0x180016258`
- `0x18001b2a8`
- `0x180020710`
- `0x180020af4`
- `0x180020ba0`
- `0x180025380`
- `0x1800268b4`
- `0x1800269ac`
- `0x180034f3c`
- `0x1800350b8`
- `0x180035b00`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180016a2a`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180016a2a`

## string_xrefs

- `0x1800162c0`: `CSpp::_DiscoverTornComponents`
- `0x1800162ef`: `spp.dll`

## pseudocode

```c
__int64 __fastcall CSpp::_DiscoverTornComponents(
        CSpp *this,
        struct CWriterEntryArray *a2,
        struct CVolumeEntryMap *a3,
        unsigned int a4,
        struct _SPP_WRITER_COMPONENT_INFO *a5,
        int a6,
        unsigned int a7,
        struct _SPP_ONDISK_SNAPSHOT_PROP *a8)
{
  struct CWriterEntryArray *v9; // rsi
  __int16 v10; // ax
  struct CVolumeEntryMap *v11; // r12
  __int64 v12; // r14
  __int64 v13; // rdi
  CVolumeEntry *v14; // r15
  CVolumeEntry *v15; // r13
  int appended; // ebx
  int Instance; // eax
  CSpp *v18; // rcx
  unsigned int v19; // ebx
  unsigned int v20; // eax
  int v21; // eax
  __int16 v22; // r10
  int v23; // r8d
  __int64 v24; // rdx
  unsigned __int64 v25; // rax
  BOOL v26; // r10d
  __int64 v27; // rax
  unsigned int v28; // ebx
  unsigned int v29; // eax
  int v30; // eax
  int v31; // r10d
  struct _SPP_WRITER_COMPONENT_INFO *v32; // r11
  const unsigned __int16 *v33; // r9
  const unsigned __int16 *v34; // r8
  unsigned __int8 IsComponentInNeededComponents; // al
  int v36; // r8d
  char v37; // cl
  int v38; // eax
  struct _GUID v39; // xmm1
  CVolumeEntryMap *v40; // rax
  __int64 v41; // rcx
  bool v42; // sf
  __int16 i; // ax
  int v44; // eax
  int v45; // eax
  int v46; // r8d
  int v47; // esi
  struct _GUID v48; // xmm1
  bool v49; // zf
  CSpp *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // r8
  unsigned int v54; // [rsp+20h] [rbp-E0h]
  unsigned int v55; // [rsp+20h] [rbp-E0h]
  struct _SPP_WRITER_COMPONENT_INFO *v56; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v57; // [rsp+28h] [rbp-D8h]
  struct _SPP_WRITER_COMPONENT_INFO *v58; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v59; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v60; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v61; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v62; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v63; // [rsp+50h] [rbp-B0h]
  int v64; // [rsp+58h] [rbp-A8h]
  int v65; // [rsp+58h] [rbp-A8h]
  CVolumeEntry *v66; // [rsp+70h] [rbp-90h] BYREF
  int v67; // [rsp+78h] [rbp-88h] BYREF
  __int16 v68; // [rsp+7Ch] [rbp-84h]
  __int16 v69; // [rsp+7Eh] [rbp-82h]
  unsigned int v70; // [rsp+B0h] [rbp-50h]
  int v71; // [rsp+B4h] [rbp-4Ch]
  unsigned int v72; // [rsp+B8h] [rbp-48h]
  int v73; // [rsp+C0h] [rbp-40h] BYREF
  CVolumeEntryMap *v74[2]; // [rsp+C8h] [rbp-38h]
  CVolumeEntry *v75; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v77; // [rsp+E8h] [rbp-18h] BYREF
  struct CVolumeEntryMap *v78[2]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v79[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned int v80; // [rsp+110h] [rbp+10h]
  struct _GUID v81; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v82; // [rsp+130h] [rbp+30h] BYREF
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  struct _GUID v85; // [rsp+140h] [rbp+40h] BYREF

  v9 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v67, "CSpp::_DiscoverTornComponents", 7312, 1);
  v83 = -2130706176;
  v78[0] = 0;
  v79[0] = (unsigned __int16 *)&FileName;
  v82 = L"spp.dll";
  v77 = 0;
  v10 = 7337;
  v76 = 0;
  v11 = 0;
  v66 = 0;
  v12 = 0;
  v75 = 0;
  v13 = 0;
  v73 = 0;
  v14 = 0;
  v79[1] = 0;
  v15 = 0;
  v84 = -2130705921;
  *(_OWORD *)v74 = 0;
  if ( !v9 )
    goto LABEL_5;
  v68 = 7337;
  if ( !a3 && !a5 && !a6 )
  {
    v10 = 7338;
LABEL_5:
    appended = -2147024809;
LABEL_6:
    v67 = appended;
    goto LABEL_7;
  }
  v67 = 0;
  v68 = 7338;
  Instance = CVolumeEntryMap::CreateInstance(v78);
  v11 = v78[0];
  appended = Instance;
  v67 = Instance;
  v42 = Instance < 0;
  v10 = 7340;
  if ( v42 )
    goto LABEL_7;
  v68 = 7340;
  v19 = 0;
  v20 = *((_DWORD *)v9 + 2);
  v80 = v20;
  while ( 1 )
  {
    v72 = v19;
    if ( v19 >= v20 )
      break;
    if ( v12 )
    {
      v77 = 0;
      CWriterEntry::Release((CWriterEntry *)v12);
    }
    v21 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(v9, v19, &v77);
    v12 = v77;
    appended = v21;
    v67 = v21;
    if ( v21 < 0 )
    {
      v69 = v22;
      goto LABEL_100;
    }
    v68 = v22;
    if ( !*(_DWORD *)(v77 + 72) )
    {
      v23 = 0;
      if ( a5 )
      {
        v24 = 0;
        *(_OWORD *)v78 = *(_OWORD *)(v77 + 32);
        while ( 1 )
        {
          if ( (unsigned int)v24 >= a4 )
            goto LABEL_27;
          v18 = (CSpp *)(6 * v24);
          v25 = *((_QWORD *)a5 + 6 * v24) - (unsigned __int64)v78[0];
          if ( !v25 )
            v25 = *((_QWORD *)a5 + 6 * v24 + 1) - (unsigned __int64)v78[1];
          if ( !v25 )
            break;
          v24 = (unsigned int)(v24 + 1);
        }
        v23 = 1;
      }
LABEL_27:
      v26 = *(_DWORD *)(v77 + 76) && a6;
      v27 = *(_QWORD *)(v77 + 64);
      v71 = v23 | v26;
      v28 = 0;
      v29 = *(_DWORD *)(v27 + 8);
      LODWORD(v78[0]) = v29;
      while ( 2 )
      {
        v70 = v28;
        if ( v28 >= v29 )
          break;
        if ( v13 )
        {
          v76 = 0;
          CComponentEntry::Release((CComponentEntry *)v13);
        }
        v30 = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(*(_QWORD *)(v12 + 64), v28, &v76);
        v13 = v76;
        appended = v30;
        v67 = v30;
        v42 = v30 < 0;
        v10 = 7376;
        if ( v42 )
          goto LABEL_7;
        v68 = 7376;
        if ( !v31 )
          goto LABEL_52;
        v33 = *(const unsigned __int16 **)(v76 + 40);
        v34 = *(const unsigned __int16 **)(v76 + 8);
        v81 = *(struct _GUID *)(v12 + 32);
        IsComponentInNeededComponents = CSpp::_IsComponentInNeededComponents(v18, &v81, v34, v33, a4, v32);
        if ( !a6 || !*(_DWORD *)(v12 + 76) || (v37 = 1, !*(_DWORD *)(v13 + 112)) )
          v37 = 0;
        LOBYTE(v18) = IsComponentInNeededComponents | v37;
        if ( (_BYTE)v18 )
        {
          if ( *(_DWORD *)(v13 + 104) == 1 )
          {
            v38 = *(_DWORD *)(v13 + 144);
            if ( v38 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
                WPP_SF_SSD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  123,
                  v36,
                  *(_QWORD *)(v13 + 56),
                  *(_QWORD *)(v13 + 24),
                  v38);
              Log_SPP_ERROR_WRITER(
                (struct CSxFunctionTracer *)&v67,
                0x4003u,
                0x1CEFu,
                *(const unsigned __int16 **)(v12 + 8),
                0,
                *(_DWORD *)(v13 + 144),
                0);
              if ( *(int *)(v13 + 144) < 0 )
              {
                CBsString::Empty((CBsString *)v79);
                appended = CBsString::FormatErrorCode(
                             (CBsString *)v79,
                             *(_DWORD *)(v13 + 144),
                             1u,
                             (const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *)&v82,
                             v54,
                             v56);
                v67 = appended;
                v10 = 7416;
                if ( appended < 0 )
                  goto LABEL_7;
                v68 = 7416;
              }
              v39 = *(struct _GUID *)(v12 + 32);
              v64 = *(_DWORD *)(v13 + 144);
              v62 = *(unsigned __int16 **)(v13 + 40);
              v60 = *(unsigned __int16 **)(v13 + 8);
              v57 = *(unsigned __int16 **)(v12 + 8);
              v81 = *(struct _GUID *)(v12 + 48);
              v85 = v39;
              appended = CSpp::_CacheBadWritersComponents(
                           this,
                           0,
                           v9,
                           &v85,
                           &v81,
                           v57,
                           0x81000112,
                           0,
                           VSS_WS_UNKNOWN,
                           v60,
                           v62,
                           v64,
                           v79[0]);
              v67 = appended;
              v10 = 7430;
              if ( appended < 0 )
                goto LABEL_7;
              v68 = 7430;
              *((_BYTE *)this + 41) = 1;
              goto LABEL_52;
            }
          }
          v45 = CSpp::_AddGoodVolumesToMap(this, *(struct CVolumeEntryMap **)(v13 + 120), a7, v11);
          v47 = v45;
          if ( v45 == -2130706168 || v45 == -2130706161 )
          {
            *(_DWORD *)(v13 + 104) = 1;
            *(_DWORD *)(v13 + 144) = v45;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
              WPP_SF_SSD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                124,
                v46,
                *(_QWORD *)(v13 + 56),
                *(_QWORD *)(v13 + 24),
                v45);
            Log_SPP_ERROR_WRITER(
              (struct CSxFunctionTracer *)&v67,
              0x4003u,
              0x1D22u,
              *(const unsigned __int16 **)(v12 + 8),
              0,
              v47,
              0);
            if ( v47 < 0 )
            {
              CBsString::Empty((CBsString *)v79);
              appended = CBsString::FormatErrorCode(
                           (CBsString *)v79,
                           v47,
                           1u,
                           (const struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *)&v82,
                           v55,
                           v58);
              v67 = appended;
              v10 = 7469;
              if ( appended < 0 )
                goto LABEL_7;
              v68 = 7469;
            }
            v48 = *(struct _GUID *)(v12 + 32);
            v65 = v47;
            v9 = a2;
            v63 = *(unsigned __int16 **)(v13 + 40);
            v61 = *(unsigned __int16 **)(v13 + 8);
            v59 = *(unsigned __int16 **)(v12 + 8);
            v85 = *(struct _GUID *)(v12 + 48);
            v81 = v48;
            v67 = CSpp::_CacheBadWritersComponents(
                    this,
                    0,
                    a2,
                    &v81,
                    &v85,
                    v59,
                    0x81000112,
                    0,
                    VSS_WS_UNKNOWN,
                    v61,
                    v63,
                    v65,
                    v79[0]);
            appended = v67;
            if ( v67 < 0 )
            {
              v10 = 7482;
              goto LABEL_7;
            }
            v67 = 0;
            *((_BYTE *)this + 41) = 1;
          }
          else
          {
            v67 = v45;
            appended = v45;
            if ( v45 < 0 )
            {
              v10 = 7487;
              goto LABEL_7;
            }
            v9 = a2;
          }
          v68 = 7487;
        }
        else
        {
LABEL_52:
          if ( *(_DWORD *)(v13 + 104) != 1 )
          {
            v40 = v74[0];
            if ( v74[0] )
            {
              CVolumeEntryMap::Release(v74[0]);
              v40 = 0;
              v74[0] = 0;
            }
            v73 = 0;
            v74[1] = 0;
            v41 = *(_QWORD *)(v13 + 120);
            if ( !v41 )
            {
              appended = -2147024809;
              goto LABEL_93;
            }
            if ( v40 )
            {
              appended = -2147418113;
LABEL_93:
              v10 = 7498;
              goto LABEL_6;
            }
            v74[0] = *(CVolumeEntryMap **)(v13 + 120);
            _InterlockedIncrement((volatile signed __int32 *)(v41 + 16));
            v73 = *((_DWORD *)v74[0] + 2);
            v74[1] = 0;
            v67 = 0;
            v68 = 7498;
            if ( v14 )
            {
              v66 = 0;
              CVolumeEntry::Release(v14);
            }
            appended = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v73, &v66);
            v67 = appended;
            v42 = appended < 0;
            for ( i = 7500; ; i = 7522 )
            {
              if ( v42 )
              {
                v14 = v66;
                v69 = i;
                goto LABEL_100;
              }
              v68 = i;
              if ( appended == 1 )
              {
                v14 = v66;
                goto LABEL_86;
              }
              if ( v15 )
              {
                v75 = 0;
                CVolumeEntry::Release(v15);
              }
              v14 = v66;
              v44 = CSxRefMap<CPathCache,CPathCacheNode>::Find(a3, v66, &v75);
              v15 = v75;
              appended = v44;
              v67 = v44;
              v42 = v44 < 0;
              v10 = 7504;
              if ( v42 )
                goto LABEL_7;
              v68 = 7504;
              if ( !v75 )
                break;
              if ( v14 )
              {
                v66 = 0;
                CVolumeEntry::Release(v14);
              }
              appended = CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(&v73, &v66);
              v67 = appended;
              v42 = appended < 0;
            }
            *(_DWORD *)(v13 + 104) = 1;
            *(_DWORD *)(v13 + 144) = -2130706161;
            v18 = (CSpp *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
              WPP_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                125,
                (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
                *(_QWORD *)(v13 + 56),
                *(_QWORD *)(v13 + 24));
          }
        }
LABEL_86:
        v28 = v70 + 1;
        v29 = (unsigned int)v78[0];
        continue;
      }
    }
    v20 = v80;
    v19 = v72 + 1;
  }
  appended = CSpp::_AppendVolumeMapToMap(v18, a3, v11);
  v67 = appended;
  v10 = 7527;
  if ( appended < 0 )
  {
LABEL_7:
    v69 = v10;
    goto LABEL_100;
  }
  v68 = 7527;
  v49 = RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)v11) == 0;
  v10 = 7531;
  if ( v49 )
  {
    appended = -2130706164;
    goto LABEL_6;
  }
  v67 = 0;
  v68 = 7531;
  appended = CSpp::_BuildVolumeProps(v50, v11, (unsigned int *)a8 + 23, (struct _SPP_ONDISK_VOLUME_PROP **)a8 + 12);
  v67 = appended;
  v10 = 7536;
  if ( appended < 0 )
    goto LABEL_7;
  v68 = 7536;
LABEL_100:
  CBsString::_Release((CBsString *)v79);
  if ( v74[0] )
  {
    CVolumeEntryMap::Release(v74[0]);
    v74[0] = 0;
  }
  v73 = 0;
  v74[1] = 0;
  if ( v15 )
    CVolumeEntry::Release(v15);
  if ( v14 )
    CVolumeEntry::Release(v14);
  if ( v13 )
    CComponentEntry::Release((CComponentEntry *)v13);
  if ( v12 )
    CWriterEntry::Release((CWriterEntry *)v12);
  if ( v11 )
    CVolumeEntryMap::Release(v11);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v67, v51, v52);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180016258  mov     rax, rsp
0x18001625b  mov     [rax+20h], r9d
0x18001625f  mov     [rax+18h], r8
0x180016263  mov     [rax+10h], rdx
0x180016267  mov     [rax+8], rcx
0x18001626b  push    rbp
0x18001626c  push    rbx
0x18001626d  push    rsi
0x18001626e  push    rdi
0x18001626f  push    r12
0x180016271  push    r13
0x180016273  push    r14
0x180016275  push    r15
0x180016277  lea     rbp, [rsp-58h]
0x18001627c  sub     rsp, 158h
0x180016283  mov     rbx, r8
0x180016286  mov     rsi, rdx
0x180016289  mov     rcx, cs:WPP_GLOBAL_Control
0x180016290  lea     rax, WPP_GLOBAL_Control
0x180016297  cmp     rcx, rax
0x18001629a  jz      short loc_1800162BA
0x18001629c  test    dword ptr [rcx+1Ch], 20000000h
0x1800162a3  jz      short loc_1800162BA
0x1800162a5  mov     rcx, [rcx+10h]
0x1800162a9  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800162b0  mov     edx, 7Ah ; 'z'
0x1800162b5  call    WPP_SF_
0x1800162ba  mov     r9d, 1; unsigned __int16
0x1800162c0  lea     rdx, aCsppDiscoverto; "CSpp::_DiscoverTornComponents"
0x1800162c7  mov     r8d, 1C90h; unsigned __int16
0x1800162cd  lea     rcx, [rsp+190h+var_118]; this
0x1800162d2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800162d7  xor     ecx, ecx
0x1800162d9  mov     [rbp+90h+var_58], 81000100h
0x1800162e0  mov     [rbp+90h+var_A0], rcx
0x1800162e4  lea     rax, FileName
0x1800162eb  mov     [rbp+90h+var_90], rax
0x1800162ef  lea     rax, aSppDll_0; "spp.dll"
0x1800162f6  mov     [rbp+90h+var_60], rax
0x1800162fa  xorps   xmm0, xmm0
0x1800162fd  mov     [rbp+90h+var_A8], rcx
0x180016301  mov     eax, 1CA9h
0x180016306  mov     [rbp+90h+var_B0], rcx
0x18001630a  mov     r12d, ecx
0x18001630d  mov     [rsp+190h+var_120], rcx
0x180016312  mov     r14d, ecx
0x180016315  mov     [rbp+90h+var_B8], rcx
0x180016319  mov     edi, ecx
0x18001631b  mov     [rbp+90h+var_D0], ecx
0x18001631e  mov     r15d, ecx
0x180016321  mov     [rbp+90h+var_88], rcx
0x180016325  mov     r13d, ecx
0x180016328  mov     [rbp+90h+var_54], 810001FFh
0x18001632f  movdqu  xmmword ptr [rbp+90h+var_C8], xmm0
0x180016334  test    rsi, rsi
0x180016337  jnz     short loc_18001634C
0x180016339  mov     ebx, 80070057h
0x18001633e  mov     [rsp+190h+var_118], ebx
0x180016342  mov     [rsp+190h+var_112], ax
0x180016347  jmp     loc_180016A7F
0x18001634c  mov     [rsp+190h+var_114], ax
0x180016351  test    rbx, rbx
0x180016354  jnz     short loc_18001636E
0x180016356  cmp     [rbp+90h+arg_20], rcx
0x18001635d  jnz     short loc_18001636E
0x18001635f  cmp     [rbp+90h+arg_28], ecx
0x180016365  jnz     short loc_18001636E
0x180016367  mov     eax, 1CAAh
0x18001636c  jmp     short loc_180016339
0x18001636e  mov     [rsp+190h+var_118], ecx
0x180016372  mov     eax, 1CAAh
0x180016377  lea     rcx, [rbp+90h+var_A0]; struct CVolumeEntryMap **
0x18001637b  mov     [rsp+190h+var_114], ax
0x180016380  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x180016385  mov     r12, [rbp+90h+var_A0]
0x180016389  mov     ebx, eax
0x18001638b  mov     [rsp+190h+var_118], eax
0x18001638f  test    eax, eax
0x180016391  mov     eax, 1CACh
0x180016396  js      short loc_180016342
0x180016398  mov     [rsp+190h+var_114], ax
0x18001639d  xor     ebx, ebx
0x18001639f  mov     eax, [rsi+8]
0x1800163a2  mov     r10d, 1CB8h
0x1800163a8  mov     [rbp+90h+var_80], eax
0x1800163ab  mov     [rbp+90h+var_D8], ebx
0x1800163ae  cmp     ebx, eax
0x1800163b0  jnb     loc_1800169FF
0x1800163b6  test    r14, r14
0x1800163b9  jz      short loc_1800163D1
0x1800163bb  mov     rcx, r14; this
0x1800163be  mov     [rbp+90h+var_A8], 0
0x1800163c6  call    ?Release@CWriterEntry@@QEAAKXZ; CWriterEntry::Release(void)
0x1800163cb  mov     r10d, 1CB8h
0x1800163d1  lea     r8, [rbp+90h+var_A8]
0x1800163d5  mov     edx, ebx
0x1800163d7  mov     rcx, rsi
0x1800163da  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x1800163df  mov     r14, [rbp+90h+var_A8]
0x1800163e3  mov     ebx, eax
0x1800163e5  mov     [rsp+190h+var_118], eax
0x1800163e9  test    eax, eax
0x1800163eb  js      loc_1800169F4
0x1800163f1  mov     [rsp+190h+var_114], r10w
0x1800163f7  cmp     dword ptr [r14+48h], 0
0x1800163fc  jnz     loc_1800169AE
0x180016402  mov     r11, [rbp+90h+arg_20]
0x180016409  xor     r8d, r8d
0x18001640c  test    r11, r11
0x18001640f  jz      short loc_180016452
0x180016411  movups  xmm0, xmmword ptr [r14+20h]
0x180016416  mov     r9d, [rbp+90h+arg_18]
0x18001641d  xor     edx, edx
0x18001641f  movdqu  xmmword ptr [rbp+90h+var_A0], xmm0
0x180016424  cmp     edx, r9d
0x180016427  jnb     short loc_180016452
0x180016429  lea     rcx, [rdx+rdx*2]
0x18001642d  add     rcx, rcx
0x180016430  mov     rax, [r11+rcx*8]
0x180016434  sub     rax, [rbp+90h+var_A0]
0x180016438  jnz     short loc_180016443
0x18001643a  mov     rax, [r11+rcx*8+8]
0x18001643f  sub     rax, [rbp+90h+var_A0+8]
0x180016443  test    rax, rax
0x180016446  jz      short loc_18001644C
0x180016448  inc     edx
0x18001644a  jmp     short loc_180016424
0x18001644c  mov     r8d, 1
0x180016452  cmp     dword ptr [r14+4Ch], 0
0x180016457  jz      short loc_18001646A
0x180016459  cmp     [rbp+90h+arg_28], 0
0x180016460  jz      short loc_18001646A
0x180016462  mov     r10d, 1
0x180016468  jmp     short loc_18001646D
0x18001646a  xor     r10d, r10d
0x18001646d  mov     rax, [r14+40h]
0x180016471  or      r10d, r8d
0x180016474  mov     [rbp+90h+var_DC], r10d
0x180016478  xor     ebx, ebx
0x18001647a  mov     eax, [rax+8]
0x18001647d  mov     dword ptr [rbp+90h+var_A0], eax
0x180016480  mov     [rbp+90h+var_E0], ebx
0x180016483  cmp     ebx, eax
0x180016485  jnb     loc_1800169A8
0x18001648b  test    rdi, rdi
0x18001648e  jz      short loc_1800164AB
0x180016490  mov     rcx, rdi; this
0x180016493  mov     [rbp+90h+var_B0], 0
0x18001649b  call    ?Release@CComponentEntry@@QEAAKXZ; CComponentEntry::Release(void)
0x1800164a0  mov     r10d, [rbp+90h+var_DC]
0x1800164a4  mov     r11, [rbp+90h+arg_20]
0x1800164ab  mov     rcx, [r14+40h]
0x1800164af  lea     r8, [rbp+90h+var_B0]
0x1800164b3  mov     edx, ebx
0x1800164b5  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x1800164ba  mov     rdi, [rbp+90h+var_B0]
0x1800164be  mov     ebx, eax
0x1800164c0  mov     [rsp+190h+var_118], eax
0x1800164c4  test    eax, eax
0x1800164c6  mov     eax, 1CD0h
0x1800164cb  js      loc_180016342
0x1800164d1  xor     ebx, ebx
0x1800164d3  mov     [rsp+190h+var_114], ax
0x1800164d8  test    r10d, r10d
0x1800164db  jz      loc_180016682
0x1800164e1  movups  xmm0, xmmword ptr [r14+20h]
0x1800164e6  mov     eax, [rbp+90h+arg_18]
0x1800164ec  lea     rdx, [rbp+90h+var_70]; struct _GUID
0x1800164f0  mov     r9, [rdi+28h]; unsigned __int16 *
0x1800164f4  mov     r8, [rdi+8]; unsigned __int16 *
0x1800164f8  mov     [rsp+190h+var_168], r11; struct _SPP_WRITER_COMPONENT_INFO *
0x1800164fd  movdqu  xmmword ptr [rbp+90h+var_70.Data1], xmm0
0x180016502  mov     dword ptr [rsp+190h+var_170], eax; unsigned int
0x180016506  call    ?_IsComponentInNeededComponents@CSpp@@AEAAEU_GUID@@PEBG1KPEAU_SPP_WRITER_COMPONENT_INFO@@@Z; CSpp::_IsComponentInNeededComponents(_GUID,ushort const *,ushort const *,ulong,_SPP_WRITER_COMPONENT_INFO *)
0x18001650b  cmp     [rbp+90h+arg_28], ebx
0x180016511  jz      short loc_180016520
0x180016513  cmp     [r14+4Ch], ebx
0x180016517  jz      short loc_180016520
0x180016519  mov     cl, 1
0x18001651b  cmp     [rdi+70h], ebx
0x18001651e  jnz     short loc_180016522
0x180016520  mov     cl, bl
0x180016522  or      cl, al
0x180016524  jz      loc_180016682
0x18001652a  cmp     dword ptr [rdi+68h], 1
0x18001652e  jnz     loc_1800167AE
0x180016534  mov     eax, [rdi+90h]
0x18001653a  test    eax, eax
0x18001653c  jns     loc_1800167AE
0x180016542  mov     rcx, cs:WPP_GLOBAL_Control
0x180016549  lea     rdx, WPP_GLOBAL_Control
0x180016550  cmp     rcx, rdx
0x180016553  jz      short loc_18001657D
0x180016555  test    dword ptr [rcx+1Ch], 8000000h
0x18001655c  jz      short loc_18001657D
0x18001655e  mov     r9, [rdi+38h]
0x180016562  mov     edx, 7Bh ; '{'
0x180016567  mov     rcx, [rcx+10h]
0x18001656b  mov     dword ptr [rsp+190h+var_168], eax
0x18001656f  mov     rax, [rdi+18h]
0x180016573  mov     [rsp+190h+var_170], rax
0x180016578  call    WPP_SF_SSD
0x18001657d  mov     eax, [rdi+90h]
0x180016583  lea     rcx, [rsp+190h+var_118]; this
0x180016588  mov     r9, [r14+8]; unsigned __int16 *
0x18001658c  mov     edx, 4003h; unsigned int
0x180016591  mov     [rsp+190h+var_160], ebx; int
0x180016595  mov     r8d, 1CEFh; unsigned int
0x18001659b  mov     dword ptr [rsp+190h+var_168], eax; struct ___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY *
0x18001659f  mov     [rsp+190h+var_170], rbx; unsigned int
0x1800165a4  call    ?Log_SPP_ERROR_WRITER@@YAJPEAVCSxFunctionTracer@@KKPEBG1JJ@Z; Log_SPP_ERROR_WRITER(CSxFunctionTracer *,ulong,ulong,ushort const *,ushort const *,long,long)
0x1800165a9  cmp     [rdi+90h], ebx
0x1800165af  jge     short loc_1800165ED
0x1800165b1  lea     rcx, [rbp+90h+var_90]; this
0x1800165b5  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x1800165ba  mov     edx, [rdi+90h]; int
0x1800165c0  lea     rcx, [rbp+90h+var_90]; this
0x1800165c4  lea     r9, [rbp+90h+var_60]; struct ___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY *
0x1800165c8  mov     r8d, 1; unsigned int
0x1800165ce  call    ?FormatErrorCode@CBsString@@QEAAJJKPEBU___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY@@KPEBU___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY@@@Z; CBsString::FormatErrorCode(long,ulong,___FORMAT_ERRORCODE_SEARCH_DLL_ENTRY const *,ulong,___FORMAT_ERRORCODE_ERROR_MAP_ENTRTY const *)
0x1800165d3  mov     ebx, eax
0x1800165d5  mov     [rsp+190h+var_118], eax
0x1800165d9  test    eax, eax
0x1800165db  mov     eax, 1CF8h
0x1800165e0  js      loc_180016342
0x1800165e6  mov     [rsp+190h+var_114], ax
0x1800165eb  xor     ebx, ebx
0x1800165ed  mov     rax, [rbp+90h+var_90]
0x1800165f1  lea     r9, [rbp+90h+var_50]; struct _GUID
0x1800165f5  movups  xmm0, xmmword ptr [r14+30h]
0x1800165fa  mov     rcx, [rbp+90h+arg_0]; this
0x180016601  mov     r8, rsi; struct CWriterEntryArray *
0x180016604  movups  xmm1, xmmword ptr [r14+20h]
0x180016609  mov     [rsp+190h+var_130], rax; unsigned __int16 *
0x18001660e  xor     edx, edx; struct IVssBackupComponents *
0x180016610  mov     eax, [rdi+90h]
0x180016616  mov     [rsp+190h+var_138], eax; int
0x18001661a  mov     rax, [rdi+28h]
0x18001661e  mov     [rsp+190h+var_140], rax; unsigned __int16 *
0x180016623  mov     rax, [rdi+8]
0x180016627  mov     [rsp+190h+var_148], rax; unsigned __int16 *
0x18001662c  mov     rax, [r14+8]
0x180016630  mov     [rsp+190h+var_150], ebx; enum _VSS_WRITER_STATE
0x180016634  mov     [rsp+190h+var_158], ebx; int
0x180016638  mov     [rsp+190h+var_160], 81000112h; int
0x180016640  mov     [rsp+190h+var_168], rax; unsigned __int16 *
0x180016645  lea     rax, [rbp+90h+var_70]
0x180016649  mov     [rsp+190h+var_170], rax; struct _GUID
0x18001664e  movdqu  xmmword ptr [rbp+90h+var_70.Data1], xmm0
0x180016653  movdqu  xmmword ptr [rbp+90h+var_50.Data1], xmm1
0x180016658  call    ?_CacheBadWritersComponents@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@U_GUID@@2PEBGJJW4_VSS_WRITER_STATE@@33J3@Z; CSpp::_CacheBadWritersComponents(IVssBackupComponents *,CWriterEntryArray *,_GUID,_GUID,ushort const *,long,long,_VSS_WRITER_STATE,ushort const *,ushort const *,long,ushort const *)
0x18001665d  mov     ebx, eax
0x18001665f  mov     [rsp+190h+var_118], eax
0x180016663  test    eax, eax
0x180016665  mov     eax, 1D06h
0x18001666a  js      loc_180016342
0x180016670  mov     [rsp+190h+var_114], ax
0x180016675  xor     ebx, ebx
0x180016677  mov     rax, [rbp+90h+arg_0]
0x18001667e  mov     byte ptr [rax+29h], 1
0x180016682  cmp     dword ptr [rdi+68h], 1
0x180016686  jz      loc_180016990
0x18001668c  mov     rax, [rbp+90h+var_C8]
0x180016690  test    rax, rax
0x180016693  jz      short loc_1800166A4
0x180016695  mov     rcx, rax; this
0x180016698  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x18001669d  mov     rax, rbx
0x1800166a0  mov     [rbp+90h+var_C8], rbx
0x1800166a4  mov     [rbp+90h+var_D0], ebx
0x1800166a7  mov     [rbp+90h+var_C8+8], rbx
0x1800166ab  mov     rcx, [rdi+78h]
0x1800166af  test    rcx, rcx
0x1800166b2  jz      loc_1800169E5
0x1800166b8  test    rax, rax
0x1800166bb  jnz     loc_1800169DE
0x1800166c1  mov     [rbp+90h+var_C8], rcx
0x1800166c5  lock inc dword ptr [rcx+10h]
0x1800166c9  mov     rax, [rbp+90h+var_C8]
0x1800166cd  mov     ecx, [rax+8]
0x1800166d0  mov     [rbp+90h+var_D0], ecx
0x1800166d3  mov     [rbp+90h+var_C8+8], rbx
0x1800166d7  mov     [rsp+190h+var_118], ebx
0x1800166db  mov     eax, 1D4Ah
0x1800166e0  mov     [rsp+190h+var_114], ax
0x1800166e5  test    r15, r15
0x1800166e8  jz      short loc_1800166F7
0x1800166ea  mov     rcx, r15; this
0x1800166ed  mov     [rsp+190h+var_120], rbx
0x1800166f2  call    ?Release@CVolumeEntry@@QEAAKXZ; CVolumeEntry::Release(void)
0x1800166f7  lea     rdx, [rsp+190h+var_120]
0x1800166fc  lea     rcx, [rbp+90h+var_D0]
0x180016700  call    ?Next@CSxIter@?$CSxRefMap@VCSxStringMap@@VCSxStringEntry@@@@QEAAJPEAPEAVCSxStringEntry@@@Z; CSxRefMap<CSxStringMap,CSxStringEntry>::CSxIter::Next(CSxStringEntry * *)
0x180016705  mov     ebx, eax
0x180016707  mov     [rsp+190h+var_118], eax
0x18001670b  test    eax, eax
0x18001670d  mov     eax, 1D4Ch
0x180016712  js      loc_1800169CF
0x180016718  mov     [rsp+190h+var_114], ax
0x18001671d  cmp     ebx, 1
  ... truncated ...
```
