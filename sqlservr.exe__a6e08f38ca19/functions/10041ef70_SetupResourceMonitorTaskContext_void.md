# SetupResourceMonitorTaskContext(void *)

- ea: `0x10041ef70`
- end: `0x10041f3ac`
- name: `?SetupResourceMonitorTaskContext@@YAPEAXPEAX@Z`
- size: `1084`
- prototype: `void *__fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x100401580`
- `0x10041ef70`
- `0x10041fa30`
- `0x10041fab0`
- `0x10044edd0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f043`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f17c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f2bd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f35e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f043`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f17c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f2bd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041f35e`
- `sqldk!SystemThread_TlsOffset` at `0x10041f018`
- `sqldk!SystemThread_TlsOffset` at `0x10041f084`
- `sqldk!SystemThread_TlsOffset` at `0x10041f151`
- `sqldk!SystemThread_TlsOffset` at `0x10041f2a4`
- `sqldk!SystemThread_TlsOffset` at `0x10041f345`
- `sqldk!SystemThread_TlsIndex` at `0x10041f00f`
- `sqldk!SystemThread_TlsIndex` at `0x10041f07b`
- `sqldk!SystemThread_TlsIndex` at `0x10041f148`
- `sqldk!SystemThread_TlsIndex` at `0x10041f29b`
- `sqldk!SystemThread_TlsIndex` at `0x10041f33c`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10041f2d3`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10041f374`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10041f2d3`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10041f374`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041f37f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x10041f37f`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x10041efb0`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x10041f257`
- `sqldk!?WaitForComponentsInitialized@@YAXXZ` at `0x10041efa0`
- `sqldk!?WaitForComponentsInitialized@@YAXXZ` at `0x10041efa0`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x10041f0f0`
- `sqldk!?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z` at `0x10041f0f0`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x10041f231`
- `sqldk!?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z` at `0x10041f231`
- `sqldk!?ResourceMonitorTask@ResourceMonitor@@SAPEAXPEAX@Z` at `0x10041f279`
- `sqldk!?ResourceMonitorTask@ResourceMonitor@@SAPEAXPEAX@Z` at `0x10041f279`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10041f0bb`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10041f128`

## string_xrefs

- `0x10041efe3`: `Resource Monitor Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void *__fastcall SetupResourceMonitorTaskContext(void *a1)
{
  __int64 v1; // rdi
  __int64 v2; // rax
  _DWORD *v3; // rdi
  int v4; // eax
  struct SOS_ResourceGroup *v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // r9
  __int64 v8; // r9
  signed __int32 v9; // r8d
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v15; // [rsp+30h] [rbp-398h]
  struct SOS_ResourceGroup *v16; // [rsp+38h] [rbp-390h] BYREF
  int v17; // [rsp+40h] [rbp-388h]
  int v18; // [rsp+44h] [rbp-384h]
  volatile signed __int32 v19; // [rsp+48h] [rbp-380h]
  volatile signed __int32 *v20; // [rsp+50h] [rbp-378h]
  __int64 v21; // [rsp+58h] [rbp-370h] BYREF
  int v22; // [rsp+60h] [rbp-368h]
  __int16 v23; // [rsp+64h] [rbp-364h]
  const wchar_t *v24; // [rsp+68h] [rbp-360h]
  int v25; // [rsp+70h] [rbp-358h]
  signed __int32 v26; // [rsp+74h] [rbp-354h]
  signed __int32 v27; // [rsp+78h] [rbp-350h]
  __int64 v28; // [rsp+80h] [rbp-348h]
  _DWORD *v29; // [rsp+88h] [rbp-340h]
  __int64 v30; // [rsp+90h] [rbp-338h]
  struct SOS_ResourceGroup *v31; // [rsp+98h] [rbp-330h]
  SOS_ResourceManager *v32; // [rsp+A0h] [rbp-328h]
  struct SOS_ResourceGroup *v33[2]; // [rsp+A8h] [rbp-320h] BYREF
  _DWORD v34[6]; // [rsp+B8h] [rbp-310h] BYREF
  _QWORD *v35; // [rsp+D0h] [rbp-2F8h]
  __int64 v36; // [rsp+D8h] [rbp-2F0h]
  __int64 v37; // [rsp+E0h] [rbp-2E8h]
  __int64 v38; // [rsp+E8h] [rbp-2E0h]
  struct SOS_ResourceGroup *v39; // [rsp+F0h] [rbp-2D8h]
  _QWORD *v40; // [rsp+F8h] [rbp-2D0h]
  __int64 v41; // [rsp+100h] [rbp-2C8h]
  __int64 v42; // [rsp+108h] [rbp-2C0h]
  __int64 v43; // [rsp+110h] [rbp-2B8h]
  _BYTE v44[16]; // [rsp+118h] [rbp-2B0h] BYREF
  _BYTE v45[16]; // [rsp+128h] [rbp-2A0h] BYREF
  _QWORD *ThreadLocalStoragePointer; // [rsp+138h] [rbp-290h]
  __int64 v47; // [rsp+140h] [rbp-288h]
  _BYTE v48[24]; // [rsp+148h] [rbp-280h] BYREF
  _BYTE v49[40]; // [rsp+160h] [rbp-268h] BYREF
  _BYTE v50[40]; // [rsp+188h] [rbp-240h] BYREF
  wchar_t v51[256]; // [rsp+1B0h] [rbp-218h] BYREF

  v43 = -2;
  WaitForComponentsInitialized();
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v50, 0, 0, 0, hdl_backout, 0);
    v21 = 0;
    v22 = 0;
    v23 = 348;
    v24 = L"Resource Monitor Task";
    CAutoSetupExecContextsForInternalTasks::Setup(&v21, 0, 0);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v1 = ThreadLocalStoragePointer[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v47 = v1;
    v2 = *(_QWORD *)(v1 + 256);
    v28 = v2;
    if ( !v2 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v2 = *(_QWORD *)(v1 + 256);
      v28 = v2;
    }
    v17 = *(unsigned __int16 *)(*(_QWORD *)(v2 + 992) + 160LL);
    v35 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v36 = v35[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v37 = *(_QWORD *)(v36 + 8);
    v38 = *(_QWORD *)(v37 + 96);
    *(_DWORD *)(v38 + 1248) = v17;
    v3 = (_DWORD *)SOS_PublicGlobals::sm_ResourceManager;
    v29 = (_DWORD *)SOS_PublicGlobals::sm_ResourceManager;
    v16 = 0;
    do
    {
      v18 = *v3;
      v3 = v29;
      v4 = SOS_ResourceManager::LookupGroup(v29, L"ResourceMonitorGroup", v18, &v16);
      v25 = v4;
    }
    while ( v4 == 0x80000000 );
    if ( v4 )
    {
      v5 = (struct SOS_ResourceGroup *)(v3 + 894);
      v39 = v5;
      v16 = v5;
    }
    else
    {
      v5 = v16;
    }
    v31 = v5;
    v32 = (SOS_ResourceManager *)SOS_PublicGlobals::sm_ResourceManager;
    v40 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v6 = v40[SystemThread_TlsIndex] + SystemThread_TlsOffset;
    v41 = v6;
    v7 = *(_QWORD *)(v6 + 256);
    v30 = v7;
    if ( !v7 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v7 = *(_QWORD *)(v6 + 256);
      v30 = v7;
    }
    v8 = *(_QWORD *)(v7 + 536);
    v33[1] = (struct SOS_ResourceGroup *)v8;
    v33[0] = v31;
    if ( v5 && (struct SOS_ResourceGroup *)v8 != v5 )
    {
      if ( *(_DWORD *)(v8 + 164) >= 3u )
      {
        v20 = (volatile signed __int32 *)(v8 + 64);
        v9 = *(_DWORD *)(v8 + 64);
        v19 = v9;
        while ( v9 >= 0 )
        {
          v26 = v9 + 1;
          v27 = _InterlockedCompareExchange(v20, v9 + 1, v9);
          if ( v9 == v27 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v8 + 40));
            break;
          }
          v9 = *v20;
          v19 = *v20;
        }
      }
      SOS_ResourceManager::BindCurrentTaskToGroup(v32, v33[0]);
    }
    do
    {
      v15 = 1;
      v42 = 0;
      try
      {
        ExcHandler::ExcHandler((ExcHandler *)v49, 0, 0, 0, hdl_prntbackout, 0);
        ResourceMonitor::ResourceMonitorTask(0);
        ExcHandler::~ExcHandler((ExcHandler *)v49);
      }
      catch ( SQLError v34 )
      {
        try
        {
          ExceptionBackout::ExceptionBackout((ExceptionBackout *)v44, (const struct SQLError *)v34);
          if ( v34[0] / 100 == 29 )
          {
            v15 = 0;
            if ( v34[0] == 2905 )
            {
              scierrlog(
                0x439Cu,
                L"resource monitor",
                (unsigned int)*(__int16 *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                       + SystemThread_TlsIndex)
                                                     + SystemThread_TlsOffset
                                                     + 80LL)
                                         + 72LL));
            }
            else
            {
              PrintStringW(v51, 0x100u, L"Exception 0x%X", v34[3]);
              scierrlog(0x429Du, L"resource monitor", v51);
            }
          }
          else
          {
            v15 = 1;
          }
          ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v44);
        }
        catch ( ShortStackException )
        {
        }
      }
      v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v11 = *(_QWORD *)(v10 + 256);
      if ( !v11 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v11 = *(_QWORD *)(v10 + 256);
      }
      if ( *(_DWORD *)(v11 + 556) )
        ExceptionPostCatchActions((struct Worker *)v11);
    }
    while ( v15 );
    if ( v21 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 16LL))(v21, 0);
    SOS_ResourceManager::AutoSwitchResourceGroup::~AutoSwitchResourceGroup((SOS_ResourceManager::AutoSwitchResourceGroup *)v33);
    SOS_AutoReleaseResourceGroup::~SOS_AutoReleaseResourceGroup((SOS_AutoReleaseResourceGroup *)&v16);
    if ( v21 )
      (**(void (__fastcall ***)(__int64, __int64))v21)(v21, 1);
    ExcHandler::~ExcHandler((ExcHandler *)v50);
  }
  catch ( SQLError v48 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v45, (const struct SQLError *)v48);
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v45);
    }
    catch ( ShortStackException )
    {
    }
  }
  v12 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v13 = *(_QWORD *)(v12 + 256);
  if ( !v13 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v13 = *(_QWORD *)(v12 + 256);
  }
  if ( *(_DWORD *)(v13 + 556) )
    ExceptionPostCatchActions((struct Worker *)v13);
  SQLExit(329);
  return 0;
}

```

## disassembly

```asm
0x10041ef70  mov     rax, rsp
0x10041ef73  push    rdi
0x10041ef74  sub     rsp, 3C0h
0x10041ef7b  mov     qword ptr [rax-2B8h], 0FFFFFFFFFFFFFFFEh
0x10041ef86  mov     [rax+8], rbx
0x10041ef8a  mov     [rax+10h], rsi
0x10041ef8e  mov     rax, cs:__security_cookie
0x10041ef95  xor     rax, rsp
0x10041ef98  mov     [rsp+3C8h+var_18], rax
0x10041efa0  call    cs:__imp_?WaitForComponentsInitialized@@YAXXZ; WaitForComponentsInitialized(void)
0x10041efa6  nop
0x10041efa7  xor     edx, edx; unsigned __int16
0x10041efa9  xor     ebx, ebx
0x10041efab  mov     [rsp+3C8h+var_3A0], rbx; struct Worker *
0x10041efb0  mov     rax, cs:__imp_?hdl_backout@@YAHHHHHPEAD@Z; hdl_backout(int,int,int,int,char *)
0x10041efb7  mov     [rsp+3C8h+var_3A8], rax; int (*)(int, int, int, int, char *)
0x10041efbc  xor     r9d, r9d; unsigned __int8
0x10041efbf  xor     r8d, r8d; unsigned __int8
0x10041efc2  lea     rcx, [rsp+3C8h+var_240]; this
0x10041efca  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10041efcf  nop
0x10041efd0  mov     [rsp+3C8h+var_370], rbx
0x10041efd5  mov     [rsp+3C8h+var_368], ebx
0x10041efd9  mov     eax, 15Ch
0x10041efde  mov     [rsp+3C8h+var_364], ax
0x10041efe3  lea     rax, aResourceMonito; "Resource Monitor Task"
0x10041efea  mov     [rsp+3C8h+var_360], rax
0x10041efef  xor     r8d, r8d
0x10041eff2  xor     edx, edx
0x10041eff4  lea     rcx, [rsp+3C8h+var_370]
0x10041eff9  call    ?Setup@CAutoSetupExecContextsForInternalTasks@@QEAAXW4EStartupErrorHandling@1@PEAVXactWorkspace@@@Z; CAutoSetupExecContextsForInternalTasks::Setup(CAutoSetupExecContextsForInternalTasks::EStartupErrorHandling,XactWorkspace *)
0x10041effe  mov     rdx, gs:58h
0x10041f007  mov     [rsp+3C8h+var_290], rdx
0x10041f00f  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f016  mov     ecx, [rax]
0x10041f018  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f01f  mov     edi, [rax]
0x10041f021  add     rdi, [rdx+rcx*8]
0x10041f025  mov     [rsp+3C8h+var_288], rdi
0x10041f02d  mov     rax, [rdi+100h]
0x10041f034  mov     [rsp+3C8h+var_348], rax
0x10041f03c  test    rax, rax
0x10041f03f  jnz     short loc_10041F058
0x10041f041  xor     ecx, ecx
0x10041f043  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f049  mov     rax, [rdi+100h]
0x10041f050  mov     [rsp+3C8h+var_348], rax
0x10041f058  mov     rax, [rax+3E0h]
0x10041f05f  movzx   ecx, word ptr [rax+0A0h]
0x10041f066  mov     [rsp+3C8h+var_388], ecx
0x10041f06a  mov     rdx, gs:58h
0x10041f073  mov     [rsp+3C8h+var_2F8], rdx
0x10041f07b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f082  mov     ecx, [rax]
0x10041f084  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f08b  mov     eax, [rax]
0x10041f08d  add     rax, [rdx+rcx*8]
0x10041f091  mov     [rsp+3C8h+var_2F0], rax
0x10041f099  mov     rax, [rax+8]
0x10041f09d  mov     [rsp+3C8h+var_2E8], rax
0x10041f0a5  mov     rcx, [rax+60h]
0x10041f0a9  mov     [rsp+3C8h+var_2E0], rcx
0x10041f0b1  mov     eax, [rsp+3C8h+var_388]
0x10041f0b5  mov     [rcx+4E0h], eax
0x10041f0bb  mov     rdi, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x10041f0c2  mov     [rsp+3C8h+var_340], rdi
0x10041f0ca  mov     [rsp+3C8h+var_390], rbx
0x10041f0cf  nop
0x10041f0d0  mov     eax, [rdi]
0x10041f0d2  mov     [rsp+3C8h+var_384], eax
0x10041f0d6  movsxd  r8, eax
0x10041f0d9  lea     r9, [rsp+3C8h+var_390]
0x10041f0de  lea     rdx, aResourcemonito; "ResourceMonitorGroup"
0x10041f0e5  mov     rdi, [rsp+3C8h+var_340]
0x10041f0ed  mov     rcx, rdi
0x10041f0f0  call    cs:__imp_?LookupGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEB_W_JPEAPEAVSOS_ResourceGroup@@@Z; SOS_ResourceManager::LookupGroup(wchar_t const *,__int64,SOS_ResourceGroup * *)
0x10041f0f6  mov     [rsp+3C8h+var_358], eax
0x10041f0fa  cmp     eax, 80000000h
0x10041f0ff  jz      short loc_10041F0D0
0x10041f101  test    eax, eax
0x10041f103  jz      short loc_10041F11B
0x10041f105  add     rdi, 0DF8h
0x10041f10c  mov     [rsp+3C8h+var_2D8], rdi
0x10041f114  mov     [rsp+3C8h+var_390], rdi
0x10041f119  jmp     short loc_10041F120
0x10041f11b  mov     rdi, [rsp+3C8h+var_390]
0x10041f120  mov     [rsp+3C8h+var_330], rdi
0x10041f128  mov     rax, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x10041f12f  mov     [rsp+3C8h+var_328], rax
0x10041f137  mov     rdx, gs:58h
0x10041f140  mov     [rsp+3C8h+var_2D0], rdx
0x10041f148  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f14f  mov     ecx, [rax]
0x10041f151  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f158  mov     esi, [rax]
0x10041f15a  add     rsi, [rdx+rcx*8]
0x10041f15e  mov     [rsp+3C8h+var_2C8], rsi
0x10041f166  mov     r9, [rsi+100h]
0x10041f16d  mov     [rsp+3C8h+var_338], r9
0x10041f175  test    r9, r9
0x10041f178  jnz     short loc_10041F191
0x10041f17a  xor     ecx, ecx
0x10041f17c  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f182  mov     r9, [rsi+100h]
0x10041f189  mov     [rsp+3C8h+var_338], r9
0x10041f191  mov     r9, [r9+218h]
0x10041f198  mov     [rsp+3C8h+var_318], r9
0x10041f1a0  mov     rax, [rsp+3C8h+var_330]
0x10041f1a8  mov     [rsp+3C8h+var_320], rax
0x10041f1b0  test    rdi, rdi
0x10041f1b3  jz      loc_10041F238
0x10041f1b9  cmp     r9, rdi
0x10041f1bc  jz      short loc_10041F238
0x10041f1be  mov     [rsp+3C8h+var_394], ebx
0x10041f1c2  cmp     dword ptr [r9+0A4h], 3
0x10041f1ca  jb      short loc_10041F221
0x10041f1cc  lea     rax, [r9+40h]
0x10041f1d0  mov     [rsp+3C8h+var_378], rax
0x10041f1d5  mov     r8d, [rax]
0x10041f1d8  mov     [rsp+3C8h+var_380], r8d
0x10041f1dd  nop     dword ptr [rax]
0x10041f1e0  test    r8d, r8d
0x10041f1e3  js      short loc_10041F219
0x10041f1e5  lea     edx, [r8+1]
0x10041f1e9  mov     [rsp+3C8h+var_354], edx
0x10041f1ed  mov     rcx, [rsp+3C8h+var_378]
0x10041f1f2  mov     eax, r8d
0x10041f1f5  lock cmpxchg [rcx], edx
0x10041f1f9  mov     [rsp+3C8h+var_350], eax
0x10041f1fd  jnz     short loc_10041F20A
0x10041f1ff  mov     [rsp+3C8h+var_394], ebx
0x10041f203  lock inc dword ptr [r9+28h]
0x10041f208  jmp     short loc_10041F221
0x10041f20a  mov     rax, [rsp+3C8h+var_378]
0x10041f20f  mov     r8d, [rax]
0x10041f212  mov     [rsp+3C8h+var_380], r8d
0x10041f217  jmp     short loc_10041F1E0
0x10041f219  mov     [rsp+3C8h+var_394], 80000000h
0x10041f221  mov     rdx, [rsp+3C8h+var_320]
0x10041f229  mov     rcx, [rsp+3C8h+var_328]
0x10041f231  call    cs:__imp_?BindCurrentTaskToGroup@SOS_ResourceManager@@QEAAXPEAVSOS_ResourceGroup@@@Z; SOS_ResourceManager::BindCurrentTaskToGroup(SOS_ResourceGroup *)
0x10041f237  nop
0x10041f238  nop     dword ptr [rax+rax]
0x10041f23c  nop     dword ptr [rax+00h]
0x10041f240  mov     [rsp+3C8h+var_398], 1
0x10041f248  mov     [rsp+3C8h+var_2C0], rbx
0x10041f250  xor     edx, edx; unsigned __int16
0x10041f252  mov     [rsp+3C8h+var_3A0], rbx; struct Worker *
0x10041f257  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x10041f25e  mov     [rsp+3C8h+var_3A8], rax; int (*)(int, int, int, int, char *)
0x10041f263  xor     r9d, r9d; unsigned __int8
0x10041f266  xor     r8d, r8d; unsigned __int8
0x10041f269  lea     rcx, [rsp+3C8h+var_268]; this
0x10041f271  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x10041f276  nop
0x10041f277  xor     ecx, ecx
0x10041f279  call    cs:__imp_?ResourceMonitorTask@ResourceMonitor@@SAPEAXPEAX@Z; ResourceMonitor::ResourceMonitorTask(void *)
0x10041f27f  nop
0x10041f280  lea     rcx, [rsp+3C8h+var_268]; this
0x10041f288  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10041f28d  nop
0x10041f28e  jmp     short loc_10041F292
0x10041f290  xor     ebx, ebx
0x10041f292  mov     rdx, gs:58h
0x10041f29b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f2a2  mov     ecx, [rax]
0x10041f2a4  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f2ab  mov     edi, [rax]
0x10041f2ad  add     rdi, [rdx+rcx*8]
0x10041f2b1  mov     rcx, [rdi+100h]
0x10041f2b8  test    rcx, rcx
0x10041f2bb  jnz     short loc_10041F2CA
0x10041f2bd  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f2c3  mov     rcx, [rdi+100h]
0x10041f2ca  cmp     dword ptr [rcx+22Ch], 0
0x10041f2d1  jz      short loc_10041F2D9
0x10041f2d3  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10041f2d9  cmp     [rsp+3C8h+var_398], 0
0x10041f2de  jnz     loc_10041F240
0x10041f2e4  mov     rcx, [rsp+3C8h+var_370]
0x10041f2e9  test    rcx, rcx
0x10041f2ec  jz      short loc_10041F2F7
0x10041f2ee  mov     rax, [rcx]
0x10041f2f1  xor     edx, edx
0x10041f2f3  call    qword ptr [rax+10h]
0x10041f2f6  nop
0x10041f2f7  lea     rcx, [rsp+3C8h+var_320]; this
0x10041f2ff  call    ??1AutoSwitchResourceGroup@SOS_ResourceManager@@QEAA@XZ; SOS_ResourceManager::AutoSwitchResourceGroup::~AutoSwitchResourceGroup(void)
0x10041f304  nop
0x10041f305  lea     rcx, [rsp+3C8h+var_390]; this
0x10041f30a  call    ??1SOS_AutoReleaseResourceGroup@@QEAA@XZ; SOS_AutoReleaseResourceGroup::~SOS_AutoReleaseResourceGroup(void)
0x10041f30f  nop
0x10041f310  mov     rcx, [rsp+3C8h+var_370]
0x10041f315  test    rcx, rcx
0x10041f318  jz      short loc_10041F325
0x10041f31a  mov     rax, [rcx]
0x10041f31d  mov     edx, 1
0x10041f322  call    qword ptr [rax]
0x10041f324  nop
0x10041f325  lea     rcx, [rsp+3C8h+var_240]; this
0x10041f32d  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10041f332  nop
0x10041f333  mov     rdx, gs:58h
0x10041f33c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041f343  mov     ecx, [rax]
0x10041f345  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041f34c  mov     ebx, [rax]
0x10041f34e  add     rbx, [rdx+rcx*8]
0x10041f352  mov     rcx, [rbx+100h]
0x10041f359  test    rcx, rcx
0x10041f35c  jnz     short loc_10041F36B
0x10041f35e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10041f364  mov     rcx, [rbx+100h]
0x10041f36b  cmp     dword ptr [rcx+22Ch], 0
0x10041f372  jz      short loc_10041F37A
0x10041f374  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10041f37a  mov     ecx, 149h
0x10041f37f  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x10041f385  xor     eax, eax
0x10041f387  mov     rcx, [rsp+3C8h+var_18]
0x10041f38f  xor     rcx, rsp; StackCookie
0x10041f392  call    __security_check_cookie
0x10041f397  lea     r11, [rsp+3C8h+var_8]
0x10041f39f  mov     rbx, [r11+10h]
0x10041f3a3  mov     rsi, [r11+18h]
0x10041f3a7  mov     rsp, r11
0x10041f3aa  pop     rdi
0x10041f3ab  retn
```
