# __scrt_initialize_thread_safe_statics

- ea: `0x10083db80`
- end: `0x10083dc50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x10083d95c`
- `0x10083db2c`
- `0x10083db80`
- `0x10083e018`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x10083dbd0`
- `KERNEL32!GetProcAddress` at `0x10083dbe3`
- `KERNEL32!GetProcAddress` at `0x10083dbd0`
- `KERNEL32!GetProcAddress` at `0x10083dbe3`
- `KERNEL32!GetModuleHandleW` at `0x10083dba3`
- `KERNEL32!GetModuleHandleW` at `0x10083dbb8`
- `KERNEL32!GetModuleHandleW` at `0x10083dba3`
- `KERNEL32!GetModuleHandleW` at `0x10083dbb8`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x10083db96`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x10083db96`
- `KERNEL32!CreateEventW` at `0x10083dc0f`
- `KERNEL32!CreateEventW` at `0x10083dc0f`

## string_xrefs

- `0x10083db9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x10083dbb1`: `kernel32.dll`

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
    qword_100CBBC18 = (__int64)ProcAddress;
    qword_10099F820 = (__int64)v2;
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
0x10083db80  mov     [rsp+arg_0], rbx
0x10083db85  push    rdi
0x10083db86  sub     rsp, 20h
0x10083db8a  mov     edx, 0FA0h; dwSpinCount
0x10083db8f  lea     rcx, CriticalSection; lpCriticalSection
0x10083db96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x10083db9c  lea     rcx, aApiMsWinCoreSy; "api-ms-win-core-synch-l1-2-0.dll"
0x10083dba3  call    cs:__imp_GetModuleHandleW
0x10083dba9  mov     rbx, rax
0x10083dbac  test    rax, rax
0x10083dbaf  jnz     short loc_10083DBC6
0x10083dbb1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x10083dbb8  call    cs:__imp_GetModuleHandleW
0x10083dbbe  mov     rbx, rax
0x10083dbc1  test    rax, rax
0x10083dbc4  jz      short loc_10083DC45
0x10083dbc6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x10083dbcd  mov     rcx, rbx; hModule
0x10083dbd0  call    cs:__imp_GetProcAddress
0x10083dbd6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x10083dbdd  mov     rcx, rbx; hModule
0x10083dbe0  mov     rdi, rax
0x10083dbe3  call    cs:__imp_GetProcAddress
0x10083dbe9  test    rdi, rdi
0x10083dbec  jz      short loc_10083DC03
0x10083dbee  test    rax, rax
0x10083dbf1  jz      short loc_10083DC03
0x10083dbf3  mov     cs:qword_100CBBC18, rdi
0x10083dbfa  mov     cs:qword_10099F820, rax
0x10083dc01  jmp     short loc_10083DC21
0x10083dc03  xor     r9d, r9d; lpName
0x10083dc06  xor     r8d, r8d; bInitialState
0x10083dc09  xor     ecx, ecx; lpEventAttributes
0x10083dc0b  lea     edx, [r9+1]; bManualReset
0x10083dc0f  call    cs:__imp_CreateEventW
0x10083dc15  mov     cs:hHandle, rax
0x10083dc1c  test    rax, rax
0x10083dc1f  jz      short loc_10083DC45
0x10083dc21  xor     ecx, ecx
0x10083dc23  call    __scrt_initialize_onexit_tables
0x10083dc28  test    al, al
0x10083dc2a  jz      short loc_10083DC45
0x10083dc2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x10083dc33  call    atexit
0x10083dc38  mov     rbx, [rsp+28h+arg_0]
0x10083dc3d  xor     eax, eax
0x10083dc3f  add     rsp, 20h
0x10083dc43  pop     rdi
0x10083dc44  retn
0x10083dc45  mov     ecx, 7
0x10083dc4a  call    __scrt_fastfail
0x10083dc4f  int     3; Trap to Debugger
```
