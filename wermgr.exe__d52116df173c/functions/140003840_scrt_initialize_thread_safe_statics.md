# __scrt_initialize_thread_safe_statics

- ea: `0x140003840`
- end: `0x140003910`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400026a8`
- `0x140002878`
- `0x1400029d0`
- `0x140003840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003890`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400038a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140003890`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400038a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003863`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003878`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003863`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140003878`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400038cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400038cf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003856`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x140003856`

## string_xrefs

- `0x14000385c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x140003871`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_14002C5E8, 0xFA0u);
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
    qword_14002C610 = (__int64)ProcAddress;
    qword_14002C618 = (__int64)v2;
  }
  else
  {
    hObject = CreateEventW(0, 1, 0, 0);
    if ( !hObject )
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
0x140003840  mov     [rsp+arg_0], rbx
0x140003845  push    rdi
0x140003846  sub     rsp, 20h
0x14000384a  mov     edx, 0FA0h; dwSpinCount
0x14000384f  lea     rcx, stru_14002C5E8; lpCriticalSection
0x140003856  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14000385c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x140003863  call    cs:__imp_GetModuleHandleW
0x140003869  mov     rbx, rax
0x14000386c  test    rax, rax
0x14000386f  jnz     short loc_140003886
0x140003871  lea     rcx, aKernel32Dll; "kernel32.dll"
0x140003878  call    cs:__imp_GetModuleHandleW
0x14000387e  mov     rbx, rax
0x140003881  test    rax, rax
0x140003884  jz      short loc_140003905
0x140003886  lea     rdx, ProcName; "SleepConditionVariableCS"
0x14000388d  mov     rcx, rbx; hModule
0x140003890  call    cs:__imp_GetProcAddress
0x140003896  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x14000389d  mov     rcx, rbx; hModule
0x1400038a0  mov     rdi, rax
0x1400038a3  call    cs:__imp_GetProcAddress
0x1400038a9  test    rdi, rdi
0x1400038ac  jz      short loc_1400038C3
0x1400038ae  test    rax, rax
0x1400038b1  jz      short loc_1400038C3
0x1400038b3  mov     cs:qword_14002C610, rdi
0x1400038ba  mov     cs:qword_14002C618, rax
0x1400038c1  jmp     short loc_1400038E1
0x1400038c3  xor     r9d, r9d; lpName
0x1400038c6  xor     r8d, r8d; bInitialState
0x1400038c9  xor     ecx, ecx; lpEventAttributes
0x1400038cb  lea     edx, [r9+1]; bManualReset
0x1400038cf  call    cs:__imp_CreateEventW
0x1400038d5  mov     cs:hObject, rax
0x1400038dc  test    rax, rax
0x1400038df  jz      short loc_140003905
0x1400038e1  xor     ecx, ecx
0x1400038e3  call    __scrt_initialize_onexit_tables
0x1400038e8  test    al, al
0x1400038ea  jz      short loc_140003905
0x1400038ec  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x1400038f3  call    atexit
0x1400038f8  mov     rbx, [rsp+28h+arg_0]
0x1400038fd  xor     eax, eax
0x1400038ff  add     rsp, 20h
0x140003903  pop     rdi
0x140003904  retn
0x140003905  mov     ecx, 7
0x14000390a  call    __scrt_fastfail
```
