# CTrace::CTrace(void)

- ea: `0x180010d50`
- end: `0x180010e9f`
- name: `??0CTrace@@QEAA@XZ`
- size: `335`
- prototype: `CTrace *__fastcall(CTrace *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010d50`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010de3`
- `KERNEL32!GetProcAddress` at `0x180010e00`
- `KERNEL32!GetProcAddress` at `0x180010e1d`
- `KERNEL32!GetProcAddress` at `0x180010e3a`
- `KERNEL32!GetProcAddress` at `0x180010de3`
- `KERNEL32!GetProcAddress` at `0x180010e00`
- `KERNEL32!GetProcAddress` at `0x180010e1d`
- `KERNEL32!GetProcAddress` at `0x180010e3a`
- `KERNEL32!GetModuleHandleW` at `0x180010dc1`
- `KERNEL32!GetModuleHandleW` at `0x180010dc1`
- `KERNEL32!GetEnvironmentVariableW` at `0x180010d75`
- `KERNEL32!GetEnvironmentVariableW` at `0x180010d99`
- `KERNEL32!GetEnvironmentVariableW` at `0x180010d75`
- `KERNEL32!GetEnvironmentVariableW` at `0x180010d99`

## string_xrefs

- `0x180010e0c`: `EventWrite`
- `0x180010e29`: `EventWriteTransfer`

## pseudocode

```c
CTrace *__fastcall CTrace::CTrace(CTrace *this)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v3; // rdi
  FARPROC ProcAddress; // rax

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = 0;
  if ( GetEnvironmentVariableW(L"WDS_TRACING_DEBUGGER_OUTPUT", 0, 0) )
    *((_DWORD *)this + 2) = 1;
  if ( GetEnvironmentVariableW(L"WDS_TRACING_CONSOLE_OUTPUT", 0, 0) )
    *((_DWORD *)this + 3) = 1;
  if ( !qword_18004BE60 )
  {
    ModuleHandleW = GetModuleHandleW(L"advapi32");
    v3 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      qword_18004BE60 = (__int64)GetProcAddress(ModuleHandleW, "EventRegister");
      qword_18004BE58 = (__int64)GetProcAddress(v3, "EventUnregister");
      qword_18004BE50 = (__int64)GetProcAddress(v3, "EventWrite");
      ProcAddress = GetProcAddress(v3, "EventWriteTransfer");
      qword_18004BE48 = (__int64)ProcAddress;
      if ( !qword_18004BE60 || !qword_18004BE58 || !ProcAddress || !qword_18004BE50 )
      {
        qword_18004BE60 = 0;
        qword_18004BE58 = 0;
        qword_18004BE50 = 0;
        qword_18004BE48 = 0;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180010d50  mov     [rsp+arg_0], rbx
0x180010d55  push    rdi
0x180010d56  sub     rsp, 20h
0x180010d5a  and     qword ptr [rcx], 0
0x180010d5e  mov     rbx, rcx
0x180010d61  and     dword ptr [rcx+8], 0
0x180010d65  xor     r8d, r8d; nSize
0x180010d68  and     dword ptr [rcx+0Ch], 0
0x180010d6c  xor     edx, edx; lpBuffer
0x180010d6e  lea     rcx, Name; "WDS_TRACING_DEBUGGER_OUTPUT"
0x180010d75  call    cs:__imp_GetEnvironmentVariableW
0x180010d7c  nop     dword ptr [rax+rax+00h]
0x180010d81  mov     edi, 1
0x180010d86  test    eax, eax
0x180010d88  jz      short loc_180010D8D
0x180010d8a  mov     [rbx+8], edi
0x180010d8d  xor     r8d, r8d; nSize
0x180010d90  lea     rcx, aWdsTracingCons; "WDS_TRACING_CONSOLE_OUTPUT"
0x180010d97  xor     edx, edx; lpBuffer
0x180010d99  call    cs:__imp_GetEnvironmentVariableW
0x180010da0  nop     dword ptr [rax+rax+00h]
0x180010da5  test    eax, eax
0x180010da7  jz      short loc_180010DAC
0x180010da9  mov     [rbx+0Ch], edi
0x180010dac  cmp     cs:qword_18004BE60, 0
0x180010db4  jnz     loc_180010E90
0x180010dba  lea     rcx, aAdvapi32; "advapi32"
0x180010dc1  call    cs:__imp_GetModuleHandleW
0x180010dc8  nop     dword ptr [rax+rax+00h]
0x180010dcd  mov     rdi, rax
0x180010dd0  test    rax, rax
0x180010dd3  jz      loc_180010E90
0x180010dd9  lea     rdx, aEventregister; "EventRegister"
0x180010de0  mov     rcx, rax; hModule
0x180010de3  call    cs:__imp_GetProcAddress
0x180010dea  nop     dword ptr [rax+rax+00h]
0x180010def  lea     rdx, aEventunregiste; "EventUnregister"
0x180010df6  mov     rcx, rdi; hModule
0x180010df9  mov     cs:qword_18004BE60, rax
0x180010e00  call    cs:__imp_GetProcAddress
0x180010e07  nop     dword ptr [rax+rax+00h]
0x180010e0c  lea     rdx, aEventwrite; "EventWrite"
0x180010e13  mov     rcx, rdi; hModule
0x180010e16  mov     cs:qword_18004BE58, rax
0x180010e1d  call    cs:__imp_GetProcAddress
0x180010e24  nop     dword ptr [rax+rax+00h]
0x180010e29  lea     rdx, aEventwritetran; "EventWriteTransfer"
0x180010e30  mov     rcx, rdi; hModule
0x180010e33  mov     cs:qword_18004BE50, rax
0x180010e3a  call    cs:__imp_GetProcAddress
0x180010e41  nop     dword ptr [rax+rax+00h]
0x180010e46  cmp     cs:qword_18004BE60, 0
0x180010e4e  mov     cs:qword_18004BE48, rax
0x180010e55  jz      short loc_180010E70
0x180010e57  cmp     cs:qword_18004BE58, 0
0x180010e5f  jz      short loc_180010E70
0x180010e61  test    rax, rax
0x180010e64  jz      short loc_180010E70
0x180010e66  cmp     cs:qword_18004BE50, 0
0x180010e6e  jnz     short loc_180010E90
0x180010e70  and     cs:qword_18004BE60, 0
0x180010e78  and     cs:qword_18004BE58, 0
0x180010e80  and     cs:qword_18004BE50, 0
0x180010e88  and     cs:qword_18004BE48, 0
0x180010e90  mov     rax, rbx
0x180010e93  mov     rbx, [rsp+28h+arg_0]
0x180010e98  add     rsp, 20h
0x180010e9c  pop     rdi
0x180010e9d  retn
```
