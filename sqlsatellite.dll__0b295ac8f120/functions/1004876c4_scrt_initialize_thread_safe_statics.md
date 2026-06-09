# __scrt_initialize_thread_safe_statics

- ea: `0x1004876c4`
- end: `0x100487794`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x100486e58`
- `0x100487028`
- `0x1004876c4`
- `0x1004879b4`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1004876da`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1004876da`
- `KERNEL32!CreateEventW` at `0x100487753`
- `KERNEL32!CreateEventW` at `0x100487753`
- `KERNEL32!GetProcAddress` at `0x100487714`
- `KERNEL32!GetProcAddress` at `0x100487727`
- `KERNEL32!GetProcAddress` at `0x100487714`
- `KERNEL32!GetProcAddress` at `0x100487727`
- `KERNEL32!GetModuleHandleW` at `0x1004876e7`
- `KERNEL32!GetModuleHandleW` at `0x1004876fc`
- `KERNEL32!GetModuleHandleW` at `0x1004876e7`
- `KERNEL32!GetModuleHandleW` at `0x1004876fc`

## string_xrefs

- `0x1004876e0`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x1004876f5`: `kernel32.dll`

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
    qword_100511288 = (__int64)ProcAddress;
    qword_100511290 = (__int64)v2;
    goto LABEL_7;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x100487793LL);
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
0x1004876c4  mov     [rsp+arg_0], rbx
0x1004876c9  push    rdi
0x1004876ca  sub     rsp, 20h
0x1004876ce  mov     edx, 0FA0h; dwSpinCount
0x1004876d3  lea     rcx, CriticalSection; lpCriticalSection
0x1004876da  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1004876e0  lea     rcx, aApiMsWinCoreSy; "api-ms-win-core-synch-l1-2-0.dll"
0x1004876e7  call    cs:__imp_GetModuleHandleW
0x1004876ed  mov     rbx, rax
0x1004876f0  test    rax, rax
0x1004876f3  jnz     short loc_10048770A
0x1004876f5  lea     rcx, aKernel32Dll_1; "kernel32.dll"
0x1004876fc  call    cs:__imp_GetModuleHandleW
0x100487702  mov     rbx, rax
0x100487705  test    rax, rax
0x100487708  jz      short loc_100487789
0x10048770a  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x100487711  mov     rcx, rbx; hModule
0x100487714  call    cs:__imp_GetProcAddress
0x10048771a  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x100487721  mov     rcx, rbx; hModule
0x100487724  mov     rdi, rax
0x100487727  call    cs:__imp_GetProcAddress
0x10048772d  test    rdi, rdi
0x100487730  jz      short loc_100487747
0x100487732  test    rax, rax
0x100487735  jz      short loc_100487747
0x100487737  mov     cs:qword_100511288, rdi
0x10048773e  mov     cs:qword_100511290, rax
0x100487745  jmp     short loc_100487765
0x100487747  xor     r9d, r9d; lpName
0x10048774a  xor     r8d, r8d; bInitialState
0x10048774d  xor     ecx, ecx; lpEventAttributes
0x10048774f  lea     edx, [r9+1]; bManualReset
0x100487753  call    cs:__imp_CreateEventW
0x100487759  mov     cs:hHandle, rax
0x100487760  test    rax, rax
0x100487763  jz      short loc_100487789
0x100487765  xor     ecx, ecx
0x100487767  call    __scrt_initialize_onexit_tables
0x10048776c  test    al, al
0x10048776e  jz      short loc_100487789
0x100487770  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x100487777  call    atexit
0x10048777c  mov     rbx, [rsp+28h+arg_0]
0x100487781  xor     eax, eax
0x100487783  add     rsp, 20h
0x100487787  pop     rdi
0x100487788  retn
0x100487789  mov     ecx, 7
0x10048778e  call    __scrt_fastfail
```
