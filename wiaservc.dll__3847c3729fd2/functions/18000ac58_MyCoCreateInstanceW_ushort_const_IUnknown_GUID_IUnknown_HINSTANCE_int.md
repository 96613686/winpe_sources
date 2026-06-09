# MyCoCreateInstanceW(ushort const *,IUnknown *,_GUID,IUnknown * *,HINSTANCE__ * *,int *)

- ea: `0x18000ac58`
- end: `0x18000b699`
- name: `?MyCoCreateInstanceW@@YAJPEBGPEAUIUnknown@@U_GUID@@PEAPEAU1@PEAPEAUHINSTANCE__@@PEAH@Z`
- size: `2625`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz, struct IUnknown *, struct _GUID *, struct IUnknown **, HINSTANCE *, int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013c80`

## callees

- `0x180009474`
- `0x18000ac58`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000f4fc`
- `0x180011a94`
- `0x180016e88`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033cc0`
- `0x180034558`
- `0x180034658`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000af52`
- `ADVAPI32!RegCloseKey` at `0x18000af52`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ad1b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ad1b`
- `ADVAPI32!RegQueryValueExW` at `0x18000ad6b`
- `ADVAPI32!RegQueryValueExW` at `0x18000afd1`
- `ADVAPI32!RegQueryValueExW` at `0x18000ad6b`
- `ADVAPI32!RegQueryValueExW` at `0x18000afd1`
- `KERNEL32!CompareStringW` at `0x18000b146`
- `KERNEL32!CompareStringW` at `0x18000b146`
- `KERNEL32!LoadLibraryExW` at `0x18000b1f0`
- `KERNEL32!LoadLibraryExW` at `0x18000b1f0`
- `KERNEL32!FreeLibrary` at `0x18000b353`
- `KERNEL32!FreeLibrary` at `0x18000b353`
- `KERNEL32!GetLastError` at `0x18000adfe`
- `KERNEL32!GetLastError` at `0x18000b35e`
- `KERNEL32!GetLastError` at `0x18000adfe`
- `KERNEL32!GetLastError` at `0x18000b35e`
- `KERNEL32!GetProcAddress` at `0x18000b20c`
- `KERNEL32!GetProcAddress` at `0x18000b20c`
- `ole32!CLSIDFromString` at `0x18000accd`
- `ole32!CLSIDFromString` at `0x18000accd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ada4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000adf0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000ada4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000adf0`

## string_xrefs

- `0x18000af0a`: `Refer to Platform SDK documentation on COM for more information.`
- `0x18000af2c`: `Refer to Platform SDK documentation on COM for more information.`
- `0x18000b30d`: `Refer to Platform SDK documentation on COM for more information.`
- `0x18000b32f`: `Refer to Platform SDK documentation on COM for more information.`
- `0x18000aecc`: `In order for us to CoCreate the USD in process to the service, the InprocServer32 entry must exist.`
- `0x18000aeee`: `In order for us to CoCreate the USD in process to the service, the InprocServer32 entry must exist.`
- `0x18000ad71`: `MyCoCreateInstanceW`
- `0x18000b10b`: `MyCoCreateInstanceW`
- `0x18000b574`: `MyCoCreateInstanceW`
- `0x18000b630`: `MyCoCreateInstanceW`
- `0x18000b367`: `DLL Specified for CLSID %ws is bad or missing.`
- `0x18000b38e`: `DLL Specified for CLSID %ws is bad or missing.`
- `0x18000b3ad`: `DLL named %ws cannot be loaded (LoadLibraryEx returned 0x%08X).  Make sure the driver is installed correctly,`
- `0x18000b3d5`: `DLL named %ws cannot be loaded (LoadLibraryEx returned 0x%08X).  Make sure the driver is installed correctly,`
- `0x18000afc5`: `ThreadingModel`
- `0x18000b441`: `Threading Model entry for %ws is (%ws).`
- `0x18000b46d`: `Threading Model entry for %ws is (%ws).`
- `0x18000b489`: `It should be either "Free" or "Both".  We cannot CoCreate this class.`
- `0x18000b4ab`: `It should be either "Free" or "Both".  We cannot CoCreate this class.`
- `0x18000b28e`: `USD's DLL (named %ws) does not export DllGetClassObject.`
- `0x18000b2b3`: `USD's DLL (named %ws) does not export DllGetClassObject.`
- `0x18000b2cf`: `USD's DLL must export DllGetClassObject in order for us to CoCreate the USD correctly.`
- `0x18000b2f1`: `USD's DLL must export DllGetClassObject in order for us to CoCreate the USD correctly.`
- `0x18000b202`: `DllGetClassObject`
- `0x18000ae4a`: `MyCoCreateInstanceW, out of memory`
- `0x18000ae6c`: `MyCoCreateInstanceW, out of memory`
- `0x18000ace3`: `CLSID\%s\InProcServer32`
- `0x18000ae0e`: `MyCoCreateInstanceW, ExpandEnvironmentStrings(%s) failed with GLE 0x%X`
- `0x18000ae3c`: `MyCoCreateInstanceW, ExpandEnvironmentStrings(%s) failed with GLE 0x%X`
- `0x18000b184`: `Trying to Load a driver which is Apartment threaded`
- `0x18000b1a8`: `Trying to Load a driver which is Apartment threaded`
- `0x18000b5b0`: `This is usually an indications that USD's CLSID is not registered, or the incorrect CLSID appears in the USD's INF`
- `0x18000b5d2`: `This is usually an indications that USD's CLSID is not registered, or the incorrect CLSID appears in the USD's INF`
- `0x18000b5ee`: `Make sure the USD is installed correctly  and that the correct USD Class ID was specfified in the INF.`
- `0x18000b610`: `Make sure the USD is installed correctly  and that the correct USD Class ID was specfified in the INF.`
- `0x18000b624`: `USD's CLSID string is invalid.  We could not convert (%ws) to a valid GUID.`
- `0x18000b650`: `USD's CLSID string is invalid.  We could not convert (%ws) to a valid GUID.`

## pseudocode

```c
__int64 __fastcall MyCoCreateInstanceW(
        LPCOLESTR lpsz,
        struct IUnknown *a2,
        struct _GUID *a3,
        struct IUnknown **a4,
        HINSTANCE *a5,
        int *a6)
{
  char v7; // bl
  WCHAR *v8; // r15
  WCHAR *v9; // rax
  DWORD v10; // eax
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r13
  int v13; // edi
  WCHAR *v14; // rax
  DWORD LastError; // edi
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  char *v21; // rbx
  void *v22; // rdx
  char *v23; // rbx
  void *v24; // rdx
  void **v25; // rax
  void *v26; // rdx
  __int64 v27; // rcx
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  int v38; // ebx
  unsigned __int64 v39; // rdx
  bool v40; // r13
  unsigned __int64 v41; // rdx
  WCHAR *v42; // rcx
  int v43; // eax
  char *v44; // rbx
  void *v45; // rdx
  void **v46; // rax
  void *v47; // rdx
  __int64 v48; // rcx
  HMODULE Library; // rax
  HMODULE v50; // rdi
  FARPROC ProcAddress; // rax
  struct IUnknown **v52; // rsi
  unsigned __int64 v53; // rdx
  char *v54; // rbx
  void *v55; // rdx
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  void **v61; // rax
  void *v62; // rdx
  __int64 v63; // rcx
  char *v64; // rbx
  void *v65; // rdx
  void **v66; // rax
  void *v67; // rdx
  __int64 v68; // rcx
  DWORD v69; // edi
  char *v70; // rbx
  void *v71; // rdx
  void **v72; // rax
  void *v73; // rdx
  __int64 v74; // rcx
  char *v75; // rbx
  void *v76; // rdx
  void **v77; // rax
  void *v78; // rdx
  __int64 v79; // rcx
  char *v80; // rbx
  void *v81; // rdx
  void **v82; // rax
  void *v83; // rdx
  __int64 v84; // rcx
  char *v85; // rbx
  void *v86; // rdx
  void **v87; // rax
  void *v88; // rdx
  __int64 v89; // rcx
  char *v90; // rbx
  void *v91; // rdx
  void **v92; // rax
  void *v93; // rdx
  __int64 v94; // rcx
  char *v95; // rbx
  void *v96; // rdx
  void **v97; // rax
  void *v98; // rdx
  __int64 v99; // rcx
  char *v100; // rbx
  void *v101; // rdx
  void **v102; // rax
  void *v103; // rdx
  __int64 v104; // rcx
  char *v105; // rbx
  void *v106; // rdx
  void **v107; // rax
  void *v108; // rdx
  __int64 v109; // rcx
  char *v110; // rbx
  void *v111; // rdx
  int *v113; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD lpcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  struct IUnknown **v118; // [rsp+50h] [rbp-B0h]
  struct _GUID *v119; // [rsp+58h] [rbp-A8h]
  struct IUnknown *v120; // [rsp+60h] [rbp-A0h]
  HINSTANCE *v121; // [rsp+68h] [rbp-98h]
  GUID pclsid; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int64 *v123; // [rsp+80h] [rbp-80h] BYREF
  char v124; // [rsp+88h] [rbp-78h] BYREF
  PCNZWCH lpString1; // [rsp+188h] [rbp+88h]
  __int64 v126; // [rsp+190h] [rbp+90h]
  const unsigned __int64 *v127; // [rsp+1B0h] [rbp+B0h] BYREF
  char v128; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v129; // [rsp+2B8h] [rbp+1B8h]
  __int64 v130; // [rsp+2C0h] [rbp+1C0h]
  const unsigned __int64 *v131; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v132; // [rsp+2E8h] [rbp+1E8h] BYREF
  PCNZWCH lpString2; // [rsp+3E8h] [rbp+2E8h]
  _QWORD v134[38]; // [rsp+410h] [rbp+310h] BYREF
  _QWORD v135[38]; // [rsp+540h] [rbp+440h] BYREF
  const unsigned __int64 *v136; // [rsp+670h] [rbp+570h] BYREF
  char v137; // [rsp+678h] [rbp+578h] BYREF
  void *v138; // [rsp+778h] [rbp+678h]
  _QWORD v139[38]; // [rsp+7A0h] [rbp+6A0h] BYREF
  BYTE v140[80]; // [rsp+8D0h] [rbp+7D0h] BYREF
  WCHAR SubKey[80]; // [rsp+920h] [rbp+820h] BYREF
  WCHAR Data[264]; // [rsp+9C0h] [rbp+8C0h] BYREF

  v120 = a2;
  v121 = a5;
  v7 = 0;
  v118 = a4;
  Type = 0;
  *a4 = 0;
  *a5 = 0;
  v119 = a3;
  v113 = a6;
  pclsid = 0;
  if ( CLSIDFromString(lpsz, &pclsid) < 0 )
  {
    v110 = (char *)WiaTrace_TraceLog("USD's CLSID string is invalid.  We could not convert (%ws) to a valid GUID.");
    WriteDbgTraceErrorWI("MyCoCreateInstanceW", v110);
    WiaTrcLib::Free((WiaTrcLib *)v110, v111);
    v107 = (void **)WiaTrace_Trace("USD's CLSID string is invalid.  We could not convert (%ws) to a valid GUID.", lpsz);
    goto LABEL_64;
  }
  hKey = 0;
  StringCchPrintfW(SubKey, 0x4Fu, L"CLSID\\%s\\InProcServer32", lpsz);
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 1u, &hKey) )
  {
    v95 = (char *)WiaTrace_TraceLog("Entry %ws is missing from HKCR.");
    WriteDbgTraceErrorWI("MyCoCreateInstanceW", v95);
    WiaTrcLib::Free((WiaTrcLib *)v95, v96);
    v97 = (void **)WiaTrace_Trace("Entry %ws is missing from HKCR.", lpsz);
    WiaTrace_ProcessTrace_Ex(v99, v98, (void *)"MyCoCreateInstanceW", 1, v97);
    v100 = (char *)WiaTrace_TraceLog("This is usually an indications that USD's CLSID is not registered, or the incorrect"
                                     " CLSID appears in the USD's INF");
    WriteDbgTraceErrorWI("MyCoCreateInstanceW", v100);
    WiaTrcLib::Free((WiaTrcLib *)v100, v101);
    v102 = (void **)WiaTrace_Trace(
                      "This is usually an indications that USD's CLSID is not registered, or the incorrect CLSID appears "
                      "in the USD's INF");
    WiaTrace_ProcessTrace_Ex(v104, v103, (void *)"MyCoCreateInstanceW", 1, v102);
    v105 = (char *)WiaTrace_TraceLog("Make sure the USD is installed correctly  and that the correct USD Class ID was spe"
                                     "cfified in the INF.");
    WriteDbgTraceErrorWI("MyCoCreateInstanceW", v105);
    WiaTrcLib::Free((WiaTrcLib *)v105, v106);
    v107 = (void **)WiaTrace_Trace(
                      "Make sure the USD is installed correctly  and that the correct USD Class ID was specfified in the INF.");
LABEL_64:
    WiaTrace_ProcessTrace_Ex(v109, v108, (void *)"MyCoCreateInstanceW", 1, v107);
    return (unsigned int)-2147221164;
  }
  memset_0(Data, 0, 0x208u);
  cbData = 520;
  v8 = 0;
  if ( !RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData) )
  {
    v9 = (WCHAR *)operator new[](0x208u);
    v8 = v9;
    if ( v9 )
    {
      v10 = ExpandEnvironmentStringsW(Data, v9, 0x104u);
      v12 = v10;
      v13 = -1;
      if ( v10 - 1 <= 0x103 )
        goto LABEL_13;
      operator delete(v8, v11);
      v14 = (WCHAR *)operator new[](saturated_mul(v12, 2u));
      v8 = v14;
      if ( v14 )
      {
        if ( !ExpandEnvironmentStringsW(Data, v14, v12) )
        {
          LastError = GetLastError();
          v16 = (char *)WiaTrace_TraceLog("MyCoCreateInstanceW, ExpandEnvironmentStrings(%s) failed with GLE 0x%X");
          WriteDbgTraceErrorWI("MyCoCreateInstanceW", v16);
          WiaTrcLib::Free((WiaTrcLib *)v16, v17);
          v18 = (void **)WiaTrace_Trace(
                           "MyCoCreateInstanceW, ExpandEnvironmentStrings(%s) failed with GLE 0x%X",
                           (const char *)Data,
                           LastError);
LABEL_10:
          WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"MyCoCreateInstanceW", 1, v18);
          goto LABEL_11;
        }
LABEL_13:
        Type = 0;
        lpcbData = 80;
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v136, L"Both");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v127, L"Free");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v123, L"Apartment");
        v40 = 0;
        if ( !RegQueryValueExW(hKey, L"ThreadingModel", 0, &Type, v140, &lpcbData) )
        {
          CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v139, v140);
          v7 = 1;
          if ( !(unsigned int)CSimpleStringBase<unsigned short>::CompareNoCase(&v136, v139)
            || (CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v135, v140),
                v7 = 3,
                !(unsigned int)CSimpleStringBase<unsigned short>::CompareNoCase(&v127, v135))
            || (CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v134, v140),
                v7 = 7,
                !(unsigned int)CSimpleStringBase<unsigned short>::CompareNoCase(&v123, v134)) )
          {
            v40 = 1;
          }
        }
        if ( (v7 & 4) != 0 )
        {
          v7 &= ~4u;
          v134[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v134);
          v134[34] = 0;
        }
        if ( (v7 & 2) != 0 )
        {
          v7 &= ~2u;
          v135[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v135);
          v135[34] = 0;
        }
        if ( (v7 & 1) != 0 )
        {
          v139[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v139);
        }
        if ( !v40 )
        {
          v85 = (char *)WiaTrace_TraceLog("Threading Model entry for %ws is (%ws).");
          WriteDbgTraceErrorWI("MyCoCreateInstanceW", v85);
          WiaTrcLib::Free((WiaTrcLib *)v85, v86);
          v87 = (void **)WiaTrace_Trace("Threading Model entry for %ws is (%ws).", lpsz, v140);
          WiaTrace_ProcessTrace_Ex(v89, v88, (void *)"MyCoCreateInstanceW", 1, v87);
          v90 = (char *)WiaTrace_TraceLog("It should be either \"Free\" or \"Both\".  We cannot CoCreate this class.");
          WriteDbgTraceErrorWI("MyCoCreateInstanceW", v90);
          WiaTrcLib::Free((WiaTrcLib *)v90, v91);
          v92 = (void **)WiaTrace_Trace("It should be either \"Free\" or \"Both\".  We cannot CoCreate this class.");
          WiaTrace_ProcessTrace_Ex(v94, v93, (void *)"MyCoCreateInstanceW", 1, v92);
          goto LABEL_52;
        }
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v131, v140);
        v42 = (WCHAR *)lpString2;
        if ( lpString1 )
        {
          if ( lpString2 )
          {
            v43 = CompareStringW(0x400u, 1u, lpString1, -1, lpString2, -1) - 1;
            if ( v43 )
              v13 = v43 == 2;
            v42 = (WCHAR *)lpString2;
          }
          else
          {
            v13 = 1;
          }
        }
        else if ( !lpString2 )
        {
          goto LABEL_38;
        }
        v131 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( v42 && v42 != (WCHAR *)&v132 )
          operator delete(v42, v41);
        if ( v13 )
        {
          if ( v113 )
            *v113 = 0;
          goto LABEL_42;
        }
LABEL_38:
        v44 = (char *)WiaTrace_TraceLogWithSubComp(0, "Trying to Load a driver which is Apartment threaded");
        WriteDbgTraceWarningWI("MyCoCreateInstanceW", v44);
        WiaTrcLib::Free((WiaTrcLib *)v44, v45);
        v46 = (void **)WiaTrace_TraceWithSubComp(0, "Trying to Load a driver which is Apartment threaded");
        WiaTrace_ProcessTrace_Ex(v48, v47, (void *)"MyCoCreateInstanceW", 2, v46);
        if ( v113 )
          *v113 = 1;
LABEL_42:
        Library = LoadLibraryExW(v8, 0, 0x800u);
        v50 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "DllGetClassObject");
          if ( ProcAddress )
          {
            v113 = 0;
            v38 = ((__int64 (__fastcall *)(GUID *, GUID *, int **))ProcAddress)(&pclsid, &IID_IClassFactory, &v113);
            if ( v38 >= 0 )
            {
              v52 = v118;
              v38 = (*(__int64 (__fastcall **)(int *, struct IUnknown *, struct _GUID *, struct IUnknown **))(*(_QWORD *)v113 + 24LL))(
                      v113,
                      v120,
                      v119,
                      v118);
              (*(void (__fastcall **)(int *))(*(_QWORD *)v113 + 16LL))(v113);
              if ( v38 >= 0 )
              {
                *v121 = v50;
                goto LABEL_53;
              }
              *v52 = 0;
            }
          }
          else
          {
            v54 = (char *)WiaTrace_TraceLog("USD's DLL (named %ws) does not export DllGetClassObject.");
            WriteDbgTraceErrorWI("MyCoCreateInstanceW", v54);
            WiaTrcLib::Free((WiaTrcLib *)v54, v55);
            v56 = (void **)WiaTrace_Trace("USD's DLL (named %ws) does not export DllGetClassObject.", v8);
            WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"MyCoCreateInstanceW", 1, v56);
            v59 = (char *)WiaTrace_TraceLog("USD's DLL must export DllGetClassObject in order for us to CoCreate the USD correctly.");
            WriteDbgTraceErrorWI("MyCoCreateInstanceW", v59);
            WiaTrcLib::Free((WiaTrcLib *)v59, v60);
            v61 = (void **)WiaTrace_Trace("USD's DLL must export DllGetClassObject in order for us to CoCreate the USD correctly.");
            WiaTrace_ProcessTrace_Ex(v63, v62, (void *)"MyCoCreateInstanceW", 1, v61);
            v64 = (char *)WiaTrace_TraceLog("Refer to Platform SDK documentation on COM for more information.");
            WriteDbgTraceErrorWI("MyCoCreateInstanceW", v64);
            WiaTrcLib::Free((WiaTrcLib *)v64, v65);
            v66 = (void **)WiaTrace_Trace("Refer to Platform SDK documentation on COM for more information.");
            WiaTrace_ProcessTrace_Ex(v68, v67, (void *)"MyCoCreateInstanceW", 1, v66);
            v38 = -2147221164;
          }
          FreeLibrary(v50);
LABEL_53:
          v123 = &CSimpleStringBase<unsigned short>::`vftable';
          if ( lpString1 && lpString1 != (PCNZWCH)&v124 )
            operator delete((void *)lpString1, v53);
          lpString1 = 0;
          v126 = 0;
          v127 = &CSimpleStringBase<unsigned short>::`vftable';
          if ( v129 && v129 != &v128 )
            operator delete(v129, v53);
          v129 = 0;
          v130 = 0;
          v136 = &CSimpleStringBase<unsigned short>::`vftable';
          if ( v138 && v138 != &v137 )
            operator delete(v138, v53);
          goto LABEL_12;
        }
        v69 = GetLastError();
        v70 = (char *)WiaTrace_TraceLog("DLL Specified for CLSID %ws is bad or missing.");
        WriteDbgTraceErrorWI("MyCoCreateInstanceW", v70);
        WiaTrcLib::Free((WiaTrcLib *)v70, v71);
        v72 = (void **)WiaTrace_Trace("DLL Specified for CLSID %ws is bad or missing.", lpsz);
        WiaTrace_ProcessTrace_Ex(v74, v73, (void *)"MyCoCreateInstanceW", 1, v72);
        v75 = (char *)WiaTrace_TraceLog("DLL named %ws cannot be loaded (LoadLibraryEx returned 0x%08X).  Make sure the d"
                                        "river is installed correctly,");
        WriteDbgTraceErrorWI("MyCoCreateInstanceW", v75);
        WiaTrcLib::Free((WiaTrcLib *)v75, v76);
        v77 = (void **)WiaTrace_Trace(
                         "DLL named %ws cannot be loaded (LoadLibraryEx returned 0x%08X).  Make sure the driver is installed correctly,",
                         v8,
                         v69);
        WiaTrace_ProcessTrace_Ex(v79, v78, (void *)"MyCoCreateInstanceW", 1, v77);
        v80 = (char *)WiaTrace_TraceLog("and that the correct USD Class was specfified in the device's INF.");
        WriteDbgTraceErrorWI("MyCoCreateInstanceW", v80);
        WiaTrcLib::Free((WiaTrcLib *)v80, v81);
        v82 = (void **)WiaTrace_Trace("and that the correct USD Class was specfified in the device's INF.");
        WiaTrace_ProcessTrace_Ex(v84, v83, (void *)"MyCoCreateInstanceW", 1, v82);
LABEL_52:
        v38 = -2147221164;
        goto LABEL_53;
      }
    }
    v21 = (char *)WiaTrace_TraceLog("MyCoCreateInstanceW, out of memory");
    WriteDbgTraceErrorWI("MyCoCreateInstanceW", v21);
    WiaTrcLib::Free((WiaTrcLib *)v21, v22);
    v18 = (void **)WiaTrace_Trace("MyCoCreateInstanceW, out of memory");
    goto LABEL_10;
  }
LABEL_11:
  v23 = (char *)WiaTrace_TraceLog("Entry for %ws is missing InProcServer32 sub-key.");
  WriteDbgTraceErrorWI("MyCoCreateInstanceW", v23);
  WiaTrcLib::Free((WiaTrcLib *)v23, v24);
  v25 = (void **)WiaTrace_Trace("Entry for %ws is missing InProcServer32 sub-key.", lpsz);
  WiaTrace_ProcessTrace_Ex(v27, v26, (void *)"MyCoCreateInstanceW", 1, v25);
  v28 = (char *)WiaTrace_TraceLog("In order for us to CoCreate the USD in process to the service, the InprocServer32 entry must exist.");
  WriteDbgTraceErrorWI("MyCoCreateInstanceW", v28);
  WiaTrcLib::Free((WiaTrcLib *)v28, v29);
  v30 = (void **)WiaTrace_Trace("In order for us to CoCreate the USD in process to the service, the InprocServer32 entry must exist.");
  WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"MyCoCreateInstanceW", 1, v30);
  v33 = (char *)WiaTrace_TraceLog("Refer to Platform SDK documentation on COM for more information.");
  WriteDbgTraceErrorWI("MyCoCreateInstanceW", v33);
  WiaTrcLib::Free((WiaTrcLib *)v33, v34);
  v35 = (void **)WiaTrace_Trace("Refer to Platform SDK documentation on COM for more information.");
  WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"MyCoCreateInstanceW", 1, v35);
  v38 = -2147221164;
LABEL_12:
  RegCloseKey(hKey);
  operator delete(v8, v39);
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x18000ac58  push    rbp
0x18000ac5a  push    rbx
0x18000ac5b  push    rsi
0x18000ac5c  push    rdi
0x18000ac5d  push    r12
0x18000ac5f  push    r13
0x18000ac61  push    r14
0x18000ac63  push    r15
0x18000ac65  lea     rbp, [rsp-0AE8h]
0x18000ac6d  sub     rsp, 0BE8h
0x18000ac74  mov     rax, cs:__security_cookie
0x18000ac7b  xor     rax, rsp
0x18000ac7e  mov     [rbp+0B20h+var_50], rax
0x18000ac85  mov     rax, [rbp+0B20h+arg_28]
0x18000ac8c  mov     r12, rcx
0x18000ac8f  mov     rcx, [rbp+0B20h+arg_20]
0x18000ac96  xor     edi, edi
0x18000ac98  mov     [rsp+0C20h+var_BC0], rdx
0x18000ac9d  xorps   xmm0, xmm0
0x18000aca0  mov     [rsp+0C20h+var_BB8], rcx
0x18000aca5  lea     rdx, [rsp+0C20h+pclsid]; pclsid
0x18000acaa  mov     ebx, edi
0x18000acac  mov     [rsp+0C20h+var_BD0], r9
0x18000acb1  mov     [rsp+0C20h+Type], ebx
0x18000acb5  mov     [r9], rdi
0x18000acb8  mov     [rcx], rdi
0x18000acbb  mov     rcx, r12; lpsz
0x18000acbe  mov     [rsp+0C20h+var_BC8], r8
0x18000acc3  mov     [rsp+0C20h+var_BF0], rax
0x18000acc8  movups  xmmword ptr [rsp+0C20h+pclsid.Data1], xmm0
0x18000accd  call    cs:__imp_CLSIDFromString
0x18000acd3  test    eax, eax
0x18000acd5  js      loc_18000B621
0x18000acdb  mov     r9, r12
0x18000acde  mov     [rsp+0C20h+hKey], rdi
0x18000ace3  lea     r8, aClsidSInprocse; "CLSID\\%s\\InProcServer32"
0x18000acea  lea     edx, [rdi+4Fh]; unsigned __int64
0x18000aced  lea     rcx, [rbp+0B20h+SubKey]; unsigned __int16 *
0x18000acf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000acf9  lea     rax, [rsp+0C20h+hKey]
0x18000acfe  xor     r8d, r8d; ulOptions
0x18000ad01  lea     r14d, [rdi+1]
0x18000ad05  mov     [rsp+0C20h+phkResult], rax; phkResult
0x18000ad0a  mov     r9d, r14d; samDesired
0x18000ad0d  lea     rdx, [rbp+0B20h+SubKey]; lpSubKey
0x18000ad14  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000ad1b  call    cs:__imp_RegOpenKeyExW
0x18000ad21  test    eax, eax
0x18000ad23  jnz     loc_18000B565
0x18000ad29  mov     r13d, 208h
0x18000ad2f  lea     rcx, [rbp+0B20h+Data]; void *
0x18000ad36  mov     r8d, r13d; Size
0x18000ad39  xor     edx, edx; Val
0x18000ad3b  call    memset_0
0x18000ad40  mov     rcx, [rsp+0C20h+hKey]; hKey
0x18000ad45  lea     rax, [rsp+0C20h+cbData]
0x18000ad4a  mov     [rsp+0C20h+lpcbData], rax; lpcbData
0x18000ad4f  xor     r9d, r9d; lpType
0x18000ad52  lea     rax, [rbp+0B20h+Data]
0x18000ad59  mov     [rsp+0C20h+cbData], r13d
0x18000ad5e  xor     r8d, r8d; lpReserved
0x18000ad61  mov     [rsp+0C20h+phkResult], rax; lpData
0x18000ad66  xor     edx, edx; lpValueName
0x18000ad68  mov     r15d, edi
0x18000ad6b  call    cs:__imp_RegQueryValueExW
0x18000ad71  lea     rsi, aMycocreateinst_0; "MyCoCreateInstanceW"
0x18000ad78  test    eax, eax
0x18000ad7a  jnz     loc_18000AE88
0x18000ad80  mov     ecx, r13d; unsigned __int64
0x18000ad83  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ad88  mov     r15, rax
0x18000ad8b  test    rax, rax
0x18000ad8e  jz      loc_18000AE4A
0x18000ad94  mov     r8d, 104h; nSize
0x18000ad9a  lea     rcx, [rbp+0B20h+Data]; lpSrc
0x18000ada1  mov     rdx, rax; lpDst
0x18000ada4  call    cs:__imp_ExpandEnvironmentStringsW
0x18000adaa  mov     r13d, eax
0x18000adad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000adb1  lea     ecx, [r13-1]
0x18000adb5  cmp     ecx, 103h
0x18000adbb  jbe     loc_18000AF65
0x18000adc1  mov     rcx, r15; void *
0x18000adc4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000adc9  lea     eax, [rdi+3]
0x18000adcc  mul     r13
0x18000adcf  cmovb   rax, rdi
0x18000add3  mov     rcx, rax; unsigned __int64
0x18000add6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000addb  mov     r15, rax
0x18000adde  test    rax, rax
0x18000ade1  jz      short loc_18000AE4A
0x18000ade3  mov     r8d, r13d; nSize
0x18000ade6  lea     rcx, [rbp+0B20h+Data]; lpSrc
0x18000aded  mov     rdx, rax; lpDst
0x18000adf0  call    cs:__imp_ExpandEnvironmentStringsW
0x18000adf6  test    eax, eax
0x18000adf8  jnz     loc_18000AF65
0x18000adfe  call    cs:__imp_GetLastError
0x18000ae04  mov     r8d, eax
0x18000ae07  lea     rdx, [rbp+0B20h+Data]
0x18000ae0e  lea     rcx, aMycocreateinst_1; "MyCoCreateInstanceW, ExpandEnvironmentS"...
0x18000ae15  mov     edi, eax
0x18000ae17  call    WiaTrace_TraceLog
0x18000ae1c  mov     rdx, rax; char *
0x18000ae1f  mov     rcx, rsi; char *
0x18000ae22  mov     rbx, rax
0x18000ae25  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000ae2a  mov     rcx, rbx; this
0x18000ae2d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000ae32  mov     r8d, edi
0x18000ae35  lea     rdx, [rbp+0B20h+Data]
0x18000ae3c  lea     rcx, aMycocreateinst_1; "MyCoCreateInstanceW, ExpandEnvironmentS"...
0x18000ae43  call    WiaTrace_Trace
0x18000ae48  jmp     short loc_18000AE78
0x18000ae4a  lea     rcx, aMycocreateinst; "MyCoCreateInstanceW, out of memory"
0x18000ae51  call    WiaTrace_TraceLog
0x18000ae56  mov     rdx, rax; char *
0x18000ae59  mov     rcx, rsi; char *
0x18000ae5c  mov     rbx, rax
0x18000ae5f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000ae64  mov     rcx, rbx; this
0x18000ae67  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000ae6c  lea     rcx, aMycocreateinst; "MyCoCreateInstanceW, out of memory"
0x18000ae73  call    WiaTrace_Trace
0x18000ae78  mov     r9d, r14d; int
0x18000ae7b  mov     [rsp+0C20h+phkResult], rax; lpMem
0x18000ae80  mov     r8, rsi; int
0x18000ae83  call    WiaTrace_ProcessTrace_Ex
0x18000ae88  mov     rdx, r12
0x18000ae8b  lea     rcx, aEntryForWsIsMi; "Entry for %ws is missing InProcServer32"...
0x18000ae92  call    WiaTrace_TraceLog
0x18000ae97  mov     rdx, rax; char *
0x18000ae9a  mov     rcx, rsi; char *
0x18000ae9d  mov     rbx, rax
0x18000aea0  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000aea5  mov     rcx, rbx; this
0x18000aea8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000aead  mov     rdx, r12
0x18000aeb0  lea     rcx, aEntryForWsIsMi; "Entry for %ws is missing InProcServer32"...
0x18000aeb7  call    WiaTrace_Trace
0x18000aebc  mov     r9d, r14d; int
0x18000aebf  mov     [rsp+0C20h+phkResult], rax; lpMem
0x18000aec4  mov     r8, rsi; int
0x18000aec7  call    WiaTrace_ProcessTrace_Ex
0x18000aecc  lea     rcx, aInOrderForUsTo; "In order for us to CoCreate the USD in "...
0x18000aed3  call    WiaTrace_TraceLog
0x18000aed8  mov     rdx, rax; char *
0x18000aedb  mov     rcx, rsi; char *
0x18000aede  mov     rbx, rax
0x18000aee1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000aee6  mov     rcx, rbx; this
0x18000aee9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000aeee  lea     rcx, aInOrderForUsTo; "In order for us to CoCreate the USD in "...
0x18000aef5  call    WiaTrace_Trace
0x18000aefa  mov     r9d, r14d; int
0x18000aefd  mov     [rsp+0C20h+phkResult], rax; lpMem
0x18000af02  mov     r8, rsi; int
0x18000af05  call    WiaTrace_ProcessTrace_Ex
0x18000af0a  lea     rcx, aReferToPlatfor; "Refer to Platform SDK documentation on "...
0x18000af11  call    WiaTrace_TraceLog
0x18000af16  mov     rdx, rax; char *
0x18000af19  mov     rcx, rsi; char *
0x18000af1c  mov     rbx, rax
0x18000af1f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000af24  mov     rcx, rbx; this
0x18000af27  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000af2c  lea     rcx, aReferToPlatfor; "Refer to Platform SDK documentation on "...
0x18000af33  call    WiaTrace_Trace
0x18000af38  mov     r9d, r14d; int
0x18000af3b  mov     [rsp+0C20h+phkResult], rax; lpMem
0x18000af40  mov     r8, rsi; int
0x18000af43  call    WiaTrace_ProcessTrace_Ex
0x18000af48  mov     ebx, 80040154h
0x18000af4d  mov     rcx, [rsp+0C20h+hKey]; hKey
0x18000af52  call    cs:__imp_RegCloseKey
0x18000af58  mov     rcx, r15; void *
0x18000af5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000af60  jmp     loc_18000B674
0x18000af65  lea     rdx, aBoth; "Both"
0x18000af6c  mov     [rsp+0C20h+Type], ebx
0x18000af70  lea     rcx, [rbp+0B20h+var_5B0]
0x18000af77  mov     [rsp+0C20h+var_BD4], 50h ; 'P'
0x18000af7f  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000af84  lea     rdx, aFree; "Free"
0x18000af8b  lea     rcx, [rbp+0B20h+var_A70]
0x18000af92  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000af97  lea     rdx, aApartment; "Apartment"
0x18000af9e  lea     rcx, [rbp+0B20h+var_BA0]
0x18000afa2  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000afa7  mov     rcx, [rsp+0C20h+hKey]; hKey
0x18000afac  lea     rax, [rsp+0C20h+var_BD4]
0x18000afb1  mov     [rsp+0C20h+lpcbData], rax; lpcbData
0x18000afb6  lea     r9, [rsp+0C20h+Type]; lpType
0x18000afbb  lea     rax, [rbp+0B20h+var_350]
0x18000afc2  xor     r8d, r8d; lpReserved
0x18000afc5  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18000afcc  mov     [rsp+0C20h+phkResult], rax; lpData
0x18000afd1  call    cs:__imp_RegQueryValueExW
0x18000afd7  test    eax, eax
0x18000afd9  jnz     loc_18000B06C
0x18000afdf  lea     rdx, [rbp+0B20h+var_350]
0x18000afe6  lea     rcx, [rbp+0B20h+var_480]
0x18000afed  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000aff2  lea     rdx, [rbp+0B20h+var_480]
0x18000aff9  mov     ebx, r14d
0x18000affc  lea     rcx, [rbp+0B20h+var_5B0]
0x18000b003  call    ?CompareNoCase@?$CSimpleStringBase@G@@QEBAHAEBV1@H@Z; CSimpleStringBase<ushort>::CompareNoCase(CSimpleStringBase<ushort> const &,int)
0x18000b008  test    eax, eax
0x18000b00a  jz      short loc_18000B067
0x18000b00c  lea     rdx, [rbp+0B20h+var_350]
0x18000b013  lea     rcx, [rbp+0B20h+var_6E0]
0x18000b01a  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000b01f  lea     rdx, [rbp+0B20h+var_6E0]
0x18000b026  mov     ebx, 3
0x18000b02b  lea     rcx, [rbp+0B20h+var_A70]
0x18000b032  call    ?CompareNoCase@?$CSimpleStringBase@G@@QEBAHAEBV1@H@Z; CSimpleStringBase<ushort>::CompareNoCase(CSimpleStringBase<ushort> const &,int)
0x18000b037  test    eax, eax
0x18000b039  jz      short loc_18000B067
0x18000b03b  lea     rdx, [rbp+0B20h+var_350]
0x18000b042  lea     rcx, [rbp+0B20h+var_810]
0x18000b049  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000b04e  lea     rdx, [rbp+0B20h+var_810]
0x18000b055  mov     ebx, 7
0x18000b05a  lea     rcx, [rbp+0B20h+var_BA0]
0x18000b05e  call    ?CompareNoCase@?$CSimpleStringBase@G@@QEBAHAEBV1@H@Z; CSimpleStringBase<ushort>::CompareNoCase(CSimpleStringBase<ushort> const &,int)
0x18000b063  test    eax, eax
0x18000b065  jnz     short loc_18000B06C
0x18000b067  mov     r13b, r14b
0x18000b06a  jmp     short loc_18000B06F
0x18000b06c  xor     r13b, r13b
0x18000b06f  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000b076  test    bl, 4
0x18000b079  jz      short loc_18000B0A3
0x18000b07b  and     ebx, 0FFFFFFFBh
0x18000b07e  mov     [rbp+0B20h+var_810], rax
0x18000b085  lea     rcx, [rbp+0B20h+var_810]
0x18000b08c  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000b091  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000b098  mov     [rbp+0B20h+var_700], 0
0x18000b0a3  test    bl, 2
0x18000b0a6  jz      short loc_18000B0C9
0x18000b0a8  and     ebx, 0FFFFFFFDh
0x18000b0ab  mov     [rbp+0B20h+var_6E0], rax
0x18000b0b2  lea     rcx, [rbp+0B20h+var_6E0]
0x18000b0b9  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000b0be  mov     [rbp+0B20h+var_5D0], 0
0x18000b0c9  test    r14b, bl
0x18000b0cc  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000b0d3  jz      short loc_18000B0E8
0x18000b0d5  lea     rcx, [rbp+0B20h+var_480]
0x18000b0dc  mov     [rbp+0B20h+var_480], rbx
0x18000b0e3  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000b0e8  test    r13b, r13b
0x18000b0eb  jz      loc_18000B437
0x18000b0f1  lea     rdx, [rbp+0B20h+var_350]
0x18000b0f8  lea     rcx, [rbp+0B20h+var_940]
0x18000b0ff  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000b104  mov     r8, [rbp+0B20h+lpString1]; lpString1
0x18000b10b  lea     rsi, aMycocreateinst_0; "MyCoCreateInstanceW"
0x18000b112  mov     rcx, [rbp+0B20h+lpString2]
0x18000b119  xor     r13d, r13d
0x18000b11c  test    r8, r8
0x18000b11f  jnz     short loc_18000B128
0x18000b121  test    rcx, rcx
0x18000b124  jnz     short loc_18000B163
0x18000b126  jmp     short loc_18000B184
0x18000b128  test    rcx, rcx
0x18000b12b  jnz     short loc_18000B132
0x18000b12d  mov     edi, r14d
0x18000b130  jmp     short loc_18000B163
0x18000b132  mov     dword ptr [rsp+0C20h+lpcbData], edi; cchCount2
0x18000b136  mov     r9d, edi; cchCount1
0x18000b139  mov     [rsp+0C20h+phkResult], rcx; lpString2
0x18000b13e  mov     edx, r14d; dwCmpFlags
0x18000b141  mov     ecx, 400h; Locale
0x18000b146  call    cs:__imp_CompareStringW
0x18000b14c  sub     eax, r14d
0x18000b14f  jz      short loc_18000B15C
0x18000b151  mov     edi, r13d
0x18000b154  cmp     eax, 2
0x18000b157  jnz     short loc_18000B15C
0x18000b159  mov     edi, r14d
0x18000b15c  mov     rcx, [rbp+0B20h+lpString2]; void *
0x18000b163  mov     [rbp+0B20h+var_940], rbx
0x18000b16a  test    rcx, rcx
0x18000b16d  jz      short loc_18000B180
0x18000b16f  lea     rax, [rbp+0B20h+var_938]
0x18000b176  cmp     rcx, rax
0x18000b179  jz      short loc_18000B180
0x18000b17b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b180  test    edi, edi
0x18000b182  jnz     short loc_18000B1D8
0x18000b184  lea     rdx, aTryingToLoadAD; "Trying to Load a driver which is Apartm"...
0x18000b18b  xor     ecx, ecx
0x18000b18d  call    WiaTrace_TraceLogWithSubComp
0x18000b192  mov     rdx, rax; char *
0x18000b195  mov     rcx, rsi; char *
0x18000b198  mov     rbx, rax
0x18000b19b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
  ... truncated ...
```
