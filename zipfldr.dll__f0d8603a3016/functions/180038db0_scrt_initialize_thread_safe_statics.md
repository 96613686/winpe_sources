# __scrt_initialize_thread_safe_statics

- ea: `0x180038db0`
- end: `0x180038e80`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180037130`
- `0x180037300`
- `0x1800374b8`
- `0x180038db0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038dd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038de8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038dd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038de8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038e13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038e00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038e13`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038e3f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038e3f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180038dc6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180038dc6`

## string_xrefs

- `0x180038dcc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180038de1`: `kernel32.dll`

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
    qword_18008B640 = (__int64)ProcAddress;
    qword_18008B648 = (__int64)v2;
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
0x180038db0  mov     [rsp+arg_0], rbx
0x180038db5  push    rdi
0x180038db6  sub     rsp, 20h
0x180038dba  mov     edx, 0FA0h; dwSpinCount
0x180038dbf  lea     rcx, CriticalSection; lpCriticalSection
0x180038dc6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180038dcc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180038dd3  call    cs:__imp_GetModuleHandleW
0x180038dd9  mov     rbx, rax
0x180038ddc  test    rax, rax
0x180038ddf  jnz     short loc_180038DF6
0x180038de1  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180038de8  call    cs:__imp_GetModuleHandleW
0x180038dee  mov     rbx, rax
0x180038df1  test    rax, rax
0x180038df4  jz      short loc_180038E75
0x180038df6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x180038dfd  mov     rcx, rbx; hModule
0x180038e00  call    cs:__imp_GetProcAddress
0x180038e06  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180038e0d  mov     rcx, rbx; hModule
0x180038e10  mov     rdi, rax
0x180038e13  call    cs:__imp_GetProcAddress
0x180038e19  test    rdi, rdi
0x180038e1c  jz      short loc_180038E33
0x180038e1e  test    rax, rax
0x180038e21  jz      short loc_180038E33
0x180038e23  mov     cs:qword_18008B640, rdi
0x180038e2a  mov     cs:qword_18008B648, rax
0x180038e31  jmp     short loc_180038E51
0x180038e33  xor     r9d, r9d; lpName
0x180038e36  xor     r8d, r8d; bInitialState
0x180038e39  xor     ecx, ecx; lpEventAttributes
0x180038e3b  lea     edx, [r9+1]; bManualReset
0x180038e3f  call    cs:__imp_CreateEventW
0x180038e45  mov     cs:hHandle, rax
0x180038e4c  test    rax, rax
0x180038e4f  jz      short loc_180038E75
0x180038e51  xor     ecx, ecx
0x180038e53  call    __scrt_initialize_onexit_tables
0x180038e58  test    al, al
0x180038e5a  jz      short loc_180038E75
0x180038e5c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180038e63  call    atexit
0x180038e68  mov     rbx, [rsp+28h+arg_0]
0x180038e6d  xor     eax, eax
0x180038e6f  add     rsp, 20h
0x180038e73  pop     rdi
0x180038e74  retn
0x180038e75  mov     ecx, 7
0x180038e7a  call    __scrt_fastfail
```
