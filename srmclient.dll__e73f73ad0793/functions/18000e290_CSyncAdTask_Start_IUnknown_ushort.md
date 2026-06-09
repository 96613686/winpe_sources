# CSyncAdTask::Start(IUnknown *,ushort *)

- ea: `0x18000e290`
- end: `0x18000e741`
- name: `?Start@CSyncAdTask@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `1201`
- prototype: `__int64 __fastcall(CSyncAdTask *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18000d560`
- `0x18000e290`
- `0x1800176f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180075510`
- `0x180076c0c`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000e4d6`
- `ole32!CoCreateInstance` at `0x18000e4d6`
- `KERNEL32!CloseHandle` at `0x18000e560`
- `KERNEL32!CloseHandle` at `0x18000e560`
- `KERNEL32!CreateThread` at `0x18000e54e`
- `KERNEL32!CreateThread` at `0x18000e54e`

## string_xrefs

- `0x18000e34b`: `CSyncAdTask::Initialize`
- `0x18000e2bf`: `base\fs\fsrm\service\globalstore\taskhandler.cpp`
- `0x18000e2cd`: `CSyncAdTask::Start`
- `0x18000e3ef`: `CLSID\{53e94fe8-9e5b-4acd-b99d-e09bb87b149b}`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSyncAdTask::Start(CSyncAdTask *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  bool v5; // r14
  int v6; // eax
  HRESULT v8; // eax
  int v9; // eax
  HANDLE Thread; // rsi
  void *v11; // rcx
  unsigned int v12; // ebx
  char Hr; // r8
  int v14; // eax
  char v15; // r8
  int v16; // eax
  char v17; // r8
  int v18; // eax
  char v19; // al
  int LastFailureAsHRESULT; // eax
  char v21; // al
  __int64 v22; // [rsp+40h] [rbp-2E8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-2E0h] BYREF
  _QWORD v24[5]; // [rsp+58h] [rbp-2D0h] BYREF
  _QWORD v25[3]; // [rsp+80h] [rbp-2A8h] BYREF
  int v26; // [rsp+98h] [rbp-290h]
  int v27; // [rsp+9Ch] [rbp-28Ch]
  int v28; // [rsp+A0h] [rbp-288h]
  _DWORD v29[26]; // [rsp+A8h] [rbp-280h] BYREF
  _QWORD v30[3]; // [rsp+110h] [rbp-218h] BYREF
  int v31; // [rsp+128h] [rbp-200h]
  int v32; // [rsp+12Ch] [rbp-1FCh]
  int v33; // [rsp+130h] [rbp-1F8h]
  char v34[96]; // [rsp+138h] [rbp-1F0h] BYREF
  int v35; // [rsp+198h] [rbp-190h]
  void **v36; // [rsp+1A0h] [rbp-188h] BYREF
  HRESULT v37; // [rsp+1A8h] [rbp-180h]
  _QWORD v38[22]; // [rsp+250h] [rbp-D8h] BYREF

  v25[0] = L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp";
  v25[1] = L"CSyncAdTask::Start";
  v25[2] = L"TSKNDLRC";
  v26 = 84;
  v27 = 30;
  v28 = 255;
  v29[24] = 0x1000000;
  memset_0(v29, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v36, v25, 0);
  v30[0] = L"base\\fs\\fsrm\\service\\globalstore\\taskhandler.cpp";
  v30[1] = L"CSyncAdTask::Initialize";
  v30[2] = L"TSKNDLRC";
  v31 = 62;
  v32 = 30;
  v33 = 255;
  v35 = 0x1000000;
  memset_0(v34, 0, sizeof(v34));
  CSrmFunctionTracer::CSrmFunctionTracer(v38, v30, 0);
  CSyncAdTask::InitalizeClientStorePaths();
  v38[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v38);
  v24[2] = 0;
  v24[1] = 0;
  v24[0] = 131353;
  v5 = CSrmRegistryKey::OpenNoLog(
         (CSrmRegistryKey *)v24,
         HKEY_CLASSES_ROOT,
         L"CLSID\\{53e94fe8-9e5b-4acd-b99d-e09bb87b149b}");
  CSrmRegistryKey::~CSrmRegistryKey((CSrmRegistryKey *)v24);
  if ( v5 )
  {
LABEL_17:
    v12 = v37;
    v36 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v36);
    return v12;
  }
  if ( !a2 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x62u, Hr, 0);
  }
  v37 = 0;
  if ( !CAdReader::ShouldSkipSync() )
  {
    ppv = 0;
    v8 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &IID_IGlobalInterfaceTable, &ppv);
    v37 = v8;
    if ( v8 < 0 )
    {
      v16 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v16);
      v17 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x79u, v17, 0);
    }
    v37 = v8;
    v9 = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *, GUID *, char *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           a2,
           &IID_IUnknown,
           (char *)this + 80);
    v37 = v9;
    if ( v9 < 0 )
    {
      v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v18);
      v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x7Bu, v19, 0);
    }
    v37 = v9;
    (*(void (__fastcall **)(CSyncAdTask *))(*(_QWORD *)this + 8LL))(this);
    Thread = CreateThread(0, 0, CSyncAdTask::AdSyncTaskThreadProc, this, 0, 0);
    v11 = (void *)*((_QWORD *)this + 9);
    if ( v11 )
      CloseHandle(v11);
    *((_QWORD *)this + 9) = Thread;
    if ( !Thread )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *((unsigned int *)this + 20));
      (*(void (__fastcall **)(CSyncAdTask *))(*(_QWORD *)this + 16LL))(this);
    }
    if ( !*((_QWORD *)this + 9) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, LastFailureAsHRESULT);
      v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x93u, v21, 0);
    }
    v37 = 0;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_17;
  }
  v22 = 0;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_ITaskHandlerStatus,
         &v22);
  v37 = v6;
  if ( v6 < 0 )
  {
    v14 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v36, v14);
    v15 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v36);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v36, 0x6Au, v15, 0);
  }
  v37 = v6;
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, 0);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v36 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v36);
  return 0;
}

```

## disassembly

```asm
0x18000e290  mov     r11, rsp
0x18000e293  mov     [r11+18h], rbx
0x18000e297  mov     [r11+20h], rsi
0x18000e29b  push    rdi
0x18000e29c  push    r14
0x18000e29e  push    r15
0x18000e2a0  sub     rsp, 310h
0x18000e2a7  mov     rax, cs:__security_cookie
0x18000e2ae  xor     rax, rsp
0x18000e2b1  mov     [rsp+328h+var_28], rax
0x18000e2b9  mov     rsi, rdx
0x18000e2bc  mov     rbx, rcx
0x18000e2bf  lea     rdi, aBaseFsFsrmServ_39; "base\\fs\\fsrm\\service\\globalstore\\t"...
0x18000e2c6  mov     [r11-2A8h], rdi
0x18000e2cd  lea     rax, aCsyncadtaskSta; "CSyncAdTask::Start"
0x18000e2d4  mov     [r11-2A0h], rax
0x18000e2db  lea     r14, aTskndlrc; "TSKNDLRC"
0x18000e2e2  mov     [r11-298h], r14
0x18000e2e9  mov     [rsp+328h+var_290], 54h ; 'T'
0x18000e2f4  mov     [rsp+328h+var_28C], 1Eh
0x18000e2ff  mov     [rsp+328h+var_288], 0FFh
0x18000e30a  xor     r15d, r15d
0x18000e30d  mov     [rsp+328h+var_220], 1000000h
0x18000e318  xor     edx, edx; Val
0x18000e31a  lea     r8d, [r15+60h]; Size
0x18000e31e  lea     rcx, [r11-280h]; void *
0x18000e325  call    memset_0
0x18000e32a  xor     r8d, r8d
0x18000e32d  lea     rdx, [rsp+328h+var_2A8]
0x18000e335  lea     rcx, [rsp+328h+var_188]
0x18000e33d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000e342  nop
0x18000e343  mov     [rsp+328h+var_218], rdi
0x18000e34b  lea     rax, aCsyncadtaskIni; "CSyncAdTask::Initialize"
0x18000e352  mov     [rsp+328h+var_210], rax
0x18000e35a  mov     [rsp+328h+var_208], r14
0x18000e362  mov     [rsp+328h+var_200], 3Eh ; '>'
0x18000e36d  mov     [rsp+328h+var_1FC], 1Eh
0x18000e378  mov     [rsp+328h+var_1F8], 0FFh
0x18000e383  mov     [rsp+328h+var_190], 1000000h
0x18000e38e  xor     edx, edx; Val
0x18000e390  lea     r8d, [r15+60h]; Size
0x18000e394  lea     rcx, [rsp+328h+var_1F0]; void *
0x18000e39c  call    memset_0
0x18000e3a1  xor     r8d, r8d
0x18000e3a4  lea     rdx, [rsp+328h+var_218]
0x18000e3ac  lea     rcx, [rsp+328h+var_D8]
0x18000e3b4  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18000e3b9  nop
0x18000e3ba  call    ?InitalizeClientStorePaths@CSyncAdTask@@SAXXZ; CSyncAdTask::InitalizeClientStorePaths(void)
0x18000e3bf  nop
0x18000e3c0  lea     rdi, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000e3c7  mov     [rsp+328h+var_D8], rdi
0x18000e3cf  lea     rcx, [rsp+328h+var_D8]; this
0x18000e3d7  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000e3dc  mov     [rsp+328h+var_2C0], r15
0x18000e3e1  mov     [rsp+328h+var_2C8], r15
0x18000e3e6  mov     [rsp+328h+var_2D0], 20119h
0x18000e3ef  lea     r8, aClsid53e94fe89; "CLSID\\{53e94fe8-9e5b-4acd-b99d-e09bb87"...
0x18000e3f6  mov     rdx, 0FFFFFFFF80000000h; hKey
0x18000e3fd  lea     rcx, [rsp+328h+var_2D0]; this
0x18000e402  call    ?OpenNoLog@CSrmRegistryKey@@QEAA_NPEAUHKEY__@@PEBGZZ; CSrmRegistryKey::OpenNoLog(HKEY__ *,ushort const *,...)
0x18000e407  mov     r14b, al
0x18000e40a  lea     rcx, [rsp+328h+var_2D0]; this
0x18000e40f  call    ??1CSrmRegistryKey@@QEAA@XZ; CSrmRegistryKey::~CSrmRegistryKey(void)
0x18000e414  test    r14b, r14b
0x18000e417  jnz     loc_18000E5BB
0x18000e41d  test    rsi, rsi
0x18000e420  jz      loc_18000E60F
0x18000e426  mov     [rsp+328h+var_180], r15d
0x18000e42e  call    ?ShouldSkipSync@CAdReader@@SA_NXZ; CAdReader::ShouldSkipSync(void)
0x18000e433  test    al, al
0x18000e435  jz      short loc_18000E4B3
0x18000e437  mov     [rsp+328h+var_2E8], r15
0x18000e43c  mov     rax, [rsi]
0x18000e43f  lea     r8, [rsp+328h+var_2E8]
0x18000e444  lea     rdx, IID_ITaskHandlerStatus
0x18000e44b  mov     rcx, rsi
0x18000e44e  mov     rax, [rax]
0x18000e451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e456  mov     [rsp+328h+var_180], eax
0x18000e45d  test    eax, eax
0x18000e45f  js      loc_18000E645
0x18000e465  mov     [rsp+328h+var_180], eax
0x18000e46c  mov     rcx, [rsp+328h+var_2E8]
0x18000e471  mov     rax, [rcx]
0x18000e474  xor     edx, edx
0x18000e476  mov     rax, [rax+20h]
0x18000e47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e47f  nop
0x18000e480  mov     rcx, [rsp+328h+var_2E8]
0x18000e485  test    rcx, rcx
0x18000e488  jz      short loc_18000E497
0x18000e48a  mov     rax, [rcx]
0x18000e48d  mov     rax, [rax+10h]
0x18000e491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e496  nop
0x18000e497  mov     [rsp+328h+var_188], rdi
0x18000e49f  lea     rcx, [rsp+328h+var_188]; this
0x18000e4a7  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000e4ac  xor     eax, eax
0x18000e4ae  jmp     loc_18000E5E2
0x18000e4b3  mov     [rsp+328h+var_2E0], r15
0x18000e4b8  lea     rax, [rsp+328h+var_2E0]
0x18000e4bd  mov     [rsp+328h+ppv], rax; ppv
0x18000e4c2  lea     r9, IID_IGlobalInterfaceTable; riid
0x18000e4c9  xor     edx, edx; pUnkOuter
0x18000e4cb  lea     r8d, [rdx+1]; dwClsContext
0x18000e4cf  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000e4d6  call    cs:__imp_CoCreateInstance
0x18000e4dc  mov     [rsp+328h+var_180], eax
0x18000e4e3  test    eax, eax
0x18000e4e5  js      loc_18000E686
0x18000e4eb  mov     [rsp+328h+var_180], eax
0x18000e4f2  mov     rcx, [rsp+328h+var_2E0]
0x18000e4f7  mov     rax, [rcx]
0x18000e4fa  lea     r9, [rbx+50h]
0x18000e4fe  lea     r8, IID_IUnknown
0x18000e505  mov     rdx, rsi
0x18000e508  mov     rax, [rax+18h]
0x18000e50c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e511  mov     [rsp+328h+var_180], eax
0x18000e518  test    eax, eax
0x18000e51a  js      loc_18000E6C6
0x18000e520  mov     [rsp+328h+var_180], eax
0x18000e527  mov     rax, [rbx]
0x18000e52a  mov     rcx, rbx
0x18000e52d  mov     rax, [rax+8]
0x18000e531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e536  mov     [rsp+328h+lpThreadId], r15; lpThreadId
0x18000e53b  mov     dword ptr [rsp+328h+ppv], r15d; dwCreationFlags
0x18000e540  mov     r9, rbx; lpParameter
0x18000e543  lea     r8, ?AdSyncTaskThreadProc@CSyncAdTask@@CAKPEAX@Z; lpStartAddress
0x18000e54a  xor     edx, edx; dwStackSize
0x18000e54c  xor     ecx, ecx; lpThreadAttributes
0x18000e54e  call    cs:__imp_CreateThread
0x18000e554  mov     rsi, rax
0x18000e557  mov     rcx, [rbx+48h]; hObject
0x18000e55b  test    rcx, rcx
0x18000e55e  jz      short loc_18000E566
0x18000e560  call    cs:__imp_CloseHandle
0x18000e566  mov     [rbx+48h], rsi
0x18000e56a  test    rsi, rsi
0x18000e56d  jnz     short loc_18000E592
0x18000e56f  mov     rcx, [rsp+328h+var_2E0]
0x18000e574  mov     rax, [rcx]
0x18000e577  mov     edx, [rbx+50h]
0x18000e57a  mov     rax, [rax+20h]
0x18000e57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e583  mov     rax, [rbx]
0x18000e586  mov     rcx, rbx
0x18000e589  mov     rax, [rax+10h]
0x18000e58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e592  cmp     [rbx+48h], r15
0x18000e596  jz      loc_18000E706
0x18000e59c  mov     [rsp+328h+var_180], r15d
0x18000e5a4  mov     rcx, [rsp+328h+var_2E0]
0x18000e5a9  test    rcx, rcx
0x18000e5ac  jz      short loc_18000E5BB
0x18000e5ae  mov     rax, [rcx]
0x18000e5b1  mov     rax, [rax+10h]
0x18000e5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5ba  nop
0x18000e5bb  jmp     short loc_18000E5C4
0x18000e5bd  lea     rdi, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18000e5c4  mov     ebx, [rsp+328h+var_180]
0x18000e5cb  mov     [rsp+328h+var_188], rdi
0x18000e5d3  lea     rcx, [rsp+328h+var_188]; this
0x18000e5db  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18000e5e0  mov     eax, ebx
0x18000e5e2  mov     rcx, [rsp+328h+var_28]
0x18000e5ea  xor     rcx, rsp; StackCookie
0x18000e5ed  call    __security_check_cookie
0x18000e5f2  lea     r11, [rsp+328h+var_18]
0x18000e5fa  mov     rbx, [r11+30h]
0x18000e5fe  mov     rsi, [r11+38h]
0x18000e602  mov     rsp, r11
0x18000e605  pop     r15
0x18000e607  pop     r14
0x18000e609  pop     rdi
0x18000e60a  retn
0x18000e60b  jmp     short loc_18000E5BD
0x18000e60d  jmp     short loc_18000E5BD
0x18000e60f  mov     edx, 80070057h; int
0x18000e614  lea     rcx, [rsp+328h+var_188]; this
0x18000e61c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000e621  lea     rcx, [rsp+328h+var_188]; this
0x18000e629  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e62e  mov     r8d, eax; char
0x18000e631  xor     r9d, r9d; unsigned __int16 *
0x18000e634  lea     edx, [rsi+62h]; unsigned int
0x18000e637  lea     rcx, [rsp+328h+var_188]; this
0x18000e63f  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000e645  lea     rcx, [rsp+328h+var_188]; this
0x18000e64d  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e652  mov     edx, eax; int
0x18000e654  lea     rcx, [rsp+328h+var_188]; this
0x18000e65c  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000e661  lea     rcx, [rsp+328h+var_188]; this
0x18000e669  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e66e  mov     r8d, eax; char
0x18000e671  xor     r9d, r9d; unsigned __int16 *
0x18000e674  lea     edx, [r9+6Ah]; unsigned int
0x18000e678  lea     rcx, [rsp+328h+var_188]; this
0x18000e680  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000e686  lea     rcx, [rsp+328h+var_188]; this
0x18000e68e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e693  mov     edx, eax; int
0x18000e695  lea     rcx, [rsp+328h+var_188]; this
0x18000e69d  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000e6a2  lea     rcx, [rsp+328h+var_188]; this
0x18000e6aa  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e6af  mov     r8d, eax; char
0x18000e6b2  xor     r9d, r9d; unsigned __int16 *
0x18000e6b5  lea     edx, [r9+79h]; unsigned int
0x18000e6b9  lea     rcx, [rsp+328h+var_188]; this
0x18000e6c1  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000e6c6  lea     rcx, [rsp+328h+var_188]; this
0x18000e6ce  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e6d3  mov     edx, eax; int
0x18000e6d5  lea     rcx, [rsp+328h+var_188]; this
0x18000e6dd  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000e6e2  lea     rcx, [rsp+328h+var_188]; this
0x18000e6ea  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e6ef  mov     r8d, eax; char
0x18000e6f2  xor     r9d, r9d; unsigned __int16 *
0x18000e6f5  lea     edx, [r9+7Bh]; unsigned int
0x18000e6f9  lea     rcx, [rsp+328h+var_188]; this
0x18000e701  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18000e706  call    GetLastFailureAsHRESULT
0x18000e70b  mov     edx, eax; int
0x18000e70d  lea     rcx, [rsp+328h+var_188]; this
0x18000e715  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18000e71a  lea     rcx, [rsp+328h+var_188]; this
0x18000e722  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18000e727  mov     r8d, eax; char
0x18000e72a  xor     r9d, r9d; unsigned __int16 *
0x18000e72d  mov     edx, 93h; unsigned int
0x18000e732  lea     rcx, [rsp+328h+var_188]; this
0x18000e73a  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
