# __scrt_initialize_thread_safe_statics

- ea: `0x180004c50`
- end: `0x180004d20`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002c94`
- `0x180002e64`
- `0x180002fe8`
- `0x180004c50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c88`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004c88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ca0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004cb3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004cdf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004cdf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004c66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004c66`

## string_xrefs

- `0x180004c6c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004c81`: `kernel32.dll`

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
    qword_1801877F0 = (__int64)ProcAddress;
    qword_1801877F8 = (__int64)v2;
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
0x180004c50  mov     [rsp+arg_0], rbx
0x180004c55  push    rdi
0x180004c56  sub     rsp, 20h
0x180004c5a  mov     edx, 0FA0h; dwSpinCount
0x180004c5f  lea     rcx, CriticalSection; lpCriticalSection
0x180004c66  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004c6c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004c73  call    cs:__imp_GetModuleHandleW
0x180004c79  mov     rbx, rax
0x180004c7c  test    rax, rax
0x180004c7f  jnz     short loc_180004C96
0x180004c81  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004c88  call    cs:__imp_GetModuleHandleW
0x180004c8e  mov     rbx, rax
0x180004c91  test    rax, rax
0x180004c94  jz      short loc_180004D15
0x180004c96  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004c9d  mov     rcx, rbx; hModule
0x180004ca0  call    cs:__imp_GetProcAddress
0x180004ca6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004cad  mov     rcx, rbx; hModule
0x180004cb0  mov     rdi, rax
0x180004cb3  call    cs:__imp_GetProcAddress
0x180004cb9  test    rdi, rdi
0x180004cbc  jz      short loc_180004CD3
0x180004cbe  test    rax, rax
0x180004cc1  jz      short loc_180004CD3
0x180004cc3  mov     cs:qword_1801877F0, rdi
0x180004cca  mov     cs:qword_1801877F8, rax
0x180004cd1  jmp     short loc_180004CF1
0x180004cd3  xor     r9d, r9d; lpName
0x180004cd6  xor     r8d, r8d; bInitialState
0x180004cd9  xor     ecx, ecx; lpEventAttributes
0x180004cdb  lea     edx, [r9+1]; bManualReset
0x180004cdf  call    cs:__imp_CreateEventW
0x180004ce5  mov     cs:hHandle, rax
0x180004cec  test    rax, rax
0x180004cef  jz      short loc_180004D15
0x180004cf1  xor     ecx, ecx
0x180004cf3  call    __scrt_initialize_onexit_tables
0x180004cf8  test    al, al
0x180004cfa  jz      short loc_180004D15
0x180004cfc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004d03  call    atexit
0x180004d08  mov     rbx, [rsp+28h+arg_0]
0x180004d0d  xor     eax, eax
0x180004d0f  add     rsp, 20h
0x180004d13  pop     rdi
0x180004d14  retn
0x180004d15  mov     ecx, 7
0x180004d1a  call    __scrt_fastfail
```
