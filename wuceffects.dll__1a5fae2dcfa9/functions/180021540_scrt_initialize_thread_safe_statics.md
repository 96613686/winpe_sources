# __scrt_initialize_thread_safe_statics

- ea: `0x180021540`
- end: `0x180021610`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002131c`
- `0x1800214ec`
- `0x180021540`
- `0x180021b8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021563`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021578`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021563`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021578`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021590`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021590`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180021556`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180021556`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800215cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800215cf`

## string_xrefs

- `0x18002155c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180021571`: `kernel32.dll`

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
    qword_18003F0F0 = (__int64)ProcAddress;
    qword_18003F0F8 = (__int64)v2;
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
0x180021540  mov     [rsp+arg_0], rbx
0x180021545  push    rdi
0x180021546  sub     rsp, 20h
0x18002154a  mov     edx, 0FA0h; dwSpinCount
0x18002154f  lea     rcx, CriticalSection; lpCriticalSection
0x180021556  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002155c  lea     rcx, aApiMsWinCoreSy_1; "api-ms-win-core-synch-l1-2-0.dll"
0x180021563  call    cs:__imp_GetModuleHandleW
0x180021569  mov     rbx, rax
0x18002156c  test    rax, rax
0x18002156f  jnz     short loc_180021586
0x180021571  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180021578  call    cs:__imp_GetModuleHandleW
0x18002157e  mov     rbx, rax
0x180021581  test    rax, rax
0x180021584  jz      short loc_180021605
0x180021586  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18002158d  mov     rcx, rbx; hModule
0x180021590  call    cs:__imp_GetProcAddress
0x180021596  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18002159d  mov     rcx, rbx; hModule
0x1800215a0  mov     rdi, rax
0x1800215a3  call    cs:__imp_GetProcAddress
0x1800215a9  test    rdi, rdi
0x1800215ac  jz      short loc_1800215C3
0x1800215ae  test    rax, rax
0x1800215b1  jz      short loc_1800215C3
0x1800215b3  mov     cs:qword_18003F0F0, rdi
0x1800215ba  mov     cs:qword_18003F0F8, rax
0x1800215c1  jmp     short loc_1800215E1
0x1800215c3  xor     r9d, r9d; lpName
0x1800215c6  xor     r8d, r8d; bInitialState
0x1800215c9  xor     ecx, ecx; lpEventAttributes
0x1800215cb  lea     edx, [r9+1]; bManualReset
0x1800215cf  call    cs:__imp_CreateEventW
0x1800215d5  mov     cs:hHandle, rax
0x1800215dc  test    rax, rax
0x1800215df  jz      short loc_180021605
0x1800215e1  xor     ecx, ecx
0x1800215e3  call    __scrt_initialize_onexit_tables
0x1800215e8  test    al, al
0x1800215ea  jz      short loc_180021605
0x1800215ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1800215f3  call    atexit
0x1800215f8  mov     rbx, [rsp+28h+arg_0]
0x1800215fd  xor     eax, eax
0x1800215ff  add     rsp, 20h
0x180021603  pop     rdi
0x180021604  retn
0x180021605  mov     ecx, 7
0x18002160a  call    __scrt_fastfail
```
