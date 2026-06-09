# __scrt_initialize_thread_safe_statics

- ea: `0x180095b40`
- end: `0x180095c10`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800901c0`
- `0x180090390`
- `0x180090af4`
- `0x180095b40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180095b63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180095b78`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180095b63`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180095b78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095b90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095ba3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095b90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180095ba3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095bcf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095bcf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180095b56`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180095b56`

## string_xrefs

- `0x180095b5c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180095b71`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180184E80, 0xFA0u);
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
    qword_180184EA8 = (__int64)ProcAddress;
    qword_180184EB0 = (__int64)v2;
    goto LABEL_7;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x180095C0FLL);
  }
LABEL_7:
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
    goto LABEL_9;
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180095b40  mov     [rsp+arg_0], rbx
0x180095b45  push    rdi
0x180095b46  sub     rsp, 20h
0x180095b4a  mov     edx, 0FA0h; dwSpinCount
0x180095b4f  lea     rcx, stru_180184E80; lpCriticalSection
0x180095b56  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180095b5c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180095b63  call    cs:__imp_GetModuleHandleW
0x180095b69  mov     rbx, rax
0x180095b6c  test    rax, rax
0x180095b6f  jnz     short loc_180095B86
0x180095b71  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180095b78  call    cs:__imp_GetModuleHandleW
0x180095b7e  mov     rbx, rax
0x180095b81  test    rax, rax
0x180095b84  jz      short loc_180095C05
0x180095b86  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180095b8d  mov     rcx, rbx; hModule
0x180095b90  call    cs:__imp_GetProcAddress
0x180095b96  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180095b9d  mov     rcx, rbx; hModule
0x180095ba0  mov     rdi, rax
0x180095ba3  call    cs:__imp_GetProcAddress
0x180095ba9  test    rdi, rdi
0x180095bac  jz      short loc_180095BC3
0x180095bae  test    rax, rax
0x180095bb1  jz      short loc_180095BC3
0x180095bb3  mov     cs:qword_180184EA8, rdi
0x180095bba  mov     cs:qword_180184EB0, rax
0x180095bc1  jmp     short loc_180095BE1
0x180095bc3  xor     r9d, r9d; lpName
0x180095bc6  xor     r8d, r8d; bInitialState
0x180095bc9  xor     ecx, ecx; lpEventAttributes
0x180095bcb  lea     edx, [r9+1]; bManualReset
0x180095bcf  call    cs:__imp_CreateEventW
0x180095bd5  mov     cs:hHandle, rax
0x180095bdc  test    rax, rax
0x180095bdf  jz      short loc_180095C05
0x180095be1  xor     ecx, ecx
0x180095be3  call    __scrt_initialize_onexit_tables
0x180095be8  test    al, al
0x180095bea  jz      short loc_180095C05
0x180095bec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180095bf3  call    atexit
0x180095bf8  mov     rbx, [rsp+28h+arg_0]
0x180095bfd  xor     eax, eax
0x180095bff  add     rsp, 20h
0x180095c03  pop     rdi
0x180095c04  retn
0x180095c05  mov     ecx, 7
0x180095c0a  call    __scrt_fastfail
```
