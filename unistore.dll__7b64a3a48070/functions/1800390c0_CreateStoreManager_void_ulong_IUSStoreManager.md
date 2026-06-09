# _CreateStoreManager(void *,ulong,IUSStoreManager * *)

- ea: `0x1800390c0`
- end: `0x180039681`
- name: `?_CreateStoreManager@@YAJPEAXKPEAPEAUIUSStoreManager@@@Z`
- size: `1473`
- prototype: `int(void *, unsigned int, struct IUSStoreManager **)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038d70`
- `0x180038fd0`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180023f9c`
- `0x180024220`
- `0x180038c30`
- `0x1800390c0`
- `0x1800396c8`
- `0x180039898`
- `0x180043cdc`
- `0x18006807c`
- `0x18006fee0`
- `0x18007007c`
- `0x180072db4`
- `0x180075a3c`
- `0x18007cc6c`
- `0x18007d134`
- `0x1800aaeb0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800390f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003927b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800390f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003927b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039106`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800392c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039501`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039595`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039106`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800392c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039501`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003948d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003948d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039198`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180039198`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800391b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800391b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800391c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800391c3`
- `UserDataPlatformHelperUtil!StartAndWaitForService` at `0x18003932b`
- `UserDataPlatformHelperUtil!StartAndWaitForService` at `0x18003932b`

## string_xrefs

- `0x180039116`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180039147`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x1800391f0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180039209`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x1800392d6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180039447`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x1800394d1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x18003951f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180039572`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180039615`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x18003964c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\createstore.cpp`
- `0x180039191`: `unistore.dll`
- `0x180039633`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.h`

## pseudocode

```c
__int64 __fastcall _CreateStoreManager(void *a1, int a2, struct IUSStoreManager **a3)
{
  int v5; // ebx
  __int64 v7; // r9
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  void *v12; // rax
  int InprocStoreManager; // ebx
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  int Rpc; // eax
  int v18; // eax
  CUSClient_ServerManager *v19; // rbx
  struct __MIDL_UnistoreService_0001 *v20; // rsi
  struct __MIDL_UnistoreService_0001 *v21; // rcx
  int v22; // eax
  unsigned int v23; // esi
  signed int v24; // eax
  signed int LastError; // eax
  __int64 v26; // rcx
  int BindingHandle; // ebx
  __int64 v28; // r9
  __int64 v29; // rcx
  __int128 v30; // [rsp+30h] [rbp-30h] BYREF
  CUSClient_ServerManager *p_Binding; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v32[24]; // [rsp+48h] [rbp-18h] BYREF
  void *v33; // [rsp+80h] [rbp+20h] BYREF
  unsigned int v34; // [rsp+88h] [rbp+28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+38h] BYREF

  v33 = a1;
  if ( g_fForceInproc )
    g_fInProc = 1;
  EnterCriticalSection(&g_csShutdownLock);
  v5 = g_serviceShuttingDown;
  LeaveCriticalSection(&g_csShutdownLock);
  if ( v5 )
  {
    Log_UnistoreHREvent_0(
      2147943515LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      144);
    return 2147943515LL;
  }
  if ( g_fInProc )
  {
    if ( !g_fForceInproc )
      g_RundownProtectionId = -2;
    ModuleHandleW = GetModuleHandleW(L"unistore.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "GetRealStoreManager");
      if ( ProcAddress )
      {
        LODWORD(Binding) = GetCurrentProcessId();
        if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
        {
          v12 = _t_address();
          EtwTraceMessage(&ETWMESSAGE, v12, &Binding, 4, 0, -1);
        }
        v10 = ((__int64 (__fastcall *)(struct IUSStoreManager **))ProcAddress)(a3);
        v11 = v10;
        if ( v10 < 0 )
        {
          Log_UnistoreHREvent_0(
            (unsigned int)v10,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
            131);
          goto LABEL_17;
        }
        return 0;
      }
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v7 = 126;
    }
    else
    {
      v24 = GetLastError();
      v11 = v24;
      if ( v24 > 0 )
        v11 = (unsigned __int16)v24 | 0x80070000;
      v7 = 123;
    }
    Log_UnistoreHREvent_0(
      v11,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      v7);
    if ( (v11 & 0x80000000) != 0 )
    {
LABEL_17:
      Log_UnistoreHREvent_0(
        v11,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
        148);
      return v11;
    }
    return 0;
  }
  v34 = a2 & 0xFFFFFFFE;
  if ( (a2 & 0xFFFFFFFE) != 0 )
  {
    Log_UnistoreHREvent_0(
      2147942487LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      161);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    Log_UnistoreHREvent_0(
      2147500035LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      162);
    return 2147500035LL;
  }
  EnterCriticalSection(&g_storeManagerLock);
  if ( !::Binding )
  {
    if ( g_fInProc )
      goto LABEL_30;
    InprocStoreManager = StartAndWaitForService(L"UnistoreSvc", 0, 30000, 0, 0, 0);
    if ( InprocStoreManager < 0 )
    {
      v14 = 176;
LABEL_45:
      Log_UnistoreHREvent_0(
        (unsigned int)InprocStoreManager,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
        v14);
LABEL_46:
      LeaveCriticalSection(&g_storeManagerLock);
      return (unsigned int)InprocStoreManager;
    }
    if ( g_fInProc )
    {
LABEL_30:
      InprocStoreManager = _CreateInprocStoreManager(a3);
      if ( InprocStoreManager >= 0 )
        goto LABEL_25;
      v14 = 207;
      goto LABEL_45;
    }
    Binding = 0;
    tlx::auto_xxx<void *,void (*)(void *),&void _CloseBinder(void *),0>::_Delete(&Binding);
    Binding = 0;
    BindingHandle = GetBindingHandle(&Binding);
    if ( BindingHandle < 0 )
    {
      v28 = 184;
LABEL_62:
      Log_UnistoreHREvent_0(
        (unsigned int)BindingHandle,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
        v28);
      tlx::auto_xxx<void *,void (*)(void *),&void _CloseBinder(void *),0>::_Delete(&Binding);
      LeaveCriticalSection(&g_storeManagerLock);
      return (unsigned int)BindingHandle;
    }
    if ( !g_RundownProtectionId )
    {
      p_Binding = (CUSClient_ServerManager *)&g_RundownProtectionId;
      BindingHandle = RpcHelper::MakeRpcCall<void *,void *,unsigned long *,tlx::auto_xxx<void *,void (*)(void *),&void _CloseBinder(void *),0> &,void * &,unsigned long *>(
                        v26,
                        &Binding,
                        &v33,
                        &p_Binding);
      if ( BindingHandle < 0 )
      {
        v28 = 192;
        goto LABEL_62;
      }
      if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x4000) != 0 )
        McTemplateU0q_EventWriteTransfer(v29, UnifiedStore_ProcessIdentifierCreated, g_RundownProtectionId);
    }
    ::Binding = Binding;
    Binding = 0;
    UnistoreTelemetry::OutOfProcessConnectionEstablished();
    tlx::auto_xxx<void *,void (*)(void *),&void _CloseBinder(void *),0>::_Delete(&Binding);
  }
  if ( g_fInProc )
    goto LABEL_30;
  if ( g_pCacheUSStoreManager )
  {
    (*(void (__fastcall **)(struct IUSStoreManager *))(*(_QWORD *)g_pCacheUSStoreManager + 8LL))(g_pCacheUSStoreManager);
LABEL_24:
    *a3 = g_pCacheUSStoreManager;
LABEL_25:
    LeaveCriticalSection(&g_storeManagerLock);
    return 0;
  }
  Binding = 0;
  p_Binding = (CUSClient_ServerManager *)&Binding;
  v30 = *(_OWORD *)GetClientThreadInfo(v32);
  Rpc = RpcHelper::MakeRpcCall<void *,_CLIENT_THREAD_INFO,unsigned long,__MIDL_UnistoreService_0001 * *,void * &,_CLIENT_THREAD_INFO,unsigned long &,__MIDL_UnistoreService_0001 * *>(
          v16,
          v15,
          &v30,
          &v34,
          &p_Binding);
  InprocStoreManager = Rpc;
  if ( Rpc < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)Rpc,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      221);
LABEL_48:
    if ( Binding )
      _ObjectCloser((struct __MIDL_UnistoreService_0001 *)Binding);
    goto LABEL_46;
  }
  *(_QWORD *)&v30 = 0;
  if ( Binding )
  {
    p_Binding = 0;
    v18 = ATL::CComObject<CUSClient_ServerManager>::CreateInstance(&p_Binding);
    InprocStoreManager = v18;
    if ( v18 >= 0 )
    {
      v19 = p_Binding;
      if ( p_Binding )
        (*(void (__fastcall **)(CUSClient_ServerManager *))(*(_QWORD *)p_Binding + 8LL))(p_Binding);
      v20 = (struct __MIDL_UnistoreService_0001 *)Binding;
      Binding = 0;
      v21 = (struct __MIDL_UnistoreService_0001 *)*((_QWORD *)v19 + 9);
      if ( v20 != v21 )
      {
        if ( v21 )
          _ObjectCloserAsync(v21);
        *((_QWORD *)v19 + 9) = v20;
      }
      goto LABEL_41;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v18,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\clientobjects.h",
      2053);
    Log_UnistoreHREvent_0(
      (unsigned int)InprocStoreManager,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
      224);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v30);
    goto LABEL_48;
  }
  v19 = 0;
LABEL_41:
  *(_QWORD *)&v30 = v19;
  v22 = CUSClient_ServerManager::Initialize(v19);
  v23 = v22;
  if ( v22 >= 0 )
  {
    g_pCacheUSStoreManager = v19;
    if ( Binding )
      _ObjectCloser((struct __MIDL_UnistoreService_0001 *)Binding);
    goto LABEL_24;
  }
  Log_UnistoreHREvent_0(
    (unsigned int)v22,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\createstore.cpp",
    226);
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v30);
  if ( Binding )
    _ObjectCloser((struct __MIDL_UnistoreService_0001 *)Binding);
  LeaveCriticalSection(&g_storeManagerLock);
  return v23;
}

```

## disassembly

```asm
0x1800390c0  mov     [rsp-18h+arg_10], rbx
0x1800390c5  mov     [rsp-18h+arg_0], rcx
0x1800390ca  push    rbp
0x1800390cb  push    rsi
0x1800390cc  push    rdi
0x1800390cd  mov     rbp, rsp
0x1800390d0  sub     rsp, 60h
0x1800390d4  cmp     cs:?g_fForceInproc@@3HA, 0; int g_fForceInproc
0x1800390db  mov     rdi, r8
0x1800390de  mov     esi, edx
0x1800390e0  jz      short loc_1800390EC
0x1800390e2  mov     cs:?g_fInProc@@3HA, 1; int g_fInProc
0x1800390ec  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800390f3  call    cs:__imp_EnterCriticalSection
0x1800390f9  mov     ebx, cs:?g_serviceShuttingDown@@3HA; int g_serviceShuttingDown
0x1800390ff  lea     rcx, ?g_csShutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180039106  call    cs:__imp_LeaveCriticalSection
0x18003910c  test    ebx, ebx
0x18003910e  jz      short loc_180039171
0x180039110  mov     r9d, 90h
0x180039116  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003911d  mov     edx, 1
0x180039122  mov     ecx, 8007045Bh
0x180039127  call    Log_UnistoreHREvent_0
0x18003912c  mov     eax, 8007045Bh
0x180039131  mov     rbx, [rsp+60h+arg_10]
0x180039139  add     rsp, 60h
0x18003913d  pop     rdi
0x18003913e  pop     rsi
0x18003913f  pop     rbp
0x180039140  retn
0x180039141  mov     r9d, 7Bh ; '{'
0x180039147  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003914e  xor     edx, edx
0x180039150  mov     ecx, ebx
0x180039152  call    Log_UnistoreHREvent_0
0x180039157  test    ebx, ebx
0x180039159  js      loc_180039203
0x18003915f  xor     eax, eax
0x180039161  mov     rbx, [rsp+60h+arg_10]
0x180039169  add     rsp, 60h
0x18003916d  pop     rdi
0x18003916e  pop     rsi
0x18003916f  pop     rbp
0x180039170  retn
0x180039171  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x180039178  jz      loc_180039263
0x18003917e  cmp     cs:?g_fForceInproc@@3HA, 0; int g_fForceInproc
0x180039185  jnz     short loc_180039191
0x180039187  mov     cs:?g_RundownProtectionId@@3KA, 0FFFFFFFEh; ulong g_RundownProtectionId
0x180039191  lea     rcx, ModuleName; "unistore.dll"
0x180039198  call    cs:__imp_GetModuleHandleW
0x18003919e  test    rax, rax
0x1800391a1  jz      loc_18003948D
0x1800391a7  lea     rdx, ProcName; "GetRealStoreManager"
0x1800391ae  mov     rcx, rax; hModule
0x1800391b1  call    cs:__imp_GetProcAddress
0x1800391b7  mov     rbx, rax
0x1800391ba  test    rax, rax
0x1800391bd  jz      loc_1800394AB
0x1800391c3  call    cs:__imp_GetCurrentProcessId
0x1800391c9  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x1800391d0  mov     dword ptr [rbp+Binding], eax
0x1800391d3  jnz     short loc_18003922E
0x1800391d5  mov     rcx, rdi
0x1800391d8  mov     rax, rbx
0x1800391db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391e0  mov     ebx, eax
0x1800391e2  test    eax, eax
0x1800391e4  jns     loc_18003915F
0x1800391ea  mov     r9d, 83h
0x1800391f0  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800391f7  mov     edx, 1
0x1800391fc  mov     ecx, eax
0x1800391fe  call    Log_UnistoreHREvent_0
0x180039203  mov     r9d, 94h
0x180039209  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180039210  mov     edx, 1
0x180039215  mov     ecx, ebx
0x180039217  call    Log_UnistoreHREvent_0
0x18003921c  mov     eax, ebx
0x18003921e  mov     rbx, [rsp+60h+arg_10]
0x180039226  add     rsp, 60h
0x18003922a  pop     rdi
0x18003922b  pop     rsi
0x18003922c  pop     rbp
0x18003922d  retn
0x18003922e  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180039233  mov     rdx, rax; void *
0x180039236  mov     [rsp+60h+var_38], 0FFFFFFFFFFFFFFFFh
0x18003923f  mov     r9d, 4
0x180039245  mov     [rsp+60h+var_40], 0
0x18003924e  lea     r8, [rbp+Binding]
0x180039252  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180039259  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18003925e  jmp     loc_1800391D5
0x180039263  and     esi, 0FFFFFFFEh
0x180039266  mov     [rbp+arg_8], esi
0x180039269  jnz     loc_180039519
0x18003926f  test    rdi, rdi
0x180039272  jz      short loc_1800392D0
0x180039274  lea     rcx, ?g_storeManagerLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18003927b  call    cs:__imp_EnterCriticalSection
0x180039281  cmp     cs:Binding, 0
0x180039289  jz      short loc_1800392FE
0x18003928b  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x180039292  jnz     loc_180039348
0x180039298  mov     rcx, cs:?g_pCacheUSStoreManager@@3PEAUIUSStoreManager@@EA; IUSStoreManager * g_pCacheUSStoreManager
0x18003929f  test    rcx, rcx
0x1800392a2  jz      loc_180039365
0x1800392a8  mov     rax, [rcx]
0x1800392ab  mov     rax, [rax+8]
0x1800392af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392b4  mov     rax, cs:?g_pCacheUSStoreManager@@3PEAUIUSStoreManager@@EA; IUSStoreManager * g_pCacheUSStoreManager
0x1800392bb  mov     [rdi], rax
0x1800392be  lea     rcx, ?g_storeManagerLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800392c5  call    cs:__imp_LeaveCriticalSection
0x1800392cb  jmp     loc_18003915F
0x1800392d0  mov     r9d, 0A2h
0x1800392d6  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800392dd  xor     edx, edx
0x1800392df  mov     ecx, 80004003h
0x1800392e4  call    Log_UnistoreHREvent_0
0x1800392e9  mov     eax, 80004003h
0x1800392ee  mov     rbx, [rsp+60h+arg_10]
0x1800392f6  add     rsp, 60h
0x1800392fa  pop     rdi
0x1800392fb  pop     rsi
0x1800392fc  pop     rbp
0x1800392fd  retn
0x1800392fe  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x180039305  jnz     short loc_180039348
0x180039307  mov     [rsp+60h+var_38], 0
0x180039310  lea     rcx, aUnistoresvc; "UnistoreSvc"
0x180039317  xor     r9d, r9d
0x18003931a  mov     [rsp+60h+var_40], 0
0x180039323  xor     edx, edx
0x180039325  mov     r8d, 7530h
0x18003932b  call    cs:__imp_StartAndWaitForService
0x180039331  mov     ebx, eax
0x180039333  test    eax, eax
0x180039335  js      loc_180039441
0x18003933b  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x180039342  jz      loc_18003953C
0x180039348  mov     rcx, rdi; struct IUSStoreManager **
0x18003934b  call    ?_CreateInprocStoreManager@@YAJPEAPEAUIUSStoreManager@@@Z; _CreateInprocStoreManager(IUSStoreManager * *)
0x180039350  mov     ebx, eax
0x180039352  test    eax, eax
0x180039354  jns     loc_1800392BE
0x18003935a  mov     r9d, 0CFh
0x180039360  jmp     loc_180039447
0x180039365  lea     rax, [rbp+Binding]
0x180039369  mov     [rbp+Binding], 0
0x180039371  lea     rcx, [rbp+var_18]
0x180039375  mov     [rbp+var_20], rax
0x180039379  call    ?GetClientThreadInfo@@YA?AU_CLIENT_THREAD_INFO@@XZ; GetClientThreadInfo(void)
0x18003937e  lea     r9, [rbp+arg_8]
0x180039382  lea     r8, [rbp+var_30]
0x180039386  movups  xmm0, xmmword ptr [rax]
0x180039389  lea     rax, [rbp+var_20]
0x18003938d  mov     [rsp+60h+var_40], rax
0x180039392  movups  [rbp+var_30], xmm0
0x180039396  call    ??$MakeRpcCall@PEAXU_CLIENT_THREAD_INFO@@KPEAPEAU__MIDL_UnistoreService_0001@@AEAPEAXU1@AEAKPEAPEAU2@@RpcHelper@@YAJP6AJPEAXU_CLIENT_THREAD_INFO@@KPEAPEAU__MIDL_UnistoreService_0001@@@ZAEAPEAX$$QEAU1@AEAK$$QEAPEAPEAU2@@Z; RpcHelper::MakeRpcCall<void *,_CLIENT_THREAD_INFO,ulong,__MIDL_UnistoreService_0001 * *,void * &,_CLIENT_THREAD_INFO,ulong &,__MIDL_UnistoreService_0001 * *>(long (*)(void *,_CLIENT_THREAD_INFO,ulong,__MIDL_UnistoreService_0001 * *),void * &,_CLIENT_THREAD_INFO &&,ulong &,__MIDL_UnistoreService_0001 * * &&)
0x18003939b  mov     ebx, eax
0x18003939d  test    eax, eax
0x18003939f  js      loc_18003960F
0x1800393a5  cmp     [rbp+Binding], 0
0x1800393aa  mov     qword ptr [rbp+var_30], 0
0x1800393b2  jz      loc_180039479
0x1800393b8  lea     rcx, [rbp+var_20]
0x1800393bc  mov     [rbp+var_20], 0
0x1800393c4  call    ?CreateInstance@?$CComObject@VCUSClient_ServerManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUSClient_ServerManager>::CreateInstance(ATL::CComObject<CUSClient_ServerManager> * *)
0x1800393c9  mov     ebx, eax
0x1800393cb  test    eax, eax
0x1800393cd  js      loc_18003962D
0x1800393d3  mov     rbx, [rbp+var_20]
0x1800393d7  test    rbx, rbx
0x1800393da  jz      short loc_1800393EB
0x1800393dc  mov     rax, [rbx]
0x1800393df  mov     rcx, rbx
0x1800393e2  mov     rax, [rax+8]
0x1800393e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393eb  mov     rsi, [rbp+Binding]
0x1800393ef  mov     [rbp+Binding], 0
0x1800393f7  mov     rcx, [rbx+48h]; struct __MIDL_UnistoreService_0001 *
0x1800393fb  cmp     rsi, rcx
0x1800393fe  jz      short loc_18003940D
0x180039400  test    rcx, rcx
0x180039403  jnz     loc_18003966D
0x180039409  mov     [rbx+48h], rsi
0x18003940d  mov     rcx, rbx; this
0x180039410  mov     qword ptr [rbp+var_30], rbx
0x180039414  call    ?Initialize@CUSClient_ServerManager@@QEAAJXZ; CUSClient_ServerManager::Initialize(void)
0x180039419  mov     esi, eax
0x18003941b  test    eax, eax
0x18003941d  js      loc_1800394CB
0x180039423  mov     rcx, [rbp+Binding]; struct __MIDL_UnistoreService_0001 *
0x180039427  mov     cs:?g_pCacheUSStoreManager@@3PEAUIUSStoreManager@@EA, rbx; IUSStoreManager * g_pCacheUSStoreManager
0x18003942e  test    rcx, rcx
0x180039431  jz      loc_1800392B4
0x180039437  call    ?_ObjectCloser@@YAXPEAU__MIDL_UnistoreService_0001@@@Z; _ObjectCloser(__MIDL_UnistoreService_0001 *)
0x18003943c  jmp     loc_1800392B4
0x180039441  mov     r9d, 0B0h
0x180039447  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18003944e  mov     edx, 1
0x180039453  mov     ecx, ebx
0x180039455  call    Log_UnistoreHREvent_0
0x18003945a  lea     rcx, ?g_storeManagerLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180039461  call    cs:__imp_LeaveCriticalSection
0x180039467  mov     eax, ebx
0x180039469  mov     rbx, [rsp+60h+arg_10]
0x180039471  add     rsp, 60h
0x180039475  pop     rdi
0x180039476  pop     rsi
0x180039477  pop     rbp
0x180039478  retn
0x180039479  xor     ebx, ebx
0x18003947b  jmp     short loc_18003940D
0x18003947d  mov     rcx, [rbp+Binding]; struct __MIDL_UnistoreService_0001 *
0x180039481  test    rcx, rcx
0x180039484  jz      short loc_18003945A
0x180039486  call    ?_ObjectCloser@@YAXPEAU__MIDL_UnistoreService_0001@@@Z; _ObjectCloser(__MIDL_UnistoreService_0001 *)
0x18003948b  jmp     short loc_18003945A
0x18003948d  call    cs:__imp_GetLastError
0x180039493  mov     ebx, eax
0x180039495  test    eax, eax
0x180039497  jle     loc_180039141
0x18003949d  movzx   ebx, ax
0x1800394a0  or      ebx, 80070000h
0x1800394a6  jmp     loc_180039141
0x1800394ab  call    cs:__imp_GetLastError
0x1800394b1  mov     ebx, eax
0x1800394b3  test    eax, eax
0x1800394b5  jle     short loc_1800394C0
0x1800394b7  movzx   ebx, ax
0x1800394ba  or      ebx, 80070000h
0x1800394c0  mov     r9d, 7Eh ; '~'
0x1800394c6  jmp     loc_180039147
0x1800394cb  mov     r9d, 0E2h
0x1800394d1  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800394d8  mov     edx, 1
0x1800394dd  mov     ecx, esi
0x1800394df  call    Log_UnistoreHREvent_0
0x1800394e4  lea     rcx, [rbp+var_30]; void *
0x1800394e8  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800394ed  mov     rcx, [rbp+Binding]; struct __MIDL_UnistoreService_0001 *
0x1800394f1  test    rcx, rcx
0x1800394f4  jnz     loc_180039677
0x1800394fa  lea     rcx, ?g_storeManagerLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180039501  call    cs:__imp_LeaveCriticalSection
0x180039507  mov     rbx, [rsp+60h+arg_10]
0x18003950f  mov     eax, esi
0x180039511  add     rsp, 60h
0x180039515  pop     rdi
0x180039516  pop     rsi
0x180039517  pop     rbp
0x180039518  retn
0x180039519  mov     r9d, 0A1h
0x18003951f  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180039526  xor     edx, edx
0x180039528  mov     ecx, 80070057h
0x18003952d  call    Log_UnistoreHREvent_0
0x180039532  mov     eax, 80070057h
0x180039537  jmp     loc_180039161
0x18003953c  lea     rcx, [rbp+Binding]
0x180039540  mov     [rbp+Binding], 0
0x180039548  call    ?_Delete@?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0>::_Delete(void)
0x18003954d  lea     rcx, [rbp+Binding]; Binding
0x180039551  mov     [rbp+Binding], 0
0x180039559  call    ?GetBindingHandle@@YAJPEAPEAX@Z; GetBindingHandle(void * *)
0x18003955e  mov     ebx, eax
0x180039560  test    eax, eax
0x180039562  jns     short loc_1800395A2
0x180039564  mov     r9d, 0B8h
0x18003956a  jmp     short loc_180039572
0x18003956c  mov     r9d, 0C0h
0x180039572  lea     r8, aOnecoreuapBase_47; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180039579  mov     edx, 1
0x18003957e  mov     ecx, ebx
0x180039580  call    Log_UnistoreHREvent_0
0x180039585  lea     rcx, [rbp+Binding]
0x180039589  call    ?_Delete@?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0>::_Delete(void)
0x18003958e  lea     rcx, ?g_storeManagerLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180039595  call    cs:__imp_LeaveCriticalSection
0x18003959b  mov     eax, ebx
0x18003959d  jmp     loc_180039161
0x1800395a2  cmp     cs:?g_RundownProtectionId@@3KA, 0; ulong g_RundownProtectionId
0x1800395a9  jnz     short loc_1800395E9
0x1800395ab  lea     rax, ?g_RundownProtectionId@@3KA; ulong g_RundownProtectionId
0x1800395b2  lea     r9, [rbp+var_20]
0x1800395b6  mov     [rbp+var_20], rax
0x1800395ba  lea     r8, [rbp+arg_0]
0x1800395be  lea     rdx, [rbp+Binding]
0x1800395c2  call    ??$MakeRpcCall@PEAXPEAXPEAKAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@AEAPEAXPEAK@RpcHelper@@YAJP6AJPEAX0PEAK@ZAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@AEAPEAX$$QEAPEAK@Z; RpcHelper::MakeRpcCall<void *,void *,ulong *,tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0> &,void * &,ulong *>(long (*)(void *,void *,ulong *),tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0> &,void * &,ulong * &&)
0x1800395c7  mov     ebx, eax
0x1800395c9  test    eax, eax
0x1800395cb  js      short loc_18003956C
0x1800395cd  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits+1, 40h
0x1800395d4  jz      short loc_1800395E9
0x1800395d6  mov     r8d, cs:?g_RundownProtectionId@@3KA; ulong g_RundownProtectionId
  ... truncated ...
```
