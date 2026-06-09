# __scrt_initialize_thread_safe_statics

- ea: `0x180002160`
- end: `0x180002230`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001f6c`
- `0x18000213c`
- `0x180002160`
- `0x180002508`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800021ef`
- `KERNEL32!CreateEventW` at `0x1800021ef`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180002176`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180002176`
- `KERNEL32!GetModuleHandleW` at `0x180002183`
- `KERNEL32!GetModuleHandleW` at `0x180002198`
- `KERNEL32!GetModuleHandleW` at `0x180002183`
- `KERNEL32!GetModuleHandleW` at `0x180002198`
- `KERNEL32!GetProcAddress` at `0x1800021b0`
- `KERNEL32!GetProcAddress` at `0x1800021c3`
- `KERNEL32!GetProcAddress` at `0x1800021b0`
- `KERNEL32!GetProcAddress` at `0x1800021c3`

## string_xrefs

- `0x18000217c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002191`: `kernel32.dll`

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
    qword_18002A510 = (__int64)ProcAddress;
    qword_18002A518 = (__int64)v2;
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
0x180002160  mov     [rsp+arg_0], rbx
0x180002165  push    rdi
0x180002166  sub     rsp, 20h
0x18000216a  mov     edx, 0FA0h; dwSpinCount
0x18000216f  lea     rcx, CriticalSection; lpCriticalSection
0x180002176  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000217c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002183  call    cs:__imp_GetModuleHandleW
0x180002189  mov     rbx, rax
0x18000218c  test    rax, rax
0x18000218f  jnz     short loc_1800021A6
0x180002191  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180002198  call    cs:__imp_GetModuleHandleW
0x18000219e  mov     rbx, rax
0x1800021a1  test    rax, rax
0x1800021a4  jz      short loc_180002225
0x1800021a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800021ad  mov     rcx, rbx; hModule
0x1800021b0  call    cs:__imp_GetProcAddress
0x1800021b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800021bd  mov     rcx, rbx; hModule
0x1800021c0  mov     rdi, rax
0x1800021c3  call    cs:__imp_GetProcAddress
0x1800021c9  test    rdi, rdi
0x1800021cc  jz      short loc_1800021E3
0x1800021ce  test    rax, rax
0x1800021d1  jz      short loc_1800021E3
0x1800021d3  mov     cs:qword_18002A510, rdi
0x1800021da  mov     cs:qword_18002A518, rax
0x1800021e1  jmp     short loc_180002201
0x1800021e3  xor     r9d, r9d; lpName
0x1800021e6  xor     r8d, r8d; bInitialState
0x1800021e9  xor     ecx, ecx; lpEventAttributes
0x1800021eb  lea     edx, [r9+1]; bManualReset
0x1800021ef  call    cs:__imp_CreateEventW
0x1800021f5  mov     cs:hHandle, rax
0x1800021fc  test    rax, rax
0x1800021ff  jz      short loc_180002225
0x180002201  xor     ecx, ecx
0x180002203  call    __scrt_initialize_onexit_tables
0x180002208  test    al, al
0x18000220a  jz      short loc_180002225
0x18000220c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002213  call    atexit
0x180002218  mov     rbx, [rsp+28h+arg_0]
0x18000221d  xor     eax, eax
0x18000221f  add     rsp, 20h
0x180002223  pop     rdi
0x180002224  retn
0x180002225  mov     ecx, 7
0x18000222a  call    __scrt_fastfail
```
