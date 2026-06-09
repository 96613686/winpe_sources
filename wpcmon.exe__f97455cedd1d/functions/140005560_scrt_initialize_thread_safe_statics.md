# __scrt_initialize_thread_safe_statics

- ea: `0x140005560`
- end: `0x140005630`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140005560`
- `0x1400058b4`
- `0x140005a84`
- `0x140005f38`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400055b0`
- `KERNEL32!GetProcAddress` at `0x1400055c3`
- `KERNEL32!GetProcAddress` at `0x1400055b0`
- `KERNEL32!GetProcAddress` at `0x1400055c3`
- `KERNEL32!GetModuleHandleW` at `0x140005583`
- `KERNEL32!GetModuleHandleW` at `0x140005598`
- `KERNEL32!GetModuleHandleW` at `0x140005583`
- `KERNEL32!GetModuleHandleW` at `0x140005598`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400055ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400055ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140005576`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140005576`

## string_xrefs

- `0x14000557c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140005591`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_14010F9E0, 0xFA0u);
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
    qword_14010FA08 = (__int64)ProcAddress;
    qword_14010FA10 = (__int64)v2;
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
0x140005560  mov     [rsp+arg_0], rbx
0x140005565  push    rdi
0x140005566  sub     rsp, 20h
0x14000556a  mov     edx, 0FA0h; dwSpinCount
0x14000556f  lea     rcx, stru_14010F9E0; lpCriticalSection
0x140005576  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000557c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140005583  call    cs:__imp_GetModuleHandleW
0x140005589  mov     rbx, rax
0x14000558c  test    rax, rax
0x14000558f  jnz     short loc_1400055A6
0x140005591  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140005598  call    cs:__imp_GetModuleHandleW
0x14000559e  mov     rbx, rax
0x1400055a1  test    rax, rax
0x1400055a4  jz      short loc_140005625
0x1400055a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1400055ad  mov     rcx, rbx; hModule
0x1400055b0  call    cs:__imp_GetProcAddress
0x1400055b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1400055bd  mov     rcx, rbx; hModule
0x1400055c0  mov     rdi, rax
0x1400055c3  call    cs:__imp_GetProcAddress
0x1400055c9  test    rdi, rdi
0x1400055cc  jz      short loc_1400055E3
0x1400055ce  test    rax, rax
0x1400055d1  jz      short loc_1400055E3
0x1400055d3  mov     cs:qword_14010FA08, rdi
0x1400055da  mov     cs:qword_14010FA10, rax
0x1400055e1  jmp     short loc_140005601
0x1400055e3  xor     r9d, r9d; lpName
0x1400055e6  xor     r8d, r8d; bInitialState
0x1400055e9  xor     ecx, ecx; lpEventAttributes
0x1400055eb  lea     edx, [r9+1]; bManualReset
0x1400055ef  call    cs:__imp_CreateEventW
0x1400055f5  mov     cs:hHandle, rax
0x1400055fc  test    rax, rax
0x1400055ff  jz      short loc_140005625
0x140005601  xor     ecx, ecx
0x140005603  call    __scrt_initialize_onexit_tables
0x140005608  test    al, al
0x14000560a  jz      short loc_140005625
0x14000560c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140005613  call    atexit
0x140005618  mov     rbx, [rsp+28h+arg_0]
0x14000561d  xor     eax, eax
0x14000561f  add     rsp, 20h
0x140005623  pop     rdi
0x140005624  retn
0x140005625  mov     ecx, 7
0x14000562a  call    __scrt_fastfail
```
