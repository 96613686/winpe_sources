# __scrt_initialize_thread_safe_statics

- ea: `0x100615680`
- end: `0x100615750`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1006152ac`
- `0x10061547c`
- `0x100615680`
- `0x100615cb4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x10061570f`
- `KERNEL32!CreateEventW` at `0x10061570f`
- `KERNEL32!GetModuleHandleW` at `0x1006156a3`
- `KERNEL32!GetModuleHandleW` at `0x1006156b8`
- `KERNEL32!GetModuleHandleW` at `0x1006156a3`
- `KERNEL32!GetModuleHandleW` at `0x1006156b8`
- `KERNEL32!GetProcAddress` at `0x1006156d0`
- `KERNEL32!GetProcAddress` at `0x1006156e3`
- `KERNEL32!GetProcAddress` at `0x1006156d0`
- `KERNEL32!GetProcAddress` at `0x1006156e3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x100615696`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x100615696`

## string_xrefs

- `0x10061569c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1006156b1`: `kernel32.dll`

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
    qword_1007AB880 = (__int64)ProcAddress;
    qword_1007AB888 = (__int64)v2;
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
0x100615680  mov     [rsp+arg_0], rbx
0x100615685  push    rdi
0x100615686  sub     rsp, 20h
0x10061568a  mov     edx, 0FA0h; dwSpinCount
0x10061568f  lea     rcx, CriticalSection; lpCriticalSection
0x100615696  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x10061569c  lea     rcx, aApiMsWinCoreSy; "api-ms-win-core-synch-l1-2-0.dll"
0x1006156a3  call    cs:__imp_GetModuleHandleW
0x1006156a9  mov     rbx, rax
0x1006156ac  test    rax, rax
0x1006156af  jnz     short loc_1006156C6
0x1006156b1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1006156b8  call    cs:__imp_GetModuleHandleW
0x1006156be  mov     rbx, rax
0x1006156c1  test    rax, rax
0x1006156c4  jz      short loc_100615745
0x1006156c6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1006156cd  mov     rcx, rbx; hModule
0x1006156d0  call    cs:__imp_GetProcAddress
0x1006156d6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1006156dd  mov     rcx, rbx; hModule
0x1006156e0  mov     rdi, rax
0x1006156e3  call    cs:__imp_GetProcAddress
0x1006156e9  test    rdi, rdi
0x1006156ec  jz      short loc_100615703
0x1006156ee  test    rax, rax
0x1006156f1  jz      short loc_100615703
0x1006156f3  mov     cs:qword_1007AB880, rdi
0x1006156fa  mov     cs:qword_1007AB888, rax
0x100615701  jmp     short loc_100615721
0x100615703  xor     r9d, r9d; lpName
0x100615706  xor     r8d, r8d; bInitialState
0x100615709  xor     ecx, ecx; lpEventAttributes
0x10061570b  lea     edx, [r9+1]; bManualReset
0x10061570f  call    cs:__imp_CreateEventW
0x100615715  mov     cs:hHandle, rax
0x10061571c  test    rax, rax
0x10061571f  jz      short loc_100615745
0x100615721  xor     ecx, ecx
0x100615723  call    __scrt_initialize_onexit_tables
0x100615728  test    al, al
0x10061572a  jz      short loc_100615745
0x10061572c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x100615733  call    atexit
0x100615738  mov     rbx, [rsp+28h+arg_0]
0x10061573d  xor     eax, eax
0x10061573f  add     rsp, 20h
0x100615743  pop     rdi
0x100615744  retn
0x100615745  mov     ecx, 7
0x10061574a  call    __scrt_fastfail
0x10061574f  int     3; Trap to Debugger
```
