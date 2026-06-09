# __scrt_initialize_thread_safe_statics

- ea: `0x180007990`
- end: `0x180007a60`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180007734`
- `0x180007904`
- `0x180007990`
- `0x180007d74`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800079f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800079c8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007a1f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007a1f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800079a6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800079a6`

## string_xrefs

- `0x1800079ac`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1800079c1`: `kernel32.dll`

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
    qword_1800AFAD0 = (__int64)ProcAddress;
    qword_1800AFAD8 = (__int64)v2;
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
0x180007990  mov     [rsp+arg_0], rbx
0x180007995  push    rdi
0x180007996  sub     rsp, 20h
0x18000799a  mov     edx, 0FA0h; dwSpinCount
0x18000799f  lea     rcx, CriticalSection; lpCriticalSection
0x1800079a6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800079ac  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x1800079b3  call    cs:__imp_GetModuleHandleW
0x1800079b9  mov     rbx, rax
0x1800079bc  test    rax, rax
0x1800079bf  jnz     short loc_1800079D6
0x1800079c1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800079c8  call    cs:__imp_GetModuleHandleW
0x1800079ce  mov     rbx, rax
0x1800079d1  test    rax, rax
0x1800079d4  jz      short loc_180007A55
0x1800079d6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1800079dd  mov     rcx, rbx; hModule
0x1800079e0  call    cs:__imp_GetProcAddress
0x1800079e6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1800079ed  mov     rcx, rbx; hModule
0x1800079f0  mov     rdi, rax
0x1800079f3  call    cs:__imp_GetProcAddress
0x1800079f9  test    rdi, rdi
0x1800079fc  jz      short loc_180007A13
0x1800079fe  test    rax, rax
0x180007a01  jz      short loc_180007A13
0x180007a03  mov     cs:qword_1800AFAD0, rdi
0x180007a0a  mov     cs:qword_1800AFAD8, rax
0x180007a11  jmp     short loc_180007A31
0x180007a13  xor     r9d, r9d; lpName
0x180007a16  xor     r8d, r8d; bInitialState
0x180007a19  xor     ecx, ecx; lpEventAttributes
0x180007a1b  lea     edx, [r9+1]; bManualReset
0x180007a1f  call    cs:__imp_CreateEventW
0x180007a25  mov     cs:hHandle, rax
0x180007a2c  test    rax, rax
0x180007a2f  jz      short loc_180007A55
0x180007a31  xor     ecx, ecx
0x180007a33  call    __scrt_initialize_onexit_tables
0x180007a38  test    al, al
0x180007a3a  jz      short loc_180007A55
0x180007a3c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180007a43  call    atexit
0x180007a48  mov     rbx, [rsp+28h+arg_0]
0x180007a4d  xor     eax, eax
0x180007a4f  add     rsp, 20h
0x180007a53  pop     rdi
0x180007a54  retn
0x180007a55  mov     ecx, 7
0x180007a5a  call    __scrt_fastfail
```
