# __scrt_initialize_thread_safe_statics

- ea: `0x180036870`
- end: `0x180036940`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180036644`
- `0x180036814`
- `0x180036870`
- `0x180036c48`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036893`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800368a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036893`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800368a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800368c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800368d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800368c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800368d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800368ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800368ff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180036886`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180036886`

## string_xrefs

- `0x18003688c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800368a1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u);
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-synch-l1-2-0.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      goto LABEL_9;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "SleepConditionVariableCS");
  v2 = GetProcAddress(ModuleHandleW, "WakeAllConditionVariable");
  if ( ProcAddress && v2 )
  {
    qword_180051350 = (__int64)ProcAddress;
    qword_180051358 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
LABEL_9:
    _scrt_fastfail(7);
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180036870  mov     [rsp+arg_0], rbx
0x180036875  push    rdi
0x180036876  sub     rsp, 20h
0x18003687a  mov     edx, 0FA0h; dwSpinCount
0x18003687f  lea     rcx, CriticalSection; lpCriticalSection
0x180036886  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003688c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180036893  call    cs:__imp_GetModuleHandleW
0x180036899  mov     rbx, rax
0x18003689c  test    rax, rax
0x18003689f  jnz     short loc_1800368B6
0x1800368a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800368a8  call    cs:__imp_GetModuleHandleW
0x1800368ae  mov     rbx, rax
0x1800368b1  test    rax, rax
0x1800368b4  jz      short loc_180036935
0x1800368b6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800368bd  mov     rcx, rbx; hModule
0x1800368c0  call    cs:__imp_GetProcAddress
0x1800368c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800368cd  mov     rcx, rbx; hModule
0x1800368d0  mov     rdi, rax
0x1800368d3  call    cs:__imp_GetProcAddress
0x1800368d9  test    rdi, rdi
0x1800368dc  jz      short loc_1800368F3
0x1800368de  test    rax, rax
0x1800368e1  jz      short loc_1800368F3
0x1800368e3  mov     cs:qword_180051350, rdi
0x1800368ea  mov     cs:qword_180051358, rax
0x1800368f1  jmp     short loc_180036911
0x1800368f3  xor     r9d, r9d; lpName
0x1800368f6  xor     r8d, r8d; bInitialState
0x1800368f9  xor     ecx, ecx; lpEventAttributes
0x1800368fb  lea     edx, [r9+1]; bManualReset
0x1800368ff  call    cs:__imp_CreateEventW
0x180036905  mov     cs:hHandle, rax
0x18003690c  test    rax, rax
0x18003690f  jz      short loc_180036935
0x180036911  xor     ecx, ecx
0x180036913  call    __scrt_initialize_onexit_tables
0x180036918  test    al, al
0x18003691a  jz      short loc_180036935
0x18003691c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180036923  call    atexit
0x180036928  mov     rbx, [rsp+28h+arg_0]
0x18003692d  xor     eax, eax
0x18003692f  add     rsp, 20h
0x180036933  pop     rdi
0x180036934  retn
0x180036935  mov     ecx, 7
0x18003693a  call    __scrt_fastfail
```
