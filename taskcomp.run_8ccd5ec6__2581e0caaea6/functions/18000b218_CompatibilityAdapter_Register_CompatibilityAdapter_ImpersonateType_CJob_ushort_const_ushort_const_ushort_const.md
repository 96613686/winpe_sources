# CompatibilityAdapter::Register(CompatibilityAdapter::ImpersonateType,CJob *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000b218`
- end: `0x18000c4c0`
- name: `?Register@CompatibilityAdapter@@QEAAJW4ImpersonateType@1@PEAVCJob@@PEBG22H@Z`
- size: `4776`
- prototype: `int __high(enum CompatibilityAdapter::ImpersonateType, struct CJob *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c4c8`
- `0x1800148d0`

## callees

- `0x180004138`
- `0x180004390`
- `0x1800047f0`
- `0x180005094`
- `0x1800050d0`
- `0x180005354`
- `0x1800053bc`
- `0x180006dd8`
- `0x180007948`
- `0x180007988`
- `0x180009c28`
- `0x180009ccc`
- `0x18000a044`
- `0x18000a0f0`
- `0x18000a2c4`
- `0x18000a384`
- `0x18000a3dc`
- `0x18000a478`
- `0x18000a658`
- `0x18000a890`
- `0x18000aa9c`
- `0x18000af88`
- `0x18000b0ac`
- `0x18000b218`
- `0x18000c588`
- `0x18000cf80`
- `0x18000cfc4`
- `0x180011894`
- `0x180015028`
- `0x180015fec`
- `0x18001a8f4`
- `0x180024a94`
- `0x180024cd0`
- `0x18002b5a0`
- `0x18002f3c8`
- `0x18002f7b4`
- `0x1800306b6`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c19d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c19d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b543`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b543`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c1ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c1ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b566`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b5fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b697`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b73e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b7e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b85d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b971`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bb35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bc35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bd6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be56`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bf3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c024`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c12a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c43d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b566`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b5fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b697`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b73e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b7e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b85d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b971`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bb35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bc35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bd6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000be56`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bf3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c024`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c12a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c43d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bdec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000bdec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bdcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bdcd`
- `ntdll!RtlNtStatusToDosError` at `0x18000bee7`
- `ntdll!RtlNtStatusToDosError` at `0x18000bee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c2c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c2de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c2c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c2de`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000ba05`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000ba05`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b333`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b345`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b440`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b452`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b509`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b51b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b59c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b5ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b634`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b646`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6df`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b774`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b786`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b81a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b82c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b893`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b961`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba4c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba92`
- `OLEAUT32!__imp_SysFreeString` at `0x18000baa4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb25`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc25`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bda0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bdb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be46`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be9e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf73`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf85`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c004`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c014`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c05a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c06c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c10a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c11a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c160`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c172`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c325`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c42d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c473`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c485`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b333`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b345`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3fa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b440`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b452`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b509`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b51b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b59c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b5ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b634`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b646`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6df`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b774`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b786`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b81a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b82c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b893`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b961`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba4c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ba92`
- `OLEAUT32!__imp_SysFreeString` at `0x18000baa4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb25`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc25`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc6b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc7d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd4a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bd5a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bda0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bdb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be46`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be9e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf73`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf85`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c004`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c014`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c05a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c06c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c10a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c11a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c160`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c172`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c325`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c42d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c473`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c485`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000bace`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000bace`

## string_xrefs

- `0x18000bd1b`: `CompatibilityAdapter::Register`
- `0x18000c343`: `SeRestorePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=23 #try_helpers=1
__int64 __fastcall CompatibilityAdapter::Register(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7)
{
  _QWORD *v11; // rdx
  BSTR v12; // r15
  unsigned int v13; // edx
  int v14; // r12d
  __int64 v15; // rax
  __int64 i; // rax
  __int64 v17; // rax
  __int64 j; // rax
  __int64 v19; // rax
  __int64 k; // rax
  __int64 v22; // rax
  __int64 m; // rax
  __int64 v24; // rax
  __int64 n; // rax
  HANDLE *v26; // rdi
  CompatibilityAdapter *v27; // rcx
  __int64 v28; // rax
  __int64 ii; // rax
  __int64 v30; // rax
  __int64 jj; // rax
  const void *v32; // rcx
  void *v33; // rbx
  CompatibilityAdapter *v34; // rcx
  __int64 v35; // rax
  __int64 mm; // rax
  int UserInfo; // r12d
  __int64 v38; // rax
  __int64 nn; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 kk; // rax
  __int64 v43; // rax
  __int64 i1; // rax
  enum _TASK_LOGON_TYPE v45; // r14d
  unsigned __int16 *v46; // rsi
  signed int Xml; // ebx
  __int64 v48; // rax
  __int64 i2; // rax
  signed int SecurityInfo; // eax
  __int64 v51; // rax
  __int64 i3; // rax
  __int64 v53; // rcx
  signed int LastError; // eax
  __int64 v55; // rax
  __int64 i4; // rax
  __int64 v57; // rax
  __int64 i5; // rax
  void *v59; // rax
  int v60; // r8d
  RpcAutoImpersonate *v61; // rax
  __int64 v62; // rax
  __int64 i11; // rax
  HANDLE CurrentThread; // rax
  signed int v65; // eax
  __int64 v66; // rax
  __int64 i8; // rax
  NTSTATUS v68; // eax
  void *v69; // rdx
  signed int v70; // eax
  __int64 v71; // rax
  __int64 i9; // rax
  tsched *v73; // rcx
  __int64 v74; // rax
  __int64 i10; // rax
  bool v76; // zf
  bool v77; // al
  void *v78; // r12
  __int64 v79; // rcx
  __int64 v80; // rax
  __int64 i7; // rax
  struct _RTL_CRITICAL_SECTION *v82; // rbx
  unsigned __int16 *v83; // r14
  unsigned int v84; // r9d
  __int64 v85; // rcx
  unsigned int v86; // r9d
  __int64 v87; // rax
  __int64 i6; // rax
  PSID *ppsidGroup; // [rsp+20h] [rbp-338h]
  bool v90; // [rsp+50h] [rbp-308h] BYREF
  int v91; // [rsp+54h] [rbp-304h]
  BSTR String1; // [rsp+58h] [rbp-300h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-2F8h] BYREF
  _BYTE v94[8]; // [rsp+68h] [rbp-2F0h] BYREF
  void *Block; // [rsp+70h] [rbp-2E8h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+78h] [rbp-2E0h] BYREF
  HANDLE handle; // [rsp+80h] [rbp-2D8h] BYREF
  int v98; // [rsp+88h] [rbp-2D0h]
  void *v99; // [rsp+90h] [rbp-2C8h] BYREF
  unsigned int v100; // [rsp+98h] [rbp-2C0h]
  BSTR v101; // [rsp+A0h] [rbp-2B8h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-2B0h] BYREF
  HLOCAL v103; // [rsp+B0h] [rbp-2A8h] BYREF
  RpcSession *v104; // [rsp+B8h] [rbp-2A0h] BYREF
  void *DuplicateTokenHandle; // [rsp+C0h] [rbp-298h] BYREF
  unsigned __int16 *v106; // [rsp+C8h] [rbp-290h] BYREF
  unsigned __int16 *v107; // [rsp+D0h] [rbp-288h]
  _QWORD v108[5]; // [rsp+D8h] [rbp-280h] BYREF
  unsigned __int16 v109[264]; // [rsp+100h] [rbp-258h] BYREF

  v107 = a4;
  v98 = a2;
  v91 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&String1, a5);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, a6);
  v90 = 0;
  v11 = *(_QWORD **)(a3 + 200);
  if ( !v11 )
    goto LABEL_6;
  if ( !String1 )
    ATL::CComBSTR::operator=(&String1, *v11);
  v12 = bstrString;
  if ( !bstrString )
  {
    ATL::CComBSTR::operator=(&bstrString, *(_QWORD *)(*(_QWORD *)(a3 + 200) + 8LL));
LABEL_6:
    v12 = bstrString;
  }
  v108[3] = v12;
  memset_0(v109, 0, 0x20Au);
  v14 = FilenameToUri(a4, v109);
  v91 = v14;
  if ( v14 < 0 )
  {
    if ( v12 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v12[v15] );
      for ( i = 2 * v15; i; --i )
      {
        *(_BYTE *)v12 = 0;
        v12 = (BSTR)((char *)v12 + 1);
      }
    }
LABEL_62:
    SysFreeString(bstrString);
    SysFreeString(String1);
    return (unsigned int)v14;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_480fa276ad7e3cd82bdd80aaed5796f0_Traceguids,
      (unsigned int)v109,
      (__int64)String1);
  }
  if ( !*(_QWORD *)(a3 + 208) )
  {
    v14 = CJob::Sign((CJob *)a3, v13);
    v91 = v14;
    if ( v14 < 0 )
    {
      if ( v12 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v12[v17] );
        for ( j = 2 * v17; j; --j )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_62;
    }
    if ( !*(_QWORD *)(a3 + 208) )
    {
      if ( v12 )
      {
        v19 = -1;
        do
          ++v19;
        while ( v12[v19] );
        for ( k = 2 * v19; k; --k )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
LABEL_32:
      SysFreeString(bstrString);
      SysFreeString(String1);
      return 2147549183LL;
    }
  }
  if ( !*(_DWORD *)(a3 + 216) )
  {
    v14 = CJob::Fingerprint((CJob *)a3);
    v91 = v14;
    if ( v14 < 0 )
    {
      if ( v12 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v12[v22] );
        for ( m = 2 * v22; m; --m )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_62;
    }
    if ( !*(_DWORD *)(a3 + 216) )
    {
      if ( v12 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v12[v24] );
        for ( n = 2 * v24; n; --n )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_32;
    }
  }
  v26 = (HANDLE *)(a1 + 16);
  v108[4] = v26;
  WaitForSingleObject(*v26, 0xFFFFFFFF);
  if ( !a2 )
  {
    if ( (*(_DWORD *)(a3 + 88) & 0x200000) != 0 )
    {
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v28 = -1;
        do
          ++v28;
        while ( v12[v28] );
        for ( ii = 2 * v28; ii; --ii )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
LABEL_90:
      SysFreeString(bstrString);
      SysFreeString(String1);
      return 2147942405LL;
    }
    Block = 0;
    LODWORD(handle) = 0;
    v14 = SignatureStore::Load(a4);
    v91 = v14;
    if ( v14 < 0 )
    {
      operator delete(Block);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v30 = -1;
        do
          ++v30;
        while ( v12[v30] );
        for ( jj = 2 * v30; jj; --jj )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_62;
    }
    v32 = *(const void **)(a3 + 208);
    v33 = Block;
    if ( !v32 || !Block )
    {
      operator delete(Block);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v41 = -1;
        do
          ++v41;
        while ( v12[v41] );
        for ( kk = 2 * v41; kk; --kk )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_90;
    }
    if ( memcmp_0(v32, Block, 0x40u) )
    {
      operator delete(v33);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v35 = -1;
        do
          ++v35;
        while ( v12[v35] );
        for ( mm = 2 * v35; mm; --mm )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_90;
    }
    if ( !String1 )
    {
      StringSecurityDescriptor = 0;
      UserInfo = CompatibilityAdapter::GetUserInfo(v34, v109, (struct _bstr_t *)&StringSecurityDescriptor, &v90);
      v91 = UserInfo;
      if ( UserInfo < 0 )
      {
        _bstr_t::~_bstr_t((_bstr_t *)&StringSecurityDescriptor);
        operator delete(v33);
        ReleaseMutex(*v26);
        if ( v12 )
        {
          v38 = -1;
          do
            ++v38;
          while ( v12[v38] );
          for ( nn = 2 * v38; nn; --nn )
          {
            *(_BYTE *)v12 = 0;
            v12 = (BSTR)((char *)v12 + 1);
          }
        }
LABEL_214:
        SysFreeString(bstrString);
        SysFreeString(String1);
        return (unsigned int)UserInfo;
      }
      if ( StringSecurityDescriptor )
        v40 = *(_QWORD *)StringSecurityDescriptor;
      else
        v40 = 0;
      ATL::CComBSTR::operator=(&String1, v40);
      _bstr_t::~_bstr_t((_bstr_t *)&StringSecurityDescriptor);
    }
    v98 = 2;
    operator delete(v33);
  }
  DuplicateTokenHandle = String1;
  if ( !String1 && (*(_DWORD *)(a3 + 88) & 0x200000) == 0 )
  {
    ReleaseMutex(*v26);
    if ( v12 )
    {
      v43 = -1;
      do
        ++v43;
      while ( v12[v43] );
      for ( i1 = 2 * v43; i1; --i1 )
      {
        *(_BYTE *)v12 = 0;
        v12 = (BSTR)((char *)v12 + 1);
      }
    }
    SysFreeString(bstrString);
    SysFreeString(String1);
    return 2147942487LL;
  }
  v45 = TASK_LOGON_NONE;
  v100 = 0;
  if ( (*(_DWORD *)(a3 + 88) & 0x200000) == 0 )
  {
    if ( User::IsLocalSystem(String1) )
    {
      DuplicateTokenHandle = (void *)L"System";
    }
    else
    {
      v45 = (*(_DWORD *)(a3 + 88) & 0x2001) != 0
          ? TASK_LOGON_INTERACTIVE_TOKEN
          : TASK_LOGON_INTERACTIVE_TOKEN_OR_PASSWORD;
      v100 = v45;
    }
  }
  v46 = 0;
  v106 = 0;
  if ( a7 )
  {
    handle = 0;
    Xml = OpenFileWithRetry(*(LPCWSTR *)(a3 + 152), 0x80020000, 1u, &handle);
    v91 = Xml;
    if ( Xml < 0 )
    {
      wmi::AutoHandle::Close((wmi::AutoHandle *)&handle);
      SysFreeString(0);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v48 = -1;
        do
          ++v48;
        while ( v12[v48] );
        for ( i2 = 2 * v48; i2; --i2 )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_191;
    }
    StringSecurityDescriptor = 0;
    Block = 0;
    SecurityInfo = GetSecurityInfo(handle, SE_FILE_OBJECT, 7u, 0, 0, 0, 0, &Block);
    Xml = SecurityInfo;
    if ( SecurityInfo )
    {
      if ( SecurityInfo > 0 )
        Xml = (unsigned __int16)SecurityInfo | 0x80070000;
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&Block);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
      wmi::AutoHandle::Close((wmi::AutoHandle *)&handle);
      SysFreeString(0);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v51 = -1;
        do
          ++v51;
        while ( v12[v51] );
        for ( i3 = 2 * v51; i3; --i3 )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_191;
    }
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(Block, 1u, 7u, &StringSecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      Xml = LastError;
      if ( LastError > 0 )
        Xml = (unsigned __int16)LastError | 0x80070000;
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&Block);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
      wmi::AutoHandle::Close((wmi::AutoHandle *)&handle);
      SysFreeString(0);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v55 = -1;
        do
          ++v55;
        while ( v12[v55] );
        for ( i4 = 2 * v55; i4; --i4 )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_191;
    }
    v99 = 0;
    UserInfo = CompatibilityAdapter::Append_A_FX_SY(v53, StringSecurityDescriptor, &v99);
    v91 = UserInfo;
    if ( UserInfo < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_480fa276ad7e3cd82bdd80aaed5796f0_Traceguids,
          (unsigned int)UserInfo);
      }
      operator delete(v99);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&Block);
      tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
      wmi::AutoHandle::Close((wmi::AutoHandle *)&handle);
      SysFreeString(0);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v57 = -1;
        do
          ++v57;
        while ( v12[v57] );
        for ( i5 = 2 * v57; i5; --i5 )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_214;
    }
    ATL::CComBSTR::operator=(&v106, v99);
    operator delete(v99);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&Block);
    tsched::AutoLocalPtr<unsigned short>::~AutoLocalPtr<unsigned short>(&StringSecurityDescriptor);
    wmi::AutoHandle::Close((wmi::AutoHandle *)&handle);
    v46 = v106;
  }
  v101 = 0;
  Block = 0;
  if ( v98 != 1 )
  {
LABEL_185:
    v78 = DuplicateTokenHandle;
    Xml = CompatibilityAdapter::GenerateXml(
            v27,
            (const struct CJob *)a3,
            (const unsigned __int16 *)DuplicateTokenHandle,
            v45,
            v90,
            (struct ATL::CComBSTR *)&v101);
    v91 = Xml;
    if ( Xml >= 0 )
    {
      CompatibilityAdapter::GetSession(v79, &v104);
      v82 = RegistrationGuard::s_pLock;
      EnterCriticalSection(RegistrationGuard::s_pLock);
      RegistrationGuard::s_name = v109;
      v83 = v101;
      RegistrationGuard::s_xml = v101;
      LeaveCriticalSection(v82);
      v103 = 0;
      hMem = 0;
      if ( (*(_DWORD *)(a3 + 88) & 0x200000) != 0 || !bstrString )
      {
        UserInfo = RpcSession::RegisterTask(
                     v104,
                     v109,
                     v83,
                     v84,
                     (const unsigned __int16 *)ppsidGroup,
                     v100,
                     0,
                     0,
                     (struct RpcString *)&v103,
                     (struct RpcXmlErrorInfo *)&hMem);
      }
      else
      {
        v108[0] = v78;
        v108[1] = bstrString;
        v108[2] = 0;
        UserInfo = RpcSession::RegisterTask(
                     v104,
                     v109,
                     v83,
                     v84,
                     (const unsigned __int16 *)ppsidGroup,
                     v100,
                     1u,
                     (const struct _TASK_USER_CRED *)v108,
                     (struct RpcString *)&v103,
                     (struct RpcXmlErrorInfo *)&hMem);
      }
      v91 = UserInfo;
      LocalFree(hMem);
      hMem = 0;
      LocalFree(v103);
      v103 = 0;
      RegistrationGuard::~RegistrationGuard((RegistrationGuard *)v94);
      if ( v104 )
        wmi::RefBase::Release(v104);
      v104 = 0;
      std::auto_ptr<RpcAutoImpersonate>::~auto_ptr<RpcAutoImpersonate>(&Block);
      SysFreeString(v83);
      if ( UserInfo >= 0 )
      {
        if ( !v46 )
          goto LABEL_208;
        ImpersonateSelfWithPrivilege::ImpersonateSelfWithPrivilege(&DuplicateTokenHandle, L"SeRestorePrivilege");
        CompatibilityAdapter::GetSession(v85, &v101);
        SdSettingGuard::SdSettingGuard((SdSettingGuard *)v94, v109, v46);
        UserInfo = RpcSession::SetSecurity((RpcSession *)v101, v109, v46, v86);
        v91 = UserInfo;
        if ( UserInfo < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_480fa276ad7e3cd82bdd80aaed5796f0_Traceguids,
            (unsigned int)UserInfo);
        }
        SdSettingGuard::~SdSettingGuard((SdSettingGuard *)v94);
        if ( v101 )
          wmi::RefBase::Release((wmi::RefBase *)v101);
        v101 = 0;
        ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege((ImpersonateSelfWithPrivilege *)&DuplicateTokenHandle);
        if ( UserInfo >= 0 )
LABEL_208:
          SignatureStore::Save(v107, *(BYTE **)(a3 + 208), *(_DWORD *)(a3 + 216));
      }
      SysFreeString(v46);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v87 = -1;
        do
          ++v87;
        while ( v12[v87] );
        for ( i6 = 2 * v87; i6; --i6 )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_214;
    }
    std::auto_ptr<RpcAutoImpersonate>::~auto_ptr<RpcAutoImpersonate>(&Block);
    SysFreeString(v101);
    SysFreeString(v46);
    ReleaseMutex(*v26);
    if ( v12 )
    {
      v80 = -1;
      do
        ++v80;
      while ( v12[v80] );
      for ( i7 = 2 * v80; i7; --i7 )
      {
        *(_BYTE *)v12 = 0;
        v12 = (BSTR)((char *)v12 + 1);
      }
    }
LABEL_191:
    SysFreeString(bstrString);
    SysFreeString(String1);
    return (unsigned int)Xml;
  }
  v59 = operator new(4u);
  v99 = v59;
  if ( v59 )
    v61 = RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)v59, L"CompatibilityAdapter::Register", v60);
  else
    v61 = 0;
  Block = v61;
  if ( v61 )
  {
    StringSecurityDescriptor = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, (PHANDLE)&StringSecurityDescriptor) )
    {
      v65 = GetLastError();
      Xml = v65;
      if ( v65 > 0 )
        Xml = (unsigned __int16)v65 | 0x80070000;
      wmi::AutoHandle::Close((wmi::AutoHandle *)&StringSecurityDescriptor);
      std::auto_ptr<RpcAutoImpersonate>::~auto_ptr<RpcAutoImpersonate>(&Block);
      SysFreeString(0);
      SysFreeString(v46);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v66 = -1;
        do
          ++v66;
        while ( v12[v66] );
        for ( i8 = 2 * v66; i8; --i8 )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_191;
    }
    v98 = 0;
    LODWORD(handle) = 1;
    v68 = LUAIsElevatedToken(StringSecurityDescriptor);
    if ( v68 < 0 )
    {
      v70 = RtlNtStatusToDosError(v68);
      Xml = v70;
      if ( v70 > 0 )
        Xml = (unsigned __int16)v70 | 0x80070000;
      wmi::AutoHandle::Close((wmi::AutoHandle *)&StringSecurityDescriptor);
      std::auto_ptr<RpcAutoImpersonate>::~auto_ptr<RpcAutoImpersonate>(&Block);
      SysFreeString(0);
      SysFreeString(v46);
      ReleaseMutex(*v26);
      if ( v12 )
      {
        v71 = -1;
        do
          ++v71;
        while ( v12[v71] );
        for ( i9 = 2 * v71; i9; --i9 )
        {
          *(_BYTE *)v12 = 0;
          v12 = (BSTR)((char *)v12 + 1);
        }
      }
      goto LABEL_191;
    }
    if ( v98 )
    {
      v90 = 1;
    }
    else if ( !(_DWORD)handle )
    {
      v99 = 0;
      Xml = User::FromImpersonationToken((struct User *)&v99, v69);
      v91 = Xml;
      if ( Xml < 0 )
      {
        wmi::AutoRef<User::UserEntry>::Release(&v99);
        wmi::AutoHandle::Close((wmi::AutoHandle *)&StringSecurityDescriptor);
        std::auto_ptr<RpcAutoImpersonate>::~auto_ptr<RpcAutoImpersonate>(&Block);
        SysFreeString(0);
        SysFreeString(v46);
        ReleaseMutex(*v26);
        if ( v12 )
        {
          v74 = -1;
          do
            ++v74;
          while ( v12[v74] );
          for ( i10 = 2 * v74; i10; --i10 )
          {
            *(_BYTE *)v12 = 0;
            v12 = (BSTR)((char *)v12 + 1);
          }
        }
        goto LABEL_191;
      }
      if ( (unsigned int)tsched::IsUserAdmin(v73) || (v76 = !User::IsLocalSystem((User *)&v99), v77 = 0, !v76) )
        v77 = 1;
      v90 = v77;
      wmi::AutoRef<User::UserEntry>::Release(&v99);
    }
    wmi::AutoHandle::Close((wmi::AutoHandle *)&StringSecurityDescriptor);
    goto LABEL_185;
  }
  std::auto_ptr<RpcAutoImpersonate>::~auto_ptr<RpcAutoImpersonate>(&Block);
  SysFreeString(0);
  SysFreeString(v46);
  ReleaseMutex(*v26);
  if ( v12 )
  {
    v62 = -1;
    do
      ++v62;
    while ( v12[v62] );
    for ( i11 = 2 * v62; i11; --i11 )
    {
      *(_BYTE *)v12 = 0;
      v12 = (BSTR)((char *)v12 + 1);
    }
  }
  SysFreeString(bstrString);
  SysFreeString(String1);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000b218  push    rbx
0x18000b21a  push    rsi
0x18000b21b  push    rdi
0x18000b21c  push    r12
0x18000b21e  push    r13
0x18000b220  push    r14
0x18000b222  push    r15
0x18000b224  sub     rsp, 320h
0x18000b22b  mov     rax, cs:__security_cookie
0x18000b232  xor     rax, rsp
0x18000b235  mov     [rsp+358h+var_48], rax
0x18000b23d  mov     r14, r9
0x18000b240  mov     [rsp+358h+var_288], r9
0x18000b248  mov     r13, r8
0x18000b24b  mov     esi, edx
0x18000b24d  mov     [rsp+358h+var_2D0], edx
0x18000b254  mov     rdi, rcx
0x18000b257  mov     rdx, [rsp+358h+arg_20]; unsigned __int16 *
0x18000b25f  mov     rbx, [rsp+358h+arg_28]
0x18000b267  xor     r12d, r12d
0x18000b26a  mov     dword ptr [rsp+358h+var_308+4], r12d
0x18000b26f  lea     rcx, [rsp+358h+String1]; this
0x18000b274  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000b279  nop
0x18000b27a  mov     rdx, rbx; unsigned __int16 *
0x18000b27d  lea     rcx, [rsp+358h+bstrString]; this
0x18000b282  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000b287  nop
0x18000b288  xor     ebx, ebx
0x18000b28a  mov     byte ptr [rsp+358h+var_308], bl
0x18000b28e  mov     rdx, [r13+0C8h]
0x18000b295  test    rdx, rdx
0x18000b298  jz      short loc_18000B2CD
0x18000b29a  cmp     [rsp+358h+String1], rbx
0x18000b29f  jnz     short loc_18000B2AE
0x18000b2a1  mov     rdx, [rdx]
0x18000b2a4  lea     rcx, [rsp+358h+String1]
0x18000b2a9  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18000b2ae  mov     r15, [rsp+358h+bstrString]
0x18000b2b3  test    r15, r15
0x18000b2b6  jnz     short loc_18000B2D2
0x18000b2b8  mov     rdx, [r13+0C8h]
0x18000b2bf  mov     rdx, [rdx+8]
0x18000b2c3  lea     rcx, [rsp+358h+bstrString]
0x18000b2c8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18000b2cd  mov     r15, [rsp+358h+bstrString]
0x18000b2d2  mov     [rsp+358h+var_268], r15
0x18000b2da  xor     edx, edx; Val
0x18000b2dc  mov     r8d, 20Ah; Size
0x18000b2e2  lea     rcx, [rsp+358h+var_258]; void *
0x18000b2ea  call    memset_0
0x18000b2ef  lea     rdx, [rsp+358h+var_258]; unsigned __int16 *
0x18000b2f7  mov     rcx, r14; unsigned __int16 *
0x18000b2fa  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x18000b2ff  mov     r12d, eax
0x18000b302  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000b306  test    eax, eax
0x18000b308  jns     short loc_18000B359
0x18000b30a  test    r15, r15
0x18000b30d  jz      short loc_18000B32E
0x18000b30f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b313  inc     rax
0x18000b316  cmp     [r15+rax*2], bx
0x18000b31b  jnz     short loc_18000B313
0x18000b31d  add     rax, rax
0x18000b320  jz      short loc_18000B32E
0x18000b322  mov     [r15], bl
0x18000b325  inc     r15
0x18000b328  sub     rax, 1
0x18000b32c  jnz     short loc_18000B322
0x18000b32e  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b333  call    cs:__imp_SysFreeString
0x18000b33a  nop     dword ptr [rax+rax+00h]
0x18000b33f  nop
0x18000b340  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b345  call    cs:__imp_SysFreeString
0x18000b34c  nop     dword ptr [rax+rax+00h]
0x18000b351  mov     eax, r12d
0x18000b354  jmp     loc_18000C49C
0x18000b359  lea     rax, WPP_GLOBAL_Control
0x18000b360  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b367  cmp     rcx, rax
0x18000b36a  jz      short loc_18000B39F
0x18000b36c  test    byte ptr [rcx+1Ch], 2
0x18000b370  jz      short loc_18000B39F
0x18000b372  cmp     byte ptr [rcx+19h], 4
0x18000b376  jb      short loc_18000B39F
0x18000b378  mov     edx, 0Ah
0x18000b37d  mov     rax, [rsp+358h+String1]
0x18000b382  mov     [rsp+358h+ppsidGroup], rax
0x18000b387  lea     r9, [rsp+358h+var_258]
0x18000b38f  lea     r8, WPP_480fa276ad7e3cd82bdd80aaed5796f0_Traceguids
0x18000b396  mov     rcx, [rcx+10h]
0x18000b39a  call    WPP_SF_SS
0x18000b39f  cmp     [r13+0D0h], rbx
0x18000b3a6  jnz     loc_18000B468
0x18000b3ac  mov     rcx, r13; this
0x18000b3af  call    ?Sign@CJob@@QEAAJK@Z; CJob::Sign(ulong)
0x18000b3b4  mov     r12d, eax
0x18000b3b7  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000b3bb  test    eax, eax
0x18000b3bd  jns     short loc_18000B40E
0x18000b3bf  test    r15, r15
0x18000b3c2  jz      short loc_18000B3E3
0x18000b3c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b3c8  inc     rax
0x18000b3cb  cmp     [r15+rax*2], bx
0x18000b3d0  jnz     short loc_18000B3C8
0x18000b3d2  add     rax, rax
0x18000b3d5  jz      short loc_18000B3E3
0x18000b3d7  mov     [r15], bl
0x18000b3da  inc     r15
0x18000b3dd  sub     rax, 1
0x18000b3e1  jnz     short loc_18000B3D7
0x18000b3e3  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b3e8  call    cs:__imp_SysFreeString
0x18000b3ef  nop     dword ptr [rax+rax+00h]
0x18000b3f4  nop
0x18000b3f5  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b3fa  call    cs:__imp_SysFreeString
0x18000b401  nop     dword ptr [rax+rax+00h]
0x18000b406  mov     eax, r12d
0x18000b409  jmp     loc_18000C49C
0x18000b40e  cmp     [r13+0D0h], rbx
0x18000b415  jnz     short loc_18000B468
0x18000b417  test    r15, r15
0x18000b41a  jz      short loc_18000B43B
0x18000b41c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b420  inc     rax
0x18000b423  cmp     [r15+rax*2], bx
0x18000b428  jnz     short loc_18000B420
0x18000b42a  add     rax, rax
0x18000b42d  jz      short loc_18000B43B
0x18000b42f  mov     [r15], bl
0x18000b432  inc     r15
0x18000b435  sub     rax, 1
0x18000b439  jnz     short loc_18000B42F
0x18000b43b  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b440  call    cs:__imp_SysFreeString
0x18000b447  nop     dword ptr [rax+rax+00h]
0x18000b44c  nop
0x18000b44d  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b452  call    cs:__imp_SysFreeString
0x18000b459  nop     dword ptr [rax+rax+00h]
0x18000b45e  mov     eax, 8000FFFFh
0x18000b463  jmp     loc_18000C49C
0x18000b468  cmp     [r13+0D8h], ebx
0x18000b46f  jnz     loc_18000B531
0x18000b475  mov     rcx, r13; this
0x18000b478  call    ?Fingerprint@CJob@@QEAAJXZ; CJob::Fingerprint(void)
0x18000b47d  mov     r12d, eax
0x18000b480  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000b484  test    eax, eax
0x18000b486  jns     short loc_18000B4D7
0x18000b488  test    r15, r15
0x18000b48b  jz      short loc_18000B4AC
0x18000b48d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b491  inc     rax
0x18000b494  cmp     [r15+rax*2], bx
0x18000b499  jnz     short loc_18000B491
0x18000b49b  add     rax, rax
0x18000b49e  jz      short loc_18000B4AC
0x18000b4a0  mov     [r15], bl
0x18000b4a3  inc     r15
0x18000b4a6  sub     rax, 1
0x18000b4aa  jnz     short loc_18000B4A0
0x18000b4ac  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b4b1  call    cs:__imp_SysFreeString
0x18000b4b8  nop     dword ptr [rax+rax+00h]
0x18000b4bd  nop
0x18000b4be  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b4c3  call    cs:__imp_SysFreeString
0x18000b4ca  nop     dword ptr [rax+rax+00h]
0x18000b4cf  mov     eax, r12d
0x18000b4d2  jmp     loc_18000C49C
0x18000b4d7  cmp     [r13+0D8h], ebx
0x18000b4de  jnz     short loc_18000B531
0x18000b4e0  test    r15, r15
0x18000b4e3  jz      short loc_18000B504
0x18000b4e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b4e9  inc     rax
0x18000b4ec  cmp     [r15+rax*2], bx
0x18000b4f1  jnz     short loc_18000B4E9
0x18000b4f3  add     rax, rax
0x18000b4f6  jz      short loc_18000B504
0x18000b4f8  mov     [r15], bl
0x18000b4fb  inc     r15
0x18000b4fe  sub     rax, 1
0x18000b502  jnz     short loc_18000B4F8
0x18000b504  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b509  call    cs:__imp_SysFreeString
0x18000b510  nop     dword ptr [rax+rax+00h]
0x18000b515  nop
0x18000b516  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b51b  call    cs:__imp_SysFreeString
0x18000b522  nop     dword ptr [rax+rax+00h]
0x18000b527  mov     eax, 8000FFFFh
0x18000b52c  jmp     loc_18000C49C
0x18000b531  add     rdi, 10h
0x18000b535  mov     [rsp+358h+var_260], rdi
0x18000b53d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b540  mov     rcx, [rdi]; hHandle
0x18000b543  call    cs:__imp_WaitForSingleObject
0x18000b54a  nop     dword ptr [rax+rax+00h]
0x18000b54f  nop
0x18000b550  test    esi, esi
0x18000b552  mov     esi, 200000h
0x18000b557  jnz     loc_18000B842
0x18000b55d  test    [r13+58h], esi
0x18000b561  jz      short loc_18000B5C4
0x18000b563  mov     rcx, [rdi]; hMutex
0x18000b566  call    cs:__imp_ReleaseMutex
0x18000b56d  nop     dword ptr [rax+rax+00h]
0x18000b572  nop
0x18000b573  test    r15, r15
0x18000b576  jz      short loc_18000B597
0x18000b578  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b57c  inc     rax
0x18000b57f  cmp     [r15+rax*2], bx
0x18000b584  jnz     short loc_18000B57C
0x18000b586  add     rax, rax
0x18000b589  jz      short loc_18000B597
0x18000b58b  mov     [r15], bl
0x18000b58e  inc     r15
0x18000b591  sub     rax, 1
0x18000b595  jnz     short loc_18000B58B
0x18000b597  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b59c  call    cs:__imp_SysFreeString
0x18000b5a3  nop     dword ptr [rax+rax+00h]
0x18000b5a8  nop
0x18000b5a9  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b5ae  call    cs:__imp_SysFreeString
0x18000b5b5  nop     dword ptr [rax+rax+00h]
0x18000b5ba  mov     eax, 80070005h
0x18000b5bf  jmp     loc_18000C49C
0x18000b5c4  mov     [rsp+358h+Block], rbx
0x18000b5c9  mov     dword ptr [rsp+358h+handle], ebx
0x18000b5d0  lea     r8, [rsp+358h+handle]
0x18000b5d8  lea     rdx, [rsp+358h+Block]
0x18000b5dd  mov     rcx, r14; unsigned __int16 *
0x18000b5e0  call    ?Load@SignatureStore@@SAJPEBGAEAV?$AutoVectorPtr@E@wmi@@AEAK@Z; SignatureStore::Load(ushort const *,wmi::AutoVectorPtr<uchar> &,ulong &)
0x18000b5e5  mov     r12d, eax
0x18000b5e8  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000b5ec  test    eax, eax
0x18000b5ee  jns     short loc_18000B65A
0x18000b5f0  mov     rcx, [rsp+358h+Block]; Block
0x18000b5f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b5fa  nop
0x18000b5fb  mov     rcx, [rdi]; hMutex
0x18000b5fe  call    cs:__imp_ReleaseMutex
0x18000b605  nop     dword ptr [rax+rax+00h]
0x18000b60a  nop
0x18000b60b  test    r15, r15
0x18000b60e  jz      short loc_18000B62F
0x18000b610  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b614  inc     rax
0x18000b617  cmp     [r15+rax*2], bx
0x18000b61c  jnz     short loc_18000B614
0x18000b61e  add     rax, rax
0x18000b621  jz      short loc_18000B62F
0x18000b623  mov     [r15], bl
0x18000b626  inc     r15
0x18000b629  sub     rax, 1
0x18000b62d  jnz     short loc_18000B623
0x18000b62f  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b634  call    cs:__imp_SysFreeString
0x18000b63b  nop     dword ptr [rax+rax+00h]
0x18000b640  nop
0x18000b641  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b646  call    cs:__imp_SysFreeString
0x18000b64d  nop     dword ptr [rax+rax+00h]
0x18000b652  mov     eax, r12d
0x18000b655  jmp     loc_18000C49C
0x18000b65a  mov     rcx, [r13+0D0h]; Buf1
0x18000b661  mov     rbx, [rsp+358h+Block]
0x18000b666  xor     r14d, r14d
0x18000b669  test    rcx, rcx
0x18000b66c  jz      loc_18000B7D8
0x18000b672  test    rbx, rbx
0x18000b675  jz      loc_18000B7D8
0x18000b67b  lea     r8d, [r14+40h]; Size
0x18000b67f  mov     rdx, rbx; Buf2
0x18000b682  call    memcmp_0
0x18000b687  test    eax, eax
0x18000b689  jz      short loc_18000B6F5
0x18000b68b  mov     rcx, rbx; Block
0x18000b68e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b693  nop
0x18000b694  mov     rcx, [rdi]; hMutex
0x18000b697  call    cs:__imp_ReleaseMutex
0x18000b69e  nop     dword ptr [rax+rax+00h]
0x18000b6a3  nop
0x18000b6a4  test    r15, r15
0x18000b6a7  jz      short loc_18000B6C8
0x18000b6a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b6ad  inc     rax
0x18000b6b0  cmp     [r15+rax*2], r14w
0x18000b6b5  jnz     short loc_18000B6AD
0x18000b6b7  add     rax, rax
0x18000b6ba  jz      short loc_18000B6C8
  ... truncated ...
```
