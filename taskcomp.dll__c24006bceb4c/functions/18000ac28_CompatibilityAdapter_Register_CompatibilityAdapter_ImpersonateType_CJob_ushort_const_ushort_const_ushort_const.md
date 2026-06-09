# CompatibilityAdapter::Register(CompatibilityAdapter::ImpersonateType,CJob *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000ac28`
- end: `0x18000bcc4`
- name: `?Register@CompatibilityAdapter@@QEAAJW4ImpersonateType@1@PEAVCJob@@PEBG22H@Z`
- size: `4252`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bccc`
- `0x180013c80`

## callees

- `0x180003f64`
- `0x180004194`
- `0x1800045e0`
- `0x180004e1c`
- `0x180004e50`
- `0x1800050a8`
- `0x1800050fc`
- `0x1800069a8`
- `0x180007488`
- `0x1800074c8`
- `0x180009740`
- `0x1800097dc`
- `0x180009afc`
- `0x180009ba0`
- `0x180009d60`
- `0x180009e0c`
- `0x180009e54`
- `0x180009edc`
- `0x18000a0ac`
- `0x18000a2c0`
- `0x18000a4b4`
- `0x18000a994`
- `0x18000aabc`
- `0x18000ac28`
- `0x18000bd7c`
- `0x18000c760`
- `0x18000c7a0`
- `0x180010e44`
- `0x1800143b4`
- `0x180015220`
- `0x180019690`
- `0x18002345c`
- `0x180023674`
- `0x180029b68`
- `0x18002d438`
- `0x18002d774`
- `0x18002e566`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b9d7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af17`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000af34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000afba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b041`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b0d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b16a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b1d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b2cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b39a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b44f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b537`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b64a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b706`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b7c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b892`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b976`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bc53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000af34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000afba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b041`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b0d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b16a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b1d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b2cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b39a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b44f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b537`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b64a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b706`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b7c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b892`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b976`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000bc53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b6b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b6b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b69b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b69b`
- `ntdll!RtlNtStatusToDosError` at `0x18000b785`
- `ntdll!RtlNtStatusToDosError` at `0x18000b785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bb06`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000b34f`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x18000b34f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad43`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adec`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adf8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae38`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae44`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aea9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aee9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aef5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af64`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af70`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aff6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b071`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b07d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b106`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b112`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b19a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b1a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b201`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b20d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b309`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b390`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b445`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b47f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b48b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b52d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b567`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b573`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b636`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b640`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b67a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b686`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b736`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b742`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b805`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b87e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b888`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b962`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b96c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb47`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc49`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc8f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad43`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad4f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adec`
- `OLEAUT32!__imp_SysFreeString` at `0x18000adf8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae38`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae44`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae9d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aea9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aee9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aef5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af64`
- `OLEAUT32!__imp_SysFreeString` at `0x18000af70`
- `OLEAUT32!__imp_SysFreeString` at `0x18000afea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aff6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b071`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b07d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b106`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b112`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b19a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b1a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b201`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b20d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b309`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b390`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b445`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b47f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b48b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b52d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b567`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b573`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b636`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b640`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b67a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b686`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b6fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b736`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b742`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7bf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b7f9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b805`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b87e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b888`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b8ce`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b962`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b96c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9a6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b9b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb47`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc49`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc83`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bc8f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000b3fa`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000b3fa`

## string_xrefs

- `0x18000b60b`: `CompatibilityAdapter::Register`
- `0x18000bb5f`: `SeRestorePrivilege`

## pseudocode

```c
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
0x18000ac28  push    rbx
0x18000ac2a  push    rsi
0x18000ac2b  push    rdi
0x18000ac2c  push    r12
0x18000ac2e  push    r13
0x18000ac30  push    r14
0x18000ac32  push    r15
0x18000ac34  sub     rsp, 320h
0x18000ac3b  mov     rax, cs:__security_cookie
0x18000ac42  xor     rax, rsp
0x18000ac45  mov     [rsp+358h+var_48], rax
0x18000ac4d  mov     r14, r9
0x18000ac50  mov     [rsp+358h+var_288], r9
0x18000ac58  mov     r13, r8
0x18000ac5b  mov     esi, edx
0x18000ac5d  mov     [rsp+358h+var_2D0], edx
0x18000ac64  mov     rdi, rcx
0x18000ac67  mov     rdx, [rsp+358h+arg_20]; unsigned __int16 *
0x18000ac6f  mov     rbx, [rsp+358h+arg_28]
0x18000ac77  xor     r12d, r12d
0x18000ac7a  mov     dword ptr [rsp+358h+var_308+4], r12d
0x18000ac7f  lea     rcx, [rsp+358h+String1]; this
0x18000ac84  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000ac89  nop
0x18000ac8a  mov     rdx, rbx; unsigned __int16 *
0x18000ac8d  lea     rcx, [rsp+358h+bstrString]; this
0x18000ac92  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18000ac97  nop
0x18000ac98  xor     ebx, ebx
0x18000ac9a  mov     byte ptr [rsp+358h+var_308], bl
0x18000ac9e  mov     rdx, [r13+0C8h]
0x18000aca5  test    rdx, rdx
0x18000aca8  jz      short loc_18000ACDD
0x18000acaa  cmp     [rsp+358h+String1], rbx
0x18000acaf  jnz     short loc_18000ACBE
0x18000acb1  mov     rdx, [rdx]
0x18000acb4  lea     rcx, [rsp+358h+String1]
0x18000acb9  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18000acbe  mov     r15, [rsp+358h+bstrString]
0x18000acc3  test    r15, r15
0x18000acc6  jnz     short loc_18000ACE2
0x18000acc8  mov     rdx, [r13+0C8h]
0x18000accf  mov     rdx, [rdx+8]
0x18000acd3  lea     rcx, [rsp+358h+bstrString]
0x18000acd8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18000acdd  mov     r15, [rsp+358h+bstrString]
0x18000ace2  mov     [rsp+358h+var_268], r15
0x18000acea  xor     edx, edx; Val
0x18000acec  mov     r8d, 20Ah; Size
0x18000acf2  lea     rcx, [rsp+358h+var_258]; void *
0x18000acfa  call    memset_0
0x18000acff  lea     rdx, [rsp+358h+var_258]; unsigned __int16 *
0x18000ad07  mov     rcx, r14; unsigned __int16 *
0x18000ad0a  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x18000ad0f  mov     r12d, eax
0x18000ad12  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000ad16  test    eax, eax
0x18000ad18  jns     short loc_18000AD5D
0x18000ad1a  test    r15, r15
0x18000ad1d  jz      short loc_18000AD3E
0x18000ad1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ad23  inc     rax
0x18000ad26  cmp     [r15+rax*2], bx
0x18000ad2b  jnz     short loc_18000AD23
0x18000ad2d  add     rax, rax
0x18000ad30  jz      short loc_18000AD3E
0x18000ad32  mov     [r15], bl
0x18000ad35  inc     r15
0x18000ad38  sub     rax, 1
0x18000ad3c  jnz     short loc_18000AD32
0x18000ad3e  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000ad43  call    cs:__imp_SysFreeString
0x18000ad49  nop
0x18000ad4a  mov     rcx, [rsp+358h+String1]; bstrString
0x18000ad4f  call    cs:__imp_SysFreeString
0x18000ad55  mov     eax, r12d
0x18000ad58  jmp     loc_18000BCA0
0x18000ad5d  lea     rax, WPP_GLOBAL_Control
0x18000ad64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad6b  cmp     rcx, rax
0x18000ad6e  jz      short loc_18000ADA3
0x18000ad70  test    byte ptr [rcx+1Ch], 2
0x18000ad74  jz      short loc_18000ADA3
0x18000ad76  cmp     byte ptr [rcx+19h], 4
0x18000ad7a  jb      short loc_18000ADA3
0x18000ad7c  mov     edx, 0Ah
0x18000ad81  mov     rax, [rsp+358h+String1]
0x18000ad86  mov     [rsp+358h+ppsidGroup], rax
0x18000ad8b  lea     r9, [rsp+358h+var_258]
0x18000ad93  lea     r8, WPP_480fa276ad7e3cd82bdd80aaed5796f0_Traceguids
0x18000ad9a  mov     rcx, [rcx+10h]
0x18000ad9e  call    WPP_SF_SS
0x18000ada3  cmp     [r13+0D0h], rbx
0x18000adaa  jnz     loc_18000AE54
0x18000adb0  mov     rcx, r13; this
0x18000adb3  call    ?Sign@CJob@@QEAAJK@Z; CJob::Sign(ulong)
0x18000adb8  mov     r12d, eax
0x18000adbb  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000adbf  test    eax, eax
0x18000adc1  jns     short loc_18000AE06
0x18000adc3  test    r15, r15
0x18000adc6  jz      short loc_18000ADE7
0x18000adc8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000adcc  inc     rax
0x18000adcf  cmp     [r15+rax*2], bx
0x18000add4  jnz     short loc_18000ADCC
0x18000add6  add     rax, rax
0x18000add9  jz      short loc_18000ADE7
0x18000addb  mov     [r15], bl
0x18000adde  inc     r15
0x18000ade1  sub     rax, 1
0x18000ade5  jnz     short loc_18000ADDB
0x18000ade7  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000adec  call    cs:__imp_SysFreeString
0x18000adf2  nop
0x18000adf3  mov     rcx, [rsp+358h+String1]; bstrString
0x18000adf8  call    cs:__imp_SysFreeString
0x18000adfe  mov     eax, r12d
0x18000ae01  jmp     loc_18000BCA0
0x18000ae06  cmp     [r13+0D0h], rbx
0x18000ae0d  jnz     short loc_18000AE54
0x18000ae0f  test    r15, r15
0x18000ae12  jz      short loc_18000AE33
0x18000ae14  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae18  inc     rax
0x18000ae1b  cmp     [r15+rax*2], bx
0x18000ae20  jnz     short loc_18000AE18
0x18000ae22  add     rax, rax
0x18000ae25  jz      short loc_18000AE33
0x18000ae27  mov     [r15], bl
0x18000ae2a  inc     r15
0x18000ae2d  sub     rax, 1
0x18000ae31  jnz     short loc_18000AE27
0x18000ae33  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000ae38  call    cs:__imp_SysFreeString
0x18000ae3e  nop
0x18000ae3f  mov     rcx, [rsp+358h+String1]; bstrString
0x18000ae44  call    cs:__imp_SysFreeString
0x18000ae4a  mov     eax, 8000FFFFh
0x18000ae4f  jmp     loc_18000BCA0
0x18000ae54  cmp     [r13+0D8h], ebx
0x18000ae5b  jnz     loc_18000AF05
0x18000ae61  mov     rcx, r13; this
0x18000ae64  call    ?Fingerprint@CJob@@QEAAJXZ; CJob::Fingerprint(void)
0x18000ae69  mov     r12d, eax
0x18000ae6c  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000ae70  test    eax, eax
0x18000ae72  jns     short loc_18000AEB7
0x18000ae74  test    r15, r15
0x18000ae77  jz      short loc_18000AE98
0x18000ae79  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae7d  inc     rax
0x18000ae80  cmp     [r15+rax*2], bx
0x18000ae85  jnz     short loc_18000AE7D
0x18000ae87  add     rax, rax
0x18000ae8a  jz      short loc_18000AE98
0x18000ae8c  mov     [r15], bl
0x18000ae8f  inc     r15
0x18000ae92  sub     rax, 1
0x18000ae96  jnz     short loc_18000AE8C
0x18000ae98  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000ae9d  call    cs:__imp_SysFreeString
0x18000aea3  nop
0x18000aea4  mov     rcx, [rsp+358h+String1]; bstrString
0x18000aea9  call    cs:__imp_SysFreeString
0x18000aeaf  mov     eax, r12d
0x18000aeb2  jmp     loc_18000BCA0
0x18000aeb7  cmp     [r13+0D8h], ebx
0x18000aebe  jnz     short loc_18000AF05
0x18000aec0  test    r15, r15
0x18000aec3  jz      short loc_18000AEE4
0x18000aec5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aec9  inc     rax
0x18000aecc  cmp     [r15+rax*2], bx
0x18000aed1  jnz     short loc_18000AEC9
0x18000aed3  add     rax, rax
0x18000aed6  jz      short loc_18000AEE4
0x18000aed8  mov     [r15], bl
0x18000aedb  inc     r15
0x18000aede  sub     rax, 1
0x18000aee2  jnz     short loc_18000AED8
0x18000aee4  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000aee9  call    cs:__imp_SysFreeString
0x18000aeef  nop
0x18000aef0  mov     rcx, [rsp+358h+String1]; bstrString
0x18000aef5  call    cs:__imp_SysFreeString
0x18000aefb  mov     eax, 8000FFFFh
0x18000af00  jmp     loc_18000BCA0
0x18000af05  add     rdi, 10h
0x18000af09  mov     [rsp+358h+var_260], rdi
0x18000af11  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000af14  mov     rcx, [rdi]; hHandle
0x18000af17  call    cs:__imp_WaitForSingleObject
0x18000af1d  nop
0x18000af1e  test    esi, esi
0x18000af20  mov     esi, 200000h
0x18000af25  jnz     loc_18000B1B6
0x18000af2b  test    [r13+58h], esi
0x18000af2f  jz      short loc_18000AF80
0x18000af31  mov     rcx, [rdi]; hMutex
0x18000af34  call    cs:__imp_ReleaseMutex
0x18000af3a  nop
0x18000af3b  test    r15, r15
0x18000af3e  jz      short loc_18000AF5F
0x18000af40  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000af44  inc     rax
0x18000af47  cmp     [r15+rax*2], bx
0x18000af4c  jnz     short loc_18000AF44
0x18000af4e  add     rax, rax
0x18000af51  jz      short loc_18000AF5F
0x18000af53  mov     [r15], bl
0x18000af56  inc     r15
0x18000af59  sub     rax, 1
0x18000af5d  jnz     short loc_18000AF53
0x18000af5f  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000af64  call    cs:__imp_SysFreeString
0x18000af6a  nop
0x18000af6b  mov     rcx, [rsp+358h+String1]; bstrString
0x18000af70  call    cs:__imp_SysFreeString
0x18000af76  mov     eax, 80070005h
0x18000af7b  jmp     loc_18000BCA0
0x18000af80  mov     [rsp+358h+Block], rbx
0x18000af85  mov     dword ptr [rsp+358h+handle], ebx
0x18000af8c  lea     r8, [rsp+358h+handle]
0x18000af94  lea     rdx, [rsp+358h+Block]
0x18000af99  mov     rcx, r14; unsigned __int16 *
0x18000af9c  call    ?Load@SignatureStore@@SAJPEBGAEAV?$AutoVectorPtr@E@wmi@@AEAK@Z; SignatureStore::Load(ushort const *,wmi::AutoVectorPtr<uchar> &,ulong &)
0x18000afa1  mov     r12d, eax
0x18000afa4  mov     dword ptr [rsp+358h+var_308+4], eax
0x18000afa8  test    eax, eax
0x18000afaa  jns     short loc_18000B004
0x18000afac  mov     rcx, [rsp+358h+Block]; Block
0x18000afb1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000afb6  nop
0x18000afb7  mov     rcx, [rdi]; hMutex
0x18000afba  call    cs:__imp_ReleaseMutex
0x18000afc0  nop
0x18000afc1  test    r15, r15
0x18000afc4  jz      short loc_18000AFE5
0x18000afc6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000afca  inc     rax
0x18000afcd  cmp     [r15+rax*2], bx
0x18000afd2  jnz     short loc_18000AFCA
0x18000afd4  add     rax, rax
0x18000afd7  jz      short loc_18000AFE5
0x18000afd9  mov     [r15], bl
0x18000afdc  inc     r15
0x18000afdf  sub     rax, 1
0x18000afe3  jnz     short loc_18000AFD9
0x18000afe5  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000afea  call    cs:__imp_SysFreeString
0x18000aff0  nop
0x18000aff1  mov     rcx, [rsp+358h+String1]; bstrString
0x18000aff6  call    cs:__imp_SysFreeString
0x18000affc  mov     eax, r12d
0x18000afff  jmp     loc_18000BCA0
0x18000b004  mov     rcx, [r13+0D0h]; Buf1
0x18000b00b  mov     rbx, [rsp+358h+Block]
0x18000b010  xor     r14d, r14d
0x18000b013  test    rcx, rcx
0x18000b016  jz      loc_18000B15E
0x18000b01c  test    rbx, rbx
0x18000b01f  jz      loc_18000B15E
0x18000b025  lea     r8d, [r14+40h]; Size
0x18000b029  mov     rdx, rbx; Buf2
0x18000b02c  call    memcmp_0
0x18000b031  test    eax, eax
0x18000b033  jz      short loc_18000B08D
0x18000b035  mov     rcx, rbx; Block
0x18000b038  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b03d  nop
0x18000b03e  mov     rcx, [rdi]; hMutex
0x18000b041  call    cs:__imp_ReleaseMutex
0x18000b047  nop
0x18000b048  test    r15, r15
0x18000b04b  jz      short loc_18000B06C
0x18000b04d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b051  inc     rax
0x18000b054  cmp     [r15+rax*2], r14w
0x18000b059  jnz     short loc_18000B051
0x18000b05b  add     rax, rax
0x18000b05e  jz      short loc_18000B06C
0x18000b060  mov     [r15], r14b
0x18000b063  inc     r15
0x18000b066  sub     rax, 1
0x18000b06a  jnz     short loc_18000B060
0x18000b06c  mov     rcx, [rsp+358h+bstrString]; bstrString
0x18000b071  call    cs:__imp_SysFreeString
0x18000b077  nop
0x18000b078  mov     rcx, [rsp+358h+String1]; bstrString
0x18000b07d  call    cs:__imp_SysFreeString
0x18000b083  mov     eax, 80070005h
0x18000b088  jmp     loc_18000BCA0
0x18000b08d  cmp     [rsp+358h+String1], r14
0x18000b092  jnz     loc_18000B147
0x18000b098  mov     [rsp+358h+StringSecurityDescriptor], r14
0x18000b09d  lea     r9, [rsp+358h+var_308]; bool *
0x18000b0a2  lea     r8, [rsp+358h+StringSecurityDescriptor]; struct _bstr_t *
0x18000b0a7  lea     rdx, [rsp+358h+var_258]; unsigned __int16 *
0x18000b0af  call    ?GetUserInfo@CompatibilityAdapter@@QEAAJPEBGAEAV_bstr_t@@AEA_N@Z; CompatibilityAdapter::GetUserInfo(ushort const *,_bstr_t &,bool &)
  ... truncated ...
```
