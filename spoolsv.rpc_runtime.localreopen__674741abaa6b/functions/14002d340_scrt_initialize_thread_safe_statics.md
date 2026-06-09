# __scrt_initialize_thread_safe_statics

- ea: `0x14002d340`
- end: `0x14002d410`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14002d144`
- `0x14002d314`
- `0x14002d340`
- `0x14002d730`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d363`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d378`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d363`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002d378`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002d390`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002d3a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002d390`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002d3a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14002d356`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14002d356`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002d3cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002d3cf`

## string_xrefs

- `0x14002d35c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14002d371`: `kernel32.dll`

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
    qword_1400D2250 = (__int64)ProcAddress;
    qword_1400D2258 = (__int64)v2;
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
0x14002d340  mov     [rsp+arg_0], rbx
0x14002d345  push    rdi
0x14002d346  sub     rsp, 20h
0x14002d34a  mov     edx, 0FA0h; dwSpinCount
0x14002d34f  lea     rcx, CriticalSection; lpCriticalSection
0x14002d356  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14002d35c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x14002d363  call    cs:__imp_GetModuleHandleW
0x14002d369  mov     rbx, rax
0x14002d36c  test    rax, rax
0x14002d36f  jnz     short loc_14002D386
0x14002d371  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x14002d378  call    cs:__imp_GetModuleHandleW
0x14002d37e  mov     rbx, rax
0x14002d381  test    rax, rax
0x14002d384  jz      short loc_14002D405
0x14002d386  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x14002d38d  mov     rcx, rbx; hModule
0x14002d390  call    cs:__imp_GetProcAddress
0x14002d396  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14002d39d  mov     rcx, rbx; hModule
0x14002d3a0  mov     rdi, rax
0x14002d3a3  call    cs:__imp_GetProcAddress
0x14002d3a9  test    rdi, rdi
0x14002d3ac  jz      short loc_14002D3C3
0x14002d3ae  test    rax, rax
0x14002d3b1  jz      short loc_14002D3C3
0x14002d3b3  mov     cs:qword_1400D2250, rdi
0x14002d3ba  mov     cs:qword_1400D2258, rax
0x14002d3c1  jmp     short loc_14002D3E1
0x14002d3c3  xor     r9d, r9d; lpName
0x14002d3c6  xor     r8d, r8d; bInitialState
0x14002d3c9  xor     ecx, ecx; lpEventAttributes
0x14002d3cb  lea     edx, [r9+1]; bManualReset
0x14002d3cf  call    cs:__imp_CreateEventW
0x14002d3d5  mov     cs:hHandle, rax
0x14002d3dc  test    rax, rax
0x14002d3df  jz      short loc_14002D405
0x14002d3e1  xor     ecx, ecx
0x14002d3e3  call    __scrt_initialize_onexit_tables
0x14002d3e8  test    al, al
0x14002d3ea  jz      short loc_14002D405
0x14002d3ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14002d3f3  call    atexit
0x14002d3f8  mov     rbx, [rsp+28h+arg_0]
0x14002d3fd  xor     eax, eax
0x14002d3ff  add     rsp, 20h
0x14002d403  pop     rdi
0x14002d404  retn
0x14002d405  mov     ecx, 7
0x14002d40a  call    __scrt_fastfail
```
