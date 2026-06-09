# UnBCL::Environment::GetSystemInfo(int)

- ea: `0x180036fd0`
- end: `0x180037af9`
- name: `?GetSystemInfo@Environment@UnBCL@@SAPEBVSystemInfo@2@H@Z`
- size: `2857`
- prototype: `const struct UnBCL::SystemInfo *__fastcall(int)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002f50`
- `0x180002f90`
- `0x180011570`
- `0x180034440`
- `0x180036fd0`
- `0x180039f70`
- `0x1800477d0`
- `0x180047800`
- `0x18005b790`
- `0x180068fe6`
- `0x180069020`
- `0x18006f010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18003708c`
- `ntdll!NtQuerySystemInformation` at `0x18003708c`
- `OLEAUT32!__imp_VariantInit` at `0x180037229`
- `OLEAUT32!__imp_VariantInit` at `0x1800372c5`
- `OLEAUT32!__imp_VariantInit` at `0x180037362`
- `OLEAUT32!__imp_VariantInit` at `0x1800373b5`
- `OLEAUT32!__imp_VariantInit` at `0x180037495`
- `OLEAUT32!__imp_VariantInit` at `0x180037531`
- `OLEAUT32!__imp_VariantInit` at `0x1800375ce`
- `OLEAUT32!__imp_VariantInit` at `0x18003778d`
- `OLEAUT32!__imp_VariantInit` at `0x18003782d`
- `OLEAUT32!__imp_VariantInit` at `0x1800378cb`
- `OLEAUT32!__imp_VariantInit` at `0x180037969`
- `OLEAUT32!__imp_VariantInit` at `0x1800379bc`
- `OLEAUT32!__imp_VariantInit` at `0x180037229`
- `OLEAUT32!__imp_VariantInit` at `0x1800372c5`
- `OLEAUT32!__imp_VariantInit` at `0x180037362`
- `OLEAUT32!__imp_VariantInit` at `0x1800373b5`
- `OLEAUT32!__imp_VariantInit` at `0x180037495`
- `OLEAUT32!__imp_VariantInit` at `0x180037531`
- `OLEAUT32!__imp_VariantInit` at `0x1800375ce`
- `OLEAUT32!__imp_VariantInit` at `0x18003778d`
- `OLEAUT32!__imp_VariantInit` at `0x18003782d`
- `OLEAUT32!__imp_VariantInit` at `0x1800378cb`
- `OLEAUT32!__imp_VariantInit` at `0x180037969`
- `OLEAUT32!__imp_VariantInit` at `0x1800379bc`
- `OLEAUT32!__imp_VariantClear` at `0x180037403`
- `OLEAUT32!__imp_VariantClear` at `0x18003740e`
- `OLEAUT32!__imp_VariantClear` at `0x18003741a`
- `OLEAUT32!__imp_VariantClear` at `0x180037425`
- `OLEAUT32!__imp_VariantClear` at `0x18003766a`
- `OLEAUT32!__imp_VariantClear` at `0x180037676`
- `OLEAUT32!__imp_VariantClear` at `0x180037681`
- `OLEAUT32!__imp_VariantClear` at `0x180037a0a`
- `OLEAUT32!__imp_VariantClear` at `0x180037a15`
- `OLEAUT32!__imp_VariantClear` at `0x180037a20`
- `OLEAUT32!__imp_VariantClear` at `0x180037a2b`
- `OLEAUT32!__imp_VariantClear` at `0x180037a37`
- `OLEAUT32!__imp_VariantClear` at `0x180037403`
- `OLEAUT32!__imp_VariantClear` at `0x18003740e`
- `OLEAUT32!__imp_VariantClear` at `0x18003741a`
- `OLEAUT32!__imp_VariantClear` at `0x180037425`
- `OLEAUT32!__imp_VariantClear` at `0x18003766a`
- `OLEAUT32!__imp_VariantClear` at `0x180037676`
- `OLEAUT32!__imp_VariantClear` at `0x180037681`
- `OLEAUT32!__imp_VariantClear` at `0x180037a0a`
- `OLEAUT32!__imp_VariantClear` at `0x180037a15`
- `OLEAUT32!__imp_VariantClear` at `0x180037a20`
- `OLEAUT32!__imp_VariantClear` at `0x180037a2b`
- `OLEAUT32!__imp_VariantClear` at `0x180037a37`
- `KERNEL32!LoadLibraryExW` at `0x180037698`
- `KERNEL32!LoadLibraryExW` at `0x180037698`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1800376fa`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1800376fa`
- `KERNEL32!GetComputerNameW` at `0x1800370dc`
- `KERNEL32!GetComputerNameW` at `0x1800370dc`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800370a8`
- `KERNEL32!GetSystemDefaultLangID` at `0x1800370a8`
- `KERNEL32!FreeLibrary` at `0x1800376d2`
- `KERNEL32!FreeLibrary` at `0x1800376d2`
- `KERNEL32!GetProcAddress` at `0x1800376b0`
- `KERNEL32!GetProcAddress` at `0x1800376b0`
- `ole32!CoInitializeEx` at `0x18003719c`
- `ole32!CoInitializeEx` at `0x18003719c`
- `ole32!CoUninitialize` at `0x180037ac8`
- `ole32!CoUninitialize` at `0x180037ac8`

## string_xrefs

- `0x1800371c8`: `SELECT * FROM Win32_ComputerSystem`
- `0x180037691`: `kernel32.dll`
- `0x1800376a6`: `GetPhysicallyInstalledSystemMemory`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
const struct UnBCL::SystemInfo *__fastcall UnBCL::Environment::GetSystemInfo(int a1)
{
  struct UnBCL::SystemInfo *v2; // rcx
  UnBCL::SystemInfo *v3; // rax
  UnBCL::SystemInfo *v4; // rbx
  struct UnBCL::SystemInfo *v5; // rax
  struct IEnumWbemClassObject *v6; // rax
  __int64 v7; // rax
  BOOL v13; // r8d
  int v19; // ecx
  int v20; // edi
  HRESULT v21; // eax
  UnBCL::String *v22; // rax
  __int64 v23; // rax
  UnBCL::String *v24; // rax
  __int64 v25; // rax
  UnBCL::String *v26; // rax
  __int64 v27; // rax
  UnBCL::String *v28; // rax
  __int64 v29; // rax
  UnBCL::String *v30; // rax
  __int64 v31; // rax
  HMODULE Library; // rax
  HMODULE v33; // rbx
  FARPROC ProcAddress; // rax
  DWORDLONG ullTotalPhys; // rcx
  UnBCL::String *v36; // rax
  __int64 v37; // rax
  UnBCL::String *v38; // rax
  __int64 v39; // rax
  UnBCL::String *v40; // rax
  __int64 v41; // rax
  void **v43; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v44; // [rsp+48h] [rbp-B8h]
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  DWORDLONG v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v50; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v52; // [rsp+A8h] [rbp-58h] BYREF
  struct IEnumWbemClassObject *v53; // [rsp+C0h] [rbp-40h] BYREF
  DWORD nSize; // [rsp+C8h] [rbp-38h] BYREF
  struct IEnumWbemClassObject *v55; // [rsp+D0h] [rbp-30h] BYREF
  struct IEnumWbemClassObject *v56; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG v57; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v58; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v59; // [rsp+110h] [rbp+10h]
  __int128 SystemInformation; // [rsp+118h] [rbp+18h] BYREF
  __int128 v61; // [rsp+128h] [rbp+28h]
  _MEMORYSTATUSEX v62; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Buffer[8]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v64; // [rsp+190h] [rbp+90h]

  v59 = -2;
  v2 = UnBCL::Environment::m_SystemInfo;
  if ( !UnBCL::Environment::m_SystemInfo )
    goto LABEL_5;
  if ( a1 )
  {
    if ( UnBCL::Environment::m_SystemInfo )
      (**(void (__fastcall ***)(struct UnBCL::SystemInfo *, __int64))UnBCL::Environment::m_SystemInfo)(
        UnBCL::Environment::m_SystemInfo,
        1);
LABEL_5:
    v3 = (UnBCL::SystemInfo *)UnBCL::Object::operator new(0xC8u, 2u);
    v4 = v3;
    if ( v3 )
    {
      memset_0(v3, 0, 0xC8u);
      v5 = (struct UnBCL::SystemInfo *)UnBCL::SystemInfo::SystemInfo(v4);
    }
    else
    {
      v5 = 0;
    }
    UnBCL::Environment::m_SystemInfo = v5;
    *((_DWORD *)v5 + 4) = 1;
    SystemInformation = 0;
    v61 = 0;
    if ( NtQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0) >= 0 && (int)v61 < 3 )
      *((_DWORD *)UnBCL::Environment::m_SystemInfo + 4) = v61;
    *((_WORD *)UnBCL::Environment::m_SystemInfo + 10) = GetSystemDefaultLangID();
    *(_OWORD *)Buffer = 0;
    v64 = 0;
    nSize = 16;
    if ( GetComputerNameW(Buffer, &nSize) )
    {
      v6 = (struct IEnumWbemClassObject *)UnBCL::Object::operator new(0x18u);
      v53 = v6;
      if ( v6 )
        v7 = UnBCL::String::String((UnBCL::String *)v6, Buffer);
      else
        v7 = 0;
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v7);
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 32, v44);
      v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
      UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
    }
    _RAX = 1;
    __asm { cpuid }
    v13 = (int)_RCX < 0;
    _RAX = 1073741827;
    __asm { cpuid }
    v43 = (void **)(unsigned int)_RAX;
    v44 = __PAIR64__(_RDX, _RCX);
    if ( !v13 || (v19 = 1, (_RBX & 0x1000) != 0) )
      v19 = 0;
    *((_DWORD *)UnBCL::Environment::m_SystemInfo + 6) = v19;
    v45 = 0;
    v20 = 0;
    v21 = CoInitializeEx(0, 0);
    if ( v21 != -2147417850 )
    {
      if ( (unsigned int)v21 < 2 )
      {
        v20 = 1;
      }
      else if ( v21 < 0 )
      {
        return UnBCL::Environment::m_SystemInfo;
      }
    }
    v53 = 0;
    v47 = 0;
    if ( pExecuteWmiQuery(&v53, L"SELECT * FROM Win32_ComputerSystem") >= 0
      && ((int (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, __int64 *, int *))v53->lpVtbl->Next)(
           v53,
           1000,
           1,
           &v47,
           &v45) >= 0
      && v45 == 1
      && v47 )
    {
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v47 + 32LL))(
             v47,
             L"Manufacturer",
             0,
             &pvarg,
             0,
             0) >= 0
        && pvarg.vt == 8
        && pvarg.llVal )
      {
        v22 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v22;
        if ( v22 )
          v23 = UnBCL::String::String(v22, pvarg.bstrVal);
        else
          v23 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v23);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 48, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantInit(&v50);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v47 + 32LL))(
             v47,
             L"Model",
             0,
             &v50,
             0,
             0) >= 0
        && v50.vt == 8
        && v50.llVal )
      {
        v24 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v24;
        if ( v24 )
          v25 = UnBCL::String::String(v24, v50.bstrVal);
        else
          v25 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v25);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 64, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantInit(&v57);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v47 + 32LL))(
             v47,
             L"NumberOfProcessors",
             0,
             &v57,
             0,
             0) >= 0
        && v57.vt == 3 )
      {
        *((_DWORD *)UnBCL::Environment::m_SystemInfo + 34) = v57.lVal;
      }
      VariantInit(&v52);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v47 + 32LL))(
             v47,
             L"NumberOfLogicalProcessors",
             0,
             &v52,
             0,
             0) >= 0
        && v52.vt == 3 )
      {
        *((_DWORD *)UnBCL::Environment::m_SystemInfo + 35) = v52.lVal;
      }
      VariantClear(&v52);
      VariantClear(&v57);
      VariantClear(&v50);
      VariantClear(&pvarg);
    }
    v56 = 0;
    v49 = 0;
    if ( pExecuteWmiQuery(&v56, L"SELECT * FROM Win32_bios") >= 0
      && ((int (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, __int64 *, int *))v56->lpVtbl->Next)(
           v56,
           1000,
           1,
           &v49,
           &v45) >= 0
      && v45 == 1
      && v49 )
    {
      VariantInit(&v52);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v49 + 32LL))(
             v49,
             L"Name",
             0,
             &v52,
             0,
             0) >= 0
        && v52.vt == 8
        && v52.llVal )
      {
        v26 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v26;
        if ( v26 )
          v27 = UnBCL::String::String(v26, v52.bstrVal);
        else
          v27 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v27);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 80, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantInit(&v50);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v49 + 32LL))(
             v49,
             L"SMBIOSBIOSVersion",
             0,
             &v50,
             0,
             0) >= 0
        && v50.vt == 8
        && v50.llVal )
      {
        v28 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v28;
        if ( v28 )
          v29 = UnBCL::String::String(v28, v50.bstrVal);
        else
          v29 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v29);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 96, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v49 + 32LL))(
             v49,
             L"ReleaseDate",
             0,
             &pvarg,
             0,
             0) >= 0
        && pvarg.vt == 8
        && pvarg.llVal )
      {
        v30 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v30;
        if ( v30 )
          v31 = UnBCL::String::String(v30, pvarg.bstrVal);
        else
          v31 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v31);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 112, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantClear(&pvarg);
      VariantClear(&v50);
      VariantClear(&v52);
    }
    v48 = 0;
    Library = LoadLibraryExW(L"kernel32.dll", 0, 0);
    v33 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetPhysicallyInstalledSystemMemory");
      if ( ProcAddress && ((unsigned int (__fastcall *)(DWORDLONG *))ProcAddress)(&v48) )
        v48 <<= 10;
      FreeLibrary(v33);
    }
    ullTotalPhys = v48;
    if ( !v48 )
    {
      memset_0(&v62, 0, sizeof(v62));
      v62.dwLength = 64;
      if ( GlobalMemoryStatusEx(&v62) )
      {
        ullTotalPhys = v62.ullTotalPhys;
        v48 = v62.ullTotalPhys;
      }
      else
      {
        ullTotalPhys = v48;
      }
    }
    *((_QWORD *)UnBCL::Environment::m_SystemInfo + 16) = ullTotalPhys;
    v55 = 0;
    v46 = 0;
    if ( pExecuteWmiQuery(&v55, L"SELECT Manufacturer, Name, Caption, Architecture, MaxClockSpeed FROM Win32_Processor") >= 0
      && ((int (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, __int64 *, int *))v55->lpVtbl->Next)(
           v55,
           1000,
           1,
           &v46,
           &v45) >= 0
      && v45 == 1
      && v46 )
    {
      VariantInit(&v50);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v46 + 32LL))(
             v46,
             L"Manufacturer",
             0,
             &v50,
             0,
             0) >= 0
        && v50.vt == 8
        && v50.llVal )
      {
        v36 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v36;
        if ( v36 )
          v37 = UnBCL::String::String(v36, v50.bstrVal);
        else
          v37 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v37);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 144, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v46 + 32LL))(
             v46,
             L"Name",
             0,
             &pvarg,
             0,
             0) >= 0
        && pvarg.vt == 8
        && pvarg.llVal )
      {
        v38 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v38;
        if ( v38 )
          v39 = UnBCL::String::String(v38, pvarg.bstrVal);
        else
          v39 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v39);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 160, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantInit(&v52);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v46 + 32LL))(
             v46,
             L"Caption",
             0,
             &v52,
             0,
             0) >= 0
        && v52.vt == 8
        && v52.llVal )
      {
        v40 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v43 = (void **)v40;
        if ( v40 )
          v41 = UnBCL::String::String(v40, v52.bstrVal);
        else
          v41 = 0;
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(&v43, v41);
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign((char *)UnBCL::Environment::m_SystemInfo + 176, v44);
        v43 = &UnBCL::SmartPtr<UnBCL::String>::`vftable';
        UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(&v43);
      }
      VariantInit(&v58);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v46 + 32LL))(
             v46,
             L"Architecture",
             0,
             &v58,
             0,
             0) >= 0
        && v58.vt == 3 )
      {
        *((_DWORD *)UnBCL::Environment::m_SystemInfo + 48) = v58.lVal;
      }
      VariantInit(&v57);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v46 + 32LL))(
             v46,
             L"MaxClockSpeed",
             0,
             &v57,
             0,
             0) >= 0
        && v57.vt == 3 )
      {
        *((_DWORD *)UnBCL::Environment::m_SystemInfo + 49) = v57.lVal;
      }
      VariantClear(&v57);
      VariantClear(&v58);
      VariantClear(&v52);
      VariantClear(&pvarg);
      VariantClear(&v50);
    }
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v55 )
      ((void (__fastcall *)(struct IEnumWbemClassObject *))v55->lpVtbl->Release)(v55);
    if ( v49 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    if ( v56 )
      ((void (__fastcall *)(struct IEnumWbemClassObject *))v56->lpVtbl->Release)(v56);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( v53 )
      ((void (__fastcall *)(struct IEnumWbemClassObject *))v53->lpVtbl->Release)(v53);
    if ( v20 )
      CoUninitialize();
    return UnBCL::Environment::m_SystemInfo;
  }
  return v2;
}

```

## disassembly

```asm
0x180036fd0  push    rbp
0x180036fd2  push    rbx
0x180036fd3  push    rsi
0x180036fd4  push    rdi
0x180036fd5  push    r12
0x180036fd7  push    r13
0x180036fd9  push    r14
0x180036fdb  lea     rbp, [rsp-0B0h]
0x180036fe3  sub     rsp, 1B0h
0x180036fea  mov     [rbp+0E0h+var_D0], 0FFFFFFFFFFFFFFFEh
0x180036ff2  mov     rax, cs:__security_cookie
0x180036ff9  xor     rax, rsp
0x180036ffc  mov     [rbp+0E0h+var_40], rax
0x180037003  mov     eax, ecx
0x180037005  mov     r14d, 1
0x18003700b  mov     rcx, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x180037012  xor     esi, esi
0x180037014  test    rcx, rcx
0x180037017  jz      short loc_180037034
0x180037019  test    eax, eax
0x18003701b  jz      loc_180037AD5
0x180037021  test    rcx, rcx
0x180037024  jz      short loc_180037034
0x180037026  mov     rax, [rcx]
0x180037029  mov     edx, r14d
0x18003702c  mov     rax, [rax]
0x18003702f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037034  mov     edx, 2; unsigned int
0x180037039  mov     edi, 0C8h
0x18003703e  mov     ecx, edi; unsigned __int64
0x180037040  call    ??2Object@UnBCL@@SAPEAX_KI@Z; UnBCL::Object::operator new(unsigned __int64,uint)
0x180037045  mov     rbx, rax
0x180037048  test    rax, rax
0x18003704b  jz      short loc_180037064
0x18003704d  mov     r8d, edi; Size
0x180037050  xor     edx, edx; Val
0x180037052  mov     rcx, rax; void *
0x180037055  call    memset_0
0x18003705a  mov     rcx, rbx; this
0x18003705d  call    ??0SystemInfo@UnBCL@@QEAA@XZ; UnBCL::SystemInfo::SystemInfo(void)
0x180037062  jmp     short loc_180037067
0x180037064  mov     rax, rsi
0x180037067  mov     cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA, rax; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x18003706e  mov     [rax+10h], r14d
0x180037072  xorps   xmm0, xmm0
0x180037075  movups  [rbp+0E0h+SystemInformation], xmm0
0x180037079  movups  [rbp+0E0h+var_B8], xmm0
0x18003707d  xor     r9d, r9d; ReturnLength
0x180037080  lea     r8d, [r9+20h]; SystemInformationLength
0x180037084  lea     rdx, [rbp+0E0h+SystemInformation]; SystemInformation
0x180037088  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18003708c  call    cs:__imp_NtQuerySystemInformation
0x180037092  test    eax, eax
0x180037094  js      short loc_1800370A8
0x180037096  mov     ecx, dword ptr [rbp+0E0h+var_B8]
0x180037099  cmp     ecx, 3
0x18003709c  jge     short loc_1800370A8
0x18003709e  mov     rax, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x1800370a5  mov     [rax+10h], ecx
0x1800370a8  call    cs:__imp_GetSystemDefaultLangID
0x1800370ae  mov     rcx, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x1800370b5  mov     [rcx+14h], ax
0x1800370b9  xorps   xmm0, xmm0
0x1800370bc  movups  xmmword ptr [rbp+0E0h+Buffer], xmm0
0x1800370c3  movups  [rbp+0E0h+var_50], xmm0
0x1800370ca  mov     [rbp+0E0h+nSize], 10h
0x1800370d1  lea     rdx, [rbp+0E0h+nSize]; nSize
0x1800370d5  lea     rcx, [rbp+0E0h+Buffer]; lpBuffer
0x1800370dc  call    cs:__imp_GetComputerNameW
0x1800370e2  mov     r12d, 18h
0x1800370e8  lea     r13, ??_7?$SmartPtr@VString@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::String>::`vftable'
0x1800370ef  test    eax, eax
0x1800370f1  jz      short loc_18003714B
0x1800370f3  mov     ecx, r12d; unsigned __int64
0x1800370f6  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800370fb  mov     [rbp+0E0h+var_120], rax
0x1800370ff  test    rax, rax
0x180037102  jz      short loc_180037115
0x180037104  lea     rdx, [rbp+0E0h+Buffer]; unsigned __int16 *
0x18003710b  mov     rcx, rax; this
0x18003710e  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180037113  jmp     short loc_180037118
0x180037115  mov     rax, rsi
0x180037118  mov     rdx, rax
0x18003711b  lea     rcx, [rsp+1E0h+var_1A0]
0x180037120  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180037125  nop
0x180037126  mov     rcx, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x18003712d  add     rcx, 20h ; ' '
0x180037131  mov     rdx, qword ptr [rsp+1E0h+var_1A0+8]
0x180037136  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18003713b  nop
0x18003713c  mov     qword ptr [rsp+1E0h+var_1A0], r13
0x180037141  lea     rcx, [rsp+1E0h+var_1A0]
0x180037146  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003714b  xorps   xmm0, xmm0
0x18003714e  mov     eax, r14d
0x180037151  xor     ecx, ecx
0x180037153  cpuid
0x180037155  mov     r8d, esi
0x180037158  test    ecx, ecx
0x18003715a  sets    r8b
0x18003715e  movups  [rsp+1E0h+var_1A0], xmm0
0x180037163  mov     eax, 40000003h
0x180037168  xor     ecx, ecx
0x18003716a  cpuid
0x18003716c  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x180037170  mov     dword ptr [rsp+1E0h+var_1A0+8], ecx
0x180037174  mov     dword ptr [rsp+1E0h+var_1A0+0Ch], edx
0x180037178  test    r8d, r8d
0x18003717b  jz      short loc_180037186
0x18003717d  bt      ebx, 0Ch
0x180037181  mov     ecx, r14d
0x180037184  jnb     short loc_180037188
0x180037186  mov     ecx, esi
0x180037188  mov     rax, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x18003718f  mov     [rax+18h], ecx
0x180037192  mov     [rsp+1E0h+var_190], esi
0x180037196  mov     edi, esi
0x180037198  xor     edx, edx; dwCoInit
0x18003719a  xor     ecx, ecx; pvReserved
0x18003719c  call    cs:__imp_CoInitializeEx
0x1800371a2  cmp     eax, 80010106h
0x1800371a7  jz      short loc_1800371BF
0x1800371a9  test    eax, eax
0x1800371ab  jz      short loc_1800371BC
0x1800371ad  cmp     eax, r14d
0x1800371b0  jz      short loc_1800371BC
0x1800371b2  test    eax, eax
0x1800371b4  js      loc_180037ACE
0x1800371ba  jmp     short loc_1800371BF
0x1800371bc  mov     edi, r14d
0x1800371bf  mov     [rbp+0E0h+var_120], rsi
0x1800371c3  mov     [rsp+1E0h+var_180], rsi
0x1800371c8  lea     rdx, aSelectFromWin3; "SELECT * FROM Win32_ComputerSystem"
0x1800371cf  lea     rcx, [rbp+0E0h+var_120]; struct IEnumWbemClassObject **
0x1800371d3  call    ?pExecuteWmiQuery@@YAJPEAPEAUIEnumWbemClassObject@@PEBG@Z; pExecuteWmiQuery(IEnumWbemClassObject * *,ushort const *)
0x1800371d8  test    eax, eax
0x1800371da  js      loc_18003742B
0x1800371e0  mov     rcx, [rbp+0E0h+var_120]
0x1800371e4  mov     rax, [rcx]
0x1800371e7  lea     rdx, [rsp+1E0h+var_190]
0x1800371ec  mov     [rsp+1E0h+var_1C0], rdx
0x1800371f1  lea     r9, [rsp+1E0h+var_180]
0x1800371f6  mov     r8d, r14d
0x1800371f9  mov     edx, 3E8h
0x1800371fe  mov     rax, [rax+20h]
0x180037202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037207  test    eax, eax
0x180037209  js      loc_18003742B
0x18003720f  cmp     [rsp+1E0h+var_190], r14d
0x180037214  jnz     loc_18003742B
0x18003721a  cmp     [rsp+1E0h+var_180], rsi
0x18003721f  jz      loc_18003742B
0x180037225  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180037229  call    cs:__imp_VariantInit
0x18003722f  nop
0x180037230  mov     rcx, [rsp+1E0h+var_180]
0x180037235  mov     rax, [rcx]
0x180037238  mov     [rsp+1E0h+var_1B8], rsi
0x18003723d  mov     [rsp+1E0h+var_1C0], rsi
0x180037242  lea     r9, [rbp+0E0h+pvarg]
0x180037246  xor     r8d, r8d
0x180037249  lea     rdx, aManufacturer; "Manufacturer"
0x180037250  mov     rax, [rax+20h]
0x180037254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037259  test    eax, eax
0x18003725b  js      short loc_1800372C0
0x18003725d  cmp     word ptr [rbp+0E0h+pvarg], 8
0x180037262  jnz     short loc_1800372C0
0x180037264  cmp     qword ptr [rbp+0E0h+pvarg+8], rsi
0x180037268  jz      short loc_1800372C0
0x18003726a  mov     rcx, r12; unsigned __int64
0x18003726d  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180037272  mov     qword ptr [rsp+1E0h+var_1A0], rax
0x180037277  test    rax, rax
0x18003727a  jz      short loc_18003728A
0x18003727c  mov     rdx, qword ptr [rbp+0E0h+pvarg+8]; unsigned __int16 *
0x180037280  mov     rcx, rax; this
0x180037283  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180037288  jmp     short loc_18003728D
0x18003728a  mov     rax, rsi
0x18003728d  mov     rdx, rax
0x180037290  lea     rcx, [rsp+1E0h+var_1A0]
0x180037295  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18003729a  nop
0x18003729b  mov     rcx, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x1800372a2  add     rcx, 30h ; '0'
0x1800372a6  mov     rdx, qword ptr [rsp+1E0h+var_1A0+8]
0x1800372ab  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x1800372b0  nop
0x1800372b1  mov     qword ptr [rsp+1E0h+var_1A0], r13
0x1800372b6  lea     rcx, [rsp+1E0h+var_1A0]
0x1800372bb  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x1800372c0  lea     rcx, [rsp+1E0h+var_168]; pvarg
0x1800372c5  call    cs:__imp_VariantInit
0x1800372cb  nop
0x1800372cc  mov     rcx, [rsp+1E0h+var_180]
0x1800372d1  mov     rax, [rcx]
0x1800372d4  mov     [rsp+1E0h+var_1B8], rsi
0x1800372d9  mov     [rsp+1E0h+var_1C0], rsi
0x1800372de  lea     r9, [rsp+1E0h+var_168]
0x1800372e3  xor     r8d, r8d
0x1800372e6  lea     rdx, aModel; "Model"
0x1800372ed  mov     rax, [rax+20h]
0x1800372f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372f6  test    eax, eax
0x1800372f8  js      short loc_18003735E
0x1800372fa  cmp     word ptr [rsp+1E0h+var_168], 8
0x180037300  jnz     short loc_18003735E
0x180037302  cmp     qword ptr [rbp+0E0h+var_168+8], rsi
0x180037306  jz      short loc_18003735E
0x180037308  mov     rcx, r12; unsigned __int64
0x18003730b  call    ??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180037310  mov     qword ptr [rsp+1E0h+var_1A0], rax
0x180037315  test    rax, rax
0x180037318  jz      short loc_180037328
0x18003731a  mov     rdx, qword ptr [rbp+0E0h+var_168+8]; unsigned __int16 *
0x18003731e  mov     rcx, rax; this
0x180037321  call    ??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180037326  jmp     short loc_18003732B
0x180037328  mov     rax, rsi
0x18003732b  mov     rdx, rax
0x18003732e  lea     rcx, [rsp+1E0h+var_1A0]
0x180037333  call    ??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180037338  nop
0x180037339  mov     rcx, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x180037340  add     rcx, 40h ; '@'
0x180037344  mov     rdx, qword ptr [rsp+1E0h+var_1A0+8]
0x180037349  call    ?Assign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXPEAVXmlNamespaceManager@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::Assign(UnBCL::XmlNamespaceManager *)
0x18003734e  nop
0x18003734f  mov     qword ptr [rsp+1E0h+var_1A0], r13
0x180037354  lea     rcx, [rsp+1E0h+var_1A0]
0x180037359  call    ?DeAssign@?$SmartPtr@VXmlNamespaceManager@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::XmlNamespaceManager>::DeAssign(void)
0x18003735e  lea     rcx, [rbp+0E0h+var_100]; pvarg
0x180037362  call    cs:__imp_VariantInit
0x180037368  nop
0x180037369  mov     rcx, [rsp+1E0h+var_180]
0x18003736e  mov     rax, [rcx]
0x180037371  mov     [rsp+1E0h+var_1B8], rsi
0x180037376  mov     [rsp+1E0h+var_1C0], rsi
0x18003737b  lea     r9, [rbp+0E0h+var_100]
0x18003737f  xor     r8d, r8d
0x180037382  lea     rdx, aNumberofproces; "NumberOfProcessors"
0x180037389  mov     rax, [rax+20h]
0x18003738d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037392  mov     ebx, 3
0x180037397  test    eax, eax
0x180037399  js      short loc_1800373B1
0x18003739b  cmp     word ptr [rbp+0E0h+var_100], bx
0x18003739f  jnz     short loc_1800373B1
0x1800373a1  mov     rcx, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x1800373a8  mov     eax, dword ptr [rbp+0E0h+var_100+8]
0x1800373ab  mov     [rcx+88h], eax
0x1800373b1  lea     rcx, [rbp+0E0h+var_138]; pvarg
0x1800373b5  call    cs:__imp_VariantInit
0x1800373bb  nop
0x1800373bc  mov     rcx, [rsp+1E0h+var_180]
0x1800373c1  mov     rax, [rcx]
0x1800373c4  mov     [rsp+1E0h+var_1B8], rsi
0x1800373c9  mov     [rsp+1E0h+var_1C0], rsi
0x1800373ce  lea     r9, [rbp+0E0h+var_138]
0x1800373d2  xor     r8d, r8d
0x1800373d5  lea     rdx, aNumberoflogica; "NumberOfLogicalProcessors"
0x1800373dc  mov     rax, [rax+20h]
0x1800373e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373e5  test    eax, eax
0x1800373e7  js      short loc_1800373FF
0x1800373e9  cmp     word ptr [rbp+0E0h+var_138], bx
0x1800373ed  jnz     short loc_1800373FF
0x1800373ef  mov     rcx, cs:?m_SystemInfo@Environment@UnBCL@@0PEAVSystemInfo@2@EA; UnBCL::SystemInfo * UnBCL::Environment::m_SystemInfo
0x1800373f6  mov     eax, dword ptr [rbp+0E0h+var_138+8]
0x1800373f9  mov     [rcx+8Ch], eax
0x1800373ff  lea     rcx, [rbp+0E0h+var_138]; pvarg
0x180037403  call    cs:__imp_VariantClear
0x180037409  nop
0x18003740a  lea     rcx, [rbp+0E0h+var_100]; pvarg
0x18003740e  call    cs:__imp_VariantClear
0x180037414  nop
0x180037415  lea     rcx, [rsp+1E0h+var_168]; pvarg
0x18003741a  call    cs:__imp_VariantClear
0x180037420  nop
0x180037421  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x180037425  call    cs:__imp_VariantClear
0x18003742b  mov     [rbp+0E0h+var_108], rsi
0x18003742f  mov     [rsp+1E0h+var_170], rsi
0x180037434  lea     rdx, aSelectFromWin3_0; "SELECT * FROM Win32_bios"
0x18003743b  lea     rcx, [rbp+0E0h+var_108]; struct IEnumWbemClassObject **
0x18003743f  call    ?pExecuteWmiQuery@@YAJPEAPEAUIEnumWbemClassObject@@PEBG@Z; pExecuteWmiQuery(IEnumWbemClassObject * *,ushort const *)
0x180037444  test    eax, eax
0x180037446  js      loc_180037687
0x18003744c  mov     rcx, [rbp+0E0h+var_108]
0x180037450  mov     rax, [rcx]
0x180037453  lea     rdx, [rsp+1E0h+var_190]
0x180037458  mov     [rsp+1E0h+var_1C0], rdx
0x18003745d  lea     r9, [rsp+1E0h+var_170]
0x180037462  mov     r8d, r14d
0x180037465  mov     edx, 3E8h
0x18003746a  mov     rax, [rax+20h]
0x18003746e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
