# __scrt_initialize_thread_safe_statics

- ea: `0x180004960`
- end: `0x180004a30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800046f0`
- `0x1800048c0`
- `0x180004960`
- `0x1800051cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800049b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800049c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800049b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800049c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004998`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004998`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800049ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800049ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004976`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004976`

## string_xrefs

- `0x18000497c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180004991`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800BE590, 0xFA0u);
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
    qword_1800BE5B8 = (__int64)ProcAddress;
    qword_1800BE5C0 = (__int64)v2;
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
0x180004960  mov     [rsp+arg_0], rbx
0x180004965  push    rdi
0x180004966  sub     rsp, 20h
0x18000496a  mov     edx, 0FA0h; dwSpinCount
0x18000496f  lea     rcx, stru_1800BE590; lpCriticalSection
0x180004976  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000497c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x180004983  call    cs:__imp_GetModuleHandleW
0x180004989  mov     rbx, rax
0x18000498c  test    rax, rax
0x18000498f  jnz     short loc_1800049A6
0x180004991  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180004998  call    cs:__imp_GetModuleHandleW
0x18000499e  mov     rbx, rax
0x1800049a1  test    rax, rax
0x1800049a4  jz      short loc_180004A25
0x1800049a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800049ad  mov     rcx, rbx; hModule
0x1800049b0  call    cs:__imp_GetProcAddress
0x1800049b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800049bd  mov     rcx, rbx; hModule
0x1800049c0  mov     rdi, rax
0x1800049c3  call    cs:__imp_GetProcAddress
0x1800049c9  test    rdi, rdi
0x1800049cc  jz      short loc_1800049E3
0x1800049ce  test    rax, rax
0x1800049d1  jz      short loc_1800049E3
0x1800049d3  mov     cs:qword_1800BE5B8, rdi
0x1800049da  mov     cs:qword_1800BE5C0, rax
0x1800049e1  jmp     short loc_180004A01
0x1800049e3  xor     r9d, r9d; lpName
0x1800049e6  xor     r8d, r8d; bInitialState
0x1800049e9  xor     ecx, ecx; lpEventAttributes
0x1800049eb  lea     edx, [r9+1]; bManualReset
0x1800049ef  call    cs:__imp_CreateEventW
0x1800049f5  mov     cs:hHandle, rax
0x1800049fc  test    rax, rax
0x1800049ff  jz      short loc_180004A25
0x180004a01  xor     ecx, ecx
0x180004a03  call    __scrt_initialize_onexit_tables
0x180004a08  test    al, al
0x180004a0a  jz      short loc_180004A25
0x180004a0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180004a13  call    atexit
0x180004a18  mov     rbx, [rsp+28h+arg_0]
0x180004a1d  xor     eax, eax
0x180004a1f  add     rsp, 20h
0x180004a23  pop     rdi
0x180004a24  retn
0x180004a25  mov     ecx, 7
0x180004a2a  call    __scrt_fastfail
```
