# __scrt_initialize_thread_safe_statics

- ea: `0x1800359c0`
- end: `0x180035a90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180035770`
- `0x180035940`
- `0x1800359c0`
- `0x180035d68`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180035a10`
- `KERNEL32!GetProcAddress` at `0x180035a23`
- `KERNEL32!GetProcAddress` at `0x180035a10`
- `KERNEL32!GetProcAddress` at `0x180035a23`
- `KERNEL32!GetModuleHandleW` at `0x1800359e3`
- `KERNEL32!GetModuleHandleW` at `0x1800359f8`
- `KERNEL32!GetModuleHandleW` at `0x1800359e3`
- `KERNEL32!GetModuleHandleW` at `0x1800359f8`
- `KERNEL32!CreateEventW` at `0x180035a4f`
- `KERNEL32!CreateEventW` at `0x180035a4f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800359d6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800359d6`

## string_xrefs

- `0x1800359dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800359f1`: `kernel32.dll`

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
    qword_1800957B0 = (__int64)ProcAddress;
    qword_1800957B8 = (__int64)v2;
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
0x1800359c0  mov     [rsp+arg_0], rbx
0x1800359c5  push    rdi
0x1800359c6  sub     rsp, 20h
0x1800359ca  mov     edx, 0FA0h; dwSpinCount
0x1800359cf  lea     rcx, CriticalSection; lpCriticalSection
0x1800359d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800359dc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800359e3  call    cs:__imp_GetModuleHandleW
0x1800359e9  mov     rbx, rax
0x1800359ec  test    rax, rax
0x1800359ef  jnz     short loc_180035A06
0x1800359f1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800359f8  call    cs:__imp_GetModuleHandleW
0x1800359fe  mov     rbx, rax
0x180035a01  test    rax, rax
0x180035a04  jz      short loc_180035A85
0x180035a06  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180035a0d  mov     rcx, rbx; hModule
0x180035a10  call    cs:__imp_GetProcAddress
0x180035a16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180035a1d  mov     rcx, rbx; hModule
0x180035a20  mov     rdi, rax
0x180035a23  call    cs:__imp_GetProcAddress
0x180035a29  test    rdi, rdi
0x180035a2c  jz      short loc_180035A43
0x180035a2e  test    rax, rax
0x180035a31  jz      short loc_180035A43
0x180035a33  mov     cs:qword_1800957B0, rdi
0x180035a3a  mov     cs:qword_1800957B8, rax
0x180035a41  jmp     short loc_180035A61
0x180035a43  xor     r9d, r9d; lpName
0x180035a46  xor     r8d, r8d; bInitialState
0x180035a49  xor     ecx, ecx; lpEventAttributes
0x180035a4b  lea     edx, [r9+1]; bManualReset
0x180035a4f  call    cs:__imp_CreateEventW
0x180035a55  mov     cs:hHandle, rax
0x180035a5c  test    rax, rax
0x180035a5f  jz      short loc_180035A85
0x180035a61  xor     ecx, ecx
0x180035a63  call    __scrt_initialize_onexit_tables
0x180035a68  test    al, al
0x180035a6a  jz      short loc_180035A85
0x180035a6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180035a73  call    atexit
0x180035a78  mov     rbx, [rsp+28h+arg_0]
0x180035a7d  xor     eax, eax
0x180035a7f  add     rsp, 20h
0x180035a83  pop     rdi
0x180035a84  retn
0x180035a85  mov     ecx, 7
0x180035a8a  call    __scrt_fastfail
```
