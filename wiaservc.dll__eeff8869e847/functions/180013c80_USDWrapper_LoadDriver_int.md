# USDWrapper::LoadDriver(int)

- ea: `0x180013c80`
- end: `0x1800147bf`
- name: `?LoadDriver@USDWrapper@@UEAAJH@Z`
- size: `2879`
- prototype: `__int64 __fastcall(struct IUnknown *this, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180008bb4`
- `0x18000a974`
- `0x18000ac34`
- `0x18000ac58`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000f4fc`
- `0x180013944`
- `0x180013c80`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033cc0`
- `0x1800775e4`
- `0x180078010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180013e3a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180013e3a`
- `ADVAPI32!RegCloseKey` at `0x1800146cc`
- `ADVAPI32!RegCloseKey` at `0x1800146cc`
- `KERNEL32!LeaveCriticalSection` at `0x18001444d`
- `KERNEL32!LeaveCriticalSection` at `0x18001444d`

## string_xrefs

- `0x18001453c`: `ServiceComponentHolder::Get`
- `0x180014572`: `ServiceComponentHolder::Get`
- `0x180014527`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x180014558`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x1800146e4`: `We encountered an error attempting to load driver for (%ws), error (%#x)`
- `0x180014710`: `We encountered an error attempting to load driver for (%ws), error (%#x)`
- `0x1800143b1`: `Error loading driver for (%ws): CoCreateInstance on ClassID (%ws) failed with hr = 0x%08X`
- `0x1800143e4`: `Error loading driver for (%ws): CoCreateInstance on ClassID (%ws) failed with hr = 0x%08X`
- `0x18001423c`: `Error loading driver for (%ws): Returned driver version from GetCapabilities is 0x08%X, which is incompatible (too old)`
- `0x180014267`: `Error loading driver for (%ws): Returned driver version from GetCapabilities is 0x08%X, which is incompatible (too old)`
- `0x180013d51`: `Driver for (%ws) is already loaded`
- `0x180013d86`: `Driver for (%ws) is already loaded`
- `0x180013eab`: `The USDWrapper could not create the IStiDeviceControl object. Aborting driver loading for (%ws)`
- `0x180013ed4`: `The USDWrapper could not create the IStiDeviceControl object. Aborting driver loading for (%ws)`
- `0x18001466d`: `Device (%ws) does not appear to be installed yet, its driver cannot be loaded at this time`
- `0x18001469d`: `Device (%ws) does not appear to be installed yet, its driver cannot be loaded at this time`
- `0x180014155`: `Error loading driver for (%ws): Driver is Apartment Threaded and is not XP Style`
- `0x18001417e`: `Error loading driver for (%ws): Driver is Apartment Threaded and is not XP Style`

## pseudocode

```c
__int64 __fastcall USDWrapper::LoadDriver(struct IUnknown *this, int a2)
{
  struct IUnknownVtbl *lpVtbl; // r9
  char *v5; // rbx
  void *v6; // rdx
  void *v7; // rax
  int v8; // edx
  int v9; // ecx
  _DWORD *v10; // r13
  char *v11; // rbx
  void *v12; // rdx
  void *v13; // rax
  int v14; // edx
  int v15; // ecx
  int v16; // r14d
  char *v17; // rbx
  void *v18; // rdx
  void *v19; // rax
  int v20; // edx
  int v21; // ecx
  char *v22; // rbx
  void *v23; // rdx
  void *v24; // rax
  int v25; // edx
  int v26; // ecx
  char *v27; // rbx
  void *v28; // rdx
  void *v29; // rax
  int v30; // edx
  int v31; // ecx
  char *v32; // rbx
  void *v33; // rdx
  void *v34; // rax
  int v35; // edx
  int v36; // ecx
  unsigned int v37; // r8d
  char *v38; // rbx
  void *v39; // rdx
  void *v40; // rax
  int v41; // edx
  int v42; // ecx
  struct IUnknown *v43; // r13
  char *v44; // rbx
  void *v45; // rdx
  void *v46; // rax
  int v47; // edx
  int v48; // ecx
  char *v49; // rbx
  void *v50; // rdx
  void *v51; // rax
  int v52; // edx
  int v53; // ecx
  char *v54; // rbx
  void *v55; // rdx
  void *v56; // rax
  int v57; // edx
  int v58; // ecx
  char *v59; // rbx
  void *v60; // rdx
  void *v61; // rax
  int v62; // edx
  int v63; // ecx
  char *v64; // rbx
  void *v65; // rdx
  void *v66; // rax
  int v67; // edx
  int v68; // ecx
  char *v69; // rbx
  void *v70; // rdx
  __int64 v71; // r13
  unsigned __int64 v72; // rdx
  __int64 v73; // rbx
  char *v74; // rbx
  void *v75; // rdx
  void *v76; // rax
  int v77; // edx
  int v78; // ecx
  __int64 v79; // rcx
  char *v80; // rbx
  void *v81; // rdx
  void *v82; // rax
  int v83; // edx
  int v84; // ecx
  __int64 v85; // rcx
  char *v86; // rbx
  void *v87; // rdx
  char *v88; // rbx
  void *v89; // rdx
  void *v90; // rax
  int v91; // edx
  int v92; // ecx
  char *v93; // rbx
  void *v94; // rdx
  void *v95; // rax
  int v96; // edx
  int v97; // ecx
  LPVOID lpMem; // [rsp+20h] [rbp-1D8h]
  LPVOID lpMema; // [rsp+20h] [rbp-1D8h]
  int v101; // [rsp+34h] [rbp-1C4h] BYREF
  __int64 v102; // [rsp+38h] [rbp-1C0h] BYREF
  struct IUnknown *v103; // [rsp+40h] [rbp-1B8h] BYREF
  __int64 v104; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v105; // [rsp+50h] [rbp-1A8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-1A0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-198h]
  int v108; // [rsp+68h] [rbp-190h]
  struct IUnknown *v109; // [rsp+70h] [rbp-188h]
  struct _GUID v110; // [rsp+80h] [rbp-178h] BYREF
  const unsigned __int64 *v111; // [rsp+90h] [rbp-168h] BYREF
  char v112; // [rsp+98h] [rbp-160h] BYREF
  void *v113; // [rsp+198h] [rbp-60h]
  __int64 v114; // [rsp+1A0h] [rbp-58h]

  v109 = this;
  hKey = 0;
  if ( !((unsigned int (__fastcall *)(struct IUnknown *))this->lpVtbl[7].QueryInterface)(this) )
  {
    v10 = (_DWORD *)&this[3].lpVtbl + 1;
    if ( (BYTE4(this[3].lpVtbl) & 4) != 0 )
    {
      if ( wcscmp_0((const wchar_t *)this[190].lpVtbl, L"No device description provided")
        && (!wcsstr((const wchar_t *)this[449].lpVtbl, L"dafwsdprovider") || WORD1(this[8].lpVtbl) == 1) )
      {
        goto LABEL_10;
      }
      v86 = (char *)WiaTrace_TraceLog("Device (%ws) does not appear to be installed yet, its driver cannot be loaded at this time");
      WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v86);
      WiaTrcLib::Free((WiaTrcLib *)v86, v87);
      v19 = (void *)WiaTrace_Trace(
                      "Device (%ws) does not appear to be installed yet, its driver cannot be loaded at this time",
                      this[301].lpVtbl);
    }
    else
    {
      v17 = (char *)WiaTrace_TraceLog("Device (%ws) is marked inactive, its driver will not be loaded");
      WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v17);
      WiaTrcLib::Free((WiaTrcLib *)v17, v18);
      v19 = (void *)WiaTrace_Trace("Device (%ws) is marked inactive, its driver will not be loaded", this[301].lpVtbl);
    }
    WiaTrace_ProcessTrace_Ex(v21, v20, (int)"USDWrapper::LoadDriver", 1, v19);
    v16 = -2147418113;
    goto LABEL_58;
  }
  lpVtbl = this[301].lpVtbl;
  if ( !a2 )
  {
    v11 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Driver for (%ws) is already loaded", lpVtbl);
    WriteDbgTraceInfoWI("USDWrapper::LoadDriver", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void *)WiaTrace_TraceWithSubCompTraceLevel(4, 0, "Driver for (%ws) is already loaded", this[301].lpVtbl);
    WiaTrace_ProcessTrace_Ex(v15, v14, (int)"USDWrapper::LoadDriver", 4, v13);
    v16 = 0;
    goto LABEL_58;
  }
  v5 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Unloading driver for (%ws) to reload", lpVtbl);
  WriteDbgTraceInfoWI("USDWrapper::LoadDriver", v5);
  WiaTrcLib::Free((WiaTrcLib *)v5, v6);
  v7 = (void *)WiaTrace_TraceWithSubCompTraceLevel(4, 0, "Unloading driver for (%ws) to reload", this[301].lpVtbl);
  WiaTrace_ProcessTrace_Ex(v9, v8, (int)"USDWrapper::LoadDriver", 4, v7);
  ((void (__fastcall *)(struct IUnknown *))this->lpVtbl[4].QueryInterface)(this);
  v10 = (_DWORD *)&this[3].lpVtbl + 1;
LABEL_10:
  hKey = (HKEY)((__int64 (__fastcall *)(struct IUnknown *))this->lpVtbl[20].QueryInterface)(this);
  v16 = ((__int64 (__fastcall *)(struct IUnknown *))this->lpVtbl[21].AddRef)(this);
  if ( v16 < 0 )
  {
    v22 = (char *)WiaTrace_TraceLog("The USDWrapper could not create the IStiDeviceControl object. Aborting driver loading for (%ws)");
    WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v22);
    WiaTrcLib::Free((WiaTrcLib *)v22, v23);
    v24 = (void *)WiaTrace_Trace(
                    "The USDWrapper could not create the IStiDeviceControl object. Aborting driver loading for (%ws)",
                    this[301].lpVtbl);
    WiaTrace_ProcessTrace_Ex(v26, v25, (int)"USDWrapper::LoadDriver", 1, v24);
    if ( (*v10 & 4) != 0 )
    {
      *v10 &= ~4u;
      v27 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(8, 0, "Device (%ws) is marked inactive", this[301].lpVtbl);
      WriteDbgTraceInfoWI("USDWrapper::LoadDriver", v27);
      WiaTrcLib::Free((WiaTrcLib *)v27, v28);
      v29 = (void *)WiaTrace_TraceWithSubCompTraceLevel(8, 0, "Device (%ws) is marked inactive", this[301].lpVtbl);
      WiaTrace_ProcessTrace_Ex(v31, v30, (int)"USDWrapper::LoadDriver", 4, v29);
    }
    goto LABEL_58;
  }
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v101 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)&this[517];
  v108 = CRIT_SECT::Lock((CRIT_SECT *)&this[517]);
  v110 = IID_IUnknown;
  v16 = MyCoCreateInstanceW((LPCOLESTR)this[116].lpVtbl, this, &v110, &v103, (HINSTANCE *)&this[497], &v101);
  if ( v16 < 0 )
  {
    v69 = (char *)WiaTrace_TraceLog("Error loading driver for (%ws): CoCreateInstance on ClassID (%ws) failed with hr = 0x%08X");
    WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v69);
    WiaTrcLib::Free((WiaTrcLib *)v69, v70);
    v66 = (void *)WiaTrace_Trace(
                    "Error loading driver for (%ws): CoCreateInstance on ClassID (%ws) failed with hr = 0x%08X",
                    this[301].lpVtbl,
                    this[116].lpVtbl,
                    (unsigned int)v16);
  }
  else
  {
    v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v103->lpVtbl->QueryInterface)(
            v103,
            &IID_IStiUSD,
            &v104);
    if ( v16 >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown *, __int64))this->lpVtbl[1].Release)(this, v104);
      if ( ((unsigned int (__fastcall *)(struct IUnknown *))this->lpVtbl[6].Release)(this) )
      {
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v103->lpVtbl->QueryInterface)(
               v103,
               &IID_IWiaMiniDrv,
               &v105) < 0 )
        {
          v32 = (char *)WiaTrace_TraceLogWithSubComp(
                          0,
                          "Non-fatal error loading driver: WIA driver for device (%ws) did not return IWiaMiniDrv interface",
                          this[42].lpVtbl);
          WriteDbgTraceWarningWI("USDWrapper::LoadDriver", v32);
          WiaTrcLib::Free((WiaTrcLib *)v32, v33);
          v34 = (void *)WiaTrace_TraceWithSubComp(
                          0,
                          "Non-fatal error loading driver: WIA driver for device (%ws) did not return IWiaMiniDrv interface",
                          this[42].lpVtbl);
          WiaTrace_ProcessTrace_Ex(v36, v35, (int)"USDWrapper::LoadDriver", 2, v34);
        }
        else
        {
          ((void (__fastcall *)(struct IUnknown *, __int64))this->lpVtbl[2].QueryInterface)(this, v105);
        }
      }
      ((void (__fastcall *)(struct IUnknown *, struct IUnknown *))this->lpVtbl[1].AddRef)(this, v103);
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknownVtbl *, __int64, HKEY))this->lpVtbl[11].QueryInterface)(
              this,
              this[496].lpVtbl,
              2,
              hKey);
      if ( v16 < 0 )
      {
        v54 = (char *)WiaTrace_TraceLog("Error loading driver for (%ws): IStiUSD::Initialize failed with hr = 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v54);
        WiaTrcLib::Free((WiaTrcLib *)v54, v55);
        v56 = (void *)WiaTrace_Trace(
                        "Error loading driver for (%ws): IStiUSD::Initialize failed with hr = 0x%08X",
                        this[301].lpVtbl,
                        (unsigned int)v16);
        WiaTrace_ProcessTrace_Ex(v58, v57, (int)"USDWrapper::LoadDriver", 1, v56);
        if ( v16 == -2145320939 )
        {
          LODWORD(lpMem) = -2145320939;
          v59 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          8,
                          0,
                          "Device (%ws) cannot be used (WIA_S_NO_DEVICE_AVAILABLE: 0x%08X), marking it inactive",
                          this[301].lpVtbl,
                          lpMem);
          WriteDbgTraceInfoWI("USDWrapper::LoadDriver", v59);
          WiaTrcLib::Free((WiaTrcLib *)v59, v60);
          LODWORD(lpMema) = -2145320939;
          v61 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                          8,
                          0,
                          "Device (%ws) cannot be used (WIA_S_NO_DEVICE_AVAILABLE: 0x%08X), marking it inactive",
                          this[301].lpVtbl,
                          lpMema);
          WiaTrace_ProcessTrace_Ex(v63, v62, (int)"USDWrapper::LoadDriver", 4, v61);
          *v10 &= ~4u;
        }
      }
      else
      {
        v102 = 0;
        v16 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))this->lpVtbl[11].AddRef)(this, &v102);
        if ( v16 < 0 )
        {
          v43 = this + 301;
          v44 = (char *)WiaTrace_TraceLog("Error loading driver for (%ws): IStiUSD::GetCapabilities failed with hr = 0x%08X");
          WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v44);
          WiaTrcLib::Free((WiaTrcLib *)v44, v45);
          v46 = (void *)WiaTrace_Trace(
                          "Error loading driver for (%ws): IStiUSD::GetCapabilities failed with hr = 0x%08X",
                          this[301].lpVtbl,
                          (unsigned int)v16);
          WiaTrace_ProcessTrace_Ex(v48, v47, (int)"USDWrapper::LoadDriver", 1, v46);
          v37 = v102;
        }
        else
        {
          v37 = v102;
          if ( (v102 & 0xFEFFFFFF) != 2 && v101 )
          {
            v38 = (char *)WiaTrace_TraceLog("Error loading driver for (%ws): Driver is Apartment Threaded and is not XP Style");
            WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v38);
            WiaTrcLib::Free((WiaTrcLib *)v38, v39);
            v40 = (void *)WiaTrace_Trace(
                            "Error loading driver for (%ws): Driver is Apartment Threaded and is not XP Style",
                            this[301].lpVtbl);
            WiaTrace_ProcessTrace_Ex(v42, v41, (int)"USDWrapper::LoadDriver", 1, v40);
            v16 = -2147467259;
            v37 = v102;
          }
          v43 = this + 301;
        }
        if ( v16 >= 0 )
        {
          if ( v37 < 2 )
          {
            v49 = (char *)WiaTrace_TraceLog("Error loading driver for (%ws): Returned driver version from GetCapabilities"
                                            " is 0x08%X, which is incompatible (too old)");
            WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v49);
            WiaTrcLib::Free((WiaTrcLib *)v49, v50);
            v51 = (void *)WiaTrace_Trace(
                            "Error loading driver for (%ws): Returned driver version from GetCapabilities is 0x08%X, whic"
                            "h is incompatible (too old)",
                            v43->lpVtbl,
                            (unsigned int)v102);
            WiaTrace_ProcessTrace_Ex(v53, v52, (int)"USDWrapper::LoadDriver", 1, v51);
            v16 = -2147023746;
          }
          else
          {
            LODWORD(this[7].lpVtbl) = (unsigned __int16)v37;
            ((void (__fastcall *)(struct IUnknown *))this->lpVtbl[21].Release)(this);
          }
        }
      }
      goto LABEL_36;
    }
    v64 = (char *)WiaTrace_TraceLog("Error loading driver for (%ws): QI for driver's IStiUSD interface failed!  Driver mu"
                                    "st support IStiUSD");
    WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v64);
    WiaTrcLib::Free((WiaTrcLib *)v64, v65);
    v66 = (void *)WiaTrace_Trace(
                    "Error loading driver for (%ws): QI for driver's IStiUSD interface failed!  Driver must support IStiUSD",
                    this[301].lpVtbl);
  }
  WiaTrace_ProcessTrace_Ex(v68, v67, (int)"USDWrapper::LoadDriver", 1, v66);
LABEL_36:
  if ( v104 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  if ( v105 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
  if ( v103 )
    ((void (__fastcall *)(struct IUnknown *))v103->lpVtbl->Release)(v103);
  if ( v108 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v108 = 0;
  }
  if ( v16 >= 0 )
  {
    ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)&v110);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v111, L"DeviceInfoSet");
    v71 = *(_QWORD *)v110.Data4;
    if ( *(_QWORD *)v110.Data4 )
    {
      v73 = CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<DeviceInfoSet>(*(_QWORD *)v110.Data4, &v111);
    }
    else
    {
      v74 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                      v113);
      WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v74);
      WiaTrcLib::Free((WiaTrcLib *)v74, v75);
      v76 = (void *)WiaTrace_TraceWithSubComp(
                      1,
                      "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                      v113);
      WiaTrace_ProcessTrace_Ex(v78, v77, (int)"ServiceComponentHolder::Get", 2, v76);
      v73 = 0;
    }
    v111 = &CSimpleStringBase<unsigned short>::`vftable';
    if ( v113 && v113 != &v112 )
      operator delete(v113, v72);
    v113 = 0;
    v114 = 0;
    if ( v73 )
    {
      DeviceInfoSet::SetWiaDeviceTypeProperty(v73, &this[9], WORD1(this[8].lpVtbl));
      v79 = v73 + *(int *)(*(_QWORD *)v73 + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
    }
    else
    {
      v80 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "The Device Class wrapper for (%ws) could not set the DEVPKEY_WIA_DeviceType device property becaus"
                      "e the DeviceInfoSet could not be found",
                      this[301].lpVtbl);
      WriteDbgTraceWarningWI("USDWrapper::LoadDriver", v80);
      WiaTrcLib::Free((WiaTrcLib *)v80, v81);
      v82 = (void *)WiaTrace_TraceWithSubComp(
                      1,
                      "The Device Class wrapper for (%ws) could not set the DEVPKEY_WIA_DeviceType device property becaus"
                      "e the DeviceInfoSet could not be found",
                      this[301].lpVtbl);
      WiaTrace_ProcessTrace_Ex(v84, v83, (int)"USDWrapper::LoadDriver", 2, v82);
    }
    if ( v71 )
    {
      v85 = v71 + *(int *)(*(_QWORD *)v71 + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    }
  }
LABEL_58:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v16 >= 0 )
  {
    v93 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Driver for (%ws) is currently loaded", this[301].lpVtbl);
    WriteDbgTraceInfoWI("USDWrapper::LoadDriver", v93);
    WiaTrcLib::Free((WiaTrcLib *)v93, v94);
    v95 = (void *)WiaTrace_TraceWithSubCompTraceLevel(4, 0, "Driver for (%ws) is currently loaded", this[301].lpVtbl);
    WiaTrace_ProcessTrace_Ex(v97, v96, (int)"USDWrapper::LoadDriver", 4, v95);
  }
  else
  {
    v88 = (char *)WiaTrace_TraceLog("We encountered an error attempting to load driver for (%ws), error (%#x)");
    WriteDbgTraceErrorWI("USDWrapper::LoadDriver", v88);
    WiaTrcLib::Free((WiaTrcLib *)v88, v89);
    v90 = (void *)WiaTrace_Trace(
                    "We encountered an error attempting to load driver for (%ws), error (%#x)",
                    this[301].lpVtbl,
                    (unsigned int)v16);
    WiaTrace_ProcessTrace_Ex(v92, v91, (int)"USDWrapper::LoadDriver", 1, v90);
    ((void (__fastcall *)(struct IUnknown *))this->lpVtbl[4].QueryInterface)(this);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180013c80  mov     [rsp+arg_8], rbx
0x180013c85  mov     [rsp+arg_10], rsi
0x180013c8a  push    rdi
0x180013c8b  push    r12
0x180013c8d  push    r13
0x180013c8f  push    r14
0x180013c91  push    r15
0x180013c93  sub     rsp, 1D0h
0x180013c9a  mov     rax, cs:__security_cookie
0x180013ca1  xor     rax, rsp
0x180013ca4  mov     [rsp+1F8h+var_38], rax
0x180013cac  mov     ebx, edx
0x180013cae  mov     rsi, rcx
0x180013cb1  mov     [rsp+1F8h+var_188], rcx
0x180013cb6  xor     edi, edi
0x180013cb8  mov     [rsp+1F8h+hKey], rdi
0x180013cbd  mov     rax, [rcx]
0x180013cc0  mov     rax, [rax+0A8h]
0x180013cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ccc  test    eax, eax
0x180013cce  jz      loc_180013DB8
0x180013cd4  mov     r9, [rsi+968h]
0x180013cdb  xor     edx, edx
0x180013cdd  test    ebx, ebx
0x180013cdf  jz      short loc_180013D51
0x180013ce1  lea     r8, aUnloadingDrive; "Unloading driver for (%ws) to reload"
0x180013ce8  lea     r14d, [rdi+4]
0x180013cec  mov     ecx, r14d
0x180013cef  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180013cf4  mov     rbx, rax
0x180013cf7  mov     rdx, rax; char *
0x180013cfa  lea     r15, aUsdwrapperLoad; "USDWrapper::LoadDriver"
0x180013d01  mov     rcx, r15; char *
0x180013d04  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180013d09  mov     rcx, rbx; this
0x180013d0c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013d11  mov     r9, [rsi+968h]
0x180013d18  lea     r8, aUnloadingDrive; "Unloading driver for (%ws) to reload"
0x180013d1f  xor     edx, edx
0x180013d21  mov     ecx, r14d
0x180013d24  call    WiaTrace_TraceWithSubCompTraceLevel
0x180013d29  mov     [rsp+1F8h+lpMem], rax; lpMem
0x180013d2e  mov     r9d, r14d; int
0x180013d31  mov     r8, r15; int
0x180013d34  call    WiaTrace_ProcessTrace_Ex
0x180013d39  mov     rax, [rsi]
0x180013d3c  mov     rcx, rsi
0x180013d3f  mov     rax, [rax+60h]
0x180013d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d48  lea     r13, [rsi+1Ch]
0x180013d4c  jmp     loc_180013E66
0x180013d51  lea     r8, aDriverForWsIsA; "Driver for (%ws) is already loaded"
0x180013d58  mov     ecx, 4
0x180013d5d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180013d62  mov     rbx, rax
0x180013d65  mov     rdx, rax; char *
0x180013d68  lea     r15, aUsdwrapperLoad; "USDWrapper::LoadDriver"
0x180013d6f  mov     rcx, r15; char *
0x180013d72  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180013d77  mov     rcx, rbx; this
0x180013d7a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013d7f  mov     r9, [rsi+968h]
0x180013d86  lea     r8, aDriverForWsIsA; "Driver for (%ws) is already loaded"
0x180013d8d  xor     edx, edx
0x180013d8f  lea     ecx, [rdx+4]
0x180013d92  call    WiaTrace_TraceWithSubCompTraceLevel
0x180013d97  mov     [rsp+1F8h+lpMem], rax; lpMem
0x180013d9c  mov     r9d, 4; int
0x180013da2  mov     r8, r15; int
0x180013da5  call    WiaTrace_ProcessTrace_Ex
0x180013daa  mov     r14d, edi
0x180013dad  mov     r12d, 1
0x180013db3  jmp     loc_1800146BF
0x180013db8  lea     r13, [rsi+1Ch]
0x180013dbc  test    byte ptr [r13+0], 4
0x180013dc1  jnz     short loc_180013E11
0x180013dc3  mov     rdx, [rsi+968h]
0x180013dca  lea     rcx, aDeviceWsIsMark; "Device (%ws) is marked inactive, its dr"...
0x180013dd1  call    WiaTrace_TraceLog
0x180013dd6  mov     rbx, rax
0x180013dd9  mov     rdx, rax; char *
0x180013ddc  lea     r15, aUsdwrapperLoad; "USDWrapper::LoadDriver"
0x180013de3  mov     rcx, r15; char *
0x180013de6  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180013deb  mov     rcx, rbx; this
0x180013dee  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013df3  mov     rdx, [rsi+968h]
0x180013dfa  lea     rcx, aDeviceWsIsMark; "Device (%ws) is marked inactive, its dr"...
0x180013e01  call    WiaTrace_Trace
0x180013e06  mov     r12d, 1
0x180013e0c  jmp     loc_1800146A9
0x180013e11  lea     rdx, aNoDeviceDescri; "No device description provided"
0x180013e18  mov     rcx, [rsi+5F0h]; String1
0x180013e1f  call    wcscmp_0
0x180013e24  test    eax, eax
0x180013e26  jz      loc_180014660
0x180013e2c  lea     rdx, aDafwsdprovider; "dafwsdprovider"
0x180013e33  mov     rcx, [rsi+0E08h]; Str
0x180013e3a  call    cs:__imp_wcsstr
0x180013e40  test    rax, rax
0x180013e43  jz      short loc_180013E5F
0x180013e45  mov     r12d, 1
0x180013e4b  cmp     r12w, [rsi+42h]
0x180013e50  jnz     loc_180014666
0x180013e56  lea     r15, aUsdwrapperLoad; "USDWrapper::LoadDriver"
0x180013e5d  jmp     short loc_180013E6C
0x180013e5f  lea     r15, aUsdwrapperLoad; "USDWrapper::LoadDriver"
0x180013e66  mov     r12d, 1
0x180013e6c  mov     rax, [rsi]
0x180013e6f  mov     rcx, rsi
0x180013e72  mov     rax, [rax+1E0h]
0x180013e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e7e  mov     [rsp+1F8h+hKey], rax
0x180013e83  mov     rcx, [rsi]
0x180013e86  mov     rax, [rcx+200h]
0x180013e8d  mov     rcx, rsi
0x180013e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e95  mov     r14d, eax
0x180013e98  mov     [rsp+1F8h+var_1C8], eax
0x180013e9c  test    eax, eax
0x180013e9e  jns     loc_180013F5F
0x180013ea4  mov     rdx, [rsi+968h]
0x180013eab  lea     rcx, aTheUsdwrapperC; "The USDWrapper could not create the ISt"...
0x180013eb2  call    WiaTrace_TraceLog
0x180013eb7  mov     rbx, rax
0x180013eba  mov     rdx, rax; char *
0x180013ebd  mov     rcx, r15; char *
0x180013ec0  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180013ec5  mov     rcx, rbx; this
0x180013ec8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013ecd  mov     rdx, [rsi+968h]
0x180013ed4  lea     rcx, aTheUsdwrapperC; "The USDWrapper could not create the ISt"...
0x180013edb  call    WiaTrace_Trace
0x180013ee0  mov     [rsp+1F8h+lpMem], rax; lpMem
0x180013ee5  mov     r9d, r12d; int
0x180013ee8  mov     r8, r15; int
0x180013eeb  call    WiaTrace_ProcessTrace_Ex
0x180013ef0  mov     eax, [r13+0]
0x180013ef4  test    al, 4
0x180013ef6  jz      short loc_180013F5A
0x180013ef8  and     eax, 0FFFFFFFBh
0x180013efb  mov     [r13+0], eax
0x180013eff  mov     r9, [rsi+968h]
0x180013f06  lea     r8, aDeviceWsIsMark_0; "Device (%ws) is marked inactive"
0x180013f0d  xor     edx, edx
0x180013f0f  lea     r13d, [rdx+8]
0x180013f13  mov     ecx, r13d
0x180013f16  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180013f1b  mov     rbx, rax
0x180013f1e  mov     rdx, rax; char *
0x180013f21  mov     rcx, r15; char *
0x180013f24  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180013f29  mov     rcx, rbx; this
0x180013f2c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013f31  mov     r9, [rsi+968h]
0x180013f38  lea     r8, aDeviceWsIsMark_0; "Device (%ws) is marked inactive"
0x180013f3f  xor     edx, edx
0x180013f41  mov     ecx, r13d
0x180013f44  call    WiaTrace_TraceWithSubCompTraceLevel
0x180013f49  mov     [rsp+1F8h+lpMem], rax; lpMem
0x180013f4e  lea     r9d, [r13-4]; int
0x180013f52  mov     r8, r15; int
0x180013f55  call    WiaTrace_ProcessTrace_Ex
0x180013f5a  jmp     loc_1800146BF
0x180013f5f  mov     [rsp+1F8h+var_1B8], rdi
0x180013f64  mov     [rsp+1F8h+var_1B0], rdi
0x180013f69  mov     [rsp+1F8h+var_1A8], rdi
0x180013f6e  mov     [rsp+1F8h+var_1C4], edi
0x180013f72  lea     rax, [rsi+1028h]
0x180013f79  mov     [rsp+1F8h+lpCriticalSection], rax
0x180013f7e  mov     [rsp+1F8h+var_190], edi
0x180013f82  mov     rcx, rax; this
0x180013f85  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x180013f8a  mov     [rsp+1F8h+var_190], eax
0x180013f8e  movups  xmm0, xmmword ptr cs:IID_IUnknown.Data1
0x180013f95  movdqu  xmmword ptr [rsp+1F8h+var_178.Data1], xmm0
0x180013f9e  lea     rcx, [rsi+0F88h]
0x180013fa5  lea     rax, [rsp+1F8h+var_1C4]
0x180013faa  mov     [rsp+1F8h+var_1D0], rax; int *
0x180013faf  mov     [rsp+1F8h+lpMem], rcx; HINSTANCE *
0x180013fb4  lea     r9, [rsp+1F8h+var_1B8]; struct IUnknown **
0x180013fb9  lea     r8, [rsp+1F8h+var_178]; struct _GUID
0x180013fc1  mov     rdx, rsi; struct IUnknown *
0x180013fc4  mov     rcx, [rsi+3A0h]; lpsz
0x180013fcb  call    ?MyCoCreateInstanceW@@YAJPEBGPEAUIUnknown@@U_GUID@@PEAPEAU1@PEAPEAUHINSTANCE__@@PEAH@Z; MyCoCreateInstanceW(ushort const *,IUnknown *,_GUID,IUnknown * *,HINSTANCE__ * *,int *)
0x180013fd0  mov     r14d, eax
0x180013fd3  mov     [rsp+1F8h+var_1C8], eax
0x180013fd7  test    eax, eax
0x180013fd9  js      loc_1800143A0
0x180013fdf  mov     rcx, [rsp+1F8h+var_1B8]
0x180013fe4  mov     rax, [rcx]
0x180013fe7  lea     r8, [rsp+1F8h+var_1B0]
0x180013fec  lea     rdx, IID_IStiUSD
0x180013ff3  mov     rax, [rax]
0x180013ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ffb  mov     r14d, eax
0x180013ffe  mov     [rsp+1F8h+var_1C8], eax
0x180014002  test    eax, eax
0x180014004  js      loc_180014362
0x18001400a  mov     rax, [rsi]
0x18001400d  mov     rdx, [rsp+1F8h+var_1B0]
0x180014012  mov     rcx, rsi
0x180014015  mov     rax, [rax+28h]
0x180014019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001401e  mov     rax, [rsi]
0x180014021  mov     rcx, rsi
0x180014024  mov     rax, [rax+0A0h]
0x18001402b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014030  test    eax, eax
0x180014032  jz      loc_1800140C9
0x180014038  mov     rcx, [rsp+1F8h+var_1B8]
0x18001403d  mov     rax, [rcx]
0x180014040  lea     r8, [rsp+1F8h+var_1A8]
0x180014045  lea     rdx, IID_IWiaMiniDrv
0x18001404c  mov     rax, [rax]
0x18001404f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014054  mov     [rsp+1F8h+var_1C8], eax
0x180014058  test    eax, eax
0x18001405a  js      short loc_180014072
0x18001405c  mov     rax, [rsi]
0x18001405f  mov     rdx, [rsp+1F8h+var_1A8]
0x180014064  mov     rcx, rsi
0x180014067  mov     rax, [rax+30h]
0x18001406b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014070  jmp     short loc_1800140C9
0x180014072  mov     r8, [rsi+150h]
0x180014079  lea     rdx, aNonFatalErrorL; "Non-fatal error loading driver: WIA dri"...
0x180014080  xor     ecx, ecx
0x180014082  call    WiaTrace_TraceLogWithSubComp
0x180014087  mov     rbx, rax
0x18001408a  mov     rdx, rax; char *
0x18001408d  mov     rcx, r15; char *
0x180014090  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180014095  mov     rcx, rbx; this
0x180014098  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001409d  mov     r8, [rsi+150h]
0x1800140a4  lea     rdx, aNonFatalErrorL; "Non-fatal error loading driver: WIA dri"...
0x1800140ab  xor     ecx, ecx
0x1800140ad  call    WiaTrace_TraceWithSubComp
0x1800140b2  mov     [rsp+1F8h+lpMem], rax; lpMem
0x1800140b7  mov     r9d, 2; int
0x1800140bd  mov     r8, r15; int
0x1800140c0  call    WiaTrace_ProcessTrace_Ex
0x1800140c5  mov     [rsp+1F8h+var_1C8], edi
0x1800140c9  mov     rax, [rsi]
0x1800140cc  mov     rdx, [rsp+1F8h+var_1B8]
0x1800140d1  mov     rcx, rsi
0x1800140d4  mov     rax, [rax+20h]
0x1800140d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140dd  mov     rax, [rsi]
0x1800140e0  mov     r9, [rsp+1F8h+hKey]
0x1800140e5  mov     r8d, 2
0x1800140eb  mov     rdx, [rsi+0F80h]
0x1800140f2  mov     rcx, rsi
0x1800140f5  mov     rax, [rax+108h]
0x1800140fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014101  mov     r14d, eax
0x180014104  mov     [rsp+1F8h+var_1C8], eax
0x180014108  test    eax, eax
0x18001410a  js      loc_180014293
0x180014110  mov     [rsp+1F8h+var_1C0], rdi
0x180014115  mov     rax, [rsi]
0x180014118  lea     rdx, [rsp+1F8h+var_1C0]
0x18001411d  mov     rcx, rsi
0x180014120  mov     rax, [rax+110h]
0x180014127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001412c  mov     r14d, eax
0x18001412f  mov     [rsp+1F8h+var_1C8], eax
0x180014133  test    eax, eax
0x180014135  js      short loc_1800141B3
0x180014137  mov     r8, [rsp+1F8h+var_1C0]
0x18001413c  mov     eax, r8d
0x18001413f  btr     eax, 18h
0x180014143  cmp     eax, 2
0x180014146  jz      short loc_1800141AA
0x180014148  cmp     [rsp+1F8h+var_1C4], edi
0x18001414c  jz      short loc_1800141AA
0x18001414e  mov     rdx, [rsi+968h]
0x180014155  lea     rcx, aErrorLoadingDr_2; "Error loading driver for (%ws): Driver "...
0x18001415c  call    WiaTrace_TraceLog
0x180014161  mov     rbx, rax
0x180014164  mov     rdx, rax; char *
0x180014167  mov     rcx, r15; char *
0x18001416a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001416f  mov     rcx, rbx; this
0x180014172  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180014177  mov     rdx, [rsi+968h]
0x18001417e  lea     rcx, aErrorLoadingDr_2; "Error loading driver for (%ws): Driver "...
0x180014185  call    WiaTrace_Trace
0x18001418a  mov     [rsp+1F8h+lpMem], rax; lpMem
0x18001418f  mov     r9d, r12d; int
0x180014192  mov     r8, r15; int
0x180014195  call    WiaTrace_ProcessTrace_Ex
0x18001419a  mov     r14d, 80004005h
0x1800141a0  mov     [rsp+1F8h+var_1C8], r14d
0x1800141a5  mov     r8, [rsp+1F8h+var_1C0]
0x1800141aa  lea     r13, [rsi+968h]
0x1800141b1  jmp     short loc_18001420B
0x1800141b3  lea     r13, [rsi+968h]
0x1800141ba  mov     r8d, r14d
  ... truncated ...
```
