# __scrt_initialize_thread_safe_statics

- ea: `0x1800203f0`
- end: `0x1800204c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800200e0`
- `0x1800202b0`
- `0x1800203f0`
- `0x180020798`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020413`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020428`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020413`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020428`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020453`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020453`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180020406`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180020406`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002047f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002047f`

## string_xrefs

- `0x18002040c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180020421`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180044448, 0xFA0u);
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
    qword_180044470 = (__int64)ProcAddress;
    qword_180044478 = (__int64)v2;
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
0x1800203f0  mov     [rsp+arg_0], rbx
0x1800203f5  push    rdi
0x1800203f6  sub     rsp, 20h
0x1800203fa  mov     edx, 0FA0h; dwSpinCount
0x1800203ff  lea     rcx, stru_180044448; lpCriticalSection
0x180020406  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002040c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x180020413  call    cs:__imp_GetModuleHandleW
0x180020419  mov     rbx, rax
0x18002041c  test    rax, rax
0x18002041f  jnz     short loc_180020436
0x180020421  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180020428  call    cs:__imp_GetModuleHandleW
0x18002042e  mov     rbx, rax
0x180020431  test    rax, rax
0x180020434  jz      short loc_1800204B5
0x180020436  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18002043d  mov     rcx, rbx; hModule
0x180020440  call    cs:__imp_GetProcAddress
0x180020446  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18002044d  mov     rcx, rbx; hModule
0x180020450  mov     rdi, rax
0x180020453  call    cs:__imp_GetProcAddress
0x180020459  test    rdi, rdi
0x18002045c  jz      short loc_180020473
0x18002045e  test    rax, rax
0x180020461  jz      short loc_180020473
0x180020463  mov     cs:qword_180044470, rdi
0x18002046a  mov     cs:qword_180044478, rax
0x180020471  jmp     short loc_180020491
0x180020473  xor     r9d, r9d; lpName
0x180020476  xor     r8d, r8d; bInitialState
0x180020479  xor     ecx, ecx; lpEventAttributes
0x18002047b  lea     edx, [r9+1]; bManualReset
0x18002047f  call    cs:__imp_CreateEventW
0x180020485  mov     cs:hHandle, rax
0x18002048c  test    rax, rax
0x18002048f  jz      short loc_1800204B5
0x180020491  xor     ecx, ecx
0x180020493  call    __scrt_initialize_onexit_tables
0x180020498  test    al, al
0x18002049a  jz      short loc_1800204B5
0x18002049c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800204a3  call    atexit
0x1800204a8  mov     rbx, [rsp+28h+arg_0]
0x1800204ad  xor     eax, eax
0x1800204af  add     rsp, 20h
0x1800204b3  pop     rdi
0x1800204b4  retn
0x1800204b5  mov     ecx, 7
0x1800204ba  call    __scrt_fastfail
```
