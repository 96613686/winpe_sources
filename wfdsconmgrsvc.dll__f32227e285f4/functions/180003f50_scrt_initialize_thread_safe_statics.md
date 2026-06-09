# __scrt_initialize_thread_safe_statics

- ea: `0x180003f50`
- end: `0x180004020`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002920`
- `0x180002af0`
- `0x180002b20`
- `0x180003f50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f88`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003fa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003fb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003fa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003fb3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f66`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003f66`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003fdf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180003fdf`

## string_xrefs

- `0x180003f6c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180003f81`: `kernel32.dll`

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
    qword_1800925D8 = (__int64)ProcAddress;
    qword_1800925E0 = (__int64)v2;
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
0x180003f50  mov     [rsp+arg_0], rbx
0x180003f55  push    rdi
0x180003f56  sub     rsp, 20h
0x180003f5a  mov     edx, 0FA0h; dwSpinCount
0x180003f5f  lea     rcx, CriticalSection; lpCriticalSection
0x180003f66  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003f6c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180003f73  call    cs:__imp_GetModuleHandleW
0x180003f79  mov     rbx, rax
0x180003f7c  test    rax, rax
0x180003f7f  jnz     short loc_180003F96
0x180003f81  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180003f88  call    cs:__imp_GetModuleHandleW
0x180003f8e  mov     rbx, rax
0x180003f91  test    rax, rax
0x180003f94  jz      short loc_180004015
0x180003f96  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180003f9d  mov     rcx, rbx; hModule
0x180003fa0  call    cs:__imp_GetProcAddress
0x180003fa6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180003fad  mov     rcx, rbx; hModule
0x180003fb0  mov     rdi, rax
0x180003fb3  call    cs:__imp_GetProcAddress
0x180003fb9  test    rdi, rdi
0x180003fbc  jz      short loc_180003FD3
0x180003fbe  test    rax, rax
0x180003fc1  jz      short loc_180003FD3
0x180003fc3  mov     cs:qword_1800925D8, rdi
0x180003fca  mov     cs:qword_1800925E0, rax
0x180003fd1  jmp     short loc_180003FF1
0x180003fd3  xor     r9d, r9d; lpName
0x180003fd6  xor     r8d, r8d; bInitialState
0x180003fd9  xor     ecx, ecx; lpEventAttributes
0x180003fdb  lea     edx, [r9+1]; bManualReset
0x180003fdf  call    cs:__imp_CreateEventW
0x180003fe5  mov     cs:hHandle, rax
0x180003fec  test    rax, rax
0x180003fef  jz      short loc_180004015
0x180003ff1  xor     ecx, ecx
0x180003ff3  call    __scrt_initialize_onexit_tables
0x180003ff8  test    al, al
0x180003ffa  jz      short loc_180004015
0x180003ffc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004003  call    atexit
0x180004008  mov     rbx, [rsp+28h+arg_0]
0x18000400d  xor     eax, eax
0x18000400f  add     rsp, 20h
0x180004013  pop     rdi
0x180004014  retn
0x180004015  mov     ecx, 7
0x18000401a  call    __scrt_fastfail
```
