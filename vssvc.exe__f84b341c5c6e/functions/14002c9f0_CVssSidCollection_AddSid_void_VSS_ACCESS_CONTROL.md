# CVssSidCollection::AddSid(void *,VSS_ACCESS_CONTROL)

- ea: `0x14002c9f0`
- end: `0x14002d6cd`
- name: `?AddSid@CVssSidCollection@@AEAAXPEAXW4VSS_ACCESS_CONTROL@@@Z`
- size: `3293`
- prototype: `__int64 __fastcall(__int64, void *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002c470`
- `0x14002dc90`

## callees

- `0x14000e640`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140015e38`
- `0x14002c9f0`
- `0x14003a8f0`
- `0x140049ec4`
- `0x14005a9a8`
- `0x140091560`
- `0x140091584`
- `0x1400919a0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cf0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002cf0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d07f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d432`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d479`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002cc02`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002cec4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002d03d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002cc02`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002cec4`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14002d03d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14002cb5a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14002cb5a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002cc80`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002cf3e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002d0b2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002cc80`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002cf3e`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14002d0b2`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ce50`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002cfbd`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002d16d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002ce50`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002cfbd`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x14002d16d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002ccb2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002cf70`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002d0e7`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002ccb2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002cf70`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14002d0e7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002cbce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002ce90`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002d006`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002cbce`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002ce90`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14002d006`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002ce26`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002cf93`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002d143`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002ce26`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002cf93`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x14002d143`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cbc5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cc3f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002ce87`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cf01`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cffd`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002d071`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cbc5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cc3f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002ce87`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cf01`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002cffd`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14002d071`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002cab2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002ccf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002cab2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002ccf3`
- `VssTrace!__imp_VssTraceMessage` at `0x14002d4c3`
- `VssTrace!__imp_VssTraceMessage` at `0x14002d4c3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002cdac`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002cdf0`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002cdac`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002cdf0`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002caeb`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002caeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ccbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ccdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ccbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cccd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ccdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002cddc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002d55d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002d55d`

## string_xrefs

- `0x14002ca29`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002cb7c`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002d1ea`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002d262`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002d38b`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002d4ce`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002d563`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002ca35`: `CVssSidCollection::AddSid`
- `0x14002d1f6`: `CVssSidCollection::AddSid`
- `0x14002d26e`: `CVssSidCollection::AddSid`
- `0x14002d31f`: `CVssSidCollection::AddSid`
- `0x14002d397`: `CVssSidCollection::AddSid`
- `0x14002d4da`: `CVssSidCollection::AddSid`
- `0x14002d573`: `CVssSidCollection::AddSid`
- `0x14002d5e7`: `CVssSidCollection::AddSid`
- `0x14002d64d`: `CVssSidCollection::AddSid`
- `0x14002d2b6`: `m_SDWriters.Allow(...)`
- `0x14002d522`: `Invalid SID passed to AddSid`
- `0x14002d5bf`: `Adding SID %s ...`
- `0x14002d695`: `m_SDWriters.Deny(...)`

## pseudocode

```c
__int64 __fastcall CVssSidCollection::AddSid(__int64 a1, void *a2, int a3)
{
  _DWORD *v6; // rax
  unsigned int v7; // r13d
  unsigned int v8; // ebx
  __int64 i; // rbx
  void *v10; // rcx
  unsigned int v11; // r8d
  unsigned int v12; // r9d
  struct _ACL *v13; // rdi
  DWORD v14; // eax
  signed int v15; // ebx
  struct _ACL *v16; // rax
  struct _ACL *v17; // rsi
  signed int v18; // eax
  signed int v19; // ebx
  DWORD v20; // esi
  DWORD j; // ebx
  struct _ACL *v23; // rdi
  DWORD LengthSid; // eax
  signed int v25; // ebx
  struct _ACL *v26; // rax
  struct _ACL *v27; // rsi
  signed int v28; // eax
  signed int v29; // ebx
  DWORD k; // ebx
  struct _ACL *v31; // rsi
  DWORD v32; // eax
  signed int v33; // ebx
  struct _ACL *v34; // rax
  struct _ACL *v35; // r12
  signed int v36; // eax
  signed int v37; // ebx
  signed int v38; // eax
  DWORD m; // ebx
  signed int LastError; // eax
  signed int v41; // eax
  int v42; // ebx
  unsigned int v43; // r8d
  unsigned int v44; // r9d
  int v45; // ebx
  unsigned int v46; // r8d
  unsigned int v47; // r9d
  int v48; // ebx
  PSID pSid; // [rsp+20h] [rbp-E0h]
  __int64 v50; // [rsp+28h] [rbp-D8h]
  __int64 v51; // [rsp+30h] [rbp-D0h]
  __int64 v52; // [rsp+38h] [rbp-C8h]
  __int64 v53; // [rsp+40h] [rbp-C0h]
  LPVOID pAce; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v55; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v56; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v57; // [rsp+68h] [rbp-98h]
  int v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+74h] [rbp-8Ch]
  int v60; // [rsp+78h] [rbp-88h]
  LPVOID v61[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v62; // [rsp+90h] [rbp-70h]
  __int128 v63; // [rsp+A0h] [rbp-60h]
  __int128 v64; // [rsp+B0h] [rbp-50h]
  __int128 v65; // [rsp+C0h] [rbp-40h]
  __int128 v66; // [rsp+D0h] [rbp-30h]
  __int128 v67; // [rsp+E0h] [rbp-20h]
  __int64 v68; // [rsp+F0h] [rbp-10h]
  int v69; // [rsp+F8h] [rbp-8h]
  _DWORD v70[2]; // [rsp+100h] [rbp+0h] BYREF
  signed int v71; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v72; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v73; // [rsp+118h] [rbp+18h]
  unsigned int v74; // [rsp+120h] [rbp+20h]
  unsigned int v75; // [rsp+124h] [rbp+24h]
  const wchar_t *v76; // [rsp+128h] [rbp+28h]
  unsigned int v77; // [rsp+130h] [rbp+30h]
  DWORD TickCount; // [rsp+134h] [rbp+34h]
  unsigned int v79; // [rsp+138h] [rbp+38h]
  LPVOID pv[2]; // [rsp+140h] [rbp+40h]
  LPVOID v81[2]; // [rsp+150h] [rbp+50h]
  _DWORD *v82; // [rsp+160h] [rbp+60h]
  void **pAclInformation; // [rsp+170h] [rbp+70h] BYREF
  LPWSTR StringSid; // [rsp+178h] [rbp+78h] BYREF
  __int64 v85; // [rsp+180h] [rbp+80h] BYREF
  int v86; // [rsp+188h] [rbp+88h]

  v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v56 = L"CVssSidCollection::AddSid";
  v57 = L"SECSECRC";
  v58 = 1456;
  v59 = 11;
  v60 = 255;
  v69 = 0x1000000;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v71 = 0;
  v76 = L"CVssSidCollection::AddSid";
  v72 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v73 = L"SECSECRC";
  v74 = 1456;
  v75 = 11;
  TickCount = GetTickCount();
  v70[1] = -1;
  v79 = 255;
  v70[0] = 0;
  v82 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v81 = 0;
  pAce = 0;
  if ( (int)VssGetTracingContextPerThread(&pAce) < 0 || (int)VssSetTracingContextPerThread(v70) < 0 )
  {
    v6 = v82;
  }
  else
  {
    v6 = pAce;
    v82 = pAce;
  }
  if ( v6 )
    v77 = v6[12] + 1;
  else
    v77 = 0;
  v7 = 160;
  v8 = 160;
  if ( v79 != 255 )
    v8 = v79;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v70, v75) )
    VssTraceMessage(v72, v73, v74, v77, v75, v76, L"ENTER", v8, 0);
  for ( i = 0; i != 15; ++i )
  {
    v10 = v61[i];
    if ( v10 )
    {
      CoTaskMemFree(v10);
      v61[i] = 0;
    }
  }
  if ( !IsValidSid(a2) )
  {
    v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v56 = L"CVssSidCollection::AddSid";
    v57 = L"SECSECRC";
    v58 = 1464;
    v59 = 11;
    v60 = 255;
    v69 = 0x1000000;
    memset_0(v61, 0, 0x78u);
    CVssFunctionTracer::Throw(v70, &v55, 2147549183LL, L"Invalid SID passed to AddSid");
  }
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v70, v75) )
  {
    StringSid = 0;
    pAclInformation = &CVssAutoLocalPtr<unsigned short *>::`vftable';
    CVssAutoGenericValue_Storage<unsigned short *,0,void * (*)(void *),&void * LocalFree(void *),unsigned short * & (*)(unsigned short * &),&public: static unsigned short * & DTyper<unsigned short *>::Identity(unsigned short * &)>::Close(&pAclInformation);
    if ( ConvertSidToStringSidW(a2, &StringSid) )
    {
      v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v56 = L"CVssSidCollection::AddSid";
      v57 = L"SECSECRC";
      v58 = 1475;
      v59 = 11;
      v60 = 255;
      v69 = 0x1000000;
      memset_0(v61, 0, 0x78u);
      CVssFunctionTracer::Trace(v70, &v55, L"Adding SID %s ...", StringSid);
    }
    CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&pAclInformation);
  }
  if ( a3 )
  {
    if ( (unsigned int)(a3 - 2) > 1 )
    {
LABEL_17:
      if ( a3 != 1 )
        goto LABEL_18;
LABEL_42:
      pAclInformation = 0;
      LODWORD(StringSid) = 0;
      v23 = *(struct _ACL **)(a1 + 32);
      if ( v23 )
        GetAclInformation(*(PACL *)(a1 + 32), &pAclInformation, 0xCu, AclSizeInformation);
      LengthSid = GetLengthSid(a2);
      v25 = LengthSid + HIDWORD(pAclInformation) + 16;
      v26 = (struct _ACL *)operator new[](v25, (const struct std::nothrow_t *)&std::nothrow);
      v27 = v26;
      if ( !v26 )
      {
        v29 = -2147024882;
        goto LABEL_97;
      }
      if ( !InitializeAcl(v26, v25, 2u) )
      {
        operator delete(v27);
        LastError = GetLastError();
        v29 = LastError;
        if ( LastError <= 0 )
        {
LABEL_87:
          if ( v29 >= 0 )
          {
LABEL_55:
            SetSecurityDescriptorDacl(*(PSECURITY_DESCRIPTOR *)(a1 + 8), 1, *(PACL *)(a1 + 32), 0);
            v71 = v29;
LABEL_18:
            pAclInformation = 0;
            LODWORD(StringSid) = 0;
            v13 = *(struct _ACL **)(a1 + 96);
            if ( v13 )
              GetAclInformation(*(PACL *)(a1 + 96), &pAclInformation, 0xCu, AclSizeInformation);
            v14 = GetLengthSid(a2);
            v15 = v14 + HIDWORD(pAclInformation) + 16;
            v16 = (struct _ACL *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
            v17 = v16;
            if ( !v16 )
            {
              v19 = -2147024882;
              goto LABEL_95;
            }
            if ( !InitializeAcl(v16, v15, 2u) )
            {
              operator delete(v17);
              v38 = GetLastError();
              v19 = v38;
              if ( v38 <= 0 )
              {
LABEL_78:
                if ( v19 >= 0 )
                {
LABEL_31:
                  SetSecurityDescriptorDacl(*(PSECURITY_DESCRIPTOR *)(a1 + 72), 1, *(PACL *)(a1 + 96), 0);
                  v71 = v19;
                  goto LABEL_32;
                }
LABEL_95:
                v71 = v19;
                v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
                v56 = L"CVssSidCollection::AddSid";
                v57 = L"SECSECRC";
                v58 = 1547;
                v59 = 11;
                v60 = 255;
                v69 = 0x1000000;
                memset_0(v61, 0, 0x78u);
                CVssFunctionTracer::TranslateGenericError(v70, &v55, (unsigned int)v19, L"m_SDBoth.Allow(...)");
              }
LABEL_77:
              v19 = (unsigned __int16)v38 | 0x80070000;
              goto LABEL_78;
            }
            v85 = 0;
            v86 = 0;
            pAce = 0;
            if ( !v13 )
            {
LABEL_27:
              if ( AddAccessAllowedAceEx(v17, 2u, 0, 1u, a2) )
              {
                *(_QWORD *)(a1 + 96) = v17;
                if ( v13 )
                  operator delete(v13);
                v19 = 0;
                goto LABEL_31;
              }
              operator delete(v17);
              v38 = GetLastError();
              v19 = v38;
              if ( v38 <= 0 )
                goto LABEL_78;
              goto LABEL_77;
            }
            if ( GetAclInformation(v13, &v85, 0xCu, AclSizeInformation) )
            {
              for ( j = 0; ; ++j )
              {
                if ( j >= (unsigned int)v85 )
                  goto LABEL_27;
                if ( !GetAce(v13, j, &pAce) )
                  goto LABEL_24;
                if ( !AddAce(v17, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
                  break;
              }
              v18 = GetLastError();
              v19 = v18;
              if ( v18 <= 0 )
              {
LABEL_26:
                if ( v19 < 0 )
                {
                  operator delete(v17);
                  goto LABEL_95;
                }
                goto LABEL_27;
              }
            }
            else
            {
LABEL_24:
              v18 = GetLastError();
              v19 = v18;
              if ( v18 <= 0 )
                goto LABEL_26;
            }
            v19 = (unsigned __int16)v18 | 0x80070000;
            goto LABEL_26;
          }
LABEL_97:
          v71 = v29;
          v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
          v56 = L"CVssSidCollection::AddSid";
          v57 = L"SECSECRC";
          v58 = 1536;
          v59 = 11;
          v60 = 255;
          v69 = 0x1000000;
          memset_0(v61, 0, 0x78u);
          CVssFunctionTracer::TranslateGenericError(v70, &v55, (unsigned int)v29, L"m_SDWriters.Allow(...)");
        }
LABEL_86:
        v29 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_87;
      }
      v85 = 0;
      v86 = 0;
      pAce = 0;
      if ( !v23 )
      {
LABEL_51:
        if ( AddAccessAllowedAceEx(v27, 2u, 0, 1u, a2) )
        {
          *(_QWORD *)(a1 + 32) = v27;
          if ( v23 )
            operator delete(v23);
          v29 = 0;
          goto LABEL_55;
        }
        operator delete(v27);
        LastError = GetLastError();
        v29 = LastError;
        if ( LastError <= 0 )
          goto LABEL_87;
        goto LABEL_86;
      }
      if ( GetAclInformation(v23, &v85, 0xCu, AclSizeInformation) )
      {
        for ( k = 0; ; ++k )
        {
          if ( k >= (unsigned int)v85 )
            goto LABEL_51;
          if ( !GetAce(v23, k, &pAce) )
            goto LABEL_48;
          if ( !AddAce(v27, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
            break;
        }
        v28 = GetLastError();
        v29 = v28;
        if ( v28 <= 0 )
        {
LABEL_50:
          if ( v29 < 0 )
          {
            operator delete(v27);
            goto LABEL_97;
          }
          goto LABEL_51;
        }
      }
      else
      {
LABEL_48:
        v28 = GetLastError();
        v29 = v28;
        if ( v28 <= 0 )
          goto LABEL_50;
      }
      v29 = (unsigned __int16)v28 | 0x80070000;
      goto LABEL_50;
    }
    v85 = 0;
    v86 = 0;
    v31 = *(struct _ACL **)(a1 + 64);
    if ( v31 )
      GetAclInformation(*(PACL *)(a1 + 64), &v85, 0xCu, AclSizeInformation);
    v32 = GetLengthSid(a2);
    v33 = v32 + HIDWORD(v85) + 16;
    v34 = (struct _ACL *)operator new[](v33, (const struct std::nothrow_t *)&std::nothrow);
    v35 = v34;
    if ( !v34 )
    {
      v37 = -2147024882;
      goto LABEL_103;
    }
    if ( !InitializeAcl(v34, v33, 2u) )
    {
      operator delete(v35);
      v41 = GetLastError();
      v37 = v41;
      if ( v41 <= 0 )
      {
LABEL_92:
        if ( v37 >= 0 )
          goto LABEL_74;
LABEL_103:
        v71 = v37;
        v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v56 = L"CVssSidCollection::AddSid";
        v57 = L"SECSECRC";
        v58 = 1523;
        v59 = 11;
        v60 = 255;
        v69 = 0x1000000;
        memset_0(v61, 0, 0x78u);
        CVssFunctionTracer::TranslateGenericError(v70, &v55, (unsigned int)v37, L"m_SDRequestors.Allow(...)");
      }
LABEL_91:
      v37 = (unsigned __int16)v41 | 0x80070000;
      goto LABEL_92;
    }
    pAclInformation = 0;
    LODWORD(StringSid) = 0;
    pAce = 0;
    if ( !v31 )
    {
LABEL_70:
      if ( AddAccessAllowedAceEx(v35, 2u, 0, 1u, a2) )
      {
        *(_QWORD *)(a1 + 64) = v35;
        if ( v31 )
          operator delete(v31);
        v37 = 0;
LABEL_74:
        SetSecurityDescriptorDacl(*(PSECURITY_DESCRIPTOR *)(a1 + 40), 1, *(PACL *)(a1 + 64), 0);
        v71 = v37;
        if ( a3 == 3 )
          goto LABEL_42;
        goto LABEL_17;
      }
      operator delete(v35);
      v41 = GetLastError();
      v37 = v41;
      if ( v41 <= 0 )
        goto LABEL_92;
      goto LABEL_91;
    }
    if ( GetAclInformation(v31, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      for ( m = 0; ; ++m )
      {
        if ( m >= (unsigned int)pAclInformation )
          goto LABEL_70;
        if ( !GetAce(v31, m, &pAce) )
          goto LABEL_67;
        if ( !AddAce(v35, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
          break;
      }
      v36 = GetLastError();
      v37 = v36;
      if ( v36 <= 0 )
      {
LABEL_69:
        if ( v37 < 0 )
        {
          operator delete(v35);
          goto LABEL_103;
        }
        goto LABEL_70;
      }
    }
    else
    {
LABEL_67:
      v36 = GetLastError();
      v37 = v36;
      if ( v36 <= 0 )
        goto LABEL_69;
    }
    v37 = (unsigned __int16)v36 | 0x80070000;
    goto LABEL_69;
  }
  v42 = CVssSecurityDescriptor::Deny((CVssSecurityDescriptor *)(a1 + 40), a2, v11, v12);
  v71 = v42;
  if ( v42 < 0 )
  {
    v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v56 = L"CVssSidCollection::AddSid";
    v57 = L"SECSECRC";
    v58 = 1489;
    v59 = 11;
    v60 = 255;
    v69 = 0x1000000;
    memset_0(v61, 0, 0x78u);
    CVssFunctionTracer::TranslateGenericError(v70, &v55, (unsigned int)v42, L"m_SDRequestors.Deny(...)");
  }
  v45 = CVssSecurityDescriptor::Deny((CVssSecurityDescriptor *)(a1 + 8), a2, v43, v44);
  v71 = v45;
  if ( v45 < 0 )
  {
    v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v56 = L"CVssSidCollection::AddSid";
    v57 = L"SECSECRC";
    v58 = 1499;
    v59 = 11;
    v60 = 255;
    v69 = 0x1000000;
    memset_0(v61, 0, 0x78u);
    CVssFunctionTracer::TranslateGenericError(v70, &v55, (unsigned int)v45, L"m_SDWriters.Deny(...)");
  }
  v48 = CVssSecurityDescriptor::Deny((CVssSecurityDescriptor *)(a1 + 72), a2, v46, v47);
  v71 = v48;
  if ( v48 < 0 )
  {
    v55 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v56 = L"CVssSidCollection::AddSid";
    v57 = L"SECSECRC";
    v58 = 1509;
    v59 = 11;
    v60 = 255;
    v69 = 0x1000000;
    memset_0(v61, 0, 0x78u);
    CVssFunctionTracer::TranslateGenericError(v70, &v55, (unsigned int)v48, L"m_SDBoth.Deny(...)");
  }
LABEL_32:
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v81[0]);
  v81[0] = 0;
  CoTaskMemFree(v81[1]);
  v81[1] = 0;
  v20 = GetTickCount() - TickCount;
  if ( v79 != 255 )
    v7 = v79;
  LODWORD(v53) = v20;
  LODWORD(v52) = v20 % 0x3E8;
  LODWORD(v51) = v20 / 0x3E8 % 0x3C;
  LODWORD(v50) = v20 / 0xEA60 % 0x3C;
  LODWORD(pSid) = v20 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v70,
    L"EXIT",
    v7,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    pSid,
    v50,
    v51,
    v52,
    v53,
    v71);
  return VssSetTracingContextPerThread(v82);
}

```

## disassembly

```asm
0x14002c9f0  mov     [rsp-8+arg_10], rbx
0x14002c9f5  push    rbp
0x14002c9f6  push    rsi
0x14002c9f7  push    rdi
0x14002c9f8  push    r12
0x14002c9fa  push    r13
0x14002c9fc  push    r14
0x14002c9fe  push    r15
0x14002ca00  lea     rbp, [rsp-0A0h]
0x14002ca08  sub     rsp, 1A0h
0x14002ca0f  mov     rax, cs:__security_cookie
0x14002ca16  xor     rax, rsp
0x14002ca19  mov     [rbp+0D0h+var_40], rax
0x14002ca20  mov     edi, r8d
0x14002ca23  mov     r15, rdx
0x14002ca26  mov     r14, rcx
0x14002ca29  lea     rcx, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002ca30  mov     [rsp+1D0h+var_178], rcx
0x14002ca35  lea     rdx, aCvsssidcollect_3; "CVssSidCollection::AddSid"
0x14002ca3c  mov     [rsp+1D0h+var_170], rdx
0x14002ca41  lea     r8, aSecsecrc; "SECSECRC"
0x14002ca48  mov     [rsp+1D0h+var_168], r8
0x14002ca4d  mov     [rsp+1D0h+var_160], 5B0h
0x14002ca55  mov     [rsp+1D0h+var_15C], 0Bh
0x14002ca5d  mov     [rsp+1D0h+var_158], 0FFh
0x14002ca65  xor     r12d, r12d
0x14002ca68  mov     [rbp+0D0h+var_D8], 1000000h
0x14002ca6f  xorps   xmm0, xmm0
0x14002ca72  xor     eax, eax
0x14002ca74  movups  xmmword ptr [rbp+0D0h+var_150], xmm0
0x14002ca78  movups  [rbp+0D0h+var_140], xmm0
0x14002ca7c  movups  [rbp+0D0h+var_130], xmm0
0x14002ca80  movups  [rbp+0D0h+var_120], xmm0
0x14002ca84  movups  [rbp+0D0h+var_110], xmm0
0x14002ca88  movups  [rbp+0D0h+var_100], xmm0
0x14002ca8c  movups  [rbp+0D0h+var_F0], xmm0
0x14002ca90  mov     [rbp+0D0h+var_E0], rax
0x14002ca94  mov     [rbp+0D0h+var_C8], r12d
0x14002ca98  mov     [rbp+0D0h+var_A8], rdx
0x14002ca9c  mov     [rbp+0D0h+var_C0], rcx
0x14002caa0  mov     [rbp+0D0h+var_B8], r8
0x14002caa4  mov     [rbp+0D0h+var_B0], 5B0h
0x14002caab  mov     [rbp+0D0h+var_AC], 0Bh
0x14002cab2  call    cs:__imp_GetTickCount
0x14002cab8  mov     [rbp+0D0h+var_9C], eax
0x14002cabb  mov     [rbp+0D0h+var_CC], 0FFFFFFFFh
0x14002cac2  mov     [rbp+0D0h+var_98], 0FFh
0x14002cac9  mov     [rbp+0D0h+var_D0], r12d
0x14002cacd  mov     [rbp+0D0h+var_70], r12
0x14002cad1  xorps   xmm0, xmm0
0x14002cad4  movdqa  xmmword ptr [rbp+0D0h+pv], xmm0
0x14002cad9  xorps   xmm1, xmm1
0x14002cadc  movdqa  xmmword ptr [rbp+0D0h+var_80], xmm1
0x14002cae1  mov     [rsp+1D0h+pAce], r12
0x14002cae6  lea     rcx, [rsp+1D0h+pAce]
0x14002caeb  call    cs:__imp_VssGetTracingContextPerThread
0x14002caf1  test    eax, eax
0x14002caf3  jns     loc_14002CDEC
0x14002caf9  mov     rax, [rbp+0D0h+var_70]
0x14002cafd  test    rax, rax
0x14002cb00  jz      loc_14002D1A9
0x14002cb06  mov     eax, [rax+30h]
0x14002cb09  inc     eax
0x14002cb0b  mov     [rbp+0D0h+var_A0], eax
0x14002cb0e  mov     r13d, 0A0h
0x14002cb14  mov     ebx, r13d
0x14002cb17  cmp     [rbp+0D0h+var_98], 0FFh
0x14002cb1e  cmovnz  ebx, [rbp+0D0h+var_98]
0x14002cb22  mov     edx, [rbp+0D0h+var_AC]; unsigned int
0x14002cb25  lea     rcx, [rbp+0D0h+var_D0]; this
0x14002cb29  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14002cb2e  test    eax, eax
0x14002cb30  jnz     loc_14002D48E
0x14002cb36  mov     rbx, r12
0x14002cb39  nop     dword ptr [rax+00000000h]
0x14002cb40  mov     rcx, [rbp+rbx*8+0D0h+var_150]; pv
0x14002cb45  test    rcx, rcx
0x14002cb48  jnz     loc_14002CDDC
0x14002cb4e  inc     rbx
0x14002cb51  cmp     rbx, 0Fh
0x14002cb55  jnz     short loc_14002CB40
0x14002cb57  mov     rcx, r15; pSid
0x14002cb5a  call    cs:__imp_IsValidSid
0x14002cb60  test    eax, eax
0x14002cb62  jz      loc_14002D4CE
0x14002cb68  mov     edx, [rbp+0D0h+var_AC]; unsigned int
0x14002cb6b  lea     rcx, [rbp+0D0h+var_D0]; this
0x14002cb6f  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14002cb74  test    eax, eax
0x14002cb76  jnz     loc_14002D53E
0x14002cb7c  lea     rsi, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002cb83  test    edi, edi
0x14002cb85  jz      loc_14002D2CF
0x14002cb8b  lea     eax, [rdi-2]
0x14002cb8e  cmp     eax, 1
0x14002cb91  jbe     loc_14002CFCF
0x14002cb97  cmp     edi, 1
0x14002cb9a  jz      loc_14002CE62
0x14002cba0  xor     eax, eax
0x14002cba2  mov     [rbp+0D0h+pAclInformation], rax
0x14002cba6  mov     dword ptr [rbp+0D0h+StringSid], eax
0x14002cba9  mov     rdi, [r14+60h]
0x14002cbad  test    rdi, rdi
0x14002cbb0  jz      short loc_14002CBCB
0x14002cbb2  mov     r9d, 2; dwAclInformationClass
0x14002cbb8  mov     r8d, 0Ch; nAclInformationLength
0x14002cbbe  lea     rdx, [rbp+0D0h+pAclInformation]; pAclInformation
0x14002cbc2  mov     rcx, rdi; pAcl
0x14002cbc5  call    cs:__imp_GetAclInformation
0x14002cbcb  mov     rcx, r15; pSid
0x14002cbce  call    cs:__imp_GetLengthSid
0x14002cbd4  mov     ebx, dword ptr [rbp+0D0h+pAclInformation+4]
0x14002cbd7  add     ebx, 10h
0x14002cbda  add     ebx, eax
0x14002cbdc  movsxd  rcx, ebx; unsigned __int64
0x14002cbdf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002cbe6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002cbeb  mov     rsi, rax
0x14002cbee  test    rax, rax
0x14002cbf1  jz      loc_14002D6C2
0x14002cbf7  mov     r8d, 2; dwAclRevision
0x14002cbfd  mov     edx, ebx; nAclLength
0x14002cbff  mov     rcx, rax; pAcl
0x14002cc02  call    cs:__imp_InitializeAcl
0x14002cc08  test    eax, eax
0x14002cc0a  jz      loc_14002D45C
0x14002cc10  xor     eax, eax
0x14002cc12  mov     [rbp+0D0h+var_50], rax
0x14002cc19  mov     [rbp+0D0h+var_48], eax
0x14002cc1f  mov     [rsp+1D0h+pAce], r12
0x14002cc24  test    rdi, rdi
0x14002cc27  jz      short loc_14002CC6A
0x14002cc29  mov     r9d, 2; dwAclInformationClass
0x14002cc2f  mov     r8d, 0Ch; nAclInformationLength
0x14002cc35  lea     rdx, [rbp+0D0h+var_50]; pAclInformation
0x14002cc3c  mov     rcx, rdi; pAcl
0x14002cc3f  call    cs:__imp_GetAclInformation
0x14002cc45  test    eax, eax
0x14002cc47  jnz     loc_14002CE0C
0x14002cc4d  call    cs:__imp_GetLastError
0x14002cc53  test    eax, eax
0x14002cc55  mov     ebx, eax
0x14002cc57  jle     short loc_14002CC62
0x14002cc59  movzx   ebx, ax
0x14002cc5c  or      ebx, 80070000h
0x14002cc62  test    ebx, ebx
0x14002cc64  js      loc_14002D1DF
0x14002cc6a  mov     [rsp+1D0h+pSid], r15; pSid
0x14002cc6f  mov     r9d, 1; AccessMask
0x14002cc75  xor     r8d, r8d; AceFlags
0x14002cc78  mov     edx, 2; dwAceRevision
0x14002cc7d  mov     rcx, rsi; pAcl
0x14002cc80  call    cs:__imp_AddAccessAllowedAceEx
0x14002cc86  test    eax, eax
0x14002cc88  jz      loc_14002D0FE
0x14002cc8e  mov     [r14+60h], rsi
0x14002cc92  test    rdi, rdi
0x14002cc95  jz      short loc_14002CC9F
0x14002cc97  mov     rcx, rdi; Block
0x14002cc9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002cc9f  mov     ebx, r12d
0x14002cca2  xor     r9d, r9d; bDaclDefaulted
0x14002cca5  mov     r8, [r14+60h]; pDacl
0x14002cca9  mov     edx, 1; bDaclPresent
0x14002ccae  mov     rcx, [r14+48h]; pSecurityDescriptor
0x14002ccb2  call    cs:__imp_SetSecurityDescriptorDacl
0x14002ccb8  mov     [rbp+0D0h+var_C8], ebx
0x14002ccbb  mov     rcx, [rbp+0D0h+pv]; pv
0x14002ccbf  call    cs:__imp_CoTaskMemFree
0x14002ccc5  mov     [rbp+0D0h+pv], r12
0x14002ccc9  mov     rcx, [rbp+0D0h+pv+8]; pv
0x14002cccd  call    cs:__imp_CoTaskMemFree
0x14002ccd3  mov     [rbp+0D0h+pv+8], r12
0x14002ccd7  mov     rcx, [rbp+0D0h+var_80]; pv
0x14002ccdb  call    cs:__imp_CoTaskMemFree
0x14002cce1  mov     [rbp+0D0h+var_80], r12
0x14002cce5  mov     rcx, [rbp+0D0h+var_80+8]; pv
0x14002cce9  call    cs:__imp_CoTaskMemFree
0x14002ccef  mov     [rbp+0D0h+var_80+8], r12
0x14002ccf3  call    cs:__imp_GetTickCount
0x14002ccf9  mov     esi, eax
0x14002ccfb  sub     esi, [rbp+0D0h+var_9C]
0x14002ccfe  mov     eax, 10624DD3h
0x14002cd03  mul     esi
0x14002cd05  mov     edi, edx
0x14002cd07  shr     edi, 6
0x14002cd0a  mov     eax, 88888889h
0x14002cd0f  mul     edi
0x14002cd11  shr     edx, 5
0x14002cd14  imul    ecx, edx, 3Ch ; '<'
0x14002cd17  mov     ebx, edi
0x14002cd19  sub     ebx, ecx
0x14002cd1b  mov     eax, 45E7B273h
0x14002cd20  mul     esi
0x14002cd22  mov     r11d, edx
0x14002cd25  shr     r11d, 0Eh
0x14002cd29  mov     eax, 88888889h
0x14002cd2e  mul     r11d
0x14002cd31  shr     edx, 5
0x14002cd34  imul    ecx, edx, 3Ch ; '<'
0x14002cd37  sub     r11d, ecx
0x14002cd3a  mov     eax, 95217CB1h
0x14002cd3f  mul     esi
0x14002cd41  mov     r10d, edx
0x14002cd44  shr     r10d, 15h
0x14002cd48  mov     eax, 88888889h
0x14002cd4d  mul     r10d
0x14002cd50  shr     edx, 5
0x14002cd53  imul    eax, edx, 3Ch ; '<'
0x14002cd56  sub     r10d, eax
0x14002cd59  mov     r9d, [rbp+0D0h+var_C8]
0x14002cd5d  cmp     [rbp+0D0h+var_98], 0FFh
0x14002cd64  cmovnz  r13d, [rbp+0D0h+var_98]
0x14002cd69  imul    eax, edi, 3E8h
0x14002cd6f  mov     ecx, esi
0x14002cd71  sub     ecx, eax
0x14002cd73  mov     [rsp+1D0h+var_188], r9d
0x14002cd78  mov     dword ptr [rsp+1D0h+var_190], esi
0x14002cd7c  mov     dword ptr [rsp+1D0h+var_198], ecx
0x14002cd80  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x14002cd84  mov     dword ptr [rsp+1D0h+var_1A8], r11d
0x14002cd89  mov     dword ptr [rsp+1D0h+pSid], r10d
0x14002cd8e  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x14002cd95  mov     r8d, r13d; unsigned int
0x14002cd98  lea     rdx, aExit; "EXIT"
0x14002cd9f  lea     rcx, [rbp+0D0h+var_D0]; this
0x14002cda3  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14002cda8  mov     rcx, [rbp+0D0h+var_70]
0x14002cdac  call    cs:__imp_VssSetTracingContextPerThread
0x14002cdb2  mov     rcx, [rbp+0D0h+var_40]
0x14002cdb9  xor     rcx, rsp; StackCookie
0x14002cdbc  call    __security_check_cookie
0x14002cdc1  mov     rbx, [rsp+1D0h+arg_10]
0x14002cdc9  add     rsp, 1A0h
0x14002cdd0  pop     r15
0x14002cdd2  pop     r14
0x14002cdd4  pop     r13
0x14002cdd6  pop     r12
0x14002cdd8  pop     rdi
0x14002cdd9  pop     rsi
0x14002cdda  pop     rbp
0x14002cddb  retn
0x14002cddc  call    cs:__imp_CoTaskMemFree
0x14002cde2  mov     [rbp+rbx*8+0D0h+var_150], r12
0x14002cde7  jmp     loc_14002CB4E
0x14002cdec  lea     rcx, [rbp+0D0h+var_D0]
0x14002cdf0  call    cs:__imp_VssSetTracingContextPerThread
0x14002cdf6  test    eax, eax
0x14002cdf8  js      loc_14002CAF9
0x14002cdfe  mov     rax, [rsp+1D0h+pAce]
0x14002ce03  mov     [rbp+0D0h+var_70], rax
0x14002ce07  jmp     loc_14002CAFD
0x14002ce0c  mov     ebx, r12d
0x14002ce0f  nop
0x14002ce10  cmp     ebx, dword ptr [rbp+0D0h+var_50]
0x14002ce16  jnb     loc_14002CC6A
0x14002ce1c  lea     r8, [rsp+1D0h+pAce]; pAce
0x14002ce21  mov     edx, ebx; dwAceIndex
0x14002ce23  mov     rcx, rdi; pAcl
0x14002ce26  call    cs:__imp_GetAce
0x14002ce2c  test    eax, eax
0x14002ce2e  jz      loc_14002CC4D
0x14002ce34  mov     r9, [rsp+1D0h+pAce]; pAceList
0x14002ce39  movzx   eax, word ptr [r9+2]
0x14002ce3e  mov     dword ptr [rsp+1D0h+pSid], eax; nAceListLength
0x14002ce42  mov     edx, 2; dwAceRevision
0x14002ce47  mov     r8d, 0FFFFFFFFh; dwStartingAceIndex
0x14002ce4d  mov     rcx, rsi; pAcl
0x14002ce50  call    cs:__imp_AddAce
0x14002ce56  test    eax, eax
0x14002ce58  jz      loc_14002D479
0x14002ce5e  inc     ebx
0x14002ce60  jmp     short loc_14002CE10
0x14002ce62  xor     eax, eax
0x14002ce64  mov     [rbp+0D0h+pAclInformation], rax
0x14002ce68  mov     dword ptr [rbp+0D0h+StringSid], eax
0x14002ce6b  mov     rdi, [r14+20h]
0x14002ce6f  test    rdi, rdi
0x14002ce72  jz      short loc_14002CE8D
0x14002ce74  mov     r9d, 2; dwAclInformationClass
0x14002ce7a  mov     r8d, 0Ch; nAclInformationLength
0x14002ce80  lea     rdx, [rbp+0D0h+pAclInformation]; pAclInformation
0x14002ce84  mov     rcx, rdi; pAcl
0x14002ce87  call    cs:__imp_GetAclInformation
0x14002ce8d  mov     rcx, r15; pSid
0x14002ce90  call    cs:__imp_GetLengthSid
0x14002ce96  mov     ebx, dword ptr [rbp+0D0h+pAclInformation+4]
0x14002ce99  add     ebx, 10h
0x14002ce9c  add     ebx, eax
0x14002ce9e  movsxd  rcx, ebx; unsigned __int64
0x14002cea1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002cea8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002cead  mov     rsi, rax
0x14002ceb0  test    rax, rax
0x14002ceb3  jz      loc_14002D6B8
0x14002ceb9  mov     r8d, 2; dwAclRevision
0x14002cebf  mov     edx, ebx; nAclLength
0x14002cec1  mov     rcx, rax; pAcl
0x14002cec4  call    cs:__imp_InitializeAcl
0x14002ceca  test    eax, eax
  ... truncated ...
```
