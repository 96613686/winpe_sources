# SetSecurityForNS(IWmiDbSession *,IWmiDbHandle *,IWmiDbSession *,IWmiDbHandle *,CNtSecurityDescriptor *,bool &,bool &,bool)

- ea: `0x180024428`
- end: `0x1800250b6`
- name: `?SetSecurityForNS@@YAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@01PEAVCNtSecurityDescriptor@@AEA_N3_N@Z`
- size: `3214`
- prototype: `__int64 __usercall@<rax>(struct IWmiDbSession *@<rcx>, struct IWmiDbHandle *@<rdx>, struct IWmiDbSession *@<r8>, struct IWmiDbHandle *@<r9>, struct CNtSecurityDescriptor *, bool *, bool *, bool)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005d9a8`
- `0x18008be98`

## callees

- `0x18000b140`
- `0x180011700`
- `0x1800220d0`
- `0x180023f30`
- `0x180024428`
- `0x1800250bc`
- `0x1800251a4`
- `0x18003cfe0`
- `0x18004b934`
- `0x1800604d0`
- `0x180060ba4`
- `0x180086544`
- `0x1800bd238`
- `0x1800bdac0`
- `0x1800bde98`
- `0x1800bf548`
- `0x1800bf788`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002446e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002509a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002446e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002509a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024864`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002485a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002485a`
- `wbemcomn!?GetPtr@CNtSecurityDescriptor@@QEAAPEAXXZ` at `0x180024830`
- `wbemcomn!?GetPtr@CNtSecurityDescriptor@@QEAAPEAXXZ` at `0x180024830`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x18002454d`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x18002493d`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x18002454d`
- `wbemcomn!??0CNtAcl@@QEAA@K@Z` at `0x18002493d`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180024c31`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180024fbe`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x18002507d`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180024c31`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x180024fbe`
- `wbemcomn!??1CNtAcl@@QEAA@XZ` at `0x18002507d`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x18002458e`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x180024683`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x180024b72`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x180024df5`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x18002458e`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x180024683`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x180024b72`
- `wbemcomn!??0CNtSecurityDescriptor@@QEAA@XZ` at `0x180024df5`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024be6`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024cb6`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024d1a`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024e63`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024f1d`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024be6`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024cb6`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024d1a`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024e63`
- `wbemcomn!??1CNtSecurityDescriptor@@QEAA@XZ` at `0x180024f1d`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180024903`
- `wbemcomn!?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180024903`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800246eb`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x180024a1d`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x180024a8f`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x1800246eb`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x180024a1d`
- `wbemcomn!?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z` at `0x180024a8f`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180024d57`
- `wbemcomn!?GetSacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ` at `0x180024d57`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002457c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180024671`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180024926`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002457c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180024671`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180024926`
- `wbemcomn!GetMemLogObject` at `0x1800244a0`
- `wbemcomn!GetMemLogObject` at `0x1800244e8`
- `wbemcomn!GetMemLogObject` at `0x1800245a3`
- `wbemcomn!GetMemLogObject` at `0x180024611`
- `wbemcomn!GetMemLogObject` at `0x180024698`
- `wbemcomn!GetMemLogObject` at `0x1800246f9`
- `wbemcomn!GetMemLogObject` at `0x180024742`
- `wbemcomn!GetMemLogObject` at `0x18002479e`
- `wbemcomn!GetMemLogObject` at `0x1800247e7`
- `wbemcomn!GetMemLogObject` at `0x18002487d`
- `wbemcomn!GetMemLogObject` at `0x18002494f`
- `wbemcomn!GetMemLogObject` at `0x1800249c1`
- `wbemcomn!GetMemLogObject` at `0x180024a3e`
- `wbemcomn!GetMemLogObject` at `0x180024a9f`
- `wbemcomn!GetMemLogObject` at `0x180024b20`
- `wbemcomn!GetMemLogObject` at `0x180024b98`
- `wbemcomn!GetMemLogObject` at `0x180024c69`
- `wbemcomn!GetMemLogObject` at `0x180024cdf`
- `wbemcomn!GetMemLogObject` at `0x180024d9b`
- `wbemcomn!GetMemLogObject` at `0x180024e16`
- `wbemcomn!GetMemLogObject` at `0x180024e88`
- `wbemcomn!GetMemLogObject` at `0x180024ed3`
- `wbemcomn!GetMemLogObject` at `0x180024f5a`
- `wbemcomn!GetMemLogObject` at `0x180025025`
- `wbemcomn!GetMemLogObject` at `0x1800244a0`
- `wbemcomn!GetMemLogObject` at `0x1800244e8`
- `wbemcomn!GetMemLogObject` at `0x1800245a3`
- `wbemcomn!GetMemLogObject` at `0x180024611`
- `wbemcomn!GetMemLogObject` at `0x180024698`
- `wbemcomn!GetMemLogObject` at `0x1800246f9`
- `wbemcomn!GetMemLogObject` at `0x180024742`
- `wbemcomn!GetMemLogObject` at `0x18002479e`
- `wbemcomn!GetMemLogObject` at `0x1800247e7`
- `wbemcomn!GetMemLogObject` at `0x18002487d`
- `wbemcomn!GetMemLogObject` at `0x18002494f`
- `wbemcomn!GetMemLogObject` at `0x1800249c1`
- `wbemcomn!GetMemLogObject` at `0x180024a3e`
- `wbemcomn!GetMemLogObject` at `0x180024a9f`
- `wbemcomn!GetMemLogObject` at `0x180024b20`
- `wbemcomn!GetMemLogObject` at `0x180024b98`
- `wbemcomn!GetMemLogObject` at `0x180024c69`
- `wbemcomn!GetMemLogObject` at `0x180024cdf`
- `wbemcomn!GetMemLogObject` at `0x180024d9b`
- `wbemcomn!GetMemLogObject` at `0x180024e16`
- `wbemcomn!GetMemLogObject` at `0x180024e88`
- `wbemcomn!GetMemLogObject` at `0x180024ed3`
- `wbemcomn!GetMemLogObject` at `0x180024f5a`
- `wbemcomn!GetMemLogObject` at `0x180025025`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800244ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800244f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800245b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002461c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800246a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024705`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024752`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800247aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800247f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024888`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002495f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800249cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024a49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024aaf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024b2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024ba4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024c74`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024cea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024da6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024e21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024e93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024ede`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024f65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025030`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800244ac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800244f3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800245b3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002461c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800246a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024705`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024752`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800247aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800247f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024888`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002495f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800249cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024a49`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024aaf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024b2b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024ba4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024c74`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024cea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024da6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024e21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024e93`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024ede`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024f65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025030`

## string_xrefs

- `0x1800245fb`: `SECURITY_DESCRIPTOR`
- `0x180024b81`: `SECURITY_DESCRIPTOR`
- `0x180024e04`: `SECURITY_DESCRIPTOR`
- `0x180024f41`: `SECURITY_DESCRIPTOR`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SetSecurityForNS(
        struct IWmiDbSession *a1,
        struct IWmiDbHandle *a2,
        struct IWmiDbSession *a3,
        struct IWmiDbHandle *a4,
        struct CNtSecurityDescriptor *a5,
        bool *a6,
        bool *a7,
        bool a8)
{
  struct IWmiDbHandle *v8; // r15
  signed int ObjectW; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v13; // rax
  struct IWbemClassObject *v14; // rdi
  __int64 v15; // rdx
  struct IWbemClassObject *v16; // rax
  struct CNtSecurityDescriptor *v17; // rax
  CMemoryLog *v18; // rax
  CClientCnt *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  CMemoryLog *v22; // rax
  struct CNtSecurityDescriptor *v23; // rcx
  struct IWbemClassObject *v24; // rax
  struct CNtSecurityDescriptor *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  void *Ptr; // rcx
  signed int LastError; // eax
  CMemoryLog *v33; // rax
  bool v34; // r13
  bool v35; // r12
  bool *v36; // r14
  struct CNtAcl *Dacl; // rax
  struct CNtAcl *v38; // r14
  struct IWbemClassObject *v39; // rax
  struct IWbemClassObject *v40; // rsi
  CMemoryLog *v41; // rax
  CClientCnt *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r9
  CMemoryLog *v45; // rax
  int v46; // ebx
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  CMemoryLog *v49; // rax
  struct IWbemClassObject *v50; // rbx
  int SDFromProperty; // r15d
  CMemoryLog *v52; // rax
  CMemoryLog *v53; // rax
  CClientCnt *v54; // rcx
  __int64 v55; // rdx
  CMemoryLog *v56; // rax
  CMemoryLog *v57; // rax
  CMemoryLog *v58; // rax
  CClientCnt *v59; // rcx
  __int64 v60; // rdx
  CMemoryLog *v61; // rax
  CMemoryLog *v62; // rax
  const struct _GUID *v63; // r8
  CMemoryLog *v64; // rax
  char v65; // al
  bool v66; // al
  CMemoryLog *v67; // rax
  struct IWbemClassObject *v69; // [rsp+38h] [rbp-A1h] BYREF
  DWORD dwRevision[2]; // [rsp+40h] [rbp-99h] BYREF
  struct CNtSecurityDescriptor *v71; // [rsp+48h] [rbp-91h] BYREF
  WORD pControl; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v73[16]; // [rsp+58h] [rbp-81h] BYREF
  struct IWbemClassObject *v74; // [rsp+68h] [rbp-71h] BYREF
  struct IWbemClassObject *v75; // [rsp+70h] [rbp-69h] BYREF
  char v76[8]; // [rsp+78h] [rbp-61h] BYREF
  void (__fastcall *v77)(_QWORD); // [rsp+80h] [rbp-59h]
  _QWORD *v78; // [rsp+88h] [rbp-51h]
  struct IWbemClassObject *v79; // [rsp+90h] [rbp-49h] BYREF
  struct IWbemClassObject *v80; // [rsp+98h] [rbp-41h] BYREF
  _BYTE v81[16]; // [rsp+A0h] [rbp-39h] BYREF
  _BYTE v82[24]; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v83; // [rsp+C8h] [rbp-11h]

  v8 = a4;
  v79 = 0;
  v83 = 0;
  TlsSetValue(g_SecFlagTlsIndex, 0);
  ObjectW = CRepository::GetObjectW(a1, a2, L"__thisnamespace=@", 0x40000u, &v79);
  if ( ObjectW < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -1);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)ObjectW);
    }
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, ObjectW);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)ObjectW);
    }
    goto LABEL_186;
  }
  v14 = v79;
  v69 = v79;
  CNtAcl::CNtAcl((CNtAcl *)v73, 0x80u);
  v71 = 0;
  MakeGuard<void (*)(CNtSecurityDescriptor const *),RefHolder<CNtSecurityDescriptor *>>(
    (__int64)v76,
    v15,
    (__int64)&v71);
  if ( !a8 )
  {
    v23 = a5;
    if ( a5 )
    {
      v71 = a5;
      v76[0] = 1;
    }
    else
    {
      v24 = (struct IWbemClassObject *)CWin32DefaultArena::WbemMemAlloc(0x10u);
      v75 = v24;
      if ( v24 )
        v25 = CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)v24);
      else
        v25 = 0;
      v71 = v25;
      if ( !v25 )
      {
        v26 = GetMemLogObject();
        ObjectW = -2147217402;
        CMemoryLog::Write(v26, -2147217402);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_185;
        }
        v20 = 84;
LABEL_19:
        v21 = 2147749894LL;
LABEL_184:
        WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v21);
        goto LABEL_185;
      }
      if ( !CNtSecurityDescriptor::SetDacl(v25, (struct CNtAcl *)v73) )
      {
        v27 = GetMemLogObject();
        CMemoryLog::Write(v27, -1);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            (unsigned int)ObjectW);
        }
        v28 = GetMemLogObject();
        ObjectW = -2147217407;
        CMemoryLog::Write(v28, -2147217407);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_185;
        }
        v20 = 86;
        goto LABEL_44;
      }
      v23 = v71;
    }
    if ( (unsigned int)SetDefaultOwnerAndGroup(v23) )
      goto LABEL_55;
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -1);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)ObjectW);
    }
    v30 = GetMemLogObject();
    ObjectW = -2147217407;
    CMemoryLog::Write(v30, -2147217407);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_185;
    }
    v20 = 88;
LABEL_44:
    v21 = 2147749889LL;
    goto LABEL_184;
  }
  v16 = (struct IWbemClassObject *)CWin32DefaultArena::WbemMemAlloc(0x10u);
  v75 = v16;
  if ( v16 )
    v17 = CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)v16);
  else
    v17 = 0;
  v71 = v17;
  if ( !v17 )
  {
    v18 = GetMemLogObject();
    ObjectW = -2147217402;
    CMemoryLog::Write(v18, -2147217402);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_185;
    }
    v20 = 82;
    goto LABEL_19;
  }
  ObjectW = GetSDFromProperty(L"SECURITY_DESCRIPTOR", v17, v79);
  if ( ObjectW < 0 )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, ObjectW);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_185;
    }
    v20 = 83;
    goto LABEL_183;
  }
LABEL_55:
  Ptr = CNtSecurityDescriptor::GetPtr(v71);
  if ( !Ptr )
  {
    ObjectW = -2147467261;
LABEL_61:
    v33 = GetMemLogObject();
    CMemoryLog::Write(v33, ObjectW);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_185;
    }
    v20 = 89;
    goto LABEL_183;
  }
  pControl = 0;
  dwRevision[0] = 0;
  if ( GetSecurityDescriptorControl(Ptr, &pControl, dwRevision) )
  {
    v34 = (pControl & 0x1000) != 0;
    v35 = (pControl & 0x2000) != 0;
  }
  else
  {
    LastError = GetLastError();
    ObjectW = LastError;
    if ( LastError > 0 )
      ObjectW = (unsigned __int16)LastError | 0x80070000;
    if ( ObjectW < 0 )
      goto LABEL_61;
    v34 = 0;
    v35 = 0;
  }
  v36 = a6;
  if ( !*a6 || v34 )
    goto LABEL_133;
  Dacl = CNtSecurityDescriptor::GetDacl(v71);
  v38 = Dacl;
  *(_QWORD *)dwRevision = Dacl;
  if ( !v8 )
  {
    if ( !Dacl )
    {
      v39 = (struct IWbemClassObject *)CWin32DefaultArena::WbemMemAlloc(0x10u);
      v75 = v39;
      if ( v39 )
        v40 = (struct IWbemClassObject *)CNtAcl::CNtAcl((CNtAcl *)v39, 0x80u);
      else
        v40 = 0;
      if ( !v40 )
      {
        v41 = GetMemLogObject();
        ObjectW = -2147217402;
        CMemoryLog::Write(v41, -2147217402);
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_80;
        }
        v43 = 90;
        v44 = 2147749894LL;
        goto LABEL_79;
      }
      v75 = v40;
      ObjectW = AddDefaultRootAces((struct CNtAcl *)v40);
      if ( ObjectW < 0 )
      {
        v45 = GetMemLogObject();
        CMemoryLog::Write(v45, ObjectW);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            91,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            (unsigned int)ObjectW);
        }
        CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>((CNtAcl **)&v75);
        goto LABEL_80;
      }
      v46 = CNtSecurityDescriptor::SetDacl(v71, (struct CNtAcl *)v40);
      CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>((CNtAcl **)&v75);
LABEL_95:
      if ( !v46 )
      {
        v48 = GetMemLogObject();
        ObjectW = -2147217407;
        CMemoryLog::Write(v48, -2147217407);
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_80;
        }
        v43 = 93;
        v44 = 2147749889LL;
        goto LABEL_79;
      }
      goto LABEL_132;
    }
    ObjectW = AddDefaultRootAces(Dacl);
    if ( ObjectW >= 0 )
    {
      v46 = CNtSecurityDescriptor::SetDacl(v71, v38);
      goto LABEL_95;
    }
    v47 = GetMemLogObject();
    CMemoryLog::Write(v47, ObjectW);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_80;
    }
    v43 = 92;
LABEL_93:
    v44 = (unsigned int)ObjectW;
LABEL_79:
    WPP_SF_d(*((_QWORD *)v42 + 2), v43, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, v44);
LABEL_80:
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>((CNtAcl **)dwRevision);
LABEL_185:
    ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>::~ScopeGuardImpl1<void (*)(unsigned short *),RefHolder<unsigned short *>>((__int64)v76);
    CNtAcl::~CNtAcl((CNtAcl *)v73);
    CReleaseMe::release((CReleaseMe *)&v69);
    goto LABEL_186;
  }
  v80 = 0;
  ObjectW = CRepository::GetObjectW(a3, v8, L"__thisnamespace=@", 0x40000u, &v80);
  if ( ObjectW < 0 )
  {
    v49 = GetMemLogObject();
    CMemoryLog::Write(v49, ObjectW);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_80;
    }
    v43 = 94;
    goto LABEL_93;
  }
  v50 = v80;
  v74 = v80;
  CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)v81);
  SDFromProperty = GetSDFromProperty(L"SECURITY_DESCRIPTOR", (struct CNtSecurityDescriptor *)v81, v80);
  if ( SDFromProperty < 0 )
  {
    v52 = GetMemLogObject();
    CMemoryLog::Write(v52, SDFromProperty);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
        (unsigned int)SDFromProperty);
    }
    CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v81);
    if ( v50 )
      ((void (__fastcall *)(struct IWbemClassObject *))v50->lpVtbl->Release)(v50);
    v74 = 0;
    if ( v38 )
      CNtAcl::`scalar deleting destructor'(v38);
    if ( !v76[0] )
      v77(*v78);
    CNtAcl::~CNtAcl((CNtAcl *)v73);
    if ( v14 )
      ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
    v69 = 0;
    ObjectW = SDFromProperty;
    goto LABEL_186;
  }
  ObjectW = StripOutInheritedAcesForDACL(v71);
  if ( ObjectW < 0 )
  {
    v53 = GetMemLogObject();
    CMemoryLog::Write(v53, ObjectW);
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_125;
    }
    v55 = 96;
LABEL_124:
    WPP_SF_d(*((_QWORD *)v54 + 2), v55, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, (unsigned int)ObjectW);
LABEL_125:
    CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v81);
    CReleaseMe::release((CReleaseMe *)&v74);
    goto LABEL_80;
  }
  ObjectW = CopyInheritedDACLAces(v71, (struct CNtSecurityDescriptor *)v81);
  if ( ObjectW < 0 )
  {
    v56 = GetMemLogObject();
    CMemoryLog::Write(v56, ObjectW);
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_125;
    }
    v55 = 97;
    goto LABEL_124;
  }
  CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v81);
  CReleaseMe::release((CReleaseMe *)&v74);
  v8 = a4;
LABEL_132:
  CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>((CNtAcl **)dwRevision);
  v36 = a6;
LABEL_133:
  if ( *a7 && !v35 )
  {
    *(_QWORD *)dwRevision = CNtSecurityDescriptor::GetSacl(v71);
    if ( v8 )
    {
      v75 = 0;
      ObjectW = CRepository::GetObjectW(a3, v8, L"__thisnamespace=@", 0x40000u, &v75);
      if ( ObjectW < 0 )
      {
        v57 = GetMemLogObject();
        CMemoryLog::Write(v57, ObjectW);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            98,
            WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
            (unsigned int)ObjectW);
        }
        goto LABEL_80;
      }
      v74 = v75;
      CNtSecurityDescriptor::CNtSecurityDescriptor((CNtSecurityDescriptor *)v82);
      ObjectW = GetSDFromProperty(L"SECURITY_DESCRIPTOR", (struct CNtSecurityDescriptor *)v82, v75);
      if ( ObjectW < 0 )
      {
        v58 = GetMemLogObject();
        CMemoryLog::Write(v58, ObjectW);
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_148;
        }
        v60 = 99;
LABEL_147:
        WPP_SF_d(*((_QWORD *)v59 + 2), v60, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids, (unsigned int)ObjectW);
LABEL_148:
        CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v82);
        CReleaseMe::release((CReleaseMe *)&v74);
        goto LABEL_80;
      }
      ObjectW = StripOutInheritedAcesForSACL(v71);
      if ( ObjectW < 0 )
      {
        v61 = GetMemLogObject();
        CMemoryLog::Write(v61, ObjectW);
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_148;
        }
        v60 = 100;
        goto LABEL_147;
      }
      ObjectW = CopyInheritedSACLAces(v71, (struct CNtSecurityDescriptor *)v82);
      if ( ObjectW < 0 )
      {
        v62 = GetMemLogObject();
        CMemoryLog::Write(v62, ObjectW);
        v59 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_148;
        }
        v60 = 101;
        goto LABEL_147;
      }
      CNtSecurityDescriptor::~CNtSecurityDescriptor((CNtSecurityDescriptor *)v82);
      CReleaseMe::release((CReleaseMe *)&v74);
    }
    CDeleteMe<CNtAcl>::~CDeleteMe<CNtAcl>((CNtAcl **)dwRevision);
  }
  ObjectW = CopySDIntoProperty(L"SECURITY_DESCRIPTOR", v71, v79);
  if ( ObjectW >= 0 )
  {
    ObjectW = CRepository::PutObject(a1, a2, v63, v79, 0x41000u);
    if ( !*v36 || (v65 = 1, v34) )
      v65 = 0;
    *v36 = v65;
    if ( !*a7 || (v66 = 1, v35) )
      v66 = 0;
    *a7 = v66;
    if ( ObjectW < 0 )
    {
      v67 = GetMemLogObject();
      CMemoryLog::Write(v67, ObjectW);
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_185;
    }
    v20 = 103;
LABEL_183:
    v21 = (unsigned int)ObjectW;
    goto LABEL_184;
  }
  v64 = GetMemLogObject();
  CMemoryLog::Write(v64, ObjectW);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids,
      (unsigned int)ObjectW);
  }
  if ( !v76[0] )
    v77(*v78);
  CNtAcl::~CNtAcl((CNtAcl *)v73);
  if ( v14 )
    ((void (__fastcall *)(struct IWbemClassObject *))v14->lpVtbl->Release)(v14);
  v69 = 0;
LABEL_186:
  TlsSetValue(g_SecFlagTlsIndex, (LPVOID)1);
  return (unsigned int)ObjectW;
}

```

## disassembly

```asm
0x180024428  mov     rax, rsp
0x18002442b  mov     [rax+20h], r9
0x18002442f  mov     [rax+18h], r8
0x180024433  mov     [rax+10h], rdx
0x180024437  mov     [rax+8], rcx
0x18002443b  push    rbp
0x18002443c  push    rbx
0x18002443d  push    rsi
0x18002443e  push    rdi
0x18002443f  push    r12
0x180024441  push    r13
0x180024443  push    r14
0x180024445  push    r15
0x180024447  lea     rbp, [rax-47h]
0x18002444b  sub     rsp, 0D8h
0x180024452  mov     r15, r9
0x180024455  mov     rbx, rdx
0x180024458  mov     rdi, rcx
0x18002445b  xor     r14d, r14d
0x18002445e  mov     [rbp+3Fh+var_88], r14
0x180024462  mov     [rbp+3Fh+var_50], r14
0x180024466  xor     edx, edx; lpTlsValue
0x180024468  mov     ecx, cs:?g_SecFlagTlsIndex@@3VCTLS@@A; dwTlsIndex
0x18002446e  call    cs:__imp_TlsSetValue
0x180024474  nop
0x180024475  lea     rax, [rbp+3Fh+var_88]
0x180024479  mov     [rsp+20h], rax; struct IWbemClassObject **
0x18002447e  mov     r9d, 40000h; unsigned int
0x180024484  lea     r8, aThisnamespace_0; "__thisnamespace=@"
0x18002448b  mov     rdx, rbx; struct IWmiDbHandle *
0x18002448e  mov     rcx, rdi; struct IWmiDbSession *
0x180024491  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x180024496  mov     ebx, eax
0x180024498  test    eax, eax
0x18002449a  jns     loc_18002453A
0x1800244a0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800244a6  or      edx, 0FFFFFFFFh
0x1800244a9  mov     rcx, rax
0x1800244ac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800244b2  lea     rsi, WPP_GLOBAL_Control
0x1800244b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244c0  cmp     rcx, rsi
0x1800244c3  jz      short loc_1800244E8
0x1800244c5  test    byte ptr [rcx+1Ch], 1
0x1800244c9  jz      short loc_1800244E8
0x1800244cb  cmp     byte ptr [rcx+19h], 2
0x1800244cf  jb      short loc_1800244E8
0x1800244d1  lea     edx, [r14+50h]
0x1800244d5  mov     r9d, ebx
0x1800244d8  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800244df  mov     rcx, [rcx+10h]
0x1800244e3  call    WPP_SF_d
0x1800244e8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800244ee  mov     edx, ebx
0x1800244f0  mov     rcx, rax
0x1800244f3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800244f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024500  cmp     rcx, rsi
0x180024503  jz      loc_18002508F
0x180024509  test    byte ptr [rcx+1Ch], 1
0x18002450d  jz      loc_18002508F
0x180024513  cmp     byte ptr [rcx+19h], 2
0x180024517  jb      loc_18002508F
0x18002451d  mov     edx, 51h ; 'Q'
0x180024522  mov     r9d, ebx
0x180024525  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x18002452c  mov     rcx, [rcx+10h]
0x180024530  call    WPP_SF_d
0x180024535  jmp     loc_18002508F
0x18002453a  mov     rdi, [rbp+3Fh+var_88]
0x18002453e  mov     [rsp+110h+var_E0], rdi
0x180024543  mov     edx, 80h
0x180024548  lea     rcx, [rsp+50h]
0x18002454d  call    cs:__imp_??0CNtAcl@@QEAA@K@Z; CNtAcl::CNtAcl(ulong)
0x180024553  nop
0x180024554  mov     [rsp+110h+var_D0], r14
0x180024559  lea     r8, [rsp+110h+var_D0]
0x18002455e  lea     rcx, [rbp+3Fh+var_A0]
0x180024562  call    ??$MakeGuard@P6AXPEBVCNtSecurityDescriptor@@@ZV?$RefHolder@PEAVCNtSecurityDescriptor@@@@@@YA?AV?$ScopeGuardImpl1@P6AXPEBVCNtSecurityDescriptor@@@ZV?$RefHolder@PEAVCNtSecurityDescriptor@@@@@@P6AXPEBVCNtSecurityDescriptor@@@ZV?$RefHolder@PEAVCNtSecurityDescriptor@@@@@Z; MakeGuard<void (*)(CNtSecurityDescriptor const *),RefHolder<CNtSecurityDescriptor *>>(void (*)(CNtSecurityDescriptor const *),RefHolder<CNtSecurityDescriptor *>)
0x180024567  nop
0x180024568  mov     esi, 10h
0x18002456d  cmp     [rbp+3Fh+arg_38], r14b
0x180024574  jz      loc_180024657
0x18002457a  mov     ecx, esi
0x18002457c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180024582  mov     [rbp+3Fh+var_A8], rax
0x180024586  test    rax, rax
0x180024589  jz      short loc_180024596
0x18002458b  mov     rcx, rax
0x18002458e  call    cs:__imp_??0CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::CNtSecurityDescriptor(void)
0x180024594  jmp     short loc_180024599
0x180024596  mov     rax, r14
0x180024599  mov     [rsp+110h+var_D0], rax
0x18002459e  test    rax, rax
0x1800245a1  jnz     short loc_1800245F4
0x1800245a3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800245a9  mov     ebx, 80041006h
0x1800245ae  mov     edx, ebx
0x1800245b0  mov     rcx, rax
0x1800245b3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800245b9  lea     rsi, WPP_GLOBAL_Control
0x1800245c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245c7  cmp     rcx, rsi
0x1800245ca  jz      loc_18002506E
0x1800245d0  test    byte ptr [rcx+1Ch], 1
0x1800245d4  jz      loc_18002506E
0x1800245da  cmp     byte ptr [rcx+19h], 2
0x1800245de  jb      loc_18002506E
0x1800245e4  mov     edx, 52h ; 'R'
0x1800245e9  mov     r9d, 80041006h
0x1800245ef  jmp     loc_18002505D
0x1800245f4  mov     r8, [rbp+3Fh+var_88]; struct IWbemClassObject *
0x1800245f8  mov     rdx, rax; struct CNtSecurityDescriptor *
0x1800245fb  lea     rcx, aSecurityDescri; "SECURITY_DESCRIPTOR"
0x180024602  call    ?GetSDFromProperty@@YAJPEAGPEAVCNtSecurityDescriptor@@PEAUIWbemClassObject@@@Z; GetSDFromProperty(ushort *,CNtSecurityDescriptor *,IWbemClassObject *)
0x180024607  mov     ebx, eax
0x180024609  test    eax, eax
0x18002460b  jns     loc_18002482B
0x180024611  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180024617  mov     edx, ebx
0x180024619  mov     rcx, rax
0x18002461c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024622  lea     rsi, WPP_GLOBAL_Control
0x180024629  mov     rcx, cs:WPP_GLOBAL_Control
0x180024630  cmp     rcx, rsi
0x180024633  jz      loc_18002506E
0x180024639  test    byte ptr [rcx+1Ch], 1
0x18002463d  jz      loc_18002506E
0x180024643  cmp     byte ptr [rcx+19h], 2
0x180024647  jb      loc_18002506E
0x18002464d  mov     edx, 53h ; 'S'
0x180024652  jmp     loc_18002505A
0x180024657  mov     rcx, [rbp+3Fh+arg_20]
0x18002465b  test    rcx, rcx
0x18002465e  jz      short loc_18002466E
0x180024660  mov     [rsp+110h+var_D0], rcx
0x180024665  mov     [rbp+3Fh+var_A0], 1
0x180024669  jmp     loc_180024791
0x18002466e  mov     rcx, rsi
0x180024671  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180024677  mov     [rbp+3Fh+var_A8], rax
0x18002467b  test    rax, rax
0x18002467e  jz      short loc_18002468B
0x180024680  mov     rcx, rax
0x180024683  call    cs:__imp_??0CNtSecurityDescriptor@@QEAA@XZ; CNtSecurityDescriptor::CNtSecurityDescriptor(void)
0x180024689  jmp     short loc_18002468E
0x18002468b  mov     rax, r14
0x18002468e  mov     [rsp+110h+var_D0], rax
0x180024693  test    rax, rax
0x180024696  jnz     short loc_1800246E3
0x180024698  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002469e  mov     ebx, 80041006h
0x1800246a3  mov     edx, ebx
0x1800246a5  mov     rcx, rax
0x1800246a8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800246ae  lea     rsi, WPP_GLOBAL_Control
0x1800246b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800246bc  cmp     rcx, rsi
0x1800246bf  jz      loc_18002506E
0x1800246c5  test    byte ptr [rcx+1Ch], 1
0x1800246c9  jz      loc_18002506E
0x1800246cf  cmp     byte ptr [rcx+19h], 2
0x1800246d3  jb      loc_18002506E
0x1800246d9  mov     edx, 54h ; 'T'
0x1800246de  jmp     loc_1800245E9
0x1800246e3  lea     rdx, [rsp+50h]
0x1800246e8  mov     rcx, rax
0x1800246eb  call    cs:__imp_?SetDacl@CNtSecurityDescriptor@@QEAAHPEAVCNtAcl@@@Z; CNtSecurityDescriptor::SetDacl(CNtAcl *)
0x1800246f1  test    eax, eax
0x1800246f3  jnz     loc_18002478C
0x1800246f9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800246ff  or      edx, 0FFFFFFFFh
0x180024702  mov     rcx, rax
0x180024705  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002470b  lea     rsi, WPP_GLOBAL_Control
0x180024712  mov     rcx, cs:WPP_GLOBAL_Control
0x180024719  cmp     rcx, rsi
0x18002471c  jz      short loc_180024742
0x18002471e  test    byte ptr [rcx+1Ch], 1
0x180024722  jz      short loc_180024742
0x180024724  cmp     byte ptr [rcx+19h], 2
0x180024728  jb      short loc_180024742
0x18002472a  mov     edx, 55h ; 'U'
0x18002472f  mov     r9d, ebx
0x180024732  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x180024739  mov     rcx, [rcx+10h]
0x18002473d  call    WPP_SF_d
0x180024742  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180024748  mov     ebx, 80041001h
0x18002474d  mov     edx, ebx
0x18002474f  mov     rcx, rax
0x180024752  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024758  mov     rcx, cs:WPP_GLOBAL_Control
0x18002475f  cmp     rcx, rsi
0x180024762  jz      loc_18002506E
0x180024768  test    byte ptr [rcx+1Ch], 1
0x18002476c  jz      loc_18002506E
0x180024772  cmp     byte ptr [rcx+19h], 2
0x180024776  jb      loc_18002506E
0x18002477c  mov     edx, 56h ; 'V'
0x180024781  mov     r9d, 80041001h
0x180024787  jmp     loc_18002505D
0x18002478c  mov     rcx, [rsp+110h+var_D0]; struct CNtSecurityDescriptor *
0x180024791  call    ?SetDefaultOwnerAndGroup@@YAHAEAVCNtSecurityDescriptor@@@Z; SetDefaultOwnerAndGroup(CNtSecurityDescriptor &)
0x180024796  test    eax, eax
0x180024798  jnz     loc_18002482B
0x18002479e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800247a4  or      edx, 0FFFFFFFFh
0x1800247a7  mov     rcx, rax
0x1800247aa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800247b0  lea     rsi, WPP_GLOBAL_Control
0x1800247b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247be  cmp     rcx, rsi
0x1800247c1  jz      short loc_1800247E7
0x1800247c3  test    byte ptr [rcx+1Ch], 1
0x1800247c7  jz      short loc_1800247E7
0x1800247c9  cmp     byte ptr [rcx+19h], 2
0x1800247cd  jb      short loc_1800247E7
0x1800247cf  mov     edx, 57h ; 'W'
0x1800247d4  mov     r9d, ebx
0x1800247d7  lea     r8, WPP_2684b750b46c3b8963056a4c01e6f70f_Traceguids
0x1800247de  mov     rcx, [rcx+10h]
0x1800247e2  call    WPP_SF_d
0x1800247e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800247ed  mov     ebx, 80041001h
0x1800247f2  mov     edx, ebx
0x1800247f4  mov     rcx, rax
0x1800247f7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800247fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180024804  cmp     rcx, rsi
0x180024807  jz      loc_18002506E
0x18002480d  test    byte ptr [rcx+1Ch], 1
0x180024811  jz      loc_18002506E
0x180024817  cmp     byte ptr [rcx+19h], 2
0x18002481b  jb      loc_18002506E
0x180024821  mov     edx, 58h ; 'X'
0x180024826  jmp     loc_180024781
0x18002482b  mov     rcx, [rsp+110h+var_D0]
0x180024830  call    cs:__imp_?GetPtr@CNtSecurityDescriptor@@QEAAPEAXXZ; CNtSecurityDescriptor::GetPtr(void)
0x180024836  mov     rcx, rax; pSecurityDescriptor
0x180024839  test    rax, rax
0x18002483c  jnz     short loc_180024845
0x18002483e  mov     ebx, 80004003h
0x180024843  jmp     short loc_18002487D
0x180024845  mov     [rsp+110h+pControl], r14w
0x18002484b  mov     [rsp+110h+dwRevision], r14d
0x180024850  lea     r8, [rsp+110h+dwRevision]; lpdwRevision
0x180024855  lea     rdx, [rsp+110h+pControl]; pControl
0x18002485a  call    cs:__imp_GetSecurityDescriptorControl
0x180024860  test    eax, eax
0x180024862  jnz     short loc_1800248CB
0x180024864  call    cs:__imp_GetLastError
0x18002486a  mov     ebx, eax
0x18002486c  test    eax, eax
0x18002486e  jle     short loc_180024879
0x180024870  movzx   ebx, ax
0x180024873  or      ebx, 80070000h
0x180024879  test    ebx, ebx
0x18002487b  jns     short loc_1800248C3
0x18002487d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180024883  mov     edx, ebx
0x180024885  mov     rcx, rax
0x180024888  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002488e  lea     rsi, WPP_GLOBAL_Control
0x180024895  mov     rcx, cs:WPP_GLOBAL_Control
0x18002489c  cmp     rcx, rsi
0x18002489f  jz      loc_18002506E
0x1800248a5  test    byte ptr [rcx+1Ch], 1
0x1800248a9  jz      loc_18002506E
0x1800248af  cmp     byte ptr [rcx+19h], 2
0x1800248b3  jb      loc_18002506E
0x1800248b9  mov     edx, 59h ; 'Y'
0x1800248be  jmp     loc_18002505A
0x1800248c3  mov     r13b, r14b
0x1800248c6  mov     r12b, r14b
0x1800248c9  jmp     short loc_1800248E7
0x1800248cb  movzx   r12d, [rsp+110h+pControl]
0x1800248d1  movzx   r13d, r12w
0x1800248d5  shr     r13w, 0Ch
0x1800248da  and     r13b, 1
0x1800248de  shr     r12w, 0Dh
0x1800248e3  and     r12b, 1
0x1800248e7  mov     r14, [rbp+3Fh+arg_28]
0x1800248eb  cmp     byte ptr [r14], 0
0x1800248ef  jz      loc_180024D3C
0x1800248f5  test    r13b, r13b
0x1800248f8  jnz     loc_180024D3C
0x1800248fe  mov     rcx, [rsp+110h+var_D0]
0x180024903  call    cs:__imp_?GetDacl@CNtSecurityDescriptor@@QEAAPEAVCNtAcl@@XZ; CNtSecurityDescriptor::GetDacl(void)
0x180024909  mov     r14, rax
0x18002490c  mov     qword ptr [rsp+110h+dwRevision], rax
0x180024911  test    r15, r15
0x180024914  jnz     loc_180024AF0
0x18002491a  test    rax, rax
0x18002491d  jnz     loc_180024A30
0x180024923  mov     rcx, rsi
0x180024926  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002492c  mov     [rbp+3Fh+var_A8], rax
0x180024930  test    rax, rax
0x180024933  jz      short loc_180024948
  ... truncated ...
```
