# CTransportServer::Initialize(CMulticastSessionGroup *,tagWDS_INTERFACE_INFO *,IAppTransportServer *,CMulticastProfile *,CCryptSymKey *)

- ea: `0x1800148b4`
- end: `0x1800150b8`
- name: `?Initialize@CTransportServer@@QEAAKPEAVCMulticastSessionGroup@@PEAUtagWDS_INTERFACE_INFO@@PEAVIAppTransportServer@@PEAVCMulticastProfile@@PEAVCCryptSymKey@@@Z`
- size: `2052`
- prototype: `unsigned int __usercall@<eax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, struct CMulticastSessionGroup *@<rdx>, struct tagWDS_INTERFACE_INFO *@<r8>, struct IAppTransportServer *@<r9>, struct CMulticastProfile *, struct CCryptSymKey *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e70`

## callees

- `0x180003c0c`
- `0x18000e340`
- `0x1800106fc`
- `0x180011098`
- `0x180011a4c`
- `0x1800148b4`
- `0x1800150c0`
- `0x18001cac4`
- `0x1800221d4`
- `0x1800227d4`
- `0x1800229c0`
- `0x180023994`
- `0x180023b60`
- `0x1800247d4`
- `0x180025850`
- `0x180026670`
- `0x180026d3a`
- `0x180026d46`
- `0x180026d70`

## import_xrefs

- `KERNEL32!CreateMemoryResourceNotification` at `0x180014bd5`
- `KERNEL32!CreateMemoryResourceNotification` at `0x180014bd5`
- `KERNEL32!GetLastError` at `0x180014be7`
- `KERNEL32!GetLastError` at `0x180014be7`
- `KERNEL32!LeaveCriticalSection` at `0x180014d65`
- `KERNEL32!LeaveCriticalSection` at `0x180014db1`
- `KERNEL32!LeaveCriticalSection` at `0x180015029`
- `KERNEL32!LeaveCriticalSection` at `0x18001504e`
- `KERNEL32!LeaveCriticalSection` at `0x180014d65`
- `KERNEL32!LeaveCriticalSection` at `0x180014db1`
- `KERNEL32!LeaveCriticalSection` at `0x180015029`
- `KERNEL32!LeaveCriticalSection` at `0x18001504e`
- `KERNEL32!EnterCriticalSection` at `0x18001492b`
- `KERNEL32!EnterCriticalSection` at `0x180014d94`
- `KERNEL32!EnterCriticalSection` at `0x180014ffb`
- `KERNEL32!EnterCriticalSection` at `0x18001492b`
- `KERNEL32!EnterCriticalSection` at `0x180014d94`
- `KERNEL32!EnterCriticalSection` at `0x180014ffb`
- `ADVAPI32!RegCloseKey` at `0x180014a60`
- `ADVAPI32!RegCloseKey` at `0x180014afc`
- `ADVAPI32!RegCloseKey` at `0x180015080`
- `ADVAPI32!RegCloseKey` at `0x180014a60`
- `ADVAPI32!RegCloseKey` at `0x180014afc`
- `ADVAPI32!RegCloseKey` at `0x180015080`
- `ADVAPI32!RegOpenKeyExW` at `0x180014a8c`
- `ADVAPI32!RegOpenKeyExW` at `0x180014a8c`
- `WDSSRV!WdsEndpointOpen` at `0x180014f1c`
- `WDSSRV!WdsEndpointOpen` at `0x180014f1c`

## string_xrefs

- `0x180014a7e`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Protocol`
- `0x180014fcc`: `WDSMCTP[0x%x]: Local=%s:%u, Multicast=%s:%u - Endpoints opened.`

## pseudocode

```c
__int64 __fastcall CTransportServer::Initialize(
        LPCRITICAL_SECTION lpCriticalSection,
        struct CMulticastSessionGroup *a2,
        struct tagWDS_INTERFACE_INFO *a3,
        struct _RTL_CRITICAL_SECTION_DEBUG *a4,
        struct CMulticastProfile *a5,
        struct CCryptSymKey *a6)
{
  int v10; // r14d
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  const char *v13; // rdx
  unsigned int LocalMacAddress; // esi
  size_t v15; // r8
  const char *v16; // rdx
  void *v17; // rdx
  void *v18; // rax
  HKEY v19; // rcx
  const char *v20; // rdx
  const char *v21; // rdx
  HKEY v22; // rcx
  char *v23; // r9
  LONG RecursionCount; // ecx
  struct _RTL_CRITICAL_SECTION_DEBUG *DebugInfo; // r10
  int OwningThread_high; // r11d
  int v27; // ebx
  const char *v28; // rdx
  const char *v29; // rdx
  HANDLE MemoryResourceNotification; // rax
  DWORD LastError; // eax
  const char *v32; // rdx
  const char *v33; // rdx
  const char *v34; // rdx
  const char *v35; // rdx
  const char *v36; // rdx
  const char *v37; // rdx
  const char *v38; // rdx
  const char *v39; // rdx
  const char *v40; // rdx
  const char *v41; // rdx
  const char *v42; // rdx
  int v43; // esi
  const char *v44; // rdx
  size_t OwningThread_low; // r8
  const unsigned __int16 *v46; // rbx
  const unsigned __int16 *v47; // r8
  HKEY hKey; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v50[2]; // [rsp+50h] [rbp-B8h] BYREF
  void *v51; // [rsp+58h] [rbp-B0h]
  _QWORD v52[3]; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v53; // [rsp+78h] [rbp-90h]
  __int128 v54; // [rsp+88h] [rbp-80h] BYREF
  unsigned int LockSemaphore; // [rsp+98h] [rbp-70h]
  _QWORD Src[2]; // [rsp+A0h] [rbp-68h] BYREF
  size_t Size; // [rsp+B0h] [rbp-58h]
  _QWORD v58[2]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v59; // [rsp+C8h] [rbp-40h]
  _QWORD v60[2]; // [rsp+D0h] [rbp-38h] BYREF
  int OwningThread; // [rsp+E0h] [rbp-28h]
  int v62; // [rsp+E8h] [rbp-20h] BYREF
  char v63; // [rsp+ECh] [rbp-1Ch] BYREF
  int v64; // [rsp+178h] [rbp+70h] BYREF
  char v65; // [rsp+17Ch] [rbp+74h] BYREF
  int v66; // [rsp+208h] [rbp+100h] BYREF
  _DWORD v67[28]; // [rsp+210h] [rbp+108h] BYREF
  unsigned int (*v68)(void *, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *); // [rsp+280h] [rbp+178h]
  LPCRITICAL_SECTION v69; // [rsp+288h] [rbp+180h]
  int v70; // [rsp+2B0h] [rbp+1A8h]
  void (__fastcall *v71)(LPCRITICAL_SECTION, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *, unsigned int); // [rsp+2B8h] [rbp+1B0h]
  LPCRITICAL_SECTION v72; // [rsp+2C0h] [rbp+1B8h]
  int v73; // [rsp+2E8h] [rbp+1E0h]
  void (*v74)(void *, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *); // [rsp+2F0h] [rbp+1E8h]
  LPCRITICAL_SECTION v75; // [rsp+2F8h] [rbp+1F0h]
  int v76; // [rsp+320h] [rbp+218h]
  unsigned int (*v77)(void *, void *, struct tagWDS_ENDPOINT *, struct tagWDS_ENDPOINT *, void *, unsigned int); // [rsp+328h] [rbp+220h]
  LPCRITICAL_SECTION v78; // [rsp+330h] [rbp+228h]
  int v79; // [rsp+358h] [rbp+250h]
  int v80; // [rsp+360h] [rbp+258h]
  int v81; // [rsp+390h] [rbp+288h]
  void (__fastcall *v82)(void *, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *); // [rsp+398h] [rbp+290h]
  LPCRITICAL_SECTION v83; // [rsp+3A0h] [rbp+298h]
  int v84; // [rsp+3C8h] [rbp+2C0h]
  int SpinCount; // [rsp+3D0h] [rbp+2C8h]
  int v86; // [rsp+400h] [rbp+2F8h]
  int v87; // [rsp+408h] [rbp+300h]
  int v88; // [rsp+438h] [rbp+330h]
  int LockSemaphore_high; // [rsp+440h] [rbp+338h]
  int v90; // [rsp+470h] [rbp+368h]
  int v91; // [rsp+478h] [rbp+370h]
  int v92; // [rsp+4A8h] [rbp+3A0h]
  unsigned int (__fastcall *v93)(void *, struct tagWDS_INTERFACE_INFO *, struct tagWDS_IP_ADDRESS6 *); // [rsp+4B0h] [rbp+3A8h]
  LPCRITICAL_SECTION v94; // [rsp+4B8h] [rbp+3B0h]

  v51 = a5;
  v66 = 0;
  memset_0(v67, 0, 0x2D0u);
  hKey = 0;
  v50[0] = 0;
  EnterCriticalSection(lpCriticalSection);
  v10 = 1;
  LODWORD(lpCriticalSection[55].OwningThread) = _InterlockedIncrement((volatile signed __int32 *)&CTransportServer::sm_uNextSessionId);
  v11 = *(_OWORD *)a3;
  *(_QWORD *)&v54 = 0;
  *(_OWORD *)&lpCriticalSection[1].LockCount = v11;
  *((_QWORD *)&v54 + 1) = 0;
  v12 = *((_OWORD *)a3 + 1);
  Src[0] = 0;
  Src[1] = 0;
  *(_OWORD *)&lpCriticalSection[1].LockSemaphore = v12;
  LODWORD(Size) = 0;
  *(_OWORD *)&lpCriticalSection[2].DebugInfo = *((_OWORD *)a3 + 2);
  LockSemaphore = (unsigned int)lpCriticalSection[1].LockSemaphore;
  memmove_0(&v54, &lpCriticalSection[1].LockCount, LockSemaphore);
  v53 = LockSemaphore;
  *(_OWORD *)&v52[1] = v54;
  LocalMacAddress = CNetworkAddress::GetLocalMacAddress(&v52[1], Src);
  if ( !LocalMacAddress )
  {
    v15 = (unsigned int)Size;
    HIDWORD(lpCriticalSection[2].DebugInfo) = Size;
    memmove_0((char *)&lpCriticalSection[1].LockSemaphore + 4, Src, v15);
  }
  if ( !ElValidateWin32(LocalMacAddress, v13, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x7Au) )
  {
    LocalMacAddress = CNetworkAddress::GetInterfaceName(
                        (struct tagWDS_INTERFACE_INFO *)&lpCriticalSection[1].LockCount,
                        (unsigned __int16 **)&lpCriticalSection[2].OwningThread);
    if ( !ElValidateWin32(LocalMacAddress, v16, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0x83u) )
    {
      v17 = v51;
      lpCriticalSection[1].DebugInfo = a4;
      lpCriticalSection[56].SpinCount = (ULONG_PTR)a2;
      memmove_0(&lpCriticalSection[57], v17, 0x9Cu);
      lpCriticalSection[353].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)a6;
      v18 = (void *)CStopwatch::CurrentMs((CStopwatch *)&lpCriticalSection[357]);
      v19 = hKey;
      lpCriticalSection[55].LockSemaphore = v18;
      if ( v19 )
      {
        RegCloseKey(v19);
        hKey = 0;
      }
      LocalMacAddress = RegOpenKeyExW(
                          HKEY_LOCAL_MACHINE,
                          L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Protocol",
                          0,
                          0x20119u,
                          &hKey);
      if ( !ElValidateWin32(LocalMacAddress, v20, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0xA6u) )
      {
        LocalMacAddress = CRegKey::GetValueDwordWithDefault((CRegKey *)&hKey, L"TpClientPortOffset", 0, v50);
        if ( !ElValidateWin32(LocalMacAddress, v21, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0xACu) )
        {
          v22 = hKey;
          WORD2(lpCriticalSection[356].SpinCount) = v50[0];
          if ( v22 )
          {
            RegCloseKey(v22);
            hKey = 0;
          }
          if ( HIWORD(lpCriticalSection[58].RecursionCount) == 2 )
          {
            v23 = (char *)qword_1800336E8 + 1080;
            *(_QWORD *)&lpCriticalSection[353].LockCount = (char *)qword_1800336E8 + 1080;
          }
          else
          {
            v23 = *(char **)&lpCriticalSection[353].LockCount;
          }
          RecursionCount = lpCriticalSection[58].RecursionCount;
          DebugInfo = lpCriticalSection[353].DebugInfo;
          OwningThread_high = HIDWORD(lpCriticalSection[58].OwningThread);
          v27 = (int)lpCriticalSection[58].LockSemaphore;
          HIDWORD(lpCriticalSection[353].OwningThread) = lpCriticalSection[55].OwningThread;
          LODWORD(lpCriticalSection[353].OwningThread) = RecursionCount;
          LODWORD(lpCriticalSection[355].SpinCount) = 1;
          if ( (unsigned __int16)RecursionCount == 1
            || HIWORD(RecursionCount) == 1
            || (unsigned __int16)RecursionCount == 2
            || HIWORD(RecursionCount) == 2 )
          {
            lpCriticalSection[353].SpinCount = (ULONG_PTR)v23;
            lpCriticalSection[354].DebugInfo = DebugInfo;
            HIDWORD(lpCriticalSection[355].LockSemaphore) = v27;
            LODWORD(lpCriticalSection[355].LockSemaphore) = OwningThread_high;
          }
          LocalMacAddress = CMcTpConstructor::CalculateHeaderLen((CMcTpConstructor *)&lpCriticalSection[353].OwningThread);
          ElValidateWin32(LocalMacAddress, v28, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0x61u);
          if ( !ElValidateWin32(
                  LocalMacAddress,
                  v29,
                  "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                  0xC1u) )
          {
            if ( !HIDWORD(lpCriticalSection[59].DebugInfo)
              || (MemoryResourceNotification = CreateMemoryResourceNotification(LowMemoryResourceNotification),
                  (*(_QWORD *)&lpCriticalSection[356].LockCount = MemoryResourceNotification) != 0) )
            {
              LocalMacAddress = CTimer<CTpSrvClients>::Initialize(&lpCriticalSection[61].OwningThread, 0xFFFFFFFE);
              if ( !ElValidateWin32(
                      LocalMacAddress,
                      v33,
                      "base\\eco\\wds\\transport\\server\\mc\\tpsrvclients.cpp",
                      0x3Fu) )
              {
                LocalMacAddress = CTimer<CTpSrvClients>::Initialize(
                                    &lpCriticalSection[63],
                                    *((_DWORD *)lpCriticalSection[132].LockSemaphore + 573));
                ElValidateWin32(LocalMacAddress, v35, "base\\eco\\wds\\transport\\server\\mc\\tpsrvclients.cpp", 0x4Au);
              }
              if ( !ElValidateWin32(
                      LocalMacAddress,
                      v34,
                      "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                      0xD5u) )
              {
                LocalMacAddress = CTpSrvKickDemote::Initialize((CTpSrvKickDemote *)&lpCriticalSection[133]);
                if ( !ElValidateWin32(
                        LocalMacAddress,
                        v36,
                        "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                        0xDCu) )
                {
                  LocalMacAddress = 0;
                  if ( ElValidateWin32(0, v37, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0xE4u)
                    || ElValidateWin32(0, v38, "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp", 0xEBu) )
                  {
LABEL_47:
                    LeaveCriticalSection(lpCriticalSection);
                    goto LABEL_48;
                  }
                  if ( !ElValidateWin32(0, v39, "base\\eco\\wds\\transport\\server\\mc\\tpsrvqccstate.cpp", 0x41u) )
                  {
                    LocalMacAddress = CTimer<CTpSrvQCCState>::Initialize(&lpCriticalSection[334].SpinCount);
                    ElValidateWin32(
                      LocalMacAddress,
                      v41,
                      "base\\eco\\wds\\transport\\server\\mc\\tpsrvqccstate.cpp",
                      0x45u);
                  }
                  if ( !ElValidateWin32(
                          LocalMacAddress,
                          v40,
                          "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                          0xEFu) )
                  {
                    LocalMacAddress = CTpSrvDataState::Initialize((CTpSrvDataState *)&lpCriticalSection[336].LockCount);
                    if ( !ElValidateWin32(
                            LocalMacAddress,
                            v42,
                            "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                            0xF3u) )
                    {
                      v10 = 0;
                      LeaveCriticalSection(lpCriticalSection);
                      memset_0(&lpCriticalSection[2].LockSemaphore, 0, 0x41Cu);
                      LODWORD(lpCriticalSection[2].LockSemaphore) = 1052;
                      HIDWORD(lpCriticalSection[2].LockSemaphore) = 0;
                      v66 = 65793;
                      EnterCriticalSection(lpCriticalSection);
                      v43 = LODWORD(lpCriticalSection[1].LockSemaphore) == 16
                          ? HIDWORD(lpCriticalSection[60].DebugInfo)
                          : LODWORD(lpCriticalSection[60].DebugInfo);
                      LeaveCriticalSection(lpCriticalSection);
                      v67[12] = 131332;
                      v67[0] = v43 + 1024;
                      v67[14] = 1;
                      v68 = CTransportServer::_EndpointQueryAdd;
                      v67[26] = 197639;
                      v71 = CTransportServer::_EndpointAddFailed;
                      v69 = lpCriticalSection;
                      v74 = CTransportServer::_EndpointRemoved;
                      v77 = CTransportServer::_RecvRequest;
                      v82 = CTransportServer::_MulticastEndpointAdded;
                      SpinCount = lpCriticalSection[57].SpinCount;
                      v87 = (int)lpCriticalSection[57].LockSemaphore;
                      LockSemaphore_high = HIDWORD(lpCriticalSection[57].LockSemaphore);
                      v93 = CTransportServer::_MulticastLeaseObtained;
                      v70 = 394247;
                      v72 = lpCriticalSection;
                      v73 = 328711;
                      v75 = lpCriticalSection;
                      v76 = 66567;
                      v78 = lpCriticalSection;
                      v79 = 262404;
                      v80 = 1;
                      v81 = 263175;
                      v83 = lpCriticalSection;
                      v84 = 459009;
                      v86 = 327937;
                      v88 = 393473;
                      v90 = 524548;
                      v91 = 1;
                      v92 = 590855;
                      v94 = lpCriticalSection;
                      LocalMacAddress = WdsEndpointOpen(
                                          *((_QWORD *)qword_1800336E8 + 36),
                                          &lpCriticalSection[2].LockSemaphore,
                                          13,
                                          &v66,
                                          &lpCriticalSection[55].LockCount);
                      if ( !ElValidateWin32(
                              LocalMacAddress,
                              v44,
                              "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                              0x129u) )
                      {
                        if ( g_ErrLibTraceFunction )
                        {
                          v59 = HIDWORD(lpCriticalSection[29].LockSemaphore);
                          v58[0] = 0;
                          v58[1] = 0;
                          memmove_0(v58, &lpCriticalSection[29].RecursionCount, v59);
                          CIPString::Initialize((CIPString *)&v62, (struct tagWDS_IP_ADDRESS6 *)v58);
                          OwningThread_low = LODWORD(lpCriticalSection[3].OwningThread);
                          v46 = (const unsigned __int16 *)&v63;
                          OwningThread = (int)lpCriticalSection[3].OwningThread;
                          if ( v62 )
                            v46 = L"<<Failed>>";
                          v60[0] = 0;
                          v60[1] = 0;
                          memmove_0(v60, &lpCriticalSection[3], OwningThread_low);
                          CIPString::Initialize((CIPString *)&v64, (struct tagWDS_IP_ADDRESS6 *)v60);
                          v47 = (const unsigned __int16 *)&v65;
                          if ( v64 )
                            v47 = L"<<Failed>>";
                          g_ErrLibTraceFunction(
                            L"WDSMCTP[0x%x]: Local=%s:%u, Multicast=%s:%u - Endpoints opened.",
                            LODWORD(lpCriticalSection[55].OwningThread),
                            v47,
                            WORD2(lpCriticalSection[2].SpinCount),
                            v46,
                            LOWORD(lpCriticalSection[29].LockCount));
                        }
                        EnterCriticalSection(lpCriticalSection);
                        CPerfCounters::Batch((CPerfCounters *)&qword_1800336A0, 1u, 12);
                        HIDWORD(lpCriticalSection[56].OwningThread) = 1;
                        v10 = 0;
                        LeaveCriticalSection(lpCriticalSection);
                      }
                    }
                  }
                }
              }
            }
            else
            {
              LastError = GetLastError();
              LocalMacAddress = ElValidateWin32(
                                  LastError,
                                  v32,
                                  "base\\eco\\wds\\transport\\server\\mc\\transportserver.cpp",
                                  0xCCu);
            }
          }
        }
      }
    }
  }
  if ( LocalMacAddress )
    CTransportServer::Shutdown(lpCriticalSection);
  if ( v10 )
    goto LABEL_47;
LABEL_48:
  if ( hKey )
    RegCloseKey(hKey);
  return LocalMacAddress;
}

```

## disassembly

```asm
0x1800148b4  mov     rax, rsp
0x1800148b7  mov     [rax+10h], rbx
0x1800148bb  mov     [rax+18h], rsi
0x1800148bf  mov     [rax+20h], rdi
0x1800148c3  push    rbp
0x1800148c4  push    r12
0x1800148c6  push    r13
0x1800148c8  push    r14
0x1800148ca  push    r15
0x1800148cc  lea     rbp, [rax-418h]
0x1800148d3  sub     rsp, 4F0h
0x1800148da  mov     rax, cs:__security_cookie
0x1800148e1  xor     rax, rsp
0x1800148e4  mov     [rbp+410h+var_30], rax
0x1800148eb  mov     rax, [rbp+410h+arg_20]
0x1800148f2  mov     rbx, r8
0x1800148f5  mov     r13, rdx
0x1800148f8  mov     [rsp+510h+var_4C0], rax
0x1800148fd  mov     rdi, rcx
0x180014900  xor     esi, esi
0x180014902  xor     edx, edx; Val
0x180014904  mov     [rbp+410h+var_310], esi
0x18001490a  mov     r8d, 2D0h; Size
0x180014910  lea     rcx, [rbp+410h+var_308]; void *
0x180014917  mov     r12, r9
0x18001491a  call    memset_0
0x18001491f  mov     rcx, rdi; lpCriticalSection
0x180014922  mov     [rsp+510h+hKey], rsi
0x180014927  mov     [rsp+510h+var_4C8], esi
0x18001492b  call    cs:__imp_EnterCriticalSection
0x180014931  lea     ecx, [rsi+1]
0x180014934  mov     r14d, ecx
0x180014937  mov     eax, ecx
0x180014939  lock xadd cs:?sm_uNextSessionId@CTransportServer@@0KA, eax; ulong CTransportServer::sm_uNextSessionId
0x180014941  lea     r15, [rdi+30h]
0x180014945  add     eax, ecx
0x180014947  mov     [rdi+8A8h], eax
0x18001494d  lea     rcx, [rbp+410h+var_490]; void *
0x180014951  movups  xmm0, xmmword ptr [rbx]
0x180014954  xor     eax, eax
0x180014956  mov     rdx, r15; Src
0x180014959  mov     qword ptr [rbp+410h+var_490], rax
0x18001495d  movups  xmmword ptr [r15], xmm0
0x180014961  mov     qword ptr [rbp+410h+var_490+8], rax
0x180014965  movups  xmm1, xmmword ptr [rbx+10h]
0x180014969  mov     [rbp+410h+Src], rax
0x18001496d  mov     [rbp+410h+var_470], rax
0x180014971  movups  xmmword ptr [r15+10h], xmm1
0x180014976  mov     dword ptr [rbp+410h+Size], eax
0x180014979  movups  xmm0, xmmword ptr [rbx+20h]
0x18001497d  movups  xmmword ptr [r15+20h], xmm0
0x180014982  mov     r8d, [r15+10h]; Size
0x180014986  mov     [rbp+410h+var_480], r8d
0x18001498a  call    memmove_0
0x18001498f  movups  xmm0, [rbp+410h+var_490]
0x180014993  mov     eax, [rbp+410h+var_480]
0x180014996  lea     rdx, [rbp+410h+Src]
0x18001499a  lea     rcx, [rsp+510h+var_4B8+8]
0x18001499f  mov     [rsp+510h+var_4A0], eax
0x1800149a3  movaps  xmmword ptr [rsp+510h+var_4B8+8], xmm0
0x1800149a8  call    ?GetLocalMacAddress@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAUtagWDS_MAC_ADDRESS@@@Z; CNetworkAddress::GetLocalMacAddress(tagWDS_IP_ADDRESS6,tagWDS_MAC_ADDRESS *)
0x1800149ad  mov     esi, eax
0x1800149af  test    eax, eax
0x1800149b1  jnz     short loc_1800149CA
0x1800149b3  mov     eax, dword ptr [rbp+410h+Size]
0x1800149b6  lea     rcx, [r15+14h]; void *
0x1800149ba  mov     r8d, eax; Size
0x1800149bd  mov     [r15+24h], eax
0x1800149c1  lea     rdx, [rbp+410h+Src]; Src
0x1800149c5  call    memmove_0
0x1800149ca  mov     r9d, 7Ah ; 'z'; unsigned int
0x1800149d0  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800149d7  mov     ecx, esi; unsigned int
0x1800149d9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800149de  test    eax, eax
0x1800149e0  jnz     loc_180015031
0x1800149e6  lea     rdx, [rdi+60h]; unsigned __int16 **
0x1800149ea  mov     rcx, r15; struct tagWDS_INTERFACE_INFO *
0x1800149ed  call    ?GetInterfaceName@CNetworkAddress@@SAKPEAUtagWDS_INTERFACE_INFO@@PEAPEAG@Z; CNetworkAddress::GetInterfaceName(tagWDS_INTERFACE_INFO *,ushort * *)
0x1800149f2  mov     r9d, 83h; unsigned int
0x1800149f8  lea     r8, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x1800149ff  mov     ecx, eax; unsigned int
0x180014a01  mov     esi, eax
0x180014a03  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014a08  xor     r15d, r15d
0x180014a0b  test    eax, eax
0x180014a0d  jnz     loc_180015034
0x180014a13  mov     rdx, [rsp+510h+var_4C0]; Src
0x180014a18  lea     rcx, [rdi+8E8h]; void *
0x180014a1f  mov     r8d, 9Ch; Size
0x180014a25  mov     [rdi+28h], r12
0x180014a29  mov     [rdi+8E0h], r13
0x180014a30  call    memmove_0
0x180014a35  mov     rax, [rbp+410h+arg_28]
0x180014a3c  lea     rcx, [rdi+37C8h]; this
0x180014a43  mov     [rdi+3728h], rax
0x180014a4a  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x180014a4f  mov     rcx, [rsp+510h+hKey]; hKey
0x180014a54  mov     [rdi+8B0h], rax
0x180014a5b  test    rcx, rcx
0x180014a5e  jz      short loc_180014A6B
0x180014a60  call    cs:__imp_RegCloseKey
0x180014a66  mov     [rsp+510h+hKey], r15
0x180014a6b  lea     rax, [rsp+510h+hKey]
0x180014a70  mov     r9d, 20119h; samDesired
0x180014a76  xor     r8d, r8d; ulOptions
0x180014a79  mov     [rsp+510h+phkResult], rax; phkResult
0x180014a7e  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x180014a85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014a8c  call    cs:__imp_RegOpenKeyExW
0x180014a92  lea     r12, aBaseEcoWdsTran_5; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180014a99  mov     r9d, 0A6h; unsigned int
0x180014a9f  mov     r8, r12; char *
0x180014aa2  mov     ecx, eax; unsigned int
0x180014aa4  mov     esi, eax
0x180014aa6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014aab  test    eax, eax
0x180014aad  jnz     loc_180015034
0x180014ab3  lea     r9, [rsp+510h+var_4C8]; unsigned int *
0x180014ab8  xor     r8d, r8d; unsigned int
0x180014abb  lea     rdx, aTpclientportof; "TpClientPortOffset"
0x180014ac2  lea     rcx, [rsp+510h+hKey]; this
0x180014ac7  call    ?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180014acc  mov     r9d, 0ACh; unsigned int
0x180014ad2  mov     r8, r12; char *
0x180014ad5  mov     ecx, eax; unsigned int
0x180014ad7  mov     esi, eax
0x180014ad9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014ade  test    eax, eax
0x180014ae0  jnz     loc_180015034
0x180014ae6  mov     rcx, [rsp+510h+hKey]; hKey
0x180014aeb  movzx   eax, word ptr [rsp+510h+var_4C8]
0x180014af0  mov     [rdi+37C4h], ax
0x180014af7  test    rcx, rcx
0x180014afa  jz      short loc_180014B07
0x180014afc  call    cs:__imp_RegCloseKey
0x180014b02  mov     [rsp+510h+hKey], r15
0x180014b07  mov     esi, 2
0x180014b0c  cmp     [rdi+91Eh], si
0x180014b13  jnz     short loc_180014B2C
0x180014b15  mov     r9, cs:qword_1800336E8
0x180014b1c  add     r9, 438h
0x180014b23  mov     [rdi+3730h], r9
0x180014b2a  jmp     short loc_180014B33
0x180014b2c  mov     r9, [rdi+3730h]
0x180014b33  mov     ecx, [rdi+91Ch]
0x180014b39  lea     rdx, [rdi+3738h]
0x180014b40  mov     eax, [rdi+8A8h]
0x180014b46  mov     r8d, ecx
0x180014b49  mov     r10, [rdi+3728h]
0x180014b50  mov     r13d, r14d
0x180014b53  mov     r11d, [rdi+924h]
0x180014b5a  mov     ebx, [rdi+928h]
0x180014b60  mov     [rdx+4], eax
0x180014b63  shr     r8d, 10h
0x180014b67  movzx   eax, cx
0x180014b6a  mov     [rdx], ecx
0x180014b6c  mov     [rdx+60h], r14d
0x180014b70  cmp     eax, r14d
0x180014b73  jz      short loc_180014B85
0x180014b75  cmp     r8w, r13w
0x180014b79  jz      short loc_180014B85
0x180014b7b  cmp     eax, esi
0x180014b7d  jz      short loc_180014B85
0x180014b7f  cmp     r8w, si
0x180014b83  jnz     short loc_180014B94
0x180014b85  mov     [rdx+10h], r9
0x180014b89  mov     [rdx+18h], r10
0x180014b8d  mov     [rdx+5Ch], ebx
0x180014b90  mov     [rdx+58h], r11d
0x180014b94  mov     rcx, rdx; this
0x180014b97  call    ?CalculateHeaderLen@CMcTpConstructor@@AEAAKXZ; CMcTpConstructor::CalculateHeaderLen(void)
0x180014b9c  mov     r9d, 61h ; 'a'; unsigned int
0x180014ba2  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x180014ba9  mov     ecx, eax; unsigned int
0x180014bab  mov     esi, eax
0x180014bad  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014bb2  mov     r9d, 0C1h; unsigned int
0x180014bb8  mov     r8, r12; char *
0x180014bbb  mov     ecx, esi; unsigned int
0x180014bbd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014bc2  test    eax, eax
0x180014bc4  jnz     loc_180015034
0x180014bca  cmp     [rdi+93Ch], r15d
0x180014bd1  jz      short loc_180014C04
0x180014bd3  xor     ecx, ecx; NotificationType
0x180014bd5  call    cs:__imp_CreateMemoryResourceNotification
0x180014bdb  mov     [rdi+37A8h], rax
0x180014be2  test    rax, rax
0x180014be5  jnz     short loc_180014C04
0x180014be7  call    cs:__imp_GetLastError
0x180014bed  mov     r9d, 0CCh; unsigned int
0x180014bf3  mov     r8, r12; char *
0x180014bf6  mov     ecx, eax; unsigned int
0x180014bf8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014bfd  mov     esi, eax
0x180014bff  jmp     loc_180015034
0x180014c04  lea     rbx, [rdi+988h]
0x180014c0b  mov     r9d, 0FFFFFFFEh
0x180014c11  lea     rcx, [rbx+10h]; Parameter
0x180014c15  mov     dword ptr [rsp+510h+phkResult], r9d; DWORD
0x180014c1a  mov     rdx, rbx
0x180014c1d  call    ?Initialize@?$CTimer@VCTpSrvClients@@@@QEAAKPEAVCTpSrvClients@@PEAXKK1K@Z; CTimer<CTpSrvClients>::Initialize(CTpSrvClients *,void *,ulong,ulong,void *,ulong)
0x180014c22  mov     r9d, 3Fh ; '?'; unsigned int
0x180014c28  lea     r8, aBaseEcoWdsTran_13; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180014c2f  mov     ecx, eax; unsigned int
0x180014c31  mov     esi, eax
0x180014c33  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014c38  test    eax, eax
0x180014c3a  jnz     short loc_180014C71
0x180014c3c  mov     rax, [rbx+0B30h]
0x180014c43  lea     rcx, [rbx+50h]; Parameter
0x180014c47  mov     rdx, rbx
0x180014c4a  mov     r9d, [rax+8F4h]
0x180014c51  mov     dword ptr [rsp+510h+phkResult], r9d; DWORD
0x180014c56  call    ?Initialize@?$CTimer@VCTpSrvClients@@@@QEAAKPEAVCTpSrvClients@@PEAXKK1K@Z; CTimer<CTpSrvClients>::Initialize(CTpSrvClients *,void *,ulong,ulong,void *,ulong)
0x180014c5b  mov     r9d, 4Ah ; 'J'; unsigned int
0x180014c61  lea     r8, aBaseEcoWdsTran_13; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180014c68  mov     ecx, eax; unsigned int
0x180014c6a  mov     esi, eax
0x180014c6c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014c71  mov     r9d, 0D5h; unsigned int
0x180014c77  mov     r8, r12; char *
0x180014c7a  mov     ecx, esi; unsigned int
0x180014c7c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014c81  test    eax, eax
0x180014c83  jnz     loc_180015034
0x180014c89  lea     rcx, [rdi+14C8h]; this
0x180014c90  call    ?Initialize@CTpSrvKickDemote@@QEAAKXZ; CTpSrvKickDemote::Initialize(void)
0x180014c95  mov     r9d, 0DCh; unsigned int
0x180014c9b  mov     r8, r12; char *
0x180014c9e  mov     ecx, eax; unsigned int
0x180014ca0  mov     esi, eax
0x180014ca2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014ca7  test    eax, eax
0x180014ca9  jnz     loc_180015034
0x180014caf  mov     r9d, 0E4h; unsigned int
0x180014cb5  mov     r8, r12; char *
0x180014cb8  xor     ecx, ecx; unsigned int
0x180014cba  mov     esi, r15d
0x180014cbd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014cc2  test    eax, eax
0x180014cc4  jnz     loc_180015045
0x180014cca  mov     r9d, 0EBh; unsigned int
0x180014cd0  mov     r8, r12; char *
0x180014cd3  xor     ecx, ecx; unsigned int
0x180014cd5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014cda  test    eax, eax
0x180014cdc  jnz     loc_180015045
0x180014ce2  lea     r9d, [rax+41h]; unsigned int
0x180014ce6  xor     ecx, ecx; unsigned int
0x180014ce8  lea     r8, aBaseEcoWdsTran_2; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180014cef  lea     rbx, [rdi+33D8h]
0x180014cf6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014cfb  test    eax, eax
0x180014cfd  jnz     short loc_180014D21
0x180014cff  lea     rcx, [rbx+78h]; Parameter
0x180014d03  mov     rdx, rbx
0x180014d06  call    ?Initialize@?$CTimer@VCTpSrvQCCState@@@@QEAAKPEAVCTpSrvQCCState@@PEAXKK1K@Z; CTimer<CTpSrvQCCState>::Initialize(CTpSrvQCCState *,void *,ulong,ulong,void *,ulong)
0x180014d0b  mov     r9d, 45h ; 'E'; unsigned int
0x180014d11  lea     r8, aBaseEcoWdsTran_2; "base\\eco\\wds\\transport\\server\\mc\\"...
0x180014d18  mov     ecx, eax; unsigned int
0x180014d1a  mov     esi, eax
0x180014d1c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014d21  mov     r9d, 0EFh; unsigned int
0x180014d27  mov     r8, r12; char *
0x180014d2a  mov     ecx, esi; unsigned int
0x180014d2c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014d31  test    eax, eax
0x180014d33  jnz     loc_180015034
0x180014d39  lea     rcx, [rdi+3488h]; this
0x180014d40  call    ?Initialize@CTpSrvDataState@@QEAAKXZ; CTpSrvDataState::Initialize(void)
0x180014d45  mov     r9d, 0F3h; unsigned int
0x180014d4b  mov     r8, r12; char *
0x180014d4e  mov     ecx, eax; unsigned int
0x180014d50  mov     esi, eax
0x180014d52  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180014d57  test    eax, eax
0x180014d59  jnz     loc_180015034
0x180014d5f  mov     rcx, rdi; lpCriticalSection
0x180014d62  mov     r14d, r15d
0x180014d65  call    cs:__imp_LeaveCriticalSection
0x180014d6b  lea     rbx, [rdi+68h]
0x180014d6f  mov     esi, 41Ch
0x180014d74  mov     r8d, esi; Size
0x180014d77  mov     rcx, rbx; void *
0x180014d7a  xor     edx, edx; Val
0x180014d7c  call    memset_0
0x180014d81  mov     rcx, rdi; lpCriticalSection
0x180014d84  mov     [rbx], esi
0x180014d86  mov     [rdi+6Ch], r15d
0x180014d8a  mov     [rbp+410h+var_310], 10101h
0x180014d94  call    cs:__imp_EnterCriticalSection
0x180014d9a  cmp     dword ptr [rdi+40h], 10h
0x180014d9e  jnz     short loc_180014DA8
0x180014da0  mov     esi, [rdi+964h]
0x180014da6  jmp     short loc_180014DAE
0x180014da8  mov     esi, [rdi+960h]
0x180014dae  mov     rcx, rdi; lpCriticalSection
0x180014db1  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```
