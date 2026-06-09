# __scrt_initialize_thread_safe_statics

- ea: `0x18009af40`
- end: `0x18009b010`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18009af40`
- `0x18009b38c`
- `0x18009b55c`
- `0x18009b6b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18009af56`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18009af56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009afcf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009afcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009af90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009afa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009af90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009afa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009af63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009af78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009af63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009af78`

## string_xrefs

- `0x18009af5c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18009af71`: `kernel32.dll`

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
    qword_180110010 = (__int64)ProcAddress;
    qword_180110018 = (__int64)v2;
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
0x18009af40  mov     [rsp+arg_0], rbx
0x18009af45  push    rdi
0x18009af46  sub     rsp, 20h
0x18009af4a  mov     edx, 0FA0h; dwSpinCount
0x18009af4f  lea     rcx, CriticalSection; lpCriticalSection
0x18009af56  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18009af5c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x18009af63  call    cs:__imp_GetModuleHandleW
0x18009af69  mov     rbx, rax
0x18009af6c  test    rax, rax
0x18009af6f  jnz     short loc_18009AF86
0x18009af71  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18009af78  call    cs:__imp_GetModuleHandleW
0x18009af7e  mov     rbx, rax
0x18009af81  test    rax, rax
0x18009af84  jz      short loc_18009B005
0x18009af86  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18009af8d  mov     rcx, rbx; hModule
0x18009af90  call    cs:__imp_GetProcAddress
0x18009af96  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18009af9d  mov     rcx, rbx; hModule
0x18009afa0  mov     rdi, rax
0x18009afa3  call    cs:__imp_GetProcAddress
0x18009afa9  test    rdi, rdi
0x18009afac  jz      short loc_18009AFC3
0x18009afae  test    rax, rax
0x18009afb1  jz      short loc_18009AFC3
0x18009afb3  mov     cs:qword_180110010, rdi
0x18009afba  mov     cs:qword_180110018, rax
0x18009afc1  jmp     short loc_18009AFE1
0x18009afc3  xor     r9d, r9d; lpName
0x18009afc6  xor     r8d, r8d; bInitialState
0x18009afc9  xor     ecx, ecx; lpEventAttributes
0x18009afcb  lea     edx, [r9+1]; bManualReset
0x18009afcf  call    cs:__imp_CreateEventW
0x18009afd5  mov     cs:hHandle, rax
0x18009afdc  test    rax, rax
0x18009afdf  jz      short loc_18009B005
0x18009afe1  xor     ecx, ecx
0x18009afe3  call    __scrt_initialize_onexit_tables
0x18009afe8  test    al, al
0x18009afea  jz      short loc_18009B005
0x18009afec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18009aff3  call    atexit
0x18009aff8  mov     rbx, [rsp+28h+arg_0]
0x18009affd  xor     eax, eax
0x18009afff  add     rsp, 20h
0x18009b003  pop     rdi
0x18009b004  retn
0x18009b005  mov     ecx, 7
0x18009b00a  call    __scrt_fastfail
```
