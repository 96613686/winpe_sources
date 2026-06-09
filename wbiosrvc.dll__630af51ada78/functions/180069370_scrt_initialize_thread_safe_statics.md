# __scrt_initialize_thread_safe_statics

- ea: `0x180069370`
- end: `0x180069440`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180069140`
- `0x180069310`
- `0x180069370`
- `0x180069798`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800693c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800693d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800693c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800693d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069393`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800693a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069393`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800693a8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180069386`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180069386`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800693ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800693ff`

## string_xrefs

- `0x18006938c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800693a1`: `kernel32.dll`

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
    qword_18010FD50 = (__int64)ProcAddress;
    qword_18010FD58 = (__int64)v2;
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
0x180069370  mov     [rsp+arg_0], rbx
0x180069375  push    rdi
0x180069376  sub     rsp, 20h
0x18006937a  mov     edx, 0FA0h; dwSpinCount
0x18006937f  lea     rcx, CriticalSection; lpCriticalSection
0x180069386  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18006938c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180069393  call    cs:__imp_GetModuleHandleW
0x180069399  mov     rbx, rax
0x18006939c  test    rax, rax
0x18006939f  jnz     short loc_1800693B6
0x1800693a1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800693a8  call    cs:__imp_GetModuleHandleW
0x1800693ae  mov     rbx, rax
0x1800693b1  test    rax, rax
0x1800693b4  jz      short loc_180069435
0x1800693b6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800693bd  mov     rcx, rbx; hModule
0x1800693c0  call    cs:__imp_GetProcAddress
0x1800693c6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800693cd  mov     rcx, rbx; hModule
0x1800693d0  mov     rdi, rax
0x1800693d3  call    cs:__imp_GetProcAddress
0x1800693d9  test    rdi, rdi
0x1800693dc  jz      short loc_1800693F3
0x1800693de  test    rax, rax
0x1800693e1  jz      short loc_1800693F3
0x1800693e3  mov     cs:qword_18010FD50, rdi
0x1800693ea  mov     cs:qword_18010FD58, rax
0x1800693f1  jmp     short loc_180069411
0x1800693f3  xor     r9d, r9d; lpName
0x1800693f6  xor     r8d, r8d; bInitialState
0x1800693f9  xor     ecx, ecx; lpEventAttributes
0x1800693fb  lea     edx, [r9+1]; bManualReset
0x1800693ff  call    cs:__imp_CreateEventW
0x180069405  mov     cs:hHandle, rax
0x18006940c  test    rax, rax
0x18006940f  jz      short loc_180069435
0x180069411  xor     ecx, ecx
0x180069413  call    __scrt_initialize_onexit_tables
0x180069418  test    al, al
0x18006941a  jz      short loc_180069435
0x18006941c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180069423  call    atexit
0x180069428  mov     rbx, [rsp+28h+arg_0]
0x18006942d  xor     eax, eax
0x18006942f  add     rsp, 20h
0x180069433  pop     rdi
0x180069434  retn
0x180069435  mov     ecx, 7
0x18006943a  call    __scrt_fastfail
```
