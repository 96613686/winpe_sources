# __scrt_initialize_thread_safe_statics

- ea: `0x180032820`
- end: `0x1800328f0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800324ac`
- `0x18003267c`
- `0x180032820`
- `0x180032bc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032870`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032883`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032870`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032883`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032843`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032858`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032843`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032858`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800328af`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800328af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180032836`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180032836`

## string_xrefs

- `0x18003283c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180032851`: `kernel32.dll`

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
    qword_1801288D0 = (__int64)ProcAddress;
    qword_1801288D8 = (__int64)v2;
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
0x180032820  mov     [rsp+arg_0], rbx
0x180032825  push    rdi
0x180032826  sub     rsp, 20h
0x18003282a  mov     edx, 0FA0h; dwSpinCount
0x18003282f  lea     rcx, CriticalSection; lpCriticalSection
0x180032836  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003283c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180032843  call    cs:__imp_GetModuleHandleW
0x180032849  mov     rbx, rax
0x18003284c  test    rax, rax
0x18003284f  jnz     short loc_180032866
0x180032851  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180032858  call    cs:__imp_GetModuleHandleW
0x18003285e  mov     rbx, rax
0x180032861  test    rax, rax
0x180032864  jz      short loc_1800328E5
0x180032866  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18003286d  mov     rcx, rbx; hModule
0x180032870  call    cs:__imp_GetProcAddress
0x180032876  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18003287d  mov     rcx, rbx; hModule
0x180032880  mov     rdi, rax
0x180032883  call    cs:__imp_GetProcAddress
0x180032889  test    rdi, rdi
0x18003288c  jz      short loc_1800328A3
0x18003288e  test    rax, rax
0x180032891  jz      short loc_1800328A3
0x180032893  mov     cs:qword_1801288D0, rdi
0x18003289a  mov     cs:qword_1801288D8, rax
0x1800328a1  jmp     short loc_1800328C1
0x1800328a3  xor     r9d, r9d; lpName
0x1800328a6  xor     r8d, r8d; bInitialState
0x1800328a9  xor     ecx, ecx; lpEventAttributes
0x1800328ab  lea     edx, [r9+1]; bManualReset
0x1800328af  call    cs:__imp_CreateEventW
0x1800328b5  mov     cs:hHandle, rax
0x1800328bc  test    rax, rax
0x1800328bf  jz      short loc_1800328E5
0x1800328c1  xor     ecx, ecx
0x1800328c3  call    __scrt_initialize_onexit_tables
0x1800328c8  test    al, al
0x1800328ca  jz      short loc_1800328E5
0x1800328cc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800328d3  call    atexit
0x1800328d8  mov     rbx, [rsp+28h+arg_0]
0x1800328dd  xor     eax, eax
0x1800328df  add     rsp, 20h
0x1800328e3  pop     rdi
0x1800328e4  retn
0x1800328e5  mov     ecx, 7
0x1800328ea  call    __scrt_fastfail
```
