# ReadWinInetProxySettings(HKEY__ *,_FILETIME *,int *,int,int,CWxGlobalCounters *,ulong *,int *,WININET_PROXY_INFO_EX *)

- ea: `0x18001fd20`
- end: `0x180020e3a`
- name: `?ReadWinInetProxySettings@@YAKPEAUHKEY__@@PEAU_FILETIME@@PEAHHHPEAVCWxGlobalCounters@@PEAK2PEAUWININET_PROXY_INFO_EX@@@Z`
- size: `4378`
- prototype: `unsigned int __fastcall(HKEY, struct _FILETIME *, int *, int, int, struct CWxGlobalCounters *, unsigned int *, int *, struct WININET_PROXY_INFO_EX *)`
- caller_count: `6`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001db1c`
- `0x18001e610`
- `0x18001f610`
- `0x18001fd20`
- `0x1800219f0`
- `0x1800743f0`

## callees

- `0x18001fd20`
- `0x180020e40`
- `0x1800210c0`
- `0x180021320`
- `0x1800219f0`
- `0x180063190`
- `0x180073fc4`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cdd7c`
- `0x1800cf008`
- `0x1800cf58c`
- `0x1800d16a0`
- `0x1800d1dd8`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800dd064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001ff15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002063a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001ff15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002063a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ff98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002032f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800204b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800206fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ff98`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002032f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800204b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800206fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020518`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020518`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020a07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020a07`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020403`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020415`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800205e3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800208ee`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020d3b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020d49`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020d57`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020403`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020415`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800205e3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800208ee`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020d3b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020d49`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180020d57`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002071a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180020770`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800207c6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002081c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002088c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180020919`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180020a28`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002071a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180020770`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800207c6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002081c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002088c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180020919`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180020a28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001feb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001feb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800203dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800204fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800203dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800204fc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180020582`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180020e06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180020582`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180020e06`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180020003`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180020003`
- `ntdll!RtlNtStatusToDosError` at `0x180020d99`
- `ntdll!RtlNtStatusToDosError` at `0x180020d99`

## pseudocode

```c
__int64 __fastcall ReadWinInetProxySettings(
        HKEY a1,
        struct _FILETIME *a2,
        int *a3,
        int a4,
        int a5,
        unsigned int **a6,
        unsigned int *a7,
        int *a8,
        struct WININET_PROXY_INFO_EX *a9)
{
  struct WININET_PROXY_INFO_EX *v9; // rax
  HKEY v10; // r14
  DWORD v11; // ebx
  struct _FILETIME *v13; // rsi
  const CHAR *v14; // rdi
  unsigned int v15; // eax
  DWORD v16; // ebx
  unsigned __int64 v17; // r13
  unsigned int v18; // eax
  __int64 v19; // rcx
  int v20; // r14d
  DWORD v21; // ebx
  unsigned int v22; // esi
  DWORD v23; // ebx
  unsigned int v24; // edi
  unsigned int v25; // edi
  __int64 v26; // rsi
  unsigned int v27; // edi
  HGLOBAL v28; // r15
  __int64 v29; // rsi
  HGLOBAL v30; // r15
  unsigned int v31; // edi
  __int64 v32; // rsi
  HGLOBAL v33; // r15
  unsigned int v34; // edi
  unsigned int v35; // edi
  __int64 v36; // rsi
  HGLOBAL v37; // r15
  unsigned int v38; // edi
  unsigned int v39; // edi
  unsigned int v40; // edi
  unsigned int v41; // r12d
  __int64 v42; // rsi
  HGLOBAL v43; // r15
  unsigned int v44; // edi
  unsigned int v45; // edi
  unsigned int v46; // r14d
  unsigned int v47; // edi
  int v48; // eax
  unsigned int v49; // ebx
  signed int v50; // esi
  int v51; // edi
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  unsigned int v58; // edi
  unsigned int v59; // eax
  SIZE_T v61; // rdi
  HGLOBAL v62; // rax
  void *v63; // rbx
  __int64 v64; // rbx
  unsigned int v65; // ebx
  char *v66; // rax
  char *v67; // r14
  unsigned int v68; // esi
  DWORD v69; // eax
  unsigned int v70; // ebx
  int WinInetProxySettings; // eax
  ULONG v72; // eax
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  signed int i; // [rsp+64h] [rbp-9Ch]
  int v75; // [rsp+68h] [rbp-98h]
  int v76; // [rsp+6Ch] [rbp-94h]
  const CHAR *v78; // [rsp+78h] [rbp-88h]
  _DWORD v80[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v81; // [rsp+B0h] [rbp-50h] BYREF
  HGLOBAL hMem[2]; // [rsp+C0h] [rbp-40h]
  HGLOBAL v83[2]; // [rsp+D0h] [rbp-30h]
  HGLOBAL v84[2]; // [rsp+E0h] [rbp-20h] BYREF
  HGLOBAL v85[2]; // [rsp+F0h] [rbp-10h] BYREF
  HGLOBAL v86[2]; // [rsp+100h] [rbp+0h] BYREF
  HGLOBAL v87[2]; // [rsp+110h] [rbp+10h]
  HKEY hKey; // [rsp+120h] [rbp+20h] BYREF
  HKEY v89; // [rsp+128h] [rbp+28h] BYREF
  int v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+134h] [rbp+34h]
  DWORD cbData; // [rsp+138h] [rbp+38h]
  int v93; // [rsp+13Ch] [rbp+3Ch]
  LPVOID lpMem; // [rsp+140h] [rbp+40h]
  LPCSTR lpValueName; // [rsp+148h] [rbp+48h]
  __int64 v96; // [rsp+150h] [rbp+50h]
  unsigned int v97; // [rsp+158h] [rbp+58h] BYREF
  int v98; // [rsp+15Ch] [rbp+5Ch]
  unsigned int v99; // [rsp+160h] [rbp+60h] BYREF
  WINBOOL AccessStatus; // [rsp+164h] [rbp+64h] BYREF
  int v101; // [rsp+168h] [rbp+68h] BYREF
  WCHAR SubKey; // [rsp+170h] [rbp+70h] BYREF
  char v103[510]; // [rsp+172h] [rbp+72h] BYREF

  v9 = a9;
  v10 = a1;
  v11 = 0;
  v13 = a2;
  v80[0] = a4;
  v98 = 0;
  v90 = 0;
  v91 = 1;
  cbData = 0;
  lpMem = 0;
  v93 = 0;
  v89 = 0;
  lpValueName = 0;
  v96 = 0;
  v99 = 0;
  v101 = 0;
  v97 = 0;
  v81 = 0;
  v76 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v83 = 0;
  *(_OWORD *)v84 = 0;
  *(_OWORD *)v85 = 0;
  *(_OWORD *)v86 = 0;
  *(_OWORD *)v87 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_q(1029, 48, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
    v9 = a9;
    v11 = cbData;
  }
  if ( a3 )
    *a3 = 0;
  if ( a8 )
    *a8 = 0;
  if ( v13 && !a3 )
  {
    v50 = -2147024809;
    v98 = 1883;
LABEL_112:
    hMem[0] = 0;
    if ( hMem[1] )
    {
      GlobalFree(hMem[1]);
      v11 = cbData;
    }
    if ( v83[0] )
    {
      GlobalFree(v83[0]);
      v11 = cbData;
    }
    if ( v83[1] )
    {
      GlobalFree(v83[1]);
      v11 = cbData;
    }
    if ( v84[0] )
    {
      GlobalFree(v84[0]);
      v11 = cbData;
    }
    if ( v85[0] )
    {
      GlobalFree(v85[0]);
      v11 = cbData;
    }
    if ( v86[1] )
    {
      GlobalFree(v86[1]);
      v11 = cbData;
    }
    v19 = (__int64)v87[1];
    if ( v87[1] )
    {
      GlobalFree(v87[1]);
      v11 = cbData;
    }
    v81 = 0;
    DWORD1(v81) = 1;
    *(_OWORD *)hMem = 0;
    *(_OWORD *)v83 = 0;
    *(_OWORD *)v84 = 0;
    *(_OWORD *)v85 = 0;
    *(_OWORD *)v86 = 0;
    *(_OWORD *)v87 = 0;
    goto LABEL_127;
  }
  if ( !v9 || *(_DWORD *)v9 != 112 )
  {
    v50 = -2147024809;
    v98 = 1889;
    goto LABEL_112;
  }
  v14 = (const CHAR *)*((_QWORD *)v9 + 2);
  i = 0;
  if ( !v14 || !*v14 )
  {
    v78 = "DefaultConnectionSettings";
LABEL_12:
    v75 = 1;
    goto LABEL_13;
  }
  v75 = 0;
  v78 = (const CHAR *)*((_QWORD *)v9 + 2);
  if ( CompareStringA(0x7Fu, 1u, v14, -1, "DefaultConnectionSettings", -1) == 2 )
    goto LABEL_12;
LABEL_13:
  AccessStatus = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 31, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
  if ( (unsigned int)IsProxySettingsPerUser() )
  {
    hKey = 0;
    SubKey = 0;
    memset_0(v103, 0, sizeof(v103));
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 25, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, 1, phkResult);
    if ( !(unsigned int)InitClientUserString(&SubKey) )
    {
      v15 = RegOpenKeyExW(HKEY_USERS, &SubKey, 0, 1u, &hKey);
      v16 = v15;
      if ( v15 )
      {
        if ( (xmmword_180107A50 & 0x20) != 0 )
          WPP_SF_d(517, 26, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, v15, phkResult);
        SetLastError(v16);
      }
    }
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_q(1029, 27, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
    v17 = (unsigned __int64)hKey;
    if ( !hKey )
    {
      v17 = -2147483647;
      if ( GlobalIsProcessNtService )
      {
        if ( (int)WxIsSystemService(&AccessStatus) >= 0 && AccessStatus )
        {
          if ( (xmmword_180107A60 & 0x20) != 0 )
            WPP_SF_(1029, 32, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
          v17 = 0;
        }
      }
    }
  }
  else
  {
    v17 = -2147483646;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_q(1029, 33, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
  if ( !v17 )
  {
    v11 = cbData;
    v50 = -2147024894;
    v98 = 1914;
    goto LABEL_112;
  }
  *(_QWORD *)&v81 = 0x100000070LL;
  hMem[0] = (HGLOBAL)v14;
  AcquireSRWLockShared(&g_srwProxyReg);
  v76 = 1;
  v18 = CRegBlob::Init(&v89, (HKEY)v17, v10, 0, phkResult, v78, v13, &v101);
  if ( v18 == 8 )
  {
    v51 = 1;
    v50 = -2147024888;
    v98 = 1940;
    goto LABEL_107;
  }
  v19 = (unsigned int)v101;
  if ( v101 && a3 )
  {
    *a3 = v101;
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_(1029, 49, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
    v51 = 1;
    v50 = 0;
    goto LABEL_107;
  }
  if ( v18 || v90 )
    goto LABEL_33;
  v20 = v93;
  v21 = cbData;
  v22 = v93 - cbData;
  if ( v93 - cbData > 4 )
  {
    v22 = 4;
LABEL_41:
    memcpy_0(&v99, (char *)lpMem + cbData, v22);
    v23 = v22 + v21;
    cbData = v23;
    if ( v99 < 0x3C )
      goto LABEL_32;
    v24 = v20 - v23;
    if ( v20 - v23 > 4 )
    {
      v24 = 4;
    }
    else if ( !v24 )
    {
      goto LABEL_45;
    }
    memcpy_0((char *)&v81 + 8, (char *)lpMem + v23, v24);
    v23 += v24;
    cbData = v23;
LABEL_45:
    v25 = v20 - v23;
    if ( v20 - v23 > 4 )
    {
      v25 = 4;
    }
    else if ( !v25 )
    {
      goto LABEL_48;
    }
    memcpy_0((char *)&v81 + 4, (char *)lpMem + v23, v25);
    v23 += v25;
    cbData = v23;
LABEL_48:
    v26 = 0;
    v27 = v20 - v23;
    v80[0] = 0;
    v28 = 0;
    if ( v20 - v23 > 4 )
    {
      v27 = 4;
    }
    else if ( !v27 )
    {
LABEL_51:
      if ( v27 == 4 && (unsigned int)(v26 - 1) <= 0xFFFFFFFD )
      {
        v28 = GlobalAlloc(0x40u, (unsigned int)(v26 + 1));
        if ( v28 )
        {
          if ( v90 )
          {
            v26 = 0;
          }
          else
          {
            if ( (unsigned int)v26 >= v93 - cbData )
              v26 = v93 - cbData;
            if ( (_DWORD)v26 )
            {
              memcpy_0(v28, (char *)lpMem + cbData, (unsigned int)v26);
              cbData += v26;
            }
          }
          *((_BYTE *)v28 + v26) = 0;
        }
        v23 = cbData;
        v20 = v93;
      }
      v29 = 0;
      hMem[1] = v28;
      v30 = 0;
      v80[0] = 0;
      if ( v90 )
      {
LABEL_59:
        v32 = 0;
        v83[0] = v30;
        v33 = 0;
        v80[0] = 0;
        if ( v90 )
          goto LABEL_65;
        v34 = v20 - v23;
        if ( v20 - v23 > 4 )
        {
          v34 = 4;
        }
        else if ( !v34 )
        {
LABEL_63:
          if ( v34 == 4 && (unsigned int)(v32 - 1) <= 0xFFFFFFFD )
          {
            v33 = GlobalAlloc(0x40u, (unsigned int)(v32 + 1));
            if ( v33 )
            {
              if ( v90 )
              {
                v32 = 0;
              }
              else
              {
                if ( (unsigned int)v32 >= v93 - cbData )
                  v32 = v93 - cbData;
                if ( (_DWORD)v32 )
                {
                  memcpy_0(v33, (char *)lpMem + cbData, (unsigned int)v32);
                  cbData += v32;
                }
              }
              *((_BYTE *)v33 + v32) = 0;
            }
            v23 = cbData;
            v20 = v93;
          }
LABEL_65:
          v83[1] = v33;
          if ( v90 )
            goto LABEL_69;
          v35 = v20 - v23;
          if ( v20 - v23 > 4 )
          {
            v35 = 4;
          }
          else if ( !v35 )
          {
            goto LABEL_69;
          }
          memcpy_0(&v84[1], (char *)lpMem + v23, v35);
          v23 += v35;
          cbData = v23;
LABEL_69:
          v36 = 0;
          v37 = 0;
          v80[0] = 0;
          if ( v90 )
            goto LABEL_75;
          v38 = v20 - v23;
          if ( v20 - v23 > 4 )
          {
            v38 = 4;
          }
          else if ( !v38 )
          {
LABEL_73:
            if ( v38 == 4 && (unsigned int)(v36 - 1) <= 0xFFFFFFFD )
            {
              v37 = GlobalAlloc(0x40u, (unsigned int)(v36 + 1));
              if ( v37 )
              {
                if ( v90 )
                {
                  v36 = 0;
                }
                else
                {
                  if ( (unsigned int)v36 >= v93 - cbData )
                    v36 = v93 - cbData;
                  if ( (_DWORD)v36 )
                  {
                    memcpy_0(v37, (char *)lpMem + cbData, (unsigned int)v36);
                    cbData += v36;
                  }
                }
                *((_BYTE *)v37 + v36) = 0;
              }
              v23 = cbData;
              v20 = v93;
            }
LABEL_75:
            v85[0] = v37;
            if ( v90 )
              goto LABEL_82;
            v39 = v20 - v23;
            if ( v20 - v23 > 8 )
            {
              v39 = 8;
            }
            else if ( !v39 )
            {
              goto LABEL_79;
            }
            memcpy_0((char *)&v85[1] + 4, (char *)lpMem + v23, v39);
            v23 += v39;
            cbData = v23;
LABEL_79:
            v40 = v20 - v23;
            if ( v20 - v23 > 4 )
            {
              v40 = 4;
            }
            else if ( !v40 )
            {
              goto LABEL_82;
            }
            memcpy_0((char *)v86 + 4, (char *)lpMem + v23, v40);
            v23 += v40;
            cbData = v23;
LABEL_82:
            if ( HIDWORD(v86[0]) )
            {
              v86[1] = 0;
              v61 = (unsigned int)(4 * HIDWORD(v86[0]));
              v62 = GlobalAlloc(0, v61);
              v63 = v62;
              if ( !v62 )
              {
                v51 = 1;
                v50 = -2147024882;
                v98 = 2055;
                goto LABEL_107;
              }
              memset_0(v62, 0, v61);
              v86[1] = v63;
              v64 = 0;
              v41 = 4;
              for ( i = 0; (unsigned int)v64 < HIDWORD(v86[0]); v64 = (unsigned int)(v64 + 1) )
                CRegBlob::ReadBytes((CRegBlob *)&v89, (char *)v86[1] + 4 * v64, 4u);
              v20 = v93;
              v23 = cbData;
            }
            else
            {
              v41 = 4;
            }
            v42 = 0;
            v43 = 0;
            v80[0] = 0;
            if ( v90 )
            {
LABEL_90:
              v84[0] = v43;
              if ( v90 )
                goto LABEL_94;
              v45 = v20 - v23;
              if ( v20 - v23 <= 4 )
              {
                if ( !v45 )
                {
LABEL_94:
                  if ( v99 < 0x46 )
                    goto LABEL_98;
                  LODWORD(v87[0]) = 0;
                  v87[1] = 0;
                  if ( v90 )
                    goto LABEL_98;
                  v46 = v20 - v23;
                  if ( v46 <= 4 )
                  {
                    v41 = v46;
                    if ( !v46 )
                      goto LABEL_98;
                  }
                  memcpy_0(&v97, (char *)lpMem + v23, v41);
                  v47 = v97;
                  v11 = v41 + v23;
                  cbData = v11;
                  if ( !v97 )
                    goto LABEL_98;
                  v19 = 0xFFFFFFFFLL;
                  if ( (unsigned __int64)v97 << 7 > 0xFFFFFFFF )
                  {
                    v51 = 1;
                    v50 = -2147024362;
                    v98 = 2079;
                    goto LABEL_108;
                  }
                  v87[1] = 0;
                  v65 = v97 << 7;
                  v66 = (char *)GlobalAlloc(0, v97 << 7);
                  v67 = v66;
                  if ( !v66 )
                  {
                    v51 = 1;
                    v50 = -2147024882;
                    v98 = 2081;
                    goto LABEL_107;
                  }
                  memset_0(v66, 0, v65);
                  v87[1] = v67;
                  LODWORD(v87[0]) = v47;
                  v68 = 0;
                  i = 0;
                  if ( !v47 )
                  {
LABEL_98:
                    ReleaseSRWLockShared(&g_srwProxyReg);
                    v76 = 0;
                    goto LABEL_99;
                  }
                  v69 = cbData;
                  while ( 1 )
                  {
                    if ( !v90 )
                    {
                      v70 = v93 - v69;
                      if ( v93 - v69 > 0x80 )
                      {
                        v70 = 128;
LABEL_251:
                        memcpy_0(&v67[128 * (unsigned __int64)v68], (char *)lpMem + v69, v70);
                        v67 = (char *)v87[1];
                        v69 = v70 + cbData;
                        v47 = (unsigned int)v87[0];
                        cbData += v70;
                        goto LABEL_252;
                      }
                      if ( v70 )
                        goto LABEL_251;
                    }
LABEL_252:
                    if ( ++v68 >= v47 )
                      goto LABEL_98;
                  }
                }
              }
              else
              {
                v45 = 4;
              }
              memcpy_0(&v85[1], (char *)lpMem + v23, v45);
              v23 += v45;
              cbData = v23;
              goto LABEL_94;
            }
            v44 = v20 - v23;
            if ( v20 - v23 > 4 )
            {
              v44 = 4;
            }
            else if ( !v44 )
            {
LABEL_88:
              if ( v44 == 4 && (unsigned int)(v42 - 1) <= 0xFFFFFFFD )
              {
                v43 = GlobalAlloc(0x40u, (unsigned int)(v42 + 1));
                if ( v43 )
                {
                  if ( v90 )
                  {
                    v42 = 0;
                  }
                  else
                  {
                    if ( (unsigned int)v42 >= v93 - cbData )
                      v42 = v93 - cbData;
                    if ( (_DWORD)v42 )
                    {
                      memcpy_0(v43, (char *)lpMem + cbData, (unsigned int)v42);
                      cbData += v42;
                    }
                  }
                  *((_BYTE *)v43 + v42) = 0;
                }
                v23 = cbData;
                v20 = v93;
              }
              goto LABEL_90;
            }
            memcpy_0(v80, (char *)lpMem + v23, v44);
            v42 = v80[0];
            v23 += v44;
            cbData = v23;
            goto LABEL_88;
          }
          memcpy_0(v80, (char *)lpMem + v23, v38);
          v36 = v80[0];
          v23 += v38;
          cbData = v23;
          goto LABEL_73;
        }
        memcpy_0(v80, (char *)lpMem + v23, v34);
        v32 = v80[0];
        v23 += v34;
        cbData = v23;
        goto LABEL_63;
      }
      v31 = v20 - v23;
      if ( v20 - v23 > 4 )
      {
        v31 = 4;
      }
      else if ( !v31 )
      {
LABEL_57:
        if ( v31 == 4 && (unsigned int)(v29 - 1) <= 0xFFFFFFFD )
        {
          v30 = GlobalAlloc(0x40u, (unsigned int)(v29 + 1));
          if ( v30 )
          {
            if ( v90 )
            {
              v29 = 0;
            }
            else
            {
              if ( (unsigned int)v29 >= v93 - cbData )
                v29 = v93 - cbData;
              if ( (_DWORD)v29 )
              {
                memcpy_0(v30, (char *)lpMem + cbData, (unsigned int)v29);
                cbData += v29;
              }
            }
            *((_BYTE *)v30 + v29) = 0;
          }
          v23 = cbData;
          v20 = v93;
        }
        goto LABEL_59;
      }
      memcpy_0(v80, (char *)lpMem + v23, v31);
      v29 = v80[0];
      v23 += v31;
      cbData = v23;
      goto LABEL_57;
    }
    memcpy_0(v80, (char *)lpMem + v23, v27);
    v26 = v80[0];
    v23 += v27;
    cbData = v23;
    goto LABEL_51;
  }
  if ( v22 )
    goto LABEL_41;
LABEL_32:
  v10 = a1;
  v13 = a2;
LABEL_33:
  ReleaseSRWLockShared(&g_srwProxyReg);
  v76 = 0;
  if ( v75 )
    goto LABEL_34;
  if ( v80[0] )
  {
    hMem[0] = 0;
    WinInetProxySettings = ReadWinInetProxySettings(v10, v13, a3, 0, a5, 0, 0, 0, (struct WININET_PROXY_INFO_EX *)&v81);
    i = WinInetProxySettings;
    v50 = WinInetProxySettings;
    hMem[0] = (HGLOBAL)v14;
    if ( WinInetProxySettings > 0 )
    {
      v50 = (unsigned __int16)WinInetProxySettings | 0x80070000;
      i = v50;
    }
    if ( v50 < 0 )
    {
      v51 = 1;
      v98 = 1996;
      goto LABEL_107;
    }
    goto LABEL_35;
  }
  if ( a5 )
LABEL_34:
    DWORD1(v81) |= 8u;
LABEL_35:
  if ( a8 )
    *a8 = 1;
LABEL_99:
  v48 = DWORD2(v81);
  v49 = 0;
  if ( !DWORD2(v81) )
    v48 = 1;
  DWORD2(v81) = v48;
  if ( v75 )
    MigrateLegacyProxySettings((HKEY)v17, (struct WININET_PROXY_INFO_EX *)&v81, (struct CWxGlobalCounters *)a6);
  if ( !a6 || !a7 )
  {
    v50 = i;
    goto LABEL_105;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(phkResult) = 0;
    WPP_SF_qD(1029, 13, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, a6);
  }
  v97 = 0;
  AcquireSRWLockShared((PSRWLOCK)a6);
  if ( !a6[2] )
  {
    v50 = -2147019873;
    goto LABEL_171;
  }
  v50 = 0;
  v49 = *a6[3];
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(phkResult) = 0;
    WPP_SF_qDD(1029, 14, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, a6);
LABEL_171:
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 15, WPP_d4cae040b0b73edceba5bfba558ab8fc_Traceguids, (unsigned int)v50, phkResult);
  }
  ReleaseSRWLockShared((PSRWLOCK)a6);
  if ( v50 >= 0 )
  {
    *a7 = v49;
LABEL_105:
    v19 = (__int64)a9;
    v51 = 0;
    v52 = *(_OWORD *)hMem;
    *(_OWORD *)a9 = v81;
    v53 = *(_OWORD *)v83;
    *((_OWORD *)a9 + 1) = v52;
    v54 = *(_OWORD *)v84;
    *((_OWORD *)a9 + 2) = v53;
    v55 = *(_OWORD *)v85;
    *((_OWORD *)a9 + 3) = v54;
    v56 = *(_OWORD *)v86;
    *((_OWORD *)a9 + 4) = v55;
    v57 = *(_OWORD *)v87;
    *((_OWORD *)a9 + 5) = v56;
    *((_OWORD *)a9 + 6) = v57;
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_DsDDDssss(
        (_DWORD)a9,
        (_DWORD)a2,
        (_DWORD)a3,
        v49,
        (__int64)v78,
        *((_DWORD *)a9 + 2),
        *((_DWORD *)a9 + 1),
        *((_DWORD *)a9 + 14),
        *((_QWORD *)a9 + 3),
        *((_QWORD *)a9 + 4),
        *((_QWORD *)a9 + 5),
        *((_QWORD *)a9 + 8));
    goto LABEL_107;
  }
  v51 = 1;
  v98 = 2120;
LABEL_107:
  v11 = cbData;
LABEL_108:
  if ( v17 + 2147483645 <= 0x7FFFFFFB || v17 <= 0xFFFFFFFF80000000uLL )
  {
    RegCloseKey((HKEY)v17);
    v11 = cbData;
  }
  if ( v51 )
    goto LABEL_112;
LABEL_127:
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_d(1029, 51, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, (unsigned int)v50, phkResult);
    v11 = cbData;
  }
  if ( (v50 & 0x1FFF0000) == 0xC0000 )
  {
    v58 = (unsigned __int16)v50;
  }
  else if ( v50 < 0 )
  {
    if ( (v50 & 0x1FFF0000) == 0x70000 )
    {
      v58 = (unsigned __int16)v50;
      if ( !(_WORD)v50 )
        v58 = 317;
    }
    else if ( (v50 & 0x10000000) != 0 )
    {
      v72 = RtlNtStatusToDosError(v50 & 0xEFFFFFFF);
      v11 = cbData;
      v58 = v72;
      if ( v72 )
      {
        if ( v72 == 317 )
          v58 = v50;
      }
      else
      {
        v58 = v50;
      }
    }
    else
    {
      v58 = v50;
    }
  }
  else
  {
    v58 = 0;
  }
  if ( v76 )
  {
    ReleaseSRWLockShared(&g_srwProxyReg);
    v11 = cbData;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(phkResult) = v90;
    WPP_SF_qlll(v19, a2, a3, &v89);
    v11 = cbData;
  }
  if ( !v90 || !v91 || !lpMem || !lpValueName )
  {
    v59 = 87;
    goto LABEL_139;
  }
  if ( HIDWORD(v96) )
  {
    v59 = RegSetValueExA(v89, "SavedLegacySettings", 0, 3u, (const BYTE *)lpMem, v11);
    if ( v59 )
      goto LABEL_139;
    v11 = cbData;
  }
  v59 = RegSetValueExA(v89, lpValueName, 0, 3u, (const BYTE *)lpMem, v11);
  if ( !v59 )
    v91 = 0;
LABEL_139:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 15, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, v59, phkResult);
  if ( v89 && (_DWORD)v96 )
    RegCloseKey(v89);
  v89 = 0;
  if ( lpMem )
    HeapFree(g_hWxProcessHeap, 0, lpMem);
  return v58;
}

```

## disassembly

```asm
0x18001fd20  mov     [rsp-8+arg_18], rbx
0x18001fd25  push    rbp
0x18001fd26  push    rsi
0x18001fd27  push    rdi
0x18001fd28  push    r12
0x18001fd2a  push    r13
0x18001fd2c  push    r14
0x18001fd2e  push    r15
0x18001fd30  lea     rbp, [rsp-280h]
0x18001fd38  sub     rsp, 380h
0x18001fd3f  mov     rax, cs:__security_cookie
0x18001fd46  xor     rax, rsp
0x18001fd49  mov     [rbp+2B0h+var_40], rax
0x18001fd50  mov     rax, [rbp+2B0h+arg_40]
0x18001fd57  xor     r13d, r13d
0x18001fd5a  mov     r12, [rbp+2B0h+arg_38]
0x18001fd61  xorps   xmm0, xmm0
0x18001fd64  mov     r14, rcx
0x18001fd67  mov     [rsp+3B0h+var_340], rcx
0x18001fd6c  mov     rcx, [rbp+2B0h+arg_28]
0x18001fd73  mov     edi, 1
0x18001fd78  mov     [rbp+2B0h+SRWLock], rcx
0x18001fd7c  mov     ebx, r13d
0x18001fd7f  mov     rcx, [rbp+2B0h+arg_30]
0x18001fd86  mov     r15, r8
0x18001fd89  mov     [rbp+2B0h+var_330], rcx
0x18001fd8d  mov     rsi, rdx
0x18001fd90  mov     [rbp+2B0h+var_310], r9d
0x18001fd94  mov     [rbp+2B0h+var_328], rdx
0x18001fd98  mov     [rbp+2B0h+var_318], rax
0x18001fd9c  mov     [rbp+2B0h+var_254], r13d
0x18001fda0  mov     [rbp+2B0h+var_280], r13d
0x18001fda4  mov     [rbp+2B0h+var_27C], edi
0x18001fda7  mov     [rbp+2B0h+cbData], ebx
0x18001fdaa  mov     [rbp+2B0h+lpMem], r13
0x18001fdae  mov     [rbp+2B0h+var_274], r13d
0x18001fdb2  mov     [rbp+2B0h+var_288], r13
0x18001fdb6  mov     [rbp+2B0h+lpValueName], r13
0x18001fdba  mov     [rbp+2B0h+var_260], r13
0x18001fdbe  mov     [rbp+2B0h+var_250], r13d
0x18001fdc2  mov     [rbp+2B0h+var_248], r13d
0x18001fdc6  mov     [rbp+2B0h+var_258], r13d
0x18001fdca  movups  [rbp+2B0h+var_300], xmm0
0x18001fdce  mov     [rsp+3B0h+var_344], r13d
0x18001fdd3  movups  xmmword ptr [rbp+2B0h+hMem], xmm0
0x18001fdd7  movups  xmmword ptr [rbp+2B0h+var_2E0], xmm0
0x18001fddb  movups  xmmword ptr [rbp+2B0h+var_2D0], xmm0
0x18001fddf  movups  xmmword ptr [rbp+2B0h+var_2C0], xmm0
0x18001fde3  movups  xmmword ptr [rbp+2B0h+var_2B0], xmm0
0x18001fde7  movups  xmmword ptr [rbp+2B0h+var_2A0], xmm0
0x18001fdeb  test    byte ptr cs:xmmword_180107A60, 20h
0x18001fdf2  jnz     loc_180020AEA
0x18001fdf8  test    r15, r15
0x18001fdfb  jz      short loc_18001FE00
0x18001fdfd  mov     [r15], r13d
0x18001fe00  test    r12, r12
0x18001fe03  jz      short loc_18001FE09
0x18001fe05  mov     [r12], r13d
0x18001fe09  test    rsi, rsi
0x18001fe0c  jnz     loc_18002086A
0x18001fe12  test    rax, rax
0x18001fe15  jz      loc_180020ABC
0x18001fe1b  cmp     dword ptr [rax], 70h ; 'p'
0x18001fe1e  jnz     loc_180020ABC
0x18001fe24  mov     rdi, [rax+10h]
0x18001fe28  mov     [rsp+3B0h+var_34C], r13d
0x18001fe2d  test    rdi, rdi
0x18001fe30  jnz     loc_18001FFC7
0x18001fe36  lea     rax, aDefaultconnect_0; "DefaultConnectionSettings"
0x18001fe3d  mov     ebx, 1
0x18001fe42  mov     [rsp+3B0h+var_338], rax
0x18001fe47  mov     [rsp+3B0h+var_348], ebx
0x18001fe4b  mov     [rbp+2B0h+AccessStatus], r13d
0x18001fe4f  test    byte ptr cs:xmmword_180107A60, 20h
0x18001fe56  jnz     loc_180020B0F
0x18001fe5c  call    ?IsProxySettingsPerUser@@YAHXZ; IsProxySettingsPerUser(void)
0x18001fe61  test    eax, eax
0x18001fe63  jz      loc_180020AB0
0x18001fe69  xor     edx, edx; Val
0x18001fe6b  mov     [rbp+2B0h+hKey], r13
0x18001fe6f  mov     r8d, 1FEh; Size
0x18001fe75  mov     [rbp+2B0h+SubKey], r13w
0x18001fe7a  lea     rcx, [rbp+2B0h+var_23E]; void *
0x18001fe7e  call    memset_0
0x18001fe83  test    byte ptr cs:xmmword_180107A60, 20h
0x18001fe8a  jnz     loc_180020C01
0x18001fe90  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x18001fe94  call    ?InitClientUserString@@YAKPEAG@Z; InitClientUserString(ushort *)
0x18001fe99  test    eax, eax
0x18001fe9b  jnz     short loc_18001FEC7
0x18001fe9d  lea     rax, [rbp+2B0h+hKey]
0x18001fea1  mov     r9d, ebx; samDesired
0x18001fea4  xor     r8d, r8d; ulOptions
0x18001fea7  mov     [rsp+3B0h+phkResult], rax; unsigned __int16 *
0x18001feac  lea     rdx, [rbp+2B0h+SubKey]; lpSubKey
0x18001feb0  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001feb7  call    cs:__imp_RegOpenKeyExW
0x18001febd  mov     ebx, eax
0x18001febf  test    eax, eax
0x18001fec1  jnz     loc_1800209F8
0x18001fec7  test    byte ptr cs:xmmword_180107A60, 20h
0x18001fece  jnz     loc_180020B2A
0x18001fed4  mov     r13, [rbp+2B0h+hKey]
0x18001fed8  test    r13, r13
0x18001fedb  jz      loc_1800209A2
0x18001fee1  test    byte ptr cs:xmmword_180107A60, 20h
0x18001fee8  jnz     loc_180020C3D
0x18001feee  test    r13, r13
0x18001fef1  jz      loc_1800208DA
0x18001fef7  mov     ebx, 1
0x18001fefc  mov     dword ptr [rbp+2B0h+var_300], 70h ; 'p'
0x18001ff03  lea     rcx, ?g_srwProxyReg@@3VWxSrw@@A; SRWLock
0x18001ff0a  mov     [rsp+3B0h+var_350], ebx
0x18001ff0e  mov     dword ptr [rbp+2B0h+var_300+4], ebx
0x18001ff11  mov     [rbp+2B0h+hMem], rdi
0x18001ff15  call    cs:__imp_AcquireSRWLockShared
0x18001ff1b  lea     rax, [rbp+2B0h+var_248]
0x18001ff1f  mov     [rsp+3B0h+var_344], ebx
0x18001ff23  mov     [rsp+3B0h+var_378], rax; int *
0x18001ff28  lea     rcx, [rbp+2B0h+var_288]; phkResult
0x18001ff2c  mov     rax, [rsp+3B0h+var_338]
0x18001ff31  xor     r9d, r9d; unsigned int
0x18001ff34  mov     [rsp+3B0h+var_380], rsi; struct _FILETIME *
0x18001ff39  mov     r8, r14; HKEY
0x18001ff3c  mov     rdx, r13; hKey
0x18001ff3f  mov     qword ptr [rsp+3B0h+cchCount2], rax; lpValueName
0x18001ff44  call    ?Init@CRegBlob@@QEAAKPEAUHKEY__@@0KPEBGPEBDPEAU_FILETIME@@PEAH@Z; CRegBlob::Init(HKEY__ *,HKEY__ *,ulong,ushort const *,char const *,_FILETIME *,int *)
0x18001ff49  cmp     eax, 8
0x18001ff4c  jz      loc_1800206AA
0x18001ff52  mov     ecx, [rbp+2B0h+var_248]
0x18001ff55  test    ecx, ecx
0x18001ff57  jnz     loc_180020686
0x18001ff5d  test    eax, eax
0x18001ff5f  jnz     short loc_18001FF91
0x18001ff61  cmp     [rbp+2B0h+var_280], eax
0x18001ff64  jnz     short loc_18001FF91
0x18001ff66  mov     r14d, [rbp+2B0h+var_274]
0x18001ff6a  mov     esi, r14d
0x18001ff6d  mov     ebx, [rbp+2B0h+cbData]
0x18001ff70  sub     esi, ebx
0x18001ff72  cmp     esi, 4
0x18001ff75  ja      loc_180020017
0x18001ff7b  test    esi, esi
0x18001ff7d  jnz     loc_18002001C
0x18001ff83  mov     r14, [rsp+3B0h+var_340]
0x18001ff88  mov     ebx, 1
0x18001ff8d  mov     rsi, [rbp+2B0h+var_328]
0x18001ff91  lea     rcx, ?g_srwProxyReg@@3VWxSrw@@A; SRWLock
0x18001ff98  call    cs:__imp_ReleaseSRWLockShared
0x18001ff9e  cmp     [rsp+3B0h+var_348], 0
0x18001ffa3  mov     [rsp+3B0h+var_344], 0
0x18001ffab  jz      loc_180020B6F
0x18001ffb1  or      dword ptr [rbp+2B0h+var_300+4], 8
0x18001ffb5  test    r12, r12
0x18001ffb8  jz      loc_18002033D
0x18001ffbe  mov     [r12], ebx
0x18001ffc2  jmp     loc_18002033D
0x18001ffc7  cmp     [rdi], r13b
0x18001ffca  jz      loc_18001FE36
0x18001ffd0  lea     rax, aDefaultconnect_0; "DefaultConnectionSettings"
0x18001ffd7  mov     [rsp+3B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001ffdf  mov     ebx, 1
0x18001ffe4  mov     [rsp+3B0h+var_348], r13d
0x18001ffe9  mov     edx, ebx; dwCmpFlags
0x18001ffeb  mov     [rsp+3B0h+var_338], rdi
0x18001fff0  mov     r9d, 0FFFFFFFFh; cchCount1
0x18001fff6  mov     [rsp+3B0h+phkResult], rax; lpString2
0x18001fffb  mov     r8, rdi; lpString1
0x18001fffe  mov     ecx, 7Fh; Locale
0x180020003  call    cs:__imp_CompareStringA
0x180020009  cmp     eax, 2
0x18002000c  jz      loc_18001FE47
0x180020012  jmp     loc_18001FE4B
0x180020017  mov     esi, 4
0x18002001c  mov     rdx, rbx
0x18002001f  mov     r8d, esi; Size
0x180020022  add     rdx, [rbp+2B0h+lpMem]; Src
0x180020026  lea     rcx, [rbp+2B0h+var_250]; void *
0x18002002a  call    memcpy_0
0x18002002f  add     ebx, esi
0x180020031  cmp     [rbp+2B0h+var_250], 3Ch ; '<'
0x180020035  mov     [rbp+2B0h+cbData], ebx
0x180020038  jb      loc_18001FF83
0x18002003e  mov     edi, r14d
0x180020041  mov     r12d, 4
0x180020047  sub     edi, ebx
0x180020049  cmp     edi, r12d
0x18002004c  ja      loc_180020599
0x180020052  test    edi, edi
0x180020054  jz      short loc_18002006D
0x180020056  mov     edx, ebx
0x180020058  lea     rcx, [rbp+2B0h+var_300+8]; void *
0x18002005c  add     rdx, [rbp+2B0h+lpMem]; Src
0x180020060  mov     r8d, edi; Size
0x180020063  call    memcpy_0
0x180020068  add     ebx, edi
0x18002006a  mov     [rbp+2B0h+cbData], ebx
0x18002006d  mov     edi, r14d
0x180020070  sub     edi, ebx
0x180020072  cmp     edi, 4
0x180020075  ja      loc_1800205A1
0x18002007b  test    edi, edi
0x18002007d  jz      short loc_180020096
0x18002007f  mov     edx, ebx
0x180020081  lea     rcx, [rbp+2B0h+var_300+4]; void *
0x180020085  add     rdx, [rbp+2B0h+lpMem]; Src
0x180020089  mov     r8d, edi; Size
0x18002008c  call    memcpy_0
0x180020091  add     ebx, edi
0x180020093  mov     [rbp+2B0h+cbData], ebx
0x180020096  xor     esi, esi
0x180020098  mov     edi, r14d
0x18002009b  sub     edi, ebx
0x18002009d  mov     [rbp+2B0h+var_310], esi
0x1800200a0  xor     r15d, r15d
0x1800200a3  cmp     edi, 4
0x1800200a6  ja      loc_1800205A9
0x1800200ac  test    edi, edi
0x1800200ae  jz      short loc_1800200CA
0x1800200b0  mov     edx, ebx
0x1800200b2  lea     rcx, [rbp+2B0h+var_310]; void *
0x1800200b6  add     rdx, [rbp+2B0h+lpMem]; Src
0x1800200ba  mov     r8d, edi; Size
0x1800200bd  call    memcpy_0
0x1800200c2  mov     esi, [rbp+2B0h+var_310]
0x1800200c5  add     ebx, edi
0x1800200c7  mov     [rbp+2B0h+cbData], ebx
0x1800200ca  cmp     edi, 4
0x1800200cd  jnz     short loc_1800200DB
0x1800200cf  lea     eax, [rsi-1]
0x1800200d2  cmp     eax, 0FFFFFFFDh
0x1800200d5  jbe     loc_180020712
0x1800200db  xor     esi, esi
0x1800200dd  mov     [rbp+2B0h+hMem+8], r15
0x1800200e1  xor     r15d, r15d
0x1800200e4  mov     [rbp+2B0h+var_310], esi
0x1800200e7  cmp     [rbp+2B0h+var_280], esi
0x1800200ea  jnz     short loc_180020129
0x1800200ec  mov     edi, r14d
0x1800200ef  sub     edi, ebx
0x1800200f1  cmp     edi, 4
0x1800200f4  ja      loc_1800205B1
0x1800200fa  test    edi, edi
0x1800200fc  jz      short loc_180020118
0x1800200fe  mov     edx, ebx
0x180020100  lea     rcx, [rbp+2B0h+var_310]; void *
0x180020104  add     rdx, [rbp+2B0h+lpMem]; Src
0x180020108  mov     r8d, edi; Size
0x18002010b  call    memcpy_0
0x180020110  mov     esi, [rbp+2B0h+var_310]
0x180020113  add     ebx, edi
0x180020115  mov     [rbp+2B0h+cbData], ebx
0x180020118  cmp     edi, 4
0x18002011b  jnz     short loc_180020129
0x18002011d  lea     eax, [rsi-1]
0x180020120  cmp     eax, 0FFFFFFFDh
0x180020123  jbe     loc_180020768
0x180020129  xor     esi, esi
0x18002012b  mov     [rbp+2B0h+var_2E0], r15
0x18002012f  xor     r15d, r15d
0x180020132  mov     [rbp+2B0h+var_310], esi
0x180020135  cmp     [rbp+2B0h+var_280], esi
0x180020138  jnz     short loc_180020177
0x18002013a  mov     edi, r14d
0x18002013d  sub     edi, ebx
0x18002013f  cmp     edi, 4
0x180020142  ja      loc_1800205B9
0x180020148  test    edi, edi
0x18002014a  jz      short loc_180020166
0x18002014c  mov     edx, ebx
0x18002014e  lea     rcx, [rbp+2B0h+var_310]; void *
0x180020152  add     rdx, [rbp+2B0h+lpMem]; Src
0x180020156  mov     r8d, edi; Size
0x180020159  call    memcpy_0
0x18002015e  mov     esi, [rbp+2B0h+var_310]
0x180020161  add     ebx, edi
0x180020163  mov     [rbp+2B0h+cbData], ebx
0x180020166  cmp     edi, 4
0x180020169  jnz     short loc_180020177
0x18002016b  lea     eax, [rsi-1]
0x18002016e  cmp     eax, 0FFFFFFFDh
0x180020171  jbe     loc_1800207BE
0x180020177  cmp     [rbp+2B0h+var_280], 0
0x18002017b  mov     [rbp+2B0h+var_2E0+8], r15
0x18002017f  jnz     short loc_1800201AA
0x180020181  mov     edi, r14d
0x180020184  sub     edi, ebx
0x180020186  cmp     edi, 4
0x180020189  ja      loc_1800205C1
0x18002018f  test    edi, edi
0x180020191  jz      short loc_1800201AA
0x180020193  mov     edx, ebx
0x180020195  lea     rcx, [rbp+2B0h+var_2D0+8]; void *
0x180020199  add     rdx, [rbp+2B0h+lpMem]; Src
0x18002019d  mov     r8d, edi; Size
0x1800201a0  call    memcpy_0
0x1800201a5  add     ebx, edi
0x1800201a7  mov     [rbp+2B0h+cbData], ebx
0x1800201aa  xor     esi, esi
0x1800201ac  xor     r15d, r15d
  ... truncated ...
```
