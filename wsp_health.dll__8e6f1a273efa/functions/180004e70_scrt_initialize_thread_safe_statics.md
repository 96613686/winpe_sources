# __scrt_initialize_thread_safe_statics

- ea: `0x180004e70`
- end: `0x180004f40`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002d30`
- `0x180002f00`
- `0x1800030cc`
- `0x180004e70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004e93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004ea8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ec0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ec0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ed3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004e86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004e86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004eff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004eff`

## string_xrefs

- `0x180004e8c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004ea1`: `kernel32.dll`

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
    qword_180159630 = (__int64)ProcAddress;
    qword_180159638 = (__int64)v2;
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
0x180004e70  mov     [rsp+arg_0], rbx
0x180004e75  push    rdi
0x180004e76  sub     rsp, 20h
0x180004e7a  mov     edx, 0FA0h; dwSpinCount
0x180004e7f  lea     rcx, CriticalSection; lpCriticalSection
0x180004e86  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004e8c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004e93  call    cs:__imp_GetModuleHandleW
0x180004e99  mov     rbx, rax
0x180004e9c  test    rax, rax
0x180004e9f  jnz     short loc_180004EB6
0x180004ea1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004ea8  call    cs:__imp_GetModuleHandleW
0x180004eae  mov     rbx, rax
0x180004eb1  test    rax, rax
0x180004eb4  jz      short loc_180004F35
0x180004eb6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004ebd  mov     rcx, rbx; hModule
0x180004ec0  call    cs:__imp_GetProcAddress
0x180004ec6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004ecd  mov     rcx, rbx; hModule
0x180004ed0  mov     rdi, rax
0x180004ed3  call    cs:__imp_GetProcAddress
0x180004ed9  test    rdi, rdi
0x180004edc  jz      short loc_180004EF3
0x180004ede  test    rax, rax
0x180004ee1  jz      short loc_180004EF3
0x180004ee3  mov     cs:qword_180159630, rdi
0x180004eea  mov     cs:qword_180159638, rax
0x180004ef1  jmp     short loc_180004F11
0x180004ef3  xor     r9d, r9d; lpName
0x180004ef6  xor     r8d, r8d; bInitialState
0x180004ef9  xor     ecx, ecx; lpEventAttributes
0x180004efb  lea     edx, [r9+1]; bManualReset
0x180004eff  call    cs:__imp_CreateEventW
0x180004f05  mov     cs:hHandle, rax
0x180004f0c  test    rax, rax
0x180004f0f  jz      short loc_180004F35
0x180004f11  xor     ecx, ecx
0x180004f13  call    __scrt_initialize_onexit_tables
0x180004f18  test    al, al
0x180004f1a  jz      short loc_180004F35
0x180004f1c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004f23  call    atexit
0x180004f28  mov     rbx, [rsp+28h+arg_0]
0x180004f2d  xor     eax, eax
0x180004f2f  add     rsp, 20h
0x180004f33  pop     rdi
0x180004f34  retn
0x180004f35  mov     ecx, 7
0x180004f3a  call    __scrt_fastfail
```
