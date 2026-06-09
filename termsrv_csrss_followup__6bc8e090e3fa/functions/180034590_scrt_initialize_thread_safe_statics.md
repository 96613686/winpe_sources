# __scrt_initialize_thread_safe_statics

- ea: `0x180034590`
- end: `0x180034660`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18003421c`
- `0x1800343ec`
- `0x180034590`
- `0x180034938`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800345e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800345f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800345e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800345f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800345b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800345c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800345b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800345c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003461f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003461f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800345a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800345a6`

## string_xrefs

- `0x1800345ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800345c1`: `kernel32.dll`

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
    qword_18012E8D0 = (__int64)ProcAddress;
    qword_18012E8D8 = (__int64)v2;
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
0x180034590  mov     [rsp+arg_0], rbx
0x180034595  push    rdi
0x180034596  sub     rsp, 20h
0x18003459a  mov     edx, 0FA0h; dwSpinCount
0x18003459f  lea     rcx, CriticalSection; lpCriticalSection
0x1800345a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800345ac  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x1800345b3  call    cs:__imp_GetModuleHandleW
0x1800345b9  mov     rbx, rax
0x1800345bc  test    rax, rax
0x1800345bf  jnz     short loc_1800345D6
0x1800345c1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800345c8  call    cs:__imp_GetModuleHandleW
0x1800345ce  mov     rbx, rax
0x1800345d1  test    rax, rax
0x1800345d4  jz      short loc_180034655
0x1800345d6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800345dd  mov     rcx, rbx; hModule
0x1800345e0  call    cs:__imp_GetProcAddress
0x1800345e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800345ed  mov     rcx, rbx; hModule
0x1800345f0  mov     rdi, rax
0x1800345f3  call    cs:__imp_GetProcAddress
0x1800345f9  test    rdi, rdi
0x1800345fc  jz      short loc_180034613
0x1800345fe  test    rax, rax
0x180034601  jz      short loc_180034613
0x180034603  mov     cs:qword_18012E8D0, rdi
0x18003460a  mov     cs:qword_18012E8D8, rax
0x180034611  jmp     short loc_180034631
0x180034613  xor     r9d, r9d; lpName
0x180034616  xor     r8d, r8d; bInitialState
0x180034619  xor     ecx, ecx; lpEventAttributes
0x18003461b  lea     edx, [r9+1]; bManualReset
0x18003461f  call    cs:__imp_CreateEventW
0x180034625  mov     cs:hHandle, rax
0x18003462c  test    rax, rax
0x18003462f  jz      short loc_180034655
0x180034631  xor     ecx, ecx
0x180034633  call    __scrt_initialize_onexit_tables
0x180034638  test    al, al
0x18003463a  jz      short loc_180034655
0x18003463c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180034643  call    atexit
0x180034648  mov     rbx, [rsp+28h+arg_0]
0x18003464d  xor     eax, eax
0x18003464f  add     rsp, 20h
0x180034653  pop     rdi
0x180034654  retn
0x180034655  mov     ecx, 7
0x18003465a  call    __scrt_fastfail
```
