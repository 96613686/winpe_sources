# DllMain

- ea: `0x18005db90`
- end: `0x18005dc74`
- name: `DllMain`
- size: `228`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800780b4`

## callees

- `0x18005db90`
- `0x180062018`
- `0x180070768`
- `0x18008a110`
- `0x18008bfb0`
- `0x1800b645a`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18005dbcc`
- `ntdll!RtlInitializeSRWLock` at `0x18005dc01`
- `ntdll!RtlInitializeSRWLock` at `0x18005dbcc`
- `ntdll!RtlInitializeSRWLock` at `0x18005dc01`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005dbf4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005dbf4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005dc4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005dc4c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005dc13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005dc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dc25`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18005dba2`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18005dba2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005dc63`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005dc63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dc3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dc3f`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    if ( !PfSvcGlobalsPerModuleInitialized )
    {
      PfDbGlobalsInitialize();
      PfUDInitialize();
      PfDSInitialize();
      PfScenDbInitialize();
      RtlInitializeSRWLock(&PfSvcGlobalsLock);
      PfSvcGlobalsPerModuleInitialized = 1;
    }
    memset_0(&SmPcGlobals, 0, 0x270u);
    InitializeCriticalSection(&SmPcGlobals);
    RtlInitializeSRWLock(&PfSvWmiLock);
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
    {
      GetLastError();
      return 0;
    }
  }
  else if ( !fdwReason )
  {
    if ( hEvent )
      CloseHandle(hEvent);
    DeleteCriticalSection(&SmPcGlobals);
    if ( !lpvReserved && PfSvWmiAdapter )
      FreeLibrary(PfSvWmiAdapter);
  }
  return 1;
}

```

## disassembly

```asm
0x18005db90  push    rbx
0x18005db92  sub     rsp, 20h
0x18005db96  mov     rbx, r8
0x18005db99  cmp     edx, 1
0x18005db9c  jnz     loc_18005DC2F
0x18005dba2  call    cs:__imp_DisableThreadLibraryCalls
0x18005dba8  cmp     cs:PfSvcGlobalsPerModuleInitialized, 0
0x18005dbaf  jnz     short loc_18005DBD9
0x18005dbb1  call    PfDbGlobalsInitialize
0x18005dbb6  call    PfUDInitialize
0x18005dbbb  call    PfDSInitialize
0x18005dbc0  call    PfScenDbInitialize
0x18005dbc5  lea     rcx, PfSvcGlobalsLock
0x18005dbcc  call    cs:__imp_RtlInitializeSRWLock
0x18005dbd2  mov     cs:PfSvcGlobalsPerModuleInitialized, 1
0x18005dbd9  xor     edx, edx; Val
0x18005dbdb  lea     rcx, SmPcGlobals; void *
0x18005dbe2  mov     r8d, 270h; Size
0x18005dbe8  call    memset_0
0x18005dbed  lea     rcx, SmPcGlobals; lpCriticalSection
0x18005dbf4  call    cs:__imp_InitializeCriticalSection
0x18005dbfa  lea     rcx, ?PfSvWmiLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK PfSvWmiLock
0x18005dc01  call    cs:__imp_RtlInitializeSRWLock
0x18005dc07  xor     r9d, r9d; lpName
0x18005dc0a  xor     r8d, r8d; bInitialState
0x18005dc0d  xor     ecx, ecx; lpEventAttributes
0x18005dc0f  lea     edx, [r9+1]; bManualReset
0x18005dc13  call    cs:__imp_CreateEventW
0x18005dc19  mov     cs:hEvent, rax
0x18005dc20  test    rax, rax
0x18005dc23  jnz     short loc_18005DC69
0x18005dc25  call    cs:__imp_GetLastError
0x18005dc2b  xor     eax, eax
0x18005dc2d  jmp     short loc_18005DC6E
0x18005dc2f  test    edx, edx
0x18005dc31  jnz     short loc_18005DC69
0x18005dc33  mov     rcx, cs:hEvent; hObject
0x18005dc3a  test    rcx, rcx
0x18005dc3d  jz      short loc_18005DC45
0x18005dc3f  call    cs:__imp_CloseHandle
0x18005dc45  lea     rcx, SmPcGlobals; lpCriticalSection
0x18005dc4c  call    cs:__imp_DeleteCriticalSection
0x18005dc52  test    rbx, rbx
0x18005dc55  jnz     short loc_18005DC69
0x18005dc57  mov     rcx, cs:?PfSvWmiAdapter@@3PEAUHINSTANCE__@@EA; hLibModule
0x18005dc5e  test    rcx, rcx
0x18005dc61  jz      short loc_18005DC69
0x18005dc63  call    cs:__imp_FreeLibrary
0x18005dc69  mov     eax, 1
0x18005dc6e  add     rsp, 20h
0x18005dc72  pop     rbx
0x18005dc73  retn
```
