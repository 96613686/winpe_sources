# __scrt_initialize_thread_safe_statics

- ea: `0x180006280`
- end: `0x180006350`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005500`
- `0x1800056d0`
- `0x180005834`
- `0x180006280`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800062b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800062e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006296`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006296`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000630f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000630f`

## string_xrefs

- `0x18000629c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800062b1`: `kernel32.dll`

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
    qword_180021450 = (__int64)ProcAddress;
    qword_180021458 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x180006280  mov     [rsp+arg_0], rbx
0x180006285  push    rdi
0x180006286  sub     rsp, 20h
0x18000628a  mov     edx, 0FA0h; dwSpinCount
0x18000628f  lea     rcx, CriticalSection; lpCriticalSection
0x180006296  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000629c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800062a3  call    cs:__imp_GetModuleHandleW
0x1800062a9  mov     rbx, rax
0x1800062ac  test    rax, rax
0x1800062af  jnz     short loc_1800062C6
0x1800062b1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800062b8  call    cs:__imp_GetModuleHandleW
0x1800062be  mov     rbx, rax
0x1800062c1  test    rax, rax
0x1800062c4  jz      short loc_180006345
0x1800062c6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800062cd  mov     rcx, rbx; hModule
0x1800062d0  call    cs:__imp_GetProcAddress
0x1800062d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800062dd  mov     rcx, rbx; hModule
0x1800062e0  mov     rdi, rax
0x1800062e3  call    cs:__imp_GetProcAddress
0x1800062e9  test    rdi, rdi
0x1800062ec  jz      short loc_180006303
0x1800062ee  test    rax, rax
0x1800062f1  jz      short loc_180006303
0x1800062f3  mov     cs:qword_180021450, rdi
0x1800062fa  mov     cs:qword_180021458, rax
0x180006301  jmp     short loc_180006321
0x180006303  xor     r9d, r9d; lpName
0x180006306  xor     r8d, r8d; bInitialState
0x180006309  xor     ecx, ecx; lpEventAttributes
0x18000630b  lea     edx, [r9+1]; bManualReset
0x18000630f  call    cs:__imp_CreateEventW
0x180006315  mov     cs:hObject, rax
0x18000631c  test    rax, rax
0x18000631f  jz      short loc_180006345
0x180006321  xor     ecx, ecx
0x180006323  call    __scrt_initialize_onexit_tables
0x180006328  test    al, al
0x18000632a  jz      short loc_180006345
0x18000632c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180006333  call    atexit
0x180006338  mov     rbx, [rsp+28h+arg_0]
0x18000633d  xor     eax, eax
0x18000633f  add     rsp, 20h
0x180006343  pop     rdi
0x180006344  retn
0x180006345  mov     ecx, 7
0x18000634a  call    __scrt_fastfail
```
