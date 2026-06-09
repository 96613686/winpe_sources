# DecodePayload

- ea: `0x180043390`
- end: `0x1800457c4`
- name: `DecodePayload`
- size: `9268`
- prototype: `int __fastcall(__int64, void *, unsigned int, unsigned __int16 *, unsigned int, __int64, struct FormatContext *, size_t Size, _DWORD *, void **)`
- caller_count: `1`
- callee_count: `31`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800115dc`

## callees

- `0x18000f7d4`
- `0x1800113a8`
- `0x1800117c8`
- `0x180012f5c`
- `0x18001eaa4`
- `0x1800207c0`
- `0x180021460`
- `0x180021490`
- `0x18002167c`
- `0x180021c58`
- `0x180023b05`
- `0x180042f7c`
- `0x1800432ec`
- `0x180043390`
- `0x1800457cc`
- `0x1800457fc`
- `0x18004582c`
- `0x180045b68`
- `0x180045ff4`
- `0x180046850`
- `0x180046a24`
- `0x180046c5c`
- `0x180046d1c`
- `0x180046d94`
- `0x180046e4c`
- `0x180046ecc`
- `0x180047054`
- `0x1800472c4`
- `0x180047310`
- `0x180049fc0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004550c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004550c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180045355`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180045355`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004400b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x18004400b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180044020`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180044020`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043b5b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043fc4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043fe0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043ff5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043b5b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043fc4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043fe0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180043ff5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043b9c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180043b9c`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180043834`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800453b7`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180043834`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800453b7`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180043a91`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800453f6`
- `ntdll!RtlIpv6AddressToStringExW` at `0x180043a91`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800453f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800448e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800448e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004489e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004489e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800442c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800452d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800452fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800452fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800442b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800442b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044348`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180044348`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180044319`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800443c4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180044319`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800443c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800452ce`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18004526c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18004526c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180043766`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180043a25`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180043e54`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180043766`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180043a25`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180043e54`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180045237`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180045237`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNetEventSymbolicName` at `0x18004440a`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNetEventSymbolicName` at `0x18004440a`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisOidSymbolicName` at `0x1800440e6`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisOidSymbolicName` at `0x1800440e6`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisSymbolicName` at `0x180044141`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisSymbolicName` at `0x180044141`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800452a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800452a3`
- `WS2_32!WSAAddressToStringW` at `0x180045417`
- `WS2_32!WSAAddressToStringW` at `0x180045417`

## string_xrefs

- `0x1800442cb`: `!ItemMerror %u : LoadLibrary of %s failed %d!`
- `0x1800449fb`: `ID: %u: eventType: %u: Component: `

## pseudocode

```c
int __fastcall DecodePayload(
        __int64 a1,
        void *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        __int64 a6,
        struct FormatContext *a7,
        size_t Size,
        _DWORD *a9,
        void **a10)
{
  unsigned __int16 *v11; // rbx
  _DWORD *v12; // r14
  unsigned __int64 v13; // rax
  wchar_t *v14; // rcx
  char *v15; // r11
  WCHAR *v16; // r9
  struct in_addr *v17; // r13
  __int64 v18; // rcx
  unsigned int (*v19)(unsigned __int16 *, ...); // rbx
  unsigned __int16 *v20; // r15
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned __int8 *p_s_b1; // r14
  __int64 s_w1; // r12
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // edi
  __int16 v28; // r12
  int v29; // edi
  int v30; // edi
  int v31; // edi
  int v32; // edi
  int v33; // edi
  int v34; // edi
  int v35; // edi
  int v36; // edi
  int v37; // edi
  int v38; // edi
  int v39; // edi
  unsigned int v40; // edi
  __int64 v41; // rdi
  void **v42; // rbx
  const CHAR *v43; // rax
  void **v44; // rbx
  WCHAR *v45; // rax
  size_t v46; // r8
  __int64 v47; // rbx
  const CHAR *v48; // rdi
  __int64 v49; // r9
  LPWSTR v50; // rbx
  int s_b3; // ecx
  int s_b2; // eax
  __int64 s_b1; // r9
  __int64 v54; // r15
  __int16 v55; // bx
  unsigned __int16 v56; // bx
  void **v57; // r14
  void **v58; // rdi
  WCHAR *v59; // r14
  const CHAR *v60; // rbx
  const unsigned __int16 *v61; // r8
  unsigned __int64 v62; // rdx
  LPWSTR v63; // r9
  int v64; // edi
  int v65; // edi
  int v66; // edi
  int v67; // edi
  int v68; // edi
  int v69; // edi
  const wchar_t *v70; // rbx
  const wchar_t *v71; // r14
  wchar_t *v72; // rax
  __int64 v73; // rcx
  LPWSTR v74; // r15
  const wchar_t *v75; // r14
  wchar_t *v76; // rax
  unsigned __int16 *v77; // rdi
  wchar_t *v78; // rcx
  unsigned __int64 v79; // rbx
  unsigned __int16 *v80; // rcx
  unsigned __int64 v81; // rdx
  LPWSTR *v82; // rdi
  unsigned int v83; // ebx
  LPWSTR v84; // rax
  LPCCH v85; // rdx
  BOOL v86; // r15d
  int v87; // eax
  unsigned int v88; // r14d
  __int64 v89; // rdi
  __int64 v90; // rbx
  struct in_addr *j; // r12
  CHAR v92; // cl
  char *v93; // rcx
  WCHAR *v94; // rbx
  const CHAR *v95; // r8
  unsigned int v96; // edi
  unsigned __int16 *v97; // rbx
  wchar_t *i; // rcx
  wchar_t *v99; // rax
  wchar_t *v100; // r14
  wchar_t *v101; // rax
  wchar_t *v102; // rbx
  const wchar_t *v103; // rdi
  wchar_t *v104; // rax
  unsigned int v105; // eax
  int v106; // edi
  int v107; // edi
  int v108; // edi
  int v109; // edi
  int v110; // edi
  int v111; // edi
  int v112; // edi
  struct in_addr v113; // ebx
  __int64 NTStatusSymbolicName; // rax
  __int64 v115; // r9
  unsigned __int16 *v116; // rcx
  unsigned __int64 v117; // rdx
  const unsigned __int16 *v118; // r8
  struct in_addr v119; // ebx
  struct in_addr v120; // ebx
  const WCHAR *v121; // rcx
  DWORD v122; // ebx
  HMODULE Library; // rax
  HMODULE v124; // rdi
  __int64 v125; // r9
  unsigned __int16 *v126; // rbx
  struct in_addr v127; // ebx
  struct in_addr S_addr; // ebx
  __int64 NetEventSymbolicName; // rax
  unsigned __int64 v130; // rdx
  int v131; // edi
  int v132; // edi
  int v133; // edi
  int v134; // edi
  int v135; // edi
  int v136; // edi
  unsigned int v137; // edi
  const unsigned __int16 *v138; // r8
  unsigned __int64 v139; // rdx
  __int64 v140; // rcx
  __int64 WinErrorSymbolicName; // rax
  __int64 v142; // rcx
  signed __int64 v143; // r13
  unsigned int v144; // ebx
  int v145; // r15d
  const unsigned __int16 *v146; // r8
  unsigned __int16 *v147; // r14
  wchar_t *v148; // rax
  unsigned int v149; // r12d
  const unsigned __int16 *v150; // rdi
  unsigned __int16 *v151; // rcx
  unsigned __int64 v152; // rdx
  const wchar_t *v153; // rcx
  size_t v154; // r8
  int v155; // edi
  int v156; // edi
  int v157; // edi
  int v158; // edi
  int v159; // edi
  int v160; // edi
  struct FormatContext *v161; // r14
  struct in_addr v162; // ebx
  signed __int64 v163; // rcx
  struct in_addr *v164; // r9
  UCHAR *v165; // rcx
  unsigned __int64 v166; // rdi
  const unsigned __int16 *v167; // r14
  __int64 v168; // r15
  const char *v169; // r12
  __int16 v170; // ax
  __int16 v171; // di
  unsigned int v172; // edi
  int v173; // r14d
  wchar_t *v174; // rcx
  const unsigned __int16 *v175; // rax
  __int64 v176; // rdi
  WCHAR *v177; // r12
  __int16 v178; // ax
  __int16 v179; // r14
  unsigned int v180; // r14d
  unsigned __int16 *v181; // r10
  unsigned int v182; // edi
  const unsigned __int16 *v183; // rax
  __int16 v184; // cx
  char v185; // al
  int v186; // r15d
  const unsigned __int16 *v187; // rax
  const wchar_t *v188; // rcx
  void **v189; // r14
  UCHAR *p_s_b3; // rbx
  __int64 v191; // r15
  unsigned __int64 v192; // rdi
  WCHAR *v193; // r14
  void *v194; // r10
  char *v195; // rax
  LPWSTR v196; // r8
  unsigned int v197; // r14d
  _BYTE *v198; // rdx
  __int64 v199; // r9
  unsigned __int64 k; // rax
  __int16 v201; // dx
  __int16 v202; // ax
  unsigned __int16 v203; // dx
  unsigned __int16 v204; // ax
  unsigned __int16 v205; // cx
  LPWSTR v206; // rbx
  unsigned __int64 v207; // r12
  __int64 v208; // r15
  DWORD LengthSid; // edi
  LPWSTR v210; // r14
  size_t v211; // r8
  size_t v212; // r8
  unsigned __int64 v213; // rbx
  unsigned __int64 v214; // r14
  char *v215; // rax
  USHORT *p_s_w2; // rdx
  char *v217; // r13
  __int16 v218; // di
  unsigned int v219; // edx
  __int64 v220; // r9
  __int64 v221; // rcx
  unsigned int v222; // ecx
  __int64 *v223; // rcx
  wchar_t *v224; // rcx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-F0h]
  unsigned int cchWideChar; // [rsp+28h] [rbp-E8h]
  unsigned int cchWideChara; // [rsp+28h] [rbp-E8h]
  va_list *Arguments; // [rsp+30h] [rbp-E0h]
  unsigned __int16 *AddressString; // [rsp+98h] [rbp-78h]
  unsigned int v232; // [rsp+A0h] [rbp-70h] BYREF
  void *Block; // [rsp+A8h] [rbp-68h] BYREF
  unsigned __int16 *v234; // [rsp+B0h] [rbp-60h] BYREF
  LPWSTR SubStr; // [rsp+B8h] [rbp-58h]
  unsigned int v236; // [rsp+C0h] [rbp-50h]
  __int64 v237; // [rsp+C8h] [rbp-48h]
  void *Src; // [rsp+D0h] [rbp-40h]
  __int64 v239; // [rsp+D8h] [rbp-38h]
  LPCCH lpMultiByteStr; // [rsp+E0h] [rbp-30h]
  struct in_addr Address; // [rsp+E8h] [rbp-28h] BYREF
  ULONG dwAddressStringLength; // [rsp+ECh] [rbp-24h] BYREF
  unsigned int *v243; // [rsp+F0h] [rbp-20h]
  unsigned int v244; // [rsp+F8h] [rbp-18h] BYREF
  unsigned int v245; // [rsp+FCh] [rbp-14h] BYREF
  DWORD cchReferencedDomainName; // [rsp+100h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+104h] [rbp-Ch] BYREF
  int v248; // [rsp+108h] [rbp-8h]
  void **v249; // [rsp+110h] [rbp+0h]
  void **v250; // [rsp+118h] [rbp+8h]
  _DWORD *v251; // [rsp+120h] [rbp+10h]
  ULONG AddressStringLength; // [rsp+128h] [rbp+18h] BYREF
  ULONG v253; // [rsp+12Ch] [rbp+1Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+130h] [rbp+20h] BYREF
  unsigned int *v255; // [rsp+138h] [rbp+28h]
  wchar_t *EndPtr; // [rsp+140h] [rbp+30h] BYREF
  wchar_t *Context; // [rsp+148h] [rbp+38h] BYREF
  wchar_t *v258; // [rsp+150h] [rbp+40h] BYREF
  struct FormatContext *v259; // [rsp+158h] [rbp+48h]
  __int64 v260; // [rsp+160h] [rbp+50h]
  unsigned __int16 *v261; // [rsp+168h] [rbp+58h]
  __int64 v262; // [rsp+170h] [rbp+60h]
  unsigned __int64 v263; // [rsp+178h] [rbp+68h]
  char v264[16]; // [rsp+180h] [rbp+70h] BYREF
  LPWSTR StringSid[2]; // [rsp+190h] [rbp+80h] BYREF
  __int128 v266; // [rsp+1A0h] [rbp+90h] BYREF
  __int128 v267; // [rsp+1B0h] [rbp+A0h]
  __int16 v268; // [rsp+1C0h] [rbp+B0h]
  struct in6_addr v269; // [rsp+1D0h] [rbp+C0h] BYREF
  char v270[32]; // [rsp+1E0h] [rbp+D0h] BYREF
  WCHAR szAddressString; // [rsp+200h] [rbp+F0h] BYREF
  char v272[142]; // [rsp+202h] [rbp+F2h] BYREF
  unsigned __int16 v273[24]; // [rsp+290h] [rbp+180h] BYREF
  WCHAR Name[128]; // [rsp+2C0h] [rbp+1B0h] BYREF
  WCHAR ReferencedDomainName[128]; // [rsp+3C0h] [rbp+2B0h] BYREF

  v11 = a4;
  v12 = a9;
  v262 = a6;
  v259 = a7;
  v236 = a3;
  Src = a2;
  v260 = a1;
  v261 = a4;
  v250 = a10;
  v251 = a9;
  AddressString = a4;
  v255 = (unsigned int *)(a10 + 3);
  v249 = a10 + 2;
  if ( ResizeBuffer(0x4000u, a10 + 2, (unsigned int *)a10 + 6) == 8
    || (lpMultiByteStr = (LPCCH)a10[2],
        v243 = (unsigned int *)(a10 + 1),
        ResizeBuffer(0x8000u, a10, (unsigned int *)a10 + 2) == 8) )
  {
    v13 = (unsigned __int64)TracePrinter;
    if ( !TracePrinter )
      goto LABEL_469;
    v14 = (wchar_t *)L"Not enough memory";
    goto LABEL_4;
  }
  v13 = *(_QWORD *)(a1 + 32);
  v15 = (char *)Src;
  v16 = (WCHAR *)*a10;
  v17 = (struct in_addr *)Src;
  ++*(_DWORD *)(a1 + 8);
  v18 = *(_QWORD *)v13;
  v19 = TracePrinter;
  v20 = AddressString;
  SubStr = v16;
  v263 = v13;
  for ( StringSid[0] = &v17->S_un.S_un_w.s_w1; ; StringSid[0] = &v17->S_un.S_un_w.s_w1 )
  {
    v239 = v18;
    v21 = 2;
    if ( v13 == v18 )
      goto LABEL_468;
    v22 = v236;
    LODWORD(v13) = (_DWORD)v17 - (_DWORD)v15;
    if ( (int)v17 - (int)v15 >= v236 )
      goto LABEL_468;
    LODWORD(v13) = *v12;
    if ( *v12 == 256 )
      goto LABEL_468;
    v248 = 0;
    p_s_b1 = &v17->S_un.S_un_b.s_b1;
    v237 = 0;
    s_w1 = 0;
    if ( v19 )
    {
      v25 = (unsigned int)(v13 + 1);
      v26 = *(_QWORD *)(v18 + 16);
      Arguments = (va_list *)&v15[v236 - (_QWORD)v17];
      cchWideChar = (unsigned int)v17;
      HIDWORD(lpWideCharStr) = HIDWORD((&str_item)[*(int *)(v18 + 40)]);
      if ( DebugExtPrint )
        TracePrinterExt((wchar_t *)L"Param %03d (%s) itemType %3d(%s) data Ptr %p, left %d\n", v25, v26);
      else
        v19(L"Param %03d (%s) itemType %3d(%s) data Ptr %p, left %d\n", v25, v26);
      v18 = v239;
      v22 = v236;
      v15 = (char *)Src;
      v19 = TracePrinter;
      v21 = 2;
    }
    v27 = *(_DWORD *)(v18 + 40);
    LODWORD(v13) = 33;
    if ( v27 > 33 )
      break;
    if ( v27 == 33 )
    {
      s_w1 = 1;
LABEL_160:
      EndPtr = 0;
      v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
      v232 = 0;
      Context = 0;
      if ( (__int64)v13 < s_w1 )
        goto LABEL_463;
      v96 = 0;
      memcpy_0(&v232, v17, s_w1);
      v97 = SubStr;
      memset_0(SubStr, 0, 0x8000u);
      StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"!0x%X!", v232);
      StringCchPrintfW(v97, 0x4000u, L"%s", *(_QWORD *)(v239 + 32));
      for ( i = v97; ; i = 0 )
      {
        v99 = o_wcstok_s_0(i, L",", &Context);
        v100 = v99;
        if ( !v99 )
          break;
        v101 = wcsstr(v99, L"=");
        v102 = v101;
        if ( v101 )
        {
          v103 = v101 + 1;
          v104 = wcsstr(v101 + 1, L"0X");
          if ( v104 || (v104 = wcsstr(v103, L"0x")) != 0 )
            v105 = wcstoul(v104, &EndPtr, 16);
          else
            v105 = wcstol(v103, &EndPtr, 10);
          v96 = v105;
        }
        if ( v232 == v96 )
        {
          cchWideChar = (unsigned int)v100;
          LODWORD(lpWideCharStr) = v102 - v100;
          StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"0x%08x(%.*s)", v96, lpWideCharStr);
          goto LABEL_454;
        }
        ++v96;
      }
      goto LABEL_454;
    }
    LODWORD(v13) = 16;
    v28 = 1;
    if ( v27 > 16 )
    {
      if ( v27 <= 25 )
      {
        if ( v27 != 25 )
        {
          if ( v27 == 17 )
            goto LABEL_377;
          if ( v27 != 18 )
          {
            if ( v27 == 19 )
              goto LABEL_395;
            if ( v27 != 20 )
            {
              if ( v27 != 21 )
              {
                if ( v27 != 22 )
                {
                  if ( v27 == 23 )
                  {
                    s_w1 = 4;
                    if ( (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17] >= 4 )
                    {
                      if ( v17->S_un.S_un_b.s_b3 )
                        s_b3 = v17->S_un.S_un_b.s_b3;
                      else
                        s_b3 = 32;
                      if ( v17->S_un.S_un_b.s_b2 )
                        s_b2 = v17->S_un.S_un_b.s_b2;
                      else
                        s_b2 = 32;
                      if ( v17->S_un.S_un_b.s_b1 )
                        s_b1 = v17->S_un.S_un_b.s_b1;
                      else
                        s_b1 = 32;
                      cchWideChar = s_b3;
                      LODWORD(lpWideCharStr) = s_b2;
                      StringCchPrintfW(v20, (unsigned __int64)a5 >> 1, L"%c%c%c%c", s_b1, lpWideCharStr);
                      goto LABEL_455;
                    }
                    StringCchCopyW(v20, (unsigned __int64)a5 >> 1, L"0000");
                    if ( v19 )
                    {
                      if ( DebugExtPrint )
                        TracePrinterExt((wchar_t *)L"ItemChar4 Invalid payload length");
                      else
                        v19(L"ItemChar4 Invalid payload length");
                      goto LABEL_455;
                    }
                  }
                  else
                  {
                    AddressStringLength = a5 >> 1;
                    Address = 0;
                    v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
                    if ( (__int64)v13 < 4 )
                      goto LABEL_463;
                    s_w1 = 4;
                    Address = (struct in_addr)v17->S_un.S_addr;
                    if ( RtlIpv4AddressToStringExW(&Address, 0, AddressString, &AddressStringLength) )
                    {
                      cchWideChar = Address.S_un.S_un_b.s_b3;
                      LODWORD(lpWideCharStr) = Address.S_un.S_un_b.s_b2;
                      StringCchPrintfW(
                        AddressString,
                        (unsigned __int64)a5 >> 1,
                        L"%03d.%03d.%03d.%03d",
                        Address.S_un.S_un_b.s_b1,
                        lpWideCharStr);
                      goto LABEL_454;
                    }
                    v20 = AddressString;
LABEL_455:
                    v19 = TracePrinter;
                  }
                  goto LABEL_456;
                }
LABEL_411:
                cchName = 0;
                v207 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
                cchReferencedDomainName = 0;
                peUse = 0;
                v208 = (unsigned int)v22;
                if ( v207 < 4 )
                  goto LABEL_463;
                if ( !v17->S_un.S_addr )
                {
                  StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"<NULL>");
                  goto LABEL_277;
                }
                LODWORD(v13) = strncmp_0((const char *)v17, "NULL", 4u);
                if ( (_DWORD)v13 )
                {
                  cchName = 128;
                  cchReferencedDomainName = 128;
                  if ( v27 == 64 )
                  {
                    v21 = (unsigned int)Size;
                    if ( (__int64)v207 < (unsigned int)(2 * Size) )
                      goto LABEL_498;
                    v17 = (struct in_addr *)((char *)v17 + ((unsigned int)Size >= 8 ? 16LL : 8LL));
                    LengthSid = 4 * (char)v17->S_un.S_un_b.s_b2 + 8;
                    LODWORD(v13) = LengthSid;
                    if ( (__int64)Src + v208 - (__int64)v17 < LengthSid )
                      goto LABEL_498;
                    v210 = SubStr;
                    v211 = 0x4000;
                    if ( LengthSid < 0x4000 )
                      v211 = LengthSid;
                    memcpy_0(SubStr, v17, v211);
                  }
                  else
                  {
                    v210 = SubStr;
                    v212 = 0x8000;
                    if ( v207 < 0x8000 )
                      v212 = v207;
                    memcpy_0(SubStr, v17, v212);
                    LengthSid = GetLengthSid(v210);
                  }
                  v213 = (unsigned __int64)a5 >> 1;
                  if ( LookupAccountSidLocalW(
                         v210,
                         Name,
                         &cchName,
                         ReferencedDomainName,
                         &cchReferencedDomainName,
                         &peUse) )
                  {
                    StringCchPrintfW(AddressString, v213, L"\\\\%s\\%s", ReferencedDomainName, Name);
                  }
                  else
                  {
                    StringSid[0] = 0;
                    if ( ConvertSidToStringSidW(v210, StringSid) )
                    {
                      StringCchPrintfW(AddressString, v213, L"%s", StringSid[0]);
                      LocalFree(StringSid[0]);
                    }
                    else
                    {
                      LODWORD(lpWideCharStr) = GetLastError();
                      StringCchPrintfW(AddressString, v213, L"%s(%d)", L"System", lpWideCharStr);
                    }
                  }
                  SetLastError(0);
                  s_w1 = LengthSid;
                }
                else
                {
                  s_w1 = 5;
                  StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"<NULL>");
                }
LABEL_454:
                v20 = AddressString;
                goto LABEL_455;
              }
LABEL_395:
              v13 = (unsigned __int64)&v15[v22 - (_QWORD)v17];
              if ( v13 < 2 )
                goto LABEL_463;
              v17 = (struct in_addr *)((char *)v17 + 2);
              if ( v27 == 21 )
              {
                v201 = *p_s_b1;
                v202 = p_s_b1[1];
              }
              else
              {
                v201 = p_s_b1[1];
                v202 = *p_s_b1;
              }
              v203 = v202 + (v201 << 8);
              v204 = 2 * v203;
              if ( v27 != 65 )
                v204 = v203;
              v205 = v204;
              if ( v204 > (__int64)&v15[v22 - (_QWORD)v17] )
              {
                if ( v19 )
                {
                  if ( DebugExtPrint )
                    TracePrinterExt((wchar_t *)L"Corrupted payload. Type = %d", (unsigned int)v27);
                  else
                    v19(L"Corrupted payload. Type = %d", (unsigned int)v27);
                  LOWORD(v15) = (_WORD)Src;
                  v19 = TracePrinter;
                }
                v205 = (_WORD)v15 + v236 - (_WORD)v17;
              }
              s_w1 = v205;
              if ( v205 )
              {
                v206 = SubStr;
                memcpy_0(SubStr, v17, v205);
                v206[(unsigned __int64)(unsigned int)s_w1 >> 1] = 0;
                StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%ws", v206);
                v19 = TracePrinter;
                goto LABEL_243;
              }
              v139 = (unsigned __int64)a5 >> 1;
LABEL_316:
              v116 = AddressString;
              v138 = L"<NULL>";
LABEL_242:
              StringCchCopyW(v116, v139, v138);
LABEL_243:
              v20 = AddressString;
              goto LABEL_456;
            }
          }
          v54 = (unsigned int)v22;
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( v13 < 2 )
            goto LABEL_463;
          v55 = v17->S_un.S_un_b.s_b2;
          if ( v27 == 20 )
            v56 = (v17->S_un.S_un_b.s_b1 << 8) + v55;
          else
            v56 = v17->S_un.S_un_b.s_b1 + (v55 << 8);
          v57 = v249;
          v17 = (struct in_addr *)((char *)v17 + 2);
          if ( ResizeBuffer((unsigned int)v56 + 1, v249, v255) == 8
            || (v58 = v250, lpMultiByteStr = (LPCCH)*v57, ResizeBuffer(2 * ((unsigned int)v56 + 1), v250, v243) == 8) )
          {
LABEL_479:
            v13 = (unsigned __int64)TracePrinter;
            if ( !TracePrinter )
              goto LABEL_468;
            v224 = (wchar_t *)L"Not enough memory";
          }
          else
          {
            s_w1 = v56;
            if ( (__int64)Src + v54 - (__int64)v17 >= v56 )
            {
              v59 = (WCHAR *)*v58;
              SubStr = (LPWSTR)*v58;
              if ( !v56 )
                goto LABEL_394;
              v60 = lpMultiByteStr;
              memcpy_0((void *)lpMultiByteStr, v17, (unsigned int)s_w1);
              v60[s_w1] = 0;
              MultiByteToWideChar(0, 0, v60, -1, v59, *((_DWORD *)v58 + 2) >> 1);
              goto LABEL_94;
            }
            v13 = (unsigned __int64)TracePrinter;
            if ( !TracePrinter )
              goto LABEL_468;
            v224 = L"iMofPtr buffer overflow";
          }
LABEL_481:
          if ( !DebugExtPrint )
          {
LABEL_467:
            LODWORD(v13) = ((__int64 (__fastcall *)(wchar_t *, __int64, __int64))v13)(v224, v21, v22);
            goto LABEL_468;
          }
          goto LABEL_473;
        }
        v253 = a5 >> 1;
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( (__int64)v13 < 16 )
          goto LABEL_463;
        v11 = AddressString;
        v269 = *(struct in6_addr *)&v17->S_un.S_un_b.s_b1;
        if ( !RtlIpv6AddressToStringExW(&v269, 0, 0, AddressString, &v253) )
        {
LABEL_98:
          s_w1 = 16;
          goto LABEL_454;
        }
        v13 = (unsigned __int64)TracePrinter;
        if ( !TracePrinter )
          goto LABEL_469;
        v14 = L"RtlIpv6AddressToStringExW failed to convert IPv6 address";
LABEL_4:
        if ( DebugExtPrint )
          LODWORD(v13) = TracePrinterExt(v14);
        else
          LODWORD(v13) = ((__int64 (__fastcall *)(wchar_t *))v13)(v14);
        goto LABEL_469;
      }
      v64 = v27 - 26;
      if ( !v64 )
      {
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( (__int64)v13 < 6 )
          goto LABEL_463;
        s_w1 = 6;
        cchWideChar = v17->S_un.S_un_b.s_b3;
        LODWORD(lpWideCharStr) = v17->S_un.S_un_b.s_b2;
        StringCchPrintfW(
          AddressString,
          (unsigned __int64)a5 >> 1,
          L"%02X-%02X-%02X-%02X-%02X-%02X",
          v17->S_un.S_un_b.s_b1,
          lpWideCharStr);
        goto LABEL_454;
      }
      v65 = v64 - 1;
      if ( v65 )
      {
        v66 = v65 - 1;
        if ( !v66 )
        {
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( v13 < 2 )
            goto LABEL_463;
          v17 = (struct in_addr *)((char *)v17 + 2);
          v21 = (__int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( !v21 )
            goto LABEL_463;
          s_w1 = -1;
          do
            ++s_w1;
          while ( *(&v17->S_un.S_un_b.s_b1 + s_w1) );
          LODWORD(v13) = s_w1;
          v237 = s_w1;
          if ( v21 < (unsigned int)s_w1 )
            goto LABEL_463;
          if ( !s_w1 )
            goto LABEL_456;
          v85 = lpMultiByteStr;
          v86 = 0;
          v87 = 0;
          v88 = 0;
          LODWORD(v89) = 0;
          LODWORD(v90) = 0;
          for ( j = v17; ; j = (struct in_addr *)((char *)j + 1) )
          {
            v92 = j->S_un.S_un_b.s_b1;
            if ( !j->S_un.S_un_b.s_b1 )
              break;
            v89 = (unsigned int)(v90 + v89);
            LODWORD(v90) = 0;
            if ( v92 == 10 )
            {
              if ( !v88 )
              {
                v85[v89] = 32;
                LODWORD(v90) = 1;
              }
              ++v88;
            }
            else if ( v92 == 34 )
            {
              if ( v86 )
              {
                StringCchPrintfA(v270, 0x20u, "{%dx}", v88);
                v90 = -1;
                do
                  ++v90;
                while ( v270[v90] );
                if ( ResizeBuffer((unsigned int)(v90 + v89), v249, v255) == 8 )
                  goto LABEL_479;
                v93 = (char *)*v249 + (unsigned int)v89;
                lpMultiByteStr = (LPCCH)*v249;
                memcpy_0(v93, v270, (unsigned int)v90);
                v85 = lpMultiByteStr;
              }
              v86 = !v86;
            }
            else if ( !v87 )
            {
              v85[v89] = v92;
              LODWORD(v90) = 1;
            }
            if ( v88 > 1 )
            {
              v87 = 1;
              if ( v86 )
                continue;
            }
            v87 = 0;
          }
          v94 = SubStr;
          v95 = lpMultiByteStr;
          lpMultiByteStr[(unsigned int)v89] = 0;
          MultiByteToWideChar(0, 0, v95, -1, v94, *v243 >> 1);
          StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%ws", v94);
          s_w1 = v237;
          goto LABEL_454;
        }
        v67 = v66 - 1;
        if ( v67 )
        {
          v68 = v67 - 1;
          if ( v68 )
          {
            v69 = v68 - 1;
            if ( v69 )
            {
              if ( v69 != 1 )
                goto LABEL_30;
              s_w1 = 2;
            }
            else
            {
              s_w1 = 4;
            }
            goto LABEL_160;
          }
          s_w1 = (unsigned int)Size;
          StringSid[0] = 0;
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( (__int64)v13 < (unsigned int)Size )
            goto LABEL_463;
          if ( (unsigned int)Size > 8 )
          {
            if ( v19 )
            {
              v224 = L"Invalid pointer size";
              goto LABEL_465;
            }
            goto LABEL_468;
          }
          v70 = *(const wchar_t **)(v260 + 56);
          memcpy_0(StringSid, v17, (unsigned int)Size);
          v71 = SubStr;
          StringCchPrintfW(SubStr, 0x4000u, L"%%%d", (unsigned int)(*v251 + 1));
          v72 = wcsstr(v70, v71);
          if ( !v72 )
            goto LABEL_123;
          v73 = -1;
          do
            ++v73;
          while ( v71[v73] );
          if ( v72[v73] != 33
            || (v74 = SubStr, v75 = &v72[v73 + 1], *SubStr = 37, (v76 = wcschr(v75, 0x21u)) == 0)
            || (v77 = v76 - 1, v76 - 1 <= v75)
            || *v77 == 112 )
          {
LABEL_123:
            v81 = (unsigned __int64)a5 >> 1;
            if ( (_DWORD)Size == 8 )
              StringCchPrintfW(AddressString, v81, L"%016I64X", StringSid[0]);
            else
              StringCchPrintfW(AddressString, v81, L"%08X", LODWORD(StringSid[0]));
            goto LABEL_454;
          }
          v78 = v74 + 1;
          v79 = ((char *)v77 - (char *)v75 - 2) >> 1;
          if ( v79 <= 0x7FFFFFFE )
            StringCopyWorkerW_0(v78, 0x3FFFu, 0, v75, ((char *)v77 - (char *)v75 - 2) >> 1);
          else
            *v78 = 0;
          v80 = &v74[v79 + 1];
          if ( (_DWORD)Size == 4 )
          {
            v63 = (LPWSTR)LODWORD(StringSid[0]);
            v61 = v74;
            *v80 = *v77;
            v62 = (unsigned __int64)a5 >> 1;
            v74[v79 + 2] = 0;
          }
          else
          {
            StringCchPrintfW(v80, 0x3FFFu, L"I64%c", *v77);
            v63 = StringSid[0];
            v61 = v74;
            v62 = (unsigned __int64)a5 >> 1;
          }
        }
        else
        {
          v82 = (LPWSTR *)v250;
          v83 = (unsigned __int16)((_WORD)v15 + v22 - (_WORD)v17);
          if ( ResizeBuffer(v83 + 1, v250, v243) == 8 )
            goto LABEL_479;
          v84 = *v82;
          s_w1 = v83;
          SubStr = *v82;
          if ( !(_WORD)v83 )
            goto LABEL_455;
          v59 = v84;
          memcpy_0(v84, v17, v83);
          v59[(unsigned __int64)v83 >> 1] = 0;
LABEL_94:
          v61 = L"%ws";
          v62 = (unsigned __int64)a5 >> 1;
          v63 = v59;
        }
      }
      else
      {
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 2 )
          goto LABEL_463;
        v61 = L"%u";
        s_w1 = 2;
        v63 = (LPWSTR)((v17->S_un.S_un_b.s_b1 << 8) + (unsigned int)v17->S_un.S_un_b.s_b2);
        v62 = (unsigned __int64)a5 >> 1;
      }
LABEL_95:
      StringCchPrintfW(AddressString, v62, v61, v63);
      goto LABEL_454;
    }
    if ( v27 == 16 )
      goto LABEL_48;
    if ( v27 > 8 )
    {
      v34 = v27 - 9;
      if ( v34 && (v35 = v34 - 1) != 0 && (v36 = v35 - 1) != 0 && (v37 = v36 - 1) != 0 && (v38 = v37 - 1) != 0 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          if ( v39 != 1 )
          {
LABEL_30:
            s_w1 = v237;
            goto LABEL_31;
          }
LABEL_377:
          v189 = v250;
          p_s_b3 = &v17->S_un.S_un_b.s_b3;
          v191 = (unsigned int)v22;
          v192 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)&v17->S_un.S_un_w.s_w2];
          if ( ResizeBuffer(2 * (unsigned int)(v192 >> 1) + 2, v250, v243) == 8 )
            goto LABEL_479;
          v193 = (WCHAR *)*v189;
          v194 = Src;
          v195 = (char *)Src + (unsigned int)v191 - (_QWORD)v17;
          SubStr = v193;
          *v193 = 0;
          if ( (unsigned __int64)v195 >= 2 )
          {
            *(_BYTE *)v193 = v17->S_un.S_un_b.s_b1;
            *((_BYTE *)v193 + 1) = v17->S_un.S_un_b.s_b2;
            if ( *v193 )
            {
              v196 = SubStr;
              v197 = 1;
              if ( v192 >= 2 )
              {
                do
                {
                  v198 = p_s_b3 + 1;
                  LOBYTE(v196[v197]) = *p_s_b3;
                  HIBYTE(v196[v197]) = p_s_b3[1];
                  if ( !v196[v197] )
                  {
                    if ( !--v28 )
                      break;
                    v196[v197] = 9;
                  }
                  p_s_b3 += 2;
                  ++v197;
                }
                while ( (unsigned __int64)v194 + v191 - (_QWORD)(v198 + 1) >= 2 );
                v17 = (struct in_addr *)StringSid[0];
              }
              v199 = v239;
              v196[v197] = 0;
              if ( *(_DWORD *)(v199 + 40) == 17 )
              {
                reduceW(v196);
                v196 = SubStr;
              }
              for ( k = 0; k < v197; ++k )
              {
                if ( v196[k] == 0xFFFF )
                  v196[k] = 0;
              }
              StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%ws", v196);
              s_w1 = 2LL * (v197 + 1);
              goto LABEL_454;
            }
          }
          s_w1 = 2;
LABEL_394:
          StringCchCopyW(AddressString, (unsigned __int64)a5 >> 1, L"<NULL>");
          goto LABEL_454;
        }
LABEL_48:
        v41 = -1;
        do
          ++v41;
        while ( *(&v17->S_un.S_un_b.s_b1 + v41) );
        s_w1 = (unsigned int)(v41 + 1);
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( (__int64)v13 < s_w1 )
          goto LABEL_463;
        if ( (_DWORD)v41 )
        {
          v42 = v249;
          if ( ResizeBuffer((unsigned int)(v41 + 1), v249, v255) == 8 )
            goto LABEL_479;
          v43 = (const CHAR *)*v42;
          v44 = v250;
          lpMultiByteStr = v43;
          if ( ResizeBuffer((unsigned int)(2 * v41 + 2), v250, v243) == 8 )
            goto LABEL_479;
          v45 = (WCHAR *)*v44;
          v46 = (unsigned int)v41;
          v47 = (unsigned int)v41;
          v48 = lpMultiByteStr;
          SubStr = v45;
          memcpy_0((void *)lpMultiByteStr, v17, v46);
          v49 = v239;
          v48[v47] = 0;
          if ( *(_DWORD *)(v49 + 40) == 16 )
            reduce(v48);
          v50 = SubStr;
          MultiByteToWideChar(0, 0, v48, -1, SubStr, *v243 >> 1);
          StringCchPrintfW(v20, (unsigned __int64)a5 >> 1, L"%ws", v50);
          goto LABEL_455;
        }
        StringCchCopyW(v20, (unsigned __int64)a5 >> 1, L"<NULL>");
      }
      else
      {
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 8 )
          goto LABEL_463;
        v40 = a5;
        if ( a5 < 8 )
        {
          if ( v19 )
          {
            if ( DebugExtPrint )
              LODWORD(v13) = TracePrinterExt((wchar_t *)L"TRACEPRT:Decoding Buffer too small", 2);
            else
              LODWORD(v13) = v19(L"TRACEPRT:Decoding Buffer too small", 2);
          }
          v11 = AddressString;
          goto LABEL_470;
        }
        s_w1 = 8;
        *(_QWORD *)v20 = *(_QWORD *)&v17->S_un.S_un_b.s_b1;
        v248 = 1;
      }
LABEL_456:
      v12 = v251;
      *(_QWORD *)(v262 + 8LL * (unsigned int)*v251) = v20;
      if ( v248 )
      {
        v222 = 8;
      }
      else
      {
        v221 = -1;
        do
          ++v221;
        while ( AddressString[v221] );
        v222 = 2 * v221 + 2;
        v20 = AddressString;
      }
      v20 = (unsigned __int16 *)((char *)v20 + v222);
      a5 -= v222;
      AddressString = v20;
      goto LABEL_462;
    }
    if ( v27 == 8 )
      goto LABEL_34;
    if ( v27 && (v29 = v27 - 1) != 0 && (v30 = v29 - 1) != 0 )
    {
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( v33 )
          {
            if ( (unsigned int)(v33 - 1) >= 2 )
              goto LABEL_30;
LABEL_34:
            s_w1 = 4;
            goto LABEL_35;
          }
        }
      }
      s_w1 = 2;
    }
    else
    {
      s_w1 = 1;
    }
LABEL_35:
    v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
    if ( (__int64)v13 < s_w1 )
      goto LABEL_463;
    memcpy_0((void *)(v262 + 8LL * (unsigned int)*v251), v17, s_w1);
    v12 = v251;
LABEL_462:
    v223 = (__int64 *)v239;
    v17 = (struct in_addr *)((char *)v17 + s_w1);
    v15 = (char *)Src;
    ++*v12;
    v13 = v263;
    v18 = *v223;
  }
  if ( v27 <= 50 )
  {
    if ( v27 != 50 )
    {
      if ( v27 <= 42 )
      {
        if ( v27 == 42 )
        {
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( v13 < 4 )
            goto LABEL_463;
          S_addr = (struct in_addr)v17->S_un.S_addr;
          s_w1 = 4;
          if ( (unsigned __int8)IsGetNetEventSymbolicNamePresent(v18, 2) )
            NetEventSymbolicName = GetNetEventSymbolicName(S_addr.S_un.S_addr);
          else
            NetEventSymbolicName = 0;
          v130 = (unsigned __int64)a5 >> 1;
          if ( NetEventSymbolicName )
            StringCchPrintfW(AddressString, v130, L"%S", NetEventSymbolicName);
          else
            StringCchPrintfW(AddressString, v130, L"NETEVENT=%8X", S_addr.S_un.S_addr);
          goto LABEL_454;
        }
        v106 = v27 - 34;
        if ( !v106 )
        {
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( v13 < 4 )
            goto LABEL_463;
          v127 = (struct in_addr)v17->S_un.S_addr;
          s_w1 = 4;
          if ( FormatMessageW(0x1200u, 0, v17->S_un.S_addr, 0x400u, AddressString, a5 >> 1, 0) )
            goto LABEL_454;
          v61 = L"!NT Error %u unrecognised!";
          v62 = (unsigned __int64)a5 >> 1;
          v63 = (LPWSTR)v127.S_un.S_addr;
          goto LABEL_95;
        }
        v107 = v106 - 1;
        if ( !v107 )
        {
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( v13 < 4 )
            goto LABEL_463;
          v121 = *(const WCHAR **)(v18 + 32);
          s_w1 = 4;
          v122 = v17->S_un.S_addr;
          if ( v121 )
          {
            Library = LoadLibraryExW(v121, 0, 2u);
            v124 = Library;
            if ( Library )
            {
              if ( FormatMessageW(0x1A00u, Library, v122, 0x400u, AddressString, a5 >> 1, 0) )
              {
                v126 = AddressString;
              }
              else
              {
                v125 = v122;
                v126 = AddressString;
                StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"!Module Error %u unrecognised!", v125);
              }
              if ( !FreeLibrary(v124) )
              {
                LODWORD(lpWideCharStr) = GetLastError();
                StringCchPrintfW(
                  v126,
                  (unsigned __int64)a5 >> 1,
                  L"Failed to free library (%s) handle, err = %d",
                  *(_QWORD *)(v239 + 32),
                  lpWideCharStr);
              }
            }
            else
            {
              cchWideChar = GetLastError();
              StringCchPrintfW(
                AddressString,
                (unsigned __int64)a5 >> 1,
                L"!ItemMerror %u : LoadLibrary of %s failed %d!",
                v122,
                *(_QWORD *)(v239 + 32));
            }
            goto LABEL_454;
          }
          v61 = L"! Error %u No Module Name!";
          v62 = (unsigned __int64)a5 >> 1;
          v63 = (LPWSTR)v122;
          goto LABEL_95;
        }
        v108 = v107 - 1;
        if ( v108 )
        {
          v109 = v108 - 1;
          if ( !v109 )
          {
            v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
            if ( v13 < 0x10 )
              goto LABEL_463;
            *(_OWORD *)StringSid = *(_OWORD *)&v17->S_un.S_un_b.s_b1;
            TraceprtGuidToString(AddressString, a5 >> 1, (struct _GUID *)StringSid);
            goto LABEL_98;
          }
          v110 = v109 - 1;
          if ( !v110 )
          {
            v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
            if ( v13 < 4 )
              goto LABEL_463;
            v120 = (struct in_addr)v17->S_un.S_addr;
            s_w1 = 4;
            if ( !v17->S_un.S_addr )
            {
              StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"STATUS_SUCCESS");
              goto LABEL_454;
            }
            NTStatusSymbolicName = FetchNTStatusSymbolicName(v120.S_un.S_addr, 2);
            v115 = v120.S_un.S_addr;
            v116 = AddressString;
            v117 = (unsigned __int64)a5 >> 1;
            if ( !NTStatusSymbolicName )
            {
              StringCchPrintfW(AddressString, v117, L"NTSTATUS=%08X", v120.S_un.S_addr);
              goto LABEL_454;
            }
            goto LABEL_189;
          }
          v111 = v110 - 1;
          if ( !v111 )
          {
            v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
            if ( v13 < 4 )
              goto LABEL_463;
            v119 = (struct in_addr)v17->S_un.S_addr;
            s_w1 = 4;
            NTStatusSymbolicName = FetchWinErrorSymbolicName(v17->S_un.S_addr, 2);
            v115 = v119.S_un.S_addr;
            v116 = AddressString;
            v117 = (unsigned __int64)a5 >> 1;
            if ( !NTStatusSymbolicName )
            {
              StringCchPrintfW(AddressString, v117, L"WINERROR=%8X", v119.S_un.S_addr);
              goto LABEL_454;
            }
            v118 = L"%d(%S)";
LABEL_190:
            StringCchPrintfW(v116, v117, v118, v115, NTStatusSymbolicName);
            goto LABEL_454;
          }
          v112 = v111 - 1;
          if ( v112 )
          {
            if ( v112 == 1 )
            {
              v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
              if ( v13 < 4 )
                goto LABEL_463;
              v113 = (struct in_addr)v17->S_un.S_addr;
              s_w1 = 4;
              if ( (unsigned __int8)IsGetNetEventSymbolicNamePresent(v18, 2) )
              {
                NTStatusSymbolicName = GetNdisOidSymbolicName(v113.S_un.S_addr);
                goto LABEL_188;
              }
LABEL_187:
              NTStatusSymbolicName = 0;
              goto LABEL_188;
            }
LABEL_31:
            ++v17;
            goto LABEL_456;
          }
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
          if ( v13 < 4 )
            goto LABEL_463;
          v113 = (struct in_addr)v17->S_un.S_addr;
          s_w1 = 4;
          if ( !(unsigned __int8)IsGetNetEventSymbolicNamePresent(v18, 2) )
            goto LABEL_187;
          NTStatusSymbolicName = GetNdisSymbolicName(v113.S_un.S_addr);
LABEL_188:
          v115 = v113.S_un.S_addr;
          v116 = AddressString;
          v117 = (unsigned __int64)a5 >> 1;
          if ( NTStatusSymbolicName )
          {
LABEL_189:
            v118 = L"0x%08x(%S)";
            goto LABEL_190;
          }
LABEL_238:
          StringCchPrintfW(v116, v117, L"0x%08x", v115);
          goto LABEL_454;
        }
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 8 )
          goto LABEL_463;
LABEL_206:
        StringSid[0] = *(LPWSTR *)&v17->S_un.S_un_b.s_b1;
        FormatFileTime(v259, AddressString, a5 >> 1, (const union _LARGE_INTEGER *)StringSid, *((_BYTE *)v259 + 160));
LABEL_277:
        s_w1 = 8;
        goto LABEL_454;
      }
      v131 = v27 - 43;
      if ( v131 )
      {
        v132 = v131 - 1;
        if ( v132 )
        {
          v133 = v132 - 1;
          if ( v133 )
          {
            v134 = v133 - 1;
            if ( v134 )
            {
              v135 = v134 - 1;
              if ( v135 )
              {
                v136 = v135 - 1;
                if ( !v136 )
                {
                  v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
                  if ( (__int64)v13 < 8 )
                    goto LABEL_463;
                  s_w1 = 8;
                  StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%g", *(_QWORD *)&v17->S_un.S_un_b.s_b1);
                  goto LABEL_454;
                }
                if ( v136 != 1 )
                  goto LABEL_31;
                v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
                if ( v13 < 4 )
                  goto LABEL_463;
                v137 = v17->S_un.S_addr;
                s_w1 = 4;
                if ( (v17->S_un.S_addr & 0x80000000) == 0 )
                {
                  v116 = AddressString;
                  if ( v137 <= 1 )
                  {
                    v138 = L"S_OK";
                    if ( v137 )
                      v138 = L"S_FALSE";
                    v139 = (unsigned __int64)a5 >> 1;
                    goto LABEL_242;
                  }
                  v117 = (unsigned __int64)a5 >> 1;
                  v115 = v137;
                  goto LABEL_238;
                }
                if ( (v137 & 0x10000000) != 0 )
                {
                  v140 = v137;
                  LODWORD(v140) = v137 & 0xEFFFFFFF;
                  WinErrorSymbolicName = FetchNTStatusSymbolicName(v140, 2);
                  goto LABEL_248;
                }
                v142 = 0;
                if ( (v137 & 0x1FFF0000) == 0x70000 )
                {
                  WinErrorSymbolicName = FetchWinErrorSymbolicName((unsigned __int16)v137, 2);
LABEL_248:
                  v142 = WinErrorSymbolicName;
                }
                v63 = (LPWSTR)v137;
                v62 = (unsigned __int64)a5 >> 1;
                if ( v142 )
                {
                  StringCchPrintfW(AddressString, v62, L"0x%08x(%S)", v137, v142);
                  goto LABEL_454;
                }
                v61 = L"HRESULT=%8X";
                goto LABEL_95;
              }
              v143 = 1;
              v237 = 1;
            }
            else
            {
              v143 = 2;
              v237 = 2;
            }
          }
          else
          {
            v143 = 4;
            v237 = 4;
          }
          v232 = 0;
          v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)p_s_b1];
          v234 = AddressString;
          Block = (void *)((unsigned __int64)a5 >> 1);
          v258 = 0;
          if ( (__int64)v13 < v143 )
          {
            if ( v19 )
            {
              if ( DebugExtPrint )
                LODWORD(v13) = TracePrinterExt((wchar_t *)L"Invalid payload length", 2);
              else
                LODWORD(v13) = v19(L"Invalid payload length", 2);
            }
            v11 = AddressString;
            goto LABEL_469;
          }
          v144 = 0;
          v145 = 1;
          memcpy_0(&v232, p_s_b1, v143);
          memset_0(SubStr, 0, 0x8000u);
          StringCchCopyExW(
            AddressString,
            (unsigned __int64)a5 >> 1,
            v146,
            &v234,
            (unsigned __int64 *)&Block,
            cchWideChar);
          v147 = v234;
          StringCchPrintfW(SubStr, 0x4000u, L"%s", *(_QWORD *)(v239 + 32));
          v148 = o_wcstok_s_0(SubStr, L",", &v258);
          v149 = v232;
          while ( 1 )
          {
            v150 = v148;
            if ( !v148 )
              break;
            if ( _bittest((const int *)&v149, v144) )
            {
              if ( !v145 )
              {
                StringCchCatExW(v147, (unsigned __int64)Block, L",", &v234, (unsigned __int64 *)&Block, cchWideChara);
                v147 = v234;
              }
              StringCchCatExW(v147, (unsigned __int64)Block, v150, &v234, (unsigned __int64 *)&Block, cchWideChara);
              v147 = v234;
              v145 = 0;
            }
            v148 = o_wcstok_s_0(0, L",", &v258);
            ++v144;
          }
          while ( v144 < (unsigned __int64)(8 * v143) )
          {
            if ( _bittest((const int *)&v149, v144) )
            {
              ConvertUnsignedInt(v273);
              if ( !v145 )
              {
                StringCchCatExW(v147, (unsigned __int64)Block, L",", &v234, (unsigned __int64 *)&Block, cchWideChara);
                v147 = v234;
              }
              StringCchCatExW(v147, (unsigned __int64)Block, v273, &v234, (unsigned __int64 *)&Block, cchWideChara);
              v147 = v234;
              v145 = 0;
            }
            ++v144;
          }
          StringCchCatExW(v147, (unsigned __int64)Block, L"]", &v234, (unsigned __int64 *)&Block, cchWideChara);
          s_w1 = v237;
LABEL_273:
          v17 = (struct in_addr *)StringSid[0];
          goto LABEL_454;
        }
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 8 )
          goto LABEL_463;
        v151 = AddressString;
        v152 = (unsigned __int64)a5 >> 1;
      }
      else
      {
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 8 )
          goto LABEL_463;
        if ( *(__int64 *)&v17->S_un.S_un_b.s_b1 > 0 )
          goto LABEL_206;
        v152 = ((unsigned __int64)a5 >> 1) - 1;
        *AddressString = 43;
        v151 = AddressString + 1;
      }
      FormatTimeDelta(v151, v152);
      goto LABEL_277;
    }
    v153 = *(const wchar_t **)(v18 + 32);
    v244 = 0;
    if ( swscanf(v153, L"%d", &v244) == -1 )
      goto LABEL_455;
    s_w1 = v244;
    if ( v244 > 0x4000uLL )
      s_w1 = 0x3FFF;
    if ( (__int64)Src + v236 - (_QWORD)v17 < s_w1 )
    {
      v13 = (unsigned __int64)TracePrinter;
      if ( !TracePrinter )
        goto LABEL_468;
      v224 = (wchar_t *)L"Invalid payload length";
      goto LABEL_481;
    }
    v11 = AddressString;
    if ( (__int64)v261 + a5 - (_QWORD)AddressString < s_w1 )
      goto LABEL_494;
    v154 = (unsigned int)s_w1;
LABEL_287:
    memcpy_0(v11, v17, v154);
    goto LABEL_454;
  }
  if ( v27 > 59 )
  {
    switch ( v27 )
    {
      case '<':
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 0x10 )
          goto LABEL_463;
        break;
      case '=':
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 0x10 )
          goto LABEL_463;
        break;
      case '>':
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 0x10 )
          goto LABEL_463;
        break;
      case '?':
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 2 )
          goto LABEL_463;
        s_w1 = v17->S_un.S_un_w.s_w1;
        v237 = s_w1;
        StringSid[0] = &v17->S_un.S_un_w.s_w2;
        v214 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)&v17->S_un.S_un_w.s_w2];
        if ( (__int64)v214 < s_w1 )
        {
LABEL_498:
          if ( v19 )
          {
            v224 = L"iMofPtr buffer overflow";
            goto LABEL_465;
          }
LABEL_468:
          v11 = AddressString;
          goto LABEL_469;
        }
        LODWORD(v13) = 16;
        if ( (unsigned __int16)s_w1 < 0x10u )
        {
          if ( !v19 )
            goto LABEL_468;
          v224 = L"iMofPtr buffer underflow";
          goto LABEL_465;
        }
        v215 = (char *)malloc((unsigned int)s_w1);
        p_s_w2 = &v17->S_un.S_un_w.s_w2;
        Block = v215;
        v217 = v215;
        memcpy_0(v215, p_s_w2, (unsigned int)s_w1);
        v218 = *(_WORD *)v217;
        szAddressString = 0;
        memset_0(v272, 0, 0x80u);
        dwAddressStringLength = 64;
        if ( v218 == 2 )
        {
          RtlIpv4AddressToStringExW(
            (const struct in_addr *)v217 + 1,
            *((_WORD *)v217 + 1),
            &szAddressString,
            &dwAddressStringLength);
        }
        else if ( v218 == 23 )
        {
          LODWORD(v13) = 28;
          if ( (unsigned __int16)s_w1 >= 0x1Cu )
          {
            if ( v214 < 0x1C )
              goto LABEL_498;
            RtlIpv6AddressToStringExW(
              (const struct in6_addr *)(v217 + 8),
              *((_DWORD *)v217 + 6),
              *((_WORD *)v217 + 1),
              &szAddressString,
              &dwAddressStringLength);
          }
        }
        else
        {
          WSAAddressToStringW((LPSOCKADDR)v217, s_w1, 0, &szAddressString, &dwAddressStringLength);
        }
        if ( szAddressString )
        {
          StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%ls", &szAddressString);
        }
        else
        {
          v232 = v217[15];
          v219 = *((char *)Block + 3);
          v220 = *(unsigned __int16 *)Block;
          v234 = (unsigned __int16 *)((unsigned __int64)a5 >> 1);
          v217 = (char *)Block;
          cchWideChar = v219;
          LODWORD(lpWideCharStr) = *((char *)Block + 2);
          StringCchPrintfW(
            AddressString,
            (unsigned __int64)v234,
            L"<sa_family=%d sa_addr=%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X>",
            v220,
            lpWideCharStr);
          s_w1 = v237;
        }
        free(v217);
        goto LABEL_273;
      case '@':
        goto LABEL_411;
      case 'A':
        goto LABEL_395;
      case 'B':
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 2 )
          goto LABEL_463;
        v28 = (v17->S_un.S_un_b.s_b1 << 8) + v17->S_un.S_un_b.s_b2;
        v17 = (struct in_addr *)((char *)v17 + 2);
        StringSid[0] = &v17->S_un.S_un_w.s_w1;
        goto LABEL_377;
      default:
        goto LABEL_31;
    }
    s_w1 = 16;
    *(_OWORD *)StringSid = *(_OWORD *)&v17->S_un.S_un_b.s_b1;
    FormatGuidData(AddressString, a5 >> 1, (struct _GUID *)StringSid);
    goto LABEL_454;
  }
  if ( v27 == 59 )
    goto LABEL_456;
  v155 = v27 - 51;
  if ( !v155 )
  {
    v188 = *(const wchar_t **)(v18 + 32);
    v245 = 0;
    if ( swscanf(v188, L"%d", &v245) == -1 )
      goto LABEL_455;
    s_w1 = v245;
    v11 = AddressString;
    if ( v245 > 0x2000uLL )
      s_w1 = 0x2000;
    if ( (__int64)v261 + a5 - (_QWORD)AddressString < (unsigned int)s_w1 )
    {
LABEL_494:
      v13 = (unsigned __int64)TracePrinter;
      if ( !TracePrinter )
        goto LABEL_469;
      v14 = L"Decoding Buffer to small";
      goto LABEL_4;
    }
    if ( (__int64)Src + v236 - (_QWORD)v17 < (unsigned int)(2 * s_w1) )
    {
      v13 = (unsigned __int64)TracePrinter;
      if ( TracePrinter )
      {
        v14 = L"iMofPtr buffer overflow";
        goto LABEL_4;
      }
      goto LABEL_469;
    }
    v154 = 2 * s_w1;
    goto LABEL_287;
  }
  v156 = v155 - 1;
  if ( v156 )
  {
    v157 = v156 - 1;
    if ( v157 )
    {
      v158 = v157 - 1;
      if ( !v158 )
      {
        v21 = (unsigned int)v22;
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 8 )
          goto LABEL_463;
        v22 = v17[1].S_un.S_addr;
        v163 = v17->S_un.S_addr;
        v164 = v17 + 2;
        StringSid[0] = &v17[2].S_un.S_un_w.s_w1;
        v13 = (unsigned __int64)&v15[(unsigned int)v21 - (_QWORD)(v17 + 2)];
        if ( (__int64)v13 < v163 )
          goto LABEL_463;
        v165 = &v164->S_un.S_un_b.s_b1 + v163;
        v13 = (unsigned __int64)&v15[(unsigned int)v21 - (_QWORD)v165];
        if ( v13 < 8 )
          goto LABEL_463;
        v166 = *(_QWORD *)v165;
        v167 = (const unsigned __int16 *)(v165 + 8);
        LODWORD(v13) = *(_QWORD *)v165;
        if ( (__int64)&v15[(unsigned int)v21 - (_QWORD)(v165 + 8)] < (unsigned int)v13
          || (v13 = (unsigned __int64)v167 + v166, v21 -= (__int64)v167 + v166, (unsigned __int64)&v15[v21] < 8)
          || (s_w1 = *(_QWORD *)v13,
              v17 = (struct in_addr *)(v13 + 8),
              v13 = (unsigned int)*(_QWORD *)v13,
              (__int64)&v15[v21 - 8] < (__int64)v13) )
        {
LABEL_463:
          if ( v19 )
          {
            v224 = (wchar_t *)L"Invalid payload length";
            goto LABEL_465;
          }
          goto LABEL_468;
        }
        LODWORD(lpWideCharStr) = v22;
        StringCchPrintfW(
          AddressString,
          (unsigned __int64)a5 >> 1,
          L"ID: %u: eventType: %u: Component: ",
          v164[3].S_un.S_un_w.s_w1,
          lpWideCharStr);
        StringCchCatNW(AddressString, (unsigned __int64)a5 >> 1, v167, v166 >> 1);
        goto LABEL_454;
      }
      v159 = v158 - 1;
      if ( !v159 )
      {
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( (__int64)v13 < 88 )
          goto LABEL_463;
        s_w1 = 88;
        FormatSRB(v17, AddressString);
        goto LABEL_454;
      }
      v160 = v159 - 1;
      if ( !v160 )
      {
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( (__int64)v13 < 18 )
          goto LABEL_463;
        s_w1 = 18;
        FormatSenseData(v17, 18, AddressString, a5 >> 1);
        goto LABEL_454;
      }
      if ( (unsigned int)(v160 - 1) <= 1 )
      {
        v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
        if ( v13 < 4 )
          goto LABEL_463;
        v161 = v259;
        s_w1 = 4;
        v162 = (struct in_addr)v17->S_un.S_addr;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v259 + 56));
        HIDWORD(Arguments) = HIDWORD(v20);
        LOBYTE(cchWideChar) = *(_DWORD *)(v239 + 40) == 58;
        LODWORD(lpWideCharStr) = v162;
        GetEnumNameFromGuidList(v264, (char *)v161 + 32, v260 + 12, *(_QWORD *)(v239 + 32), lpWideCharStr);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v161 + 56));
        goto LABEL_455;
      }
      goto LABEL_31;
    }
    v168 = (unsigned int)v22;
    v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
    if ( v13 < 2 )
      goto LABEL_500;
    v169 = (const char *)&v17->S_un.S_un_b.s_b3;
    v170 = v17->S_un.S_un_b.s_b1;
    v171 = v17->S_un.S_un_b.s_b2 << 8;
    v17 = (struct in_addr *)((char *)v17 + 2);
    v172 = (unsigned __int16)(v170 + v171);
    v232 = v172;
    if ( (_WORD)v172 == 5 )
    {
      if ( (__int64)&v15[(unsigned int)v22 - (_QWORD)v169] > 4 )
      {
        if ( !strncmp_0(v169, "NULL", 5u) )
        {
          s_w1 = 5;
LABEL_315:
          v139 = (unsigned __int64)a5 >> 1;
          goto LABEL_316;
        }
        v15 = (char *)Src;
      }
    }
    else if ( (unsigned __int16)v172 > 0x990u )
    {
      LOWORD(v172) = 2448;
      v232 = 2448;
    }
    v21 = (unsigned __int64)a5 >> 1;
    if ( (_WORD)v172 )
    {
      LODWORD(v13) = (unsigned __int16)v172;
      Block = (void *)((unsigned __int64)a5 >> 1);
      if ( (__int64)&v15[v168 - (_QWORD)v169] < (unsigned __int16)v172 )
        goto LABEL_498;
      v173 = 0;
      v174 = AddressString;
      *AddressString = 0;
      while ( 1 )
      {
        StringSid[0] = 0;
        v175 = L"%02X";
        if ( (v173 & 0xF) == 0 )
          v175 = L" %02X";
        StringCchPrintfExW(v174, v21, StringSid, (unsigned __int64 *)&Block, 0, v175);
        v174 = StringSid[0];
        if ( ++v173 >= (unsigned __int16)v172 )
          break;
        v21 = (__int64)Block;
      }
      v19 = TracePrinter;
      LOWORD(v172) = v232;
    }
    else
    {
      StringCchCopyW(AddressString, v21, L"<NULL>");
    }
    s_w1 = (unsigned __int16)v172;
    goto LABEL_243;
  }
  v176 = (unsigned int)v22;
  v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v17];
  if ( v13 < 2 )
  {
LABEL_500:
    if ( !v19 )
      goto LABEL_468;
    v224 = L"HEXDUMP Invalid payload length";
LABEL_465:
    if ( !DebugExtPrint )
    {
      v13 = (unsigned __int64)v19;
      goto LABEL_467;
    }
LABEL_473:
    LODWORD(v13) = TracePrinterExt(v224, v21, v22);
    goto LABEL_468;
  }
  v177 = &v17->S_un.S_un_w.s_w2;
  v178 = v17->S_un.S_un_b.s_b1;
  v179 = v17->S_un.S_un_b.s_b2 << 8;
  v17 = (struct in_addr *)v177;
  StringSid[0] = v177;
  v180 = (unsigned __int16)(v178 + v179);
  v232 = v180;
  if ( (_WORD)v180 == 5 )
  {
    v13 = (unsigned __int64)&v15[(unsigned int)v22 - (_QWORD)v177];
    if ( (__int64)v13 > 4 )
    {
      LODWORD(v13) = strncmp_0((const char *)v177, "NULL", 5u);
      if ( !(_DWORD)v13 )
      {
        s_w1 = 5;
        goto LABEL_315;
      }
      v15 = (char *)Src;
    }
  }
  else
  {
    LODWORD(v13) = 2448;
    if ( (unsigned __int16)v180 > 0x990u )
    {
      LOWORD(v180) = 2448;
      v232 = 2448;
    }
  }
  v21 = (unsigned __int64)a5 >> 1;
  v237 = (unsigned __int16)v180;
  if ( !(_WORD)v180 )
  {
    StringCchCopyW(AddressString, v21, L"<NULL>");
    goto LABEL_360;
  }
  Block = (void *)((unsigned __int64)a5 >> 1);
  if ( (__int64)&v15[v176 - (_QWORD)v177] < (unsigned __int16)v180 )
    goto LABEL_498;
  v268 = 0;
  v181 = AddressString;
  v182 = 0;
  *AddressString = 0;
  v266 = 0;
  v267 = 0;
  do
  {
    if ( (v182 & 0xF) == 0 )
    {
      if ( v182 )
      {
        v234 = 0;
        StringCchPrintfExW(v181, (unsigned __int64)Block, &v234, (unsigned __int64 *)&Block, 0, L"  %s", &v266);
        v181 = v234;
        v266 = 0;
        v267 = 0;
      }
      LODWORD(Arguments) = v182;
      v234 = 0;
      StringCchPrintfExW(v181, (unsigned __int64)Block, &v234, (unsigned __int64 *)&Block, 0, L"\n\t%04X ", Arguments);
      v181 = v234;
    }
    v183 = L"%02X";
    v234 = 0;
    if ( (v182 & 3) == 0 )
      v183 = L" %02X";
    LODWORD(Arguments) = *((unsigned __int8 *)v177 + v182);
    StringCchPrintfExW(v181, (unsigned __int64)Block, &v234, (unsigned __int64 *)&Block, 0, v183, Arguments);
    v181 = v234;
    if ( (unsigned __int8)(*((_BYTE *)v177 + v182) - 32) > 0x5Eu )
      v184 = 46;
    else
      v184 = *((unsigned __int8 *)v177 + v182);
    v185 = v182++;
    *((_WORD *)&v266 + (v185 & 0xF)) = v184;
  }
  while ( (int)v182 < (unsigned __int16)v180 );
  v11 = AddressString;
  if ( (v232 & 0xF) != 0 )
  {
    v186 = v180 & 0xF;
    do
    {
      v234 = 0;
      v187 = L"%s";
      if ( (v186 & 3) == 0 )
        v187 = L" %s";
      StringCchPrintfExW(v181, (unsigned __int64)Block, &v234, (unsigned __int64 *)&Block, 0, v187, L"  ");
      v181 = v234;
      ++v186;
    }
    while ( v186 < 16 );
    v11 = AddressString;
  }
  Arguments = (va_list *)&v266;
  if ( (unsigned int)StringCchPrintfExW(
                       v181,
                       (unsigned __int64)Block,
                       &v234,
                       (unsigned __int64 *)&Block,
                       0,
                       L"  %s\n\t") != -2147024774 )
  {
    v19 = TracePrinter;
LABEL_360:
    s_w1 = v237;
    v17 = (struct in_addr *)StringSid[0];
    goto LABEL_243;
  }
  v13 = (unsigned __int64)TracePrinter;
  if ( TracePrinter )
  {
    v14 = L"HEXDUMP Invalid payload data";
    goto LABEL_4;
  }
LABEL_469:
  v40 = a5;
LABEL_470:
  if ( v40 )
    *(_BYTE *)v11 = 0;
  return v13;
}

```

## disassembly

```asm
0x180043390  push    rbp
0x180043392  push    rbx
0x180043393  push    rsi
0x180043394  push    rdi
0x180043395  push    r12
0x180043397  push    r13
0x180043399  push    r14
0x18004339b  push    r15
0x18004339d  lea     rbp, [rsp-3C8h]
0x1800433a5  sub     rsp, 4D8h
0x1800433ac  mov     rax, cs:__security_cookie
0x1800433b3  xor     rax, rsp
0x1800433b6  mov     [rbp+400h+var_50], rax
0x1800433bd  mov     rdi, [rbp+400h+arg_48]
0x1800433c4  mov     r15, rcx
0x1800433c7  mov     eax, [rbp+400h+arg_20]
0x1800433cd  mov     rbx, r9
0x1800433d0  mov     r14, [rbp+400h+arg_40]
0x1800433d7  mov     [rbp+400h+var_480], eax
0x1800433da  mov     rax, [rbp+400h+arg_28]
0x1800433e1  lea     rsi, [rdi+10h]
0x1800433e5  mov     [rbp+400h+var_3A0], rax
0x1800433e9  mov     rax, [rbp+400h+arg_30]
0x1800433f0  mov     [rbp+400h+var_3B8], rax
0x1800433f4  lea     rax, [rdi+18h]
0x1800433f8  mov     [rbp+400h+var_450], r8d
0x1800433fc  mov     r8, rax; unsigned int *
0x1800433ff  mov     [rbp+400h+Src], rdx
0x180043403  mov     rdx, rsi; void **
0x180043406  mov     [rbp+400h+var_3B0], rcx
0x18004340a  mov     ecx, 4000h; Size
0x18004340f  mov     [rbp+400h+var_3A8], r9
0x180043413  mov     [rbp+400h+var_3F8], rdi
0x180043417  mov     [rbp+400h+var_3F0], r14
0x18004341b  mov     [rbp+400h+AddressString], rbx
0x18004341f  mov     [rbp+400h+var_3D8], rax
0x180043423  mov     [rbp+400h+var_400], rsi
0x180043427  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x18004342c  cmp     eax, 8
0x18004342f  jnz     short loc_180043466
0x180043431  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180043438  xor     esi, esi
0x18004343a  test    rax, rax
0x18004343d  jz      loc_180045623
0x180043443  lea     rcx, aNotEnoughMemor_2; "Not enough memory"
0x18004344a  cmp     cs:?DebugExtPrint@@3HA, esi; int DebugExtPrint
0x180043450  jnz     short loc_18004345C
0x180043452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043457  jmp     loc_180045623
0x18004345c  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x180043461  jmp     loc_180045623
0x180043466  mov     rax, [rsi]
0x180043469  mov     rdx, rdi; void **
0x18004346c  mov     [rbp+400h+lpMultiByteStr], rax
0x180043470  mov     ecx, 8000h; Size
0x180043475  lea     rax, [rdi+8]
0x180043479  mov     r8, rax; unsigned int *
0x18004347c  mov     [rbp+400h+var_420], rax
0x180043480  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x180043485  cmp     eax, 8
0x180043488  jz      short loc_180043431
0x18004348a  mov     rax, [r15+20h]
0x18004348e  mov     r10d, 1
0x180043494  mov     r11, [rbp+400h+Src]
0x180043498  mov     r9, [rdi]
0x18004349b  mov     r13, r11
0x18004349e  add     [r15+8], r10d
0x1800434a2  mov     rcx, [rax]
0x1800434a5  xor     esi, esi
0x1800434a7  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800434ae  mov     r15, [rbp+400h+AddressString]
0x1800434b2  mov     [rbp+400h+StringSid], r11
0x1800434b9  mov     [rbp+400h+SubStr], r9
0x1800434bd  mov     [rbp+400h+var_398], rax
0x1800434c1  mov     [rbp+400h+StringSid], r11
0x1800434c8  mov     [rbp+400h+var_438], rcx
0x1800434cc  mov     r9d, 4
0x1800434d2  mov     edi, 100h
0x1800434d7  lea     edx, [r9-2]
0x1800434db  cmp     rax, rcx
0x1800434de  jz      loc_18004561F
0x1800434e4  mov     r8d, [rbp+400h+var_450]
0x1800434e8  mov     eax, r13d
0x1800434eb  sub     eax, r11d
0x1800434ee  cmp     eax, r8d
0x1800434f1  jnb     loc_18004561F
0x1800434f7  mov     eax, [r14]
0x1800434fa  cmp     eax, edi
0x1800434fc  jz      loc_18004561F
0x180043502  mov     [rbp+400h+var_408], esi
0x180043505  mov     r14, r13
0x180043508  mov     [rbp+400h+var_448], rsi
0x18004350c  mov     r12, rsi
0x18004350f  test    rbx, rbx
0x180043512  jz      loc_18004359F
0x180043518  movsxd  r9, dword ptr [rcx+28h]
0x18004351c  lea     edx, [rax+1]
0x18004351f  mov     eax, [rbp+400h+var_450]
0x180043522  lea     r10, ?str_item@@3QBQEBGB; ushort const * const near * const str_item
0x180043529  mov     r8, [rcx+10h]
0x18004352d  sub     rax, r13
0x180043530  cmp     cs:?DebugExtPrint@@3HA, esi; int DebugExtPrint
0x180043536  mov     r10, [r10+r9*8]
0x18004353a  jnz     short loc_180043560
0x18004353c  lea     rcx, [r11+rax]
0x180043540  mov     rax, rbx
0x180043543  mov     [rsp+510h+Arguments], rcx
0x180043548  lea     rcx, aParam03dSItemt; "Param %03d (%s) itemType %3d(%s) data P"...
0x18004354f  mov     qword ptr [rsp+510h+cchWideChar], r13
0x180043554  mov     [rsp+510h+lpWideCharStr], r10
0x180043559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004355e  jmp     short loc_18004357E
0x180043560  add     rax, r11
0x180043563  lea     rcx, aParam03dSItemt; "Param %03d (%s) itemType %3d(%s) data P"...
0x18004356a  mov     [rsp+510h+Arguments], rax
0x18004356f  mov     qword ptr [rsp+510h+cchWideChar], r13; unsigned int
0x180043574  mov     [rsp+510h+lpWideCharStr], r10
0x180043579  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18004357e  mov     rcx, [rbp+400h+var_438]
0x180043582  mov     r10d, 1
0x180043588  mov     r8d, [rbp+400h+var_450]
0x18004358c  mov     r11, [rbp+400h+Src]
0x180043590  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x180043597  lea     r9d, [r10+3]
0x18004359b  lea     edx, [r10+1]
0x18004359f  mov     edi, [rcx+28h]
0x1800435a2  mov     eax, 21h ; '!'
0x1800435a7  cmp     edi, eax
0x1800435a9  jg      loc_180044060
0x1800435af  jz      loc_180043F1C
0x1800435b5  mov     eax, 10h
0x1800435ba  movzx   r12d, r10w
0x1800435be  cmp     edi, eax
0x1800435c0  jg      loc_1800437A3
0x1800435c6  jz      loc_1800436A7
0x1800435cc  cmp     edi, 8
0x1800435cf  jg      short loc_180043649
0x1800435d1  jz      short loc_180043611
0x1800435d3  test    edi, edi
0x1800435d5  jz      short loc_18004360C
0x1800435d7  sub     edi, 1
0x1800435da  jz      short loc_18004360C
0x1800435dc  sub     edi, 1
0x1800435df  jz      short loc_18004360C
0x1800435e1  sub     edi, 1
0x1800435e4  jz      short loc_180043607
0x1800435e6  sub     edi, 1
0x1800435e9  jz      short loc_180043607
0x1800435eb  sub     edi, 1
0x1800435ee  jz      short loc_180043607
0x1800435f0  sub     edi, 1
0x1800435f3  jz      short loc_180043611
0x1800435f5  cmp     edi, 1
0x1800435f8  jz      short loc_180043611
0x1800435fa  mov     r12, [rbp+400h+var_448]
0x1800435fe  add     r13, 4
0x180043602  jmp     loc_18004559A
0x180043607  mov     r12, rdx
0x18004360a  jmp     short loc_180043614
0x18004360c  mov     r12, r10
0x18004360f  jmp     short loc_180043614
0x180043611  mov     r12, r9
0x180043614  mov     eax, r8d
0x180043617  sub     rax, r14
0x18004361a  add     rax, r11
0x18004361d  cmp     rax, r12
0x180043620  jl      loc_180045603
0x180043626  mov     r9, [rbp+400h+var_3F0]
0x18004362a  mov     r8, r12; Size
0x18004362d  mov     rcx, [rbp+400h+var_3A0]
0x180043631  mov     rdx, r14; Src
0x180043634  mov     eax, [r9]
0x180043637  lea     rcx, [rcx+rax*8]; void *
0x18004363b  call    memcpy_0
0x180043640  mov     r14, [rbp+400h+var_3F0]
0x180043644  jmp     loc_1800455DC
0x180043649  sub     edi, 9
0x18004364c  jz      short loc_180043672
0x18004364e  sub     edi, 1
0x180043651  jz      short loc_180043672
0x180043653  sub     edi, 1
0x180043656  jz      short loc_180043672
0x180043658  sub     edi, 1
0x18004365b  jz      short loc_180043672
0x18004365d  sub     edi, 1
0x180043660  jz      short loc_180043672
0x180043662  sub     edi, 1
0x180043665  jz      short loc_1800436A7
0x180043667  cmp     edi, 1
0x18004366a  jz      loc_180044F09
0x180043670  jmp     short loc_1800435FA
0x180043672  mov     eax, r8d
0x180043675  sub     rax, r13
0x180043678  add     rax, r11
0x18004367b  cmp     rax, 8
0x18004367f  jb      loc_180045603
0x180043685  mov     edi, [rbp+400h+var_480]
0x180043688  cmp     edi, 8
0x18004368b  jb      loc_180045657
0x180043691  mov     rax, [r13+0]
0x180043695  mov     r12d, 8
0x18004369b  mov     [r15], rax
0x18004369e  mov     [rbp+400h+var_408], r10d
0x1800436a2  jmp     loc_18004559A
0x1800436a7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800436ab  inc     rdi
0x1800436ae  cmp     [rdi+r13], sil
0x1800436b2  jnz     short loc_1800436AB
0x1800436b4  mov     eax, r8d
0x1800436b7  lea     ecx, [rdi+1]; Size
0x1800436ba  sub     rax, r14
0x1800436bd  mov     r12d, ecx
0x1800436c0  add     rax, r11
0x1800436c3  cmp     rax, r12
0x1800436c6  jl      loc_180045603
0x1800436cc  test    edi, edi
0x1800436ce  jz      loc_180043789
0x1800436d4  mov     rbx, [rbp+400h+var_400]
0x1800436d8  mov     r8, [rbp+400h+var_3D8]; unsigned int *
0x1800436dc  mov     rdx, rbx; void **
0x1800436df  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x1800436e4  cmp     eax, 8
0x1800436e7  jz      loc_180045680
0x1800436ed  mov     rax, [rbx]
0x1800436f0  lea     ecx, ds:2[rdi*2]; Size
0x1800436f7  mov     rbx, [rbp+400h+var_3F8]
0x1800436fb  mov     r8, [rbp+400h+var_420]; unsigned int *
0x1800436ff  mov     rdx, rbx; void **
0x180043702  mov     [rbp+400h+lpMultiByteStr], rax
0x180043706  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x18004370b  cmp     eax, 8
0x18004370e  jz      loc_180045680
0x180043714  mov     rax, [rbx]
0x180043717  mov     rdx, r14; Src
0x18004371a  mov     r8d, edi; Size
0x18004371d  mov     ebx, edi
0x18004371f  mov     rdi, [rbp+400h+lpMultiByteStr]
0x180043723  mov     rcx, rdi; void *
0x180043726  mov     [rbp+400h+SubStr], rax
0x18004372a  call    memcpy_0
0x18004372f  mov     r9, [rbp+400h+var_438]
0x180043733  mov     [rbx+rdi], sil
0x180043737  cmp     dword ptr [r9+28h], 10h
0x18004373c  jnz     short loc_180043746
0x18004373e  mov     rcx, rdi
0x180043741  call    reduce
0x180043746  mov     rax, [rbp+400h+var_420]
0x18004374a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18004374e  mov     rbx, [rbp+400h+SubStr]
0x180043752  mov     r8, rdi; lpMultiByteStr
0x180043755  xor     edx, edx; dwFlags
0x180043757  xor     ecx, ecx; CodePage
0x180043759  mov     eax, [rax]
0x18004375b  shr     eax, 1
0x18004375d  mov     [rsp+510h+cchWideChar], eax; cchWideChar
0x180043761  mov     [rsp+510h+lpWideCharStr], rbx; lpWideCharStr
0x180043766  call    cs:__imp_MultiByteToWideChar
0x18004376c  mov     edx, [rbp+400h+var_480]
0x18004376f  lea     r8, aWs_0; "%ws"
0x180043776  shr     rdx, 1; unsigned __int64
0x180043779  mov     r9, rbx
0x18004377c  mov     rcx, r15; unsigned __int16 *
0x18004377f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043784  jmp     loc_180045593
0x180043789  mov     edx, [rbp+400h+var_480]
0x18004378c  lea     r8, aNull_2; "<NULL>"
0x180043793  shr     rdx, 1; unsigned __int64
0x180043796  mov     rcx, r15; unsigned __int16 *
0x180043799  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004379e  jmp     loc_18004559A
0x1800437a3  cmp     edi, 19h
0x1800437a6  jg      loc_180043AA7
0x1800437ac  jz      loc_180043A49
0x1800437b2  mov     ecx, edi
0x1800437b4  sub     ecx, 11h
0x1800437b7  jz      loc_180044F09
0x1800437bd  sub     ecx, 1
0x1800437c0  jz      loc_18004394F
0x1800437c6  sub     ecx, 1
0x1800437c9  jz      loc_18004505C
0x1800437cf  sub     ecx, 1
0x1800437d2  jz      loc_18004394F
0x1800437d8  sub     ecx, 1
0x1800437db  jz      loc_18004505C
0x1800437e1  sub     ecx, 1
0x1800437e4  jz      loc_180045141
0x1800437ea  sub     ecx, 1
0x1800437ed  jz      loc_180043889
0x1800437f3  cmp     ecx, 1
0x1800437f6  jnz     loc_1800435FA
0x1800437fc  mov     eax, [rbp+400h+var_480]
0x1800437ff  shr     eax, 1
0x180043801  mov     [rbp+400h+AddressStringLength], eax
0x180043804  mov     eax, r8d
0x180043807  sub     rax, r14
0x18004380a  mov     dword ptr [rbp+400h+Address.S_un], esi
0x18004380d  add     rax, r11
0x180043810  cmp     rax, r9
0x180043813  jl      loc_180045603
0x180043819  mov     eax, [r13+0]
  ... truncated ...
```
