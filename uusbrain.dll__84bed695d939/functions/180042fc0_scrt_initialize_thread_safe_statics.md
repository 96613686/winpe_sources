# __scrt_initialize_thread_safe_statics

- ea: `0x180042fc0`
- end: `0x180043090`
- name: `__scrt_initialize_thread_safe_statics`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800429d4`
- `0x180042ba4`
- `0x180042fc0`
- `0x1800437a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043010`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043023`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043010`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043023`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042fe3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042ff8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042fe3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180042ff8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180042fd6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180042fd6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004304f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004304f`

## string_xrefs

- `0x180042fdc`: `api-ms-win-core-synch-l1-2-0.dll`
- `0x180042ff1`: `kernel32.dll`

## pseudocode

```c
__int64 _scrt_initialize_thread_safe_statics()
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v2; // rax

  InitializeCriticalSectionAndSpinCount(&stru_180062C98, 0xFA0u);
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
    qword_180062CC0 = (__int64)ProcAddress;
    qword_180062CC8 = (__int64)v2;
    goto LABEL_7;
  }
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
LABEL_9:
    _scrt_fastfail(7);
    JUMPOUT(0x18004308FLL);
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
0x180042fc0  mov     [rsp+arg_0], rbx
0x180042fc5  push    rdi
0x180042fc6  sub     rsp, 20h
0x180042fca  mov     edx, 0FA0h; dwSpinCount
0x180042fcf  lea     rcx, stru_180062C98; lpCriticalSection
0x180042fd6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180042fdc  lea     rcx, aApiMsWinCoreSy_3; "api-ms-win-core-synch-l1-2-0.dll"
0x180042fe3  call    cs:__imp_GetModuleHandleW
0x180042fe9  mov     rbx, rax
0x180042fec  test    rax, rax
0x180042fef  jnz     short loc_180043006
0x180042ff1  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180042ff8  call    cs:__imp_GetModuleHandleW
0x180042ffe  mov     rbx, rax
0x180043001  test    rax, rax
0x180043004  jz      short loc_180043085
0x180043006  lea     rdx, aSleepcondition; "SleepConditionVariableCS"
0x18004300d  mov     rcx, rbx; hModule
0x180043010  call    cs:__imp_GetProcAddress
0x180043016  lea     rdx, aWakeallconditi; "WakeAllConditionVariable"
0x18004301d  mov     rcx, rbx; hModule
0x180043020  mov     rdi, rax
0x180043023  call    cs:__imp_GetProcAddress
0x180043029  test    rdi, rdi
0x18004302c  jz      short loc_180043043
0x18004302e  test    rax, rax
0x180043031  jz      short loc_180043043
0x180043033  mov     cs:qword_180062CC0, rdi
0x18004303a  mov     cs:qword_180062CC8, rax
0x180043041  jmp     short loc_180043061
0x180043043  xor     r9d, r9d; lpName
0x180043046  xor     r8d, r8d; bInitialState
0x180043049  xor     ecx, ecx; lpEventAttributes
0x18004304b  lea     edx, [r9+1]; bManualReset
0x18004304f  call    cs:__imp_CreateEventW
0x180043055  mov     cs:hHandle, rax
0x18004305c  test    rax, rax
0x18004305f  jz      short loc_180043085
0x180043061  xor     ecx, ecx
0x180043063  call    __scrt_initialize_onexit_tables
0x180043068  test    al, al
0x18004306a  jz      short loc_180043085
0x18004306c  lea     rcx, __scrt_uninitialize_thread_safe_statics; void (__cdecl *)()
0x180043073  call    atexit
0x180043078  mov     rbx, [rsp+28h+arg_0]
0x18004307d  xor     eax, eax
0x18004307f  add     rsp, 20h
0x180043083  pop     rdi
0x180043084  retn
0x180043085  mov     ecx, 7
0x18004308a  call    __scrt_fastfail
```
