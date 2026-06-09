# __scrt_initialize_thread_safe_statics

- ea: `0x1801892c0`
- end: `0x180189390`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180189090`
- `0x180189260`
- `0x1801892c0`
- `0x180189748`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801892e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801892f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801892e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801892f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180189310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180189323`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180189310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180189323`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1801892d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1801892d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18018934f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18018934f`

## string_xrefs

- `0x1801892dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1801892f1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180367228, 0xFA0u);
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
    qword_180367250 = (__int64)ProcAddress;
    qword_180367258 = (__int64)v2;
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
0x1801892c0  mov     [rsp+arg_0], rbx
0x1801892c5  push    rdi
0x1801892c6  sub     rsp, 20h
0x1801892ca  mov     edx, 0FA0h; dwSpinCount
0x1801892cf  lea     rcx, stru_180367228; lpCriticalSection
0x1801892d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1801892dc  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x1801892e3  call    cs:__imp_GetModuleHandleW
0x1801892e9  mov     rbx, rax
0x1801892ec  test    rax, rax
0x1801892ef  jnz     short loc_180189306
0x1801892f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1801892f8  call    cs:__imp_GetModuleHandleW
0x1801892fe  mov     rbx, rax
0x180189301  test    rax, rax
0x180189304  jz      short loc_180189385
0x180189306  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18018930d  mov     rcx, rbx; hModule
0x180189310  call    cs:__imp_GetProcAddress
0x180189316  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18018931d  mov     rcx, rbx; hModule
0x180189320  mov     rdi, rax
0x180189323  call    cs:__imp_GetProcAddress
0x180189329  test    rdi, rdi
0x18018932c  jz      short loc_180189343
0x18018932e  test    rax, rax
0x180189331  jz      short loc_180189343
0x180189333  mov     cs:qword_180367250, rdi
0x18018933a  mov     cs:qword_180367258, rax
0x180189341  jmp     short loc_180189361
0x180189343  xor     r9d, r9d; lpName
0x180189346  xor     r8d, r8d; bInitialState
0x180189349  xor     ecx, ecx; lpEventAttributes
0x18018934b  lea     edx, [r9+1]; bManualReset
0x18018934f  call    cs:__imp_CreateEventW
0x180189355  mov     cs:hHandle, rax
0x18018935c  test    rax, rax
0x18018935f  jz      short loc_180189385
0x180189361  xor     ecx, ecx
0x180189363  call    __scrt_initialize_onexit_tables
0x180189368  test    al, al
0x18018936a  jz      short loc_180189385
0x18018936c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180189373  call    atexit
0x180189378  mov     rbx, [rsp+28h+arg_0]
0x18018937d  xor     eax, eax
0x18018937f  add     rsp, 20h
0x180189383  pop     rdi
0x180189384  retn
0x180189385  mov     ecx, 7
0x18018938a  call    __scrt_fastfail
```
