# XsLoadPrintSpoolerFunctions

- ea: `0x180030c18`
- end: `0x180030d68`
- name: `XsLoadPrintSpoolerFunctions`
- size: `336`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800304d0`
- `0x180030a50`
- `0x180030d70`
- `0x180031330`

## callees

- `0x180030c18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030c47`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030c47`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030d42`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030d42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030c67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030c8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030cab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030ccb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030ceb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030c67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030c8b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030cab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030ccb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030ceb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030c27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030d5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030d5a`

## string_xrefs

- `0x180030c5d`: `OpenPrinterW`

## pseudocode

```c
char XsLoadPrintSpoolerFunctions()
{
  char v0; // bl
  HMODULE Library; // rax

  v0 = 1;
  EnterCriticalSection(&SpoolerMutex);
  if ( !hSpoolerLibrary )
  {
    Library = LoadLibraryExW(L"winspool.drv", 0, 0);
    hSpoolerLibrary = Library;
    if ( !Library
      || (pSpoolerOpenPrinterFunction = (__int64)GetProcAddress(Library, "OpenPrinterW")) == 0
      || (pSpoolerResetPrinterFunction = (__int64)GetProcAddress(hSpoolerLibrary, "ResetPrinterW")) == 0
      || (pSpoolerAddJobFunction = (__int64)GetProcAddress(hSpoolerLibrary, "AddJobW")) == 0
      || (pSpoolerScheduleJobFunction = (__int64)GetProcAddress(hSpoolerLibrary, "ScheduleJob")) == 0
      || (pSpoolerClosePrinterFunction = (__int64)GetProcAddress(hSpoolerLibrary, "ClosePrinter")) == 0 )
    {
      v0 = 0;
      pSpoolerOpenPrinterFunction = 0;
      pSpoolerResetPrinterFunction = 0;
      pSpoolerAddJobFunction = 0;
      pSpoolerScheduleJobFunction = 0;
      pSpoolerClosePrinterFunction = 0;
      if ( hSpoolerLibrary )
      {
        FreeLibrary(hSpoolerLibrary);
        hSpoolerLibrary = 0;
      }
    }
  }
  LeaveCriticalSection(&SpoolerMutex);
  return v0;
}

```

## disassembly

```asm
0x180030c18  push    rbx
0x180030c1a  sub     rsp, 20h
0x180030c1e  lea     rcx, SpoolerMutex; lpCriticalSection
0x180030c25  mov     bl, 1
0x180030c27  call    cs:__imp_EnterCriticalSection
0x180030c2d  cmp     cs:hSpoolerLibrary, 0
0x180030c35  jnz     loc_180030D53
0x180030c3b  xor     r8d, r8d; dwFlags
0x180030c3e  lea     rcx, aWinspoolDrv; "winspool.drv"
0x180030c45  xor     edx, edx; hFile
0x180030c47  call    cs:__imp_LoadLibraryExW
0x180030c4d  mov     cs:hSpoolerLibrary, rax
0x180030c54  test    rax, rax
0x180030c57  jz      loc_180030CFD
0x180030c5d  lea     rdx, aOpenprinterw; "OpenPrinterW"
0x180030c64  mov     rcx, rax; hModule
0x180030c67  call    cs:__imp_GetProcAddress
0x180030c6d  mov     cs:pSpoolerOpenPrinterFunction, rax
0x180030c74  test    rax, rax
0x180030c77  jz      loc_180030CFD
0x180030c7d  mov     rcx, cs:hSpoolerLibrary; hModule
0x180030c84  lea     rdx, aResetprinterw; "ResetPrinterW"
0x180030c8b  call    cs:__imp_GetProcAddress
0x180030c91  mov     cs:pSpoolerResetPrinterFunction, rax
0x180030c98  test    rax, rax
0x180030c9b  jz      short loc_180030CFD
0x180030c9d  mov     rcx, cs:hSpoolerLibrary; hModule
0x180030ca4  lea     rdx, aAddjobw; "AddJobW"
0x180030cab  call    cs:__imp_GetProcAddress
0x180030cb1  mov     cs:pSpoolerAddJobFunction, rax
0x180030cb8  test    rax, rax
0x180030cbb  jz      short loc_180030CFD
0x180030cbd  mov     rcx, cs:hSpoolerLibrary; hModule
0x180030cc4  lea     rdx, aSchedulejob; "ScheduleJob"
0x180030ccb  call    cs:__imp_GetProcAddress
0x180030cd1  mov     cs:pSpoolerScheduleJobFunction, rax
0x180030cd8  test    rax, rax
0x180030cdb  jz      short loc_180030CFD
0x180030cdd  mov     rcx, cs:hSpoolerLibrary; hModule
0x180030ce4  lea     rdx, aCloseprinter; "ClosePrinter"
0x180030ceb  call    cs:__imp_GetProcAddress
0x180030cf1  mov     cs:pSpoolerClosePrinterFunction, rax
0x180030cf8  test    rax, rax
0x180030cfb  jnz     short loc_180030D53
0x180030cfd  xor     bl, bl
0x180030cff  mov     rcx, cs:hSpoolerLibrary; hLibModule
0x180030d06  mov     cs:pSpoolerOpenPrinterFunction, 0
0x180030d11  mov     cs:pSpoolerResetPrinterFunction, 0
0x180030d1c  mov     cs:pSpoolerAddJobFunction, 0
0x180030d27  mov     cs:pSpoolerScheduleJobFunction, 0
0x180030d32  mov     cs:pSpoolerClosePrinterFunction, 0
0x180030d3d  test    rcx, rcx
0x180030d40  jz      short loc_180030D53
0x180030d42  call    cs:__imp_FreeLibrary
0x180030d48  mov     cs:hSpoolerLibrary, 0
0x180030d53  lea     rcx, SpoolerMutex; lpCriticalSection
0x180030d5a  call    cs:__imp_LeaveCriticalSection
0x180030d60  mov     al, bl
0x180030d62  add     rsp, 20h
0x180030d66  pop     rbx
0x180030d67  retn
```
