# XE_Engine::Initialize(XEHostProperties const * const)

- ea: `0x1005e3c00`
- end: `0x1005e4783`
- name: `?Initialize@XE_Engine@@SAHQEBUXEHostProperties@@@Z`
- size: `2947`
- prototype: `__int64 __fastcall(const struct XEHostProperties *const)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x100403070`
- `0x100406510`
- `0x10041e880`
- `0x10041ee60`
- `0x100442c50`
- `0x1004544e0`
- `0x10046b900`
- `0x10046ca90`
- `0x1004adef0`
- `0x1004afa70`
- `0x1004b6cf0`
- `0x100556660`
- `0x1005b7b20`
- `0x1005e1020`
- `0x1005e1150`
- `0x1005e3c00`
- `0x1005e4b30`
- `0x1005e4d00`
- `0x1005e4f90`
- `0x1005f2350`
- `0x1005f5f40`
- `0x1005fa810`
- `0x1005fa9c0`

## import_xrefs

- `KERNEL32!QueryPerformanceFrequency` at `0x1005e4434`
- `KERNEL32!QueryPerformanceFrequency` at `0x1005e4434`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e4454`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e4486`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e44d8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e4503`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e4454`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e4486`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e44d8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005e4503`
- `KERNEL32!FlsGetValue` at `0x1005e404e`
- `KERNEL32!FlsSetValue` at `0x1005e405c`
- `KERNEL32!FlsAlloc` at `0x1005e4071`
- `KERNEL32!FlsAlloc` at `0x1005e4071`
- `KERNEL32!TlsAlloc` at `0x1005e4079`
- `KERNEL32!TlsAlloc` at `0x1005e4079`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e446d`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e44a4`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e44eb`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e4516`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e446d`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e44a4`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e44eb`
- `KERNEL32!QueryPerformanceCounter` at `0x1005e4516`
- `KERNEL32!GetModuleHandleW` at `0x1005e3f3d`
- `KERNEL32!GetModuleHandleW` at `0x1005e3f3d`
- `KERNEL32!GetProcAddress` at `0x1005e3f52`
- `KERNEL32!GetProcAddress` at `0x1005e3f52`
- `KERNEL32!GetLastError` at `0x1005e3f66`
- `KERNEL32!GetLastError` at `0x1005e3f66`

## string_xrefs

- `0x1005e40bd`: `sql\common\dk\xe\xeeng\xeeng.cpp`
- `0x1005e4193`: `sql\common\dk\xe\xeeng\xeeng.cpp`
- `0x1005e41ff`: `sql\common\dk\xe\xeeng\xeeng.cpp`
- `0x1005e42ae`: `sql\common\dk\xe\xeeng\xeeng.cpp`
- `0x1005e4313`: `sql\common\dk\xe\xeeng\xeeng.cpp`
- `0x1005e4399`: `sql\common\dk\xe\xeeng\xeeng.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall XE_Engine::Initialize(const struct XEHostProperties *const a1)
{
  unsigned int v2; // r15d
  int v3; // edx
  int v4; // ecx
  unsigned __int16 v5; // si
  char *v6; // rbx
  __int64 v7; // rax
  bool (__fastcall *v8)(WaitForGraph *__hidden); // rax
  __int64 (__fastcall *v9)(wchar_t *, unsigned __int64); // rax
  __int64 (__fastcall *v10)(wchar_t *, unsigned __int64); // rax
  __int64 (__fastcall *v11)(const wchar_t *, wchar_t *, unsigned __int64); // rax
  int (*v12)(const wchar_t *, wchar_t *, unsigned __int64); // rax
  int (*v13)(const wchar_t *, wchar_t *, unsigned __int64); // rax
  int (*v14)(wchar_t *, unsigned __int64, const wchar_t *, const wchar_t *); // rax
  __int64 (__fastcall *v15)(PWSTR, unsigned __int64, const wchar_t *, const wchar_t *); // rax
  __int64 (__fastcall *v16)(const wchar_t *); // rax
  __int64 (__fastcall *v17)(wchar_t *, LPCWSTR); // rax
  __int64 (__fastcall *v18)(LPCWSTR, DWORD, DWORD, LPSECURITY_ATTRIBUTES, DWORD, DWORD, HANDLE); // rax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  signed int v21; // eax
  signed int LastError; // eax
  bool v23; // sf
  struct IDmpClient *v24; // rax
  struct IMemObj *Pmo; // rax
  unsigned int SOSHostObject; // eax
  struct SOSHost_MemObj *v27; // rdi
  int v28; // r14d
  struct SOSHost_MemObj *v29; // rbx
  DWORD v30; // eax
  struct XE_TlsRecordBlock **v31; // rax
  struct SOSHost_MemObj *v32; // rax
  struct SOSHost_MemObj *v33; // rax
  SOSHost_RecursiveMutex *v34; // rax
  struct SOSHost *v35; // rdx
  struct ISOSClient_ResourceInfo *v36; // r8
  SOSHost_RecursiveMutex *v37; // rax
  struct SOSHost_MemObj *v38; // rdi
  struct SOSClient_MemoryNotificationCallback *v39; // rbx
  _OWORD *v40; // rax
  _QWORD *v41; // rcx
  _QWORD *v42; // rax
  struct XE_FeatureSwitches *v43; // rax
  struct XE_FeatureSwitches *v44; // rbx
  unsigned int v45; // r14d
  LARGE_INTEGER v46; // rbx
  LARGE_INTEGER v47; // rdi
  struct _FILETIME v48; // rcx
  LARGE_INTEGER v49; // rax
  union _LARGE_INTEGER v50; // rax
  __int64 QuadPart; // xmm2_8
  LONGLONG v52; // rax
  __int16 v53; // dx
  double v54; // xmm0_8
  bool v55; // zf
  int v56; // ett
  int v58; // [rsp+28h] [rbp-E0h]
  int v59; // [rsp+28h] [rbp-E0h]
  int v60; // [rsp+28h] [rbp-E0h]
  int v61; // [rsp+28h] [rbp-E0h]
  int v62; // [rsp+28h] [rbp-E0h]
  struct IDmpClient *v63; // [rsp+40h] [rbp-C8h] BYREF
  struct SOSHost_MemObj *v64; // [rsp+48h] [rbp-C0h]
  _DWORD v65[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v66; // [rsp+58h] [rbp-B0h]
  struct SOSHost_MemObj *v67; // [rsp+60h] [rbp-A8h]
  struct SOSHost_MemObj *v68; // [rsp+68h] [rbp-A0h]
  LARGE_INTEGER Frequency; // [rsp+70h] [rbp-98h] BYREF
  struct _FILETIME v70; // [rsp+78h] [rbp-90h] BYREF
  struct SOSClient_MemoryNotificationCallback *v71; // [rsp+80h] [rbp-88h]
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-80h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER v74; // [rsp+98h] [rbp-70h] BYREF
  LARGE_INTEGER v75; // [rsp+A0h] [rbp-68h] BYREF
  LARGE_INTEGER v76; // [rsp+A8h] [rbp-60h] BYREF
  struct _FILETIME v77; // [rsp+B0h] [rbp-58h] BYREF
  struct _FILETIME v78; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v79; // [rsp+C0h] [rbp-48h]
  __int64 v80; // [rsp+D0h] [rbp-38h]
  __int64 v81; // [rsp+D8h] [rbp-30h]
  int v82; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v83; // [rsp+F0h] [rbp-18h]
  _DWORD v84[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v85; // [rsp+100h] [rbp-8h]
  char v86[64]; // [rsp+108h] [rbp+0h] BYREF
  __int16 v87[2]; // [rsp+148h] [rbp+40h] BYREF
  __int128 v88; // [rsp+14Ch] [rbp+44h]
  int v89; // [rsp+15Ch] [rbp+54h]
  __int16 v90; // [rsp+160h] [rbp+58h]

  v81 = -2;
  v2 = 1;
  SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(&v82, 536871062, 1);
  do
  {
    v3 = XE_Engine::sm_initializer;
    v4 = XE_Engine::sm_initializer + 1;
    if ( XE_Engine::sm_initializer >= 0 )
      v4 = _InterlockedCompareExchange(
             (volatile signed __int32 *)&XE_Engine::sm_initializer,
             v4 | 0x80000000,
             XE_Engine::sm_initializer);
    _mm_pause();
  }
  while ( v4 != v3 );
  if ( v4 )
    goto LABEL_139;
  v5 = 0;
  if ( !qword_100715148 || !qword_100714EC8 || !qword_100720EC8 )
  {
    v65[0] = 655370;
    v65[1] = 1310738;
    LOWORD(v66) = 10;
    v2 = XE_API::Initialize(0, (const struct XEEngineVersion *)v65);
    if ( !v2 )
    {
      v5 = 6;
      goto LABEL_138;
    }
  }
  v2 = 0;
  if ( (__int64 (__fastcall *)(const struct XEHostProperties *const))qword_100715160 != XE_Engine::Initialize )
  {
    v5 = 9;
    goto LABEL_138;
  }
  if ( a1 )
  {
    if ( *(_WORD *)a1 )
    {
      if ( *(_WORD *)a1 == 10 )
      {
        XE_Engine::sm_hostProperties = *(_OWORD *)a1;
        *(_OWORD *)&qword_1007BB6F0 = *((_OWORD *)a1 + 1);
        *(_OWORD *)&qword_1007BB700 = *((_OWORD *)a1 + 2);
        *(_OWORD *)&qword_1007BB710 = *((_OWORD *)a1 + 3);
        *(_OWORD *)&qword_1007BB720 = *((_OWORD *)a1 + 4);
        *(_OWORD *)&qword_1007BB730 = *((_OWORD *)a1 + 5);
        *(_OWORD *)&qword_1007BB740 = *((_OWORD *)a1 + 6);
        *((_OWORD *)&qword_1007BB760 - 1) = *((_OWORD *)a1 + 7);
        v6 = (char *)a1 + 128;
        *(_OWORD *)&qword_1007BB760 = *(_OWORD *)v6;
        *(_OWORD *)&qword_1007BB770 = *((_OWORD *)v6 + 1);
        *(_OWORD *)&qword_1007BB780 = *((_OWORD *)v6 + 2);
        *(_OWORD *)&qword_1007BB790 = *((_OWORD *)v6 + 3);
        *(_OWORD *)&qword_1007BB7A0 = *((_OWORD *)v6 + 4);
        *(_OWORD *)&qword_1007BB7B0 = *((_OWORD *)v6 + 5);
        qword_1007BB7C0 = *((_QWORD *)v6 + 12);
        v7 = qword_1007BB710;
        if ( !qword_1007BB710 )
          v7 = qword_10078FB40;
        qword_1007BB710 = v7;
        v8 = (bool (__fastcall *)(WaitForGraph *__hidden))qword_1007BB718;
        if ( !qword_1007BB718 )
          v8 = off_10078FB48;
        qword_1007BB718 = (__int64)v8;
        v9 = (__int64 (__fastcall *)(wchar_t *, unsigned __int64))qword_1007BB760;
        if ( !qword_1007BB760 )
          v9 = off_10078FB90[0];
        qword_1007BB760 = (__int64)v9;
        v10 = (__int64 (__fastcall *)(wchar_t *, unsigned __int64))qword_1007BB768;
        if ( !qword_1007BB768 )
          v10 = off_10078FB98;
        qword_1007BB768 = (__int64)v10;
        v11 = (__int64 (__fastcall *)(const wchar_t *, wchar_t *, unsigned __int64))qword_1007BB770;
        if ( !qword_1007BB770 )
          v11 = off_10078FBA0;
        qword_1007BB770 = (__int64)v11;
        v12 = (int (*)(const wchar_t *, wchar_t *, unsigned __int64))qword_1007BB778;
        if ( !qword_1007BB778 )
          v12 = off_10078FBA8[0];
        qword_1007BB778 = (__int64)v12;
        v13 = (int (*)(const wchar_t *, wchar_t *, unsigned __int64))qword_1007BB780;
        if ( !qword_1007BB780 )
          v13 = off_10078FBB0;
        qword_1007BB780 = (__int64)v13;
        v14 = (int (*)(wchar_t *, unsigned __int64, const wchar_t *, const wchar_t *))qword_1007BB788;
        if ( !qword_1007BB788 )
          v14 = off_10078FBB8;
        qword_1007BB788 = (__int64)v14;
        v15 = (__int64 (__fastcall *)(PWSTR, unsigned __int64, const wchar_t *, const wchar_t *))qword_1007BB790;
        if ( !qword_1007BB790 )
          v15 = off_10078FBC0;
        qword_1007BB790 = (__int64)v15;
        v16 = (__int64 (__fastcall *)(const wchar_t *))qword_1007BB798;
        if ( !qword_1007BB798 )
          v16 = off_10078FBC8;
        qword_1007BB798 = (__int64)v16;
        v17 = (__int64 (__fastcall *)(wchar_t *, LPCWSTR))qword_1007BB708;
        if ( !qword_1007BB708 )
          v17 = off_10078FB38;
        qword_1007BB708 = (__int64)v17;
        v18 = (__int64 (__fastcall *)(LPCWSTR, DWORD, DWORD, LPSECURITY_ATTRIBUTES, DWORD, DWORD, HANDLE))qword_1007BB6F8;
        if ( !qword_1007BB6F8 )
          v18 = off_10078FB28;
        qword_1007BB6F8 = (__int64)v18;
        if ( !qword_1007BB7A0 )
          qword_1007BB7A0 = (__int64)off_10078FBD0;
      }
    }
    else
    {
      qword_1007BB6E8 = *((_QWORD *)a1 + 1);
      qword_1007BB6F0 = *((_QWORD *)a1 + 2);
      qword_1007BB6F8 = *((_QWORD *)a1 + 3);
      qword_1007BB700 = *((_QWORD *)a1 + 4);
    }
  }
  XE_Engine::sm_pObjectFactory = (struct XE_EngineObjectFactory *)&off_10078FC40;
  XE_DumpCallbacks::sm_pInstance = (struct XE_DumpCallbacks *)((__int64 (*)(void))off_10078FC40[4])();
  v63 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "DmpGetClientExport");
    if ( ProcAddress )
    {
      v21 = ((__int64 (__fastcall *)(struct IDmpClient **))ProcAddress)(&v63);
LABEL_48:
      v23 = v21 < 0;
      goto LABEL_49;
    }
  }
  LastError = GetLastError();
  v23 = LastError < 0;
  if ( LastError > 0 )
  {
    v21 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_48;
  }
LABEL_49:
  if ( !v23
    && (*(int (__fastcall **)(struct IDmpClient *, struct XE_DumpCallbacks *, struct DMP_CLIENT_CALLBACK_COOKIE__ **))(*(_QWORD *)v63 + 56LL))(
         v63,
         XE_DumpCallbacks::sm_pInstance,
         &XE_DumpCallbacks::sm_dumpCallbackCookie) >= 0 )
  {
    v24 = v63;
    v63 = 0;
    XE_DumpCallbacks::sm_pDumpClient = v24;
  }
  if ( v63 )
    (*(void (__fastcall **)(struct IDmpClient *))(*(_QWORD *)v63 + 16LL))(v63);
  Pmo = SOS_Node::GetPmo();
  SOSHostObject = HostManager::CreateSOSHostObject(
                    &SOS_PublicGlobals::sm_HostManager,
                    Pmo,
                    67,
                    L"XE_Host",
                    &XE_Engine::sm_pHost);
  if ( (int)HRESULT_FROM_SOS_RESULT(SOSHostObject) < 0 )
    goto LABEL_138;
  XE_Engine::sm_hostVersion = 1;
  qword_1007B23C8 = 127;
  qword_1007B23D0 = 1023;
  if ( !(unsigned int)XE_Engine::InitializeMemorySubsystem() )
    goto LABEL_138;
  v27 = XE_Engine::sm_pmo;
  v67 = XE_Engine::sm_pmo;
  v28 = 0;
  v29 = 0;
  v68 = 0;
  XE_Tls::sm_useFibers = SOS_PublicGlobals::sm_WorkerType == 0;
  if ( SOS_PublicGlobals::sm_WorkerType )
  {
    v30 = TlsAlloc();
  }
  else
  {
    XE_Tls::sm_XlsGetValue = (void *(*)(unsigned int))FlsGetValue;
    XE_Tls::sm_XlsSetValue = (int (*)(unsigned int, void *))FlsSetValue;
    v30 = FlsAlloc(XE_Tls::FlsCallback);
  }
  if ( v30 != -1 )
  {
    XE_Tls::sm_tlsSlot = v30;
    v31 = (struct XE_TlsRecordBlock **)XE_TlsRecordBlock::BlockAllocate();
    if ( v31 )
    {
      XE_Tls::sm_pBlocks = v31;
      LOBYTE(v58) = 6;
      v32 = (struct SOSHost_MemObj *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**((_QWORD **)v27 + 1) + 80LL))(
                                       *((_QWORD *)v27 + 1),
                                       48,
                                       "sql\\common\\dk\\xe\\xeeng\\xeeng.cpp",
                                       294,
                                       v58);
      v64 = v32;
      if ( v32 )
      {
        *(_QWORD *)v32 = 0;
        *((_QWORD *)v32 + 1) = 0;
        *((_DWORD *)v32 + 4) = 1;
        *((_QWORD *)v32 + 3) = 0;
        *((_QWORD *)v32 + 4) = 0;
        *((_QWORD *)v32 + 5) = XE_Tls::ThreadCreateDestroyCallback;
      }
      else
      {
        v32 = 0;
      }
      v29 = v32;
      v68 = v32;
      if ( v32 )
      {
        v29 = 0;
        v68 = 0;
        XE_Tls::sm_cbo = v32;
        XList<BaseSafeCallbackTraits<TBaseSafeCallbackWithParam<void,TListSLock,SOSCallbackEvent,void *,SystemAffinity const &,SystemAffinity const &,NullType>,TListSLock,SOSCallbackEvent>::Elem>::Insert(
          &SOS_OS::sm_OSThreadCreateDestroyCallbackList,
          v32);
        v28 = 1;
      }
    }
  }
  v64 = v29;
  if ( v29 )
  {
    if ( *((_QWORD *)v29 + 3) )
      BaseSafeCallbackTraits<TBaseSafeCallbackWithParam<void,TListSLock,SOSCallbackEvent,void *,SOS_Node *,unsigned __int64,unsigned __int64>,TListSLock,SOSCallbackEvent>::Elem::RemoveSelf(v29);
    operator delete(v29, 0x30u);
  }
  if ( !v28 )
    goto LABEL_138;
  XE_Engine::sm_pTimer = XE_Timer::Create(XE_Engine::sm_pmo);
  if ( !XE_Engine::sm_pTimer )
    goto LABEL_138;
  LOBYTE(v58) = 6;
  v33 = (struct SOSHost_MemObj *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**((_QWORD **)XE_Engine::sm_pmo + 1) + 80LL))(
                                   *((_QWORD *)XE_Engine::sm_pmo + 1),
                                   48,
                                   "sql\\common\\dk\\xe\\xeeng\\xeeng.cpp",
                                   3360,
                                   v58);
  v64 = v33;
  if ( v33 )
  {
    *(_DWORD *)v33 = 1;
    *((_QWORD *)v33 + 2) = (char *)v33 + 8;
    *((_QWORD *)v33 + 1) = (char *)v33 + 8;
    *((_QWORD *)v33 + 4) = (char *)v33 + 24;
    *((_QWORD *)v33 + 3) = (char *)v33 + 24;
    *((_QWORD *)v33 + 5) = 0;
  }
  else
  {
    v33 = 0;
  }
  XE_Engine::sm_sessionMgr = v33;
  if ( !v33 )
    goto LABEL_138;
  LOBYTE(v59) = 6;
  v34 = (SOSHost_RecursiveMutex *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**((_QWORD **)XE_Engine::sm_pmo + 1) + 80LL))(
                                    *((_QWORD *)XE_Engine::sm_pmo + 1),
                                    304,
                                    "sql\\common\\dk\\xe\\xeeng\\xeeng.cpp",
                                    3364,
                                    v59);
  v64 = v34;
  v37 = v34 ? SOSHost_RecursiveMutex::SOSHost_RecursiveMutex(v34, v35, v36) : 0LL;
  XE_Engine::sm_sessionCreateLock = v37;
  if ( !v37 )
    goto LABEL_138;
  XE_Engine::sm_pTable = XE_ModuleManager::Create(XE_Engine::sm_pmo);
  if ( !XE_Engine::sm_pTable )
    goto LABEL_138;
  XE_Engine::sm_singletonTargetMgr = XE_SingletonTargetManager::Create(XE_Engine::sm_pmo);
  if ( !XE_Engine::sm_singletonTargetMgr
    || !(**(unsigned int (__fastcall ***)(struct XE_EngineObjectFactory *, struct SOSHost_MemObj *))XE_Engine::sm_pObjectFactory)(
          XE_Engine::sm_pObjectFactory,
          XE_Engine::sm_pmo) )
  {
    goto LABEL_138;
  }
  v38 = XE_Engine::sm_pmo;
  v64 = XE_Engine::sm_pmo;
  LOBYTE(v60) = 6;
  v39 = (struct SOSClient_MemoryNotificationCallback *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**((_QWORD **)XE_Engine::sm_pmo + 1) + 80LL))(
                                                         *((_QWORD *)XE_Engine::sm_pmo + 1),
                                                         24,
                                                         "sql\\common\\dk\\xe\\xeeng\\xeeng.cpp",
                                                         699,
                                                         v60);
  v67 = v39;
  if ( v39 )
  {
    *(_QWORD *)v39 = &XE_IProxyTransportStrategy::`vftable';
    *((_DWORD *)v39 + 2) = 1;
    *(_QWORD *)v39 = &XE_NotificationManager::`vftable';
    *((_QWORD *)v39 + 2) = 0;
  }
  else
  {
    v39 = 0;
  }
  v71 = v39;
  if ( !v39 )
    goto LABEL_135;
  LOBYTE(v61) = 6;
  v40 = (_OWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**((_QWORD **)v38 + 1) + 80LL))(
                    *((_QWORD *)v38 + 1),
                    48,
                    "sql\\common\\dk\\xe\\xeeng\\xeeng.cpp",
                    702,
                    v61);
  v41 = v40;
  v67 = (struct SOSHost_MemObj *)v40;
  if ( v40 )
  {
    *v40 = 0;
    v40[1] = 0;
    v40[2] = 0;
    *(_DWORD *)v40 = 1;
    v42 = (_QWORD *)v40 + 1;
    v42[1] = v42;
    *v42 = v42;
    v41[4] = v41 + 3;
    v41[3] = v41 + 3;
    v41[5] = 0;
  }
  else
  {
    v41 = 0;
  }
  *((_QWORD *)v39 + 2) = v41;
  if ( !v41 )
  {
LABEL_135:
    if ( v39 )
      (*(void (__fastcall **)(struct SOSClient_MemoryNotificationCallback *))(*(_QWORD *)v39 + 8LL))(v39);
    XE_Engine::sm_pMemoryNotification = 0;
    goto LABEL_138;
  }
  v71 = 0;
  XE_Engine::sm_pMemoryNotification = v39;
  LOBYTE(v62) = 6;
  v43 = (struct XE_FeatureSwitches *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(**((_QWORD **)XE_Engine::sm_pmo + 1) + 80LL))(
                                       *((_QWORD *)XE_Engine::sm_pmo + 1),
                                       72,
                                       "sql\\common\\dk\\xe\\xeeng\\xeeng.cpp",
                                       3378,
                                       v62);
  v44 = v43;
  v64 = v43;
  if ( v43 )
  {
    *(_QWORD *)v43 = &XE_FeatureSwitches::`vftable'{for `XE_IFeatureSwitchesAccessor'};
    *((_QWORD *)v43 + 1) = &XE_FeatureSwitches::`vftable'{for `XE_IFeatureSwitches'};
    *((_QWORD *)v43 + 2) = &XE_FeatureSwitches::`vftable'{for `XE_IFeatureSwitchesObservable'};
    *((_QWORD *)v43 + 3) = 0;
    *((_QWORD *)v43 + 4) = 0;
    qword_100714F40((char *)v43 + 24);
    *((_QWORD *)v44 + 5) = 0;
    *((_QWORD *)v44 + 6) = 0;
    *((_QWORD *)v44 + 7) = 0;
    *((_QWORD *)v44 + 8) = 0;
  }
  else
  {
    v44 = 0;
  }
  XE_Engine::sm_pFeatureSwitchImpl = v44;
  if ( !v44 )
  {
LABEL_138:
    XE_Engine::FinalizeInternal();
    XE_Tls::SetLastError(v5, 1u, 0);
    goto LABEL_139;
  }
  Base_PublicGlobals::sm_invariantTscAvailable = XE_Engine::IsInvariantTscAvailable();
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    if ( !Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart )
    {
      Frequency.QuadPart = 0;
      QueryPerformanceFrequency(&Frequency);
      Base_PublicGlobals::sm_QueryPerformanceFrequency = Frequency;
    }
    v45 = 0;
    do
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      do
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&PerformanceCount);
          v46 = PerformanceCount;
        }
        else
        {
          v46.QuadPart = MEMORY[0x7FFE0008];
        }
        GetSystemTimeAsFileTime(&v70);
      }
      while ( SystemTimeAsFileTime == v70 );
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v74);
        v47 = v74;
      }
      else
      {
        v47.QuadPart = MEMORY[0x7FFE0008];
      }
      ++v45;
    }
    while ( (unsigned __int64)(v46.QuadPart + 100000) < v47.QuadPart && v45 <= 0xA );
    v48 = v70;
  }
  else
  {
    do
    {
      GetSystemTimeAsFileTime(&v77);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v75);
        v47 = v75;
      }
      else
      {
        v47.QuadPart = MEMORY[0x7FFE0008];
      }
      GetSystemTimeAsFileTime(&v78);
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v76);
        v49 = v76;
      }
      else
      {
        v49.QuadPart = MEMORY[0x7FFE0008];
      }
      v48 = v77;
    }
    while ( v77 != v78 || v47.QuadPart != v49.QuadPart );
  }
  XE_Engine::sm_ticksConfig = 1;
  v50.QuadPart = 0;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v50 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
  qword_100720FD8 = v50.QuadPart;
  v79 = XE_Engine::sm_ticksConfig;
  QuadPart = v50.QuadPart;
  v80 = v50.QuadPart;
  v52 = 0;
  v53 = _mm_cvtsi128_si32(XE_Engine::sm_ticksConfig);
  if ( v53 == 1 )
  {
    if ( v80 )
    {
      if ( v80 < 0 )
        v54 = (double)(int)(v80 & 1 | ((unsigned __int64)v80 >> 1))
            + (double)(int)(v80 & 1 | ((unsigned __int64)v80 >> 1));
      else
        v54 = (double)(int)v80;
      v52 = *((_QWORD *)&v79 + 1) + (unsigned int)(int)((double)(int)v47.LowPart * (10000000.0 / v54));
      goto LABEL_128;
    }
    goto LABEL_127;
  }
  if ( !v53 )
LABEL_127:
    v52 = v47.QuadPart + *((_QWORD *)&v79 + 1);
LABEL_128:
  *(&XE_Engine::sm_ticksConfig + 1) = *(_QWORD *)&v48 - v52;
  XE_Engine::sm_ticksUtil = XE_Engine::sm_ticksConfig;
  qword_1007BB6C8 = QuadPart;
  XE_Engine::sm_diagLevel = 0;
  XE_Engine::sm_customizationFlags = 0;
  if ( (qword_1007B23C8 & 0x10) != 0
    && (int)SOSHost_MemoryClerk::SetMemoryNotificationCallback(
              XE_Engine::sm_memClerk,
              XE_Engine::sm_pMemoryNotification) < 0 )
  {
    goto LABEL_138;
  }
  XE_Engine::sm_noTlsRecordError = 0x1000000;
  dword_1007B23FC = 655368;
  word_1007B2400 = 17;
  qword_1007B2408 = 0;
  v2 = XE_PackageManager::StaticInit();
  if ( !v2 )
    goto LABEL_138;
  XE_Timer::Add(XE_Engine::sm_pTimer, (struct XE_ITimerEntry *)&XE_Engine::sm_timerEntry);
  dword_1007705A8 = 1;
  v87[0] = 0;
  v88 = XEPackage0_GUID;
  v89 = 1879048192;
  v90 = 0;
  if ( qword_100715148 && qword_100714EC8 && qword_100720EC8 )
    qword_100715030(v87);
  do
  {
LABEL_139:
    v56 = XE_Engine::sm_initializer;
    v55 = v56 == _InterlockedCompareExchange(
                   (volatile signed __int32 *)&XE_Engine::sm_initializer,
                   XE_Engine::sm_initializer & 0x7FFFFFFF,
                   XE_Engine::sm_initializer);
    _mm_pause();
  }
  while ( !v55 );
  v64 = (struct SOSHost_MemObj *)&v82;
  v67 = (struct SOSHost_MemObj *)v84;
  if ( v84[0] )
  {
    if ( v84[1] )
      *(_DWORD *)(v85 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v85 + 608) + 16LL))(
        *(_QWORD *)(v85 + 608),
        v85,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)v86);
  *(_DWORD *)(v83 + 616) &= ~v82;
  return v2;
}

```

## disassembly

```asm
0x1005e3c00  mov     rax, rsp
0x1005e3c03  push    rbp
0x1005e3c04  push    r12
0x1005e3c06  push    r13
0x1005e3c08  push    r14
0x1005e3c0a  push    r15
0x1005e3c0c  lea     rbp, [rax-0F8h]
0x1005e3c13  sub     rsp, 1D0h
0x1005e3c1a  mov     [rbp+0F0h+var_120], 0FFFFFFFFFFFFFFFEh
0x1005e3c22  mov     [rax+8], rbx
0x1005e3c26  mov     [rax+10h], rsi
0x1005e3c2a  mov     [rax+18h], rdi
0x1005e3c2e  mov     rax, cs:__security_cookie
0x1005e3c35  xor     rax, rsp
0x1005e3c38  mov     [rbp+0F0h+var_30], rax
0x1005e3c3f  mov     rbx, rcx
0x1005e3c42  mov     r12d, 1
0x1005e3c48  mov     r15d, r12d
0x1005e3c4b  mov     r8d, r12d
0x1005e3c4e  mov     edx, 20000096h
0x1005e3c53  lea     rcx, [rbp+0F0h+var_110]
0x1005e3c57  call    ??0AutoSwitchPreemptive@SOS_Task@@QEAA@W4PWAIT_enum@@H@Z; SOS_Task::AutoSwitchPreemptive::AutoSwitchPreemptive(PWAIT_enum,int)
0x1005e3c5c  nop     dword ptr [rax+00h]
0x1005e3c60  mov     edx, cs:?sm_initializer@XE_Engine@@0VXE_OneTimeInit@@A; XE_OneTimeInit XE_Engine::sm_initializer
0x1005e3c66  lea     ecx, [rdx+1]
0x1005e3c69  test    edx, edx
0x1005e3c6b  js      short loc_1005E3C7F
0x1005e3c6d  or      ecx, 80000000h
0x1005e3c73  mov     eax, edx
0x1005e3c75  lock cmpxchg cs:?sm_initializer@XE_Engine@@0VXE_OneTimeInit@@A, ecx; XE_OneTimeInit XE_Engine::sm_initializer
0x1005e3c7d  mov     ecx, eax
0x1005e3c7f  pause
0x1005e3c81  cmp     ecx, edx
0x1005e3c83  jnz     short loc_1005E3C60
0x1005e3c85  test    ecx, ecx
0x1005e3c87  jnz     loc_1005E46E0
0x1005e3c8d  xor     esi, esi
0x1005e3c8f  lea     r13d, [rcx+0Ah]
0x1005e3c93  cmp     cs:qword_100715148, rsi
0x1005e3c9a  jz      short loc_1005E3CAE
0x1005e3c9c  cmp     cs:qword_100714EC8, rsi
0x1005e3ca3  jz      short loc_1005E3CAE
0x1005e3ca5  cmp     cs:qword_100720EC8, rsi
0x1005e3cac  jnz     short loc_1005E3CDF
0x1005e3cae  mov     dword ptr [rsp+1F0h+var_1A8], 0A000Ah
0x1005e3cb6  mov     [rsp+1F0h+var_1A4], 140012h
0x1005e3cbe  mov     word ptr [rsp+1F0h+var_1A0], r13w
0x1005e3cc4  lea     rdx, [rsp+1F0h+var_1A8]; struct XEEngineVersion *
0x1005e3cc9  xor     ecx, ecx; enum XEGetAPIResult (__high *)(struct XEEngineAPISet *, enum XEGetAPIOption)
0x1005e3ccb  call    ?Initialize@XE_API@@SAHP6A?AW4XEGetAPIResult@@PEAUXEEngineAPISet@@W4XEGetAPIOption@@@ZAEBUXEEngineVersion@@@Z; XE_API::Initialize(XEGetAPIResult (*)(XEEngineAPISet *,XEGetAPIOption),XEEngineVersion const &)
0x1005e3cd0  mov     r15d, eax
0x1005e3cd3  test    eax, eax
0x1005e3cd5  jnz     short loc_1005E3CDF
0x1005e3cd7  lea     esi, [rax+6]
0x1005e3cda  jmp     loc_1005E46CD
0x1005e3cdf  mov     r15d, esi
0x1005e3ce2  lea     rax, ?Initialize@XE_Engine@@SAHQEBUXEHostProperties@@@Z; XE_Engine::Initialize(XEHostProperties const * const)
0x1005e3ce9  cmp     cs:qword_100715160, rax
0x1005e3cf0  jz      short loc_1005E3CFC
0x1005e3cf2  mov     esi, 9
0x1005e3cf7  jmp     loc_1005E46CD
0x1005e3cfc  test    rbx, rbx
0x1005e3cff  jz      loc_1005E3F12
0x1005e3d05  movzx   eax, word ptr [rbx]
0x1005e3d08  test    ax, ax
0x1005e3d0b  jz      loc_1005E3EE6
0x1005e3d11  cmp     ax, r13w
0x1005e3d15  jnz     loc_1005E3F12
0x1005e3d1b  lea     rcx, ?sm_hostProperties@XE_Engine@@0UXEHostProperties@@A; XEHostProperties XE_Engine::sm_hostProperties
0x1005e3d22  movups  xmm0, xmmword ptr [rbx]
0x1005e3d25  movups  xmmword ptr [rcx], xmm0
0x1005e3d28  movups  xmm1, xmmword ptr [rbx+10h]
0x1005e3d2c  movups  xmmword ptr [rcx+10h], xmm1
0x1005e3d30  movups  xmm0, xmmword ptr [rbx+20h]
0x1005e3d34  movups  xmmword ptr [rcx+20h], xmm0
0x1005e3d38  movups  xmm1, xmmword ptr [rbx+30h]
0x1005e3d3c  movups  xmmword ptr [rcx+30h], xmm1
0x1005e3d40  movups  xmm0, xmmword ptr [rbx+40h]
0x1005e3d44  movups  xmmword ptr [rcx+40h], xmm0
0x1005e3d48  movups  xmm1, xmmword ptr [rbx+50h]
0x1005e3d4c  movups  xmmword ptr [rcx+50h], xmm1
0x1005e3d50  movups  xmm0, xmmword ptr [rbx+60h]
0x1005e3d54  movups  xmmword ptr [rcx+60h], xmm0
0x1005e3d58  lea     rcx, [rcx+80h]
0x1005e3d5f  movups  xmm0, xmmword ptr [rbx+70h]
0x1005e3d63  movups  xmmword ptr [rcx-10h], xmm0
0x1005e3d67  sub     rbx, 0FFFFFFFFFFFFFF80h
0x1005e3d6b  movups  xmm1, xmmword ptr [rbx]
0x1005e3d6e  movups  xmmword ptr [rcx], xmm1
0x1005e3d71  movups  xmm0, xmmword ptr [rbx+10h]
0x1005e3d75  movups  xmmword ptr [rcx+10h], xmm0
0x1005e3d79  movups  xmm1, xmmword ptr [rbx+20h]
0x1005e3d7d  movups  xmmword ptr [rcx+20h], xmm1
0x1005e3d81  movups  xmm0, xmmword ptr [rbx+30h]
0x1005e3d85  movups  xmmword ptr [rcx+30h], xmm0
0x1005e3d89  movups  xmm1, xmmword ptr [rbx+40h]
0x1005e3d8d  movups  xmmword ptr [rcx+40h], xmm1
0x1005e3d91  movups  xmm0, xmmword ptr [rbx+50h]
0x1005e3d95  movups  xmmword ptr [rcx+50h], xmm0
0x1005e3d99  mov     rax, [rbx+60h]
0x1005e3d9d  mov     [rcx+60h], rax
0x1005e3da1  mov     rax, cs:qword_1007BB710
0x1005e3da8  test    rax, rax
0x1005e3dab  cmovz   rax, cs:qword_10078FB40
0x1005e3db3  mov     cs:qword_1007BB710, rax
0x1005e3dba  mov     rax, cs:qword_1007BB718
0x1005e3dc1  test    rax, rax
0x1005e3dc4  cmovz   rax, cs:off_10078FB48
0x1005e3dcc  mov     cs:qword_1007BB718, rax
0x1005e3dd3  mov     rax, cs:qword_1007BB760
0x1005e3dda  test    rax, rax
0x1005e3ddd  cmovz   rax, cs:off_10078FB90
0x1005e3de5  mov     cs:qword_1007BB760, rax
0x1005e3dec  mov     rax, cs:qword_1007BB768
0x1005e3df3  test    rax, rax
0x1005e3df6  cmovz   rax, cs:off_10078FB98
0x1005e3dfe  mov     cs:qword_1007BB768, rax
0x1005e3e05  mov     rax, cs:qword_1007BB770
0x1005e3e0c  test    rax, rax
0x1005e3e0f  cmovz   rax, cs:off_10078FBA0
0x1005e3e17  mov     cs:qword_1007BB770, rax
0x1005e3e1e  mov     rax, cs:qword_1007BB778
0x1005e3e25  test    rax, rax
0x1005e3e28  cmovz   rax, cs:off_10078FBA8
0x1005e3e30  mov     cs:qword_1007BB778, rax
0x1005e3e37  mov     rax, cs:qword_1007BB780
0x1005e3e3e  test    rax, rax
0x1005e3e41  cmovz   rax, cs:off_10078FBB0
0x1005e3e49  mov     cs:qword_1007BB780, rax
0x1005e3e50  mov     rax, cs:qword_1007BB788
0x1005e3e57  test    rax, rax
0x1005e3e5a  cmovz   rax, cs:off_10078FBB8
0x1005e3e62  mov     cs:qword_1007BB788, rax
0x1005e3e69  mov     rax, cs:qword_1007BB790
0x1005e3e70  test    rax, rax
0x1005e3e73  cmovz   rax, cs:off_10078FBC0
0x1005e3e7b  mov     cs:qword_1007BB790, rax
0x1005e3e82  mov     rax, cs:qword_1007BB798
0x1005e3e89  test    rax, rax
0x1005e3e8c  cmovz   rax, cs:off_10078FBC8
0x1005e3e94  mov     cs:qword_1007BB798, rax
0x1005e3e9b  mov     rax, cs:qword_1007BB708
0x1005e3ea2  test    rax, rax
0x1005e3ea5  cmovz   rax, cs:off_10078FB38
0x1005e3ead  mov     cs:qword_1007BB708, rax
0x1005e3eb4  mov     rax, cs:qword_1007BB6F8
0x1005e3ebb  test    rax, rax
0x1005e3ebe  cmovz   rax, cs:off_10078FB28
0x1005e3ec6  mov     cs:qword_1007BB6F8, rax
0x1005e3ecd  cmp     cs:qword_1007BB7A0, rsi
0x1005e3ed4  jnz     short loc_1005E3F12
0x1005e3ed6  mov     rax, cs:off_10078FBD0
0x1005e3edd  mov     cs:qword_1007BB7A0, rax
0x1005e3ee4  jmp     short loc_1005E3F12
0x1005e3ee6  mov     rax, [rbx+8]
0x1005e3eea  mov     cs:qword_1007BB6E8, rax
0x1005e3ef1  mov     rax, [rbx+10h]
0x1005e3ef5  mov     cs:qword_1007BB6F0, rax
0x1005e3efc  mov     rax, [rbx+18h]
0x1005e3f00  mov     cs:qword_1007BB6F8, rax
0x1005e3f07  mov     rax, [rbx+20h]
0x1005e3f0b  mov     cs:qword_1007BB700, rax
0x1005e3f12  lea     rcx, off_10078FC40
0x1005e3f19  mov     cs:?sm_pObjectFactory@XE_Engine@@0PEAVXE_EngineObjectFactory@@EA, rcx; XE_EngineObjectFactory * XE_Engine::sm_pObjectFactory
0x1005e3f20  mov     rax, cs:off_10078FC40
0x1005e3f27  call    qword ptr [rax+20h]
0x1005e3f2a  mov     cs:?sm_pInstance@XE_DumpCallbacks@@0PEAV1@EA, rax; XE_DumpCallbacks * XE_DumpCallbacks::sm_pInstance
0x1005e3f31  mov     [rsp+1F0h+var_1B8], rsi
0x1005e3f36  mov     [rsp+1F0h+var_1B8], rsi
0x1005e3f3b  xor     ecx, ecx; lpModuleName
0x1005e3f3d  call    cs:__imp_GetModuleHandleW
0x1005e3f43  test    rax, rax
0x1005e3f46  jz      short loc_1005E3F66
0x1005e3f48  lea     rdx, aDmpgetclientex; "DmpGetClientExport"
0x1005e3f4f  mov     rcx, rax; hModule
0x1005e3f52  call    cs:__imp_GetProcAddress
0x1005e3f58  test    rax, rax
0x1005e3f5b  jz      short loc_1005E3F66
0x1005e3f5d  lea     rcx, [rsp+1F0h+var_1B8]
0x1005e3f62  call    rax
0x1005e3f64  jmp     short loc_1005E3F78
0x1005e3f66  call    cs:__imp_GetLastError
0x1005e3f6c  test    eax, eax
0x1005e3f6e  jle     short loc_1005E3F7A
0x1005e3f70  movzx   eax, ax
0x1005e3f73  or      eax, 80070000h
0x1005e3f78  test    eax, eax
0x1005e3f7a  js      short loc_1005E3FAA
0x1005e3f7c  mov     rcx, [rsp+1F0h+var_1B8]
0x1005e3f81  mov     rax, [rcx]
0x1005e3f84  lea     r8, ?sm_dumpCallbackCookie@XE_DumpCallbacks@@0PEAUDMP_CLIENT_CALLBACK_COOKIE__@@EA; DMP_CLIENT_CALLBACK_COOKIE__ * XE_DumpCallbacks::sm_dumpCallbackCookie
0x1005e3f8b  mov     rdx, cs:?sm_pInstance@XE_DumpCallbacks@@0PEAV1@EA; XE_DumpCallbacks * XE_DumpCallbacks::sm_pInstance
0x1005e3f92  call    qword ptr [rax+38h]
0x1005e3f95  test    eax, eax
0x1005e3f97  js      short loc_1005E3FAA
0x1005e3f99  mov     rax, [rsp+1F0h+var_1B8]
0x1005e3f9e  mov     [rsp+1F0h+var_1B8], rsi
0x1005e3fa3  mov     cs:?sm_pDumpClient@XE_DumpCallbacks@@0PEAUIDmpClient@@EA, rax; IDmpClient * XE_DumpCallbacks::sm_pDumpClient
0x1005e3faa  mov     rcx, [rsp+1F0h+var_1B8]
0x1005e3faf  test    rcx, rcx
0x1005e3fb2  jz      short loc_1005E3FBA
0x1005e3fb4  mov     rax, [rcx]
0x1005e3fb7  call    qword ptr [rax+10h]
0x1005e3fba  call    ?GetPmo@SOS_Node@@SAPEAVIMemObj@@XZ; SOS_Node::GetPmo(void)
0x1005e3fbf  lea     rcx, ?sm_pHost@XE_Engine@@0PEAVSOSHost@@EA; SOSHost * XE_Engine::sm_pHost
0x1005e3fc6  mov     qword ptr [rsp+1F0h+var_1D0], rcx
0x1005e3fcb  lea     r9, aXeHost; "XE_Host"
0x1005e3fd2  mov     r8d, 43h ; 'C'
0x1005e3fd8  mov     rdx, rax
0x1005e3fdb  lea     rcx, ?sm_HostManager@SOS_PublicGlobals@@2VHostManager@@A; HostManager SOS_PublicGlobals::sm_HostManager
0x1005e3fe2  call    ?CreateSOSHostObject@HostManager@@AEAA?AW4SOS_RESULT@@PEAVIMemObj@@W4SOSHOST_CLIENTID@@PEB_WPEAPEAVSOSHost@@@Z; HostManager::CreateSOSHostObject(IMemObj *,SOSHOST_CLIENTID,wchar_t const *,SOSHost * *)
0x1005e3fe7  mov     ecx, eax
0x1005e3fe9  call    ?HRESULT_FROM_SOS_RESULT@@YAJW4SOS_RESULT@@@Z; HRESULT_FROM_SOS_RESULT(SOS_RESULT)
0x1005e3fee  test    eax, eax
0x1005e3ff0  js      loc_1005E46CD
0x1005e3ff6  mov     cs:?sm_hostVersion@XE_Engine@@0USOSHost_VersionInfo@@A, r12d; SOSHost_VersionInfo XE_Engine::sm_hostVersion
0x1005e3ffd  mov     cs:qword_1007B23C8, 7Fh
0x1005e4008  mov     cs:qword_1007B23D0, 3FFh
0x1005e4013  call    ?InitializeMemorySubsystem@XE_Engine@@CAHXZ; XE_Engine::InitializeMemorySubsystem(void)
0x1005e4018  test    eax, eax
0x1005e401a  jz      loc_1005E46CD
0x1005e4020  mov     rdi, cs:?sm_pmo@XE_Engine@@0PEAVSOSHost_MemObj@@EA; SOSHost_MemObj * XE_Engine::sm_pmo
0x1005e4027  mov     [rsp+1F0h+var_198], rdi
0x1005e402c  mov     r14d, esi
0x1005e402f  mov     rbx, rsi
0x1005e4032  mov     [rsp+1F0h+var_190], rbx
0x1005e4037  mov     eax, esi
0x1005e4039  mov     ecx, cs:?sm_WorkerType@SOS_PublicGlobals@@2W4WORKER_TYPE@@A; WORKER_TYPE SOS_PublicGlobals::sm_WorkerType
0x1005e403f  test    ecx, ecx
0x1005e4041  setz    al
0x1005e4044  mov     cs:?sm_useFibers@XE_Tls@@0HA, eax; int XE_Tls::sm_useFibers
0x1005e404a  test    ecx, ecx
0x1005e404c  jnz     short loc_1005E4079
0x1005e404e  mov     rax, cs:__imp_FlsGetValue
0x1005e4055  mov     cs:?sm_XlsGetValue@XE_Tls@@0P6APEAXK@ZEA, rax; void * (*XE_Tls::sm_XlsGetValue)(ulong)
0x1005e405c  mov     rax, cs:__imp_FlsSetValue
0x1005e4063  mov     cs:?sm_XlsSetValue@XE_Tls@@0P6AHKPEAX@ZEA, rax; int (*XE_Tls::sm_XlsSetValue)(ulong,void *)
0x1005e406a  lea     rcx, ?FlsCallback@XE_Tls@@CAXPEAX@Z; lpCallback
0x1005e4071  call    cs:__imp_FlsAlloc
0x1005e4077  jmp     short loc_1005E407F
0x1005e4079  call    cs:__imp_TlsAlloc
0x1005e407f  cmp     eax, 0FFFFFFFFh
0x1005e4082  jz      loc_1005E4127
0x1005e4088  mov     cs:?sm_tlsSlot@XE_Tls@@0IA, eax; uint XE_Tls::sm_tlsSlot
0x1005e408e  call    ?BlockAllocate@XE_TlsRecordBlock@@SAPEAV1@XZ; XE_TlsRecordBlock::BlockAllocate(void)
0x1005e4093  test    rax, rax
0x1005e4096  jz      loc_1005E4127
0x1005e409c  mov     cs:?sm_pBlocks@XE_Tls@@0PAPEAVXE_TlsRecordBlock@@A, rax; XE_TlsRecordBlock * near * XE_Tls::sm_pBlocks
0x1005e40a3  mov     dword ptr [rsp+1F0h+var_1C0], 126h
0x1005e40ab  mov     rcx, [rdi+8]
0x1005e40af  mov     rax, [rcx]
0x1005e40b2  mov     byte ptr [rsp+1F0h+var_1D0], 6
0x1005e40b7  mov     r9d, 126h
0x1005e40bd  lea     r8, aSqlCommonDkXeX_8; "sql\\common\\dk\\xe\\xeeng\\xeeng.cpp"
0x1005e40c4  mov     edx, 30h ; '0'
0x1005e40c9  call    qword ptr [rax+50h]
0x1005e40cc  mov     [rsp+1F0h+var_1B0], rax
0x1005e40d1  test    rax, rax
0x1005e40d4  jz      short loc_1005E40F6
0x1005e40d6  mov     [rax], rsi
0x1005e40d9  mov     [rax+8], rsi
0x1005e40dd  mov     [rax+10h], r12d
0x1005e40e1  mov     [rax+18h], rsi
0x1005e40e5  mov     [rax+20h], rsi
0x1005e40e9  lea     rcx, ?ThreadCreateDestroyCallback@XE_Tls@@CAXK@Z; XE_Tls::ThreadCreateDestroyCallback(ulong)
0x1005e40f0  mov     [rax+28h], rcx
0x1005e40f4  jmp     short loc_1005E40F9
0x1005e40f6  mov     rax, rsi
0x1005e40f9  mov     rbx, rax
0x1005e40fc  mov     [rsp+1F0h+var_190], rax
0x1005e4101  test    rax, rax
0x1005e4104  jz      short loc_1005E4127
0x1005e4106  mov     rbx, rsi
0x1005e4109  mov     [rsp+1F0h+var_190], rbx
0x1005e410e  mov     cs:?sm_cbo@XE_Tls@@0PEAVSOSHost_OSThreadCreateDestroyCallback@@EA, rax; SOSHost_OSThreadCreateDestroyCallback * XE_Tls::sm_cbo
0x1005e4115  mov     rdx, rax
0x1005e4118  lea     rcx, ?sm_OSThreadCreateDestroyCallbackList@SOS_OS@@2V?$TBaseSafeCallbackList@V?$TBaseSafeCallback@XUTListSLock@@VSOSCallbackEvent@@KVNullType@@V3@V3@@@@@A; TBaseSafeCallbackList<TBaseSafeCallback<void,TListSLock,SOSCallbackEvent,ulong,NullType,NullType,NullType>> SOS_OS::sm_OSThreadCreateDestroyCallbackList
0x1005e411f  call    ?Insert@?$XList@VElem@?$BaseSafeCallbackTraits@V?$TBaseSafeCallbackWithParam@XUTListSLock@@VSOSCallbackEvent@@PEAXAEBVSystemAffinity@@AEBV3@VNullType@@@@UTListSLock@@VSOSCallbackEvent@@@@@@QEAAXQEAVElem@?$BaseSafeCallbackTraits@V?$TBaseSafeCallbackWithParam@XUTListSLock@@VSOSCallbackEvent@@PEAXAEBVSystemAffinity@@AEBV3@VNullType@@@@UTListSLock@@VSOSCallbackEvent@@@@@Z; XList<BaseSafeCallbackTraits<TBaseSafeCallbackWithParam<void,TListSLock,SOSCallbackEvent,void *,SystemAffinity const &,SystemAffinity const &,NullType>,TListSLock,SOSCallbackEvent>::Elem>::Insert(BaseSafeCallbackTraits<TBaseSafeCallbackWithParam<void,TListSLock,SOSCallbackEvent,void *,SystemAffinity const &,SystemAffinity const &,NullType>,TListSLock,SOSCallbackEvent>::Elem * const)
0x1005e4124  mov     r14d, r12d
0x1005e4127  mov     [rsp+1F0h+var_1B0], rbx
0x1005e412c  test    rbx, rbx
0x1005e412f  jz      short loc_1005E414D
0x1005e4131  cmp     qword ptr [rbx+18h], 0
0x1005e4136  jz      short loc_1005E4140
0x1005e4138  mov     rcx, rbx
0x1005e413b  call    ?RemoveSelf@Elem@?$BaseSafeCallbackTraits@V?$TBaseSafeCallbackWithParam@XUTListSLock@@VSOSCallbackEvent@@PEAXPEAVSOS_Node@@_K_K@@UTListSLock@@VSOSCallbackEvent@@@@QEAAXXZ; BaseSafeCallbackTraits<TBaseSafeCallbackWithParam<void,TListSLock,SOSCallbackEvent,void *,SOS_Node *,unsigned __int64,unsigned __int64>,TListSLock,SOSCallbackEvent>::Elem::RemoveSelf(void)
0x1005e4140  mov     edx, 30h ; '0'; unsigned __int64
0x1005e4145  mov     rcx, rbx; void *
0x1005e4148  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1005e414d  test    r14d, r14d
0x1005e4150  jz      loc_1005E46CD
0x1005e4156  mov     rcx, cs:?sm_pmo@XE_Engine@@0PEAVSOSHost_MemObj@@EA; struct SOSHost_MemObj *
0x1005e415d  call    ?Create@XE_Timer@@SAPEAV1@PEAVSOSHost_MemObj@@@Z; XE_Timer::Create(SOSHost_MemObj *)
0x1005e4162  mov     cs:?sm_pTimer@XE_Engine@@0PEAVXE_Timer@@EA, rax; XE_Timer * XE_Engine::sm_pTimer
0x1005e4169  test    rax, rax
0x1005e416c  jz      loc_1005E46CD
0x1005e4172  mov     dword ptr [rsp+1F0h+var_1C0], 0D20h
0x1005e417a  mov     rax, cs:?sm_pmo@XE_Engine@@0PEAVSOSHost_MemObj@@EA; SOSHost_MemObj * XE_Engine::sm_pmo
0x1005e4181  mov     rcx, [rax+8]
0x1005e4185  mov     rax, [rcx]
  ... truncated ...
```
