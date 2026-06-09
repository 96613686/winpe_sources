# CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)

- ea: `0x18001f6d0`
- end: `0x180020351`
- name: `?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z`
- size: `3201`
- prototype: `char __fastcall(CWbemNamespace *this, struct CNtSecurityDescriptor *, unsigned int, unsigned __int16 *, const unsigned __int16 *, bool, bool)`
- caller_count: `23`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001d410`
- `0x18001e9a0`
- `0x180022a90`
- `0x1800237fc`
- `0x18002427c`
- `0x180026a00`
- `0x18002dda4`
- `0x18002fa00`
- `0x1800477b0`
- `0x180048360`
- `0x180048a50`
- `0x180049d34`
- `0x18004bc18`
- `0x18004d684`
- `0x18005b874`
- `0x18005cc60`
- `0x180066e10`
- `0x180071000`
- `0x1800827d0`
- `0x18009ddcc`
- `0x18009e9b0`
- `0x18009fc70`
- `0x1800a01c0`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18001f6d0`
- `0x180020358`
- `0x1800203a0`
- `0x180021520`
- `0x18004e6b0`
- `0x18005e204`
- `0x18005fc58`
- `0x1800604d0`
- `0x180065cd0`
- `0x1800c3b48`
- `0x1800c3ba4`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f8dd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f8dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f8c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f8c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001ff1c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001ff1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002033b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002033b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001f9b4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001fa55`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001f9b4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001fa55`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ff3d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ff3d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001f9d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001fa74`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001f9d3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001fa74`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18001f9dd`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18001fa7e`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18001f9dd`
- `wbemcomn!?GetStatus@CNtSid@@QEAAKXZ` at `0x18001fa7e`
- `wbemcomn!?IsUserInGroup@CNtSecurity@@SAHPEAXAEAVCNtSid@@PEAH@Z` at `0x18001f9f2`
- `wbemcomn!?IsUserInGroup@CNtSecurity@@SAHPEAXAEAVCNtSid@@PEAH@Z` at `0x18001fa93`
- `wbemcomn!?IsUserInGroup@CNtSecurity@@SAHPEAXAEAVCNtSid@@PEAH@Z` at `0x18001f9f2`
- `wbemcomn!?IsUserInGroup@CNtSecurity@@SAHPEAXAEAVCNtSid@@PEAH@Z` at `0x18001fa93`
- `wbemcomn!IsAdmin` at `0x18001fb66`
- `wbemcomn!IsAdmin` at `0x18001fb66`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18001f9c7`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18001fa68`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18001f9c7`
- `wbemcomn!??0CNtSid@@QEAA@PEAX@Z` at `0x18001fa68`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18001fa0f`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18001faa5`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800200e4`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18001fa0f`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x18001faa5`
- `wbemcomn!??1CNtSid@@QEAA@XZ` at `0x1800200e4`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x180020284`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x180020284`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001f78c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001faf0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001f78c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001faf0`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002018e`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201a6`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201bf`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201d7`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201f2`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002020d`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002022b`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x180020246`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x180020261`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002018e`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201a6`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201bf`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201d7`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800201f2`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002020d`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x18002022b`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x180020246`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x180020261`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800202d7`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800202d7`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18001f72c`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18001f72c`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001f894`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001fb21`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001f894`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001fb21`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001f8b1`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001fb75`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001fbb1`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001fee5`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001f8b1`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001fb75`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001fbb1`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001fee5`
- `wbemcomn!GetMemLogObject` at `0x18001f7da`
- `wbemcomn!GetMemLogObject` at `0x18001fc60`
- `wbemcomn!GetMemLogObject` at `0x18001fe07`
- `wbemcomn!GetMemLogObject` at `0x18001fe5d`
- `wbemcomn!GetMemLogObject` at `0x180020040`
- `wbemcomn!GetMemLogObject` at `0x180020122`
- `wbemcomn!GetMemLogObject` at `0x18001f7da`
- `wbemcomn!GetMemLogObject` at `0x18001fc60`
- `wbemcomn!GetMemLogObject` at `0x18001fe07`
- `wbemcomn!GetMemLogObject` at `0x18001fe5d`
- `wbemcomn!GetMemLogObject` at `0x180020040`
- `wbemcomn!GetMemLogObject` at `0x180020122`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f7e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fc6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe12`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002004b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020132`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001f7e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fc6b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe12`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001fe68`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002004b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020132`
- `wbemcomn!GetAccessToken` at `0x18001f871`
- `wbemcomn!GetAccessToken` at `0x18001f871`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001f912`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18001f912`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall CWbemNamespace::InnerAllowedWithSD(
        CWbemNamespace *this,
        struct CNtSecurityDescriptor *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        bool a6,
        bool a7)
{
  const unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rsi
  unsigned __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *i; // rdx
  __int64 v16; // r15
  unsigned __int16 *v17; // r8
  unsigned int v18; // esi
  CMemoryLog *v19; // rax
  unsigned int v20; // esi
  unsigned __int16 *v21; // rcx
  char *v22; // rbx
  HANDLE CurrentThread; // rax
  signed int v24; // esi
  bool v25; // di
  HANDLE v26; // rdi
  unsigned __int64 v27; // rdi
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rdx
  unsigned int v31; // edi
  unsigned __int16 *v33; // r8
  unsigned int v34; // esi
  CMemoryLog *v35; // rax
  unsigned __int16 *v36; // rcx
  unsigned __int64 v37; // rcx
  unsigned __int16 *v38; // rax
  unsigned int v39; // esi
  unsigned __int64 v40; // r8
  __int64 v41; // rax
  const unsigned __int16 *v42; // r9
  bool v43; // zf
  unsigned __int64 v44; // rdx
  unsigned __int16 *v45; // r8
  unsigned __int16 v46; // cx
  unsigned __int16 *v47; // rcx
  unsigned __int64 v48; // rcx
  unsigned __int16 *v49; // rax
  unsigned __int64 v50; // rdx
  __int64 v51; // rax
  unsigned __int64 v52; // rdi
  unsigned __int16 v53; // cx
  CMemoryLog *v54; // rax
  CMemoryLog *MemLogObject; // rax
  int v56; // edi
  signed int LastError; // eax
  __int64 v58; // rax
  const wchar_t *v59; // r9
  wchar_t v60; // cx
  unsigned __int16 *v61; // rcx
  unsigned __int64 v62; // rcx
  unsigned __int16 *v63; // rax
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rdi
  unsigned __int16 v66; // ax
  unsigned int v67; // esi
  unsigned __int16 *v68; // rcx
  CMemoryLog *v69; // rax
  __int64 v70; // rax
  unsigned __int16 v71; // cx
  CMemoryLog *v72; // rax
  CInsertionString *v73; // r13
  CInsertionString *v74; // r12
  CInsertionString *v75; // r15
  CInsertionString *v76; // r14
  CInsertionString *v77; // rsi
  CInsertionString *v78; // rdi
  CInsertionString *v79; // rbx
  CInsertionString *v80; // rax
  bool nSubAuthority4; // [rsp+30h] [rbp-D0h]
  void *ppInterface; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v83[2]; // [rsp+78h] [rbp-88h]
  unsigned int v84[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v85; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v87; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v88; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE hObject; // [rsp+A8h] [rbp-58h] BYREF
  CWbemNamespace *v90; // [rsp+B0h] [rbp-50h]
  _QWORD v91[2]; // [rsp+B8h] [rbp-48h] BYREF
  HANDLE v92; // [rsp+C8h] [rbp-38h] BYREF
  char v93[8]; // [rsp+D0h] [rbp-30h] BYREF
  void (__fastcall *v94)(_QWORD); // [rsp+D8h] [rbp-28h]
  _QWORD *v95; // [rsp+E0h] [rbp-20h]
  char v96[8]; // [rsp+E8h] [rbp-18h] BYREF
  struct CNtSecurityDescriptor *v97; // [rsp+F0h] [rbp-10h]
  char v98[8]; // [rsp+100h] [rbp+0h] BYREF
  void (__fastcall *v99)(_QWORD); // [rsp+108h] [rbp+8h]
  _QWORD *v100; // [rsp+110h] [rbp+10h]
  _BYTE *v101; // [rsp+118h] [rbp+18h]
  _BYTE *v102; // [rsp+120h] [rbp+20h]
  _BYTE *v103; // [rsp+128h] [rbp+28h]
  _BYTE *v104; // [rsp+130h] [rbp+30h]
  _BYTE *v105; // [rsp+138h] [rbp+38h]
  _BYTE v106[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v107[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v108[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v109[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v110[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v111[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v112[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v113[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v114[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v115[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE *v116; // [rsp+1E0h] [rbp+E0h]
  _BYTE *v117; // [rsp+1E8h] [rbp+E8h]
  CInsertionString *pIdentifierAuthority; // [rsp+1F0h] [rbp+F0h] BYREF

  v83[0] = a3;
  v97 = a2;
  v90 = this;
  v9 = a5;
  hObject = (HANDLE)-1LL;
  v88 = 0;
  v87 = 0;
  if ( (unsigned __int8)CWbemInstallObject::IsOffline() )
    return 1;
  v10 = (unsigned __int16 *)*((_QWORD *)this + 12);
  v11 = 2;
  if ( v10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
    v11 = v12 + 2;
  }
  if ( a5 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a5[v13] );
    v11 += v13;
  }
  v14 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v11, 2u));
  v87 = v14;
  v16 = 2147483646;
  if ( v14 )
  {
    *v14 = 0;
    if ( !v10 )
      goto LABEL_77;
    v17 = v87;
    if ( v11 )
    {
      if ( v11 > 0x7FFFFFFF )
      {
        v18 = -2147024809;
        *v87 = 0;
      }
      else
      {
        v70 = 2147483646;
        i = (unsigned __int16 *)v11;
        do
        {
          if ( !v70 )
            break;
          v71 = *v10;
          if ( !*v10 )
            break;
          ++v10;
          *v17++ = v71;
          --v70;
          i = (unsigned __int16 *)((char *)i - 1);
        }
        while ( i );
        v36 = v17 - 1;
        if ( i )
          v36 = v17;
        *v36 = 0;
        v18 = -2147024774;
        if ( i )
        {
LABEL_77:
          if ( !a5 )
            goto LABEL_24;
          if ( v11 - 1 > 0x7FFFFFFE )
          {
            v39 = -2147024809;
          }
          else
          {
            v37 = v11;
            v38 = v87;
            do
            {
              if ( !*v38 )
                break;
              ++v38;
              --v37;
            }
            while ( v37 );
            v39 = -2147024809;
            if ( v37 )
            {
              v39 = 0;
              v40 = v11 - v37;
            }
            else
            {
              v40 = 0;
            }
            if ( v37 )
            {
              v41 = 2147483646;
              v42 = L":";
              v44 = v11 - v40;
              v43 = v11 == v40;
              v45 = &v87[v40];
              if ( !v43 )
              {
                do
                {
                  if ( !v41 )
                    break;
                  v46 = *v42;
                  if ( !*v42 )
                    break;
                  ++v42;
                  *v45++ = v46;
                  --v41;
                  --v44;
                }
                while ( v44 );
              }
              v39 = -2147024774;
              if ( v44 )
                v39 = 0;
              v47 = v45 - 1;
              if ( v44 )
                v47 = v45;
              *v47 = 0;
              if ( v44 )
              {
LABEL_94:
                if ( v11 - 1 > 0x7FFFFFFE )
                {
                  v20 = -2147024809;
                }
                else
                {
                  v48 = v11;
                  v49 = v87;
                  do
                  {
                    if ( !*v49 )
                      break;
                    ++v49;
                    --v48;
                  }
                  while ( v48 );
                  v20 = -2147024809;
                  if ( v48 )
                  {
                    v20 = 0;
                    v50 = v11 - v48;
                  }
                  else
                  {
                    v50 = 0;
                  }
                  if ( v48 )
                  {
                    v51 = 2147483646;
                    v52 = v11 - v50;
                    for ( i = &v87[v50]; v52; --v52 )
                    {
                      if ( !v51 )
                        break;
                      v53 = *v9;
                      if ( !*v9 )
                        break;
                      ++v9;
                      *i++ = v53;
                      --v51;
                    }
                    v20 = -2147024774;
                    if ( v52 )
                      v20 = 0;
                    v21 = i - 1;
                    if ( v52 )
                      v21 = i;
                    *v21 = 0;
                    if ( v52 )
                      goto LABEL_24;
                  }
                }
                MemLogObject = GetMemLogObject();
                CMemoryLog::Write(MemLogObject, v20);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    34,
                    WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
                    v20);
                }
                goto LABEL_24;
              }
            }
          }
          v54 = GetMemLogObject();
          CMemoryLog::Write(v54, v39);
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v39);
          }
          goto LABEL_94;
        }
      }
    }
    else
    {
      v18 = -2147024809;
    }
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, v18);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v18);
    }
    goto LABEL_77;
  }
LABEL_24:
  MakeGuard<void (*)(unsigned short *),RefHolder<unsigned short *>>(v93, i, &v87);
  if ( !*((_BYTE *)this + 328) || EncryptedCaller() )
  {
    if ( (int)GetAccessToken(&hObject) < 0 )
    {
LABEL_65:
      if ( !v93[0] )
        v94(*v95);
      return 1;
    }
    v22 = (char *)hObject;
    v92 = hObject;
    CInCritSec::CInCritSec((CInCritSec *)&ppInterface, (struct _RTL_CRITICAL_SECTION *)((char *)this + 136));
    if ( *((_DWORD *)v90 + 60) )
    {
      CInCritSec::~CInCritSec((CInCritSec *)&ppInterface);
    }
    else
    {
      v56 = CWbemNamespace::InitializeSD(v90, 0);
      if ( v56 >= 0 )
        *((_DWORD *)v90 + 60) = 1;
      CInCritSec::~CInCritSec((CInCritSec *)&ppInterface);
      if ( v56 < 0 )
        goto LABEL_56;
    }
    v85 = 0;
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      HIBYTE(v85) = 1;
      RevertToSelf();
    }
    else
    {
      if ( GetLastError() == 1008 )
      {
        v24 = 0;
        v25 = 0;
        ppInterface = 0;
        if ( !CoGetCallContext(&IID_IServerSecurity, &ppInterface) )
        {
          v25 = (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) == 1;
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
        }
        LOBYTE(v85) = v25;
        if ( v25 )
          v24 = WbemCoRevertToSelf();
      }
      else
      {
        LastError = GetLastError();
        v24 = LastError;
        if ( LastError > 0 )
          v24 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v24 < 0 )
      {
        CRevertToSelfAndCleanup::~CRevertToSelfAndCleanup((CRevertToSelfAndCleanup *)&v85);
        CCloseMe::~CCloseMe((CCloseMe *)&v92);
        ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v93);
        return 1;
      }
    }
    v83[0] |= 1u;
    v26 = hObject;
    ppInterface = 0;
    LODWORD(pIdentifierAuthority) = 0;
    WORD2(pIdentifierAuthority) = 1280;
    v84[0] = 1;
    if ( AllocateAndInitializeSid(
           (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority,
           1u,
           4u,
           0,
           0,
           0,
           0,
           0,
           0,
           0,
           &ppInterface) )
    {
      CNtSid::CNtSid((CNtSid *)v91, ppInterface);
      FreeSid(ppInterface);
      if ( !CNtSid::GetStatus((CNtSid *)v91) )
      {
        if ( !CNtSecurity::IsUserInGroup(v26, (struct CNtSid *)v91, (int *)v84) )
        {
          CNtSid::~CNtSid((CNtSid *)v91);
          goto LABEL_162;
        }
        v84[0] = v84[0] == 0;
      }
      CNtSid::~CNtSid((CNtSid *)v91);
    }
    if ( !v84[0] )
      goto LABEL_47;
    if ( AllocateAndInitializeSid(
           (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority,
           1u,
           2u,
           0,
           0,
           0,
           0,
           0,
           0,
           0,
           &ppInterface) )
    {
      CNtSid::CNtSid((CNtSid *)v91, ppInterface);
      FreeSid(ppInterface);
      if ( !CNtSid::GetStatus((CNtSid *)v91) && !CNtSecurity::IsUserInGroup(v26, (struct CNtSid *)v91, (int *)v84) )
        v84[0] = 1;
      CNtSid::~CNtSid((CNtSid *)v91);
    }
    if ( !v84[0] )
    {
LABEL_47:
      v27 = 7;
      if ( a4 )
      {
        v28 = -1;
        do
          ++v28;
        while ( a4[v28] );
        v27 = v28 + 7;
      }
      v29 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v27, 2u));
      v88 = v29;
      if ( !v29 )
        goto LABEL_52;
      *v29 = 0;
      v33 = v88;
      if ( v27 )
      {
        if ( v27 > 0x7FFFFFFF )
        {
          v34 = -2147024809;
          *v88 = 0;
        }
        else
        {
          v58 = 2147483646;
          v59 = L"Local ";
          v30 = (unsigned __int16 *)v27;
          do
          {
            if ( !v58 )
              break;
            v60 = *v59;
            if ( !*v59 )
              break;
            ++v59;
            *v33++ = v60;
            --v58;
            v30 = (unsigned __int16 *)((char *)v30 - 1);
          }
          while ( v30 );
          v61 = v33 - 1;
          if ( v30 )
            v61 = v33;
          *v61 = 0;
          v34 = -2147024774;
          if ( v30 )
          {
LABEL_135:
            if ( a4 )
            {
              if ( v27 - 1 > 0x7FFFFFFE )
                goto LABEL_154;
              v62 = v27;
              v63 = v88;
              do
              {
                if ( !*v63 )
                  break;
                ++v63;
                --v62;
              }
              while ( v62 );
              if ( v62 )
              {
                v64 = v27 - v62;
                v65 = v62;
                v30 = &v88[v64];
                do
                {
                  if ( !v16 )
                    break;
                  v66 = *a4;
                  if ( !*a4 )
                    break;
                  ++a4;
                  *v30++ = v66;
                  --v16;
                  --v65;
                }
                while ( v65 );
                v67 = -2147024774;
                if ( v65 )
                  v67 = 0;
                v68 = v30 - 1;
                if ( v65 )
                  v68 = v30;
                *v68 = 0;
                if ( v65 )
                  goto LABEL_52;
              }
              else
              {
LABEL_154:
                v67 = -2147024809;
              }
              v69 = GetMemLogObject();
              CMemoryLog::Write(v69, v67);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v67);
              }
            }
LABEL_52:
            v31 = v83[0];
LABEL_53:
            MakeGuard<void (*)(unsigned short *),RefHolder<unsigned short *>>(v98, v30, &v88);
            CInCritSec::CInCritSec((CInCritSec *)v96, (struct _RTL_CRITICAL_SECTION *)((char *)this + 136));
            v84[0] = 0;
            if ( (!CWbemNamespace::WMIAccessCheckAndAudit(v90, v97, v31, v88, v87, hObject, nSubAuthority4, v84)
               || !v84[0])
              && IsAdmin(hObject) != 1 )
            {
              CInCritSec::~CInCritSec((CInCritSec *)v96);
              ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v98);
              CRevertToSelfAndCleanup::~CRevertToSelfAndCleanup((CRevertToSelfAndCleanup *)&v85);
LABEL_56:
              CCloseMe::~CCloseMe((CCloseMe *)&v92);
              ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v93);
              return 0;
            }
            CInCritSec::~CInCritSec((CInCritSec *)v96);
            if ( !v98[0] )
              v99(*v100);
            if ( HIBYTE(v85) )
            {
              if ( !SetThreadToken(0, TokenHandle) )
                GetLastError();
              CloseHandle(TokenHandle);
            }
            else if ( (_BYTE)v85 )
            {
              WbemCoImpersonateClient();
            }
            TokenHandle = 0;
            v85 = 0;
            if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v22);
            goto LABEL_65;
          }
        }
      }
      else
      {
        v34 = -2147024809;
      }
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, v34);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v34);
      }
      goto LABEL_135;
    }
LABEL_162:
    v31 = v83[0] | 0x20;
    BuildObjectOperationString(L"Remote ", a4, &v88);
    goto LABEL_53;
  }
  if ( *((_QWORD *)this + 12) )
  {
    v72 = GetMemLogObject();
    CMemoryLog::Write(v72, -1);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        157,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        *((_QWORD *)this + 12));
    }
    if ( a7 )
    {
      *(_QWORD *)v84 = g_pEventLog;
      v97 = (struct CNtSecurityDescriptor *)v106;
      ppInterface = CInsertionString::CInsertionString((CInsertionString *)v106);
      *(_QWORD *)v83 = v107;
      pIdentifierAuthority = CInsertionString::CInsertionString((CInsertionString *)v107);
      v101 = v108;
      v73 = CInsertionString::CInsertionString((CInsertionString *)v108);
      v116 = v109;
      v74 = CInsertionString::CInsertionString((CInsertionString *)v109);
      v105 = v110;
      v75 = CInsertionString::CInsertionString((CInsertionString *)v110);
      v104 = v111;
      v76 = CInsertionString::CInsertionString((CInsertionString *)v111);
      v117 = v112;
      v77 = CInsertionString::CInsertionString((CInsertionString *)v112);
      v102 = v113;
      v78 = CInsertionString::CInsertionString((CInsertionString *)v113);
      v103 = v114;
      v79 = CInsertionString::CInsertionString((CInsertionString *)v114);
      v91[0] = v115;
      v80 = CInsertionString::CInsertionString((CInsertionString *)v115, *((const unsigned __int16 **)v90 + 12));
      CEventLog::Report(
        *(_QWORD *)v84,
        4,
        WBEM_MC_WBEM_REQUIRES_ENCRYPTION_DENIED,
        v80,
        v79,
        v78,
        v77,
        v76,
        v75,
        v74,
        v73,
        pIdentifierAuthority,
        ppInterface);
    }
  }
  ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>(v93);
  return 0;
}

```

## disassembly

```asm
0x18001f6d0  push    rbp
0x18001f6d2  push    rbx
0x18001f6d3  push    rsi
0x18001f6d4  push    rdi
0x18001f6d5  push    r12
0x18001f6d7  push    r13
0x18001f6d9  push    r14
0x18001f6db  push    r15
0x18001f6dd  lea     rbp, [rsp-108h]
0x18001f6e5  sub     rsp, 208h
0x18001f6ec  mov     rax, cs:__security_cookie
0x18001f6f3  xor     rax, rsp
0x18001f6f6  mov     [rbp+140h+var_48], rax
0x18001f6fd  mov     r14, r9
0x18001f700  mov     [rsp+240h+var_1C8], r8d
0x18001f705  mov     [rbp+140h+var_150], rdx
0x18001f709  mov     r12, rcx
0x18001f70c  mov     [rbp+140h+var_190], rcx
0x18001f710  mov     rbx, [rbp+140h+arg_20]
0x18001f717  xor     eax, eax
0x18001f719  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18001f720  mov     [rbp+140h+hObject], r15
0x18001f724  mov     [rbp+140h+var_1A0], rax
0x18001f728  mov     [rbp+140h+var_1A8], rax
0x18001f72c  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18001f732  test    al, al
0x18001f734  jnz     loc_18001FC1B
0x18001f73a  mov     rsi, [r12+60h]
0x18001f73f  mov     edi, 2
0x18001f744  test    rsi, rsi
0x18001f747  jz      short loc_18001F75F
0x18001f749  mov     rax, r15
0x18001f74c  nop     dword ptr [rax+00h]
0x18001f750  lea     rax, [rax+1]
0x18001f754  cmp     word ptr [rsi+rax*2], 0
0x18001f759  jnz     short loc_18001F750
0x18001f75b  lea     rdi, [rax+2]
0x18001f75f  test    rbx, rbx
0x18001f762  jz      short loc_18001F77D
0x18001f764  mov     rax, r15
0x18001f767  nop     word ptr [rax+rax+00000000h]
0x18001f770  inc     rax
0x18001f773  cmp     word ptr [rbx+rax*2], 0
0x18001f778  jnz     short loc_18001F770
0x18001f77a  add     rdi, rax
0x18001f77d  mov     eax, 2
0x18001f782  mul     rdi
0x18001f785  cmovb   rax, r15
0x18001f789  mov     rcx, rax
0x18001f78c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001f792  mov     [rbp+140h+var_1A8], rax
0x18001f796  mov     r13d, 80070057h
0x18001f79c  mov     r15d, 7FFFFFFEh
0x18001f7a2  mov     r11d, 8007007Ah
0x18001f7a8  test    rax, rax
0x18001f7ab  jz      loc_18001F849
0x18001f7b1  xor     ecx, ecx
0x18001f7b3  mov     [rax], cx
0x18001f7b6  test    rsi, rsi
0x18001f7b9  jz      loc_18001FCD8
0x18001f7bf  mov     r8, [rbp+140h+var_1A8]
0x18001f7c3  test    rdi, rdi
0x18001f7c6  jnz     loc_18002009E
0x18001f7cc  mov     esi, r13d
0x18001f7cf  test    rdi, rdi
0x18001f7d2  jz      short loc_18001F7DA
0x18001f7d4  xor     eax, eax
0x18001f7d6  mov     [r8], ax
0x18001f7da  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001f7e0  mov     edx, esi
0x18001f7e2  mov     rcx, rax
0x18001f7e5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001f7eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7f2  lea     rax, WPP_GLOBAL_Control
0x18001f7f9  cmp     rcx, rax
0x18001f7fc  jz      short loc_18001F822
0x18001f7fe  test    byte ptr [rcx+1Ch], 1
0x18001f802  jz      short loc_18001F822
0x18001f804  cmp     byte ptr [rcx+19h], 2
0x18001f808  jb      short loc_18001F822
0x18001f80a  mov     edx, 20h ; ' '
0x18001f80f  mov     r9d, esi
0x18001f812  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18001f819  mov     rcx, [rcx+10h]
0x18001f81d  call    WPP_SF_d
0x18001f822  mov     r11d, 8007007Ah
0x18001f828  jmp     loc_18001FCD8
0x18001f82d  mov     esi, r11d
0x18001f830  xor     eax, eax
0x18001f832  test    rdi, rdi
0x18001f835  cmovnz  esi, eax
0x18001f838  lea     rcx, [rdx-2]
0x18001f83c  cmovnz  rcx, rdx
0x18001f840  mov     [rcx], ax
0x18001f843  jz      loc_18001FE5D
0x18001f849  lea     rbx, WPP_GLOBAL_Control
0x18001f850  lea     r8, [rbp+140h+var_1A8]
0x18001f854  lea     rcx, [rbp+140h+var_170]
0x18001f858  call    ??$MakeGuard@P6AXPEAG@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@P6AXPEAG@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(ushort *),RefHolder<ushort *>>(void (*)(ushort *),RefHolder<ushort *>)
0x18001f85d  nop
0x18001f85e  cmp     byte ptr [r12+148h], 0
0x18001f867  jnz     loc_180020109
0x18001f86d  lea     rcx, [rbp+140h+hObject]
0x18001f871  call    cs:__imp_?GetAccessToken@@YAJAEAPEAX@Z; GetAccessToken(void * &)
0x18001f877  test    eax, eax
0x18001f879  js      loc_18001FC05
0x18001f87f  mov     rbx, [rbp+140h+hObject]
0x18001f883  mov     [rbp+140h+var_178], rbx
0x18001f887  lea     rdx, [r12+88h]
0x18001f88f  lea     rcx, [rsp+240h+ppInterface]
0x18001f894  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001f89a  nop
0x18001f89b  mov     rax, [rbp+140h+var_190]
0x18001f89f  cmp     dword ptr [rax+0F0h], 0
0x18001f8a6  jz      loc_18001FEC2
0x18001f8ac  lea     rcx, [rsp+240h+ppInterface]
0x18001f8b1  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001f8b7  mov     [rbp+140h+var_1B8], 0
0x18001f8bd  mov     [rbp+140h+TokenHandle], 0
0x18001f8c5  call    cs:__imp_GetCurrentThread
0x18001f8cb  mov     rcx, rax; ThreadHandle
0x18001f8ce  lea     r9, [rbp+140h+TokenHandle]; TokenHandle
0x18001f8d2  mov     edx, 4; DesiredAccess
0x18001f8d7  mov     r8d, 1; OpenAsSelf
0x18001f8dd  call    cs:__imp_OpenThreadToken
0x18001f8e3  test    eax, eax
0x18001f8e5  jnz     loc_18001FF39
0x18001f8eb  call    cs:__imp_GetLastError
0x18001f8f1  cmp     eax, 3F0h
0x18001f8f6  jnz     loc_18001FEF8
0x18001f8fc  xor     esi, esi
0x18001f8fe  xor     dil, dil
0x18001f901  mov     [rsp+240h+ppInterface], rsi
0x18001f906  lea     rdx, [rsp+240h+ppInterface]; ppInterface
0x18001f90b  lea     rcx, IID_IServerSecurity; riid
0x18001f912  call    cs:__imp_CoGetCallContext
0x18001f918  test    eax, eax
0x18001f91a  jnz     short loc_18001F945
0x18001f91c  mov     rcx, [rsp+240h+ppInterface]
0x18001f921  mov     rax, [rcx]
0x18001f924  mov     rax, [rax+30h]
0x18001f928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f92d  cmp     eax, 1
0x18001f930  setz    dil
0x18001f934  mov     rcx, [rsp+240h+ppInterface]
0x18001f939  mov     rax, [rcx]
0x18001f93c  mov     rax, [rax+10h]
0x18001f940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f945  mov     byte ptr [rbp+140h+var_1B8], dil
0x18001f949  test    dil, dil
0x18001f94c  jnz     loc_180020305
0x18001f952  test    esi, esi
0x18001f954  js      loc_180020311
0x18001f95a  or      [rsp+240h+var_1C8], 1
0x18001f95f  mov     rdi, [rbp+140h+hObject]
0x18001f963  xor     ecx, ecx
0x18001f965  mov     [rsp+240h+ppInterface], rcx
0x18001f96a  mov     dword ptr [rbp+140h+pIdentifierAuthority], ecx
0x18001f970  mov     word ptr [rbp+140h+pIdentifierAuthority+4], 500h
0x18001f979  mov     [rbp+140h+var_1C0], 1
0x18001f980  lea     rax, [rsp+240h+ppInterface]
0x18001f985  mov     [rsp+240h+pSid], rax; pSid
0x18001f98a  mov     [rsp+240h+nSubAuthority7], ecx; nSubAuthority7
0x18001f98e  mov     [rsp+240h+nSubAuthority6], ecx; nSubAuthority6
0x18001f992  mov     [rsp+240h+nSubAuthority5], ecx; nSubAuthority5
0x18001f996  mov     [rsp+240h+nSubAuthority4], ecx; nSubAuthority4
0x18001f99a  mov     [rsp+240h+nSubAuthority3], ecx; nSubAuthority3
0x18001f99e  mov     [rsp+240h+nSubAuthority2], ecx; nSubAuthority2
0x18001f9a2  xor     r9d, r9d; nSubAuthority1
0x18001f9a5  mov     r8d, 4; nSubAuthority0
0x18001f9ab  mov     dl, 1; nSubAuthorityCount
0x18001f9ad  lea     rcx, [rbp+140h+pIdentifierAuthority]; pIdentifierAuthority
0x18001f9b4  call    cs:__imp_AllocateAndInitializeSid
0x18001f9ba  test    eax, eax
0x18001f9bc  jz      short loc_18001FA15
0x18001f9be  mov     rdx, [rsp+240h+ppInterface]
0x18001f9c3  lea     rcx, [rbp+140h+var_188]
0x18001f9c7  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18001f9cd  nop
0x18001f9ce  mov     rcx, [rsp+240h+ppInterface]; pSid
0x18001f9d3  call    cs:__imp_FreeSid
0x18001f9d9  lea     rcx, [rbp+140h+var_188]
0x18001f9dd  call    cs:__imp_?GetStatus@CNtSid@@QEAAKXZ; CNtSid::GetStatus(void)
0x18001f9e3  test    eax, eax
0x18001f9e5  jnz     short loc_18001FA0B
0x18001f9e7  lea     r8, [rbp+140h+var_1C0]
0x18001f9eb  lea     rdx, [rbp+140h+var_188]
0x18001f9ef  mov     rcx, rdi
0x18001f9f2  call    cs:__imp_?IsUserInGroup@CNtSecurity@@SAHPEAXAEAVCNtSid@@PEAH@Z; CNtSecurity::IsUserInGroup(void *,CNtSid &,int *)
0x18001f9f8  test    eax, eax
0x18001f9fa  jz      loc_1800200E0
0x18001fa00  xor     eax, eax
0x18001fa02  cmp     [rbp+140h+var_1C0], eax
0x18001fa05  setz    al
0x18001fa08  mov     [rbp+140h+var_1C0], eax
0x18001fa0b  lea     rcx, [rbp+140h+var_188]
0x18001fa0f  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x18001fa15  cmp     [rbp+140h+var_1C0], 0
0x18001fa19  jz      loc_18001FAB5
0x18001fa1f  lea     rax, [rsp+240h+ppInterface]
0x18001fa24  mov     [rsp+240h+pSid], rax; pSid
0x18001fa29  xor     eax, eax
0x18001fa2b  mov     [rsp+240h+nSubAuthority7], eax; nSubAuthority7
0x18001fa2f  mov     [rsp+240h+nSubAuthority6], eax; nSubAuthority6
0x18001fa33  mov     [rsp+240h+nSubAuthority5], eax; nSubAuthority5
0x18001fa37  mov     [rsp+240h+nSubAuthority4], eax; bool
0x18001fa3b  mov     [rsp+240h+nSubAuthority3], eax; nSubAuthority3
0x18001fa3f  mov     [rsp+240h+nSubAuthority2], eax; nSubAuthority2
0x18001fa43  xor     r9d, r9d; nSubAuthority1
0x18001fa46  mov     r8d, 2; nSubAuthority0
0x18001fa4c  mov     dl, 1; nSubAuthorityCount
0x18001fa4e  lea     rcx, [rbp+140h+pIdentifierAuthority]; pIdentifierAuthority
0x18001fa55  call    cs:__imp_AllocateAndInitializeSid
0x18001fa5b  test    eax, eax
0x18001fa5d  jz      short loc_18001FAAB
0x18001fa5f  mov     rdx, [rsp+240h+ppInterface]
0x18001fa64  lea     rcx, [rbp+140h+var_188]
0x18001fa68  call    cs:__imp_??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18001fa6e  nop
0x18001fa6f  mov     rcx, [rsp+240h+ppInterface]; pSid
0x18001fa74  call    cs:__imp_FreeSid
0x18001fa7a  lea     rcx, [rbp+140h+var_188]
0x18001fa7e  call    cs:__imp_?GetStatus@CNtSid@@QEAAKXZ; CNtSid::GetStatus(void)
0x18001fa84  test    eax, eax
0x18001fa86  jnz     short loc_18001FAA1
0x18001fa88  lea     r8, [rbp+140h+var_1C0]
0x18001fa8c  lea     rdx, [rbp+140h+var_188]
0x18001fa90  mov     rcx, rdi
0x18001fa93  call    cs:__imp_?IsUserInGroup@CNtSecurity@@SAHPEAXAEAVCNtSid@@PEAH@Z; CNtSecurity::IsUserInGroup(void *,CNtSid &,int *)
0x18001fa99  test    eax, eax
0x18001fa9b  jz      loc_18001FEB6
0x18001faa1  lea     rcx, [rbp+140h+var_188]
0x18001faa5  call    cs:__imp_??1CNtSid@@QEAA@XZ; CNtSid::~CNtSid(void)
0x18001faab  cmp     [rbp+140h+var_1C0], 0
0x18001faaf  jnz     loc_1800200EA
0x18001fab5  mov     eax, [rsp+240h+var_1C8]
0x18001fab9  mov     [rsp+240h+var_1C8], eax
0x18001fabd  mov     edi, 7
0x18001fac2  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18001fac9  test    r14, r14
0x18001facc  jz      short loc_18001FAE1
0x18001face  mov     rcx, r8
0x18001fad1  lea     rcx, [rcx+1]
0x18001fad5  cmp     word ptr [r14+rcx*2], 0
0x18001fadb  jnz     short loc_18001FAD1
0x18001fadd  lea     rdi, [rcx+7]
0x18001fae1  mov     eax, 2
0x18001fae6  mul     rdi
0x18001fae9  cmovb   rax, r8
0x18001faed  mov     rcx, rax
0x18001faf0  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001faf6  mov     [rbp+140h+var_1A0], rax
0x18001fafa  test    rax, rax
0x18001fafd  jnz     loc_18001FC40
0x18001fb03  mov     edi, [rsp+240h+var_1C8]
0x18001fb07  lea     r8, [rbp+140h+var_1A0]
0x18001fb0b  lea     rcx, [rbp+140h+var_140]
0x18001fb0f  call    ??$MakeGuard@P6AXPEAG@ZV?$RefHolder@PEAG@@@@YA?AV?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@P6AXPEAG@ZV?$RefHolder@PEAG@@@Z; MakeGuard<void (*)(ushort *),RefHolder<ushort *>>(void (*)(ushort *),RefHolder<ushort *>)
0x18001fb14  nop
0x18001fb15  lea     rdx, [r12+88h]
0x18001fb1d  lea     rcx, [rbp+140h+var_158]
0x18001fb21  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001fb27  nop
0x18001fb28  mov     [rbp+140h+var_1C0], 0
0x18001fb2f  lea     rax, [rbp+140h+var_1C0]
0x18001fb33  mov     qword ptr [rsp+240h+nSubAuthority5], rax; unsigned int *
0x18001fb38  mov     rax, [rbp+140h+hObject]
0x18001fb3c  mov     qword ptr [rsp+240h+nSubAuthority3], rax; TokenHandle
0x18001fb41  mov     rax, [rbp+140h+var_1A8]
0x18001fb45  mov     qword ptr [rsp+240h+nSubAuthority2], rax; unsigned __int16 *
0x18001fb4a  mov     r9, [rbp+140h+var_1A0]; unsigned __int16 *
0x18001fb4e  mov     r8d, edi; unsigned int
0x18001fb51  mov     rdx, [rbp+140h+var_150]; struct CNtSecurityDescriptor *
0x18001fb55  mov     rcx, [rbp+140h+var_190]; this
0x18001fb59  call    ?WMIAccessCheckAndAudit@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1PEAX_NPEAK@Z; CWbemNamespace::WMIAccessCheckAndAudit(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,void *,bool,ulong *)
0x18001fb5e  test    al, al
0x18001fb60  jnz     short loc_18001FBA7
0x18001fb62  mov     rcx, [rbp+140h+hObject]
0x18001fb66  call    cs:__imp_?IsAdmin@@YAHPEAX@Z; IsAdmin(void *)
0x18001fb6c  cmp     eax, 1
0x18001fb6f  jz      short loc_18001FBAD
0x18001fb71  lea     rcx, [rbp+140h+var_158]
0x18001fb75  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001fb7b  nop
0x18001fb7c  lea     rcx, [rbp+140h+var_140]
0x18001fb80  call    ??1?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort *),RefHolder<ushort *>>::~ScopeGuardImpl1<void (*)(ushort *),RefHolder<ushort *>>(void)
0x18001fb85  nop
0x18001fb86  lea     rcx, [rbp+140h+var_1B8]; this
0x18001fb8a  call    ??1CRevertToSelfAndCleanup@@QEAA@XZ; CRevertToSelfAndCleanup::~CRevertToSelfAndCleanup(void)
0x18001fb8f  nop
0x18001fb90  lea     rcx, [rbp+140h+var_178]; this
0x18001fb94  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x18001fb99  nop
0x18001fb9a  lea     rcx, [rbp+140h+var_170]
0x18001fb9e  call    ??1?$ScopeGuardImpl1@P6AXPEAG@ZV?$RefHolder@PEAG@@@@QEAA@XZ; ScopeGuardImpl1<void (*)(ushort *),RefHolder<ushort *>>::~ScopeGuardImpl1<void (*)(ushort *),RefHolder<ushort *>>(void)
0x18001fba3  xor     al, al
0x18001fba5  jmp     short loc_18001FC1D
0x18001fba7  cmp     [rbp+140h+var_1C0], 0
0x18001fbab  jz      short loc_18001FB62
0x18001fbad  lea     rcx, [rbp+140h+var_158]
  ... truncated ...
```
