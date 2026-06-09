# __scrt_initialize_thread_safe_statics

- ea: `0x140006960`
- end: `0x140006a30`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400054d4`
- `0x1400056a4`
- `0x140005c54`
- `0x140006960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006998`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006983`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006998`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400069b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400069c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400069b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400069c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400069ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400069ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140006976`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140006976`

## string_xrefs

- `0x14000697c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140006991`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_14015F208, 0xFA0u);
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
    qword_14015F230 = (__int64)ProcAddress;
    qword_14015F238 = (__int64)v2;
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
0x140006960  mov     [rsp+arg_0], rbx
0x140006965  push    rdi
0x140006966  sub     rsp, 20h
0x14000696a  mov     edx, 0FA0h; dwSpinCount
0x14000696f  lea     rcx, stru_14015F208; lpCriticalSection
0x140006976  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000697c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140006983  call    cs:__imp_GetModuleHandleW
0x140006989  mov     rbx, rax
0x14000698c  test    rax, rax
0x14000698f  jnz     short loc_1400069A6
0x140006991  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140006998  call    cs:__imp_GetModuleHandleW
0x14000699e  mov     rbx, rax
0x1400069a1  test    rax, rax
0x1400069a4  jz      short loc_140006A25
0x1400069a6  lea     rdx, ProcName; "SleepConditionVariableCS"
0x1400069ad  mov     rcx, rbx; hModule
0x1400069b0  call    cs:__imp_GetProcAddress
0x1400069b6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x1400069bd  mov     rcx, rbx; hModule
0x1400069c0  mov     rdi, rax
0x1400069c3  call    cs:__imp_GetProcAddress
0x1400069c9  test    rdi, rdi
0x1400069cc  jz      short loc_1400069E3
0x1400069ce  test    rax, rax
0x1400069d1  jz      short loc_1400069E3
0x1400069d3  mov     cs:qword_14015F230, rdi
0x1400069da  mov     cs:qword_14015F238, rax
0x1400069e1  jmp     short loc_140006A01
0x1400069e3  xor     r9d, r9d; lpName
0x1400069e6  xor     r8d, r8d; bInitialState
0x1400069e9  xor     ecx, ecx; lpEventAttributes
0x1400069eb  lea     edx, [r9+1]; bManualReset
0x1400069ef  call    cs:__imp_CreateEventW
0x1400069f5  mov     cs:hHandle, rax
0x1400069fc  test    rax, rax
0x1400069ff  jz      short loc_140006A25
0x140006a01  xor     ecx, ecx
0x140006a03  call    __scrt_initialize_onexit_tables
0x140006a08  test    al, al
0x140006a0a  jz      short loc_140006A25
0x140006a0c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x140006a13  call    atexit
0x140006a18  mov     rbx, [rsp+28h+arg_0]
0x140006a1d  xor     eax, eax
0x140006a1f  add     rsp, 20h
0x140006a23  pop     rdi
0x140006a24  retn
0x140006a25  mov     ecx, 7
0x140006a2a  call    __scrt_fastfail
```
