# __scrt_initialize_thread_safe_statics

- ea: `0x140133ac0`
- end: `0x140133b90`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140132ae0`
- `0x140132cb0`
- `0x140132ed0`
- `0x140133ac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133ae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133af8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133ae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140133af8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133b10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133b23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133b10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140133b23`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140133b4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140133b4f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140133ad6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140133ad6`

## string_xrefs

- `0x140133adc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140133af1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1403B7568, 0xFA0u);
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
    qword_1403B7590 = (__int64)ProcAddress;
    qword_1403B7598 = (__int64)v2;
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
0x140133ac0  mov     [rsp+arg_0], rbx
0x140133ac5  push    rdi
0x140133ac6  sub     rsp, 20h
0x140133aca  mov     edx, 0FA0h; dwSpinCount
0x140133acf  lea     rcx, stru_1403B7568; lpCriticalSection
0x140133ad6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x140133adc  lea     rcx, aApiMsWinCoreSy_6; "api-ms-win-core-synch-l1-2-0.dll"
0x140133ae3  call    cs:__imp_GetModuleHandleW
0x140133ae9  mov     rbx, rax
0x140133aec  test    rax, rax
0x140133aef  jnz     short loc_140133B06
0x140133af1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140133af8  call    cs:__imp_GetModuleHandleW
0x140133afe  mov     rbx, rax
0x140133b01  test    rax, rax
0x140133b04  jz      short loc_140133B85
0x140133b06  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x140133b0d  mov     rcx, rbx; hModule
0x140133b10  call    cs:__imp_GetProcAddress
0x140133b16  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x140133b1d  mov     rcx, rbx; hModule
0x140133b20  mov     rdi, rax
0x140133b23  call    cs:__imp_GetProcAddress
0x140133b29  test    rdi, rdi
0x140133b2c  jz      short loc_140133B43
0x140133b2e  test    rax, rax
0x140133b31  jz      short loc_140133B43
0x140133b33  mov     cs:qword_1403B7590, rdi
0x140133b3a  mov     cs:qword_1403B7598, rax
0x140133b41  jmp     short loc_140133B61
0x140133b43  xor     r9d, r9d; lpName
0x140133b46  xor     r8d, r8d; bInitialState
0x140133b49  xor     ecx, ecx; lpEventAttributes
0x140133b4b  lea     edx, [r9+1]; bManualReset
0x140133b4f  call    cs:__imp_CreateEventW
0x140133b55  mov     cs:hEvent, rax
0x140133b5c  test    rax, rax
0x140133b5f  jz      short loc_140133B85
0x140133b61  xor     ecx, ecx
0x140133b63  call    __scrt_initialize_onexit_tables
0x140133b68  test    al, al
0x140133b6a  jz      short loc_140133B85
0x140133b6c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140133b73  call    atexit
0x140133b78  mov     rbx, [rsp+28h+arg_0]
0x140133b7d  xor     eax, eax
0x140133b7f  add     rsp, 20h
0x140133b83  pop     rdi
0x140133b84  retn
0x140133b85  mov     ecx, 7
0x140133b8a  call    __scrt_fastfail
```
