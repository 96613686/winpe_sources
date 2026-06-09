# __scrt_initialize_thread_safe_statics

- ea: `0x180106ba0`
- end: `0x180106c70`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1801065f0`
- `0x1801067c0`
- `0x180106ba0`
- `0x180107020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180106bc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180106bd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180106bc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180106bd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106bf0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106c03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106bf0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180106c03`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180106bb6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180106bb6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180106c2f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180106c2f`

## string_xrefs

- `0x180106bbc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180106bd1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1802A0770, 0xFA0u);
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
    qword_1802A0798 = (__int64)ProcAddress;
    qword_1802A07A0 = (__int64)v2;
  }
  else
  {
    qword_1802A0768 = CreateEventW(0, 1, 0, 0);
    if ( !qword_1802A0768 )
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
0x180106ba0  mov     [rsp+arg_0], rbx
0x180106ba5  push    rdi
0x180106ba6  sub     rsp, 20h
0x180106baa  mov     edx, 0FA0h; dwSpinCount
0x180106baf  lea     rcx, stru_1802A0770; lpCriticalSection
0x180106bb6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180106bbc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180106bc3  call    cs:__imp_GetModuleHandleW
0x180106bc9  mov     rbx, rax
0x180106bcc  test    rax, rax
0x180106bcf  jnz     short loc_180106BE6
0x180106bd1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180106bd8  call    cs:__imp_GetModuleHandleW
0x180106bde  mov     rbx, rax
0x180106be1  test    rax, rax
0x180106be4  jz      short loc_180106C65
0x180106be6  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x180106bed  mov     rcx, rbx; hModule
0x180106bf0  call    cs:__imp_GetProcAddress
0x180106bf6  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x180106bfd  mov     rcx, rbx; hModule
0x180106c00  mov     rdi, rax
0x180106c03  call    cs:__imp_GetProcAddress
0x180106c09  test    rdi, rdi
0x180106c0c  jz      short loc_180106C23
0x180106c0e  test    rax, rax
0x180106c11  jz      short loc_180106C23
0x180106c13  mov     cs:qword_1802A0798, rdi
0x180106c1a  mov     cs:qword_1802A07A0, rax
0x180106c21  jmp     short loc_180106C41
0x180106c23  xor     r9d, r9d; lpName
0x180106c26  xor     r8d, r8d; bInitialState
0x180106c29  xor     ecx, ecx; lpEventAttributes
0x180106c2b  lea     edx, [r9+1]; bManualReset
0x180106c2f  call    cs:__imp_CreateEventW
0x180106c35  mov     cs:qword_1802A0768, rax
0x180106c3c  test    rax, rax
0x180106c3f  jz      short loc_180106C65
0x180106c41  xor     ecx, ecx
0x180106c43  call    __scrt_initialize_onexit_tables
0x180106c48  test    al, al
0x180106c4a  jz      short loc_180106C65
0x180106c4c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180106c53  call    atexit
0x180106c58  mov     rbx, [rsp+28h+arg_0]
0x180106c5d  xor     eax, eax
0x180106c5f  add     rsp, 20h
0x180106c63  pop     rdi
0x180106c64  retn
0x180106c65  mov     ecx, 7
0x180106c6a  call    __scrt_fastfail
```
