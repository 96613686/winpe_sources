# __scrt_initialize_thread_safe_statics

- ea: `0x180004ce0`
- end: `0x180004db0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002cf4`
- `0x180002ec4`
- `0x180003048`
- `0x180004ce0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004d18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004d43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004d6f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004cf6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004cf6`

## string_xrefs

- `0x180004cfc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004d11`: `kernel32.dll`

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
    qword_180189930 = (__int64)ProcAddress;
    qword_180189938 = (__int64)v2;
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
0x180004ce0  mov     [rsp+arg_0], rbx
0x180004ce5  push    rdi
0x180004ce6  sub     rsp, 20h
0x180004cea  mov     edx, 0FA0h; dwSpinCount
0x180004cef  lea     rcx, CriticalSection; lpCriticalSection
0x180004cf6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004cfc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004d03  call    cs:__imp_GetModuleHandleW
0x180004d09  mov     rbx, rax
0x180004d0c  test    rax, rax
0x180004d0f  jnz     short loc_180004D26
0x180004d11  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004d18  call    cs:__imp_GetModuleHandleW
0x180004d1e  mov     rbx, rax
0x180004d21  test    rax, rax
0x180004d24  jz      short loc_180004DA5
0x180004d26  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180004d2d  mov     rcx, rbx; hModule
0x180004d30  call    cs:__imp_GetProcAddress
0x180004d36  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180004d3d  mov     rcx, rbx; hModule
0x180004d40  mov     rdi, rax
0x180004d43  call    cs:__imp_GetProcAddress
0x180004d49  test    rdi, rdi
0x180004d4c  jz      short loc_180004D63
0x180004d4e  test    rax, rax
0x180004d51  jz      short loc_180004D63
0x180004d53  mov     cs:qword_180189930, rdi
0x180004d5a  mov     cs:qword_180189938, rax
0x180004d61  jmp     short loc_180004D81
0x180004d63  xor     r9d, r9d; lpName
0x180004d66  xor     r8d, r8d; bInitialState
0x180004d69  xor     ecx, ecx; lpEventAttributes
0x180004d6b  lea     edx, [r9+1]; bManualReset
0x180004d6f  call    cs:__imp_CreateEventW
0x180004d75  mov     cs:hHandle, rax
0x180004d7c  test    rax, rax
0x180004d7f  jz      short loc_180004DA5
0x180004d81  xor     ecx, ecx
0x180004d83  call    __scrt_initialize_onexit_tables
0x180004d88  test    al, al
0x180004d8a  jz      short loc_180004DA5
0x180004d8c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004d93  call    atexit
0x180004d98  mov     rbx, [rsp+28h+arg_0]
0x180004d9d  xor     eax, eax
0x180004d9f  add     rsp, 20h
0x180004da3  pop     rdi
0x180004da4  retn
0x180004da5  mov     ecx, 7
0x180004daa  call    __scrt_fastfail
```
