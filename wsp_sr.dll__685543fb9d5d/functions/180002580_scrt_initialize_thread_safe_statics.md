# __scrt_initialize_thread_safe_statics

- ea: `0x180002580`
- end: `0x180002650`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800017e4`
- `0x1800019b4`
- `0x1800019e4`
- `0x180002580`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800025a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800025b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800025a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800025b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000260f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000260f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002596`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002596`

## string_xrefs

- `0x18000259c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800025b1`: `kernel32.dll`

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
    qword_1800C72D8 = (__int64)ProcAddress;
    qword_1800C72E0 = (__int64)v2;
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
0x180002580  mov     [rsp+arg_0], rbx
0x180002585  push    rdi
0x180002586  sub     rsp, 20h
0x18000258a  mov     edx, 0FA0h; dwSpinCount
0x18000258f  lea     rcx, CriticalSection; lpCriticalSection
0x180002596  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000259c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800025a3  call    cs:__imp_GetModuleHandleW
0x1800025a9  mov     rbx, rax
0x1800025ac  test    rax, rax
0x1800025af  jnz     short loc_1800025C6
0x1800025b1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800025b8  call    cs:__imp_GetModuleHandleW
0x1800025be  mov     rbx, rax
0x1800025c1  test    rax, rax
0x1800025c4  jz      short loc_180002645
0x1800025c6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800025cd  mov     rcx, rbx; hModule
0x1800025d0  call    cs:__imp_GetProcAddress
0x1800025d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800025dd  mov     rcx, rbx; hModule
0x1800025e0  mov     rdi, rax
0x1800025e3  call    cs:__imp_GetProcAddress
0x1800025e9  test    rdi, rdi
0x1800025ec  jz      short loc_180002603
0x1800025ee  test    rax, rax
0x1800025f1  jz      short loc_180002603
0x1800025f3  mov     cs:qword_1800C72D8, rdi
0x1800025fa  mov     cs:qword_1800C72E0, rax
0x180002601  jmp     short loc_180002621
0x180002603  xor     r9d, r9d; lpName
0x180002606  xor     r8d, r8d; bInitialState
0x180002609  xor     ecx, ecx; lpEventAttributes
0x18000260b  lea     edx, [r9+1]; bManualReset
0x18000260f  call    cs:__imp_CreateEventW
0x180002615  mov     cs:hHandle, rax
0x18000261c  test    rax, rax
0x18000261f  jz      short loc_180002645
0x180002621  xor     ecx, ecx
0x180002623  call    __scrt_initialize_onexit_tables
0x180002628  test    al, al
0x18000262a  jz      short loc_180002645
0x18000262c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002633  call    atexit
0x180002638  mov     rbx, [rsp+28h+arg_0]
0x18000263d  xor     eax, eax
0x18000263f  add     rsp, 20h
0x180002643  pop     rdi
0x180002644  retn
0x180002645  mov     ecx, 7
0x18000264a  call    __scrt_fastfail
```
