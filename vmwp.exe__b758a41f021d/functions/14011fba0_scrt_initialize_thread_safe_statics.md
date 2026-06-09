# __scrt_initialize_thread_safe_statics

- ea: `0x14011fba0`
- end: `0x14011fc70`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14011ebc0`
- `0x14011ed90`
- `0x14011efb0`
- `0x14011fba0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14011fbf0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14011fc03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14011fbf0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14011fc03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14011fbc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14011fbd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14011fbc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14011fbd8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14011fbb6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14011fbb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14011fc2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14011fc2f`

## string_xrefs

- `0x14011fbbc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14011fbd1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1403C3AE8, 0xFA0u);
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
    qword_1403C3B10 = (__int64)ProcAddress;
    qword_1403C3B18 = (__int64)v2;
  }
  else
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
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
0x14011fba0  mov     [rsp+arg_0], rbx
0x14011fba5  push    rdi
0x14011fba6  sub     rsp, 20h
0x14011fbaa  mov     edx, 0FA0h; dwSpinCount
0x14011fbaf  lea     rcx, stru_1403C3AE8; lpCriticalSection
0x14011fbb6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14011fbbc  lea     rcx, aApiMsWinCoreSy_6; "api-ms-win-core-synch-l1-2-0.dll"
0x14011fbc3  call    cs:__imp_GetModuleHandleW
0x14011fbc9  mov     rbx, rax
0x14011fbcc  test    rax, rax
0x14011fbcf  jnz     short loc_14011FBE6
0x14011fbd1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x14011fbd8  call    cs:__imp_GetModuleHandleW
0x14011fbde  mov     rbx, rax
0x14011fbe1  test    rax, rax
0x14011fbe4  jz      short loc_14011FC65
0x14011fbe6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x14011fbed  mov     rcx, rbx; hModule
0x14011fbf0  call    cs:__imp_GetProcAddress
0x14011fbf6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14011fbfd  mov     rcx, rbx; hModule
0x14011fc00  mov     rdi, rax
0x14011fc03  call    cs:__imp_GetProcAddress
0x14011fc09  test    rdi, rdi
0x14011fc0c  jz      short loc_14011FC23
0x14011fc0e  test    rax, rax
0x14011fc11  jz      short loc_14011FC23
0x14011fc13  mov     cs:qword_1403C3B10, rdi
0x14011fc1a  mov     cs:qword_1403C3B18, rax
0x14011fc21  jmp     short loc_14011FC41
0x14011fc23  xor     r9d, r9d; lpName
0x14011fc26  xor     r8d, r8d; bInitialState
0x14011fc29  xor     ecx, ecx; lpEventAttributes
0x14011fc2b  lea     edx, [r9+1]; bManualReset
0x14011fc2f  call    cs:__imp_CreateEventW
0x14011fc35  mov     cs:hEvent, rax
0x14011fc3c  test    rax, rax
0x14011fc3f  jz      short loc_14011FC65
0x14011fc41  xor     ecx, ecx
0x14011fc43  call    __scrt_initialize_onexit_tables
0x14011fc48  test    al, al
0x14011fc4a  jz      short loc_14011FC65
0x14011fc4c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14011fc53  call    atexit
0x14011fc58  mov     rbx, [rsp+28h+arg_0]
0x14011fc5d  xor     eax, eax
0x14011fc5f  add     rsp, 20h
0x14011fc63  pop     rdi
0x14011fc64  retn
0x14011fc65  mov     ecx, 7
0x14011fc6a  call    __scrt_fastfail
```
