# __scrt_initialize_thread_safe_statics

- ea: `0x180083e80`
- end: `0x180083f50`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800812cc`
- `0x18008149c`
- `0x180081618`
- `0x180083e80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180083ea3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180083eb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180083ea3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180083eb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083ee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083ed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180083ee3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180083f0f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180083f0f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180083e96`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180083e96`

## string_xrefs

- `0x180083e9c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180083eb1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1801134B8, 0xFA0u);
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
    qword_1801134E0 = (__int64)ProcAddress;
    qword_1801134E8 = (__int64)v2;
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
0x180083e80  mov     [rsp+arg_0], rbx
0x180083e85  push    rdi
0x180083e86  sub     rsp, 20h
0x180083e8a  mov     edx, 0FA0h; dwSpinCount
0x180083e8f  lea     rcx, stru_1801134B8; lpCriticalSection
0x180083e96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180083e9c  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180083ea3  call    cs:__imp_GetModuleHandleW
0x180083ea9  mov     rbx, rax
0x180083eac  test    rax, rax
0x180083eaf  jnz     short loc_180083EC6
0x180083eb1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180083eb8  call    cs:__imp_GetModuleHandleW
0x180083ebe  mov     rbx, rax
0x180083ec1  test    rax, rax
0x180083ec4  jz      short loc_180083F45
0x180083ec6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180083ecd  mov     rcx, rbx; hModule
0x180083ed0  call    cs:__imp_GetProcAddress
0x180083ed6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180083edd  mov     rcx, rbx; hModule
0x180083ee0  mov     rdi, rax
0x180083ee3  call    cs:__imp_GetProcAddress
0x180083ee9  test    rdi, rdi
0x180083eec  jz      short loc_180083F03
0x180083eee  test    rax, rax
0x180083ef1  jz      short loc_180083F03
0x180083ef3  mov     cs:qword_1801134E0, rdi
0x180083efa  mov     cs:qword_1801134E8, rax
0x180083f01  jmp     short loc_180083F21
0x180083f03  xor     r9d, r9d; lpName
0x180083f06  xor     r8d, r8d; bInitialState
0x180083f09  xor     ecx, ecx; lpEventAttributes
0x180083f0b  lea     edx, [r9+1]; bManualReset
0x180083f0f  call    cs:__imp_CreateEventW
0x180083f15  mov     cs:hHandle, rax
0x180083f1c  test    rax, rax
0x180083f1f  jz      short loc_180083F45
0x180083f21  xor     ecx, ecx
0x180083f23  call    __scrt_initialize_onexit_tables
0x180083f28  test    al, al
0x180083f2a  jz      short loc_180083F45
0x180083f2c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180083f33  call    atexit
0x180083f38  mov     rbx, [rsp+28h+arg_0]
0x180083f3d  xor     eax, eax
0x180083f3f  add     rsp, 20h
0x180083f43  pop     rdi
0x180083f44  retn
0x180083f45  mov     ecx, 7
0x180083f4a  call    __scrt_fastfail
```
