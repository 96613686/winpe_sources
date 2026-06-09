# _dynamic_initializer_for__s_Trace__

- ea: `0x180001100`
- end: `0x180001228`
- name: `_dynamic_initializer_for__s_Trace__`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001100`
- `0x18001575c`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x180001112`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000113a`
- `KERNEL32!GetEnvironmentVariableW` at `0x180001112`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000113a`
- `KERNEL32!GetProcAddress` at `0x180001182`
- `KERNEL32!GetProcAddress` at `0x180001199`
- `KERNEL32!GetProcAddress` at `0x1800011b0`
- `KERNEL32!GetProcAddress` at `0x1800011c7`
- `KERNEL32!GetProcAddress` at `0x180001182`
- `KERNEL32!GetProcAddress` at `0x180001199`
- `KERNEL32!GetProcAddress` at `0x1800011b0`
- `KERNEL32!GetProcAddress` at `0x1800011c7`
- `KERNEL32!GetModuleHandleW` at `0x180001166`
- `KERNEL32!GetModuleHandleW` at `0x180001166`

## string_xrefs

- `0x18000119f`: `EventWrite`
- `0x1800011b6`: `EventWriteTransfer`

## pseudocode

```c
int dynamic_initializer_for__s_Trace__()
{
  DWORD EnvironmentVariableW; // eax
  int v1; // ecx
  DWORD v2; // eax
  int v3; // ecx
  HMODULE ModuleHandleW; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rax

  EnvironmentVariableW = GetEnvironmentVariableW(L"WDS_TRACING_DEBUGGER_OUTPUT", 0, 0);
  v1 = dword_18001DF10;
  if ( EnvironmentVariableW )
    v1 = 1;
  dword_18001DF10 = v1;
  v2 = GetEnvironmentVariableW(L"WDS_TRACING_CONSOLE_OUTPUT", 0, 0);
  v3 = dword_18001DF14;
  if ( v2 )
    v3 = 1;
  dword_18001DF14 = v3;
  if ( !qword_18001DD80 )
  {
    ModuleHandleW = GetModuleHandleW(L"advapi32");
    v5 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      qword_18001DD80 = (__int64)GetProcAddress(ModuleHandleW, "EventRegister");
      qword_18001DD78 = (__int64)GetProcAddress(v5, "EventUnregister");
      qword_18001DD70 = (__int64)GetProcAddress(v5, "EventWrite");
      ProcAddress = GetProcAddress(v5, "EventWriteTransfer");
      qword_18001DD68 = (__int64)ProcAddress;
      if ( !qword_18001DD80 || !qword_18001DD78 || !ProcAddress || !qword_18001DD70 )
      {
        qword_18001DD80 = 0;
        qword_18001DD78 = 0;
        qword_18001DD70 = 0;
        qword_18001DD68 = 0;
      }
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__s_Trace__);
}

```

## disassembly

```asm
0x180001100  push    rbx
0x180001102  sub     rsp, 20h
0x180001106  xor     r8d, r8d; nSize
0x180001109  lea     rcx, Name; "WDS_TRACING_DEBUGGER_OUTPUT"
0x180001110  xor     edx, edx; lpBuffer
0x180001112  call    cs:__imp_GetEnvironmentVariableW
0x180001118  mov     ecx, cs:dword_18001DF10
0x18000111e  mov     ebx, 1
0x180001123  test    eax, eax
0x180001125  cmovnz  ecx, ebx
0x180001128  xor     r8d, r8d; nSize
0x18000112b  mov     cs:dword_18001DF10, ecx
0x180001131  xor     edx, edx; lpBuffer
0x180001133  lea     rcx, aWdsTracingCons; "WDS_TRACING_CONSOLE_OUTPUT"
0x18000113a  call    cs:__imp_GetEnvironmentVariableW
0x180001140  mov     ecx, cs:dword_18001DF14
0x180001146  test    eax, eax
0x180001148  cmovnz  ecx, ebx
0x18000114b  cmp     cs:qword_18001DD80, 0
0x180001153  mov     cs:dword_18001DF14, ecx
0x180001159  jnz     loc_180001217
0x18000115f  lea     rcx, ModuleName; "advapi32"
0x180001166  call    cs:__imp_GetModuleHandleW
0x18000116c  mov     rbx, rax
0x18000116f  test    rax, rax
0x180001172  jz      loc_180001217
0x180001178  lea     rdx, ProcName; "EventRegister"
0x18000117f  mov     rcx, rax; hModule
0x180001182  call    cs:__imp_GetProcAddress
0x180001188  lea     rdx, aEventunregiste; "EventUnregister"
0x18000118f  mov     rcx, rbx; hModule
0x180001192  mov     cs:qword_18001DD80, rax
0x180001199  call    cs:__imp_GetProcAddress
0x18000119f  lea     rdx, aEventwrite; "EventWrite"
0x1800011a6  mov     rcx, rbx; hModule
0x1800011a9  mov     cs:qword_18001DD78, rax
0x1800011b0  call    cs:__imp_GetProcAddress
0x1800011b6  lea     rdx, aEventwritetran; "EventWriteTransfer"
0x1800011bd  mov     rcx, rbx; hModule
0x1800011c0  mov     cs:qword_18001DD70, rax
0x1800011c7  call    cs:__imp_GetProcAddress
0x1800011cd  cmp     cs:qword_18001DD80, 0
0x1800011d5  mov     cs:qword_18001DD68, rax
0x1800011dc  jz      short loc_1800011F7
0x1800011de  cmp     cs:qword_18001DD78, 0
0x1800011e6  jz      short loc_1800011F7
0x1800011e8  test    rax, rax
0x1800011eb  jz      short loc_1800011F7
0x1800011ed  cmp     cs:qword_18001DD70, 0
0x1800011f5  jnz     short loc_180001217
0x1800011f7  and     cs:qword_18001DD80, 0
0x1800011ff  and     cs:qword_18001DD78, 0
0x180001207  and     cs:qword_18001DD70, 0
0x18000120f  and     cs:qword_18001DD68, 0
0x180001217  lea     rcx, _dynamic_atexit_destructor_for__s_Trace__
0x18000121e  add     rsp, 20h
0x180001222  pop     rbx
0x180001223  jmp     atexit
```
