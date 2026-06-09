# __scrt_initialize_thread_safe_statics

- ea: `0x180064d10`
- end: `0x180064de0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180064a4c`
- `0x180064bfc`
- `0x180064d10`
- `0x180065040`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180064d33`
- `KERNEL32!GetModuleHandleW` at `0x180064d48`
- `KERNEL32!GetModuleHandleW` at `0x180064d33`
- `KERNEL32!GetModuleHandleW` at `0x180064d48`
- `KERNEL32!GetProcAddress` at `0x180064d60`
- `KERNEL32!GetProcAddress` at `0x180064d73`
- `KERNEL32!GetProcAddress` at `0x180064d60`
- `KERNEL32!GetProcAddress` at `0x180064d73`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180064d26`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180064d26`
- `KERNEL32!CreateEventW` at `0x180064d9f`
- `KERNEL32!CreateEventW` at `0x180064d9f`

## string_xrefs

- `0x180064d41`: `kernel32.dll`
- `0x180064d2c`: `api-ms-win-core-synch-l1-2-0.dll`

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
    qword_1800942F0 = (__int64)ProcAddress;
    qword_1800942F8 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
  {
LABEL_9:
    _scrt_fastfail(7);
    __debugbreak();
  }
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x180064d10  mov     [rsp+arg_0], rbx
0x180064d15  push    rdi
0x180064d16  sub     rsp, 20h
0x180064d1a  mov     edx, 0FA0h; dwSpinCount
0x180064d1f  lea     rcx, CriticalSection; lpCriticalSection
0x180064d26  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180064d2c  lea     rcx, aApiMsWinCoreSy
0x180064d33  call    cs:__imp_GetModuleHandleW
0x180064d39  mov     rbx, rax
0x180064d3c  test    rax, rax
0x180064d3f  jnz     short loc_180064D56
0x180064d41  lea     rcx, aKernel32Dll_0
0x180064d48  call    cs:__imp_GetModuleHandleW
0x180064d4e  mov     rbx, rax
0x180064d51  test    rax, rax
0x180064d54  jz      short loc_180064DD5
0x180064d56  lea     rdx, aSleepcondition
0x180064d5d  mov     rcx, rbx; hModule
0x180064d60  call    cs:__imp_GetProcAddress
0x180064d66  lea     rdx, aWakeallconditi
0x180064d6d  mov     rcx, rbx; hModule
0x180064d70  mov     rdi, rax
0x180064d73  call    cs:__imp_GetProcAddress
0x180064d79  test    rdi, rdi
0x180064d7c  jz      short loc_180064D93
0x180064d7e  test    rax, rax
0x180064d81  jz      short loc_180064D93
0x180064d83  mov     cs:qword_1800942F0, rdi
0x180064d8a  mov     cs:qword_1800942F8, rax
0x180064d91  jmp     short loc_180064DB1
0x180064d93  xor     r9d, r9d; lpName
0x180064d96  xor     r8d, r8d; bInitialState
0x180064d99  xor     ecx, ecx; lpEventAttributes
0x180064d9b  lea     edx, [r9+1]; bManualReset
0x180064d9f  call    cs:__imp_CreateEventW
0x180064da5  mov     cs:hHandle, rax
0x180064dac  test    rax, rax
0x180064daf  jz      short loc_180064DD5
0x180064db1  xor     ecx, ecx
0x180064db3  call    __scrt_initialize_onexit_tables
0x180064db8  test    al, al
0x180064dba  jz      short loc_180064DD5
0x180064dbc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180064dc3  call    atexit
0x180064dc8  mov     rbx, [rsp+28h+arg_0]
0x180064dcd  xor     eax, eax
0x180064dcf  add     rsp, 20h
0x180064dd3  pop     rdi
0x180064dd4  retn
0x180064dd5  mov     ecx, 7
0x180064dda  call    __scrt_fastfail
0x180064ddf  int     3; Trap to Debugger
```
