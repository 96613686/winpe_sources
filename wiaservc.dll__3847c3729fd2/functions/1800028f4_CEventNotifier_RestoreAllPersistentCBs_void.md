# CEventNotifier::RestoreAllPersistentCBs(void)

- ea: `0x1800028f4`
- end: `0x180002c1c`
- name: `?RestoreAllPersistentCBs@CEventNotifier@@QEAAJXZ`
- size: `808`
- prototype: `__int64 __fastcall(CEventNotifier *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800459d8`

## callees

- `0x180001cd4`
- `0x1800028f4`
- `0x1800045e0`
- `0x180006f9c`
- `0x18000a974`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x18000fc60`
- `0x18002de18`
- `0x18002def8`
- `0x180033878`
- `0x180033cc0`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180002b16`
- `ADVAPI32!RegCloseKey` at `0x180002b23`
- `ADVAPI32!RegCloseKey` at `0x180002bb6`
- `ADVAPI32!RegCloseKey` at `0x180002b16`
- `ADVAPI32!RegCloseKey` at `0x180002b23`
- `ADVAPI32!RegCloseKey` at `0x180002bb6`
- `ADVAPI32!RegEnumKeyExW` at `0x180002ac6`
- `ADVAPI32!RegEnumKeyExW` at `0x180002ac6`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a64`
- `ADVAPI32!RegOpenKeyExW` at `0x180002af6`
- `ADVAPI32!RegOpenKeyExW` at `0x180002b53`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a64`
- `ADVAPI32!RegOpenKeyExW` at `0x180002af6`
- `ADVAPI32!RegOpenKeyExW` at `0x180002b53`
- `KERNEL32!LeaveCriticalSection` at `0x180002bc8`
- `KERNEL32!LeaveCriticalSection` at `0x180002bc8`

## string_xrefs

- `0x180002b5d`: `CEventNotifier::RestoreAllPersistentCBs : Can not open STI control key.`
- `0x180002b7f`: `CEventNotifier::RestoreAllPersistentCBs : Can not open STI control key.`
- `0x1800029f1`: `Could not restore persistent event handlers, because we could not find the ServiceComponentHolder`
- `0x180002a13`: `Could not restore persistent event handlers, because we could not find the ServiceComponentHolder`

## pseudocode

```c
__int64 __fastcall CEventNotifier::RestoreAllPersistentCBs(CEventNotifier *this)
{
  struct tagWiaTraceData_Type *v1; // rax
  char *v2; // rdx
  unsigned int v3; // r8d
  unsigned __int64 v4; // rdx
  DeviceListManager *v5; // rbx
  char *v6; // rcx
  char *v7; // rbx
  void *v8; // rdx
  void **v9; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  DWORD i; // ebx
  char *v13; // rbx
  void *v14; // rdx
  void **v15; // rax
  void *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v23; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v24; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+70h] [rbp-90h]
  char v28[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[80]; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int64 *v31; // [rsp+E0h] [rbp-20h] BYREF
  char v32; // [rsp+E8h] [rbp-18h] BYREF
  void *v33; // [rsp+1E8h] [rbp+E8h]
  __int64 v34; // [rsp+1F0h] [rbp+F0h]
  WCHAR Name[128]; // [rsp+210h] [rbp+110h] BYREF

  v1 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CEventNotifier::RestoreAllPresistentCBs");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v30, v2, v3, "CEventNotifier::RestoreAllPersistentCBs", phkResult, v1);
  v24 = 0;
  hKey = 0;
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v28);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v31, L"DeviceListManager");
  v5 = (DeviceListManager *)ServiceComponentHolder::Get<DeviceListManager>(v28, &v31);
  v31 = &CSimpleStringBase<unsigned short>::`vftable';
  if ( v33 && v33 != &v32 )
    operator delete(v33, v4);
  v33 = 0;
  v34 = 0;
  if ( v5 )
  {
    DeviceListManager::EnumerateDevicesWithCallback(v5, 0, 0, (struct EnumDeviceInterface *)&g_eventNotifier);
    v6 = (char *)v5 + *(int *)(*((_QWORD *)v5 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else
  {
    v7 = (char *)WiaTrace_TraceLog("Could not restore persistent event handlers, because we could not find the ServiceComponentHolder");
    WriteDbgTraceErrorWI("CEventNotifier::RestoreAllPersistentCBs", v7);
    WiaTrcLib::Free((WiaTrcLib *)v7, v8);
    v9 = (void **)WiaTrace_Trace("Could not restore persistent event handlers, because we could not find the ServiceComponentHolder");
    WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"CEventNotifier::RestoreAllPersistentCBs", 1, v9);
  }
  CWiaCritSect::CWiaCritSect((CWiaCritSect *)&lpCriticalSection, &stru_1800AF348);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\StillImage\\MSCDeviceList",
          0,
          0x20019u,
          &hKey) )
  {
    for ( i = 0; ; ++i )
    {
      ftLastWriteTime = 0;
      v23 = 0;
      cchName = 128;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      Name[127] = 0;
      if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &v23) )
      {
        CEventNotifier::RestoreDevPersistentCBs((CEventNotifier *)&g_eventNotifier, v23);
        RegCloseKey(v23);
      }
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\StillImage", 0, 0x20019u, &v24) )
  {
    v13 = (char *)WiaTrace_TraceLog("CEventNotifier::RestoreAllPersistentCBs : Can not open STI control key.");
    WriteDbgTraceErrorWI("CEventNotifier::RestoreAllPersistentCBs", v13);
    WiaTrcLib::Free((WiaTrcLib *)v13, v14);
    v15 = (void **)WiaTrace_Trace("CEventNotifier::RestoreAllPersistentCBs : Can not open STI control key.");
    WiaTrace_ProcessTrace_Ex(v17, v16, (void *)"CEventNotifier::RestoreAllPersistentCBs", 1, v15);
  }
  else
  {
    CEventNotifier::RestoreDevPersistentCBs((CEventNotifier *)&g_eventNotifier, v24);
    RegCloseKey(v24);
  }
  if ( v27 )
    LeaveCriticalSection(lpCriticalSection);
  if ( v29 )
  {
    v18 = v29 + *(int *)(*(_QWORD *)v29 + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v30);
  return 0;
}

```

## disassembly

```asm
0x1800028f4  mov     [rsp-8+arg_0], rbx
0x1800028f9  mov     [rsp-8+arg_8], r12
0x1800028fe  push    rbp
0x1800028ff  lea     rbp, [rsp-220h]
0x180002907  sub     rsp, 320h
0x18000290e  mov     rax, cs:__security_cookie
0x180002915  xor     rax, rsp
0x180002918  mov     [rbp+220h+var_10], rax
0x18000291f  lea     rcx, aCeventnotifier_11; "CEventNotifier::RestoreAllPresistentCBs"
0x180002926  call    WiaTrace_Trace
0x18000292b  lea     r12, aCeventnotifier_10; "CEventNotifier::RestoreAllPersistentCBs"
0x180002932  mov     [rsp+320h+lpClass], rax; struct tagWiaTraceData_Type *
0x180002937  mov     r9, r12; char *
0x18000293a  lea     rcx, [rbp+220h+var_290]; this
0x18000293e  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180002943  lea     rcx, [rsp+320h+var_2A8]; this
0x180002948  mov     [rsp+320h+var_2C8], 0
0x180002951  mov     [rsp+320h+hKey], 0
0x18000295a  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18000295f  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x180002966  lea     rcx, [rbp+220h+var_240]
0x18000296a  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000296f  lea     rdx, [rbp+220h+var_240]
0x180002973  lea     rcx, [rsp+320h+var_2A8]
0x180002978  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x18000297d  mov     rcx, [rbp+220h+var_138]; void *
0x180002984  mov     rbx, rax
0x180002987  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000298e  mov     [rbp+220h+var_240], rax
0x180002992  test    rcx, rcx
0x180002995  jz      short loc_1800029A5
0x180002997  lea     rax, [rbp+220h+var_238]
0x18000299b  cmp     rcx, rax
0x18000299e  jz      short loc_1800029A5
0x1800029a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800029a5  mov     [rbp+220h+var_138], 0
0x1800029b0  mov     [rbp+220h+var_130], 0
0x1800029bb  test    rbx, rbx
0x1800029be  jz      short loc_1800029F1
0x1800029c0  lea     r9, ?g_eventNotifier@@3VCEventNotifier@@A; struct EnumDeviceInterface *
0x1800029c7  xor     r8d, r8d; void *
0x1800029ca  xor     edx, edx; int
0x1800029cc  mov     rcx, rbx; this
0x1800029cf  call    ?EnumerateDevicesWithCallback@DeviceListManager@@QEAAXJPEAXPEAVEnumDeviceInterface@@@Z; DeviceListManager::EnumerateDevicesWithCallback(long,void *,EnumDeviceInterface *)
0x1800029d4  mov     rax, [rbx+8]
0x1800029d8  movsxd  rcx, dword ptr [rax+4]
0x1800029dc  add     rcx, 8
0x1800029e0  add     rcx, rbx
0x1800029e3  mov     rax, [rcx]
0x1800029e6  mov     rax, [rax+10h]
0x1800029ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ef  jmp     short loc_180002A32
0x1800029f1  lea     rcx, aCouldNotRestor; "Could not restore persistent event hand"...
0x1800029f8  call    WiaTrace_TraceLog
0x1800029fd  mov     rdx, rax; char *
0x180002a00  mov     rcx, r12; char *
0x180002a03  mov     rbx, rax
0x180002a06  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180002a0b  mov     rcx, rbx; this
0x180002a0e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180002a13  lea     rcx, aCouldNotRestor; "Could not restore persistent event hand"...
0x180002a1a  call    WiaTrace_Trace
0x180002a1f  mov     r9d, 1; int
0x180002a25  mov     [rsp+320h+phkResult], rax; lpMem
0x180002a2a  mov     r8, r12; int
0x180002a2d  call    WiaTrace_ProcessTrace_Ex
0x180002a32  lea     rdx, stru_1800AF348; struct _RTL_CRITICAL_SECTION *
0x180002a39  lea     rcx, [rsp+320h+lpCriticalSection]; this
0x180002a3e  call    ??0CWiaCritSect@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CWiaCritSect::CWiaCritSect(_RTL_CRITICAL_SECTION *)
0x180002a43  lea     rax, [rsp+320h+hKey]
0x180002a48  mov     r9d, 20019h; samDesired
0x180002a4e  xor     r8d, r8d; ulOptions
0x180002a51  mov     [rsp+320h+phkResult], rax; phkResult
0x180002a56  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Sti"...
0x180002a5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002a64  call    cs:__imp_RegOpenKeyExW
0x180002a6a  test    eax, eax
0x180002a6c  jnz     loc_180002B32
0x180002a72  xor     ebx, ebx
0x180002a74  mov     rcx, [rsp+320h+hKey]; hKey
0x180002a79  lea     rax, [rsp+320h+ftLastWriteTime]
0x180002a7e  mov     [rsp+320h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180002a83  lea     r9, [rsp+320h+cchName]; lpcchName
0x180002a88  mov     [rsp+320h+lpcchClass], 0; lpcchClass
0x180002a91  lea     r8, [rbp+220h+Name]; lpName
0x180002a98  mov     [rsp+320h+lpClass], 0; lpClass
0x180002aa1  mov     edx, ebx; dwIndex
0x180002aa3  mov     [rsp+320h+phkResult], 0; lpReserved
0x180002aac  mov     qword ptr [rsp+320h+ftLastWriteTime.dwLowDateTime], 0
0x180002ab5  mov     [rsp+320h+var_2D0], 0
0x180002abe  mov     [rsp+320h+cchName], 80h
0x180002ac6  call    cs:__imp_RegEnumKeyExW
0x180002acc  mov     rcx, [rsp+320h+hKey]; hKey
0x180002ad1  test    eax, eax
0x180002ad3  jnz     short loc_180002B23
0x180002ad5  mov     [rbp+220h+var_12], ax
0x180002adc  lea     rdx, [rbp+220h+Name]; lpSubKey
0x180002ae3  lea     rax, [rsp+320h+var_2D0]
0x180002ae8  mov     r9d, 20019h; samDesired
0x180002aee  xor     r8d, r8d; ulOptions
0x180002af1  mov     [rsp+320h+phkResult], rax; phkResult
0x180002af6  call    cs:__imp_RegOpenKeyExW
0x180002afc  test    eax, eax
0x180002afe  jnz     short loc_180002B1C
0x180002b00  mov     rdx, [rsp+320h+var_2D0]; HKEY
0x180002b05  lea     rcx, ?g_eventNotifier@@3VCEventNotifier@@A; this
0x180002b0c  call    ?RestoreDevPersistentCBs@CEventNotifier@@QEAAJPEAUHKEY__@@@Z; CEventNotifier::RestoreDevPersistentCBs(HKEY__ *)
0x180002b11  mov     rcx, [rsp+320h+var_2D0]; hKey
0x180002b16  call    cs:__imp_RegCloseKey
0x180002b1c  inc     ebx
0x180002b1e  jmp     loc_180002A74
0x180002b23  call    cs:__imp_RegCloseKey
0x180002b29  mov     [rsp+320h+hKey], 0
0x180002b32  lea     rax, [rsp+320h+var_2C8]
0x180002b37  mov     r9d, 20019h; samDesired
0x180002b3d  xor     r8d, r8d; ulOptions
0x180002b40  mov     [rsp+320h+phkResult], rax; phkResult
0x180002b45  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Sti"...
0x180002b4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180002b53  call    cs:__imp_RegOpenKeyExW
0x180002b59  test    eax, eax
0x180002b5b  jz      short loc_180002BA0
0x180002b5d  lea     rcx, aCeventnotifier_17; "CEventNotifier::RestoreAllPersistentCBs"...
0x180002b64  call    WiaTrace_TraceLog
0x180002b69  mov     rdx, rax; char *
0x180002b6c  mov     rcx, r12; char *
0x180002b6f  mov     rbx, rax
0x180002b72  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180002b77  mov     rcx, rbx; this
0x180002b7a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180002b7f  lea     rcx, aCeventnotifier_17; "CEventNotifier::RestoreAllPersistentCBs"...
0x180002b86  call    WiaTrace_Trace
0x180002b8b  mov     r9d, 1; int
0x180002b91  mov     [rsp+320h+phkResult], rax; lpMem
0x180002b96  mov     r8, r12; int
0x180002b99  call    WiaTrace_ProcessTrace_Ex
0x180002b9e  jmp     short loc_180002BBC
0x180002ba0  mov     rdx, [rsp+320h+var_2C8]; HKEY
0x180002ba5  lea     rcx, ?g_eventNotifier@@3VCEventNotifier@@A; this
0x180002bac  call    ?RestoreDevPersistentCBs@CEventNotifier@@QEAAJPEAUHKEY__@@@Z; CEventNotifier::RestoreDevPersistentCBs(HKEY__ *)
0x180002bb1  mov     rcx, [rsp+320h+var_2C8]; hKey
0x180002bb6  call    cs:__imp_RegCloseKey
0x180002bbc  cmp     [rsp+320h+var_2B0], 0
0x180002bc1  jz      short loc_180002BCE
0x180002bc3  mov     rcx, [rsp+320h+lpCriticalSection]; lpCriticalSection
0x180002bc8  call    cs:__imp_LeaveCriticalSection
0x180002bce  mov     rdx, [rbp+220h+var_2A0]
0x180002bd2  test    rdx, rdx
0x180002bd5  jz      short loc_180002BED
0x180002bd7  mov     rax, [rdx]
0x180002bda  movsxd  rcx, dword ptr [rax+4]
0x180002bde  add     rcx, rdx
0x180002be1  mov     rax, [rcx]
0x180002be4  mov     rax, [rax+10h]
0x180002be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bed  lea     rcx, [rbp+220h+var_290]; this
0x180002bf1  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x180002bf6  xor     eax, eax
0x180002bf8  mov     rcx, [rbp+220h+var_10]
0x180002bff  xor     rcx, rsp; StackCookie
0x180002c02  call    __security_check_cookie
0x180002c07  lea     r11, [rsp+320h+var_s0]
0x180002c0f  mov     rbx, [r11+10h]
0x180002c13  mov     r12, [r11+18h]
0x180002c17  mov     rsp, r11
0x180002c1a  pop     rbp
0x180002c1b  retn
```
