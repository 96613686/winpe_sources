# WDiagQueryDeviceInfo(_GUID *,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,ushort *,ulong,_SYSTEMTIME *,ushort *,ulong,ushort *,ulong)

- ea: `0x1800792a0`
- end: `0x18007a485`
- name: `?WDiagQueryDeviceInfo@@YAKPEAU_GUID@@PEAGK1K1K1K1KPEAU_SYSTEMTIME@@1K1K@Z`
- size: `4581`
- prototype: `unsigned int __fastcall(struct _GUID *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, struct _SYSTEMTIME *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078c74`
- `0x1800ab998`
- `0x1800b4990`
- `0x180140120`

## callees

- `0x180006540`
- `0x180006638`
- `0x1800066e0`
- `0x1800067a4`
- `0x18000aa0c`
- `0x180011530`
- `0x18001ad54`
- `0x180036110`
- `0x180068350`
- `0x1800792a0`
- `0x180088624`
- `0x1800ac8ac`
- `0x180106340`
- `0x180107318`
- `0x18021e441`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800796a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180079f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a0eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007978c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079b45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079be9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079cb0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079df7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a1c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007978c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079b45`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079be9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079cb0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180079df7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007a1c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079d38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079ebe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a001`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a043`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079d38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079ebe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a001`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079865`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007988a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800799b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079e89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a260`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a385`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079865`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007988a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800799b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079e51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180079e89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a260`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a385`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a399`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180079a1c`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180079a1c`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800798dc`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x1800798dc`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180079692`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180079692`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007a41a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18007a41a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180079648`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800798a5`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180079648`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800798a5`
- `DEVOBJ!DevObjGetClassDevs` at `0x180079562`
- `DEVOBJ!DevObjGetClassDevs` at `0x180079562`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180079470`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180079470`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180079cfa`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180079cfa`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180079856`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180079856`

## string_xrefs

- `0x180079713`: `DevObjOpenDevRegKey Failure`
- `0x180079505`: `DevObjCreateDeviceInfoList Failure`
- `0x180079aa4`: `DevObjGetDeviceRegistryProperty DODRP_MFG Failure`
- `0x180079eb0`: `System\CurrentControlSet\Services`
- `0x180079f2c`: `Failed to open HKLM Services key`
- `0x180079de1`: `Service`
- `0x18007a0d1`: `Failed to open Driver Service Config key`
- `0x180079fb8`: `Failed to open HKLM Services key. Invalid Handle.`
- `0x18007a239`: `Failed to read Driver Image Path from registry.`
- `0x18007a31f`: `Failed to read binary version.`
- `0x18007a15f`: `Failed to open Driver Service Config key. Invalid Handle.`
- `0x18007a1aa`: `ImagePath`

## pseudocode

```c
__int64 __fastcall WDiagQueryDeviceInfo(
        struct _GUID *a1,
        unsigned __int16 *a2,
        int a3,
        unsigned __int16 *a4,
        DWORD a5,
        unsigned __int16 *a6,
        DWORD a7,
        unsigned __int16 *a8,
        unsigned int a9,
        unsigned __int16 *a10,
        DWORD a11,
        struct _SYSTEMTIME *a12,
        unsigned __int16 *a13,
        unsigned int a14,
        unsigned __int16 *a15,
        unsigned int a16)
{
  struct _GUID *v16; // r13
  DWORD v17; // edi
  unsigned __int16 *v18; // r8
  __int64 DeviceInfoList; // rax
  __int64 v20; // rsi
  DWORD LastError; // eax
  __int64 v22; // r8
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  DWORD v26; // eax
  __int64 v27; // r8
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  DWORD v31; // ebx
  __int64 v32; // r8
  HKEY v33; // r13
  DWORD v34; // eax
  __int64 v35; // r8
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  unsigned int v39; // eax
  __int64 v40; // r8
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  DWORD v44; // eax
  __int64 v45; // r8
  DWORD v46; // ebx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  DWORD v50; // edi
  char *v51; // rdi
  size_t v52; // rbx
  DWORD v53; // eax
  __int64 v54; // r8
  DWORD v55; // ebx
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  unsigned __int64 v59; // rbx
  _WORD *v60; // rdi
  unsigned int v61; // eax
  unsigned __int64 v62; // rbx
  _WORD *v63; // rdi
  unsigned int v64; // eax
  unsigned __int64 v65; // rbx
  _WORD *v66; // rdi
  struct _SYSTEMTIME *v67; // rbx
  unsigned int v68; // eax
  DWORD v69; // eax
  _QWORD *v70; // rcx
  __int64 v71; // rdx
  unsigned int v72; // eax
  unsigned __int64 v73; // rbx
  unsigned int v74; // eax
  __int64 v75; // r8
  int v76; // ecx
  int v77; // r8d
  int v78; // r9d
  const char *v79; // rax
  int *v80; // rdx
  DWORD v81; // eax
  __int64 v82; // r8
  __int64 v83; // r8
  HKEY v84; // rcx
  int v85; // ecx
  int v86; // r8d
  int v87; // r9d
  __int16 *v88; // rdx
  char *v89; // rax
  DWORD v90; // eax
  __int64 v91; // r8
  unsigned int v92; // eax
  __int64 v93; // r8
  int v94; // ecx
  int v95; // r8d
  int v96; // r9d
  const char *v97; // rax
  int *v98; // rdx
  unsigned __int64 v99; // rbx
  unsigned __int16 *v100; // rcx
  int BinaryVersion; // eax
  __int64 v102; // r8
  unsigned __int64 v103; // rbx
  int v104; // ecx
  int v105; // r8d
  int v106; // r9d
  size_t v108; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v109[8]; // [rsp+48h] [rbp-B8h] BYREF
  int v110; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v111; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v113; // [rsp+60h] [rbp-A0h]
  DWORD v114; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  DWORD lpcbData; // [rsp+78h] [rbp-88h] BYREF
  DWORD v117; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD v118; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v120; // [rsp+90h] [rbp-70h] BYREF
  _DWORD Size[3]; // [rsp+94h] [rbp-6Ch] BYREF
  void *v122; // [rsp+A0h] [rbp-60h] BYREF
  void *v123; // [rsp+A8h] [rbp-58h] BYREF
  void *v124; // [rsp+B0h] [rbp-50h] BYREF
  const char *v125; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v126; // [rsp+C0h] [rbp-40h]
  void *v127; // [rsp+C8h] [rbp-38h] BYREF
  void *v128; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v129; // [rsp+D8h] [rbp-28h]
  void *v130; // [rsp+E0h] [rbp-20h]
  struct _SYSTEMTIME SystemTime; // [rsp+E8h] [rbp-18h] BYREF
  GUID iid; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v133[3]; // [rsp+108h] [rbp+8h] BYREF
  char v134[32]; // [rsp+138h] [rbp+38h] BYREF
  const char *v135; // [rsp+158h] [rbp+58h]
  __int64 v136; // [rsp+160h] [rbp+60h]
  BYTE Data[2]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t v138[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  BYTE v139[528]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE Src[512]; // [rsp+5D0h] [rbp+4D0h] BYREF
  char v141[512]; // [rsp+7D0h] [rbp+6D0h] BYREF
  BYTE lpData[512]; // [rsp+9D0h] [rbp+8D0h] BYREF
  BYTE v143[512]; // [rsp+BD0h] [rbp+AD0h] BYREF
  unsigned __int16 v144[256]; // [rsp+DD0h] [rbp+CD0h] BYREF

  v16 = a1;
  v17 = 0;
  *(_QWORD *)&SystemTime.wYear = a12;
  v129 = a13;
  *a2 = 0;
  *a4 = 0;
  *a6 = 0;
  v113 = a1;
  *(_DWORD *)v109 = a3;
  v18 = a10;
  v128 = a4;
  *a8 = 0;
  v127 = a2;
  *a10 = 0;
  *a15 = 0;
  v124 = a6;
  v130 = a8;
  v122 = a10;
  v123 = a15;
  phkResult = 0;
  hKey = 0;
  cbData = 0;
  v120 = 0;
  lpcbData = 0;
  v118 = 0;
  Size[0] = 0;
  v117 = 0;
  v114 = 0;
  *(_WORD *)v139 = 0;
  *(_WORD *)Data = 0;
  memset(v133, 0, sizeof(v133));
  iid = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 21, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids);
    }
    if ( (unsigned int)dword_18029E6C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v18) )
    {
      v136 = 21;
      v135 = "pAdapterGuid is null";
      tlgWriteTransfer_EventWriteTransfer(&dword_18029E6C8, byte_18027850D, 0, 0, 3, v134);
    }
    return v17;
  }
  DeviceInfoList = DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  v126 = DeviceInfoList;
  v20 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 22, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, LastError);
    }
    if ( (unsigned int)dword_18029E6C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v22) )
    {
      v123 = v16;
      v124 = "DevObjCreateDeviceInfoList Failure";
      v110 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        v23,
        (unsigned int)byte_1802784BD,
        v24,
        v25,
        (__int64)&v124,
        (__int64)&v110,
        (__int64)&v123);
    }
    goto LABEL_187;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 2, 0, 0) )
  {
    v26 = GetLastError();
    v17 = v26;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 23, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v26);
    }
    if ( (unsigned int)dword_18029E6C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v27) )
    {
      v123 = v16;
      v124 = "DevObjGetClassDevs Failure";
      v110 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        v28,
        (unsigned int)&unk_1802785A0,
        v29,
        v30,
        (__int64)&v124,
        (__int64)&v110,
        (__int64)&v123);
    }
    goto LABEL_186;
  }
  v31 = 0;
  v110 = 0;
  LODWORD(v108) = 0;
  LODWORD(v133[0]) = 48;
  if ( !(unsigned int)DevObjEnumDeviceInfo(v20, 0, v133) )
    goto LABEL_183;
  while ( 1 )
  {
    if ( v31 == -1 )
      goto LABEL_181;
    v33 = (HKEY)DevObjOpenDevRegKey(v126, v133, 1);
    if ( v33 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      break;
    v34 = GetLastError();
    v17 = v34;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 24, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v34);
    }
    if ( (unsigned int)dword_18029E6C8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v35) )
      goto LABEL_48;
    v16 = v113;
    *(_QWORD *)&Size[1] = "DevObjOpenDevRegKey Failure";
    v125 = (const char *)v113;
    LODWORD(v108) = v17;
    v111 = v31;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v36,
      (unsigned int)byte_180278543,
      v37,
      v38,
      (__int64)&Size[1],
      (__int64)&v111,
      (__int64)&v108,
      (__int64)&v125);
LABEL_49:
    LODWORD(v108) = ++v31;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v126, v31, v133) )
      goto LABEL_181;
  }
  cbData = 78;
  v39 = RegQueryValueExW(v33, L"NetCfgInstanceId", 0, 0, Data, &cbData);
  v17 = v39;
  if ( v39 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 25, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v39);
    }
    if ( (unsigned int)dword_18029E6C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v40) )
    {
      *(_QWORD *)&Size[1] = v113;
      v125 = "RegQueryValueEx NetCfgInstanceId Failure";
      v111 = v17;
      LODWORD(v108) = v31;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        v41,
        (unsigned int)byte_180278403,
        v42,
        v43,
        (__int64)&v125,
        (__int64)&v108,
        (__int64)&v111,
        (__int64)&Size[1]);
    }
    goto LABEL_47;
  }
  v17 = IIDFromString((LPCOLESTR)Data, &iid);
  if ( v17 )
  {
    RegCloseKey(v33);
    v17 = 0;
LABEL_48:
    v16 = v113;
    goto LABEL_49;
  }
  if ( *(_QWORD *)&iid.Data1 != *(_QWORD *)&v113->Data1 || *(_QWORD *)iid.Data4 != *(_QWORD *)v113->Data4 )
  {
LABEL_47:
    RegCloseKey(v33);
    goto LABEL_48;
  }
  cbData = 256;
  if ( (unsigned int)DevObjGetDeviceInstanceId(v126, v133, Src, 256, &v120) )
  {
    if ( *(_DWORD *)v109 > v120 )
    {
      v51 = (char *)v127;
      v52 = 2LL * v120;
      memcpy_0(v127, Src, v52);
      *(_WORD *)&v51[v52] = 0;
      goto LABEL_63;
    }
LABEL_60:
    v17 = 8;
LABEL_61:
    RegCloseKey(v33);
    goto LABEL_186;
  }
  v44 = GetLastError();
  v46 = v44;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 26, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v44);
  }
  if ( (unsigned int)dword_18029E6C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v45) )
  {
    v50 = v108;
    *(_QWORD *)&Size[1] = v113;
    v125 = "DevObjGetDeviceInstanceId Failure";
    v111 = v46;
    v110 = v108;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v47,
      (unsigned int)&word_1802783A6,
      v48,
      v49,
      (__int64)&v125,
      (__int64)&v110,
      (__int64)&v111,
      (__int64)&Size[1]);
    goto LABEL_64;
  }
LABEL_63:
  v50 = v108;
LABEL_64:
  cbData = 256;
  if ( (unsigned int)DevObjGetDeviceRegistryProperty(v126, v133, 11) )
  {
    if ( a9 > Size[0] >> 1 )
    {
      v59 = Size[0];
      v60 = v130;
      memcpy_0(v130, v141, Size[0]);
      v60[v59 >> 1] = 0;
      goto LABEL_74;
    }
    goto LABEL_60;
  }
  v53 = GetLastError();
  v55 = v53;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 27, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v53);
  }
  if ( (unsigned int)dword_18029E6C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v54) )
  {
    v127 = v113;
    *(_QWORD *)&Size[1] = "DevObjGetDeviceRegistryProperty DODRP_MFG Failure";
    *(_DWORD *)v109 = v55;
    v111 = v50;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v56,
      (unsigned int)&unk_180278460,
      v57,
      v58,
      (__int64)&Size[1],
      (__int64)&v111,
      (__int64)v109,
      (__int64)&v127);
  }
LABEL_74:
  lpcbData = 512;
  v61 = RegQueryValueExW(v33, L"DriverVersion", 0, 0, lpData, &lpcbData);
  if ( !v61 )
  {
    if ( a5 > lpcbData >> 1 )
    {
      v62 = lpcbData;
      v63 = v128;
      memcpy_0(v128, lpData, lpcbData);
      v63[v62 >> 1] = 0;
      goto LABEL_81;
    }
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 28, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v61);
  }
LABEL_81:
  v117 = 512;
  v64 = RegQueryValueExW(v33, L"DriverDate", 0, 0, v143, &v117);
  if ( !v64 )
  {
    if ( a11 > v117 >> 1 )
    {
      v65 = v117;
      v66 = v122;
      memcpy_0(v122, v143, v117);
      v66[v65 >> 1] = 0;
      goto LABEL_88;
    }
    goto LABEL_60;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 29, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v64);
  }
LABEL_88:
  v67 = *(struct _SYSTEMTIME **)&SystemTime.wYear;
  v110 = 1;
  if ( !*(_QWORD *)&SystemTime.wYear )
  {
LABEL_97:
    v69 = RegOpenKeyExW(v33, L"Ndi", 0, 0x20019u, &phkResult);
    v118 = 512;
    v17 = v69;
    if ( v69 )
    {
      v70 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 4u
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) == 0 )
      {
        goto LABEL_180;
      }
      v71 = 31;
      goto LABEL_107;
    }
    if ( phkResult == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v69 = GetLastError();
      v17 = v69;
      v70 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 4u
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) == 0 )
      {
        goto LABEL_180;
      }
      v71 = 32;
LABEL_107:
      WPP_SF_d(v70[27], v71, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v69);
      goto LABEL_180;
    }
    v72 = RegQueryValueExW(phkResult, L"Service", 0, 0, (LPBYTE)v138, &v118);
    v17 = v72;
    if ( v72 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 33, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v72);
      }
    }
    else
    {
      if ( a7 <= v118 >> 1 )
      {
        v17 = 8;
LABEL_115:
        RegCloseKey(phkResult);
        goto LABEL_61;
      }
      v73 = v118;
      memcpy_0(v124, v138, v118);
      *((_WORD *)v124 + (v73 >> 1)) = 0;
    }
    RegCloseKey(phkResult);
    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    if ( v17 )
      goto LABEL_180;
    v74 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services", 0, 0x20019u, &phkResult);
    v17 = v74;
    if ( v74 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 34, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v74);
      }
      if ( (unsigned int)dword_18029E6C8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v75) )
        goto LABEL_179;
      v79 = "Failed to open HKLM Services key";
      v80 = (int *)byte_1802782C5;
      goto LABEL_134;
    }
    if ( phkResult == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v81 = GetLastError();
      v17 = v81;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 35, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v81);
      }
      if ( (unsigned int)dword_18029E6C8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v82) )
        goto LABEL_179;
      v79 = "Failed to open HKLM Services key. Invalid Handle.";
      v80 = &dword_180278284;
LABEL_134:
      *(_QWORD *)&SystemTime.wYear = v79;
      *(_DWORD *)v109 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v76,
        (_DWORD)v80,
        v77,
        v78,
        (__int64)&SystemTime,
        (__int64)v109);
LABEL_179:
      RegCloseKey(phkResult);
      goto LABEL_180;
    }
    v17 = RegOpenKeyExW(phkResult, v138, 0, 0x20019u, &hKey);
    if ( v17 )
    {
      if ( wcscmp_0(L"QCWLAN", v138)
        || (v17 = RegOpenKeyExW(phkResult, L"QcaWlan", 0, 0x20019u, &hKey)) != 0
        || (v84 = hKey, hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 36, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v17);
        }
        if ( (unsigned int)dword_18029E6C8 <= 5
          || !(unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v83) )
        {
          goto LABEL_155;
        }
        *(_QWORD *)&SystemTime.wYear = v138;
        v88 = &word_180278356;
        v89 = "Failed to open Driver Service Config key";
LABEL_154:
        v122 = v89;
        *(_DWORD *)v109 = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v85,
          (_DWORD)v88,
          v86,
          v87,
          (__int64)&v122,
          (__int64)&SystemTime,
          (__int64)v109);
LABEL_155:
        if ( v17 )
        {
LABEL_178:
          RegCloseKey(hKey);
          goto LABEL_179;
        }
        v84 = hKey;
      }
    }
    else
    {
      v84 = hKey;
      if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        v90 = GetLastError();
        v17 = v90;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 37, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v90);
        }
        if ( (unsigned int)dword_18029E6C8 <= 5
          || !(unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v91) )
        {
          goto LABEL_155;
        }
        *(_QWORD *)&SystemTime.wYear = v138;
        v88 = &word_180278306;
        v89 = "Failed to open Driver Service Config key. Invalid Handle.";
        goto LABEL_154;
      }
    }
    v114 = 520;
    v92 = RegQueryValueExW(v84, L"ImagePath", 0, 0, v139, &v114);
    v17 = v92;
    if ( v92 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 38, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v92);
      }
      if ( (unsigned int)dword_18029E6C8 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v93) )
        goto LABEL_178;
      *(_DWORD *)v109 = v17;
      v97 = "Failed to read Driver Image Path from registry.";
      v98 = &dword_1802781EC;
      goto LABEL_175;
    }
    if ( (v114 & 0xFFFFFFFE) < 0x208 )
    {
      v99 = v114;
      memcpy_0(v129, v139, v114);
      v100 = v129;
      LODWORD(v108) = 512;
      v129[v99 >> 1] = 0;
      BinaryVersion = GetBinaryVersion(v100, v114, v144, (unsigned int *)&v108);
      if ( BinaryVersion < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            39,
            (unsigned int)&WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids,
            (_DWORD)v129,
            BinaryVersion);
        }
        if ( (unsigned int)dword_18029E6C8 <= 5
          || !(unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v102) )
        {
          goto LABEL_178;
        }
        *(_DWORD *)v109 = 0;
        v97 = "Failed to read binary version.";
        v98 = (int *)byte_1802781AB;
LABEL_175:
        *(_QWORD *)&SystemTime.wYear = v97;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v94,
          (_DWORD)v98,
          v95,
          v96,
          (__int64)&SystemTime,
          (__int64)v109);
        goto LABEL_178;
      }
      if ( a16 > (unsigned int)v108 >> 1 )
      {
        v103 = (unsigned int)v108;
        memcpy_0(v123, v144, (unsigned int)v108);
        *((_WORD *)v123 + (v103 >> 1)) = 0;
        goto LABEL_178;
      }
    }
    v17 = 8;
    RegCloseKey(hKey);
    goto LABEL_115;
  }
  *(_QWORD *)v109 = 0;
  cbData = 8;
  SystemTime = 0;
  v68 = RegQueryValueExW(v33, L"DriverDateData", 0, 0, v109, &cbData);
  if ( v68 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v68);
    }
    goto LABEL_97;
  }
  if ( FileTimeToSystemTime((const FILETIME *)v109, &SystemTime) )
  {
    *v67 = SystemTime;
    goto LABEL_97;
  }
  v17 = GetLastError();
LABEL_180:
  RegCloseKey(v33);
  v16 = v113;
LABEL_181:
  if ( !v17 && !v110 )
  {
LABEL_183:
    v17 = 1168;
    if ( (unsigned int)dword_18029E6C8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18029E6C8, 0x200000000000LL, v32) )
    {
      v122 = v16;
      *(_QWORD *)&SystemTime.wYear = Data;
      v128 = "Device Not Found";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        v104,
        (unsigned int)byte_18027822D,
        v105,
        v106,
        (__int64)&v128,
        (__int64)&v122,
        (__int64)&SystemTime);
    }
  }
LABEL_186:
  DevObjDestroyDeviceInfoList(v126);
LABEL_187:
  if ( v17
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 40, &WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids, v17);
  }
  return v17;
}

```

## disassembly

```asm
0x1800792a0  mov     [rsp-8+arg_0], rbx
0x1800792a5  push    rbp
0x1800792a6  push    rsi
0x1800792a7  push    rdi
0x1800792a8  push    r12
0x1800792aa  push    r13
0x1800792ac  push    r14
0x1800792ae  push    r15
0x1800792b0  lea     rbp, [rsp-0EE0h]
0x1800792b8  sub     rsp, 0FE0h
0x1800792bf  mov     rax, cs:__security_cookie
0x1800792c6  xor     rax, rsp
0x1800792c9  mov     [rbp+0F10h+var_40], rax
0x1800792d0  mov     rax, [rbp+0F10h+arg_58]
0x1800792d7  xorps   xmm0, xmm0
0x1800792da  mov     r10, [rbp+0F10h+arg_28]
0x1800792e1  mov     r13, rcx
0x1800792e4  mov     r11, [rbp+0F10h+arg_70]
0x1800792eb  xor     edi, edi
0x1800792ed  mov     qword ptr [rbp+0F10h+SystemTime.wYear], rax
0x1800792f1  mov     rax, [rbp+0F10h+arg_60]
0x1800792f8  mov     [rbp+0F10h+var_F38], rax
0x1800792fc  xor     eax, eax
0x1800792fe  mov     [rdx], ax
0x180079301  mov     [r9], ax
0x180079305  mov     [r10], ax
0x180079309  mov     [rsp+1010h+var_FB0], rcx
0x18007930e  mov     rcx, [rbp+0F10h+arg_38]
0x180079315  mov     dword ptr [rsp+1010h+var_FC8], r8d
0x18007931a  mov     r8, [rbp+0F10h+arg_48]
0x180079321  mov     [rbp+0F10h+var_F40], r9
0x180079325  mov     [rcx], ax
0x180079328  mov     [rbp+0F10h+var_F48], rdx
0x18007932c  mov     [r8], ax
0x180079330  mov     [r11], ax
0x180079334  mov     [rbp+0F10h+var_F60], r10
0x180079338  mov     [rbp+0F10h+var_F30], rcx
0x18007933c  mov     [rbp+0F10h+var_F70], r8
0x180079340  mov     [rbp+0F10h+var_F68], r11
0x180079344  mov     [rsp+1010h+phkResult], 0
0x18007934d  mov     [rbp+0F10h+hKey], 0
0x180079355  mov     [rsp+1010h+cbData], 0
0x18007935d  mov     [rbp+0F10h+var_F80], 0
0x180079364  mov     [rsp+1010h+var_F98], 0
0x18007936c  mov     [rbp+0F10h+var_F90], 0
0x180079373  mov     dword ptr [rbp+0F10h+Size], 0
0x18007937a  mov     [rsp+1010h+var_F94], 0
0x180079382  mov     [rsp+1010h+var_FA8], 0
0x18007938a  mov     word ptr [rbp+0F10h+var_C50], ax
0x180079391  mov     word ptr [rbp+0F10h+Data], ax
0x180079395  movups  [rbp+0F10h+var_F08], xmm0
0x180079399  movups  [rbp+0F10h+var_EF8], xmm0
0x18007939d  movups  [rbp+0F10h+var_EE8], xmm0
0x1800793a1  movups  xmmword ptr [rbp+0F10h+iid.Data1], xmm0
0x1800793a5  test    r13, r13
0x1800793a8  jnz     loc_18007945C
0x1800793ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793b5  lea     r15, WPP_GLOBAL_Control
0x1800793bc  lea     ebx, [rax+15h]
0x1800793bf  cmp     rcx, r15
0x1800793c2  jz      short loc_1800793F1
0x1800793c4  mov     sil, 4
0x1800793c7  cmp     [rcx+0E1h], sil
0x1800793ce  jb      short loc_1800793F1
0x1800793d0  mov     r14b, 10h
0x1800793d3  test    [rcx+0E4h], r14b
0x1800793da  jz      short loc_1800793F1
0x1800793dc  mov     rcx, [rcx+0D8h]
0x1800793e3  lea     r8, WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids
0x1800793ea  mov     edx, ebx
0x1800793ec  call    WPP_SF_
0x1800793f1  mov     eax, cs:dword_18029E6C8
0x1800793f7  cmp     eax, 5
0x1800793fa  jbe     loc_18007A459
0x180079400  mov     rdx, 200000000000h
0x18007940a  lea     rcx, dword_18029E6C8
0x180079411  call    _tlgKeywordOn
0x180079416  test    al, al
0x180079418  jz      loc_18007A459
0x18007941e  lea     rax, aPadapterguidIs; "pAdapterGuid is null"
0x180079425  mov     [rbp+0F10h+var_EB0], rbx
0x180079429  mov     [rbp+0F10h+var_EB8], rax
0x18007942d  lea     rdx, byte_18027850D
0x180079434  lea     rax, [rbp+0F10h+var_ED8]
0x180079438  xor     r9d, r9d
0x18007943b  mov     [rsp+1010h+lpcbData], rax
0x180079440  lea     rcx, dword_18029E6C8
0x180079447  xor     r8d, r8d
0x18007944a  mov     dword ptr [rsp+1010h+lpData], 3
0x180079452  call    _tlgWriteTransfer_EventWriteTransfer
0x180079457  jmp     loc_18007A459
0x18007945c  xor     r9d, r9d
0x18007945f  mov     [rsp+1010h+lpData], rax
0x180079464  xor     r8d, r8d
0x180079467  lea     rcx, GUID_DEVCLASS_NET
0x18007946e  xor     edx, edx
0x180079470  call    cs:__imp_DevObjCreateDeviceInfoList
0x180079476  mov     [rbp+0F10h+var_F50], rax
0x18007947a  mov     rsi, rax
0x18007947d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180079481  jnz     loc_180079545
0x180079487  call    cs:__imp_GetLastError
0x18007948d  mov     edi, eax
0x18007948f  mov     rcx, cs:WPP_GLOBAL_Control
0x180079496  lea     r15, WPP_GLOBAL_Control
0x18007949d  lea     r12, WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids
0x1800794a4  mov     r14b, 10h
0x1800794a7  mov     sil, 4
0x1800794aa  cmp     rcx, r15
0x1800794ad  jz      short loc_1800794D8
0x1800794af  cmp     [rcx+0E1h], sil
0x1800794b6  jb      short loc_1800794D8
0x1800794b8  test    [rcx+0E4h], r14b
0x1800794bf  jz      short loc_1800794D8
0x1800794c1  mov     rcx, [rcx+0D8h]
0x1800794c8  mov     edx, 16h
0x1800794cd  mov     r9d, eax
0x1800794d0  mov     r8, r12
0x1800794d3  call    WPP_SF_d
0x1800794d8  mov     eax, cs:dword_18029E6C8
0x1800794de  cmp     eax, 5
0x1800794e1  jbe     loc_18007A420
0x1800794e7  mov     rdx, 200000000000h
0x1800794f1  lea     rcx, dword_18029E6C8
0x1800794f8  call    _tlgKeywordOn
0x1800794fd  test    al, al
0x1800794ff  jz      loc_18007A420
0x180079505  lea     rax, aDevobjcreatede; "DevObjCreateDeviceInfoList Failure"
0x18007950c  mov     [rbp+0F10h+var_F68], r13
0x180079510  mov     [rbp+0F10h+var_F60], rax
0x180079514  lea     rdx, byte_1802784BD
0x18007951b  lea     rax, [rbp+0F10h+var_F68]
0x18007951f  mov     [rsp+1010h+var_FC0], edi
0x180079523  mov     [rsp+1010h+var_FE0], rax
0x180079528  lea     rax, [rsp+1010h+var_FC0]
0x18007952d  mov     [rsp+1010h+lpcbData], rax
0x180079532  lea     rax, [rbp+0F10h+var_F60]
0x180079536  mov     [rsp+1010h+lpData], rax
0x18007953b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180079540  jmp     loc_18007A420
0x180079545  mov     [rsp+1010h+lpcbData], rdi
0x18007954a  lea     rdx, GUID_DEVCLASS_NET
0x180079551  mov     r9d, 2
0x180079557  mov     [rsp+1010h+lpData], rdi
0x18007955c  xor     r8d, r8d
0x18007955f  mov     rcx, rsi
0x180079562  call    cs:__imp_DevObjGetClassDevs
0x180079568  test    eax, eax
0x18007956a  jnz     loc_18007962E
0x180079570  call    cs:__imp_GetLastError
0x180079576  mov     edi, eax
0x180079578  mov     rcx, cs:WPP_GLOBAL_Control
0x18007957f  lea     r15, WPP_GLOBAL_Control
0x180079586  lea     r12, WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids
0x18007958d  mov     r14b, 10h
0x180079590  mov     sil, 4
0x180079593  cmp     rcx, r15
0x180079596  jz      short loc_1800795C1
0x180079598  cmp     [rcx+0E1h], sil
0x18007959f  jb      short loc_1800795C1
0x1800795a1  test    [rcx+0E4h], r14b
0x1800795a8  jz      short loc_1800795C1
0x1800795aa  mov     rcx, [rcx+0D8h]
0x1800795b1  mov     edx, 17h
0x1800795b6  mov     r9d, eax
0x1800795b9  mov     r8, r12
0x1800795bc  call    WPP_SF_d
0x1800795c1  mov     eax, cs:dword_18029E6C8
0x1800795c7  cmp     eax, 5
0x1800795ca  jbe     loc_18007A416
0x1800795d0  mov     rdx, 200000000000h
0x1800795da  lea     rcx, dword_18029E6C8
0x1800795e1  call    _tlgKeywordOn
0x1800795e6  test    al, al
0x1800795e8  jz      loc_18007A416
0x1800795ee  lea     rax, aDevobjgetclass; "DevObjGetClassDevs Failure"
0x1800795f5  mov     [rbp+0F10h+var_F68], r13
0x1800795f9  mov     [rbp+0F10h+var_F60], rax
0x1800795fd  lea     rdx, unk_1802785A0
0x180079604  lea     rax, [rbp+0F10h+var_F68]
0x180079608  mov     [rsp+1010h+var_FC0], edi
0x18007960c  mov     [rsp+1010h+var_FE0], rax
0x180079611  lea     rax, [rsp+1010h+var_FC0]
0x180079616  mov     [rsp+1010h+lpcbData], rax
0x18007961b  lea     rax, [rbp+0F10h+var_F60]
0x18007961f  mov     [rsp+1010h+lpData], rax
0x180079624  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180079629  jmp     loc_18007A416
0x18007962e  xor     ebx, ebx
0x180079630  mov     [rsp+1010h+var_FC0], edi
0x180079634  lea     r8, [rbp+0F10h+var_F08]
0x180079638  mov     dword ptr [rsp+1010h+var_FD0], ebx
0x18007963c  xor     edx, edx
0x18007963e  mov     dword ptr [rbp+0F10h+var_F08], 30h ; '0'
0x180079645  mov     rcx, rsi
0x180079648  call    cs:__imp_DevObjEnumDeviceInfo
0x18007964e  lea     r15, WPP_GLOBAL_Control
0x180079655  mov     sil, 4
0x180079658  lea     r12, WPP_6309ba5c0c0831fd9a1686f84799f1fb_Traceguids
0x18007965f  mov     r14b, 10h
0x180079662  test    eax, eax
0x180079664  jz      loc_18007A3AE
0x18007966a  cmp     ebx, 0FFFFFFFFh
0x18007966d  jnb     loc_18007A3A4
0x180079673  mov     rcx, [rbp+0F10h+var_F50]
0x180079677  lea     rdx, [rbp+0F10h+var_F08]
0x18007967b  xor     r9d, r9d
0x18007967e  mov     dword ptr [rsp+1010h+lpcbData], 20019h
0x180079686  mov     dword ptr [rsp+1010h+lpData], 2
0x18007968e  lea     r8d, [r9+1]
0x180079692  call    cs:__imp_DevObjOpenDevRegKey
0x180079698  mov     r13, rax
0x18007969b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007969f  jnz     loc_180079761
0x1800796a5  call    cs:__imp_GetLastError
0x1800796ab  mov     edi, eax
0x1800796ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796b4  cmp     rcx, r15
0x1800796b7  jz      short loc_1800796E1
0x1800796b9  cmp     [rcx+0E1h], sil
0x1800796c0  jb      short loc_1800796E1
0x1800796c2  test    [rcx+0E4h], r14b
0x1800796c9  jz      short loc_1800796E1
0x1800796cb  mov     rcx, [rcx+0D8h]
0x1800796d2  lea     edx, [r13+19h]
0x1800796d6  mov     r9d, eax
0x1800796d9  mov     r8, r12
0x1800796dc  call    WPP_SF_d
0x1800796e1  mov     eax, cs:dword_18029E6C8
0x1800796e7  cmp     eax, 5
0x1800796ea  jbe     loc_180079890
0x1800796f0  mov     rdx, 200000000000h
0x1800796fa  lea     rcx, dword_18029E6C8
0x180079701  call    _tlgKeywordOn
0x180079706  test    al, al
0x180079708  jz      loc_180079890
0x18007970e  mov     r13, [rsp+1010h+var_FB0]
0x180079713  lea     rax, aDevobjopendevr; "DevObjOpenDevRegKey Failure"
0x18007971a  mov     qword ptr [rbp+0F10h+Size+4], rax
0x18007971e  lea     rdx, byte_180278543
0x180079725  lea     rax, [rbp+0F10h+var_F58]
0x180079729  mov     [rbp+0F10h+var_F58], r13
0x18007972d  mov     [rsp+1010h+var_FD8], rax
0x180079732  lea     rax, [rsp+1010h+var_FD0]
0x180079737  mov     [rsp+1010h+var_FE0], rax
0x18007973c  lea     rax, [rsp+1010h+var_FBC]
0x180079741  mov     [rsp+1010h+lpcbData], rax
0x180079746  lea     rax, [rbp+0F10h+Size+4]
0x18007974a  mov     [rsp+1010h+lpData], rax
0x18007974f  mov     dword ptr [rsp+1010h+var_FD0], edi
0x180079753  mov     [rsp+1010h+var_FBC], ebx
0x180079757  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18007975c  jmp     loc_180079895
0x180079761  lea     rax, [rsp+1010h+cbData]
0x180079766  mov     [rsp+1010h+cbData], 4Eh ; 'N'
0x18007976e  mov     [rsp+1010h+lpcbData], rax; lpcbData
0x180079773  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x18007977a  lea     rax, [rbp+0F10h+Data]
0x18007977e  xor     r9d, r9d; lpType
0x180079781  xor     r8d, r8d; lpReserved
0x180079784  mov     [rsp+1010h+lpData], rax; lpData
0x180079789  mov     rcx, r13; hKey
0x18007978c  call    cs:__imp_RegQueryValueExW
0x180079792  mov     edi, eax
0x180079794  test    eax, eax
0x180079796  jz      loc_18007984E
0x18007979c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800797a3  cmp     rcx, r15
0x1800797a6  jz      short loc_1800797D1
0x1800797a8  cmp     [rcx+0E1h], sil
0x1800797af  jb      short loc_1800797D1
0x1800797b1  test    [rcx+0E4h], r14b
0x1800797b8  jz      short loc_1800797D1
0x1800797ba  mov     rcx, [rcx+0D8h]
0x1800797c1  mov     edx, 19h
0x1800797c6  mov     r9d, eax
0x1800797c9  mov     r8, r12
0x1800797cc  call    WPP_SF_d
0x1800797d1  mov     eax, cs:dword_18029E6C8
0x1800797d7  cmp     eax, 5
0x1800797da  jbe     loc_180079887
0x1800797e0  mov     rdx, 200000000000h
0x1800797ea  lea     rcx, dword_18029E6C8
0x1800797f1  call    _tlgKeywordOn
0x1800797f6  test    al, al
0x1800797f8  jz      loc_180079887
0x1800797fe  mov     rax, [rsp+1010h+var_FB0]
0x180079803  lea     rdx, byte_180278403
0x18007980a  mov     qword ptr [rbp+0F10h+Size+4], rax
0x18007980e  lea     rax, aRegqueryvaluee; "RegQueryValueEx NetCfgInstanceId Failur"...
0x180079815  mov     [rbp+0F10h+var_F58], rax
0x180079819  lea     rax, [rbp+0F10h+Size+4]
0x18007981d  mov     [rsp+1010h+var_FD8], rax
0x180079822  lea     rax, [rsp+1010h+var_FBC]
0x180079827  mov     [rsp+1010h+var_FE0], rax
0x18007982c  lea     rax, [rsp+1010h+var_FD0]
0x180079831  mov     [rsp+1010h+lpcbData], rax
0x180079836  lea     rax, [rbp+0F10h+var_F58]
0x18007983a  mov     [rsp+1010h+lpData], rax
0x18007983f  mov     [rsp+1010h+var_FBC], edi
  ... truncated ...
```
