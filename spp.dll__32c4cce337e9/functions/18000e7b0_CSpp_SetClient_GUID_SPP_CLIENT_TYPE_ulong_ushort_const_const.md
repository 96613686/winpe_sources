# CSpp::SetClient(_GUID,_SPP_CLIENT_TYPE,ulong,ushort const * const *)

- ea: `0x18000e7b0`
- end: `0x18000f25b`
- name: `?SetClient@CSpp@@UEAAJU_GUID@@W4_SPP_CLIENT_TYPE@@KPEBQEBG@Z`
- size: `2731`
- prototype: `__int64 __fastcall(CSpp *, struct _GUID *, int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004188`
- `0x18000702c`
- `0x1800073a0`
- `0x180007424`
- `0x180008654`
- `0x180008c74`
- `0x18000c894`
- `0x18000e040`
- `0x18000e208`
- `0x18000e288`
- `0x18000e7b0`
- `0x18000f888`
- `0x1800141ac`
- `0x18001be74`
- `0x180020ba0`
- `0x1800212ac`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800299c4`
- `0x180029ce0`
- `0x18002ce10`
- `0x18002d1e0`
- `0x18002e9b8`
- `0x1800346c0`
- `0x18003532c`
- `0x180035b00`
- `0x180035b76`
- `0x180035b9a`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x18000e800`
- `ntdll!RtlGetCurrentTransaction` at `0x18000e800`
- `ntdll!RtlSetCurrentTransaction` at `0x18000e80b`
- `ntdll!RtlSetCurrentTransaction` at `0x18000f228`
- `ntdll!RtlSetCurrentTransaction` at `0x18000e80b`
- `ntdll!RtlSetCurrentTransaction` at `0x18000f228`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ebde`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000ebde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f215`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f1ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f215`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f0f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f0f1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ec0c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ec1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f123`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ec0c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ec1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000f123`

## pseudocode

```c
__int64 __fastcall CSpp::SetClient(CSpp *a1, struct _GUID *a2, int a3, unsigned int a4, __int64 a5)
{
  CSpp *v7; // r14
  __int64 CurrentTransaction; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  struct CSppStringMapEntry *v11; // rsi
  HKEY v12; // rbx
  const BYTE **v13; // r15
  CSppStringMap *v14; // r13
  bool v15; // zf
  __int16 v16; // ax
  struct _GUID v17; // xmm0
  unsigned int i; // r14d
  int v19; // eax
  int v20; // eax
  bool v21; // sf
  int v22; // eax
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  unsigned int v25; // r14d
  __int64 v26; // r12
  unsigned int v27; // eax
  __int64 v28; // r14
  _WORD *v29; // rax
  int v30; // eax
  CSppStringMapEntry *v31; // rcx
  int v32; // eax
  int v33; // eax
  CSppStringMapEntry *v34; // rcx
  CSppStringMapEntry *v35; // r14
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // r8
  const unsigned __int16 *v39; // rdx
  __int64 v40; // r8
  int v41; // eax
  unsigned int v42; // r14d
  __int64 v43; // rdx
  __int64 v44; // r8
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  int UniqueVolumeForPath; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v48; // [rsp+3Ch] [rbp-C4h]
  __int16 v49; // [rsp+3Eh] [rbp-C2h]
  CSppStringMap *v50; // [rsp+70h] [rbp-90h] BYREF
  CSppStringMapEntry *v51; // [rsp+78h] [rbp-88h] BYREF
  struct CSppStringMapEntry *v52; // [rsp+80h] [rbp-80h] BYREF
  HKEY v53; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v55; // [rsp+94h] [rbp-6Ch]
  int v56; // [rsp+98h] [rbp-68h]
  HKEY v57; // [rsp+A0h] [rbp-60h] BYREF
  CSppStringMap *v58; // [rsp+A8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v60[2]; // [rsp+B8h] [rbp-48h] BYREF
  CSpp *v61; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v62[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v63; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v64[3]; // [rsp+E8h] [rbp-18h] BYREF
  struct _GUID v65; // [rsp+100h] [rbp+0h] BYREF
  int v66; // [rsp+110h] [rbp+10h] BYREF
  __int128 v67; // [rsp+114h] [rbp+14h]
  _BYTE v68[28]; // [rsp+124h] [rbp+24h] BYREF
  OLECHAR sz; // [rsp+140h] [rbp+40h] BYREF
  char v70[78]; // [rsp+142h] [rbp+42h] BYREF
  WCHAR szVolumeName; // [rsp+190h] [rbp+90h] BYREF
  char v72[110]; // [rsp+192h] [rbp+92h] BYREF

  v63 = a5;
  v55 = a4;
  v7 = a1;
  v56 = a3;
  v61 = a1;
  CurrentTransaction = RtlGetCurrentTransaction();
  RtlSetCurrentTransaction(0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF__guid_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, a2, a4, a5);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&UniqueVolumeForPath, "CSpp::SetClient", 10116, 1);
  v11 = 0;
  v12 = 0;
  hKey = 0;
  v53 = 0;
  v57 = 0;
  v64[0] = (unsigned __int16 *)&FileName;
  v64[1] = 0;
  v62[0] = (unsigned __int16 *)&FileName;
  v62[1] = 0;
  v60[0] = (unsigned __int16 *)&FileName;
  v60[1] = 0;
  sz = 0;
  memset_0(v70, 0, 0x4Cu);
  szVolumeName = 0;
  memset_0(v72, 0, 0x64u);
  v54 = 0;
  memset(v68, 0, sizeof(v68));
  Block = 0;
  v66 = 0;
  v50 = 0;
  v13 = 0;
  v58 = 0;
  v67 = 0;
  v14 = 0;
  v51 = 0;
  v52 = 0;
  v15 = memcmp_0(a2, &GUID_NULL, 0x10u) == 0;
  v16 = 10137;
  if ( v15 || (v48 = 10137, v16 = 10138, (unsigned int)(v56 - 1) > 1) )
  {
    UniqueVolumeForPath = -2147024809;
    goto LABEL_116;
  }
  UniqueVolumeForPath = 0;
  v48 = 10138;
  if ( (unsigned int)SxIsSafeMode() || (unsigned int)SxIsWinPE() )
  {
    UniqueVolumeForPath = -2147023812;
    v16 = 10140;
    goto LABEL_116;
  }
  UniqueVolumeForPath = 0;
  v48 = 10140;
  UniqueVolumeForPath = CSppStringMap::CreateInstance(&v50);
  v16 = 10142;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_10;
  v48 = 10142;
  UniqueVolumeForPath = CSppStringMap::CreateInstance(&v58);
  v16 = 10143;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_10;
  v17 = *a2;
  v48 = 10143;
  v65 = v17;
  if ( (int)CSpp::_LoadClient(v7, 0, &v65, (struct _SPP_CLIENT_PROP *)&v66) >= 0 )
  {
    for ( i = 0; i < *(_DWORD *)&v68[4]; ++i )
    {
      if ( !v11 )
      {
        v19 = CSppStringMapEntry::CreateInstance(&v52);
        v11 = v52;
        UniqueVolumeForPath = v19;
        if ( v19 < 0 )
        {
          v49 = 10156;
          v13 = (const BYTE **)Block;
LABEL_35:
          v14 = v50;
          goto LABEL_117;
        }
        v48 = 10156;
      }
      v20 = CBsString::Set(
              (struct CSppStringMapEntry *)((char *)v11 + 8),
              *(const unsigned __int16 **)(*(_QWORD *)&v68[12] + 8LL * i));
      v14 = v50;
      v21 = v20 < 0;
      UniqueVolumeForPath = v20;
      v16 = 10158;
      if ( v21 )
        goto LABEL_38;
      v48 = 10158;
      v22 = CSxRefMap<CPathCache,CPathCacheNode>::Find(v50, v11, &v51);
      UniqueVolumeForPath = v22;
      if ( v22 < 0 )
      {
        v16 = 10159;
        goto LABEL_38;
      }
      v48 = 10159;
      if ( v22 == 1 )
      {
        UniqueVolumeForPath = CBsString::Set(
                                (struct CSppStringMapEntry *)((char *)v11 + 24),
                                *(const unsigned __int16 **)(*(_QWORD *)&v68[12] + 8LL * i));
        v16 = 10165;
        if ( UniqueVolumeForPath < 0 )
          goto LABEL_36;
        v48 = 10165;
        if ( *(_QWORD *)&v68[20] )
        {
          v23 = *(const unsigned __int16 **)(*(_QWORD *)&v68[20] + 8LL * i);
          if ( v23 )
          {
            UniqueVolumeForPath = CBsString::Set((struct CSppStringMapEntry *)((char *)v11 + 24), v23);
            v16 = 10168;
            if ( UniqueVolumeForPath < 0 )
              goto LABEL_36;
            v48 = 10168;
          }
        }
        v14 = v50;
        UniqueVolumeForPath = CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(v50, v11);
        v16 = 10170;
        if ( UniqueVolumeForPath < 0 )
          goto LABEL_38;
        LODWORD(v14) = 0;
        v48 = 10170;
        if ( v11 )
          CSppStringMapEntry::Release(v11);
        v11 = 0;
        v52 = 0;
      }
      else
      {
        LODWORD(v14) = 0;
      }
      if ( v51 )
        CSppStringMapEntry::Release(v51);
      v51 = 0;
    }
    v13 = (const BYTE **)Block;
    v7 = v61;
  }
  Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)&v66);
  v24 = CSpp::_CreateRegKey(v7, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", &v53);
  v12 = v53;
  v21 = v24 < 0;
  UniqueVolumeForPath = v24;
  v16 = 10179;
  if ( v21
    || (v48 = 10179,
        UniqueVolumeForPath = CSpp::_CreateRegKey(v7, v53, L"Clients", &hKey),
        v16 = 10180,
        UniqueVolumeForPath < 0)
    || (v48 = 10180,
        UniqueVolumeForPath = CSpp::_CreateRegKey(v7, v12, L"Leases", &v57),
        v16 = 10181,
        UniqueVolumeForPath < 0) )
  {
LABEL_10:
    v14 = v50;
    goto LABEL_116;
  }
  v48 = 10181;
  v15 = StringFromGUID2(a2, &sz, 39) == 0;
  v16 = 10183;
  if ( v15 )
  {
    UniqueVolumeForPath = -2147418113;
    goto LABEL_10;
  }
  v25 = v55;
  UniqueVolumeForPath = (int)v14;
  v48 = 10183;
  if ( !v55 )
  {
    RegDeleteValueW(hKey, &sz);
    RegDeleteValueW(v57, &sz);
    UniqueVolumeForPath = (int)v14;
    v48 = 10192;
    goto LABEL_35;
  }
  v26 = v63;
  v16 = 10195;
  if ( !v63 )
  {
    UniqueVolumeForPath = -2147024809;
    goto LABEL_10;
  }
  v48 = 10195;
  UniqueVolumeForPath = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&Block);
  v16 = 10212;
  if ( UniqueVolumeForPath < 0 )
  {
LABEL_36:
    v13 = (const BYTE **)Block;
    goto LABEL_10;
  }
  v48 = 10212;
  v27 = (unsigned int)v14;
  v14 = v50;
  while ( 1 )
  {
    LODWORD(v53) = v27;
    if ( v27 >= v25 )
      break;
    v28 = v27;
    v29 = *(_WORD **)(v26 + 8LL * v27);
    if ( !v29 )
    {
      v49 = 10218;
      goto LABEL_104;
    }
    UniqueVolumeForPath = 0;
    v48 = 10218;
    if ( !*v29 )
    {
      v49 = 10219;
LABEL_104:
      v13 = (const BYTE **)Block;
      UniqueVolumeForPath = -2147024809;
      goto LABEL_117;
    }
    v48 = 10219;
    if ( !v11 )
    {
      v30 = CSppStringMapEntry::CreateInstance(&v52);
      v11 = v52;
      v21 = v30 < 0;
      UniqueVolumeForPath = v30;
      v16 = 10223;
      if ( v21 )
        goto LABEL_38;
      v48 = 10223;
    }
    UniqueVolumeForPath = CBsString::Set(
                            (struct CSppStringMapEntry *)((char *)v11 + 8),
                            *(const unsigned __int16 **)(v26 + 8 * v28));
    v16 = 10225;
    if ( UniqueVolumeForPath < 0 )
      goto LABEL_38;
    v31 = v51;
    v48 = 10225;
    if ( v51 )
    {
      v51 = 0;
      CSppStringMapEntry::Release(v31);
    }
    v32 = CSxRefMap<CPathCache,CPathCacheNode>::Find(v14, v11, &v51);
    UniqueVolumeForPath = v32;
    if ( v32 < 0 )
    {
      v16 = 10227;
      goto LABEL_38;
    }
    v48 = 10227;
    if ( v32 == 1 )
    {
      UniqueVolumeForPath = SxGetUniqueVolumeForPath(*(const unsigned __int16 **)(v26 + 8 * v28), &szVolumeName, 0x33u);
      v16 = 10233;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_38;
      v48 = 10233;
      v33 = (*(__int64 (__fastcall **)(CSpp *, WCHAR *, int *))(*(_QWORD *)v61 + 80LL))(v61, &szVolumeName, &v54);
      UniqueVolumeForPath = v33;
      if ( v33 < 0 )
      {
        v16 = 10239;
        goto LABEL_38;
      }
      v48 = 10239;
      if ( v33 && (~(_BYTE)v54 & 5) != 5 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            177,
            v54,
            *(_QWORD *)(v26 + 8 * v28),
            (__int64)&szVolumeName,
            v54);
        UniqueVolumeForPath = -2130706168;
        v16 = 10244;
LABEL_38:
        v13 = (const BYTE **)Block;
LABEL_116:
        v49 = v16;
        goto LABEL_117;
      }
      UniqueVolumeForPath = CBsString::Set((struct CSppStringMapEntry *)((char *)v11 + 8), &szVolumeName);
      v16 = 10247;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_38;
      v48 = 10247;
      UniqueVolumeForPath = SxGetVolumeDescription(&szVolumeName, (struct CBsString *)v62);
      v16 = 10248;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_38;
      v48 = 10248;
      UniqueVolumeForPath = CBsString::Set((struct CSppStringMapEntry *)((char *)v11 + 24), v62[0]);
      v16 = 10249;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_38;
      v34 = v51;
      v48 = 10249;
    }
    else
    {
      v35 = v51;
      UniqueVolumeForPath = CBsString::Set(
                              (struct CSppStringMapEntry *)((char *)v11 + 24),
                              *((const unsigned __int16 **)v51 + 3));
      v16 = 10258;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_38;
      v48 = 10258;
      if ( v35 )
        CSppStringMapEntry::Release(v35);
      v34 = 0;
      v51 = 0;
    }
    if ( v34 )
    {
      v51 = 0;
      CSppStringMapEntry::Release(v34);
    }
    v36 = CSxRefMap<CPathCache,CPathCacheNode>::Find(v58, v11, &v51);
    UniqueVolumeForPath = v36;
    if ( v36 < 0 )
    {
      v16 = 10262;
      goto LABEL_38;
    }
    v48 = 10262;
    if ( v36 == 1 )
    {
      UniqueVolumeForPath = CBsString::Set((CBsString *)v60, *((const unsigned __int16 **)v11 + 1));
      v16 = 10281;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_38;
      v48 = 10281;
      UniqueVolumeForPath = SxHexEncode((struct CBsString *)v60, v37);
      v16 = 10282;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_38;
      v38 = -1;
      v48 = 10282;
      do
        ++v38;
      while ( v60[0][v38] );
      v13 = (const BYTE **)Block;
      UniqueVolumeForPath = ExtendCopy(Block, v60[0]);
      v16 = 10284;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_116;
      v48 = 10284;
      UniqueVolumeForPath = ExtendCopy(v13, L":");
      v16 = 10285;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_116;
      v48 = 10285;
      UniqueVolumeForPath = CBsString::Set((CBsString *)v60, *((const unsigned __int16 **)v11 + 3));
      v16 = 10286;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_116;
      v48 = 10286;
      UniqueVolumeForPath = SxHexEncode((struct CBsString *)v60, v39);
      v16 = 10287;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_116;
      v40 = -1;
      v48 = 10287;
      do
        ++v40;
      while ( v60[0][v40] );
      UniqueVolumeForPath = ExtendCopy(v13, v60[0]);
      v16 = 10288;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_116;
      v48 = 10288;
      UniqueVolumeForPath = CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(v58, v11);
      v16 = 10290;
      if ( UniqueVolumeForPath < 0 )
        goto LABEL_116;
      v48 = 10290;
      if ( v11 )
        CSppStringMapEntry::Release(v11);
      v11 = 0;
      v52 = 0;
    }
    else
    {
      if ( v51 )
        CSppStringMapEntry::Release(v51);
      v51 = 0;
    }
    v25 = v55;
    v27 = (_DWORD)v53 + 1;
  }
  v13 = (const BYTE **)Block;
  UniqueVolumeForPath = CSxSimpleArray<unsigned short>::Append(Block, 10218);
  v16 = 10294;
  if ( UniqueVolumeForPath < 0 )
    goto LABEL_116;
  v48 = 10294;
  v41 = RegSetValueExW(hKey, &sz, 0, 7u, v13[1], 2 * *((_DWORD *)v13 + 4));
  if ( v41 > 0 )
    v41 = (unsigned __int16)v41 | 0x80070000;
  UniqueVolumeForPath = v41;
  v21 = v41 < 0;
  v16 = 10301;
  if ( v21 )
    goto LABEL_116;
  v48 = 10301;
  if ( v56 == 2 )
  {
    RegDeleteValueW(v57, &sz);
  }
  else
  {
    UniqueVolumeForPath = SxRegWriteULONGLONG(v57, &sz, 0);
    v16 = 10309;
    if ( UniqueVolumeForPath < 0 )
      goto LABEL_116;
    v48 = 10309;
  }
LABEL_117:
  Free_SPP_CLIENT_PROP((struct _SPP_CLIENT_PROP *)&v66);
  v42 = UniqueVolumeForPath;
  if ( v11 )
    CSppStringMapEntry::Release(v11);
  if ( v51 )
    CSppStringMapEntry::Release(v51);
  if ( v58 )
    CSppStringMap::Release(v58);
  if ( v14 )
    CSppStringMap::Release(v14);
  if ( v13 )
    CSxSimpleArray<_GUID>::Release(v13);
  CBsString::_Release(v60);
  CBsString::_Release(v62);
  CBsString::_Release(v64);
  if ( (unsigned __int64)v57 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v57);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( (unsigned __int64)v12 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v12);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&UniqueVolumeForPath, v43, v44);
  RtlSetCurrentTransaction(CurrentTransaction);
  return v42;
}

```

## disassembly

```asm
0x18000e7b0  mov     [rsp-8+arg_10], rbx
0x18000e7b5  push    rbp
0x18000e7b6  push    rsi
0x18000e7b7  push    rdi
0x18000e7b8  push    r12
0x18000e7ba  push    r13
0x18000e7bc  push    r14
0x18000e7be  push    r15
0x18000e7c0  lea     rbp, [rsp-110h]
0x18000e7c8  sub     rsp, 210h
0x18000e7cf  mov     rax, cs:__security_cookie
0x18000e7d6  xor     rax, rsp
0x18000e7d9  mov     [rbp+140h+var_40], rax
0x18000e7e0  mov     rbx, [rbp+140h+arg_20]
0x18000e7e7  mov     esi, r9d
0x18000e7ea  mov     [rbp+140h+var_160], rbx
0x18000e7ee  mov     r12, rdx
0x18000e7f1  mov     [rbp+140h+var_1AC], r9d
0x18000e7f5  mov     r14, rcx
0x18000e7f8  mov     [rbp+140h+var_1A8], r8d
0x18000e7fc  mov     [rbp+140h+var_178], rcx
0x18000e800  call    cs:__imp_RtlGetCurrentTransaction
0x18000e806  xor     ecx, ecx
0x18000e808  mov     rdi, rax
0x18000e80b  call    cs:__imp_RtlSetCurrentTransaction
0x18000e811  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e818  lea     rax, WPP_GLOBAL_Control
0x18000e81f  cmp     rcx, rax
0x18000e822  jz      short loc_18000E842
0x18000e824  test    dword ptr [rcx+1Ch], 20000000h
0x18000e82b  jz      short loc_18000E842
0x18000e82d  mov     rcx, [rcx+10h]
0x18000e831  mov     r9, r12
0x18000e834  mov     qword ptr [rsp+240h+cbData], rbx
0x18000e839  mov     dword ptr [rsp+240h+lpData], esi
0x18000e83d  call    WPP_SF__guid_dq
0x18000e842  mov     r9d, 1; unsigned __int16
0x18000e848  lea     rdx, aCsppSetclient; "CSpp::SetClient"
0x18000e84f  mov     r8d, 2784h; unsigned __int16
0x18000e855  lea     rcx, [rsp+240h+var_208]; this
0x18000e85a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e85f  xor     esi, esi
0x18000e861  lea     rax, FileName
0x18000e868  mov     ebx, esi
0x18000e86a  mov     [rbp+140h+hKey], rsi
0x18000e86e  xor     edx, edx; Val
0x18000e870  mov     [rbp+140h+var_1B8], rbx
0x18000e874  lea     rcx, [rbp+140h+var_FE]; void *
0x18000e878  mov     [rbp+140h+var_1A0], rsi
0x18000e87c  lea     r8d, [rsi+4Ch]; Size
0x18000e880  mov     [rbp+140h+var_158], rax
0x18000e884  mov     [rbp+140h+var_150], rsi
0x18000e888  mov     [rbp+140h+var_170], rax
0x18000e88c  mov     [rbp+140h+var_168], rsi
0x18000e890  mov     [rbp+140h+var_188], rax
0x18000e894  mov     [rbp+140h+var_180], rsi
0x18000e898  mov     [rbp+140h+sz], si
0x18000e89c  call    memset_0
0x18000e8a1  xor     edx, edx; Val
0x18000e8a3  mov     [rbp+140h+szVolumeName], si
0x18000e8aa  lea     r8d, [rsi+64h]; Size
0x18000e8ae  lea     rcx, [rbp+140h+var_AE]; void *
0x18000e8b5  call    memset_0
0x18000e8ba  xorps   xmm0, xmm0
0x18000e8bd  mov     [rbp+140h+var_1B0], esi
0x18000e8c0  movups  [rbp+140h+var_11C], xmm0
0x18000e8c4  lea     r8d, [rsi+10h]; Size
0x18000e8c8  mov     [rsp+240h+Block], rsi
0x18000e8cd  lea     rdx, GUID_NULL; Buf2
0x18000e8d4  mov     [rbp+140h+var_130], esi
0x18000e8d7  mov     rcx, r12; Buf1
0x18000e8da  mov     [rsp+240h+var_1D0], rsi
0x18000e8df  movups  [rbp+140h+var_11C+0Ch], xmm0
0x18000e8e3  mov     r15d, esi
0x18000e8e6  mov     [rbp+140h+var_198], rsi
0x18000e8ea  movups  [rbp+140h+var_12C], xmm0
0x18000e8ee  mov     r13d, esi
0x18000e8f1  mov     [rsp+240h+var_1C8], rsi
0x18000e8f6  mov     [rbp+140h+var_1C0], rsi
0x18000e8fa  call    memcmp_0
0x18000e8ff  xor     ecx, ecx
0x18000e901  test    eax, eax
0x18000e903  mov     eax, 2799h
0x18000e908  jnz     short loc_18000E917
0x18000e90a  mov     [rsp+240h+var_208], 80070057h
0x18000e912  jmp     loc_18000F16E
0x18000e917  mov     [rsp+240h+var_204], ax
0x18000e91c  mov     eax, [rbp+140h+var_1A8]
0x18000e91f  dec     eax
0x18000e921  cmp     eax, 1
0x18000e924  mov     eax, 279Ah
0x18000e929  ja      short loc_18000E90A
0x18000e92b  mov     [rsp+240h+var_208], ecx
0x18000e92f  mov     [rsp+240h+var_204], ax
0x18000e934  call    ?SxIsSafeMode@@YAHXZ; SxIsSafeMode(void)
0x18000e939  test    eax, eax
0x18000e93b  jnz     loc_18000F161
0x18000e941  call    ?SxIsWinPE@@YAHXZ; SxIsWinPE(void)
0x18000e946  test    eax, eax
0x18000e948  jnz     loc_18000F161
0x18000e94e  mov     eax, 279Ch
0x18000e953  mov     [rsp+240h+var_208], r13d
0x18000e958  lea     rcx, [rsp+240h+var_1D0]; struct CSppStringMap **
0x18000e95d  mov     [rsp+240h+var_204], ax
0x18000e962  call    ?CreateInstance@CSppStringMap@@SAJPEAPEAV1@@Z; CSppStringMap::CreateInstance(CSppStringMap * *)
0x18000e967  mov     [rsp+240h+var_208], eax
0x18000e96b  test    eax, eax
0x18000e96d  mov     eax, 279Eh
0x18000e972  jns     short loc_18000E97E
0x18000e974  mov     r13, [rsp+240h+var_1D0]
0x18000e979  jmp     loc_18000F16E
0x18000e97e  lea     rcx, [rbp+140h+var_198]; struct CSppStringMap **
0x18000e982  mov     [rsp+240h+var_204], ax
0x18000e987  call    ?CreateInstance@CSppStringMap@@SAJPEAPEAV1@@Z; CSppStringMap::CreateInstance(CSppStringMap * *)
0x18000e98c  mov     [rsp+240h+var_208], eax
0x18000e990  test    eax, eax
0x18000e992  mov     eax, 279Fh
0x18000e997  js      short loc_18000E974
0x18000e999  movups  xmm0, xmmword ptr [r12]
0x18000e99e  lea     r9, [rbp+140h+var_130]; struct _SPP_CLIENT_PROP *
0x18000e9a2  mov     [rsp+240h+var_204], ax
0x18000e9a7  lea     r8, [rbp+140h+var_140]; struct _GUID
0x18000e9ab  xor     edx, edx; int
0x18000e9ad  mov     rcx, r14; this
0x18000e9b0  movdqu  xmmword ptr [rbp+140h+var_140.Data1], xmm0
0x18000e9b5  call    ?_LoadClient@CSpp@@AEAAJHU_GUID@@PEAU_SPP_CLIENT_PROP@@@Z; CSpp::_LoadClient(int,_GUID,_SPP_CLIENT_PROP *)
0x18000e9ba  test    eax, eax
0x18000e9bc  js      loc_18000EB3C
0x18000e9c2  mov     r14d, r13d
0x18000e9c5  mov     r15d, 27ACh
0x18000e9cb  cmp     r14d, dword ptr [rbp+140h+var_11C+4]
0x18000e9cf  jnb     loc_18000EB33
0x18000e9d5  test    rsi, rsi
0x18000e9d8  jnz     short loc_18000E9F9
0x18000e9da  lea     rcx, [rbp+140h+var_1C0]; struct CSppStringMapEntry **
0x18000e9de  call    ?CreateInstance@CSppStringMapEntry@@SAJPEAPEAV1@@Z; CSppStringMapEntry::CreateInstance(CSppStringMapEntry * *)
0x18000e9e3  mov     rsi, [rbp+140h+var_1C0]
0x18000e9e7  mov     [rsp+240h+var_208], eax
0x18000e9eb  test    eax, eax
0x18000e9ed  js      loc_18000EB05
0x18000e9f3  mov     [rsp+240h+var_204], r15w
0x18000e9f9  mov     rdx, qword ptr [rbp+140h+var_11C+0Ch]
0x18000e9fd  lea     rcx, [rsi+8]; this
0x18000ea01  mov     r15d, r14d
0x18000ea04  mov     rdx, [rdx+r15*8]; unsigned __int16 *
0x18000ea08  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000ea0d  mov     r13, [rsp+240h+var_1D0]
0x18000ea12  test    eax, eax
0x18000ea14  mov     [rsp+240h+var_208], eax
0x18000ea18  mov     eax, 27AEh
0x18000ea1d  js      loc_18000EB29
0x18000ea23  lea     r8, [rsp+240h+var_1C8]
0x18000ea28  mov     [rsp+240h+var_204], ax
0x18000ea2d  mov     rdx, rsi
0x18000ea30  mov     rcx, r13
0x18000ea33  call    ?Find@?$CSxRefMap@VCPathCache@@VCPathCacheNode@@@@QEAAJPEAVCPathCacheNode@@PEAPEAV2@@Z; CSxRefMap<CPathCache,CPathCacheNode>::Find(CPathCacheNode *,CPathCacheNode * *)
0x18000ea38  mov     [rsp+240h+var_208], eax
0x18000ea3c  test    eax, eax
0x18000ea3e  js      loc_18000EB24
0x18000ea44  mov     ecx, 27AFh
0x18000ea49  mov     [rsp+240h+var_204], cx
0x18000ea4e  cmp     eax, 1
0x18000ea51  jnz     loc_18000EAE6
0x18000ea57  mov     rdx, qword ptr [rbp+140h+var_11C+0Ch]
0x18000ea5b  lea     rcx, [rsi+18h]; this
0x18000ea5f  mov     rdx, [rdx+r15*8]; unsigned __int16 *
0x18000ea63  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000ea68  mov     [rsp+240h+var_208], eax
0x18000ea6c  test    eax, eax
0x18000ea6e  mov     eax, 27B5h
0x18000ea73  js      loc_18000EB1A
0x18000ea79  mov     [rsp+240h+var_204], ax
0x18000ea7e  mov     rax, [rbp+140h+var_108]
0x18000ea82  test    rax, rax
0x18000ea85  jz      short loc_18000EAAB
0x18000ea87  mov     rdx, [rax+r15*8]; unsigned __int16 *
0x18000ea8b  test    rdx, rdx
0x18000ea8e  jz      short loc_18000EAAB
0x18000ea90  lea     rcx, [rsi+18h]; this
0x18000ea94  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000ea99  mov     [rsp+240h+var_208], eax
0x18000ea9d  test    eax, eax
0x18000ea9f  mov     eax, 27B8h
0x18000eaa4  js      short loc_18000EB1A
0x18000eaa6  mov     [rsp+240h+var_204], ax
0x18000eaab  mov     r13, [rsp+240h+var_1D0]
0x18000eab0  mov     rdx, rsi
0x18000eab3  mov     rcx, r13
0x18000eab6  call    ?Insert@?$CSxRefMap@VCWriterEntryMap@@VCWriterEntry@@@@QEAAJPEAVCWriterEntry@@PEAPEAV2@@Z; CSxRefMap<CWriterEntryMap,CWriterEntry>::Insert(CWriterEntry *,CWriterEntry * *)
0x18000eabb  mov     [rsp+240h+var_208], eax
0x18000eabf  test    eax, eax
0x18000eac1  mov     eax, 27BAh
0x18000eac6  js      short loc_18000EB29
0x18000eac8  xor     r13d, r13d
0x18000eacb  mov     [rsp+240h+var_204], ax
0x18000ead0  test    rsi, rsi
0x18000ead3  jz      short loc_18000EADD
0x18000ead5  mov     rcx, rsi; this
0x18000ead8  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x18000eadd  mov     rsi, r13
0x18000eae0  mov     [rbp+140h+var_1C0], r13
0x18000eae4  jmp     short loc_18000EAE9
0x18000eae6  xor     r13d, r13d
0x18000eae9  mov     rcx, [rsp+240h+var_1C8]; this
0x18000eaee  test    rcx, rcx
0x18000eaf1  jz      short loc_18000EAF8
0x18000eaf3  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x18000eaf8  mov     [rsp+240h+var_1C8], r13
0x18000eafd  inc     r14d
0x18000eb00  jmp     loc_18000E9C5
0x18000eb05  mov     [rsp+240h+var_202], r15w
0x18000eb0b  mov     r15, [rsp+240h+Block]
0x18000eb10  mov     r13, [rsp+240h+var_1D0]
0x18000eb15  jmp     loc_18000F173
0x18000eb1a  mov     r15, [rsp+240h+Block]
0x18000eb1f  jmp     loc_18000E974
0x18000eb24  mov     eax, 27AFh
0x18000eb29  mov     r15, [rsp+240h+Block]
0x18000eb2e  jmp     loc_18000F16E
0x18000eb33  mov     r15, [rsp+240h+Block]
0x18000eb38  mov     r14, [rbp+140h+var_178]
0x18000eb3c  lea     rcx, [rbp+140h+var_130]; struct _SPP_CLIENT_PROP *
0x18000eb40  call    ?Free_SPP_CLIENT_PROP@@YAXPEAU_SPP_CLIENT_PROP@@@Z; Free_SPP_CLIENT_PROP(_SPP_CLIENT_PROP *)
0x18000eb45  lea     r9, [rbp+140h+var_1B8]; HKEY *
0x18000eb49  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000eb50  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000eb57  mov     rcx, r14; this
0x18000eb5a  call    ?_CreateRegKey@CSpp@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSpp::_CreateRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18000eb5f  mov     rbx, [rbp+140h+var_1B8]
0x18000eb63  test    eax, eax
0x18000eb65  mov     [rsp+240h+var_208], eax
0x18000eb69  mov     eax, 27C3h
0x18000eb6e  js      loc_18000E974
0x18000eb74  lea     r9, [rbp+140h+hKey]; HKEY *
0x18000eb78  mov     [rsp+240h+var_204], ax
0x18000eb7d  lea     r8, aClients; "Clients"
0x18000eb84  mov     rdx, rbx; HKEY
0x18000eb87  mov     rcx, r14; this
0x18000eb8a  call    ?_CreateRegKey@CSpp@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSpp::_CreateRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18000eb8f  mov     [rsp+240h+var_208], eax
0x18000eb93  test    eax, eax
0x18000eb95  mov     eax, 27C4h
0x18000eb9a  js      loc_18000E974
0x18000eba0  lea     r9, [rbp+140h+var_1A0]; HKEY *
0x18000eba4  mov     [rsp+240h+var_204], ax
0x18000eba9  lea     r8, aLeases; "Leases"
0x18000ebb0  mov     rdx, rbx; HKEY
0x18000ebb3  mov     rcx, r14; this
0x18000ebb6  call    ?_CreateRegKey@CSpp@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSpp::_CreateRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18000ebbb  mov     [rsp+240h+var_208], eax
0x18000ebbf  test    eax, eax
0x18000ebc1  mov     eax, 27C5h
0x18000ebc6  js      loc_18000E974
0x18000ebcc  mov     r8d, 27h ; '''; cchMax
0x18000ebd2  mov     [rsp+240h+var_204], ax
0x18000ebd7  lea     rdx, [rbp+140h+sz]; lpsz
0x18000ebdb  mov     rcx, r12; rguid
0x18000ebde  call    cs:__imp_StringFromGUID2
0x18000ebe4  test    eax, eax
0x18000ebe6  mov     eax, 27C7h
0x18000ebeb  jz      loc_18000F154
0x18000ebf1  mov     r14d, [rbp+140h+var_1AC]
0x18000ebf5  mov     [rsp+240h+var_208], r13d
0x18000ebfa  mov     [rsp+240h+var_204], ax
0x18000ebff  test    r14d, r14d
0x18000ec02  jnz     short loc_18000EC34
0x18000ec04  mov     rcx, [rbp+140h+hKey]; hKey
0x18000ec08  lea     rdx, [rbp+140h+sz]; lpValueName
0x18000ec0c  call    cs:__imp_RegDeleteValueW
0x18000ec12  mov     rcx, [rbp+140h+var_1A0]; hKey
0x18000ec16  lea     rdx, [rbp+140h+sz]; lpValueName
0x18000ec1a  call    cs:__imp_RegDeleteValueW
0x18000ec20  mov     eax, 27D0h
0x18000ec25  mov     [rsp+240h+var_208], r13d
0x18000ec2a  mov     [rsp+240h+var_204], ax
0x18000ec2f  jmp     loc_18000EB10
0x18000ec34  mov     r12, [rbp+140h+var_160]
0x18000ec38  mov     eax, 27D3h
0x18000ec3d  test    r12, r12
0x18000ec40  jz      loc_18000F147
0x18000ec46  lea     rcx, [rsp+240h+Block]
0x18000ec4b  mov     [rsp+240h+var_204], ax
0x18000ec50  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18000ec55  mov     [rsp+240h+var_208], eax
0x18000ec59  test    eax, eax
0x18000ec5b  mov     eax, 27E4h
0x18000ec60  js      loc_18000EB1A
0x18000ec66  mov     [rsp+240h+var_204], ax
0x18000ec6b  mov     eax, r13d
0x18000ec6e  mov     r13, [rsp+240h+var_1D0]
0x18000ec73  mov     dword ptr [rbp+140h+var_1B8], eax
0x18000ec76  mov     ecx, 27EBh
0x18000ec7b  lea     edx, [rcx-1]
0x18000ec7e  cmp     eax, r14d
0x18000ec81  jnb     loc_18000F0AA
0x18000ec87  mov     r14d, eax
0x18000ec8a  xor     r15d, r15d
0x18000ec8d  mov     rax, [r12+r14*8]
0x18000ec91  test    rax, rax
0x18000ec94  jz      loc_18000F093
  ... truncated ...
```
