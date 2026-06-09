# __scrt_initialize_thread_safe_statics

- ea: `0x180004210`
- end: `0x1800042e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800034f8`
- `0x1800036c8`
- `0x180003874`
- `0x180004210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004226`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004226`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000429f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000429f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004233`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004248`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004233`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004248`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004260`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004273`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004260`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004273`

## string_xrefs

- `0x18000422c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004241`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180034808, 0xFA0u);
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
    qword_180034830 = (__int64)ProcAddress;
    qword_180034838 = (__int64)v2;
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
0x180004210  mov     [rsp+arg_0], rbx
0x180004215  push    rdi
0x180004216  sub     rsp, 20h
0x18000421a  mov     edx, 0FA0h; dwSpinCount
0x18000421f  lea     rcx, stru_180034808; lpCriticalSection
0x180004226  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000422c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004233  call    cs:__imp_GetModuleHandleW
0x180004239  mov     rbx, rax
0x18000423c  test    rax, rax
0x18000423f  jnz     short loc_180004256
0x180004241  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004248  call    cs:__imp_GetModuleHandleW
0x18000424e  mov     rbx, rax
0x180004251  test    rax, rax
0x180004254  jz      short loc_1800042D5
0x180004256  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000425d  mov     rcx, rbx; hModule
0x180004260  call    cs:__imp_GetProcAddress
0x180004266  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000426d  mov     rcx, rbx; hModule
0x180004270  mov     rdi, rax
0x180004273  call    cs:__imp_GetProcAddress
0x180004279  test    rdi, rdi
0x18000427c  jz      short loc_180004293
0x18000427e  test    rax, rax
0x180004281  jz      short loc_180004293
0x180004283  mov     cs:qword_180034830, rdi
0x18000428a  mov     cs:qword_180034838, rax
0x180004291  jmp     short loc_1800042B1
0x180004293  xor     r9d, r9d; lpName
0x180004296  xor     r8d, r8d; bInitialState
0x180004299  xor     ecx, ecx; lpEventAttributes
0x18000429b  lea     edx, [r9+1]; bManualReset
0x18000429f  call    cs:__imp_CreateEventW
0x1800042a5  mov     cs:hHandle, rax
0x1800042ac  test    rax, rax
0x1800042af  jz      short loc_1800042D5
0x1800042b1  xor     ecx, ecx
0x1800042b3  call    __scrt_initialize_onexit_tables
0x1800042b8  test    al, al
0x1800042ba  jz      short loc_1800042D5
0x1800042bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800042c3  call    atexit
0x1800042c8  mov     rbx, [rsp+28h+arg_0]
0x1800042cd  xor     eax, eax
0x1800042cf  add     rsp, 20h
0x1800042d3  pop     rdi
0x1800042d4  retn
0x1800042d5  mov     ecx, 7
0x1800042da  call    __scrt_fastfail
```
