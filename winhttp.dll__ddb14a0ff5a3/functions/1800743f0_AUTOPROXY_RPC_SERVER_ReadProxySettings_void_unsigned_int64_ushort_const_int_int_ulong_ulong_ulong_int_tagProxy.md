# AUTOPROXY_RPC_SERVER::ReadProxySettings(void *,unsigned __int64,ushort const *,int,int,ulong,ulong *,ulong *,int *,tagProxySettings *)

- ea: `0x1800743f0`
- end: `0x180074e79`
- name: `?ReadProxySettings@AUTOPROXY_RPC_SERVER@@AEAAJPEAX_KPEBGHHKPEAK3PEAHPEAUtagProxySettings@@@Z`
- size: `2697`
- prototype: `__int64 __fastcall(AUTOPROXY_RPC_SERVER *__hidden this, void *, unsigned __int64, const unsigned __int16 *, int, int, unsigned int, unsigned int *, unsigned int *, int *, struct tagProxySettings *)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800741d0`
- `0x1800accd8`

## callees

- `0x180005670`
- `0x180006084`
- `0x180007cb0`
- `0x1800082a4`
- `0x180019e58`
- `0x18001e960`
- `0x18001fd20`
- `0x180069be0`
- `0x1800743f0`
- `0x180076b44`
- `0x180097bf0`
- `0x1800a1d10`
- `0x1800c9134`
- `0x1800cdd7c`
- `0x1800cf008`
- `0x1800cfc0c`
- `0x1800cfca8`
- `0x1800d02bc`
- `0x1800d2358`
- `0x1800db6b0`
- `0x1800dd854`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074ced`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074d1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074d4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074d80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074db5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074dea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074e1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074e4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074ced`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074d1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074d4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074d80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074db5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074dea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074e1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074e4c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180074892`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180074892`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180074669`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800747aa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180074669`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800747aa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180074ca0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180074ca0`
- `RPCRT4!RpcImpersonateClient` at `0x1800745dd`
- `RPCRT4!RpcImpersonateClient` at `0x1800745dd`
- `RPCRT4!RpcRevertToSelf` at `0x180074c62`
- `RPCRT4!RpcRevertToSelf` at `0x180074c62`

## pseudocode

```c
__int64 __fastcall AUTOPROXY_RPC_SERVER::ReadProxySettings(
        AUTOPROXY_RPC_SERVER *this,
        void *a2,
        size_t a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int *a8,
        unsigned int *a9,
        int *a10,
        struct tagProxySettings *a11)
{
  void *v11; // r14
  void *v12; // r12
  void *v13; // r13
  void *v14; // r15
  void *v15; // rsi
  void *v16; // rdi
  CHAR *v17; // rbx
  int v18; // edx
  int v19; // ecx
  struct tagProxySettings *v20; // rax
  CRpcWatchDog *v21; // rcx
  int *v22; // rdx
  __int64 v23; // rcx
  unsigned int *v24; // rax
  RPC_STATUS v25; // eax
  bool v26; // sf
  int v27; // edx
  int v28; // ecx
  int v29; // r8d
  int v30; // ecx
  int v31; // r8d
  __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // rdx
  struct tagProxySettings *v35; // rax
  int ProxySettings; // eax
  int v37; // eax
  bool v38; // sf
  int v39; // ecx
  int v40; // r8d
  int ConnectionNameInternal; // eax
  __int64 v42; // rax
  int WinInetProxySettings; // eax
  signed int v44; // ecx
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // edx
  size_t v50; // rax
  int v51; // ecx
  size_t v52; // rax
  struct tagProxySettings *v53; // r8
  LPVOID v54; // rax
  int v56[2]; // [rsp+20h] [rbp-E0h]
  signed int BindingHandlea; // [rsp+70h] [rbp-90h]
  unsigned int v59; // [rsp+78h] [rbp-88h]
  LPCWCH lpWideCharStr; // [rsp+80h] [rbp-80h] BYREF
  LPCCH lpMultiByteStr; // [rsp+88h] [rbp-78h]
  size_t Size; // [rsp+90h] [rbp-70h]
  LPVOID lpMem; // [rsp+98h] [rbp-68h]
  LPVOID v64; // [rsp+A0h] [rbp-60h]
  struct tagProxySettings *v65; // [rsp+A8h] [rbp-58h]
  int *v66; // [rsp+B0h] [rbp-50h]
  unsigned int *v67; // [rsp+B8h] [rbp-48h]
  unsigned int *v68; // [rsp+C0h] [rbp-40h]
  AUTOPROXY_RPC_SERVER *v69; // [rsp+C8h] [rbp-38h]
  void *v70; // [rsp+D0h] [rbp-30h]
  void *v71; // [rsp+D8h] [rbp-28h]
  void *v72; // [rsp+E0h] [rbp-20h]
  void *v73; // [rsp+E8h] [rbp-18h]
  void *v74; // [rsp+F0h] [rbp-10h]
  void *v75; // [rsp+F8h] [rbp-8h]
  void *v76; // [rsp+100h] [rbp+0h]
  void *v77; // [rsp+108h] [rbp+8h]
  __int128 v78; // [rsp+110h] [rbp+10h] BYREF
  LPCCH v79[2]; // [rsp+120h] [rbp+20h]
  LPCCH v80[2]; // [rsp+130h] [rbp+30h]
  LPCCH v81[2]; // [rsp+140h] [rbp+40h]
  LPCCH v82[4]; // [rsp+150h] [rbp+50h] BYREF
  void *v83[2]; // [rsp+170h] [rbp+70h]
  LARGE_INTEGER v84; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v85; // [rsp+188h] [rbp+88h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v87[32]; // [rsp+198h] [rbp+98h] BYREF

  v69 = this;
  v67 = a9;
  v11 = 0;
  v12 = 0;
  v68 = a8;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v70 = 0;
  v16 = 0;
  v74 = 0;
  v17 = 0;
  v64 = 0;
  v75 = 0;
  lpMem = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v76 = 0;
  v77 = 0;
  lpMultiByteStr = 0;
  PerformanceCount.LowPart = 0;
  v84.QuadPart = 0;
  lpWideCharStr = a4;
  Size = a3;
  v65 = a11;
  v66 = a10;
  v78 = 0;
  *(_OWORD *)v79 = 0;
  *(_OWORD *)v80 = 0;
  *(_OWORD *)v81 = 0;
  memset(v82, 0, sizeof(v82));
  *(_OWORD *)v83 = 0;
  AutoRpcWatchDog::AutoRpcWatchDog((AutoRpcWatchDog *)v87);
  v85 = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qSDD(v19, v18, 0, (_DWORD)a2, (__int64)lpWideCharStr, a5, a6);
  v20 = v65;
  if ( !v65 )
  {
    BindingHandlea = -2147024809;
    v84.HighPart = 1946;
    v79[0] = 0;
    CleanWinInetProxyStruct((struct WININET_PROXY_INFO_EX *)&v78);
    goto LABEL_97;
  }
  v22 = v66;
  if ( !v66 )
  {
    v84.HighPart = 1947;
    BindingHandlea = -2147024809;
    v79[0] = 0;
    CleanWinInetProxyStruct((struct WININET_PROXY_INFO_EX *)&v78);
    goto LABEL_97;
  }
  if ( v68 )
    *v68 = 0;
  v23 = 112;
  do
  {
    *(_BYTE *)v20 = 0;
    v20 = (struct tagProxySettings *)((char *)v20 + 1);
    --v23;
  }
  while ( v23 );
  v24 = v67;
  *v22 = 0;
  if ( v24 )
    *v24 = 0;
  if ( !*((_DWORD *)v69 + 21) )
  {
    BindingHandlea = -2146685199;
    v84.HighPart = 1955;
    v79[0] = 0;
    CleanWinInetProxyStruct((struct WININET_PROXY_INFO_EX *)&v78);
    goto LABEL_97;
  }
  v25 = RpcImpersonateClient(a2);
  BindingHandlea = v25;
  v26 = v25 < 0;
  if ( v25 > 0 )
  {
    BindingHandlea = (unsigned __int16)v25 | 0x80070000;
    v26 = 1;
  }
  if ( v26 )
  {
    v84.HighPart = 1961;
    v79[0] = 0;
    CleanWinInetProxyStruct((struct WININET_PROXY_INFO_EX *)&v78);
    goto LABEL_97;
  }
  if ( (unsigned int)AUTOPROXY_RPC_SERVER::IsHvsiContainer(v69) )
  {
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_(1029, 81, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids);
    v30 = 0;
    HIDWORD(v68) = 0;
    PerformanceCount.QuadPart = 0;
    v84.QuadPart = 0;
    if ( !g_fKirHttpBugFix26Q2 )
      QueryPerformanceCounter(&PerformanceCount);
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_Sll(v30, v27, v29, (_DWORD)lpWideCharStr, a5, a6);
    v31 = (int)v67;
    if ( v67 )
      *v67 = 0;
    v32 = (__int64)v66;
    v33 = 112;
    v34 = (__int64)v65;
    v35 = v65;
    *v66 = 0;
    do
    {
      *(_BYTE *)v35 = 0;
      v35 = (struct tagProxySettings *)((char *)v35 + 1);
      --v33;
    }
    while ( v33 );
    ProxySettings = HvsiWinHttpReadProxySettings((_DWORD)lpWideCharStr, a5, a6, v31, v32, v34);
    BindingHandlea = ProxySettings;
    if ( ProxySettings >= 0 )
    {
      if ( (xmmword_180107A60 & 0x20) == 0 )
      {
LABEL_36:
        if ( !g_fKirHttpBugFix26Q2 )
        {
          QueryPerformanceCounter(&v84);
          WinHttpLogCallDuration(v84.QuadPart - PerformanceCount.QuadPart, 2, (unsigned int)BindingHandlea);
        }
        if ( BindingHandlea >= 0 )
          BindingHandlea = 0;
        else
          v84.HighPart = 1975;
        v79[0] = 0;
        goto LABEL_96;
      }
      WPP_SF_DlSSDDDSSSS(
        (_DWORD)v67,
        171,
        (unsigned int)WPP_641a94d440413893505b2c7b2413b0bb_Traceguids,
        *v67,
        *v66,
        (__int64)lpWideCharStr,
        *((_QWORD *)v65 + 2),
        *((_DWORD *)v65 + 2),
        *((_DWORD *)v65 + 1),
        *((_DWORD *)v65 + 14),
        *((_QWORD *)v65 + 3),
        *((_QWORD *)v65 + 4),
        *((_QWORD *)v65 + 5),
        *((_QWORD *)v65 + 6));
      ProxySettings = BindingHandlea;
    }
    else
    {
      HIDWORD(v68) = 5151;
    }
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 172, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)ProxySettings, *(_QWORD *)v56);
    goto LABEL_36;
  }
  if ( lpWideCharStr )
  {
    v37 = WxNewStringWtoACchCp<WxGlobalAllocator>(lpWideCharStr);
    BindingHandlea = v37;
    v38 = v37 < 0;
    if ( v37 > 0 )
    {
      BindingHandlea = (unsigned __int16)v37 | 0x80070000;
      v38 = 1;
    }
    if ( v38 )
    {
      v79[0] = 0;
      v17 = (CHAR *)lpMultiByteStr;
      v84.HighPart = 1982;
      goto LABEL_96;
    }
    v17 = (CHAR *)lpMultiByteStr;
  }
  else
  {
    HIDWORD(lpMultiByteStr) = 0;
    lpWideCharStr = 0;
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_iDq(v28, 35, v29, Size, a7, (__int64)&v85);
    v85 = 0;
    if ( InitOnceExecuteOnce(&g_fUseActiveIfForProxyConfigOverrideInit, UseActiveIfForProxyConfigInitOnce, 0, 0) )
    {
      ConnectionNameInternal = GetConnectionNameInternal(Size, a7, &v85, (char **)&lpWideCharStr);
      if ( ConnectionNameInternal < 0 )
        HIDWORD(lpMultiByteStr) = 2207;
      v17 = (CHAR *)lpWideCharStr;
    }
    else
    {
      ConnectionNameInternal = -2147467259;
      HIDWORD(lpMultiByteStr) = 2202;
    }
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_ds(v39, 36, v40, ConnectionNameInternal, (__int64)v17);
  }
  LODWORD(v78) = 112;
  v42 = *((_QWORD *)v69 + 37);
  v79[0] = v17;
  WinInetProxySettings = ReadWinInetProxySettings(
                           0,
                           0,
                           0,
                           a5,
                           a6,
                           (unsigned int **)(v42 + 8),
                           (unsigned int *)&v84,
                           (int *)&PerformanceCount,
                           (struct WININET_PROXY_INFO_EX *)&v78);
  BindingHandlea = WinInetProxySettings;
  v44 = WinInetProxySettings;
  if ( WinInetProxySettings > 0 )
  {
    v44 = (unsigned __int16)WinInetProxySettings | 0x80070000;
    BindingHandlea = v44;
  }
  if ( v44 >= 0 )
  {
    if ( v17 && (v45 = WxNewStringAtoWCch<WxHeapAllocator>(v17, -1), v11 = v70, BindingHandlea = v45, v45 < 0) )
    {
      v84.HighPart = 2006;
      v79[0] = 0;
    }
    else
    {
      v59 = DWORD1(v78);
      if ( v80[1] && (BindingHandlea = WxNewStringAtoWCch<WxHeapAllocator>(v80[1], -1), lpMem = v71, BindingHandlea < 0) )
      {
        v84.HighPart = 2013;
        v79[0] = 0;
      }
      else if ( v81[0]
             && (v46 = WxNewStringAtoWCch<WxHeapAllocator>(v81[0], -1), v13 = v72, BindingHandlea = v46, v46 < 0) )
      {
        v84.HighPart = 2018;
        v79[0] = 0;
      }
      else if ( v82[0]
             && (v47 = WxNewStringAtoWCch<WxHeapAllocator>(v82[0], -1), v14 = v73, BindingHandlea = v47, v47 < 0) )
      {
        v84.HighPart = 2023;
        v79[0] = 0;
      }
      else if ( v79[1]
             && (v48 = WxNewStringAtoWCch<WxHeapAllocator>(v79[1], -1), v12 = v74, BindingHandlea = v48, v48 < 0) )
      {
        v84.HighPart = 2028;
        v79[0] = 0;
      }
      else
      {
        if ( !v80[0]
          || (BindingHandlea = WxNewStringAtoWCch<WxHeapAllocator>(v80[0], -1), v64 = v75, BindingHandlea >= 0) )
        {
          v49 = HIDWORD(v82[2]);
          if ( HIDWORD(v82[2]) )
          {
            v50 = 4LL * HIDWORD(v82[2]);
            Size = v50;
            if ( v50 > 0xFFFFFFFF )
            {
              BindingHandlea = -2147024362;
              v84.HighPart = 2038;
              v79[0] = 0;
              goto LABEL_96;
            }
            BindingHandlea = WxAllocZero<_ProxyNetworkKey,WxHeapAllocator>((unsigned int)v50);
            if ( BindingHandlea < 0 )
            {
              v79[0] = 0;
              v15 = v76;
              v84.HighPart = 2041;
              goto LABEL_96;
            }
            v15 = v76;
            memcpy_0(v76, v82[3], (unsigned int)Size);
            v49 = HIDWORD(v82[2]);
          }
          v51 = (int)v83[0];
          if ( LODWORD(v83[0]) )
          {
            v52 = (unsigned __int64)LODWORD(v83[0]) << 7;
            Size = v52;
            if ( v52 > 0xFFFFFFFF )
            {
              v84.HighPart = 2052;
              BindingHandlea = -2147024362;
              v79[0] = 0;
              goto LABEL_96;
            }
            BindingHandlea = WxAllocZero<_ProxyNetworkKey,WxHeapAllocator>((unsigned int)v52);
            if ( BindingHandlea < 0 )
            {
              v79[0] = 0;
              v16 = v77;
              v84.HighPart = 2055;
              goto LABEL_96;
            }
            v16 = v77;
            memcpy_0(v77, v83[1], (unsigned int)Size);
            v51 = (int)v83[0];
            v49 = HIDWORD(v82[2]);
          }
          v53 = v65;
          *((_DWORD *)v65 + 1) = v59;
          *((_DWORD *)v53 + 14) = v81[1];
          *((_DWORD *)v53 + 2) = DWORD2(v78);
          *(LPCCH *)((char *)v53 + 76) = *(LPCCH *)((char *)&v82[1] + 4);
          *((_DWORD *)v53 + 18) = v82[1];
          *((_QWORD *)v53 + 4) = v64;
          v54 = lpMem;
          *((_QWORD *)v53 + 2) = v11;
          v11 = 0;
          *((_QWORD *)v53 + 3) = v12;
          v12 = 0;
          *((_QWORD *)v53 + 6) = v13;
          v13 = 0;
          *((_QWORD *)v53 + 8) = v14;
          v14 = 0;
          *((_QWORD *)v53 + 5) = v54;
          *(_DWORD *)v53 = 112;
          v64 = 0;
          lpMem = 0;
          *((_DWORD *)v53 + 21) = v49;
          if ( v49 )
          {
            *((_QWORD *)v53 + 11) = v15;
            v15 = 0;
          }
          *((_DWORD *)v53 + 24) = v51;
          if ( v51 )
          {
            *((_QWORD *)v53 + 13) = v16;
            v16 = 0;
          }
          v79[0] = 0;
          *v66 = PerformanceCount.LowPart;
          *v67 = v84.LowPart;
          if ( v68 )
            *v68 = v85;
          goto LABEL_96;
        }
        v84.HighPart = 2033;
        v79[0] = 0;
      }
    }
  }
  else
  {
    v84.HighPart = 2002;
    v79[0] = 0;
  }
LABEL_96:
  CleanWinInetProxyStruct((struct WININET_PROXY_INFO_EX *)&v78);
  RpcRevertToSelf();
LABEL_97:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 82, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)BindingHandlea, *(_QWORD *)v56);
  CRpcWatchDog::RemoveEntry(v21, (struct _WatchDogEntry *)v87);
  if ( v17 )
    GlobalFree(v17);
  if ( v16 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v16);
    else
      HeapFree(g_hWxProcessHeap, 0, v16);
  }
  if ( v15 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v15);
    else
      HeapFree(g_hWxProcessHeap, 0, v15);
  }
  if ( v14 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v14);
    else
      HeapFree(g_hWxProcessHeap, 0, v14);
  }
  if ( v13 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v13);
    else
      HeapFree(g_hWxProcessHeap, 0, v13);
  }
  if ( lpMem )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(lpMem);
    else
      HeapFree(g_hWxProcessHeap, 0, lpMem);
  }
  if ( v64 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v64);
    else
      HeapFree(g_hWxProcessHeap, 0, v64);
  }
  if ( v12 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v12);
    else
      HeapFree(g_hWxProcessHeap, 0, v12);
  }
  if ( v11 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(v11);
    else
      HeapFree(g_hWxProcessHeap, 0, v11);
  }
  return (unsigned int)BindingHandlea;
}

```

## disassembly

```asm
0x1800743f0  push    rbp
0x1800743f2  push    rbx
0x1800743f3  push    rsi
0x1800743f4  push    rdi
0x1800743f5  push    r12
0x1800743f7  push    r13
0x1800743f9  push    r14
0x1800743fb  push    r15
0x1800743fd  lea     rbp, [rsp-0C8h]
0x180074405  sub     rsp, 1C8h
0x18007440c  mov     rax, cs:__security_cookie
0x180074413  xor     rax, rsp
0x180074416  mov     [rbp+100h+var_48], rax
0x18007441d  mov     eax, [rbp+100h+arg_30]
0x180074423  xorps   xmm0, xmm0
0x180074426  mov     [rbp+100h+var_138], rcx
0x18007442a  mov     rcx, [rbp+100h+arg_40]
0x180074431  mov     [rsp+200h+var_188], eax
0x180074435  mov     rax, [rbp+100h+arg_38]
0x18007443c  mov     [rbp+100h+var_148], rcx
0x180074440  xor     ecx, ecx
0x180074442  mov     [rsp+200h+BindingHandle], rdx
0x180074447  mov     r14d, ecx
0x18007444a  mov     rdx, [rbp+100h+arg_50]
0x180074451  mov     r12d, ecx
0x180074454  mov     [rbp+100h+var_140], rax
0x180074458  mov     r13d, ecx
0x18007445b  mov     rax, [rbp+100h+arg_48]
0x180074462  mov     r15d, ecx
0x180074465  mov     dword ptr [rbp+100h+var_80+4], ecx
0x18007446b  mov     esi, ecx
0x18007446d  mov     [rbp+100h+var_130], rcx
0x180074471  mov     edi, ecx
0x180074473  mov     [rbp+100h+var_110], rcx
0x180074477  mov     ebx, ecx
0x180074479  mov     [rbp+100h+var_160], rcx
0x18007447d  mov     [rbp+100h+var_108], rcx
0x180074481  mov     [rbp+100h+lpMem], rcx
0x180074485  mov     [rbp+100h+var_128], rcx
0x180074489  mov     [rbp+100h+var_120], rcx
0x18007448d  mov     [rbp+100h+var_118], rcx
0x180074491  mov     [rbp+100h+var_100], rcx
0x180074495  mov     [rbp+100h+var_F8], rcx
0x180074499  mov     [rbp+100h+lpMultiByteStr], rcx
0x18007449d  mov     dword ptr [rbp+100h+PerformanceCount], ecx
0x1800744a3  mov     dword ptr [rbp+100h+var_80], ecx
0x1800744a9  lea     rcx, [rbp+100h+var_68]; this
0x1800744b0  mov     [rbp+100h+lpWideCharStr], r9
0x1800744b4  mov     [rbp+100h+Size], r8
0x1800744b8  mov     [rbp+100h+var_158], rdx
0x1800744bc  mov     [rbp+100h+var_150], rax
0x1800744c0  movups  [rbp+100h+var_F0], xmm0
0x1800744c4  movups  xmmword ptr [rbp+100h+var_E0], xmm0
0x1800744c8  movups  xmmword ptr [rbp+100h+var_D0], xmm0
0x1800744cc  movups  xmmword ptr [rbp+100h+var_C0], xmm0
0x1800744d0  movups  xmmword ptr [rbp+100h+var_B0], xmm0
0x1800744d4  movups  xmmword ptr [rbp+100h+Src], xmm0
0x1800744d8  movups  xmmword ptr [rbp+100h+var_90], xmm0
0x1800744dc  call    ??0AutoRpcWatchDog@@QEAA@XZ; AutoRpcWatchDog::AutoRpcWatchDog(void)
0x1800744e1  xor     r8d, r8d
0x1800744e4  mov     [rbp+100h+var_78], r8d
0x1800744eb  test    byte ptr cs:xmmword_180107A60, 20h
0x1800744f2  jz      short loc_18007451E
0x1800744f4  mov     eax, [rbp+100h+arg_28]
0x1800744fa  mov     r9, [rsp+200h+BindingHandle]
0x1800744ff  mov     dword ptr [rsp+200h+var_1D0], eax
0x180074503  mov     eax, [rbp+100h+arg_20]
0x180074509  mov     dword ptr [rsp+200h+var_1D8], eax
0x18007450d  mov     rax, [rbp+100h+lpWideCharStr]
0x180074511  mov     qword ptr [rsp+200h+var_1E0], rax
0x180074516  call    WPP_SF_qSDD
0x18007451b  xor     r8d, r8d
0x18007451e  mov     rax, [rbp+100h+var_158]
0x180074522  test    rax, rax
0x180074525  jnz     short loc_18007454B
0x180074527  lea     rcx, [rbp+100h+var_F0]; struct WININET_PROXY_INFO_EX *
0x18007452b  mov     dword ptr [rsp+200h+BindingHandle], 80070057h
0x180074533  mov     dword ptr [rbp+100h+var_80+4], 79Ah
0x18007453d  mov     [rbp+100h+var_E0], r8
0x180074541  call    ?CleanWinInetProxyStruct@@YAXPEAUWININET_PROXY_INFO_EX@@@Z; CleanWinInetProxyStruct(WININET_PROXY_INFO_EX *)
0x180074546  jmp     loc_180074C68
0x18007454b  mov     rdx, [rbp+100h+var_150]
0x18007454f  test    rdx, rdx
0x180074552  jnz     short loc_180074579
0x180074554  mov     eax, 80070057h
0x180074559  mov     dword ptr [rbp+100h+var_80+4], 79Bh
0x180074563  lea     rcx, [rbp+100h+var_F0]; struct WININET_PROXY_INFO_EX *
0x180074567  mov     dword ptr [rsp+200h+BindingHandle], eax
0x18007456b  mov     [rbp+100h+var_E0], r8
0x18007456f  call    ?CleanWinInetProxyStruct@@YAXPEAUWININET_PROXY_INFO_EX@@@Z; CleanWinInetProxyStruct(WININET_PROXY_INFO_EX *)
0x180074574  jmp     loc_180074C68
0x180074579  mov     rcx, [rbp+100h+var_140]
0x18007457d  test    rcx, rcx
0x180074580  jz      short loc_180074585
0x180074582  mov     [rcx], r8d
0x180074585  mov     ecx, 70h ; 'p'
0x18007458a  nop     word ptr [rax+rax+00h]
0x180074590  mov     [rax], bl
0x180074592  lea     rax, [rax+1]
0x180074596  sub     rcx, 1
0x18007459a  jnz     short loc_180074590
0x18007459c  mov     rax, [rbp+100h+var_148]
0x1800745a0  mov     [rdx], r8d
0x1800745a3  test    rax, rax
0x1800745a6  jz      short loc_1800745AB
0x1800745a8  mov     [rax], r8d
0x1800745ab  mov     rax, [rbp+100h+var_138]
0x1800745af  cmp     [rax+54h], ebx
0x1800745b2  jnz     short loc_1800745D8
0x1800745b4  lea     rcx, [rbp+100h+var_F0]; struct WININET_PROXY_INFO_EX *
0x1800745b8  mov     dword ptr [rsp+200h+BindingHandle], 800C2EF1h
0x1800745c0  mov     dword ptr [rbp+100h+var_80+4], 7A3h
0x1800745ca  mov     [rbp+100h+var_E0], r8
0x1800745ce  call    ?CleanWinInetProxyStruct@@YAXPEAUWININET_PROXY_INFO_EX@@@Z; CleanWinInetProxyStruct(WININET_PROXY_INFO_EX *)
0x1800745d3  jmp     loc_180074C68
0x1800745d8  mov     rcx, [rsp+200h+BindingHandle]; BindingHandle
0x1800745dd  call    cs:__imp_RpcImpersonateClient
0x1800745e3  mov     dword ptr [rsp+200h+BindingHandle], eax
0x1800745e7  test    eax, eax
0x1800745e9  jle     short loc_1800745F9
0x1800745eb  movzx   eax, ax
0x1800745ee  or      eax, 80070000h
0x1800745f3  mov     dword ptr [rsp+200h+BindingHandle], eax
0x1800745f7  test    eax, eax
0x1800745f9  jns     short loc_180074617
0x1800745fb  lea     rcx, [rbp+100h+var_F0]; struct WININET_PROXY_INFO_EX *
0x1800745ff  mov     dword ptr [rbp+100h+var_80+4], 7A9h
0x180074609  mov     [rbp+100h+var_E0], rbx
0x18007460d  call    ?CleanWinInetProxyStruct@@YAXPEAUWININET_PROXY_INFO_EX@@@Z; CleanWinInetProxyStruct(WININET_PROXY_INFO_EX *)
0x180074612  jmp     loc_180074C68
0x180074617  mov     rcx, [rbp+100h+var_138]; this
0x18007461b  call    ?IsHvsiContainer@AUTOPROXY_RPC_SERVER@@QEAAHXZ; AUTOPROXY_RPC_SERVER::IsHvsiContainer(void)
0x180074620  test    eax, eax
0x180074622  jz      loc_1800747F9
0x180074628  test    byte ptr cs:xmmword_180107A60, 20h
0x18007462f  jz      short loc_180074647
0x180074631  mov     edx, 51h ; 'Q'
0x180074636  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18007463d  mov     ecx, 405h
0x180074642  call    WPP_SF_
0x180074647  xor     ecx, ecx
0x180074649  cmp     cs:g_fKirHttpBugFix26Q2, cl
0x18007464f  mov     dword ptr [rbp+100h+var_140+4], ecx
0x180074652  mov     qword ptr [rbp+100h+PerformanceCount], rcx
0x180074659  mov     qword ptr [rbp+100h+var_80], rcx
0x180074660  jnz     short loc_18007466F
0x180074662  lea     rcx, [rbp+100h+PerformanceCount]; lpPerformanceCount
0x180074669  call    cs:__imp_QueryPerformanceCounter
0x18007466f  test    byte ptr cs:xmmword_180107A60, 20h
0x180074676  jz      short loc_180074695
0x180074678  mov     eax, [rbp+100h+arg_28]
0x18007467e  mov     r9, [rbp+100h+lpWideCharStr]
0x180074682  mov     dword ptr [rsp+200h+var_1D8], eax
0x180074686  mov     eax, [rbp+100h+arg_20]
0x18007468c  mov     [rsp+200h+var_1E0], eax
0x180074690  call    WPP_SF_Sll
0x180074695  mov     r8, [rbp+100h+var_148]
0x180074699  test    r8, r8
0x18007469c  jz      short loc_1800746A1
0x18007469e  mov     [r8], ebx
0x1800746a1  mov     r9, [rbp+100h+var_150]
0x1800746a5  mov     ecx, 70h ; 'p'
0x1800746aa  mov     rdx, [rbp+100h+var_158]
0x1800746ae  mov     rax, rdx
0x1800746b1  mov     [r9], ebx
0x1800746b4  mov     [rax], bl
0x1800746b6  lea     rax, [rax+1]
0x1800746ba  sub     rcx, 1
0x1800746be  jnz     short loc_1800746B4
0x1800746c0  mov     rcx, [rbp+100h+lpWideCharStr]
0x1800746c4  mov     [rsp+200h+var_1D8], rdx
0x1800746c9  mov     edx, [rbp+100h+arg_20]
0x1800746cf  mov     qword ptr [rsp+200h+var_1E0], r9
0x1800746d4  mov     r9, r8
0x1800746d7  mov     r8d, [rbp+100h+arg_28]
0x1800746de  call    HvsiWinHttpReadProxySettings
0x1800746e3  mov     dword ptr [rsp+200h+BindingHandle], eax
0x1800746e7  test    eax, eax
0x1800746e9  jns     short loc_1800746F7
0x1800746eb  mov     dword ptr [rbp+100h+var_140+4], 141Fh
0x1800746f2  jmp     loc_180074779
0x1800746f7  test    byte ptr cs:xmmword_180107A60, 20h
0x1800746fe  jz      loc_18007479B
0x180074704  mov     rcx, [rbp+100h+var_158]
0x180074708  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18007470f  mov     edx, 0ABh
0x180074714  mov     rax, [rcx+30h]
0x180074718  mov     [rsp+200h+var_198], rax
0x18007471d  mov     rax, [rcx+28h]
0x180074721  mov     [rsp+200h+var_1A0], rax
0x180074726  mov     rax, [rcx+20h]
0x18007472a  mov     [rsp+200h+var_1A8], rax
0x18007472f  mov     rax, [rcx+18h]
0x180074733  mov     [rsp+200h+var_1B0], rax
0x180074738  mov     eax, [rcx+38h]
0x18007473b  mov     [rsp+200h+var_1B8], eax
0x18007473f  mov     eax, [rcx+4]
0x180074742  mov     dword ptr [rsp+200h+var_1C0], eax
0x180074746  mov     eax, [rcx+8]
0x180074749  mov     dword ptr [rsp+200h+var_1C8], eax
0x18007474d  mov     rax, [rcx+10h]
0x180074751  mov     rcx, [rbp+100h+var_150]
0x180074755  mov     [rsp+200h+var_1D0], rax
0x18007475a  mov     rax, [rbp+100h+lpWideCharStr]
0x18007475e  mov     [rsp+200h+var_1D8], rax
0x180074763  mov     eax, [rcx]
0x180074765  mov     rcx, [rbp+100h+var_148]
0x180074769  mov     [rsp+200h+var_1E0], eax
0x18007476d  mov     r9d, [rcx]
0x180074770  call    WPP_SF_DlSSDDDSSSS
0x180074775  mov     eax, dword ptr [rsp+200h+BindingHandle]
0x180074779  test    byte ptr cs:xmmword_180107A60, 20h
0x180074780  jz      short loc_18007479B
0x180074782  mov     edx, 0ACh
0x180074787  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18007478e  mov     ecx, 405h
0x180074793  mov     r9d, eax
0x180074796  call    WPP_SF_d
0x18007479b  cmp     cs:g_fKirHttpBugFix26Q2, bl
0x1800747a1  jnz     short loc_1800747CD
0x1800747a3  lea     rcx, [rbp+100h+var_80]; lpPerformanceCount
0x1800747aa  call    cs:__imp_QueryPerformanceCounter
0x1800747b0  mov     rcx, qword ptr [rbp+100h+var_80]
0x1800747b7  mov     edx, 2
0x1800747bc  sub     rcx, qword ptr [rbp+100h+PerformanceCount]
0x1800747c3  mov     r8d, dword ptr [rsp+200h+BindingHandle]
0x1800747c8  call    ?WinHttpLogCallDuration@@YAX_JW4MEASURED_CALL_TYPE@@J@Z; WinHttpLogCallDuration(__int64,MEASURED_CALL_TYPE,long)
0x1800747cd  lea     rcx, [rbp+100h+var_F0]
0x1800747d1  cmp     dword ptr [rsp+200h+BindingHandle], ebx
0x1800747d5  jge     short loc_1800747EA
0x1800747d7  mov     dword ptr [rbp+100h+var_80+4], 7B7h
0x1800747e1  mov     [rbp+100h+var_E0], rbx
0x1800747e5  jmp     loc_180074C5D
0x1800747ea  xor     eax, eax
0x1800747ec  mov     dword ptr [rsp+200h+BindingHandle], eax
0x1800747f0  mov     [rbp+100h+var_E0], rax
0x1800747f4  jmp     loc_180074C5D
0x1800747f9  mov     rax, [rbp+100h+lpWideCharStr]
0x1800747fd  test    rax, rax
0x180074800  jz      short loc_180074846
0x180074802  lea     r9, [rbp+100h+lpMultiByteStr]
0x180074806  mov     rcx, rax; lpWideCharStr
0x180074809  call    ??$WxNewStringWtoACchCp@VWxGlobalAllocator@@@@YAJPEBGKKPEAPEAD@Z; WxNewStringWtoACchCp<WxGlobalAllocator>(ushort const *,ulong,ulong,char * *)
0x18007480e  mov     dword ptr [rsp+200h+BindingHandle], eax
0x180074812  test    eax, eax
0x180074814  jle     short loc_180074824
0x180074816  movzx   eax, ax
0x180074819  or      eax, 80070000h
0x18007481e  mov     dword ptr [rsp+200h+BindingHandle], eax
0x180074822  test    eax, eax
0x180074824  jns     short loc_18007483D
0x180074826  mov     [rbp+100h+var_E0], rbx
0x18007482a  mov     rbx, [rbp+100h+lpMultiByteStr]
0x18007482e  mov     dword ptr [rbp+100h+var_80+4], 7BEh
0x180074838  jmp     loc_180074C59
0x18007483d  mov     rbx, [rbp+100h+lpMultiByteStr]
0x180074841  jmp     loc_1800748EC
0x180074846  mov     dword ptr [rbp+100h+lpMultiByteStr+4], ebx
0x180074849  mov     [rbp+100h+lpWideCharStr], rbx
0x18007484d  test    byte ptr cs:xmmword_180107A60, 20h
0x180074854  jz      short loc_180074878
0x180074856  mov     r9, [rbp+100h+Size]
0x18007485a  lea     rax, [rbp+100h+var_78]
0x180074861  mov     [rsp+200h+var_1D8], rax
0x180074866  mov     edx, 23h ; '#'
0x18007486b  mov     eax, [rsp+200h+var_188]
0x18007486f  mov     [rsp+200h+var_1E0], eax
0x180074873  call    WPP_SF_iDq
0x180074878  xor     r9d, r9d; Context
0x18007487b  mov     [rbp+100h+var_78], ebx
0x180074881  xor     r8d, r8d; Parameter
0x180074884  lea     rdx, ?UseActiveIfForProxyConfigInitOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18007488b  lea     rcx, ?g_fUseActiveIfForProxyConfigOverrideInit@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180074892  call    cs:__imp_InitOnceExecuteOnce
0x180074898  test    eax, eax
0x18007489a  jnz     short loc_1800748AA
0x18007489c  mov     eax, 80004005h
0x1800748a1  mov     dword ptr [rbp+100h+lpMultiByteStr+4], 89Ah
0x1800748a8  jmp     short loc_1800748D1
0x1800748aa  mov     edx, [rsp+200h+var_188]; unsigned int
0x1800748ae  lea     r9, [rbp+100h+lpWideCharStr]; char **
0x1800748b2  mov     rcx, [rbp+100h+Size]; unsigned __int64
0x1800748b6  lea     r8, [rbp+100h+var_78]; unsigned int *
0x1800748bd  call    ?GetConnectionNameInternal@@YAJ_KKPEAKPEAPEAD@Z; GetConnectionNameInternal(unsigned __int64,ulong,ulong *,char * *)
0x1800748c2  test    eax, eax
0x1800748c4  jns     short loc_1800748CD
0x1800748c6  mov     dword ptr [rbp+100h+lpMultiByteStr+4], 89Fh
0x1800748cd  mov     rbx, [rbp+100h+lpWideCharStr]
0x1800748d1  test    byte ptr cs:xmmword_180107A60, 20h
0x1800748d8  jz      short loc_1800748EC
0x1800748da  mov     edx, 24h ; '$'
0x1800748df  mov     qword ptr [rsp+200h+var_1E0], rbx
0x1800748e4  mov     r9d, eax
0x1800748e7  call    WPP_SF_ds
0x1800748ec  mov     rax, [rbp+100h+var_138]
0x1800748f0  lea     rcx, [rbp+100h+var_F0]
0x1800748f4  mov     r9d, [rbp+100h+arg_20]; int
0x1800748fb  xor     r8d, r8d; int *
0x1800748fe  mov     [rsp+200h+var_1C0], rcx; struct WININET_PROXY_INFO_EX *
0x180074903  xor     edx, edx; struct _FILETIME *
  ... truncated ...
```
