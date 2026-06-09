# __scrt_initialize_thread_safe_statics

- ea: `0x180030760`
- end: `0x180030830`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180030544`
- `0x180030714`
- `0x180030760`
- `0x180030fc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030783`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030798`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030783`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030798`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800307b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800307c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800307b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800307c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800307ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800307ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030776`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030776`

## string_xrefs

- `0x18003077c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180030791`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_18004E958, 0xFA0u);
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
    qword_18004E980 = (__int64)ProcAddress;
    qword_18004E988 = (__int64)v2;
    goto LABEL_7;
  }
  hObject = CreateEventW(0, 1, 0, 0);
  if ( !hObject )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x18003082FLL);
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
0x180030760  mov     [rsp+arg_0], rbx
0x180030765  push    rdi
0x180030766  sub     rsp, 20h
0x18003076a  mov     edx, 0FA0h; dwSpinCount
0x18003076f  lea     rcx, stru_18004E958; lpCriticalSection
0x180030776  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003077c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180030783  call    cs:__imp_GetModuleHandleW
0x180030789  mov     rbx, rax
0x18003078c  test    rax, rax
0x18003078f  jnz     short loc_1800307A6
0x180030791  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180030798  call    cs:__imp_GetModuleHandleW
0x18003079e  mov     rbx, rax
0x1800307a1  test    rax, rax
0x1800307a4  jz      short loc_180030825
0x1800307a6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x1800307ad  mov     rcx, rbx; hModule
0x1800307b0  call    cs:__imp_GetProcAddress
0x1800307b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800307bd  mov     rcx, rbx; hModule
0x1800307c0  mov     rdi, rax
0x1800307c3  call    cs:__imp_GetProcAddress
0x1800307c9  test    rdi, rdi
0x1800307cc  jz      short loc_1800307E3
0x1800307ce  test    rax, rax
0x1800307d1  jz      short loc_1800307E3
0x1800307d3  mov     cs:qword_18004E980, rdi
0x1800307da  mov     cs:qword_18004E988, rax
0x1800307e1  jmp     short loc_180030801
0x1800307e3  xor     r9d, r9d; lpName
0x1800307e6  xor     r8d, r8d; bInitialState
0x1800307e9  xor     ecx, ecx; lpEventAttributes
0x1800307eb  lea     edx, [r9+1]; bManualReset
0x1800307ef  call    cs:__imp_CreateEventW
0x1800307f5  mov     cs:hObject, rax
0x1800307fc  test    rax, rax
0x1800307ff  jz      short loc_180030825
0x180030801  xor     ecx, ecx
0x180030803  call    __scrt_initialize_onexit_tables
0x180030808  test    al, al
0x18003080a  jz      short loc_180030825
0x18003080c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180030813  call    atexit
0x180030818  mov     rbx, [rsp+28h+arg_0]
0x18003081d  xor     eax, eax
0x18003081f  add     rsp, 20h
0x180030823  pop     rdi
0x180030824  retn
0x180030825  mov     ecx, 7
0x18003082a  call    __scrt_fastfail
```
