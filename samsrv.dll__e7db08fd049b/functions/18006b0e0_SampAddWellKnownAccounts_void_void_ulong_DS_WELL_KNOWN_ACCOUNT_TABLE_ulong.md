# SampAddWellKnownAccounts(void *,void *,ulong,_DS_WELL_KNOWN_ACCOUNT_TABLE *,ulong)

- ea: `0x18006b0e0`
- end: `0x18006bcd3`
- name: `?SampAddWellKnownAccounts@@YAJPEAX0KPEAU_DS_WELL_KNOWN_ACCOUNT_TABLE@@K@Z`
- size: `3059`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, struct _SAMP_OBJECT *, int, struct _DS_WELL_KNOWN_ACCOUNT_TABLE *, unsigned int)`
- caller_count: `3`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x18006c580`
- `0x18006dff0`
- `0x180072a64`

## callees

- `0x1800026e0`
- `0x18000a570`
- `0x180015c50`
- `0x180021400`
- `0x180027e24`
- `0x180027ef8`
- `0x18002cd80`
- `0x18002d720`
- `0x1800372ac`
- `0x1800412cc`
- `0x18004e2d4`
- `0x180056510`
- `0x180056c30`
- `0x1800573f0`
- `0x180059a74`
- `0x18006aecc`
- `0x18006b0e0`
- `0x180070e00`
- `0x180072ff0`
- `0x180073c14`
- `0x180076e64`
- `0x18007bd40`
- `0x1800b03d0`
- `0x1800bb788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18006b5f3`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18006b5f3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006b1de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006b1de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006bc70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006bc70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bae0`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006babf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006babf`
- `ntdll!RtlNtStatusToDosError` at `0x18006ba95`
- `ntdll!RtlNtStatusToDosError` at `0x18006ba95`
- `ntdll!RtlInitUnicodeString` at `0x18006b6d4`
- `ntdll!RtlInitUnicodeString` at `0x18006bad4`
- `ntdll!RtlInitUnicodeString` at `0x18006b6d4`
- `ntdll!RtlInitUnicodeString` at `0x18006bad4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006b6a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006b6a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b572`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b585`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b67c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b76b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bc58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bc67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b572`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b585`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b67c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006b76b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bc58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bc67`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18006b163`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18006b163`

## string_xrefs

- `0x18006b1d3`: `SAMSRV.DLL`

## pseudocode

```c
__int64 __fastcall SampAddWellKnownAccounts(
        struct _SAMP_OBJECT *a1,
        struct _SAMP_OBJECT *a2,
        int a3,
        struct _DS_WELL_KNOWN_ACCOUNT_TABLE *a4,
        unsigned int a5)
{
  __int16 v5; // r12
  struct _SAMP_OBJECT *v6; // r15
  int v8; // r9d
  int v9; // ebx
  const wchar_t *v10; // rdx
  const wchar_t *v11; // rax
  HMODULE Library; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  HMODULE v15; // r13
  unsigned int i; // r14d
  __int64 v18; // rcx
  HLOCAL *v19; // rax
  HLOCAL *v20; // rax
  __int64 v21; // rdi
  unsigned __int8 IsDownlevelDcUpgrade; // al
  __int64 v23; // rcx
  HLOCAL *v24; // rax
  __int64 v25; // rcx
  HLOCAL *v26; // rax
  struct _SAMP_OBJECT *v27; // rbx
  unsigned int v28; // r8d
  unsigned int v29; // eax
  unsigned int v30; // r15d
  PUNICODE_STRING v31; // rcx
  __int64 v32; // rcx
  _DWORD *v33; // r13
  __int64 v34; // r9
  unsigned int v35; // eax
  int v36; // ecx
  unsigned __int64 v37; // r12
  unsigned __int16 *v38; // r14
  NTSTATUS v39; // eax
  __int64 v40; // r9
  unsigned __int64 v41; // r9
  NTSTATUS v42; // eax
  __int64 v43; // rbx
  __int64 v44; // r9
  __int64 v45; // rdx
  int v46; // ecx
  __int64 v47; // rax
  SIZE_T v48; // rbx
  HLOCAL v49; // rax
  unsigned int GroupInDomain; // eax
  __int64 v51; // rdx
  NTSTATUS v52; // eax
  __int64 *v53; // rcx
  UCHAR *v54; // rax
  HLOCAL *v55; // rax
  __int64 v56; // rcx
  __int64 v57; // rcx
  wchar_t *p_Buffer; // rax
  int MessageStringsWithLanguage; // ebx
  __int64 v60; // rdx
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  int lpBuffera; // [rsp+20h] [rbp-E0h]
  NTSTATUS Status; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v64; // [rsp+64h] [rbp-9Ch]
  HMODULE hLibModule; // [rsp+68h] [rbp-98h]
  struct _SAMP_OBJECT *v66; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v67[2]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR v68[4]; // [rsp+88h] [rbp-78h] BYREF
  int v69; // [rsp+90h] [rbp-70h]
  int v70; // [rsp+94h] [rbp-6Ch]
  HLOCAL hMem[2]; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v72[2]; // [rsp+A8h] [rbp-58h] BYREF
  struct _SAMP_OBJECT *v73; // [rsp+B8h] [rbp-48h]
  struct _SAMP_OBJECT *v74; // [rsp+C0h] [rbp-40h]
  HLOCAL v75[3]; // [rsp+C8h] [rbp-38h] BYREF
  HLOCAL v76[2]; // [rsp+E0h] [rbp-20h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v78; // [rsp+208h] [rbp+108h]
  char v79; // [rsp+20Ah] [rbp+10Ah]
  struct _UNICODE_STRING Buffer; // [rsp+210h] [rbp+110h] BYREF
  __int16 Src; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v82[30]; // [rsp+232h] [rbp+132h] BYREF
  unsigned __int16 v83[264]; // [rsp+250h] [rbp+150h] BYREF
  UCHAR pbBuffer[528]; // [rsp+460h] [rbp+360h] BYREF

  v69 = a3;
  v74 = a2;
  v5 = a3;
  v73 = a1;
  v6 = a1;
  Status = 0;
  v66 = 0;
  *(_OWORD *)v67 = 0;
  *(_OWORD *)v76 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v72 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  GetVersionExW(&VersionInformation);
  if ( v79 != 1 || (v9 = 1, (v78 & 0x200) == 0) )
    v9 = 0;
  v70 = v9;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
  {
    v10 = L"TRUE";
    v11 = L"TRUE";
    if ( (*((_BYTE *)v6 + 192) & 2) == 0 )
      v11 = (const wchar_t *)L"FALSE";
    if ( !v9 )
      v10 = (const wchar_t *)L"FALSE";
    WPP_SF_dSS(WPP_GLOBAL_Control[3].Buffer, (_DWORD)v10, (unsigned int)L"FALSE", v8, (__int64)v10, (__int64)v11);
  }
  Library = LoadLibraryExW(L"SAMSRV.DLL", 0, 2u);
  v14 = 0;
  hLibModule = Library;
  v15 = Library;
  if ( !Library )
  {
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control[3].Buffer,
        89,
        WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
        3221225609LL,
        -1073741687);
    return 3221225609LL;
  }
  for ( i = 0; ; ++i )
  {
    v64 = i;
    if ( i >= a5 )
      break;
    v18 = 16;
    v19 = hMem;
    do
    {
      *(_BYTE *)v19 = 0;
      v19 = (HLOCAL *)((char *)v19 + 1);
      --v18;
    }
    while ( v18 );
    v13 = 16;
    v20 = v72;
    do
    {
      *(_BYTE *)v20 = 0;
      v20 = (HLOCAL *)((char *)v20 + 1);
      --v13;
    }
    while ( v13 );
    v21 = 5LL * i;
    if ( !*((_BYTE *)a4 + 40 * i + 29) || (v5 & 1) != 0 )
    {
      if ( *((_BYTE *)a4 + 40 * i + 30) && (*((_BYTE *)v6 + 192) & 2) != 0
        || *((_BYTE *)a4 + 40 * i + 32)
        && SampProductType == NtProductLanManNt
        && (*((_BYTE *)v6 + 192) & 2) == 0
        && (IsDownlevelDcUpgrade = SampIsDownlevelDcUpgrade(), v14 = 0, !IsDownlevelDcUpgrade)
        || (v5 & 0x100) != 0
        || *((_BYTE *)a4 + 40 * i + 31) && SampProductType == NtProductWinNt && !v9
        || *((_BYTE *)a4 + 40 * i + 32) && SampProductType == NtProductServer
        || *((_BYTE *)a4 + 40 * i + 33) && v9 )
      {
        v66 = 0;
        v23 = 16;
        v24 = v67;
        do
        {
          *(_BYTE *)v24 = 0;
          v24 = (HLOCAL *)((char *)v24 + 1);
          --v23;
        }
        while ( v23 );
        v25 = 16;
        v26 = v76;
        do
        {
          *(_BYTE *)v26 = 0;
          v26 = (HLOCAL *)((char *)v26 + 1);
          --v25;
        }
        while ( v25 );
        v27 = v74;
        v28 = *((_DWORD *)a4 + 10 * i);
        if ( !*((_BYTE *)a4 + 40 * i + 28) )
          v27 = v6;
        v29 = *((_DWORD *)a4 + 10 * i + 1);
        *(_QWORD *)v68 = v27;
        v30 = 0;
        Status = SampGetMessageStringsWithLanguage(
                   v15,
                   0,
                   v28,
                   (struct _UNICODE_STRING *)v67,
                   v29,
                   (struct _UNICODE_STRING *)v76);
        if ( Status < 0 )
          goto LABEL_120;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
          WPP_SF_Z(WPP_GLOBAL_Control[3].Buffer, 91, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v67);
        v32 = *((unsigned int *)a4 + 10 * i + 5);
        v33 = (_DWORD *)((char *)a4 + 40 * i + 16);
        v34 = (unsigned int)*v33;
        v75[0] = *((HLOCAL *)a4 + 5 * i + 1);
        LOBYTE(lpBuffer) = 0;
        v35 = SampOpenAccount(v32, v27, 0x10000000, v34, lpBuffer, &v66);
        Status = v35;
        if ( v35 != -1073741487 )
          goto LABEL_55;
        if ( *v33 != 517 )
          goto LABEL_54;
        LOBYTE(lpBuffera) = 0;
        v35 = SampOpenAccount(2, v27, 0x10000000, (unsigned int)*v33, lpBuffera, &v66);
        Status = v35;
        if ( v35 == -1073741722 )
        {
          v35 = -1073741487;
          Status = -1073741487;
LABEL_54:
          v36 = -1073741487;
        }
        else
        {
LABEL_55:
          v36 = v35;
        }
        v14 = *((unsigned int *)a4 + 10 * i + 5);
        if ( (_DWORD)v14 == 3 )
        {
          if ( v36 != -1073741487 )
            goto LABEL_58;
LABEL_70:
          v37 = LOWORD(v67[0]);
          v38 = (unsigned __int16 *)v67[1];
          v39 = SamILookupNamesInDomain(v73, (struct _SAMPR_ULONG_ARRAY *)hMem, (struct _SAMPR_ULONG_ARRAY *)v72);
          Status = v39;
          v40 = (unsigned int)v39;
          if ( v39 == -1073741709 )
          {
            v39 = SamILookupNamesInDomain(v74, (struct _SAMPR_ULONG_ARRAY *)hMem, (struct _SAMPR_ULONG_ARRAY *)v72);
            v40 = (unsigned int)v39;
            Status = v39;
          }
          if ( v39 >= 0 )
          {
            while ( *v33 != 502 )
            {
              if ( hMem[1] )
              {
                LocalFree(hMem[1]);
                hMem[1] = 0;
              }
              if ( v72[1] )
              {
                LocalFree(v72[1]);
                v72[1] = 0;
              }
              v41 = 40;
              if ( (unsigned __int16)v37 <= 0x28u )
                v41 = v37;
              v42 = RtlStringCbCopyNW(v83, 0x202u, v38, v41);
              Status = v42;
              v40 = (unsigned int)v42;
              if ( v42 >= 0 )
              {
                v43 = -1;
                do
                  ++v43;
                while ( *(&Buffer.Length + v43) );
                Src = 126;
                _ultow(v30, &Buffer.Length, 10);
                memcpy_0(v82, &Buffer, (unsigned int)(2 * v43 + 2));
                v44 = -1;
                do
                  ++v44;
                while ( v83[v44] );
                v45 = -1;
                do
                  ++v45;
                while ( *(_WORD *)&v82[2 * v45 - 2] );
                v46 = 20 - v45;
                if ( (unsigned int)(v45 + v44) <= 0x14 )
                  v46 = v44;
                memcpy_0(&v83[v46], &Src, 2LL * (unsigned int)(v45 + 1));
                if ( v67[1] != v38 )
                  LocalFree(v67[1]);
                v47 = -1;
                do
                  ++v47;
                while ( v83[v47] );
                v48 = (unsigned int)(2 * v47 + 2);
                v49 = LocalAlloc(0x40u, v48);
                v67[1] = v49;
                if ( !v49 )
                {
                  v40 = 3221225495LL;
                  Status = -1073741801;
                  break;
                }
                memcpy_0(v49, v83, (unsigned int)v48);
                RtlInitUnicodeString((PUNICODE_STRING)v67, (PCWSTR)v67[1]);
                v42 = SamILookupNamesInDomain(v73, (struct _SAMPR_ULONG_ARRAY *)hMem, (struct _SAMPR_ULONG_ARRAY *)v72);
                Status = v42;
                v40 = (unsigned int)v42;
                if ( v42 == -1073741709 )
                {
                  v42 = SamILookupNamesInDomain(
                          v74,
                          (struct _SAMPR_ULONG_ARRAY *)hMem,
                          (struct _SAMPR_ULONG_ARRAY *)v72);
                  v40 = (unsigned int)v42;
                  Status = v42;
                }
              }
              ++v30;
              if ( v42 < 0 )
                break;
            }
            v27 = *(struct _SAMP_OBJECT **)v68;
          }
          if ( v38 != v67[1] )
          {
            LocalFree(v38);
            v40 = (unsigned int)Status;
          }
          if ( (_DWORD)v40 != -1073741709 )
          {
            if ( (int)v40 < 0 )
            {
              v13 = (__int64)WPP_GLOBAL_Control;
              if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
              {
                v60 = 95;
                goto LABEL_176;
              }
LABEL_177:
              v15 = hLibModule;
              break;
            }
            Status = -1073741725;
            goto LABEL_118;
          }
          switch ( *((_DWORD *)a4 + 2 * v21 + 5) )
          {
            case 2:
              GroupInDomain = SampCreateGroupInDomain(
                                v27,
                                (struct _RPC_UNICODE_STRING *)v67,
                                0,
                                *((_DWORD *)a4 + 2 * v21 + 6),
                                (__int64)&v66,
                                (__int64)a4 + 8 * v21 + 16);
              break;
            case 3:
              GroupInDomain = SampCreateAliasInDomain(
                                v27,
                                (struct _RPC_UNICODE_STRING *)v67,
                                0,
                                *((_DWORD *)a4 + 2 * v21 + 6),
                                (__int64)&v66,
                                (__int64)a4 + 8 * v21 + 16);
              break;
            case 4:
              *(_DWORD *)v68 = 0;
              GroupInDomain = SampCreateUserInDomain(
                                v27,
                                (PUNICODE_STRING)v67,
                                0,
                                0,
                                (__int64)&v66,
                                (__int64)v68,
                                (__int64)a4 + 8 * v21 + 16,
                                0,
                                0);
              break;
            default:
LABEL_110:
              v31 = WPP_GLOBAL_Control;
              if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
              {
                WPP_SF_ZD(
                  WPP_GLOBAL_Control[3].Buffer,
                  92,
                  (unsigned int)WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
                  (unsigned int)v67,
                  v40);
                v40 = (unsigned int)Status;
                v31 = WPP_GLOBAL_Control;
              }
              if ( (int)v40 < 0 )
              {
                if ( (*(_BYTE *)(&v31[4].MaximumLength + 1) & 0x80) != 0 && HIBYTE(v31[4].Length) >= 4u )
                {
                  v51 = 93;
                  goto LABEL_117;
                }
                goto LABEL_118;
              }
              if ( (unsigned __int8)SampDsIsRunning(v31, v14) )
              {
                if ( (unsigned int)SampExtExistsDsTransactionDs() )
                {
                  v52 = SampExtMaybeEndDsTransactionDs(3);
                  Status = v52;
                  if ( v52 < 0 )
                  {
                    v31 = WPP_GLOBAL_Control;
                    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x80) != 0
                      && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
                    {
                      v51 = 94;
                      v40 = (unsigned int)v52;
LABEL_117:
                      WPP_SF_d(v31[3].Buffer, v51, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v40);
                    }
LABEL_118:
                    i = v64;
LABEL_119:
                    v15 = hLibModule;
LABEL_120:
                    if ( (unsigned __int8)SampDsIsRunning(v31, v14) && (unsigned int)SampExtExistsDsTransactionDs() )
                    {
                      if ( Status < 0 )
                        SampExtMaybeEndDsTransactionDs(2);
                      else
                        Status = SampExtMaybeEndDsTransactionDs(3);
                    }
                    if ( Status < 0 )
                    {
                      v64 = 0;
                      *(_QWORD *)v68 = 0;
                      v55 = v75;
                      *(_OWORD *)v75 = 0;
                      v56 = 16;
                      Buffer = 0;
                      do
                      {
                        *(_BYTE *)v55 = 0;
                        v55 = (HLOCAL *)((char *)v55 + 1);
                        --v56;
                      }
                      while ( v56 );
                      v57 = 16;
                      p_Buffer = (wchar_t *)&Buffer;
                      do
                      {
                        *(_BYTE *)p_Buffer = 0;
                        p_Buffer = (wchar_t *)((char *)p_Buffer + 1);
                        --v57;
                      }
                      while ( v57 );
                      MessageStringsWithLanguage = SampGetMessageStringsWithLanguage(
                                                     v15,
                                                     0,
                                                     *((_DWORD *)a4 + 2 * v21),
                                                     (struct _UNICODE_STRING *)v75,
                                                     0,
                                                     0);
                      v64 = RtlNtStatusToDosError(Status);
                      if ( FormatMessageW(0x1100u, 0, v64, 0, v68, 0, 0) )
                      {
                        RtlInitUnicodeString(&Buffer, *(PCWSTR *)v68);
                        *(_QWORD *)v68 = 0;
LABEL_153:
                        if ( MessageStringsWithLanguage >= 0 )
                          SampWriteEventLog(SAMMSG_USER_SETUP_ERROR, L"uub", v75, &Buffer, 4);
                      }
                      else if ( !GetLastError() )
                      {
                        goto LABEL_153;
                      }
                      if ( v75[1] )
                        LocalFree(v75[1]);
                      if ( Buffer.Buffer )
                        LocalFree(Buffer.Buffer);
                      Status = 0;
                    }
                    if ( v66 )
                    {
                      SamrCloseHandle(&v66);
                      v66 = 0;
                    }
                    if ( hMem[1] )
                    {
                      LocalFree(hMem[1]);
                      hMem[1] = 0;
                    }
                    if ( v72[1] )
                    {
                      LocalFree(v72[1]);
                      v72[1] = 0;
                    }
                    if ( v67[1] )
                    {
                      LocalFree(v67[1]);
                      v67[1] = 0;
                    }
                    v13 = (__int64)v76[1];
                    if ( v76[1] )
                    {
                      LocalFree(v76[1]);
                      v76[1] = 0;
                    }
                    v5 = v69;
                    v6 = v73;
LABEL_171:
                    v14 = 0;
                    goto LABEL_172;
                  }
                }
              }
              if ( (v69 & 8) != 0 && !*((_BYTE *)a4 + 8 * v21 + 34) )
              {
                if ( *((_DWORD *)a4 + 2 * v21 + 5) == 4 )
                  v53 = SAMMSG_WELL_KNOWN_ACCOUNT_RECREATED;
                else
                  v53 = SAMMSG_WELL_KNOWN_GROUP_RECREATED;
                SampWriteEventLog(v53, L"ub", v67, 4, &Status);
              }
              i = v64;
LABEL_136:
              v54 = (UCHAR *)v75[0];
              if ( !v75[0] && *((_DWORD *)a4 + 2 * v21 + 5) == 4 )
              {
                Status = SampGenerateRandomPassword(pbBuffer);
                if ( Status < 0 )
                  goto LABEL_177;
                v54 = pbBuffer;
              }
              Buffer = *(struct _UNICODE_STRING *)v76;
              Status = SampSetWellKnownAccountProperties(
                         v66,
                         &Buffer,
                         (struct _UNICODE_STRING *)v67,
                         (const unsigned __int16 *)v54,
                         a4,
                         i);
              goto LABEL_119;
          }
          Status = GroupInDomain;
          v40 = GroupInDomain;
          goto LABEL_110;
        }
        if ( (_DWORD)v14 == 2 && v36 == -1073741722 || (_DWORD)v14 == 4 && v36 == -1073741724 )
          goto LABEL_70;
LABEL_58:
        if ( v36 < 0 )
        {
          v13 = (__int64)WPP_GLOBAL_Control;
          if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
          {
            v60 = 97;
            v40 = v35;
LABEL_176:
            WPP_SF_d(*(_QWORD *)(v13 + 56), v60, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v40);
          }
          goto LABEL_177;
        }
        v31 = WPP_GLOBAL_Control;
        if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
          WPP_SF_Z(WPP_GLOBAL_Control[3].Buffer, 96, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v67);
        if ( !*((_BYTE *)a4 + 40 * i + 34) || *((_BYTE *)a4 + 40 * i + 32) || (v5 & 0x400) != 0 )
          goto LABEL_119;
        goto LABEL_136;
      }
      v13 = (__int64)WPP_GLOBAL_Control;
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[3].Buffer,
          90,
          WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
          *((unsigned int *)a4 + 10 * i + 4));
        goto LABEL_171;
      }
    }
LABEL_172:
    v9 = v70;
  }
  if ( (unsigned __int8)SampDsIsRunning(v13, v14) && (unsigned int)SampExtExistsDsTransactionDs() )
  {
    if ( Status < 0 )
      SampExtMaybeEndDsTransactionDs(2);
    else
      Status = SampExtMaybeEndDsTransactionDs(3);
  }
  if ( v66 )
    SamrCloseHandle(&v66);
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v72[1] )
    LocalFree(v72[1]);
  FreeLibrary(v15);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      98,
      WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids,
      (unsigned int)Status,
      Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x18006b0e0  mov     [rsp-8+arg_10], rbx
0x18006b0e5  push    rbp
0x18006b0e6  push    rsi
0x18006b0e7  push    rdi
0x18006b0e8  push    r12
0x18006b0ea  push    r13
0x18006b0ec  push    r14
0x18006b0ee  push    r15
0x18006b0f0  lea     rbp, [rsp-580h]
0x18006b0f8  sub     rsp, 680h
0x18006b0ff  mov     rax, cs:__security_cookie
0x18006b106  xor     rax, rsp
0x18006b109  mov     [rbp+5B0h+var_40], rax
0x18006b110  xorps   xmm0, xmm0
0x18006b113  mov     [rbp+5B0h+var_620], r8d
0x18006b117  xorps   xmm1, xmm1
0x18006b11a  mov     [rbp+5B0h+var_5F0], rdx
0x18006b11e  mov     r12d, r8d
0x18006b121  mov     [rbp+5B0h+var_5F8], rcx
0x18006b125  mov     r15, rcx
0x18006b128  xor     edi, edi
0x18006b12a  xor     edx, edx; Val
0x18006b12c  mov     [rsp+6B0h+Status], edi
0x18006b130  mov     r8d, 118h; Size
0x18006b136  mov     [rsp+6B0h+var_640], rdi
0x18006b13b  lea     rcx, [rbp+5B0h+VersionInformation.dwMajorVersion]; void *
0x18006b13f  mov     rsi, r9
0x18006b142  movups  xmmword ptr [rsp+6B0h+var_638], xmm0
0x18006b147  movups  xmmword ptr [rbp+5B0h+var_5D0], xmm1
0x18006b14b  movups  xmmword ptr [rbp+5B0h+hMem], xmm0
0x18006b14f  movups  xmmword ptr [rbp+5B0h+var_608], xmm1
0x18006b153  call    memset_0
0x18006b158  lea     rcx, [rbp+5B0h+VersionInformation]; lpVersionInformation
0x18006b15c  mov     [rbp+5B0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18006b163  call    cs:__imp_GetVersionExW
0x18006b169  cmp     [rbp+5B0h+var_4A6], 1
0x18006b170  mov     eax, 200h
0x18006b175  jnz     short loc_18006B183
0x18006b177  lea     ebx, [rdi+1]
0x18006b17a  test    [rbp+5B0h+var_4A8], ax
0x18006b181  jnz     short loc_18006B185
0x18006b183  mov     ebx, edi
0x18006b185  mov     [rbp+5B0h+var_61C], ebx
0x18006b188  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b18f  test    byte ptr [rcx+44h], 80h
0x18006b193  jz      short loc_18006B1D1
0x18006b195  cmp     byte ptr [rcx+41h], 4
0x18006b199  jb      short loc_18006B1D1
0x18006b19b  test    byte ptr [r15+0C0h], 2
0x18006b1a3  lea     r8, aFalse_0; "FALSE"
0x18006b1aa  mov     rcx, [rcx+38h]
0x18006b1ae  lea     rdx, aTrue_0; "TRUE"
0x18006b1b5  mov     rax, rdx
0x18006b1b8  cmovz   rax, r8
0x18006b1bc  test    ebx, ebx
0x18006b1be  mov     qword ptr [rsp+6B0h+nSize], rax
0x18006b1c3  cmovz   rdx, r8
0x18006b1c7  mov     [rsp+6B0h+lpBuffer], rdx
0x18006b1cc  call    WPP_SF_dSS
0x18006b1d1  xor     edx, edx; hFile
0x18006b1d3  lea     rcx, LibFileName; "SAMSRV.DLL"
0x18006b1da  lea     r8d, [rdx+2]; dwFlags
0x18006b1de  call    cs:__imp_LoadLibraryExW
0x18006b1e4  xor     edx, edx
0x18006b1e6  mov     [rsp+6B0h+hLibModule], rax
0x18006b1eb  mov     r13, rax
0x18006b1ee  test    rax, rax
0x18006b1f1  jnz     short loc_18006B22C
0x18006b1f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b1fa  mov     ebx, 0C0000089h
0x18006b1ff  test    dword ptr [rcx+44h], 20000h
0x18006b206  jz      short loc_18006B225
0x18006b208  mov     rcx, [rcx+38h]
0x18006b20c  lea     edx, [rax+59h]
0x18006b20f  mov     r9d, 0C0000089h
0x18006b215  mov     dword ptr [rsp+6B0h+lpBuffer], ebx
0x18006b219  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006b220  call    WPP_SF_Dd
0x18006b225  mov     eax, ebx
0x18006b227  jmp     loc_18006BCA9
0x18006b22c  mov     r14d, edx
0x18006b22f  mov     [rsp+6B0h+var_64C], r14d
0x18006b234  cmp     r14d, [rbp+5B0h+arg_20]
0x18006b23b  jnb     loc_18006BC08
0x18006b241  mov     ecx, 10h
0x18006b246  lea     rax, [rbp+5B0h+hMem]
0x18006b24a  mov     [rax], dl
0x18006b24c  inc     rax
0x18006b24f  sub     rcx, 1
0x18006b253  jnz     short loc_18006B24A
0x18006b255  mov     ecx, 10h
0x18006b25a  lea     rax, [rbp+5B0h+var_608]
0x18006b25e  mov     [rax], dl
0x18006b260  inc     rax
0x18006b263  sub     rcx, 1
0x18006b267  jnz     short loc_18006B25E
0x18006b269  mov     eax, r14d
0x18006b26c  lea     rdi, [rax+rax*4]
0x18006b270  cmp     [rsi+rdi*8+1Dh], dl
0x18006b274  jz      short loc_18006B280
0x18006b276  test    r12b, 1
0x18006b27a  jz      loc_18006BBB1
0x18006b280  cmp     [rsi+rdi*8+1Eh], dl
0x18006b284  jz      short loc_18006B294
0x18006b286  test    byte ptr [r15+0C0h], 2
0x18006b28e  jnz     loc_18006B325
0x18006b294  cmp     [rsi+rdi*8+20h], dl
0x18006b298  jz      short loc_18006B2B8
0x18006b29a  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 2; _NT_PRODUCT_TYPE SampProductType
0x18006b2a1  jnz     short loc_18006B2B8
0x18006b2a3  test    byte ptr [r15+0C0h], 2
0x18006b2ab  jnz     short loc_18006B2B8
0x18006b2ad  call    ?SampIsDownlevelDcUpgrade@@YAEXZ; SampIsDownlevelDcUpgrade(void)
0x18006b2b2  xor     edx, edx
0x18006b2b4  test    al, al
0x18006b2b6  jz      short loc_18006B325
0x18006b2b8  bt      r12d, 8
0x18006b2bd  jb      short loc_18006B325
0x18006b2bf  cmp     [rsi+rdi*8+1Fh], dl
0x18006b2c3  jz      short loc_18006B2D2
0x18006b2c5  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 1; _NT_PRODUCT_TYPE SampProductType
0x18006b2cc  jnz     short loc_18006B2D2
0x18006b2ce  test    ebx, ebx
0x18006b2d0  jz      short loc_18006B325
0x18006b2d2  cmp     [rsi+rdi*8+20h], dl
0x18006b2d6  jz      short loc_18006B2E1
0x18006b2d8  cmp     cs:?SampProductType@@3W4_NT_PRODUCT_TYPE@@A, 3; _NT_PRODUCT_TYPE SampProductType
0x18006b2df  jz      short loc_18006B325
0x18006b2e1  cmp     [rsi+rdi*8+21h], dl
0x18006b2e5  jz      short loc_18006B2EB
0x18006b2e7  test    ebx, ebx
0x18006b2e9  jnz     short loc_18006B325
0x18006b2eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b2f2  test    byte ptr [rcx+44h], 80h
0x18006b2f6  jz      loc_18006BBB1
0x18006b2fc  cmp     byte ptr [rcx+41h], 4
0x18006b300  jb      loc_18006BBB1
0x18006b306  mov     r9d, [rsi+rdi*8+10h]
0x18006b30b  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006b312  mov     rcx, [rcx+38h]
0x18006b316  mov     edx, 5Ah ; 'Z'
0x18006b31b  call    WPP_SF_d
0x18006b320  jmp     loc_18006BBAF
0x18006b325  mov     r8d, 10h
0x18006b32b  mov     [rsp+6B0h+var_640], rdx
0x18006b330  mov     ecx, r8d
0x18006b333  lea     rax, [rsp+6B0h+var_638]
0x18006b338  mov     [rax], dl
0x18006b33a  inc     rax
0x18006b33d  sub     rcx, 1
0x18006b341  jnz     short loc_18006B338
0x18006b343  mov     rcx, r8
0x18006b346  lea     rax, [rbp+5B0h+var_5D0]
0x18006b34a  mov     [rax], dl
0x18006b34c  inc     rax
0x18006b34f  sub     rcx, 1
0x18006b353  jnz     short loc_18006B34A
0x18006b355  cmp     [rsi+rdi*8+1Ch], dl
0x18006b359  lea     rax, [rbp+5B0h+var_5D0]
0x18006b35d  mov     rbx, [rbp+5B0h+var_5F0]
0x18006b361  lea     r9, [rsp+6B0h+var_638]; struct _UNICODE_STRING *
0x18006b366  mov     r8d, [rsi+rdi*8]; unsigned int
0x18006b36a  cmovz   rbx, r15
0x18006b36e  mov     qword ptr [rsp+6B0h+nSize], rax; struct _UNICODE_STRING *
0x18006b373  xor     edx, edx; unsigned int
0x18006b375  mov     eax, [rsi+rdi*8+4]
0x18006b379  mov     rcx, r13; void *
0x18006b37c  mov     qword ptr [rbp+5B0h+var_628], rbx
0x18006b380  mov     dword ptr [rsp+6B0h+lpBuffer], eax; unsigned int
0x18006b384  call    ?SampGetMessageStringsWithLanguage@@YAJPEAXKKPEAU_UNICODE_STRING@@K1@Z; SampGetMessageStringsWithLanguage(void *,ulong,ulong,_UNICODE_STRING *,ulong,_UNICODE_STRING *)
0x18006b389  xor     r15d, r15d
0x18006b38c  mov     [rsp+6B0h+Status], eax
0x18006b390  test    eax, eax
0x18006b392  js      loc_18006B8CC
0x18006b398  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b39f  test    byte ptr [rcx+44h], 80h
0x18006b3a3  jz      short loc_18006B3C4
0x18006b3a5  cmp     byte ptr [rcx+41h], 4
0x18006b3a9  jb      short loc_18006B3C4
0x18006b3ab  mov     rcx, [rcx+38h]
0x18006b3af  lea     edx, [r15+5Bh]
0x18006b3b3  lea     r9, [rsp+6B0h+var_638]
0x18006b3b8  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006b3bf  call    WPP_SF_Z
0x18006b3c4  mov     rax, [rsi+rdi*8+8]
0x18006b3c9  lea     r13, [rsi+10h]
0x18006b3cd  mov     ecx, [rsi+rdi*8+14h]
0x18006b3d1  lea     r13, [r13+rdi*8+0]
0x18006b3d6  mov     r9d, [r13+0]
0x18006b3da  mov     r8d, 10000000h
0x18006b3e0  mov     [rbp+5B0h+var_5E8], rax
0x18006b3e4  mov     rdx, rbx
0x18006b3e7  lea     rax, [rsp+6B0h+var_640]
0x18006b3ec  mov     qword ptr [rsp+6B0h+nSize], rax
0x18006b3f1  mov     byte ptr [rsp+6B0h+lpBuffer], r15b
0x18006b3f6  call    ?SampOpenAccount@@YAJW4_SAMP_OBJECT_TYPE@@PEAXKKEPEAPEAX@Z; SampOpenAccount(_SAMP_OBJECT_TYPE,void *,ulong,ulong,uchar,void * *)
0x18006b3fb  mov     r8d, 0C0000151h
0x18006b401  mov     [rsp+6B0h+Status], eax
0x18006b405  cmp     eax, r8d
0x18006b408  jnz     short loc_18006B457
0x18006b40a  cmp     dword ptr [r13+0], 205h
0x18006b412  jnz     short loc_18006B452
0x18006b414  mov     r9d, [r13+0]
0x18006b418  lea     rax, [rsp+6B0h+var_640]
0x18006b41d  mov     qword ptr [rsp+6B0h+nSize], rax
0x18006b422  mov     r8d, 10000000h
0x18006b428  mov     rdx, rbx
0x18006b42b  mov     byte ptr [rsp+6B0h+lpBuffer], r15b
0x18006b430  mov     ecx, 2
0x18006b435  call    ?SampOpenAccount@@YAJW4_SAMP_OBJECT_TYPE@@PEAXKKEPEAPEAX@Z; SampOpenAccount(_SAMP_OBJECT_TYPE,void *,ulong,ulong,uchar,void * *)
0x18006b43a  mov     [rsp+6B0h+Status], eax
0x18006b43e  mov     r8d, 0C0000151h
0x18006b444  cmp     eax, 0C0000066h
0x18006b449  jnz     short loc_18006B457
0x18006b44b  mov     eax, r8d
0x18006b44e  mov     [rsp+6B0h+Status], eax
0x18006b452  mov     ecx, r8d
0x18006b455  jmp     short loc_18006B459
0x18006b457  mov     ecx, eax
0x18006b459  mov     edx, [rsi+rdi*8+14h]
0x18006b45d  cmp     edx, 3
0x18006b460  jnz     short loc_18006B4C2
0x18006b462  cmp     ecx, r8d
0x18006b465  jz      short loc_18006B4DC
0x18006b467  test    ecx, ecx
0x18006b469  js      loc_18006BBEB
0x18006b46f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b476  test    byte ptr [rcx+44h], 80h
0x18006b47a  jz      short loc_18006B49C
0x18006b47c  cmp     byte ptr [rcx+41h], 4
0x18006b480  jb      short loc_18006B49C
0x18006b482  mov     rcx, [rcx+38h]
0x18006b486  lea     r9, [rsp+6B0h+var_638]
0x18006b48b  mov     edx, 60h ; '`'
0x18006b490  lea     r8, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x18006b497  call    WPP_SF_Z
0x18006b49c  cmp     [rsi+rdi*8+22h], r15b
0x18006b4a1  jz      loc_18006B8C7
0x18006b4a7  cmp     [rsi+rdi*8+20h], r15b
0x18006b4ac  jnz     loc_18006B8C7
0x18006b4b2  bt      r12d, 0Ah
0x18006b4b7  jb      loc_18006B8C7
0x18006b4bd  jmp     loc_18006B989
0x18006b4c2  cmp     edx, 2
0x18006b4c5  jnz     short loc_18006B4CF
0x18006b4c7  cmp     ecx, 0C0000066h
0x18006b4cd  jz      short loc_18006B4DC
0x18006b4cf  cmp     edx, 4
0x18006b4d2  jnz     short loc_18006B467
0x18006b4d4  cmp     ecx, 0C0000064h
0x18006b4da  jnz     short loc_18006B467
0x18006b4dc  mov     rcx, [rbp+5B0h+var_5F8]
0x18006b4e0  lea     rax, [rbp+5B0h+var_608]
0x18006b4e4  movzx   r12d, word ptr [rsp+6B0h+var_638]
0x18006b4ea  lea     r9, [rsp+6B0h+var_638]
0x18006b4ef  mov     r14, [rbp+5B0h+var_638+8]
0x18006b4f3  mov     edx, 200h
0x18006b4f8  mov     qword ptr [rsp+6B0h+nSize], rax
0x18006b4fd  mov     r8d, 1
0x18006b503  lea     rax, [rbp+5B0h+hMem]
0x18006b507  mov     [rsp+6B0h+lpBuffer], rax
0x18006b50c  call    SamILookupNamesInDomain
0x18006b511  mov     [rsp+6B0h+Status], eax
0x18006b515  mov     r9d, eax
0x18006b518  cmp     eax, 0C0000073h
0x18006b51d  jnz     short loc_18006B551
0x18006b51f  mov     rcx, [rbp+5B0h+var_5F0]
0x18006b523  lea     rax, [rbp+5B0h+var_608]
0x18006b527  mov     qword ptr [rsp+6B0h+nSize], rax
0x18006b52c  lea     r9, [rsp+6B0h+var_638]
0x18006b531  lea     rax, [rbp+5B0h+hMem]
0x18006b535  mov     edx, 200h
0x18006b53a  mov     r8d, 1
0x18006b540  mov     [rsp+6B0h+lpBuffer], rax
0x18006b545  call    SamILookupNamesInDomain
0x18006b54a  mov     r9d, eax
0x18006b54d  mov     [rsp+6B0h+Status], eax
0x18006b551  test    eax, eax
0x18006b553  js      loc_18006B762
0x18006b559  xor     ebx, ebx
0x18006b55b  cmp     dword ptr [r13+0], 1F6h
0x18006b563  jz      loc_18006B75E
0x18006b569  mov     rcx, [rbp+5B0h+hMem+8]; hMem
0x18006b56d  test    rcx, rcx
0x18006b570  jz      short loc_18006B57C
0x18006b572  call    cs:__imp_LocalFree
0x18006b578  mov     [rbp+5B0h+hMem+8], rbx
0x18006b57c  mov     rcx, [rbp+5B0h+var_608+8]; hMem
0x18006b580  test    rcx, rcx
0x18006b583  jz      short loc_18006B58F
0x18006b585  call    cs:__imp_LocalFree
0x18006b58b  mov     [rbp+5B0h+var_608+8], rbx
0x18006b58f  mov     eax, 28h ; '('
0x18006b594  mov     r9d, eax
0x18006b597  cmp     ax, r12w
0x18006b59b  jb      short loc_18006B5A0
0x18006b59d  mov     r9, r12; unsigned __int64
0x18006b5a0  mov     r8, r14; unsigned __int16 *
0x18006b5a3  lea     rcx, [rbp+5B0h+var_460]; unsigned __int16 *
0x18006b5aa  mov     edx, 202h; unsigned __int64
  ... truncated ...
```
