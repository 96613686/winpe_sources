# LocalConvertSDToStringSD_Rev1

- ea: `0x180004260`
- end: `0x180004f0b`
- name: `LocalConvertSDToStringSD_Rev1`
- size: `3243`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002ed0`
- `0x1800216b0`

## callees

- `0x180003190`
- `0x180004260`
- `0x180004f20`
- `0x180005730`
- `0x180005aa0`
- `0x18001c5e0`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcsncpy_s` at `0x1800047dd`
- `api-ms-win-core-crt-l1-1-0!wcsncpy_s` at `0x180004831`
- `api-ms-win-core-crt-l1-1-0!wcsncpy_s` at `0x1800047dd`
- `api-ms-win-core-crt-l1-1-0!wcsncpy_s` at `0x180004831`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x18000493c`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x18000498b`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x1800049ef`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x180004aa4`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x180004b26`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x180004d4f`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x18000493c`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x18000498b`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x1800049ef`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x180004aa4`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x180004b26`
- `api-ms-win-core-crt-l1-1-0!swprintf_s` at `0x180004d4f`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x18000451a`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004682`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004a2c`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004adc`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004e70`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004ebe`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x18000451a`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004682`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004a2c`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004adc`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004e70`
- `api-ms-win-core-crt-l1-1-0!wcscpy_s` at `0x180004ebe`
- `ntdll!RtlNtStatusToDosError` at `0x18000432c`
- `ntdll!RtlNtStatusToDosError` at `0x180004782`
- `ntdll!RtlNtStatusToDosError` at `0x180004c98`
- `ntdll!RtlNtStatusToDosError` at `0x180004d5c`
- `ntdll!RtlNtStatusToDosError` at `0x18000432c`
- `ntdll!RtlNtStatusToDosError` at `0x180004782`
- `ntdll!RtlNtStatusToDosError` at `0x180004c98`
- `ntdll!RtlNtStatusToDosError` at `0x180004d5c`
- `ntdll!RtlValidSid` at `0x180004d74`
- `ntdll!RtlValidSid` at `0x180004d74`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180004441`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180004441`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1800043d0`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1800043d0`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800046f9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180004c08`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800046f9`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180004c08`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18000431e`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18000431e`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180004385`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180004385`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800043a7`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800043a7`
- `ntdll!RtlFreeUnicodeString` at `0x180004d09`
- `ntdll!RtlFreeUnicodeString` at `0x180004d28`
- `ntdll!RtlFreeUnicodeString` at `0x180004db3`
- `ntdll!RtlFreeUnicodeString` at `0x180004e03`
- `ntdll!RtlFreeUnicodeString` at `0x180004d09`
- `ntdll!RtlFreeUnicodeString` at `0x180004d28`
- `ntdll!RtlFreeUnicodeString` at `0x180004db3`
- `ntdll!RtlFreeUnicodeString` at `0x180004e03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000478a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ca0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000478a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004ca0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004790`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ca6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ef6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ef6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004406`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800044f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000465a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004712`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004ea5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004406`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800044f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000465a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004712`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004c26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004ea5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004550`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000455a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004564`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000456f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000457a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000458c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d85`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004547`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004550`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000455a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004564`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000456f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000457a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000458c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004d85`

## pseudocode

```c
ULONG __fastcall LocalConvertSDToStringSD_Rev1(
        _BYTE *Sid,
        __int64 a2,
        __int64 a3,
        void *a4,
        __int16 a5,
        wchar_t **a6,
        unsigned int *a7)
{
  _WORD *v7; // r12
  struct _ACL *v10; // r14
  int OwnerSecurityDescriptor; // edi
  ULONG v12; // ebx
  int SaclSecurityDescriptor; // eax
  struct _ACL *v15; // rax
  _BYTE *v16; // rsi
  _WORD *v17; // r15
  __int64 v18; // r13
  PSID v19; // rbx
  __int64 *v20; // rax
  __int64 *v21; // rsi
  unsigned int v22; // r14d
  __int64 v23; // rax
  SIZE_T v24; // rbx
  wchar_t *v25; // rax
  const wchar_t *v26; // r8
  int v27; // ebx
  _WORD *v28; // r14
  PSID v29; // rbx
  __int64 v30; // rsi
  __int64 i; // rdi
  __int64 v32; // r8
  __int64 *v33; // rax
  __int64 *v34; // rsi
  wchar_t *v35; // rax
  const wchar_t *v36; // r8
  __int64 v37; // rsi
  __int64 j; // rdi
  __int64 v39; // r8
  int v40; // ecx
  unsigned __int64 v41; // rdx
  PWSTR Buffer; // r8
  _WORD *v43; // r9
  unsigned __int64 v44; // rax
  _WORD *v45; // rcx
  DWORD v46; // eax
  DWORD LastError; // eax
  unsigned int v48; // ecx
  wchar_t **v49; // r14
  unsigned int v50; // ecx
  wchar_t **v51; // r14
  unsigned __int8 v52; // dl
  _BYTE *v53; // rbx
  unsigned __int8 v54; // cl
  __int64 v55; // rsi
  __int64 v56; // rax
  bool v57; // zf
  __int64 v58; // rax
  wchar_t *v59; // rax
  wchar_t **v60; // rbx
  wchar_t *v61; // r10
  size_t v62; // r14
  __int64 v63; // rdi
  __int64 v64; // rbx
  __int64 v65; // rax
  size_t v66; // rdx
  __int64 v67; // rbx
  wchar_t *v68; // rcx
  __int64 v69; // rax
  __int64 v70; // rax
  size_t v71; // rdx
  __int64 v72; // rbx
  wchar_t *v73; // rcx
  wchar_t *v74; // r10
  __int64 v75; // rax
  __int64 v76; // rax
  int v77; // eax
  int v78; // ecx
  unsigned __int64 v79; // rdx
  PWSTR v80; // r9
  _WORD *v81; // r8
  unsigned __int64 v82; // rax
  _WORD *v83; // rcx
  DWORD v84; // eax
  DWORD v85; // eax
  _WORD *v86; // rax
  HLOCAL v87; // rax
  __int64 v88; // [rsp+28h] [rbp-E0h]
  unsigned __int8 OwnerDefaulted[2]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int8 DaclPresent[2]; // [rsp+5Ah] [rbp-AEh] BYREF
  int v91; // [rsp+5Ch] [rbp-ACh]
  WORD uBytes; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int uBytes_4; // [rsp+64h] [rbp-A4h] BYREF
  HLOCAL v94; // [rsp+68h] [rbp-A0h] BYREF
  ULONG Revision[2]; // [rsp+70h] [rbp-98h] BYREF
  _WORD *v96; // [rsp+78h] [rbp-90h]
  struct _UNICODE_STRING v97; // [rsp+80h] [rbp-88h] BYREF
  PACL Sacl; // [rsp+90h] [rbp-78h] BYREF
  wchar_t **v99; // [rsp+98h] [rbp-70h]
  _BYTE *v100; // [rsp+A0h] [rbp-68h]
  HLOCAL hMem; // [rsp+A8h] [rbp-60h] BYREF
  HLOCAL v102; // [rsp+B0h] [rbp-58h] BYREF
  PSID Owner; // [rsp+B8h] [rbp-50h] BYREF
  PSID Group; // [rsp+C0h] [rbp-48h] BYREF
  PACL Dacl; // [rsp+C8h] [rbp-40h] BYREF
  HLOCAL v106; // [rsp+D0h] [rbp-38h]
  unsigned int *v107; // [rsp+D8h] [rbp-30h]
  wchar_t Source[256]; // [rsp+E8h] [rbp-20h] BYREF

  v7 = 0;
  v100 = Sid;
  v99 = a6;
  v107 = a7;
  uBytes_4 = 0;
  Owner = 0;
  Group = 0;
  Dacl = 0;
  Sacl = 0;
  OwnerDefaulted[1] = 0;
  OwnerDefaulted[0] = 0;
  DaclPresent[0] = 0;
  hMem = 0;
  v102 = 0;
  uBytes = 0;
  Revision[0] = 0;
  if ( !a4 || !a6 )
    return 87;
  v10 = 0;
  v106 = 0;
  if ( (a5 & 1) != 0 )
  {
    OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(a4, &Owner, &OwnerDefaulted[1]);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_5;
  }
  if ( (a5 & 2) != 0 )
  {
    OwnerSecurityDescriptor = RtlGetGroupSecurityDescriptor(a4, &Group, &OwnerDefaulted[1]);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_5;
  }
  if ( (a5 & 4) != 0 )
  {
    OwnerSecurityDescriptor = RtlGetDaclSecurityDescriptor(a4, DaclPresent, &Dacl, &OwnerDefaulted[1]);
    if ( OwnerSecurityDescriptor < 0 )
      goto LABEL_5;
  }
  if ( (a5 & 0x1F8) != 0 )
  {
    SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(a4, OwnerDefaulted, &Sacl, &OwnerDefaulted[1]);
    if ( SaclSecurityDescriptor < 0 )
      return RtlNtStatusToDosError(SaclSecurityDescriptor);
    if ( OwnerDefaulted[0] && Sacl )
    {
      SddlFilterSacl(Sacl, 0, &uBytes_4, a5 & 0x1F8);
      v15 = (struct _ACL *)LocalAlloc(0x40u, uBytes_4);
      v106 = v15;
      v10 = v15;
      if ( !v15 )
      {
        OwnerSecurityDescriptor = -1073741801;
        goto LABEL_5;
      }
      SddlFilterSacl(Sacl, v15, &uBytes_4, a5 & 0x1F8);
      Sacl = v10;
    }
  }
  OwnerSecurityDescriptor = RtlGetControlSecurityDescriptor(a4, &uBytes, Revision);
  if ( OwnerSecurityDescriptor < 0 )
  {
LABEL_5:
    v12 = RtlNtStatusToDosError(OwnerSecurityDescriptor);
    LocalFree(v10);
    return v12;
  }
  if ( Sid && !RtlValidSid(Sid) )
  {
    LocalFree(v10);
    return 1337;
  }
  v16 = v100;
  v17 = 0;
  v18 = 0;
  v91 = 0;
  v96 = 0;
  if ( v100 )
  {
    EnterCriticalSection(&SddlSidLookupCritical);
    gbLookupTableInitialized = 0;
  }
  InitializeSidLookupTable(1u);
  v19 = Owner;
  if ( !Owner )
  {
    v22 = 2;
    goto LABEL_35;
  }
  v94 = 0;
  v91 = 0;
  v20 = LookupSidInTable(0, Owner, v16, 0, 0, 1, &v94);
  v21 = v20;
  v22 = 2;
  if ( v20 )
  {
    v23 = *((unsigned int *)v20 + 3);
    goto LABEL_23;
  }
  if ( v94 )
  {
    v23 = 2;
LABEL_23:
    v24 = 2 * v23 + 2;
    v25 = (wchar_t *)LocalAlloc(0x40u, v24);
    v17 = v25;
    if ( v25 )
    {
      if ( v21 )
        v26 = (const wchar_t *)v21 + 1;
      else
        v26 = L"SA";
      wcscpy_s(v25, v24 >> 1, v26);
    }
    else
    {
      v18 = 8;
      v91 = 8;
    }
    goto LABEL_27;
  }
  v97 = 0;
  v40 = RtlConvertSidToUnicodeString(&v97, v19, 1u);
  if ( v40 < 0 )
    goto LABEL_66;
  v17 = LocalAlloc(0x40u, v97.Length + 2LL);
  if ( !v17 )
  {
    RtlFreeUnicodeString(&v97);
    v40 = -1073741801;
LABEL_66:
    v46 = RtlNtStatusToDosError(v40);
    SetLastError(v46);
    LastError = GetLastError();
    v18 = LastError;
    v91 = LastError;
    goto LABEL_27;
  }
  v41 = ((unsigned __int64)v97.Length + 2) >> 1;
  if ( !v41 )
  {
    v40 = -1073741811;
    goto LABEL_66;
  }
  Buffer = v97.Buffer;
  v43 = v17;
  v44 = (unsigned __int64)v97.Length >> 1;
  do
  {
    if ( !v44 )
      break;
    if ( !*Buffer )
      break;
    *v43++ = *Buffer++;
    --v44;
    --v41;
  }
  while ( v41 );
  v45 = v43 - 1;
  if ( v41 )
    v45 = v43;
  *v45 = 0;
  v40 = -2147483643;
  if ( !v41 )
    goto LABEL_66;
  RtlFreeUnicodeString(&v97);
  SetLastError(0);
LABEL_27:
  if ( (_DWORD)v18 )
  {
LABEL_28:
    LOWORD(v27) = uBytes;
LABEL_29:
    v28 = v96;
    goto LABEL_30;
  }
  v16 = v100;
LABEL_35:
  v29 = Group;
  if ( !Group )
    goto LABEL_36;
  v94 = 0;
  v18 = 0;
  v91 = 0;
  v33 = LookupSidInTable(0, Group, v16, 0, 0, 1, &v94);
  v34 = v33;
  if ( v33 )
  {
    v22 = *((_DWORD *)v33 + 3);
    goto LABEL_43;
  }
  if ( v94 )
  {
LABEL_43:
    v35 = (wchar_t *)LocalAlloc(0x40u, 2LL * v22 + 2);
    v7 = v35;
    if ( v35 )
    {
      if ( v34 )
        v36 = (const wchar_t *)v34 + 1;
      else
        v36 = L"SA";
      wcscpy_s(v35, (2 * (unsigned __int64)v22 + 2) >> 1, v36);
    }
    else
    {
      v18 = 8;
      v91 = 8;
    }
    goto LABEL_47;
  }
  v97 = 0;
  v78 = RtlConvertSidToUnicodeString(&v97, v29, 1u);
  if ( v78 >= 0 )
  {
    v7 = LocalAlloc(0x40u, v97.Length + 2LL);
    if ( v7 )
    {
      v79 = ((unsigned __int64)v97.Length + 2) >> 1;
      if ( v79 )
      {
        v80 = v97.Buffer;
        v81 = v7;
        v82 = (unsigned __int64)v97.Length >> 1;
        do
        {
          if ( !v82 )
            break;
          if ( !*v80 )
            break;
          *v81++ = *v80++;
          --v82;
          --v79;
        }
        while ( v79 );
        v83 = v81 - 1;
        if ( v79 )
          v83 = v81;
        *v83 = 0;
        v78 = -2147483643;
        if ( v79 )
        {
          RtlFreeUnicodeString(&v97);
          SetLastError(0);
          goto LABEL_47;
        }
      }
      else
      {
        v78 = -1073741811;
      }
    }
    else
    {
      RtlFreeUnicodeString(&v97);
      v78 = -1073741801;
    }
  }
  v84 = RtlNtStatusToDosError(v78);
  SetLastError(v84);
  v85 = GetLastError();
  v18 = v85;
  v91 = v85;
LABEL_47:
  if ( (_DWORD)v18 )
    goto LABEL_28;
LABEL_36:
  v27 = uBytes;
  if ( !uBytes )
    goto LABEL_29;
  v30 = 0;
  v96 = 0;
  for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
  {
    v32 = 3 * i;
    if ( ((__int64)(&ControlLookup)[3 * i + 1] & 1) != 0 )
    {
      v48 = *((_DWORD *)&ControlLookup + 2 * v32 + 2);
      v49 = &(&ControlLookup)[v32];
      if ( v48 + (unsigned int)v30 >= 0x100 )
      {
        v28 = v96;
        v18 = 87;
        goto LABEL_132;
      }
      if ( (v27 & *((_DWORD *)&ControlLookup + 2 * v32 + 3)) != 0 )
      {
        wcsncpy_s(&Source[v30], 256LL - (unsigned int)v30, (&ControlLookup)[v32], v48);
        v30 = (unsigned int)(*((_DWORD *)v49 + 2) + v30);
      }
    }
  }
  if ( (unsigned __int64)(2 * v30) >= 0x200 )
    _report_rangecheckfailure();
  Source[v30] = 0;
  if ( !(_DWORD)v30 )
  {
    v28 = 0;
LABEL_131:
    v18 = 0;
    goto LABEL_132;
  }
  v86 = LocalAlloc(0x40u, 2LL * (unsigned int)(v30 + 1));
  v96 = v86;
  v28 = v86;
  if ( v86 )
  {
    wcscpy_s(v86, (unsigned int)(v30 + 1), Source);
    goto LABEL_131;
  }
  v18 = 8;
LABEL_132:
  LOWORD(v27) = uBytes;
  v91 = v18;
LABEL_30:
  v94 = 0;
  if ( (_DWORD)v18 )
    goto LABEL_31;
  if ( (_WORD)v27 )
  {
    v37 = 0;
    v94 = 0;
    for ( j = 0; (unsigned int)j < 6; j = (unsigned int)(j + 1) )
    {
      v39 = 3 * j;
      if ( ((__int64)(&ControlLookup)[3 * j + 1] & 2) != 0 )
      {
        v50 = *((_DWORD *)&ControlLookup + 2 * v39 + 2);
        v51 = &(&ControlLookup)[v39];
        if ( v50 + (unsigned int)v37 >= 0x100 )
        {
          v18 = 87;
          goto LABEL_76;
        }
        if ( ((unsigned __int16)v27 & *((_DWORD *)&ControlLookup + 2 * v39 + 3)) != 0 )
        {
          wcsncpy_s(&Source[v37], 256LL - (unsigned int)v37, (&ControlLookup)[v39], v50);
          v37 = (unsigned int)(*((_DWORD *)v51 + 2) + v37);
        }
      }
    }
    if ( (unsigned __int64)(2 * v37) >= 0x200 )
      _report_rangecheckfailure();
    Source[v37] = 0;
    if ( !(_DWORD)v37 )
    {
LABEL_75:
      v18 = 0;
      goto LABEL_76;
    }
    v87 = LocalAlloc(0x40u, 2LL * (unsigned int)(v37 + 1));
    v94 = v87;
    if ( v87 )
    {
      wcscpy_s((wchar_t *)v87, (unsigned int)(v37 + 1), Source);
      goto LABEL_75;
    }
    v18 = 8;
LABEL_76:
    v28 = v96;
    v91 = v18;
  }
  if ( !(_DWORD)v18 )
  {
    v52 = OwnerDefaulted[0];
    v53 = v100;
    if ( OwnerDefaulted[0] )
    {
      v91 = LocalConvertAclToString((__int64)Sacl, OwnerDefaulted[0], 0, (wchar_t **)&hMem, &uBytes_4, v100, 0, v18);
      LODWORD(v18) = v91;
      if ( v91 )
        goto LABEL_31;
      LODWORD(v18) = uBytes_4;
      v52 = OwnerDefaulted[0];
    }
    v54 = DaclPresent[0];
    if ( DaclPresent[0] )
    {
      v77 = LocalConvertAclToString((__int64)Dacl, DaclPresent[0], 1, (wchar_t **)&v102, &uBytes_4, v53, 0, 0);
      v91 = v77;
      if ( v77 )
      {
        LODWORD(v18) = v77;
        goto LABEL_31;
      }
      LODWORD(v18) = uBytes_4 + v18;
      v52 = OwnerDefaulted[0];
      v54 = DaclPresent[0];
    }
    v55 = -1;
    if ( v17 )
    {
      v56 = -1;
      do
        v57 = v17[++v56] == 0;
      while ( !v57 );
      LODWORD(v18) = v18 + 2 * v56 + 4;
    }
    if ( v7 )
    {
      v58 = -1;
      do
        v57 = v7[++v58] == 0;
      while ( !v57 );
      LODWORD(v18) = v18 + 2 * v58 + 4;
    }
    if ( v54 )
    {
      LODWORD(v18) = v18 + 4;
      if ( v28 )
      {
        v76 = -1;
        do
          v57 = v28[++v76] == 0;
        while ( !v57 );
        LODWORD(v18) = v18 + 2 * v76;
      }
    }
    if ( v52 )
    {
      LODWORD(v18) = v18 + 4;
      if ( v94 )
      {
        v75 = -1;
        do
          v57 = *((_WORD *)v94 + ++v75) == 0;
        while ( !v57 );
        LODWORD(v18) = v18 + 2 * v75;
      }
    }
    v59 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)v18 + 2LL);
    v60 = v99;
    v61 = v59;
    *v99 = v59;
    if ( v59 )
    {
      v62 = ((unsigned __int64)(unsigned int)v18 + 2) >> 1;
      if ( v17 )
      {
        LODWORD(v88) = 58;
        swprintf_s(v59, v62, L"%ws%wc%ws", L"O", v88, v17);
        v61 = *v60;
        v63 = -1;
        do
          ++v63;
        while ( v61[v63] );
      }
      else
      {
        LODWORD(v63) = 0;
      }
      if ( v7 )
      {
        LODWORD(v88) = 58;
        v64 = (unsigned int)v63;
        swprintf_s(&v61[v64], v62 - (unsigned int)v63, L"%ws%wc%ws", L"G", v88, v7);
        v61 = *v99;
        v65 = -1;
        do
          ++v65;
        while ( (*v99)[v64 + v65] );
        Revision[0] = v65;
        LODWORD(v63) = v65 + v63;
      }
      if ( DaclPresent[0] )
      {
        v66 = v62 - (unsigned int)v63;
        v67 = (unsigned int)v63;
        v68 = &v61[v67];
        LODWORD(v88) = 58;
        if ( v96 )
          swprintf_s(v68, v66, L"%ws%wc%ws", L"D", v88, v96);
        else
          swprintf_s(v68, v66, L"%ws%wc", L"D", v88);
        v61 = *v99;
        v69 = -1;
        do
          ++v69;
        while ( (*v99)[v67 + v69] );
        v63 = (unsigned int)(v69 + v63);
        Revision[0] = v69;
        if ( v102 )
        {
          wcscpy_s(&v61[v63], v62 - (unsigned int)v63, (const wchar_t *)v102);
          v61 = *v99;
          v70 = -1;
          do
            ++v70;
          while ( (*v99)[v63 + v70] );
          Revision[0] = v70;
          LODWORD(v63) = v70 + v63;
        }
      }
      if ( OwnerDefaulted[0] )
      {
        v71 = v62 - (unsigned int)v63;
        v72 = (unsigned int)v63;
        v73 = &v61[v72];
        LODWORD(v88) = 58;
        if ( v94 )
          swprintf_s(v73, v71, L"%ws%wc%ws", L"S", v88, v94);
        else
          swprintf_s(v73, v71, L"%ws%wc", L"S", v88);
        v74 = *v99;
        do
          ++v55;
        while ( (*v99)[v72 + v55] );
        Revision[0] = v55;
        if ( hMem )
          wcscpy_s(&v74[(unsigned int)(v55 + v63)], v62 - (unsigned int)(v55 + v63), (const wchar_t *)hMem);
      }
      if ( v107 )
        *v107 = (unsigned int)v18 >> 1;
      LODWORD(v18) = v91;
    }
    else
    {
      LODWORD(v18) = 8;
    }
  }
LABEL_31:
  LocalFree(v17);
  LocalFree(v7);
  LocalFree(hMem);
  LocalFree(v102);
  LocalFree(v94);
  LocalFree(v96);
  LocalFree(v106);
  LocalFree(0);
  InitializeSidLookupTable(2u);
  if ( v100 )
  {
    gbLookupTableInitialized = 0;
    LeaveCriticalSection(&SddlSidLookupCritical);
  }
  return v18;
}

```

## disassembly

```asm
0x180004260  mov     r11, rsp
0x180004263  push    rbp
0x180004264  push    rsi
0x180004265  push    r12
0x180004267  push    r15
0x180004269  lea     rbp, [r11-228h]
0x180004270  sub     rsp, 308h
0x180004277  mov     rax, cs:__security_cookie
0x18000427e  xor     rax, rsp
0x180004281  mov     [rbp+220h+var_40], rax
0x180004288  mov     rax, [rbp+220h+arg_30]
0x18000428f  xor     r12d, r12d
0x180004292  mov     [rbp+220h+var_288], rcx
0x180004296  mov     r15, rcx
0x180004299  mov     rcx, [rbp+220h+arg_28]
0x1800042a0  mov     rsi, r9
0x1800042a3  mov     [rbp+220h+var_290], rcx
0x1800042a7  mov     [rbp+220h+var_250], rax
0x1800042ab  mov     dword ptr [rsp+320h+uBytes+4], r12d
0x1800042b0  mov     [rbp+220h+Owner], r12
0x1800042b4  mov     [rbp+220h+Group], r12
0x1800042b8  mov     [rbp+220h+Dacl], r12
0x1800042bc  mov     [rbp+220h+Sacl], r12
0x1800042c0  mov     [rsp+320h+OwnerDefaulted+1], r12b
0x1800042c5  mov     [rsp+320h+OwnerDefaulted], r12b
0x1800042ca  mov     [rsp+320h+DaclPresent], r12b
0x1800042cf  mov     [rbp+220h+hMem], r12
0x1800042d3  mov     [rbp+220h+var_278], r12
0x1800042d7  mov     word ptr [rsp+320h+uBytes], r12w
0x1800042dd  mov     [rsp+320h+Revision], r12d
0x1800042e2  test    r9, r9
0x1800042e5  jz      loc_180004F01
0x1800042eb  test    rcx, rcx
0x1800042ee  jz      loc_180004F01
0x1800042f4  mov     [r11+10h], rbx
0x1800042f8  mov     ebx, dword ptr [rbp+220h+arg_20]
0x1800042fe  mov     [r11-38h], r14
0x180004302  mov     r14d, r12d
0x180004305  mov     [r11-28h], rdi
0x180004309  mov     [rbp+220h+var_258], r12
0x18000430d  test    bl, 1
0x180004310  jz      short loc_180004374
0x180004312  lea     r8, [rsp+320h+OwnerDefaulted+1]; OwnerDefaulted
0x180004317  mov     rcx, r9; SecurityDescriptor
0x18000431a  lea     rdx, [rbp+220h+Owner]; Owner
0x18000431e  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x180004324  mov     edi, eax
0x180004326  test    eax, eax
0x180004328  jns     short loc_180004374
0x18000432a  mov     ecx, edi; Status
0x18000432c  call    cs:__imp_RtlNtStatusToDosError
0x180004332  mov     rcx, r14; hMem
0x180004335  mov     ebx, eax
0x180004337  call    cs:__imp_LocalFree
0x18000433d  mov     eax, ebx
0x18000433f  mov     rdi, [rsp+300h]
0x180004347  mov     rbx, [rsp+320h+arg_8]
0x18000434f  mov     r14, [rsp+320h+var_30]
0x180004357  mov     rcx, [rbp+220h+var_40]
0x18000435e  xor     rcx, rsp; StackCookie
0x180004361  call    __security_check_cookie
0x180004366  add     rsp, 308h
0x18000436d  pop     r15
0x18000436f  pop     r12
0x180004371  pop     rsi
0x180004372  pop     rbp
0x180004373  retn
0x180004374  test    bl, 2
0x180004377  jz      short loc_180004391
0x180004379  lea     r8, [rsp+320h+OwnerDefaulted+1]; GroupDefaulted
0x18000437e  mov     rcx, rsi; SecurityDescriptor
0x180004381  lea     rdx, [rbp+220h+Group]; Group
0x180004385  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18000438b  mov     edi, eax
0x18000438d  test    eax, eax
0x18000438f  js      short loc_18000432A
0x180004391  test    bl, 4
0x180004394  jz      short loc_1800043B7
0x180004396  lea     r9, [rsp+320h+OwnerDefaulted+1]; DaclDefaulted
0x18000439b  mov     rcx, rsi; SecurityDescriptor
0x18000439e  lea     r8, [rbp+220h+Dacl]; Dacl
0x1800043a2  lea     rdx, [rsp+320h+DaclPresent]; DaclPresent
0x1800043a7  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800043ad  mov     edi, eax
0x1800043af  test    eax, eax
0x1800043b1  js      loc_18000432A
0x1800043b7  and     ebx, 1F8h
0x1800043bd  jz      short loc_180004434
0x1800043bf  lea     r9, [rsp+320h+OwnerDefaulted+1]; SaclDefaulted
0x1800043c4  mov     rcx, rsi; SecurityDescriptor
0x1800043c7  lea     r8, [rbp+220h+Sacl]; Sacl
0x1800043cb  lea     rdx, [rsp+320h+OwnerDefaulted]; SaclPresent
0x1800043d0  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1800043d6  test    eax, eax
0x1800043d8  js      loc_180004D5A
0x1800043de  cmp     [rsp+320h+OwnerDefaulted], r12b
0x1800043e3  jz      short loc_180004434
0x1800043e5  mov     rcx, [rbp+220h+Sacl]
0x1800043e9  test    rcx, rcx
0x1800043ec  jz      short loc_180004434
0x1800043ee  mov     r9d, ebx
0x1800043f1  lea     r8, [rsp+320h+uBytes+4]
0x1800043f6  xor     edx, edx
0x1800043f8  call    SddlFilterSacl
0x1800043fd  mov     edx, dword ptr [rsp+320h+uBytes+4]; uBytes
0x180004401  mov     ecx, 40h ; '@'; uFlags
0x180004406  call    cs:__imp_LocalAlloc
0x18000440c  mov     [rbp+220h+var_258], rax
0x180004410  mov     r14, rax
0x180004413  test    rax, rax
0x180004416  jz      loc_180004D67
0x18000441c  mov     rcx, [rbp+220h+Sacl]
0x180004420  lea     r8, [rsp+320h+uBytes+4]
0x180004425  mov     r9d, ebx
0x180004428  mov     rdx, rax
0x18000442b  call    SddlFilterSacl
0x180004430  mov     [rbp+220h+Sacl], r14
0x180004434  lea     r8, [rsp+320h+Revision]; Revision
0x180004439  mov     rcx, rsi; SecurityDescriptor
0x18000443c  lea     rdx, [rsp+320h+uBytes]; Control
0x180004441  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180004447  mov     edi, eax
0x180004449  test    eax, eax
0x18000444b  js      loc_18000432A
0x180004451  test    r15, r15
0x180004454  jnz     loc_180004D71
0x18000445a  mov     rsi, [rbp+220h+var_288]
0x18000445e  mov     r15, r12
0x180004461  mov     [rsp+320h+var_28], r13
0x180004469  mov     r13d, r12d
0x18000446c  mov     [rsp+320h+var_2CC], r12d
0x180004471  mov     [rsp+320h+var_2B0], r12
0x180004476  test    rsi, rsi
0x180004479  jnz     loc_180004D95
0x18000447f  mov     cl, 1
0x180004481  call    InitializeSidLookupTable
0x180004486  mov     rbx, [rbp+220h+Owner]
0x18000448a  lea     r10, ControlLookup
0x180004491  test    rbx, rbx
0x180004494  jz      loc_1800045B4
0x18000449a  lea     rax, [rsp+320h+var_2C0]
0x18000449f  mov     [rsp+320h+var_2C0], r12
0x1800044a4  mov     [rsp+320h+var_2F0], rax; __int64
0x1800044a9  xor     r9d, r9d
0x1800044ac  mov     [rsp+320h+var_2F8], 1; char
0x1800044b1  mov     r8, rsi
0x1800044b4  mov     rdx, rbx; Sid
0x1800044b7  mov     [rsp+320h+var_300], r12; __int64
0x1800044bc  xor     ecx, ecx; String1
0x1800044be  mov     [rsp+320h+var_2CC], r13d
0x1800044c3  call    LookupSidInTable
0x1800044c8  mov     rsi, rax
0x1800044cb  mov     edi, 0C0000017h
0x1800044d0  mov     r14d, 2
0x1800044d6  test    rax, rax
0x1800044d9  jz      loc_1800046DB
0x1800044df  mov     eax, [rax+0Ch]
0x1800044e2  lea     rbx, ds:2[rax*2]
0x1800044ea  mov     ecx, 40h ; '@'; uFlags
0x1800044ef  mov     rdx, rbx; uBytes
0x1800044f2  call    cs:__imp_LocalAlloc
0x1800044f8  mov     r15, rax
0x1800044fb  test    rax, rax
0x1800044fe  jz      loc_180004DD2
0x180004504  shr     rbx, 1
0x180004507  mov     rcx, rax; Destination
0x18000450a  mov     rdx, rbx; SizeInWords
0x18000450d  test    rsi, rsi
0x180004510  jz      loc_180004DE2
0x180004516  lea     r8, [rsi+2]; Source
0x18000451a  call    cs:__imp_wcscpy_s
0x180004520  test    r13d, r13d
0x180004523  jz      loc_180004DEE
0x180004529  movzx   ebx, word ptr [rsp+320h+uBytes]
0x18000452e  mov     r14, [rsp+320h+var_2B0]
0x180004533  xor     r9d, r9d
0x180004536  mov     [rsp+320h+var_2C0], r9
0x18000453b  test    r13d, r13d
0x18000453e  jz      loc_18000469D
0x180004544  mov     rcx, r15; hMem
0x180004547  call    cs:__imp_LocalFree
0x18000454d  mov     rcx, r12; hMem
0x180004550  call    cs:__imp_LocalFree
0x180004556  mov     rcx, [rbp+220h+hMem]; hMem
0x18000455a  call    cs:__imp_LocalFree
0x180004560  mov     rcx, [rbp+220h+var_278]; hMem
0x180004564  call    cs:__imp_LocalFree
0x18000456a  mov     rcx, [rsp+320h+var_2C0]; hMem
0x18000456f  call    cs:__imp_LocalFree
0x180004575  mov     rcx, [rsp+320h+var_2B0]; hMem
0x18000457a  call    cs:__imp_LocalFree
0x180004580  mov     rcx, [rbp+220h+var_258]; hMem
0x180004584  call    cs:__imp_LocalFree
0x18000458a  xor     ecx, ecx; hMem
0x18000458c  call    cs:__imp_LocalFree
0x180004592  mov     cl, 2
0x180004594  call    InitializeSidLookupTable
0x180004599  cmp     [rbp+220h+var_288], 0
0x18000459e  jnz     loc_180004EE5
0x1800045a4  mov     eax, r13d
0x1800045a7  mov     r13, [rsp+320h+var_28]
0x1800045af  jmp     loc_18000433F
0x1800045b4  mov     edi, 0C0000017h
0x1800045b9  mov     r14d, 2
0x1800045bf  mov     rbx, [rbp+220h+Group]
0x1800045c3  test    rbx, rbx
0x1800045c6  jnz     short loc_180004606
0x1800045c8  movzx   ebx, word ptr [rsp+320h+uBytes]
0x1800045cd  test    bx, bx
0x1800045d0  jz      loc_18000452E
0x1800045d6  xor     ecx, ecx
0x1800045d8  xor     esi, esi
0x1800045da  mov     [rsp+320h+var_2B0], rcx
0x1800045df  xor     edi, edi
0x1800045e1  cmp     edi, 6
0x1800045e4  jnb     loc_180004BAD
0x1800045ea  lea     rcx, [rdi+rdi*2]
0x1800045ee  lea     r8, ds:0[rcx*8]
0x1800045f6  test    byte ptr [r8+r10+10h], 1
0x1800045fc  jnz     loc_1800047A2
0x180004602  inc     edi
0x180004604  jmp     short loc_1800045E1
0x180004606  lea     rax, [rsp+320h+var_2C0]
0x18000460b  mov     [rsp+320h+var_2C0], r12
0x180004610  mov     [rsp+320h+var_2F0], rax; __int64
0x180004615  xor     r13d, r13d
0x180004618  mov     [rsp+320h+var_2F8], 1; char
0x18000461d  xor     r9d, r9d
0x180004620  mov     r8, rsi
0x180004623  mov     [rsp+320h+var_300], r12; __int64
0x180004628  mov     rdx, rbx; Sid
0x18000462b  mov     [rsp+320h+var_2CC], r13d
0x180004630  xor     ecx, ecx; String1
0x180004632  call    LookupSidInTable
0x180004637  mov     rsi, rax
0x18000463a  test    rax, rax
0x18000463d  jz      loc_180004BEA
0x180004643  mov     r14d, [rax+0Ch]
0x180004647  mov     eax, r14d
0x18000464a  mov     ecx, 40h ; '@'; uFlags
0x18000464f  lea     rbx, ds:2[rax*2]
0x180004657  mov     rdx, rbx; uBytes
0x18000465a  call    cs:__imp_LocalAlloc
0x180004660  mov     r12, rax
0x180004663  test    rax, rax
0x180004666  jz      loc_180004E1A
0x18000466c  shr     rbx, 1
0x18000466f  mov     rcx, rax; Destination
0x180004672  mov     rdx, rbx; SizeInWords
0x180004675  test    rsi, rsi
0x180004678  jz      loc_180004E2A
0x18000467e  lea     r8, [rsi+2]; Source
0x180004682  call    cs:__imp_wcscpy_s
0x180004688  test    r13d, r13d
0x18000468b  jnz     loc_180004529
0x180004691  lea     r10, ControlLookup
0x180004698  jmp     loc_1800045C8
0x18000469d  test    bx, bx
0x1800046a0  jz      loc_18000486D
0x1800046a6  xor     esi, esi
0x1800046a8  lea     r13, ControlLookup
0x1800046af  mov     [rsp+320h+var_2C0], rsi
0x1800046b4  xor     edi, edi
0x1800046b6  cmp     edi, 6
0x1800046b9  jnb     loc_180004840
0x1800046bf  lea     rcx, [rdi+rdi*2]
0x1800046c3  lea     r8, ds:0[rcx*8]
0x1800046cb  test    byte ptr [r8+r13+10h], 2
0x1800046d1  jnz     loc_1800047F3
0x1800046d7  inc     edi
0x1800046d9  jmp     short loc_1800046B6
0x1800046db  cmp     [rsp+320h+var_2C0], r12
0x1800046e0  jnz     loc_180004DCA
0x1800046e6  xorps   xmm0, xmm0
0x1800046e9  lea     rcx, [rsp+320h+var_2B0+8]; UnicodeString
0x1800046ee  mov     r8b, 1; AllocateDestinationString
0x1800046f1  mov     rdx, rbx; Sid
0x1800046f4  movups  xmmword ptr [rsp+320h+var_2B0+8], xmm0
0x1800046f9  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800046ff  mov     ecx, eax
0x180004701  test    eax, eax
0x180004703  js      short loc_180004782
0x180004705  movzx   edx, word ptr [rsp+320h+var_2B0+8]
0x18000470a  mov     ecx, 40h ; '@'; uFlags
0x18000470f  add     rdx, r14; uBytes
0x180004712  call    cs:__imp_LocalAlloc
0x180004718  mov     r15, rax
0x18000471b  test    rax, rax
0x18000471e  jz      loc_180004DAE
0x180004724  movzx   eax, word ptr [rsp+320h+var_2B0+8]
0x180004729  lea     rdx, [rax+2]
0x18000472d  shr     rdx, 1
0x180004730  jz      loc_180004DC0
0x180004736  mov     r8, [rbp+220h+var_2A0]
0x18000473a  mov     r9, r15
0x18000473d  shr     rax, 1
0x180004740  test    rax, rax
0x180004743  jz      short loc_180004761
0x180004745  movzx   ecx, word ptr [r8]
0x180004749  test    cx, cx
  ... truncated ...
```
