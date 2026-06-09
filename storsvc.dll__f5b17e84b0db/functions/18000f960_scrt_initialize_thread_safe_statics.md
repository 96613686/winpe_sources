# __scrt_initialize_thread_safe_statics

- ea: `0x18000f960`
- end: `0x18000fa30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000d210`
- `0x18000d3e0`
- `0x18000da9c`
- `0x18000f960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f9b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f9c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f9b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f9c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f998`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f998`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000f976`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000f976`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f9ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f9ef`

## string_xrefs

- `0x18000f97c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18000f991`: `kernel32.dll`

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
    qword_1800C04E0 = (__int64)ProcAddress;
    qword_1800C04E8 = (__int64)v2;
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
0x18000f960  mov     [rsp+arg_0], rbx
0x18000f965  push    rdi
0x18000f966  sub     rsp, 20h
0x18000f96a  mov     edx, 0FA0h; dwSpinCount
0x18000f96f  lea     rcx, CriticalSection; lpCriticalSection
0x18000f976  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000f97c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x18000f983  call    cs:__imp_GetModuleHandleW
0x18000f989  mov     rbx, rax
0x18000f98c  test    rax, rax
0x18000f98f  jnz     short loc_18000F9A6
0x18000f991  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18000f998  call    cs:__imp_GetModuleHandleW
0x18000f99e  mov     rbx, rax
0x18000f9a1  test    rax, rax
0x18000f9a4  jz      short loc_18000FA25
0x18000f9a6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000f9ad  mov     rcx, rbx; hModule
0x18000f9b0  call    cs:__imp_GetProcAddress
0x18000f9b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000f9bd  mov     rcx, rbx; hModule
0x18000f9c0  mov     rdi, rax
0x18000f9c3  call    cs:__imp_GetProcAddress
0x18000f9c9  test    rdi, rdi
0x18000f9cc  jz      short loc_18000F9E3
0x18000f9ce  test    rax, rax
0x18000f9d1  jz      short loc_18000F9E3
0x18000f9d3  mov     cs:qword_1800C04E0, rdi
0x18000f9da  mov     cs:qword_1800C04E8, rax
0x18000f9e1  jmp     short loc_18000FA01
0x18000f9e3  xor     r9d, r9d; lpName
0x18000f9e6  xor     r8d, r8d; bInitialState
0x18000f9e9  xor     ecx, ecx; lpEventAttributes
0x18000f9eb  lea     edx, [r9+1]; bManualReset
0x18000f9ef  call    cs:__imp_CreateEventW
0x18000f9f5  mov     cs:hObject, rax
0x18000f9fc  test    rax, rax
0x18000f9ff  jz      short loc_18000FA25
0x18000fa01  xor     ecx, ecx
0x18000fa03  call    __scrt_initialize_onexit_tables
0x18000fa08  test    al, al
0x18000fa0a  jz      short loc_18000FA25
0x18000fa0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18000fa13  call    atexit
0x18000fa18  mov     rbx, [rsp+28h+arg_0]
0x18000fa1d  xor     eax, eax
0x18000fa1f  add     rsp, 20h
0x18000fa23  pop     rdi
0x18000fa24  retn
0x18000fa25  mov     ecx, 7
0x18000fa2a  call    __scrt_fastfail
```
