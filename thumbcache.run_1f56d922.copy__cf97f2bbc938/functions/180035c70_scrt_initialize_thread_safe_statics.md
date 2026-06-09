# __scrt_initialize_thread_safe_statics

- ea: `0x180035c70`
- end: `0x180035d40`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180035a78`
- `0x180035c48`
- `0x180035c70`
- `0x180036054`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035c93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035ca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035c93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180035ca8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035cc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035cd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035cc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035cd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035cff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180035cff`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035c86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180035c86`

## string_xrefs

- `0x180035c8c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180035ca1`: `kernel32.dll`

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
    qword_180062510 = (__int64)ProcAddress;
    qword_180062518 = (__int64)v2;
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
0x180035c70  mov     [rsp+arg_0], rbx
0x180035c75  push    rdi
0x180035c76  sub     rsp, 20h
0x180035c7a  mov     edx, 0FA0h; dwSpinCount
0x180035c7f  lea     rcx, CriticalSection; lpCriticalSection
0x180035c86  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180035c8c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180035c93  call    cs:__imp_GetModuleHandleW
0x180035c99  mov     rbx, rax
0x180035c9c  test    rax, rax
0x180035c9f  jnz     short loc_180035CB6
0x180035ca1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180035ca8  call    cs:__imp_GetModuleHandleW
0x180035cae  mov     rbx, rax
0x180035cb1  test    rax, rax
0x180035cb4  jz      short loc_180035D35
0x180035cb6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180035cbd  mov     rcx, rbx; hModule
0x180035cc0  call    cs:__imp_GetProcAddress
0x180035cc6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180035ccd  mov     rcx, rbx; hModule
0x180035cd0  mov     rdi, rax
0x180035cd3  call    cs:__imp_GetProcAddress
0x180035cd9  test    rdi, rdi
0x180035cdc  jz      short loc_180035CF3
0x180035cde  test    rax, rax
0x180035ce1  jz      short loc_180035CF3
0x180035ce3  mov     cs:qword_180062510, rdi
0x180035cea  mov     cs:qword_180062518, rax
0x180035cf1  jmp     short loc_180035D11
0x180035cf3  xor     r9d, r9d; lpName
0x180035cf6  xor     r8d, r8d; bInitialState
0x180035cf9  xor     ecx, ecx; lpEventAttributes
0x180035cfb  lea     edx, [r9+1]; bManualReset
0x180035cff  call    cs:__imp_CreateEventW
0x180035d05  mov     cs:hEvent, rax
0x180035d0c  test    rax, rax
0x180035d0f  jz      short loc_180035D35
0x180035d11  xor     ecx, ecx
0x180035d13  call    __scrt_initialize_onexit_tables
0x180035d18  test    al, al
0x180035d1a  jz      short loc_180035D35
0x180035d1c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180035d23  call    atexit
0x180035d28  mov     rbx, [rsp+28h+arg_0]
0x180035d2d  xor     eax, eax
0x180035d2f  add     rsp, 20h
0x180035d33  pop     rdi
0x180035d34  retn
0x180035d35  mov     ecx, 7
0x180035d3a  call    __scrt_fastfail
```
