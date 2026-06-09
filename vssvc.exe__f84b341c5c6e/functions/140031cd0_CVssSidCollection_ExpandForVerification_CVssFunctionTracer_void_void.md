# CVssSidCollection::ExpandForVerification(CVssFunctionTracer &,void *,void *)

- ea: `0x140031cd0`
- end: `0x1400326b7`
- name: `?ExpandForVerification@CVssSidCollection@@AEAA_NAEAVCVssFunctionTracer@@PEAX1@Z`
- size: `2535`
- prototype: `bool(CVssSidCollection *__hidden this, struct CVssFunctionTracer *, void *, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140031760`

## callees

- `0x140006020`
- `0x140011a90`
- `0x1400138e0`
- `0x1400139c0`
- `0x140015e38`
- `0x140031cd0`
- `0x1400326c0`
- `0x1400330fc`
- `0x14003a8f0`
- `0x14003eedc`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400ccd64`
- `0x1400cd268`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031ef7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003219a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400321a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032224`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003228b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003229e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032005`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032133`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003219a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400321a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140032224`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003228b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003229e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140031e8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140031eb0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140031e8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140031eb0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1400320c2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1400320c2`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x140031e28`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x140031e28`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140031dfe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140031e0a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140031dfe`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140031e0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003262b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14003262b`
- `netutils!NetApiBufferFree` at `0x14003260a`
- `netutils!NetApiBufferFree` at `0x140032615`
- `netutils!NetApiBufferFree` at `0x140032620`
- `netutils!NetApiBufferFree` at `0x140032664`
- `netutils!NetApiBufferFree` at `0x14003266f`
- `netutils!NetApiBufferFree` at `0x14003267a`
- `netutils!NetApiBufferFree` at `0x1400326ab`
- `netutils!NetApiBufferFree` at `0x14003260a`
- `netutils!NetApiBufferFree` at `0x140032615`
- `netutils!NetApiBufferFree` at `0x140032620`
- `netutils!NetApiBufferFree` at `0x140032664`
- `netutils!NetApiBufferFree` at `0x14003266f`
- `netutils!NetApiBufferFree` at `0x14003267a`
- `netutils!NetApiBufferFree` at `0x1400326ab`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140031e5c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140031ee9`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140031e5c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x140031ee9`
- `samcli!NetLocalGroupGetMembers` at `0x14003207f`
- `samcli!NetLocalGroupGetMembers` at `0x14003207f`

## string_xrefs

- `0x140031d4a`: `base\stor\vss\modules\sec\security.cxx`
- `0x140031efd`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400322b0`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400323b8`: `base\stor\vss\modules\sec\security.cxx`
- `0x140032651`: `base\stor\vss\modules\sec\security.cxx`
- `0x140031d58`: `CVssSidCollection::ExpandForVerification`
- `0x140031f0c`: `CVssSidCollection::ExpandForVerification`
- `0x1400322bf`: `CVssSidCollection::ExpandForVerification`
- `0x1400323c7`: `CVssSidCollection::ExpandForVerification`
- `0x140032658`: `CVssSidCollection::ExpandForVerification`
- `0x140031f9e`: `LookupAccountSid fails unexpectedly, winerror %d.`
- `0x14003233a`: `LookupAccountSid returned with winerror %d, bRes %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
char __fastcall CVssSidCollection::ExpandForVerification(PSID *this, struct CVssFunctionTracer *a2, void *a3, void *a4)
{
  PUCHAR SidSubAuthorityCount; // rdi
  BOOL v8; // edi
  DWORD LastError; // esi
  HLOCAL v10; // rsi
  _WORD *v11; // rdi
  DWORD v12; // eax
  DWORD Members; // eax
  int v15; // r14d
  LPBYTE v16; // r14
  DWORD i; // r15d
  const wchar_t *v18; // rax
  DWORD v19; // esi
  struct CVssDebugInfo *v20; // rax
  __int64 v21; // rax
  bool v22; // bl
  ULONGLONG TickCount64; // rax
  PSID v24; // rdx
  PSID_NAME_USE peUse; // [rsp+28h] [rbp-2C0h]
  void **v26; // [rsp+40h] [rbp-2A8h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-2A0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-298h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-294h] BYREF
  void **v30; // [rsp+58h] [rbp-290h] BYREF
  HLOCAL v31; // [rsp+60h] [rbp-288h]
  void **v32; // [rsp+68h] [rbp-280h] BYREF
  _WORD *v33; // [rsp+70h] [rbp-278h]
  enum _SID_NAME_USE v34; // [rsp+78h] [rbp-270h] BYREF
  DWORD entriesread[3]; // [rsp+7Ch] [rbp-26Ch] BYREF
  const unsigned __int16 *v36; // [rsp+88h] [rbp-260h] BYREF
  const unsigned __int16 *v37; // [rsp+90h] [rbp-258h]
  const unsigned __int16 *v38; // [rsp+98h] [rbp-250h]
  int v39; // [rsp+A0h] [rbp-248h]
  int v40; // [rsp+A4h] [rbp-244h]
  int v41; // [rsp+A8h] [rbp-240h]
  __int128 v42; // [rsp+B0h] [rbp-238h] BYREF
  __int128 v43; // [rsp+C0h] [rbp-228h]
  __int128 v44; // [rsp+D0h] [rbp-218h]
  __int128 v45; // [rsp+E0h] [rbp-208h]
  __int128 v46; // [rsp+F0h] [rbp-1F8h]
  __int128 v47; // [rsp+100h] [rbp-1E8h]
  __int128 v48; // [rsp+110h] [rbp-1D8h]
  __int64 v49; // [rsp+120h] [rbp-1C8h]
  int v50; // [rsp+128h] [rbp-1C0h]
  int pExceptionObject; // [rsp+130h] [rbp-1B8h] BYREF
  int v52; // [rsp+134h] [rbp-1B4h] BYREF
  DWORD totalentries; // [rsp+138h] [rbp-1B0h] BYREF
  ULONG_PTR resumehandle[3]; // [rsp+140h] [rbp-1A8h] BYREF
  _BYTE v55[168]; // [rsp+158h] [rbp-190h] BYREF
  _BYTE v56[232]; // [rsp+200h] [rbp-E8h] BYREF
  BOOL pfEqual; // [rsp+2F0h] [rbp+8h] BYREF
  struct CVssFunctionTracer *v58; // [rsp+2F8h] [rbp+10h]
  PSID pSid2; // [rsp+300h] [rbp+18h]

  pSid2 = a3;
  v58 = a2;
  v31 = 0;
  v30 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  v33 = 0;
  v32 = &CVssAutoLocalPtr<unsigned short *>::`vftable';
  bufptr = 0;
  v26 = &CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::`vftable';
  v34 = SidTypeInvalid;
  resumehandle[0] = 0;
  entriesread[0] = 0;
  totalentries = 0;
  cchReferencedDomainName = 0;
  cchName = 0;
  pfEqual = 0;
  v36 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v37 = L"CVssSidCollection::ExpandForVerification";
  v38 = L"SECSECRC";
  v39 = 1893;
  v40 = 11;
  v41 = 255;
  v50 = 0x1000000;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  CVssFunctionTracer::Trace(a2, &v36, L"ExpandForVerification()");
  SidSubAuthorityCount = GetSidSubAuthorityCount(this[13]);
  if ( GetSidSubAuthorityCount(a4) < SidSubAuthorityCount )
  {
    pfEqual = 1;
  }
  else
  {
    EqualDomainSid(a4, this[13], &pfEqual);
    if ( !pfEqual )
    {
      v22 = CVssFunctionTracer::Exit(a2, 0);
      CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::~CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>(&v26);
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v32);
      CVssAutoLocalPtr<void *>::~CVssAutoLocalPtr<void *>(&v30);
      return v22;
    }
  }
  v8 = LookupAccountSidLocalW(a4, 0, &cchName, 0, &cchReferencedDomainName, &v34);
  LastError = GetLastError();
  if ( LastError != 122 || v8 )
  {
    v36 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v37 = L"CVssSidCollection::ExpandForVerification";
    v38 = L"SECSECRC";
    v39 = 1928;
    v40 = 11;
    v41 = 255;
    v50 = 0x1000000;
    memset_0(&v42, 0, 0x78u);
    v18 = L"TRUE";
    if ( !v8 )
      v18 = L"FALSE";
    CVssFunctionTracer::Trace(a2, &v36, L"LookupAccountSid returned with winerror %d, bRes %s.", LastError, v18);
    CVssFunctionTracer::TraceInternalWithFormat(a2, L"RETURN", 0xAAu, L"Returning BOOL: %s", L"FALSE");
    bufptr = 0;
    v26 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
    v33 = 0;
    v31 = 0;
    return 0;
  }
  v10 = LocalAlloc(0, 2LL * cchReferencedDomainName + 2);
  v31 = v10;
  if ( !v10 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v11 = LocalAlloc(0, 2LL * cchName + 2);
  v33 = v11;
  if ( !v11 )
  {
    v52 = -2147024882;
    throw (long *)&v52;
  }
  if ( !LookupAccountSidLocalW(a4, v11, &cchName, (LPWSTR)v10, &cchReferencedDomainName, &v34) )
  {
    v12 = GetLastError();
    v36 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v37 = L"CVssSidCollection::ExpandForVerification";
    v38 = L"SECSECRC";
    v39 = 1943;
    v40 = 11;
    v41 = 255;
    v50 = 0x1000000;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    CVssFunctionTracer::Trace(a2, &v36, L"LookupAccountSid fails unexpectedly, winerror %d.", v12);
    CVssFunctionTracer::TraceInternalWithFormat(a2, L"RETURN", 0xAAu, L"Returning BOOL: %s", L"FALSE");
    bufptr = 0;
    v26 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
    LocalFree(v11);
    v33 = 0;
    LocalFree(v10);
    v31 = 0;
    return 0;
  }
  bufptr = 0;
  Members = NetLocalGroupGetMembers(0, v11, 0, &bufptr, 0xFFFFFFFF, entriesread, &totalentries, resumehandle);
  v15 = Members;
  if ( Members == 2220 )
  {
    CVssFunctionTracer::TraceInternalWithFormat(a2, L"RETURN", 0xAAu, L"Returning BOOL: %s", L"FALSE");
    v26 = &CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::`vftable';
    if ( bufptr )
      NetApiBufferFree(bufptr);
    goto LABEL_18;
  }
  if ( Members )
  {
    TickCount64 = GetTickCount64();
    v24 = this[14];
    if ( !v24 || TickCount64 - (unsigned __int64)v24 > 0x36EE80 )
    {
      this[14] = (PSID)TickCount64;
      if ( v15 > 0 )
        v19 = (unsigned __int16)v15 | 0x80070000;
      else
        v19 = v15;
      v36 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v37 = L"CVssSidCollection::ExpandForVerification";
      v38 = L"SECSECRC";
      v39 = 1978;
      v40 = 11;
      v41 = 255;
      v50 = 0x1000000;
      memset_0(&v42, 0, 0x78u);
      CVssFunctionTracer::AddGenericErrorContext(
        (__int64)a2,
        (const struct CVssDebugInfo *)&v36,
        v19,
        L"NetLocalGroupGetMemebers(%s)",
        v11);
      v36 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
      v37 = L"CVssSidCollection::ExpandForVerification";
      v38 = L"SECSECRC";
      v39 = 1983;
      v40 = 11;
      v41 = 255;
      v50 = 0x1000000;
      memset_0(&v42, 0, 0x78u);
      v20 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v36, (CVssDebugInfo *)v56, v11);
      v21 = CVssDebugInfo::operator<<(v20, (CVssDebugInfo *)v55);
      CVssFunctionTracer::LogError(a2, 8230, v21, 2);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v56);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v36);
    }
    v36 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v37 = L"CVssSidCollection::ExpandForVerification";
    v38 = L"SECSECRC";
    v39 = 1987;
    v40 = 11;
    v41 = 255;
    v50 = 0x1000000;
    memset_0(&v42, 0, 0x78u);
    LODWORD(peUse) = v15;
    CVssFunctionTracer::Throw(
      a2,
      &v36,
      2147754754LL,
      L"NetLocalGroupGetMembers() failed for \"%s\" with %d",
      v11,
      peUse);
  }
  v16 = bufptr;
  if ( !bufptr )
  {
    CVssFunctionTracer::TraceInternalWithFormat(a2, L"RETURN", 0xAAu, L"Returning BOOL: %s", L"FALSE");
    v26 = &CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::`vftable';
    if ( bufptr )
      NetApiBufferFree(bufptr);
LABEL_18:
    bufptr = 0;
    v26 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
    LocalFree(v11);
    v33 = 0;
    LocalFree(v10);
    v31 = 0;
    return 0;
  }
  for ( i = 0; i < entriesread[0]; ++i )
  {
    if ( EqualSid(*(PSID *)&v16[8 * i], pSid2) )
    {
      CVssFunctionTracer::TraceInternalWithFormat(a2, L"RETURN", 0xAAu, L"Returning BOOL: %s", L"TRUE");
      v26 = &CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::`vftable';
      if ( bufptr )
        NetApiBufferFree(bufptr);
      bufptr = 0;
      v26 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
      LocalFree(v11);
      v33 = 0;
      LocalFree(v10);
      v31 = 0;
      return 1;
    }
  }
  CVssFunctionTracer::TraceInternalWithFormat(a2, L"RETURN", 0xAAu, L"Returning BOOL: %s", L"FALSE");
  v26 = &CVssAuto<unsigned char *,CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>>::`vftable';
  if ( bufptr )
    NetApiBufferFree(bufptr);
  bufptr = 0;
  v26 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
  LocalFree(v11);
  LocalFree(v10);
  return 0;
}

```

## disassembly

```asm
0x140031cd0  mov     r11, rsp
0x140031cd3  mov     [r11+18h], r8
0x140031cd7  mov     [r11+10h], rdx
0x140031cdb  push    rbx
0x140031cdc  push    rsi
0x140031cdd  push    rdi
0x140031cde  push    r12
0x140031ce0  push    r13
0x140031ce2  push    r14
0x140031ce4  push    r15
0x140031ce6  sub     rsp, 2B0h
0x140031ced  mov     r14, r9
0x140031cf0  mov     r12, rdx
0x140031cf3  mov     r15, rcx
0x140031cf6  xor     ebx, ebx
0x140031cf8  mov     [rsp+2E8h+var_288], rbx
0x140031cfd  lea     rax, ??_7?$CVssAutoLocalPtr@PEAG@@6B@; const CVssAutoLocalPtr<ushort *>::`vftable'
0x140031d04  mov     [rsp+2E8h+var_290], rax
0x140031d09  mov     [rsp+2E8h+var_278], rbx
0x140031d0e  mov     [rsp+2E8h+var_280], rax
0x140031d13  mov     [rsp+2E8h+bufptr], rbx
0x140031d18  lea     r13, ??_7?$CVssAuto@PEAEV?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@@@6B@; const CVssAuto<uchar *,CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>>::`vftable'
0x140031d1f  mov     [rsp+2E8h+var_2A8], r13
0x140031d24  mov     [rsp+2E8h+var_270], 7
0x140031d2c  mov     [r11-1A8h], rbx
0x140031d33  mov     [rsp+2E8h+entriesread], ebx
0x140031d37  mov     [rsp+2E8h+var_1B0], ebx
0x140031d3e  mov     [rsp+2E8h+var_298], ebx
0x140031d42  mov     [rsp+2E8h+cchName], ebx
0x140031d46  mov     [r11+8], ebx
0x140031d4a  lea     rax, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140031d51  mov     [r11-260h], rax
0x140031d58  lea     rax, aCvsssidcollect_1; "CVssSidCollection::ExpandForVerificatio"...
0x140031d5f  mov     [r11-258h], rax
0x140031d66  lea     rax, aSecsecrc; "SECSECRC"
0x140031d6d  mov     [r11-250h], rax
0x140031d74  mov     [rsp+2E8h+var_248], 765h
0x140031d7f  mov     [rsp+2E8h+var_244], 0Bh
0x140031d8a  mov     [rsp+2E8h+var_240], 0FFh
0x140031d95  mov     [rsp+2E8h+var_1C0], 1000000h
0x140031da0  xorps   xmm0, xmm0
0x140031da3  xor     eax, eax
0x140031da5  movups  [rsp+2E8h+var_238], xmm0
0x140031dad  movups  [rsp+2E8h+var_228], xmm0
0x140031db5  movups  [rsp+2E8h+var_218], xmm0
0x140031dbd  movups  [rsp+2E8h+var_208], xmm0
0x140031dc5  movups  [rsp+2E8h+var_1F8], xmm0
0x140031dcd  movups  [rsp+2E8h+var_1E8], xmm0
0x140031dd5  movups  [rsp+2E8h+var_1D8], xmm0
0x140031ddd  mov     [r11-1C8h], rax
0x140031de4  lea     r8, aExpandforverif; "ExpandForVerification()"
0x140031deb  lea     rdx, [r11-260h]
0x140031df2  mov     rcx, r12
0x140031df5  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140031dfa  mov     rcx, [r15+68h]; pSid
0x140031dfe  call    cs:__imp_GetSidSubAuthorityCount
0x140031e04  mov     rdi, rax
0x140031e07  mov     rcx, r14; pSid
0x140031e0a  call    cs:__imp_GetSidSubAuthorityCount
0x140031e10  cmp     rax, rdi
0x140031e13  jb      loc_1400321B6
0x140031e19  lea     r8, [rsp+2E8h+pfEqual]; pfEqual
0x140031e21  mov     rdx, [r15+68h]; pSid2
0x140031e25  mov     rcx, r14; pSid1
0x140031e28  call    cs:__imp_EqualDomainSid
0x140031e2e  cmp     [rsp+2E8h+pfEqual], ebx
0x140031e35  jz      loc_140032596
0x140031e3b  lea     rax, [rsp+2E8h+var_270]
0x140031e40  mov     [rsp+2E8h+peUse], rax; peUse
0x140031e45  lea     rax, [rsp+2E8h+var_298]
0x140031e4a  mov     [rsp+2E8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140031e4f  xor     r9d, r9d; ReferencedDomainName
0x140031e52  lea     r8, [rsp+2E8h+cchName]; cchName
0x140031e57  xor     edx, edx; Name
0x140031e59  mov     rcx, r14; Sid
0x140031e5c  call    cs:__imp_LookupAccountSidLocalW
0x140031e62  mov     edi, eax
0x140031e64  call    cs:__imp_GetLastError
0x140031e6a  mov     esi, eax
0x140031e6c  cmp     eax, 7Ah ; 'z'
0x140031e6f  jnz     loc_1400322B0
0x140031e75  test    edi, edi
0x140031e77  jnz     loc_1400322B0
0x140031e7d  mov     edx, [rsp+2E8h+var_298]
0x140031e81  lea     rdx, ds:2[rdx*2]; uBytes
0x140031e89  xor     ecx, ecx; uFlags
0x140031e8b  call    cs:__imp_LocalAlloc
0x140031e91  mov     rsi, rax
0x140031e94  mov     [rsp+2E8h+var_288], rax
0x140031e99  test    rax, rax
0x140031e9c  jz      loc_1400325CB
0x140031ea2  mov     edx, [rsp+2E8h+cchName]
0x140031ea6  lea     rdx, ds:2[rdx*2]; uBytes
0x140031eae  xor     ecx, ecx; uFlags
0x140031eb0  call    cs:__imp_LocalAlloc
0x140031eb6  mov     rdi, rax
0x140031eb9  mov     [rsp+2E8h+var_278], rax
0x140031ebe  test    rax, rax
0x140031ec1  jz      loc_1400325EA
0x140031ec7  lea     rax, [rsp+2E8h+var_270]
0x140031ecc  mov     [rsp+2E8h+peUse], rax; peUse
0x140031ed1  lea     rax, [rsp+2E8h+var_298]
0x140031ed6  mov     [rsp+2E8h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140031edb  mov     r9, rsi; ReferencedDomainName
0x140031ede  lea     r8, [rsp+2E8h+cchName]; cchName
0x140031ee3  mov     rdx, rdi; Name
0x140031ee6  mov     rcx, r14; Sid
0x140031ee9  call    cs:__imp_LookupAccountSidLocalW
0x140031eef  test    eax, eax
0x140031ef1  jnz     loc_140032033
0x140031ef7  call    cs:__imp_GetLastError
0x140031efd  lea     r15, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140031f04  mov     [rsp+2E8h+var_260], r15
0x140031f0c  lea     rcx, aCvsssidcollect_1; "CVssSidCollection::ExpandForVerificatio"...
0x140031f13  mov     [rsp+2E8h+var_258], rcx
0x140031f1b  lea     rcx, aSecsecrc; "SECSECRC"
0x140031f22  mov     [rsp+2E8h+var_250], rcx
0x140031f2a  mov     [rsp+2E8h+var_248], 797h
0x140031f35  mov     [rsp+2E8h+var_244], 0Bh
0x140031f40  mov     [rsp+2E8h+var_240], 0FFh
0x140031f4b  mov     [rsp+2E8h+var_1C0], 1000000h
0x140031f56  xorps   xmm0, xmm0
0x140031f59  xor     ecx, ecx
0x140031f5b  movups  [rsp+2E8h+var_238], xmm0
0x140031f63  movups  [rsp+2E8h+var_228], xmm0
0x140031f6b  movups  [rsp+2E8h+var_218], xmm0
0x140031f73  movups  [rsp+2E8h+var_208], xmm0
0x140031f7b  movups  [rsp+2E8h+var_1F8], xmm0
0x140031f83  movups  [rsp+2E8h+var_1E8], xmm0
0x140031f8b  movups  [rsp+2E8h+var_1D8], xmm0
0x140031f93  mov     [rsp+2E8h+var_1C8], rcx
0x140031f9b  mov     r9d, eax
0x140031f9e  lea     r8, aLookupaccounts_1; "LookupAccountSid fails unexpectedly, wi"...
0x140031fa5  lea     rdx, [rsp+2E8h+var_260]
0x140031fad  mov     rcx, r12
0x140031fb0  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140031fb5  lea     r14, aFalse; "FALSE"
0x140031fbc  mov     [rsp+2E8h+cchReferencedDomainName], r14
0x140031fc1  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140031fc8  mov     r8d, 0AAh; unsigned int
0x140031fce  lea     rdx, aReturn; "RETURN"
0x140031fd5  mov     rcx, r12; this
0x140031fd8  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140031fdd  nop
0x140031fde  mov     [rsp+2E8h+var_2A8], r13
0x140031fe3  mov     rcx, [rsp+2E8h+bufptr]; Buffer
0x140031fe8  test    rcx, rcx
0x140031feb  jnz     loc_14003260A
0x140031ff1  mov     [rsp+2E8h+bufptr], rbx
0x140031ff6  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x140031ffd  mov     [rsp+2E8h+var_2A8], rax
0x140032002  mov     rcx, rdi; hMem
0x140032005  call    cs:__imp_LocalFree
0x14003200b  mov     [rsp+2E8h+var_278], rbx
0x140032010  mov     rcx, rsi; hMem
0x140032013  call    cs:__imp_LocalFree
0x140032019  mov     [rsp+2E8h+var_288], rbx
0x14003201e  xor     al, al
0x140032020  add     rsp, 2B0h
0x140032027  pop     r15
0x140032029  pop     r14
0x14003202b  pop     r13
0x14003202d  pop     r12
0x14003202f  pop     rdi
0x140032030  pop     rsi
0x140032031  pop     rbx
0x140032032  retn
0x140032033  mov     rcx, [rsp+2E8h+bufptr]; Buffer
0x140032038  test    rcx, rcx
0x14003203b  jnz     loc_140032615
0x140032041  mov     [rsp+2E8h+bufptr], rbx
0x140032046  lea     rax, [rsp+2E8h+var_1A8]
0x14003204e  mov     [rsp+2E8h+resumehandle], rax; resumehandle
0x140032053  lea     rax, [rsp+2E8h+var_1B0]
0x14003205b  mov     [rsp+2E8h+totalentries], rax; totalentries
0x140032060  lea     rax, [rsp+2E8h+entriesread]
0x140032065  mov     [rsp+2E8h+peUse], rax; entriesread
0x14003206a  mov     dword ptr [rsp+2E8h+cchReferencedDomainName], 0FFFFFFFFh; prefmaxlen
0x140032072  lea     r9, [rsp+2E8h+bufptr]; bufptr
0x140032077  xor     r8d, r8d; level
0x14003207a  mov     rdx, rdi; localgroupname
0x14003207d  xor     ecx, ecx; servername
0x14003207f  call    cs:__imp_NetLocalGroupGetMembers
0x140032085  mov     r14d, eax
0x140032088  cmp     eax, 8ACh
0x14003208d  jz      short loc_1400320D5
0x14003208f  test    eax, eax
0x140032091  jnz     loc_14003262B
0x140032097  mov     r14, [rsp+2E8h+bufptr]
0x14003209c  test    r14, r14
0x14003209f  jz      loc_1400321C6
0x1400320a5  mov     r15d, ebx
0x1400320a8  cmp     r15d, [rsp+2E8h+entriesread]
0x1400320ad  jnb     loc_140032145
0x1400320b3  mov     ecx, r15d
0x1400320b6  mov     rdx, [rsp+2E8h+pSid2]; pSid2
0x1400320be  mov     rcx, [r14+rcx*8]; pSid1
0x1400320c2  call    cs:__imp_EqualSid
0x1400320c8  test    eax, eax
0x1400320ca  jnz     loc_140032236
0x1400320d0  inc     r15d
0x1400320d3  jmp     short loc_1400320A8
0x1400320d5  lea     r14, aFalse; "FALSE"
0x1400320dc  mov     [rsp+2E8h+cchReferencedDomainName], r14
0x1400320e1  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1400320e8  mov     r8d, 0AAh; unsigned int
0x1400320ee  lea     rdx, aReturn; "RETURN"
0x1400320f5  mov     rcx, r12; this
0x1400320f8  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400320fd  nop
0x1400320fe  mov     [rsp+2E8h+var_2A8], r13
0x140032103  mov     rcx, [rsp+2E8h+bufptr]; Buffer
0x140032108  test    rcx, rcx
0x14003210b  jnz     loc_140032620
0x140032111  mov     [rsp+2E8h+bufptr], rbx
0x140032116  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x14003211d  mov     [rsp+2E8h+var_2A8], rax
0x140032122  mov     rcx, rdi; hMem
0x140032125  call    cs:__imp_LocalFree
0x14003212b  mov     [rsp+2E8h+var_278], rbx
0x140032130  mov     rcx, rsi; hMem
0x140032133  call    cs:__imp_LocalFree
0x140032139  mov     [rsp+2E8h+var_288], rbx
0x14003213e  xor     al, al
0x140032140  jmp     loc_140032020
0x140032145  lea     r14, aFalse; "FALSE"
0x14003214c  mov     [rsp+2E8h+cchReferencedDomainName], r14
0x140032151  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140032158  mov     r8d, 0AAh; unsigned int
0x14003215e  lea     rdx, aReturn; "RETURN"
0x140032165  mov     rcx, r12; this
0x140032168  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003216d  nop
0x14003216e  mov     [rsp+2E8h+var_2A8], r13
0x140032173  mov     rcx, [rsp+2E8h+bufptr]; Buffer
0x140032178  test    rcx, rcx
0x14003217b  jnz     loc_1400326AB
0x140032181  mov     [rsp+2E8h+bufptr], rbx
0x140032186  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x14003218d  mov     [rsp+2E8h+var_2A8], rax
0x140032192  test    rdi, rdi
0x140032195  jz      short loc_1400321A1
0x140032197  mov     rcx, rdi; hMem
0x14003219a  call    cs:__imp_LocalFree
0x1400321a0  nop
0x1400321a1  test    rsi, rsi
0x1400321a4  jz      short loc_1400321AF
0x1400321a6  mov     rcx, rsi; hMem
0x1400321a9  call    cs:__imp_LocalFree
0x1400321af  xor     al, al
0x1400321b1  jmp     loc_140032020
0x1400321b6  mov     [rsp+2E8h+pfEqual], 1
0x1400321c1  jmp     loc_140031E3B
0x1400321c6  lea     r14, aFalse; "FALSE"
0x1400321cd  mov     [rsp+2E8h+cchReferencedDomainName], r14
0x1400321d2  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1400321d9  mov     r8d, 0AAh; unsigned int
0x1400321df  lea     rdx, aReturn; "RETURN"
0x1400321e6  mov     rcx, r12; this
0x1400321e9  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1400321ee  nop
0x1400321ef  mov     [rsp+2E8h+var_2A8], r13
0x1400321f4  mov     rcx, [rsp+2E8h+bufptr]; Buffer
0x1400321f9  test    rcx, rcx
0x1400321fc  jnz     loc_140032664
0x140032202  mov     [rsp+2E8h+bufptr], rbx
0x140032207  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x14003220e  mov     [rsp+2E8h+var_2A8], rax
0x140032213  mov     rcx, rdi; hMem
0x140032216  call    cs:__imp_LocalFree
0x14003221c  mov     [rsp+2E8h+var_278], rbx
0x140032221  mov     rcx, rsi; hMem
0x140032224  call    cs:__imp_LocalFree
0x14003222a  mov     [rsp+2E8h+var_288], rbx
0x14003222f  xor     al, al
0x140032231  jmp     loc_140032020
0x140032236  lea     rax, aTrue; "TRUE"
0x14003223d  mov     [rsp+2E8h+cchReferencedDomainName], rax
0x140032242  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140032249  mov     r8d, 0AAh; unsigned int
0x14003224f  lea     rdx, aReturn; "RETURN"
0x140032256  mov     rcx, r12; this
0x140032259  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003225e  nop
0x14003225f  mov     [rsp+2E8h+var_2A8], r13
0x140032264  mov     rcx, [rsp+2E8h+bufptr]; Buffer
0x140032269  test    rcx, rcx
0x14003226c  jnz     loc_14003266F
0x140032272  mov     [rsp+2E8h+bufptr], rbx
0x140032277  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x14003227e  mov     [rsp+2E8h+var_2A8], rax
0x140032283  test    rdi, rdi
0x140032286  jz      short loc_140032291
0x140032288  mov     rcx, rdi; hMem
0x14003228b  call    cs:__imp_LocalFree
0x140032291  mov     [rsp+2E8h+var_278], rbx
0x140032296  test    rsi, rsi
0x140032299  jz      short loc_1400322A4
0x14003229b  mov     rcx, rsi; hMem
0x14003229e  call    cs:__imp_LocalFree
  ... truncated ...
```
