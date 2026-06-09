# CapabilityHelper::CreateSecurityAttributesForUWPCapability

- ea: `0x1800c6a90`
- end: `0x1800c7470`
- name: `CapabilityHelper::CreateSecurityAttributesForUWPCapability`
- size: `2528`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c6718`

## callees

- `0x18007f488`
- `0x1800c6a90`
- `0x1800c7a60`
- `0x1800c7c34`
- `0x1800d4a50`
- `0x180277a9c`
- `0x1802cc14c`
- `0x180303644`
- `0x180356360`
- `0x180356754`
- `0x180438140`
- `0x1804ae288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c7374`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c7374`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c6e3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c6e3c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6e51`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6e51`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c7387`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c7387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c727d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c727d`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c6b4a`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800c6b4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7245`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7271`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7245`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c7271`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c71dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800c71dc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c6b81`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c6eb2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c6b81`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800c6eb2`

## string_xrefs

- `0x1800c7288`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c729a`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c72af`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c72c1`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c72d3`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c72e8`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c72fd`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c730f`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c7321`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c7333`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c7345`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c73b0`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c73c5`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c73d7`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c7418`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`
- `0x1800c7449`: `shellcommon\internal\shell\inc\Private\CapabilityHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall CapabilityHelper::CreateSecurityAttributesForUWPCapability(_QWORD *a1)
{
  __int64 v2; // rdx
  const wchar_t *v3; // rax
  const char *v4; // r9
  int v5; // eax
  const char *v6; // r9
  __int64 v7; // rsi
  __int64 v8; // rax
  const unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // r8
  unsigned __int16 v12; // r9
  WCHAR *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  const char *v16; // r9
  __int64 v17; // r8
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r9
  __int64 v20; // rdx
  WCHAR *v21; // rax
  unsigned __int16 v22; // r8
  WCHAR *v23; // rcx
  int v24; // eax
  __int64 v25; // rdx
  WCHAR *v26; // rax
  const char *v27; // r9
  __int64 v28; // r8
  const unsigned __int16 *v29; // rdi
  __int64 v30; // rcx
  const unsigned __int16 *v31; // r9
  __int64 v32; // rdx
  WCHAR *v33; // rax
  unsigned __int16 v34; // r8
  WCHAR *v35; // rcx
  __int64 v36; // rdx
  WCHAR *v37; // rax
  const char *v38; // r9
  __int64 v39; // r8
  __int64 v40; // rcx
  const unsigned __int16 *v41; // r9
  __int64 v42; // rdx
  WCHAR *v43; // rax
  unsigned __int16 v44; // r8
  WCHAR *v45; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v48; // r9
  int v49; // eax
  void *v50; // rcx
  __int64 v51; // rdx
  WCHAR *v52; // rax
  const char *v53; // r9
  __int64 v54; // r8
  __int64 v55; // rcx
  __int64 v56; // rdx
  WCHAR *v57; // rax
  unsigned __int16 v58; // r8
  WCHAR *v59; // rcx
  __int64 v60; // rdx
  WCHAR *v61; // rax
  const char *v62; // r9
  __int64 v63; // r8
  __int64 v64; // rcx
  const unsigned __int16 *v65; // r9
  __int64 v66; // rdx
  WCHAR *v67; // rax
  unsigned __int16 v68; // r8
  WCHAR *v69; // rcx
  __int64 v70; // rdx
  WCHAR *v71; // rax
  const char *v72; // r9
  __int64 v73; // r8
  __int64 v74; // rcx
  const unsigned __int16 *v75; // r9
  __int64 v76; // rdx
  WCHAR *v77; // rax
  unsigned __int16 v78; // r8
  WCHAR *v79; // rcx
  __int64 v80; // rdx
  WCHAR *v81; // rax
  const char *v82; // r9
  __int64 v83; // r8
  const unsigned __int16 *v84; // rcx
  __int64 v85; // rbx
  WCHAR *v86; // rax
  unsigned __int16 v87; // dx
  WCHAR *v88; // rcx
  const char *v89; // r9
  __int64 v90; // rcx
  HANDLE CurrentProcess; // rax
  int v93; // [rsp+20h] [rbp-E0h]
  LPWSTR StringSid; // [rsp+28h] [rbp-D8h] BYREF
  char v95; // [rsp+30h] [rbp-D0h]
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL v97; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v100; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v101; // [rsp+60h] [rbp-A0h]
  __int64 v102; // [rsp+70h] [rbp-90h]
  __int128 v103; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Sid[48]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v105[48]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR StringSecurityDescriptor[1024]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+848h]

  hMem = a1;
  v103 = 0;
  v2 = 0x7FFF;
  v3 = L"shellExperience";
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v2;
  }
  while ( v2 );
  v4 = v2 == 0 ? (const char *)0xC000000DLL : 0LL;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x15,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v4,
      v93);
  LOWORD(v103) = -2 - 2 * v2;
  WORD1(v103) = -2 * v2;
  *((_QWORD *)&v103 + 1) = L"shellExperience";
  v5 = RtlDeriveCapabilitySidsFromName(&v103, v105, Sid, v4);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x1E,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      (const char *)(unsigned int)v5,
      v93);
  hMem = 0;
  StringSid = 0;
  v95 = 1;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x22,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v6);
  if ( v95 )
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hMem,
      StringSid);
  v7 = 2147483646;
  v8 = 2147483646;
  v9 = L"D:AI";
  v10 = 1024;
  v11 = StringSecurityDescriptor;
  do
  {
    if ( !v8 )
      break;
    v12 = *v9;
    if ( !*v9 )
      break;
    ++v9;
    *v11++ = v12;
    --v8;
    --v10;
  }
  while ( v10 );
  v13 = v11 - 1;
  if ( v10 )
    v13 = v11;
  *v13 = 0;
  if ( !v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      (const char *)0x8007007ALL,
      (int)&hMem);
  v14 = 1024;
  v15 = StringSecurityDescriptor;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  v16 = v14 == 0 ? (const char *)0x80070057LL : 0LL;
  v17 = (1024 - v14) & -(__int64)(v14 != 0);
  if ( v14 )
  {
    v18 = 2147483646;
    v19 = L"(A;CI;KA;;;";
    v20 = 1024 - v17;
    v21 = &StringSecurityDescriptor[v17];
    if ( v17 != 1024 )
    {
      do
      {
        if ( !v18 )
          break;
        v22 = *v19;
        if ( !*v19 )
          break;
        ++v19;
        *v21++ = v22;
        --v18;
        --v20;
      }
      while ( v20 );
    }
    v23 = v21 - 1;
    if ( v20 )
      v23 = v21;
    *v23 = 0;
    v16 = v20 == 0 ? (const char *)0x8007007ALL : 0LL;
  }
  if ( (int)v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v16,
      (int)&hMem);
  v24 = StringCchCatW(StringSecurityDescriptor, 0x400u, (const unsigned __int16 *)hMem);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      (const char *)(unsigned int)v24,
      (int)&hMem);
  v25 = 1024;
  v26 = StringSecurityDescriptor;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v27 = v25 == 0 ? (const char *)0x80070057LL : 0LL;
  v28 = (1024 - v25) & -(__int64)(v25 != 0);
  v29 = L")";
  if ( v25 )
  {
    v30 = 2147483646;
    v31 = L")";
    v32 = 1024 - v28;
    v33 = &StringSecurityDescriptor[v28];
    if ( v28 != 1024 )
    {
      do
      {
        if ( !v30 )
          break;
        v34 = *v31;
        if ( !*v31 )
          break;
        ++v31;
        *v33++ = v34;
        --v30;
        --v32;
      }
      while ( v32 );
    }
    v35 = v33 - 1;
    if ( v32 )
      v35 = v33;
    *v35 = 0;
    v27 = v32 == 0 ? (const char *)0x8007007ALL : 0LL;
  }
  if ( (int)v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v27,
      (int)&hMem);
  v36 = 1024;
  v37 = StringSecurityDescriptor;
  do
  {
    if ( !*v37 )
      break;
    ++v37;
    --v36;
  }
  while ( v36 );
  v38 = v36 == 0 ? (const char *)0x80070057LL : 0LL;
  v39 = (1024 - v36) & -(__int64)(v36 != 0);
  if ( v36 )
  {
    v40 = 2147483646;
    v41 = L"(A;OICIID;KA;;;";
    v42 = 1024 - v39;
    v43 = &StringSecurityDescriptor[v39];
    if ( v39 != 1024 )
    {
      do
      {
        if ( !v40 )
          break;
        v44 = *v41;
        if ( !*v41 )
          break;
        ++v41;
        *v43++ = v44;
        --v40;
        --v42;
      }
      while ( v42 );
    }
    v45 = v43 - 1;
    if ( v42 )
      v45 = v43;
    *v45 = 0;
    v38 = v42 == 0 ? (const char *)0x8007007ALL : 0LL;
  }
  if ( (int)v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v38,
      (int)&hMem);
  hObject = 0;
  StringSid = 0;
  v95 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, (PHANDLE)&StringSid) )
    goto LABEL_54;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, (PHANDLE)&StringSid) )
    {
LABEL_54:
      LastError = 0;
      goto LABEL_55;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_55:
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      (const char *)(unsigned int)LastError,
      (int)&hObject);
  if ( v95 )
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hObject,
      StringSid);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, hObject);
  v97 = 0;
  StringSid = 0;
  v95 = 1;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v48);
  if ( v95 )
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v97,
      StringSid);
  v49 = StringCchCatW(StringSecurityDescriptor, 0x400u, (const unsigned __int16 *)v97);
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      (const char *)(unsigned int)v49,
      (int)&v97);
  if ( v97 )
    LocalFree(v97);
  v50 = Block;
  Block = 0;
  if ( v50 )
    operator delete(v50);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  v51 = 1024;
  v52 = StringSecurityDescriptor;
  do
  {
    if ( !*v52 )
      break;
    ++v52;
    --v51;
  }
  while ( v51 );
  v53 = v51 == 0 ? (const char *)0x80070057LL : 0LL;
  v54 = (1024 - v51) & -(__int64)(v51 != 0);
  if ( v51 )
  {
    v55 = 2147483646;
    v56 = 1024 - v54;
    v57 = &StringSecurityDescriptor[v54];
    if ( v54 != 1024 )
    {
      do
      {
        if ( !v55 )
          break;
        v58 = *v29;
        if ( !*v29 )
          break;
        ++v29;
        *v57++ = v58;
        --v55;
        --v56;
      }
      while ( v56 );
    }
    v59 = v57 - 1;
    if ( v56 )
      v59 = v57;
    *v59 = 0;
    v53 = v56 == 0 ? (const char *)0x8007007ALL : 0LL;
  }
  if ( (int)v53 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v53,
      (int)&v97);
  v60 = 1024;
  v61 = StringSecurityDescriptor;
  do
  {
    if ( !*v61 )
      break;
    ++v61;
    --v60;
  }
  while ( v60 );
  v62 = v60 == 0 ? (const char *)0x80070057LL : 0LL;
  v63 = (1024 - v60) & -(__int64)(v60 != 0);
  if ( v60 )
  {
    v64 = 2147483646;
    v65 = L"(A;OICIID;KA;;;SY)";
    v66 = 1024 - v63;
    v67 = &StringSecurityDescriptor[v63];
    if ( v63 != 1024 )
    {
      do
      {
        if ( !v64 )
          break;
        v68 = *v65;
        if ( !*v65 )
          break;
        ++v65;
        *v67++ = v68;
        --v64;
        --v66;
      }
      while ( v66 );
    }
    v69 = v67 - 1;
    if ( v66 )
      v69 = v67;
    *v69 = 0;
    v62 = v66 == 0 ? (const char *)0x8007007ALL : 0LL;
  }
  if ( (int)v62 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v62,
      (int)&v97);
  v70 = 1024;
  v71 = StringSecurityDescriptor;
  do
  {
    if ( !*v71 )
      break;
    ++v71;
    --v70;
  }
  while ( v70 );
  v72 = v70 == 0 ? (const char *)0x80070057LL : 0LL;
  v73 = (1024 - v70) & -(__int64)(v70 != 0);
  if ( v70 )
  {
    v74 = 2147483646;
    v75 = L"(A;OICIID;KA;;;BA)";
    v76 = 1024 - v73;
    v77 = &StringSecurityDescriptor[v73];
    if ( v73 != 1024 )
    {
      do
      {
        if ( !v74 )
          break;
        v78 = *v75;
        if ( !*v75 )
          break;
        ++v75;
        *v77++ = v78;
        --v74;
        --v76;
      }
      while ( v76 );
    }
    v79 = v77 - 1;
    if ( v76 )
      v79 = v77;
    *v79 = 0;
    v72 = v76 == 0 ? (const char *)0x8007007ALL : 0LL;
  }
  if ( (int)v72 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v72,
      (int)&v97);
  v80 = 1024;
  v81 = StringSecurityDescriptor;
  do
  {
    if ( !*v81 )
      break;
    ++v81;
    --v80;
  }
  while ( v80 );
  v82 = v80 == 0 ? (const char *)0x80070057LL : 0LL;
  v83 = (1024 - v80) & -(__int64)(v80 != 0);
  if ( v80 )
  {
    v84 = L"(A;OICIID;KR;;;RC)";
    v85 = 1024 - v83;
    v86 = &StringSecurityDescriptor[v83];
    if ( 1024 != v83 )
    {
      do
      {
        if ( !v7 )
          break;
        v87 = *v84;
        if ( !*v84 )
          break;
        ++v84;
        *v86++ = v87;
        --v7;
        --v85;
      }
      while ( v85 );
    }
    v88 = v86 - 1;
    if ( v85 )
      v88 = v86;
    *v88 = 0;
    v82 = v85 == 0 ? (const char *)0x8007007ALL : 0LL;
  }
  if ( (int)v82 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v82,
      (int)&v97);
  v100 = 0;
  v101 = 0;
  v102 = 0;
  StringSid = 0;
  v95 = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          StringSecurityDescriptor,
          1u,
          (PSECURITY_DESCRIPTOR *)&StringSid,
          0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x44,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\Private\\CapabilityHelper.h",
      v89);
  if ( v95 )
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &v100,
      StringSid);
  LODWORD(v101) = 24;
  v90 = v100;
  *((_QWORD *)&v101 + 1) = v100;
  *a1 = v100;
  v100 = 0;
  *((_DWORD *)a1 + 2) = 24;
  *((_DWORD *)a1 + 3) = DWORD1(v101);
  a1[2] = v90;
  a1[3] = v102;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v100);
  if ( hMem )
    LocalFree(hMem);
  return a1;
}

```

## disassembly

```asm
0x1800c6a90  push    rbp
0x1800c6a92  push    rbx
0x1800c6a93  push    rsi
0x1800c6a94  push    rdi
0x1800c6a95  push    r12
0x1800c6a97  push    r13
0x1800c6a99  push    r14
0x1800c6a9b  push    r15
0x1800c6a9d  lea     rbp, [rsp-808h]
0x1800c6aa5  sub     rsp, 908h
0x1800c6aac  mov     rax, cs:__security_cookie
0x1800c6ab3  xor     rax, rsp
0x1800c6ab6  mov     [rbp+840h+var_50], rax
0x1800c6abd  mov     r14, rcx
0x1800c6ac0  mov     [rsp+940h+hMem], rcx
0x1800c6ac5  xor     r15d, r15d
0x1800c6ac8  xorps   xmm0, xmm0
0x1800c6acb  movups  [rsp+940h+var_8C8], xmm0
0x1800c6ad0  mov     edx, 7FFFh
0x1800c6ad5  lea     r8, aShellexperienc_0; "shellExperience"
0x1800c6adc  mov     rax, r8
0x1800c6adf  lea     r13d, [r15+2]
0x1800c6ae3  lea     r12d, [r15+1]
0x1800c6ae7  cmp     [rax], r15w
0x1800c6aeb  jz      short loc_1800C6AF5
0x1800c6aed  add     rax, r13
0x1800c6af0  sub     rdx, r12
0x1800c6af3  jnz     short loc_1800C6AE7
0x1800c6af5  mov     rax, rdx
0x1800c6af8  neg     rax
0x1800c6afb  sbb     r9d, r9d
0x1800c6afe  not     r9d
0x1800c6b01  and     r9d, 0C000000Dh; char *
0x1800c6b08  test    rdx, rdx
0x1800c6b0b  jz      short loc_1800C6B2D
0x1800c6b0d  movzx   eax, dx
0x1800c6b10  add     ax, ax
0x1800c6b13  mov     ecx, 0FFFEh
0x1800c6b18  sub     cx, ax
0x1800c6b1b  mov     word ptr [rsp+940h+var_8C8], cx
0x1800c6b20  add     cx, r13w
0x1800c6b24  mov     word ptr [rsp+940h+var_8C8+2], cx
0x1800c6b29  mov     qword ptr [rbp+840h+var_8C8+8], r8
0x1800c6b2d  mov     rcx, [rbp+848h]; this
0x1800c6b34  test    rdx, rdx
0x1800c6b37  jz      loc_1800C73B0
0x1800c6b3d  lea     r8, [rbp+840h+Sid]
0x1800c6b41  lea     rdx, [rbp+840h+var_880]
0x1800c6b45  lea     rcx, [rsp+940h+var_8C8]
0x1800c6b4a  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800c6b50  mov     rcx, [rbp+848h]; this
0x1800c6b57  test    eax, eax
0x1800c6b59  js      loc_1800C73C2
0x1800c6b5f  mov     [rsp+940h+hMem], r15
0x1800c6b64  lea     rax, [rsp+940h+hMem]
0x1800c6b69  mov     qword ptr [rsp+940h+var_920], rax; int
0x1800c6b6e  mov     [rsp+940h+StringSid], r15
0x1800c6b73  mov     [rsp+940h+var_910], r12b
0x1800c6b78  lea     rdx, [rsp+940h+StringSid]; StringSid
0x1800c6b7d  lea     rcx, [rbp+840h+Sid]; Sid
0x1800c6b81  call    cs:__imp_ConvertSidToStringSidW
0x1800c6b87  mov     rcx, [rbp+848h]; this
0x1800c6b8e  test    eax, eax
0x1800c6b90  jz      loc_1800C73D7
0x1800c6b96  cmp     [rsp+940h+var_910], r15b
0x1800c6b9b  jnz     loc_1800C73E9
0x1800c6ba1  mov     esi, 7FFFFFFEh
0x1800c6ba6  mov     eax, esi
0x1800c6ba8  lea     rcx, aDAi; "D:AI"
0x1800c6baf  mov     ebx, 400h
0x1800c6bb4  mov     edx, ebx
0x1800c6bb6  lea     r8, [rbp+840h+StringSecurityDescriptor]
0x1800c6bba  test    rax, rax
0x1800c6bbd  jz      short loc_1800C6BDB
0x1800c6bbf  movzx   r9d, word ptr [rcx]
0x1800c6bc3  test    r9w, r9w
0x1800c6bc7  jz      short loc_1800C6BDB
0x1800c6bc9  add     rcx, r13
0x1800c6bcc  mov     [r8], r9w
0x1800c6bd0  add     r8, r13
0x1800c6bd3  sub     rax, r12
0x1800c6bd6  sub     rdx, r12
0x1800c6bd9  jnz     short loc_1800C6BBA
0x1800c6bdb  mov     rax, rdx
0x1800c6bde  neg     rax
0x1800c6be1  sbb     r9d, r9d
0x1800c6be4  not     r9d
0x1800c6be7  mov     r10d, 8007007Ah
0x1800c6bed  and     r9d, r10d; char *
0x1800c6bf0  lea     rcx, [r8-2]
0x1800c6bf4  test    rdx, rdx
0x1800c6bf7  cmovnz  rcx, r8
0x1800c6bfb  mov     [rcx], r15w
0x1800c6bff  mov     rcx, [rbp+848h]; this
0x1800c6c06  jz      loc_1800C7288
0x1800c6c0c  mov     rdx, rbx
0x1800c6c0f  lea     rax, [rbp+840h+StringSecurityDescriptor]
0x1800c6c13  cmp     [rax], r15w
0x1800c6c17  jz      short loc_1800C6C21
0x1800c6c19  add     rax, r13
0x1800c6c1c  sub     rdx, r12
0x1800c6c1f  jnz     short loc_1800C6C13
0x1800c6c21  mov     rax, rdx
0x1800c6c24  neg     rax
0x1800c6c27  sbb     r9d, r9d
0x1800c6c2a  not     r9d
0x1800c6c2d  mov     edi, 80070057h
0x1800c6c32  and     r9d, edi
0x1800c6c35  mov     rax, rdx
0x1800c6c38  mov     rcx, rbx
0x1800c6c3b  sub     rcx, rdx
0x1800c6c3e  neg     rax
0x1800c6c41  sbb     r8, r8
0x1800c6c44  and     r8, rcx
0x1800c6c47  test    rdx, rdx
0x1800c6c4a  jz      short loc_1800C6CA2
0x1800c6c4c  mov     rcx, rsi
0x1800c6c4f  lea     r9, aACiKa; "(A;CI;KA;;;"
0x1800c6c56  mov     rdx, rbx
0x1800c6c59  sub     rdx, r8
0x1800c6c5c  lea     rax, [rbp+840h+StringSecurityDescriptor]
0x1800c6c60  lea     rax, [rax+r8*2]
0x1800c6c64  jz      short loc_1800C6C87
0x1800c6c66  test    rcx, rcx
0x1800c6c69  jz      short loc_1800C6C87
0x1800c6c6b  movzx   r8d, word ptr [r9]
0x1800c6c6f  test    r8w, r8w
0x1800c6c73  jz      short loc_1800C6C87
0x1800c6c75  add     r9, r13
0x1800c6c78  mov     [rax], r8w
0x1800c6c7c  add     rax, r13
0x1800c6c7f  sub     rcx, r12
0x1800c6c82  sub     rdx, r12
0x1800c6c85  jnz     short loc_1800C6C66
0x1800c6c87  lea     rcx, [rax-2]
0x1800c6c8b  test    rdx, rdx
0x1800c6c8e  cmovnz  rcx, rax
0x1800c6c92  mov     [rcx], r15w
0x1800c6c96  neg     rdx
0x1800c6c99  sbb     r9d, r9d
0x1800c6c9c  not     r9d
0x1800c6c9f  and     r9d, r10d; char *
0x1800c6ca2  mov     rcx, [rbp+848h]; this
0x1800c6ca9  test    r9d, r9d
0x1800c6cac  js      loc_1800C729A
0x1800c6cb2  mov     r8, [rsp+940h+hMem]; unsigned __int16 *
0x1800c6cb7  mov     rdx, rbx; unsigned __int64
0x1800c6cba  lea     rcx, [rbp+840h+StringSecurityDescriptor]; unsigned __int16 *
0x1800c6cbe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c6cc3  mov     rcx, [rbp+848h]; this
0x1800c6cca  test    eax, eax
0x1800c6ccc  js      loc_1800C72AC
0x1800c6cd2  mov     rdx, rbx
0x1800c6cd5  lea     rax, [rbp+840h+StringSecurityDescriptor]
0x1800c6cd9  cmp     [rax], r15w
0x1800c6cdd  jz      short loc_1800C6CE7
0x1800c6cdf  add     rax, r13
0x1800c6ce2  sub     rdx, r12
0x1800c6ce5  jnz     short loc_1800C6CD9
0x1800c6ce7  mov     rax, rdx
0x1800c6cea  neg     rax
0x1800c6ced  sbb     r9d, r9d
0x1800c6cf0  not     r9d
0x1800c6cf3  and     r9d, edi
0x1800c6cf6  mov     rax, rdx
0x1800c6cf9  mov     rcx, rbx
0x1800c6cfc  sub     rcx, rdx
0x1800c6cff  neg     rax
0x1800c6d02  sbb     r8, r8
0x1800c6d05  and     r8, rcx
0x1800c6d08  lea     rdi, asc_1807719AC; ")"
0x1800c6d0f  test    rdx, rdx
0x1800c6d12  jz      short loc_1800C6D6A
0x1800c6d14  mov     rcx, rsi
0x1800c6d17  mov     r9, rdi
0x1800c6d1a  mov     rdx, rbx
0x1800c6d1d  sub     rdx, r8
0x1800c6d20  lea     rax, [rbp+840h+StringSecurityDescriptor]
0x1800c6d24  lea     rax, [rax+r8*2]
0x1800c6d28  jz      short loc_1800C6D4B
0x1800c6d2a  test    rcx, rcx
0x1800c6d2d  jz      short loc_1800C6D4B
0x1800c6d2f  movzx   r8d, word ptr [r9]
0x1800c6d33  test    r8w, r8w
0x1800c6d37  jz      short loc_1800C6D4B
0x1800c6d39  add     r9, r13
0x1800c6d3c  mov     [rax], r8w
0x1800c6d40  add     rax, r13
0x1800c6d43  sub     rcx, r12
0x1800c6d46  sub     rdx, r12
0x1800c6d49  jnz     short loc_1800C6D2A
0x1800c6d4b  lea     rcx, [rax-2]
0x1800c6d4f  test    rdx, rdx
0x1800c6d52  cmovnz  rcx, rax
0x1800c6d56  mov     [rcx], r15w
0x1800c6d5a  neg     rdx
0x1800c6d5d  sbb     r9d, r9d
0x1800c6d60  not     r9d
0x1800c6d63  and     r9d, 8007007Ah; char *
0x1800c6d6a  mov     rcx, [rbp+848h]; this
0x1800c6d71  test    r9d, r9d
0x1800c6d74  js      loc_1800C72C1
0x1800c6d7a  mov     rdx, rbx
0x1800c6d7d  lea     rax, [rbp+840h+StringSecurityDescriptor]
0x1800c6d81  cmp     [rax], r15w
0x1800c6d85  jz      short loc_1800C6D8F
0x1800c6d87  add     rax, r13
0x1800c6d8a  sub     rdx, r12
0x1800c6d8d  jnz     short loc_1800C6D81
0x1800c6d8f  mov     rax, rdx
0x1800c6d92  neg     rax
0x1800c6d95  sbb     r9d, r9d
0x1800c6d98  not     r9d
0x1800c6d9b  and     r9d, 80070057h
0x1800c6da2  mov     rax, rdx
0x1800c6da5  mov     rcx, rbx
0x1800c6da8  sub     rcx, rdx
0x1800c6dab  neg     rax
0x1800c6dae  sbb     r8, r8
0x1800c6db1  and     r8, rcx
0x1800c6db4  test    rdx, rdx
0x1800c6db7  jz      short loc_1800C6E13
0x1800c6db9  mov     rcx, rsi
0x1800c6dbc  lea     r9, aAOiciidKa; "(A;OICIID;KA;;;"
0x1800c6dc3  mov     rdx, rbx
0x1800c6dc6  sub     rdx, r8
0x1800c6dc9  lea     rax, [rbp+840h+StringSecurityDescriptor]
0x1800c6dcd  lea     rax, [rax+r8*2]
0x1800c6dd1  jz      short loc_1800C6DF4
0x1800c6dd3  test    rcx, rcx
0x1800c6dd6  jz      short loc_1800C6DF4
0x1800c6dd8  movzx   r8d, word ptr [r9]
0x1800c6ddc  test    r8w, r8w
0x1800c6de0  jz      short loc_1800C6DF4
0x1800c6de2  add     r9, r13
0x1800c6de5  mov     [rax], r8w
0x1800c6de9  add     rax, r13
0x1800c6dec  sub     rcx, r12
0x1800c6def  sub     rdx, r12
0x1800c6df2  jnz     short loc_1800C6DD3
0x1800c6df4  lea     rcx, [rax-2]
0x1800c6df8  test    rdx, rdx
0x1800c6dfb  cmovnz  rcx, rax
0x1800c6dff  mov     [rcx], r15w
0x1800c6e03  neg     rdx
0x1800c6e06  sbb     r9d, r9d
0x1800c6e09  not     r9d
0x1800c6e0c  and     r9d, 8007007Ah; char *
0x1800c6e13  mov     rcx, [rbp+848h]; this
0x1800c6e1a  test    r9d, r9d
0x1800c6e1d  js      loc_1800C72D3
0x1800c6e23  mov     [rsp+940h+hObject], r15
0x1800c6e28  lea     rax, [rsp+940h+hObject]
0x1800c6e2d  mov     qword ptr [rsp+940h+var_920], rax; int
0x1800c6e32  mov     [rsp+940h+StringSid], r15
0x1800c6e37  mov     [rsp+940h+var_910], r12b
0x1800c6e3c  call    cs:__imp_GetCurrentThread
0x1800c6e42  mov     rcx, rax; ThreadHandle
0x1800c6e45  lea     r9, [rsp+940h+StringSid]; TokenHandle
0x1800c6e4a  xor     r8d, r8d; OpenAsSelf
0x1800c6e4d  lea     edx, [r8+8]; DesiredAccess
0x1800c6e51  call    cs:__imp_OpenThreadToken
0x1800c6e57  test    eax, eax
0x1800c6e59  jz      loc_1800C7357
0x1800c6e5f  mov     eax, r15d
0x1800c6e62  mov     rcx, [rbp+848h]; this
0x1800c6e69  test    eax, eax
0x1800c6e6b  js      loc_1800C72E5
0x1800c6e71  cmp     [rsp+940h+var_910], r15b
0x1800c6e76  jnz     loc_1800C73FD
0x1800c6e7c  mov     rdx, [rsp+940h+hObject]
0x1800c6e81  lea     rcx, [rsp+940h+Block]
0x1800c6e86  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x1800c6e8b  nop
0x1800c6e8c  mov     [rsp+940h+var_900], r15
0x1800c6e91  lea     rax, [rsp+940h+var_900]
0x1800c6e96  mov     qword ptr [rsp+940h+var_920], rax; int
0x1800c6e9b  mov     [rsp+940h+StringSid], r15
0x1800c6ea0  mov     [rsp+940h+var_910], r12b
0x1800c6ea5  lea     rdx, [rsp+940h+StringSid]; StringSid
0x1800c6eaa  mov     rcx, [rsp+940h+Block]
0x1800c6eaf  mov     rcx, [rcx]; Sid
0x1800c6eb2  call    cs:__imp_ConvertSidToStringSidW
0x1800c6eb8  test    eax, eax
0x1800c6eba  jz      loc_1800C7411
0x1800c6ec0  cmp     [rsp+940h+var_910], r15b
0x1800c6ec5  jnz     loc_1800C742A
0x1800c6ecb  mov     r8, [rsp+940h+var_900]; unsigned __int16 *
0x1800c6ed0  mov     rdx, rbx; unsigned __int64
0x1800c6ed3  lea     rcx, [rbp+840h+StringSecurityDescriptor]; unsigned __int16 *
0x1800c6ed7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800c6edc  mov     rcx, [rbp+848h]; this
0x1800c6ee3  test    eax, eax
0x1800c6ee5  js      loc_1800C72FA
0x1800c6eeb  mov     rcx, [rsp+940h+var_900]; hMem
0x1800c6ef0  test    rcx, rcx
0x1800c6ef3  jnz     loc_1800C7271
0x1800c6ef9  mov     rcx, [rsp+940h+Block]; Block
0x1800c6efe  mov     [rsp+940h+Block], r15
0x1800c6f03  test    rcx, rcx
  ... truncated ...
```
