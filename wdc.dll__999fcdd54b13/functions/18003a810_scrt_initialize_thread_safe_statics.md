# __scrt_initialize_thread_safe_statics

- ea: `0x18003a810`
- end: `0x18003a8e0`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18003a5a0`
- `0x18003a770`
- `0x18003a810`
- `0x18003abc8`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003a833`
- `KERNEL32!GetModuleHandleW` at `0x18003a848`
- `KERNEL32!GetModuleHandleW` at `0x18003a833`
- `KERNEL32!GetModuleHandleW` at `0x18003a848`
- `KERNEL32!GetProcAddress` at `0x18003a860`
- `KERNEL32!GetProcAddress` at `0x18003a873`
- `KERNEL32!GetProcAddress` at `0x18003a860`
- `KERNEL32!GetProcAddress` at `0x18003a873`
- `KERNEL32!CreateEventW` at `0x18003a89f`
- `KERNEL32!CreateEventW` at `0x18003a89f`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18003a826`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18003a826`

## string_xrefs

- `0x18003a82c`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x18003a841`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_1800B2768, 0xFA0u);
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
    qword_1800B2790 = (__int64)ProcAddress;
    qword_1800B2798 = (__int64)v2;
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
0x18003a810  mov     [rsp+arg_0], rbx
0x18003a815  push    rdi
0x18003a816  sub     rsp, 20h
0x18003a81a  mov     edx, 0FA0h; dwSpinCount
0x18003a81f  lea     rcx, stru_1800B2768; lpCriticalSection
0x18003a826  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003a82c  lea     rcx, ModuleName; "api-ms-win-core-synch-l1-2-0.dll"
0x18003a833  call    cs:__imp_GetModuleHandleW
0x18003a839  mov     rbx, rax
0x18003a83c  test    rax, rax
0x18003a83f  jnz     short loc_18003A856
0x18003a841  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18003a848  call    cs:__imp_GetModuleHandleW
0x18003a84e  mov     rbx, rax
0x18003a851  test    rax, rax
0x18003a854  jz      short loc_18003A8D5
0x18003a856  lea     rdx, ProcName; "SleepConditionVariableCS"
0x18003a85d  mov     rcx, rbx; hModule
0x18003a860  call    cs:__imp_GetProcAddress
0x18003a866  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18003a86d  mov     rcx, rbx; hModule
0x18003a870  mov     rdi, rax
0x18003a873  call    cs:__imp_GetProcAddress
0x18003a879  test    rdi, rdi
0x18003a87c  jz      short loc_18003A893
0x18003a87e  test    rax, rax
0x18003a881  jz      short loc_18003A893
0x18003a883  mov     cs:qword_1800B2790, rdi
0x18003a88a  mov     cs:qword_1800B2798, rax
0x18003a891  jmp     short loc_18003A8B1
0x18003a893  xor     r9d, r9d; lpName
0x18003a896  xor     r8d, r8d; bInitialState
0x18003a899  xor     ecx, ecx; lpEventAttributes
0x18003a89b  lea     edx, [r9+1]; bManualReset
0x18003a89f  call    cs:__imp_CreateEventW
0x18003a8a5  mov     cs:hHandle, rax
0x18003a8ac  test    rax, rax
0x18003a8af  jz      short loc_18003A8D5
0x18003a8b1  xor     ecx, ecx
0x18003a8b3  call    __scrt_initialize_onexit_tables
0x18003a8b8  test    al, al
0x18003a8ba  jz      short loc_18003A8D5
0x18003a8bc  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x18003a8c3  call    atexit
0x18003a8c8  mov     rbx, [rsp+28h+arg_0]
0x18003a8cd  xor     eax, eax
0x18003a8cf  add     rsp, 20h
0x18003a8d3  pop     rdi
0x18003a8d4  retn
0x18003a8d5  mov     ecx, 7
0x18003a8da  call    __scrt_fastfail
```
