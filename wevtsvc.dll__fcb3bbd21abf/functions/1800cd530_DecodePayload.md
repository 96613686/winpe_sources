# DecodePayload

- ea: `0x1800cd530`
- end: `0x1800cf90c`
- name: `DecodePayload`
- size: `9180`
- prototype: `int __fastcall(__int64, void *, unsigned int, unsigned __int16 *, unsigned int, __int64, struct FormatContext *, size_t Size, _DWORD *, void **)`
- caller_count: `1`
- callee_count: `31`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cd330`

## callees

- `0x180070d7c`
- `0x180078274`
- `0x1800953c8`
- `0x18009aee0`
- `0x18009bb58`
- `0x18009bb88`
- `0x18009bdb8`
- `0x18009cbf0`
- `0x1800cce08`
- `0x1800cce68`
- `0x1800ccee0`
- `0x1800cd28c`
- `0x1800cd530`
- `0x1800cf914`
- `0x1800cf944`
- `0x1800cf974`
- `0x1800cfcb0`
- `0x1800d013c`
- `0x1800d0998`
- `0x1800d0b6c`
- `0x1800d0da4`
- `0x1800d0e64`
- `0x1800d0edc`
- `0x1800d0f94`
- `0x1800d1014`
- `0x1800d119c`
- `0x1800d12f4`
- `0x1800d1340`
- `0x1800d3334`
- `0x1800d3370`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf670`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800cf670`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800cf4b9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800cf4b9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800ce1bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800ce1bf`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800ce1d4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800ce1d4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800cdd1a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ce178`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ce194`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ce1a9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800cdd1a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ce178`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ce194`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800ce1a9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800cdd55`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800cdd55`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800cdc4e`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800cf55a`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800cdc4e`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800cf55a`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800cd9d4`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800cf51b`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800cd9d4`
- `ntdll!RtlIpv4AddressToStringExW` at `0x1800cf51b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cea8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cea8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cea49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cea49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cf460`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cf460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce50a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf43a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce50a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf43a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ce4fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ce4fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ce467`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ce467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf432`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cd906`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cdbc7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ce008`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cd906`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800cdbc7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ce008`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cf39b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cf39b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ce4cd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ce578`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ce4cd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ce578`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cf407`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800cf407`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800cf3d0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800cf3d0`
- `WS2_32!WSAAddressToStringW` at `0x1800cf57b`
- `WS2_32!WSAAddressToStringW` at `0x1800cf57b`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNetEventSymbolicName` at `0x1800ce5be`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNetEventSymbolicName` at `0x1800ce5be`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisSymbolicName` at `0x1800ce2f5`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisSymbolicName` at `0x1800ce2f5`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisOidSymbolicName` at `0x1800ce29a`
- `ext-ms-win-core-symbolicnames-l1-1-0!GetNdisOidSymbolicName` at `0x1800ce29a`

## string_xrefs

- `0x1800ce47f`: `!ItemMerror %u : LoadLibrary of %s failed %d!`
- `0x1800ceba6`: `ID: %u: eventType: %u: Component: `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 S_addr; // r8
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
  __int64 v53; // r9
  __int64 v54; // r15
  __int16 v55; // bx
  unsigned __int16 v56; // bx
  void **v57; // r14
  CHAR *v58; // r14
  void **v59; // rdi
  WCHAR *v60; // rdi
  unsigned int *v61; // rax
  unsigned __int64 v62; // rdx
  const unsigned __int16 *v63; // r8
  unsigned __int64 v64; // r9
  unsigned __int64 v65; // rdx
  unsigned __int16 *v66; // rcx
  const unsigned __int16 *v67; // r8
  int v68; // edi
  int v69; // edi
  int v70; // edi
  int v71; // edi
  int v72; // edi
  int v73; // edi
  const wchar_t *v74; // rbx
  wchar_t *v75; // rdi
  wchar_t *v76; // rax
  __int64 v77; // rcx
  const wchar_t *v78; // r14
  wchar_t *v79; // rax
  unsigned __int16 *v80; // rdi
  wchar_t *v81; // rcx
  unsigned __int64 v82; // rbx
  LPWSTR v83; // r14
  WCHAR *v84; // rcx
  unsigned __int64 v85; // rdx
  void **v86; // rdi
  unsigned int v87; // ebx
  LPCCH v88; // rdx
  BOOL v89; // r15d
  int v90; // eax
  unsigned int v91; // r14d
  __int64 v92; // rdi
  __int64 v93; // rbx
  struct in_addr *i; // r12
  CHAR v95; // cl
  char *v96; // rcx
  WCHAR *v97; // rbx
  const CHAR *v98; // r8
  unsigned int v99; // edi
  unsigned __int16 *v100; // rbx
  wchar_t *j; // rcx
  wchar_t *v102; // rax
  wchar_t *v103; // r14
  wchar_t *v104; // rax
  wchar_t *v105; // rbx
  const wchar_t *v106; // rdi
  wchar_t *v107; // rax
  unsigned int v108; // eax
  int v109; // edi
  int v110; // edi
  int v111; // edi
  int v112; // edi
  int v113; // edi
  int v114; // edi
  int v115; // edi
  ULONG v116; // ebx
  __int64 NTStatusSymbolicName; // rax
  __int64 v118; // r9
  unsigned __int64 v119; // rdx
  const unsigned __int16 *v120; // r8
  ULONG v121; // ebx
  ULONG v122; // ebx
  const WCHAR *v123; // rcx
  DWORD v124; // ebx
  HMODULE Library; // rax
  HMODULE v126; // rdi
  __int64 v127; // r9
  unsigned __int16 *v128; // rbx
  ULONG v129; // ebx
  ULONG v130; // ebx
  __int64 NetEventSymbolicName; // rax
  unsigned __int64 v132; // rdx
  int v133; // edi
  int v134; // edi
  int v135; // edi
  int v136; // edi
  int v137; // edi
  int v138; // edi
  unsigned int v139; // ebx
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
  ULONG v162; // ebx
  signed __int64 v163; // rcx
  struct in_addr *v164; // r9
  UCHAR *v165; // rcx
  unsigned __int64 v166; // rdi
  const unsigned __int16 *v167; // r14
  __int64 v168; // r15
  const char *p_s_b3; // r12
  __int16 s_b1; // ax
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
  UCHAR *v190; // rbx
  __int64 v191; // r15
  unsigned __int64 v192; // rdi
  WCHAR *v193; // r14
  void *v194; // r10
  char *v195; // rax
  bool v196; // cf
  LPWSTR v197; // rdi
  unsigned int v198; // r14d
  _BYTE *v199; // rdx
  __int64 v200; // r9
  unsigned __int64 k; // rax
  __int16 v202; // dx
  __int16 v203; // ax
  unsigned __int16 v204; // dx
  unsigned __int16 v205; // ax
  unsigned __int16 v206; // cx
  unsigned __int64 v207; // r12
  __int64 v208; // r15
  DWORD LengthSid; // edi
  LPWSTR v210; // r14
  size_t v211; // r8
  size_t v212; // r8
  unsigned __int64 v213; // rbx
  USHORT *p_s_w2; // r14
  unsigned __int64 v215; // rdi
  char *v216; // r13
  __int16 v217; // bx
  unsigned int v218; // edx
  __int64 v219; // r9
  __int64 v220; // rcx
  unsigned int v221; // ecx
  __int64 *v222; // rcx
  wchar_t *v223; // rcx
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-F0h]
  unsigned int cchWideChar; // [rsp+28h] [rbp-E8h]
  unsigned int cchWideChara; // [rsp+28h] [rbp-E8h]
  va_list *Arguments; // [rsp+30h] [rbp-E0h]
  unsigned __int16 *AddressString; // [rsp+98h] [rbp-78h]
  unsigned int v231; // [rsp+A0h] [rbp-70h] BYREF
  void *Block; // [rsp+A8h] [rbp-68h] BYREF
  unsigned __int16 *v233; // [rsp+B0h] [rbp-60h] BYREF
  LPWSTR SubStr; // [rsp+B8h] [rbp-58h]
  unsigned int v235; // [rsp+C0h] [rbp-50h]
  __int64 v236; // [rsp+C8h] [rbp-48h]
  void *Src; // [rsp+D0h] [rbp-40h]
  __int64 v238; // [rsp+D8h] [rbp-38h]
  struct in_addr Address; // [rsp+E0h] [rbp-30h] BYREF
  ULONG dwAddressStringLength; // [rsp+E4h] [rbp-2Ch] BYREF
  LPCCH lpMultiByteStr; // [rsp+E8h] [rbp-28h]
  unsigned int *v242; // [rsp+F0h] [rbp-20h]
  unsigned int v243; // [rsp+F8h] [rbp-18h] BYREF
  DWORD cchReferencedDomainName; // [rsp+FCh] [rbp-14h] BYREF
  DWORD cchName; // [rsp+100h] [rbp-10h] BYREF
  int v246; // [rsp+104h] [rbp-Ch]
  unsigned int v247; // [rsp+108h] [rbp-8h] BYREF
  void **v248; // [rsp+110h] [rbp+0h]
  void **v249; // [rsp+118h] [rbp+8h]
  _DWORD *v250; // [rsp+120h] [rbp+10h]
  ULONG AddressStringLength; // [rsp+128h] [rbp+18h] BYREF
  ULONG v252; // [rsp+12Ch] [rbp+1Ch] BYREF
  enum _SID_NAME_USE peUse; // [rsp+130h] [rbp+20h] BYREF
  unsigned int *v254; // [rsp+138h] [rbp+28h]
  wchar_t *EndPtr; // [rsp+140h] [rbp+30h] BYREF
  wchar_t *Context; // [rsp+148h] [rbp+38h] BYREF
  wchar_t *v257; // [rsp+150h] [rbp+40h] BYREF
  struct FormatContext *v258; // [rsp+158h] [rbp+48h]
  __int64 v259; // [rsp+160h] [rbp+50h]
  unsigned __int16 *v260; // [rsp+168h] [rbp+58h]
  __int64 v261; // [rsp+170h] [rbp+60h]
  unsigned __int64 v262; // [rsp+178h] [rbp+68h]
  char v263[16]; // [rsp+180h] [rbp+70h] BYREF
  LPWSTR StringSid[2]; // [rsp+190h] [rbp+80h] BYREF
  __int128 v265; // [rsp+1A0h] [rbp+90h] BYREF
  __int128 v266; // [rsp+1B0h] [rbp+A0h]
  __int16 v267; // [rsp+1C0h] [rbp+B0h]
  struct in6_addr v268; // [rsp+1D0h] [rbp+C0h] BYREF
  char v269[32]; // [rsp+1E0h] [rbp+D0h] BYREF
  WCHAR szAddressString; // [rsp+200h] [rbp+F0h] BYREF
  char v271[142]; // [rsp+202h] [rbp+F2h] BYREF
  unsigned __int16 v272[24]; // [rsp+290h] [rbp+180h] BYREF
  WCHAR Name[128]; // [rsp+2C0h] [rbp+1B0h] BYREF
  WCHAR ReferencedDomainName[128]; // [rsp+3C0h] [rbp+2B0h] BYREF

  v11 = a4;
  v12 = a9;
  v261 = a6;
  v258 = a7;
  v235 = a3;
  Src = a2;
  v259 = a1;
  v260 = a4;
  v249 = a10;
  v250 = a9;
  AddressString = a4;
  v254 = (unsigned int *)(a10 + 3);
  v248 = a10 + 2;
  if ( ResizeBuffer(0x4000u, a10 + 2, (unsigned int *)a10 + 6) != 8 )
  {
    lpMultiByteStr = (LPCCH)a10[2];
    v242 = (unsigned int *)(a10 + 1);
    if ( ResizeBuffer(0x8000u, a10, (unsigned int *)a10 + 2) != 8 )
    {
      v13 = *(_QWORD *)(a1 + 32);
      v15 = (char *)Src;
      v16 = (WCHAR *)*a10;
      v17 = (struct in_addr *)Src;
      ++*(_DWORD *)(a1 + 8);
      v18 = *(_QWORD *)v13;
      v19 = TracePrinter;
      v20 = AddressString;
      SubStr = v16;
      v262 = v13;
      for ( StringSid[0] = &v17->S_un.S_un_w.s_w1; ; StringSid[0] = &v17->S_un.S_un_w.s_w1 )
      {
        v238 = v18;
        v21 = 2;
        if ( v13 == v18 )
          goto LABEL_468;
        S_addr = v235;
        LODWORD(v13) = (_DWORD)v17 - (_DWORD)v15;
        if ( (int)v17 - (int)v15 >= v235 )
          goto LABEL_468;
        LODWORD(v13) = *v12;
        if ( *v12 == 256 )
          goto LABEL_468;
        v246 = 0;
        p_s_b1 = &v17->S_un.S_un_b.s_b1;
        v236 = 0;
        s_w1 = 0;
        if ( v19 )
        {
          v25 = (unsigned int)(v13 + 1);
          v26 = *(_QWORD *)(v18 + 16);
          Arguments = (va_list *)&v15[v235 - (_QWORD)v17];
          cchWideChar = (unsigned int)v17;
          HIDWORD(lpWideCharStr) = HIDWORD((&str_item)[*(int *)(v18 + 40)]);
          if ( DebugExtPrint )
            TracePrinterExt((wchar_t *)L"Param %03d (%s) itemType %3d(%s) data Ptr %p, left %d\n", v25, v26);
          else
            v19(L"Param %03d (%s) itemType %3d(%s) data Ptr %p, left %d\n", v25, v26);
          v18 = v238;
          S_addr = v235;
          v15 = (char *)Src;
          v19 = TracePrinter;
          v21 = 2;
        }
        v27 = *(_DWORD *)(v18 + 40);
        LODWORD(v13) = 33;
        if ( v27 > 33 )
        {
          if ( v27 > 50 )
          {
            if ( v27 > 59 )
            {
              switch ( v27 )
              {
                case '<':
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 0x10 )
                    goto LABEL_463;
                  break;
                case '=':
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 0x10 )
                    goto LABEL_463;
                  break;
                case '>':
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 0x10 )
                    goto LABEL_463;
                  break;
                case '?':
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 2 )
                    goto LABEL_463;
                  s_w1 = v17->S_un.S_un_w.s_w1;
                  p_s_w2 = &v17->S_un.S_un_w.s_w2;
                  v236 = s_w1;
                  StringSid[0] = &v17->S_un.S_un_w.s_w2;
                  v215 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)&v17->S_un.S_un_w.s_w2];
                  if ( (__int64)v215 < s_w1 )
                  {
LABEL_498:
                    if ( v19 )
                    {
                      v223 = L"iMofPtr buffer overflow";
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
                    v223 = L"iMofPtr buffer underflow";
                    goto LABEL_465;
                  }
                  Block = malloc((unsigned int)s_w1);
                  v216 = (char *)Block;
                  memcpy_0(Block, p_s_w2, (unsigned int)s_w1);
                  v217 = *(_WORD *)v216;
                  szAddressString = 0;
                  memset_0(v271, 0, 0x80u);
                  dwAddressStringLength = 64;
                  if ( v217 == 2 )
                  {
                    RtlIpv4AddressToStringExW(
                      (const struct in_addr *)v216 + 1,
                      *((_WORD *)v216 + 1),
                      &szAddressString,
                      &dwAddressStringLength);
                  }
                  else if ( v217 == 23 )
                  {
                    if ( (unsigned __int16)s_w1 >= 0x1Cu )
                    {
                      if ( v215 < 0x1C )
                      {
LABEL_483:
                        v13 = (unsigned __int64)TracePrinter;
                        if ( !TracePrinter )
                          goto LABEL_468;
                        v223 = L"iMofPtr buffer overflow";
                        goto LABEL_481;
                      }
                      RtlIpv6AddressToStringExW(
                        (const struct in6_addr *)(v216 + 8),
                        *((_DWORD *)v216 + 6),
                        *((_WORD *)v216 + 1),
                        &szAddressString,
                        &dwAddressStringLength);
                    }
                  }
                  else
                  {
                    WSAAddressToStringW((LPSOCKADDR)v216, s_w1, 0, &szAddressString, &dwAddressStringLength);
                  }
                  if ( szAddressString )
                  {
                    StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%ls", &szAddressString);
                  }
                  else
                  {
                    v231 = v216[15];
                    v218 = *((char *)Block + 3);
                    v219 = *(unsigned __int16 *)Block;
                    v233 = (unsigned __int16 *)((unsigned __int64)a5 >> 1);
                    v216 = (char *)Block;
                    cchWideChar = v218;
                    LODWORD(lpWideCharStr) = *((char *)Block + 2);
                    StringCchPrintfW(
                      AddressString,
                      (unsigned __int64)v233,
                      L"<sa_family=%d sa_addr=%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X%02X>",
                      v219,
                      lpWideCharStr);
                    s_w1 = v236;
                  }
                  free(v216);
                  goto LABEL_276;
                case '@':
                  goto LABEL_411;
                case 'A':
                  goto LABEL_395;
                case 'B':
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 2 )
                    goto LABEL_463;
                  v28 = (v17->S_un.S_un_b.s_b1 << 8) + v17->S_un.S_un_b.s_b2;
                  v17 = (struct in_addr *)((char *)v17 + 2);
                  StringSid[0] = &v17->S_un.S_un_w.s_w1;
                  goto LABEL_378;
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
            if ( v155 )
            {
              v156 = v155 - 1;
              if ( v156 )
              {
                v157 = v156 - 1;
                if ( !v157 )
                {
                  v168 = (unsigned int)S_addr;
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 2 )
                    goto LABEL_500;
                  p_s_b3 = (const char *)&v17->S_un.S_un_b.s_b3;
                  s_b1 = v17->S_un.S_un_b.s_b1;
                  v171 = v17->S_un.S_un_b.s_b2 << 8;
                  v17 = (struct in_addr *)((char *)v17 + 2);
                  v172 = (unsigned __int16)(s_b1 + v171);
                  v231 = v172;
                  if ( (_WORD)v172 == 5 )
                  {
                    if ( (__int64)&v15[(unsigned int)S_addr - (_QWORD)p_s_b3] > 4 )
                    {
                      if ( !strncmp_0(p_s_b3, "NULL", 5u) )
                      {
                        s_w1 = 5;
                        goto LABEL_97;
                      }
                      v15 = (char *)Src;
                    }
                  }
                  else if ( (unsigned __int16)v172 > 0x990u )
                  {
                    LOWORD(v172) = 2448;
                    v231 = 2448;
                  }
                  v21 = (unsigned __int64)a5 >> 1;
                  if ( (_WORD)v172 )
                  {
                    LODWORD(v13) = (unsigned __int16)v172;
                    Block = (void *)((unsigned __int64)a5 >> 1);
                    if ( (__int64)&v15[v168 - (_QWORD)p_s_b3] < (unsigned __int16)v172 )
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
                    LOWORD(v172) = v231;
                  }
                  else
                  {
                    StringCchCopyW(AddressString, v21, L"<NULL>");
                  }
                  v19 = TracePrinter;
                  v20 = AddressString;
                  s_w1 = (unsigned __int16)v172;
                  goto LABEL_456;
                }
                v158 = v157 - 1;
                if ( !v158 )
                {
                  v21 = (unsigned int)S_addr;
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 8 )
                    goto LABEL_463;
                  S_addr = v17[1].S_un.S_addr;
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
                    || (v13 = (unsigned __int64)v167 + v166, v21 -= (__int64)v167 + v166,
                                                             (unsigned __int64)&v15[v21] < 8)
                    || (s_w1 = *(_QWORD *)v13,
                        v17 = (struct in_addr *)(v13 + 8),
                        v13 = (unsigned int)*(_QWORD *)v13,
                        (__int64)&v15[v21 - 8] < (__int64)v13) )
                  {
LABEL_463:
                    if ( v19 )
                    {
                      v223 = (wchar_t *)L"Invalid payload length";
                      goto LABEL_465;
                    }
                    goto LABEL_468;
                  }
                  LODWORD(lpWideCharStr) = S_addr;
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
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( (__int64)v13 < 88 )
                    goto LABEL_463;
                  s_w1 = 88;
                  FormatSRB(v17, AddressString);
                  goto LABEL_454;
                }
                v160 = v159 - 1;
                if ( !v160 )
                {
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( (__int64)v13 < 18 )
                    goto LABEL_463;
                  s_w1 = 18;
                  FormatSenseData(v17, 18, AddressString, a5 >> 1);
                  goto LABEL_454;
                }
                if ( (unsigned int)(v160 - 1) <= 1 )
                {
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 4 )
                    goto LABEL_463;
                  v161 = v258;
                  s_w1 = 4;
                  v162 = v17->S_un.S_addr;
                  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v258 + 56));
                  HIDWORD(Arguments) = HIDWORD(v20);
                  LOBYTE(cchWideChar) = *(_DWORD *)(v238 + 40) == 58;
                  LODWORD(lpWideCharStr) = v162;
                  GetEnumNameFromGuidList(v263, (char *)v161 + 32, v259 + 12, *(_QWORD *)(v238 + 32), lpWideCharStr);
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v161 + 56));
                  goto LABEL_455;
                }
                goto LABEL_31;
              }
              v176 = (unsigned int)S_addr;
              v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
              if ( v13 < 2 )
              {
LABEL_500:
                if ( !v19 )
                  goto LABEL_468;
                v223 = L"HEXDUMP Invalid payload length";
LABEL_465:
                if ( !DebugExtPrint )
                {
                  v13 = (unsigned __int64)v19;
                  goto LABEL_467;
                }
LABEL_473:
                LODWORD(v13) = TracePrinterExt(v223, v21, S_addr);
                goto LABEL_468;
              }
              v177 = &v17->S_un.S_un_w.s_w2;
              v178 = v17->S_un.S_un_b.s_b1;
              v179 = v17->S_un.S_un_b.s_b2 << 8;
              v17 = (struct in_addr *)v177;
              StringSid[0] = v177;
              v180 = (unsigned __int16)(v178 + v179);
              v231 = v180;
              if ( (_WORD)v180 == 5 )
              {
                v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v177];
                if ( (__int64)v13 > 4 )
                {
                  LODWORD(v13) = strncmp_0((const char *)v177, "NULL", 5u);
                  if ( !(_DWORD)v13 )
                  {
                    s_w1 = 5;
                    goto LABEL_97;
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
                  v231 = 2448;
                }
              }
              v21 = (unsigned __int64)a5 >> 1;
              v236 = (unsigned __int16)v180;
              if ( (_WORD)v180 )
              {
                Block = (void *)((unsigned __int64)a5 >> 1);
                if ( (__int64)&v15[v176 - (_QWORD)v177] < (unsigned __int16)v180 )
                  goto LABEL_498;
                v267 = 0;
                v181 = AddressString;
                v182 = 0;
                *AddressString = 0;
                v265 = 0;
                v266 = 0;
                do
                {
                  if ( (v182 & 0xF) == 0 )
                  {
                    if ( v182 )
                    {
                      v233 = 0;
                      StringCchPrintfExW(
                        v181,
                        (unsigned __int64)Block,
                        &v233,
                        (unsigned __int64 *)&Block,
                        0,
                        L"  %s",
                        &v265);
                      v181 = v233;
                      v265 = 0;
                      v266 = 0;
                    }
                    LODWORD(Arguments) = v182;
                    v233 = 0;
                    StringCchPrintfExW(
                      v181,
                      (unsigned __int64)Block,
                      &v233,
                      (unsigned __int64 *)&Block,
                      0,
                      L"\n\t%04X ",
                      Arguments);
                    v181 = v233;
                  }
                  v183 = L"%02X";
                  v233 = 0;
                  if ( (v182 & 3) == 0 )
                    v183 = L" %02X";
                  LODWORD(Arguments) = *((unsigned __int8 *)v177 + v182);
                  StringCchPrintfExW(
                    v181,
                    (unsigned __int64)Block,
                    &v233,
                    (unsigned __int64 *)&Block,
                    0,
                    v183,
                    Arguments);
                  v181 = v233;
                  if ( (unsigned __int8)(*((_BYTE *)v177 + v182) - 32) > 0x5Eu )
                    v184 = 46;
                  else
                    v184 = *((unsigned __int8 *)v177 + v182);
                  v185 = v182++;
                  *((_WORD *)&v265 + (v185 & 0xF)) = v184;
                }
                while ( (int)v182 < (unsigned __int16)v180 );
                v11 = AddressString;
                if ( (v231 & 0xF) != 0 )
                {
                  v186 = v180 & 0xF;
                  do
                  {
                    v233 = 0;
                    v187 = L"%s";
                    if ( (v186 & 3) == 0 )
                      v187 = L" %s";
                    StringCchPrintfExW(v181, (unsigned __int64)Block, &v233, (unsigned __int64 *)&Block, 0, v187, L"  ");
                    v181 = v233;
                    ++v186;
                  }
                  while ( v186 < 16 );
                  v11 = AddressString;
                }
                Arguments = (va_list *)&v265;
                if ( (unsigned int)StringCchPrintfExW(
                                     v181,
                                     (unsigned __int64)Block,
                                     &v233,
                                     (unsigned __int64 *)&Block,
                                     0,
                                     L"  %s\n\t") == -2147024774 )
                {
                  v13 = (unsigned __int64)TracePrinter;
                  if ( !TracePrinter )
                    goto LABEL_469;
                  v14 = L"HEXDUMP Invalid payload data";
LABEL_4:
                  if ( DebugExtPrint )
                    LODWORD(v13) = TracePrinterExt(v14);
                  else
                    LODWORD(v13) = ((__int64 (__fastcall *)(wchar_t *))v13)(v14);
                  goto LABEL_469;
                }
              }
              else
              {
                StringCchCopyW(AddressString, v21, L"<NULL>");
              }
              goto LABEL_275;
            }
            v188 = *(const wchar_t **)(v18 + 32);
            v243 = 0;
            if ( swscanf(v188, L"%d", &v243) == -1 )
              goto LABEL_455;
            s_w1 = v243;
            v11 = AddressString;
            if ( v243 > 0x2000uLL )
              s_w1 = 0x2000;
            if ( (__int64)v260 + a5 - (_QWORD)AddressString < (unsigned int)s_w1 )
            {
LABEL_494:
              v13 = (unsigned __int64)TracePrinter;
              if ( TracePrinter )
              {
                v14 = L"Decoding Buffer to small";
                goto LABEL_4;
              }
              goto LABEL_469;
            }
            if ( (__int64)Src + v235 - (_QWORD)v17 < (unsigned int)(2 * s_w1) )
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
          }
          else
          {
            if ( v27 != 50 )
            {
              if ( v27 <= 42 )
              {
                if ( v27 == 42 )
                {
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 4 )
                    goto LABEL_463;
                  v130 = v17->S_un.S_addr;
                  s_w1 = 4;
                  if ( (unsigned __int8)IsGetNetEventSymbolicNamePresent(v18, 2) )
                    NetEventSymbolicName = GetNetEventSymbolicName(v130);
                  else
                    NetEventSymbolicName = 0;
                  v132 = (unsigned __int64)a5 >> 1;
                  if ( NetEventSymbolicName )
                    StringCchPrintfW(AddressString, v132, L"%S", NetEventSymbolicName);
                  else
                    StringCchPrintfW(AddressString, v132, L"NETEVENT=%8X", v130);
                  goto LABEL_454;
                }
                v109 = v27 - 34;
                if ( !v109 )
                {
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 4 )
                    goto LABEL_463;
                  v129 = v17->S_un.S_addr;
                  s_w1 = 4;
                  if ( FormatMessageW(0x1200u, 0, v17->S_un.S_addr, 0x400u, AddressString, a5 >> 1, 0) )
                    goto LABEL_454;
                  v63 = L"!NT Error %u unrecognised!";
                  v62 = (unsigned __int64)a5 >> 1;
                  v64 = v129;
                  goto LABEL_96;
                }
                v110 = v109 - 1;
                if ( !v110 )
                {
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 4 )
                    goto LABEL_463;
                  v123 = *(const WCHAR **)(v18 + 32);
                  s_w1 = 4;
                  v124 = v17->S_un.S_addr;
                  if ( v123 )
                  {
                    Library = LoadLibraryExW(v123, 0, 2u);
                    v126 = Library;
                    if ( Library )
                    {
                      if ( FormatMessageW(0x1A00u, Library, v124, 0x400u, AddressString, a5 >> 1, 0) )
                      {
                        v128 = AddressString;
                      }
                      else
                      {
                        v127 = v124;
                        v128 = AddressString;
                        StringCchPrintfW(
                          AddressString,
                          (unsigned __int64)a5 >> 1,
                          L"!Module Error %u unrecognised!",
                          v127);
                      }
                      if ( !FreeLibrary(v126) )
                      {
                        LODWORD(lpWideCharStr) = GetLastError();
                        StringCchPrintfW(
                          v128,
                          (unsigned __int64)a5 >> 1,
                          L"Failed to free library (%s) handle, err = %d",
                          *(_QWORD *)(v238 + 32),
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
                        v124,
                        *(_QWORD *)(v238 + 32));
                    }
                    goto LABEL_454;
                  }
                  v63 = L"! Error %u No Module Name!";
                  v62 = (unsigned __int64)a5 >> 1;
                  v64 = v124;
                  goto LABEL_96;
                }
                v111 = v110 - 1;
                if ( v111 )
                {
                  v112 = v111 - 1;
                  if ( !v112 )
                  {
                    v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                    if ( v13 < 0x10 )
                      goto LABEL_463;
                    *(_OWORD *)StringSid = *(_OWORD *)&v17->S_un.S_un_b.s_b1;
                    TraceprtGuidToString(AddressString, a5 >> 1, (struct _GUID *)StringSid);
                    goto LABEL_102;
                  }
                  v113 = v112 - 1;
                  if ( !v113 )
                  {
                    v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                    if ( v13 < 4 )
                      goto LABEL_463;
                    v122 = v17->S_un.S_addr;
                    s_w1 = 4;
                    if ( !v17->S_un.S_addr )
                    {
                      StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"STATUS_SUCCESS");
                      goto LABEL_454;
                    }
                    NTStatusSymbolicName = FetchNTStatusSymbolicName(v122, 2);
                    v118 = v122;
                    v66 = AddressString;
                    v119 = (unsigned __int64)a5 >> 1;
                    if ( !NTStatusSymbolicName )
                    {
                      StringCchPrintfW(AddressString, v119, L"NTSTATUS=%08X", v122);
                      goto LABEL_454;
                    }
                    goto LABEL_193;
                  }
                  v114 = v113 - 1;
                  if ( !v114 )
                  {
                    v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                    if ( v13 < 4 )
                      goto LABEL_463;
                    v121 = v17->S_un.S_addr;
                    s_w1 = 4;
                    NTStatusSymbolicName = FetchWinErrorSymbolicName(v17->S_un.S_addr, 2);
                    v118 = v121;
                    v66 = AddressString;
                    v119 = (unsigned __int64)a5 >> 1;
                    if ( !NTStatusSymbolicName )
                    {
                      StringCchPrintfW(AddressString, v119, L"WINERROR=%8X", v121);
                      goto LABEL_454;
                    }
                    v120 = L"%d(%S)";
LABEL_194:
                    StringCchPrintfW(v66, v119, v120, v118, NTStatusSymbolicName);
                    goto LABEL_454;
                  }
                  v115 = v114 - 1;
                  if ( v115 )
                  {
                    if ( v115 == 1 )
                    {
                      v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                      if ( v13 < 4 )
                        goto LABEL_463;
                      v116 = v17->S_un.S_addr;
                      s_w1 = 4;
                      if ( (unsigned __int8)IsGetNetEventSymbolicNamePresent(v18, 2) )
                      {
                        NTStatusSymbolicName = GetNdisOidSymbolicName(v116);
                        goto LABEL_192;
                      }
LABEL_191:
                      NTStatusSymbolicName = 0;
                      goto LABEL_192;
                    }
LABEL_31:
                    ++v17;
                    goto LABEL_456;
                  }
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                  if ( v13 < 4 )
                    goto LABEL_463;
                  v116 = v17->S_un.S_addr;
                  s_w1 = 4;
                  if ( !(unsigned __int8)IsGetNetEventSymbolicNamePresent(v18, 2) )
                    goto LABEL_191;
                  NTStatusSymbolicName = GetNdisSymbolicName(v116);
LABEL_192:
                  v118 = v116;
                  v66 = AddressString;
                  v119 = (unsigned __int64)a5 >> 1;
                  if ( NTStatusSymbolicName )
                  {
LABEL_193:
                    v120 = L"0x%08x(%S)";
                    goto LABEL_194;
                  }
LABEL_242:
                  StringCchPrintfW(v66, v119, L"0x%08x", v118);
                  goto LABEL_454;
                }
                v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                if ( v13 < 8 )
                  goto LABEL_463;
LABEL_210:
                StringSid[0] = *(LPWSTR *)&v17->S_un.S_un_b.s_b1;
                FormatFileTime(
                  v258,
                  AddressString,
                  a5 >> 1,
                  (const union _LARGE_INTEGER *)StringSid,
                  *((_BYTE *)v258 + 160));
LABEL_280:
                s_w1 = 8;
                goto LABEL_454;
              }
              v133 = v27 - 43;
              if ( v133 )
              {
                v134 = v133 - 1;
                if ( v134 )
                {
                  v135 = v134 - 1;
                  if ( v135 )
                  {
                    v136 = v135 - 1;
                    if ( v136 )
                    {
                      v137 = v136 - 1;
                      if ( v137 )
                      {
                        v138 = v137 - 1;
                        if ( !v138 )
                        {
                          v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                          if ( (__int64)v13 < 8 )
                            goto LABEL_463;
                          s_w1 = 8;
                          StringCchPrintfW(
                            AddressString,
                            (unsigned __int64)a5 >> 1,
                            L"%g",
                            *(_QWORD *)&v17->S_un.S_un_b.s_b1);
                          goto LABEL_454;
                        }
                        if ( v138 != 1 )
                          goto LABEL_31;
                        v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                        if ( v13 < 4 )
                          goto LABEL_463;
                        v139 = v17->S_un.S_addr;
                        s_w1 = 4;
                        if ( (v17->S_un.S_addr & 0x80000000) == 0 )
                        {
                          v66 = AddressString;
                          if ( v139 <= 1 )
                          {
                            v67 = L"S_OK";
                            if ( v139 )
                              v67 = L"S_FALSE";
                            v65 = (unsigned __int64)a5 >> 1;
                            goto LABEL_99;
                          }
                          v119 = (unsigned __int64)a5 >> 1;
                          v118 = v139;
                          goto LABEL_242;
                        }
                        if ( (v139 & 0x10000000) != 0 )
                        {
                          v140 = v139;
                          LODWORD(v140) = v139 & 0xEFFFFFFF;
                          WinErrorSymbolicName = FetchNTStatusSymbolicName(v140, 2);
                          goto LABEL_250;
                        }
                        v142 = 0;
                        if ( (v139 & 0x1FFF0000) == 0x70000 )
                        {
                          WinErrorSymbolicName = FetchWinErrorSymbolicName((unsigned __int16)v139, 2);
LABEL_250:
                          v142 = WinErrorSymbolicName;
                        }
                        v64 = v139;
                        v62 = (unsigned __int64)a5 >> 1;
                        if ( v142 )
                        {
                          StringCchPrintfW(AddressString, v62, L"0x%08x(%S)", v139, v142);
                          goto LABEL_454;
                        }
                        v63 = L"HRESULT=%8X";
                        goto LABEL_96;
                      }
                      v143 = 1;
                      v236 = 1;
                    }
                    else
                    {
                      v143 = 2;
                      v236 = 2;
                    }
                  }
                  else
                  {
                    v143 = 4;
                    v236 = 4;
                  }
                  v231 = 0;
                  v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)p_s_b1];
                  v233 = AddressString;
                  Block = (void *)((unsigned __int64)a5 >> 1);
                  v257 = 0;
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
                  memcpy_0(&v231, p_s_b1, v143);
                  memset_0(SubStr, 0, 0x8000u);
                  StringCchCopyExW(
                    AddressString,
                    (unsigned __int64)a5 >> 1,
                    v146,
                    &v233,
                    (unsigned __int64 *)&Block,
                    cchWideChar);
                  v147 = v233;
                  StringCchPrintfW(SubStr, 0x4000u, L"%s", *(_QWORD *)(v238 + 32));
                  v148 = o_wcstok_s_0(SubStr, L",", &v257);
                  v149 = v231;
                  while ( 1 )
                  {
                    v150 = v148;
                    if ( !v148 )
                      break;
                    if ( _bittest((const int *)&v149, v144) )
                    {
                      if ( !v145 )
                      {
                        StringCchCatExW(
                          v147,
                          (unsigned __int64)Block,
                          L",",
                          &v233,
                          (unsigned __int64 *)&Block,
                          cchWideChara);
                        v147 = v233;
                      }
                      StringCchCatExW(
                        v147,
                        (unsigned __int64)Block,
                        v150,
                        &v233,
                        (unsigned __int64 *)&Block,
                        cchWideChara);
                      v147 = v233;
                      v145 = 0;
                    }
                    v148 = o_wcstok_s_0(0, L",", &v257);
                    ++v144;
                  }
                  while ( v144 < (unsigned __int64)(8 * v143) )
                  {
                    if ( _bittest((const int *)&v149, v144) )
                    {
                      ConvertUnsignedInt(v272);
                      if ( !v145 )
                      {
                        StringCchCatExW(
                          v147,
                          (unsigned __int64)Block,
                          L",",
                          &v233,
                          (unsigned __int64 *)&Block,
                          cchWideChara);
                        v147 = v233;
                      }
                      StringCchCatExW(
                        v147,
                        (unsigned __int64)Block,
                        v272,
                        &v233,
                        (unsigned __int64 *)&Block,
                        cchWideChara);
                      v147 = v233;
                      v145 = 0;
                    }
                    ++v144;
                  }
                  StringCchCatExW(v147, (unsigned __int64)Block, L"]", &v233, (unsigned __int64 *)&Block, cchWideChara);
LABEL_275:
                  s_w1 = v236;
LABEL_276:
                  v17 = (struct in_addr *)StringSid[0];
                  goto LABEL_454;
                }
                v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                if ( v13 < 8 )
                  goto LABEL_463;
                v151 = AddressString;
                v152 = (unsigned __int64)a5 >> 1;
              }
              else
              {
                v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                if ( v13 < 8 )
                  goto LABEL_463;
                if ( *(__int64 *)&v17->S_un.S_un_b.s_b1 > 0 )
                  goto LABEL_210;
                v152 = ((unsigned __int64)a5 >> 1) - 1;
                *AddressString = 43;
                v151 = AddressString + 1;
              }
              FormatTimeDelta(v151, v152);
              goto LABEL_280;
            }
            v153 = *(const wchar_t **)(v18 + 32);
            v247 = 0;
            if ( swscanf(v153, L"%d", &v247) == -1 )
              goto LABEL_455;
            s_w1 = v247;
            if ( v247 > 0x4000uLL )
              s_w1 = 0x3FFF;
            if ( (__int64)Src + v235 - (_QWORD)v17 < s_w1 )
            {
              v13 = (unsigned __int64)TracePrinter;
              if ( !TracePrinter )
                goto LABEL_468;
              v223 = (wchar_t *)L"Invalid payload length";
              goto LABEL_481;
            }
            v11 = AddressString;
            if ( (__int64)v260 + a5 - (_QWORD)AddressString < s_w1 )
              goto LABEL_494;
            v154 = (unsigned int)s_w1;
          }
          memcpy_0(v11, v17, v154);
          goto LABEL_454;
        }
        if ( v27 == 33 )
        {
          s_w1 = 1;
          goto LABEL_164;
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
                goto LABEL_378;
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
                      if ( v27 != 23 )
                      {
                        AddressStringLength = a5 >> 1;
                        Address = 0;
                        v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
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
                        goto LABEL_455;
                      }
                      s_w1 = 4;
                      if ( (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17] >= 4 )
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
                          v53 = v17->S_un.S_un_b.s_b1;
                        else
                          v53 = 32;
                        cchWideChar = s_b3;
                        LODWORD(lpWideCharStr) = s_b2;
                        StringCchPrintfW(v20, (unsigned __int64)a5 >> 1, L"%c%c%c%c", v53, lpWideCharStr);
                        goto LABEL_455;
                      }
                      StringCchCopyW(v20, (unsigned __int64)a5 >> 1, L"0000");
                      v19 = TracePrinter;
                      if ( TracePrinter )
                      {
                        if ( DebugExtPrint )
                          TracePrinterExt((wchar_t *)L"ItemChar4 Invalid payload length");
                        else
                          TracePrinter(L"ItemChar4 Invalid payload length");
                        goto LABEL_455;
                      }
LABEL_456:
                      v12 = v250;
                      *(_QWORD *)(v261 + 8LL * (unsigned int)*v250) = v20;
                      if ( v246 )
                      {
                        v221 = 8;
                      }
                      else
                      {
                        v220 = -1;
                        do
                          ++v220;
                        while ( AddressString[v220] );
                        v221 = 2 * v220 + 2;
                        v20 = AddressString;
                      }
                      v20 = (unsigned __int16 *)((char *)v20 + v221);
                      a5 -= v221;
                      AddressString = v20;
                      goto LABEL_462;
                    }
LABEL_411:
                    cchName = 0;
                    v207 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
                    cchReferencedDomainName = 0;
                    peUse = 0;
                    v208 = (unsigned int)S_addr;
                    if ( v207 < 4 )
                      goto LABEL_463;
                    if ( !v17->S_un.S_addr )
                    {
                      StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"<NULL>");
                      goto LABEL_280;
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
                  v13 = (unsigned __int64)&v15[S_addr - (_QWORD)v17];
                  if ( v13 < 2 )
                    goto LABEL_463;
                  v17 = (struct in_addr *)((char *)v17 + 2);
                  if ( v27 == 21 )
                  {
                    v202 = *p_s_b1;
                    v203 = p_s_b1[1];
                  }
                  else
                  {
                    v202 = p_s_b1[1];
                    v203 = *p_s_b1;
                  }
                  v204 = v203 + (v202 << 8);
                  v205 = 2 * v204;
                  if ( v27 != 65 )
                    v205 = v204;
                  v206 = v205;
                  if ( v205 > (__int64)&v15[S_addr - (_QWORD)v17] )
                  {
                    if ( v19 )
                    {
                      if ( DebugExtPrint )
                        TracePrinterExt((wchar_t *)L"Corrupted payload. Type = %d", (unsigned int)v27);
                      else
                        v19(L"Corrupted payload. Type = %d", (unsigned int)v27);
                      LOWORD(v15) = (_WORD)Src;
                    }
                    v206 = (_WORD)v15 + v235 - (_WORD)v17;
                  }
                  s_w1 = v206;
                  if ( !v206 )
                  {
                    v65 = (unsigned __int64)a5 >> 1;
                    goto LABEL_98;
                  }
                  v60 = SubStr;
                  memcpy_0(SubStr, v17, v206);
                  v62 = (unsigned __int64)a5 >> 1;
                  v60[(unsigned __int64)(unsigned int)s_w1 >> 1] = 0;
LABEL_95:
                  v63 = L"%ws";
                  v64 = (unsigned __int64)v60;
LABEL_96:
                  StringCchPrintfW(AddressString, v62, v63, v64);
                  goto LABEL_454;
                }
              }
              v54 = (unsigned int)S_addr;
              v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
              if ( v13 < 2 )
                goto LABEL_463;
              v55 = v17->S_un.S_un_b.s_b2;
              if ( v27 == 20 )
                v56 = (v17->S_un.S_un_b.s_b1 << 8) + v55;
              else
                v56 = v17->S_un.S_un_b.s_b1 + (v55 << 8);
              v57 = v248;
              v17 = (struct in_addr *)((char *)v17 + 2);
              if ( ResizeBuffer((unsigned int)v56 + 1, v248, v254) == 8
                || (v58 = (CHAR *)*v57,
                    v59 = v249,
                    lpMultiByteStr = v58,
                    ResizeBuffer(2 * ((unsigned int)v56 + 1), v249, v242) == 8) )
              {
LABEL_479:
                v13 = (unsigned __int64)TracePrinter;
                if ( !TracePrinter )
                  goto LABEL_468;
                v223 = (wchar_t *)L"Not enough memory";
LABEL_481:
                if ( !DebugExtPrint )
                {
LABEL_467:
                  LODWORD(v13) = ((__int64 (__fastcall *)(wchar_t *, __int64, __int64))v13)(v223, v21, S_addr);
                  goto LABEL_468;
                }
                goto LABEL_473;
              }
              s_w1 = v56;
              if ( (__int64)Src + v54 - (__int64)v17 < v56 )
                goto LABEL_483;
              v60 = (WCHAR *)*v59;
              SubStr = v60;
              if ( !v56 )
                goto LABEL_97;
              memcpy_0(v58, v17, v56);
              v61 = v242;
              v58[v56] = 0;
              MultiByteToWideChar(0, 0, v58, -1, v60, *v61 >> 1);
LABEL_94:
              v62 = (unsigned __int64)a5 >> 1;
              goto LABEL_95;
            }
            v252 = a5 >> 1;
            v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
            if ( (__int64)v13 < 16 )
              goto LABEL_463;
            v11 = AddressString;
            v268 = *(struct in6_addr *)&v17->S_un.S_un_b.s_b1;
            if ( RtlIpv6AddressToStringExW(&v268, 0, 0, AddressString, &v252) )
            {
              v13 = (unsigned __int64)TracePrinter;
              if ( TracePrinter )
              {
                v14 = L"RtlIpv6AddressToStringExW failed to convert IPv6 address";
                goto LABEL_4;
              }
              goto LABEL_469;
            }
LABEL_102:
            s_w1 = 16;
            goto LABEL_454;
          }
          v68 = v27 - 26;
          if ( !v68 )
          {
            v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
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
          v69 = v68 - 1;
          if ( !v69 )
          {
            v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
            if ( v13 < 2 )
              goto LABEL_463;
            v63 = L"%u";
            s_w1 = 2;
            v64 = (v17->S_un.S_un_b.s_b1 << 8) + (unsigned int)v17->S_un.S_un_b.s_b2;
            v62 = (unsigned __int64)a5 >> 1;
            goto LABEL_96;
          }
          v70 = v69 - 1;
          if ( !v70 )
          {
            v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
            if ( v13 < 2 )
              goto LABEL_463;
            v17 = (struct in_addr *)((char *)v17 + 2);
            v21 = (__int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
            if ( !v21 )
              goto LABEL_463;
            s_w1 = -1;
            do
              ++s_w1;
            while ( *(&v17->S_un.S_un_b.s_b1 + s_w1) );
            LODWORD(v13) = s_w1;
            v236 = s_w1;
            if ( v21 < (unsigned int)s_w1 )
              goto LABEL_463;
            if ( !s_w1 )
              goto LABEL_456;
            v88 = lpMultiByteStr;
            v89 = 0;
            v90 = 0;
            v91 = 0;
            LODWORD(v92) = 0;
            LODWORD(v93) = 0;
            for ( i = v17; ; i = (struct in_addr *)((char *)i + 1) )
            {
              v95 = i->S_un.S_un_b.s_b1;
              if ( !i->S_un.S_un_b.s_b1 )
                break;
              v92 = (unsigned int)(v93 + v92);
              LODWORD(v93) = 0;
              if ( v95 == 10 )
              {
                if ( !v91 )
                {
                  v88[v92] = 32;
                  LODWORD(v93) = 1;
                }
                ++v91;
              }
              else if ( v95 == 34 )
              {
                if ( v89 )
                {
                  StringCchPrintfA(v269, 0x20u, "{%dx}", v91);
                  v93 = -1;
                  do
                    ++v93;
                  while ( v269[v93] );
                  if ( ResizeBuffer((unsigned int)(v93 + v92), v248, v254) == 8 )
                    goto LABEL_479;
                  v96 = (char *)*v248 + (unsigned int)v92;
                  lpMultiByteStr = (LPCCH)*v248;
                  memcpy_0(v96, v269, (unsigned int)v93);
                  v88 = lpMultiByteStr;
                }
                v89 = !v89;
              }
              else if ( !v90 )
              {
                v88[v92] = v95;
                LODWORD(v93) = 1;
              }
              if ( v91 > 1 )
              {
                v90 = 1;
                if ( v89 )
                  continue;
              }
              v90 = 0;
            }
            v97 = SubStr;
            v98 = lpMultiByteStr;
            lpMultiByteStr[(unsigned int)v92] = 0;
            MultiByteToWideChar(0, 0, v98, -1, v97, *v242 >> 1);
            StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%ws", v97);
            s_w1 = v236;
            goto LABEL_454;
          }
          v71 = v70 - 1;
          if ( !v71 )
          {
            v86 = v249;
            v87 = (unsigned __int16)((_WORD)v15 + S_addr - (_WORD)v17);
            if ( ResizeBuffer(v87 + 1, v249, v242) == 8 )
              goto LABEL_479;
            v60 = (WCHAR *)*v86;
            s_w1 = v87;
            SubStr = v60;
            if ( !(_WORD)v87 )
              goto LABEL_455;
            memcpy_0(v60, v17, v87);
            v60[(unsigned __int64)v87 >> 1] = 0;
            goto LABEL_94;
          }
          v72 = v71 - 1;
          if ( !v72 )
          {
            s_w1 = (unsigned int)Size;
            StringSid[0] = 0;
            v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
            if ( (__int64)v13 < (unsigned int)Size )
              goto LABEL_463;
            if ( (unsigned int)Size > 8 )
            {
              if ( v19 )
              {
                v223 = L"Invalid pointer size";
                goto LABEL_465;
              }
              goto LABEL_468;
            }
            v74 = *(const wchar_t **)(v259 + 56);
            memcpy_0(StringSid, v17, (unsigned int)Size);
            v75 = SubStr;
            StringCchPrintfW(SubStr, 0x4000u, L"%%%d", (unsigned int)(*v250 + 1));
            v76 = wcsstr(v74, v75);
            if ( !v76 )
              goto LABEL_127;
            v77 = -1;
            do
              ++v77;
            while ( v75[v77] );
            if ( v76[v77] != 33
              || (*v75 = 37, v78 = &v76[v77 + 1], (v79 = wcschr(v78, 0x21u)) == 0)
              || (v80 = v79 - 1, v79 - 1 <= v78)
              || *v80 == 112 )
            {
LABEL_127:
              v85 = (unsigned __int64)a5 >> 1;
              if ( (_DWORD)Size == 8 )
                StringCchPrintfW(AddressString, v85, L"%016I64X", StringSid[0]);
              else
                StringCchPrintfW(AddressString, v85, L"%08X", LODWORD(StringSid[0]));
              goto LABEL_454;
            }
            v81 = SubStr + 1;
            v82 = ((char *)v80 - (char *)v78 - 2) >> 1;
            if ( v82 <= 0x7FFFFFFE )
              StringCopyWorkerW_0(v81, 0x3FFFu, 0, v78, ((char *)v80 - (char *)v78 - 2) >> 1);
            else
              *v81 = 0;
            v83 = SubStr;
            v84 = &SubStr[v82 + 1];
            if ( (_DWORD)Size == 4 )
            {
              v64 = LODWORD(StringSid[0]);
              v63 = SubStr;
              *v84 = *v80;
              v62 = (unsigned __int64)a5 >> 1;
              v83[v82 + 2] = 0;
            }
            else
            {
              StringCchPrintfW(v84, 0x3FFFu, L"I64%c", *v80);
              v64 = (unsigned __int64)StringSid[0];
              v63 = v83;
              v62 = (unsigned __int64)a5 >> 1;
            }
            goto LABEL_96;
          }
          v73 = v72 - 1;
          if ( v73 )
          {
            if ( v73 != 1 )
              goto LABEL_30;
            s_w1 = 2;
          }
          else
          {
            s_w1 = 4;
          }
LABEL_164:
          EndPtr = 0;
          v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
          v231 = 0;
          Context = 0;
          if ( (__int64)v13 < s_w1 )
            goto LABEL_463;
          v99 = 0;
          memcpy_0(&v231, v17, s_w1);
          v100 = SubStr;
          memset_0(SubStr, 0, 0x8000u);
          StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"!0x%X!", v231);
          StringCchPrintfW(v100, 0x4000u, L"%s", *(_QWORD *)(v238 + 32));
          for ( j = v100; ; j = 0 )
          {
            v102 = o_wcstok_s_0(j, L",", &Context);
            v103 = v102;
            if ( !v102 )
              break;
            v104 = wcsstr(v102, L"=");
            v105 = v104;
            if ( v104 )
            {
              v106 = v104 + 1;
              v107 = wcsstr(v104 + 1, L"0X");
              if ( v107 || (v107 = wcsstr(v106, L"0x")) != 0 )
                v108 = wcstoul(v107, &EndPtr, 16);
              else
                v108 = wcstol(v106, &EndPtr, 10);
              v99 = v108;
            }
            if ( v231 == v99 )
            {
              cchWideChar = (unsigned int)v103;
              LODWORD(lpWideCharStr) = v105 - v103;
              StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"0x%08x(%.*s)", v99, lpWideCharStr);
              goto LABEL_454;
            }
            ++v99;
          }
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
                s_w1 = v236;
                goto LABEL_31;
              }
LABEL_378:
              v189 = v249;
              v190 = &v17->S_un.S_un_b.s_b3;
              v191 = (unsigned int)S_addr;
              v192 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)&v17->S_un.S_un_w.s_w2];
              if ( ResizeBuffer(2 * (unsigned int)(v192 >> 1) + 2, v249, v242) == 8 )
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
                  v196 = v192 < 2;
                  v197 = SubStr;
                  v198 = 1;
                  if ( !v196 )
                  {
                    do
                    {
                      v199 = v190 + 1;
                      LOBYTE(v197[v198]) = *v190;
                      HIBYTE(v197[v198]) = v190[1];
                      if ( !v197[v198] )
                      {
                        if ( !--v28 )
                          break;
                        v197[v198] = 9;
                      }
                      v190 += 2;
                      ++v198;
                    }
                    while ( (unsigned __int64)v194 + v191 - (_QWORD)(v199 + 1) >= 2 );
                    v17 = (struct in_addr *)StringSid[0];
                  }
                  v200 = v238;
                  v197[v198] = 0;
                  if ( *(_DWORD *)(v200 + 40) == 17 )
                    reduceW(v197);
                  for ( k = 0; k < v198; ++k )
                  {
                    if ( v197[k] == 0xFFFF )
                      v197[k] = 0;
                  }
                  StringCchPrintfW(AddressString, (unsigned __int64)a5 >> 1, L"%ws", v197);
                  s_w1 = 2LL * (v198 + 1);
                  goto LABEL_454;
                }
              }
              s_w1 = 2;
LABEL_97:
              v65 = (unsigned __int64)a5 >> 1;
LABEL_98:
              v66 = AddressString;
              v67 = L"<NULL>";
LABEL_99:
              StringCchCopyW(v66, v65, v67);
              goto LABEL_454;
            }
LABEL_48:
            v41 = -1;
            do
              ++v41;
            while ( *(&v17->S_un.S_un_b.s_b1 + v41) );
            s_w1 = (unsigned int)(v41 + 1);
            v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
            if ( (__int64)v13 < s_w1 )
              goto LABEL_463;
            if ( (_DWORD)v41 )
            {
              v42 = v248;
              if ( ResizeBuffer((unsigned int)(v41 + 1), v248, v254) == 8 )
                goto LABEL_479;
              v43 = (const CHAR *)*v42;
              v44 = v249;
              lpMultiByteStr = v43;
              if ( ResizeBuffer((unsigned int)(2 * v41 + 2), v249, v242) == 8 )
                goto LABEL_479;
              v45 = (WCHAR *)*v44;
              v46 = (unsigned int)v41;
              v47 = (unsigned int)v41;
              v48 = lpMultiByteStr;
              SubStr = v45;
              memcpy_0((void *)lpMultiByteStr, v17, v46);
              v49 = v238;
              v48[v47] = 0;
              if ( *(_DWORD *)(v49 + 40) == 16 )
                reduce(v48);
              v50 = SubStr;
              MultiByteToWideChar(0, 0, v48, -1, SubStr, *v242 >> 1);
              StringCchPrintfW(v20, (unsigned __int64)a5 >> 1, L"%ws", v50);
            }
            else
            {
              StringCchCopyW(v20, (unsigned __int64)a5 >> 1, L"<NULL>");
            }
LABEL_455:
            v19 = TracePrinter;
          }
          else
          {
            v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
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
            v246 = 1;
          }
          goto LABEL_456;
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
        v13 = (unsigned __int64)&v15[(unsigned int)S_addr - (_QWORD)v17];
        if ( (__int64)v13 < s_w1 )
          goto LABEL_463;
        memcpy_0((void *)(v261 + 8LL * (unsigned int)*v250), v17, s_w1);
        v12 = v250;
LABEL_462:
        v222 = (__int64 *)v238;
        v17 = (struct in_addr *)((char *)v17 + s_w1);
        v15 = (char *)Src;
        ++*v12;
        v13 = v262;
        v18 = *v222;
      }
    }
  }
  v13 = (unsigned __int64)TracePrinter;
  if ( TracePrinter )
  {
    v14 = (wchar_t *)L"Not enough memory";
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
0x1800cd530  push    rbp
0x1800cd532  push    rbx
0x1800cd533  push    rsi
0x1800cd534  push    rdi
0x1800cd535  push    r12
0x1800cd537  push    r13
0x1800cd539  push    r14
0x1800cd53b  push    r15
0x1800cd53d  lea     rbp, [rsp-3C8h]
0x1800cd545  sub     rsp, 4D8h
0x1800cd54c  mov     rax, cs:__security_cookie
0x1800cd553  xor     rax, rsp
0x1800cd556  mov     [rbp+400h+var_50], rax
0x1800cd55d  mov     rdi, [rbp+400h+arg_48]
0x1800cd564  mov     r15, rcx
0x1800cd567  mov     eax, [rbp+400h+arg_20]
0x1800cd56d  mov     rbx, r9
0x1800cd570  mov     r14, [rbp+400h+arg_40]
0x1800cd577  mov     [rbp+400h+var_480], eax
0x1800cd57a  mov     rax, [rbp+400h+arg_28]
0x1800cd581  lea     rsi, [rdi+10h]
0x1800cd585  mov     [rbp+400h+var_3A0], rax
0x1800cd589  mov     rax, [rbp+400h+arg_30]
0x1800cd590  mov     [rbp+400h+var_3B8], rax
0x1800cd594  lea     rax, [rdi+18h]
0x1800cd598  mov     [rbp+400h+var_450], r8d
0x1800cd59c  mov     r8, rax; unsigned int *
0x1800cd59f  mov     [rbp+400h+Src], rdx
0x1800cd5a3  mov     rdx, rsi; void **
0x1800cd5a6  mov     [rbp+400h+var_3B0], rcx
0x1800cd5aa  mov     ecx, 4000h; Size
0x1800cd5af  mov     [rbp+400h+var_3A8], r9
0x1800cd5b3  mov     [rbp+400h+var_3F8], rdi
0x1800cd5b7  mov     [rbp+400h+var_3F0], r14
0x1800cd5bb  mov     [rbp+400h+AddressString], rbx
0x1800cd5bf  mov     [rbp+400h+var_3D8], rax
0x1800cd5c3  mov     [rbp+400h+var_400], rsi
0x1800cd5c7  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x1800cd5cc  cmp     eax, 8
0x1800cd5cf  jnz     short loc_1800CD606
0x1800cd5d1  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cd5d8  xor     esi, esi
0x1800cd5da  test    rax, rax
0x1800cd5dd  jz      loc_1800CF787
0x1800cd5e3  lea     rcx, aNotEnoughMemor_2; "Not enough memory"
0x1800cd5ea  cmp     cs:?DebugExtPrint@@3HA, esi; int DebugExtPrint
0x1800cd5f0  jnz     short loc_1800CD5FC
0x1800cd5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5f7  jmp     loc_1800CF787
0x1800cd5fc  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800cd601  jmp     loc_1800CF787
0x1800cd606  mov     rax, [rsi]
0x1800cd609  mov     rdx, rdi; void **
0x1800cd60c  mov     [rbp+400h+lpMultiByteStr], rax
0x1800cd610  mov     ecx, 8000h; Size
0x1800cd615  lea     rax, [rdi+8]
0x1800cd619  mov     r8, rax; unsigned int *
0x1800cd61c  mov     [rbp+400h+var_420], rax
0x1800cd620  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x1800cd625  cmp     eax, 8
0x1800cd628  jz      short loc_1800CD5D1
0x1800cd62a  mov     rax, [r15+20h]
0x1800cd62e  mov     r10d, 1
0x1800cd634  mov     r11, [rbp+400h+Src]
0x1800cd638  mov     r9, [rdi]
0x1800cd63b  mov     r13, r11
0x1800cd63e  add     [r15+8], r10d
0x1800cd642  mov     rcx, [rax]
0x1800cd645  xor     esi, esi
0x1800cd647  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cd64e  mov     r15, [rbp+400h+AddressString]
0x1800cd652  mov     [rbp+400h+StringSid], r11
0x1800cd659  mov     [rbp+400h+SubStr], r9
0x1800cd65d  mov     [rbp+400h+var_398], rax
0x1800cd661  mov     [rbp+400h+StringSid], r11
0x1800cd668  mov     [rbp+400h+var_438], rcx
0x1800cd66c  mov     r9d, 4
0x1800cd672  mov     edi, 100h
0x1800cd677  lea     edx, [r9-2]
0x1800cd67b  cmp     rax, rcx
0x1800cd67e  jz      loc_1800CF783
0x1800cd684  mov     r8d, [rbp+400h+var_450]
0x1800cd688  mov     eax, r13d
0x1800cd68b  sub     eax, r11d
0x1800cd68e  cmp     eax, r8d
0x1800cd691  jnb     loc_1800CF783
0x1800cd697  mov     eax, [r14]
0x1800cd69a  cmp     eax, edi
0x1800cd69c  jz      loc_1800CF783
0x1800cd6a2  mov     [rbp+400h+var_40C], esi
0x1800cd6a5  mov     r14, r13
0x1800cd6a8  mov     [rbp+400h+var_448], rsi
0x1800cd6ac  mov     r12, rsi
0x1800cd6af  test    rbx, rbx
0x1800cd6b2  jz      loc_1800CD73F
0x1800cd6b8  movsxd  r9, dword ptr [rcx+28h]
0x1800cd6bc  lea     edx, [rax+1]
0x1800cd6bf  mov     eax, [rbp+400h+var_450]
0x1800cd6c2  lea     r10, ?str_item@@3QBQEBGB; ushort const * const near * const str_item
0x1800cd6c9  mov     r8, [rcx+10h]
0x1800cd6cd  sub     rax, r13
0x1800cd6d0  cmp     cs:?DebugExtPrint@@3HA, esi; int DebugExtPrint
0x1800cd6d6  mov     r10, [r10+r9*8]
0x1800cd6da  jnz     short loc_1800CD700
0x1800cd6dc  lea     rcx, [r11+rax]
0x1800cd6e0  mov     rax, rbx
0x1800cd6e3  mov     [rsp+510h+Arguments], rcx
0x1800cd6e8  lea     rcx, aParam03dSItemt; "Param %03d (%s) itemType %3d(%s) data P"...
0x1800cd6ef  mov     qword ptr [rsp+510h+cchWideChar], r13
0x1800cd6f4  mov     [rsp+510h+lpWideCharStr], r10
0x1800cd6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd6fe  jmp     short loc_1800CD71E
0x1800cd700  add     rax, r11
0x1800cd703  lea     rcx, aParam03dSItemt; "Param %03d (%s) itemType %3d(%s) data P"...
0x1800cd70a  mov     [rsp+510h+Arguments], rax
0x1800cd70f  mov     qword ptr [rsp+510h+cchWideChar], r13; unsigned int
0x1800cd714  mov     [rsp+510h+lpWideCharStr], r10
0x1800cd719  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x1800cd71e  mov     rcx, [rbp+400h+var_438]
0x1800cd722  mov     r10d, 1
0x1800cd728  mov     r8d, [rbp+400h+var_450]
0x1800cd72c  mov     r11, [rbp+400h+Src]
0x1800cd730  mov     rbx, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x1800cd737  lea     r9d, [r10+3]
0x1800cd73b  lea     edx, [r10+1]
0x1800cd73f  mov     edi, [rcx+28h]
0x1800cd742  mov     eax, 21h ; '!'
0x1800cd747  cmp     edi, eax
0x1800cd749  jg      loc_1800CE214
0x1800cd74f  jz      loc_1800CE0D0
0x1800cd755  mov     eax, 10h
0x1800cd75a  movzx   r12d, r10w
0x1800cd75e  cmp     edi, eax
0x1800cd760  jg      loc_1800CD943
0x1800cd766  jz      loc_1800CD847
0x1800cd76c  cmp     edi, 8
0x1800cd76f  jg      short loc_1800CD7E9
0x1800cd771  jz      short loc_1800CD7B1
0x1800cd773  test    edi, edi
0x1800cd775  jz      short loc_1800CD7AC
0x1800cd777  sub     edi, 1
0x1800cd77a  jz      short loc_1800CD7AC
0x1800cd77c  sub     edi, 1
0x1800cd77f  jz      short loc_1800CD7AC
0x1800cd781  sub     edi, 1
0x1800cd784  jz      short loc_1800CD7A7
0x1800cd786  sub     edi, 1
0x1800cd789  jz      short loc_1800CD7A7
0x1800cd78b  sub     edi, 1
0x1800cd78e  jz      short loc_1800CD7A7
0x1800cd790  sub     edi, 1
0x1800cd793  jz      short loc_1800CD7B1
0x1800cd795  cmp     edi, 1
0x1800cd798  jz      short loc_1800CD7B1
0x1800cd79a  mov     r12, [rbp+400h+var_448]
0x1800cd79e  add     r13, 4
0x1800cd7a2  jmp     loc_1800CF6FE
0x1800cd7a7  mov     r12, rdx
0x1800cd7aa  jmp     short loc_1800CD7B4
0x1800cd7ac  mov     r12, r10
0x1800cd7af  jmp     short loc_1800CD7B4
0x1800cd7b1  mov     r12, r9
0x1800cd7b4  mov     eax, r8d
0x1800cd7b7  sub     rax, r14
0x1800cd7ba  add     rax, r11
0x1800cd7bd  cmp     rax, r12
0x1800cd7c0  jl      loc_1800CF767
0x1800cd7c6  mov     r9, [rbp+400h+var_3F0]
0x1800cd7ca  mov     r8, r12; Size
0x1800cd7cd  mov     rcx, [rbp+400h+var_3A0]
0x1800cd7d1  mov     rdx, r14; Src
0x1800cd7d4  mov     eax, [r9]
0x1800cd7d7  lea     rcx, [rcx+rax*8]; void *
0x1800cd7db  call    memcpy_0
0x1800cd7e0  mov     r14, [rbp+400h+var_3F0]
0x1800cd7e4  jmp     loc_1800CF740
0x1800cd7e9  sub     edi, 9
0x1800cd7ec  jz      short loc_1800CD812
0x1800cd7ee  sub     edi, 1
0x1800cd7f1  jz      short loc_1800CD812
0x1800cd7f3  sub     edi, 1
0x1800cd7f6  jz      short loc_1800CD812
0x1800cd7f8  sub     edi, 1
0x1800cd7fb  jz      short loc_1800CD812
0x1800cd7fd  sub     edi, 1
0x1800cd800  jz      short loc_1800CD812
0x1800cd802  sub     edi, 1
0x1800cd805  jz      short loc_1800CD847
0x1800cd807  cmp     edi, 1
0x1800cd80a  jz      loc_1800CF0AF
0x1800cd810  jmp     short loc_1800CD79A
0x1800cd812  mov     eax, r8d
0x1800cd815  sub     rax, r13
0x1800cd818  add     rax, r11
0x1800cd81b  cmp     rax, 8
0x1800cd81f  jb      loc_1800CF767
0x1800cd825  mov     edi, [rbp+400h+var_480]
0x1800cd828  cmp     edi, 8
0x1800cd82b  jb      loc_1800CF7BB
0x1800cd831  mov     rax, [r13+0]
0x1800cd835  mov     r12d, 8
0x1800cd83b  mov     [r15], rax
0x1800cd83e  mov     [rbp+400h+var_40C], r10d
0x1800cd842  jmp     loc_1800CF6FE
0x1800cd847  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800cd84b  inc     rdi
0x1800cd84e  cmp     [rdi+r13], sil
0x1800cd852  jnz     short loc_1800CD84B
0x1800cd854  mov     eax, r8d
0x1800cd857  lea     ecx, [rdi+1]; Size
0x1800cd85a  sub     rax, r14
0x1800cd85d  mov     r12d, ecx
0x1800cd860  add     rax, r11
0x1800cd863  cmp     rax, r12
0x1800cd866  jl      loc_1800CF767
0x1800cd86c  test    edi, edi
0x1800cd86e  jz      loc_1800CD929
0x1800cd874  mov     rbx, [rbp+400h+var_400]
0x1800cd878  mov     r8, [rbp+400h+var_3D8]; unsigned int *
0x1800cd87c  mov     rdx, rbx; void **
0x1800cd87f  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x1800cd884  cmp     eax, 8
0x1800cd887  jz      loc_1800CF7E4
0x1800cd88d  mov     rax, [rbx]
0x1800cd890  lea     ecx, ds:2[rdi*2]; Size
0x1800cd897  mov     rbx, [rbp+400h+var_3F8]
0x1800cd89b  mov     r8, [rbp+400h+var_420]; unsigned int *
0x1800cd89f  mov     rdx, rbx; void **
0x1800cd8a2  mov     [rbp+400h+lpMultiByteStr], rax
0x1800cd8a6  call    ?ResizeBuffer@@YAKKPEAPEAXPEAK@Z; ResizeBuffer(ulong,void * *,ulong *)
0x1800cd8ab  cmp     eax, 8
0x1800cd8ae  jz      loc_1800CF7E4
0x1800cd8b4  mov     rax, [rbx]
0x1800cd8b7  mov     rdx, r14; Src
0x1800cd8ba  mov     r8d, edi; Size
0x1800cd8bd  mov     ebx, edi
0x1800cd8bf  mov     rdi, [rbp+400h+lpMultiByteStr]
0x1800cd8c3  mov     rcx, rdi; void *
0x1800cd8c6  mov     [rbp+400h+SubStr], rax
0x1800cd8ca  call    memcpy_0
0x1800cd8cf  mov     r9, [rbp+400h+var_438]
0x1800cd8d3  mov     [rbx+rdi], sil
0x1800cd8d7  cmp     dword ptr [r9+28h], 10h
0x1800cd8dc  jnz     short loc_1800CD8E6
0x1800cd8de  mov     rcx, rdi
0x1800cd8e1  call    reduce
0x1800cd8e6  mov     rax, [rbp+400h+var_420]
0x1800cd8ea  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800cd8ee  mov     rbx, [rbp+400h+SubStr]
0x1800cd8f2  mov     r8, rdi; lpMultiByteStr
0x1800cd8f5  xor     edx, edx; dwFlags
0x1800cd8f7  xor     ecx, ecx; CodePage
0x1800cd8f9  mov     eax, [rax]
0x1800cd8fb  shr     eax, 1
0x1800cd8fd  mov     [rsp+510h+cchWideChar], eax; cchWideChar
0x1800cd901  mov     [rsp+510h+lpWideCharStr], rbx; lpWideCharStr
0x1800cd906  call    cs:__imp_MultiByteToWideChar
0x1800cd90c  mov     edx, [rbp+400h+var_480]
0x1800cd90f  lea     r8, aWs; "%ws"
0x1800cd916  shr     rdx, 1; unsigned __int64
0x1800cd919  mov     r9, rbx
0x1800cd91c  mov     rcx, r15; unsigned __int16 *
0x1800cd91f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cd924  jmp     loc_1800CF6F7
0x1800cd929  mov     edx, [rbp+400h+var_480]
0x1800cd92c  lea     r8, aNull_2; "<NULL>"
0x1800cd933  shr     rdx, 1; unsigned __int64
0x1800cd936  mov     rcx, r15; unsigned __int16 *
0x1800cd939  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cd93e  jmp     loc_1800CF6F7
0x1800cd943  cmp     edi, 19h
0x1800cd946  jg      loc_1800CDC64
0x1800cd94c  jz      loc_1800CDC06
0x1800cd952  mov     ecx, edi
0x1800cd954  sub     ecx, 11h
0x1800cd957  jz      loc_1800CF0AF
0x1800cd95d  sub     ecx, 1
0x1800cd960  jz      loc_1800CDAF6
0x1800cd966  sub     ecx, 1
0x1800cd969  jz      loc_1800CF1E1
0x1800cd96f  sub     ecx, 1
0x1800cd972  jz      loc_1800CDAF6
0x1800cd978  sub     ecx, 1
0x1800cd97b  jz      loc_1800CF1E1
0x1800cd981  sub     ecx, 1
0x1800cd984  jz      loc_1800CF2A5
0x1800cd98a  sub     ecx, 1
0x1800cd98d  jz      loc_1800CDA29
0x1800cd993  cmp     ecx, 1
0x1800cd996  jnz     loc_1800CD79A
0x1800cd99c  mov     eax, [rbp+400h+var_480]
0x1800cd99f  shr     eax, 1
0x1800cd9a1  mov     [rbp+400h+AddressStringLength], eax
0x1800cd9a4  mov     eax, r8d
0x1800cd9a7  sub     rax, r14
0x1800cd9aa  mov     dword ptr [rbp+400h+Address.S_un], esi
0x1800cd9ad  add     rax, r11
0x1800cd9b0  cmp     rax, r9
0x1800cd9b3  jl      loc_1800CF767
0x1800cd9b9  mov     eax, [r13+0]
  ... truncated ...
```
