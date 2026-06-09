# ProcessRefCount::~ProcessRefCount(void)

- ea: `0x140001140`
- end: `0x1400011f7`
- name: `??1ProcessRefCount@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001340`

## callees

- `0x140001140`
- `0x1400059e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400011af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400011af`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x140001199`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x140001199`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400011be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400011be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400011c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400011c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400011d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400011d7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400011e5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400011e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000117e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000117e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001166`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001166`

## string_xrefs

- `0x14000115f`: `api-ms-win-shcore-thread-l1-1-0.dll`

## pseudocode

```c
void __fastcall ProcessRefCount::~ProcessRefCount(ProcessRefCount *this)
{
  HMODULE Library; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax
  struct _TP_TIMER *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &ProcessRefCount::`vftable';
  Library = LoadLibraryExW(L"api-ms-win-shcore-thread-l1-1-0.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SetProcessReference");
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD))ProcAddress)(0);
  }
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
  if ( v5 )
  {
    if ( IsThreadpoolTimerSet(v5) )
    {
      SetThreadpoolTimer(*((PTP_TIMER *)this + 3), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
    }
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 3));
  }
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
    CloseHandle(v6);
  if ( v3 )
    FreeLibrary(v3);
}

```

## disassembly

```asm
0x140001140  mov     [rsp+arg_8], rbx
0x140001145  push    rdi
0x140001146  sub     rsp, 20h
0x14000114a  mov     rbx, rcx
0x14000114d  lea     rax, ??_7ProcessRefCount@@6B@; const ProcessRefCount::`vftable'
0x140001154  mov     [rcx], rax
0x140001157  xor     edx, edx; hFile
0x140001159  mov     r8d, 800h; dwFlags
0x14000115f  lea     rcx, LibFileName; "api-ms-win-shcore-thread-l1-1-0.dll"
0x140001166  call    cs:__imp_LoadLibraryExW
0x14000116c  mov     rdi, rax
0x14000116f  test    rax, rax
0x140001172  jz      short loc_140001190
0x140001174  lea     rdx, ProcName; "SetProcessReference"
0x14000117b  mov     rcx, rax; hModule
0x14000117e  call    cs:__imp_GetProcAddress
0x140001184  test    rax, rax
0x140001187  jz      short loc_140001190
0x140001189  xor     ecx, ecx
0x14000118b  call    _guard_dispatch_icall
0x140001190  mov     rcx, [rbx+18h]; pti
0x140001194  test    rcx, rcx
0x140001197  jz      short loc_1400011CE
0x140001199  call    cs:__imp_IsThreadpoolTimerSet
0x14000119f  test    eax, eax
0x1400011a1  jz      short loc_1400011C4
0x1400011a3  xor     r9d, r9d; msWindowLength
0x1400011a6  xor     r8d, r8d; msPeriod
0x1400011a9  xor     edx, edx; pftDueTime
0x1400011ab  mov     rcx, [rbx+18h]; pti
0x1400011af  call    cs:__imp_SetThreadpoolTimer
0x1400011b5  mov     edx, 1; fCancelPendingCallbacks
0x1400011ba  mov     rcx, [rbx+18h]; pti
0x1400011be  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400011c4  mov     rcx, [rbx+18h]; pti
0x1400011c8  call    cs:__imp_CloseThreadpoolTimer
0x1400011ce  mov     rcx, [rbx+10h]; hObject
0x1400011d2  test    rcx, rcx
0x1400011d5  jz      short loc_1400011DD
0x1400011d7  call    cs:__imp_CloseHandle
0x1400011dd  test    rdi, rdi
0x1400011e0  jz      short loc_1400011EC
0x1400011e2  mov     rcx, rdi; hLibModule
0x1400011e5  call    cs:__imp_FreeLibrary
0x1400011eb  nop
0x1400011ec  mov     rbx, [rsp+28h+arg_8]
0x1400011f1  add     rsp, 20h
0x1400011f5  pop     rdi
0x1400011f6  retn
```
