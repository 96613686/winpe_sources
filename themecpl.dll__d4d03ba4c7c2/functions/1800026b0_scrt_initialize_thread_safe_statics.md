# __scrt_initialize_thread_safe_statics

- ea: `0x1800026b0`
- end: `0x180002780`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002460`
- `0x180002630`
- `0x1800026b0`
- `0x180002aa8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002700`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002713`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002700`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002713`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800026d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800026e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800026d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800026e8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800026c6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800026c6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000273f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000273f`

## string_xrefs

- `0x1800026cc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800026e1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18006FCA8, 0xFA0u);
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
    qword_18006FCD0 = (__int64)ProcAddress;
    qword_18006FCD8 = (__int64)v2;
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
0x1800026b0  mov     [rsp+arg_0], rbx
0x1800026b5  push    rdi
0x1800026b6  sub     rsp, 20h
0x1800026ba  mov     edx, 0FA0h; dwSpinCount
0x1800026bf  lea     rcx, stru_18006FCA8; lpCriticalSection
0x1800026c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800026cc  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800026d3  call    cs:__imp_GetModuleHandleW
0x1800026d9  mov     rbx, rax
0x1800026dc  test    rax, rax
0x1800026df  jnz     short loc_1800026F6
0x1800026e1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800026e8  call    cs:__imp_GetModuleHandleW
0x1800026ee  mov     rbx, rax
0x1800026f1  test    rax, rax
0x1800026f4  jz      short loc_180002775
0x1800026f6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800026fd  mov     rcx, rbx; hModule
0x180002700  call    cs:__imp_GetProcAddress
0x180002706  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18000270d  mov     rcx, rbx; hModule
0x180002710  mov     rdi, rax
0x180002713  call    cs:__imp_GetProcAddress
0x180002719  test    rdi, rdi
0x18000271c  jz      short loc_180002733
0x18000271e  test    rax, rax
0x180002721  jz      short loc_180002733
0x180002723  mov     cs:qword_18006FCD0, rdi
0x18000272a  mov     cs:qword_18006FCD8, rax
0x180002731  jmp     short loc_180002751
0x180002733  xor     r9d, r9d; lpName
0x180002736  xor     r8d, r8d; bInitialState
0x180002739  xor     ecx, ecx; lpEventAttributes
0x18000273b  lea     edx, [r9+1]; bManualReset
0x18000273f  call    cs:__imp_CreateEventW
0x180002745  mov     cs:hHandle, rax
0x18000274c  test    rax, rax
0x18000274f  jz      short loc_180002775
0x180002751  xor     ecx, ecx
0x180002753  call    __scrt_initialize_onexit_tables
0x180002758  test    al, al
0x18000275a  jz      short loc_180002775
0x18000275c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180002763  call    atexit
0x180002768  mov     rbx, [rsp+28h+arg_0]
0x18000276d  xor     eax, eax
0x18000276f  add     rsp, 20h
0x180002773  pop     rdi
0x180002774  retn
0x180002775  mov     ecx, 7
0x18000277a  call    __scrt_fastfail
```
