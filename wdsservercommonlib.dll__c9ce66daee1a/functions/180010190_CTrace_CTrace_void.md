# CTrace::CTrace(void)

- ea: `0x180010190`
- end: `0x1800102df`
- name: `??0CTrace@@QEAA@XZ`
- size: `335`
- prototype: `CTrace *__fastcall(CTrace *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010190`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180010223`
- `KERNEL32!GetProcAddress` at `0x180010240`
- `KERNEL32!GetProcAddress` at `0x18001025d`
- `KERNEL32!GetProcAddress` at `0x18001027a`
- `KERNEL32!GetProcAddress` at `0x180010223`
- `KERNEL32!GetProcAddress` at `0x180010240`
- `KERNEL32!GetProcAddress` at `0x18001025d`
- `KERNEL32!GetProcAddress` at `0x18001027a`
- `KERNEL32!GetModuleHandleW` at `0x180010201`
- `KERNEL32!GetModuleHandleW` at `0x180010201`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800101b5`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800101d9`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800101b5`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800101d9`

## string_xrefs

- `0x18001024c`: `EventWrite`
- `0x180010269`: `EventWriteTransfer`

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
  if ( !qword_180049D60 )
  {
    ModuleHandleW = GetModuleHandleW(L"advapi32");
    v3 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      qword_180049D60 = (__int64)GetProcAddress(ModuleHandleW, "EventRegister");
      qword_180049D58 = (__int64)GetProcAddress(v3, "EventUnregister");
      qword_180049D50 = (__int64)GetProcAddress(v3, "EventWrite");
      ProcAddress = GetProcAddress(v3, "EventWriteTransfer");
      qword_180049D48 = (__int64)ProcAddress;
      if ( !qword_180049D60 || !qword_180049D58 || !ProcAddress || !qword_180049D50 )
      {
        qword_180049D60 = 0;
        qword_180049D58 = 0;
        qword_180049D50 = 0;
        qword_180049D48 = 0;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180010190  mov     [rsp+arg_0], rbx
0x180010195  push    rdi
0x180010196  sub     rsp, 20h
0x18001019a  and     qword ptr [rcx], 0
0x18001019e  mov     rbx, rcx
0x1800101a1  and     dword ptr [rcx+8], 0
0x1800101a5  xor     r8d, r8d; nSize
0x1800101a8  and     dword ptr [rcx+0Ch], 0
0x1800101ac  xor     edx, edx; lpBuffer
0x1800101ae  lea     rcx, Name; "WDS_TRACING_DEBUGGER_OUTPUT"
0x1800101b5  call    cs:__imp_GetEnvironmentVariableW
0x1800101bc  nop     dword ptr [rax+rax+00h]
0x1800101c1  mov     edi, 1
0x1800101c6  test    eax, eax
0x1800101c8  jz      short loc_1800101CD
0x1800101ca  mov     [rbx+8], edi
0x1800101cd  xor     r8d, r8d; nSize
0x1800101d0  lea     rcx, aWdsTracingCons; "WDS_TRACING_CONSOLE_OUTPUT"
0x1800101d7  xor     edx, edx; lpBuffer
0x1800101d9  call    cs:__imp_GetEnvironmentVariableW
0x1800101e0  nop     dword ptr [rax+rax+00h]
0x1800101e5  test    eax, eax
0x1800101e7  jz      short loc_1800101EC
0x1800101e9  mov     [rbx+0Ch], edi
0x1800101ec  cmp     cs:qword_180049D60, 0
0x1800101f4  jnz     loc_1800102D0
0x1800101fa  lea     rcx, aAdvapi32; "advapi32"
0x180010201  call    cs:__imp_GetModuleHandleW
0x180010208  nop     dword ptr [rax+rax+00h]
0x18001020d  mov     rdi, rax
0x180010210  test    rax, rax
0x180010213  jz      loc_1800102D0
0x180010219  lea     rdx, aEventregister; "EventRegister"
0x180010220  mov     rcx, rax; hModule
0x180010223  call    cs:__imp_GetProcAddress
0x18001022a  nop     dword ptr [rax+rax+00h]
0x18001022f  lea     rdx, aEventunregiste; "EventUnregister"
0x180010236  mov     rcx, rdi; hModule
0x180010239  mov     cs:qword_180049D60, rax
0x180010240  call    cs:__imp_GetProcAddress
0x180010247  nop     dword ptr [rax+rax+00h]
0x18001024c  lea     rdx, aEventwrite; "EventWrite"
0x180010253  mov     rcx, rdi; hModule
0x180010256  mov     cs:qword_180049D58, rax
0x18001025d  call    cs:__imp_GetProcAddress
0x180010264  nop     dword ptr [rax+rax+00h]
0x180010269  lea     rdx, aEventwritetran; "EventWriteTransfer"
0x180010270  mov     rcx, rdi; hModule
0x180010273  mov     cs:qword_180049D50, rax
0x18001027a  call    cs:__imp_GetProcAddress
0x180010281  nop     dword ptr [rax+rax+00h]
0x180010286  cmp     cs:qword_180049D60, 0
0x18001028e  mov     cs:qword_180049D48, rax
0x180010295  jz      short loc_1800102B0
0x180010297  cmp     cs:qword_180049D58, 0
0x18001029f  jz      short loc_1800102B0
0x1800102a1  test    rax, rax
0x1800102a4  jz      short loc_1800102B0
0x1800102a6  cmp     cs:qword_180049D50, 0
0x1800102ae  jnz     short loc_1800102D0
0x1800102b0  and     cs:qword_180049D60, 0
0x1800102b8  and     cs:qword_180049D58, 0
0x1800102c0  and     cs:qword_180049D50, 0
0x1800102c8  and     cs:qword_180049D48, 0
0x1800102d0  mov     rax, rbx
0x1800102d3  mov     rbx, [rsp+28h+arg_0]
0x1800102d8  add     rsp, 20h
0x1800102dc  pop     rdi
0x1800102dd  retn
```
