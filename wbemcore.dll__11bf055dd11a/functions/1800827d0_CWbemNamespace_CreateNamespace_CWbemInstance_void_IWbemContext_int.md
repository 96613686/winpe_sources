# CWbemNamespace::CreateNamespace(CWbemInstance *,void *,IWbemContext *,int)

- ea: `0x1800827d0`
- end: `0x180083a78`
- name: `?CreateNamespace@CWbemNamespace@@IEAAJPEAVCWbemInstance@@PEAXPEAUIWbemContext@@H@Z`
- size: `4776`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, struct CWbemInstance *@<rdx>, void *@<r8>, struct IWbemContext *@<r9>, int)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180049d34`

## callees

- `0x18000b104`
- `0x18000b140`
- `0x18000e950`
- `0x18000fa74`
- `0x18001cce0`
- `0x18001d390`
- `0x18001f6d0`
- `0x180021520`
- `0x180024098`
- `0x18002ab80`
- `0x18002ca8c`
- `0x18002dd24`
- `0x18002fee4`
- `0x180036db0`
- `0x18003cfe0`
- `0x18004b88c`
- `0x18004b934`
- `0x1800604d0`
- `0x180060ba4`
- `0x1800708bc`
- `0x1800827d0`
- `0x180086544`
- `0x18008be98`
- `0x180096504`
- `0x18009a4bc`
- `0x1800be898`
- `0x1800bedc0`
- `0x1800bef34`
- `0x1800da010`

## import_xrefs

- `msvcrt!isdigit` at `0x1800834bb`
- `msvcrt!isdigit` at `0x1800834d1`
- `msvcrt!isdigit` at `0x1800834e7`
- `msvcrt!isdigit` at `0x1800834bb`
- `msvcrt!isdigit` at `0x1800834d1`
- `msvcrt!isdigit` at `0x1800834e7`
- `msvcrt!_wcsnicmp` at `0x1800834a5`
- `msvcrt!_wcsnicmp` at `0x1800834a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082af1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180082ae7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180082ae7`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180082a65`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180082a65`
- `wbemcomn!_IsValidElementName` at `0x18008290d`
- `wbemcomn!_IsValidElementName` at `0x18008290d`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x180082c82`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@PEAX@Z` at `0x180082c82`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180082d50`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180082d50`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180082dda`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180082dda`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x180083059`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x180083059`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x180082885`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x1800828d3`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x180082885`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x1800828d3`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18008284d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18008289b`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18008284d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18008289b`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800828e9`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800829ad`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800830bc`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083180`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083193`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800832cb`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800832de`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800833c8`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083566`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18008364a`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18008374e`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083832`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083903`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800828e9`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800829ad`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800830bc`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083180`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083193`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800832cb`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800832de`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x1800833c8`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083566`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18008364a`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18008374e`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083832`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180083903`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008311f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008312e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008344b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008345a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800835db`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800835ea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800836bb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800836ca`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800838aa`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800838b9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008396a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180083979`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800839bd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180083a5d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008311f`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008312e`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008344b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008345a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800835db`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800835ea`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800836bb`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800836ca`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800838aa`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800838b9`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18008396a`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180083979`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800839bd`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180083a5d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180082c6c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800831c3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180082c6c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800831c3`
- `wbemcomn!GetMemLogObject` at `0x180082917`
- `wbemcomn!GetMemLogObject` at `0x180082961`
- `wbemcomn!GetMemLogObject` at `0x1800829ea`
- `wbemcomn!GetMemLogObject` at `0x180082a6f`
- `wbemcomn!GetMemLogObject` at `0x180082b0a`
- `wbemcomn!GetMemLogObject` at `0x180082b66`
- `wbemcomn!GetMemLogObject` at `0x180082bc9`
- `wbemcomn!GetMemLogObject` at `0x180082c16`
- `wbemcomn!GetMemLogObject` at `0x180082c9a`
- `wbemcomn!GetMemLogObject` at `0x180082cf7`
- `wbemcomn!GetMemLogObject` at `0x180082d6c`
- `wbemcomn!GetMemLogObject` at `0x180082dfa`
- `wbemcomn!GetMemLogObject` at `0x180082e57`
- `wbemcomn!GetMemLogObject` at `0x180082eb8`
- `wbemcomn!GetMemLogObject` at `0x180082f6f`
- `wbemcomn!GetMemLogObject` at `0x180083082`
- `wbemcomn!GetMemLogObject` at `0x180083213`
- `wbemcomn!GetMemLogObject` at `0x180083276`
- `wbemcomn!GetMemLogObject` at `0x1800832f9`
- `wbemcomn!GetMemLogObject` at `0x18008338f`
- `wbemcomn!GetMemLogObject` at `0x18008352d`
- `wbemcomn!GetMemLogObject` at `0x180083611`
- `wbemcomn!GetMemLogObject` at `0x180083709`
- `wbemcomn!GetMemLogObject` at `0x1800837a4`
- `wbemcomn!GetMemLogObject` at `0x1800837f9`
- `wbemcomn!GetMemLogObject` at `0x1800838c9`
- `wbemcomn!GetMemLogObject` at `0x1800839c8`
- `wbemcomn!GetMemLogObject` at `0x180083a0f`
- `wbemcomn!GetMemLogObject` at `0x180082917`
- `wbemcomn!GetMemLogObject` at `0x180082961`
- `wbemcomn!GetMemLogObject` at `0x1800829ea`
- `wbemcomn!GetMemLogObject` at `0x180082a6f`
- `wbemcomn!GetMemLogObject` at `0x180082b0a`
- `wbemcomn!GetMemLogObject` at `0x180082b66`
- `wbemcomn!GetMemLogObject` at `0x180082bc9`
- `wbemcomn!GetMemLogObject` at `0x180082c16`
- `wbemcomn!GetMemLogObject` at `0x180082c9a`
- `wbemcomn!GetMemLogObject` at `0x180082cf7`
- `wbemcomn!GetMemLogObject` at `0x180082d6c`
- `wbemcomn!GetMemLogObject` at `0x180082dfa`
- `wbemcomn!GetMemLogObject` at `0x180082e57`
- `wbemcomn!GetMemLogObject` at `0x180082eb8`
- `wbemcomn!GetMemLogObject` at `0x180082f6f`
- `wbemcomn!GetMemLogObject` at `0x180083082`
- `wbemcomn!GetMemLogObject` at `0x180083213`
- `wbemcomn!GetMemLogObject` at `0x180083276`
- `wbemcomn!GetMemLogObject` at `0x1800832f9`
- `wbemcomn!GetMemLogObject` at `0x18008338f`
- `wbemcomn!GetMemLogObject` at `0x18008352d`
- `wbemcomn!GetMemLogObject` at `0x180083611`
- `wbemcomn!GetMemLogObject` at `0x180083709`
- `wbemcomn!GetMemLogObject` at `0x1800837a4`
- `wbemcomn!GetMemLogObject` at `0x1800837f9`
- `wbemcomn!GetMemLogObject` at `0x1800838c9`
- `wbemcomn!GetMemLogObject` at `0x1800839c8`
- `wbemcomn!GetMemLogObject` at `0x180083a0f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082927`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082971`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800829fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082a7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082b15`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082b76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082bd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082c26`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082caa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082d07`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082d7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082e0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082e62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082ec3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082f7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008308f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008321f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083282`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083305`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008339b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083539`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008361d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083715`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800837af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083805`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800838d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800839d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083a1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082927`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082971`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800829fa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082a7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082b15`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082b76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082bd4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082c26`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082caa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082d07`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082d7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082e0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082e62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082ec3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180082f7a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008308f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008321f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083282`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083305`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008339b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083539`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008361d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083715`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800837af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180083805`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800838d6`

## string_xrefs

- `0x1800828ad`: `__RELPATH`
- `0x1800829d1`: `Write (PutInstance)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall CWbemNamespace::CreateNamespace(
        CWbemNamespace *this,
        struct IWbemClassObject *a2,
        void *a3,
        struct IWbemContext *a4,
        int a5)
{
  wchar_t *LPWSTR; // rbx
  CMemoryLog *v9; // rax
  signed int NewSession; // ebx
  CClientCnt *v11; // rcx
  __int64 v12; // rdx
  CMemoryLog *v13; // rax
  const unsigned __int16 *v14; // rax
  __int64 v15; // rdx
  unsigned __int16 *v16; // r15
  CMemoryLog *v17; // rax
  __int64 v18; // r9
  CMemoryLog *v19; // rax
  CClientCnt *v20; // rcx
  __int64 v21; // rdx
  signed int LastError; // eax
  CMemoryLog *v23; // rax
  __int64 v24; // r9
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  struct IWmiDbSession *v28; // rax
  struct CNtSecurityDescriptor *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  struct IWmiDbSession *Dacl; // rax
  CMemoryLog *v33; // rax
  struct IWmiDbSession *Sacl; // rax
  CMemoryLog *v35; // rax
  CClientCnt *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  CMemoryLog *v39; // rax
  CMemoryLog *v40; // rax
  struct IWmiDbSession *v41; // r12
  CMemoryLog *v42; // rax
  const struct _GUID *v43; // r8
  int IsLocalMachine; // eax
  int v45; // ebx
  CMemoryLog *v46; // rax
  unsigned int v47; // eax
  struct CWbemNamespace *Instance; // rax
  struct IWmiDbHandle **v50; // rbx
  int v51; // r15d
  __int64 v52; // rcx
  __int64 v53; // rax
  unsigned __int16 *v54; // rax
  __int64 v55; // rcx
  unsigned __int64 v56; // r13
  struct _ACL *v57; // rax
  unsigned __int16 *v58; // r15
  const unsigned __int16 *v59; // r8
  int v60; // r13d
  CMemoryLog *v61; // rax
  int v62; // r13d
  CMemoryLog *v63; // rax
  const unsigned __int16 *v64; // rax
  int v65; // r13d
  CMemoryLog *v66; // rax
  int v67; // r15d
  CMemoryLog *v68; // rax
  unsigned int v69; // eax
  bool v70; // r15
  __int64 v71; // rax
  int v72; // r15d
  CMemoryLog *v73; // rax
  unsigned int v74; // eax
  CMemoryLog *v75; // rax
  unsigned int v76; // eax
  CMemoryLog *v77; // rax
  unsigned int v78; // eax
  CMemoryLog *v79; // rax
  CMemoryLog *v80; // rax
  unsigned int v81; // eax
  CMemoryLog *v82; // rax
  unsigned int v83; // eax
  CMemoryLog *v84; // rax
  CMemoryLog *MemLogObject; // rax
  bool v86; // [rsp+28h] [rbp-150h]
  bool v87; // [rsp+60h] [rbp-118h] BYREF
  struct IWmiDbSession *v88; // [rsp+68h] [rbp-110h] BYREF
  bool v89; // [rsp+70h] [rbp-108h]
  WINBOOL bDaclPresent[2]; // [rsp+78h] [rbp-100h] BYREF
  WINBOOL bDaclDefaulted[2]; // [rsp+80h] [rbp-F8h] BYREF
  struct IWmiDbSession *v92; // [rsp+88h] [rbp-F0h] BYREF
  struct CNtSecurityDescriptor *v93; // [rsp+90h] [rbp-E8h] BYREF
  _BYTE v94[24]; // [rsp+98h] [rbp-E0h] BYREF
  _BYTE v95[32]; // [rsp+B0h] [rbp-C8h] BYREF
  wchar_t *String1; // [rsp+D0h] [rbp-A8h]
  VARIANTARG pvarg; // [rsp+D8h] [rbp-A0h] BYREF
  PACL pDacl[2]; // [rsp+F0h] [rbp-88h] BYREF
  _BYTE v99[24]; // [rsp+100h] [rbp-78h] BYREF
  _BYTE v100[96]; // [rsp+118h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  CVar::CVar((CVar *)v95);
  if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _BYTE *))a2->lpVtbl[3].CompareTo)(
         a2,
         L"Name",
         v95) < 0
    || CVar::IsNull((CVar *)v95) )
  {
    MemLogObject = GetMemLogObject();
    NewSession = -2147217394;
    CMemoryLog::Write(MemLogObject, -2147217394);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749902LL);
    }
    goto LABEL_205;
  }
  CVar::CVar((CVar *)v100);
  if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _BYTE *))a2->lpVtbl[3].CompareTo)(
         a2,
         L"__RELPATH",
         v100) < 0
    || CVar::IsNull((CVar *)v100) )
  {
    v84 = GetMemLogObject();
    NewSession = -2147217394;
    CMemoryLog::Write(v84, -2147217394);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_194;
    }
    v12 = 184;
LABEL_199:
    v18 = 2147749902LL;
LABEL_200:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v18);
    goto LABEL_194;
  }
  LPWSTR = CVar::GetLPWSTR((CVar *)v95);
  String1 = LPWSTR;
  if ( !_IsValidElementName(LPWSTR, g_PathLimit - 19, L"-") )
  {
    v9 = GetMemLogObject();
    NewSession = -2147217394;
    CMemoryLog::Write(v9, -2147217394);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_194;
    }
    v12 = 185;
    goto LABEL_199;
  }
  if ( *LPWSTR == 95 )
  {
    v13 = GetMemLogObject();
    NewSession = -2147217394;
    CMemoryLog::Write(v13, -2147217394);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_194;
    }
    v12 = 186;
    goto LABEL_199;
  }
  v14 = CVar::GetLPWSTR((CVar *)v100);
  v16 = (unsigned __int16 *)v14;
  if ( !a5
    && !CWbemNamespace::InnerAllowedWithSD(
          this,
          (CWbemNamespace *)((char *)this + 216),
          4u,
          L"Write (PutInstance)",
          v14,
          v86,
          1) )
  {
    v17 = GetMemLogObject();
    NewSession = -2147217405;
    CMemoryLog::Write(v17, -2147217405);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_194;
    }
    v12 = 187;
    v18 = 2147749891LL;
    goto LABEL_200;
  }
  v93 = 0;
  MakeGuard<void (*)(CNtSecurityDescriptor const *),RefHolder<CNtSecurityDescriptor *>>(
    (__int64)v94,
    v15,
    (__int64)&v93);
  if ( a3 )
  {
    if ( !IsValidSecurityDescriptor(a3) )
    {
      v19 = GetMemLogObject();
      NewSession = -2147217400;
      CMemoryLog::Write(v19, -2147217400);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_193;
      }
      v21 = 188;
      goto LABEL_57;
    }
    bDaclPresent[0] = 0;
    bDaclDefaulted[0] = 0;
    pDacl[0] = 0;
    if ( !GetSecurityDescriptorDacl(a3, bDaclPresent, pDacl, bDaclDefaulted) )
    {
      LastError = GetLastError();
      NewSession = LastError;
      if ( LastError > 0 )
        NewSession = (unsigned __int16)LastError | 0x80070000;
      if ( NewSession < 0 )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, NewSession);
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_193;
      }
      v21 = 189;
LABEL_40:
      v24 = (unsigned int)NewSession;
LABEL_41:
      WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v24);
LABEL_193:
      ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>((__int64)v94);
LABEL_194:
      CVar::~CVar((CVar *)v100);
LABEL_205:
      CVar::~CVar((CVar *)v95);
      return (unsigned int)NewSession;
    }
    if ( !bDaclPresent[0] )
    {
      v25 = GetMemLogObject();
      NewSession = -2147217400;
      CMemoryLog::Write(v25, -2147217400);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_193;
      }
      v21 = 190;
      goto LABEL_57;
    }
    v87 = 0;
    NewSession = HasInheritedAces(a3, &v87);
    if ( NewSession < 0 )
    {
      v26 = GetMemLogObject();
      CMemoryLog::Write(v26, NewSession);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_193;
      }
      v21 = 191;
      goto LABEL_40;
    }
    if ( v87 )
    {
      v27 = GetMemLogObject();
      NewSession = -2147217400;
      CMemoryLog::Write(v27, -2147217400);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_193;
      }
      v21 = 192;
LABEL_57:
      v24 = 2147749896LL;
      goto LABEL_41;
    }
    v28 = (struct IWmiDbSession *)CWin32DefaultArena::WbemMemAlloc(0x10u);
    v88 = v28;
    if ( v28 )
      v29 = CNtSecurityDescriptor::CNtSecurityDescriptor(v28, a3);
    else
      v29 = 0;
    v93 = v29;
    if ( !v29 )
    {
      v30 = GetMemLogObject();
      NewSession = -2147217402;
      CMemoryLog::Write(v30, -2147217402);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_193;
      }
      v21 = 193;
      v24 = 2147749894LL;
      goto LABEL_41;
    }
    if ( !(unsigned int)SetDefaultOwner(v29) )
    {
      v31 = GetMemLogObject();
      NewSession = -2147217407;
      CMemoryLog::Write(v31, -2147217407);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_193;
      }
      v21 = 194;
      v24 = 2147749889LL;
      goto LABEL_41;
    }
    Dacl = CNtSecurityDescriptor::GetDacl(v93);
    if ( Dacl )
    {
      v88 = Dacl;
      if ( !(unsigned int)IsValidAclForNSSecurity(Dacl) )
      {
        v33 = GetMemLogObject();
        NewSession = -2147217400;
        CMemoryLog::Write(v33, -2147217400);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            195,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749896LL);
        }
        goto LABEL_77;
      }
      CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v88);
    }
    Sacl = CNtSecurityDescriptor::GetSacl(v93);
    if ( Sacl )
    {
      v88 = Sacl;
      if ( !(unsigned int)IsValidAclForNSSecurity(Sacl) )
      {
        v35 = GetMemLogObject();
        NewSession = -2147217400;
        CMemoryLog::Write(v35, -2147217400);
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v37 = 196;
        v38 = 2147749896LL;
LABEL_85:
        WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v38);
LABEL_77:
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v88);
        goto LABEL_193;
      }
      NewSession = CheckForSaclPriv();
      if ( NewSession < 0 )
      {
        v39 = GetMemLogObject();
        CMemoryLog::Write(v39, NewSession);
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v37 = 197;
        v38 = (unsigned int)NewSession;
        goto LABEL_85;
      }
      CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>(&v88);
    }
  }
  v88 = 0;
  v92 = 0;
  NewSession = CRepository::GetNewSession(&v88);
  if ( NewSession < 0 )
  {
    v40 = GetMemLogObject();
    CMemoryLog::Write(v40, NewSession);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_193;
    }
    v21 = 198;
    goto LABEL_40;
  }
  v41 = v88;
  (**(void (__fastcall ***)(struct IWmiDbSession *, GUID *, struct IWmiDbSession **))v88)(
    v88,
    &IID_IWmiDbSessionEx,
    &v92);
  if ( v92 )
  {
    (*(void (__fastcall **)(struct IWmiDbSession *))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = v92;
  }
  v88 = v41;
  if ( v92 )
  {
    NewSession = (*(__int64 (__fastcall **)(struct IWmiDbSession *, _QWORD))(*(_QWORD *)v92 + 112LL))(v92, 0);
    if ( NewSession < 0 )
    {
      v42 = GetMemLogObject();
      CMemoryLog::Write(v42, NewSession);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          199,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)NewSession);
      }
LABEL_192:
      CReleaseMe::release((CReleaseMe *)&v88);
      goto LABEL_193;
    }
  }
  MakeGuard<void (*)(IWmiDbSessionEx *),IWmiDbSessionEx *>(v99);
  VariantInit(&pvarg);
  if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a4->lpVtbl->GetValue)(
         a4,
         L"__GroupOperationId",
         0,
         &pvarg) >= 0 )
  {
    IsLocalMachine = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
    CPublishWMIOperationEvent::PublishRepUpdate(
      pvarg.cyVal.Lo,
      v16,
      0,
      a4,
      *((_DWORD *)this + 76),
      *((unsigned __int16 **)this + 36),
      *((_QWORD *)this + 37),
      IsLocalMachine);
  }
  v45 = CRepository::PutObject(v41, *((struct IWmiDbHandle **)this + 8), v43, a2, 0);
  if ( v45 >= 0 )
  {
    Instance = CWbemNamespace::CreateInstance();
    v50 = (struct IWmiDbHandle **)Instance;
    if ( Instance )
    {
      *(_QWORD *)bDaclPresent = Instance;
      v51 = 2;
      v52 = *((_QWORD *)this + 12);
      if ( v52 )
      {
        v53 = -1;
        do
          ++v53;
        while ( *(_WORD *)(v52 + 2 * v53) );
        v51 = v53 + 2;
      }
      if ( CVar::GetLPWSTR((CVar *)v95) )
      {
        v54 = CVar::GetLPWSTR((CVar *)v95);
        v55 = -1;
        do
          ++v55;
        while ( v54[v55] );
        v51 += v55;
      }
      v56 = v51;
      *(_QWORD *)bDaclDefaulted = v51;
      v57 = (struct _ACL *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v51, 2u));
      v58 = (unsigned __int16 *)v57;
      if ( v57 )
      {
        pDacl[0] = v57;
        pDacl[1] = 0;
        *(_WORD *)&v57->AclRevision = 0;
        v59 = (const unsigned __int16 *)*((_QWORD *)this + 12);
        if ( v59 )
        {
          v60 = StringCchCopyW((unsigned __int16 *)v57, v56, v59);
          if ( v60 < 0 )
          {
            v61 = GetMemLogObject();
            CMemoryLog::Write(v61, v60);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                201,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)v60);
            }
          }
          v62 = StringCchCatW(v58, *(unsigned __int64 *)bDaclDefaulted, L"\\");
          if ( v62 < 0 )
          {
            v63 = GetMemLogObject();
            CMemoryLog::Write(v63, v62);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                202,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)v62);
            }
          }
          v56 = *(_QWORD *)bDaclDefaulted;
        }
        if ( CVar::GetLPWSTR((CVar *)v95) )
        {
          v64 = CVar::GetLPWSTR((CVar *)v95);
          v65 = StringCchCatW(v58, v56, v64);
          if ( v65 < 0 )
          {
            v66 = GetMemLogObject();
            CMemoryLog::Write(v66, v65);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                203,
                WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                (unsigned int)v65);
            }
          }
        }
        v67 = CWbemNamespace::Initialize(
                (CWbemNamespace *)v50,
                v58,
                *((unsigned __int16 **)this + 14),
                0,
                0,
                0,
                1,
                0,
                0xFFFFFFFF,
                1,
                v41,
                0);
        if ( v67 >= 0 )
        {
          CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>((void **)pDacl);
          v70 = 0;
          v89 = 0;
          v71 = -1;
          do
            ++v71;
          while ( String1[v71] );
          if ( v71 == 6 && !_wcsnicmp(String1, L"ms_", 3u) && isdigit(String1[3]) && isdigit(String1[4]) )
          {
            if ( isdigit(String1[5]) )
              v70 = 1;
            v89 = v70;
          }
          v72 = CRepository::EnsureNsSystemInstances(v41, v50[7], v41, *((struct IWmiDbHandle **)this + 7), v93, 1, v70);
          if ( v72 >= 0 )
          {
            v72 = CWbemNamespace::InitializeSD(this, v41);
            if ( v72 >= 0 )
            {
              CWbemNamespace::Release((CWbemNamespace *)v50);
              *(_QWORD *)bDaclPresent = 0;
              _variant_t::~_variant_t(&pvarg);
              NewSession = CWbemNamespace::DecorateObject(this, a2);
              if ( NewSession >= 0 )
              {
                v99[0] = 1;
                if ( v92 )
                {
                  NewSession = (*(__int64 (__fastcall **)(struct IWmiDbSession *, _QWORD))(*(_QWORD *)v92 + 128LL))(
                                 v92,
                                 0);
                  if ( NewSession < 0 )
                  {
                    v79 = GetMemLogObject();
                    CMemoryLog::Write(v79, NewSession);
                  }
                }
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    211,
                    WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    (unsigned int)NewSession);
                }
              }
              else
              {
                v77 = GetMemLogObject();
                CMemoryLog::Write(v77, -1);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v78 = (unsigned int)CVar::GetLPWSTR((CVar *)v95);
                  WPP_SF_SD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    210,
                    (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                    v78,
                    NewSession);
                }
              }
              ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v99);
              goto LABEL_192;
            }
            v75 = GetMemLogObject();
            CMemoryLog::Write(v75, -1);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v76 = (unsigned int)CVar::GetLPWSTR((CVar *)v95);
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                207,
                (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                v76,
                v72);
            }
          }
          else
          {
            v73 = GetMemLogObject();
            CMemoryLog::Write(v73, -1);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v74 = (unsigned int)CVar::GetLPWSTR((CVar *)v95);
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                206,
                (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
                v74,
                v72);
            }
          }
          CWbemNamespace::Release((CWbemNamespace *)v50);
          *(_QWORD *)bDaclPresent = 0;
          _variant_t::~_variant_t(&pvarg);
          ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v99);
          CReleaseMe::release((CReleaseMe *)&v88);
          ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>((__int64)v94);
          CVar::~CVar((CVar *)v100);
          CVar::~CVar((CVar *)v95);
          return (unsigned int)v72;
        }
        v68 = GetMemLogObject();
        CMemoryLog::Write(v68, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v69 = (unsigned int)CVar::GetLPWSTR((CVar *)v95);
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            204,
            (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            v69,
            v67);
        }
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>((void **)pDacl);
        CWbemNamespace::Release((CWbemNamespace *)v50);
        *(_QWORD *)bDaclPresent = 0;
        _variant_t::~_variant_t(&pvarg);
        ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v99);
        CReleaseMe::release((CReleaseMe *)&v88);
        ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>((__int64)v94);
        CVar::~CVar((CVar *)v100);
        CVar::~CVar((CVar *)v95);
        return (unsigned int)v67;
      }
      else
      {
        v80 = GetMemLogObject();
        CMemoryLog::Write(v80, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v81 = (unsigned int)CVar::GetLPWSTR((CVar *)v95);
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            205,
            (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            v81,
            6);
        }
        CWbemNamespace::Release((CWbemNamespace *)v50);
        *(_QWORD *)bDaclPresent = 0;
        _variant_t::~_variant_t(&pvarg);
        ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v99);
        CReleaseMe::release((CReleaseMe *)&v88);
        ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>((__int64)v94);
        CVar::~CVar((CVar *)v100);
        CVar::~CVar((CVar *)v95);
        return 2147749894LL;
      }
    }
    else
    {
      v82 = GetMemLogObject();
      CMemoryLog::Write(v82, -1);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v83 = (unsigned int)CVar::GetLPWSTR((CVar *)v95);
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          208,
          (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          v83,
          6);
      }
      _variant_t::~_variant_t(&pvarg);
      ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v99);
      CReleaseMe::release((CReleaseMe *)&v88);
      ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>((__int64)v94);
      CVar::~CVar((CVar *)v100);
      CVar::~CVar((CVar *)v95);
      return 2147749894LL;
    }
  }
  else
  {
    v46 = GetMemLogObject();
    CMemoryLog::Write(v46, -1);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v47 = (unsigned int)CVar::GetLPWSTR((CVar *)v95);
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        200,
        (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        v47,
        v45);
    }
    _variant_t::~_variant_t(&pvarg);
    ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v99);
    CReleaseMe::release((CReleaseMe *)&v88);
    ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>((__int64)v94);
    CVar::~CVar((CVar *)v100);
    CVar::~CVar((CVar *)v95);
    return (unsigned int)v45;
  }
}

```

## disassembly

```asm
0x1800827d0  mov     [rsp+arg_18], r9
0x1800827d5  mov     [rsp+arg_8], rdx
0x1800827da  mov     [rsp+arg_0], rcx
0x1800827df  push    rbx
0x1800827e0  push    rsi
0x1800827e1  push    rdi
0x1800827e2  push    r12
0x1800827e4  push    r13
0x1800827e6  push    r14
0x1800827e8  push    r15
0x1800827ea  sub     rsp, 140h
0x1800827f1  mov     r14, r8
0x1800827f4  mov     rbx, rdx
0x1800827f7  mov     r13, rcx
0x1800827fa  xor     r12d, r12d
0x1800827fd  lea     r15, WPP_GLOBAL_Control
0x180082804  mov     rcx, cs:WPP_GLOBAL_Control
0x18008280b  lea     edi, [r12+1]
0x180082810  cmp     rcx, r15
0x180082813  jz      short loc_18008283E
0x180082815  test    [rcx+1Ch], dil
0x180082819  jz      short loc_18008283E
0x18008281b  cmp     byte ptr [rcx+19h], 5
0x18008281f  jb      short loc_18008283E
0x180082821  mov     edx, 0B6h
0x180082826  mov     r9, rbx
0x180082829  lea     rsi, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180082830  mov     r8, rsi
0x180082833  mov     rcx, [rcx+10h]
0x180082837  call    WPP_SF_q
0x18008283c  jmp     short loc_180082845
0x18008283e  lea     rsi, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x180082845  lea     rcx, [rsp+178h+var_C8]
0x18008284d  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180082853  nop
0x180082854  mov     rax, [rbx]
0x180082857  lea     r8, [rsp+178h+var_C8]
0x18008285f  lea     rdx, aName; "Name"
0x180082866  mov     rcx, rbx
0x180082869  mov     rax, [rax+308h]
0x180082870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082875  test    eax, eax
0x180082877  js      loc_180083A0F
0x18008287d  lea     rcx, [rsp+178h+var_C8]
0x180082885  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x18008288b  test    eax, eax
0x18008288d  jnz     loc_180083A0F
0x180082893  lea     rcx, [rsp+178h+var_60]
0x18008289b  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x1800828a1  nop
0x1800828a2  mov     rax, [rbx]
0x1800828a5  lea     r8, [rsp+178h+var_60]
0x1800828ad  lea     rdx, aRelpath_0; "__RELPATH"
0x1800828b4  mov     rcx, rbx
0x1800828b7  mov     rax, [rax+308h]
0x1800828be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800828c3  test    eax, eax
0x1800828c5  js      loc_1800839C8
0x1800828cb  lea     rcx, [rsp+178h+var_60]
0x1800828d3  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x1800828d9  test    eax, eax
0x1800828db  jnz     loc_1800839C8
0x1800828e1  lea     rcx, [rsp+178h+var_C8]
0x1800828e9  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x1800828ef  mov     rbx, rax
0x1800828f2  mov     [rsp+178h+String1], rax
0x1800828fa  mov     edx, cs:?g_PathLimit@@3KA; ulong g_PathLimit
0x180082900  add     edx, 0FFFFFFEDh
0x180082903  lea     r8, asc_1800F1338; "-"
0x18008290a  mov     rcx, rax
0x18008290d  call    cs:__imp_?_IsValidElementName@@YAHPEBGK0@Z; _IsValidElementName(ushort const *,ulong,ushort const *)
0x180082913  test    eax, eax
0x180082915  jnz     short loc_18008295B
0x180082917  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18008291d  mov     ebx, 8004100Eh
0x180082922  mov     edx, ebx
0x180082924  mov     rcx, rax
0x180082927  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008292d  mov     rcx, cs:WPP_GLOBAL_Control
0x180082934  cmp     rcx, r15
0x180082937  jz      loc_1800839B5
0x18008293d  test    [rcx+1Ch], dil
0x180082941  jz      loc_1800839B5
0x180082947  cmp     byte ptr [rcx+19h], 2
0x18008294b  jb      loc_1800839B5
0x180082951  mov     edx, 0B9h
0x180082956  jmp     loc_1800839FB
0x18008295b  cmp     word ptr [rbx], 5Fh ; '_'
0x18008295f  jnz     short loc_1800829A5
0x180082961  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082967  mov     ebx, 8004100Eh
0x18008296c  mov     edx, ebx
0x18008296e  mov     rcx, rax
0x180082971  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082977  mov     rcx, cs:WPP_GLOBAL_Control
0x18008297e  cmp     rcx, r15
0x180082981  jz      loc_1800839B5
0x180082987  test    [rcx+1Ch], dil
0x18008298b  jz      loc_1800839B5
0x180082991  cmp     byte ptr [rcx+19h], 2
0x180082995  jb      loc_1800839B5
0x18008299b  mov     edx, 0BAh
0x1800829a0  jmp     loc_1800839FB
0x1800829a5  lea     rcx, [rsp+178h+var_60]
0x1800829ad  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x1800829b3  mov     r15, rax
0x1800829b6  cmp     [rsp+178h+arg_20], r12d
0x1800829be  jnz     short loc_180082A3B
0x1800829c0  lea     rdx, [r13+0D8h]; struct CNtSecurityDescriptor *
0x1800829c7  mov     [rsp+178h+var_148], dil; bool
0x1800829cc  mov     [rsp+178h+var_158], rax; unsigned __int16 *
0x1800829d1  lea     r9, aWritePutinstan; "Write (PutInstance)"
0x1800829d8  mov     r8d, 4; unsigned int
0x1800829de  mov     rcx, r13; this
0x1800829e1  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x1800829e6  test    al, al
0x1800829e8  jnz     short loc_180082A3B
0x1800829ea  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800829f0  mov     ebx, 80041003h
0x1800829f5  mov     edx, ebx
0x1800829f7  mov     rcx, rax
0x1800829fa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180082a07  lea     rdx, WPP_GLOBAL_Control
0x180082a0e  cmp     rcx, rdx
0x180082a11  jz      loc_1800839B5
0x180082a17  test    [rcx+1Ch], dil
0x180082a1b  jz      loc_1800839B5
0x180082a21  cmp     byte ptr [rcx+19h], 2
0x180082a25  jb      loc_1800839B5
0x180082a2b  mov     edx, 0BBh
0x180082a30  mov     r9d, 80041003h
0x180082a36  jmp     loc_180083A01
0x180082a3b  mov     [rsp+178h+var_E8], r12
0x180082a43  lea     r8, [rsp+178h+var_E8]
0x180082a4b  lea     rcx, [rsp+178h+var_E0]
0x180082a53  call    ??$MakeGuard@P6AXPEBVCNtSecurityDescriptor@@@ZV?$RefHolder@PEAVCNtSecurityDescriptor@@@@@@YA?AV?$ScopeGuardImpl1@P6AXPEBVCNtSecurityDescriptor@@@ZV?$RefHolder@PEAVCNtSecurityDescriptor@@@@@@P6AXPEBVCNtSecurityDescriptor@@@ZV?$RefHolder@PEAVCNtSecurityDescriptor@@@@@Z; MakeGuard<void (*)(CNtSecurityDescriptor const *),RefHolder<CNtSecurityDescriptor *>>(void (*)(CNtSecurityDescriptor const *),RefHolder<CNtSecurityDescriptor *>)
0x180082a58  nop
0x180082a59  test    r14, r14
0x180082a5c  jz      loc_180082E9B
0x180082a62  mov     rcx, r14; pSecurityDescriptor
0x180082a65  call    cs:__imp_IsValidSecurityDescriptor
0x180082a6b  test    eax, eax
0x180082a6d  jnz     short loc_180082ABA
0x180082a6f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082a75  mov     ebx, 80041008h
0x180082a7a  mov     edx, ebx
0x180082a7c  mov     rcx, rax
0x180082a7f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180082a8c  lea     rdx, WPP_GLOBAL_Control
0x180082a93  cmp     rcx, rdx
0x180082a96  jz      loc_1800839A7
0x180082a9c  test    [rcx+1Ch], dil
0x180082aa0  jz      loc_1800839A7
0x180082aa6  cmp     byte ptr [rcx+19h], 2
0x180082aaa  jb      loc_1800839A7
0x180082ab0  mov     edx, 0BCh
0x180082ab5  jmp     loc_180082C5C
0x180082aba  mov     [rsp+178h+bDaclPresent], r12d
0x180082abf  mov     [rsp+178h+bDaclDefaulted], r12d
0x180082ac7  mov     [rsp+178h+pDacl], r12
0x180082acf  lea     r9, [rsp+178h+bDaclDefaulted]; lpbDaclDefaulted
0x180082ad7  lea     r8, [rsp+178h+pDacl]; pDacl
0x180082adf  lea     rdx, [rsp+178h+bDaclPresent]; lpbDaclPresent
0x180082ae4  mov     rcx, r14; pSecurityDescriptor
0x180082ae7  call    cs:__imp_GetSecurityDescriptorDacl
0x180082aed  test    eax, eax
0x180082aef  jnz     short loc_180082B5F
0x180082af1  call    cs:__imp_GetLastError
0x180082af7  mov     ebx, eax
0x180082af9  test    eax, eax
0x180082afb  jle     short loc_180082B06
0x180082afd  movzx   ebx, ax
0x180082b00  or      ebx, 80070000h
0x180082b06  test    ebx, ebx
0x180082b08  jns     short loc_180082B1B
0x180082b0a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082b10  mov     edx, ebx
0x180082b12  mov     rcx, rax
0x180082b15  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180082b22  lea     rdx, WPP_GLOBAL_Control
0x180082b29  cmp     rcx, rdx
0x180082b2c  jz      loc_1800839A7
0x180082b32  test    [rcx+1Ch], dil
0x180082b36  jz      loc_1800839A7
0x180082b3c  cmp     byte ptr [rcx+19h], 2
0x180082b40  jb      loc_1800839A7
0x180082b46  mov     edx, 0BDh
0x180082b4b  mov     r9d, ebx
0x180082b4e  mov     r8, rsi
0x180082b51  mov     rcx, [rcx+10h]
0x180082b55  call    WPP_SF_d
0x180082b5a  jmp     loc_1800839A7
0x180082b5f  cmp     [rsp+178h+bDaclPresent], r12d
0x180082b64  jnz     short loc_180082BB1
0x180082b66  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082b6c  mov     ebx, 80041008h
0x180082b71  mov     edx, ebx
0x180082b73  mov     rcx, rax
0x180082b76  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082b7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082b83  lea     rdx, WPP_GLOBAL_Control
0x180082b8a  cmp     rcx, rdx
0x180082b8d  jz      loc_1800839A7
0x180082b93  test    [rcx+1Ch], dil
0x180082b97  jz      loc_1800839A7
0x180082b9d  cmp     byte ptr [rcx+19h], 2
0x180082ba1  jb      loc_1800839A7
0x180082ba7  mov     edx, 0BEh
0x180082bac  jmp     loc_180082C5C
0x180082bb1  mov     [rsp+178h+var_118], r12b
0x180082bb6  lea     rdx, [rsp+178h+var_118]; bool *
0x180082bbb  mov     rcx, r14; pSecurityDescriptor
0x180082bbe  call    ?HasInheritedAces@@YAJPEAXPEA_N@Z; HasInheritedAces(void *,bool *)
0x180082bc3  mov     ebx, eax
0x180082bc5  test    eax, eax
0x180082bc7  jns     short loc_180082C0F
0x180082bc9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082bcf  mov     edx, ebx
0x180082bd1  mov     rcx, rax
0x180082bd4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180082be1  lea     rdx, WPP_GLOBAL_Control
0x180082be8  cmp     rcx, rdx
0x180082beb  jz      loc_1800839A7
0x180082bf1  test    [rcx+1Ch], dil
0x180082bf5  jz      loc_1800839A7
0x180082bfb  cmp     byte ptr [rcx+19h], 2
0x180082bff  jb      loc_1800839A7
0x180082c05  mov     edx, 0BFh
0x180082c0a  jmp     loc_180082B4B
0x180082c0f  cmp     [rsp+178h+var_118], r12b
0x180082c14  jz      short loc_180082C67
0x180082c16  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082c1c  mov     ebx, 80041008h
0x180082c21  mov     edx, ebx
0x180082c23  mov     rcx, rax
0x180082c26  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c33  lea     rdx, WPP_GLOBAL_Control
0x180082c3a  cmp     rcx, rdx
0x180082c3d  jz      loc_1800839A7
0x180082c43  test    [rcx+1Ch], dil
0x180082c47  jz      loc_1800839A7
0x180082c4d  cmp     byte ptr [rcx+19h], 2
0x180082c51  jb      loc_1800839A7
0x180082c57  mov     edx, 0C0h
0x180082c5c  mov     r9d, 80041008h
0x180082c62  jmp     loc_180082B4E
0x180082c67  mov     ecx, 10h
0x180082c6c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180082c72  mov     [rsp+178h+var_110], rax
0x180082c77  test    rax, rax
0x180082c7a  jz      short loc_180082C8A
0x180082c7c  mov     rdx, r14
0x180082c7f  mov     rcx, rax
0x180082c82  call    cs:__imp_??0CNtSecurityDescriptor@@QEAA@PEAX@Z; CNtSecurityDescriptor::CNtSecurityDescriptor(void *)
0x180082c88  jmp     short loc_180082C8D
0x180082c8a  mov     rax, r12
0x180082c8d  mov     [rsp+178h+var_E8], rax
0x180082c95  test    rax, rax
0x180082c98  jnz     short loc_180082CEB
0x180082c9a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082ca0  mov     ebx, 80041006h
0x180082ca5  mov     edx, ebx
0x180082ca7  mov     rcx, rax
0x180082caa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180082cb7  lea     rdx, WPP_GLOBAL_Control
0x180082cbe  cmp     rcx, rdx
0x180082cc1  jz      loc_1800839A7
0x180082cc7  test    [rcx+1Ch], dil
0x180082ccb  jz      loc_1800839A7
0x180082cd1  cmp     byte ptr [rcx+19h], 2
0x180082cd5  jb      loc_1800839A7
0x180082cdb  mov     edx, 0C1h
0x180082ce0  mov     r9d, 80041006h
0x180082ce6  jmp     loc_180082B4E
0x180082ceb  mov     rcx, rax; struct CNtSecurityDescriptor *
0x180082cee  call    ?SetDefaultOwner@@YAHAEAVCNtSecurityDescriptor@@@Z; SetDefaultOwner(CNtSecurityDescriptor &)
0x180082cf3  test    eax, eax
0x180082cf5  jnz     short loc_180082D48
0x180082cf7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180082cfd  mov     ebx, 80041001h
0x180082d02  mov     edx, ebx
0x180082d04  mov     rcx, rax
0x180082d07  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180082d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180082d14  lea     rdx, WPP_GLOBAL_Control
0x180082d1b  cmp     rcx, rdx
0x180082d1e  jz      loc_1800839A7
0x180082d24  test    [rcx+1Ch], dil
0x180082d28  jz      loc_1800839A7
0x180082d2e  cmp     byte ptr [rcx+19h], 2
0x180082d32  jb      loc_1800839A7
0x180082d38  mov     edx, 0C2h
0x180082d3d  mov     r9d, 80041001h
0x180082d43  jmp     loc_180082B4E
  ... truncated ...
```
