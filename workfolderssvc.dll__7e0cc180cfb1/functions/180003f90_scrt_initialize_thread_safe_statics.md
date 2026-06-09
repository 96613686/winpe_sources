# __scrt_initialize_thread_safe_statics

- ea: `0x180003f90`
- end: `0x180004060`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002da8`
- `0x180002f78`
- `0x180003100`
- `0x180003f90`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180003fe0`
- `KERNEL32!GetProcAddress` at `0x180003ff3`
- `KERNEL32!GetProcAddress` at `0x180003fe0`
- `KERNEL32!GetProcAddress` at `0x180003ff3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003fa6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003fa6`
- `KERNEL32!GetModuleHandleW` at `0x180003fb3`
- `KERNEL32!GetModuleHandleW` at `0x180003fc8`
- `KERNEL32!GetModuleHandleW` at `0x180003fb3`
- `KERNEL32!GetModuleHandleW` at `0x180003fc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000401f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000401f`

## string_xrefs

- `0x180003fac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003fc1`: `kernel32.dll`

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
    qword_1801AF730 = (__int64)ProcAddress;
    qword_1801AF738 = (__int64)v2;
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
0x180003f90  mov     [rsp+arg_0], rbx
0x180003f95  push    rdi
0x180003f96  sub     rsp, 20h
0x180003f9a  mov     edx, 0FA0h; dwSpinCount
0x180003f9f  lea     rcx, CriticalSection; lpCriticalSection
0x180003fa6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003fac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003fb3  call    cs:__imp_GetModuleHandleW
0x180003fb9  mov     rbx, rax
0x180003fbc  test    rax, rax
0x180003fbf  jnz     short loc_180003FD6
0x180003fc1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180003fc8  call    cs:__imp_GetModuleHandleW
0x180003fce  mov     rbx, rax
0x180003fd1  test    rax, rax
0x180003fd4  jz      short loc_180004055
0x180003fd6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180003fdd  mov     rcx, rbx; hModule
0x180003fe0  call    cs:__imp_GetProcAddress
0x180003fe6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180003fed  mov     rcx, rbx; hModule
0x180003ff0  mov     rdi, rax
0x180003ff3  call    cs:__imp_GetProcAddress
0x180003ff9  test    rdi, rdi
0x180003ffc  jz      short loc_180004013
0x180003ffe  test    rax, rax
0x180004001  jz      short loc_180004013
0x180004003  mov     cs:qword_1801AF730, rdi
0x18000400a  mov     cs:qword_1801AF738, rax
0x180004011  jmp     short loc_180004031
0x180004013  xor     r9d, r9d; lpName
0x180004016  xor     r8d, r8d; bInitialState
0x180004019  xor     ecx, ecx; lpEventAttributes
0x18000401b  lea     edx, [r9+1]; bManualReset
0x18000401f  call    cs:__imp_CreateEventW
0x180004025  mov     cs:hHandle, rax
0x18000402c  test    rax, rax
0x18000402f  jz      short loc_180004055
0x180004031  xor     ecx, ecx
0x180004033  call    __scrt_initialize_onexit_tables
0x180004038  test    al, al
0x18000403a  jz      short loc_180004055
0x18000403c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004043  call    atexit
0x180004048  mov     rbx, [rsp+28h+arg_0]
0x18000404d  xor     eax, eax
0x18000404f  add     rsp, 20h
0x180004053  pop     rdi
0x180004054  retn
0x180004055  mov     ecx, 7
0x18000405a  call    __scrt_fastfail
```
