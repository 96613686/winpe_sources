# __scrt_initialize_thread_safe_statics

- ea: `0x14000fb30`
- end: `0x14000fc00`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000f8c8`
- `0x14000fa98`
- `0x14000fb30`
- `0x140010250`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fb80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fb93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fb80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000fb93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fb68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000fbbf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000fbbf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14000fb46`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14000fb46`

## string_xrefs

- `0x14000fb4c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x14000fb61`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_140082FB0, 0xFA0u);
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
    qword_140082FD8 = (__int64)ProcAddress;
    qword_140082FE0 = (__int64)v2;
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
0x14000fb30  mov     [rsp+arg_0], rbx
0x14000fb35  push    rdi
0x14000fb36  sub     rsp, 20h
0x14000fb3a  mov     edx, 0FA0h; dwSpinCount
0x14000fb3f  lea     rcx, stru_140082FB0; lpCriticalSection
0x14000fb46  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000fb4c  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x14000fb53  call    cs:__imp_GetModuleHandleW
0x14000fb59  mov     rbx, rax
0x14000fb5c  test    rax, rax
0x14000fb5f  jnz     short loc_14000FB76
0x14000fb61  lea     rcx, aKernel32Dll; "kernel32.dll"
0x14000fb68  call    cs:__imp_GetModuleHandleW
0x14000fb6e  mov     rbx, rax
0x14000fb71  test    rax, rax
0x14000fb74  jz      short loc_14000FBF5
0x14000fb76  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x14000fb7d  mov     rcx, rbx; hModule
0x14000fb80  call    cs:__imp_GetProcAddress
0x14000fb86  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000fb8d  mov     rcx, rbx; hModule
0x14000fb90  mov     rdi, rax
0x14000fb93  call    cs:__imp_GetProcAddress
0x14000fb99  test    rdi, rdi
0x14000fb9c  jz      short loc_14000FBB3
0x14000fb9e  test    rax, rax
0x14000fba1  jz      short loc_14000FBB3
0x14000fba3  mov     cs:qword_140082FD8, rdi
0x14000fbaa  mov     cs:qword_140082FE0, rax
0x14000fbb1  jmp     short loc_14000FBD1
0x14000fbb3  xor     r9d, r9d; lpName
0x14000fbb6  xor     r8d, r8d; bInitialState
0x14000fbb9  xor     ecx, ecx; lpEventAttributes
0x14000fbbb  lea     edx, [r9+1]; bManualReset
0x14000fbbf  call    cs:__imp_CreateEventW
0x14000fbc5  mov     cs:hHandle, rax
0x14000fbcc  test    rax, rax
0x14000fbcf  jz      short loc_14000FBF5
0x14000fbd1  xor     ecx, ecx
0x14000fbd3  call    __scrt_initialize_onexit_tables
0x14000fbd8  test    al, al
0x14000fbda  jz      short loc_14000FBF5
0x14000fbdc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x14000fbe3  call    atexit
0x14000fbe8  mov     rbx, [rsp+28h+arg_0]
0x14000fbed  xor     eax, eax
0x14000fbef  add     rsp, 20h
0x14000fbf3  pop     rdi
0x14000fbf4  retn
0x14000fbf5  mov     ecx, 7
0x14000fbfa  call    __scrt_fastfail
```
