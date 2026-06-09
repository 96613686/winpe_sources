# __scrt_initialize_thread_safe_statics

- ea: `0x180004500`
- end: `0x1800045d0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180003198`
- `0x180003368`
- `0x1800036e8`
- `0x180004500`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004523`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004538`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004523`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004538`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004550`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004563`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004550`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004563`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000458f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000458f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004516`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004516`

## string_xrefs

- `0x18000451c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004531`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800B5550, 0xFA0u);
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
    qword_1800B5578 = (__int64)ProcAddress;
    qword_1800B5580 = (__int64)v2;
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
0x180004500  mov     [rsp+arg_0], rbx
0x180004505  push    rdi
0x180004506  sub     rsp, 20h
0x18000450a  mov     edx, 0FA0h; dwSpinCount
0x18000450f  lea     rcx, stru_1800B5550; lpCriticalSection
0x180004516  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000451c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004523  call    cs:__imp_GetModuleHandleW
0x180004529  mov     rbx, rax
0x18000452c  test    rax, rax
0x18000452f  jnz     short loc_180004546
0x180004531  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004538  call    cs:__imp_GetModuleHandleW
0x18000453e  mov     rbx, rax
0x180004541  test    rax, rax
0x180004544  jz      short loc_1800045C5
0x180004546  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000454d  mov     rcx, rbx; hModule
0x180004550  call    cs:__imp_GetProcAddress
0x180004556  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000455d  mov     rcx, rbx; hModule
0x180004560  mov     rdi, rax
0x180004563  call    cs:__imp_GetProcAddress
0x180004569  test    rdi, rdi
0x18000456c  jz      short loc_180004583
0x18000456e  test    rax, rax
0x180004571  jz      short loc_180004583
0x180004573  mov     cs:qword_1800B5578, rdi
0x18000457a  mov     cs:qword_1800B5580, rax
0x180004581  jmp     short loc_1800045A1
0x180004583  xor     r9d, r9d; lpName
0x180004586  xor     r8d, r8d; bInitialState
0x180004589  xor     ecx, ecx; lpEventAttributes
0x18000458b  lea     edx, [r9+1]; bManualReset
0x18000458f  call    cs:__imp_CreateEventW
0x180004595  mov     cs:hHandle, rax
0x18000459c  test    rax, rax
0x18000459f  jz      short loc_1800045C5
0x1800045a1  xor     ecx, ecx
0x1800045a3  call    __scrt_initialize_onexit_tables
0x1800045a8  test    al, al
0x1800045aa  jz      short loc_1800045C5
0x1800045ac  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800045b3  call    atexit
0x1800045b8  mov     rbx, [rsp+28h+arg_0]
0x1800045bd  xor     eax, eax
0x1800045bf  add     rsp, 20h
0x1800045c3  pop     rdi
0x1800045c4  retn
0x1800045c5  mov     ecx, 7
0x1800045ca  call    __scrt_fastfail
```
