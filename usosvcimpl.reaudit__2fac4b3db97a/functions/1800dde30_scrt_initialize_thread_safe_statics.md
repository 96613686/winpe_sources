# __scrt_initialize_thread_safe_statics

- ea: `0x1800dde30`
- end: `0x1800ddf00`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800ddc04`
- `0x1800dddd4`
- `0x1800dde30`
- `0x1800de960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dde80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dde93`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dde80`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dde93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800dde53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800dde68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800dde53`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800dde68`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800dde46`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800dde46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ddebf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ddebf`

## string_xrefs

- `0x1800dde4c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800dde61`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18014F788, 0xFA0u);
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
    qword_18014F7B0 = (__int64)ProcAddress;
    qword_18014F7B8 = (__int64)v2;
    goto LABEL_7;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x1800DDEFFLL);
  }
LABEL_7:
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
    goto LABEL_9;
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x1800dde30  mov     [rsp+arg_0], rbx
0x1800dde35  push    rdi
0x1800dde36  sub     rsp, 20h
0x1800dde3a  mov     edx, 0FA0h; dwSpinCount
0x1800dde3f  lea     rcx, stru_18014F788; lpCriticalSection
0x1800dde46  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800dde4c  lea     rcx, aApiMsWinCoreSy_5; "api-ms-win-core-synch-l1-2-0.dll"
0x1800dde53  call    cs:__imp_GetModuleHandleW
0x1800dde59  mov     rbx, rax
0x1800dde5c  test    rax, rax
0x1800dde5f  jnz     short loc_1800DDE76
0x1800dde61  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800dde68  call    cs:__imp_GetModuleHandleW
0x1800dde6e  mov     rbx, rax
0x1800dde71  test    rax, rax
0x1800dde74  jz      short loc_1800DDEF5
0x1800dde76  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800dde7d  mov     rcx, rbx; hModule
0x1800dde80  call    cs:__imp_GetProcAddress
0x1800dde86  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800dde8d  mov     rcx, rbx; hModule
0x1800dde90  mov     rdi, rax
0x1800dde93  call    cs:__imp_GetProcAddress
0x1800dde99  test    rdi, rdi
0x1800dde9c  jz      short loc_1800DDEB3
0x1800dde9e  test    rax, rax
0x1800ddea1  jz      short loc_1800DDEB3
0x1800ddea3  mov     cs:qword_18014F7B0, rdi
0x1800ddeaa  mov     cs:qword_18014F7B8, rax
0x1800ddeb1  jmp     short loc_1800DDED1
0x1800ddeb3  xor     r9d, r9d; lpName
0x1800ddeb6  xor     r8d, r8d; bInitialState
0x1800ddeb9  xor     ecx, ecx; lpEventAttributes
0x1800ddebb  lea     edx, [r9+1]; bManualReset
0x1800ddebf  call    cs:__imp_CreateEventW
0x1800ddec5  mov     cs:hHandle, rax
0x1800ddecc  test    rax, rax
0x1800ddecf  jz      short loc_1800DDEF5
0x1800dded1  xor     ecx, ecx
0x1800dded3  call    __scrt_initialize_onexit_tables
0x1800dded8  test    al, al
0x1800ddeda  jz      short loc_1800DDEF5
0x1800ddedc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800ddee3  call    atexit
0x1800ddee8  mov     rbx, [rsp+28h+arg_0]
0x1800ddeed  xor     eax, eax
0x1800ddeef  add     rsp, 20h
0x1800ddef3  pop     rdi
0x1800ddef4  retn
0x1800ddef5  mov     ecx, 7
0x1800ddefa  call    __scrt_fastfail
```
