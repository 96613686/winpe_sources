# CEventNotifier::RestoreDevPersistentCBs(HKEY__ *)

- ea: `0x180001cd4`
- end: `0x180002607`
- name: `?RestoreDevPersistentCBs@CEventNotifier@@QEAAJPEAUHKEY__@@@Z`
- size: `2355`
- prototype: `int(CEventNotifier *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800028f4`
- `0x180026e80`

## callees

- `0x180001cd4`
- `0x180002610`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x180010d78`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x180034658`
- `0x1800775fc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180002522`
- `ADVAPI32!RegCloseKey` at `0x180002551`
- `ADVAPI32!RegCloseKey` at `0x1800025c2`
- `ADVAPI32!RegCloseKey` at `0x180002522`
- `ADVAPI32!RegCloseKey` at `0x180002551`
- `ADVAPI32!RegCloseKey` at `0x1800025c2`
- `ADVAPI32!RegEnumKeyExW` at `0x180001f4e`
- `ADVAPI32!RegEnumKeyExW` at `0x18000212e`
- `ADVAPI32!RegEnumKeyExW` at `0x180001f4e`
- `ADVAPI32!RegEnumKeyExW` at `0x18000212e`
- `ADVAPI32!RegOpenKeyExW` at `0x180001ef7`
- `ADVAPI32!RegOpenKeyExW` at `0x180001f78`
- `ADVAPI32!RegOpenKeyExW` at `0x180002179`
- `ADVAPI32!RegOpenKeyExW` at `0x180001ef7`
- `ADVAPI32!RegOpenKeyExW` at `0x180001f78`
- `ADVAPI32!RegOpenKeyExW` at `0x180002179`
- `ADVAPI32!RegQueryValueExW` at `0x180001e72`
- `ADVAPI32!RegQueryValueExW` at `0x180001fc3`
- `ADVAPI32!RegQueryValueExW` at `0x180002099`
- `ADVAPI32!RegQueryValueExW` at `0x1800021f6`
- `ADVAPI32!RegQueryValueExW` at `0x18000225e`
- `ADVAPI32!RegQueryValueExW` at `0x1800022c6`
- `ADVAPI32!RegQueryValueExW` at `0x180002322`
- `ADVAPI32!RegQueryValueExW` at `0x180001e72`
- `ADVAPI32!RegQueryValueExW` at `0x180001fc3`
- `ADVAPI32!RegQueryValueExW` at `0x180002099`
- `ADVAPI32!RegQueryValueExW` at `0x1800021f6`
- `ADVAPI32!RegQueryValueExW` at `0x18000225e`
- `ADVAPI32!RegQueryValueExW` at `0x1800022c6`
- `ADVAPI32!RegQueryValueExW` at `0x180002322`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e83`
- `OLEAUT32!__imp_SysAllocString` at `0x180002213`
- `OLEAUT32!__imp_SysAllocString` at `0x18000227b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800023d2`
- `OLEAUT32!__imp_SysAllocString` at `0x180001e83`
- `OLEAUT32!__imp_SysAllocString` at `0x180002213`
- `OLEAUT32!__imp_SysAllocString` at `0x18000227b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800023d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180002463`
- `OLEAUT32!__imp_SysFreeString` at `0x180002530`
- `OLEAUT32!__imp_SysFreeString` at `0x18000253e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800025d0`
- `OLEAUT32!__imp_SysFreeString` at `0x180002463`
- `OLEAUT32!__imp_SysFreeString` at `0x180002530`
- `OLEAUT32!__imp_SysFreeString` at `0x18000253e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800025d0`
- `ole32!CLSIDFromString` at `0x180001ff8`
- `ole32!CLSIDFromString` at `0x1800020ba`
- `ole32!CLSIDFromString` at `0x180002144`
- `ole32!CLSIDFromString` at `0x180001ff8`
- `ole32!CLSIDFromString` at `0x1800020ba`
- `ole32!CLSIDFromString` at `0x180002144`

## string_xrefs

- `0x180001e04`: `String copy failed (0x%X)`
- `0x180001e28`: `String copy failed (0x%X)`
- `0x180002183`: `RegOpenKeyEx() for CLSID failed.`
- `0x1800021a9`: `RegOpenKeyEx() for CLSID failed.`

## pseudocode

```c
__int64 __fastcall CEventNotifier::RestoreDevPersistentCBs(CEventNotifier *this, HKEY a2)
{
  char ***v3; // rax
  char *v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  const WCHAR *v7; // rcx
  __int64 v8; // rdx
  WCHAR *v9; // r8
  WCHAR *v10; // rcx
  unsigned int v11; // edi
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rsi
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  LSTATUS v23; // eax
  DWORD i; // edi
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  char *v30; // rbx
  void *v31; // rdx
  void **v32; // rax
  void *v33; // rdx
  __int64 v34; // rcx
  DWORD j; // r12d
  wchar_t *v36; // r14
  unsigned __int16 *v37; // r15
  char *v38; // rbx
  void *v39; // rdx
  void **v40; // rax
  void *v41; // rdx
  __int64 v42; // rcx
  int v43; // eax
  const wchar_t *v44; // r9
  BOOL v45; // edi
  char *v46; // rbx
  void *v47; // rdx
  const wchar_t *v48; // r9
  void **v49; // rax
  void *v50; // rdx
  __int64 v51; // rcx
  unsigned __int16 *v52; // r13
  CEventNotifier *v53; // rcx
  char *v54; // rbx
  void *v55; // rdx
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  char *v61; // rbx
  void *v62; // rdx
  char *v63; // rbx
  void *v64; // rdx
  char *v65; // rbx
  void *v66; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  DWORD v69; // [rsp+50h] [rbp-B0h] BYREF
  DWORD lpcbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v71; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v72; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  DWORD v75; // [rsp+74h] [rbp-8Ch]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  DWORD Type; // [rsp+84h] [rbp-7Ch] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v80[80]; // [rsp+90h] [rbp-70h] BYREF
  GUID pclsid; // [rsp+E0h] [rbp-20h] BYREF
  GUID Buf1; // [rsp+F0h] [rbp-10h] BYREF
  GUID v83; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR Data[128]; // [rsp+320h] [rbp+220h] BYREF
  BYTE v86[2]; // [rsp+420h] [rbp+320h] BYREF
  OLECHAR sz[264]; // [rsp+630h] [rbp+530h] BYREF

  v3 = (char ***)WiaTrace_Trace((const char *)&word_18007CF56);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v80, v4, v5, (char **)"CEventNotifier::RestoreDevPersistentCBs", lpData, v3);
  memset_0(SubKey, 0, 0x20Au);
  phkResult = 0;
  cchName = 0;
  ftLastWriteTime = 0;
  hKey = 0;
  v72 = 0;
  v83 = 0;
  v69 = 0;
  pclsid = 0;
  v71 = 0;
  Buf1 = 0;
  memset_0(Data, 0, sizeof(Data));
  lpcbData = 0;
  memset_0(v86, 0, 0x208u);
  v6 = 2147483646;
  Type = 1;
  v7 = L"Events";
  cbData = 256;
  v8 = 261;
  v9 = SubKey;
  do
  {
    if ( !v6 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v6;
    --v8;
  }
  while ( v8 );
  v10 = v9 - 1;
  v11 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v10 = v9;
  *v10 = 0;
  if ( !v8 )
  {
    v12 = (char *)WiaTrace_TraceLog("String copy failed (0x%X)");
    WriteDbgTraceErrorWI("CEventNotifier::RestoreDevPersistentCBs", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("String copy failed (0x%X)", v11);
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"CEventNotifier::RestoreDevPersistentCBs", 1, v14);
    goto LABEL_69;
  }
  if ( RegQueryValueExW(a2, L"DeviceID", 0, &Type, (LPBYTE)Data, &cbData) )
  {
    v17 = 0;
  }
  else
  {
    v17 = SysAllocString(Data);
    if ( !v17 )
    {
      v18 = (char *)WiaTrace_TraceLog("Out of memory!");
      WriteDbgTraceErrorWI("CEventNotifier::RestoreDevPersistentCBs", v18);
      WiaTrcLib::Free((WiaTrcLib *)v18, v19);
      v20 = (void **)WiaTrace_Trace("Out of memory!");
      WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"CEventNotifier::RestoreDevPersistentCBs", 1, v20);
      v11 = -2147024882;
      goto LABEL_69;
    }
  }
  v23 = RegOpenKeyExW(a2, SubKey, 0, 0x20019u, &phkResult);
  v11 = v23;
  if ( v23 )
  {
    if ( v23 > 0 )
      v11 = (unsigned __int16)v23 | 0x80070000;
    goto LABEL_69;
  }
  for ( i = 0; ; ++i )
  {
    v75 = i;
    cchName = 261;
    if ( RegEnumKeyExW(phkResult, i, SubKey, &cchName, 0, 0, 0, &ftLastWriteTime) )
      break;
    if ( RegOpenKeyExW(phkResult, SubKey, 0, 0x20019u, &hKey) )
      continue;
    memset_0(SubKey, 0, 0x20Au);
    lpcbData = 520;
    if ( RegQueryValueExW(hKey, L"DefaultHandler", 0, &v69, (LPBYTE)SubKey, &lpcbData) || v69 != 1 )
    {
      pclsid = 0;
    }
    else
    {
      StringCchCopyW(sz, 0x104u, SubKey);
      if ( CLSIDFromString(sz, &pclsid) >= 0 )
      {
        v25 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Default guid: %S", SubKey);
        WriteDbgTraceInfoWI("CEventNotifier::RestoreDevPersistentCBs", v25);
        WiaTrcLib::Free((WiaTrcLib *)v25, v26);
        v27 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Default guid: %S", SubKey);
        WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"CEventNotifier::RestoreDevPersistentCBs", 4, v27);
      }
    }
    memset_0(SubKey, 0, 0x20Au);
    v71 = 78;
    if ( RegQueryValueExW(hKey, L"GUID", 0, &v69, (LPBYTE)SubKey, &v71) || v69 != 1 )
    {
      v65 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Junk event %S found", SubKey);
      WriteDbgTraceInfoWI("CEventNotifier::RestoreDevPersistentCBs", v65);
      WiaTrcLib::Free((WiaTrcLib *)v65, v66);
      v32 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Junk event %S found", SubKey);
      goto LABEL_64;
    }
    if ( CLSIDFromString(SubKey, &v83) >= 0 )
    {
      for ( j = 0; ; ++j )
      {
        v71 = 39;
        if ( RegEnumKeyExW(hKey, j, SubKey, &v71, 0, 0, 0, &ftLastWriteTime) )
        {
          RegCloseKey(hKey);
          i = v75;
          goto LABEL_65;
        }
        if ( CLSIDFromString(SubKey, &Buf1) >= 0 )
          break;
LABEL_61:
        ;
      }
      v72 = 0;
      v36 = 0;
      v37 = 0;
      if ( RegOpenKeyExW(hKey, SubKey, 0, 1u, &v72) )
      {
        v38 = (char *)WiaTrace_TraceLog("RegOpenKeyEx() for CLSID failed.");
        WriteDbgTraceErrorWI("CEventNotifier::RestoreDevPersistentCBs", v38);
        WiaTrcLib::Free((WiaTrcLib *)v38, v39);
        v40 = (void **)WiaTrace_Trace("RegOpenKeyEx() for CLSID failed.");
        goto LABEL_54;
      }
      memset_0(SubKey, 0, 0x20Au);
      lpcbData = 520;
      if ( !RegQueryValueExW(v72, L"Name", 0, &v69, (LPBYTE)SubKey, &lpcbData) && v69 == 1 )
      {
        v36 = SysAllocString(SubKey);
        if ( v36 )
        {
          memset_0(SubKey, 0, 0x20Au);
          lpcbData = 520;
          if ( RegQueryValueExW(v72, L"Desc", 0, &v69, (LPBYTE)SubKey, &lpcbData) || v69 != 1 )
          {
            v61 = (char *)WiaTrace_TraceLog("RegQueryValueEx() for Desc failed.");
            WriteDbgTraceErrorWI("CEventNotifier::RestoreDevPersistentCBs", v61);
            WiaTrcLib::Free((WiaTrcLib *)v61, v62);
            v40 = (void **)WiaTrace_Trace("RegQueryValueEx() for Desc failed.");
            goto LABEL_54;
          }
          v37 = SysAllocString(SubKey);
          if ( v37 )
          {
            memset_0(SubKey, 0, 0x20Au);
            lpcbData = 520;
            if ( !RegQueryValueExW(v72, L"Icon", 0, &v69, (LPBYTE)SubKey, &lpcbData) && v69 == 1 )
            {
              memset_0(v86, 0, 0x208u);
              lpcbData = 518;
              if ( RegQueryValueExW(v72, L"Cmdline", 0, &v69, v86, &lpcbData) || v69 != 1 )
                *(_WORD *)v86 = 0;
              v43 = memcmp_0(&Buf1, &pclsid, 0x10u);
              v44 = L"NULL";
              v45 = v43 == 0;
              if ( v17 )
                v44 = v17;
              v46 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                              0,
                              0,
                              "Restoring CBs for Device: %S, Program: %S",
                              v44,
                              v36);
              WriteDbgTraceInfoWI("CEventNotifier::RestoreDevPersistentCBs", v46);
              WiaTrcLib::Free((WiaTrcLib *)v46, v47);
              v48 = L"NULL";
              if ( v17 )
                v48 = v17;
              v49 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                               0,
                               0,
                               "Restoring CBs for Device: %S, Program: %S",
                               v48,
                               v36);
              WiaTrace_ProcessTrace_Ex(v51, v50, (void *)"CEventNotifier::RestoreDevPersistentCBs", 4, v49);
              v52 = SysAllocString(SubKey);
              if ( CEventNotifier::RegisterEventCB(
                     v53,
                     v17,
                     &v83,
                     &Buf1,
                     (const unsigned __int16 *)v86,
                     v36,
                     v37,
                     v52,
                     &ftLastWriteTime,
                     v45) < 0 )
              {
                v54 = (char *)WiaTrace_TraceLog("RegisterEventCB() failed.");
                WriteDbgTraceErrorWI("CEventNotifier::RestoreDevPersistentCBs", v54);
                WiaTrcLib::Free((WiaTrcLib *)v54, v55);
                v56 = (void **)WiaTrace_Trace("RegisterEventCB() failed.");
                WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"CEventNotifier::RestoreDevPersistentCBs", 1, v56);
              }
              SysFreeString(v52);
              goto LABEL_55;
            }
            v59 = (char *)WiaTrace_TraceLog("RegQueryValueEx() for Icon failed.");
            WriteDbgTraceErrorWI("CEventNotifier::RestoreDevPersistentCBs", v59);
            WiaTrcLib::Free((WiaTrcLib *)v59, v60);
            v40 = (void **)WiaTrace_Trace("RegQueryValueEx() for Icon failed.");
LABEL_54:
            WiaTrace_ProcessTrace_Ex(v42, v41, (void *)"CEventNotifier::RestoreDevPersistentCBs", 1, v40);
          }
        }
LABEL_55:
        if ( v72 )
          RegCloseKey(v72);
        if ( v36 )
          SysFreeString(v36);
        if ( v37 )
          SysFreeString(v37);
        goto LABEL_61;
      }
      v63 = (char *)WiaTrace_TraceLog("RegQueryValueEx() for Name failed.");
      WriteDbgTraceErrorWI("CEventNotifier::RestoreDevPersistentCBs", v63);
      WiaTrcLib::Free((WiaTrcLib *)v63, v64);
      v40 = (void **)WiaTrace_Trace("RegQueryValueEx() for Name failed.");
      goto LABEL_54;
    }
    v30 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Invalid event GUID %S found", SubKey);
    WriteDbgTraceInfoWI("CEventNotifier::RestoreDevPersistentCBs", v30);
    WiaTrcLib::Free((WiaTrcLib *)v30, v31);
    v32 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Invalid event GUID %S found", SubKey);
LABEL_64:
    WiaTrace_ProcessTrace_Ex(v34, v33, (void *)"CEventNotifier::RestoreDevPersistentCBs", 4, v32);
LABEL_65:
    ;
  }
  RegCloseKey(phkResult);
  if ( v17 )
    SysFreeString(v17);
  v11 = 0;
LABEL_69:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v80);
  return v11;
}

```

## disassembly

```asm
0x180001cd4  push    rbp
0x180001cd6  push    rbx
0x180001cd7  push    rsi
0x180001cd8  push    rdi
0x180001cd9  push    r12
0x180001cdb  push    r13
0x180001cdd  push    r14
0x180001cdf  push    r15
0x180001ce1  lea     rbp, [rsp-758h]
0x180001ce9  sub     rsp, 858h
0x180001cf0  mov     rax, cs:__security_cookie
0x180001cf7  xor     rax, rsp
0x180001cfa  mov     [rbp+790h+var_50], rax
0x180001d01  lea     rcx, word_18007CF56
0x180001d08  mov     rbx, rdx
0x180001d0b  call    WiaTrace_Trace
0x180001d10  lea     r14, aCeventnotifier_3; "CEventNotifier::RestoreDevPersistentCBs"
0x180001d17  mov     [rsp+890h+lpcbData], rax; struct tagWiaTraceData_Type *
0x180001d1c  mov     r9, r14; char *
0x180001d1f  lea     rcx, [rbp+790h+var_800]; this
0x180001d23  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180001d28  mov     r15d, 20Ah
0x180001d2e  lea     rcx, [rbp+790h+SubKey]; void *
0x180001d32  mov     r8d, r15d; Size
0x180001d35  xor     edx, edx; Val
0x180001d37  call    memset_0
0x180001d3c  xor     r13d, r13d
0x180001d3f  lea     rcx, [rbp+790h+Data]; void *
0x180001d46  xorps   xmm0, xmm0
0x180001d49  mov     [rsp+890h+phkResult], r13
0x180001d4e  xorps   xmm1, xmm1
0x180001d51  mov     [rsp+890h+cchName], r13d
0x180001d56  mov     edi, 100h
0x180001d5b  mov     qword ptr [rbp+790h+ftLastWriteTime.dwLowDateTime], r13
0x180001d5f  mov     r8d, edi; Size
0x180001d62  mov     [rsp+890h+hKey], r13
0x180001d67  xor     edx, edx; Val
0x180001d69  mov     [rsp+890h+var_830], r13
0x180001d6e  movups  xmmword ptr [rbp+790h+var_790.Data1], xmm0
0x180001d72  mov     [rsp+890h+var_840], r13d
0x180001d77  movups  xmmword ptr [rbp+790h+pclsid.Data1], xmm1
0x180001d7b  mov     [rsp+890h+var_838], r13d
0x180001d80  movups  xmmword ptr [rbp+790h+Buf1.Data1], xmm0
0x180001d84  call    memset_0
0x180001d89  xor     edx, edx; Val
0x180001d8b  mov     [rsp+890h+var_83C], r13d
0x180001d90  lea     r8d, [r15-2]; Size
0x180001d94  lea     rcx, [rbp+790h+var_470]; void *
0x180001d9b  call    memset_0
0x180001da0  mov     eax, 7FFFFFFEh
0x180001da5  mov     [rbp+790h+Type], 1
0x180001dac  lea     rcx, aEvents; "Events"
0x180001db3  mov     [rbp+790h+cbData], edi
0x180001db6  lea     edx, [rdi+5]
0x180001db9  lea     r8, [rbp+790h+SubKey]
0x180001dbd  test    rax, rax
0x180001dc0  jz      short loc_180001DE1
0x180001dc2  movzx   r9d, word ptr [rcx]
0x180001dc6  test    r9w, r9w
0x180001dca  jz      short loc_180001DE1
0x180001dcc  mov     [r8], r9w
0x180001dd0  add     rcx, 2
0x180001dd4  add     r8, 2
0x180001dd8  dec     rax
0x180001ddb  sub     rdx, 1
0x180001ddf  jnz     short loc_180001DBD
0x180001de1  mov     rax, rdx
0x180001de4  lea     rcx, [r8-2]
0x180001de8  neg     rax
0x180001deb  sbb     edi, edi
0x180001ded  not     edi
0x180001def  and     edi, 8007007Ah
0x180001df5  test    rdx, rdx
0x180001df8  cmovnz  rcx, r8
0x180001dfc  mov     [rcx], r13w
0x180001e00  jnz     short loc_180001E4C
0x180001e02  mov     edx, edi
0x180001e04  lea     rcx, Format; "String copy failed (0x%X)"
0x180001e0b  call    WiaTrace_TraceLog
0x180001e10  mov     rdx, rax; char *
0x180001e13  mov     rcx, r14; char *
0x180001e16  mov     rbx, rax
0x180001e19  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180001e1e  mov     rcx, rbx; this
0x180001e21  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180001e26  mov     edx, edi
0x180001e28  lea     rcx, Format; "String copy failed (0x%X)"
0x180001e2f  call    WiaTrace_Trace
0x180001e34  mov     r9d, 1; int
0x180001e3a  mov     [rsp+890h+lpData], rax; lpMem
0x180001e3f  mov     r8, r14; int
0x180001e42  call    WiaTrace_ProcessTrace_Ex
0x180001e47  jmp     loc_1800025D9
0x180001e4c  lea     rax, [rbp+790h+cbData]
0x180001e50  xor     r8d, r8d; lpReserved
0x180001e53  mov     [rsp+890h+lpcbData], rax; lpcbData
0x180001e58  lea     r9, [rbp+790h+Type]; lpType
0x180001e5c  lea     rax, [rbp+790h+Data]
0x180001e63  mov     rcx, rbx; hKey
0x180001e66  lea     rdx, ValueName; "DeviceID"
0x180001e6d  mov     [rsp+890h+lpData], rax; lpData
0x180001e72  call    cs:__imp_RegQueryValueExW
0x180001e78  test    eax, eax
0x180001e7a  jnz     short loc_180001EDA
0x180001e7c  lea     rcx, [rbp+790h+Data]; psz
0x180001e83  call    cs:__imp_SysAllocString
0x180001e89  mov     rsi, rax
0x180001e8c  test    rax, rax
0x180001e8f  jnz     short loc_180001EDD
0x180001e91  lea     rcx, aOutOfMemory; "Out of memory!"
0x180001e98  call    WiaTrace_TraceLog
0x180001e9d  mov     rdx, rax; char *
0x180001ea0  mov     rcx, r14; char *
0x180001ea3  mov     rbx, rax
0x180001ea6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180001eab  mov     rcx, rbx; this
0x180001eae  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180001eb3  lea     rcx, aOutOfMemory; "Out of memory!"
0x180001eba  call    WiaTrace_Trace
0x180001ebf  lea     r9d, [rsi+1]; int
0x180001ec3  mov     [rsp+890h+lpData], rax; lpMem
0x180001ec8  mov     r8, r14; int
0x180001ecb  call    WiaTrace_ProcessTrace_Ex
0x180001ed0  mov     edi, 8007000Eh
0x180001ed5  jmp     loc_1800025D9
0x180001eda  mov     rsi, r13
0x180001edd  lea     rax, [rsp+890h+phkResult]
0x180001ee2  mov     r9d, 20019h; samDesired
0x180001ee8  xor     r8d, r8d; ulOptions
0x180001eeb  mov     [rsp+890h+lpData], rax; phkResult
0x180001ef0  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x180001ef4  mov     rcx, rbx; hKey
0x180001ef7  call    cs:__imp_RegOpenKeyExW
0x180001efd  mov     edi, eax
0x180001eff  test    eax, eax
0x180001f01  jz      short loc_180001F17
0x180001f03  jle     loc_1800025D9
0x180001f09  movzx   edi, ax
0x180001f0c  or      edi, 80070000h
0x180001f12  jmp     loc_1800025D9
0x180001f17  mov     edi, r13d
0x180001f1a  mov     rcx, [rsp+890h+phkResult]; hKey
0x180001f1f  lea     rax, [rbp+790h+ftLastWriteTime]
0x180001f23  mov     [rsp+890h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180001f28  lea     r9, [rsp+890h+cchName]; lpcchName
0x180001f2d  mov     [rsp+890h+lpcchClass], r13; lpcchClass
0x180001f32  lea     r8, [rbp+790h+SubKey]; lpName
0x180001f36  mov     [rsp+890h+lpcbData], r13; lpClass
0x180001f3b  mov     edx, edi; dwIndex
0x180001f3d  mov     [rsp+890h+lpData], r13; lpReserved
0x180001f42  mov     [rsp+890h+var_81C], edi
0x180001f46  mov     [rsp+890h+cchName], 105h
0x180001f4e  call    cs:__imp_RegEnumKeyExW
0x180001f54  mov     rcx, [rsp+890h+phkResult]; hKey
0x180001f59  test    eax, eax
0x180001f5b  jnz     loc_1800025C2
0x180001f61  lea     rax, [rsp+890h+hKey]
0x180001f66  mov     r9d, 20019h; samDesired
0x180001f6c  xor     r8d, r8d; ulOptions
0x180001f6f  mov     [rsp+890h+lpData], rax; phkResult
0x180001f74  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x180001f78  call    cs:__imp_RegOpenKeyExW
0x180001f7e  test    eax, eax
0x180001f80  jnz     loc_1800025BB
0x180001f86  mov     r8, r15; Size
0x180001f89  lea     rcx, [rbp+790h+SubKey]; void *
0x180001f8d  xor     edx, edx; Val
0x180001f8f  call    memset_0
0x180001f94  mov     rcx, [rsp+890h+hKey]; hKey
0x180001f99  lea     rax, [rsp+890h+var_83C]
0x180001f9e  mov     [rsp+890h+lpcbData], rax; lpcbData
0x180001fa3  lea     r9, [rsp+890h+var_840]; lpType
0x180001fa8  lea     rax, [rbp+790h+SubKey]
0x180001fac  mov     [rsp+890h+var_83C], 208h
0x180001fb4  xor     r8d, r8d; lpReserved
0x180001fb7  mov     [rsp+890h+lpData], rax; lpData
0x180001fbc  lea     rdx, aDefaulthandler; "DefaultHandler"
0x180001fc3  call    cs:__imp_RegQueryValueExW
0x180001fc9  test    eax, eax
0x180001fcb  jnz     loc_180002055
0x180001fd1  cmp     [rsp+890h+var_840], 1
0x180001fd6  jnz     short loc_180002055
0x180001fd8  lea     r8, [rbp+790h+SubKey]; unsigned __int16 *
0x180001fdc  mov     edx, 104h; unsigned __int64
0x180001fe1  lea     rcx, [rbp+790h+sz]; unsigned __int16 *
0x180001fe8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001fed  lea     rdx, [rbp+790h+pclsid]; pclsid
0x180001ff1  lea     rcx, [rbp+790h+sz]; lpsz
0x180001ff8  call    cs:__imp_CLSIDFromString
0x180001ffe  test    eax, eax
0x180002000  js      short loc_18000205C
0x180002002  lea     r9, [rbp+790h+SubKey]
0x180002006  xor     edx, edx
0x180002008  lea     r8, aDefaultGuidS; "Default guid: %S"
0x18000200f  xor     ecx, ecx
0x180002011  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180002016  mov     rdx, rax; char *
0x180002019  mov     rcx, r14; char *
0x18000201c  mov     rbx, rax
0x18000201f  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180002024  mov     rcx, rbx; this
0x180002027  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000202c  lea     r9, [rbp+790h+SubKey]
0x180002030  xor     edx, edx
0x180002032  lea     r8, aDefaultGuidS; "Default guid: %S"
0x180002039  xor     ecx, ecx
0x18000203b  call    WiaTrace_TraceWithSubCompTraceLevel
0x180002040  mov     r9d, 4; int
0x180002046  mov     [rsp+890h+lpData], rax; lpMem
0x18000204b  mov     r8, r14; int
0x18000204e  call    WiaTrace_ProcessTrace_Ex
0x180002053  jmp     short loc_18000205C
0x180002055  xorps   xmm0, xmm0
0x180002058  movups  xmmword ptr [rbp+790h+pclsid.Data1], xmm0
0x18000205c  mov     r8, r15; Size
0x18000205f  lea     rcx, [rbp+790h+SubKey]; void *
0x180002063  xor     edx, edx; Val
0x180002065  call    memset_0
0x18000206a  mov     rcx, [rsp+890h+hKey]; hKey
0x18000206f  lea     rax, [rsp+890h+var_838]
0x180002074  mov     [rsp+890h+lpcbData], rax; lpcbData
0x180002079  lea     r9, [rsp+890h+var_840]; lpType
0x18000207e  lea     rax, [rbp+790h+SubKey]
0x180002082  mov     [rsp+890h+var_838], 4Eh ; 'N'
0x18000208a  xor     r8d, r8d; lpReserved
0x18000208d  mov     [rsp+890h+lpData], rax; lpData
0x180002092  lea     rdx, aGuid; "GUID"
0x180002099  call    cs:__imp_RegQueryValueExW
0x18000209f  test    eax, eax
0x1800020a1  jnz     loc_18000256A
0x1800020a7  cmp     [rsp+890h+var_840], 1
0x1800020ac  jnz     loc_18000256A
0x1800020b2  lea     rdx, [rbp+790h+var_790]; pclsid
0x1800020b6  lea     rcx, [rbp+790h+SubKey]; lpsz
0x1800020ba  call    cs:__imp_CLSIDFromString
0x1800020c0  test    eax, eax
0x1800020c2  jns     short loc_1800020FA
0x1800020c4  lea     r9, [rbp+790h+SubKey]
0x1800020c8  xor     edx, edx
0x1800020ca  lea     r8, aInvalidEventGu; "Invalid event GUID %S found"
0x1800020d1  xor     ecx, ecx
0x1800020d3  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800020d8  mov     rdx, rax; char *
0x1800020db  mov     rcx, r14; char *
0x1800020de  mov     rbx, rax
0x1800020e1  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800020e6  mov     rcx, rbx; this
0x1800020e9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800020ee  lea     r8, aInvalidEventGu; "Invalid event GUID %S found"
0x1800020f5  jmp     loc_18000259B
0x1800020fa  mov     r12d, r13d
0x1800020fd  mov     rcx, [rsp+890h+hKey]; hKey
0x180002102  lea     rax, [rbp+790h+ftLastWriteTime]
0x180002106  mov     [rsp+890h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000210b  lea     r9, [rsp+890h+var_838]; lpcchName
0x180002110  mov     [rsp+890h+lpcchClass], r13; lpcchClass
0x180002115  lea     r8, [rbp+790h+SubKey]; lpName
0x180002119  mov     [rsp+890h+lpcbData], r13; lpClass
0x18000211e  mov     edx, r12d; dwIndex
0x180002121  mov     [rsp+890h+lpData], r13; lpReserved
0x180002126  mov     [rsp+890h+var_838], 27h ; '''
0x18000212e  call    cs:__imp_RegEnumKeyExW
0x180002134  test    eax, eax
0x180002136  jnz     loc_18000254C
0x18000213c  lea     rdx, [rbp+790h+Buf1]; pclsid
0x180002140  lea     rcx, [rbp+790h+SubKey]; lpsz
0x180002144  call    cs:__imp_CLSIDFromString
0x18000214a  test    eax, eax
0x18000214c  js      loc_180002544
0x180002152  mov     rcx, [rsp+890h+hKey]; hKey
0x180002157  lea     rax, [rsp+890h+var_830]
0x18000215c  mov     r9d, 1; samDesired
0x180002162  mov     [rsp+890h+lpData], rax; phkResult
0x180002167  xor     r8d, r8d; ulOptions
0x18000216a  mov     [rsp+890h+var_830], r13
0x18000216f  lea     rdx, [rbp+790h+SubKey]; lpSubKey
0x180002173  mov     r14, r13
0x180002176  mov     r15, r13
0x180002179  call    cs:__imp_RegOpenKeyExW
0x18000217f  test    eax, eax
0x180002181  jz      short loc_1800021B5
0x180002183  lea     rcx, aRegopenkeyexFo; "RegOpenKeyEx() for CLSID failed."
0x18000218a  call    WiaTrace_TraceLog
0x18000218f  mov     rdx, rax; char *
0x180002192  lea     rcx, aCeventnotifier_3; "CEventNotifier::RestoreDevPersistentCBs"
0x180002199  mov     rbx, rax
0x18000219c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800021a1  mov     rcx, rbx; this
0x1800021a4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800021a9  lea     rcx, aRegopenkeyexFo; "RegOpenKeyEx() for CLSID failed."
0x1800021b0  jmp     loc_1800024FC
0x1800021b5  mov     ebx, 20Ah
0x1800021ba  lea     rcx, [rbp+790h+SubKey]; void *
0x1800021be  mov     r8d, ebx; Size
0x1800021c1  xor     edx, edx; Val
0x1800021c3  call    memset_0
0x1800021c8  mov     rcx, [rsp+890h+var_830]; hKey
0x1800021cd  lea     rax, [rsp+890h+var_83C]
0x1800021d2  mov     [rsp+890h+lpcbData], rax; lpcbData
0x1800021d7  lea     edi, [rbx-2]
  ... truncated ...
```
