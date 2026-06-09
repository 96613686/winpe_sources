# __scrt_initialize_thread_safe_statics

- ea: `0x100452a38`
- end: `0x100452b08`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x10045266c`
- `0x10045283c`
- `0x100452a38`
- `0x100452fe0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100452a88`
- `KERNEL32!GetProcAddress` at `0x100452a9b`
- `KERNEL32!GetProcAddress` at `0x100452a88`
- `KERNEL32!GetProcAddress` at `0x100452a9b`
- `KERNEL32!GetModuleHandleW` at `0x100452a5b`
- `KERNEL32!GetModuleHandleW` at `0x100452a70`
- `KERNEL32!GetModuleHandleW` at `0x100452a5b`
- `KERNEL32!GetModuleHandleW` at `0x100452a70`
- `KERNEL32!CreateEventW` at `0x100452ac7`
- `KERNEL32!CreateEventW` at `0x100452ac7`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x100452a4e`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x100452a4e`

## string_xrefs

- `0x100452a54`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x100452a69`: `kernel32.dll`

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
    qword_1004A35A8 = (__int64)ProcAddress;
    qword_1004A35B0 = (__int64)v2;
  }
  else
  {
    hHandle = CreateEventW(0, 1, 0, 0);
    if ( !hHandle )
      goto LABEL_9;
  }
  if ( !(unsigned __int8)_scrt_initialize_onexit_tables(0) )
  {
LABEL_9:
    _scrt_fastfail(7);
    __debugbreak();
  }
  atexit(_scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x100452a38  mov     [rsp+arg_0], rbx
0x100452a3d  push    rdi
0x100452a3e  sub     rsp, 20h
0x100452a42  mov     edx, 0FA0h; dwSpinCount
0x100452a47  lea     rcx, CriticalSection; lpCriticalSection
0x100452a4e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x100452a54  lea     rcx, aApiMsWinCoreSy
0x100452a5b  call    cs:__imp_GetModuleHandleW
0x100452a61  mov     rbx, rax
0x100452a64  test    rax, rax
0x100452a67  jnz     short loc_100452A7E
0x100452a69  lea     rcx, aKernel32Dll_0
0x100452a70  call    cs:__imp_GetModuleHandleW
0x100452a76  mov     rbx, rax
0x100452a79  test    rax, rax
0x100452a7c  jz      short loc_100452AFD
0x100452a7e  lea     rdx, aSleepcondition
0x100452a85  mov     rcx, rbx; hModule
0x100452a88  call    cs:__imp_GetProcAddress
0x100452a8e  lea     rdx, aWakeallconditi
0x100452a95  mov     rcx, rbx; hModule
0x100452a98  mov     rdi, rax
0x100452a9b  call    cs:__imp_GetProcAddress
0x100452aa1  test    rdi, rdi
0x100452aa4  jz      short loc_100452ABB
0x100452aa6  test    rax, rax
0x100452aa9  jz      short loc_100452ABB
0x100452aab  mov     cs:qword_1004A35A8, rdi
0x100452ab2  mov     cs:qword_1004A35B0, rax
0x100452ab9  jmp     short loc_100452AD9
0x100452abb  xor     r9d, r9d; lpName
0x100452abe  xor     r8d, r8d; bInitialState
0x100452ac1  xor     ecx, ecx; lpEventAttributes
0x100452ac3  lea     edx, [r9+1]; bManualReset
0x100452ac7  call    cs:__imp_CreateEventW
0x100452acd  mov     cs:hHandle, rax
0x100452ad4  test    rax, rax
0x100452ad7  jz      short loc_100452AFD
0x100452ad9  xor     ecx, ecx
0x100452adb  call    __scrt_initialize_onexit_tables
0x100452ae0  test    al, al
0x100452ae2  jz      short loc_100452AFD
0x100452ae4  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x100452aeb  call    atexit
0x100452af0  mov     rbx, [rsp+28h+arg_0]
0x100452af5  xor     eax, eax
0x100452af7  add     rsp, 20h
0x100452afb  pop     rdi
0x100452afc  retn
0x100452afd  mov     ecx, 7
0x100452b02  call    __scrt_fastfail
0x100452b07  int     3; Trap to Debugger
```
