# ReenumeratePortsThread(void *)

- ea: `0x140064b80`
- end: `0x140064c72`
- name: `?ReenumeratePortsThread@@YAKPEAX@Z`
- size: `242`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14000d520`
- `0x140064b80`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140064c1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140064c1a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140064c56`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140064c56`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140064bce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140064bce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064bbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064bf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064bbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064bf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140064c5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064b94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064bd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064c36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064b94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064bd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140064c36`
- `KERNEL32!FreeLibrary` at `0x140064c2d`
- `KERNEL32!FreeLibrary` at `0x140064c2d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140064c02`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140064c02`

## string_xrefs

- `0x140064bfb`: `localspl.dll`

## pseudocode

```c
__int64 __fastcall ReenumeratePortsThread(void *a1)
{
  HMODULE LibraryW; // rax
  HMODULE v2; // rbx
  void (*ProcAddress)(void); // rax

  EnterCriticalSection(&DeviceArrivalCS);
  if ( !dword_1400CC9AC )
  {
    if ( dword_1400CC9B0 )
    {
      dword_1400CC9AC = 1;
      LeaveCriticalSection(&DeviceArrivalCS);
      WaitForSingleObject(ThdOutEvent, 0xFFFFFFFF);
      EnterCriticalSection(&DeviceArrivalCS);
      dword_1400CC9AC = 0;
    }
    dword_1400CC9B0 = 1;
    LeaveCriticalSection(&DeviceArrivalCS);
    WaitForSpoolerInitialization();
    LibraryW = LoadLibraryW(L"localspl.dll");
    v2 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = (void (*)(void))GetProcAddress(LibraryW, "SplReenumeratePorts");
      if ( ProcAddress )
        ProcAddress();
      FreeLibrary(v2);
    }
    EnterCriticalSection(&DeviceArrivalCS);
    dword_1400CC9B0 = 0;
    if ( dword_1400CC9AC )
      SetEvent(ThdOutEvent);
  }
  LeaveCriticalSection(&DeviceArrivalCS);
  return 0;
}

```

## disassembly

```asm
0x140064b80  mov     [rsp+arg_0], rbx
0x140064b85  push    rsi
0x140064b86  sub     rsp, 20h
0x140064b8a  lea     rsi, ?DeviceArrivalCS@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DeviceArrivalCS
0x140064b91  mov     rcx, rsi; lpCriticalSection
0x140064b94  call    cs:__imp_EnterCriticalSection
0x140064b9a  cmp     cs:dword_1400CC9AC, 0
0x140064ba1  jnz     loc_140064C5C
0x140064ba7  cmp     cs:dword_1400CC9B0, 0
0x140064bae  mov     ebx, 1
0x140064bb3  jz      short loc_140064BE7
0x140064bb5  mov     rcx, rsi; lpCriticalSection
0x140064bb8  mov     cs:dword_1400CC9AC, ebx
0x140064bbe  call    cs:__imp_LeaveCriticalSection
0x140064bc4  mov     rcx, cs:?ThdOutEvent@@3PEAXEA; hHandle
0x140064bcb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140064bce  call    cs:__imp_WaitForSingleObject
0x140064bd4  mov     rcx, rsi; lpCriticalSection
0x140064bd7  call    cs:__imp_EnterCriticalSection
0x140064bdd  mov     cs:dword_1400CC9AC, 0
0x140064be7  mov     rcx, rsi; lpCriticalSection
0x140064bea  mov     cs:dword_1400CC9B0, ebx
0x140064bf0  call    cs:__imp_LeaveCriticalSection
0x140064bf6  call    WaitForSpoolerInitialization
0x140064bfb  lea     rcx, aLocalsplDll; "localspl.dll"
0x140064c02  call    cs:__imp_LoadLibraryW
0x140064c08  mov     rbx, rax
0x140064c0b  test    rax, rax
0x140064c0e  jz      short loc_140064C33
0x140064c10  lea     rdx, aSplreenumerate; "SplReenumeratePorts"
0x140064c17  mov     rcx, rax; hModule
0x140064c1a  call    cs:__imp_GetProcAddress
0x140064c20  test    rax, rax
0x140064c23  jz      short loc_140064C2A
0x140064c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064c2a  mov     rcx, rbx; hLibModule
0x140064c2d  call    cs:__imp_FreeLibrary
0x140064c33  mov     rcx, rsi; lpCriticalSection
0x140064c36  call    cs:__imp_EnterCriticalSection
0x140064c3c  cmp     cs:dword_1400CC9AC, 0
0x140064c43  mov     cs:dword_1400CC9B0, 0
0x140064c4d  jz      short loc_140064C5C
0x140064c4f  mov     rcx, cs:?ThdOutEvent@@3PEAXEA; hEvent
0x140064c56  call    cs:__imp_SetEvent
0x140064c5c  mov     rcx, rsi; lpCriticalSection
0x140064c5f  call    cs:__imp_LeaveCriticalSection
0x140064c65  mov     rbx, [rsp+28h+arg_0]
0x140064c6a  xor     eax, eax
0x140064c6c  add     rsp, 20h
0x140064c70  pop     rsi
0x140064c71  retn
```
