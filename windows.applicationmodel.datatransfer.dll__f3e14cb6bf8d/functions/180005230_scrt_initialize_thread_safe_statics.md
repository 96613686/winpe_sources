# __scrt_initialize_thread_safe_statics

- ea: `0x180005230`
- end: `0x180005300`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002cb0`
- `0x180002e80`
- `0x180002fc4`
- `0x180005230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800052bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800052bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005246`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005246`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005280`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005293`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005280`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005293`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005253`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005268`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005253`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005268`

## string_xrefs

- `0x18000524c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180005261`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800AA958, 0xFA0u);
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
    qword_1800AA980 = (__int64)ProcAddress;
    qword_1800AA988 = (__int64)v2;
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
0x180005230  mov     [rsp+arg_0], rbx
0x180005235  push    rdi
0x180005236  sub     rsp, 20h
0x18000523a  mov     edx, 0FA0h; dwSpinCount
0x18000523f  lea     rcx, stru_1800AA958; lpCriticalSection
0x180005246  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000524c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180005253  call    cs:__imp_GetModuleHandleW
0x180005259  mov     rbx, rax
0x18000525c  test    rax, rax
0x18000525f  jnz     short loc_180005276
0x180005261  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180005268  call    cs:__imp_GetModuleHandleW
0x18000526e  mov     rbx, rax
0x180005271  test    rax, rax
0x180005274  jz      short loc_1800052F5
0x180005276  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18000527d  mov     rcx, rbx; hModule
0x180005280  call    cs:__imp_GetProcAddress
0x180005286  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000528d  mov     rcx, rbx; hModule
0x180005290  mov     rdi, rax
0x180005293  call    cs:__imp_GetProcAddress
0x180005299  test    rdi, rdi
0x18000529c  jz      short loc_1800052B3
0x18000529e  test    rax, rax
0x1800052a1  jz      short loc_1800052B3
0x1800052a3  mov     cs:qword_1800AA980, rdi
0x1800052aa  mov     cs:qword_1800AA988, rax
0x1800052b1  jmp     short loc_1800052D1
0x1800052b3  xor     r9d, r9d; lpName
0x1800052b6  xor     r8d, r8d; bInitialState
0x1800052b9  xor     ecx, ecx; lpEventAttributes
0x1800052bb  lea     edx, [r9+1]; bManualReset
0x1800052bf  call    cs:__imp_CreateEventW
0x1800052c5  mov     cs:hHandle, rax
0x1800052cc  test    rax, rax
0x1800052cf  jz      short loc_1800052F5
0x1800052d1  xor     ecx, ecx
0x1800052d3  call    __scrt_initialize_onexit_tables
0x1800052d8  test    al, al
0x1800052da  jz      short loc_1800052F5
0x1800052dc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800052e3  call    atexit
0x1800052e8  mov     rbx, [rsp+28h+arg_0]
0x1800052ed  xor     eax, eax
0x1800052ef  add     rsp, 20h
0x1800052f3  pop     rdi
0x1800052f4  retn
0x1800052f5  mov     ecx, 7
0x1800052fa  call    __scrt_fastfail
```
