# __scrt_initialize_thread_safe_statics

- ea: `0x14002ae60`
- end: `0x14002af30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14002ac64`
- `0x14002ae34`
- `0x14002ae60`
- `0x14002b228`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002ae83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002ae98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002ae83`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14002ae98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002aeb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002aec3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002aeb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002aec3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14002ae76`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14002ae76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002aeef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14002aeef`

## string_xrefs

- `0x14002ae7c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14002ae91`: `kernel32.dll`

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
    qword_1400CB0D0 = (__int64)ProcAddress;
    qword_1400CB0D8 = (__int64)v2;
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
0x14002ae60  mov     [rsp+arg_0], rbx
0x14002ae65  push    rdi
0x14002ae66  sub     rsp, 20h
0x14002ae6a  mov     edx, 0FA0h; dwSpinCount
0x14002ae6f  lea     rcx, CriticalSection; lpCriticalSection
0x14002ae76  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14002ae7c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x14002ae83  call    cs:__imp_GetModuleHandleW
0x14002ae89  mov     rbx, rax
0x14002ae8c  test    rax, rax
0x14002ae8f  jnz     short loc_14002AEA6
0x14002ae91  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x14002ae98  call    cs:__imp_GetModuleHandleW
0x14002ae9e  mov     rbx, rax
0x14002aea1  test    rax, rax
0x14002aea4  jz      short loc_14002AF25
0x14002aea6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x14002aead  mov     rcx, rbx; hModule
0x14002aeb0  call    cs:__imp_GetProcAddress
0x14002aeb6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14002aebd  mov     rcx, rbx; hModule
0x14002aec0  mov     rdi, rax
0x14002aec3  call    cs:__imp_GetProcAddress
0x14002aec9  test    rdi, rdi
0x14002aecc  jz      short loc_14002AEE3
0x14002aece  test    rax, rax
0x14002aed1  jz      short loc_14002AEE3
0x14002aed3  mov     cs:qword_1400CB0D0, rdi
0x14002aeda  mov     cs:qword_1400CB0D8, rax
0x14002aee1  jmp     short loc_14002AF01
0x14002aee3  xor     r9d, r9d; lpName
0x14002aee6  xor     r8d, r8d; bInitialState
0x14002aee9  xor     ecx, ecx; lpEventAttributes
0x14002aeeb  lea     edx, [r9+1]; bManualReset
0x14002aeef  call    cs:__imp_CreateEventW
0x14002aef5  mov     cs:hHandle, rax
0x14002aefc  test    rax, rax
0x14002aeff  jz      short loc_14002AF25
0x14002af01  xor     ecx, ecx
0x14002af03  call    __scrt_initialize_onexit_tables
0x14002af08  test    al, al
0x14002af0a  jz      short loc_14002AF25
0x14002af0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14002af13  call    atexit
0x14002af18  mov     rbx, [rsp+28h+arg_0]
0x14002af1d  xor     eax, eax
0x14002af1f  add     rsp, 20h
0x14002af23  pop     rdi
0x14002af24  retn
0x14002af25  mov     ecx, 7
0x14002af2a  call    __scrt_fastfail
```
