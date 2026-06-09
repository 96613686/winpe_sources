# __scrt_initialize_thread_safe_statics

- ea: `0x180002550`
- end: `0x180002620`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800017e4`
- `0x1800019b4`
- `0x1800019e4`
- `0x180002550`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002573`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002588`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002573`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002588`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800025b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800025df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800025df`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002566`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002566`

## string_xrefs

- `0x18000256c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180002581`: `kernel32.dll`

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
0x180002550  mov     [rsp+arg_0], rbx
0x180002555  push    rdi
0x180002556  sub     rsp, 20h
0x18000255a  mov     edx, 0FA0h; dwSpinCount
0x18000255f  lea     rcx, CriticalSection; lpCriticalSection
0x180002566  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000256c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180002573  call    cs:__imp_GetModuleHandleW
0x180002579  mov     rbx, rax
0x18000257c  test    rax, rax
0x18000257f  jnz     short loc_180002596
0x180002581  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180002588  call    cs:__imp_GetModuleHandleW
0x18000258e  mov     rbx, rax
0x180002591  test    rax, rax
0x180002594  jz      short loc_180002615
0x180002596  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000259d  mov     rcx, rbx; hModule
0x1800025a0  call    cs:__imp_GetProcAddress
0x1800025a6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800025ad  mov     rcx, rbx; hModule
0x1800025b0  mov     rdi, rax
0x1800025b3  call    cs:__imp_GetProcAddress
0x1800025b9  test    rdi, rdi
0x1800025bc  jz      short loc_1800025D3
0x1800025be  test    rax, rax
0x1800025c1  jz      short loc_1800025D3
0x1800025c3  mov     cs:qword_1800C72D8, rdi
0x1800025ca  mov     cs:qword_1800C72E0, rax
0x1800025d1  jmp     short loc_1800025F1
0x1800025d3  xor     r9d, r9d; lpName
0x1800025d6  xor     r8d, r8d; bInitialState
0x1800025d9  xor     ecx, ecx; lpEventAttributes
0x1800025db  lea     edx, [r9+1]; bManualReset
0x1800025df  call    cs:__imp_CreateEventW
0x1800025e5  mov     cs:hHandle, rax
0x1800025ec  test    rax, rax
0x1800025ef  jz      short loc_180002615
0x1800025f1  xor     ecx, ecx
0x1800025f3  call    __scrt_initialize_onexit_tables
0x1800025f8  test    al, al
0x1800025fa  jz      short loc_180002615
0x1800025fc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002603  call    atexit
0x180002608  mov     rbx, [rsp+28h+arg_0]
0x18000260d  xor     eax, eax
0x18000260f  add     rsp, 20h
0x180002613  pop     rdi
0x180002614  retn
0x180002615  mov     ecx, 7
0x18000261a  call    __scrt_fastfail
```
