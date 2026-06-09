# __scrt_initialize_thread_safe_statics

- ea: `0x1800bc1d0`
- end: `0x1800bc2a0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800b9cd0`
- `0x1800b9ea0`
- `0x1800ba024`
- `0x1800bc1d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc233`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc220`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bc233`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bc1f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bc208`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bc1f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800bc208`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc25f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800bc25f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800bc1e6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800bc1e6`

## string_xrefs

- `0x1800bc1ec`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800bc201`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18015D0C0, 0xFA0u);
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
    qword_18015D0E8 = (__int64)ProcAddress;
    qword_18015D0F0 = (__int64)v2;
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
0x1800bc1d0  mov     [rsp+arg_0], rbx
0x1800bc1d5  push    rdi
0x1800bc1d6  sub     rsp, 20h
0x1800bc1da  mov     edx, 0FA0h; dwSpinCount
0x1800bc1df  lea     rcx, stru_18015D0C0; lpCriticalSection
0x1800bc1e6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800bc1ec  lea     rcx, aApiMsWinCoreSy_2; "api-ms-win-core-synch-l1-2-0.dll"
0x1800bc1f3  call    cs:__imp_GetModuleHandleW
0x1800bc1f9  mov     rbx, rax
0x1800bc1fc  test    rax, rax
0x1800bc1ff  jnz     short loc_1800BC216
0x1800bc201  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800bc208  call    cs:__imp_GetModuleHandleW
0x1800bc20e  mov     rbx, rax
0x1800bc211  test    rax, rax
0x1800bc214  jz      short loc_1800BC295
0x1800bc216  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800bc21d  mov     rcx, rbx; hModule
0x1800bc220  call    cs:__imp_GetProcAddress
0x1800bc226  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800bc22d  mov     rcx, rbx; hModule
0x1800bc230  mov     rdi, rax
0x1800bc233  call    cs:__imp_GetProcAddress
0x1800bc239  test    rdi, rdi
0x1800bc23c  jz      short loc_1800BC253
0x1800bc23e  test    rax, rax
0x1800bc241  jz      short loc_1800BC253
0x1800bc243  mov     cs:qword_18015D0E8, rdi
0x1800bc24a  mov     cs:qword_18015D0F0, rax
0x1800bc251  jmp     short loc_1800BC271
0x1800bc253  xor     r9d, r9d; lpName
0x1800bc256  xor     r8d, r8d; bInitialState
0x1800bc259  xor     ecx, ecx; lpEventAttributes
0x1800bc25b  lea     edx, [r9+1]; bManualReset
0x1800bc25f  call    cs:__imp_CreateEventW
0x1800bc265  mov     cs:hHandle, rax
0x1800bc26c  test    rax, rax
0x1800bc26f  jz      short loc_1800BC295
0x1800bc271  xor     ecx, ecx
0x1800bc273  call    __scrt_initialize_onexit_tables
0x1800bc278  test    al, al
0x1800bc27a  jz      short loc_1800BC295
0x1800bc27c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800bc283  call    atexit
0x1800bc288  mov     rbx, [rsp+28h+arg_0]
0x1800bc28d  xor     eax, eax
0x1800bc28f  add     rsp, 20h
0x1800bc293  pop     rdi
0x1800bc294  retn
0x1800bc295  mov     ecx, 7
0x1800bc29a  call    __scrt_fastfail
```
