# __scrt_initialize_thread_safe_statics

- ea: `0x1400539c0`
- end: `0x140053a90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400537c4`
- `0x140053994`
- `0x1400539c0`
- `0x140053e24`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140053a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140053a23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140053a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140053a23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400539e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400539f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400539e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400539f8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140053a4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140053a4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400539d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1400539d6`

## string_xrefs

- `0x1400539dc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1400539f1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1400D1D28, 0xFA0u);
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
    qword_1400D1D50 = (__int64)ProcAddress;
    qword_1400D1D58 = (__int64)v2;
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
0x1400539c0  mov     [rsp+arg_0], rbx
0x1400539c5  push    rdi
0x1400539c6  sub     rsp, 20h
0x1400539ca  mov     edx, 0FA0h; dwSpinCount
0x1400539cf  lea     rcx, stru_1400D1D28; lpCriticalSection
0x1400539d6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1400539dc  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1400539e3  call    cs:__imp_GetModuleHandleW
0x1400539e9  mov     rbx, rax
0x1400539ec  test    rax, rax
0x1400539ef  jnz     short loc_140053A06
0x1400539f1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1400539f8  call    cs:__imp_GetModuleHandleW
0x1400539fe  mov     rbx, rax
0x140053a01  test    rax, rax
0x140053a04  jz      short loc_140053A85
0x140053a06  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x140053a0d  mov     rcx, rbx; hModule
0x140053a10  call    cs:__imp_GetProcAddress
0x140053a16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140053a1d  mov     rcx, rbx; hModule
0x140053a20  mov     rdi, rax
0x140053a23  call    cs:__imp_GetProcAddress
0x140053a29  test    rdi, rdi
0x140053a2c  jz      short loc_140053A43
0x140053a2e  test    rax, rax
0x140053a31  jz      short loc_140053A43
0x140053a33  mov     cs:qword_1400D1D50, rdi
0x140053a3a  mov     cs:qword_1400D1D58, rax
0x140053a41  jmp     short loc_140053A61
0x140053a43  xor     r9d, r9d; lpName
0x140053a46  xor     r8d, r8d; bInitialState
0x140053a49  xor     ecx, ecx; lpEventAttributes
0x140053a4b  lea     edx, [r9+1]; bManualReset
0x140053a4f  call    cs:__imp_CreateEventW
0x140053a55  mov     cs:hHandle, rax
0x140053a5c  test    rax, rax
0x140053a5f  jz      short loc_140053A85
0x140053a61  xor     ecx, ecx
0x140053a63  call    __scrt_initialize_onexit_tables
0x140053a68  test    al, al
0x140053a6a  jz      short loc_140053A85
0x140053a6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140053a73  call    atexit
0x140053a78  mov     rbx, [rsp+28h+arg_0]
0x140053a7d  xor     eax, eax
0x140053a7f  add     rsp, 20h
0x140053a83  pop     rdi
0x140053a84  retn
0x140053a85  mov     ecx, 7
0x140053a8a  call    __scrt_fastfail
```
