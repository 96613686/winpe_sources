# BINDING_TABLE::ProcessApplicationBindings(ulong,ushort const *,ushort const *,INativeConfigurationElement *,INativeConfigurationElement *)

- ea: `0x1800108c0`
- end: `0x1800115b2`
- name: `?ProcessApplicationBindings@BINDING_TABLE@@AEAAJKPEBG0PEAVINativeConfigurationElement@@1@Z`
- size: `3314`
- prototype: `__int64 __fastcall(HTTP_URL_GROUP_ID *this, unsigned int, const unsigned __int16 *, wchar_t *, struct INativeConfigurationElement *, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fad0`

## callees

- `0x1800108c0`
- `0x1800115b8`
- `0x180011d44`
- `0x180012b5c`
- `0x180013374`
- `0x180013ed8`
- `0x180015e44`
- `0x180016072`
- `0x1800160a0`
- `0x180016130`
- `0x180017010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800109b5`
- `msvcrt!_ultow_s` at `0x1800109b5`
- `msvcrt!_wcsicmp` at `0x180010bad`
- `msvcrt!_wcsicmp` at `0x180010e10`
- `msvcrt!_wcsicmp` at `0x18001154c`
- `msvcrt!_wcsicmp` at `0x180010bad`
- `msvcrt!_wcsicmp` at `0x180010e10`
- `msvcrt!_wcsicmp` at `0x18001154c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fb9`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180010c15`
- `HTTPAPI!HttpAddUrlToUrlGroup` at `0x180010c15`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010948`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010955`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001095f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001099a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010bf1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010948`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010955`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001095f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001099a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010bf1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010c34`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010da9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010db6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010dc0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010dcd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010dd7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010ea9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010eb3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011529`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011533`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010c34`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010da9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010db6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010dc0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010dcd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010dd7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010ea9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010eb3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011529`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011533`
- `iisutil!PuDbgPrintError` at `0x180010c95`
- `iisutil!PuDbgPrintError` at `0x180010d23`
- `iisutil!PuDbgPrintError` at `0x18001104c`
- `iisutil!PuDbgPrintError` at `0x1800110ab`
- `iisutil!PuDbgPrintError` at `0x1800110f0`
- `iisutil!PuDbgPrintError` at `0x18001119f`
- `iisutil!PuDbgPrintError` at `0x180011246`
- `iisutil!PuDbgPrintError` at `0x1800112a0`
- `iisutil!PuDbgPrintError` at `0x1800112e5`
- `iisutil!PuDbgPrintError` at `0x18001132a`
- `iisutil!PuDbgPrintError` at `0x18001151f`
- `iisutil!PuDbgPrintError` at `0x180010c95`
- `iisutil!PuDbgPrintError` at `0x180010d23`
- `iisutil!PuDbgPrintError` at `0x18001104c`
- `iisutil!PuDbgPrintError` at `0x1800110ab`
- `iisutil!PuDbgPrintError` at `0x1800110f0`
- `iisutil!PuDbgPrintError` at `0x18001119f`
- `iisutil!PuDbgPrintError` at `0x180011246`
- `iisutil!PuDbgPrintError` at `0x1800112a0`
- `iisutil!PuDbgPrintError` at `0x1800112e5`
- `iisutil!PuDbgPrintError` at `0x18001132a`
- `iisutil!PuDbgPrintError` at `0x18001151f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b37`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010bc6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010eef`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010f2d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010f48`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010fdc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011482`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001155d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011578`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010b37`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010bc6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010eef`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010f2d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010f48`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180010fdc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011482`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001155d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011578`
- `iisutil!PuDbgPrint` at `0x18001115c`
- `iisutil!PuDbgPrint` at `0x1800111eb`
- `iisutil!PuDbgPrint` at `0x18001115c`
- `iisutil!PuDbgPrint` at `0x1800111eb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010b67`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010be4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010c52`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010e00`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010f20`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011384`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800113f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011407`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011432`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011452`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800114a8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800114b5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001158c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010b67`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010be4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010c52`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010e00`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180010f20`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011384`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800113f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011407`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011432`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011452`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800114a8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800114b5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001158c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001098d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010e5d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010e88`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001098d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010e5d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180010e88`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180011471`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180011471`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180010fab`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180010fab`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180010b4b`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180010b4b`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180010f7b`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180010f7b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180010b58`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180010e25`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001143f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001145f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180011499`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180010b58`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180010e25`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001143f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18001145f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180011499`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180010f60`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180010f60`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x180010f91`
- `iisutil!?FindStringNoCase@MULTISZ@@QEAAHPEBG@Z` at `0x180010f91`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010b19`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010e95`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010ed4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010b19`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010e95`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180010ed4`

## string_xrefs

- `0x180010a8a`: `protocol`
- `0x180010c7a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180010d1c`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x18001103a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x18001108e`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800110e9`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180011139`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180011198`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800111c8`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180011216`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180011299`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800112de`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180011323`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x18001150a`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800110cc`: ` Failed getting the protocol string \n`
- `0x180011144`: ` Protocol '%S' \n`
- `0x18001120a`: `BINDING_TABLE::AddUrlToConfigGroup`
- `0x180011236`: `Failed to set w3c control channel logging info\n   LogPeriod = %d \n   LogFileTruncateSize = %d \n   LogFileDirectory = %S \n   LocalFiletimeRollover = %S \n`

## pseudocode

```c
__int64 __fastcall BINDING_TABLE::ProcessApplicationBindings(
        HTTP_URL_GROUP_ID *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        wchar_t *a4,
        struct INativeConfigurationElement *a5,
        struct INativeConfigurationElement *a6)
{
  unsigned int v6; // edi
  unsigned int v8; // r14d
  signed int ApplicationPhysicalPath; // ebx
  signed int SiteHttpLogInfo; // esi
  int v11; // r15d
  unsigned int CCH; // ebx
  const unsigned __int16 *Str; // rax
  wchar_t *v14; // rbx
  const WCHAR *v15; // rbx
  HTTP_URL_GROUP_ID v16; // rcx
  signed int v17; // eax
  unsigned int v18; // ecx
  const wchar_t *v20; // rax
  unsigned __int16 *v21; // r15
  signed int v22; // ebx
  const unsigned __int16 *v23; // rax
  signed int LastError; // eax
  unsigned int v25; // eax
  const wchar_t *v26; // rcx
  unsigned __int16 *v27; // rcx
  signed int v28; // ebx
  int v29; // eax
  unsigned __int16 *v30; // rax
  const wchar_t *v31; // rdi
  const wchar_t *v32; // rax
  unsigned __int16 *v33; // rbx
  unsigned __int16 *v34; // rbx
  unsigned int v35; // edi
  const unsigned __int16 *v36; // rbx
  const unsigned __int16 *v37; // rax
  wchar_t *v38; // rbx
  unsigned __int16 *v39; // rax
  int v40; // eax
  unsigned __int16 *v41; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+58h] [rbp-A8h]
  __int64 v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v45; // [rsp+6Ch] [rbp-94h]
  int v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  HTTP_URL_CONTEXT UrlContext; // [rsp+90h] [rbp-70h]
  wchar_t *String1; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v52; // [rsp+A0h] [rbp-60h]
  struct INativeConfigurationElement *v53; // [rsp+A8h] [rbp-58h]
  unsigned int v54; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v55; // [rsp+B4h] [rbp-4Ch]
  unsigned int v56; // [rsp+B8h] [rbp-48h]
  enum _HTTP_LOGGING_TYPE v57; // [rsp+BCh] [rbp-44h]
  int v58; // [rsp+C0h] [rbp-40h]
  int v59; // [rsp+C4h] [rbp-3Ch]
  _BYTE v60[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v61[56]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v62[56]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v63[56]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v64[56]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v65[56]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v66[56]; // [rsp+218h] [rbp+118h] BYREF
  wchar_t Buffer[32]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v68[256]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v69[1024]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v70[1024]; // [rsp+C90h] [rbp+B90h] BYREF

  v6 = a2;
  v8 = 0;
  String1 = a4;
  v47 = 0;
  v43 = 0;
  v49 = 0;
  v44 = 0;
  v48 = 0;
  v41 = 0;
  v52 = a3;
  v45 = a2;
  v53 = a6;
  STRU::STRU((STRU *)v62);
  STRU::STRU((STRU *)v64);
  STRU::STRU((STRU *)v63);
  memset_0(v68, 0, sizeof(v68));
  STRU::STRU((STRU *)v65, v68, 0x100u);
  STRU::STRU((STRU *)v66);
  if ( _ultow_s(v6, Buffer, 0x20u, 10) )
  {
    ApplicationPhysicalPath = -2147467259;
    goto LABEL_34;
  }
  ApplicationPhysicalPath = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)a5 + 32LL))(
                              a5,
                              L"bindings",
                              &v49);
  if ( ApplicationPhysicalPath < 0 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        1704,
        "BINDING_TABLE::ProcessApplicationBindings",
        ApplicationPhysicalPath,
        " Failed getting bindings element \n");
  }
  else
  {
    ApplicationPhysicalPath = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 40LL))(v49, &v47);
    if ( ApplicationPhysicalPath < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
          1713,
          "BINDING_TABLE::ProcessApplicationBindings",
          ApplicationPhysicalPath,
          " Failed getting binding collection \n");
    }
    else
    {
      ApplicationPhysicalPath = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v47 + 24LL))(v47, &v44);
      if ( ApplicationPhysicalPath >= 0 )
      {
        SiteHttpLogInfo = 0;
        v46 = 0;
        v11 = 0;
        v42 = 0;
        while ( 1 )
        {
          while ( 1 )
          {
            if ( v8 >= v44 )
            {
              if ( v46 )
                ApplicationPhysicalPath = 0;
              goto LABEL_34;
            }
            ApplicationPhysicalPath = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 32LL))(
                                        v47,
                                        v8,
                                        &v43);
            if ( ApplicationPhysicalPath < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                  1735,
                  "BINDING_TABLE::ProcessApplicationBindings",
                  ApplicationPhysicalPath,
                  " Failed getting the binding element \n");
              goto LABEL_34;
            }
            ApplicationPhysicalPath = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v43 + 64LL))(
                                        v43,
                                        L"protocol",
                                        &v48,
                                        0,
                                        0);
            if ( ApplicationPhysicalPath < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                  1746,
                  "BINDING_TABLE::ProcessApplicationBindings",
                  ApplicationPhysicalPath,
                  " Failed getting the protocol string \n");
              goto LABEL_34;
            }
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
            {
              v26 = L"NULL";
              if ( v48 )
                v26 = v48;
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                1754,
                "BINDING_TABLE::ProcessApplicationBindings",
                " Protocol '%S' \n",
                v26);
            }
            ApplicationPhysicalPath = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v43 + 64LL))(
                                        v43,
                                        L"bindingInformation",
                                        &v41,
                                        0,
                                        0);
            if ( ApplicationPhysicalPath < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                  1766,
                  "BINDING_TABLE::ProcessApplicationBindings",
                  ApplicationPhysicalPath,
                  " Failed getting the binding info \n");
              goto LABEL_34;
            }
            if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
            {
              v27 = L"NULL";
              if ( v41 )
                v27 = v41;
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                1774,
                "BINDING_TABLE::ProcessApplicationBindings",
                " Binding '%S' \n",
                v27);
            }
            ApplicationPhysicalPath = STRU::Copy((STRU *)v64, v48);
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            ApplicationPhysicalPath = STRU::Append((STRU *)v64, L"://");
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            STRU::Reset((STRU *)v62);
            CCH = STRU::QueryCCH((STRU *)v64);
            Str = STRU::QueryStr((STRU *)v64);
            ApplicationPhysicalPath = BINDING_TABLE::TranslateBindingStringToUrlPrefix(
                                        (BINDING_TABLE *)this,
                                        v41,
                                        Str,
                                        CCH,
                                        (struct STRU *)v65,
                                        (struct STRU *)v62);
            if ( ApplicationPhysicalPath < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                if ( SiteHttpLogInfo > 0 )
                  SiteHttpLogInfo = (unsigned __int16)SiteHttpLogInfo | 0x80070000;
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                  1808,
                  "BINDING_TABLE::ProcessApplicationBindings",
                  SiteHttpLogInfo,
                  "Failed to translate binding to url prefix %S\n",
                  v41);
              }
              goto LABEL_34;
            }
            v14 = String1;
            if ( _wcsicmp(String1, L"/") )
            {
              ApplicationPhysicalPath = STRU::Append((STRU *)v62, v14);
              if ( ApplicationPhysicalPath < 0 )
                goto LABEL_34;
            }
            ApplicationPhysicalPath = STRU::Append((STRU *)v62, L"/");
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            if ( v11 != 1 )
              break;
            v20 = STRU::QueryStr((STRU *)v65);
            if ( _wcsicmp(v20, L"localhost") )
              break;
LABEL_42:
            if ( !STRU::QueryCCH((STRU *)v65) )
            {
              v21 = v41;
              memset_0(v69, 0, sizeof(v69));
              STRU::STRU((STRU *)v61, v69, 0x400u);
              memset_0(v70, 0, sizeof(v70));
              STRU::STRU((STRU *)&v54, v70, 0x400u);
              v22 = STRU::Copy((STRU *)v61, v21);
              if ( v22 >= 0 )
              {
                v33 = STRU::QueryStr((STRU *)v61);
                if ( v33[STRU::QueryCCH((STRU *)v61) - 1] == 42 )
                {
                  v34 = STRU::QueryStr((STRU *)v61);
                  v34[STRU::QueryCCH((STRU *)v61) - 1] = 0;
                  STRU::SyncWithBuffer((STRU *)v61);
                }
                v22 = STRU::Append((STRU *)v61, L"localhost");
                if ( v22 >= 0 )
                {
                  v35 = STRU::QueryCCH((STRU *)v64);
                  v36 = STRU::QueryStr((STRU *)v64);
                  v37 = STRU::QueryStr((STRU *)v61);
                  if ( BINDING_TABLE::TranslateBindingStringToUrlPrefix(
                         (BINDING_TABLE *)this,
                         v37,
                         v36,
                         v35,
                         0,
                         (struct STRU *)&v54) < 0 )
                  {
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                      PuDbgPrintError(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                        1488,
                        "BINDING_TABLE::RegisterLocalhostBinding",
                        0,
                        "Failed to translate binding to url prefix %S\n",
                        v21);
                    STRU::~STRU((STRU *)&v54);
                    STRU::~STRU((STRU *)v61);
LABEL_61:
                    if ( (g_dwDebugFlags & 0xF) != 0 )
                    {
                      if ( SiteHttpLogInfo <= 0 )
                        v25 = SiteHttpLogInfo;
                      else
                        v25 = (unsigned __int16)SiteHttpLogInfo | 0x80070000;
                      PuDbgPrintError(
                        g_pDebug,
                        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                        1902,
                        "BINDING_TABLE::ProcessApplicationBindings",
                        v25,
                        "Failed to add localhost binding to binding '%S'\n",
                        v41);
                    }
                    v11 = v42;
                    goto LABEL_46;
                  }
                  v38 = String1;
                  if ( !_wcsicmp(String1, L"/") || (v22 = STRU::Append((STRU *)&v54, v38), v22 >= 0) )
                  {
                    v22 = STRU::Append((STRU *)&v54, L"/");
                    if ( v22 >= 0 )
                    {
                      v39 = STRU::QueryStr((STRU *)&v54);
                      v40 = BINDING_TABLE::AddUrlToConfigGroup((BINDING_TABLE *)this, v39, v45, a5);
                      if ( v40 )
                      {
                        if ( v40 > 0 )
                          v22 = (unsigned __int16)v40 | 0x80070000;
                        else
                          v22 = v40;
                      }
                    }
                  }
                }
              }
              STRU::~STRU((STRU *)&v54);
              STRU::~STRU((STRU *)v61);
              if ( v22 < 0 )
                goto LABEL_61;
              v11 = 1;
              v42 = 1;
            }
LABEL_46:
            ApplicationPhysicalPath = STRU::Copy((STRU *)v63, v52);
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            ApplicationPhysicalPath = STRU::Append((STRU *)v63, L"|");
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            ApplicationPhysicalPath = GetApplicationPhysicalPath(v53, (struct STRU *)v66);
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            v23 = STRU::QueryStr((STRU *)v66);
            ApplicationPhysicalPath = STRU::Append((STRU *)v63, v23);
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            ApplicationPhysicalPath = STRU::Append((STRU *)v63, L"|");
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            ApplicationPhysicalPath = STRU::Append((STRU *)v63, (const struct STRU *)v62);
            if ( ApplicationPhysicalPath < 0 )
              goto LABEL_34;
            if ( !MULTISZ::Append((MULTISZ *)(this + 16), (struct STRU *)v63)
              || !MULTISZ::FindStringNoCase((MULTISZ *)(this + 23), v41)
              && !MULTISZ::Append((MULTISZ *)(this + 23), v41) )
            {
              LastError = GetLastError();
              ApplicationPhysicalPath = LastError;
              if ( LastError > 0 )
                ApplicationPhysicalPath = (unsigned __int16)LastError | 0x80070000;
              goto LABEL_34;
            }
            v48 = 0;
            v41 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            v43 = 0;
LABEL_31:
            v6 = v45;
            ++v8;
          }
          v15 = STRU::QueryStr((STRU *)v62);
          STRU::STRU((STRU *)v60);
          LODWORD(UrlContext) = *((_DWORD *)this + 100);
          v16 = this[48];
          HIDWORD(UrlContext) = v6;
          v17 = HttpAddUrlToUrlGroup(v16, v15, UrlContext, 0);
          SiteHttpLogInfo = v17;
          if ( v17 )
          {
            if ( v17 > 0 )
              SiteHttpLogInfo = (unsigned __int16)v17 | 0x80070000;
          }
          else
          {
            v29 = *((_DWORD *)this + 100);
            SiteHttpLogInfo = 0;
            if ( v29 == -1 )
            {
              *((_DWORD *)this + 100) = 0;
            }
            else if ( v29 )
            {
              *((_DWORD *)this + 100) = v29 + 1;
            }
            if ( !*((_DWORD *)this + 101) )
            {
              SiteHttpLogInfo = ReadSiteHttpLogInfo(a5, (struct SITE_HTTP_LOG_SETTINGS *)&v54);
              if ( SiteHttpLogInfo >= 0 )
              {
                v30 = STRU::QueryStr((STRU *)v60);
                v28 = HTTP_WRAPPER::SetConfigGroupLogging(
                        (HTTP_WRAPPER *)(this + 44),
                        this[48],
                        v59,
                        v30,
                        v57,
                        v54,
                        v55,
                        v56,
                        v58,
                        0);
                if ( v28 )
                {
                  if ( (g_dwDebugFlags & 0xF) != 0 )
                  {
                    v31 = L"TRUE";
                    if ( !v58 )
                      v31 = L"FALSE";
                    if ( STRU::QueryStr((STRU *)v60) )
                      v32 = STRU::QueryStr((STRU *)v60);
                    else
                      v32 = L"<NULL>";
                    if ( v28 > 0 )
                      v28 = (unsigned __int16)v28 | 0x80070000;
                    PuDbgPrintError(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                      523,
                      "BINDING_TABLE::AddUrlToConfigGroup",
                      v28,
                      "Failed to set w3c control channel logging info\n"
                      "   LogPeriod = %d \n"
                      "   LogFileTruncateSize = %d \n"
                      "   LogFileDirectory = %S \n"
                      "   LocalFiletimeRollover = %S \n",
                      v54,
                      v55,
                      v32,
                      v31);
                  }
                }
                else
                {
                  *((_DWORD *)this + 101) = 1;
                }
              }
            }
          }
          STRU::~STRU((STRU *)v60);
          if ( !SiteHttpLogInfo )
          {
            v46 = 1;
            goto LABEL_42;
          }
          if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            STRU::QueryStr((STRU *)v62);
            v18 = (unsigned __int16)SiteHttpLogInfo | 0x80070000;
            if ( SiteHttpLogInfo <= 0 )
              v18 = SiteHttpLogInfo;
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
              1847,
              "BINDING_TABLE::ProcessApplicationBindings",
              v18,
              "Failed to call HttpAddUrl with %S\n");
          }
          ApplicationPhysicalPath = (unsigned __int16)SiteHttpLogInfo | 0x80070000;
          if ( SiteHttpLogInfo <= 0 )
            ApplicationPhysicalPath = SiteHttpLogInfo;
          if ( SiteHttpLogInfo == 183 )
            goto LABEL_31;
          GetErrorMessage(SiteHttpLogInfo);
          v6 = v45;
          ++v8;
        }
      }
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
          1722,
          "BINDING_TABLE::ProcessApplicationBindings",
          ApplicationPhysicalPath,
          " Failed getting count of bindings in binding collection \n");
    }
  }
LABEL_34:
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  STRU::~STRU((STRU *)v66);
  STRU::~STRU((STRU *)v65);
  STRU::~STRU((STRU *)v63);
  STRU::~STRU((STRU *)v64);
  STRU::~STRU((STRU *)v62);
  return (unsigned int)ApplicationPhysicalPath;
}

```

## disassembly

```asm
0x1800108c0  push    rbp
0x1800108c2  push    rbx
0x1800108c3  push    rdi
0x1800108c4  lea     rbp, [rsp-13D0h]
0x1800108cc  mov     eax, 14D0h
0x1800108d1  call    _alloca_probe
0x1800108d6  sub     rsp, rax
0x1800108d9  mov     rax, cs:__security_cookie
0x1800108e0  xor     rax, rsp
0x1800108e3  mov     [rbp+13E0h+var_50], rax
0x1800108ea  mov     rax, [rbp+13E0h+arg_28]
0x1800108f1  mov     edi, edx
0x1800108f3  mov     [rsp+14E0h+var_20], r12
0x1800108fb  mov     r12, [rbp+13E0h+arg_20]
0x180010902  mov     [rsp+14E0h+var_28], r13
0x18001090a  mov     r13, rcx
0x18001090d  mov     [rsp+14E0h+var_30], r14
0x180010915  lea     rcx, [rbp+13E0h+var_13A8]
0x180010919  xor     r14d, r14d
0x18001091c  mov     [rbp+13E0h+String1], r9
0x180010920  mov     [rsp+14E0h+var_1468], r14
0x180010925  mov     [rsp+14E0h+var_1480], r14
0x18001092a  mov     [rbp+13E0h+var_1458], r14
0x18001092e  mov     [rsp+14E0h+var_1478], r14d
0x180010933  mov     [rbp+13E0h+var_1460], r14
0x180010937  mov     [rsp+14E0h+var_1490], r14
0x18001093c  mov     [rbp+13E0h+var_1440], r8
0x180010940  mov     [rsp+14E0h+var_1474], edx
0x180010944  mov     [rbp+13E0h+var_1438], rax
0x180010948  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001094e  lea     rcx, [rbp+13E0h+var_1338]
0x180010955  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001095b  lea     rcx, [rbp+13E0h+var_1370]
0x18001095f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180010965  xor     edx, edx; Val
0x180010967  lea     rcx, [rbp+13E0h+var_1250]; void *
0x18001096e  mov     r8d, 200h; Size
0x180010974  call    memset_0
0x180010979  mov     r8d, 100h
0x18001097f  lea     rdx, [rbp+13E0h+var_1250]
0x180010986  lea     rcx, [rbp+13E0h+var_1300]
0x18001098d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180010993  lea     rcx, [rbp+13E0h+var_12C8]
0x18001099a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800109a0  mov     r9d, 0Ah; Radix
0x1800109a6  lea     rdx, [rbp+13E0h+Buffer]; Buffer
0x1800109ad  mov     r8d, 20h ; ' '; BufferCount
0x1800109b3  mov     ecx, edi; Value
0x1800109b5  call    cs:__imp__ultow_s
0x1800109bb  test    eax, eax
0x1800109bd  jnz     loc_18001110B
0x1800109c3  mov     rax, [r12]
0x1800109c7  lea     r8, [rbp+13E0h+var_1458]
0x1800109cb  mov     [rsp+14E0h+var_18], rsi
0x1800109d3  lea     rdx, aBindings; "bindings"
0x1800109da  mov     rcx, r12
0x1800109dd  mov     [rsp+14E0h+var_38], r15
0x1800109e5  mov     rax, [rax+20h]
0x1800109e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ee  mov     ebx, eax
0x1800109f0  test    eax, eax
0x1800109f2  js      loc_180011268
0x1800109f8  mov     rcx, [rbp+13E0h+var_1458]
0x1800109fc  lea     rdx, [rsp+14E0h+var_1468]
0x180010a01  mov     rax, [rcx]
0x180010a04  mov     rax, [rax+28h]
0x180010a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a0d  mov     ebx, eax
0x180010a0f  test    eax, eax
0x180010a11  js      loc_1800112AD
0x180010a17  mov     rcx, [rsp+14E0h+var_1468]
0x180010a1c  lea     rdx, [rsp+14E0h+var_1478]
0x180010a21  mov     rax, [rcx]
0x180010a24  mov     rax, [rax+18h]
0x180010a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a2d  mov     ebx, eax
0x180010a2f  test    eax, eax
0x180010a31  js      loc_1800112F2
0x180010a37  mov     esi, r14d
0x180010a3a  mov     [rsp+14E0h+var_1470], r14d
0x180010a3f  mov     r15d, r14d
0x180010a42  mov     [rsp+14E0h+var_1488], r14d
0x180010a47  cmp     r14d, [rsp+14E0h+var_1478]
0x180010a4c  jnb     loc_1800110FD
0x180010a52  mov     rcx, [rsp+14E0h+var_1468]
0x180010a57  lea     r8, [rsp+14E0h+var_1480]
0x180010a5c  mov     edx, r14d
0x180010a5f  mov     rax, [rcx]
0x180010a62  mov     rax, [rax+20h]
0x180010a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6b  mov     ebx, eax
0x180010a6d  test    eax, eax
0x180010a6f  js      loc_180010CEF
0x180010a75  mov     rcx, [rsp+14E0h+var_1480]
0x180010a7a  lea     r8, [rbp+13E0h+var_1460]
0x180010a7e  xor     r9d, r9d
0x180010a81  mov     qword ptr [rsp+14E0h+var_14C0], 0
0x180010a8a  lea     rdx, aProtocol; "protocol"
0x180010a91  mov     rax, [rcx]
0x180010a94  mov     rax, [rax+40h]
0x180010a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a9d  mov     ebx, eax
0x180010a9f  test    eax, eax
0x180010aa1  js      loc_1800110B8
0x180010aa7  mov     eax, cs:g_dwDebugFlags
0x180010aad  test    al, 3
0x180010aaf  setnz   cl
0x180010ab2  bt      eax, 15h
0x180010ab6  setb    al
0x180010ab9  test    al, cl
0x180010abb  jnz     loc_18001111E
0x180010ac1  mov     rcx, [rsp+14E0h+var_1480]
0x180010ac6  lea     r8, [rsp+14E0h+var_1490]
0x180010acb  xor     r9d, r9d
0x180010ace  mov     qword ptr [rsp+14E0h+var_14C0], 0
0x180010ad7  lea     rdx, aBindinginforma; "bindingInformation"
0x180010ade  mov     rax, [rcx]
0x180010ae1  mov     rax, [rax+40h]
0x180010ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aea  mov     ebx, eax
0x180010aec  test    eax, eax
0x180010aee  js      loc_180011167
0x180010af4  mov     eax, cs:g_dwDebugFlags
0x180010afa  test    al, 3
0x180010afc  setnz   cl
0x180010aff  bt      eax, 15h
0x180010b03  setb    al
0x180010b06  test    al, cl
0x180010b08  jnz     loc_1800111AC
0x180010b0e  mov     rdx, [rbp+13E0h+var_1460]
0x180010b12  lea     rcx, [rbp+13E0h+var_1338]
0x180010b19  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180010b1f  mov     ebx, eax
0x180010b21  test    eax, eax
0x180010b23  js      loc_180010D29
0x180010b29  lea     rdx, asc_180018BE0; "://"
0x180010b30  lea     rcx, [rbp+13E0h+var_1338]
0x180010b37  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010b3d  mov     ebx, eax
0x180010b3f  test    eax, eax
0x180010b41  js      loc_180010D29
0x180010b47  lea     rcx, [rbp+13E0h+var_13A8]
0x180010b4b  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x180010b51  lea     rcx, [rbp+13E0h+var_1338]
0x180010b58  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180010b5e  lea     rcx, [rbp+13E0h+var_1338]
0x180010b65  mov     ebx, eax
0x180010b67  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010b6d  mov     rdx, [rsp+14E0h+var_1490]; unsigned __int16 *
0x180010b72  lea     rcx, [rbp+13E0h+var_13A8]
0x180010b76  mov     [rsp+14E0h+var_14B8], rcx; struct STRU *
0x180010b7b  mov     r9d, ebx; unsigned int
0x180010b7e  lea     rcx, [rbp+13E0h+var_1300]
0x180010b85  mov     r8, rax; unsigned __int16 *
0x180010b88  mov     qword ptr [rsp+14E0h+var_14C0], rcx; struct STRU *
0x180010b8d  mov     rcx, r13; this
0x180010b90  call    ?TranslateBindingStringToUrlPrefix@BINDING_TABLE@@AEAAJPEBG0KPEAVSTRU@@1@Z; BINDING_TABLE::TranslateBindingStringToUrlPrefix(ushort const *,ushort const *,ulong,STRU *,STRU *)
0x180010b95  mov     ebx, eax
0x180010b97  test    eax, eax
0x180010b99  js      loc_18001105C
0x180010b9f  mov     rbx, [rbp+13E0h+String1]
0x180010ba3  lea     rdx, String2; "/"
0x180010baa  mov     rcx, rbx; String1
0x180010bad  call    cs:__imp__wcsicmp
0x180010bb3  test    eax, eax
0x180010bb5  jnz     loc_180010FD5
0x180010bbb  lea     rdx, String2; "/"
0x180010bc2  lea     rcx, [rbp+13E0h+var_13A8]
0x180010bc6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180010bcc  mov     ebx, eax
0x180010bce  test    eax, eax
0x180010bd0  js      loc_180010D29
0x180010bd6  cmp     r15d, 1
0x180010bda  jz      loc_180010DF9
0x180010be0  lea     rcx, [rbp+13E0h+var_13A8]
0x180010be4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010bea  lea     rcx, [rbp+13E0h+var_1418]
0x180010bee  mov     rbx, rax
0x180010bf1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180010bf7  mov     ecx, [r13+190h]
0x180010bfe  xor     r9d, r9d; Reserved
0x180010c01  mov     dword ptr [rbp+13E0h+UrlContext], ecx
0x180010c04  mov     rdx, rbx; pFullyQualifiedUrl
0x180010c07  mov     rcx, [r13+180h]; UrlGroupId
0x180010c0e  mov     dword ptr [rbp+13E0h+UrlContext+4], edi
0x180010c11  mov     r8, [rbp+13E0h+UrlContext]; UrlContext
0x180010c15  call    cs:__imp_HttpAddUrlToUrlGroup
0x180010c1b  mov     esi, eax
0x180010c1d  test    eax, eax
0x180010c1f  jz      loc_180011337
0x180010c25  jle     short loc_180010C30
0x180010c27  movzx   esi, ax
0x180010c2a  or      esi, 80070000h
0x180010c30  lea     rcx, [rbp+13E0h+var_1418]
0x180010c34  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010c3a  test    esi, esi
0x180010c3c  jz      loc_180010FF1
0x180010c42  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010c49  movzx   ebx, si
0x180010c4c  jz      short loc_180010C9B
0x180010c4e  lea     rcx, [rbp+13E0h+var_13A8]
0x180010c52  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010c58  mov     qword ptr [rsp+14E0h+var_14B0], rax
0x180010c5d  mov     ecx, ebx
0x180010c5f  or      ecx, 80070000h
0x180010c65  lea     r9, aBindingTablePr; "BINDING_TABLE::ProcessApplicationBindin"...
0x180010c6c  test    esi, esi
0x180010c6e  lea     rax, aFailedToCallHt; "Failed to call HttpAddUrl with %S\n"
0x180010c75  mov     [rsp+14E0h+var_14B8], rax
0x180010c7a  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180010c81  cmovle  ecx, esi
0x180010c84  mov     r8d, 737h
0x180010c8a  mov     [rsp+14E0h+var_14C0], ecx
0x180010c8e  mov     rcx, cs:g_pDebug
0x180010c95  call    cs:__imp_PuDbgPrintError
0x180010c9b  mov     eax, 80070000h
0x180010ca0  or      ebx, eax
0x180010ca2  test    esi, esi
0x180010ca4  cmovle  ebx, esi
0x180010ca7  cmp     esi, 0B7h
0x180010cad  jz      short loc_180010CE3
0x180010caf  mov     ecx, esi; dwMessageId
0x180010cb1  call    GetErrorMessage
0x180010cb6  mov     edi, [rsp+14E0h+var_1474]
0x180010cba  inc     r14d
0x180010cbd  jmp     loc_180010A47
0x180010cc2  mov     rcx, [rsp+14E0h+var_1480]
0x180010cc7  xor     edi, edi
0x180010cc9  mov     [rbp+13E0h+var_1460], rdi
0x180010ccd  mov     [rsp+14E0h+var_1490], rdi
0x180010cd2  mov     rax, [rcx]
0x180010cd5  mov     rax, [rax+10h]
0x180010cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cde  mov     [rsp+14E0h+var_1480], rdi
0x180010ce3  mov     edi, [rsp+14E0h+var_1474]
0x180010ce7  inc     r14d
0x180010cea  jmp     loc_180010A47
0x180010cef  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180010cf6  jz      short loc_180010D29
0x180010cf8  mov     rcx, cs:g_pDebug
0x180010cff  lea     rax, aFailedGettingT_0; " Failed getting the binding element \n"
0x180010d06  mov     [rsp+14E0h+var_14B8], rax
0x180010d0b  lea     r9, aBindingTablePr; "BINDING_TABLE::ProcessApplicationBindin"...
0x180010d12  mov     r8d, 6C7h
0x180010d18  mov     [rsp+14E0h+var_14C0], ebx
0x180010d1c  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180010d23  call    cs:__imp_PuDbgPrintError
0x180010d29  xor     edi, edi
0x180010d2b  mov     rsi, [rsp+14E0h+var_18]
0x180010d33  mov     r15, [rsp+14E0h+var_38]
0x180010d3b  mov     rcx, [rsp+14E0h+var_1480]
0x180010d40  mov     r14, [rsp+14E0h+var_30]
0x180010d48  mov     r13, [rsp+14E0h+var_28]
0x180010d50  mov     r12, [rsp+14E0h+var_20]
0x180010d58  test    rcx, rcx
0x180010d5b  jz      short loc_180010D6E
0x180010d5d  mov     rax, [rcx]
0x180010d60  mov     rax, [rax+10h]
0x180010d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d69  mov     [rsp+14E0h+var_1480], rdi
0x180010d6e  mov     rcx, [rsp+14E0h+var_1468]
0x180010d73  test    rcx, rcx
0x180010d76  jz      short loc_180010D89
0x180010d78  mov     rax, [rcx]
0x180010d7b  mov     rax, [rax+10h]
0x180010d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d84  mov     [rsp+14E0h+var_1468], rdi
0x180010d89  mov     rcx, [rbp+13E0h+var_1458]
0x180010d8d  test    rcx, rcx
0x180010d90  jz      short loc_180010DA2
0x180010d92  mov     rax, [rcx]
0x180010d95  mov     rax, [rax+10h]
0x180010d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d9e  mov     [rbp+13E0h+var_1458], rdi
0x180010da2  lea     rcx, [rbp+13E0h+var_12C8]
0x180010da9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010daf  lea     rcx, [rbp+13E0h+var_1300]
0x180010db6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010dbc  lea     rcx, [rbp+13E0h+var_1370]
0x180010dc0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010dc6  lea     rcx, [rbp+13E0h+var_1338]
0x180010dcd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010dd3  lea     rcx, [rbp+13E0h+var_13A8]
0x180010dd7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010ddd  mov     eax, ebx
0x180010ddf  mov     rcx, [rbp+13E0h+var_50]
0x180010de6  xor     rcx, rsp; StackCookie
0x180010de9  call    __security_check_cookie
0x180010dee  add     rsp, 14D0h
0x180010df5  pop     rdi
0x180010df6  pop     rbx
0x180010df7  pop     rbp
0x180010df8  retn
0x180010df9  lea     rcx, [rbp+13E0h+var_1300]
0x180010e00  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180010e06  mov     rcx, rax; String1
0x180010e09  lea     rdx, aLocalhost; "localhost"
0x180010e10  call    cs:__imp__wcsicmp
0x180010e16  test    eax, eax
0x180010e18  jnz     loc_180010BE0
  ... truncated ...
```
