# __scrt_initialize_thread_safe_statics

- ea: `0x1800052c0`
- end: `0x180005390`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003410`
- `0x1800035e0`
- `0x180003718`
- `0x1800052c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000534f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000534f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800052d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800052d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800052f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005323`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005323`

## string_xrefs

- `0x1800052dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800052f1`: `kernel32.dll`

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
    qword_1800756B0 = (__int64)ProcAddress;
    qword_1800756B8 = (__int64)v2;
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
0x1800052c0  mov     [rsp+arg_0], rbx
0x1800052c5  push    rdi
0x1800052c6  sub     rsp, 20h
0x1800052ca  mov     edx, 0FA0h; dwSpinCount
0x1800052cf  lea     rcx, CriticalSection; lpCriticalSection
0x1800052d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800052dc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800052e3  call    cs:__imp_GetModuleHandleW
0x1800052e9  mov     rbx, rax
0x1800052ec  test    rax, rax
0x1800052ef  jnz     short loc_180005306
0x1800052f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800052f8  call    cs:__imp_GetModuleHandleW
0x1800052fe  mov     rbx, rax
0x180005301  test    rax, rax
0x180005304  jz      short loc_180005385
0x180005306  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000530d  mov     rcx, rbx; hModule
0x180005310  call    cs:__imp_GetProcAddress
0x180005316  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000531d  mov     rcx, rbx; hModule
0x180005320  mov     rdi, rax
0x180005323  call    cs:__imp_GetProcAddress
0x180005329  test    rdi, rdi
0x18000532c  jz      short loc_180005343
0x18000532e  test    rax, rax
0x180005331  jz      short loc_180005343
0x180005333  mov     cs:qword_1800756B0, rdi
0x18000533a  mov     cs:qword_1800756B8, rax
0x180005341  jmp     short loc_180005361
0x180005343  xor     r9d, r9d; lpName
0x180005346  xor     r8d, r8d; bInitialState
0x180005349  xor     ecx, ecx; lpEventAttributes
0x18000534b  lea     edx, [r9+1]; bManualReset
0x18000534f  call    cs:__imp_CreateEventW
0x180005355  mov     cs:hHandle, rax
0x18000535c  test    rax, rax
0x18000535f  jz      short loc_180005385
0x180005361  xor     ecx, ecx
0x180005363  call    __scrt_initialize_onexit_tables
0x180005368  test    al, al
0x18000536a  jz      short loc_180005385
0x18000536c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180005373  call    atexit
0x180005378  mov     rbx, [rsp+28h+arg_0]
0x18000537d  xor     eax, eax
0x18000537f  add     rsp, 20h
0x180005383  pop     rdi
0x180005384  retn
0x180005385  mov     ecx, 7
0x18000538a  call    __scrt_fastfail
```
