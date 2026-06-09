# LoadClusterResourceLibraries(CLUSTER_API *)

- ea: `0x100422210`
- end: `0x100422702`
- name: `?LoadClusterResourceLibraries@@YAKPEAUCLUSTER_API@@@Z`
- size: `1266`
- prototype: `unsigned int __fastcall(struct CLUSTER_API *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100424a20`

## callees

- `0x100422210`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x10042261f`
- `KERNEL32!FreeLibrary` at `0x100422634`
- `KERNEL32!FreeLibrary` at `0x100422649`
- `KERNEL32!FreeLibrary` at `0x10042261f`
- `KERNEL32!FreeLibrary` at `0x100422634`
- `KERNEL32!FreeLibrary` at `0x100422649`
- `KERNEL32!SetLastError` at `0x100422606`
- `KERNEL32!SetLastError` at `0x100422606`
- `KERNEL32!GetProcAddress` at `0x100422306`
- `KERNEL32!GetProcAddress` at `0x100422323`
- `KERNEL32!GetProcAddress` at `0x100422340`
- `KERNEL32!GetProcAddress` at `0x10042235d`
- `KERNEL32!GetProcAddress` at `0x10042237a`
- `KERNEL32!GetProcAddress` at `0x100422397`
- `KERNEL32!GetProcAddress` at `0x1004223b4`
- `KERNEL32!GetProcAddress` at `0x1004223d1`
- `KERNEL32!GetProcAddress` at `0x1004223ee`
- `KERNEL32!GetProcAddress` at `0x10042240b`
- `KERNEL32!GetProcAddress` at `0x100422428`
- `KERNEL32!GetProcAddress` at `0x100422445`
- `KERNEL32!GetProcAddress` at `0x100422462`
- `KERNEL32!GetProcAddress` at `0x10042247f`
- `KERNEL32!GetProcAddress` at `0x10042249c`
- `KERNEL32!GetProcAddress` at `0x1004224b9`
- `KERNEL32!GetProcAddress` at `0x1004224d6`
- `KERNEL32!GetProcAddress` at `0x1004224f3`
- `KERNEL32!GetProcAddress` at `0x100422513`
- `KERNEL32!GetProcAddress` at `0x10042259e`
- `KERNEL32!GetProcAddress` at `0x1004225ba`
- `KERNEL32!GetProcAddress` at `0x100422306`
- `KERNEL32!GetProcAddress` at `0x100422323`
- `KERNEL32!GetProcAddress` at `0x100422340`
- `KERNEL32!GetProcAddress` at `0x10042235d`
- `KERNEL32!GetProcAddress` at `0x10042237a`
- `KERNEL32!GetProcAddress` at `0x100422397`
- `KERNEL32!GetProcAddress` at `0x1004223b4`
- `KERNEL32!GetProcAddress` at `0x1004223d1`
- `KERNEL32!GetProcAddress` at `0x1004223ee`
- `KERNEL32!GetProcAddress` at `0x10042240b`
- `KERNEL32!GetProcAddress` at `0x100422428`
- `KERNEL32!GetProcAddress` at `0x100422445`
- `KERNEL32!GetProcAddress` at `0x100422462`
- `KERNEL32!GetProcAddress` at `0x10042247f`
- `KERNEL32!GetProcAddress` at `0x10042249c`
- `KERNEL32!GetProcAddress` at `0x1004224b9`
- `KERNEL32!GetProcAddress` at `0x1004224d6`
- `KERNEL32!GetProcAddress` at `0x1004224f3`
- `KERNEL32!GetProcAddress` at `0x100422513`
- `KERNEL32!GetProcAddress` at `0x10042259e`
- `KERNEL32!GetProcAddress` at `0x1004225ba`
- `KERNEL32!GetLastError` at `0x10042260f`
- `KERNEL32!GetLastError` at `0x10042260f`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x1004222ea`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100422586`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x1004222ea`
- `sqldk!?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z` at `0x100422586`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1004222d5`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x10042256e`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x1004222d5`
- `sqlTsEs!?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z` at `0x10042256e`

## string_xrefs

- `0x100422249`: `sql\common\dk\sni\src\sni.cpp`
- `0x1004222fc`: `OpenCluster`
- `0x100422294`: `CLUSAPI.DLL`
- `0x1004222cc`: `CLUSAPI.DLL`
- `0x100422336`: `OpenClusterResource`
- `0x100422370`: `ClusterOpenEnum`
- `0x1004223c7`: `ClusterResourceOpenEnum`
- `0x10042241e`: `ClusterGroupOpenEnum`
- `0x100422492`: `ClusterGroupOpenEnum`
- `0x100422458`: `OpenClusterGroup`
- `0x100422531`: `RESUTILS.DLL`
- `0x100422565`: `RESUTILS.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LoadClusterResourceLibraries(HMODULE *a1)
{
  __int64 v2; // rcx
  const char *v3; // rax
  DWORD v4; // esi
  HMODULE v5; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  FARPROC v11; // rax
  FARPROC v12; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // rax
  FARPROC v17; // rax
  FARPROC v18; // rax
  FARPROC v19; // rax
  FARPROC v20; // rax
  FARPROC v21; // rax
  FARPROC v22; // rax
  FARPROC v23; // rax
  FARPROC v24; // rax
  FARPROC v25; // rax
  __int64 v26; // rcx
  const char *v27; // rax
  HMODULE v28; // rax
  FARPROC v29; // rax
  FARPROC v30; // rax
  const wchar_t *v31; // r9
  DWORD LastError; // ebp
  HMODULE v33; // rcx
  __int64 v35; // [rsp+20h] [rbp-488h]
  wchar_t v36[264]; // [rsp+60h] [rbp-448h] BYREF
  wchar_t v37[264]; // [rsp+270h] [rbp-238h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "LoadClusterResourceLibraries",
      459,
      L"API|SNIpClusterApi: %p{CLUSTER_API*}\n",
      a1);
  v2 = 261;
  v3 = "CLUSAPI.DLL";
  while ( 1 )
  {
    v4 = 0;
    if ( !*v3 )
      break;
    ++v3;
    if ( !--v2 )
    {
LABEL_36:
      SetLastError(0x7Bu);
      v6 = 0;
LABEL_37:
      LastError = GetLastError();
      if ( *a1 )
      {
        FreeLibrary(*a1);
        *a1 = 0;
      }
      v33 = a1[18];
      if ( v33 )
      {
        FreeLibrary(v33);
        a1[18] = 0;
      }
      if ( v6 )
        FreeLibrary(v6);
      if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
      {
        LODWORD(v35) = 7;
        SNIXE_SNI_ERROR_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "LoadClusterResourceLibraries",
          625,
          L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
          v35,
          0,
          LastError);
      }
      SNISetLastError(7, LastError, 50100);
      if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
      {
        LODWORD(v35) = LastError;
        SNIXE_SNI_TRACE_ON(
          "sql\\common\\dk\\sni\\src\\sni.cpp",
          "LoadClusterResourceLibraries",
          627,
          L"RET|SNI%d{WINERR}\n",
          v35);
      }
      v4 = LastError;
      goto LABEL_48;
    }
  }
  FastDBCSToUnicode(0, "CLUSAPI.DLL", -1, v36, 261);
  v5 = SOS_OS::SOSLoadLibraryW(v36, 1, 0, 0);
  v6 = v5;
  if ( !v5 )
    goto LABEL_37;
  ProcAddress = GetProcAddress(v5, "OpenCluster");
  a1[1] = (HMODULE)ProcAddress;
  if ( !ProcAddress )
    goto LABEL_37;
  v8 = GetProcAddress(v6, "CloseCluster");
  a1[2] = (HMODULE)v8;
  if ( !v8 )
    goto LABEL_37;
  v9 = GetProcAddress(v6, "OpenClusterResource");
  a1[3] = (HMODULE)v9;
  if ( !v9 )
    goto LABEL_37;
  v10 = GetProcAddress(v6, "CloseClusterResource");
  a1[4] = (HMODULE)v10;
  if ( !v10 )
    goto LABEL_37;
  v11 = GetProcAddress(v6, "ClusterOpenEnum");
  a1[5] = (HMODULE)v11;
  if ( !v11 )
    goto LABEL_37;
  v12 = GetProcAddress(v6, "ClusterEnum");
  a1[6] = (HMODULE)v12;
  if ( !v12 )
    goto LABEL_37;
  v13 = GetProcAddress(v6, "ClusterCloseEnum");
  a1[7] = (HMODULE)v13;
  if ( !v13 )
    goto LABEL_37;
  v14 = GetProcAddress(v6, "ClusterResourceOpenEnum");
  a1[8] = (HMODULE)v14;
  if ( !v14 )
    goto LABEL_37;
  v15 = GetProcAddress(v6, "ClusterResourceEnum");
  a1[9] = (HMODULE)v15;
  if ( !v15 )
    goto LABEL_37;
  v16 = GetProcAddress(v6, "ClusterResourceCloseEnum");
  a1[10] = (HMODULE)v16;
  if ( !v16 )
    goto LABEL_37;
  v17 = GetProcAddress(v6, "ClusterGroupOpenEnum");
  a1[13] = (HMODULE)v17;
  if ( !v17 )
    goto LABEL_37;
  v18 = GetProcAddress(v6, "ClusterGroupCloseEnum");
  a1[14] = (HMODULE)v18;
  if ( !v18 )
    goto LABEL_37;
  v19 = GetProcAddress(v6, "OpenClusterGroup");
  a1[11] = (HMODULE)v19;
  if ( !v19 )
    goto LABEL_37;
  v20 = GetProcAddress(v6, "CloseClusterGroup");
  a1[12] = (HMODULE)v20;
  if ( !v20 )
    goto LABEL_37;
  v21 = GetProcAddress(v6, "ClusterGroupOpenEnum");
  a1[13] = (HMODULE)v21;
  if ( !v21 )
    goto LABEL_37;
  v22 = GetProcAddress(v6, "ClusterGroupCloseEnum");
  a1[14] = (HMODULE)v22;
  if ( !v22 )
    goto LABEL_37;
  v23 = GetProcAddress(v6, "ClusterGroupEnum");
  a1[15] = (HMODULE)v23;
  if ( !v23 )
    goto LABEL_37;
  v24 = GetProcAddress(v6, "ClusterResourceControl");
  a1[16] = (HMODULE)v24;
  if ( !v24 )
    goto LABEL_37;
  v25 = GetProcAddress(v6, "GetClusterResourceState");
  a1[17] = (HMODULE)v25;
  if ( !v25 )
    goto LABEL_37;
  *a1 = v6;
  v26 = 261;
  v27 = "RESUTILS.DLL";
  while ( *v27 )
  {
    ++v27;
    if ( !--v26 )
      goto LABEL_36;
  }
  FastDBCSToUnicode(0, "RESUTILS.DLL", -1, v37, 261);
  v28 = SOS_OS::SOSLoadLibraryW(v37, 1, 0, 0);
  v6 = v28;
  if ( !v28 )
    goto LABEL_37;
  v29 = GetProcAddress(v28, "ResUtilFindSzProperty");
  a1[19] = (HMODULE)v29;
  if ( !v29 )
    goto LABEL_37;
  v30 = GetProcAddress(v6, "ResUtilResourceTypesEqual");
  a1[20] = (HMODULE)v30;
  if ( !v30 )
    goto LABEL_37;
  a1[18] = v6;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v35) = 0;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni.cpp",
      "LoadClusterResourceLibraries",
      600,
      L"RET|SNI%d{WINERR}\n",
      v35);
  }
LABEL_48:
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni.cpp", "LoadClusterResourceLibraries", 459, v31);
  return v4;
}

```

## disassembly

```asm
0x100422210  mov     rax, rsp
0x100422213  push    rdi
0x100422214  push    r14
0x100422216  push    r15
0x100422218  sub     rsp, 490h
0x10042221f  mov     [rsp+4A8h+var_468], 0FFFFFFFFFFFFFFFEh
0x100422228  mov     [rax+10h], rbx
0x10042222c  mov     [rax+18h], rbp
0x100422230  mov     [rax+20h], rsi
0x100422234  mov     rax, cs:__security_cookie
0x10042223b  xor     rax, rsp
0x10042223e  mov     [rsp+4A8h+var_28], rax
0x100422246  mov     rdi, rcx
0x100422249  lea     r14, aSqlCommonDkSni_13; "sql\\common\\dk\\sni\\src\\sni.cpp"
0x100422250  mov     [rsp+4A8h+var_460], r14
0x100422255  lea     r15, aLoadclusterres; "LoadClusterResourceLibraries"
0x10042225c  mov     [rsp+4A8h+var_458], r15
0x100422261  mov     [rsp+4A8h+var_450], 1CBh
0x100422269  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422270  jz      short loc_10042228F
0x100422272  mov     [rsp+4A8h+var_488], rcx
0x100422277  lea     r9, aApiSnipcluster; "API|SNIpClusterApi: %p{CLUSTER_API*}\n"
0x10042227e  mov     r8d, 1CBh; int
0x100422284  mov     rdx, r15; char *
0x100422287  mov     rcx, r14; char *
0x10042228a  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x10042228f  mov     ecx, 105h
0x100422294  lea     rax, aClusapiDll; "CLUSAPI.DLL"
0x10042229b  nop     dword ptr [rax+rax+00h]
0x1004222a0  xor     esi, esi
0x1004222a2  cmp     [rax], sil
0x1004222a5  jz      short loc_1004222B9
0x1004222a7  inc     rax
0x1004222aa  sub     rcx, 1
0x1004222ae  jnz     short loc_1004222A0
0x1004222b0  test    rcx, rcx
0x1004222b3  jz      loc_100422601
0x1004222b9  mov     dword ptr [rsp+4A8h+var_488], 105h
0x1004222c1  lea     r9, [rsp+4A8h+var_448]
0x1004222c6  mov     r8d, 0FFFFFFFFh
0x1004222cc  lea     rdx, aClusapiDll; "CLUSAPI.DLL"
0x1004222d3  xor     ecx, ecx
0x1004222d5  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x1004222db  xor     r9d, r9d
0x1004222de  xor     r8d, r8d
0x1004222e1  lea     edx, [r9+1]
0x1004222e5  lea     rcx, [rsp+4A8h+var_448]
0x1004222ea  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x1004222f0  mov     rbx, rax
0x1004222f3  test    rax, rax
0x1004222f6  jz      loc_10042260F
0x1004222fc  lea     rdx, aOpencluster; "OpenCluster"
0x100422303  mov     rcx, rax; hModule
0x100422306  call    cs:__imp_GetProcAddress
0x10042230c  mov     [rdi+8], rax
0x100422310  test    rax, rax
0x100422313  jz      loc_10042260F
0x100422319  lea     rdx, aClosecluster; "CloseCluster"
0x100422320  mov     rcx, rbx; hModule
0x100422323  call    cs:__imp_GetProcAddress
0x100422329  mov     [rdi+10h], rax
0x10042232d  test    rax, rax
0x100422330  jz      loc_10042260F
0x100422336  lea     rdx, aOpenclusterres; "OpenClusterResource"
0x10042233d  mov     rcx, rbx; hModule
0x100422340  call    cs:__imp_GetProcAddress
0x100422346  mov     [rdi+18h], rax
0x10042234a  test    rax, rax
0x10042234d  jz      loc_10042260F
0x100422353  lea     rdx, aCloseclusterre; "CloseClusterResource"
0x10042235a  mov     rcx, rbx; hModule
0x10042235d  call    cs:__imp_GetProcAddress
0x100422363  mov     [rdi+20h], rax
0x100422367  test    rax, rax
0x10042236a  jz      loc_10042260F
0x100422370  lea     rdx, aClusteropenenu; "ClusterOpenEnum"
0x100422377  mov     rcx, rbx; hModule
0x10042237a  call    cs:__imp_GetProcAddress
0x100422380  mov     [rdi+28h], rax
0x100422384  test    rax, rax
0x100422387  jz      loc_10042260F
0x10042238d  lea     rdx, aClusterenum; "ClusterEnum"
0x100422394  mov     rcx, rbx; hModule
0x100422397  call    cs:__imp_GetProcAddress
0x10042239d  mov     [rdi+30h], rax
0x1004223a1  test    rax, rax
0x1004223a4  jz      loc_10042260F
0x1004223aa  lea     rdx, aClustercloseen; "ClusterCloseEnum"
0x1004223b1  mov     rcx, rbx; hModule
0x1004223b4  call    cs:__imp_GetProcAddress
0x1004223ba  mov     [rdi+38h], rax
0x1004223be  test    rax, rax
0x1004223c1  jz      loc_10042260F
0x1004223c7  lea     rdx, aClusterresourc_1; "ClusterResourceOpenEnum"
0x1004223ce  mov     rcx, rbx; hModule
0x1004223d1  call    cs:__imp_GetProcAddress
0x1004223d7  mov     [rdi+40h], rax
0x1004223db  test    rax, rax
0x1004223de  jz      loc_10042260F
0x1004223e4  lea     rdx, aClusterresourc; "ClusterResourceEnum"
0x1004223eb  mov     rcx, rbx; hModule
0x1004223ee  call    cs:__imp_GetProcAddress
0x1004223f4  mov     [rdi+48h], rax
0x1004223f8  test    rax, rax
0x1004223fb  jz      loc_10042260F
0x100422401  lea     rdx, aClusterresourc_0; "ClusterResourceCloseEnum"
0x100422408  mov     rcx, rbx; hModule
0x10042240b  call    cs:__imp_GetProcAddress
0x100422411  mov     [rdi+50h], rax
0x100422415  test    rax, rax
0x100422418  jz      loc_10042260F
0x10042241e  lea     rdx, aClustergroupop; "ClusterGroupOpenEnum"
0x100422425  mov     rcx, rbx; hModule
0x100422428  call    cs:__imp_GetProcAddress
0x10042242e  mov     [rdi+68h], rax
0x100422432  test    rax, rax
0x100422435  jz      loc_10042260F
0x10042243b  lea     rdx, aClustergroupcl; "ClusterGroupCloseEnum"
0x100422442  mov     rcx, rbx; hModule
0x100422445  call    cs:__imp_GetProcAddress
0x10042244b  mov     [rdi+70h], rax
0x10042244f  test    rax, rax
0x100422452  jz      loc_10042260F
0x100422458  lea     rdx, aOpenclustergro; "OpenClusterGroup"
0x10042245f  mov     rcx, rbx; hModule
0x100422462  call    cs:__imp_GetProcAddress
0x100422468  mov     [rdi+58h], rax
0x10042246c  test    rax, rax
0x10042246f  jz      loc_10042260F
0x100422475  lea     rdx, aCloseclustergr; "CloseClusterGroup"
0x10042247c  mov     rcx, rbx; hModule
0x10042247f  call    cs:__imp_GetProcAddress
0x100422485  mov     [rdi+60h], rax
0x100422489  test    rax, rax
0x10042248c  jz      loc_10042260F
0x100422492  lea     rdx, aClustergroupop; "ClusterGroupOpenEnum"
0x100422499  mov     rcx, rbx; hModule
0x10042249c  call    cs:__imp_GetProcAddress
0x1004224a2  mov     [rdi+68h], rax
0x1004224a6  test    rax, rax
0x1004224a9  jz      loc_10042260F
0x1004224af  lea     rdx, aClustergroupcl; "ClusterGroupCloseEnum"
0x1004224b6  mov     rcx, rbx; hModule
0x1004224b9  call    cs:__imp_GetProcAddress
0x1004224bf  mov     [rdi+70h], rax
0x1004224c3  test    rax, rax
0x1004224c6  jz      loc_10042260F
0x1004224cc  lea     rdx, aClustergroupen; "ClusterGroupEnum"
0x1004224d3  mov     rcx, rbx; hModule
0x1004224d6  call    cs:__imp_GetProcAddress
0x1004224dc  mov     [rdi+78h], rax
0x1004224e0  test    rax, rax
0x1004224e3  jz      loc_10042260F
0x1004224e9  lea     rdx, aClusterresourc_2; "ClusterResourceControl"
0x1004224f0  mov     rcx, rbx; hModule
0x1004224f3  call    cs:__imp_GetProcAddress
0x1004224f9  mov     [rdi+80h], rax
0x100422500  test    rax, rax
0x100422503  jz      loc_10042260F
0x100422509  lea     rdx, aGetclusterreso; "GetClusterResourceState"
0x100422510  mov     rcx, rbx; hModule
0x100422513  call    cs:__imp_GetProcAddress
0x100422519  mov     [rdi+88h], rax
0x100422520  test    rax, rax
0x100422523  jz      loc_10042260F
0x100422529  mov     [rdi], rbx
0x10042252c  mov     ecx, 105h
0x100422531  lea     rax, aResutilsDll; "RESUTILS.DLL"
0x100422538  cmp     [rax], sil
0x10042253b  jz      short loc_10042254F
0x10042253d  inc     rax
0x100422540  sub     rcx, 1
0x100422544  jnz     short loc_100422538
0x100422546  test    rcx, rcx
0x100422549  jz      loc_100422601
0x10042254f  mov     dword ptr [rsp+4A8h+var_488], 105h
0x100422557  lea     r9, [rsp+4A8h+var_238]
0x10042255f  mov     r8d, 0FFFFFFFFh
0x100422565  lea     rdx, aResutilsDll; "RESUTILS.DLL"
0x10042256c  xor     ecx, ecx
0x10042256e  call    cs:__imp_?FastDBCSToUnicode@@YAHIPEBDHPEA_WH@Z; FastDBCSToUnicode(uint,char const *,int,wchar_t *,int)
0x100422574  xor     r9d, r9d
0x100422577  xor     r8d, r8d
0x10042257a  lea     edx, [r9+1]
0x10042257e  lea     rcx, [rsp+4A8h+var_238]
0x100422586  call    cs:__imp_?SOSLoadLibraryW@SOS_OS@@SAPEAUHINSTANCE__@@PEB_WH0H@Z; SOS_OS::SOSLoadLibraryW(wchar_t const *,int,wchar_t const *,int)
0x10042258c  mov     rbx, rax
0x10042258f  test    rax, rax
0x100422592  jz      short loc_10042260F
0x100422594  lea     rdx, aResutilfindszp; "ResUtilFindSzProperty"
0x10042259b  mov     rcx, rax; hModule
0x10042259e  call    cs:__imp_GetProcAddress
0x1004225a4  mov     [rdi+98h], rax
0x1004225ab  test    rax, rax
0x1004225ae  jz      short loc_10042260F
0x1004225b0  lea     rdx, aResutilresourc; "ResUtilResourceTypesEqual"
0x1004225b7  mov     rcx, rbx; hModule
0x1004225ba  call    cs:__imp_GetProcAddress
0x1004225c0  mov     [rdi+0A0h], rax
0x1004225c7  test    rax, rax
0x1004225ca  jz      short loc_10042260F
0x1004225cc  mov     [rdi+90h], rbx
0x1004225d3  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004225da  jz      loc_1004226B9
0x1004225e0  mov     dword ptr [rsp+4A8h+var_488], esi
0x1004225e4  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004225eb  mov     r8d, 258h; int
0x1004225f1  mov     rdx, r15; char *
0x1004225f4  mov     rcx, r14; char *
0x1004225f7  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004225fc  jmp     loc_1004226B9
0x100422601  mov     ecx, 7Bh ; '{'; dwErrCode
0x100422606  call    cs:__imp_SetLastError
0x10042260c  mov     rbx, rsi
0x10042260f  call    cs:__imp_GetLastError
0x100422615  mov     ebp, eax
0x100422617  mov     rcx, [rdi]; hLibModule
0x10042261a  test    rcx, rcx
0x10042261d  jz      short loc_100422628
0x10042261f  call    cs:__imp_FreeLibrary
0x100422625  mov     [rdi], rsi
0x100422628  mov     rcx, [rdi+90h]; hLibModule
0x10042262f  test    rcx, rcx
0x100422632  jz      short loc_100422641
0x100422634  call    cs:__imp_FreeLibrary
0x10042263a  mov     [rdi+90h], rsi
0x100422641  test    rbx, rbx
0x100422644  jz      short loc_10042264F
0x100422646  mov     rcx, rbx; hLibModule
0x100422649  call    cs:__imp_FreeLibrary
0x10042264f  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422656  jz      short loc_100422680
0x100422658  mov     [rsp+4A8h+var_478], ebp
0x10042265c  mov     [rsp+4A8h+var_480], esi
0x100422660  mov     dword ptr [rsp+4A8h+var_488], 7
0x100422668  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10042266f  mov     r8d, 271h; int
0x100422675  mov     rdx, r15; char *
0x100422678  mov     rcx, r14; char *
0x10042267b  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100422680  mov     r8d, 0C3B4h
0x100422686  mov     edx, ebp
0x100422688  mov     ecx, 7
0x10042268d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422692  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100422699  jz      short loc_1004226B7
0x10042269b  mov     dword ptr [rsp+4A8h+var_488], ebp
0x10042269f  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004226a6  mov     r8d, 273h; int
0x1004226ac  mov     rdx, r15; char *
0x1004226af  mov     rcx, r14; char *
0x1004226b2  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004226b7  mov     esi, ebp
0x1004226b9  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004226c0  jz      short loc_1004226D3
0x1004226c2  mov     r8d, 1CBh; int
0x1004226c8  mov     rdx, r15; char *
0x1004226cb  mov     rcx, r14; char *
0x1004226ce  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004226d3  mov     eax, esi
0x1004226d5  mov     rcx, [rsp+4A8h+var_28]
0x1004226dd  xor     rcx, rsp; StackCookie
0x1004226e0  call    __security_check_cookie
0x1004226e5  lea     r11, [rsp+4A8h+var_18]
0x1004226ed  mov     rbx, [r11+28h]
0x1004226f1  mov     rbp, [r11+30h]
0x1004226f5  mov     rsi, [r11+38h]
0x1004226f9  mov     rsp, r11
0x1004226fc  pop     r15
0x1004226fe  pop     r14
0x100422700  pop     rdi
0x100422701  retn
```
