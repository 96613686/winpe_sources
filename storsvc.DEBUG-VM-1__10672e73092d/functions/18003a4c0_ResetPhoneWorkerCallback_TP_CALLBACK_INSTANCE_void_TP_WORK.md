# ResetPhoneWorkerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18003a4c0`
- end: `0x18003a556`
- name: `?ResetPhoneWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `150`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18003a4c0`
- `0x18003a55c`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a533`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a533`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a546`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a546`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a4e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a4e9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a4dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a4dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a50e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a50e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a4f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a4f6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003a51b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003a51b`

## string_xrefs

- `0x18003a514`: `SprintCSP.dll`

## pseudocode

```c
void __fastcall ResetPhoneWorkerCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rbx
  void (*ProcAddress)(void); // rax

  if ( TargetHandle && dwMilliseconds )
  {
    WaitForSingleObject(TargetHandle, dwMilliseconds);
    EnterCriticalSection(&stru_1800C9B80);
    CloseHandle(TargetHandle);
    TargetHandle = (HANDLE)-1LL;
    LeaveCriticalSection(&stru_1800C9B80);
  }
  LibraryW = LoadLibraryW(L"SprintCSP.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "FactoryResetUICC");
    if ( ProcAddress )
      ProcAddress();
    FreeLibrary(v4);
  }
  StorageSvcReqShutdown();
}

```

## disassembly

```asm
0x18003a4c0  push    rbx
0x18003a4c2  sub     rsp, 20h
0x18003a4c6  mov     rcx, cs:TargetHandle; hHandle
0x18003a4cd  test    rcx, rcx
0x18003a4d0  jz      short loc_18003A514
0x18003a4d2  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x18003a4d8  test    edx, edx
0x18003a4da  jz      short loc_18003A514
0x18003a4dc  call    cs:__imp_WaitForSingleObject
0x18003a4e2  lea     rcx, stru_1800C9B80; lpCriticalSection
0x18003a4e9  call    cs:__imp_EnterCriticalSection
0x18003a4ef  mov     rcx, cs:TargetHandle; hObject
0x18003a4f6  call    cs:__imp_CloseHandle
0x18003a4fc  lea     rcx, stru_1800C9B80; lpCriticalSection
0x18003a503  mov     cs:TargetHandle, 0FFFFFFFFFFFFFFFFh
0x18003a50e  call    cs:__imp_LeaveCriticalSection
0x18003a514  lea     rcx, aSprintcspDll; "SprintCSP.dll"
0x18003a51b  call    cs:__imp_LoadLibraryW
0x18003a521  mov     rbx, rax
0x18003a524  test    rax, rax
0x18003a527  jz      short loc_18003A54C
0x18003a529  lea     rdx, aFactoryresetui; "FactoryResetUICC"
0x18003a530  mov     rcx, rax; hModule
0x18003a533  call    cs:__imp_GetProcAddress
0x18003a539  test    rax, rax
0x18003a53c  jz      short loc_18003A543
0x18003a53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a543  mov     rcx, rbx; hLibModule
0x18003a546  call    cs:__imp_FreeLibrary
0x18003a54c  add     rsp, 20h
0x18003a550  pop     rbx
0x18003a551  jmp     ?StorageSvcReqShutdown@@YAJW4SHUTDOWN_REQUEST_TYPE@@K@Z; StorageSvcReqShutdown(SHUTDOWN_REQUEST_TYPE,ulong)
```
