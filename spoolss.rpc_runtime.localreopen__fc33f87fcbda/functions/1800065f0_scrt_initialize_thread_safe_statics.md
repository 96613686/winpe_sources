# __scrt_initialize_thread_safe_statics

- ea: `0x1800065f0`
- end: `0x1800066c0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180005860`
- `0x180005a30`
- `0x180005b94`
- `0x1800065f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006613`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006628`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006613`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006628`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006640`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006653`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006640`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006653`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006606`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180006606`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000667f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000667f`

## string_xrefs

- `0x18000660c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180006621`: `kernel32.dll`

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
    qword_180022450 = (__int64)ProcAddress;
    qword_180022458 = (__int64)v2;
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
0x1800065f0  mov     [rsp+arg_0], rbx
0x1800065f5  push    rdi
0x1800065f6  sub     rsp, 20h
0x1800065fa  mov     edx, 0FA0h; dwSpinCount
0x1800065ff  lea     rcx, CriticalSection; lpCriticalSection
0x180006606  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000660c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x180006613  call    cs:__imp_GetModuleHandleW
0x180006619  mov     rbx, rax
0x18000661c  test    rax, rax
0x18000661f  jnz     short loc_180006636
0x180006621  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180006628  call    cs:__imp_GetModuleHandleW
0x18000662e  mov     rbx, rax
0x180006631  test    rax, rax
0x180006634  jz      short loc_1800066B5
0x180006636  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18000663d  mov     rcx, rbx; hModule
0x180006640  call    cs:__imp_GetProcAddress
0x180006646  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000664d  mov     rcx, rbx; hModule
0x180006650  mov     rdi, rax
0x180006653  call    cs:__imp_GetProcAddress
0x180006659  test    rdi, rdi
0x18000665c  jz      short loc_180006673
0x18000665e  test    rax, rax
0x180006661  jz      short loc_180006673
0x180006663  mov     cs:qword_180022450, rdi
0x18000666a  mov     cs:qword_180022458, rax
0x180006671  jmp     short loc_180006691
0x180006673  xor     r9d, r9d; lpName
0x180006676  xor     r8d, r8d; bInitialState
0x180006679  xor     ecx, ecx; lpEventAttributes
0x18000667b  lea     edx, [r9+1]; bManualReset
0x18000667f  call    cs:__imp_CreateEventW
0x180006685  mov     cs:hObject, rax
0x18000668c  test    rax, rax
0x18000668f  jz      short loc_1800066B5
0x180006691  xor     ecx, ecx
0x180006693  call    __scrt_initialize_onexit_tables
0x180006698  test    al, al
0x18000669a  jz      short loc_1800066B5
0x18000669c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800066a3  call    atexit
0x1800066a8  mov     rbx, [rsp+28h+arg_0]
0x1800066ad  xor     eax, eax
0x1800066af  add     rsp, 20h
0x1800066b3  pop     rdi
0x1800066b4  retn
0x1800066b5  mov     ecx, 7
0x1800066ba  call    __scrt_fastfail
```
