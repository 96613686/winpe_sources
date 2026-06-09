# __scrt_initialize_thread_safe_statics

- ea: `0x180277440`
- end: `0x180277510`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18015cdb0`
- `0x18015cf80`
- `0x18015d454`
- `0x180277440`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180277490`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802774a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180277490`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802774a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180277463`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180277478`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180277463`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180277478`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180277456`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180277456`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802774cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802774cf`

## string_xrefs

- `0x18027745c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180277471`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1805E88B8, 0xFA0u);
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
    qword_1805E88E0 = (__int64)ProcAddress;
    qword_1805E88E8 = (__int64)v2;
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
0x180277440  mov     [rsp+arg_0], rbx
0x180277445  push    rdi
0x180277446  sub     rsp, 20h
0x18027744a  mov     edx, 0FA0h; dwSpinCount
0x18027744f  lea     rcx, stru_1805E88B8; lpCriticalSection
0x180277456  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18027745c  lea     rcx, aApiMsWinCoreSy_4; "api-ms-win-core-synch-l1-2-0.dll"
0x180277463  call    cs:__imp_GetModuleHandleW
0x180277469  mov     rbx, rax
0x18027746c  test    rax, rax
0x18027746f  jnz     short loc_180277486
0x180277471  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180277478  call    cs:__imp_GetModuleHandleW
0x18027747e  mov     rbx, rax
0x180277481  test    rax, rax
0x180277484  jz      short loc_180277505
0x180277486  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18027748d  mov     rcx, rbx; hModule
0x180277490  call    cs:__imp_GetProcAddress
0x180277496  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18027749d  mov     rcx, rbx; hModule
0x1802774a0  mov     rdi, rax
0x1802774a3  call    cs:__imp_GetProcAddress
0x1802774a9  test    rdi, rdi
0x1802774ac  jz      short loc_1802774C3
0x1802774ae  test    rax, rax
0x1802774b1  jz      short loc_1802774C3
0x1802774b3  mov     cs:qword_1805E88E0, rdi
0x1802774ba  mov     cs:qword_1805E88E8, rax
0x1802774c1  jmp     short loc_1802774E1
0x1802774c3  xor     r9d, r9d; lpName
0x1802774c6  xor     r8d, r8d; bInitialState
0x1802774c9  xor     ecx, ecx; lpEventAttributes
0x1802774cb  lea     edx, [r9+1]; bManualReset
0x1802774cf  call    cs:__imp_CreateEventW
0x1802774d5  mov     cs:hHandle, rax
0x1802774dc  test    rax, rax
0x1802774df  jz      short loc_180277505
0x1802774e1  xor     ecx, ecx
0x1802774e3  call    __scrt_initialize_onexit_tables
0x1802774e8  test    al, al
0x1802774ea  jz      short loc_180277505
0x1802774ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1802774f3  call    atexit
0x1802774f8  mov     rbx, [rsp+28h+arg_0]
0x1802774fd  xor     eax, eax
0x1802774ff  add     rsp, 20h
0x180277503  pop     rdi
0x180277504  retn
0x180277505  mov     ecx, 7
0x18027750a  call    __scrt_fastfail
```
