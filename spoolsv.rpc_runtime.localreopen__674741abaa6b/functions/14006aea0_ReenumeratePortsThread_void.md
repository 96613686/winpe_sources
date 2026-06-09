# ReenumeratePortsThread(void *)

- ea: `0x14006aea0`
- end: `0x14006afd5`
- name: `?ReenumeratePortsThread@@YAKPEAX@Z`
- size: `309`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14000e700`
- `0x14006aea0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006af5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006af5e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006afac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006afac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14006aefa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14006aefa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006aee4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006af28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006afbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006aee4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006af28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006afbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006aeb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006af09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006af86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006aeb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006af09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006af86`
- `KERNEL32!FreeLibrary` at `0x14006af77`
- `KERNEL32!FreeLibrary` at `0x14006af77`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14006af40`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14006af40`

## string_xrefs

- `0x14006af39`: `localspl.dll`

## pseudocode

```c
__int64 __fastcall ReenumeratePortsThread(void *a1)
{
  HMODULE LibraryW; // rax
  HMODULE v2; // rbx
  void (*ProcAddress)(void); // rax

  EnterCriticalSection(&DeviceArrivalCS);
  if ( !dword_1400D3A1C )
  {
    if ( dword_1400D3A20 )
    {
      dword_1400D3A1C = 1;
      LeaveCriticalSection(&DeviceArrivalCS);
      WaitForSingleObject(ThdOutEvent, 0xFFFFFFFF);
      EnterCriticalSection(&DeviceArrivalCS);
      dword_1400D3A1C = 0;
    }
    dword_1400D3A20 = 1;
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
    dword_1400D3A20 = 0;
    if ( dword_1400D3A1C )
      SetEvent(ThdOutEvent);
  }
  LeaveCriticalSection(&DeviceArrivalCS);
  return 0;
}

```

## disassembly

```asm
0x14006aea0  mov     [rsp+arg_0], rbx
0x14006aea5  push    rsi
0x14006aea6  sub     rsp, 20h
0x14006aeaa  lea     rsi, ?DeviceArrivalCS@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION DeviceArrivalCS
0x14006aeb1  mov     rcx, rsi; lpCriticalSection
0x14006aeb4  call    cs:__imp_EnterCriticalSection
0x14006aebb  nop     dword ptr [rax+rax+00h]
0x14006aec0  cmp     cs:dword_1400D3A1C, 0
0x14006aec7  jnz     loc_14006AFB8
0x14006aecd  cmp     cs:dword_1400D3A20, 0
0x14006aed4  mov     ebx, 1
0x14006aed9  jz      short loc_14006AF1F
0x14006aedb  mov     rcx, rsi; lpCriticalSection
0x14006aede  mov     cs:dword_1400D3A1C, ebx
0x14006aee4  call    cs:__imp_LeaveCriticalSection
0x14006aeeb  nop     dword ptr [rax+rax+00h]
0x14006aef0  mov     rcx, cs:?ThdOutEvent@@3PEAXEA; hHandle
0x14006aef7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14006aefa  call    cs:__imp_WaitForSingleObject
0x14006af01  nop     dword ptr [rax+rax+00h]
0x14006af06  mov     rcx, rsi; lpCriticalSection
0x14006af09  call    cs:__imp_EnterCriticalSection
0x14006af10  nop     dword ptr [rax+rax+00h]
0x14006af15  mov     cs:dword_1400D3A1C, 0
0x14006af1f  mov     rcx, rsi; lpCriticalSection
0x14006af22  mov     cs:dword_1400D3A20, ebx
0x14006af28  call    cs:__imp_LeaveCriticalSection
0x14006af2f  nop     dword ptr [rax+rax+00h]
0x14006af34  call    WaitForSpoolerInitialization
0x14006af39  lea     rcx, aLocalsplDll; "localspl.dll"
0x14006af40  call    cs:__imp_LoadLibraryW
0x14006af47  nop     dword ptr [rax+rax+00h]
0x14006af4c  mov     rbx, rax
0x14006af4f  test    rax, rax
0x14006af52  jz      short loc_14006AF83
0x14006af54  lea     rdx, aSplreenumerate; "SplReenumeratePorts"
0x14006af5b  mov     rcx, rax; hModule
0x14006af5e  call    cs:__imp_GetProcAddress
0x14006af65  nop     dword ptr [rax+rax+00h]
0x14006af6a  test    rax, rax
0x14006af6d  jz      short loc_14006AF74
0x14006af6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006af74  mov     rcx, rbx; hLibModule
0x14006af77  call    cs:__imp_FreeLibrary
0x14006af7e  nop     dword ptr [rax+rax+00h]
0x14006af83  mov     rcx, rsi; lpCriticalSection
0x14006af86  call    cs:__imp_EnterCriticalSection
0x14006af8d  nop     dword ptr [rax+rax+00h]
0x14006af92  cmp     cs:dword_1400D3A1C, 0
0x14006af99  mov     cs:dword_1400D3A20, 0
0x14006afa3  jz      short loc_14006AFB8
0x14006afa5  mov     rcx, cs:?ThdOutEvent@@3PEAXEA; hEvent
0x14006afac  call    cs:__imp_SetEvent
0x14006afb3  nop     dword ptr [rax+rax+00h]
0x14006afb8  mov     rcx, rsi; lpCriticalSection
0x14006afbb  call    cs:__imp_LeaveCriticalSection
0x14006afc2  nop     dword ptr [rax+rax+00h]
0x14006afc7  mov     rbx, [rsp+28h+arg_0]
0x14006afcc  xor     eax, eax
0x14006afce  add     rsp, 20h
0x14006afd2  pop     rsi
0x14006afd3  retn
```
