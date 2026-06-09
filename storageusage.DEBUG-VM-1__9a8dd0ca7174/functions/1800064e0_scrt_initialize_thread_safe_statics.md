# __scrt_initialize_thread_safe_statics

- ea: `0x1800064e0`
- end: `0x1800065b0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005408`
- `0x1800055d8`
- `0x180005760`
- `0x1800064e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800064f6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800064f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000656f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000656f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006503`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006518`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006503`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006518`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006543`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006530`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006543`

## string_xrefs

- `0x1800064fc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180006511`: `kernel32.dll`

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
    qword_1800405D0 = (__int64)ProcAddress;
    qword_1800405D8 = (__int64)v2;
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
0x1800064e0  mov     [rsp+arg_0], rbx
0x1800064e5  push    rdi
0x1800064e6  sub     rsp, 20h
0x1800064ea  mov     edx, 0FA0h; dwSpinCount
0x1800064ef  lea     rcx, CriticalSection; lpCriticalSection
0x1800064f6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800064fc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180006503  call    cs:__imp_GetModuleHandleW
0x180006509  mov     rbx, rax
0x18000650c  test    rax, rax
0x18000650f  jnz     short loc_180006526
0x180006511  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180006518  call    cs:__imp_GetModuleHandleW
0x18000651e  mov     rbx, rax
0x180006521  test    rax, rax
0x180006524  jz      short loc_1800065A5
0x180006526  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000652d  mov     rcx, rbx; hModule
0x180006530  call    cs:__imp_GetProcAddress
0x180006536  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000653d  mov     rcx, rbx; hModule
0x180006540  mov     rdi, rax
0x180006543  call    cs:__imp_GetProcAddress
0x180006549  test    rdi, rdi
0x18000654c  jz      short loc_180006563
0x18000654e  test    rax, rax
0x180006551  jz      short loc_180006563
0x180006553  mov     cs:qword_1800405D0, rdi
0x18000655a  mov     cs:qword_1800405D8, rax
0x180006561  jmp     short loc_180006581
0x180006563  xor     r9d, r9d; lpName
0x180006566  xor     r8d, r8d; bInitialState
0x180006569  xor     ecx, ecx; lpEventAttributes
0x18000656b  lea     edx, [r9+1]; bManualReset
0x18000656f  call    cs:__imp_CreateEventW
0x180006575  mov     cs:hObject, rax
0x18000657c  test    rax, rax
0x18000657f  jz      short loc_1800065A5
0x180006581  xor     ecx, ecx
0x180006583  call    __scrt_initialize_onexit_tables
0x180006588  test    al, al
0x18000658a  jz      short loc_1800065A5
0x18000658c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180006593  call    atexit
0x180006598  mov     rbx, [rsp+28h+arg_0]
0x18000659d  xor     eax, eax
0x18000659f  add     rsp, 20h
0x1800065a3  pop     rdi
0x1800065a4  retn
0x1800065a5  mov     ecx, 7
0x1800065aa  call    __scrt_fastfail
```
