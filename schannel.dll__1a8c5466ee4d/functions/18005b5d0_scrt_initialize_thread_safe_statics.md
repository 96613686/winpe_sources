# __scrt_initialize_thread_safe_statics

- ea: `0x18005b5d0`
- end: `0x18005b6a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18005999c`
- `0x180059b6c`
- `0x180059cc8`
- `0x18005b5d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b633`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b620`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b633`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005b5f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005b608`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005b5f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005b608`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b65f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005b65f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005b5e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18005b5e6`

## string_xrefs

- `0x18005b5ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18005b601`: `kernel32.dll`

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
    qword_1800ADD20 = (__int64)ProcAddress;
    qword_1800ADD28 = (__int64)v2;
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
0x18005b5d0  mov     [rsp+arg_0], rbx
0x18005b5d5  push    rdi
0x18005b5d6  sub     rsp, 20h
0x18005b5da  mov     edx, 0FA0h; dwSpinCount
0x18005b5df  lea     rcx, CriticalSection; lpCriticalSection
0x18005b5e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18005b5ec  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x18005b5f3  call    cs:__imp_GetModuleHandleW
0x18005b5f9  mov     rbx, rax
0x18005b5fc  test    rax, rax
0x18005b5ff  jnz     short loc_18005B616
0x18005b601  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18005b608  call    cs:__imp_GetModuleHandleW
0x18005b60e  mov     rbx, rax
0x18005b611  test    rax, rax
0x18005b614  jz      short loc_18005B695
0x18005b616  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18005b61d  mov     rcx, rbx; hModule
0x18005b620  call    cs:__imp_GetProcAddress
0x18005b626  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18005b62d  mov     rcx, rbx; hModule
0x18005b630  mov     rdi, rax
0x18005b633  call    cs:__imp_GetProcAddress
0x18005b639  test    rdi, rdi
0x18005b63c  jz      short loc_18005B653
0x18005b63e  test    rax, rax
0x18005b641  jz      short loc_18005B653
0x18005b643  mov     cs:qword_1800ADD20, rdi
0x18005b64a  mov     cs:qword_1800ADD28, rax
0x18005b651  jmp     short loc_18005B671
0x18005b653  xor     r9d, r9d; lpName
0x18005b656  xor     r8d, r8d; bInitialState
0x18005b659  xor     ecx, ecx; lpEventAttributes
0x18005b65b  lea     edx, [r9+1]; bManualReset
0x18005b65f  call    cs:__imp_CreateEventW
0x18005b665  mov     cs:hHandle, rax
0x18005b66c  test    rax, rax
0x18005b66f  jz      short loc_18005B695
0x18005b671  xor     ecx, ecx
0x18005b673  call    __scrt_initialize_onexit_tables
0x18005b678  test    al, al
0x18005b67a  jz      short loc_18005B695
0x18005b67c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18005b683  call    atexit
0x18005b688  mov     rbx, [rsp+28h+arg_0]
0x18005b68d  xor     eax, eax
0x18005b68f  add     rsp, 20h
0x18005b693  pop     rdi
0x18005b694  retn
0x18005b695  mov     ecx, 7
0x18005b69a  call    __scrt_fastfail
```
