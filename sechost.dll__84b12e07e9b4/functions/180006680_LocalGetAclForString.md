# LocalGetAclForString

- ea: `0x180006680`
- end: `0x180007fc4`
- name: `LocalGetAclForString`
- size: `6468`
- prototype: `__int64 __usercall@<rax>(wchar_t *String1@<rcx>, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180005d00`

## callees

- `0x180004f20`
- `0x180006680`
- `0x180008220`
- `0x180008740`
- `0x1800172e4`
- `0x180021930`
- `0x180021b58`
- `0x180021dd8`
- `0x1800224e8`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcsncpy_s` at `0x180007947`
- `api-ms-win-core-crt-l1-1-0!wcsncpy_s` at `0x180007947`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006744`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006795`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800067b3`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800067d1`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800067ef`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000680d`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000682b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006849`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800068da`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800068f8`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006916`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006934`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006952`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006970`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000698e`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006d9a`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006fe5`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000709b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006744`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006795`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800067b3`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800067d1`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800067ef`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000680d`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000682b`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006849`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800068da`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800068f8`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006916`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006934`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006952`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006970`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000698e`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006d9a`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180006fe5`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x18000709b`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180006868`
- `api-ms-win-core-crt-l1-1-0!wcschr` at `0x180006868`
- `api-ms-win-core-crt-l1-1-0!wcstoul` at `0x180006d5e`
- `api-ms-win-core-crt-l1-1-0!wcstoul` at `0x180006d5e`
- `ntdll!RtlCopySid` at `0x180007547`
- `ntdll!RtlCopySid` at `0x1800076d0`
- `ntdll!RtlCopySid` at `0x180007bba`
- `ntdll!RtlCopySid` at `0x180007547`
- `ntdll!RtlCopySid` at `0x1800076d0`
- `ntdll!RtlCopySid` at `0x180007bba`
- `ntdll!RtlNtStatusToDosError` at `0x180007119`
- `ntdll!RtlNtStatusToDosError` at `0x1800077c2`
- `ntdll!RtlNtStatusToDosError` at `0x180007119`
- `ntdll!RtlNtStatusToDosError` at `0x1800077c2`
- `ntdll!RtlValidSid` at `0x18000745d`
- `ntdll!RtlValidSid` at `0x18000745d`
- `ntdll!RtlValidAcl` at `0x1800074cb`
- `ntdll!RtlValidAcl` at `0x1800074cb`
- `ntdll!RtlAddAuditAccessObjectAce` at `0x180007c25`
- `ntdll!RtlAddAuditAccessObjectAce` at `0x180007c25`
- `ntdll!RtlGetAce` at `0x180007d98`
- `ntdll!RtlGetAce` at `0x180007d98`
- `ntdll!RtlAddAuditAccessAceEx` at `0x180007381`
- `ntdll!RtlAddAuditAccessAceEx` at `0x180007381`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000741b`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18000741b`
- `ntdll!RtlAddAce` at `0x180007719`
- `ntdll!RtlAddAce` at `0x180007719`
- `ntdll!RtlAddAccessDeniedAceEx` at `0x180007b15`
- `ntdll!RtlAddAccessDeniedAceEx` at `0x180007b15`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x180007c60`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x180007d7b`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x180007c60`
- `ntdll!RtlAddAccessAllowedObjectAce` at `0x180007d7b`
- `ntdll!RtlAddAccessDeniedObjectAce` at `0x180007d33`
- `ntdll!RtlAddAccessDeniedObjectAce` at `0x180007d33`
- `ntdll!RtlLengthSid` at `0x1800072f7`
- `ntdll!RtlLengthSid` at `0x1800074f3`
- `ntdll!RtlLengthSid` at `0x180007538`
- `ntdll!RtlLengthSid` at `0x1800076c1`
- `ntdll!RtlLengthSid` at `0x1800076e3`
- `ntdll!RtlLengthSid` at `0x180007bab`
- `ntdll!RtlLengthSid` at `0x180007bd1`
- `ntdll!RtlLengthSid` at `0x180007de8`
- `ntdll!RtlLengthSid` at `0x180007e1c`
- `ntdll!RtlLengthSid` at `0x1800072f7`
- `ntdll!RtlLengthSid` at `0x1800074f3`
- `ntdll!RtlLengthSid` at `0x180007538`
- `ntdll!RtlLengthSid` at `0x1800076c1`
- `ntdll!RtlLengthSid` at `0x1800076e3`
- `ntdll!RtlLengthSid` at `0x180007bab`
- `ntdll!RtlLengthSid` at `0x180007bd1`
- `ntdll!RtlLengthSid` at `0x180007de8`
- `ntdll!RtlLengthSid` at `0x180007e1c`
- `ntdll!RtlFirstFreeAce` at `0x1800074e0`
- `ntdll!RtlFirstFreeAce` at `0x1800074e0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007337`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007063`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007127`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006bc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000768e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000776b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007875`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006bc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000768e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000776b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007875`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007636`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007efe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006df0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800073a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007636`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800077a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800079fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007efe`

## string_xrefs

- `0x18000673d`: `NO_ACCESS_CONTROL`

## pseudocode

```c
__int64 __fastcall LocalGetAclForString(
        wchar_t *String1,
        char a2,
        PACL *a3,
        wchar_t **a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  DWORD LastError; // r12d
  wchar_t *v12; // rsi
  bool v13; // cf
  wchar_t *v14; // rbx
  wchar_t *v15; // r15
  __int64 v16; // rax
  wchar_t *v18; // r15
  wchar_t *v19; // rdi
  unsigned int v20; // r13d
  wchar_t *v21; // rbx
  unsigned int v22; // edx
  __int64 v23; // rcx
  BOOL v24; // r10d
  unsigned int v25; // r8d
  unsigned int v26; // r9d
  wchar_t *v27; // rdx
  int v29; // r8d
  unsigned int v30; // edx
  __int64 v31; // rcx
  int v32; // ecx
  BOOL v33; // edx
  wchar_t v34; // ax
  int v35; // r8d
  unsigned int v36; // r9d
  unsigned int v37; // ebx
  struct _ACL *v38; // rax
  PACL *v39; // r8
  PACL v40; // rax
  unsigned int v41; // eax
  wchar_t i; // ax
  const wchar_t *v43; // rdi
  int v44; // r8d
  __int64 v45; // rsi
  __int64 v46; // rbx
  wchar_t **v47; // rcx
  __int64 v48; // rax
  wchar_t v49; // dx
  unsigned int v50; // r13d
  BYTE v51; // r14
  wchar_t *v52; // rbx
  ACCESS_MASK v53; // r15d
  unsigned int v54; // r12d
  int v55; // esi
  __int64 v56; // rdi
  unsigned int v57; // eax
  PACL v58; // rax
  const wchar_t **v59; // r14
  GUID *v60; // r15
  __int128 *v61; // r14
  wchar_t *v62; // rbx
  unsigned int k; // edi
  wchar_t v64; // ax
  char v65; // di
  __int64 v66; // rax
  char *v67; // r9
  unsigned int v68; // edi
  __int64 v69; // rdx
  unsigned int v70; // r8d
  wchar_t **v71; // rsi
  NTSTATUS v72; // eax
  int v73; // eax
  DWORD v74; // eax
  __int64 j; // r9
  wchar_t *v76; // rsi
  wchar_t *v77; // rbx
  int v78; // ecx
  int v79; // edx
  unsigned int v80; // r8d
  wchar_t n; // ax
  unsigned int v82; // edi
  ULONG v83; // r14d
  ULONG v84; // eax
  NTSTATUS v85; // eax
  void *v86; // r15
  int v87; // ebx
  PACL v88; // rdi
  int v89; // ecx
  char AclRevision; // r14
  __int16 v91; // ax
  PACE v92; // rbx
  __int64 v93; // rdx
  ULONG v94; // eax
  wchar_t v95; // ax
  wchar_t *m; // rbx
  DWORD ConditionForString; // eax
  char *v98; // rax
  char *v99; // rdi
  ULONG v100; // eax
  unsigned __int64 v101; // rcx
  unsigned int v102; // edi
  struct _ACL *v103; // rax
  struct _ACL *v104; // r15
  unsigned int v105; // eax
  unsigned int v106; // eax
  struct _ACL *v107; // rax
  wchar_t v108; // ax
  int v109; // eax
  int v110; // ecx
  int v111; // eax
  int v112; // ecx
  char *v113; // rax
  ULONG v114; // eax
  size_t v115; // rbx
  ULONG v116; // eax
  char v117; // cl
  int Sid; // [rsp+20h] [rbp-E0h]
  BYTE v119; // [rsp+50h] [rbp-B0h]
  char v120; // [rsp+51h] [rbp-AFh]
  char *hMem; // [rsp+60h] [rbp-A0h]
  ACCESS_MASK AccessMask; // [rsp+68h] [rbp-98h]
  unsigned int v124; // [rsp+6Ch] [rbp-94h]
  int v125; // [rsp+70h] [rbp-90h]
  size_t Size; // [rsp+74h] [rbp-8Ch] BYREF
  wchar_t *v127; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL Src; // [rsp+88h] [rbp-78h]
  int v129; // [rsp+90h] [rbp-70h]
  unsigned __int16 v130; // [rsp+94h] [rbp-6Ch]
  int v131; // [rsp+98h] [rbp-68h]
  unsigned __int16 v132; // [rsp+9Ch] [rbp-64h]
  unsigned int v133; // [rsp+A0h] [rbp-60h]
  unsigned int v134; // [rsp+A4h] [rbp-5Ch]
  int v135; // [rsp+A8h] [rbp-58h]
  HLOCAL v136; // [rsp+B0h] [rbp-50h] BYREF
  PVOID v137; // [rsp+B8h] [rbp-48h] BYREF
  GUID *InheritedObjectTypeGuid; // [rsp+C0h] [rbp-40h]
  PACE Ace; // [rsp+C8h] [rbp-38h] BYREF
  char *v140; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v141; // [rsp+D8h] [rbp-28h]
  __int64 v142; // [rsp+E0h] [rbp-20h]
  __int64 v143; // [rsp+E8h] [rbp-18h]
  wchar_t *EndPtr; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v145; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t **v146; // [rsp+100h] [rbp+0h]
  __int128 v147; // [rsp+108h] [rbp+8h] BYREF
  __int128 v148; // [rsp+118h] [rbp+18h] BYREF
  wchar_t Destination[40]; // [rsp+130h] [rbp+30h] BYREF

  LastError = 0;
  v143 = a5;
  v142 = a6;
  v12 = String1;
  v141 = a7;
  hMem = 0;
  v140 = 0;
  v129 = 0;
  v146 = a4;
  EndPtr = 0;
  Src = 0;
  Size = 0;
  v136 = 0;
  v137 = 0;
  v127 = 0;
  v130 = 256;
  if ( !String1 || !a3 || !a4 )
    return 87;
  if ( !_wcsnicmp(String1, L"NO_ACCESS_CONTROL", 0x11u) )
  {
    *a3 = 0;
    *a4 = v12 + 17;
    goto LABEL_73;
  }
  v13 = a2 != 0;
  *a4 = 0;
  v14 = v12;
  v125 = 2 - v13;
  while ( 1 )
  {
    if ( !*v14 || !v14[1] )
    {
      *a4 = wcschr(v12, 0x3Au);
      goto LABEL_17;
    }
    if ( !_wcsnicmp(v14, L"XA", 2u)
      || !_wcsnicmp(v14, L"XD", 2u)
      || !_wcsnicmp(v14, L"RA", 2u)
      || !_wcsnicmp(v14, L"SP", 2u)
      || !_wcsnicmp(v14, L"XU", 2u)
      || !_wcsnicmp(v14, L"ZA", 2u)
      || !_wcsnicmp(v14, L"FL", 2u) )
    {
      v22 = 1;
      if ( v14 - 1 >= v12 )
      {
        do
        {
          if ( v14[-v22] != 32 )
            break;
          ++v22;
        }
        while ( &v14[-v22] >= v12 );
      }
      if ( v14[-v22] == 40 )
      {
        LODWORD(v23) = 2;
        if ( v14[2] == 32 )
        {
          do
            v23 = (unsigned int)(v23 + 1);
          while ( v14[v23] == 32 );
        }
        if ( v14[(unsigned int)v23] == 59 )
          break;
      }
    }
    ++v14;
  }
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = v12;
  if ( *v12 )
  {
    while ( 1 )
    {
      if ( *a4 || v26 )
      {
LABEL_45:
        if ( v24 || v25 )
          return 1336;
        if ( v26 )
          return v26;
        break;
      }
      switch ( *v27 )
      {
        case '"':
          if ( v25 <= 1 )
          {
LABEL_188:
            v26 = 1336;
            break;
          }
          v24 = !v24;
          break;
        case '(':
          if ( !v24 )
            ++v25;
          break;
        case ')':
          if ( !v24 )
          {
            if ( !v25 )
              goto LABEL_188;
            --v25;
          }
          break;
        default:
          if ( *v27 == 58 && !v25 )
            *a4 = v27;
          break;
      }
      if ( !*++v27 )
        goto LABEL_45;
    }
  }
LABEL_17:
  v15 = *a4;
  if ( *a4 == v12 )
    return 87;
  if ( v15 )
  {
    v18 = v15 - 1;
  }
  else
  {
    v16 = -1;
    while ( v12[++v16] != 0 )
      ;
    v18 = &v12[v16];
  }
  *a4 = v18;
  v19 = v12;
  v20 = 0;
  v21 = v12;
  v124 = 0;
  while ( *v21 && v21[1] )
  {
    if ( !_wcsnicmp(v21, L"XA", 2u)
      || !_wcsnicmp(v21, L"XD", 2u)
      || !_wcsnicmp(v21, L"RA", 2u)
      || !_wcsnicmp(v21, L"SP", 2u)
      || !_wcsnicmp(v21, L"XU", 2u)
      || !_wcsnicmp(v21, L"ZA", 2u)
      || !_wcsnicmp(v21, L"FL", 2u) )
    {
      v29 = 1;
      v30 = 1;
      if ( v21 - 1 >= v12 )
      {
        do
        {
          if ( v21[-v30] != 32 )
            break;
          ++v30;
        }
        while ( &v21[-v30] >= v12 );
      }
      if ( v21[-v30] == 40 )
      {
        LODWORD(v31) = 2;
        if ( v21[2] == 32 )
        {
          do
            v31 = (unsigned int)(v31 + 1);
          while ( v21[v31] == 32 );
        }
        if ( v21[(unsigned int)v31] == 59 )
        {
          v32 = 0;
          v33 = 0;
          if ( v12 >= v18 )
          {
LABEL_56:
            if ( v19 == v18 )
              goto LABEL_59;
          }
          else
          {
            while ( *v19 == 32 )
            {
              if ( ++v19 >= v18 )
                goto LABEL_56;
            }
          }
          if ( *v19 == 40 )
            v29 = 0;
          while ( 1 )
          {
LABEL_59:
            if ( v19 >= v18 )
            {
              if ( v32 )
              {
LABEL_290:
                LastError = 1336;
                goto LABEL_73;
              }
LABEL_203:
              v36 = v124;
              goto LABEL_72;
            }
            v34 = *v19;
            if ( *v19 == 32 )
              break;
            if ( v29 )
              goto LABEL_171;
            switch ( v34 )
            {
              case '(':
                if ( v33 )
                  goto LABEL_63;
                ++v32;
                ++v19;
                break;
              case ')':
                if ( v33 )
                  goto LABEL_63;
                if ( !v32 )
                  goto LABEL_290;
                if ( v32 == 1 )
                {
                  if ( v20 < 5 )
                    goto LABEL_290;
                  v20 = 0;
                  ++v124;
                }
                --v32;
                ++v19;
                break;
              case ';':
                ++v20;
                ++v19;
                break;
              default:
                goto LABEL_61;
            }
          }
LABEL_61:
          if ( v34 == 34 )
            v33 = !v33;
LABEL_63:
          ++v19;
          goto LABEL_59;
        }
      }
    }
    ++v21;
  }
  v35 = 0;
  if ( v12 < v18 )
  {
    do
    {
      if ( *v19 == 59 )
      {
        ++v20;
      }
      else if ( *v19 != 40 )
      {
        v35 = 1;
      }
      ++v19;
    }
    while ( v19 < v18 );
  }
  if ( v20 != 5 * (v20 / 5) )
  {
    LastError = 87;
    goto LABEL_203;
  }
  if ( !v20 && v35 )
  {
LABEL_171:
    LastError = 87;
    goto LABEL_73;
  }
  v36 = v20 / 5;
  v124 = v20 / 5;
LABEL_72:
  if ( LastError )
    goto LABEL_73;
  if ( !v36 )
  {
    v107 = (struct _ACL *)LocalAlloc(0x40u, 8u);
    *a3 = v107;
    if ( v107 )
    {
      v107->AclRevision = 2;
      (*a3)->Sbz1 = 0;
      (*a3)->AclSize = 8;
      (*a3)->AceCount = 0;
      (*a3)->Sbz2 = 0;
    }
    else
    {
      return 8;
    }
    return LastError;
  }
  v37 = 84 * v36 + 8;
  v133 = v37;
  if ( v37 > 0xFFFF )
  {
    v37 = 0xFFFF;
    v133 = 0xFFFF;
  }
  v38 = (struct _ACL *)LocalAlloc(0x40u, v37);
  v39 = a3;
  *a3 = v38;
  if ( !v38 )
  {
    LastError = 8;
    goto LABEL_73;
  }
  v38->AclRevision = 2;
  v40 = *a3;
  v135 = 8;
  v120 = 0;
  v40->Sbz1 = 0;
  (*a3)->AclSize = v37;
  v41 = 0;
  (*a3)->AceCount = 0;
  (*a3)->Sbz2 = 0;
  while ( 2 )
  {
    v134 = v41;
    if ( v41 >= v124 )
      goto LABEL_127;
    v147 = 0;
    v148 = 0;
    for ( i = *v12; i == 32; ++v12 )
      i = v12[1];
    v43 = v12 + 1;
    if ( i != 40 )
      v43 = v12;
    for ( ; *v43 == 32; ++v43 )
      ;
    v44 = v125;
    v45 = 0;
    while ( 1 )
    {
      v46 = 3 * v45;
      if ( (v44 & qword_180079538[3 * v45 + 1]) == v44 )
      {
        if ( !v43 )
        {
          if ( !HIDWORD(qword_180079538[v46]) )
            break;
          goto LABEL_114;
        }
        v73 = _wcsnicmp(v43, (&off_180079530)[v46], LODWORD(qword_180079538[v46]));
        v44 = v125;
        if ( !v73 )
          break;
      }
LABEL_114:
      v45 = (unsigned int)(v45 + 1);
      if ( (unsigned int)v45 >= 0x11 )
        goto LABEL_115;
    }
    v47 = &(&off_180079530)[v46];
    if ( !&(&off_180079530)[v46] )
    {
LABEL_115:
      LastError = 1804;
      v58 = *a3;
      goto LABEL_116;
    }
    v48 = *((unsigned int *)v47 + 2);
    v49 = v43[v48];
    if ( v49 != 32 && v49 != 59 )
    {
LABEL_109:
      LastError = 1336;
LABEL_110:
      v58 = *a3;
      goto LABEL_116;
    }
    v50 = *((unsigned __int8 *)v47 + 12);
    v51 = 0;
    v52 = (wchar_t *)&v43[v48 + 1];
    v119 = 0;
    if ( (unsigned __int8)(v50 - 5) <= 3u || (_BYTE)v50 == 11 )
      (*a3)->AclRevision = 4;
    for ( ; *v52 == 32; ++v52 )
      ;
LABEL_98:
    if ( v52 != *v146 )
    {
      if ( *v52 == 59 )
      {
        ++v52;
        goto LABEL_99;
      }
      for ( ; *v52 == 32; ++v52 )
        ;
      v68 = 0;
      while ( 1 )
      {
        v69 = 4LL * v68;
        if ( (v44 & qword_180079178[v69 + 1]) == v44 )
        {
          v70 = HIDWORD(qword_180079178[v69 + 1]);
          if ( v70 )
          {
            for ( j = 0; (unsigned int)j < v70; j = (unsigned int)(j + 1) )
            {
              if ( *(_BYTE *)(j + qword_180079178[v69 + 2]) == (_BYTE)v50 )
                goto LABEL_149;
            }
          }
          else
          {
LABEL_149:
            v71 = &(&off_180079170)[v69];
            if ( !_wcsnicmp(v52, (&off_180079170)[v69], LODWORD(qword_180079178[v69])) )
            {
              if ( !v71 )
              {
LABEL_154:
                LastError = 1004;
                v58 = *a3;
                goto LABEL_116;
              }
              v51 |= *((_BYTE *)v71 + 12);
              v44 = v125;
              v119 = v51;
              v52 += *((unsigned int *)v71 + 2);
              goto LABEL_98;
            }
          }
          v44 = v125;
        }
        if ( ++v68 >= 9 )
          goto LABEL_154;
      }
    }
LABEL_99:
    v53 = 0;
    for ( AccessMask = 0; *v52 == 32; ++v52 )
      ;
    v54 = v124;
    while ( *v52 != 59 )
    {
      for ( ; *v52 == 32; ++v52 )
        ;
      v55 = v44;
      if ( (_BYTE)v50 == 17 )
        v55 = 4;
      v56 = 0;
      while ( 1 )
      {
        if ( (v55 & dword_1800792A0[6 * v56]) == v55 )
        {
          v59 = (const wchar_t **)(&_ImageBase + 6 * v56 + 124068);
          if ( !_wcsnicmp(v52, *v59, (unsigned int)dword_180079298[6 * v56]) )
            break;
        }
        v56 = (unsigned int)(v56 + 1);
        if ( (unsigned int)v56 >= 0x1C )
          goto LABEL_108;
      }
      v124 = v54;
      if ( v59 )
      {
        v53 |= *(_DWORD *)&word_18000000C[12 * v56 + 248136];
        v44 = v125;
        AccessMask = v53;
        v52 += *(unsigned int *)&word_180000008[12 * v56 + 248136];
      }
      else
      {
LABEL_108:
        v57 = wcstoul(v52, &EndPtr, 0);
        if ( EndPtr == v52 )
          goto LABEL_109;
        v44 = v125;
        v53 |= v57;
        v52 = EndPtr;
        AccessMask = v53;
      }
    }
    v60 = 0;
    v61 = 0;
    v62 = v52 + 1;
    Ace = 0;
    InheritedObjectTypeGuid = 0;
    for ( k = 0; ; ++k )
    {
      v64 = *v62;
      if ( k >= 2 )
        break;
      for ( ; v64 == 32; ++v62 )
        v64 = v62[1];
      if ( v64 != 59 )
      {
        if ( (unsigned __int8)(v50 - 5) > 3u && (_BYTE)v50 != 11 )
        {
          LastError = 1336;
          v58 = *a3;
          goto LABEL_116;
        }
        wcsncpy_s(Destination, 0x25u, v62, 0x24u);
        Destination[36] = 0;
        if ( k )
        {
          if ( !(unsigned int)SddlpUuidFromString(Destination, &v148) )
            goto LABEL_315;
          v61 = &v148;
          InheritedObjectTypeGuid = (GUID *)&v148;
        }
        else
        {
          if ( !(unsigned int)SddlpUuidFromString(Destination, &v147) )
            goto LABEL_315;
          v60 = (GUID *)&v147;
          Ace = (PACE)&v147;
        }
        v108 = v62[36];
        v62 += 36;
        if ( v108 != 59 && v108 != 32 )
        {
LABEL_315:
          LastError = 1705;
          v58 = *a3;
          goto LABEL_116;
        }
      }
      ++v62;
    }
    for ( ; v64 == 32; ++v62 )
      v64 = v62[1];
    v65 = 0;
    v145 = 0;
    v120 = 0;
    if ( !v64 || !v62[1] )
    {
      LastError = 1332;
      v58 = *a3;
      goto LABEL_116;
    }
    v127 = v62 + 2;
    LastError = 0;
    v66 = LookupSidInTable(v62, 0, v141, a8, (__int64)&v145);
    if ( v66 )
    {
      v67 = *(char **)(v66 + 16);
      goto LABEL_124;
    }
    v67 = (char *)v145;
    hMem = (char *)v145;
    if ( v145 )
    {
      v65 = 1;
      v120 = 1;
      goto LABEL_125;
    }
    v127 -= 2;
    v72 = LocalpConvertStringSidToSid(v62, &v140, &v127);
    if ( v72 < 0 )
    {
      v74 = RtlNtStatusToDosError(v72);
      SetLastError(v74);
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_157;
      v67 = v140;
LABEL_124:
      hMem = v67;
    }
    else
    {
      SetLastError(0);
LABEL_157:
      v67 = v140;
      hMem = v140;
      if ( v140 )
      {
        v65 = 1;
        v120 = 1;
      }
    }
LABEL_125:
    if ( !LastError )
    {
      v76 = v127;
      if ( !v127 || !v67 )
        goto LABEL_109;
      v77 = v127;
      v120 = v65;
      if ( *v127 == 32 )
      {
        do
          ++v77;
        while ( *v77 == 32 );
      }
      else
      {
        v120 = v65;
      }
      if ( (unsigned __int8)v50 <= 0x15u && (v78 = 2371072, _bittest(&v78, v50)) )
      {
        if ( *v77 == 59 )
        {
          v95 = v77[1];
          for ( m = v77 + 1; v95 == 32; ++m )
            v95 = m[1];
          if ( v95 == 40 )
          {
            if ( Src )
            {
              LocalFree(Src);
              Src = 0;
            }
            LODWORD(Size) = 0;
            if ( v136 )
            {
              LocalFree(v136);
              v136 = 0;
            }
            HIDWORD(Size) = 0;
            if ( (_BYTE)v50 == 18 )
            {
              LastError = LocalGetRelativeAttributeForString(
                            (_DWORD)m,
                            (unsigned int)&v127,
                            (unsigned int)&v136,
                            (unsigned int)&Size + 4,
                            v143,
                            v142,
                            v141,
                            a8);
              if ( LastError )
                goto LABEL_110;
              v76 = v127;
              v67 = hMem;
            }
            else
            {
              ConditionForString = LocalGetConditionForString(m, v143, v142, v141, a8, 0);
              v67 = hMem;
              LastError = ConditionForString;
              v76 = v127;
            }
          }
          else
          {
            v76 = m;
            v127 = m;
          }
        }
        v79 = Size;
        v80 = HIDWORD(Size);
        if ( !HIDWORD(Size) )
          goto LABEL_109;
        if ( LastError )
        {
          v58 = *a3;
          goto LABEL_116;
        }
      }
      else
      {
        v79 = Size;
        v80 = HIDWORD(Size);
      }
      for ( n = *v76; *v76 == 32; n = *v76 )
        v127 = ++v76;
      if ( n != 41 )
        goto LABEL_109;
      if ( v50 != 3 )
      {
        switch ( v50 )
        {
          case 0u:
          case 1u:
          case 2u:
          case 0x11u:
          case 0x13u:
          case 0x14u:
            break;
          case 5u:
          case 6u:
          case 7u:
          case 8u:
            v111 = 32;
            if ( !v60 )
              v111 = 16;
            v82 = v111 + 16;
            if ( !v61 )
              v82 = v111;
            goto LABEL_215;
          case 9u:
          case 0xAu:
          case 0xDu:
          case 0x15u:
            v105 = (v79 + 3) & 0xFFFFFFFC;
            v82 = v105 + 12;
            if ( v105 + 12 >= v105 )
              goto LABEL_215;
            goto LABEL_217;
          case 0xBu:
            v109 = 32;
            if ( !v60 )
              v109 = 16;
            v110 = v109 + 16;
            if ( !v61 )
              v110 = v109;
            v106 = (v79 + 3) & 0xFFFFFFFC;
            v82 = v106 + v110;
            if ( v106 + v110 >= v106 )
              goto LABEL_215;
            goto LABEL_217;
          case 0x12u:
            v82 = v80 + 12;
            if ( v80 + 12 >= v80 )
              goto LABEL_215;
            goto LABEL_217;
          default:
            goto LABEL_109;
        }
      }
      v82 = 12;
LABEL_215:
      v12 = v76 + 1;
      v83 = RtlLengthSid(v67) + v82 - 4;
      if ( v83 < v82 || (v84 = v83 + v135, v135 = v84, v84 < v83) )
      {
LABEL_217:
        LastError = 534;
        v58 = *a3;
        goto LABEL_116;
      }
      if ( v84 <= v133 )
      {
LABEL_219:
        SetLastError(0);
        if ( v50 == 2 )
        {
          v85 = RtlAddAuditAccessAceEx(*a3, 2u, v119 & 0x3F, AccessMask, hMem, v119 & 0x40, v119 & 0x80);
        }
        else
        {
          if ( (_BYTE)v50 )
          {
            if ( v50 == 17 )
            {
              v86 = hMem;
              Ace = 0;
              v131 = 0;
              v88 = *a3;
              v132 = 4096;
              if ( v88 )
              {
                if ( RtlValidSid(hMem) )
                {
                  v89 = *(_DWORD *)(hMem + 2) - v131;
                  if ( !v89 )
                    v89 = *((unsigned __int16 *)hMem + 3) - v132;
                  if ( v89 )
                  {
                    v87 = -1073741811;
                  }
                  else if ( v88->AclRevision > 4u )
                  {
                    v87 = -1073741735;
                  }
                  else
                  {
                    AclRevision = 2;
                    if ( v88->AclRevision > 2u )
                      AclRevision = v88->AclRevision;
                    if ( (v119 & 0xE0) != 0 )
                    {
                      v87 = -1073741811;
                    }
                    else if ( (AccessMask & 0xFFFFFFF8) != 0 )
                    {
                      v86 = hMem;
                      v87 = -1073741811;
                    }
                    else if ( RtlValidAcl(v88) )
                    {
                      if ( RtlFirstFreeAce(v88, &Ace) )
                      {
                        v91 = RtlLengthSid(hMem);
                        v92 = Ace;
                        if ( Ace && (v93 = (unsigned __int16)(v91 + 8), (char *)Ace + v93 <= (char *)v88 + v88->AclSize) )
                        {
                          Ace->AccessMask = AccessMask;
                          v86 = hMem;
                          v92->Header.AceFlags = v119;
                          v92->Header.AceType = 17;
                          v92->Header.AceSize = v93;
                          v94 = RtlLengthSid(hMem);
                          RtlCopySid(v94, &v92[1], hMem);
                          ++v88->AceCount;
                          v87 = 0;
                          v88->AclRevision = AclRevision;
                        }
                        else
                        {
                          v86 = hMem;
                          v87 = -1073741671;
                        }
                      }
                      else
                      {
                        v86 = hMem;
                        v87 = -1073741705;
                      }
                    }
                    else
                    {
                      v86 = hMem;
                      v87 = -1073741705;
                    }
                  }
                }
                else
                {
                  v87 = -1073741704;
                }
              }
              else
              {
                v87 = -1073741705;
              }
            }
            else
            {
              switch ( v50 )
              {
                case 1u:
                  v85 = RtlAddAccessDeniedAceEx(*a3, 2u, v119, AccessMask, hMem);
                  goto LABEL_221;
                case 5u:
                  v85 = RtlAddAccessAllowedObjectAce(*a3, 4u, v119, AccessMask, v60, InheritedObjectTypeGuid, hMem);
                  goto LABEL_221;
                case 6u:
                  v85 = RtlAddAccessDeniedObjectAce(*a3, 4u, v119, AccessMask, v60, InheritedObjectTypeGuid, hMem);
                  goto LABEL_221;
                case 7u:
                  v85 = RtlAddAuditAccessObjectAce(
                          *a3,
                          4u,
                          v119,
                          AccessMask,
                          v60,
                          InheritedObjectTypeGuid,
                          hMem,
                          v119 & 0x40,
                          v119 & 0x80);
                  goto LABEL_221;
                case 9u:
                case 0xAu:
                case 0xDu:
                  if ( v83 >= 0xFFFF )
                    goto LABEL_372;
                  v98 = (char *)LocalAlloc(0x40u, v83);
                  v99 = v98;
                  if ( !v98 )
                    goto LABEL_276;
                  *((_DWORD *)v98 + 1) = AccessMask;
                  v86 = hMem;
                  *v98 = v50;
                  v98[1] = v119;
                  *((_WORD *)v98 + 1) = v83;
                  v100 = RtlLengthSid(hMem);
                  RtlCopySid(v100, v99 + 8, hMem);
                  goto LABEL_270;
                case 0xBu:
                  if ( v83 >= 0xFFFF )
                    goto LABEL_372;
                  v87 = RtlAddAccessAllowedObjectAce(*a3, 4u, v119, AccessMask, v60, InheritedObjectTypeGuid, hMem);
                  if ( v87 < 0 )
                    goto LABEL_277;
                  v87 = RtlGetAce(*a3, (*a3)->AceCount - 1, &v137);
                  if ( v87 < 0 )
                    goto LABEL_277;
                  v117 = 9;
                  v86 = hMem;
                  if ( *(_BYTE *)v137 == 5 )
                    v117 = 11;
                  *(_BYTE *)v137 = v117;
                  *((_WORD *)v137 + 1) = v83;
                  goto LABEL_224;
                case 0x12u:
                  if ( v83 >= 0xFFFF || (v119 & 0xE0) != 0 || AccessMask )
                    goto LABEL_372;
                  v86 = hMem;
                  v112 = *(_DWORD *)(hMem + 2) - v129;
                  if ( !v112 )
                    v112 = *((unsigned __int16 *)hMem + 3) - v130;
                  if ( v112 || hMem[1] != 1 || *((_DWORD *)hMem + 2) )
                  {
LABEL_372:
                    v87 = -1073741705;
                    goto LABEL_277;
                  }
                  v113 = (char *)LocalAlloc(0x40u, v83);
                  v99 = v113;
                  if ( !v113 )
                  {
LABEL_276:
                    v87 = -1073741801;
                    goto LABEL_277;
                  }
                  *v113 = v50;
                  v113[1] = v119;
                  *((_WORD *)v113 + 1) = v83;
                  *((_DWORD *)v113 + 1) = 0;
                  v114 = RtlLengthSid(hMem);
                  RtlCopySid(v114, v99 + 8, hMem);
                  if ( HIDWORD(Size) )
                  {
                    v115 = HIDWORD(Size);
                    v116 = RtlLengthSid(hMem);
                    memcpy_0(&v99[v116 + 8], v136, v115);
                  }
LABEL_270:
                  v87 = RtlAddAce(*a3, 2u, 0xFFFFFFFF, v99, v83);
                  LocalFree(v99);
                  break;
                case 0x13u:
                  v85 = SddlAddScopedPolicyIDAce(*a3, hMem);
                  goto LABEL_221;
                case 0x14u:
                  v86 = hMem;
                  v85 = SddlAddProcessTrustLabelAce(*a3, Sid, AccessMask);
                  goto LABEL_222;
                case 0x15u:
                  v86 = hMem;
                  v85 = SddlAddAccessFilterAce(*a3, Sid, AccessMask, Src, Size);
                  goto LABEL_222;
                default:
                  v87 = -1073741811;
                  goto LABEL_277;
              }
            }
LABEL_223:
            if ( v87 >= 0 )
            {
LABEL_224:
              if ( v120 == 1 )
                LocalFree(v86);
              hMem = 0;
              v140 = 0;
              if ( Src )
              {
                LocalFree(Src);
                Src = 0;
              }
              LODWORD(Size) = 0;
              if ( v136 )
              {
                LocalFree(v136);
                v136 = 0;
              }
              HIDWORD(Size) = 0;
              if ( *v12 == 40 )
                ++v12;
              v39 = a3;
              v41 = v134 + 1;
              continue;
            }
LABEL_277:
            LastError = RtlNtStatusToDosError(v87);
            break;
          }
          v85 = RtlAddAccessAllowedAceEx(*a3, 2u, v119, AccessMask, hMem);
        }
LABEL_221:
        v86 = hMem;
LABEL_222:
        v87 = v85;
        goto LABEL_223;
      }
      v101 = v83 * (unsigned __int64)(v124 - v134);
      if ( v101 > 0xFFFFFFFF )
        goto LABEL_217;
      v102 = v101 + v133;
      if ( (unsigned int)v101 + v133 < (unsigned int)v101 )
        goto LABEL_217;
      v103 = (struct _ACL *)LocalAlloc(0x40u, v102);
      v104 = v103;
      if ( v103 )
      {
        memcpy_0(v103, *a3, v133);
        v104->AclSize = v102;
        LocalFree(*a3);
        v133 = v102;
        *a3 = v104;
        v60 = (GUID *)Ace;
        goto LABEL_219;
      }
      LocalFree(*a3);
      *a3 = 0;
      if ( v120 == 1 )
      {
        LocalFree(hMem);
        hMem = 0;
        v120 = 0;
      }
      v58 = *a3;
      LastError = 8;
LABEL_116:
      LocalFree(v58);
      *a3 = 0;
      goto LABEL_129;
    }
    break;
  }
  v39 = a3;
LABEL_127:
  v58 = *v39;
  if ( LastError )
    goto LABEL_116;
  v58->AclSize = v135;
LABEL_129:
  if ( v120 && hMem )
    LocalFree(hMem);
LABEL_73:
  if ( Src )
    LocalFree(Src);
  if ( !v136 )
    return LastError;
  LocalFree(v136);
  return LastError;
}

```

## disassembly

```asm
0x180006680  mov     [rsp-8+arg_8], rbx
0x180006685  push    rbp
0x180006686  push    rsi
0x180006687  push    rdi
0x180006688  push    r12
0x18000668a  push    r13
0x18000668c  push    r14
0x18000668e  push    r15
0x180006690  lea     rbp, [rsp-90h]
0x180006698  sub     rsp, 190h
0x18000669f  mov     rax, cs:__security_cookie
0x1800066a6  xor     rax, rsp
0x1800066a9  mov     [rbp+0C0h+var_40], rax
0x1800066b0  mov     rax, [rbp+0C0h+arg_20]
0x1800066b7  xor     r12d, r12d
0x1800066ba  mov     [rbp+0C0h+var_D8], rax
0x1800066be  mov     r13, r9
0x1800066c1  mov     rax, [rbp+0C0h+arg_28]
0x1800066c8  mov     rdi, r8
0x1800066cb  mov     [rbp+0C0h+var_E0], rax
0x1800066cf  movzx   ebx, dl
0x1800066d2  mov     rax, [rbp+0C0h+arg_30]
0x1800066d9  mov     rsi, rcx
0x1800066dc  mov     [rbp+0C0h+var_E8], rax
0x1800066e0  mov     eax, r12d
0x1800066e3  mov     [rsp+1C0h+hMem], rax
0x1800066e8  mov     [rbp+0C0h+var_F0], rax
0x1800066ec  mov     [rbp+0C0h+var_130], eax
0x1800066ef  mov     [rbp+0C0h+var_C0], r9
0x1800066f3  mov     [rsp+1C0h+var_168], r8
0x1800066f8  mov     [rbp+0C0h+EndPtr], r12
0x1800066fc  mov     [rbp+0C0h+Src], r12
0x180006700  mov     dword ptr [rsp+1C0h+Size], r12d
0x180006705  mov     [rbp+0C0h+var_110], r12
0x180006709  mov     dword ptr [rsp+1C0h+Size+4], r12d
0x18000670e  mov     [rbp+0C0h+var_108], r12
0x180006712  mov     [rbp+0C0h+var_140], r12
0x180006716  mov     [rbp+0C0h+var_12C], 100h
0x18000671c  test    rcx, rcx
0x18000671f  jz      loc_180007F0C
0x180006725  test    r8, r8
0x180006728  jz      loc_180007F0C
0x18000672e  test    r9, r9
0x180006731  jz      loc_180007F0C
0x180006737  mov     r8d, 11h; MaxCount
0x18000673d  lea     rdx, aNoAccessContro; "NO_ACCESS_CONTROL"
0x180006744  call    cs:__imp__wcsnicmp
0x18000674a  test    eax, eax
0x18000674c  jz      loc_18000780E
0x180006752  neg     bl
0x180006754  mov     [r13+0], r12
0x180006758  mov     rbx, rsi
0x18000675b  mov     r14d, 1
0x180006761  sbb     eax, eax
0x180006763  add     eax, 2
0x180006766  mov     [rsp+1C0h+var_150], eax
0x18000676a  nop     word ptr [rax+rax+00h]
0x180006770  cmp     [rbx], r12w
0x180006774  jz      loc_180006860
0x18000677a  cmp     [rbx+2], r12w
0x18000677f  jz      loc_180006860
0x180006785  mov     r8d, 2; MaxCount
0x18000678b  lea     rdx, aXa; "XA"
0x180006792  mov     rcx, rbx; String1
0x180006795  call    cs:__imp__wcsnicmp
0x18000679b  test    eax, eax
0x18000679d  jz      loc_1800069A5
0x1800067a3  mov     r8d, 2; MaxCount
0x1800067a9  lea     rdx, aXd; "XD"
0x1800067b0  mov     rcx, rbx; String1
0x1800067b3  call    cs:__imp__wcsnicmp
0x1800067b9  test    eax, eax
0x1800067bb  jz      loc_1800069A5
0x1800067c1  mov     r8d, 2; MaxCount
0x1800067c7  lea     rdx, aRa; "RA"
0x1800067ce  mov     rcx, rbx; String1
0x1800067d1  call    cs:__imp__wcsnicmp
0x1800067d7  test    eax, eax
0x1800067d9  jz      loc_1800069A5
0x1800067df  mov     r8d, 2; MaxCount
0x1800067e5  lea     rdx, aSp; "SP"
0x1800067ec  mov     rcx, rbx; String1
0x1800067ef  call    cs:__imp__wcsnicmp
0x1800067f5  test    eax, eax
0x1800067f7  jz      loc_1800069A5
0x1800067fd  mov     r8d, 2; MaxCount
0x180006803  lea     rdx, aXu; "XU"
0x18000680a  mov     rcx, rbx; String1
0x18000680d  call    cs:__imp__wcsnicmp
0x180006813  test    eax, eax
0x180006815  jz      loc_1800069A5
0x18000681b  mov     r8d, 2; MaxCount
0x180006821  lea     rdx, aZa; "ZA"
0x180006828  mov     rcx, rbx; String1
0x18000682b  call    cs:__imp__wcsnicmp
0x180006831  test    eax, eax
0x180006833  jz      loc_1800069A5
0x180006839  mov     r8d, 2; MaxCount
0x18000683f  lea     rdx, aFl; "FL"
0x180006846  mov     rcx, rbx; String1
0x180006849  call    cs:__imp__wcsnicmp
0x18000684f  test    eax, eax
0x180006851  jz      loc_1800069A5
0x180006857  add     rbx, 2
0x18000685b  jmp     loc_180006770
0x180006860  mov     edx, 3Ah ; ':'; Ch
0x180006865  mov     rcx, rsi; Str
0x180006868  call    cs:__imp_wcschr
0x18000686e  mov     [r13+0], rax
0x180006872  mov     r15, [r13+0]
0x180006876  cmp     r15, rsi
0x180006879  jz      loc_180007F0C
0x18000687f  test    r15, r15
0x180006882  jnz     loc_18000710E
0x180006888  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000688f  nop
0x180006890  cmp     [rsi+rax*2+2], r12w
0x180006896  lea     rax, [rax+1]
0x18000689a  jnz     short loc_180006890
0x18000689c  lea     r15, [rsi+rax*2]
0x1800068a0  mov     [r13+0], r15
0x1800068a4  mov     rdi, rsi
0x1800068a7  xor     r13d, r13d
0x1800068aa  mov     rbx, rsi
0x1800068ad  xor     r9d, r9d
0x1800068b0  mov     [rsp+1C0h+var_154], r9d
0x1800068b5  cmp     [rbx], r12w
0x1800068b9  jz      loc_180006AF9
0x1800068bf  cmp     [rbx+2], r12w
0x1800068c4  jz      loc_180006AF9
0x1800068ca  mov     r8d, 2; MaxCount
0x1800068d0  lea     rdx, aXa; "XA"
0x1800068d7  mov     rcx, rbx; String1
0x1800068da  call    cs:__imp__wcsnicmp
0x1800068e0  test    eax, eax
0x1800068e2  jz      loc_180006A62
0x1800068e8  mov     r8d, 2; MaxCount
0x1800068ee  lea     rdx, aXd; "XD"
0x1800068f5  mov     rcx, rbx; String1
0x1800068f8  call    cs:__imp__wcsnicmp
0x1800068fe  test    eax, eax
0x180006900  jz      loc_180006A62
0x180006906  mov     r8d, 2; MaxCount
0x18000690c  lea     rdx, aRa; "RA"
0x180006913  mov     rcx, rbx; String1
0x180006916  call    cs:__imp__wcsnicmp
0x18000691c  test    eax, eax
0x18000691e  jz      loc_180006A62
0x180006924  mov     r8d, 2; MaxCount
0x18000692a  lea     rdx, aSp; "SP"
0x180006931  mov     rcx, rbx; String1
0x180006934  call    cs:__imp__wcsnicmp
0x18000693a  test    eax, eax
0x18000693c  jz      loc_180006A62
0x180006942  mov     r8d, 2; MaxCount
0x180006948  lea     rdx, aXu; "XU"
0x18000694f  mov     rcx, rbx; String1
0x180006952  call    cs:__imp__wcsnicmp
0x180006958  test    eax, eax
0x18000695a  jz      loc_180006A62
0x180006960  mov     r8d, 2; MaxCount
0x180006966  lea     rdx, aZa; "ZA"
0x18000696d  mov     rcx, rbx; String1
0x180006970  call    cs:__imp__wcsnicmp
0x180006976  test    eax, eax
0x180006978  jz      loc_180006A62
0x18000697e  mov     r8d, 2; MaxCount
0x180006984  lea     rdx, aFl; "FL"
0x18000698b  mov     rcx, rbx; String1
0x18000698e  call    cs:__imp__wcsnicmp
0x180006994  test    eax, eax
0x180006996  jz      loc_180006A62
0x18000699c  add     rbx, 2
0x1800069a0  jmp     loc_1800068B5
0x1800069a5  lea     rax, [rbx-2]
0x1800069a9  mov     edx, r14d
0x1800069ac  cmp     rax, rsi
0x1800069af  jnb     loc_180006F40
0x1800069b5  mov     ecx, edx
0x1800069b7  mov     rax, rbx
0x1800069ba  add     rcx, rcx
0x1800069bd  sub     rax, rcx
0x1800069c0  cmp     word ptr [rax], 28h ; '('
0x1800069c4  jnz     loc_180006857
0x1800069ca  cmp     word ptr [rbx+4], 20h ; ' '
0x1800069cf  mov     ecx, 2
0x1800069d4  jz      loc_18000781E
0x1800069da  mov     eax, ecx
0x1800069dc  cmp     word ptr [rbx+rax*2], 3Bh ; ';'
0x1800069e1  jnz     loc_180006857
0x1800069e7  mov     r10d, r12d
0x1800069ea  mov     r8d, r12d
0x1800069ed  mov     r9d, r12d
0x1800069f0  mov     rdx, rsi
0x1800069f3  cmp     [rsi], r12w
0x1800069f7  jz      loc_180006872
0x1800069fd  mov     r11d, 0FFFFFFFFh
0x180006a03  cmp     [r13+0], r12
0x180006a07  jnz     short loc_180006A3F
0x180006a09  test    r9d, r9d
0x180006a0c  jnz     short loc_180006A3F
0x180006a0e  movzx   ecx, word ptr [rdx]
0x180006a11  sub     ecx, 22h ; '"'
0x180006a14  jz      loc_1800071D9
0x180006a1a  sub     ecx, 6
0x180006a1d  jz      loc_1800071B6
0x180006a23  sub     ecx, r14d
0x180006a26  jz      loc_1800071A0
0x180006a2c  cmp     ecx, 11h
0x180006a2f  jz      loc_1800071C7
0x180006a35  add     rdx, 2
0x180006a39  cmp     [rdx], r12w
0x180006a3d  jnz     short loc_180006A03
0x180006a3f  test    r10d, r10d
0x180006a42  jnz     loc_18000782C
0x180006a48  test    r8d, r8d
0x180006a4b  jnz     loc_18000782C
0x180006a51  test    r9d, r9d
0x180006a54  jz      loc_180006872
0x180006a5a  mov     eax, r9d
0x180006a5d  jmp     loc_180006B69
0x180006a62  lea     rax, [rbx-2]
0x180006a66  mov     r8d, r14d
0x180006a69  mov     edx, r14d
0x180006a6c  cmp     rax, rsi
0x180006a6f  jnb     loc_180006F70
0x180006a75  mov     ecx, edx
0x180006a77  mov     rax, rbx
0x180006a7a  add     rcx, rcx
0x180006a7d  sub     rax, rcx
0x180006a80  cmp     word ptr [rax], 28h ; '('
0x180006a84  jnz     loc_18000699C
0x180006a8a  cmp     word ptr [rbx+4], 20h ; ' '
0x180006a8f  mov     ecx, 2
0x180006a94  jz      loc_180007837
0x180006a9a  mov     eax, ecx
0x180006a9c  cmp     word ptr [rbx+rax*2], 3Bh ; ';'
0x180006aa1  jnz     loc_18000699C
0x180006aa7  xor     ecx, ecx
0x180006aa9  xor     edx, edx
0x180006aab  cmp     rsi, r15
0x180006aae  jnb     short loc_180006ABF
0x180006ab0  cmp     word ptr [rdi], 20h ; ' '
0x180006ab4  jnz     short loc_180006AC4
0x180006ab6  add     rdi, 2
0x180006aba  cmp     rdi, r15
0x180006abd  jb      short loc_180006AB0
0x180006abf  cmp     rdi, r15
0x180006ac2  jz      short loc_180006ACD
0x180006ac4  cmp     word ptr [rdi], 28h ; '('
0x180006ac8  jnz     short loc_180006ACD
0x180006aca  xor     r8d, r8d
0x180006acd  mov     r9d, 0FFFFFFFFh
0x180006ad3  cmp     rdi, r15
0x180006ad6  jnb     loc_18000726A
0x180006adc  movzx   eax, word ptr [rdi]
0x180006adf  cmp     ax, 20h ; ' '
0x180006ae3  jnz     loc_1800071FA
0x180006ae9  cmp     ax, 22h ; '"'
0x180006aed  jz      loc_180007845
0x180006af3  add     rdi, 2
0x180006af7  jmp     short loc_180006AD3
0x180006af9  xor     r8d, r8d
0x180006afc  cmp     rsi, r15
0x180006aff  jnb     short loc_180006B20
0x180006b01  movzx   eax, word ptr [rdi]
0x180006b04  cmp     ax, 3Bh ; ';'
0x180006b08  jz      loc_180006B93
0x180006b0e  cmp     ax, 28h ; '('
0x180006b12  jz      short loc_180006B17
0x180006b14  mov     r8d, r14d
0x180006b17  add     rdi, 2
0x180006b1b  cmp     rdi, r15
0x180006b1e  jb      short loc_180006B01
0x180006b20  mov     eax, 0CCCCCCCDh
0x180006b25  mul     r13d
0x180006b28  shr     edx, 2
0x180006b2b  lea     ecx, [rdx+rdx*4]
0x180006b2e  cmp     r13d, ecx
0x180006b31  jnz     loc_18000785E
0x180006b37  test    r13d, r13d
0x180006b3a  jz      loc_180007141
0x180006b40  mov     r9d, edx
0x180006b43  mov     [rsp+1C0h+var_154], edx
0x180006b47  test    r12d, r12d
0x180006b4a  jz      short loc_180006B9B
0x180006b4c  mov     rcx, [rbp+0C0h+Src]; hMem
0x180006b50  test    rcx, rcx
0x180006b53  jnz     loc_180007EF3
0x180006b59  mov     rcx, [rbp+0C0h+var_110]; hMem
0x180006b5d  test    rcx, rcx
0x180006b60  jnz     loc_180007EFE
0x180006b66  mov     eax, r12d
0x180006b69  mov     rcx, [rbp+0C0h+var_40]
0x180006b70  xor     rcx, rsp; StackCookie
0x180006b73  call    __security_check_cookie
0x180006b78  mov     rbx, [rsp+1C0h+arg_8]
0x180006b80  add     rsp, 190h
0x180006b87  pop     r15
0x180006b89  pop     r14
  ... truncated ...
```
