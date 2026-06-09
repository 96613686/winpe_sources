# PfSvGlobalsStart

- ea: `0x180081b6c`
- end: `0x180081fe8`
- name: `PfSvGlobalsStart`
- size: `1148`
- prototype: `ULONG __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073494`

## callees

- `0x1800382e0`
- `0x18003a2ac`
- `0x180068ae0`
- `0x18007975c`
- `0x180081b6c`
- `0x180081ff0`
- `0x1800825d8`
- `0x180083140`
- `0x1800831d8`
- `0x180083234`
- `0x180085a50`
- `0x18008ff70`
- `0x1800b645a`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x180081c5d`
- `ntdll!RtlGetVersion` at `0x180081c5d`
- `ntdll!NtQuerySystemInformation` at `0x180081ca4`
- `ntdll!NtQuerySystemInformation` at `0x180081ca4`
- `ntdll!RtlNtStatusToDosError` at `0x180081c69`
- `ntdll!RtlNtStatusToDosError` at `0x180081c69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180081d20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180081d20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081e76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081eac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081e76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081eac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180081bec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180081d78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180081bec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180081d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180081ed5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180081ed5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180081eb9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180081eb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081ce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180081ce8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180081cfe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180081cfe`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180081c06`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180081c06`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180081c8e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180081c8e`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsVaMgrAlloc` at `0x180081c27`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!PfsVaMgrAlloc` at `0x180081c27`

## string_xrefs

- `0x180081bc1`: `StaticConfig`
- `0x180081db2`: `ServiceFlags`
- `0x180081eb2`: `kernelbase.dll`

## pseudocode

```c
ULONG __fastcall PfSvGlobalsStart(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  HKEY *v3; // rbx
  ULONG result; // eax
  HANDLE v5; // rax
  __int64 v6; // rax
  int Version; // eax
  unsigned __int128 v8; // rax
  DWORD CurrentThreadId; // eax
  HANDLE v10; // rax
  HANDLE EventW; // rax
  HKEY *v12; // rbx
  unsigned __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  HMODULE LibraryW; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  int v21; // [rsp+64h] [rbp+Ch]
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  int v23; // [rsp+6Ch] [rbp+14h]

  v23 = HIDWORD(a2);
  v21 = HIDWORD(a1);
  v2 = *(_QWORD *)&PfSvcGlobals;
  Type = 0;
  cbData = 0;
  v3 = (HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL);
  result = PfSvServiceRegistryKeyGet(*(_QWORD *)&PfSvcGlobals + 1432LL, 0);
  if ( result )
    return result;
  result = RegCreateKeyExW(*v3, L"StaticConfig", 0, 0, 0, 0xF003Fu, 0, (PHKEY)(v2 + 1440), 0);
  if ( result )
    return result;
  v5 = HeapCreate(0, 0x10000u, 0);
  *(_QWORD *)(v2 + 88) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = PfsVaMgrAlloc(*(_QWORD *)(v2 + 8), 0x10000);
  *(_QWORD *)v2 = v6;
  if ( !v6 )
    return 8;
  memset_0((void *)(v2 + 524), 0, 0x118u);
  *(_DWORD *)(v2 + 520) = 284;
  Version = RtlGetVersion((PRTL_OSVERSIONINFOW)(v2 + 520));
  if ( Version < 0 )
    return RtlNtStatusToDosError(Version);
  *(_QWORD *)(v2 + 472) = 0;
  EventRegister(&SYSMAIN_SERVICE_EVENT_PROVIDER, 0, 0, (PREGHANDLE)(v2 + 472));
  Version = NtQuerySystemInformation(SystemBasicInformation, (PVOID)(v2 + 808), 0x40u, 0);
  if ( Version < 0 )
    return RtlNtStatusToDosError(Version);
  if ( *(_DWORD *)(v2 + 816) != 4096 )
    return 1805;
  v8 = *(unsigned int *)(v2 + 820) * (unsigned __int128)0xAAAAAAAAAAAAAAABuLL;
  *(_QWORD *)(v2 + 872) = *(unsigned int *)(v2 + 820);
  *(_DWORD *)(v2 + 3800) = *((_QWORD *)&v8 + 1) >> 3;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(v2 + 3648) = CurrentThreadId;
  v10 = OpenThread(0x100060u, 0, CurrentThreadId);
  *(_QWORD *)(v2 + 3656) = v10;
  if ( !v10 )
    return GetLastError();
  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)(v2 + 880) = EventW;
  if ( !EventW )
    return GetLastError();
  v12 = (HKEY *)(v2 + 1448);
  result = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\Session Manager\\Memory Management\\PrefetchParameters",
             0,
             0,
             0,
             0xF003Fu,
             0,
             (PHKEY)(v2 + 1448),
             0);
  if ( !result )
  {
    result = PfSvInitializePrefetchDirectory((int)*v12);
    if ( !result )
    {
      PfsRegQueryValue(*(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 1432LL), (unsigned int)L"ServiceFlags", 4, 4, v2 + 244);
      v13 = *(_QWORD *)(v2 + 872);
      if ( v13 > 0x2BC00 )
      {
        v14 = *(_DWORD *)(v2 + 1600);
        if ( v13 > 0x51400 )
        {
          if ( v13 > 0xC8000 )
          {
            if ( v13 > 0x1E7800 )
            {
              if ( v13 > 0x3E8000 )
                v15 = v14 & 0xFFFF8FFF | 0x5000;
              else
                v15 = v14 & 0xFFFF8FFF | 0x4000;
            }
            else
            {
              v15 = v14 & 0xFFFF8FFF | 0x3000;
            }
          }
          else
          {
            v15 = v14 & 0xFFFF8FFF | 0x2000;
          }
        }
        else
        {
          v15 = v14 & 0xFFFF8FFF | 0x1000;
        }
        *(_DWORD *)(v2 + 1600) = v15;
      }
      else
      {
        *(_DWORD *)(v2 + 1600) &= 0xFFFF8FFF;
      }
      cbData = 4;
      RegQueryValueExW(*v12, L"BootId", 0, &Type, (LPBYTE)(v2 + 1456), &cbData);
      cbData = 4;
      RegQueryValueExW(*v12, L"BaseTime", 0, &Type, (LPBYTE)(v2 + 240), &cbData);
      LibraryW = LoadLibraryW(L"kernelbase.dll");
      *(_QWORD *)(v2 + 1416) = LibraryW;
      if ( LibraryW )
        *(_QWORD *)(v2 + 1424) = GetProcAddress(LibraryW, "SetWaitableTimerEx");
      result = PfSvScenCtxStart((PHANDLE)(v2 + 3696));
      if ( !result )
      {
        result = PfSvServiceCommandStart(v2 + 1616);
        if ( !result )
        {
          result = PfsActionItemMgrStart(v2 + 1720, v17, *(_QWORD *)(v2 + 3656));
          if ( !result )
          {
            result = PfSvPerfStatsStart(v2 + 1904);
            if ( !result || *(_DWORD *)(v2 + 524) < 6u )
            {
              PfLgStart((PVOID)(v2 + 384));
              v18 = PfScStringInsertEx(v2 + 96, L"\\$LOGFILE", 9);
              *(_QWORD *)(v2 + 3664) = v18;
              if ( v18 )
              {
                v19 = PfScStringInsertEx(v2 + 96, L"\\$MFT", 5);
                *(_QWORD *)(v2 + 3672) = v19;
                if ( v19 )
                {
                  if ( (unsigned int)PfSvPerformAoAcCheck() )
                    *(_DWORD *)(v2 + 1600) |= 2u;
                  if ( (unsigned __int8)IsRegisterIdleTaskPresent() && (unsigned __int8)IsRegisterIdleTaskPresent() )
                    *(_BYTE *)(v2 + 4137) |= 1u;
                  else
                    *(_BYTE *)(v2 + 4137) &= ~1u;
                  *(_BYTE *)(v2 + 4137) |= 2u;
                  return 0;
                }
              }
              return 8;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180081b6c  mov     rax, rsp
0x180081b6f  mov     [rax+18h], rbx
0x180081b73  mov     [rax+10h], rdx
0x180081b77  mov     [rax+8], rcx
0x180081b7b  push    rdi
0x180081b7c  sub     rsp, 50h
0x180081b80  mov     rdi, cs:PfSvcGlobals
0x180081b87  xor     edx, edx
0x180081b89  mov     dword ptr [rax+8], 0
0x180081b90  mov     dword ptr [rax+10h], 0
0x180081b97  lea     rbx, [rdi+598h]
0x180081b9e  mov     rcx, rbx
0x180081ba1  call    PfSvServiceRegistryKeyGet
0x180081ba6  test    eax, eax
0x180081ba8  jnz     loc_180081FDD
0x180081bae  mov     rcx, [rbx]; hKey
0x180081bb1  lea     rax, [rdi+5A0h]
0x180081bb8  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180081bc1  lea     rdx, aStaticconfig; "StaticConfig"
0x180081bc8  mov     [rsp+58h+phkResult], rax; phkResult
0x180081bcd  xor     r9d, r9d; lpClass
0x180081bd0  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180081bd9  xor     r8d, r8d; Reserved
0x180081bdc  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180081be4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180081bec  call    cs:__imp_RegCreateKeyExW
0x180081bf2  test    eax, eax
0x180081bf4  jnz     loc_180081FDD
0x180081bfa  mov     ebx, 10000h
0x180081bff  xor     r8d, r8d; dwMaximumSize
0x180081c02  mov     edx, ebx; dwInitialSize
0x180081c04  xor     ecx, ecx; flOptions
0x180081c06  call    cs:__imp_HeapCreate
0x180081c0c  mov     [rdi+58h], rax
0x180081c10  test    rax, rax
0x180081c13  jnz     short loc_180081C20
0x180081c15  call    cs:__imp_GetLastError
0x180081c1b  jmp     loc_180081FDD
0x180081c20  mov     rcx, [rdi+8]
0x180081c24  mov     rdx, rbx
0x180081c27  call    cs:__imp_PfsVaMgrAlloc
0x180081c2d  mov     [rdi], rax
0x180081c30  test    rax, rax
0x180081c33  jz      loc_180081FD8
0x180081c39  lea     rcx, [rdi+20Ch]; void *
0x180081c40  xor     edx, edx; Val
0x180081c42  mov     r8d, 118h; Size
0x180081c48  lea     rbx, [rdi+208h]
0x180081c4f  call    memset_0
0x180081c54  mov     rcx, rbx; lpVersionInformation
0x180081c57  mov     dword ptr [rbx], 11Ch
0x180081c5d  call    cs:__imp_RtlGetVersion
0x180081c63  test    eax, eax
0x180081c65  jns     short loc_180081C74
0x180081c67  mov     ecx, eax; Status
0x180081c69  call    cs:__imp_RtlNtStatusToDosError
0x180081c6f  jmp     loc_180081FDD
0x180081c74  lea     r9, [rdi+1D8h]; RegHandle
0x180081c7b  xor     r8d, r8d; CallbackContext
0x180081c7e  xor     edx, edx; EnableCallback
0x180081c80  mov     qword ptr [r9], 0
0x180081c87  lea     rcx, SYSMAIN_SERVICE_EVENT_PROVIDER; ProviderId
0x180081c8e  call    cs:__imp_EventRegister
0x180081c94  xor     r9d, r9d; ReturnLength
0x180081c97  lea     rdx, [rdi+328h]; SystemInformation
0x180081c9e  xor     ecx, ecx; SystemInformationClass
0x180081ca0  lea     r8d, [r9+40h]; SystemInformationLength
0x180081ca4  call    cs:__imp_NtQuerySystemInformation
0x180081caa  test    eax, eax
0x180081cac  js      short loc_180081C67
0x180081cae  cmp     dword ptr [rdi+330h], 1000h
0x180081cb8  jz      short loc_180081CC4
0x180081cba  mov     eax, 70Dh
0x180081cbf  jmp     loc_180081FDD
0x180081cc4  mov     ecx, [rdi+334h]
0x180081cca  mov     rax, 0AAAAAAAAAAAAAAABh
0x180081cd4  mul     rcx
0x180081cd7  mov     [rdi+368h], rcx
0x180081cde  shr     rdx, 3
0x180081ce2  mov     [rdi+0ED8h], edx
0x180081ce8  call    cs:__imp_GetCurrentThreadId
0x180081cee  xor     edx, edx; bInheritHandle
0x180081cf0  mov     ecx, 100060h; dwDesiredAccess
0x180081cf5  mov     r8d, eax; dwThreadId
0x180081cf8  mov     [rdi+0E40h], eax
0x180081cfe  call    cs:__imp_OpenThread
0x180081d04  mov     [rdi+0E48h], rax
0x180081d0b  test    rax, rax
0x180081d0e  jz      loc_180081C15
0x180081d14  xor     r9d, r9d; lpName
0x180081d17  xor     r8d, r8d; bInitialState
0x180081d1a  xor     ecx, ecx; lpEventAttributes
0x180081d1c  lea     edx, [r9+1]; bManualReset
0x180081d20  call    cs:__imp_CreateEventW
0x180081d26  mov     [rdi+370h], rax
0x180081d2d  test    rax, rax
0x180081d30  jz      loc_180081C15
0x180081d36  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180081d3f  lea     rbx, [rdi+5A8h]
0x180081d46  mov     [rsp+58h+phkResult], rbx; phkResult
0x180081d4b  lea     rdx, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Ses"...
0x180081d52  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180081d5b  xor     r9d, r9d; lpClass
0x180081d5e  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180081d66  xor     r8d, r8d; Reserved
0x180081d69  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081d70  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180081d78  call    cs:__imp_RegCreateKeyExW
0x180081d7e  test    eax, eax
0x180081d80  jnz     loc_180081FDD
0x180081d86  mov     rcx, [rbx]
0x180081d89  call    PfSvInitializePrefetchDirectory
0x180081d8e  test    eax, eax
0x180081d90  jnz     loc_180081FDD
0x180081d96  mov     rcx, cs:PfSvcGlobals
0x180081d9d  lea     rax, [rdi+0F4h]
0x180081da4  mov     r9d, 4
0x180081daa  mov     qword ptr [rsp+58h+dwOptions], rax
0x180081daf  mov     r8d, r9d
0x180081db2  lea     rdx, aServiceflags; "ServiceFlags"
0x180081db9  mov     rcx, [rcx+598h]
0x180081dc0  call    PfsRegQueryValue
0x180081dc5  mov     rcx, [rdi+368h]
0x180081dcc  cmp     rcx, 2BC00h
0x180081dd3  ja      short loc_180081DE1
0x180081dd5  and     dword ptr [rdi+640h], 0FFFF8FFFh
0x180081ddf  jmp     short loc_180081E46
0x180081de1  mov     eax, [rdi+640h]
0x180081de7  cmp     rcx, 51400h
0x180081dee  ja      short loc_180081DFB
0x180081df0  and     eax, 0FFFF9FFFh
0x180081df5  bts     eax, 0Ch
0x180081df9  jmp     short loc_180081E40
0x180081dfb  cmp     rcx, 0C8000h
0x180081e02  ja      short loc_180081E0F
0x180081e04  and     eax, 0FFFFAFFFh
0x180081e09  bts     eax, 0Dh
0x180081e0d  jmp     short loc_180081E40
0x180081e0f  cmp     rcx, 1E7800h
0x180081e16  ja      short loc_180081E23
0x180081e18  btr     eax, 0Eh
0x180081e1c  or      eax, 3000h
0x180081e21  jmp     short loc_180081E40
0x180081e23  cmp     rcx, 3E8000h
0x180081e2a  ja      short loc_180081E37
0x180081e2c  and     eax, 0FFFFCFFFh
0x180081e31  bts     eax, 0Eh
0x180081e35  jmp     short loc_180081E40
0x180081e37  btr     eax, 0Dh
0x180081e3b  or      eax, 5000h
0x180081e40  mov     [rdi+640h], eax
0x180081e46  lea     rcx, [rsp+58h+cbData]
0x180081e4b  mov     [rsp+58h+cbData], 4
0x180081e53  mov     qword ptr [rsp+58h+samDesired], rcx; lpcbData
0x180081e58  lea     rax, [rdi+5B0h]
0x180081e5f  mov     rcx, [rbx]; hKey
0x180081e62  lea     r9, [rsp+58h+Type]; lpType
0x180081e67  xor     r8d, r8d; lpReserved
0x180081e6a  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180081e6f  lea     rdx, aBootid; "BootId"
0x180081e76  call    cs:__imp_RegQueryValueExW
0x180081e7c  lea     rcx, [rsp+58h+cbData]
0x180081e81  mov     [rsp+58h+cbData], 4
0x180081e89  mov     qword ptr [rsp+58h+samDesired], rcx; lpcbData
0x180081e8e  lea     rax, [rdi+0F0h]
0x180081e95  mov     rcx, [rbx]; hKey
0x180081e98  lea     r9, [rsp+58h+Type]; lpType
0x180081e9d  xor     r8d, r8d; lpReserved
0x180081ea0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180081ea5  lea     rdx, aBasetime; "BaseTime"
0x180081eac  call    cs:__imp_RegQueryValueExW
0x180081eb2  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180081eb9  call    cs:__imp_LoadLibraryW
0x180081ebf  mov     [rdi+588h], rax
0x180081ec6  test    rax, rax
0x180081ec9  jz      short loc_180081EE2
0x180081ecb  lea     rdx, aSetwaitabletim; "SetWaitableTimerEx"
0x180081ed2  mov     rcx, rax; hModule
0x180081ed5  call    cs:__imp_GetProcAddress
0x180081edb  mov     [rdi+590h], rax
0x180081ee2  lea     rcx, [rdi+0E70h]; EventHandle
0x180081ee9  call    PfSvScenCtxStart
0x180081eee  test    eax, eax
0x180081ef0  jnz     loc_180081FDD
0x180081ef6  lea     rcx, [rdi+650h]
0x180081efd  call    PfSvServiceCommandStart
0x180081f02  test    eax, eax
0x180081f04  jnz     loc_180081FDD
0x180081f0a  mov     r8, [rdi+0E48h]
0x180081f11  lea     rcx, [rdi+6B8h]
0x180081f18  call    PfsActionItemMgrStart
0x180081f1d  test    eax, eax
0x180081f1f  jnz     loc_180081FDD
0x180081f25  lea     rcx, [rdi+770h]
0x180081f2c  call    PfSvPerfStatsStart
0x180081f31  test    eax, eax
0x180081f33  jz      short loc_180081F42
0x180081f35  cmp     dword ptr [rdi+20Ch], 6
0x180081f3c  jnb     loc_180081FDD
0x180081f42  lea     rcx, [rdi+180h]; RequestContext
0x180081f49  call    PfLgStart
0x180081f4e  xor     r9d, r9d
0x180081f51  lea     rdx, aLogfile_0; "\\$LOGFILE"
0x180081f58  lea     rcx, [rdi+60h]
0x180081f5c  lea     r8d, [r9+9]
0x180081f60  call    PfScStringInsertEx
0x180081f65  mov     [rdi+0E50h], rax
0x180081f6c  test    rax, rax
0x180081f6f  jz      short loc_180081FD8
0x180081f71  xor     r9d, r9d
0x180081f74  lea     rdx, aMft_0; "\\$MFT"
0x180081f7b  lea     rcx, [rdi+60h]
0x180081f7f  lea     r8d, [r9+5]
0x180081f83  call    PfScStringInsertEx
0x180081f88  mov     [rdi+0E58h], rax
0x180081f8f  test    rax, rax
0x180081f92  jz      short loc_180081FD8
0x180081f94  call    PfSvPerformAoAcCheck
0x180081f99  test    eax, eax
0x180081f9b  jz      short loc_180081FA4
0x180081f9d  or      dword ptr [rdi+640h], 2
0x180081fa4  call    IsRegisterIdleTaskPresent
0x180081fa9  test    al, al
0x180081fab  jz      short loc_180081FBF
0x180081fad  call    IsRegisterIdleTaskPresent
0x180081fb2  test    al, al
0x180081fb4  jz      short loc_180081FBF
0x180081fb6  or      byte ptr [rdi+1029h], 1
0x180081fbd  jmp     short loc_180081FC6
0x180081fbf  and     byte ptr [rdi+1029h], 0FEh
0x180081fc6  mov     al, [rdi+1029h]
0x180081fcc  or      al, 2
0x180081fce  mov     [rdi+1029h], al
0x180081fd4  xor     eax, eax
0x180081fd6  jmp     short loc_180081FDD
0x180081fd8  mov     eax, 8
0x180081fdd  mov     rbx, [rsp+58h+arg_10]
0x180081fe2  add     rsp, 50h
0x180081fe6  pop     rdi
0x180081fe7  retn
```
